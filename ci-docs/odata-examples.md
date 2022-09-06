---
title: أمثلة على استعلامات OData لواجهات برمجة التطبيقات في Customer Insights
description: أمثلة شائعة الاستخدام لبروتوكول البيانات المفتوحة (OData) للاستعلام عن واجهات API الخاصة بـ Customer Insights لمراجعة البيانات.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 26e56a3bab01ba55284a52e72efbcbfbaadaad6f
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387186"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>أمثلة على استعلامات OData لواجهات برمجة التطبيقات في Customer Insights

بروتوكول البيانات المفتوحة (OData) هو بروتوكول وصول إلى البيانات مبني على بروتوكولات أساسية مثل HTTP. تستخدم منهجيات مقبولة بشكل عام مثل REST للويب. هناك أنواع مختلفة من المكتبات والأدوات التي يمكن استخدامها لاستهلاك خدمات OData.

لمساعدتك في إنشاء عمليات التنفيذ الخاصة بك استنادًا إلى [Customer Insights APIs](apis.md)، راجع بعض الاستعلامات النموذجية المطلوبة بشكل متكرر.

قم بتعديل نماذج الاستعلام لجعلها تعمل في البيئات المستهدفة:

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` حيث {instanceId} هو GUID لبيئة Customer Insights التي تريد الاستعلام عنها. تتيح [عملية ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) العثور على {InstanceId} الذي لديك الوصول إليه.
- {CID}:‏ GUID لسجل عميل موحد. مثال:`ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: معرف المفتاح الأساسي لسجل العميل في مصدر البيانات. مثال: `CNTID_1002`
- {DSname}: سلسلة مع اسم الكيان لمصدر البيانات الذي يتم نقله إلى Customer Insights. مثال:`Website_contacts`.
- {SegmentName}: سلسلة مع اسم كيان الإخراج لمقطع في Customer Insights. مثال:`Male_under_40`.

## <a name="customer"></a>العميل 

نموذج استعلامات كيان *العميل*.

|نوع الاستعلام |مثال  | ‏‫ملاحظة‬  |
|---------|---------|---------|
|معرف عميل واحد     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|مفتاح بديل    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  تستمر المفاتيح البديلة في كيان العميل الموحد       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|خلال    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|مفتاح بديل + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|بحث   | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   يُرجع أهم 10 نتائج لسلسلة بحث      |
|عضوية المقطع  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | إرجاع عدد الصفوف المعين مسبقًا من كيان التجزئة.      |
|عضوية المقطع للعميل | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | إرجاع ملف تعريف العميل إذا كان عضوًا في مقطع معين     |

## <a name="unified-activity"></a>النشاط الموحد

نموذج استعلامات كيان *UnifiedActivity*.

|نوع الاستعلام |مثال  | ‏‫ملاحظة‬  |
|---------|---------|---------|
|نشاط CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | سرد أنشطة ملف تعريف عميل محدد |
|إطار زمني النشاط    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  أنشطة ملف تعريف العميل في إطار زمني       |
|نوع النشاط     |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|النشاط حسب اسم العرض     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|فرز الأنشطة    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  فرز الأنشطة تصاعديًا أو تنازليًا       |
|تم توسيع النشاط من عضوية المقطع  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>أمثلة أخرى

نموذج استعلامات للكيانات الأخرى.

|نوع الاستعلام |مثال  | ‏‫ملاحظة‬  |
|---------|---------|---------|
|مقاييس CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|الأسماء التجارية التي تم إثراؤها لـ CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|الاهتمامات التي تم إثراؤها لـ CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|في بند + توسيع     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>استعلامات OData غير المدعومة

الاستعلامات التالية غير مدعومة بواسطة Customer Insights:

- `$filter` في كيانات المصادر التي تم استيعابها يمكنك فقط تشغيل استعلامات $filter على كيانات النظام التي يقوم Customer Insights بإنشائها.
- `$expand` من استعلام `$search`. مثال: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` من `$select` فقط في حال تحديد مجموعة فرعية من السمات. مثال: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- قام `$expand` بإثراء صلات العلامات التجارية أو الاهتمامات لعميل معين. مثال: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- الاستعلام عن كيانات إخراج نموذج التنبؤ عبر المفتاح الثانوي. مثال: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
