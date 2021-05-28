---
title: دمج الكيانات في توحيد البيانات
description: دمج الكيانات لإنشاء ملفات تعريف العملاء الموحدة.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085560"
---
# <a name="merge-entities"></a><span data-ttu-id="7555c-103">دمج الكيانات</span><span class="sxs-lookup"><span data-stu-id="7555c-103">Merge entities</span></span>

<span data-ttu-id="7555c-104">تُعتبر مرحلة الدمج هي المرحلة الأخيرة في عملية توحيد البيانات.</span><span class="sxs-lookup"><span data-stu-id="7555c-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="7555c-105">والغرض منها هو التوفيق بين البيانات المتعارضة.</span><span class="sxs-lookup"><span data-stu-id="7555c-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="7555c-106">قد تتضمن أمثلة البيانات المتعارضة اسم عميل موجود في اثنين من مجموعات البيانات الخاصة بك ولكن يظهر بشكل مختلف قليلاً في كل من ("Grant Marshall" مقابل "Grant Marshall") ، أو رقم هاتف يختلف في التنسيق (617-803-091X مقابل 617803091X).</span><span class="sxs-lookup"><span data-stu-id="7555c-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="7555c-107">يتم دمج نقاط البيانات المتعارضة هذه على أساس كل سمة على حدة.</span><span class="sxs-lookup"><span data-stu-id="7555c-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="صفحة الدمج في عملية توحيد البيانات تُظهر جدول بالحقول المدمجة التي تحدد ملف تعريف العميل الموحد.":::

<span data-ttu-id="7555c-109">بعد الانتهاء من [مرحلة المطابقة](match-entities.md)، يمكنك بدء مرحلة الدمج من خلال تحديد الإطار المتجانب **دمج** في الصفحة **توحيد** .</span><span class="sxs-lookup"><span data-stu-id="7555c-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="7555c-110">مراجعة توصيات النظام</span><span class="sxs-lookup"><span data-stu-id="7555c-110">Review system recommendations</span></span>

<span data-ttu-id="7555c-111">في **البيانات** > **توحيد** > **دمج**، عليك اختيار السمات المراد دمجها واستثنائها للدمج داخل كيان ملف تعريف العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="7555c-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="7555c-112">يكون ملف تعريف العميل الموحد هو نتيجة عملية توحيد البيانات.</span><span class="sxs-lookup"><span data-stu-id="7555c-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="7555c-113">يتم دمج بعض السمات تلقائيًا بواسطة النظام.</span><span class="sxs-lookup"><span data-stu-id="7555c-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="7555c-114">لعرض السمات المضمنة في السمات المدمجة تلقائيًا الخاصة بك، حدد السمة المدمجة في علامة التبويب **حقول العملاء** في الجدول.</span><span class="sxs-lookup"><span data-stu-id="7555c-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="7555c-115">ستظهر السمات التي تشكل السمة المدمجة في صفين جديدين أسفل السمة المدمجة.</span><span class="sxs-lookup"><span data-stu-id="7555c-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="7555c-116">فصل الحقول ودمجها وإعادة تسميتها واستبعادها وتحريرها</span><span class="sxs-lookup"><span data-stu-id="7555c-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="7555c-117">يمكنك تغيير كيفية معالجة النظام للسمات المدمجة لإنشاء ملف تعريف العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="7555c-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="7555c-118">حدد **إظهار المزيد** واختر ما ترغب في تغييره.</span><span class="sxs-lookup"><span data-stu-id="7555c-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="خيارات في القائمة المنسدلة إظهار المزيد لإدارة السمات المدمجة.":::

<span data-ttu-id="7555c-120">لمزيد من المعلومات، انظر الأقسام التالية.</span><span class="sxs-lookup"><span data-stu-id="7555c-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="7555c-121">فصل الحقول المدمجة</span><span class="sxs-lookup"><span data-stu-id="7555c-121">Separate merged fields</span></span>

<span data-ttu-id="7555c-122">لفصل الحقول المدمجة، ابحث عن السمة في الجدول.</span><span class="sxs-lookup"><span data-stu-id="7555c-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="7555c-123">تظهر الحقول المفصولة كنقاط بيانات فردية في ملف تعريف العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="7555c-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="7555c-124">حدد الحقل المدمج.</span><span class="sxs-lookup"><span data-stu-id="7555c-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="7555c-125">حدد **إظهار المزيد** واختر **فصل الحقول**.</span><span class="sxs-lookup"><span data-stu-id="7555c-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="7555c-126">قم بتأكد من الفصل.</span><span class="sxs-lookup"><span data-stu-id="7555c-126">Confirm the separation.</span></span>

1. <span data-ttu-id="7555c-127">حدد **حفظ** و **تشغيل** لمعالجة التغييرات.</span><span class="sxs-lookup"><span data-stu-id="7555c-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="7555c-128">إعادة تسمية الحقول المدمجة</span><span class="sxs-lookup"><span data-stu-id="7555c-128">Rename merged fields</span></span>

<span data-ttu-id="7555c-129">تغيير اسم العرض للسمات المدمجة.</span><span class="sxs-lookup"><span data-stu-id="7555c-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="7555c-130">لا يمكنك تغيير اسم كيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="7555c-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="7555c-131">حدد الحقل المدمج.</span><span class="sxs-lookup"><span data-stu-id="7555c-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="7555c-132">حدد **إظهار المزيد** واختر **إعادة تسمية**.</span><span class="sxs-lookup"><span data-stu-id="7555c-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="7555c-133">قم بتأكيد اسم العرض الذي تم تغييره.</span><span class="sxs-lookup"><span data-stu-id="7555c-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="7555c-134">حدد **حفظ** و **تشغيل** لمعالجة التغييرات.</span><span class="sxs-lookup"><span data-stu-id="7555c-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="7555c-135">استبعاد الحقول المدمجة</span><span class="sxs-lookup"><span data-stu-id="7555c-135">Exclude merged fields</span></span>

<span data-ttu-id="7555c-136">استبعاد سمة من ملف تعريف العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="7555c-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="7555c-137">إذا كان الحقل مستخدمًا في عمليات أخرى، في شريحة مثلا، فقم بإزالته من هذه العمليات قبل استبعاده من ملف تعريف العميل.</span><span class="sxs-lookup"><span data-stu-id="7555c-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="7555c-138">حدد الحقل المدمج.</span><span class="sxs-lookup"><span data-stu-id="7555c-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="7555c-139">حدد **إظهار المزيد** واختر **استبعاد**.</span><span class="sxs-lookup"><span data-stu-id="7555c-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="7555c-140">قم بتأكيد الاستبعاد.</span><span class="sxs-lookup"><span data-stu-id="7555c-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="7555c-141">حدد **حفظ** و **تشغيل** لمعالجة التغييرات.</span><span class="sxs-lookup"><span data-stu-id="7555c-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="7555c-142">في صفحة **الدمج**، قم بتحديد **الحقول المستبعدة‬** لرؤية قائمة بجميع الحقول المستبعدة‬.</span><span class="sxs-lookup"><span data-stu-id="7555c-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="7555c-143">يتيح لك هذا الجزء إضافة الحقول المستثناة مرة أخرى.</span><span class="sxs-lookup"><span data-stu-id="7555c-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="7555c-144">تجميع الحقول يدويًا</span><span class="sxs-lookup"><span data-stu-id="7555c-144">Manually combine fields</span></span>

<span data-ttu-id="7555c-145">حدد سمة مدمجة يدويًا.</span><span class="sxs-lookup"><span data-stu-id="7555c-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="7555c-146">في صفحة **الدمج**، قم بتحديد **دمج الحقول**.</span><span class="sxs-lookup"><span data-stu-id="7555c-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="7555c-147">قم بتوفير **اسم** و **اسم حقل الإخراج**.</span><span class="sxs-lookup"><span data-stu-id="7555c-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="7555c-148">اختر حقلا لإضافته.</span><span class="sxs-lookup"><span data-stu-id="7555c-148">Choose a field to add.</span></span> <span data-ttu-id="7555c-149">حدد **إضافة حقول** لدمج مزيد من الحقول.</span><span class="sxs-lookup"><span data-stu-id="7555c-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="7555c-150">قم بتأكيد الاستبعاد.</span><span class="sxs-lookup"><span data-stu-id="7555c-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="7555c-151">حدد **حفظ** و **تشغيل** لمعالجة التغييرات.</span><span class="sxs-lookup"><span data-stu-id="7555c-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="7555c-152">تغيير ترتيب الحقول</span><span class="sxs-lookup"><span data-stu-id="7555c-152">Change the order of fields</span></span>

<span data-ttu-id="7555c-153">تحتوي بعض الكيانات على تفاصيل أكثر من الأخرى.</span><span class="sxs-lookup"><span data-stu-id="7555c-153">Some entities contain more details than others.</span></span> <span data-ttu-id="7555c-154">إذا كان أحد الكيانات يتضمن أحدث البيانات حول أحد الحقول، فيمكنك تحديد أولوياته على الكيانات الأخرى عند دمج القيم.</span><span class="sxs-lookup"><span data-stu-id="7555c-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="7555c-155">حدد الحقل المدمج.</span><span class="sxs-lookup"><span data-stu-id="7555c-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="7555c-156">حدد **إظهار المزيد** واختر **تحرير**.</span><span class="sxs-lookup"><span data-stu-id="7555c-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="7555c-157">من جزء **دمج الحقول**، قم بتحديد **نقل لأعلى/لأسفل** لتعيين الترتيب أو قم بسحبها وإفلاتها في الموضع المطلوب.</span><span class="sxs-lookup"><span data-stu-id="7555c-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="7555c-158">قم بتأكيد التغيير.</span><span class="sxs-lookup"><span data-stu-id="7555c-158">Confirm the change.</span></span>

1. <span data-ttu-id="7555c-159">حدد **حفظ** و **تشغيل** لمعالجة التغييرات.</span><span class="sxs-lookup"><span data-stu-id="7555c-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="7555c-160">تشغيل الدمج الخاص بك</span><span class="sxs-lookup"><span data-stu-id="7555c-160">Run your merge</span></span>

<span data-ttu-id="7555c-161">سواء كنت تقوم بدمج السمات يدويًا أو إتاحة الفرصة للنظام ليدمجها، يمكنك دائمًا تشغيل الدمج.</span><span class="sxs-lookup"><span data-stu-id="7555c-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="7555c-162">حدد **تشغيل** في صفحة **الدمج** لبدء العملية.</span><span class="sxs-lookup"><span data-stu-id="7555c-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7555c-163">![حفظ دمج البيانات وتشغيلها](media/configure-data-merge-save-run.png "حفظ دمج البيانات وتشغيلها")</span><span class="sxs-lookup"><span data-stu-id="7555c-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="7555c-164">اختر ‏‫**تشغيل الدمج فقط‬** إذا كنت ترغب فقط في رؤية الإخراج ينعكس على كيان العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="7555c-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="7555c-165">سيتم تحديث العمليات اللاحقة كما هي [محددة في جدولة التحديث](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7555c-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="7555c-166">اختر **تشغيل الدمج والعمليات اللاحقة** لتحديث النظام بتغييراتك.</span><span class="sxs-lookup"><span data-stu-id="7555c-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="7555c-167">سيتم تشغيل جميع العمليات تلقائيا، بما في ذلك العمليات المضمنة والشرائح و القياسات.</span><span class="sxs-lookup"><span data-stu-id="7555c-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="7555c-168">بعد اكتمال كافة العمليات اللاحقة، ستعكس ملفات تعريف العملاء أية تغييرات قمت بها.</span><span class="sxs-lookup"><span data-stu-id="7555c-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="7555c-169">لإجراء مزيد من التغييرات ثم إعادة تشغيل الخطوة، يمكنك إلغاء الدمج قيد التقدم.</span><span class="sxs-lookup"><span data-stu-id="7555c-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="7555c-170">حدد النص **جار التحديث...** وحدد **مهمة الإلغاء** في أسفل الجزء الجانبي الذي يظهر.</span><span class="sxs-lookup"><span data-stu-id="7555c-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="7555c-171">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="7555c-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="7555c-172">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="7555c-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="7555c-173">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="7555c-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="7555c-174">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="7555c-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="7555c-175">الخطوة التالية</span><span class="sxs-lookup"><span data-stu-id="7555c-175">Next Step</span></span>

<span data-ttu-id="7555c-176">قم بتكوين [الأنشطة](activities.md)، [‏‫الإثراء‬](enrichment-hub.md)، أو [العلاقات](relationships.md) لمزيد من الرؤى حول عملائك.</span><span class="sxs-lookup"><span data-stu-id="7555c-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="7555c-177">إذا كنت قد قمت بالفعل بتكوين الأنشطة أو الإثراء أو الشرائح، فسوف تتم معالجتها تلقائيًا لاستخدام أحدث بيانات العملاء.</span><span class="sxs-lookup"><span data-stu-id="7555c-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
