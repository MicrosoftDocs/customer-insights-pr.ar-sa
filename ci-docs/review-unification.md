---
title: مراجعة توحيد البيانات
description: مراجعة خطوات توحيد البيانات وإنشاء ملفات تعريف موحدة للعملاء ومراجعة النتائج
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139552"
---
# <a name="review-data-unification"></a>مراجعة توحيد البيانات

تعرض هذه الخطوة الأخيرة في عملية التوحيد ملخصًا للخطوات في العملية وتوفر فرصة لإجراء تغييرات قبل إنشاء ملف التعريف الموحد.

:::image type="content" source="media/m3_review.png" alt-text="لقطة شاشة للمراجعة وإنشاء ملفات تعريف العملاء.":::

## <a name="review-the-data-unification-steps"></a>مراجعة خطوات توحيد البيانات

1. حدد **تحرير** في أي من خطوات توحيد البيانات لمراجعة وإجراء أي تغييرات.

1. إذا كنت راضيًا عن اختياراتك، فحدد **إنشاء ملفات تعريف العملاء**. يتم عرض صفحة **التوحيد** أثناء إنشاء ملف تعريف العميل الموحد. تظهر كافة الإطارات المتجانبة باستثناء **الحقول المصدر** الحالة **في قائمة الانتظار** أو **جارٍ التحديث**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="لقطة شاشة لصفحة التوحيد مع إطارات متجانبة تُظهر الحالة في قائمة انتظار أو جارٍ التحديث.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

تستغرق خوارزمية التوحيد بعض الوقت حتى تكتمل ولا يمكنك تغيير التكوين حتى يكتمل. عند اكتمال عملية التوحيد، يتم إدراج كيان ملف تعريف العميل الموحد، المسمى *العميل*، في صفحة **الكيانات** في قسم **ملفات التعريف**. تؤدي أول عملية توحيد ناجحة إلى إنشاء كيان *العميل* الموحد. كل عمليات التشغيل اللاحقة توسع هذا الكيان.

## <a name="review-the-results-of-data-unification"></a>مراجعة نتائج توحيد البيانات

بعد التوحيد، تُظهر صفحة **البيانات** > **التوحيد** عدد ملفات تعريف العملاء الموحدة. يتم عرض نتائج كل خطوة في عملية التوحيد في كل إطار متجانب. على سبيل المثال، تُظهر **الحقول المصدر** عدد (حقول) السمات المعينة وتُظهر **السجلات المكررة** عدد من السجلات المكررة التي تم العثور عليها.

:::image type="content" source="media/m3_unified.png" alt-text="لقطة شاشة لصفحة توحيد البيانات بعد توحيد البيانات.":::

> [!TIP]
> لا يتم عرض الإطار المتجانب **شروط المطابقة** إلا في حالة تحديد كيانات متعددة.

نوصيك بمراجعة النتائج، لا سيما جودة [قواعد المطابقة](data-unification-update.md#manage-match-rules) الخاصة بك وتحسينها إذا لزم الأمر.

عند الحاجة، [قم بإجراء تغييرات على إعدادات التوحيد](data-unification-update.md) وأعد تشغيل ملف التعريف الموحد.

## <a name="next-step"></a>الخطوة التالية

قم بتكوين [الأنشطة](activities.md)، أو [الإثراء](enrichment-hub.md)، أو [العلاقات](relationships.md)، أو [القياسات](measures.md) لاكتساب المزيد من الرؤى حول عملائك.

[!INCLUDE[footer-include](includes/footer-banner.md)]
