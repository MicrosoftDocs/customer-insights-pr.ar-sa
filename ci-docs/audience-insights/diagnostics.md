---
title: تدقيق Dynamics 365 Customer Insights باستخدام Azure Monitor
description: تعرّف على كيفية إرسال السجلات إلى Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: d84ae8301bdf384c2484cdb1e7dd8eb75d406769
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376400"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>إعادة توجيه السجل في Dynamics 365 Customer Insights باستخدام Azure Monitor (إصدار أولي)

توفر Dynamics 365 Customer Insights تكاملاً مباشرًا مع Azure Monitor. تسمح لك سجلات موارد Azure Monitor بمراقبة وإرسال السجلات إلى [Azure Storage](https://azure.microsoft.com/services/storage/)، أو [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview)، أو دفقها إلى [مراكز أحداث Azure](https://azure.microsoft.com/services/event-hubs/).

تقوم Customer Insights بإرسال سجلات الأحداث التالية:

- **أحداث التدقيق**
  - **APIEvent** - يتيح إمكانية تعقب التغييرات الذي يتم عبر واجهة مستخدم Dynamics 365 Customer Insights.
- **الأحداث التشغيلية**
  - **WorkflowEvent** - سير العمل الذي يسمح للشخص بإعداد [مصادر البيانات](data-sources.md)، و[توحيد البيانات](data-unification.md) و[إثرائها](enrichment-hub.md) وأخيرًا [تصديرها](export-destinations.md) في أنظمة أخرى. يمكن القيام بكل هذه الخطوات بشكل فردي (على سبيل المثال، تشغيل عملية تصدير واحدة) أو بشكل منظم (على سبيل المثال، تحديث البيانات من مصادر البيانات التي تقوم بتشغيل عملية توحيد ستسحب عمليات الإثراء الإضافية وبمجرد الانتهاء، تقوم بتصدير البيانات إلى نظام آخر). لمزيد من التفاصيل، انظر [مخطط WorkflowEvent](#workflow-event-schema).
  - **APIEvent** - كافة استدعاءات API إلى مثيل العملاء إلى Dynamics 365 Customer Insights. لمزيد من التفاصيل، انظر [مخطط APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>إعداد إعدادات التشخيص

### <a name="prerequisites"></a>المتطلبات

لتكوين التشخيصات في Customer Insights، يجب تلبية المتطلبات الأساسية التالية:

- لديك [اشتراك Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) نشط.
- لديك [أذونات المسؤول](permissions.md#admin) في Customer Insights.
- لديك دور **المساهم** و **مسؤول وصول المستخدم** على المورد الوجهة في Azure. قد يكون المورد حساب Azure Storage أو مركز أحداث Azure أو مساحة عمل Azure Log Analytics. لمزيد من المعلومات، راجع [إضافة أو إزالة تعيينات أدوار Azure باستخدام مدخل Azure](/azure/role-based-access-control/role-assignments-portal).
- [تمت تلبية المتطلبات الوجهة](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) لـ Azure Storage أو مركز أحداث Azure أو Azure Log Analytics.
- لديك على الأقل دور **قارئ** في مجموعة الموارد التي ينتمي إليها المورد.

### <a name="set-up-diagnostics-with-azure-monitor"></a>إعداد التشخيصات باستخدام Azure Monitor

1. في Customer Insights، قم بتحديد **النظام** > **تشخيصات** لرؤية وجهات التشخيصات التي تم تكوينها لهذا المثيل.

1. حدد **إضافة وجهة**.

   > [!div class="mx-imgBorder"]
   > ![اتصال التشخيصات](media/diagnostics-pane.png "اتصال التشخيصات")

1. قم بتوفير اسم في الحقل **اسم وجهة عملية التشخيص**.

1. اختر **مستأجر** اشتراك Azure بالمورد الوجهة وحدد **تسجيل الدخول**.

1. حدد **نوع المورد** (حساب التخزين أو مركز الأحداث أو تحليلات السجل).

1. حدد **اشتراك** للمورد الوجهة.

1. حدد **مجموعة الموارد** للمورد الوجهة.

1. حدد **المورد**.

1. قم بتأكيد بيان **خصوصية البيانات وتوافقها**.

1. حدد **الاتصال بالنظام** للاتصال بالمورد الوجهة. تبدأ ملفات السجل في الظهور في الوجهة بعد 15 دقيقة، إذا كانت API قيد الاستخدام وتقوم بإنشاء أحداث.

### <a name="remove-a-destination"></a>إزالة وجهة

1. انتقل إلى **النظام** > **التشخيصات**.

1. حدد وجهة عملية التشخيص في القائمة.

1. في العمود **إجراءات**، قم بتحديد أيقونة **حذف**.

1. تأكد من الحذف لإيقاف إعادة توجيه السجل. لن يتم حذف المورد في اشتراك Azure. يمكنك تحديد الارتباط في العمود **إجراءات** لفتح مدخل Azure للمورد المحدد وحذفه هناك.

## <a name="log-categories-and-event-schemas"></a>فئات السجل ومخططات الأحداث

يتم حاليًا دعم [أحداث API](apis.md) وأحداث سير العمل وتنطبق الفئات والمخططات التالية.
يتبع مخطط السجل [المخطط الشائع لـ Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>الفئات

يوفر Customer Insights فئتين:

- **أحداث التدقيق**: [أحداث API](#api-event-schema) لتعقب تغييرات التكوين على الخدمة. تدخل عمليات `POST|PUT|DELETE|PATCH` في هذه الفئة.
- **الأحداث التشغيلية**: [أحداث API](#api-event-schema) أو [أحداث سير العمل](#workflow-event-schema) التي تم إنشاؤها أثناء استخدام الخدمة.  على سبيل المثال، طلبات `GET` أو أحداث تنفيذ سير عمل.

## <a name="configuration-on-the-destination-resource"></a>التكوين على المورد الوجهة

استنادًا إلى اختيارك لنوع المورد، سيتم تطبيق الخطوات التالية تلقائيًا:

### <a name="storage-account"></a>حساب التخزين

يحصل أساسي خدمة Customer Insights على إذن **مساهم حساب التخزين** على المورد المحدد وينشئ اثنتين من الحاويات ضمن مساحة الاسم المحددة:

- يحتوي `insight-logs-audit` على **أحداث التدقيق**
- يحتوي `insight-logs-operational` على **أحداث تشغيلية**

### <a name="event-hub"></a>مركز الأحداث

يحصل أساسي خدمة Customer Insights على إذن **‏‫مالك بيانات مراكز أحداث Azure‬** على المورد وسوف ينشئ اثنين من مراكز الأحداث ضمن مساحة الاسم المحددة:

- يحتوي `insight-logs-audit` على **أحداث التدقيق**
- يحتوي `insight-logs-operational` على **أحداث تشغيلية**

### <a name="log-analytics"></a>Log Analytics

يحصل أساسي خدمة Customer Insights على إذن **مساهم Log Analytics** على المورد. ستكون السجلات متوفرة ضمن **السجلات** > **الجداول** > **إدارة السجلات** في مساحة عمل Log Analytics المحددة. قم بتوسيع حل **إدارة السجلات** وحدد موقع جداول `CIEventsAudit` و`CIEventsOperational`.

- يحتوي `CIEventsAudit` على **أحداث التدقيق**
- يحتوي `CIEventsOperational` على **أحداث تشغيلية**

ضمن الإطار **استعلامات**، قم بتوسيع حل **التدقيق** وتحديد موقع نموذج الاستعلامات المقدم من خلال البحث عن `CIEvents`.

## <a name="event-schemas"></a>مخططات الأحداث

تشترك أحداث API وأحداث سير العمل في البنية وتختلف في التفاصيل، راجع [مخطط حدث API](#api-event-schema) أو [مخطط حدث سير العمل](#workflow-event-schema).

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

يحتوي سير العمل على خطوات متعددة. [استيعاب مصادر البيانات](data-sources.md)، [توحيد البيانات](data-unification.md)، [وإثراؤها](enrichment-hub.md)، و[تصديرها](export-destinations.md). يمكن تشغيل كل هذه الخطوات بشكل فردي أو تنظيمها باستخدام العمليات التالية. 

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
|                 |

#### <a name="workflow-properties-schema"></a>مخطط خصائص سير العمل

تتمتع أحداث سير العمل بالخصائص التالية.

| الحقل              | Workflow | المهمة | الوصف             |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | نعم       | نعم   | `WorkflowEvent` دائمًا، يضع علامة على الحدث كحدث سير عمل.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | نعم       | نعم   | معرف تشغيل سير العمل. جميع أحداث سير العمل وأحداث المهام في تنفيذ سير العمل لها نفس `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | نعم       | نعم   | معرف العملية، راجع [أنواع العمليات].(#operation-types)                                                                                                                                                                                       |
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
