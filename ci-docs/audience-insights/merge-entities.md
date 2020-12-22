---
title: دمج الكيانات في توحيد البيانات
description: دمج الكيانات لإنشاء ملفات تعريف العملاء الموحدة.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4404935"
---
# <a name="merge-entities"></a><span data-ttu-id="91137-103">دمج الكيانات</span><span class="sxs-lookup"><span data-stu-id="91137-103">Merge entities</span></span>

<span data-ttu-id="91137-104">تُعتبر مرحلة الدمج هي المرحلة الأخيرة في عملية توحيد البيانات.</span><span class="sxs-lookup"><span data-stu-id="91137-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="91137-105">والغرض منها هو التوفيق بين البيانات المتعارضة.</span><span class="sxs-lookup"><span data-stu-id="91137-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="91137-106">قد تتضمن أمثلة البيانات المتعارضة اسم عميل موجود في اثنين من مجموعات البيانات الخاصة بك ولكن يظهر بشكل مختلف قليلاً في كل من ("Grant Marshall" مقابل "Grant Marshall") ، أو رقم هاتف يختلف في التنسيق (617-803-091X مقابل 617803091X).</span><span class="sxs-lookup"><span data-stu-id="91137-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="91137-107">يتم دمج نقاط البيانات المتعارضة هذه على أساس كل سمة على حدة.</span><span class="sxs-lookup"><span data-stu-id="91137-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="91137-108">بعد الانتهاء من [مرحلة المطابقة](match-entities.md)، يمكنك بدء مرحلة الدمج من خلال تحديد الإطار المتجانب **دمج** في الصفحة **توحيد** .</span><span class="sxs-lookup"><span data-stu-id="91137-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="91137-109">مراجعة توصيات النظام</span><span class="sxs-lookup"><span data-stu-id="91137-109">Review system recommendations</span></span>

<span data-ttu-id="91137-110">في صفحة **الدمج** ، اختر واستبعد السمات المراد دمجها في كيان ملف تعريف العميل الموحد الخاص بك (نتيجة عملية التكوين).</span><span class="sxs-lookup"><span data-stu-id="91137-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="91137-111">يتم دمج بعض السمات تلقائيًا بواسطة النظام.</span><span class="sxs-lookup"><span data-stu-id="91137-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="91137-112">عرض السمات المدمجة</span><span class="sxs-lookup"><span data-stu-id="91137-112">View merged attributes</span></span>

<span data-ttu-id="91137-113">لعرض السمات المضمنة في إحدى السمات المدمجة تلقائيًا، حدد تلك السمة المدمجة.</span><span class="sxs-lookup"><span data-stu-id="91137-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="91137-114">تظهر السمتان اللتان تشكلان السمة المدمجة في صفين جديدين أسفل السمة المدمجة.</span><span class="sxs-lookup"><span data-stu-id="91137-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91137-115">![حدد سمة مُدمجة](media/configure-data-merge-profile-attributes.png "حدد سمة مُدمجة")</span><span class="sxs-lookup"><span data-stu-id="91137-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="91137-116">سمات مدمجة منفصلة</span><span class="sxs-lookup"><span data-stu-id="91137-116">Separate merged attributes</span></span>

<span data-ttu-id="91137-117">لفصل أو إلغاء دمج أي من السمات المدمجة تلقائيًا ، ابحث عن السمة في جدول **‏‫سمات ملف التعريف** .</span><span class="sxs-lookup"><span data-stu-id="91137-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="91137-118">حدد زر علامة القطع (...).</span><span class="sxs-lookup"><span data-stu-id="91137-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="91137-119">في القائمة المنسدلة، حدد **فصل الحقول**.</span><span class="sxs-lookup"><span data-stu-id="91137-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="91137-120">إزالة السمات المدمجة</span><span class="sxs-lookup"><span data-stu-id="91137-120">Remove merged attributes</span></span>

<span data-ttu-id="91137-121">لاستبعاد سمة من كيان ملف تعريف العميل النهائي ، ابحث عنها في جدول **سمات ملف التعريف** .</span><span class="sxs-lookup"><span data-stu-id="91137-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="91137-122">حدد زر علامة القطع (...).</span><span class="sxs-lookup"><span data-stu-id="91137-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="91137-123">في القائمة المنسدلة، حدد **عدم الدمج**.</span><span class="sxs-lookup"><span data-stu-id="91137-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="91137-124">يتم نقل السمة إلى قسم **تمت الإزالة من سجل العملاء** .</span><span class="sxs-lookup"><span data-stu-id="91137-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="91137-125">إضافة سمة مدمجة يدويًا</span><span class="sxs-lookup"><span data-stu-id="91137-125">Manually add a merged attribute</span></span>

<span data-ttu-id="91137-126">لإضافة سمة مدمجة، انتقل إلى صفحة **الدمج** .</span><span class="sxs-lookup"><span data-stu-id="91137-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="91137-127">حدد **إضافة سمة مدمجة**.</span><span class="sxs-lookup"><span data-stu-id="91137-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="91137-128">أدخل **اسم** لتحديده في صفحة **الدمج** لاحقًا.</span><span class="sxs-lookup"><span data-stu-id="91137-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="91137-129">بشكل اختياري، قم بتوفير **اسم العرض** الذي يظهر في كيان ملف تعريف العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="91137-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="91137-130">تكوين **تحديد سمات مكررة** لتحديد السمات التي تريد دمجها من الكيانات المتطابقة.</span><span class="sxs-lookup"><span data-stu-id="91137-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="91137-131">يمكنك أيضًا البحث عن السمات.</span><span class="sxs-lookup"><span data-stu-id="91137-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="91137-132">عيّن **الرتبة حسب الأهمية** لتحديد أولوية سمة واحدة فوق غيرها.</span><span class="sxs-lookup"><span data-stu-id="91137-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="91137-133">على سبيل المثال، إذا كان الكيان *WebAccountCSV* يتضمن البيانات الأكثر دقة حول السمة *الأسماء بالكامل* ، فيمكنك إعطاء الأولوية لهذا الكيان على *ContactCSV* عن طريق تحديد *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="91137-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="91137-134">ونتيجة لذلك، ينتقل *WebAccountCSV* إلى الأولوية الأولى، بينما ينتقل *ContactCSV* إلى الأولوية الثانية عند سحب قيم للسمة *الاسم بالكامل* .</span><span class="sxs-lookup"><span data-stu-id="91137-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="91137-135">تشغيل الدمج الخاص بك</span><span class="sxs-lookup"><span data-stu-id="91137-135">Run your merge</span></span>

<span data-ttu-id="91137-136">سواء كنت تقوم بدمج السمات يدويًا أو إتاحة الفرصة للنظام ليدمجها، يمكنك دائمًا تشغيل الدمج.</span><span class="sxs-lookup"><span data-stu-id="91137-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="91137-137">حدد **تشغيل** في صفحة **الدمج** لبدء العملية.</span><span class="sxs-lookup"><span data-stu-id="91137-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91137-138">![حفظ دمج البيانات وتشغيلها](media/configure-data-merge-save-run.png "حفظ دمج البيانات وتشغيلها")</span><span class="sxs-lookup"><span data-stu-id="91137-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="91137-139">لإجراء تغييرات إضافية وإعادة تشغيل الخطوة، فإنه يمكنك إلغاء دمج قيد التقدم.</span><span class="sxs-lookup"><span data-stu-id="91137-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="91137-140">حدد النص **جار التحديث...** وحدد **مهمة الإلغاء** في أسفل الجزء الجانبي الذي يظهر.</span><span class="sxs-lookup"><span data-stu-id="91137-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="91137-141">بعد أن يتم تغيير النص **جار التحديث...** إلى **ناجح**، تم إكمال الدمج وحل التناقضات في بياناتك وفقًا للسياسات التي قمت بتحديدها.</span><span class="sxs-lookup"><span data-stu-id="91137-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="91137-142">يتم تضمين السمات المدمجة وغير المدمجة في كيان ملف التعريف الموحد.</span><span class="sxs-lookup"><span data-stu-id="91137-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="91137-143">لم يتم تضمين السمات المستبعدة في كيان ملف التعريف الموحد.</span><span class="sxs-lookup"><span data-stu-id="91137-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="91137-144">إذا لم تكن في المرة الأولي التي تقوم فيها بتشغيل الدمج بنجاح، فإنه سيتم إعادة تشغيل كافة العمليات اللاحقة، بما في ذلك الإثراء والتقسيم والمقاييس تلقائيًا.</span><span class="sxs-lookup"><span data-stu-id="91137-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="91137-145">بعد إعادة تشغيل كافة العمليات اللاحقة، تُظهر ملفات تعريف العملاء أية تغييرات قمت بإجرائها.</span><span class="sxs-lookup"><span data-stu-id="91137-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="91137-146">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="91137-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="91137-147">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="91137-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="91137-148">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="91137-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="91137-149">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="91137-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="91137-150">الخطوة التالية</span><span class="sxs-lookup"><span data-stu-id="91137-150">Next Step</span></span>

<span data-ttu-id="91137-151">قم بتكوين [الأنشطة](activities.md)، [‏‫الإثراء‬](enrichment-microsoft-graph.md)، أو [العلاقات](relationships.md) لمزيد من الرؤى حول عملائك.</span><span class="sxs-lookup"><span data-stu-id="91137-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="91137-152">إذا كنت قد قمت بالفعل بتكوين الأنشطة أو الإثراء أو العلاقات أو إذا قمت بتحديد الشرائح، فإنه ستتم معالجتها تلقائيًا لاستخدام أحدث بيانات العميل.</span><span class="sxs-lookup"><span data-stu-id="91137-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>


