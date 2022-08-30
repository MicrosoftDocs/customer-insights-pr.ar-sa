---
title: الاتصال بحساب Azure Data Lake Storage باستخدام كيان خدمة من Azure
description: استخدم كيان خدمة من Azure للاتصال بمستودع بياناتك.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304181"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>الاتصال بحساب Azure Data Lake Storage باستخدام كيان خدمة من Azure

يوفر Dynamics 365 Customer Insights خيارًا للاتصال بحساب Azure Data Lake Storage باستخدام كيان خدمة من Azure بدلاً من مفاتيح حساب التخزين.

يجب أن يكون للأدوات التلقائية التي تستخدم خدمات Azure أذونات مقيدة. بدلاً من قيام التطبيقات بتسجيل الدخول كمستخدم له امتيازات كاملة، يقدم Azure كيانات الخدمة. يمكنك استخدام كيان خدمة لـ [إضافة مجلد "نموذج البيانات العامة" أو تحريره بأمان كمصدر بيانات](connect-common-data-model.md) أو [إنشاء بيئة أو تحديثها](create-environment.md).

## <a name="prerequisites"></a>المتطلبات

- يجب أن يكون حساب Data Lake Storage الذي سيستخدم كيان خدمة من النوع Gen2. حسابات تخزين Azure Data Lake Gen1 غير مدعومة.
- يحتوي حساب Data Lake Storage على [مساحة اسم هرمية ممكّنة](/azure/storage/blobs/data-lake-storage-namespace).
- تحتاج إلى أذونات المسؤول لمستأجر Azure الخاص بك، إذا أردت إنشاء كيان خدمة جديد.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>إنشاء كيان خدمة من Azure لـ Customer Insights

قبل إنشاء أساسي خدمة جديد لـ Customer Insights، تحقق مما إذا كان موجودًا بالفعل في مؤسستك. وفي معظم الحالات، يكون موجودًا بالفعل.

### <a name="look-for-an-existing-service-principal"></a>البحث عن كيان خدمة موجود

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com) وسجل دخولك إلى مؤسستك.

2. من **خدمات Azure**، حدد **Azure Active Directory**.

3. ضمن **إدارة**، حدد **تطبيق Microsoft**.

4. أضف عامل تصفية إلى **يبدأ معرف التطبيق بـ** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` أو ابحث عن الاسم `Dynamics 365 AI for Customer Insights`.

5. إذا وجدت سجلاً مطابقًا، فهذا يعني أن كيان الخدمة موجود بالفعل. [منح االأذونات](#grant-permissions-to-the-service-principal-to-access-the-storage-account) لكيان الخدمة للوصول إلى حساب التخزين.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="لقطة شاشة تُظهر كيان خدمة موجودًا.":::

6. إذا لم يتم إرجاع أي نتائج، فيمكنك [إنشاء كيان خدمة جديد](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>إنشاء كيان خدمة جديد

1. ثبّت الإصدار الأخير من Azure Active Directory PowerShell for Graph. لمزيد من المعلومات، انتقل إلى [تثبيت Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).

   1. على الكمبيوتر، اضغط على مفتاح Windows على لوحة المفاتيح وابحث عن **Windows PowerShell** وحدد **تشغيل كمسؤول**.

   1. في نافذة PowerShell التي تفتح، أدخل `Install-Module AzureAD`.

2. أنشئ كيان الخدمة لـ Customer Insights باستخدام الوحدة النمطية Azure AD PowerShell.

   1. في نافذة PowerShell، أدخل `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. استبدل *[معرف الدليل الخاص بك]* بمعرف الدليل الفعلي لاشتراك Azure الخاص بك حيث تريد إنشاء كيان الخدمة. معلمة اسم البيئة، `AzureEnvironmentName`، اختيارية.
  
   1. أدخل `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. يقوم هذا الأمر بإنشاء كيان الخدمة لـ Customer Insights في اشتراك Azure المحدد.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>منح أذونات لكيان الخدمة للوصول إلى حساب التخزين

لمنح أذونات لكيان خدمة لحساب التخزين الذي تريد استخدامه في Customer Insights، يجب تعيين أحد الأدوار التالية لحساب أو حاوية التخزين:

|بيانات الاعتماد|المتطلبات|
|----------|------------|
|مستخدم في وضع تسجيل الدخول حاليًا|**الدور**: قارئ بيانات مخزن البيانات الثنائية الكبيرة أو مساهم مخزن البيانات الثنائية الكبيرة أو مالك مخزن البيانات الثنائية الكبيرة.<br>**المستوى**: تُمنح الأذونات على حساب التخزين أو الحاوية.</br>|
|كيان الخدمة في Customer Insights -<br>استخدام Azure Data Lake Storage كمصدر بيانات</br>|خيار 1<ul><li>**الدور**: قارئ بيانات مخزن البيانات الثنائية الكبيرة أو مساهم بيانات مخزن البيانات الثنائية الكبيرة أو مالك بيانات مخزن البيانات الثنائية الكبيرة.</li><li>**المستوى**: تُمنح الأذونات على حساب التخزين.</li></ul>الخيار 2 *(بدون مشاركة وصول كيان الخدمة إلى حساب التخزين)*<ul><li>**الدور 1**: قارئ بيانات مخزن البيانات الثنائية الكبيرة أو مساهم بيانات مخزن البيانات الثنائية الكبيرة أو مالك بيانات مخزن البيانات الثنائية الكبيرة.</li><li>**المستوى**: تُمنح الأذونات على الحاوية.</li><li>**الدور 2**: مفوض بيانات مخزن البيانات الثنائية الكبيرة.</li><li>**المستوى**: تُمنح الأذونات على حساب التخزين.</li></ul>|
|كيان الخدمة في Customer Insights - <br>استخدام Azure Data Lake Storage كإخراج أو وجهة</br>|خيار 1<ul><li>**الدور**: مساهم مخزن البيانات الثنائية الكبيرة أو مالك مخزن البيانات الثنائية الكبيرة.</li><li>**المستوى**: تُمنح الأذونات على حساب التخزين.</li></ul>الخيار 2 *(بدون مشاركة وصول كيان الخدمة إلى حساب التخزين)*<ul><li>**الدور**: مساهم مخزن البيانات الثنائية الكبيرة أو مالك مخزن البيانات الثنائية الكبيرة.</li><li>**المستوى**: تُمنح الأذونات على الحاوية.</li><li>**الدور 2**: مفوض مخزن البيانات الثنائية الكبيرة.</li><li>**المستوى**: تُمنح الأذونات على حساب التخزين.</li></ul>|

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com) وسجل دخولك إلى مؤسستك.

1. افتح حساب التخزين الذي ترغب في أن يكون لدى كيان الخدمة لـ Customer Insights إمكانية الوصول إليه.

1. من الجزء الأيسر، حدد **عنصر تحكم الوصول (IAM)**، ثم حدد **إضافة** > **إضافة تعيين الدور**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="لقطة شاشة تُظهر مدخل Azure أثناء إضافة تعيين دور.":::

1. في جزء **إضافة تعيين الدور**، قم بتعيين الخصائص التالية:
   - **الدور**: قارئ بيانات مخزن البيانات الثنائية الكبيرة أو مساهم مخزن البيانات الثنائية الكبيرة أو مالك مخزن البيانات الثنائية الكبيرة بالاستناد إلى بيانات الاعتماد المذكورة أعلاه.
   - **تعيين الوصول إلى**: **المستخدم أو المجموعة أو كيان الخدمة**
   - **حدد** الأعضاء: **Dynamics 365 AI for Customer Insights** ( [كيان الخدمة](#create-a-new-service-principal) الذي بحثت عنه في وقت سابق في هذا الإجراء)

1. حدد **مراجعة + تعيين**.

قد تستغرق فترة نشر التغييرات ما يصل إلى 15 دقيقة.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>أدخل معرف مورد Azure أو تفاصيل اشتراك Azure في مرفق حساب التخزين إلى Customer Insights

إرفاق حساب Data Lake Storage في Customer Insights من أجل [تخزين بيانات الإخراج](manage-environments.md) أو [استخدامها كمصدر بيانات](connect-dataverse-managed-lake.md). اختر من بين نهج [مستند إلى المورد](#resource-based-storage-account-connection) أو [مستند إلى اشتراك](#subscription-based-storage-account-connection) واتبع تلك الخطوات.

### <a name="resource-based-storage-account-connection"></a>‏‏اتصال حساب التخزين المستند إلى الموارد

1. انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com)، ثم قم بتسجيل الدخول إلى اشتراكك وافتح حساب التخزين.

1. في الجزء الأيمن، انتقل إلى **الإعدادات** > **نقاط النهاية**.

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
