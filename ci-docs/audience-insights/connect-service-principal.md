---
title: الاتصال بحساب Azure Data Lake Storage Gen2 بواسطة كيان خدمة
description: استخدم كيان خدمة في Azure لرؤى الجمهور للاتصال بمستودع بياناتك الخاص عند إرفاقه برؤى الجمهور.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596483"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>الاتصال بحساب Azure Data Lake Storage Gen2 بواسطة كيان خدمة Azure لرؤى الجمهور

يجب أن تكون دائمًا الأدوات المؤتمتة التي تستخدم خدمات Azure ذات أذونات مقيدة. بدلاً من قيام التطبيقات بتسجيل الدخول كمستخدم له امتيازات كاملة، يقدم Azure كيانات الخدمة. اقرأ لمعرفة كيفية توصيل رؤى الجمهور بواسطة حساب Azure Data Lake Storage Gen2 يستخدم كيان خدمة Azure بدلاً من مفاتيح حساب تخزين. 

يمكنك استخدام كيان الخدمة من أجل [إضافة أو تحرير مجلد نموذج البيانات العامة كمصدر بيانات](connect-common-data-model.md) بشكل آمن أو [إنشاء بيئة جديدة أو تحديث بيئة موجودة](manage-environments.md#create-an-environment-in-an-existing-organization).

> [!IMPORTANT]
> - يجب أن يكون حساب التخزين Azure Data Lake Gen2 الذي ينوي استخدام كيان الخدمة [ممكّنًا لاستخدام مساحة الاسم الهرمية](/azure/storage/blobs/data-lake-storage-namespace).
> - تحتاج إلى أذونات المسؤول لاشتراكك في Azure لإنشاء كيان الخدمة.

## <a name="create-azure-service-principal-for-audience-insights"></a>إنشاء كيان خدمة Azure لرؤى الجمهور‬

قبل إنشاء كيان خدمة جديد لرؤى الجمهور‬، تحقق مما إذا كان موجودًا بالفعل في مؤسستك.

### <a name="look-for-an-existing-service-principal"></a>البحث عن كيان خدمة موجود

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com) وسجل دخولك إلى مؤسستك.

2. حدد **Azure Active Directory** من خدمات Azure.

3. ضمن **إدارة**، حدد **تطبيقات المؤسسة**.

4. ابحث عن معرف تطبيق الطرف الأول لرؤى الجمهور `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` أو عن الاسم `Dynamics 365 AI for Customer Insights`.

5. إذا عثرت على سجل مطابق، فهذا يعني أن كيان الخدمة لرؤى الجمهور موجود. لا حاجة إلى إنشائه من جديد.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="لقطة شاشة تُظهر كيان الخدمة الحالي.":::
   
6. إذا لم يتم إرجاع أي نتائج، فيمكنك إنشاء كيان خدمة جديد.

### <a name="create-a-new-service-principal"></a>إنشاء كيان خدمة جديد

1. ثبّت الإصدار الأخير من **Azure Active Directory PowerShell for Graph**. لمزيد من المعلومات، راجع [تثبيت Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   - علي جهاز الكمبيوتر، حدد مفتاح Windows على لوحة المفاتيح وابحث عن **Windows PowerShell** و **تشغيل كمسؤول**.
   
   - في نافذة PowerShell التي تفتح، أدخل `Install-Module AzureAD`.

2. أنشئ كيان الخدمة لرؤى الجمهور بواسطة الوحدة النمطية Azure AD PowerShell.
   - في نافذة PowerShell، أدخل `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. استبدل "معرف المستأجر" بالمعرف الفعلي للمستأجر حيث تريد إنشاء كيان الخدمة. معلمة اسم البيئة `AzureEnvironmentName` اختيارية.
  
   - أدخل `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. يقوم هذا الأمر بإنشاء كيان الخدمة لرؤى الجمهور على المستأجر المحدد.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>منح أذونات لكيان الخدمة للوصول إلى حساب التخزين

انتقل إلى مدخل Azure لمنح أذونات لكيان الخدمة الخاص بحساب التخزين الذي ترغب في استخدامه في رؤى الجمهور.

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com) وسجل دخولك إلى مؤسستك.

1. افتح حساب التخزين الذي تريد أن يدخل إليه كيان الخدمة لرؤى الجمهور.

1. حدد **التحكم بالوصول (IAM)** من جزء التنقل، وحدد **إضافة** > **إضافة‏‎ تعيين الدور**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="لقطة شاشة تُظهر مدخل Azure أثناء إضافة تعيين الدور.":::
   
1. في الجزء **إضافة تعيين الدور**، قم بتعيين الخصائص التالية:
   - الدور: *المساهم في بيانات مخزن البيانات الثنائية الكبيرة*
   - تعيين الوصول إلى: *المستخدم أو المجموعة أو كيان الخدمة*
   - حدد: *Dynamics 365 AI for Customer Insights* ([كيان الخدمة الذي قمت بإنشائه](#create-a-new-service-principal))

1.  حدد **حفظ**.

قد تستغرق فترة نشر التغييرات ما يصل إلى 15 دقيقة.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>أدخل معرف مورد Azure أو تفاصيل اشتراك Azure في مرفق حساب التخزين في رؤى الجمهور.

قم بإرفاق حساب Azure Data Lake Storage في رؤى الجمهور [لتخزين بيانات الإخراج](manage-environments.md) أو [لاستخدامه كمصدر بيانات](connect-common-data-service-lake.md). يتيح لك تحديد خيار Azure Data Lake الاختيار بين طريقة تستند إلى الموارد أو طريقة تستند إلى الاشتراكات.

اتبع الخطوات أدناه لتقديم المعلومات المطلوبة بالطريقة المحددة.

### <a name="resource-based-storage-account-connection"></a>‏‏اتصال حساب التخزين المستند إلى الموارد

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com)، ثم قم بتسجيل الدخول إلى اشتراكك وافتح حساب التخزين.

1. انتقل إلى **الإعدادات** > **خصائص** في جزء التنقل.

1. انسخ قيمة معرف مورد حساب التخزين.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="انسخ معرف مورد حساب التخزين.":::

1. في رؤى الجمهور، أدخل معرف المورد في حقل المورد المعروض في شاشة اتصال حساب التخزين.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="أدخل معلومات معرف مورد حساب التخزين.":::   
   
1. تابع تنفيذ الخطوات المتبقية في رؤى الجمهور لإرفاق حساب التخزين.

### <a name="subscription-based-storage-account-connection"></a>‏‏اتصال حساب التخزين المستند إلى الاشتراكات

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com)، ثم قم بتسجيل الدخول إلى اشتراكك وافتح حساب التخزين.

1. انتقل إلى **الإعدادات** > **خصائص** في جزء التنقل.

1. راجع **اشتراك** حساب التخزين بالإضافة إلى **مجموعة الموارد** و **الاسم** للتأكد من أنك تحدد القيم الصحيحة في رؤى الجمهور.

1. في رؤى الجمهور، اختر القيم أو الحقول المطابقة عند إرفاق حساب التخزين.
   
1. تابع تنفيذ الخطوات المتبقية في رؤى الجمهور لإرفاق حساب التخزين.


[!INCLUDE[footer-include](../includes/footer-banner.md)]