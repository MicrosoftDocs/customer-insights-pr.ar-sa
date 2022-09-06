---
title: حدود الخدمة في Customer Insights
description: التعرف على الحدود والقيود في خدمة Customer Insights SaaS.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 421e1aa41a54a4b8c34ac27fc7c02e510d2bb588
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387140"
---
# <a name="service-limits-in-customer-insights"></a>حدود الخدمة في Customer Insights

 يحتوي Customer Insights على حدود مضمنة مصممة لضمان موثوقية الخدمة واستقرارها. يمكن اجراء أي طلبات تغيير من خلال [منتدى الأفكار](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| المساحة  | الحدود  | ملاحظات  |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| المقاطع والمقاييس والتنبؤات | 300  | لا يمكن أن يتجاوز إجمالي عدد [المقاطع](segments.md)، و[القياسات](measures.md)، و[التنبؤات](predictions.md) المجمعة 300.  |
| العلاقات | 20 مستوى من التعمق في العلاقات في مسارات الكيانات. | عند إنشاء [شرائح](segments.md) أو [قياسات](measures.md) باستخدام واجهة منشئ البيانات، يمكن أن تكون لمسارات الكيانات ما يصل إلى 20 نقطة علاقة بين كيان البدء والكيان الهدف.  |

## <a name="fair-scheduling-of-jobs"></a>جدولة عادلة للوظائف

إن Customer Insights عبارة عن خدمة SaaS تستخدم موارد Azure المشتركة. يميل العملاء إلى تحمل أعباء عمل ذات كثافة متغيرة وفي جداول مختلفة. لضمان الوصول العادل إلى الموارد الأساسية ، نتأكد من تنفيذ عمليات النظام بترتيب عادل. من أمثلة عمليات النظام الوظائف المتعلقة بتوحيد البيانات أو تحديثات الشرائح أو حساب القياسات. وتحميك الجدولة العادلة من الوقوف في قوائم الانتظار للحصول على الموارد إذا كان هناك ارتفاع في الوظائف المطلوبة. وفي الوقت نفسه، لا يضمن Customer Insights معالجة جميع الوظائف التي تضعها في قائمة الانتظار بشكل متوازٍ.

[!INCLUDE [footer-include](includes/footer-banner.md)]
