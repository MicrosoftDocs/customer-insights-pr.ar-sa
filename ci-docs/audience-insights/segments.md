---
title: الشرائح في معلومات الجمهور
description: نظرة عامة على الشرائح وكيفية إنشائها وإدارتها.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 336cab8619c0b80b7b8a38035cae99620baf2873
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306241"
---
# <a name="segments-overview"></a><span data-ttu-id="127b1-103">نظرة عامة على الشرائح</span><span class="sxs-lookup"><span data-stu-id="127b1-103">Segments overview</span></span>

<span data-ttu-id="127b1-104">تتيح لك الشرائح تجميع العملاء وفقًا للسمات المتعلقة بالبيانات السكانية أو المعاملات أو السلوكيات.</span><span class="sxs-lookup"><span data-stu-id="127b1-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="127b1-105">يمكنك استخدام الشرائح لاستهداف الحملات الترويجية وأنشطة المبيعات وإجراءات دعم العملاء لتحقيق أهداف العمل الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="127b1-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="127b1-106">يتم الإشارة إلى ملفات تعريف العميل التي تطابق عوامل تصفية تعريف الشرائح *كأعضاء* في شريحة.</span><span class="sxs-lookup"><span data-stu-id="127b1-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="127b1-107">تنطبق بعض [قيود الخدمة](service-limits.md) apply.</span><span class="sxs-lookup"><span data-stu-id="127b1-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="127b1-108">إنشاء مقطع جديد</span><span class="sxs-lookup"><span data-stu-id="127b1-108">Create a new segment</span></span>

<span data-ttu-id="127b1-109">هناك العديد من الطرق لإنشاء شريحة جديدة:</span><span class="sxs-lookup"><span data-stu-id="127b1-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="127b1-110">شريحة معقدة باستخدام منشئ الشرائح: [شريحة فارغة](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="127b1-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="127b1-111">شرائح بسيطة بمشغل واحد: [شريحة سريعة](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="127b1-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="127b1-112">طريقة مدعومة بالذكاء الاصطناعي للعثور على عملاء مشابهين: [عملاء مشابهون](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="127b1-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="127b1-113">اقتراحات مدعومة بالذكاء الاصطناعي تستند إلى قياسات أو سمات: [الشرائح المقترحة لتحسين القياسات](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="127b1-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="127b1-114">الاقتراحات المستندة إلى الأنشطة: [الشرائح المقترحة استنادا إلى نشاط العميل](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="127b1-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="127b1-115">إدارة المقاطع الموجودة</span><span class="sxs-lookup"><span data-stu-id="127b1-115">Manage existing segments</span></span>

<span data-ttu-id="127b1-116">انتقل إلى صفحة **الشرائح** لعرض كافة الشرائح المحفوظة وإدارتها.</span><span class="sxs-lookup"><span data-stu-id="127b1-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="127b1-117">يتم تمثيل كل شريحة بصف يشتمل على معلومات إضافية حول الشريحة.</span><span class="sxs-lookup"><span data-stu-id="127b1-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="شريحة محددة مع قائمة خيارات منسدلة وخيارات متوفرة.":::

<span data-ttu-id="127b1-119">تتوفر الإجراءات التالية عند تحديد أحد الأجزاء:</span><span class="sxs-lookup"><span data-stu-id="127b1-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="127b1-120">**اعرض** تفاصيل المقطع، بما في ذلك معاينة اتجاه عدد الأعضاء لأعضاء المقطع.</span><span class="sxs-lookup"><span data-stu-id="127b1-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="127b1-121">**قم بتحرير** المقطع لتغيير خصائصه.</span><span class="sxs-lookup"><span data-stu-id="127b1-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="127b1-122">**أنشئ تكرارًا** لشريحة.</span><span class="sxs-lookup"><span data-stu-id="127b1-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="127b1-123">يمكنك اختيار تحرير خصائصها على الفور أو حفظ التكرار فقط.</span><span class="sxs-lookup"><span data-stu-id="127b1-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="127b1-124">**قم بتحديث** المقطع ليتضمن أحدث البيانات.</span><span class="sxs-lookup"><span data-stu-id="127b1-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="127b1-125">**قم بتنشيط** أو **إلغاء تنشيط** المقطع.</span><span class="sxs-lookup"><span data-stu-id="127b1-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="127b1-126">تحتوي الشرائح على حالتين محتملتين - نشطة أو غير نشطة.</span><span class="sxs-lookup"><span data-stu-id="127b1-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="127b1-127">تتوفر هذه الحالات في متناول عند تحرير مقطع.</span><span class="sxs-lookup"><span data-stu-id="127b1-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="127b1-128">بالنسبة للقطاعات غير النشطة ، يكون تعريف الشريحة موجودا ، ولكنه لا يحتوي علي اي عملاء حتى الآن.</span><span class="sxs-lookup"><span data-stu-id="127b1-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="127b1-129">عند تنشيط المقطع ، تتغير الحالة الخاصة به من "غير نشط" إلى "نشط" وتبدا في البحث عن العملاء الذين يتطابقون مع تعريف الشريحة.</span><span class="sxs-lookup"><span data-stu-id="127b1-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="127b1-130">إذا تم تكوين [تحديث مجدول](system.md#schedule-tab)، تم تسجيل **الحالة** كـ **تم التخطي** للشرائح غير النشطة، مما يشير إلى أنه لم تتم محاولة التحديث.</span><span class="sxs-lookup"><span data-stu-id="127b1-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="127b1-131">وعند تنشيط جزء غير نشط ، فانه سيتم تحديثه سيتم تضمينه في التحديثات المجدولة.</span><span class="sxs-lookup"><span data-stu-id="127b1-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="127b1-132">بدلاً من ذلك، يمكنك استخدام الوظيفة **الجدولة لاحقًا** في القائمة المنسدلة **تنشيط/إلغاء التنشيط** لتحديد التاريخ والوقت المستقبليين لعملية تنشيط وإلغاء تنشيط شريحة معينة.</span><span class="sxs-lookup"><span data-stu-id="127b1-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="127b1-133">**أعد تسمية** المقطع.</span><span class="sxs-lookup"><span data-stu-id="127b1-133">**Rename** the segment.</span></span>
- <span data-ttu-id="127b1-134">**قم بتنزيل** قائمة الأعضاء كملف بتنسيق CSV.</span><span class="sxs-lookup"><span data-stu-id="127b1-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="127b1-135">**إدارة عمليات التصدير** لرؤية عمليات التصدير ذات الصلة بالشرائح وإدارتها.</span><span class="sxs-lookup"><span data-stu-id="127b1-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="127b1-136">اعرف المزيد حول عمليات التصدير</span><span class="sxs-lookup"><span data-stu-id="127b1-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="127b1-137">**احذف** المقطع.</span><span class="sxs-lookup"><span data-stu-id="127b1-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="127b1-138">تحديث الشرائح</span><span class="sxs-lookup"><span data-stu-id="127b1-138">Refresh segments</span></span>

<span data-ttu-id="127b1-139">يمكنك تحديث كل الشرائح مرة واحدة من خلال تحديد **تحديث الكل** في صفحة **الشرائح** أو يمكنك تحديث شريحة واحدة أو عدة شرائح عندما تقوم بتحديدها واختيار **تحديث** من الخيارات.</span><span class="sxs-lookup"><span data-stu-id="127b1-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="127b1-140">وبدلاً من ذلك، يمكنك تكوين تحديث متكرر في **المسؤول** > **النظام** > **جدولة**.</span><span class="sxs-lookup"><span data-stu-id="127b1-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="127b1-141">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="127b1-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="127b1-142">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="127b1-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="127b1-143">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="127b1-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="127b1-144">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="127b1-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="127b1-145">شرائح التصدير</span><span class="sxs-lookup"><span data-stu-id="127b1-145">Export segments</span></span>

<span data-ttu-id="127b1-146">يمكنك تصدير شريحة من صفحة الشرائح أو [صفحة عمليات التصدير](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="127b1-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="127b1-147">انتقل إلى الصفحة **مقاطع**.</span><span class="sxs-lookup"><span data-stu-id="127b1-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="127b1-148">حدد **إظهار المزيد [...]** للشريحة التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="127b1-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="127b1-149">حدد **إدارة عمليات التصدير** من قائمة الإجراءات المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="127b1-149">Select **Manage exports** from the actions dropdown list.</span></span>

1. <span data-ttu-id="127b1-150">تفتح الصفحة **عمليات التصدير (إصدار أولي) للشريحة**.</span><span class="sxs-lookup"><span data-stu-id="127b1-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="127b1-151">يمكنك رؤية جميع عمليات التصدير المكونة وقد تم تجميعها حسب عمليات التصدير التي تحتوي على الشريحة الحالية أو لا تحتوي عليها.</span><span class="sxs-lookup"><span data-stu-id="127b1-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="127b1-152">لإضافة الشريحة المحددة إلى تصدير، حدد التصدير في القائمة وحدد **إضافة شريحة**.</span><span class="sxs-lookup"><span data-stu-id="127b1-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="127b1-153">لإنشاء تصدير جديد باستخدام الشريحة المحددة، حدد **إضافة تصدير**.</span><span class="sxs-lookup"><span data-stu-id="127b1-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="127b1-154">لمزيد من المعلومات حول إنشاء عمليات تصدير، راجع [إعداد تصدير جديد](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="127b1-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="127b1-155">حدد **السابق** للعودة إلى الصفحة الرئيسية للشرائح.</span><span class="sxs-lookup"><span data-stu-id="127b1-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="127b1-156">عرض معالجة المحفوظات وأعضاء المقاطع</span><span class="sxs-lookup"><span data-stu-id="127b1-156">View processing history and segment members</span></span>

<span data-ttu-id="127b1-157">يمكنك الاطلاع على البيانات المدمجة حول مقطع من خلال مراجعة التفاصيل الخاصة بها.</span><span class="sxs-lookup"><span data-stu-id="127b1-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="127b1-158">في الصفحة **المقاطع**، حدد المقطع الذي تريد مراجعته.</span><span class="sxs-lookup"><span data-stu-id="127b1-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="127b1-159">يتضمن الجزء العلوي من الصفحة رسم الاتجاه الذي يصور التغييرات في عدد الأعضاء.</span><span class="sxs-lookup"><span data-stu-id="127b1-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="127b1-160">قم بالمرور فوق نقاط البيانات لعرض عدد الأعضاء في تاريخ محدد.</span><span class="sxs-lookup"><span data-stu-id="127b1-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="127b1-161">يمكنك تحديث الإطار الزمني للرسوم المرئية.</span><span class="sxs-lookup"><span data-stu-id="127b1-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="127b1-162">![النطاق الزمني للمقطع](media/segment-time-range.png "النطاق الزمني للمقطع")</span><span class="sxs-lookup"><span data-stu-id="127b1-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="127b1-163">ويحتوي الجزء السفلي على قائمة تحتوي على أعضاء المقاطع.</span><span class="sxs-lookup"><span data-stu-id="127b1-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="127b1-164">تعتمد الحقول التي تظهر في هذه القائمة على سمات كيانات المقطع الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="127b1-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="127b1-165">تعتبر القائمة معاينة لأعضاء المقطع المطابق وعرض أول 100 سجل للمقطع الخاص بك بحيث يمكنك تقييمها بسرعة ومراجعة التعريفات إذا لزم الأمر.</span><span class="sxs-lookup"><span data-stu-id="127b1-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="127b1-166">لرؤية جميع السجلات المتطابقة، يتعين عليك [تصدير المقطع](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="127b1-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
