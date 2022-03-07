---
title: حدود الخدمة في Dynamics 365 Customer Insights
description: فهم الحدود والقيود.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350391"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>حدود الخدمة في إمكانات Customer Insights

تصف هذه المقالة الحدود المضمنة في خدمة Customer Insights، والتي تم تصميمها لضمان ثبات الخدمة واستقرارها. يمكن اجراء أي طلبات تغيير من خلال [منتدى الأفكار](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>رؤى الجمهور

| المساحة  | الحدود  | ملاحظات  |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| المقاطع والمقاييس والتنبؤات | 300  | لا يمكن أن يتجاوز إجمالي عدد [المقاطع](audience-insights/segments.md)، و[القياسات](audience-insights/measures.md)، و[التنبؤات](audience-insights/predictions.md) المجمعة 300.  |
| العلاقات | 20 مستوى من التعمق في العلاقات في مسارات الكيانات. | عند إنشاء [شرائح](audience-insights/segments.md) أو [قياسات](audience-insights/measures.md) باستخدام واجهة منشئ البيانات، يمكن أن تكون لمسارات الكيانات ما يصل إلى 20 نقطة علاقة بين كيان البدء والكيان الهدف.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
