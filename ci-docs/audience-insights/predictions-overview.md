---
title: نظرة عامة حول سيناريوهات التنبؤ المدعومة
description: سيناريوهات وخيارات التنبؤ التي يغطيها تطبيق Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095679"
---
# <a name="predictions-overview"></a><span data-ttu-id="72f2d-103">نظرة عامة حول التبنؤات</span><span class="sxs-lookup"><span data-stu-id="72f2d-103">Predictions overview</span></span>

<span data-ttu-id="72f2d-104">يأتي Dynamics 365 Customer Insights مع مجموعة متنوعة من الخيارات التي تستفيد من الذكاء الاصطناعي والتعلم الآلي للتنبؤ بالبيانات.</span><span class="sxs-lookup"><span data-stu-id="72f2d-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="72f2d-105">النماذج الجاهزة</span><span class="sxs-lookup"><span data-stu-id="72f2d-105">Out-of-box models</span></span>

<span data-ttu-id="72f2d-106">تشكّل النماذج المعرّفة مسبقًا أسهل طريقة لبدء التنبؤ بالبيانات، ويُشار إلى هذه النماذج في أغلب الأحيان بالنماذج الجاهزة.</span><span class="sxs-lookup"><span data-stu-id="72f2d-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="72f2d-107">فهي تتطلب فقط بيانات وبنية معينة لتوليد الرؤى بسرعة.</span><span class="sxs-lookup"><span data-stu-id="72f2d-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="72f2d-108">تتوفر حاليًا النماذج التالية:</span><span class="sxs-lookup"><span data-stu-id="72f2d-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="72f2d-109">[القيمة العمرية للعميل](predict-customer-lifetime-value.md): توقع الإيرادات المحتملة للعميل طوال التفاعل الكامل مع نشاط تجاري.</span><span class="sxs-lookup"><span data-stu-id="72f2d-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="72f2d-110">[توصية المنتج](predict-product-recommendation.md): تقترح مجموعات من توصيات المنتجات التنبؤية بالاستناد إلى سلوك الشراء والعملاء الذين لديهم أنماط شراء مماثلة.</span><span class="sxs-lookup"><span data-stu-id="72f2d-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="72f2d-111">[خسارة الاشتراك‬](predict-subscription-churn.md): التنبؤ بما إذا كان العميل عرضة لخطر التوقف عن استخدام خدمات أو منتجات الاشتراك الخاصة بشركتك.</span><span class="sxs-lookup"><span data-stu-id="72f2d-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="72f2d-112">[خسارة الحركة](predict-transactional-churn.md): التنبؤ بما إذا كان العميل سيتوقف عن شراء المنتجات والخدمات في إطار زمني معين.</span><span class="sxs-lookup"><span data-stu-id="72f2d-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="72f2d-113">تكامل التعلم الآلي من Azure</span><span class="sxs-lookup"><span data-stu-id="72f2d-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="72f2d-114">إذا كانت إحدى المؤسسات تستخدم سيناريوهات التعلم الآلي بالاستناد إلى تجارب التعلم الآلي من Azure، فإن ميزة النماذج المخصصة في Customer Insights تساعد على جمع المعلومات.</span><span class="sxs-lookup"><span data-stu-id="72f2d-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="72f2d-115">أنشئ عمليات سير عمل تساعدك على اختيار البيانات التي تريد إنشاء رؤى منها، وعيّن النتائج إلى ملفات تعريف العملاء الموحدة.</span><span class="sxs-lookup"><span data-stu-id="72f2d-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="72f2d-116">لمزيد من المعلومات، راجع [نماذج التعلم الآلي المخصصة](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="72f2d-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="72f2d-117">تنبؤ AI Builder</span><span class="sxs-lookup"><span data-stu-id="72f2d-117">AI Builder prediction</span></span>

<span data-ttu-id="72f2d-118">في بعض الأحيان، تكون مجموعات البيانات غير كاملة وبعض القيم مفقودة.</span><span class="sxs-lookup"><span data-stu-id="72f2d-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="72f2d-119">بإمكان Customer Insights المساعدة في التنبؤ بالقيم المفقودة لكيان العميل وشرائحه.</span><span class="sxs-lookup"><span data-stu-id="72f2d-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="72f2d-120">لمزيد من المعلومات، راجع [إكمال بياناتك الجزئية بالتنبؤات](predictions.md)</span><span class="sxs-lookup"><span data-stu-id="72f2d-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
