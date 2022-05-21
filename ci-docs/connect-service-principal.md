---
title: الاتصال بحساب Azure Data Lake Storage باستخدام كيان خدمة
description: استخدم كيان خدمة من Azure للاتصال بمستودع بياناتك.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 776eee79c25edbd40ed119510a314f5126933c3e
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/11/2022
ms.locfileid: "8739146"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>الاتصال بحساب Azure Data Lake Storage باستخدام كيان خدمة من Azure

يناقش هذا المقال كيفية اتصال Dynamics 365 Customer Insights بحساب Azure Data Lake Storage باستخدام أساسي خدمة Azure بدلاً من مفاتيح حساب التخزين. 

يجب أن تكون دائمًا الأدوات المؤتمتة التي تستخدم خدمات Azure ذات أذونات مقيدة. بدلاً من قيام التطبيقات بتسجيل الدخول كمستخدم له امتيازات كاملة، يقدم Azure كيانات الخدمة. يمكنك استخدام أساسيات الخدمة لـ [إضافة مجلد "نموذج البيانات العامة" أو تحريره بأمان كمصدر بيانات](connect-common-data-model.md) أو [إنشاء بيئة أو تحديثها](create-environment.md).

> [!IMPORTANT]
> - يجب أن يكون حساب Data Lake Storage الذي سيستخدم مدير الخدمة Gen2 وأن يكون به [مساحة اسم تدرج هرمي ممكّن](/azure/storage/blobs/data-lake-storage-namespace). حسابات تخزين Azure Data Lake Gen1 غير مدعومة.
> - تحتاج إلى أذونات المسؤول لاشتراك Azure لإنشاء أساسي خدمة.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>إنشاء كيان خدمة من Azure لـ Customer Insights

قبل إنشاء أساسي خدمة جديد لـ Customer Insights، تحقق مما إذا كان موجودًا بالفعل في مؤسستك.

### <a name="look-for-an-existing-service-principal"></a>البحث عن كيان خدمة موجود

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com) وسجل دخولك إلى مؤسستك.

2. من **خدمات Azure**، حدد **Azure Active Directory**.

3. ضمن **إدارة**، حدد **تطبيقات المؤسسة**.

4. أضف عامل تصفية إلى **يبدأ معرف التطبيق بـ** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` أو ابحث عن الاسم `Dynamics 365 AI for Customer Insights`.

5. إذا وجدت سجلاً مطابقًا، فهذا يعني أن كيان الخدمة موجود بالفعل. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="لقطة شاشة تُظهر كيان خدمة موجودًا.":::
   
6. إذا لم يتم إرجاع أي نتائج، فيمكنك إنشاء كيان خدمة جديد.

### <a name="create-a-new-service-principal"></a>إنشاء كيان خدمة جديد

1. ثبّت الإصدار الأخير من Azure Active Directory PowerShell for Graph. لمزيد من المعلومات، انتقل إلى [تثبيت Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. على الكمبيوتر، حدد مفتاح Windows على لوحة المفاتيح وابحث عن **Windows PowerShell** ثم حدد **تشغيل كمسؤول**.
   
   1. في نافذة PowerShell التي تفتح، أدخل `Install-Module AzureAD`.

2. أنشئ كيان الخدمة لـ Customer Insights باستخدام الوحدة النمطية Azure AD PowerShell.

   1. في نافذة PowerShell، أدخل `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. استبدل *[معرف الدليل الخاص بك]* بمعرف الدليل الفعلي لاشتراك Azure الخاص بك حيث تريد إنشاء كيان الخدمة. معلمة اسم البيئة، `AzureEnvironmentName`، اختيارية.
  
   1. أدخل `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. يقوم هذا الأمر بإنشاء كيان الخدمة لـ Customer Insights في اشتراك Azure المحدد. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>منح أذونات لكيان الخدمة للوصول إلى حساب التخزين

انتقل إلى مدخل Azure لمنح أذونات لكيان الخدمة لحساب التخزين الذي ترغب في استخدامه في Customer Insights.

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com) وسجل دخولك إلى مؤسستك.

1. افتح حساب التخزين الذي ترغب في أن يكون لدى كيان الخدمة لـ Customer Insights إمكانية الوصول إليه.

1. من الجزء الأيسر، حدد **عنصر تحكم الوصول (IAM)**، ثم حدد **إضافة** > **إضافة تعيين الدور**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="لقطة شاشة تُظهر مدخل Azure أثناء إضافة تعيين دور.":::

1. في جزء **إضافة تعيين الدور**، قم بتعيين الخصائص التالية:
   - الدور: **المساهم في بيانات مخزن البيانات الثنائية الكبيرة**
   - تعيين الوصول إلى: **المستخدم أو المجموعة أو كيان الخدمة**
   - تحديد الأعضاء: **Dynamics 365 AI for Customer Insights** ( [كيان الخدمة](#create-a-new-service-principal) الذي قمت بإنشاؤه قبل ذلك في هذا الإجراء)

1.  حدد **مراجعة + تعيين**.

قد تستغرق فترة نشر التغييرات ما يصل إلى 15 دقيقة.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>أدخل معرف مورد Azure أو تفاصيل اشتراك Azure في مرفق حساب التخزين إلى Customer Insights

يمكنك إرفاق حساب Data Lake Storage في Customer Insights بـ [تخزين بيانات المخرجات](manage-environments.md) أو [استخدامه كمصدر بيانات](connect-dataverse-managed-lake.md). يتيح لك هذا الخيار الاختيار بين أسلوب يستند إلى المورد أو أسلوب يستند إلى الاشتراك. وبحسب الأسلوب الذي تختاره، اتبع الإجراء في أحد الأقسام التالية.

### <a name="resource-based-storage-account-connection"></a>‏‏اتصال حساب التخزين المستند إلى الموارد

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com)، ثم قم بتسجيل الدخول إلى اشتراكك وافتح حساب التخزين.

1. في الجزء الأيسر، انتقل إلى **الإعدادات** > **خصائص**.

1. انسخ قيمة معرف مورد حساب التخزين.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="انسخ معرف مورد حساب التخزين.":::

1. في Customer Insights، أدخل معرف المورد في حقل المورد المعروض على شاشة اتصال حساب التخزين.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="أدخل معلومات معرف مورد حساب التخزين.":::   

1. تابع الخطوات المتبقية في Customer Insights لإرفاق حساب التخزين.

### <a name="subscription-based-storage-account-connection"></a>‏‏اتصال حساب التخزين المستند إلى الاشتراكات

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com)، ثم قم بتسجيل الدخول إلى اشتراكك وافتح حساب التخزين.

1. في الجزء الأيسر، انتقل إلى **الإعدادات** > **خصائص**.

1. راجع **الاشتراك**، و **مجموعة الموارد**، و **الاسم** لحساب التخزين للتأكد من تحديد القيم الصحيحة في Customer Insights.

1. في Customer Insights، اختر قيم الحقول المقابلة عند إرفاق حساب التخزين.

1. تابع الخطوات المتبقية في Customer Insights لإرفاق حساب التخزين.


[!INCLUDE [footer-include](includes/footer-banner.md)]