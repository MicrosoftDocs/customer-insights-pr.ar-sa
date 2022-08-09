---
title: إنشاء مقاطع بسيطة مع مقاطع سريعة
description: قم بإنشاء مقاطع بسيطة للعملاء لتجميعها استنادًا إلى العديد من السمات.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171124"
---
# <a name="create-simple-segments-with-quick-segments"></a>إنشاء مقاطع بسيطة مع مقاطع سريعة

تسمح لك المقاطع السريعة ببناء مقاطع بسيطة باستخدام عامل تشغيل واحد بسرعة للحصول على معلومات أسرع. يتم دعم المقاطع السريعة فقط في البيئات **للعملاء الفرديين**.

## <a name="create-a-new-segment-with-quick-segments"></a>إنشاء مقطع بسيط باستخدام مقاطع سريعة

1. انتقل إلى **المقاطع**.

1. حدد **جديد** > **إنشاء من**.
   - حدد خيار **ملفات التعريف** لإنشاء مقطع تستند إلى كيان *العميل الموحد*.
   - حدد خيار **القياسات** لبناء مقطع حول القياسات التي قمت إنشاؤها مسبقًا.
   - حدد الخيار **ذكاء** لإنشاء مقطع حول أحد كيانات الإخراج التي قمت بإنشاءها باستخدام إمكانات إما **التنبؤات** أو **نماذج مخصصة**.

1. في مربع الحوار **مقطع سريع جديد**، حدد سمة من القائمة المنسدلة **الحقل**. بناءً على اختيارك، يوفر النظام قيمًا مختلفة.
   - بالنسبة للحقول الفئوية، يتم عرض أهم 10 أعداد للعملاء. اختر **القيمة** وحدد **المراجعة**.
   - بالنسبة للسمة الرقمية، يُظهر النظام قيمة السمة التي تقع ضمن كل قيمة مئوية للعميل. اختر **عامل** و **قيمة**، ثم حدد **مراجعة**.

1. يوفر النظام **حجم مقطع مقدر**. اختر ما إذا كنت تريد إنشاء المقطع التي حددتها، أو ارجع لاختيار حقل مختلف.

   :::image type="content" source="media/quick-segment-name.png" alt-text="اسم وتقدير مقطع سريعة.":::

1. قم بتوفير **اسم** و **اسم كيان الإخراج** لشريحتك. بشكل اختياري، أضف [علامات](work-with-tags-columns.md#manage-tags).

1. حدد **حفظ** لحفظ المقطع. تظهر صفحة **المقاطع**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>الخطوات التالية

[تصدير مقطع](export-destinations.md) واستكشاف [تكامل بطاقة العميل](customer-card-add-in.md) لاستخدام المقاطع في تطبيقات أخرى.

[!INCLUDE [footer-include](includes/footer-banner.md)]
