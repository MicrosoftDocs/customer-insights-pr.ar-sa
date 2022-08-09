---
title: نظرة عامة على القياسات
description: تعرف على الكيفة التي تساعد بها القياسات في تحليل أداء عملك والإشارة إليه.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: ead57ccbdcaf9f86ee54d1f15de71a63f2e1081b
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170804"
---
# <a name="measures-overview"></a>نظرة عامة على القياسات

تساعدك القياسات على فهم سلوكيات العملاء وأداء الأعمال بشكل أفضل. فهي تنظر إلى القيم ذات الصلة من [ملفات التعريف الموحدة](data-unification.md). على سبيل المثال، تريد شركة ما رؤية *إجمالي الإنفاق لكل عميل* لفهم سجل الشراء للعميل الفردي أو قياس *إجمالي مبيعات الشركة* لفهم إجمالي الإيرادات في النشاط التجاري بأكمله.

أنشئ المقاييس للتخطيط لأنشطة الأعمال من خلال الاستعلام عن بيانات العميل واستخراج الرؤى. على سبيل المثال، أنشئ مقياس *إجمالي الإنفاق لكل عميل* و *إجمالي الإرجاع لكل عميل* للمساعدة على تحديد مجموعة من العملاء مع إنفاق عالٍ وإرجاع عالٍ. بعد ذلك، يمكنك [إنشاء مقطع](segments.md) استنادًا إلى هذه القياسات للحث على اتخاذ أفضل الإجراءات التالية.

## <a name="create-a-measure"></a>إنشاء مقياس

اختر كيفية إنشاء قياس بناءً على جمهورك المستهدف.

# <a name="individual-consumers-b-to-c"></a>[المستهلكون الفرديون (B-to-C)](#tab/b2c)

- من البداية باستخدام منشئ القياسات: [أنشئ الخاص بك](measure-builder.md).
- من القياسات الأكثر شيوعًا في الاستخدام: [استخدم القوالب المحددة مسبقًا](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[حسابات الأعمال (B-to-B)](#tab/b2b)

من البداية باستخدام منشئ القياسات: [أنشئ الخاص بك](measure-builder.md).

---

## <a name="manage-existing-measures"></a>إدارة القياسات الموجودة

انتقل إلى صفحة **القياسات** لعرض القياسات التي قمت بإنشائها وحالتها ونوع المقياس وآخر مرة تم فيها تحديث البيانات. يمكنك فرز قائمة المقاييس حسب أي عمود أو استخدام مربع البحث للعثور على المقياس الذي تريد إدارته.

حدد بجوار مقياس لعرض الإجراءات المتاحة. حدد اسم المقياس لمعاينة الناتج وتنزيل ملف CSV.

:::image type="content" source="media/measures-actions.png" alt-text="إجراءات لإدارة المقاييس الفردية."lightbox="media/measures-actions.png":::

- يمكنك **تحرير** القياس لتغيير خصائصه.
- يمكنك **تحديث** القياس ليتضمن أحدث البيانات.
- **إعادة تسمية** المقياس.
- يمكنك **تنشيط** أو **إلغاء تنشيط** القياس. لن يتم تحديث القياسات غير النشطة أثناء [تحديث مجدول](system.md#schedule-tab)، وتكون بـ **الحالة** المسجلة كـ **تم التخطي**، مما يشير إلى أنه لم تتم محاولة التحديث.
- يمكنك وضع **علامة** من أجل [إدارة العلامات](work-with-tags-columns.md#manage-tags) للقياس.
- **حذف** المقياس.
- **أعمدة‏‎** من أجل [لتخصيص الأعمدة](work-with-tags-columns.md#customize-columns) التي تظهر.
- **التصفية‏‎** من أجل [التصفية على العلامات](work-with-tags-columns.md#filter-on-tags).
- يمكنك **البحث عن الاسم** للبحث حسب اسم القياس.

## <a name="refresh-measures"></a>تحديث القياسات

يمكن تحديث القياسات في جدول تلقائي أو يمكن تحديثها يدويًا عند الطلب. لتحديث قياس أو أكثر يدويًا، حدده واختر **تحديث**. لـ [جدولة تحديث تلقائي](system.md#schedule-tab)، انتقل إلى **مسؤول** > **نظام** > **جدولة**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
