---
title: تصدير البيانات من Customer Insights
description: إدارة عمليات التصدير لمشاركة البيانات.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 28563e3a76535cb0c92bfcda4ef5037430d00cfa
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305462"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="9b730-103">نظرة عامة على عمليات التصدير (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="9b730-103">Exports (preview) overview</span></span>

<span data-ttu-id="9b730-104">تعرض صفحة **عمليات التصدير** كل عمليات التصدير التي تم تكوينها.</span><span class="sxs-lookup"><span data-stu-id="9b730-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="9b730-105">تشترك عمليات التصدير في بيانات محددة مع تطبيقات متعددة.</span><span class="sxs-lookup"><span data-stu-id="9b730-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="9b730-106">يمكن أن تتضمن ملفات تعريف العملاء أو الكيانات، والتخططات، وتفاصيل التعيين.</span><span class="sxs-lookup"><span data-stu-id="9b730-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="9b730-107">تتطلب كل عملية تصدير [اتصالاً، والإعداد بواسطة مسؤول، لإدارة المصادقة والوصول](connections.md).</span><span class="sxs-lookup"><span data-stu-id="9b730-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="9b730-108">انتقل إلى **البيانات** > **عمليات التصدير** لعرض صفحة عمليات التصدير.</span><span class="sxs-lookup"><span data-stu-id="9b730-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="9b730-109">يمكن لجميع أدوار المستخدمين عرض عمليات التصدير المكونة.</span><span class="sxs-lookup"><span data-stu-id="9b730-109">All user roles can view configured exports.</span></span> <span data-ttu-id="9b730-110">استخدم حقل البحث في شريط الأوامر للبحث عن عمليات التصدير حسب اسمها أو اسم الاتصال أو نوع الاتصال بها.</span><span class="sxs-lookup"><span data-stu-id="9b730-110">Use the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="9b730-111">إعداد تصدير جديد </span><span class="sxs-lookup"><span data-stu-id="9b730-111">Set up a new export</span></span>

<span data-ttu-id="9b730-112">لإعداد عملية تصدير أو تحريرها، ستحتاج إلى أن تتوفر لديك اتصالات.</span><span class="sxs-lookup"><span data-stu-id="9b730-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="9b730-113">تعتمد الاتصالات على [دور المستخدم](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="9b730-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="9b730-114">يمكن للمسؤولين الوصول إلى جميع الاتصالات.</span><span class="sxs-lookup"><span data-stu-id="9b730-114">Administrators have access to all connections.</span></span> <span data-ttu-id="9b730-115">كما يمكنهم إنشاء اتصالات جديدة عند إعداد عملية تصدير.</span><span class="sxs-lookup"><span data-stu-id="9b730-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="9b730-116">يمكن أن يكون للمساهمين إمكانية الوصول إلى اتصالات معينة.</span><span class="sxs-lookup"><span data-stu-id="9b730-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="9b730-117">وهي تعتمد على المسؤولين لتكوين الاتصالات ومشاركتها.</span><span class="sxs-lookup"><span data-stu-id="9b730-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="9b730-118">تبيّن قائمة التصدير للمساهمين ما إذا كان بإمكانهم تحرير تصدير أو فقط عرضه في عمود **الأذونات الخاصة بك‬**.</span><span class="sxs-lookup"><span data-stu-id="9b730-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="9b730-119">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9b730-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="9b730-120">يمكن فقط للمشاهدين عرض الصادرات الموجودة ولكن لا يمكنهم إنشائها.</span><span class="sxs-lookup"><span data-stu-id="9b730-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="9b730-121">تعريف تصدير جديد</span><span class="sxs-lookup"><span data-stu-id="9b730-121">Define a new export</span></span>

1. <span data-ttu-id="9b730-122">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="9b730-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9b730-123">لإنشاء تصدير جديد، حدد **إضافة تصدير**.</span><span class="sxs-lookup"><span data-stu-id="9b730-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="9b730-124">في جزء **إعداد التصدير**، حدد الاتصال المراد استخدامه.</span><span class="sxs-lookup"><span data-stu-id="9b730-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="9b730-125">[الاتصالات](connections.md) المدارة بواسطة المسؤولين.</span><span class="sxs-lookup"><span data-stu-id="9b730-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="9b730-126">قم بتقديم التفاصيل المطلوبة وحدد **حفظ** لإنشاء التصدير.</span><span class="sxs-lookup"><span data-stu-id="9b730-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="9b730-127">تعريف تصدير جديد بالاستناد إلى تصدير موجود</span><span class="sxs-lookup"><span data-stu-id="9b730-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="9b730-128">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="9b730-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9b730-129">في قائمة عمليات التصدير، حدد التصدير الذي تريد تكراره.</span><span class="sxs-lookup"><span data-stu-id="9b730-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="9b730-130">حدد **إنشاء تكرار** في شريط الأوامر لفتح الجزء **إعداد تصدير** مع التفاصيل المتعلقة بالتصدير المحدد.</span><span class="sxs-lookup"><span data-stu-id="9b730-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="9b730-131">حدد **حفظ** لإنشاء تصدير جديد، بعد مراجعة التصدير وتكييفه.</span><span class="sxs-lookup"><span data-stu-id="9b730-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="9b730-132">تحرير تصدير</span><span class="sxs-lookup"><span data-stu-id="9b730-132">Edit an export</span></span>

1. <span data-ttu-id="9b730-133">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="9b730-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9b730-134">في قائمة التصديرات، حدد التصدير الذي تريد تحريره.</span><span class="sxs-lookup"><span data-stu-id="9b730-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="9b730-135">في شريط الأوامر، حدد **تحرير**.</span><span class="sxs-lookup"><span data-stu-id="9b730-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="9b730-136">قم بتغيير القيم التي تريد تحديثها وحدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="9b730-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="9b730-137">عرض عمليات التصدير وتفاصيلها</span><span class="sxs-lookup"><span data-stu-id="9b730-137">View exports and export details</span></span>

<span data-ttu-id="9b730-138">بعد إنشاء وجهات التصدير، يتم سردها في **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="9b730-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="9b730-139">يمكن لجميع المستخدمين معرفة البيانات التي تمت مشاركتها وآخر حالة لها.</span><span class="sxs-lookup"><span data-stu-id="9b730-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="9b730-140">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="9b730-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9b730-141">المستخدمون الذين ليس لديهم أذونات بالتحرير، قم بتحديد **طريقة عرض** بدلا من **تحرير** لعرض تفاصيل التصدير.</span><span class="sxs-lookup"><span data-stu-id="9b730-141">Users without edit permissions select **View** instead of **Edit** to see the export details.</span></span>

1. <span data-ttu-id="9b730-142">يعرض الجزء الجانبي تكوين التصدير.</span><span class="sxs-lookup"><span data-stu-id="9b730-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="9b730-143">بدون أذونات التحرير، لا يمكنك تغيير القيم.</span><span class="sxs-lookup"><span data-stu-id="9b730-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="9b730-144">حدد **إغلاق** للعودة إلى صفحة التصدير.</span><span class="sxs-lookup"><span data-stu-id="9b730-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="9b730-145">جدولة التصديرات وتشغيلها</span><span class="sxs-lookup"><span data-stu-id="9b730-145">Schedule and run exports</span></span>

<span data-ttu-id="9b730-146">يحتوي كل تصدير تقوم بتكوينه على جدول تحديث.</span><span class="sxs-lookup"><span data-stu-id="9b730-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="9b730-147">أثناء التحديث، سيبحث النظام عن بيانات جديدة أو محدثة لتضمينها في التصدير.</span><span class="sxs-lookup"><span data-stu-id="9b730-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="9b730-148">بشكل افتراضي، يتم تشغيل عمليات التصدير كجزء من كل [تحديث مجدول للنظام](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9b730-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9b730-149">يمكنك تخصيص جدول التحديث أو إيقاف تشغيله لتشغيل التصديرات يدويًا.</span><span class="sxs-lookup"><span data-stu-id="9b730-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="9b730-150">تتوقف جداول التصدير على حالة بيئتك.</span><span class="sxs-lookup"><span data-stu-id="9b730-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="9b730-151">وفي حالة وجود تحديثات حالية على [التبعيات](system.md#refresh-policies) عند بدء عملية تصدير مجدولة، سيكمل النظام أولا التحديثات ثم يتم تشغيل التصدير.</span><span class="sxs-lookup"><span data-stu-id="9b730-151">If there are updates in progress on [dependencies](system.md#refresh-policies) when a scheduled export should start, the system will first complete the updates and then run the export.</span></span> <span data-ttu-id="9b730-152">يمكنك رؤية آخر مرة تم فيها تحديث تصدير في العمود **تم التحديث**.</span><span class="sxs-lookup"><span data-stu-id="9b730-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="9b730-153">جدولة التصديرات</span><span class="sxs-lookup"><span data-stu-id="9b730-153">Schedule exports</span></span>

<span data-ttu-id="9b730-154">يمكنك تعريف جداول تحديث مخصصة للتصديرات الفردية أو عدة تصديرات مرة واحدة.</span><span class="sxs-lookup"><span data-stu-id="9b730-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="9b730-155">يتم سرد الجدول المحدد حاليًا في عمود **الجدول** لقائمة التصدير.</span><span class="sxs-lookup"><span data-stu-id="9b730-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="9b730-156">إذن تغيير الجدول هو نفسه إذن [تحرير التصديرات وتعريفها](export-destinations.md#set-up-a-new-export)</span><span class="sxs-lookup"><span data-stu-id="9b730-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="9b730-157">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="9b730-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9b730-158">حدد التصدير الذي تريد جدولته.</span><span class="sxs-lookup"><span data-stu-id="9b730-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="9b730-159">حدد **جدولة** في شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="9b730-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="9b730-160">في جزء **جدولة التصدير**، عيّن الخيار **تشغيل الجدول** إلى **تشغيل** لتشغيل التصدير تلقائيًا.</span><span class="sxs-lookup"><span data-stu-id="9b730-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="9b730-161">عيّن هذا الخيار إلى **إيقاف** لتحديثه يدويًا.</span><span class="sxs-lookup"><span data-stu-id="9b730-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="9b730-162">بالنسبة للتصديرات التي يتم تحديثها تلقائيًا، اختر قيمة **تكرار** وحدد تفاصيل لها.</span><span class="sxs-lookup"><span data-stu-id="9b730-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="9b730-163">ينطبق الوقت المحدد على جميع مثيلات التكرار.</span><span class="sxs-lookup"><span data-stu-id="9b730-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="9b730-164">إنه الوقت الذي يجب أن يبدأ فيه تحديث التصدير.</span><span class="sxs-lookup"><span data-stu-id="9b730-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="9b730-165">حدد **حفظ** بعد تطبيق تغييراتك وتنشيطها.</span><span class="sxs-lookup"><span data-stu-id="9b730-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="9b730-166">عند تحرير جدول تصديرات متعددة، يجب عليك إجراء تحديد ضمن **الاحتفاظ بالجداول أو تجاوزها‬**:</span><span class="sxs-lookup"><span data-stu-id="9b730-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="9b730-167">**الاحتفاظ بالجداول الفردية‬**: الإبقاء على الجدول المحدد في وقت سابق للتصديرات المحددة وتعطيلها أو تمكينها فقط.</span><span class="sxs-lookup"><span data-stu-id="9b730-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="9b730-168">**تحديد جدولة جديدة لجميع عمليات التصدير المحددة‬**: تجاوز الجداول الموجودة لعمليات التصدير المحددة.</span><span class="sxs-lookup"><span data-stu-id="9b730-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="9b730-169">تشغيل عمليات التصدير عند الطلب</span><span class="sxs-lookup"><span data-stu-id="9b730-169">Run exports on demand</span></span>

<span data-ttu-id="9b730-170">لتصدير البيانات دون انتظار التحديث المجدول، انتقل إلى **البيانات** > **عمليات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="9b730-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="9b730-171">لتشغيل كافة عمليات التصدير، حدد **تشغيل الكل** في شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="9b730-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="9b730-172">لن يتم تشغيل هذا الإجراء إلا لعمليات التصدير ذات جدول نشط.</span><span class="sxs-lookup"><span data-stu-id="9b730-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="9b730-173">لتشغيل تصدير واحد، حددها في القائمة وحدد **تشغيل** في شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="9b730-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="9b730-174">هذه هي الطريقة التي تقوم من خلالها بتشغيل عمليات تصدير من دون جدول نشط.</span><span class="sxs-lookup"><span data-stu-id="9b730-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="9b730-175">إزالة تصدير</span><span class="sxs-lookup"><span data-stu-id="9b730-175">Remove an Export</span></span>

1. <span data-ttu-id="9b730-176">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="9b730-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9b730-177">حدد التصدير الذي ترغب في إزالته.</span><span class="sxs-lookup"><span data-stu-id="9b730-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="9b730-178">على شريط الأوامر، حدد **إزالة**.</span><span class="sxs-lookup"><span data-stu-id="9b730-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="9b730-179">حدد **إزالة** على شاشة التأكيد لتأكيد الإزالة.</span><span class="sxs-lookup"><span data-stu-id="9b730-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
