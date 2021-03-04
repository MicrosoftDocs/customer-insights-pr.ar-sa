---
title: إنشاء مقاطع وإدارتها
description: قم بإنشاء شرائح العملاء لتجميعهم استنادًا إلى العديد من السمات.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270340"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="11468-103">إنشاء مقاطع وإدارتها</span><span class="sxs-lookup"><span data-stu-id="11468-103">Create and manage segments</span></span>

<span data-ttu-id="11468-104">تتيح لك الشرائح تجميع العملاء وفقًا للسمات المتعلقة بالبيانات السكانية أو المعاملات أو السلوكيات.</span><span class="sxs-lookup"><span data-stu-id="11468-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="11468-105">يمكنك استخدام الشرائح لاستهداف الحملات الترويجية وأنشطة المبيعات وإجراءات دعم العملاء لتحقيق أهداف العمل الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="11468-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="11468-106">يمكنك تعريف عوامل تصفية معقدة حول كيان ملف تعريف العميل والكيانات المرتبطة به.</span><span class="sxs-lookup"><span data-stu-id="11468-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="11468-107">تعمل كل شريحة، بعد المعالجة، على إنشاء مجموعة من سجلات العملاء التي يمكنك تصديرها وتنفيذ إجراء عليها.</span><span class="sxs-lookup"><span data-stu-id="11468-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="11468-108">تنطبق بعض [قيود الخدمة](service-limits.md) apply.</span><span class="sxs-lookup"><span data-stu-id="11468-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="11468-109">الشرائح كلها هي **شرائح ديناميكية** يتم تحديثها وفق جدول متكرر، ما لم يتم ذكر عكس ذلك.</span><span class="sxs-lookup"><span data-stu-id="11468-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="11468-110">يوضح المثال التالي قدرة التقسيم إلى شرائح.</span><span class="sxs-lookup"><span data-stu-id="11468-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="11468-111">لقد قمنا بتحديد مقطع العملاء الذين قاموا بطلب بضائع بمبلغ 500 دولار أمريكي على الأقل في 90 يومًا الأخيرة *و* الذين تم تضمينهم في مكالمة خدمة العملاء التي تم تصعيدها.</span><span class="sxs-lookup"><span data-stu-id="11468-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11468-112">![مجموعات متعددة](media/segmentation-group1-2.png "مجموعات متعددة")</span><span class="sxs-lookup"><span data-stu-id="11468-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="11468-113">إنشاء مقطع جديد</span><span class="sxs-lookup"><span data-stu-id="11468-113">Create a new segment</span></span>

<span data-ttu-id="11468-114">تُدار الشرائح في صفحة **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="11468-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="11468-115">في رؤى الجمهور، انتقل إلى صفحة **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="11468-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="11468-116">حدد **جديد** > **مقطع فارغ**.</span><span class="sxs-lookup"><span data-stu-id="11468-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="11468-117">في جزء **المقطع الجديد**، اختر نوع المقطع وأطلق عليه **اسمًا**.</span><span class="sxs-lookup"><span data-stu-id="11468-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="11468-118">اختياريًا، أطلق اسم عرض ووصف يساعدك على تعريف المقطع.</span><span class="sxs-lookup"><span data-stu-id="11468-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="11468-119">حدد **التالي** للوصول إلى الصفحة **مُنشئ المقطع** حيث يمكنك تعريف مجموعة.</span><span class="sxs-lookup"><span data-stu-id="11468-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="11468-120">المجموعة هي مجموعة من العملاء.</span><span class="sxs-lookup"><span data-stu-id="11468-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="11468-121">اختر الكيان الذي يتضمن السمة التي تريد وضع المقطع بها.</span><span class="sxs-lookup"><span data-stu-id="11468-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="11468-122">اختر السمة المراد التقسيم وفقًا لها.</span><span class="sxs-lookup"><span data-stu-id="11468-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="11468-123">يمكن أن تحتوي هذه السمة على نوع واحد من أنواع القيم الأربعة: رقمي أو سلسلة أو تاريخ أو منطقي.</span><span class="sxs-lookup"><span data-stu-id="11468-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="11468-124">اختر عامل وقيمة للسمة المحددة.</span><span class="sxs-lookup"><span data-stu-id="11468-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11468-125">![عامل تصفية مخصص للمجموعة](media/customer-group-numbers.png "عامل تصفية مجموعة العميل")</span><span class="sxs-lookup"><span data-stu-id="11468-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="11468-126">الرقم</span><span class="sxs-lookup"><span data-stu-id="11468-126">Number</span></span> |<span data-ttu-id="11468-127">تعريف</span><span class="sxs-lookup"><span data-stu-id="11468-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="11468-128">1</span><span class="sxs-lookup"><span data-stu-id="11468-128">1</span></span>     |<span data-ttu-id="11468-129">Entity</span><span class="sxs-lookup"><span data-stu-id="11468-129">Entity</span></span>          |
   |<span data-ttu-id="11468-130">2</span><span class="sxs-lookup"><span data-stu-id="11468-130">2</span></span>     |<span data-ttu-id="11468-131">السمة</span><span class="sxs-lookup"><span data-stu-id="11468-131">Attribute</span></span>          |
   |<span data-ttu-id="11468-132">3</span><span class="sxs-lookup"><span data-stu-id="11468-132">3</span></span>    |<span data-ttu-id="11468-133">عامل</span><span class="sxs-lookup"><span data-stu-id="11468-133">Operator</span></span>         |
   |<span data-ttu-id="11468-134">4</span><span class="sxs-lookup"><span data-stu-id="11468-134">4</span></span>    |<span data-ttu-id="11468-135">قيمة</span><span class="sxs-lookup"><span data-stu-id="11468-135">Value</span></span>         |

8. <span data-ttu-id="11468-136">إذا كان الكيان متصلاً بكيان عميل موحد من خلال [العلاقات](relationships.md)، ستحتاج إلى تحديد مسار العلاقة لإنشاء مقطع صالح.</span><span class="sxs-lookup"><span data-stu-id="11468-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="11468-137">قم بإضافة الكيانات من مسار العلاقة حتى يمكنك تحديد الكيان **العميل: CustomerInsights** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="11468-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="11468-138">ثم، اختر **كافة السجلات** لكل شرط.</span><span class="sxs-lookup"><span data-stu-id="11468-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11468-139">![مسار العلاقة أثناء إنشاء المقطع](media/segments-multiple-relationships.png "مسار العلاقة أثناء إنشاء المقطع")</span><span class="sxs-lookup"><span data-stu-id="11468-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="11468-140">حدد **حفظ** لحفظ المقطع.</span><span class="sxs-lookup"><span data-stu-id="11468-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="11468-141">سيتم حفظ المقطع الخاص بك ومعالجته في حالة التحقق من صحة كافة المتطلبات.</span><span class="sxs-lookup"><span data-stu-id="11468-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="11468-142">وإلا، سيتم حفظه كمسودة.</span><span class="sxs-lookup"><span data-stu-id="11468-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="11468-143">قم بتحديد **رجوع إلى الشرائح** للعودة إلى صفحة **المقاطع**.</span><span class="sxs-lookup"><span data-stu-id="11468-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="11468-144">إدارة المقاطع الموجودة</span><span class="sxs-lookup"><span data-stu-id="11468-144">Manage existing segments</span></span>

<span data-ttu-id="11468-145">في صفحة **المقاطع**، يمكنك عرض كافة المقاطع التي قمت بحفظها وإدارتها.</span><span class="sxs-lookup"><span data-stu-id="11468-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="11468-146">يتم تمثيل كل شريحة بصف يشتمل على معلومات إضافية حول الشريحة.</span><span class="sxs-lookup"><span data-stu-id="11468-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="11468-147">يمكنك فرز الأجزاء في عمود من خلال تحديد عنوان العمود.</span><span class="sxs-lookup"><span data-stu-id="11468-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="11468-148">استخدم مربع **البحث** في الزاوية العليا اليمني لتصفية الشرائح.</span><span class="sxs-lookup"><span data-stu-id="11468-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11468-149">![خيارات إدارة مقطع حالي](media/segments-selected-segment.png "خيارات إدارة مقطع حالي")</span><span class="sxs-lookup"><span data-stu-id="11468-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="11468-150">تتوفر الإجراءات التالية عند تحديد أحد الأجزاء:</span><span class="sxs-lookup"><span data-stu-id="11468-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="11468-151">**اعرض** تفاصيل المقطع، بما في ذلك معاينة اتجاه عدد الأعضاء لأعضاء المقطع.</span><span class="sxs-lookup"><span data-stu-id="11468-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="11468-152">**قم بتحرير** المقطع لتغيير خصائصه.</span><span class="sxs-lookup"><span data-stu-id="11468-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="11468-153">**قم بتحديث** المقطع ليتضمن أحدث البيانات.</span><span class="sxs-lookup"><span data-stu-id="11468-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="11468-154">**قم بتنشيط** أو **إلغاء تنشيط** المقطع.</span><span class="sxs-lookup"><span data-stu-id="11468-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="11468-155">تحتوي الشرائح على حالتين محتملتين - نشطة أو غير نشطة.</span><span class="sxs-lookup"><span data-stu-id="11468-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="11468-156">تتوفر هذه الحالات في متناول عند تحرير مقطع.</span><span class="sxs-lookup"><span data-stu-id="11468-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="11468-157">بالنسبة للقطاعات غير النشطة ، يكون تعريف الشريحة موجودا ، ولكنه لا يحتوي علي اي عملاء حتى الآن.</span><span class="sxs-lookup"><span data-stu-id="11468-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="11468-158">عند تنشيط المقطع ، تتغير الحالة الخاصة به من "غير نشط" إلى "نشط" وتبدا في البحث عن العملاء الذين يتطابقون مع تعريف الشريحة.</span><span class="sxs-lookup"><span data-stu-id="11468-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="11468-159">إذا تم تكوين [تحديث مجدول](system.md#schedule-tab)، تم تسجيل **الحالة** كـ **تم التخطي** للشرائح غير النشطة، مما يشير إلى أنه لم تتم محاولة التحديث.</span><span class="sxs-lookup"><span data-stu-id="11468-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="11468-160">وعند تنشيط جزء غير نشط ، فانه سيتم تحديثه سيتم تضمينه في التحديثات المجدولة.</span><span class="sxs-lookup"><span data-stu-id="11468-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="11468-161">بدلاً من ذلك، يمكنك استخدام الوظيفة **الجدولة لاحقًا** في القائمة المنسدلة **تنشيط/إلغاء التنشيط** لتحديد التاريخ والوقت المستقبليين لعملية تنشيط وإلغاء تنشيط شريحة معينة.</span><span class="sxs-lookup"><span data-stu-id="11468-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="11468-162">**أعد تسمية** المقطع.</span><span class="sxs-lookup"><span data-stu-id="11468-162">**Rename** the segment.</span></span>
- <span data-ttu-id="11468-163">**قم بتنزيل** قائمة الأعضاء كملف بتنسيق CSV.</span><span class="sxs-lookup"><span data-stu-id="11468-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="11468-164">يقوم خيار **إضافة إلى** بإرسال قائمة بمعرفات العملاء في الشريحة لمعالجتها في تطبيق آخر.</span><span class="sxs-lookup"><span data-stu-id="11468-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="11468-165">**احذف** المقطع.</span><span class="sxs-lookup"><span data-stu-id="11468-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="11468-166">تحديث الشرائح</span><span class="sxs-lookup"><span data-stu-id="11468-166">Refresh segments</span></span>

<span data-ttu-id="11468-167">يمكنك تحديث كل الشرائح مرة واحدة من خلال تحديد **تحديث الكل** في صفحة **الشرائح** أو يمكنك تحديث شريحة واحدة أو عدة شرائح عندما تقوم بتحديدها واختيار **تحديث** من الخيارات.</span><span class="sxs-lookup"><span data-stu-id="11468-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="11468-168">وبدلاً من ذلك، يمكنك تكوين تحديث متكرر في **المسؤول** > **النظام** > **جدولة**.</span><span class="sxs-lookup"><span data-stu-id="11468-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="11468-169">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="11468-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="11468-170">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="11468-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="11468-171">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="11468-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="11468-172">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="11468-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="11468-173">تنزيل المقاطع وتصديرها</span><span class="sxs-lookup"><span data-stu-id="11468-173">Download and export segments</span></span>

<span data-ttu-id="11468-174">يمكنك تنزيل المقاطع الخاصة بك إلى ملف CSV أو تصديرها إلى Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="11468-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="11468-175">قم بتنزيل المقاطع إلى ملف CSV</span><span class="sxs-lookup"><span data-stu-id="11468-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="11468-176">في رؤى الجمهور، انتقل إلى صفحة **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="11468-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="11468-177">حدد علامة الحذف في إطار مقطع معين.</span><span class="sxs-lookup"><span data-stu-id="11468-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="11468-178">حدد **تنزيل كـ CSV** من قائمة الإجراءات المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="11468-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="11468-179">تصدير المقاطع إلى Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="11468-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="11468-180">قبل تصدير المقاطع إلى Dynamics 365 Sales، يجب على المسؤول [إنشاء وجهه التصدير](export-destinations.md) لـ Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="11468-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="11468-181">في رؤى الجمهور، انتقل إلى صفحة **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="11468-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="11468-182">حدد علامة الحذف في إطار مقطع معين.</span><span class="sxs-lookup"><span data-stu-id="11468-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="11468-183">حدد **إضافة إلى** من القائمة المنسدلة "إجراءات" وحدد وجهة التصدير التي ترغب في إرسال البيانات إليها.</span><span class="sxs-lookup"><span data-stu-id="11468-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="11468-184">وضع المسودة للمقاطع</span><span class="sxs-lookup"><span data-stu-id="11468-184">Draft mode for segments</span></span>

<span data-ttu-id="11468-185">في حالة عدم استيفاء كافة متطلبات معالجة مقطع ما، فإنه يمكنك حفظ المقطع كمسودة والوصول إليه من الصفحة **المقاطع**.</span><span class="sxs-lookup"><span data-stu-id="11468-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="11468-186">سيتم حفظه كمقطع غير نشط، ولا يمكن تنشيطه إلى أن يصبح صالحًا.</span><span class="sxs-lookup"><span data-stu-id="11468-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="11468-187">أضق المزيد من الشروط إلى مجموعة</span><span class="sxs-lookup"><span data-stu-id="11468-187">Add more conditions to a group</span></span>

<span data-ttu-id="11468-188">لإضافة المزيد من الشروط إلى مجموعة، فإنه يمكنك استخدام عاملين منطقيين:</span><span class="sxs-lookup"><span data-stu-id="11468-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="11468-189">العامل **AND**: يجب استيفاء كلا الشرطين كجزء من عملية التقسيم.</span><span class="sxs-lookup"><span data-stu-id="11468-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="11468-190">يكون هذا الخيار أكثر إفادة عندما تقوم بتعريف الشروط عبر الكيانات المختلفة.</span><span class="sxs-lookup"><span data-stu-id="11468-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="11468-191">العامل **OR**: إما واحدًا من احتياجات الشروط التي يجب استيفائها كجزء من عملية التقسيم.</span><span class="sxs-lookup"><span data-stu-id="11468-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="11468-192">يكون هذا الخيار أكثر إفادة عندما تقوم بتعريف شروط متعددة للكيان نفسه.</span><span class="sxs-lookup"><span data-stu-id="11468-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11468-193">![عامل OR حيث يلزم استيفاء أي من الشرطين](media/segmentation-either-condition.png "عامل OR حيث يلزم استيفاء أي من الشرطين")</span><span class="sxs-lookup"><span data-stu-id="11468-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="11468-194">من الممكن حاليًا إدخال عامل **OR** ضمن عامل **AND**، وليس الطريقة الأخرى.</span><span class="sxs-lookup"><span data-stu-id="11468-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="11468-195">دمج مجموعات متعددة</span><span class="sxs-lookup"><span data-stu-id="11468-195">Combine multiple groups</span></span>

<span data-ttu-id="11468-196">كل مجموعة تنتج مجموعة معينة من العملاء.</span><span class="sxs-lookup"><span data-stu-id="11468-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="11468-197">يمكنك دمج هذه المجموعات لتضمين العملاء المطلوبين لحالة العمل الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="11468-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="11468-198">في رؤى الجمهور ، انتقل إلى صفحة **الشرائح**، وحدد شريحة.</span><span class="sxs-lookup"><span data-stu-id="11468-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="11468-199">حدد **إضافة مجموعة**.</span><span class="sxs-lookup"><span data-stu-id="11468-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11468-200">![مجموعة العميل إضافة مجموعة](media/customer-group-add-group.png "مجموعة العميل إضافة مجموعة")</span><span class="sxs-lookup"><span data-stu-id="11468-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="11468-201">قم بتحديد إحدى عوامل المجموعات التالية: **اتحاد** أو **تقاطع** أو **استثناء**.</span><span class="sxs-lookup"><span data-stu-id="11468-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="11468-202">![مجموعة العميل إضافة اتحاد](media/customer-group-union.png "مجموعة العميل إضافة اتحاد")</span><span class="sxs-lookup"><span data-stu-id="11468-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="11468-203">حدد عامل مجموعة لتحديد مجموعة جديدة.</span><span class="sxs-lookup"><span data-stu-id="11468-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="11468-204">احفظ مجموعات مختلفة التحديد البيانات التي سيتم الاحتفاظ بها:</span><span class="sxs-lookup"><span data-stu-id="11468-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="11468-205">**Union** يوحد المجموعتين.</span><span class="sxs-lookup"><span data-stu-id="11468-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="11468-206">**Intersect** يعمل على تداخل المجموعتين.</span><span class="sxs-lookup"><span data-stu-id="11468-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="11468-207">في المجموعة الموحدة، يتم الاحتفاظ فقط بالبيانات *المشتركة* بين المجموعتين.</span><span class="sxs-lookup"><span data-stu-id="11468-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="11468-208">**باستثناء** يعمل على دمج المجموعتين.</span><span class="sxs-lookup"><span data-stu-id="11468-208">**Except** combines the two groups.</span></span> <span data-ttu-id="11468-209">يتم الاحتفاظ فقط بالبيانات في المجموعة A *غير المشتركة* مع البيانات في المجموعة B.</span><span class="sxs-lookup"><span data-stu-id="11468-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="11468-210">عرض معالجة المحفوظات وأعضاء المقاطع</span><span class="sxs-lookup"><span data-stu-id="11468-210">View processing history and segment members</span></span>

<span data-ttu-id="11468-211">يمكنك الاطلاع على البيانات المدمجة حول مقطع من خلال مراجعة التفاصيل الخاصة بها.</span><span class="sxs-lookup"><span data-stu-id="11468-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="11468-212">في الصفحة **المقاطع**، حدد المقطع الذي تريد مراجعته.</span><span class="sxs-lookup"><span data-stu-id="11468-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="11468-213">يتضمن الجزء العلوي من الصفحة رسم الاتجاه الذي يصور التغييرات في عدد الأعضاء.</span><span class="sxs-lookup"><span data-stu-id="11468-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="11468-214">قم بالمرور فوق نقاط البيانات لعرض عدد الأعضاء في تاريخ محدد.</span><span class="sxs-lookup"><span data-stu-id="11468-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="11468-215">يمكنك تحديث الإطار الزمني للرسوم المرئية.</span><span class="sxs-lookup"><span data-stu-id="11468-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="11468-216">![النطاق الزمني للمقطع](media/segment-time-range.png "النطاق الزمني للمقطع")</span><span class="sxs-lookup"><span data-stu-id="11468-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="11468-217">ويحتوي الجزء السفلي على قائمة تحتوي على أعضاء المقاطع.</span><span class="sxs-lookup"><span data-stu-id="11468-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="11468-218">تعتمد الحقول التي تظهر في هذه القائمة على سمات كيانات المقطع الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="11468-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="11468-219">تعتبر القائمة معاينة لأعضاء المقطع المطابق وعرض أول 100 سجل للمقطع الخاص بك بحيث يمكنك تقييمها بسرعة ومراجعة التعريفات إذا لزم الأمر.</span><span class="sxs-lookup"><span data-stu-id="11468-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="11468-220">لرؤية جميع السجلات المتطابقة، يتعين عليك [تصدير المقطع](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="11468-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="11468-221">مقاطع سريعة</span><span class="sxs-lookup"><span data-stu-id="11468-221">Quick segments</span></span>

<span data-ttu-id="11468-222">بالإضافة إلى منشئ الشرائح، يوجد مسار آخر لإنشاء الشرائح.</span><span class="sxs-lookup"><span data-stu-id="11468-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="11468-223">تتيح لك الشرائح السريعة إنشاء شرائح بسيطة باستخدام عامل تشغيل واحد بسرعة وباستخدام نتائج تحليلات فورية.</span><span class="sxs-lookup"><span data-stu-id="11468-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="11468-224">في الصفحة **المقاطع**، حدد **جديد** > **إنشاء من سريعًا**.</span><span class="sxs-lookup"><span data-stu-id="11468-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="11468-225">حدد الخيار **ملفات التعريف** لإنشاء مقطع يستند إلى كيان العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="11468-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="11468-226">حدد الخيار **المقاييس** لإنشاء مقطع حول كل نوع من سمة العميل للمقاييس التي قمت بإنشاءها مسبقًا في الصفحة **المقاييس**.</span><span class="sxs-lookup"><span data-stu-id="11468-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="11468-227">حدد الخيار **ذكاء** لإنشاء مقطع حول أحد كيانات الإخراج التي قمت بإنشاءها باستخدام إمكانات إما **التنبؤات** أو **نماذج مخصصة**.</span><span class="sxs-lookup"><span data-stu-id="11468-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="11468-228">في مربع الحوار **مقطع سريع جديد**، حدد سمة من القائمة المنسدلة **الحقل**.</span><span class="sxs-lookup"><span data-stu-id="11468-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="11468-229">سيوفر النظام بعض المعلومات الإضافية التي تساعدك في إنشاء مقاطع أفضل للعملاء.</span><span class="sxs-lookup"><span data-stu-id="11468-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="11468-230">بالنسبة لحقول الفئات، سنقوم بإظهار أهم 10 حسابات للعملاء.</span><span class="sxs-lookup"><span data-stu-id="11468-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="11468-231">اختر **القيمة** وحدد **المراجعة**.</span><span class="sxs-lookup"><span data-stu-id="11468-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="11468-232">بالنسبة للسمة الرقمية، سيظهر النظام قيمة السمة التي تقع ضمن كل قيمة مئوية للعميل.</span><span class="sxs-lookup"><span data-stu-id="11468-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="11468-233">اختر **عامل** و **قيمة**، ثم حدد **مراجعة**.</span><span class="sxs-lookup"><span data-stu-id="11468-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="11468-234">سيوفر لك النظام **حجم مقطع مقدر**.</span><span class="sxs-lookup"><span data-stu-id="11468-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="11468-235">يمكنك اختيار إما إنشاء المقطع الذي قمت بتحديده، أو إعادة زيارته أولاً للحصول على حجم قطعة مختلف.</span><span class="sxs-lookup"><span data-stu-id="11468-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="11468-236">![اسم وتقدير مقطع سريع](media/quick-segment-name.png "اسم وتقدير مقطع سريع")</span><span class="sxs-lookup"><span data-stu-id="11468-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="11468-237">أدخل **اسمًا** للمقطع الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="11468-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="11468-238">اختياريًا، أدخل **اسم العرض**.</span><span class="sxs-lookup"><span data-stu-id="11468-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="11468-239">حدد **حفظ** لحفظ المقطع.</span><span class="sxs-lookup"><span data-stu-id="11468-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="11468-240">بعد انتهاء معالجة المقطع، يمكنك عرضه كأي مقطع آخر قمت بإنشائه.</span><span class="sxs-lookup"><span data-stu-id="11468-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="11468-241">بالنسبة للسيناريوهات التالية، فإننا نوصي باستخدام منشئ المقطع بدلاً من إمكانية المقاطع المُوصى بها:</span><span class="sxs-lookup"><span data-stu-id="11468-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="11468-242">إنشاء مقاطع باستخدام عوامل تصفية على حقول الفئة حيث يكون العامل مختلفًا عن العامل **Is**</span><span class="sxs-lookup"><span data-stu-id="11468-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="11468-243">إنشاء مقاطع باستخدام عوامل التصفية حيث يكون العامل مختلفًا عن العامل **Between** و **Greater than** و **Less than**.</span><span class="sxs-lookup"><span data-stu-id="11468-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="11468-244">إنشاء مقاطع باستخدام عوامل تصفية لحقول نوع التاريخ</span><span class="sxs-lookup"><span data-stu-id="11468-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="11468-245">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="11468-245">Next steps</span></span>

<span data-ttu-id="11468-246">[قم بتصدير مقطع](export-destinations.md) واستكشف [بطاقة العميل](customer-card-add-in.md) و [الموصلات](export-power-bi.md) للحصول على معلومات عن مستوى العميل.</span><span class="sxs-lookup"><span data-stu-id="11468-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]