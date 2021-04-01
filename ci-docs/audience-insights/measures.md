---
title: إنشاء المقاييس وإدارتها
description: حدد المقاييس لتحليل أداء شركتك وإظهاره.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654716"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="232a5-103">تحديد المقاييس وإدارتها</span><span class="sxs-lookup"><span data-stu-id="232a5-103">Define and manage measures</span></span>

<span data-ttu-id="232a5-104">تساعدك المقاييس على فهم سلوكيات العملاء وأداء الأعمال بشكل أفضل من خلال استرداد القيم ذات الصلة من [ملفات التعريف الموحدة](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="232a5-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="232a5-105">على سبيل المثال، ترغب شركة في رؤية *إجمالي الإنفاق لكل عميل* لفهم محفوظات شراء عميل فردي.</span><span class="sxs-lookup"><span data-stu-id="232a5-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="232a5-106">أو قياس *إجمالي مبيعات الشركة* لفهم الإيرادات على المستوى المجمع في الشركة كلها.</span><span class="sxs-lookup"><span data-stu-id="232a5-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="232a5-107">يتم إنشاء المقاييس باستخدام منشئ المقاييس، نظام أساسي لاستعلام البيانات به عوامل تشغيل متنوعة وخيارات تعيين بسيطة.</span><span class="sxs-lookup"><span data-stu-id="232a5-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="232a5-108">كما يتيح لك تصفية البيانات وتجميع النتائج والكشف عن [مسارات علاقات الكيان](relationships.md)، ومعاينة الإخراج</span><span class="sxs-lookup"><span data-stu-id="232a5-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="232a5-109">استخدم منشئ المقاييس للتخطيط لأنشطة الأعمال من خلال الاستعلام عن بيانات العميل واستخراج الرؤى.</span><span class="sxs-lookup"><span data-stu-id="232a5-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="232a5-110">على سبيل المثال، يساعد إنشاء مقياس *إجمالي الإنفاق لكل عميل* و *إجمالي الإرجاع لكل عميل* على تحديد مجموعة من العملاء مع إنفاق عالٍ وإرجاع عالٍ.</span><span class="sxs-lookup"><span data-stu-id="232a5-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="232a5-111">يمكنك [إنشاء شريحة](segments.md) لقيادة أفضل الإجراءات التالية.</span><span class="sxs-lookup"><span data-stu-id="232a5-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="232a5-112">إنشاء مقياس</span><span class="sxs-lookup"><span data-stu-id="232a5-112">Create a measure</span></span>

<span data-ttu-id="232a5-113">ينقلك هذا القسم عبر عملية إنشاء مقياس جديد من البداية.</span><span class="sxs-lookup"><span data-stu-id="232a5-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="232a5-114">يمكنك بناء مقياس باستخدام سمات البيانات من كيانات البيانات التي تم إعداد علاقة لها للاتصال بكيان العميل.</span><span class="sxs-lookup"><span data-stu-id="232a5-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="232a5-115">في رؤى الجمهور، انتقل إلى **المقاييس**.</span><span class="sxs-lookup"><span data-stu-id="232a5-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="232a5-116">حدد **جديد**.</span><span class="sxs-lookup"><span data-stu-id="232a5-116">Select **New**.</span></span>

1. <span data-ttu-id="232a5-117">حدد **تحرير الاسم** وقدم **اسمًا** للمقياس.</span><span class="sxs-lookup"><span data-stu-id="232a5-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="232a5-118">إذا كان تكوين المقياس الجديد يتضمن حقلين فقط، على سبيل المثال، CustomerID وحساب واحد، سيُضاف الإخراج كعمود جديد إلى الكيان الذي تم إنشاؤه من قبل النظام والمسمى Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="232a5-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="232a5-119">وستتمكن من رؤية قيمة المقياس في ملف تعريف العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="232a5-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="232a5-120">ستقوم المقاييس الأخرى بإنشاء كيانات خاصة بها.</span><span class="sxs-lookup"><span data-stu-id="232a5-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="232a5-121">في منطقة التكوين، اختر وظيفة التجميع من القائمة المنسدلة **تحديد الوظيفة**.</span><span class="sxs-lookup"><span data-stu-id="232a5-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="232a5-122">تتضمن وظائف التجميع ما يلي:</span><span class="sxs-lookup"><span data-stu-id="232a5-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="232a5-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="232a5-123">**Sum**</span></span>
   - <span data-ttu-id="232a5-124">**المتوسط**</span><span class="sxs-lookup"><span data-stu-id="232a5-124">**Average**</span></span>
   - <span data-ttu-id="232a5-125">**عدد**</span><span class="sxs-lookup"><span data-stu-id="232a5-125">**Count**</span></span>
   - <span data-ttu-id="232a5-126">**العدد الفريد**</span><span class="sxs-lookup"><span data-stu-id="232a5-126">**Count Unique**</span></span>
   - <span data-ttu-id="232a5-127">**‏‫الحد الأقصى**</span><span class="sxs-lookup"><span data-stu-id="232a5-127">**Max**</span></span>
   - <span data-ttu-id="232a5-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="232a5-128">**Min**</span></span>
   - <span data-ttu-id="232a5-129">**الأول**: أخذ القيمة الأولى من سجل البيانات</span><span class="sxs-lookup"><span data-stu-id="232a5-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="232a5-130">**الأخير**: أخذ آخر قيمة تمت إضافتها إلى سجل البيانات</span><span class="sxs-lookup"><span data-stu-id="232a5-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="عوامل تشغيل لقياس عمليات الحساب.":::

1. <span data-ttu-id="232a5-132">حدد **إضافة سمة** لتحديد البيانات التي تحتاجها لإنشاء هذا المقياس.</span><span class="sxs-lookup"><span data-stu-id="232a5-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="232a5-133">حدد علامة تبويب **السمات**.</span><span class="sxs-lookup"><span data-stu-id="232a5-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="232a5-134">كيان البيانات: اختر الكيان الذي يتضمن السمة التي تريد قياسها.</span><span class="sxs-lookup"><span data-stu-id="232a5-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="232a5-135">سمة البيانات: اختر السمة التي تريد استخدامها في وظيفة التجميع لحساب المقياس.</span><span class="sxs-lookup"><span data-stu-id="232a5-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="232a5-136">يمكن سمة واحدة فقط في كل مرة.</span><span class="sxs-lookup"><span data-stu-id="232a5-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="232a5-137">يمكنك أيضًا تحديد سمة بيانات من مقياس موجود بتحديد علامة تبويب **المقاييس**. أو، يمكنك البحث عن اسم كيان أو اسم مقياس.</span><span class="sxs-lookup"><span data-stu-id="232a5-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="232a5-138">حدد **إضافة** لإضافة السمة المحددة إلى المقياس.</span><span class="sxs-lookup"><span data-stu-id="232a5-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="حدد سمة لاستخدامها في عمليات الحساب.":::

1. <span data-ttu-id="232a5-140">لبناء مقاييس أكثر تعقيدًا، يمكنك إضافة مزيد من السمات أو استخدام عوامل تشغيل رياضية على وظيفة المقياس.</span><span class="sxs-lookup"><span data-stu-id="232a5-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="إنشاء مقياس معقد باستخدام عوامل تشغيل رياضية.":::

1. <span data-ttu-id="232a5-142">لإضافة عوامل تصفية، حدد **عامل التصفية** في منطقة التكوين.</span><span class="sxs-lookup"><span data-stu-id="232a5-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="232a5-143">في القسم **إضافة سمة** في جزء **عوامل التصفية**، حدد السمة التي ترغب في استخدامها لإنشاء عوامل تصفية.</span><span class="sxs-lookup"><span data-stu-id="232a5-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="232a5-144">قم بتعيين عوامل تشغيل التصفية لتحديد عامل التصفية لكل سمة محددة.</span><span class="sxs-lookup"><span data-stu-id="232a5-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="232a5-145">حدد **تطبيق** لإضافة عوامل التصفية إلى المقياس.</span><span class="sxs-lookup"><span data-stu-id="232a5-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="232a5-146">لإضافة أبعاد، حدد **البُعد** في منطقة التكوين.</span><span class="sxs-lookup"><span data-stu-id="232a5-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="232a5-147">ستظهر الأبعاد كأعمدة في كيان إخراج المقياس.</span><span class="sxs-lookup"><span data-stu-id="232a5-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="232a5-148">حدد **تحرير الأبعاد** لإضافة سمات بيانات ترغب في تجميع قيم المقياس وفقًا لها.</span><span class="sxs-lookup"><span data-stu-id="232a5-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="232a5-149">على سبيل المثال، المدينة أو الجنس.</span><span class="sxs-lookup"><span data-stu-id="232a5-149">For example, city or gender.</span></span> <span data-ttu-id="232a5-150">يتم تحديد بُعد *CustomerID* بشكل افتراضي لإنشاء *مقاييس على مستوى العميل*.</span><span class="sxs-lookup"><span data-stu-id="232a5-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="232a5-151">يمكنك إزالة البُعد الافتراضي إذا كنت ترغب في إنشاء *مقاييس على مستوى الأعمال*.</span><span class="sxs-lookup"><span data-stu-id="232a5-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="232a5-152">حدد **تم** لإضافة الأبعاد إلى المقياس.</span><span class="sxs-lookup"><span data-stu-id="232a5-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="232a5-153">في حالة وجود مسارات متعددة بين كيان البيانات الذي قمت تعيينه وكيان *العميل*، يجب عليك اختيار أحد [مسارات علاقات الكيان](relationships.md) المحددة.</span><span class="sxs-lookup"><span data-stu-id="232a5-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="232a5-154">وقد تختلف نتائج القياس بناء على المسار المحدد.</span><span class="sxs-lookup"><span data-stu-id="232a5-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="232a5-155">حدد **تفضيلات البيانات** واختر مسار الكيان الذي ينبغي استخدامه لتحديد المقياس الذي تستخدمه.</span><span class="sxs-lookup"><span data-stu-id="232a5-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="232a5-156">إذا كان هناك مسار واحد فقط إلى كيان *العميل*، فلن يظهر عنصر التحكم هذا.</span><span class="sxs-lookup"><span data-stu-id="232a5-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="232a5-157">حدد **تم** لتطبيق التحديد.</span><span class="sxs-lookup"><span data-stu-id="232a5-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="حدد مسار الكيان للمقياس.":::

1. <span data-ttu-id="232a5-159">لإضافة مزيد من عمليات الحساب للمقياس، حدد **حساب جديد**.</span><span class="sxs-lookup"><span data-stu-id="232a5-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="232a5-160">يمكنك استخدام الكيانات فقط على مسار الكيان نفسها لعمليات الحساب الجديدة.</span><span class="sxs-lookup"><span data-stu-id="232a5-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="232a5-161">ستظهر عمليات الحساب الجديدة كأعمدة جديدة في كيان إخراج المقياس.</span><span class="sxs-lookup"><span data-stu-id="232a5-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="232a5-162">حدد **...** على عملية الحساب من أجل **تكرار** عملية حساب أو **إعادتها** أو **إزالتها** من مقياس.</span><span class="sxs-lookup"><span data-stu-id="232a5-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="232a5-163">في منطقة **المعاينة**، سوف ترى مخطط البيانات الخاص بكيان إخراج المقياس، بما في ذلك عوامل التصفية والأبعاد.</span><span class="sxs-lookup"><span data-stu-id="232a5-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="232a5-164">تتفاعل المعاينة بشكل ديناميكي مع التغييرات في التكوين.</span><span class="sxs-lookup"><span data-stu-id="232a5-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="232a5-165">حدد **تشغيل** لحساب النتائج للمقياس المكوّن.</span><span class="sxs-lookup"><span data-stu-id="232a5-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="232a5-166">حدد **حفظ وإغلاق** إذا كنت ترغب في الاحتفاظ بالتكوين الحالي وتشغيل المقياس لاحقًا.</span><span class="sxs-lookup"><span data-stu-id="232a5-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="232a5-167">انتقل إلى **المقاييس** لرؤية المقياس الذي تم إنشاؤه مؤخرًا في القائمة.</span><span class="sxs-lookup"><span data-stu-id="232a5-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="232a5-168">إدارة المقاييس الخاصة بك</span><span class="sxs-lookup"><span data-stu-id="232a5-168">Manage your measures</span></span>

<span data-ttu-id="232a5-169">بعد [إنشاء مقياس](#create-a-measure)، سترى قائمة بالمقاييس في صفحة **المقاييس**.</span><span class="sxs-lookup"><span data-stu-id="232a5-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="232a5-170">ستعثر على معلومات حول نوع المقياس والمنشئ وتاريخ الإنشاء والحالة والولاية.</span><span class="sxs-lookup"><span data-stu-id="232a5-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="232a5-171">عند تحديد مقياس من القائمة، يمكنك معاينة الإخراج وتنزيل ملف CSV.</span><span class="sxs-lookup"><span data-stu-id="232a5-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="232a5-172">لتحديث كافة المقاييس الخاصة بك في نفس الوقت، حدد **تحديث الكل** دون تحديد مقياس معين.</span><span class="sxs-lookup"><span data-stu-id="232a5-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="232a5-173">![إجراءات لإدارة المقاييس الفردية](media/measure-actions.png "إجراءات لإدارة المقاييس الفردية")</span><span class="sxs-lookup"><span data-stu-id="232a5-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="232a5-174">حدد مقياسًا من القائمة للخيارات التالية:</span><span class="sxs-lookup"><span data-stu-id="232a5-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="232a5-175">حدد اسم المقياس لرؤية التفاصيل الخاصة به.</span><span class="sxs-lookup"><span data-stu-id="232a5-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="232a5-176">**تحرير** تكوين المقياس.</span><span class="sxs-lookup"><span data-stu-id="232a5-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="232a5-177">**تحديث** المقياس استنادًا إلى البيانات الأخيرة.</span><span class="sxs-lookup"><span data-stu-id="232a5-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="232a5-178">**إعادة تسمية** المقياس.</span><span class="sxs-lookup"><span data-stu-id="232a5-178">**Rename** the measure.</span></span>
- <span data-ttu-id="232a5-179">**حذف** المقياس.</span><span class="sxs-lookup"><span data-stu-id="232a5-179">**Delete** the measure.</span></span>
- <span data-ttu-id="232a5-180">**تنشيط** أو **إلغاء التنشيط**.</span><span class="sxs-lookup"><span data-stu-id="232a5-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="232a5-181">لن يتم تحديث الإجراءات غير النشطة أثناء [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="232a5-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="232a5-182">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="232a5-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="232a5-183">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="232a5-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="232a5-184">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="232a5-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="232a5-185">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="232a5-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="232a5-186">الخطوة التالية</span><span class="sxs-lookup"><span data-stu-id="232a5-186">Next step</span></span>

<span data-ttu-id="232a5-187">يمكنك استخدام مقاييس موجودة لإنشاء [شريحة عملاء](segments.md).</span><span class="sxs-lookup"><span data-stu-id="232a5-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]