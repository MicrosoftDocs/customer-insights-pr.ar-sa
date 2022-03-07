---
title: استخدام الأبعاد السكانية لتقسيم البيانات السلوكية (أبعاد منظمة)
description: استخدم الأبعاد المنظمة لملف التعريف الموحد لتمكين خصائص ملف تعريف العميل لرؤى الجمهور.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 95395e09bc0ba5ba93138957c62105f31c709e91
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232951"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>استخدام الأبعاد السكانية لتقسيم البيانات السلوكية

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

باستخدام الأبعاد السكانية لملف التعريف الموحد، بإمكان مستخدمي رؤى المشاركة الوصول إلى خصائص ملف تعريف رؤى الجمهور. بعد ذلك، يمكنك استخدام هذه الخصائص في التحليلات التفاعلية للبيانات السلوكية، بما في ذلك البيانات التي تم التقاطها من خلال رؤى المشاركة على مواقعك على الويب أو على تطبيق الأجهزة المحمولة.

>[!NOTE]
> تتضمن رؤى المشاركة أبعادًا جديدة لخصائص الأحداث. مزيد من المعلومات: [إنشاء الأبعاد وعرضها](dimensions.md)

## <a name="prerequisite"></a>المتطلب الأساسي

- بيئة رؤى مشاركة حيث توجد لديك بيانات ملف تعريف العملاء المرتبطة ببيئة رؤى الجمهور حيث يتم إنشاء ملفات تعريف العملاء. مزيد من المعلومات: [إنشاء ارتباط بين رؤى الجمهور ورؤى المشاركة](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> بعد إنشاء ارتباط بين بيئات رؤى الجمهور وبيئات رؤى المشاركة، قد تحتاج فقط إلى بيانات خاصة بخصائص ملف تعريف العميل، والتي يمكن أن تكون مفيدة كأبعاد في رؤى المشاركة. لمزيد من المعلومات، انتقل إلى [تمكين سمات وشرائح ملفات التعريف الموحدة لرؤى الجمهور](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>إنشاء تقرير مخصص جديد

1. في الجزء الأيسر، حدد **مخصص** > **تقرير جديد**، ثم حدد المقياس الذي تريده. (لهذا المثال، اخترنا **طرق عرض الصفحة حسب الساعة**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="تحديد مقياس.":::

2. في محرر الرسوم المرئية، حدد **الأبعاد**، ثم حدد **البيانات السكانية** في القائمة المنسدلة **نوع البُعد**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="حدد البيانات السكانية.":::

3. حدد بُعد **Signal.Customer.*xxx***. (هذا المثال يعرض Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="تحديد بُعد.":::
  
## <a name="limitations"></a>القيود

في الوقت الحالي، يمكنك فقط استخدام الأبعاد السكانية لتقسيم البيانات السلوكية.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
