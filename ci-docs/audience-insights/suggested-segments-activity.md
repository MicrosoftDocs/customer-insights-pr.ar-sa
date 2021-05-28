---
title: الشرائح المقترحة استنادًا إلى النشاط.
description: دع التعلم الآلي يساعدك في البحث عن شرائح جديدة ومجدية استنادا إلى نشاط العميل.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034043"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="ea78d-103">الشرائح المقترحة استنادا إلى بيانات النشاط (معاينة)</span><span class="sxs-lookup"><span data-stu-id="ea78d-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="ea78d-104">اكتشف شرائح مستهدفة من عملائك استنادا إلى بيانات نشاط العميل التي تم استقائها من Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ea78d-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="ea78d-105">من أمثلة بيانات النشاط المعاملات أو مدة مكالمة الدعم أو عمليات الشراء أو عمليات الإرجاع.</span><span class="sxs-lookup"><span data-stu-id="ea78d-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="ea78d-106">لاقتراح الشرائح، يتم تحليل بيانات النشاط لمعرفة التردد والتكرار والقيمة المالية (أو المدة).</span><span class="sxs-lookup"><span data-stu-id="ea78d-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="ea78d-107">وبدلا من ذلك، يمكنك إنشاء [شرائح مقترحة لتحسين القياس أو فهم ما الذي يؤثر على سمة بشكل أفضل](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="ea78d-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="علامة التبويب الشرائح المقترحة تعرض اقتراحات الشرائح للشرائح المستندة إلى النشاط والشرائح المستندة إلى السمة.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="ea78d-109">تصنيف العملاء حسب النشاط</span><span class="sxs-lookup"><span data-stu-id="ea78d-109">Categorize customers by activity</span></span>

<span data-ttu-id="ea78d-110">من خلال توفر [بيانات النشاط ](activities.md) في Customer Insights، يمكننا إنشاء اقتراحات تمثل مجموعات العملاء:</span><span class="sxs-lookup"><span data-stu-id="ea78d-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="ea78d-111">العملاء الأكثر نشاطًا</span><span class="sxs-lookup"><span data-stu-id="ea78d-111">most active customers</span></span> 
- <span data-ttu-id="ea78d-112">العملاء الذين سجلوا أكثر عمليات شراء</span><span class="sxs-lookup"><span data-stu-id="ea78d-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="ea78d-113">العملاء الذين حققوا أكبر الإيرادات</span><span class="sxs-lookup"><span data-stu-id="ea78d-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="ea78d-114">العملاء الذين لم ينشطوا في الآونة الأخيرة</span><span class="sxs-lookup"><span data-stu-id="ea78d-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="ea78d-115">العملاء الذين يتفاعلون باستمرار مع أعمالك</span><span class="sxs-lookup"><span data-stu-id="ea78d-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="ea78d-116">إذا كان لديك أعمال بيع بالتجزئة، يمكنك معرفة العملاء الذين يدرون معظم الإيرادات ومكافأتهم من خلال قسيمة.</span><span class="sxs-lookup"><span data-stu-id="ea78d-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="ea78d-117">أو يمكنك تحديد العملاء العارضين وتقديم عرض لهم للانضمام إلى برنامج مكافآت، لكي يزوروا أعمالك بشكل أكبر.</span><span class="sxs-lookup"><span data-stu-id="ea78d-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="ea78d-118">إذا كنت في مجال الرعاية الصحية توفر الرعاية الصحية العامة، وكان هدفك هو تقليل النفقات للمرضى إلى الحد الأدنى.</span><span class="sxs-lookup"><span data-stu-id="ea78d-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="ea78d-119">كطريقة للقيام بذلك يمكنك تقليل الزيارات المتكررة من خلال توفير أفضل العناية الممكنة في عدد قليل من الزيارات قدر الإمكان.</span><span class="sxs-lookup"><span data-stu-id="ea78d-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="ea78d-120">في هذه الحالة، يكون هدفك هو الحفاظ على تكرار الزيارة منخفضًا وتقليل التكلفة المتكررة للمرضى.</span><span class="sxs-lookup"><span data-stu-id="ea78d-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="ea78d-121">أو يمكنك تحديد شرائح من المرضى الذين لديهم مواعيد متكررة وتكاليف متكررة عالية وتحليل هذه الحالات لتحسين علاج الفرد.</span><span class="sxs-lookup"><span data-stu-id="ea78d-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="ea78d-122">البيانات المطلوبة</span><span class="sxs-lookup"><span data-stu-id="ea78d-122">Required data</span></span>

<span data-ttu-id="ea78d-123">يتم إنشاء الاقتراحات استنادا إلى بيانات الإدخال المحددة.</span><span class="sxs-lookup"><span data-stu-id="ea78d-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="ea78d-124">ملفات تعريف العملاء: كافة العملاء أو أعضاء شريحة معينة.</span><span class="sxs-lookup"><span data-stu-id="ea78d-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="ea78d-125">الفترة الزمنية: الشهر الماضي أو العام الماضي أو أي إطار زمني محدد.</span><span class="sxs-lookup"><span data-stu-id="ea78d-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="ea78d-126">نوع النشاط: عمليات الشراء، معاملات البيع بالتجزئة، المعاملات عبر الإنترنت، حالات دعم العميل، الاشتراكات، وهكذا.</span><span class="sxs-lookup"><span data-stu-id="ea78d-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="ea78d-127">الكيان في Customer Insights الذي يحتوي على بيانات النشاط: كيان UnifiedActivity أو الكيان الخاص بنشاط محدد.</span><span class="sxs-lookup"><span data-stu-id="ea78d-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="ea78d-128">الأبعاد المراد تضمينها: الحداثة أو التكرار أو البعد النقدي، حسب متطلبات الأعمال الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="ea78d-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="ea78d-129">إنشاء الشرائح المقترحة</span><span class="sxs-lookup"><span data-stu-id="ea78d-129">Generate suggested segments</span></span>

1. <span data-ttu-id="ea78d-130">انتقل إلى **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="ea78d-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="ea78d-131">حدد علامة التبويب **اقتراحات (إصدار أولي)**.</span><span class="sxs-lookup"><span data-stu-id="ea78d-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="ea78d-132">حدد **بحث عن اقتراحات جديدة** واختر **شاهد سلوك العميل أو توقعه**.</span><span class="sxs-lookup"><span data-stu-id="ea78d-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="ea78d-133">حدد **ابدأ** لتشغيل تجربة إرشادية.</span><span class="sxs-lookup"><span data-stu-id="ea78d-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="الخطوة الأولى لمعالج التكوين للشريحة المقترحة استنادا إلى النشاط.":::

1. <span data-ttu-id="ea78d-135">قم بتوفير بيانات الإدخال المطلوبة وحدد المتابعة **التالية**.</span><span class="sxs-lookup"><span data-stu-id="ea78d-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="ea78d-136">اختيار العملاء: قم بتضمين كافة العملاء أو شريحة معينة.</span><span class="sxs-lookup"><span data-stu-id="ea78d-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="ea78d-137">اختيار النشاط: حدد نوع النشاط والكيانات التي تصف النشاط.</span><span class="sxs-lookup"><span data-stu-id="ea78d-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="ea78d-138">التفضيلات: قم بتعيين الفترة الزمنية بما في ذلك، عوامل الاقتراحات، وتعيين السمات.</span><span class="sxs-lookup"><span data-stu-id="ea78d-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="ea78d-139">راجع إدخالك وحدد **تشغيل** لتشغيل النموذج وإنشاء اقتراحات.</span><span class="sxs-lookup"><span data-stu-id="ea78d-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="ea78d-140">وقد يستغرق إكمال ذلك دقائق قليلة حسب عدد ملفات تعريف العملاء والأنشطة المحددة.</span><span class="sxs-lookup"><span data-stu-id="ea78d-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="ea78d-141">بعد إنشاء الاقتراحات، يمكنك تصفيتها حسب البعد أو القيمة التي تهمك أكثر من غيرها.</span><span class="sxs-lookup"><span data-stu-id="ea78d-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="ea78d-142">عرض تفاصيل شريحة مقترحة</span><span class="sxs-lookup"><span data-stu-id="ea78d-142">View details of a suggested segment</span></span>

<span data-ttu-id="ea78d-143">بمجرد إنشاء الاقتراحات، ستجدها مدرجة في **الشرائح** > **الاقتراحات (معاينة)** في قسم **الاقتراحات المستندة إلى النشاط**.</span><span class="sxs-lookup"><span data-stu-id="ea78d-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="جزء الجانب الموسع الذي يوضح البيانات التفصيلية الخاصة بشرائح المقترحة.":::

<span data-ttu-id="ea78d-145">حدد **راجع الاقتراح** في شريحة مقترحة لعرض تفاصيل تلك الشريحة.</span><span class="sxs-lookup"><span data-stu-id="ea78d-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="ea78d-146">يوفر الجزء الجانبي تفاصيل مثل مدى كل بعد مقارنة بالمجموعة الهدف.</span><span class="sxs-lookup"><span data-stu-id="ea78d-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="ea78d-147">كما أنه يلقي الضوء على عدد الأعضاء المحتملين في الشريحة والنسبة المئوية المقابلة لإجمالي العملاء.</span><span class="sxs-lookup"><span data-stu-id="ea78d-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="ea78d-148">إذا كنت تريد الاحتفاظ باقتراح كشريحة، فحدد **إنشاء شريحة**.</span><span class="sxs-lookup"><span data-stu-id="ea78d-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="ea78d-149">حفظ اقتراح كشريحة</span><span class="sxs-lookup"><span data-stu-id="ea78d-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="ea78d-150">انتقل إلى **الشرائح** > **الاقتراحات (إصدار أولي)**.</span><span class="sxs-lookup"><span data-stu-id="ea78d-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="ea78d-151">حدد الشريحة التي تريد حفظها.</span><span class="sxs-lookup"><span data-stu-id="ea78d-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="ea78d-152">في الجزء الجانبي، حدد **إنشاء شريحة**.</span><span class="sxs-lookup"><span data-stu-id="ea78d-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="ea78d-153">بعد حفظ الشريحة، سوف تظهر في قائمة الشرائح في علامة التبويب **كافة الشرائح**. ويمكن الآن [تحديثها أوحذفها مثل أي شريحة أخرى](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ea78d-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="ea78d-154">لا يمكنك تحرير تفاصيل الشريحة.</span><span class="sxs-lookup"><span data-stu-id="ea78d-154">You can't edit the segment details.</span></span> <span data-ttu-id="ea78d-155">ومع ذلك، يمكنك تغيير معايير الإدخال للاقتراحات وإنشاء اقتراحات مختلفة.</span><span class="sxs-lookup"><span data-stu-id="ea78d-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="ea78d-156">تحديث مجموعة من الاقتراحات أو تحريرها</span><span class="sxs-lookup"><span data-stu-id="ea78d-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="ea78d-157">انتقل إلى **الشرائح** > **الاقتراحات (معاينة)** وابحث عن الشريحة في قسم **الاقتراحات المستندة إلى النشاط**.</span><span class="sxs-lookup"><span data-stu-id="ea78d-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="ea78d-158">حدد **تحديث الاقتراحات** لتحديث الاقتراحات مع المحافظة على السمات المكوّنة.</span><span class="sxs-lookup"><span data-stu-id="ea78d-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="ea78d-159">أو حدد **اقتراحات التحرير** لتعديل السمات المكونة.</span><span class="sxs-lookup"><span data-stu-id="ea78d-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="ea78d-160">يقوم النظام بإعادة تشغيل العملية، وإنشاء اقتراحات الشرائح استنادا إلى أحدث البيانات واستبدال الاقتراحات الحالية.</span><span class="sxs-lookup"><span data-stu-id="ea78d-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
