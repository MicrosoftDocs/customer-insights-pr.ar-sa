---
title: حدود الخدمة في Customer Insights
description: التعرف على الحدود والقيود في خدمة Customer Insights SaaS.
ms.date: 05/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6d1b761a5c9f67bfdc7c5b152132c618db3ea36a
ms.sourcegitcommit: 78ef22cd39a1ebd7525f96829cd79d95f34438b9
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/07/2022
ms.locfileid: "8940652"
---
# <a name="service-limits-in-customer-insights"></a>حدود الخدمة في Customer Insights

تصف هذه المقالة الحدود المضمنة في خدمة Customer Insights، والتي تم تصميمها لضمان ثبات الخدمة واستقرارها. يمكن اجراء أي طلبات تغيير من خلال [منتدى الأفكار](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| المساحة  | الحدود  | ملاحظات  |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| المقاطع والمقاييس والتنبؤات | 300  | لا يمكن أن يتجاوز إجمالي عدد [المقاطع](segments.md)، و[القياسات](measures.md)، و[التنبؤات](predictions.md) المجمعة 300.  |
| العلاقات | 20 مستوى من التعمق في العلاقات في مسارات الكيانات. | عند إنشاء [شرائح](segments.md) أو [قياسات](measures.md) باستخدام واجهة منشئ البيانات، يمكن أن تكون لمسارات الكيانات ما يصل إلى 20 نقطة علاقة بين كيان البدء والكيان الهدف.  |

## <a name="fair-scheduling-of-jobs"></a>جدولة عادلة للوظائف

إن Customer Insights عبارة عن خدمة SaaS تستخدم موارد Azure المشتركة. يميل العملاء إلى تحمل أعباء عمل ذات كثافة متغيرة وفي جداول مختلفة. لضمان الوصول العادل إلى الموارد الأساسية ، نتأكد من تنفيذ عمليات النظام بترتيب عادل. من أمثلة عمليات النظام الوظائف المتعلقة بتوحيد البيانات أو تحديثات الشرائح أو حساب القياسات. وتحميك الجدولة العادلة من الوقوف في قوائم الانتظار للحصول على الموارد إذا كان هناك ارتفاع في الوظائف المطلوبة. وفي الوقت نفسه، لا يضمن Customer Insights معالجة جميع الوظائف التي تضعها في قائمة الانتظار بشكل متوازٍ.

[!INCLUDE [footer-include](includes/footer-banner.md)]
