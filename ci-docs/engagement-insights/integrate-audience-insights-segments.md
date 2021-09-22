---
title: استخدام شرائح رؤى الجمهور لتصفية تقارير رؤى المشاركة
description: استخدم شرائح رؤى الجمهور في التحليلات التفاعلية للبيانات السلوكية التي تم التقاطها من خلال رؤى المشاركة على موقع ويب الخاص للعميل.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bdd5641bb17384725491f22f70ae967ad90b1696
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461042"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>استخدام شرائح رؤى الجمهور لتصفية تقارير رؤى المشاركة

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

باستخدام رؤى المشاركة، يمكنك استخدام شرائح رؤى الجمهور في التحليلات التفاعلية للبيانات السلوكية التي تم التقاطها من خلال رؤى المشاركة على مواقعك على الويب.

## <a name="prerequisite"></a>المتطلب الأساسي

- بيئة رؤى مشاركة حيث توجد لديك بيانات خاصة بشرائح رؤى الجمهور ترتبط ببيئة رؤى الجمهور حيث يتم إنشاء الشرائح وملفات تعريف العملاء. مزيد من المعلومات: [إنشاء ارتباط بين رؤى الجمهور ورؤى المشاركة](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>إنشاء شرائح رؤى الجمهور 

> [!IMPORTANT]
> كي تظهر شرائح رؤى الجمهور في رؤى المشاركة، يجب عليك أولاً [تشغيل عمليات الدمج والعمليات النهائية](../audience-insights/merge-entities.md). تعد العمليات النهائية مهمة لأنها تنشئ جدولاُ فريدًا يعمل على تحضير شرائح رؤى الجمهور لمشاركتها مع رؤى المشاركة. (في حالة جدولة عملية للنظام، فستتضمن تلقائيًا عمليات نهائية.)

يمكنك استخدام شرائح رؤى الجمهور في تقارير جاهزة أو تقارير مخصصة قمت بإنشائها للرؤى المشاركة. لمزيد من المعلومات، انتقل إلى [تقارير ملفات تعريف جاهزة](profile-reports.md) و[إنشاء تقارير مخصصة وتحريرها](custom-reports.md).

**لاستخدام شرائح رؤى الجمهور في تقارير رؤى المشاركة**

1. من صفحة  **مساحة العمل**، حدد **البيانات**، ثم حدد علامة التبويب **الشرائح**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="حدد علامة تبويب الشرائح.":::

   >[!NOTE]
   > يؤدي تحديد شريحة من رؤى الجمهور إلى نقلك إلى رؤى الجمهور، حيث يمكنك معرفة كيف تم إنشاء تلك الشريحة من حيث القواعد والمنطق. لمزيد من المعلومات حول شرائح رؤى الجمهور، انتقل إلى [عرض الشرائح وإنشاؤها](../audience-insights/segments.md).

2. حدد تقريرًا جاهزًا أو [أنشئ تقريرًا مخصصًا](custom-reports.md)، ثم حدد **إضافة شرط**. (على سبيل المثال، اخترنا تقرير **طرق عرض الصفحة**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="إضافة شرط.":::

3. حدد **تصفية حسب الشريحة**، وقم بتوسيع **نوع الشريحة** ، ثم حدد **بيانات سكانية**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="تحديد نوع شريحة البيانات السكانية.":::

4. قم بتوسيع قائمة **اسم الشريحة**، ثم اختر شريحة رؤى الجمهور.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="اختيار شريحة.":::

5. يمكنك تطبيق شريحة واحدة أو أكثر، بما في ذلك الشرائح السلوكية (رؤى المشاركة) وشرائح البيانات السكانية (رؤى الجمهور). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="يقتصر تقرير طرق عرض الصفحة على عملاء الولايات المتحدة الأمريكية وشرائح الصفحة الرئيسية.":::

في الصورة السابقة، تم تحديد الشريحتين **عملاء الولايات المتحدة** و **الصفحة الرئيسية**، مما يقيد تقرير **طرق عرض الصفحة** لعرض هاتين الشريحتين فقط. 


>[!NOTE]
> يمكنك استخدام شرائح رؤى الجمهور لتصفية التقارير الجاهزة والتقارير المخصصة والمسارات في رؤى المشاركة. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]