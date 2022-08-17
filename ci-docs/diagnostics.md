---
title: تصدير سجلات التشخيص (معاينة)
description: تعرّف على كيفية إرسال السجلات إلى Microsoft Azure Monitor.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 60b039173fd938482c782c7394420d4951c222a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245909"
---
# <a name="export-diagnostic-logs-preview"></a>تصدير سجلات التشخيص (معاينة)

سجلات إعادة التوجيه من Customer Insights باستخدام Azure Monitor. تسمح لك سجلات موارد Azure Monitor بمراقبة وإرسال السجلات إلى [Azure Storage](https://azure.microsoft.com/services/storage/)، أو [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview)، أو دفقها إلى [مراكز أحداث Azure](https://azure.microsoft.com/services/event-hubs/).

يرسل Customer Insights سجلات الأحداث التالية:

- **أحداث التدقيق**
  - **APIEvent** - يتيح تتبع التغيير عبر Dynamics 365 Customer Insights واجهة المستخدم.
- **الأحداث التشغيلية**
  - **WorkflowEvent** - يتيح لك إعداد [مصادر البيانات](data-sources.md), [توحد](data-unification.md), [وإثراء ](enrichment-hub.md) و،[تصدير](export-destinations.md) البيانات في أنظمة أخرى. يمكن تنفيذ هذه الخطوات بشكل فردي (على سبيل المثال ، بدء عملية تصدير واحدة). يمكنهم أيضًا تشغيل منسق (على سبيل المثال ، تحديث البيانات من مصادر البيانات التي تؤدي إلى عملية التوحيد ، والتي ستجذب الإثراء وتصدير البيانات إلى نظام آخر). لمزيد من المعلومات، راجع [مخطط WorkflowEvent](#workflow-event-schema).
  - **APIEvent** -يرسل جميع استدعاءات API الخاصة بنسخة العملاء إلى Dynamics 365 Customer Insights. لمزيد من المعلومات، راجع [مخطط APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>إعداد إعدادات التشخيص

### <a name="prerequisites"></a>المتطلبات

- اشتراك Azure [نشط](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/).
- [أذونات](permissions.md#admin) المسؤول في Customer Insights.
- [دور المسؤول للمساهم ووصول المستخدم](/azure/role-based-access-control/role-assignments-portal) في المورد الوجهة على Azure.. قد يكون المورد حساب Azure Data Lake Storage أو مركز أحداث Azure أو مساحة عمل Azure Log Analytics. هذا الإذن ضروري أثناء تكوين إعدادات التشخيص في Customer Insights ، ولكن يمكن تغييره بعد الإعداد الناجح.
- [متطلبات الوجهة](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) بالنسبة إلى Azure Storage أو مركز أحداث Azure أو Azure Log Analytics.
- على الأقل دور **القارئ** في مجموعة الموارد التي ينتمي إليها المورد.

### <a name="set-up-diagnostics-with-azure-monitor"></a>إعداد التشخيصات باستخدام Azure Monitor

1. في Customer Insights.، انتقل إلى **المسؤل** > **النظام** وحدد **علامة تبويب** التشخيص.

1. حدد **إضافة وجهة**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="اتصال التشخيص.":::

1. قم بتوفير اسم في الحقل **اسم وجهة عملية التشخيص**.

1. حدد **نوع المورد** (حساب التخزين أو Event Hub أو Log Analytics).

1. حدد **الاشتراك**, **مجموعة الموارد** و، **المورد** لمورد الوجهة. راجع [التكوين على المورد الوجهة](#configuration-on-the-destination-resource) للحصول على إذن وتسجيل المعلومات.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **الاتصال بالنظام** للاتصال بالمورد الوجهة. تبدأ ملفات السجل في الظهور في الوجهة بعد 15 دقيقة، إذا كانت API قيد الاستخدام وتقوم بإنشاء أحداث.

## <a name="configuration-on-the-destination-resource"></a>التكوين على المورد الوجهة

بناءً على اختيارك لنوع المورد، تحدث التغييرات التالية تلقائيًا:

### <a name="storage-account"></a>حساب التخزين

يحصل أساسي خدمة Customer Insights على إذن **مساهم حساب التخزين** على المورد المحدد وينشئ اثنتين من الحاويات ضمن مساحة الاسم المحددة:

- يحتوي `insight-logs-audit` على **أحداث التدقيق**
- يحتوي `insight-logs-operational` على **أحداث تشغيلية**

### <a name="event-hub"></a>مركز الأحداث

يحصل مدير خدمة Customer Insights. على **مالك بيانات Azure Event Hubs** إذن على المورد وإنشاء مركزي أحداث ضمن مساحة الاسم المحددة:

- يحتوي `insight-logs-audit` على **أحداث التدقيق**
- يحتوي `insight-logs-operational` على **أحداث تشغيلية**

### <a name="log-analytics"></a>Log Analytics

يحصل أساسي خدمة Customer Insights على إذن **مساهم Log Analytics** على المورد. السجلات متوفرة تحت **السجلات** > **الجداول** > **إدارة السجل** في مساحة عمل تحليلات السجل المحددة. قم بتوسيع حل **إدارة السجلات** وحدد موقع جداول `CIEventsAudit` و`CIEventsOperational`.

- يحتوي `CIEventsAudit` على **أحداث التدقيق**
- يحتوي `CIEventsOperational` على **أحداث تشغيلية**

ضمن الإطار **استعلامات**، قم بتوسيع حل **التدقيق** وتحديد موقع نموذج الاستعلامات المقدم من خلال البحث عن `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>إزالة وجهة التشخيص

1. انتقل إلى **المسؤل** > **النظام** وحدد **علامة تبويب** التشخيص.

1. حدد وجهة عملية التشخيص في القائمة.

   > [!TIP]
   > تؤدي إزالة الوجهة إلى إيقاف إعادة توجيه السجل ، ولكنها لا تحذف المورد في اشتراك Azure. لحذف المورد في Azure ، حدد الارتباط في عمود **أجراءات** لفتح مدخل Azure للمورد المحدد وحذفه هناك. ثم احذف وجهة التشخيص.

1. في العمود **إجراءات**، قم بتحديد أيقونة **حذف**.

1. قم بتأكيد الحذف لإزالة الوجهة وإيقاف إعادة توجيه السجل.

## <a name="log-categories-and-event-schemas"></a>فئات السجل ومخططات الأحداث

يتم حاليًا دعم [أحداث API](apis.md) وأحداث سير العمل وتنطبق الفئات والمخططات التالية.
يتبع مخطط السجل [المخطط الشائع لـ Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>الفئات

يوفر Customer Insights فئتين:

- **أحداث التدقيق**: [أحداث API](#api-event-schema) لتعقب تغييرات التكوين على الخدمة. تدخل عمليات `POST|PUT|DELETE|PATCH` في هذه الفئة.
- **الأحداث التشغيلية**: [أحداث API](#api-event-schema) أو [أحداث سير العمل](#workflow-event-schema) التي تم إنشاؤها أثناء استخدام الخدمة.  على سبيل المثال، طلبات `GET` أو أحداث تنفيذ سير عمل.

## <a name="event-schemas"></a>مخططات الأحداث

أحداث API وأحداث سير العمل لها بنية مشتركة ، ولكن مع بعض الاختلافات. لمزيد من المعلومات، راجع [مخطط حدث API](#api-event-schema) أو [مخطط حدث سير العمل](#workflow-event-schema).

### <a name="api-event-schema"></a>مخططات أحداث API

| الحقل             | نوع البيانات  | مطلوب/اختياري | الوصف        | مثال        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | الطابع الزمني | مطلوبة          | الطابع الزمني للحدث (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | السلسلة‬    | مطلوبة          | ResourceId للمثيل الذي أطلق الحدث         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | السلسلة‬    | مطلوبة          | اسم العملية التي يمثلها هذا الحدث.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | السلسلة‬    | مطلوبة          | فئة السجل للحدث. إما `Operational` أو `Audit`. كل طلبات POST/PUT/PATCH/DELETE HTTP موضوع عليها علامة `Audit`، أي شيء آخر بعلامة `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | السلسلة‬    | مطلوبة          | حالة الحدث. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | السلسلة‬    | اختيارية          | حالة نتيجة الحدث. إذا كانت العملية مطابقة لاستدعاء واجهة برمجة تطبيقات REST، فهي رمز حالة HTTP.        | `200`             |
| `durationMs`      | طويل      | اختيارية          | مدة العملية بالمللي ثانية.     | `133`     |
| `callerIpAddress` | السلسلة‬    | اختيارية          | عنوان IP للمتصل، إذا كانت العملية تتوافق مع استدعاء API الذي يأتي من عنوان IP متاح للجمهور.                                                 | `144.318.99.233`         |
| `identity`        | السلسلة‬    | اختيارية          | كائن JSON يصف هوية المستخدم أو التطبيق الذي قام بالعملية.       | راجع قسم [الهوية](#identity-schema).     |  
| `properties`      | السلسلة‬    | اختيارية          | كائن JSON مع مزيد من الخصائص لفئة معينة من الأحداث.      | راجع قسم [الخصائص](#api-properties-schema).    |
| `level`           | السلسلة‬    | مطلوبة          | مستوى خطورة الحدث.    | `Informational` أو `Warning` أو `Error` أو `Critical`.           |
| `uri`             | السلسلة‬    | اختيارية          | عنوان URI المطلق للطلب.    |               |

#### <a name="identity-schema"></a>مخطط الهوية

يحتوي كائن `identity` JSON على البنية التالية

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| الحقل                         | الوصف                                                                                                                           |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | دور تم تعيينه للمستخدم أو التطبيق. لمزيد من المعلومات، راجع [أذونات المستخدم](permissions.md).                                     |
| `Authorization.RequiredRoles` | الأدوار المطلوبة للقيام بالعملية. دور `Admin` مسموح به للقيام بجميع العمليات.                                                    |
| `Claims`                      | مطالبات الرمز المميز لويب JSON للمستخدم أو التطبيق (JWT). تختلف خصائص المطالبة حسب المؤسسة وتكوين Azure Active Directory. |

#### <a name="api-properties-schema"></a>مخطط خصائص API

[تتمتع أحداث API](apis.md) بالخصائص التالية.

| الحقل                        | الوصف                                                                                                             |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | `ApiEvent` دائمًا، يضع علامة على حدث السجل كحدث API.                                                                 |
| `properties.userAgent`       | عامل المتصفح الذي يرسل الطلب أو `unknown`.                                                                        |
| `properties.method`          | طريقة HTTP: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | مسار الطلب النسبي.                                                                                          |
| `properties.origin`          | عنوان URI يشير إلى مصدر الإحضار أو `unknown`.                                                                  |
| `properties.operationStatus` | `Success` لرمز حالة HTTP < 400 <br> `ClientError` لرمز حالة HTTP < 500 <br> `Error` لحالة HTTP >= 500 |
| `properties.tenantId`        | معرّف المؤسسة                                                                                                        |
| `properties.tenantName`      | اسم المؤسسة.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId للمتصل.                                                                         |
| `properties.instanceId`      | Customer Insights `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>مخطط حدث سير العمل

يحتوي سير العمل على خطوات متعددة. [استيعاب مصادر البيانات](data-sources.md)، [توحيد البيانات](data-unification.md)، [وإثراؤها](enrichment-hub.md)، و[تصديرها](export-destinations.md). يمكن تشغيل كل هذه الخطوات بشكل فردي أو بتنسيق مع العمليات التالية.

#### <a name="operation-types"></a>أنواع العمليات

| OperationType     | Group (المجموعة)                                     |
| ----------------- | ----------------------------------------- |
| استيعاب         | [مصادر البيانات](data-sources.md)           |
| DataPreparation   | [مصادر البيانات](data-sources.md)           |
| تعيين               | [توحيد البيانات](data-unification.md)   |
| مطابقة             | [توحيد البيانات](data-unification.md)   |
| ‏‏دمج             | [توحيد البيانات](data-unification.md)   |
| ProfileStore      | [ملفات تعريف العملاء](customer-profiles.md) |
| بحث             | [ملفات تعريف العملاء](customer-profiles.md) |
| النشاط          | [أنشطة](activities.md)                  |
| AttributeMeasures | [المقاطع والمقاييس](segments.md)      |
| EntityMeasures    | [المقاطع والمقاييس](segments.md)      |
| القياسات          | [المقاطع والمقاييس](segments.md)      |
| التقسيم      | [المقاطع والمقاييس](segments.md)      |
| الإثراء        | [الإثراء](enrichment-hub.md)                                          |
| المعلومات      | [التنبؤات](predictions-overview.md)                                          |
| AiBuilder         | [التنبؤات](predictions-overview.md)                                          |
| الرؤى          | [التنبؤات](predictions-overview.md)                                          |
| Export            | [التصديرات](export-destinations.md)                                          |
| ModelManagement   | [التنبؤات](custom-models.md)                                           |
| العلاقة       | [توحيد البيانات](relationships.md)                                           |

#### <a name="field-description"></a>وصف الحقل

| الحقل           | نوع البيانات  | مطلوب/اختياري | الوصف                                                                                                                                                    | مثال                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | الطابع الزمني | مطلوبة          | الطابع الزمني للحدث (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | السلسلة‬    | مطلوبة          | ResourceId للمثيل الذي أطلق الحدث.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | السلسلة‬    | مطلوبة          | اسم العملية التي يمثلها هذا الحدث. `{OperationType}.[WorkFlow|Task][Started|Completed]`. راجع [أنواع العمليات](#operation-types) كمرجع. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | السلسلة‬    | مطلوبة          | فئة السجل للحدث. `Operational` دائمًا لأحداث سير العمل                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | السلسلة‬    | مطلوبة          | حالة الحدث. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | طويل      | اختيارية          | مدة العملية بالمللي ثانية.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | السلسلة‬    | اختيارية          | كائن JSON مع مزيد من الخصائص لفئة معينة من الأحداث.                                                                                        | راجع القسم الفرعي [خصائص سير العمل](#workflow-properties-schema)                                                                                                       |
| `level`         | السلسلة‬    | مطلوبة          | مستوى خطورة الحدث.                                                                                                                                  | `Informational`، أو`Warning`، أو `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>مخطط خصائص سير العمل

تتمتع أحداث سير العمل بالخصائص التالية.

| الحقل              | Workflow | المهمة | الوصف             |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | نعم       | نعم   | `WorkflowEvent` دائمًا، يضع علامة على الحدث كحدث سير عمل.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | نعم       | نعم   | معرف تشغيل سير العمل. جميع أحداث سير العمل وأحداث المهام في تنفيذ سير العمل لها نفس `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | نعم       | نعم   | معرف العملية، راجع [أنواع العمليات](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | نعم       | لا    | سير العمل فقط. عدد المهام التي يطلقها سير العمل.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | نعم       | لا    | اختياري. أحداث سير العمل فقط. Azure Active Directory [objectId للمستخدم](/azure/marketplace/find-tenant-object-id#find-user-object-id) الذي قام بتشغيل سير العمل، انظر أيضًا `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | نعم       | لا    | تحديث `full` أو `incremental`.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | نعم       | لا    | `OnDemand` أو `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | نعم       | لا    | `Running` أو `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | نعم       | نعم   | الطابع الزمني UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | نعم       | نعم   | الطابع الزمني UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | نعم       | نعم   | الطابع الزمني UTC `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | نعم       | نعم   | Customer Insights `instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | لا        | نعم   | - بالنسبة إلى OperationType = `Export`، يكون المعرف هو دليل تكوين التصدير. <br> - بالنسبة إلى OperationType = `Enrichment`، يكون هو دليل الإثراء <br> - بالنسبة إلى OperationType `Measures` و`Segmentation`، يكون المعرف هو اسم الكيان. |
| `properties.friendlyName`                    | لا        | نعم   | الاسم سهل الاستخدام للمستخدم للتصدير أو الكيان الذي تمت معالجته.                                                                                                                                                                                           |
| `properties.error`                           | لا        | نعم   | اختياري. رسالة خطأ بمزيد من التفاصيل.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | لا        | نعم   | اختياري. بالنسبة إلى OperationType `Export` فقط. يحدد نوع التصدير. لمزيد من المعلومات، راجع [نظرة عامة على وجهات التصدير](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | لا        | نعم   | اختياري. بالنسبة إلى OperationType `Export` فقط. يتضمن قائمة بالكيانات المكونة في التصدير.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | لا        | نعم   | اختياري. بالنسبة إلى OperationType `Export` فقط. رسالة تفصيلية للتصدير.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | لا        | نعم   | اختياري. بالنسبة إلى OperationType `Segmentation` فقط. يشير إلى إجمالي عدد الأعضاء في المقطع.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
