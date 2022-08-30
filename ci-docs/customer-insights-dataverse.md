---
title: استخدام بيانات Customer Insights في Microsoft Dataverse
description: تعرف على كيفية توصيل Customer Insights وMicrosoft Dataverse وتعرف على كيانات الإخراج التي يتم تصديرها إلى Dataverse.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303813"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>استخدام بيانات Customer Insights في Microsoft Dataverse

يوفر Customer Insights خيار جعل كيانات الإخراج متوفرة في [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). يتيح هذا التكامل سهولة مشاركة البيانات والتطوير المخصص من خلال أسلوب قائم على التعليمات البرمجية المنخفضة / بدون تعليمات برمجية. تتوفر [كيانات الإخراج](#output-entities) كجداول في بيئة Dataverse. يمكنك استخدام البيانات لأي تطبيق آخر بالاستناد إلى جداول Dataverse. تمكّن هذه الجداول سيناريوهات مثل مهام سير العمل التلقائية من خلال Power Automate أو بناء التطبيقات باستخدام Power Apps.

كما يمكنك الاتصال ببيئة Dataverse الخاصة بك استيعاب البيانات من مصادر بيانات داخلية[ باستخدام تدفقات البيانات والبوابات Power Platform](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>المتطلبات

- يجب استضافة بيئات Customer Insights وDataverse في نفس المنطقة.
- تم إعداد دور مسئول عام في بيئة Dataverse. تحقق مما إذا كانت [بيئة Dataverse هذه مقترنة](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) بمجموعات أمان معينة وتأكد من إضافتك إلى مجموعات الأمان هذه.
- لا توجد بيئة Customer Insights أخرى مرتبطة بالفعل ببيئة Dataverse التي تريد الاتصال بها. تعرف على كيفية [إزالة اتصال موجود ببيئة Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- بيئة Microsoft Dataverseمتصلة بحساب تخزين فردي، إذا قمت بتكوين البيئة بغرض [استخدام Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>استحقاق سعة تخزين Dataverse

يؤهلك اشتراك Customer Insights للحصول على سعة إضافية [لسعة تخزين Dataverse الحالية لمؤسستك](/power-platform/admin/capacity-storage). تعتمد السعة المضافة على عدد ملفات التعريف التي يستخدمها اشتراكك.

**مثال:**

بافتراض أنك تحصل على مساحة تخزين لقاعدة البيانات تبلغ 15 جيجا بايت وتخزين ملفات 20 جيجا بايت لكل 100000 ملف تعريف عميل. إذا كان اشتراكك يتضمن 300,000 ملف تعريف عميل، فإن سعة التخزين الإجمالية لديك هي 45 جيجا بايت (3 × 15 غيغابايت) لتخزين قاعدة البيانات و60 غيغابايت لتخزين الملفات (3 × 20 غيغابايت). وبالمثل، إذا كان لديك اشتراك (متاجرة شركة إلى شركة) بعدد 30 ألف حساب، فإن سعة التخزين الإجمالية لديك هي 45 غيغابايت (3 × 15 غيغابايت) لتخزين قاعدة البيانات ، وتخزين ملفات 60 غيغابايت (3 × 20 غيغابايت).

سعة السجل ليست تزايدية وثابتة لمؤسستك.

لمزيد من المعلومات حول استحقاقات السعة التفصيلية، راجع [دليل ترخيص Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>توصيل بيئة Dataverse بـ Customer Insights

تسمح لك خطوة **Microsoft Dataverse** بتوصيل Customer Insights ببيئتك في Dataverse أثناء [إنشاء بيئة Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="تمكين مشاركة البيانات مع Microsoft Dataverse بشكل تلقائي للبيئات الجديدة.":::

1. قم بتوفير عنوان URL لبيئة Dataverse الخاصة بك أو اتركه فارغًا لإنشاء عنوان URL لك.

   > [!NOTE]
   > بعد إنشاء الاتصال بين Customer Insights وDataverse، لا تقم بتغيير اسم المؤسسة لبيئة Dataverse. يتم استخدام اسم المؤسسة في عنوان URL لـ Dataverse ويقطع الاسم الذي تم تغييره الاتصال بـ Customer Insights.

   يمكن لمسؤولي [Power Platform التحكم في من يمكنه إنشاء بيئات Dataverse جديدة](/power-platform/admin/control-environment-creation). إذا كنت تحاول إعداد بيئة Customer Insights جديدة ولا يمكنك ذلك، فربما يكون المسؤول قد قام بتعطيل إنشاء بيئات Dataverse للجميع باستثناء المسؤولين.

1. إذا كنت تستخدم حساب Data Lake Storage الخاص بك:
   1. حدد **تمكين مشاركة البيانات** باستخدام Dataverse.
   1. أدخل **معرف الأذونات**. للحصول على معرّف الإذن، [مكّن مشاركة البيانات مع Dataverse من Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview) الخاص بك.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>تمكين مشاركة البيانات باستخدام Dataverse من Azure Data Lake Storage الخاص بك (إصدار أولي)

في [حساب Azure Data Lake Storage الخاص بك](own-data-lake-storage.md)، تحقق من أن المستخدم الذي قام بإعداد بيئة Customer Insights لديه على الأقل أذونات **قارئ بيانات تخزين البيانات الثنائية الكبيرة** على حاوية `customerinsights` في حساب التخزين.

### <a name="limitations"></a>القيود

- يوجد فقط تعيين واحد لواحد بين مؤسسة Dataverse وحساب Azure Data Lake Storage. بعد توصيل مؤسسة Dataverse بحساب تخزين، لا يمكنها الاتصال بحساب تخزين آخر. يمنع هذا القيد عدم قيام Dataverse بتعبئة حسابات تخزين متعددة.
- لن تعمل مشاركة البيانات إذا كان إعداد Azure Private Link مطلوبًا للوصول إلى حسابك في Azure Data Lake Storage لأنه موجود خلف جدار حماية. لا يدعم Dataverse في الوقت الحالي الاتصال بنقاط النهاية الخاصة من خلال الارتباط الخاص.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>إعداد مجموعات الأمان في Azure Data Lake Storage الخاصة بك

1. قم بإنشاء مجموعتي أمان في اشتراك Azure - مجموعة أمان **قارئ** ومجموعة أمان **المساهم** ثم قم بتعيين خدمة Microsoft Dataverse كمالك لمجموعتي الأمان.

1. قم بإدارة قائمة التحكم بالوصول (ACL) في حاوية `customerinsights` في حساب موقع التخزين الخاص بك عبر مجموعتي الأمان هذه.
   1. أضف خدمة Microsoft Dataverse وأي تطبيقات أعمال مستندة إلى Dataverse مثل Dynamics 365 Marketing إلى مجموعة الأمان **قارئ** باستخدام أذونات **للقراءة فقط**.
   1. أضف تطبيق Customers Insights *فقط* إلى مجموعة أمان **المساهم** لمنح أذونات **القراءة والكتابة** لكتابة ملفات التعريف والرؤى.

### <a name="set-up-powershell"></a>إعداد PowerShell

إعداد PowerShell لتنفيذ برامج PowerShell النصية.

1. ثبّت الإصدار الأخير من [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. على الكمبيوتر، حدد مفتاح Windows على لوحة المفاتيح وابحث عن **Windows PowerShell** ثم حدد **تشغيل كمسؤول**.
   1. في نافذة PowerShell التي تفتح، أدخل `Install-Module AzureAD`.

1. استيراد ثلاث وحدات نمطية.
   1. في نافذه Powershell، اكتب `Install-Module -Name Az.Accounts` واتبع الخطوات.
   1. كرر لـ `Install-Module -Name Az.Resources` و`Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>تنفيذ برامج PowerShell النصية والحصول على معرف الإذن

1. قم بتنزيل برنامجي PowerShell النصيين اللذين تحتاج إلى تشغيلهما من [برنامج GitHub repo الخاص بمهندسنا](https://github.com/trin-msft/byol).
   - `CreateSecurityGroups.ps1`: يتطلب أذونات مسؤول المستأجر.
   - `ByolSetup.ps1`: يتطلب أذونات ‏‫مالك بيانات مخزن البيانات الثنائية الكبيرة على مستوى حساب التخزين/الحاوية. سينشئ هذا البرنامج النصي الإذن لك. ويمكن إزالة تعيين الدور الخاص بك يدويًا بعد تشغيل البرنامج النصي بنجاح.

1. نفذ `CreateSecurityGroups.ps1` في Windows PowerShell من خلال توفير معرف اشتراك Azure الذي يحتوي على Azure Data Lake Storage الخاص بك. افتح برنامج PowerShell النصي في محرر لمراجعة المعلومات الإضافية والمنطق الذي تم تنفيذه.

   ينشئ هذا البرنامج النصي مجموعتين أمان في اشتراك Azure: واحدة لمجموعة القارئ والأخرى لمجموعة المساهم. تعد خدمة Microsoft Dataverse هي المالكة لمجموعتي الأمان هاتين.

1. احفظ قيم معرّف مجموعة الأمان التي تم إنشاؤها بواسطة هذا البرنامج النصي لاستخدامها في البرنامج النصي `ByolSetup.ps1`.

   > [!NOTE]
   > يمكن تعطيل إنشاء مجموعة الأمان في المستأجر الخاص بك. في هذه الحالة، يلزم إعداد يدوي كما يجب على مسؤول Azure AD[ تمكين إنشاء مجموعة أمان](/azure/active-directory/enterprise-users/groups-self-service-management).

1. نفذ البرنامج النصي `ByolSetup.ps1` في Windows PowerShell من خلال توفير معرف اشتراك Azure الذي يحتوي على Azure Data Lake Storage الخاص بك، واسم حساب موقع التخزين، واسم مجموعة الموارد، وقيم معرف مجموعتي أمان القارئ والمساهم. افتح برنامج PowerShell النصي في محرر لمراجعة المعلومات الإضافية والمنطق الذي تم تنفيذه.

   يضيف هذا البرنامج النصي عنصر التحكم في الوصول المستند إلى الدور المطلوب لخدمة Microsoft Dataverse وأي تطبيقات أعمال تستند إلى Dataverse. كما يقوم أيضًا بتحديث قائمة مراقبة الوصول (ACL) إلى حاوية `customerinsights` لمجموعات الأمان التي تم إنشاؤها باستخدام البرنامج النصي `CreateSecurityGroups.ps1`. تُمنح مجموعة المساهم إذن *rwx* وتُمنح مجموعة القارئ‬ إذن *r-x* فقط.

1. انسخ سلسلة الإخراج التي تبدو كالتالي: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. أدخل سلسلة الإخراج المنسوخة إلى حقل **معرف الأذونات** الخاص بخطوة تكوين البيئة لـ Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="خيارات التكوين لتمكين مشاركة البيانات من Azure Data Lake Storage الخاص بك باستخدام Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>إزالة اتصال موجود ببيئة Dataverse

عند الاتصال ببيئة Dataverse، فإن رسالة الخطأ **مؤسسة CDS هذه متصلة بمثيل Customer Insights** تعني أن بيئة Dataverse مستخدمة بالفعل في بيئة Customer Insights. يمكنك إزالة الاتصال الموجود كمسؤول عمومي على بيئة Dataverse. قد تستغرق عملية ملء التغييرات بضع ساعات.

1. اذهب إلى [Power Apps](https://make.powerapps.com).
1. حدد البيئة من منتقي البيئة.
1. انتقل إلى **الحلول**.
1. قم بإزالة تثبيت أو حذف الحل الذي يسمى **‏‫الوظيفة الإضافية لبطاقة عميل Dynamics 365 Customer Insights (إصدار أولي)**.

OR

1. افتح بيئة Dataverse الخاصة بك.
1. انتقل إلى **الإعدادات المتقدمة** > **الحلول**.
1. إزالة تثبيت حل **CustomerInsightsCustomerCard**.

إذا فشلت فشل إزالة الاتصال بسبب التبعيات، ستحتاج إلى إزالة التبعيات أيضًا. لمزيد من المعلومات، راجع [إزالة التبعيات](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>كيانات الإخراج

تتوفر بعض كيانات الإخراج من Customer Insights كجداول في Dataverse. تصف الأقسام أدناه المخطط المتوقع لهذه الجداول.

- [ملف تعريف العميل](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [الإثراء](#enrichment)
- [التنبؤ](#prediction)
- [عضوية المقطع](#segment-membership)

### <a name="customerprofile"></a>ملف تعريف العميل

يحتوي هذا الجدول على ملف تعريف العميل الموحد من Customer Insights. يعتمد مخطط ملف تعريف العميل الموحد على الكيانات والسمات المستخدمة في عملية توحيد البيانات. يحتوي مخطط ملف تعريف العميل عادة على مجموعة فرعية من السمات من [تعريف نموذج البيانات العامة لـ CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

يحتوي جدول AlternateKey على مفاتيح الكيانات التي شاركت في عملية التوحيد.

|Column  |النوع  |الوصف   |
|---------|---------|---------|
|DataSourceName    |السلسلة‬         | اسم مصدر البيانات. على سبيل المثال: `datasource5`        |
|EntityName        | سلسلة‬        | اسم الكيان في Customer Insights. على سبيل المثال: `contact1`        |
|AlternateValue    |سلسلة‬         |المعرف البديل الذي يتم تعيينه إلى معرف العميل. مثال: `cntid_1078`         |
|KeyRing           | نص متعدد الأسطر        | قيمة JSON  </br> العينة: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"المفتاح المفضل":" cntid_1078"،</br>"keys":[" cntid_1078"]}]       |
|Customerid         | السلسلة‬        | معرف ملف تعريف العميل الموحد.         |
|AlternateKeyId     | GUID         |  GUID المؤكد لـ AlternateKey استنادًا إلى msdynci_identifier       |
|msdynci_identifier |   السلسلة‬      |   `DataSourceName|EntityName|AlternateValue`  </br> العينة: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

يحتوي هذا الجدول على الأنشطة حسب المستخدمين المتوفرين في Customer Insights.

| Column            | نوع        | الوصف                                                                               |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| Customerid        | سلسلة‬‬      | معرف ملف تعريف العميل                                                                      |
| ActivityId        | سلسلة‬‬      | المعرف الداخلي لنشاط العميل (المفتاح الأساسي)                                       |
| SourceEntityName  | السلسلة‬      | اسم الكيان المصدر.                                                                |
| SourceActivityId  | السلسلة‬      | المفتاح الأساسي من الكيان المصدر                                                       |
| ActivityType      | السلسلة‬      | نوع النشاط الدلالي أو اسم النشاط المخصص                                        |
| ActivityTimeStamp | DATETIME    | الطابع الزمني للنشاط                                                                      |
| ‏‫المسمى الوظيفي             | سلسلة‬‬      | اسم أو عنوان النشاط                                                               |
| الوصف        | السلسلة‬      | وصف النشاط                                                                     |
| عنوان URL                | السلسلة‬      | ارتباط إلى عنوان URL خارجي خاص بالنشاط                                         |
| SemanticData      | سلسلة JSON | تتضمن قائمة بأزواج القيم الأساسية بحقول التعيين الدلالي الخاصة بنوع النشاط |
| RangeIndex        | السلسلة‬      | طابع زمني لـ Unix يستخدم لفرز المخطط الزمني للنشاط واستعلامات النطاق الفعالة |
| mydynci_unifiedactivityid   | GUID | المعرف الداخلي لنشاط العميل (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

يحتوي هذا الجدول على بيانات الإخراج الخاصة بالمقاييس المستندة إلى سمات العميل.

| Column             | النوع             | الوصف                  |
|--------------------|------------------|-----------------------------|
| Customerid         | السلسلة‬           | معرف ملف تعريف العميل        |
| المقاييس           | سلسلة JSON      | تتضمن قائمة بأزواج القيم الأساسية لاسم المقياس وقيمه للعميل المحدد | 
| msdynci_identifier | السلسلة‬           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | معرف ملف تعريف العميل |


### <a name="enrichment"></a>الإثراء

يحتوي هذا الجدول على إخراج عملية الإثراء.

| Column               | النوع             |  الوصف                                           |
|----------------------|------------------|------------------------------------------------------|
| Customerid           | السلسلة‬           | معرف ملف تعريف العميل                                 |
| EnrichmentProvider   | السلسلة‬           | اسم موفر الإثراء                                  |
| EnrichmentType       | السلسلة‬           | نوع الإثراء                                      |
| القيم               | سلسلة JSON      | قائمة السمات التي تنتجها عملية الإثراء |
| msdynci_enrichmentid | GUID             | GUID المؤكد الناشئ عن msdynci_identifier |
| msdynci_identifier   | السلسلة‬           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>التنبؤ

يحتوي هذا الجدول على إخراج تنبؤات النموذج.

| Column               | نوع        | الوصف                                           |
|----------------------|-------------|------------------------------------------------------|
| Customerid           | سلسلة‬‬      | معرف ملف تعريف العميل                                  |
| ModelProvider        | سلسلة‬‬      | اسم موفر النموذج                                      |
| النموذج                | السلسلة‬      | اسم النموذج                                                |
| القيم               | سلسلة JSON | قائمة السمات التي ينتجها النموذج |
| msdynci_predictionid | GUID        | GUID المؤكد الناشئ عن msdynci_identifier | 
| msdynci_identifier   | السلسلة‬      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>عضوية المقطع

يحتوي هذا الجدول على معلومات عضوية المقطع لملفات تعريف العملاء.

| Column        | كتابة | الوصف                         |
|--------------------|--------------|-----------------------------|
| Customerid        | السلسلة‬       | معرف ملف تعريف العميل        |
| SegmentProvider      | سلسلة‬       | التطبيق الذي ينشر المقاطع.      |
| SegmentMembershipType | سلسلة‬‬       | نوع العميل لسجل عضوية هذا المقطع. يدعم أنواعًا متعددة مثل العميل أو جهة الاتصال أو الحساب. الافتراضي: العميل  |
| المقاطع       | سلسلة JSON  | قائمة الأقسام الفريدة التي ينتمي إليها ملف تعريف العميل      |
| msdynci_identifier  | السلسلة‬   | معرّف فريد لسجل عضوية المقطع. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | معرف Guid      | تم إنشاء GUID الحتمي من `msdynci_identifier`          |


[!INCLUDE [footer-include](includes/footer-banner.md)]
