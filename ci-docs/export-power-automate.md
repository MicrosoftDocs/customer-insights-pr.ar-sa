---
title: موصل Power Automate  | Microsoft Docs
description: إنشاء عمليات سير المهام في Microsoft Power Automate من Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 409792bc3f12fca451ef038e3300758bdf9ecf3b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645553"
---
# <a name="power-automate-connector-preview"></a>موصل Power Automate (معاينة)

قم بتشغيل أحداث معينة لكي تحدث تلقائيًا عند تغيير بياناتك وأدر مزيدًا من عمليات سير المهام المعقدة مباشرةً في [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>القيود المعروفة

- يمكنك إجراء 100 مكالمة كحد أقصى لكل 60 ثانية. يمكنك استدعاء نقطة نهاية API عدة مرات باستخدام المعلمة $ skip. [تعرف على المزيد حول معلمة $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Power Automate المشغلات

استخدم المشغلات لإنشاء عمليات سير مهام في السحابة وأتمتة المهام المتكررة، مثل الإعلامات أو إجراءات أكثر تقدمًا. 

- التشغيل عند فشل تحديث مصدر البيانات. 
- التشغيل عند نجاح تحديث مصدر البيانات.
- التشغيل عند تخطي الحد في شريحة. يقتصر التشغيل على تجاوز الحد.
- التشغيل عند تخطي الحد في إجراء أعمال. يتم دعم فقط مقاييس العمل بدون بُعد. يقتصر التشغيل على تجاوز الحد.
- التشغيل عند اكتمال عملية تحديث كاملة (مصادر البيانات والشرائح والمقاييس، ...).
- تشغيل عند اكتمال تحديث عملية التوحيد (التعيين، المطابقة، الدمج).

[تكوين المشغلات في Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>إجراءات Power Automate

يوفر موصل Power Automate إجراءات أخرى بخلاف المشغلات المتوفرة. لمزيد من المعلومات، راجع [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>إنشاء سير مهام Power Automate

1. انتقل إلى **المسؤول** > **وجهات التصدير**.

1. على الإطار المتجانب **Power Automate**، حدد **إعداد‏‎**.

1. يفتح موصل Customer Insights (إصدار أولي) في Power Automate. **سجل دخولك إلى** to Power Automate.

1. اختر أحد المشغلات المتوفرة وأضف المزيد من الخطوات إلى سير المهام الجديد. لمزيد من المعلومات، راجع [إنشاء سير مهام في السحابة في Power Automate](/power-automate/get-started-logic-flow).

أمثلة على كيفية استخدام تدفقات: 
- نشر رسالة إلى قناة Microsoft Teams في حالة فشل تحديث مصدر بيانات. 
- إرسال بريد إلكتروني إلى مالكي البيانات عند تجاوز حد ما على الشريحة.



[!INCLUDE [footer-include](includes/footer-banner.md)]
