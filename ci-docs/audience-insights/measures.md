---
title: إنشاء المقاييس وتحريرها
description: تحديد المقاييس المتعلقة بالعملاء لتحليل وعكس أداء بعض مجالات العمل.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4404938"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="49923-103">تحديد المقاييس وإدارتها</span><span class="sxs-lookup"><span data-stu-id="49923-103">Define and manage measures</span></span>

<span data-ttu-id="49923-104">تمثل **المقاييس** مؤشرات الأداء الرئيسية (KPIs) التي تعكس أداء مناطق العمل المحددة وسلامتها.</span><span class="sxs-lookup"><span data-stu-id="49923-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="49923-105">توفر رؤى الجمهور تجربة سهلة لإنشاء أنواع مختلفة من المقاييس، باستخدام منشئ الاستعلام الذي لا يتطلب تعليمات برمجية أو يتحقق من صحة المقاييس يدويًا.</span><span class="sxs-lookup"><span data-stu-id="49923-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="49923-106">يمكنك تعقب مقاييس الأعمال الخاصة بك علي الصفحة **الرئيسية** ، ومراجعه المقاييس الخاصة بالعملاء المعينين علي **بطاقة العميل**، واستخدام المقاييس لتحديد شرائح العميل في صفحه **الشرائح** .</span><span class="sxs-lookup"><span data-stu-id="49923-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="49923-107">إنشاء مقياس</span><span class="sxs-lookup"><span data-stu-id="49923-107">Create a measure</span></span>

<span data-ttu-id="49923-108">يوضح لك هذا القسم كيفية إنشاء مقياس من البداية.</span><span class="sxs-lookup"><span data-stu-id="49923-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="49923-109">يمكنك إنشاء مقاييس بالبيانات من مصادر بيانات متعددة متصلة من خلال كيان العميل.</span><span class="sxs-lookup"><span data-stu-id="49923-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="49923-110">تنطبق بعض [قيود الخدمة](service-limits.md) apply.</span><span class="sxs-lookup"><span data-stu-id="49923-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="49923-111">في رؤى الجمهور، انتقل إلى **المقاييس**.</span><span class="sxs-lookup"><span data-stu-id="49923-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="49923-112">‏‏حدد **مقياس جديد**.</span><span class="sxs-lookup"><span data-stu-id="49923-112">Select **New measure**.</span></span>

3. <span data-ttu-id="49923-113">اختر **نوع** المقياس:</span><span class="sxs-lookup"><span data-stu-id="49923-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="49923-114">**سمة العميل**: حقل واحد لكل عميل يعكس درجة أو قيمة أو حالة العميل.</span><span class="sxs-lookup"><span data-stu-id="49923-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="49923-115">يتم إنشاء سمات العملاء بصفتها سمات في كيان جديد تم إنشاؤه بواسطة النظام يسمى **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="49923-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="49923-116">**مقياس العميل**: رؤى حول سلوك العملاء مع توزيع حسب الأبعاد المحددة.</span><span class="sxs-lookup"><span data-stu-id="49923-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="49923-117">يتم إنشاء كيان جديد لكل مقياس، ومن المحتمل أن يكون مع العديد من السجلات لكل عميل.</span><span class="sxs-lookup"><span data-stu-id="49923-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="49923-118">**مقياس الأعمال**: تعقب أداء الأعمال الخاصة بك وسلامتها.</span><span class="sxs-lookup"><span data-stu-id="49923-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="49923-119">يمكن أن تحتوي مقاييس الأعمال علي مخرجين مختلفين : المخرج الرقمي الذي يظهر علي الصفحة **الرئيسية** أو الكيان الجديد الذي تجده في صفحه **الكيانات** .</span><span class="sxs-lookup"><span data-stu-id="49923-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="49923-120">قم بتوفير **اسم** ويكون **‏‫الاسم المعروض** اختياري، ثم قم بتحديد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="49923-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="49923-121">في قسم **الكيانات** ، حدد الكيان الأول من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="49923-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="49923-122">عند هذه النقطة، ينبغي أن تقرر ما إذا كانت هناك حاجة إلى كيانات إضافية كجزء من تعريف المقياس الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="49923-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="49923-123">![تعريف المقياس](media/measure-definition.png "تعريف القياس")</span><span class="sxs-lookup"><span data-stu-id="49923-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="49923-124">لإضافة المزيد من الكيانات ، حدد **إضافة كيان** وحدد كيانات تريد استخدامها للقياس.</span><span class="sxs-lookup"><span data-stu-id="49923-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="49923-125">يمكنك تحديد الكيانات التي لها علاقات بكيان البداية فقط.</span><span class="sxs-lookup"><span data-stu-id="49923-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="49923-126">للمزيد من المعلومات حول تعريف العلاقات ، راجع [العلاقات](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="49923-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="49923-127">اختياريًا، يمكنك تكوين المتغيرات.</span><span class="sxs-lookup"><span data-stu-id="49923-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="49923-128">في قسم **المتغيرات** ، حدد **مُتغير جديد**.</span><span class="sxs-lookup"><span data-stu-id="49923-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="49923-129">المتغيرات هي حسابات يتم إجراؤها على كل سجل من سجلاتك المحددة.</span><span class="sxs-lookup"><span data-stu-id="49923-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="49923-130">على سبيل المثال، تجميع نقاط البيع (POS) والمبيعات عبر الإنترنت لكل سجل من سجلات عملائك.</span><span class="sxs-lookup"><span data-stu-id="49923-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="49923-131">قم بإدخال **اسم** لكل متغير.</span><span class="sxs-lookup"><span data-stu-id="49923-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="49923-132">في منطقة **‎التعبير** ‏‎، اختر حقلًا لبدء العمل مع الحساب الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="49923-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="49923-133">اكتب تعبيرًا في منطقة **التعبير** في أثناء اختيار المزيد من الحقول التي سيتم تضمينها في عمليه الحساب الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="49923-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="49923-134">في الوقت الحالي، التعابير الرياضية وحدها مدعومة.</span><span class="sxs-lookup"><span data-stu-id="49923-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="49923-135">بالإضافة إلى ذلك ، لا يتم دعم الحساب المتغير للكيانات من [مسارات الكيانات](relationships.md)المختلفة .</span><span class="sxs-lookup"><span data-stu-id="49923-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="49923-136">حدد **تم**.</span><span class="sxs-lookup"><span data-stu-id="49923-136">Select **Done**.</span></span>

11. <span data-ttu-id="49923-137">في القسم **تعريف المقياس** ، ستحدد كيفية تجميع الكيانات التي اخترتها والمتغيرات المحتسبة في كيان أو سمة قياس جديدة.</span><span class="sxs-lookup"><span data-stu-id="49923-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="49923-138">‏‏حدد **البعد الجديد**.</span><span class="sxs-lookup"><span data-stu-id="49923-138">Select **New dimension**.</span></span> <span data-ttu-id="49923-139">يمكنك اعتبار البعد كوظيفة *تجميع حسب* .</span><span class="sxs-lookup"><span data-stu-id="49923-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="49923-140">سوف يتم تجميع مخرجات البيانات الخاصة بكيان مقياس أو سمة من خلال جميع الأبعاد المحددة.</span><span class="sxs-lookup"><span data-stu-id="49923-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="49923-141">![اختر دورة التجميع](media/measures-businessreport-measure-definition2.png "اختر دورة التجميع")</span><span class="sxs-lookup"><span data-stu-id="49923-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="49923-142">حدد أو أدخل المعلومات التالية كجزء من تعريف البعد الخاص بك:</span><span class="sxs-lookup"><span data-stu-id="49923-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="49923-143">**الكيان**: إذا قمت بتحديد كيان المقياس، فيجب أن يتضمن سمة واحدة على الأقل.</span><span class="sxs-lookup"><span data-stu-id="49923-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="49923-144">إذا قمت بتحديد سمة المقياس، فستشمل سمة واحدة فقط افتراضيًا.</span><span class="sxs-lookup"><span data-stu-id="49923-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="49923-145">هذا التحديد يدور حول اختيار الكيان الذي يتضمن تلك السمة.</span><span class="sxs-lookup"><span data-stu-id="49923-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="49923-146">**الحقل**: اختر السمة المحددة المراد تضمينها إما في كيان القياس أو السمة.</span><span class="sxs-lookup"><span data-stu-id="49923-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="49923-147">**المستودع**: اختر ما إذا كنت ترغب في تجميع البيانات على أساس يومي أو شهري أو سنوي.</span><span class="sxs-lookup"><span data-stu-id="49923-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="49923-148">إنه التحديد المطلوب فقط إذا كنت قد قمت بتحديد سمة نوع التاريخ.</span><span class="sxs-lookup"><span data-stu-id="49923-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="49923-149">**باعتباره**: يُعرف اسم الحقل الجديد الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="49923-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="49923-150">**الاسم المعروض**: يحدد الاسم المعروض للحقل الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="49923-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="49923-151">سيتم حفظ مقياس العمل ككيان من رقم واحد وسوف يظهر علي الصفحة **الرئيسية** ما لم تتم إضافة المزيد من الأبعاد إلى المقياس الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="49923-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="49923-152">بعد إضافة المزيد من الأبعاد، *لن* يظهر المقياس علي الصفحة **الرئيسية** .</span><span class="sxs-lookup"><span data-stu-id="49923-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="49923-153">بشكل اختياري، قم بإضافة وظائف التجميع.</span><span class="sxs-lookup"><span data-stu-id="49923-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="49923-154">ينتج عن أي تجميع تقوم بإنشائه قيمة جديدة داخل كيان أو سمة المقياس الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="49923-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="49923-155">وظائف التجميع المدعومة هي: **‏‫الحد الأدنى**، **الحد الأقصى**، **المتوسط**، **Median**، **المجموع**، **‏‫العدد الفريد‬**، **الأول** (يأخذ السجل الأول من قيمة البعد)، و **الأخير** (يأخذ السجل الأخير المضاف إلى قيمة البعد).</span><span class="sxs-lookup"><span data-stu-id="49923-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="49923-156">حدد **حفظ** لتطبيق تغييراتك على المقياس.</span><span class="sxs-lookup"><span data-stu-id="49923-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="49923-157">إدارة المقاييس الخاصة بك</span><span class="sxs-lookup"><span data-stu-id="49923-157">Manage your measures</span></span>

<span data-ttu-id="49923-158">بعد إنشاء مقياس واحد على الأقل، سترى قائمة تتضمن مقاييس في صفحة **المقاييس**.</span><span class="sxs-lookup"><span data-stu-id="49923-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="49923-159">سوف تجد معلومات حول نوع المقياس والمُنشئ وتاريخ ووقت الإنشاء وتاريخ آخر تحرير ووقته والحالة (سواء كانت المقاييس نشطة أو غير نشطه أو فشلت) وتاريخ ووقت آخر تحديث.</span><span class="sxs-lookup"><span data-stu-id="49923-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="49923-160">عندما تقوم بتحديد مقياس من القائمة، فإنه يمكنك رؤية معاينة لإخراجه.</span><span class="sxs-lookup"><span data-stu-id="49923-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="49923-161">لتحديث كافة المقاييس الخاصة بك في نفس الوقت، حدد **تحديث الكل** دون تحديد مقياس معين.</span><span class="sxs-lookup"><span data-stu-id="49923-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="49923-162">![إجراءات لإدارة المقاييس الفردية](media/measure-actions.png "إجراءات لإدارة المقاييس الفردية")</span><span class="sxs-lookup"><span data-stu-id="49923-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="49923-163">بدلاً من ذلك، حدد مقياسًا من القائمة وقم بتنفيذ أحد الإجراءات التالية:</span><span class="sxs-lookup"><span data-stu-id="49923-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="49923-164">حدد اسم المقياس لرؤية التفاصيل الخاصة به.</span><span class="sxs-lookup"><span data-stu-id="49923-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="49923-165">**قم بتحرير** تكوين المقياس.</span><span class="sxs-lookup"><span data-stu-id="49923-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="49923-166">**إعادة تسمية** المقياس.</span><span class="sxs-lookup"><span data-stu-id="49923-166">**Rename** the measure.</span></span>
- <span data-ttu-id="49923-167">**حذف** المقياس.</span><span class="sxs-lookup"><span data-stu-id="49923-167">**Delete** the measure.</span></span>
- <span data-ttu-id="49923-168">حدد علامة الحذف (...) ثم قم **بالتحديث** لبدء عملية التحديث لهذا المقياس.</span><span class="sxs-lookup"><span data-stu-id="49923-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="49923-169">حدد علامة الحذف (...) ثم قم **بالتنزيل** للحصول علي. ملف .CSV الخاص بالمقياس.</span><span class="sxs-lookup"><span data-stu-id="49923-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="49923-170">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="49923-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="49923-171">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="49923-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="49923-172">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="49923-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="49923-173">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="49923-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="49923-174">الخطوة التالية</span><span class="sxs-lookup"><span data-stu-id="49923-174">Next step</span></span>

<span data-ttu-id="49923-175">يمكنك استخدام القياسات الموجودة لإنشاء أول شريحة للعميل علي صفحة **الشرائح** .</span><span class="sxs-lookup"><span data-stu-id="49923-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="49923-176">للمزيد من المعلومات، راجع [الشرائح](segments.md).</span><span class="sxs-lookup"><span data-stu-id="49923-176">For more information, see [Segments](segments.md).</span></span>
