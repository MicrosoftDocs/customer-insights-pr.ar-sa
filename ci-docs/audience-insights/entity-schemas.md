---
title: مخططات كيانات Customer Insights في نموذج البيانات العامة
description: العمل مع الكيانات في نموذج البيانات العامة.
ms.date: 04/17/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6667e411a1b56e13105a6b59b7b5d249bc8141ea
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596345"
---
# <a name="entity-schemas-in-common-data-model"></a>مخططات الكيانات في نموذج البيانات العامة

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[نموذج البيانات العامة](/common-data-model/) عبارة عن مواصفة تعريفية وتعريف للكيانات القياسية التي تمثل المفاهيم والأنشطة المستخدمة بشكل عام عبر تطبيقات الأعمال والإنتاجية. ويتوسع هذا النموذج ليشمل البيانات الرصدية والتحليلية. يوفر نموذج البيانات العامة كيانات أعمال محددة بطريقة واضحة ونمطية وقابلة للتوسعة — مثل الحساب ووحدة العمل والحالة وجهة الاتصال والعميل المتوقع والفرصة والمنتج — بالإضافة إلى التفاعلات مع المورّدين والعاملين والعملاء — مثل الأنشطة واتفاقيات مستوى الخدمة. بإمكان أي كان البناء على تعريفات نموذج البيانات العامة وتوسيعها للحصول على أفكار إضافية خاصة بالأعمال.

يسمح نموذج البيانات المشتركة هذا للعاملين على دمج التطبيقات والبيانات بالتعاون بشكل أسهل من خلال توفير تعريف موحد للبيانات. يتضمن نموذج البيانات العامة نظام بيانات تعريف غنيًا بالكيانات القياسية والعلاقات والتدرجات الهرمية والسمات والمزيد. وهو نشأ من تطبيقات Dynamics 365 وذو مصدر مفتوح على GitHub مع أكثر من 260 كيانًا قياسيًا. يساهم نظام كبير من شركاء داخليين وخارجيين في المفاهيم الخاصة بالمجال لنموذج البيانات العامة.

تقوم أنظمة وأنظمة أساسية متعددة بتطبيق نموذج البيانات العامة اليوم، بما في ذلك تدفقات بيانات Power BI وAzure Data Services. وهي مدعومة في Common Data Service وDynamics 365 وPower Apps وPower BI وخدمات Azure القادمة، مما يساعد على تراكم القيمة باتجاه [مبادرة البيانات المفتوحة](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>مخططات كيانات Customer Insights

لإنشاء طريقة عرض 360 درجة‬ للعميل وجعل نماذج Customer Insights متوفرة في نموذج البيانات العامة لتمكين التوسعة، قمنا بنشر مخططات الكيانات التالية:

| الكيان | الوصف |
|---------|---------|
|[نشاط العميل](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | نشاط ينفذه مستخدم لديه قيمة رصدية للأعمال. |
|[ملف تعريف العميل](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | شخص أو مؤسسة قامت بتنفيذ أنشطة عمل أو لديها القدرة على المشاركة في مثل هذه الأنشطة. |
|[تعريف القياس](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | تعريف مؤشرات الأداء الأساسية (KPI) المقسمة على صفر من الأبعاد أو أكثر (مثل المستخدمون النشطاء شهريًا، وإجمالي الإنفاق حسب العميل ومتوسط تكلفة الاستحواذ للعميل) |
|[الشريحة](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | تعريف مجموعة من الأعضاء الذين لديهم خصائص مشتركة. |
|[عضوية الشريحة](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | الأعضاء المشاركون في شريحة معينة. |

للحصول على مزيد من المعلومات، راجع الوثائق حول [مخططات كيانات Customer Insights في نموذج البيانات العامة](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>عرض الكيانات باستخدام متصفح كيانات نموذج البيانات العامة

يمكنك عرض الكيانات في [متصفح كيانات نموذج البيانات العامة](https://microsoft.github.io/CDM/). حدد الزر **تحميل من GitHub!** وانتقل إلى **foundationCommon** > **crmCommon** > **solutions** > **customerInsights** حيث ستعثر على كيانات Customer Insights وتعريفاتها.
> [!div class="mx-imgBorder"]
> ![متصفح كيانات CDS يعرض كيان CustomerActivity](media/CDM-entity-navigator.png "متصفح كيانات CDS يعرض كيان CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]