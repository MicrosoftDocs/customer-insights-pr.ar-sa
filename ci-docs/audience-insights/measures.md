---
title: إنشاء المقاييس وإدارتها
description: حدد المقاييس لتحليل أداء شركتك وإظهاره.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a83caf2428f3dbd9791b9f746d00d370362a508c
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304772"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="fc4ed-103">تحديد المقاييس وإدارتها</span><span class="sxs-lookup"><span data-stu-id="fc4ed-103">Define and manage measures</span></span>

<span data-ttu-id="fc4ed-104">تساعدك القياسات على فهم سلوكيات العملاء وأداء الأعمال بشكل أفضل.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="fc4ed-105">فهي تنظر إلى القيم ذات الصلة من [ملفات التعريف الموحدة](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="fc4ed-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="fc4ed-106">على سبيل المثال ، تريد شركة ما رؤية *إجمالي الإنفاق لكل عميل* لفهم سجل الشراء للعميل الفردي أو قياس *إجمالي مبيعات الشركة* لفهم إجمالي الإيرادات في النشاط التجاري بأكمله.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-106">For example, a business wants to see the *total spend per customer* to understand an individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="fc4ed-107">يتم إنشاء المقاييس باستخدام منشئ المقاييس، نظام أساسي لاستعلام البيانات به عوامل تشغيل متنوعة وخيارات تعيين بسيطة.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="fc4ed-108">كما يتيح لك تصفية البيانات وتجميع النتائج والكشف عن [مسارات علاقات الكيان](relationships.md)، ومعاينة الإخراج</span><span class="sxs-lookup"><span data-stu-id="fc4ed-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="fc4ed-109">استخدم منشئ المقاييس للتخطيط لأنشطة الأعمال من خلال الاستعلام عن بيانات العميل واستخراج الرؤى.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="fc4ed-110">على سبيل المثال، يساعد إنشاء مقياس *إجمالي الإنفاق لكل عميل* و *إجمالي الإرجاع لكل عميل* على تحديد مجموعة من العملاء مع إنفاق عالٍ وإرجاع عالٍ.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="fc4ed-111">يمكنك [إنشاء شريحة](segments.md) لقيادة أفضل الإجراءات التالية.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="fc4ed-112">بناء القياس الخاص بك من البداية</span><span class="sxs-lookup"><span data-stu-id="fc4ed-112">Build your own measure from scratch</span></span>

<span data-ttu-id="fc4ed-113">ينقلك هذا القسم عبر عملية إنشاء مقياس جديد من البداية.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="fc4ed-114">يمكنك بناء مقياس باستخدام سمات البيانات من كيانات البيانات التي تم إعداد علاقة لها للاتصال بكيان العميل.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="fc4ed-115">في رؤى الجمهور، انتقل إلى **المقاييس**.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="fc4ed-116">حدد **جديد** واختر **إنشاء الخاص بك**.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="fc4ed-117">حدد **تحرير الاسم** وقدم **اسمًا** للمقياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="fc4ed-118">إذا كان تكوين القياس الجديد الخاص بك يتكون من حقلين فقط، على سبيل المثال، CustomerID وحساب واحد، فسيتم إضافة الإخراج كعمود جديد إلى الكيان الذي تم إنشاؤه من قبل النظام والمسمى Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-118">If your new measure configuration has only two fields—for example, CustomerID and one calculation—the output will be added as a new column to the system-generated entity called Customer_Measure.</span></span> <span data-ttu-id="fc4ed-119">وستتمكن من رؤية قيمة المقياس في ملف تعريف العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="fc4ed-120">ستقوم المقاييس الأخرى بإنشاء كيانات خاصة بها.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="fc4ed-121">في منطقة التكوين، اختر وظيفة التجميع من القائمة المنسدلة **تحديد الوظيفة**.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-121">In the configuration area, choose the aggregation function from the **Select Function** dropdown menu.</span></span> <span data-ttu-id="fc4ed-122">تتضمن وظائف التجميع ما يلي:</span><span class="sxs-lookup"><span data-stu-id="fc4ed-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="fc4ed-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="fc4ed-123">**Sum**</span></span>
   - <span data-ttu-id="fc4ed-124">**المتوسط**</span><span class="sxs-lookup"><span data-stu-id="fc4ed-124">**Average**</span></span>
   - <span data-ttu-id="fc4ed-125">**عدد**</span><span class="sxs-lookup"><span data-stu-id="fc4ed-125">**Count**</span></span>
   - <span data-ttu-id="fc4ed-126">**العدد الفريد**</span><span class="sxs-lookup"><span data-stu-id="fc4ed-126">**Count Unique**</span></span>
   - <span data-ttu-id="fc4ed-127">**‏‫الحد الأقصى**</span><span class="sxs-lookup"><span data-stu-id="fc4ed-127">**Max**</span></span>
   - <span data-ttu-id="fc4ed-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="fc4ed-128">**Min**</span></span>
   - <span data-ttu-id="fc4ed-129">**الأول**: أخذ القيمة الأولى من سجل البيانات</span><span class="sxs-lookup"><span data-stu-id="fc4ed-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="fc4ed-130">**الأخير**: أخذ آخر قيمة تمت إضافتها إلى سجل البيانات</span><span class="sxs-lookup"><span data-stu-id="fc4ed-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="عوامل تشغيل لقياس عمليات الحساب.":::

1. <span data-ttu-id="fc4ed-132">حدد **إضافة سمة** لتحديد البيانات التي تحتاجها لإنشاء هذا المقياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="fc4ed-133">حدد علامة تبويب **السمات**.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="fc4ed-134">كيان البيانات: اختر الكيان الذي يتضمن السمة التي تريد قياسها.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="fc4ed-135">سمة البيانات: اختر السمة التي تريد استخدامها في وظيفة التجميع لحساب المقياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="fc4ed-136">يمكن سمة واحدة فقط في كل مرة.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="fc4ed-137">يمكنك أيضًا تحديد سمة بيانات من مقياس موجود بتحديد علامة تبويب **المقاييس**. أو، يمكنك البحث عن اسم كيان أو اسم مقياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="fc4ed-138">حدد **إضافة** لإضافة السمة المحددة إلى المقياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="حدد سمة لاستخدامها في عمليات الحساب.":::

1. <span data-ttu-id="fc4ed-140">لبناء مقاييس أكثر تعقيدًا، يمكنك إضافة مزيد من السمات أو استخدام عوامل تشغيل رياضية على وظيفة المقياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="إنشاء مقياس معقد باستخدام عوامل تشغيل رياضية.":::

1. <span data-ttu-id="fc4ed-142">لإضافة عوامل تصفية، حدد **عامل التصفية** في منطقة التكوين.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="fc4ed-143">في قسم **إضافة التسمية** في جزء **عوامل التصفية**، حدد السمة التي تريد استخدامها لإنشاء عوامل تصفية.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-143">In the **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="fc4ed-144">قم بتعيين عوامل تشغيل التصفية لتحديد عامل التصفية لكل سمة محددة.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="fc4ed-145">حدد **تطبيق** لإضافة عوامل التصفية إلى المقياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="fc4ed-146">لإضافة أبعاد، حدد **البُعد** في منطقة التكوين.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="fc4ed-147">ستظهر الأبعاد كأعمدة في كيان إخراج المقياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-147">Dimensions will show as columns in the measure output entity.</span></span>
 
   1. <span data-ttu-id="fc4ed-148">حدد **تحرير الأبعاد** لإضافة سمات بيانات ترغب في تجميع قيم المقياس وفقًا لها.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="fc4ed-149">على سبيل المثال، المدينة أو الجنس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-149">For example, city or gender.</span></span> <span data-ttu-id="fc4ed-150">يتم تحديد بُعد *CustomerID* بشكل افتراضي لإنشاء *مقاييس على مستوى العميل*.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="fc4ed-151">يمكنك إزالة البُعد الافتراضي إذا كنت ترغب في إنشاء *مقاييس على مستوى الأعمال*.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="fc4ed-152">حدد **تم** لإضافة الأبعاد إلى المقياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="fc4ed-153">إذا كانت هناك قيم في بياناتك تحتاج إلى استبدالها بعدد صحيح، على سبيل المثال، استبدل *فارغ* بـ *0*، وحدد **القواعد**.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-153">If there are values in your data that you need to replace with an integer—for example, replace *null* with *0*—select **Rules**.</span></span> <span data-ttu-id="fc4ed-154">قم بتكوين القاعدة وتأكد من اختيار الأعداد الصحيحة فقط كبدائل.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="fc4ed-155">في حالة وجود مسارات متعددة بين كيان البيانات الذي قمت تعيينه وكيان *العميل*، يجب عليك اختيار أحد [مسارات علاقات الكيان](relationships.md) المحددة.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="fc4ed-156">وقد تختلف نتائج القياس بناء على المسار المحدد.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-156">Measure results can vary depending on the selected path.</span></span> 
   
   1. <span data-ttu-id="fc4ed-157">حدد **تفضيلات البيانات** واختر مسار الكيان الذي ينبغي استخدامه لتحديد المقياس الذي تستخدمه.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="fc4ed-158">إذا كان هناك مسار واحد فقط إلى كيان *العميل*، فلن يظهر عنصر التحكم هذا.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="fc4ed-159">حدد **تم** لتطبيق التحديد.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="حدد مسار الكيان للمقياس.":::

1. <span data-ttu-id="fc4ed-161">لإضافة مزيد من عمليات الحساب للمقياس، حدد **حساب جديد**.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="fc4ed-162">يمكنك استخدام الكيانات فقط على مسار الكيان نفسها لعمليات الحساب الجديدة.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="fc4ed-163">ستظهر عمليات الحساب الجديدة كأعمدة جديدة في كيان إخراج المقياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="fc4ed-164">حدد **...** على عملية الحساب من أجل **تكرار** عملية حساب أو **إعادتها** أو **إزالتها** من مقياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="fc4ed-165">في منطقة **المعاينة**، سوف ترى مخطط البيانات الخاص بكيان إخراج المقياس، بما في ذلك عوامل التصفية والأبعاد.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="fc4ed-166">تتفاعل المعاينة بشكل ديناميكي مع التغييرات في التكوين.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="fc4ed-167">حدد **تشغيل** لحساب النتائج للمقياس المكوّن.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="fc4ed-168">حدد **حفظ وإغلاق** إذا كنت ترغب في الاحتفاظ بالتكوين الحالي وتشغيل المقياس لاحقًا.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="fc4ed-169">انتقل إلى **المقاييس** لرؤية المقياس الذي تم إنشاؤه مؤخرًا في القائمة.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="fc4ed-170">استخدام قالب لإنشاء مقياس</span><span class="sxs-lookup"><span data-stu-id="fc4ed-170">Use a template to build a measure</span></span>

<span data-ttu-id="fc4ed-171">يمكنك استخدام قوالب محددة مسبقًا للمقاييس شائعة الاستخدام لإنشائها.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="fc4ed-172">تساعدك الأوصاف التفصيلية للقوالب والتجربة الإرشادية في إنشاء مقياس فعال.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="fc4ed-173">تستند القوالب إلى البيانات المعينة من كيان *النشاط الموحد*.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="fc4ed-174">لذلك تأكد من قيمك بتكوين [أنشطة العملاء](activities.md) قبل أن تنشئ قياسًا من قالب.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="fc4ed-175">قوالب القياس المتوفرة:</span><span class="sxs-lookup"><span data-stu-id="fc4ed-175">Available measure templates:</span></span> 
- <span data-ttu-id="fc4ed-176">متوسط قيمة المعاملة (ATV)</span><span class="sxs-lookup"><span data-stu-id="fc4ed-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="fc4ed-177">إجمالي قيمة الحركة</span><span class="sxs-lookup"><span data-stu-id="fc4ed-177">Total transaction value</span></span>
- <span data-ttu-id="fc4ed-178">متوسط الإيراد اليومي</span><span class="sxs-lookup"><span data-stu-id="fc4ed-178">Average daily revenue</span></span>
- <span data-ttu-id="fc4ed-179">متوسط الإيراد السنوي</span><span class="sxs-lookup"><span data-stu-id="fc4ed-179">Average yearly revenue</span></span>
- <span data-ttu-id="fc4ed-180">عدد المعاملات</span><span class="sxs-lookup"><span data-stu-id="fc4ed-180">Transaction count</span></span>
- <span data-ttu-id="fc4ed-181">نقاط الولاء المُكتسبة</span><span class="sxs-lookup"><span data-stu-id="fc4ed-181">Loyalty points earned</span></span>
- <span data-ttu-id="fc4ed-182">نقاط الولاء المُستردة</span><span class="sxs-lookup"><span data-stu-id="fc4ed-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="fc4ed-183">رصيد نقاط الولاء</span><span class="sxs-lookup"><span data-stu-id="fc4ed-183">Loyalty points balance</span></span>
- <span data-ttu-id="fc4ed-184">فترة عمر العميل النشط</span><span class="sxs-lookup"><span data-stu-id="fc4ed-184">Active customer lifespan</span></span>
- <span data-ttu-id="fc4ed-185">مدة عضوية الولاء</span><span class="sxs-lookup"><span data-stu-id="fc4ed-185">Loyalty membership duration</span></span>
- <span data-ttu-id="fc4ed-186">الوقت منذ آخر عملية شراء</span><span class="sxs-lookup"><span data-stu-id="fc4ed-186">Time since last purchase</span></span>

<span data-ttu-id="fc4ed-187">يستعرض الإجراء التالي الخطوات اللازمة لبناء مقياس جديد باستخدام قالب.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="fc4ed-188">في رؤى الجمهور، انتقل إلى **المقاييس**.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="fc4ed-189">حدد **جديد** وحدد **اختيار قالب**.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="لقطة شاشة من القائمة المنسدلة عند إنشاء مقياس جديد مع تمييز على القالب.":::

1. <span data-ttu-id="fc4ed-191">اعثر على القالب الذي يناسب احتياجاتك وحدد **اختيار القالب**.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="fc4ed-192">راجع البيانات المطلوبة وحدد **الشروع في العمل** إذا كانت لديك جميع البيانات المطلوبة.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="fc4ed-193">في جزء **تحرير الاسم**، قم بتعيين الاسم لمقياسك ولكيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="fc4ed-194">حدد **تم**.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-194">Select **Done**.</span></span>

1. <span data-ttu-id="fc4ed-195">في قسم **تعيين الفترة الزمنية**، حدد الإطار الزمني للبيانات المراد استخدامها.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="fc4ed-196">اختر ما إذا كنت تريد أن يغطي المقياس الجديد مجموعة البيانات بأكملها عن طريق تحديد **كل الوقت**, أو ما إذا كنت تريد التركيز على **فترة زمنية محددة**.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-196">Choose if you want the new measure to cover the entire dataset by selecting **All time**, or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="لقطة شاشة توضح قسم الفترة الزمنية عند تكوين مقياس من قالب.":::

1. <span data-ttu-id="fc4ed-198">في القسم التالي، حدد **إضافة البيانات** لاختيار الأنشطة وتعيين البيانات المقابلة من كيان *النشاط الموحد*.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-198">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="fc4ed-199">الخطوة 1 من 2: ضمن **نوع النشاط**، اختر نوع الكيان الذي تريد استخدامه.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-199">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="fc4ed-200">بالنسبة إلى **الأنشطة**، حدد الكيانات التي تريد تعيينها.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-200">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="fc4ed-201">الخطوة 2 من 2: اختر السمة من كيان *النشاط الموحد* للمكون المطلوب بواسطة الصيغة.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-201">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="fc4ed-202">على سبيل المثال، بالنسبة لمعدل قيمة المعاملة، فإن هذه هي السمة التي تمثل قيمة المعاملة.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-202">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="fc4ed-203">بالنسبة إلى **الطابع الزمني للنشاط**، اختر السمة من كيان النشاط الموحد الذي يمثل تاريخ ووقت النشاط.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-203">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="fc4ed-204">بمجرد نجاح تعيين البيانات، يمكنك رؤية الحالة كـ **مكتمل** واسم الأنشطة والسمات المعينة.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-204">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="لقطة شاشة لتكوين قالب مقياس مكتمل.":::

1. <span data-ttu-id="fc4ed-206">يمكنك الآن تحديد **تشغيل** لحساب نتائج القياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-206">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="fc4ed-207">لتحسينه لاحقًا، حدد **حفظ مسودة**.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-207">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="fc4ed-208">إدارة المقاييس الخاصة بك</span><span class="sxs-lookup"><span data-stu-id="fc4ed-208">Manage your measures</span></span>

<span data-ttu-id="fc4ed-209">يمكنك العثور على قائمة القياسات في صفحة **القياسات**.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-209">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="fc4ed-210">ستعثر على معلومات حول نوع المقياس والمنشئ وتاريخ الإنشاء والحالة والولاية.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-210">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="fc4ed-211">عند تحديد مقياس من القائمة، يمكنك معاينة الإخراج وتنزيل ملف CSV.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-211">When you select a measure from the list, you can preview the output and download a CSV file.</span></span>

<span data-ttu-id="fc4ed-212">لتحديث كافة المقاييس الخاصة بك في نفس الوقت، حدد **تحديث الكل** دون تحديد مقياس معين.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-212">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="fc4ed-213">![إجراءات لإدارة المقاييس الفردية.](media/measure-actions.png "إجراءات لإدارة المقاييس الفردية.")</span><span class="sxs-lookup"><span data-stu-id="fc4ed-213">![Actions to manage single measures.](media/measure-actions.png "Actions to manage single measures.")</span></span>

<span data-ttu-id="fc4ed-214">حدد مقياسًا من القائمة للخيارات التالية:</span><span class="sxs-lookup"><span data-stu-id="fc4ed-214">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="fc4ed-215">حدد اسم المقياس لرؤية التفاصيل الخاصة به.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-215">Select the measure name to see its details.</span></span>
- <span data-ttu-id="fc4ed-216">**تحرير** تكوين المقياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-216">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="fc4ed-217">**تحديث** المقياس استنادًا إلى البيانات الأخيرة.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-217">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="fc4ed-218">**إعادة تسمية** المقياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-218">**Rename** the measure.</span></span>
- <span data-ttu-id="fc4ed-219">**حذف** المقياس.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-219">**Delete** the measure.</span></span>
- <span data-ttu-id="fc4ed-220">**تنشيط** أو **إلغاء التنشيط**.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-220">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="fc4ed-221">لن يتم تحديث الإجراءات غير النشطة أثناء [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fc4ed-221">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="fc4ed-222">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-222">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="fc4ed-223">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="fc4ed-223">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="fc4ed-224">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-224">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="fc4ed-225">بعد تحديد **راجع التفاصيل** بالنسبة لإحدى مهام الوظيفة ، ستجد معلومات إضافية: وقت المعالجة ، وتاريخ المعالجة الأخير ، وجميع الأخطاء والتحذيرات المرتبطة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="fc4ed-225">After selecting **See details** for one of the job's tasks, you'll find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="fc4ed-226">الخطوة التالية</span><span class="sxs-lookup"><span data-stu-id="fc4ed-226">Next step</span></span>

<span data-ttu-id="fc4ed-227">يمكنك استخدام القياسات الموجودة لإنشاء [مقطع عميل](segments.md).</span><span class="sxs-lookup"><span data-stu-id="fc4ed-227">You can use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
