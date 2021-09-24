---
title: حدود الخدمة في Dynamics 365 Customer Insights
description: فهم الحدود والقيود.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483637"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>حدود الخدمة في إمكانات Customer Insights

تصف هذه المقالة الحدود المضمنة في خدمة Customer Insights، والتي تم تصميمها لضمان ثبات الخدمة واستقرارها. يمكن اجراء أي طلبات تغيير من خلال [منتدى الأفكار](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>رؤى الجمهور

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>حدود الخدمة في قدرة رؤى الجمهور في Dynamics 365 Customer Insights

| المنطقة  | الحدود  | ملاحظات  |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| الشرائح والمقاييس | 100 شريحة أو مقياس. | لا يمكن أن يتجاوز إجمالي عدد [الشرائح](audience-insights/segments.md) و[المقاييس](audience-insights/measures.md) مجتمعة 100.  |
| العلاقات | 20 مستوى من التعمق في العلاقات في مسارات الكيانات. | عند إنشاء [شرائح](audience-insights/segments.md) أو [قياسات](audience-insights/measures.md) باستخدام واجهة منشئ البيانات، يمكن أن تكون لمسارات الكيانات ما يصل إلى 20 نقطة علاقة بين كيان البدء والكيان الهدف.  |


## <a name="engagement-insights"></a>معلومات المشاركة

### <a name="workspace-and-event-quotas"></a>مساحة العمل والحصص النسبية للأحداث

رؤى المشاركة هو تطبيق قابل للتوسعة للغاية يمكنه دعم ملايين الأحداث في الثانية. أثناء المعاينة العامة، يكون للأحداث حد وحدة تخزين. هناك أيضا حد لعدد مساحات العمل في المؤسسة.

### <a name="engagement-insights-limits"></a>قيود رؤى المشاركة

- الحد الأقصى لحجم الحدث لكل مساحة عمل = 100 حدث في الثانية

- الحد الأقصى لعدد مساحات العمل لكل مؤسسة = 100

عندما تتجاوز الأحداث العتبة، يمكن أن يؤدي ذلك إلى فقدان البيانات في التقارير استنادا إلى تلك الأحداث. يمكنك [الاتصال بالدعم](https://go.microsoft.com/fwlink/?linkid=2145734) لطلب زيادة في مستوى الصوت قبل تجاوز الحدود. وسنعمل معك لتحديد حاجتك لزيادة حجم الطلب ودعمه.


[!INCLUDE[footer-include](includes/footer-banner.md)]