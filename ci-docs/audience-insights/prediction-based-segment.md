---
title: الشرائح على أساس إخراج التنبؤ
description: إنشاء شرائح استنادا إلى كيان الإخراج تنبؤ النموذج.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741413"
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

1. حدد الأشكال البيضاوية العمودية بجوار النموذج الذي تريد مراجعته وحدد **عرض**.

1. في صفحة النتائج، حدد **إنشاء شريحة**. لمزيد من المعلومات حول صفحة النتائج، راجع المقالة حول النموذج.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="لقطة شاشة لصفحة نتائج التنبؤ مع التركيز على إجراء إنشاء الشريحة.":::

1. أنشئ مقطعًا جديدًا استنادًا إلى كيان الإخراج للنموذج المحدد. لمزيد من المعلومات، راجع [إنشاء شرائح وإدارتها](segments.md).