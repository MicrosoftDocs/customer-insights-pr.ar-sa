---
title: موصل Power Automate (إصدار أولي) | ‏Microsoft Docs
description: إنشاء عمليات سير المهام في Microsoft Power Automate من Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196102"
---
# <a name="power-automate-connector-preview"></a>موصل Power Automate (معاينة)

قم بتشغيل أحداث معينة لكي تحدث تلقائيًا عند تغيير بياناتك وأدر مزيدًا من عمليات سير المهام المعقدة مباشرةً في [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>القيود المعروفة

- 100 مكالمة كحد أقصى لكل 60 ثانية. استخدم [معلمة $skip](/connectors/customerinsights/#get-items-from-an-entity) استدعاء نقطة نهاية API عدة مرات.

## <a name="power-automate-triggers"></a>Power Automate المشغلات

استخدم المشغلات لإنشاء عمليات سير مهام في السحابة وأتمتة المهام المتكررة، مثل الإعلامات أو إجراءات أكثر تقدمًا. استخدام المشغلات في الحالات التالية:

- فشل تحديث مصدر البيانات.
- نجاح تحديث مصدر البيانات.
- تجاوز حد في مقطع. يقتصر التشغيل على تجاوز الحد.
- تخطي الحد في إجراء أعمال. يتم دعم فقط مقاييس العمل بدون بُعد. يقتصر التشغيل على تجاوز الحد.
- اكتمال التحديث المجدول الكامل. لا يعمل هذا المشغل للتحديثات التي تم بدء تشغيلها يدويًا.
- اكتمال تحديث عملية التوحيد.

[تكوين المشغلات في Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>إجراءات Power Automate

يوفر موصل Power Automate إجراءات أخرى بخلاف المشغلات المتوفرة. لمزيد من المعلومات، راجع [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>إنشاء سير مهام Power Automate

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. على الإطار المتجانب **Power Automate**، حدد **إعداد‏‎**.

1. يفتح موصل Customer Insights (إصدار أولي) في Power Automate. **سجل دخولك إلى** to Power Automate.

1. اختر أحد المشغلات المتوفرة وأضف المزيد من الخطوات إلى سير المهام الجديد. لمزيد من المعلومات، راجع [إنشاء سير مهام في السحابة في Power Automate](/power-automate/get-started-logic-flow).

أمثلة على كيفية استخدام تدفقات: 
- نشر رسالة إلى قناة Microsoft Teams في حالة فشل تحديث مصدر بيانات. 
- إرسال بريد إلكتروني إلى مالكي البيانات عند تجاوز حد ما على المقطع.

[!INCLUDE [footer-include](includes/footer-banner.md)]
