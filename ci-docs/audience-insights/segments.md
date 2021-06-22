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
ms.openlocfilehash: 6cb7bd62bf0f61e6dc5811b20e5011e4a086c743
ms.sourcegitcommit: 84283d523a891298fca8aaf629d9f9ab2a1bc067
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/27/2021
ms.locfileid: "6111371"
---
# <a name="segments-overview"></a><span data-ttu-id="60178-103">نظرة عامة على الشرائح</span><span class="sxs-lookup"><span data-stu-id="60178-103">Segments overview</span></span>

<span data-ttu-id="60178-104">تتيح لك الشرائح تجميع العملاء وفقًا للسمات المتعلقة بالبيانات السكانية أو المعاملات أو السلوكيات.</span><span class="sxs-lookup"><span data-stu-id="60178-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="60178-105">يمكنك استخدام الشرائح لاستهداف الحملات الترويجية وأنشطة المبيعات وإجراءات دعم العملاء لتحقيق أهداف العمل الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="60178-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="60178-106">يتم الإشارة إلى ملفات تعريف العميل التي تطابق عوامل تصفية تعريف الشرائح *كأعضاء* في شريحة.</span><span class="sxs-lookup"><span data-stu-id="60178-106">Customer profiles that match the filters of a segment definition are referred as *members* of a segment.</span></span> <span data-ttu-id="60178-107">تنطبق بعض [قيود الخدمة](service-limits.md) apply.</span><span class="sxs-lookup"><span data-stu-id="60178-107">Some [service limits](service-limits.md) apply.</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="60178-108">إنشاء مقطع جديد</span><span class="sxs-lookup"><span data-stu-id="60178-108">Create a new segment</span></span>

<span data-ttu-id="60178-109">هناك العديد من الطرق لإنشاء شريحة جديدة:</span><span class="sxs-lookup"><span data-stu-id="60178-109">There are multiple ways to create a new segment:</span></span> 

- <span data-ttu-id="60178-110">شريحة معقدة باستخدام منشئ الشرائح: [شريحة فارغة](segment-builder.md#create-a-new-segment)</span><span class="sxs-lookup"><span data-stu-id="60178-110">Complex segment with segment builder: [Blank segment](segment-builder.md#create-a-new-segment)</span></span>
- <span data-ttu-id="60178-111">شرائح بسيطة بمشغل واحد: [شريحة سريعة](segment-builder.md#quick-segments)</span><span class="sxs-lookup"><span data-stu-id="60178-111">Simple segments with one operator: [Quick segment](segment-builder.md#quick-segments)</span></span>
- <span data-ttu-id="60178-112">طريقة مدعومة بالذكاء الاصطناعي للعثور على عملاء مشابهين: [عملاء مشابهون](find-similar-customer-segments.md)</span><span class="sxs-lookup"><span data-stu-id="60178-112">AI-powered way to find similar customers: [Similar Customers](find-similar-customer-segments.md)</span></span>
- <span data-ttu-id="60178-113">اقتراحات مدعومة بالذكاء الاصطناعي تستند إلى قياسات أو سمات: [الشرائح المقترحة لتحسين القياسات](suggested-segments.md)</span><span class="sxs-lookup"><span data-stu-id="60178-113">AI-powered suggestions based on measures or attributes: [Suggested segments to improve measures](suggested-segments.md)</span></span>
- <span data-ttu-id="60178-114">الاقتراحات المستندة إلى الأنشطة: [الشرائح المقترحة استنادا إلى نشاط العميل](suggested-segments-activity.md)</span><span class="sxs-lookup"><span data-stu-id="60178-114">Suggestions based on activities: [Suggested segments based on customer activity](suggested-segments-activity.md)</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="60178-115">إدارة المقاطع الموجودة</span><span class="sxs-lookup"><span data-stu-id="60178-115">Manage existing segments</span></span>

<span data-ttu-id="60178-116">انتقل إلى صفحة **الشرائح** لعرض كافة الشرائح المحفوظة وإدارتها.</span><span class="sxs-lookup"><span data-stu-id="60178-116">Go to the **Segments** page, to view all your saved segments and manage them.</span></span>

<span data-ttu-id="60178-117">يتم تمثيل كل شريحة بصف يشتمل على معلومات إضافية حول الشريحة.</span><span class="sxs-lookup"><span data-stu-id="60178-117">Each segment is represented by a row that includes additional information about the segment.</span></span>

:::image type="content" source="media/segments-selected-segment.png" alt-text="شريحة محددة مع قائمة منسدلة للخيارات والخيارات المتاحة.":::

<span data-ttu-id="60178-119">تتوفر الإجراءات التالية عند تحديد أحد الأجزاء:</span><span class="sxs-lookup"><span data-stu-id="60178-119">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="60178-120">**اعرض** تفاصيل المقطع، بما في ذلك معاينة اتجاه عدد الأعضاء لأعضاء المقطع.</span><span class="sxs-lookup"><span data-stu-id="60178-120">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="60178-121">**قم بتحرير** المقطع لتغيير خصائصه.</span><span class="sxs-lookup"><span data-stu-id="60178-121">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="60178-122">**أنشئ تكرارًا** لشريحة.</span><span class="sxs-lookup"><span data-stu-id="60178-122">**Create duplicate** of a segment.</span></span> <span data-ttu-id="60178-123">يمكنك اختيار تحرير خصائصها على الفور أو حفظ التكرار فقط.</span><span class="sxs-lookup"><span data-stu-id="60178-123">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="60178-124">**قم بتحديث** المقطع ليتضمن أحدث البيانات.</span><span class="sxs-lookup"><span data-stu-id="60178-124">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="60178-125">**قم بتنشيط** أو **إلغاء تنشيط** المقطع.</span><span class="sxs-lookup"><span data-stu-id="60178-125">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="60178-126">تحتوي الشرائح على حالتين محتملتين - نشطة أو غير نشطة.</span><span class="sxs-lookup"><span data-stu-id="60178-126">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="60178-127">تتوفر هذه الحالات في متناول عند تحرير مقطع.</span><span class="sxs-lookup"><span data-stu-id="60178-127">These states come in handy when editing a segment.</span></span> <span data-ttu-id="60178-128">بالنسبة للقطاعات غير النشطة ، يكون تعريف الشريحة موجودا ، ولكنه لا يحتوي علي اي عملاء حتى الآن.</span><span class="sxs-lookup"><span data-stu-id="60178-128">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="60178-129">عند تنشيط المقطع ، تتغير الحالة الخاصة به من "غير نشط" إلى "نشط" وتبدا في البحث عن العملاء الذين يتطابقون مع تعريف الشريحة.</span><span class="sxs-lookup"><span data-stu-id="60178-129">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="60178-130">إذا تم تكوين [تحديث مجدول](system.md#schedule-tab)، تم تسجيل **الحالة** كـ **تم التخطي** للشرائح غير النشطة، مما يشير إلى أنه لم تتم محاولة التحديث.</span><span class="sxs-lookup"><span data-stu-id="60178-130">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="60178-131">وعند تنشيط جزء غير نشط ، فانه سيتم تحديثه سيتم تضمينه في التحديثات المجدولة.</span><span class="sxs-lookup"><span data-stu-id="60178-131">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="60178-132">بدلاً من ذلك، يمكنك استخدام الوظيفة **الجدولة لاحقًا** في القائمة المنسدلة **تنشيط/إلغاء التنشيط** لتحديد التاريخ والوقت المستقبليين لعملية تنشيط وإلغاء تنشيط شريحة معينة.</span><span class="sxs-lookup"><span data-stu-id="60178-132">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="60178-133">**أعد تسمية** المقطع.</span><span class="sxs-lookup"><span data-stu-id="60178-133">**Rename** the segment.</span></span>
- <span data-ttu-id="60178-134">**قم بتنزيل** قائمة الأعضاء كملف بتنسيق CSV.</span><span class="sxs-lookup"><span data-stu-id="60178-134">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="60178-135">**إدارة عمليات التصدير** لرؤية عمليات التصدير ذات الصلة بالشرائح وإدارتها.</span><span class="sxs-lookup"><span data-stu-id="60178-135">**Manage exports** to see exports related segment and manage them.</span></span> [<span data-ttu-id="60178-136">اعرف المزيد حول عمليات التصدير</span><span class="sxs-lookup"><span data-stu-id="60178-136">Learn more about exports.</span></span>](export-destinations.md)
- <span data-ttu-id="60178-137">**احذف** المقطع.</span><span class="sxs-lookup"><span data-stu-id="60178-137">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="60178-138">تحديث الشرائح</span><span class="sxs-lookup"><span data-stu-id="60178-138">Refresh segments</span></span>

<span data-ttu-id="60178-139">يمكنك تحديث كل الشرائح مرة واحدة من خلال تحديد **تحديث الكل** في صفحة **الشرائح** أو يمكنك تحديث شريحة واحدة أو عدة شرائح عندما تقوم بتحديدها واختيار **تحديث** من الخيارات.</span><span class="sxs-lookup"><span data-stu-id="60178-139">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="60178-140">وبدلاً من ذلك، يمكنك تكوين تحديث متكرر في **المسؤول** > **النظام** > **جدولة**.</span><span class="sxs-lookup"><span data-stu-id="60178-140">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="60178-141">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="60178-141">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="60178-142">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="60178-142">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="60178-143">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="60178-143">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="60178-144">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="60178-144">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="export-segments"></a><span data-ttu-id="60178-145">شرائح التصدير</span><span class="sxs-lookup"><span data-stu-id="60178-145">Export segments</span></span>

<span data-ttu-id="60178-146">يمكنك تصدير شريحة من صفحة الشرائح أو [صفحة عمليات التصدير](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="60178-146">You can export a segment from the segments page or the [exports page](export-destinations.md).</span></span> 

1. <span data-ttu-id="60178-147">انتقل إلى الصفحة **مقاطع**.</span><span class="sxs-lookup"><span data-stu-id="60178-147">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="60178-148">حدد **إظهار المزيد [...]** للشريحة التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="60178-148">Select **Show more [...]** for the segment you want to export.</span></span>

1. <span data-ttu-id="60178-149">حدد **إدارة عمليات التصدير** من القائمة المنسدلة للإجراءات.</span><span class="sxs-lookup"><span data-stu-id="60178-149">Select **Manage exports** from the actions drop-down list.</span></span>

1. <span data-ttu-id="60178-150">تفتح الصفحة **عمليات التصدير (إصدار أولي) للشريحة**.</span><span class="sxs-lookup"><span data-stu-id="60178-150">The page **Exports (preview) for segment** opens.</span></span> <span data-ttu-id="60178-151">يمكنك رؤية جميع عمليات التصدير المكونة وقد تم تجميعها حسب عمليات التصدير التي تحتوي على الشريحة الحالية أو لا تحتوي عليها.</span><span class="sxs-lookup"><span data-stu-id="60178-151">You can see all configured exports grouped by by exports that contain the current segment or don't contain it.</span></span>

   1. <span data-ttu-id="60178-152">لإضافة الشريحة المحددة إلى تصدير، حدد التصدير في القائمة وحدد **إضافة شريحة**.</span><span class="sxs-lookup"><span data-stu-id="60178-152">To add the selected segment to an export, select the export in the list and select **Add segment**.</span></span>

   1. <span data-ttu-id="60178-153">لإنشاء تصدير جديد باستخدام الشريحة المحددة، حدد **إضافة تصدير**.</span><span class="sxs-lookup"><span data-stu-id="60178-153">To create a new export with the selected segment, select **Add export**.</span></span> <span data-ttu-id="60178-154">لمزيد من المعلومات حول إنشاء عمليات تصدير، راجع [إعداد تصدير جديد](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="60178-154">For more information about creating exports, see [Set up a new export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="60178-155">حدد **السابق** للعودة إلى الصفحة الرئيسية للشرائح.</span><span class="sxs-lookup"><span data-stu-id="60178-155">Select **Back** to return to the main page for segments.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="60178-156">عرض معالجة المحفوظات وأعضاء المقاطع</span><span class="sxs-lookup"><span data-stu-id="60178-156">View processing history and segment members</span></span>

<span data-ttu-id="60178-157">يمكنك الاطلاع على البيانات المدمجة حول مقطع من خلال مراجعة التفاصيل الخاصة بها.</span><span class="sxs-lookup"><span data-stu-id="60178-157">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="60178-158">في الصفحة **المقاطع**، حدد المقطع الذي تريد مراجعته.</span><span class="sxs-lookup"><span data-stu-id="60178-158">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="60178-159">يتضمن الجزء العلوي من الصفحة رسم الاتجاه الذي يصور التغييرات في عدد الأعضاء.</span><span class="sxs-lookup"><span data-stu-id="60178-159">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="60178-160">قم بالمرور فوق نقاط البيانات لعرض عدد الأعضاء في تاريخ محدد.</span><span class="sxs-lookup"><span data-stu-id="60178-160">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="60178-161">يمكنك تحديث الإطار الزمني للرسوم المرئية.</span><span class="sxs-lookup"><span data-stu-id="60178-161">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="60178-162">![النطاق الزمني للمقطع](media/segment-time-range.png "النطاق الزمني للمقطع")</span><span class="sxs-lookup"><span data-stu-id="60178-162">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="60178-163">ويحتوي الجزء السفلي على قائمة تحتوي على أعضاء المقاطع.</span><span class="sxs-lookup"><span data-stu-id="60178-163">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="60178-164">تعتمد الحقول التي تظهر في هذه القائمة على سمات كيانات المقطع الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="60178-164">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="60178-165">تعتبر القائمة معاينة لأعضاء المقطع المطابق وعرض أول 100 سجل للمقطع الخاص بك بحيث يمكنك تقييمها بسرعة ومراجعة التعريفات إذا لزم الأمر.</span><span class="sxs-lookup"><span data-stu-id="60178-165">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="60178-166">لرؤية جميع السجلات المتطابقة، يتعين عليك [تصدير المقطع](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="60178-166">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)] 
