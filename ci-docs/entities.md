---
title: الكيانات ومجموعات البيانات
description: عرض البيانات في صفحة الكيانات.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: c1094bc2f6d137087b317ed20d0615289d6f1187
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645506"
---
# <a name="entities-in-customer-insights"></a>الكيانات في Customer Insights

بعد [تكوين مصادر البيانات الخاصة بك](data-sources.md)، انتقل إلى صفحة **الكيانات** لتقييم جودة البيانات المستوعبة. تعتبر الكيانات بمثابة مجموعات بيانات. يتم بناء العديد من قدرات Dynamics 365 Customer Insights حول هذه الكيانات. يُمكن أن يساعدك مراجعة هذه الكيانات بشكل كبير في التحقق من صحة إخراج هذه الإمكانيات. 

تسرد صفحة **الكيانات** الكيانات وتتضمن هذه الأعمدة:

- **الاسم**: اسم كيان البيانات. إذا شاهدت رمز تحذير بجوار اسم الكيان، فهذا يعني أن البيانات لهذا الكيان لم يتم تحميلها بنجاح.
- **المصدر**: نوع مصدر البيانات الذي استوعب الكيان.
- **محدّث**: آخر مرة تم فيها تحديث الكيان.
- **الحالة**: تفاصيل حول آخر تحديث للكيان.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>استكشاف بيانات كيان معين

1. انتقل إلى **البيانات** > **الكيانات**.
1. من صفحة **الكيانات**، حدد كيانًا لفتح صفحة التفاصيل.  
1. استكشاف الحقول والسجلات المختلفة المُضمنة لذلك الكيان.

- يتم تحديد علامة التبويب **السمات** افتراضيا وهي تعرض جدولاً لمراجعة التفاصيل الخاصة بالكيانات المحددة، مثل أسماء الحقول وأنواع البيانات والأنواع. يظهر عمود **النوع** الأنواع المقترنة بنموذج البيانات المشتركة، والتي تكون إما مُحددة تلقائيًا بواسطة النظام أو [مُعينة يدويًا](map-entities.md) بوسطة المستخدمين. تُعد هذه الأنواع أنواع دلالية والتي يمكن أن تختلف عن أنواع بيانات السمات. على سبيل المثال، يحتوي الحقل *البريد الإلكتروني* أدناه على نوع بيانات *نص* ولكن نوع نموذج البيانات المشترك (الدلالي) الخاص به قد يكون *البريد الإلكتروني* أو *عنوان البريد الإلكتروني*.

> [!div class="mx-imgBorder"]
> ![جدول الحقول.](media/data-manager-entities-fields.PNG "جدول الحقول")

> [!NOTE]
> تعرض هذه الصفحة عينة فقط من بيانات الكيان. لعرض مجموعة البيانات الكاملة، انتقل إلى صفحة **Data sources (مصادر البيانات)**، حدد كيانًا، وحدد **Edit (تحرير)**، ثم اعرض بيانات الكيان باستخدام محرر Power Query على النحو الموضح في [مصادر البيانات ](data-sources.md).

لمعرفة المزيد حول البيانات المستوعبة في الكيان، يوفر لك عمود **الملخص** بعض الخصائص الهامة للبيانات، مثل القيم الخالية والقيم المفقودة والقيم الفريدة والتوزيعات، على النحو المنطبق على بياناتك. حدد أيقونة المخطط لرؤية ملخص البيانات.

> [!div class="mx-imgBorder"]
> ![رمز الملخص.](media/data-manager-entities-summary.png "جدول ملخص البيانات")

- تعرض علامة تبويب **البيانات** تفاصيل قائمة الجدول حول السجلات الفردية للكيان. تعتمد التفاصيل المدرجة على نوع بيانات الكيان.

> [!div class="mx-imgBorder"]
> ![حدد كيانًا.](media/data-manager-entities-data.png "تحديد كيان")

- تتيح لك علامة التبويب **التقارير** (المتوفرة لبعض الكيانات) إمكانية تصور البيانات من خلال إنشاء تقرير، وتتضمن هذه الأعمدة:

  - **اسم التقرير**: اسم التقرير.
  - **مُنشأ بواسطة**: اسم الشخص الذي أنشأ الكيان.
  - **تم الإنشاء**: تاريخ ووقت إنشاء الكيان.
  - **تم تحرير بواسطة**: اسم الشخص الذي قام بتعديل الكيان.
  - **تم التحرير**: تاريخ ووقت تعديل الكيان. 

## <a name="entity-specific-information"></a>معلومات خاصة بالكيانات

يوفر القسم التالي معلومات حول بعض الكيانات التي أنشأها النظام.

### <a name="corrupted-data-sources"></a>مصادر بيانات تالفة

يمكن أن تحتوي الحقول من مصدر بيانات تم إدخاله على بيانات تالفة. تُعرض السجلات ذات الحقول التالفة في الكيانات التي تم إنشاؤها بواسطة النظام. تساعدك معرفة السجلات التالفة في تحديد البيانات التي يجب مراجعتها وتحديثها على النظام المصدر. بعد التحديث التالي لمصدر البيانات، يتم نقل السجلات الصحيحة إلى Customer Insights وتمريرها إلى العمليات النهائية. 

على سبيل المثال، يحتوي عمود "عيد الميلاد" على نوع بيانات معين وهو "تاريخ". يتم إدخال تاريخ الميلاد لسجل العميل على أنه '01/01/19777'. سيقوم النظام بوضع علامة على هذا السجل على أنه تالف. يمكن لأي شخص الآن تغيير تاريخ الميلاد في نظام المصدر إلى "1977". بعد التحديث التلقائي لمصادر البيانات، يكون للحقل الآن تنسيق صالح وستتم إزالة السجل من الكيان التالف. 

انتقل إلى **البيانات** > **الكيانات** وابحث عن الكيانات التالفة في قسم **النظام**. يكون تسمية مخطط الكيانات التالفة: هو 'DataSourceName_EntityName_corrupt'. حدد كيانًا تالفًا لتحديد جميع الحقول التالفة والسبب على مستوى السجل الفردي.
> [!div class="mx-imgBorder"]
> ![سبب التلف.](media/corruption-reason.png "سبب التلف")

لا يزال Customer Insights يقوم بمعالجة السجلات التالفة. ومع ذلك، قد تتسبب في حدوث مشكلات عند العمل مع البيانات الموحدة.

يتم إجراء عمليات التحقق التالية على البيانات التي تم إدخالها لكشف السجلات التالفة: 

- لا تتطابق قيمة الحقل مع نوع بيانات العمود الخاصة به.
- تحتوي الحقول على أحرف تتسبب في عدم تطابق الأعمدة مع المخطط المتوقع. على سبيل المثال: علامات الاقتباس المنسقة بشكل غير صحيح أو علامات الاقتباس التي لم يتم تجاوزها أو أحرف السطر الجديد.
- في حالة وجود أعمدة التاريخ والوقت/التاريخ/datetimeoffset، يجب تحديد تنسيقها في النموذج إذا لم تكن تتبع تنسيق ISO القياسي.


[!INCLUDE [footer-include](includes/footer-banner.md)]