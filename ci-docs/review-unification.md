---
title: مراجعة توحيد البيانات
description: مراجعة خطوات توحيد البيانات وإنشاء ملفات تعريف موحدة للعملاء ومراجعة النتائج
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741604"
---
# <a name="review-data-unification"></a>مراجعة توحيد البيانات

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

تعرض هذه الخطوة الأخيرة في عملية التوحيد ملخصًا للخطوات في العملية وتوفر فرصة لإجراء تغييرات قبل إنشاء ملف التعريف الموحد.

:::image type="content" source="media/m3_review.png" alt-text="لقطة شاشة للمراجعة وإنشاء ملفات تعريف العملاء.":::

## <a name="review-the-data-unification-steps"></a>مراجعة خطوات توحيد البيانات

1. حدد **تحرير** في أي من خطوات توحيد البيانات لمراجعة وإجراء أي تغييرات.

1. إذا كنت راضيًا عن اختياراتك، فحدد **إنشاء ملفات تعريف العملاء**. يتم عرض صفحة **التوحيد** أثناء إنشاء ملف تعريف العميل الموحد. تستغرق خوارزمية التوحيد بعض الوقت حتى تكتمل ولا يمكنك تغيير التكوين حتى يكتمل.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

عند اكتمال عملية التوحيد، يتم إدراج كيان ملف تعريف العميل الموحد، المسمى *العميل*، في صفحة **الكيانات** في قسم **ملفات التعريف**. تؤدي أول عملية توحيد ناجحة إلى إنشاء كيان *العميل* الموحد. كل عمليات التشغيل اللاحقة توسع هذا الكيان.

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
