---
title: إنشاء مقطع استنادًا إلى نموذج التنبؤ
description: إنشاء شرائح استنادا إلى كيان الإخراج تنبؤ النموذج.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610404"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>إنشاء شريحة استنادا إلى نموذج تنبؤ (معاينة)

تسري نتائج التنبؤات في بعض الأحيان على مجموعة فرعية من العملاء فقط. زيادة تخصيص التوصيات من خلال إنشاء شرائح من نتائج تنبؤ النماذج. على سبيل المثال، قد ترغب في تقديم توصيات معينة إلى العملاء الذين يفضلون نوع خدمة معين.

## <a name="prerequisites"></a>المتطلبات الأساسية

- على الأقل [أذونات المساهم](permissions.md) في Customer Insights.

- توصية منتج أو مجموعة معاملات أو مجموعة اشتراك أو نموذج قيمة مدى الحياة للعميل تم تكوينه في Customer Insights. راجع المتطلبات لإعداد النماذج المختلفة:

  - [نموذج توصيات المنتج](predict-product-recommendation.md)
  - [نموذج خسارة الاشتراك](predict-subscription-churn.md)
  - [نموذج خسارة المعاملة](predict-transactional-churn.md)
  - [نموذج قيمة عمر العميل](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>قم بإنشاء شريحة العملاء بناءً على التوقعات

1. انتقل إلى **الذكاء** > **التنبؤات** وحدد علامة التبويب **التنبؤات الخاصة بي‬**.

1. حدد النموذج الذي ترغب في مراجعته وحدد **عرض**.

1. في صفحة النتائج، حدد **إنشاء شريحة**. لمزيد من المعلومات حول صفحة النتائج، راجع المقالة حول النموذج.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="لقطة شاشة لصفحة نتائج التنبؤ مع التركيز على إجراء إنشاء الشريحة.":::

1. أنشئ شريحة جديدة باستخدام سمات من كيان الإخراج للنموذج المحدد. لمزيد من المعلومات، راجع [إنشاء شرائح وإدارتها](segments.md).

> [!TIP]
> يمكنك أيضًا إنشاء شريحة لنموذج تنبؤ من صفحة **الشرائح** عن طريق تحديد **جديد** واختيار **إنشاء من** > **التحليل الذكي**. لمزيد من المعلومات، راجع [إنشاء شريحة جديدة باستخدام شرائح سريعة](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
