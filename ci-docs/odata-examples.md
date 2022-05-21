---
title: أمثلة OData لواجهات API الخاصة بـ Dynamics 365 Customer Insights
description: أمثلة شائعة الاستخدام لبروتوكول البيانات المفتوحة (OData) للاستعلام عن واجهات API الخاصة بـ Customer Insights لمراجعة البيانات.
ms.date: 05/10/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 007278e1330e1a8e64d524ded8496acaf83b874c
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740028"
---
# <a name="odata-query-examples"></a>أمثلة على استعلامات OData

بروتوكول البيانات المفتوحة (OData) هو بروتوكول وصول إلى البيانات مبني على بروتوكولات أساسية مثل HTTP. تستخدم منهجيات مقبولة بشكل عام مثل REST للويب. هناك أنواع مختلفة من المكتبات والأدوات التي يمكن استخدامها لاستهلاك خدمات OData.

تسرد هذه المقالة بعض الاستعلامات النموذجية المطلوبة بشكل متكرر لمساعدتك في إنشاء عمليات التنفيذ الخاصة بك استنادًا إلى [واجهات API الخاصة بـ Customer Insights](apis.md).

يجب عليك تعديل نماذج الاستعلام لجعلها تعمل في البيئات المستهدفة: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}` حيث {instanceId} هو GUID لبيئة Customer Insights التي تريد الاستعلام عنها. تتيح [عملية ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) العثور على {InstanceId} الذي لديك الوصول إليه.
- {CID}:‏ GUID لسجل عميل موحد. مثال:`ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: معرف المفتاح الأساسي لسجل العميل في مصدر البيانات. مثال: `CNTID_1002`
- {DSname}: سلسلة مع اسم الكيان لمصدر البيانات الذي يتم نقله إلى Customer Insights. مثال:`Website_contacts`.
- {SegmentName}: سلسلة مع اسم كيان الإخراج لمقطع في Customer Insights. مثال:`Male_under_40`.

## <a name="customer"></a>العميل 

يحتوي الجدول التالي على مجموعة من نماذج الاستعلامات لكيان *العميل*.


|نوع الاستعلام |مثال  | ‏‫ملاحظة‬  |
|---------|---------|---------|
|معرف عميل واحد     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|مفتاح بديل    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}' `         |  تستمر المفاتيح البديلة في كيان العميل الموحد       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|خلال    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|مفتاح بديل + In   | `Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|بحث   | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   يُرجع أهم 10 نتائج لسلسلة بحث      |
|عضوية المقطع  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10  `     | إرجاع عدد الصفوف المعين مسبقًا من كيان التجزئة.      |

## <a name="unified-activity"></a>النشاط الموحد

يحتوي الجدول التالي على مجموعة من نماذج الاستعلامات لكيان *UnifiedActivity*.

|نوع الاستعلام |مثال  | ‏‫ملاحظة‬  |
|---------|---------|---------|
|نشاط CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | سرد أنشطة ملف تعريف عميل محدد |
|إطار زمني النشاط    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  أنشطة ملف تعريف العميل في إطار زمني       |
|نوع النشاط     |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|النشاط حسب اسم العرض     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’ `        | |
|فرز الأنشطة    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  فرز الأنشطة تصاعديًا أو تنازليًا       |
|تم توسيع النشاط من عضوية المقطع  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>أمثلة أخرى

يحتوي الجدول التالي على مجموعة من نماذج الاستعلامات للكيانات الأخرى.

|نوع الاستعلام |مثال  | ‏‫ملاحظة‬  |
|---------|---------|---------|
|مقاييس CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|الأسماء التجارية التي تم إثراؤها لـ CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|الاهتمامات التي تم إثراؤها لـ CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|في بند + توسيع     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |
