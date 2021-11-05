---
title: نظرة عامة حول سيناريوهات التنبؤ المدعومة
description: سيناريوهات وخيارات التنبؤ التي يغطيها تطبيق Dynamics 365 Customer Insights.
ms.date: 09/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 63e22bf9a457ea43c65132643681cffb295ae7e5
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673946"
---
# <a name="predictions-overview"></a>نظرة عامة حول التبنؤات

يأتي Dynamics 365 Customer Insights مع مجموعة متنوعة من الخيارات التي تستفيد من الذكاء الاصطناعي والتعلم الآلي للتنبؤ بالبيانات. 

## <a name="out-of-box-models"></a>النماذج الجاهزة

تشكّل النماذج المعرّفة مسبقًا أسهل طريقة لبدء التنبؤ بالبيانات، ويُشار إلى هذه النماذج في أغلب الأحيان بالنماذج الجاهزة. فهي تتطلب فقط بيانات وبنية معينة لتوليد الرؤى بسرعة. تتوفر حاليًا النماذج التالية: 

# <a name="individual-consumers-b-to-c"></a>[المستهلكون الفرديون (B-to-C)](#tab/b2c)

- [القيمة العمرية للعميل](predict-customer-lifetime-value.md): توقع الإيرادات المحتملة للعميل طوال التفاعل الكامل مع نشاط تجاري.
- [توصية المنتج](predict-product-recommendation.md): تقترح مجموعات من توصيات المنتجات التنبؤية بالاستناد إلى سلوك الشراء والعملاء الذين لديهم أنماط شراء مماثلة.
- [خسارة الاشتراك‬](predict-subscription-churn.md): التنبؤ بما إذا كان العميل عرضة لخطر التوقف عن استخدام خدمات أو منتجات الاشتراك الخاصة بشركتك.
- [خسارة الحركة](predict-transactional-churn.md): التنبؤ بما إذا كان العميل سيتوقف عن شراء المنتجات والخدمات في إطار زمني معين.

# <a name="business-accounts-b-to-b"></a>[حسابات الأعمال (B-to-B)](#tab/b2b)

- [خسارة الحركة](predict-transactional-churn.md): التنبؤ بما إذا كان العميل سيتوقف عن شراء المنتجات والخدمات في إطار زمني معين.

---


## <a name="azure-machine-learning-integration"></a>تكامل التعلم الآلي من Azure

إذا كانت إحدى المؤسسات تستخدم سيناريوهات التعلم الآلي بالاستناد إلى تجارب التعلم الآلي من Azure، فإن ميزة النماذج المخصصة في Customer Insights تساعد على جمع المعلومات. أنشئ عمليات سير عمل تساعدك على اختيار البيانات التي تريد إنشاء رؤى منها، وعيّن النتائج إلى ملفات تعريف العملاء الموحدة. لمزيد من المعلومات، راجع [نماذج التعلم الآلي المخصصة](custom-models.md).

## <a name="ai-builder-prediction"></a>تنبؤ AI Builder

في بعض الأحيان، تكون مجموعات البيانات غير كاملة وبعض القيم مفقودة. بإمكان Customer Insights المساعدة في التنبؤ بالقيم المفقودة لكيان العميل وشرائحه. لمزيد من المعلومات، راجع [إكمال بياناتك الجزئية بالتنبؤات](predictions.md)
