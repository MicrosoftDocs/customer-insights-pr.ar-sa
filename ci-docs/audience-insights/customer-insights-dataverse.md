---
title: بيانات Customer Insights في Microsoft Dataverse
description: استخدم كيانات Customer Insights كجداول في Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 220e01a06711a5d35b8df09e265017a6d8fd0490
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650026"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>استخدام بيانات Customer Insights في Microsoft Dataverse

يوفر Customer Insights خيار جعل كيانات الإخراج متوفرة في [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). يتيح هذا التكامل سهولة مشاركة البيانات والتطوير المخصص من خلال أسلوب قائم على التعليمات البرمجية منخفضة / بدون تعليمات برمجية. ستتوفر كيانات الإخراج كجداول في Dataverse. تمكّن هذه الجداول سيناريوهات مثل [عمليات سير العمل التلقائية عبر Power Automate](/power-automate/getting-started) و[التطبيقات التي تستند إلى النموذج](/powerapps/maker/model-driven-apps/) و[تطبيقات اللوحة](/powerapps/maker/canvas-apps/) عبر Power Apps. يمكنك استخدام البيانات لأي تطبيق آخر يستند إلى جداول Dataverse. يدعم التطبيق الحالي بشكل أساسي عمليات البحث حيث يمكن إحضار البيانات من كيانات رؤى الجمهور لمعرف عميل معين.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>إرفاق بيئة Dataverse بـ Customer Insights

**المؤسسات ذات بيئات Dataverse موجودة**

بإمكان المؤسسات التي تستخدم Dataverse [استخدام إحدى بيئات Dataverse الموجودة لديها](get-started-paid.md) عندما يقوم المسؤول بإعداد رؤى الجمهور. ومن خلال توفير عنوان URL لبيئة Dataverse، فهو يتصل ببيئة رؤى الجمهور الجديدة. لضمان أفضل أداء ممكن، يجب استضافة Customer Insights وبيئات Dataverse في نفس المنطقة.

لإرفاق بيئة Dataverse، قم بتوسيع **الإعدادات المتقدمة** عند إنشاء بيئة رؤى الجمهور. قدّم **عنوان URL لبيئة Microsoft Dataverse** وحدد خانة الاختيار **تمكين مشاركة البيانات**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Alt.":::

**مؤسسة جديدة**

إذا قمت بإنشاء مؤسسة جديدة عند إعداد Customer Insights، فستحصل على بيئة Dataverse جديدة بشكل تلقائي.

> [!NOTE]
> إذا كانت مؤسساتك تستخدم Dataverse في المستأجر الخاص بها، فمن الضروري أن تتذكر أن  [إنشاء بيئة Dataverse يخضع لمراقبة المسؤول.](/power-platform/admin/control-environment-creation.md). على سبيل المثال، إذا كنت تقوم بإعداد بيئة جديدة لرؤى الجمهور جديدة باستخدام حساب مؤسستك وكان المسؤول قد عطل إنشاء بيئات Dataverse التجريبية للجميع باستثناء المسؤولين، فلا يمكنك إنشاء بيئة تجريبية جديدة.
> 
> سعة تخزين بيئات Dataverse التجريبية التي تم إنشاؤها في Customer Insights هي 3 غيغابايت لا يتم حسابها بالنسبة إلى السعة الإجمالية التي يجب للمستأجر الحصول عليها. يحق للاشتراكات المدفوعة الحصول على 15 غيغابايت لتخزين قاعدة البيانات و20 غيغابايت لتخزين الملفات في Dataverse.

## <a name="output-entities"></a>كيانات الإخراج

تتوفر بعض كيانات الإخراج من رؤى الجمهور كجداول في Dataverse. تصف الأقسام أدناه المخطط المتوقع لهذه الجداول.

- [ملف تعريف العميل](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [الإثراء](#enrichment)
- [التنبؤ](#prediction)


### <a name="customerprofile"></a>ملف تعريف العميل

يحتوي هذا الجدول على ملف تعريف العميل الموحد من Customer Insights. يتوقف مخطط ملف تعريف العميل الموحد على الكيانات والسمات المستخدمة في عملية الدمج. يحتوي مخطط ملف تعريف العميل عادة على مجموعة فرعية من السمات من [تعريف نموذج البيانات العامة لـ CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

يحتوي جدول AlternateKey على مفاتيح الكيانات التي شاركت في عملية التوحيد.

|Column  |النوع  |الوصف   |
|---------|---------|---------|
|DataSourceName    |السلسلة‬         | اسم مصدر البيانات. على سبيل المثال: `datasource5`        |
|EntityName        | السلسلة‬        | اسم الكيان في رؤى الجمهور. على سبيل المثال: `contact1`        |
|AlternateValue    |السلسلة‬         |المعرف البديل الذي يتم تعيينه إلى معرف العميل. مثال: `cntid_1078`         |
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
