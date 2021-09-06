---
title: الاتصال بحساب Azure Data Lake Storage باستخدام كيان خدمة
description: استخدم كيان خدمة من Azure للاتصال بمستودع بياناتك.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461132"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>الاتصال بحساب Azure Data Lake Storage باستخدام كيان خدمة من Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
يجب أن تكون دائمًا الأدوات المؤتمتة التي تستخدم خدمات Azure ذات أذونات مقيدة. بدلاً من قيام التطبيقات بتسجيل الدخول كمستخدم له امتيازات كاملة، يقدم Azure كيانات الخدمة. اقرأ لمعرفة كيفية توصيل Dynamics 365 Customer Insights بحساب Azure Data Lake Storage باستخدام كيان خدمة من Azure بدلاً من مفاتيح حساب التخزين. 

يمكنك استخدام كيان الخدمة كي تتمكن من [إضافة نموذج بيانات عامة أو تحريره كمصدر بيانات](connect-common-data-model.md) أو [إنشاء بيئة أو تحديثها](get-started-paid.md) بطريقة آمنة.<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - بالنسبة إلى حساب Data Lake Storage account الذي سيستخدم<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> كيان الخدمة، يجب أن تكون [مساحة الأسماء الهرمية فيه ممكّنة](/azure/storage/blobs/data-lake-storage-namespace).
> - تحتاج إلى أذونات المسؤول لاشتراكك في Azure لإنشاء كيان الخدمة.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>إنشاء كيان خدمة من Azure لـ Customer Insights

قبل إنشاء كيان خدمة جديد لرؤى الجمهور أو رؤى المشاركة، تحقق مما إذا كان موجودًا بالفعل في مؤسستك.

### <a name="look-for-an-existing-service-principal"></a>البحث عن كيان خدمة موجود

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com) وسجل دخولك إلى مؤسستك.

2. من **خدمات Azure**، حدد **Azure Active Directory**.

3. ضمن **إدارة**، حدد **تطبيقات المؤسسة**.

4. البحث عن معرف<!--note from editor: Via Microsoft Writing Style Guide.--> تطبيق Microsoft:
   - رؤى الجمهور: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` بالاسم `Dynamics 365 AI for Customer Insights`
   - رؤى المشاركة: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` بالاسم `Dynamics 365 AI for Customer Insights engagement insights`

5. إذا وجدت سجلاً مطابقًا، فهذا يعني أن كيان الخدمة موجود بالفعل. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="لقطة شاشة تُظهر كيان خدمة موجودًا.":::
   
6. إذا لم يتم إرجاع أي نتائج، فيمكنك إنشاء كيان خدمة جديد.

>[!NOTE]
>لاستخدام إمكانيات Dynamics 365 Customer Insights الكاملة، نقترح بأن تقوم بإضافة التطبيقين إلى كيان الخدمة.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>إنشاء كيان خدمة جديد
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. ثبّت الإصدار الأخير من Azure Active Directory PowerShell for Graph. لمزيد من المعلومات، انتقل إلى [تثبيت Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. على الكمبيوتر، حدد مفتاح Windows على لوحة المفاتيح وابحث عن **Windows PowerShell** ثم حدد **تشغيل كمسؤول**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. في نافذة PowerShell التي تفتح، أدخل `Install-Module AzureAD`.

2. أنشئ كيان الخدمة لـ Customer Insights باستخدام الوحدة النمطية Azure AD PowerShell.

   1. في نافذة PowerShell، أدخل `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. استبدل *"[معرف المستأجر]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> بالمعرف الفعلي للمستأجر حيث تريد إنشاء كيان الخدمة. معلمة اسم البيئة، `AzureEnvironmentName`، اختيارية.
  
   1. أدخل `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. يقوم هذا الأمر بإنشاء كيان الخدمة لرؤى الجمهور على المستأجر المحدد. 

   1. أدخل `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. ينشئ هذا الأمر كيان الخدمة لرؤى المشاركة<!--note from editor: Edit okay?--> في المستأجر المحدد.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>منح أذونات لكيان الخدمة للوصول إلى حساب التخزين

انتقل إلى مدخل Azure لمنح أذونات لكيان الخدمة الخاص بحساب التخزين الذي ترغب في استخدامه في رؤى الجمهور.

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com) وسجل دخولك إلى مؤسستك.

1. افتح حساب التخزين الذي تريد أن يدخل إليه كيان الخدمة لرؤى الجمهور.

1. من الجزء الأيسر، حدد **عنصر تحكم الوصول (IAM)**، ثم حدد **إضافة** > **إضافة تعيين الدور**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="لقطة شاشة تُظهر مدخل Azure أثناء إضافة تعيين دور.":::

1. في جزء **إضافة تعيين الدور**، قم بتعيين الخصائص التالية:
   - الدور: **المساهم في بيانات مخزن البيانات الثنائية الكبيرة**
   - تعيين الوصول إلى: **المستخدم أو المجموعة أو كيان الخدمة**
   - حدد: **Dynamics 365 AI لـ Customer Insights** و **Dynamics 365 AI لرؤى مشاركة Customer Insights** (وهما [كيانا الخدمة](#create-a-new-service-principal) اللذان أنشأتهما سابقًا في هذا الإجراء)

1.  حدد **حفظ**.

قد تستغرق فترة نشر التغييرات ما يصل إلى 15 دقيقة.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>أدخل معرف مورد Azure أو تفاصيل اشتراك Azure في مرفق حساب التخزين في رؤى الجمهور.

بإمكانك<!--note from editor: Edit suggested only if this section is optional.--> إرفاق حساب Data Lake Storage في رؤى الجمهور من أجل [تخزين بيانات الإخراج](manage-environments.md) أو [استخدامها كمصدر بيانات](connect-common-data-service-lake.md). يتيح لك هذا الخيار الاختيار بين أسلوب يستند إلى المورد أو أسلوب يستند إلى الاشتراك. وبحسب الأسلوب الذي تختاره، اتبع الإجراء في أحد الأقسام التالية.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>‏‏اتصال حساب التخزين المستند إلى الموارد

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com)، ثم قم بتسجيل الدخول إلى اشتراكك وافتح حساب التخزين.

1. في الجزء الأيسر، انتقل إلى **الإعدادات** > **خصائص**.

1. انسخ قيمة معرف مورد حساب التخزين.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="انسخ معرف مورد حساب التخزين.":::

1. في رؤى الجمهور، أدخل معرف المورد في حقل المورد المعروض على شاشة اتصال حساب التخزين.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="أدخل معلومات معرف مورد حساب التخزين.":::   

1. تابع تنفيذ الخطوات المتبقية في رؤى الجمهور لإرفاق حساب التخزين.

### <a name="subscription-based-storage-account-connection"></a>‏‏اتصال حساب التخزين المستند إلى الاشتراكات

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com)، ثم قم بتسجيل الدخول إلى اشتراكك وافتح حساب التخزين.

1. في الجزء الأيسر، انتقل إلى **الإعدادات** > **خصائص**.

1. راجع **اشتراك** حساب التخزين بالإضافة إلى **مجموعة الموارد** و **الاسم** للتأكد من أنك تحدد القيم الصحيحة في رؤى الجمهور.

1. في رؤى الجمهور، اختر القيم للحقول المناظرة عند إرفاق حساب التخزين.

1. تابع تنفيذ الخطوات المتبقية في رؤى الجمهور لإرفاق حساب التخزين.


[!INCLUDE[footer-include](../includes/footer-banner.md)]