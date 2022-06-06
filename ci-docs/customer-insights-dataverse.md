---
title: استخدام بيانات Customer Insights في Microsoft Dataverse
description: تعرف على كيفية توصيل Customer Insights وMicrosoft Dataverse وتعرف على كيانات الإخراج التي يتم تصديرها إلى Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833660"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>استخدام بيانات Customer Insights في Microsoft Dataverse

يوفر Customer Insights خيارًا يسمح بجعل كيانات الإخراج متوفرة باعتبارها [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). يتيح هذا التكامل سهولة مشاركة البيانات والتطوير المخصص من خلال أسلوب قائم على التعليمات البرمجية المنخفضة / بدون تعليمات برمجية. تتوفر [كيانات الإخراج](#output-entities) كجداول في بيئة Dataverse. يمكنك استخدام البيانات لأي تطبيق آخر بالاستناد إلى جداول Dataverse. تمكّن هذه الجداول سيناريوهات مثل مهام سير العمل التلقائية من خلال Power Automate أو بناء التطبيقات باستخدام Power Apps.

كما يمكنك الاتصال ببيئة Dataverse الخاصة بك استيعاب البيانات من مصادر بيانات داخلية[ باستخدام تدفقات البيانات والبوابات Power Platform](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>المتطلبات

- يجب استضافة بيئات Customer Insights وDataverse في نفس المنطقة.
- يجب أن يكون لديك دور مسؤول عمومي في بيئة Dataverse. تحقق مما إذا كانت [بيئة Dataverse هذه مقترنة](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) بمجموعات أمان معينة وتأكد من إضافتك إلى مجموعات الأمان هذه.
- لا توجد بيئة Customer Insights أخرى موجودة مقترنة بالفعل ببيئة Dataverse التي تريد توصيلها. تعرف على كيفية [إزالة اتصال موجود ببيئة Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- بإمكان بيئة Microsoft Dataverse الاتصال بحساب تخزين واحد فقط. ينطبق هذا الأمر فقط إذا قمت بتكوين البيئة [لاستخدام Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>توصيل بيئة Dataverse بـ Customer Insights

تسمح لك خطوة **Microsoft Dataverse** بتوصيل Customer Insights ببيئتك في Dataverse أثناء [إنشاء بيئة Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="تمكين مشاركة البيانات مع Microsoft Dataverse بشكل تلقائي للبيئات الجديدة الصافية.":::

يمكن للمسؤولين تكوين Customer Insights لتوصيل بيئة Dataverse موجودة. ومن خلال توفير عنوان URL لبيئة Dataverse، يتم إرفاقه ببيئة Customer Insights الجديدة الخاصة بهم.

إذا كنت لا تريد استخدام بيئة Dataverse موجودة، فيقوم النظام بإنشاء بيئة جديدة لبيانات Customer Insights في المستأجر. بإمكان مسؤولي [Power Platform التحكم في اختيار الأشخاص الذين يمكنهم إنشاء البيئات](/power-platform/admin/control-environment-creation). عندما تقوم بإعداد بيئة Customer Insights جديدة وقام المسؤول بتعطيل إنشاء بيئات Dataverse لكل شخص باستثناء المسؤولين، فقد لا تتمكن من إنشاء بيئة جديدة.

**تمكين مشاركة البيانات** مع Dataverse عن طريق تحديد خانة اختيار مشاركة البيانات.

إذا كنت تستخدم حساب مساحة تخزين Data Lake Storage، ستحتاج أيضًا إلى **معرف الأذونات**. لمزيد من المعلومات حول كيفية الحصول على معرف الأذونات، راجع القسم التالي.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>تمكين مشاركة البيانات باستخدام Dataverse من Azure Data Lake Storage الخاص بك (إصدار أولي)

تحتاج مشاركة البيانات مع Microsoft Dataverse عندما تقوم بيئتك [باستخدام حسابك الخاص في Azure Data Lake Storage](own-data-lake-storage.md) إلى بعض التكوينات الإضافية. يجب أن تتوفر لدى المستخدم الذي يقوم بإعداد بيئة Customer Insights أذونات **قارئ بيانات تخزين البيانات الثنائية الكبيرة** على الأقل على حاوية *CustomerInsights* في حساب Azure Data Lake Storage.

1. قم بإنشاء مجموعتي أمان في اشتراك Azure - مجموعة أمان **قارئ** ومجموعة أمان **المساهم** ثم قم بتعيين خدمة Microsoft Dataverse كمالك لمجموعتي الأمان.
2. قم بإدارة قائمة التحكم بالوصول (ACL) في حاوية CustomerInsights في حساب موقع التخزين الخاص بك عبر مجموعتي الأمان هذه. أضف خدمة Microsoft Dataverse وأي تطبيقات أعمال مستندة إلى Dataverse مثل Dynamics 365 Marketing إلى مجموعة الأمان **قارئ** باستخدام أذونات **للقراءة فقط**. أضف تطبيق Customers Insights *فقط* إلى مجموعة أمان **المساهم** لمنح أذونات **القراءة والكتابة** لكتابة ملفات التعريف والرؤى.

### <a name="limitations"></a>القيود

هناك نوعان من القيود عند استخدام Dataverse مع حسابك الخاص في Azure Data Lake Storage:

- هناك تعيين واحد لواحد بين مؤسسة Dataverse وحساب Azure Data Lake Storage. بعد توصيل مؤسسة Dataverse بحساب تخزين، لا يمكنها الاتصال بحساب تخزين آخر. يمنع هذا القيد عدم قيام Dataverse بتعبئة حسابات تخزين متعددة.
- لن تعمل مشاركة البيانات إذا كان إعداد Azure Private Link مطلوبًا للوصول إلى حساب Azure Data Lake Storage لأنه موجود خلف جدار حماية. لا يدعم Dataverse في الوقت الحالي الاتصال بنقاط النهاية الخاصة من خلال الارتباط الخاص.

### <a name="set-up-powershell"></a>إعداد PowerShell

لتنفيذ البرامج النصية PowerShell، ستحتاج أولاً إلى إعداد PowerShell وفقًا لذلك.

1. ثبّت الإصدار الأخير من [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. على الكمبيوتر، حدد مفتاح Windows على لوحة المفاتيح وابحث عن **Windows PowerShell** ثم حدد **تشغيل كمسؤول**.
   1. في نافذة PowerShell التي تفتح، أدخل `Install-Module AzureAD`.
2. استيراد ثلاث وحدات نمطية.
    1. في نافذه Powershell، اكتب `Install-Module -Name Az.Accounts` واتبع الخطوات.
    1. كرر لـ `Install-Module -Name Az.Resources` و`Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>خطوات التكوين

1. قم بتنزيل برنامجي PowerShell النصيين اللذين تحتاج إلى تشغيلهما من [برنامج GitHub repo الخاص بمهندسنا](https://github.com/trin-msft/byol).
    1. `CreateSecurityGroups.ps1`
       - ولتشغيل برنامج PowerShell النصي هذا، تحتاج إلى أذونات *مسؤول مستأجر*.
       - ينشئ برنامج PowerShell النصي هذا مجموعتي أمان على اشتراك Azure الخاص بك. واحدة للمجموعة قارئ، وأخرى للمجموعة المساهم وسوف يجعل خدمة Microsoft Dataverse كمالك لكل من مجموعتي الأمان هاتين.
       - نفذ برنامج PowerShell النصي هذا في Windows PowerShell من خلال توفير معرف اشتراك Azure الذي يحتوي على Azure Data Lake Storage. افتح برنامج PowerShell النصي في محرر لمراجعة المعلومات الإضافية والمنطق الذي تم تنفيذه.
       - احفظ قيمتي معرفي مجموعتي الأمان اللذين تم إنشاؤهما بواسطة هذا البرنامج النصي، حيث سنستخدمهما في برنامج `ByolSetup.ps1` النصي.

        > [!NOTE]
        > يمكن تعطيل إنشاء مجموعة الأمان في المستأجر الخاص بك. في هذه الحالة، يلزم إعداد يدوي كما يجب على مسؤول Azure AD[ تمكين إنشاء مجموعة أمان](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - تحتاج إلى أذونات *‏‫مالك بيانات التخزين كبيرة الحجم‬* في حساب موقع التخزين/مستوى الحاوية لتشغيل هذا البرنامج النصي، أو أن هذا البرنامج النصي سينشئ واحدًا لك. ويمكن إزالة تعيين الدور الخاص بك يدويًا بعد تشغيل البرنامج النصي بنجاح.
        - يقوم برنامج PowerShell النصي هذا بإضافة عنصر التحكم بالوصول (ACAC) المطلوب المستند إلى الدور لخدمة Microsoft Dataverse وأي تطبيقات أعمال مستندة إلى Dataverse. كما يقوم أيضًا بتحديث قائمة مراقبة الوصول (ACL) في حاوية CustomerInsights لمجموعات الأمان التي تم إنشاؤها باستخدام برنامج `CreateSecurityGroups.ps1` النصي. ستحصل مجموعة المساهم على إذن *rwx* وستحصل مجموعة القُرّاء‬ على إذن *r-x* فقط.
        - نفذ برنامج PowerShell النصي هذا في Windows PowerShell من خلال توفير معرف اشتراك Azure الذي يحتوي على Azure Data Lake Storage، واسم حساب موقع التخزين، واسم مجموعة الموارد، وقيم معرف مجموعتي أمان القارئ والمساهم. افتح برنامج PowerShell النصي في محرر لمراجعة المعلومات الإضافية والمنطق الذي تم تنفيذه.
        - انسخ سلسلة الإخراج بعد تشغيل البرنامج النصي بنجاح. تبدو سلسلة الإخراج كما يلي: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. أدخل سلسلة الإخراج المنسوخة من أعلى إلى حقل **معرف الأذونات** الخاص بخطوة تكوين البيئة لـ Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="خيارات التكوين لتمكين مشاركة البيانات من Azure Data Lake Storage الخاص بك باستخدام Microsoft Dataverse.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>إزالة اتصال موجود ببيئة Dataverse

عند الاتصال ببيئة Dataverse، فإن رسالة الخطأ **مؤسسة CDS هذه متصلة بمثيل Customer Insights** تعني أن بيئة Dataverse مستخدمة بالفعل في بيئة Customer Insights. يمكنك إزالة الاتصال الموجود كمسؤول عمومي على بيئة Dataverse. قد تستغرق عملية ملء التغييرات بضع ساعات.

1. اذهب إلى [Power Apps](https://make.powerapps.com).
1. حدد البيئة من منتقي البيئة.
1. انتقل إلى **الحلول**
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

| Column            | النوع        | الوصف                                                                               |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| Customerid        | السلسلة‬      | معرف ملف تعريف العميل                                                                      |
| ActivityId        | السلسلة‬      | المعرف الداخلي لنشاط العميل (المفتاح الأساسي)                                       |
| SourceEntityName  | السلسلة‬      | اسم الكيان المصدر.                                                                |
| SourceActivityId  | السلسلة‬      | المفتاح الأساسي من الكيان المصدر                                                       |
| ActivityType      | السلسلة‬      | نوع النشاط الدلالي أو اسم النشاط المخصص                                        |
| ActivityTimeStamp | DATETIME    | الطابع الزمني للنشاط                                                                      |
| ‏‫المسمى الوظيفي             | السلسلة‬      | اسم أو عنوان النشاط                                                               |
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

| Column               | النوع        | الوصف                                           |
|----------------------|-------------|------------------------------------------------------|
| Customerid           | السلسلة‬      | معرف ملف تعريف العميل                                  |
| ModelProvider        | السلسلة‬      | اسم موفر النموذج                                      |
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
| SegmentMembershipType | سلسلة‬       | نوع العميل لسجل عضوية المقطع هذا. يدعم أنواعًا متعددة مثل العميل أو جهة الاتصال أو الحساب. الافتراضي: العميل  |
| المقاطع       | سلسلة JSON  | قائمة الأقسام الفريدة التي ينتمي إليها ملف تعريف العميل      |
| msdynci_identifier  | السلسلة‬   | معرّف فريد لسجل عضوية المقطع. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | معرف Guid      | تم إنشاء GUID الحتمي من `msdynci_identifier`          |

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
