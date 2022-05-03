---
title: بيانات Customer Insights في Microsoft Dataverse
description: استخدم كيانات Customer Insights كجداول في Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 85995cbd7f797810bfb6ecdc8a24d56542f0b5a9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645468"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>استخدام بيانات Customer Insights في Microsoft Dataverse

يوفر Customer Insights خيار جعل كيانات الإخراج متوفرة في [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). يتيح هذا التكامل سهولة مشاركة البيانات والتطوير المخصص من خلال أسلوب قائم على التعليمات البرمجية المنخفضة / بدون تعليمات برمجية. تتوفر [كيانات الإخراج](#output-entities) كجداول في بيئة Dataverse. يمكنك استخدام البيانات لأي تطبيق آخر بالاستناد إلى جداول Dataverse. تمكّن هذه الجداول سيناريوهات مثل مهام سير العمل التلقائية من خلال Power Automate أو بناء التطبيقات باستخدام Power Apps. يدعم التنفيذ الحالي بشكل أساسي البحث عن المكان من حيث يمكن إحضار البيانات من كيانات Customer Insights المتوفرة لمعرف عميل معين.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>إرفاق بيئة Dataverse بـ Customer Insights

**مؤسسة موجودة**

بإمكان المسؤولين تكوين Customer Insights من أجل [استخدام بيئة Dataverse موجودة](create-environment.md) عند إنشاء بيئة Customer Insights. ومن خلال توفير عنوان URL لبيئة Dataverse، يتم إرفاقه ببيئة Customer Insights الجديدة الخاصة بهم. يجب استضافة بيئات Customer Insights وDataverse في نفس المنطقة. 

إذا كنت لا تريد استخدام بيئة Dataverse موجودة، فيقوم النظام بإنشاء بيئة جديدة لبيانات Customer Insights في المستأجر. 

> [!NOTE]
> إذا كانت مؤسستك تستخدم Dataverse بالفعل في المستأجر الخاص بها، فمن المهم أن تتذكر أن إنشاء بيئة [Dataverse يتحكم فيه المسؤول](/power-platform/admin/control-environment-creation). على سبيل المثال، إذا كنت تقوم بإعداد بيئة Customer Insights جديدة باستخدام حسابك المؤسسي وقام المسؤول بتعطيل إنشاء بيئات Dataverse التجريبية للجميع باستثناء المسؤولين، فلا يمكنك إنشاء بيئة تجريبية جديدة.
> 
> سعة تخزين بيئات Dataverse التجريبية التي تم إنشاؤها في Customer Insights هي 3 غيغابايت لا يتم حسابها بالنسبة إلى السعة الإجمالية التي يجب للمستأجر الحصول عليها. يحق للاشتراكات المدفوعة الحصول على 15 غيغابايت لتخزين قاعدة البيانات و20 غيغابايت لتخزين الملفات في Dataverse.

**مؤسسة جديدة**

إذا قمت بإنشاء مؤسسة جديدة عند إعداد Customer Insights، فيقوم النظام تلقائيًا بإنشاء بيئة Dataverse جديدة في مؤسستك نيابة عنك.

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

يحتوي هذا الجدول على ملف تعريف العميل الموحد من Customer Insights. يتوقف مخطط ملف تعريف العميل الموحد على الكيانات والسمات المستخدمة في عملية الدمج. يحتوي مخطط ملف تعريف العميل عادة على مجموعة فرعية من السمات من [تعريف نموذج البيانات العامة لـ CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

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
