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
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="1d4e1-103">إنشاء شريحة استنادا إلى نموذج تنبؤ (معاينة)</span><span class="sxs-lookup"><span data-stu-id="1d4e1-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="1d4e1-104">تسري نتائج التنبؤات في بعض الأحيان على مجموعة فرعية من العملاء فقط.</span><span class="sxs-lookup"><span data-stu-id="1d4e1-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="1d4e1-105">زيادة تخصيص التوصيات من خلال إنشاء شرائح من نتائج تنبؤ النماذج.</span><span class="sxs-lookup"><span data-stu-id="1d4e1-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="1d4e1-106">على سبيل المثال، قد ترغب في تقديم توصيات معينة إلى العملاء الذين يفضلون نوع خدمة معين.</span><span class="sxs-lookup"><span data-stu-id="1d4e1-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="1d4e1-107">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="1d4e1-107">Prerequisites</span></span>

- <span data-ttu-id="1d4e1-108">على الأقل [أذونات المساهم](permissions.md) في Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1d4e1-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="1d4e1-109">توصية منتج أو مجموعة معاملات أو مجموعة اشتراك أو نموذج قيمة مدى الحياة للعميل تم تكوينه في Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1d4e1-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="1d4e1-110">راجع المتطلبات لإعداد النماذج المختلفة:</span><span class="sxs-lookup"><span data-stu-id="1d4e1-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="1d4e1-111">نموذج توصيات المنتج</span><span class="sxs-lookup"><span data-stu-id="1d4e1-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="1d4e1-112">نموذج خسارة الاشتراك</span><span class="sxs-lookup"><span data-stu-id="1d4e1-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="1d4e1-113">نموذج خسارة المعاملة</span><span class="sxs-lookup"><span data-stu-id="1d4e1-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="1d4e1-114">نموذج قيمة عمر العميل</span><span class="sxs-lookup"><span data-stu-id="1d4e1-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="1d4e1-115">قم بإنشاء شريحة العملاء بناءً على التوقعات</span><span class="sxs-lookup"><span data-stu-id="1d4e1-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="1d4e1-116">انتقل إلى **الذكاء** > **التنبؤات** وحدد علامة التبويب **التنبؤات الخاصة بي‬**.</span><span class="sxs-lookup"><span data-stu-id="1d4e1-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="1d4e1-117">حدد الأشكال البيضاوية العمودية بجوار النموذج الذي تريد مراجعته وحدد **عرض**.</span><span class="sxs-lookup"><span data-stu-id="1d4e1-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="1d4e1-118">في صفحة النتائج، حدد **إنشاء شريحة**.</span><span class="sxs-lookup"><span data-stu-id="1d4e1-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="1d4e1-119">لمزيد من المعلومات حول صفحة النتائج، راجع المقالة حول النموذج.</span><span class="sxs-lookup"><span data-stu-id="1d4e1-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="لقطة شاشة لصفحة نتائج التنبؤ مع التركيز على إجراء إنشاء الشريحة.":::

1. <span data-ttu-id="1d4e1-121">أنشئ مقطعًا جديدًا استنادًا إلى كيان الإخراج للنموذج المحدد.</span><span class="sxs-lookup"><span data-stu-id="1d4e1-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="1d4e1-122">لمزيد من المعلومات، راجع [إنشاء شرائح وإدارتها](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1d4e1-122">For more information, see [Create and manage segments](segments.md).</span></span>