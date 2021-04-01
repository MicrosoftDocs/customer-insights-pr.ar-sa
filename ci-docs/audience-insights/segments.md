---
title: إنشاء شرائج وإدارتها
description: قم بإنشاء شرائح العملاء لتجميعهم استنادًا إلى العديد من السمات.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597035"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="f3ead-103">إنشاء مقاطع وإدارتها</span><span class="sxs-lookup"><span data-stu-id="f3ead-103">Create and manage segments</span></span>

<span data-ttu-id="f3ead-104">تتيح لك الشرائح تجميع العملاء وفقًا للسمات المتعلقة بالبيانات السكانية أو المعاملات أو السلوكيات.</span><span class="sxs-lookup"><span data-stu-id="f3ead-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="f3ead-105">يمكنك استخدام الشرائح لاستهداف الحملات الترويجية وأنشطة المبيعات وإجراءات دعم العملاء لتحقيق أهداف العمل الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="f3ead-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="f3ead-106">يمكنك تعريف عوامل تصفية معقدة حول كيان ملف تعريف العميل والكيانات المرتبطة به.</span><span class="sxs-lookup"><span data-stu-id="f3ead-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="f3ead-107">تعمل كل شريحة، بعد المعالجة، على إنشاء مجموعة من سجلات العملاء التي يمكنك تصديرها وتنفيذ إجراء عليها.</span><span class="sxs-lookup"><span data-stu-id="f3ead-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="f3ead-108">تنطبق بعض [قيود الخدمة](service-limits.md) apply.</span><span class="sxs-lookup"><span data-stu-id="f3ead-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="f3ead-109">الشرائح كلها هي **شرائح ديناميكية** يتم تحديثها وفق جدول متكرر، ما لم يتم ذكر عكس ذلك.</span><span class="sxs-lookup"><span data-stu-id="f3ead-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="f3ead-110">يوضح المثال التالي قدرة التقسيم إلى شرائح.</span><span class="sxs-lookup"><span data-stu-id="f3ead-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="f3ead-111">لقد قمنا بتحديد مقطع العملاء الذين قاموا بطلب بضائع بمبلغ 500 دولار أمريكي على الأقل في 90 يومًا الأخيرة *و* الذين تم تضمينهم في مكالمة خدمة العملاء التي تم تصعيدها.</span><span class="sxs-lookup"><span data-stu-id="f3ead-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f3ead-112">![مجموعات متعددة](media/segmentation-group1-2.png "مجموعات متعددة")</span><span class="sxs-lookup"><span data-stu-id="f3ead-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="f3ead-113">إنشاء مقطع جديد</span><span class="sxs-lookup"><span data-stu-id="f3ead-113">Create a new segment</span></span>

<span data-ttu-id="f3ead-114">تُدار الشرائح في صفحة **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="f3ead-115">في رؤى الجمهور، انتقل إلى صفحة **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="f3ead-116">حدد **جديد** > **مقطع فارغ**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="f3ead-117">في جزء **المقطع الجديد**، اختر نوع المقطع وأطلق عليه **اسمًا**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="f3ead-118">اختياريًا، أطلق اسم عرض ووصف يساعدك على تعريف المقطع.</span><span class="sxs-lookup"><span data-stu-id="f3ead-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="f3ead-119">حدد **التالي** للوصول إلى الصفحة **مُنشئ المقطع** حيث يمكنك تعريف مجموعة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="f3ead-120">المجموعة هي مجموعة من العملاء.</span><span class="sxs-lookup"><span data-stu-id="f3ead-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="f3ead-121">اختر الكيان الذي يتضمن السمة التي تريد وضع المقطع بها.</span><span class="sxs-lookup"><span data-stu-id="f3ead-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="f3ead-122">اختر السمة المراد التقسيم وفقًا لها.</span><span class="sxs-lookup"><span data-stu-id="f3ead-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="f3ead-123">يمكن أن تحتوي هذه السمة على نوع واحد من أنواع القيم الأربعة: رقمي أو سلسلة أو تاريخ أو منطقي.</span><span class="sxs-lookup"><span data-stu-id="f3ead-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="f3ead-124">اختر عامل وقيمة للسمة المحددة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f3ead-125">![عامل تصفية مخصص للمجموعة](media/customer-group-numbers.png "عامل تصفية مجموعة العميل")</span><span class="sxs-lookup"><span data-stu-id="f3ead-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="f3ead-126">الرقم</span><span class="sxs-lookup"><span data-stu-id="f3ead-126">Number</span></span> |<span data-ttu-id="f3ead-127">تعريف</span><span class="sxs-lookup"><span data-stu-id="f3ead-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="f3ead-128">1</span><span class="sxs-lookup"><span data-stu-id="f3ead-128">1</span></span>     |<span data-ttu-id="f3ead-129">Entity</span><span class="sxs-lookup"><span data-stu-id="f3ead-129">Entity</span></span>          |
   |<span data-ttu-id="f3ead-130">2</span><span class="sxs-lookup"><span data-stu-id="f3ead-130">2</span></span>     |<span data-ttu-id="f3ead-131">السمة</span><span class="sxs-lookup"><span data-stu-id="f3ead-131">Attribute</span></span>          |
   |<span data-ttu-id="f3ead-132">3</span><span class="sxs-lookup"><span data-stu-id="f3ead-132">3</span></span>    |<span data-ttu-id="f3ead-133">عامل</span><span class="sxs-lookup"><span data-stu-id="f3ead-133">Operator</span></span>         |
   |<span data-ttu-id="f3ead-134">4</span><span class="sxs-lookup"><span data-stu-id="f3ead-134">4</span></span>    |<span data-ttu-id="f3ead-135">قيمة</span><span class="sxs-lookup"><span data-stu-id="f3ead-135">Value</span></span>         |

8. <span data-ttu-id="f3ead-136">إذا كان الكيان متصلاً بكيان عميل موحد من خلال [العلاقات](relationships.md)، ستحتاج إلى تحديد مسار العلاقة لإنشاء مقطع صالح.</span><span class="sxs-lookup"><span data-stu-id="f3ead-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="f3ead-137">قم بإضافة الكيانات من مسار العلاقة حتى يمكنك تحديد الكيان **العميل: CustomerInsights** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="f3ead-138">ثم، اختر **كافة السجلات** لكل شرط.</span><span class="sxs-lookup"><span data-stu-id="f3ead-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f3ead-139">![مسار العلاقة أثناء إنشاء المقطع](media/segments-multiple-relationships.png "مسار العلاقة أثناء إنشاء المقطع")</span><span class="sxs-lookup"><span data-stu-id="f3ead-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="f3ead-140">بشكل افتراضي، تنشئ الشرائح كيان إخراج يحتوي على كافة سمات ملفات تعريف العملاء التي تطابق عوامل التصفية المعرّفة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="f3ead-141">إذا كانت شريحة تستند إلى كيانات أخرى غير كيان *العميل*، فيمكنك إضافة المزيد من السمات من هذه الكيانات إلى كيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="f3ead-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="f3ead-142">حدد **سمات المشروع** لاختيار السمات التي سيتم إلحاقها بكيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="f3ead-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="f3ead-143">مثال: تستند شريحة إلى كيان يحتوي على بيانات نشاط العميل المرتبطة بكيان *العميل*.</span><span class="sxs-lookup"><span data-stu-id="f3ead-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="f3ead-144">تبحث الشريحة عن جميع العملاء الذين اتصلوا بمكتب المساعدة في آخر 60 يومًا.</span><span class="sxs-lookup"><span data-stu-id="f3ead-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="f3ead-145">يمكنك اختيار إلحاق مدة المكالمة وعدد المكالمات بجميع سجلات العملاء المتطابقة في كيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="f3ead-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="f3ead-146">قد تكون هذه المعلومات مفيدة لإرسال بريد إلكتروني يتضمن ارتباطات مفيدة إلى مقالات المساعدة عبر الإنترنت والأسئلة المتداولة للعملاء الذين اتصلوا بشكل متكرر.</span><span class="sxs-lookup"><span data-stu-id="f3ead-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="f3ead-147">حدد **حفظ** لحفظ المقطع.</span><span class="sxs-lookup"><span data-stu-id="f3ead-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="f3ead-148">سيتم حفظ المقطع الخاص بك ومعالجته في حالة التحقق من صحة كافة المتطلبات.</span><span class="sxs-lookup"><span data-stu-id="f3ead-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="f3ead-149">وإلا، سيتم حفظه كمسودة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="f3ead-150">قم بتحديد **رجوع إلى الشرائح** للعودة إلى صفحة **المقاطع**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="f3ead-151">إدارة المقاطع الموجودة</span><span class="sxs-lookup"><span data-stu-id="f3ead-151">Manage existing segments</span></span>

<span data-ttu-id="f3ead-152">في صفحة **المقاطع**، يمكنك عرض كافة المقاطع التي قمت بحفظها وإدارتها.</span><span class="sxs-lookup"><span data-stu-id="f3ead-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="f3ead-153">يتم تمثيل كل شريحة بصف يشتمل على معلومات إضافية حول الشريحة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="f3ead-154">يمكنك فرز الأجزاء في عمود من خلال تحديد عنوان العمود.</span><span class="sxs-lookup"><span data-stu-id="f3ead-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="f3ead-155">استخدم مربع **البحث** في الزاوية العليا اليمني لتصفية الشرائح.</span><span class="sxs-lookup"><span data-stu-id="f3ead-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f3ead-156">![خيارات إدارة مقطع حالي](media/segments-selected-segment.png "خيارات إدارة مقطع حالي")</span><span class="sxs-lookup"><span data-stu-id="f3ead-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="f3ead-157">تتوفر الإجراءات التالية عند تحديد أحد الأجزاء:</span><span class="sxs-lookup"><span data-stu-id="f3ead-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="f3ead-158">**اعرض** تفاصيل المقطع، بما في ذلك معاينة اتجاه عدد الأعضاء لأعضاء المقطع.</span><span class="sxs-lookup"><span data-stu-id="f3ead-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="f3ead-159">**قم بتحرير** المقطع لتغيير خصائصه.</span><span class="sxs-lookup"><span data-stu-id="f3ead-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="f3ead-160">**أنشئ تكرارًا** لشريحة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="f3ead-161">يمكنك اختيار تحرير خصائصها على الفور أو حفظ التكرار فقط.</span><span class="sxs-lookup"><span data-stu-id="f3ead-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="f3ead-162">**قم بتحديث** المقطع ليتضمن أحدث البيانات.</span><span class="sxs-lookup"><span data-stu-id="f3ead-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="f3ead-163">**قم بتنشيط** أو **إلغاء تنشيط** المقطع.</span><span class="sxs-lookup"><span data-stu-id="f3ead-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="f3ead-164">تحتوي الشرائح على حالتين محتملتين - نشطة أو غير نشطة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="f3ead-165">تتوفر هذه الحالات في متناول عند تحرير مقطع.</span><span class="sxs-lookup"><span data-stu-id="f3ead-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="f3ead-166">بالنسبة للقطاعات غير النشطة ، يكون تعريف الشريحة موجودا ، ولكنه لا يحتوي علي اي عملاء حتى الآن.</span><span class="sxs-lookup"><span data-stu-id="f3ead-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="f3ead-167">عند تنشيط المقطع ، تتغير الحالة الخاصة به من "غير نشط" إلى "نشط" وتبدا في البحث عن العملاء الذين يتطابقون مع تعريف الشريحة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="f3ead-168">إذا تم تكوين [تحديث مجدول](system.md#schedule-tab)، تم تسجيل **الحالة** كـ **تم التخطي** للشرائح غير النشطة، مما يشير إلى أنه لم تتم محاولة التحديث.</span><span class="sxs-lookup"><span data-stu-id="f3ead-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="f3ead-169">وعند تنشيط جزء غير نشط ، فانه سيتم تحديثه سيتم تضمينه في التحديثات المجدولة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="f3ead-170">بدلاً من ذلك، يمكنك استخدام الوظيفة **الجدولة لاحقًا** في القائمة المنسدلة **تنشيط/إلغاء التنشيط** لتحديد التاريخ والوقت المستقبليين لعملية تنشيط وإلغاء تنشيط شريحة معينة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="f3ead-171">**أعد تسمية** المقطع.</span><span class="sxs-lookup"><span data-stu-id="f3ead-171">**Rename** the segment.</span></span>
- <span data-ttu-id="f3ead-172">**قم بتنزيل** قائمة الأعضاء كملف بتنسيق CSV.</span><span class="sxs-lookup"><span data-stu-id="f3ead-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="f3ead-173">يقوم خيار **إضافة إلى** بإرسال قائمة بمعرفات العملاء في الشريحة لمعالجتها في تطبيق آخر.</span><span class="sxs-lookup"><span data-stu-id="f3ead-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="f3ead-174">**احذف** المقطع.</span><span class="sxs-lookup"><span data-stu-id="f3ead-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="f3ead-175">تحديث الشرائح</span><span class="sxs-lookup"><span data-stu-id="f3ead-175">Refresh segments</span></span>

<span data-ttu-id="f3ead-176">يمكنك تحديث كل الشرائح مرة واحدة من خلال تحديد **تحديث الكل** في صفحة **الشرائح** أو يمكنك تحديث شريحة واحدة أو عدة شرائح عندما تقوم بتحديدها واختيار **تحديث** من الخيارات.</span><span class="sxs-lookup"><span data-stu-id="f3ead-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="f3ead-177">وبدلاً من ذلك، يمكنك تكوين تحديث متكرر في **المسؤول** > **النظام** > **جدولة**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="f3ead-178">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="f3ead-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f3ead-179">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f3ead-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f3ead-180">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="f3ead-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f3ead-181">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="f3ead-182">تنزيل المقاطع وتصديرها</span><span class="sxs-lookup"><span data-stu-id="f3ead-182">Download and export segments</span></span>

<span data-ttu-id="f3ead-183">يمكنك تنزيل المقاطع الخاصة بك إلى ملف CSV أو تصديرها إلى Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="f3ead-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="f3ead-184">قم بتنزيل المقاطع إلى ملف CSV</span><span class="sxs-lookup"><span data-stu-id="f3ead-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="f3ead-185">في رؤى الجمهور، انتقل إلى صفحة **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="f3ead-186">حدد علامة الحذف في إطار مقطع معين.</span><span class="sxs-lookup"><span data-stu-id="f3ead-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="f3ead-187">حدد **تنزيل كـ CSV** من قائمة الإجراءات المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="f3ead-188">تصدير المقاطع إلى Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="f3ead-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="f3ead-189">قبل تصدير المقاطع إلى Dynamics 365 Sales، يجب على المسؤول [إنشاء وجهه التصدير](export-destinations.md) لـ Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="f3ead-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="f3ead-190">في رؤى الجمهور، انتقل إلى صفحة **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="f3ead-191">حدد علامة الحذف في إطار مقطع معين.</span><span class="sxs-lookup"><span data-stu-id="f3ead-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="f3ead-192">حدد **إضافة إلى** من القائمة المنسدلة "إجراءات" وحدد وجهة التصدير التي ترغب في إرسال البيانات إليها.</span><span class="sxs-lookup"><span data-stu-id="f3ead-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="f3ead-193">وضع المسودة للمقاطع</span><span class="sxs-lookup"><span data-stu-id="f3ead-193">Draft mode for segments</span></span>

<span data-ttu-id="f3ead-194">في حالة عدم استيفاء كافة متطلبات معالجة مقطع ما، فإنه يمكنك حفظ المقطع كمسودة والوصول إليه من الصفحة **المقاطع**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="f3ead-195">سيتم حفظه كمقطع غير نشط، ولا يمكن تنشيطه إلى أن يصبح صالحًا.</span><span class="sxs-lookup"><span data-stu-id="f3ead-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="f3ead-196">أضق المزيد من الشروط إلى مجموعة</span><span class="sxs-lookup"><span data-stu-id="f3ead-196">Add more conditions to a group</span></span>

<span data-ttu-id="f3ead-197">لإضافة المزيد من الشروط إلى مجموعة، فإنه يمكنك استخدام عاملين منطقيين:</span><span class="sxs-lookup"><span data-stu-id="f3ead-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="f3ead-198">العامل **AND**: يجب استيفاء كلا الشرطين كجزء من عملية التقسيم.</span><span class="sxs-lookup"><span data-stu-id="f3ead-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="f3ead-199">يكون هذا الخيار أكثر إفادة عندما تقوم بتعريف الشروط عبر الكيانات المختلفة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="f3ead-200">العامل **OR**: إما واحدًا من احتياجات الشروط التي يجب استيفائها كجزء من عملية التقسيم.</span><span class="sxs-lookup"><span data-stu-id="f3ead-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="f3ead-201">يكون هذا الخيار أكثر إفادة عندما تقوم بتعريف شروط متعددة للكيان نفسه.</span><span class="sxs-lookup"><span data-stu-id="f3ead-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f3ead-202">![عامل OR حيث يلزم استيفاء أي من الشرطين](media/segmentation-either-condition.png "عامل OR حيث يلزم استيفاء أي من الشرطين")</span><span class="sxs-lookup"><span data-stu-id="f3ead-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="f3ead-203">من الممكن حاليًا إدخال عامل **OR** ضمن عامل **AND**، وليس الطريقة الأخرى.</span><span class="sxs-lookup"><span data-stu-id="f3ead-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="f3ead-204">دمج مجموعات متعددة</span><span class="sxs-lookup"><span data-stu-id="f3ead-204">Combine multiple groups</span></span>

<span data-ttu-id="f3ead-205">كل مجموعة تنتج مجموعة معينة من العملاء.</span><span class="sxs-lookup"><span data-stu-id="f3ead-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="f3ead-206">يمكنك دمج هذه المجموعات لتضمين العملاء المطلوبين لحالة العمل الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="f3ead-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="f3ead-207">في رؤى الجمهور ، انتقل إلى صفحة **الشرائح**، وحدد شريحة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="f3ead-208">حدد **إضافة مجموعة**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f3ead-209">![مجموعة العميل إضافة مجموعة](media/customer-group-add-group.png "مجموعة العميل إضافة مجموعة")</span><span class="sxs-lookup"><span data-stu-id="f3ead-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="f3ead-210">قم بتحديد إحدى عوامل المجموعات التالية: **اتحاد** أو **تقاطع** أو **استثناء**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f3ead-211">![مجموعة العميل إضافة اتحاد](media/customer-group-union.png "مجموعة العميل إضافة اتحاد")</span><span class="sxs-lookup"><span data-stu-id="f3ead-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="f3ead-212">حدد عامل مجموعة لتحديد مجموعة جديدة.</span><span class="sxs-lookup"><span data-stu-id="f3ead-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="f3ead-213">احفظ مجموعات مختلفة التحديد البيانات التي سيتم الاحتفاظ بها:</span><span class="sxs-lookup"><span data-stu-id="f3ead-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="f3ead-214">**Union** يوحد المجموعتين.</span><span class="sxs-lookup"><span data-stu-id="f3ead-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="f3ead-215">**Intersect** يعمل على تداخل المجموعتين.</span><span class="sxs-lookup"><span data-stu-id="f3ead-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="f3ead-216">في المجموعة الموحدة، يتم الاحتفاظ فقط بالبيانات *المشتركة* بين المجموعتين.</span><span class="sxs-lookup"><span data-stu-id="f3ead-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="f3ead-217">**باستثناء** يعمل على دمج المجموعتين.</span><span class="sxs-lookup"><span data-stu-id="f3ead-217">**Except** combines the two groups.</span></span> <span data-ttu-id="f3ead-218">يتم الاحتفاظ فقط بالبيانات في المجموعة A *غير المشتركة* مع البيانات في المجموعة B.</span><span class="sxs-lookup"><span data-stu-id="f3ead-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="f3ead-219">عرض معالجة المحفوظات وأعضاء المقاطع</span><span class="sxs-lookup"><span data-stu-id="f3ead-219">View processing history and segment members</span></span>

<span data-ttu-id="f3ead-220">يمكنك الاطلاع على البيانات المدمجة حول مقطع من خلال مراجعة التفاصيل الخاصة بها.</span><span class="sxs-lookup"><span data-stu-id="f3ead-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="f3ead-221">في الصفحة **المقاطع**، حدد المقطع الذي تريد مراجعته.</span><span class="sxs-lookup"><span data-stu-id="f3ead-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="f3ead-222">يتضمن الجزء العلوي من الصفحة رسم الاتجاه الذي يصور التغييرات في عدد الأعضاء.</span><span class="sxs-lookup"><span data-stu-id="f3ead-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="f3ead-223">قم بالمرور فوق نقاط البيانات لعرض عدد الأعضاء في تاريخ محدد.</span><span class="sxs-lookup"><span data-stu-id="f3ead-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="f3ead-224">يمكنك تحديث الإطار الزمني للرسوم المرئية.</span><span class="sxs-lookup"><span data-stu-id="f3ead-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f3ead-225">![النطاق الزمني للمقطع](media/segment-time-range.png "النطاق الزمني للمقطع")</span><span class="sxs-lookup"><span data-stu-id="f3ead-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="f3ead-226">ويحتوي الجزء السفلي على قائمة تحتوي على أعضاء المقاطع.</span><span class="sxs-lookup"><span data-stu-id="f3ead-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="f3ead-227">تعتمد الحقول التي تظهر في هذه القائمة على سمات كيانات المقطع الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="f3ead-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="f3ead-228">تعتبر القائمة معاينة لأعضاء المقطع المطابق وعرض أول 100 سجل للمقطع الخاص بك بحيث يمكنك تقييمها بسرعة ومراجعة التعريفات إذا لزم الأمر.</span><span class="sxs-lookup"><span data-stu-id="f3ead-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="f3ead-229">لرؤية جميع السجلات المتطابقة، يتعين عليك [تصدير المقطع](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f3ead-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="f3ead-230">مقاطع سريعة</span><span class="sxs-lookup"><span data-stu-id="f3ead-230">Quick segments</span></span>

<span data-ttu-id="f3ead-231">بالإضافة إلى منشئ الشرائح، يوجد مسار آخر لإنشاء الشرائح.</span><span class="sxs-lookup"><span data-stu-id="f3ead-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="f3ead-232">تتيح لك الشرائح السريعة إنشاء شرائح بسيطة باستخدام عامل تشغيل واحد بسرعة وباستخدام نتائج تحليلات فورية.</span><span class="sxs-lookup"><span data-stu-id="f3ead-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="f3ead-233">في الصفحة **المقاطع**، حدد **جديد** > **إنشاء من سريعًا**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="f3ead-234">حدد الخيار **ملفات التعريف** لإنشاء مقطع يستند إلى كيان العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="f3ead-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="f3ead-235">حدد الخيار **المقاييس** لإنشاء مقطع حول كل نوع من سمة العميل للمقاييس التي قمت بإنشاءها مسبقًا في الصفحة **المقاييس**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="f3ead-236">حدد الخيار **ذكاء** لإنشاء مقطع حول أحد كيانات الإخراج التي قمت بإنشاءها باستخدام إمكانات إما **التنبؤات** أو **نماذج مخصصة**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="f3ead-237">في مربع الحوار **مقطع سريع جديد**، حدد سمة من القائمة المنسدلة **الحقل**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="f3ead-238">سيوفر النظام بعض المعلومات الإضافية التي تساعدك في إنشاء مقاطع أفضل للعملاء.</span><span class="sxs-lookup"><span data-stu-id="f3ead-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="f3ead-239">بالنسبة لحقول الفئات، سنقوم بإظهار أهم 10 حسابات للعملاء.</span><span class="sxs-lookup"><span data-stu-id="f3ead-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="f3ead-240">اختر **القيمة** وحدد **المراجعة**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="f3ead-241">بالنسبة للسمة الرقمية، سيظهر النظام قيمة السمة التي تقع ضمن كل قيمة مئوية للعميل.</span><span class="sxs-lookup"><span data-stu-id="f3ead-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="f3ead-242">اختر **عامل** و **قيمة**، ثم حدد **مراجعة**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="f3ead-243">سيوفر لك النظام **حجم مقطع مقدر**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="f3ead-244">يمكنك اختيار إما إنشاء المقطع الذي قمت بتحديده، أو إعادة زيارته أولاً للحصول على حجم قطعة مختلف.</span><span class="sxs-lookup"><span data-stu-id="f3ead-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f3ead-245">![اسم وتقدير مقطع سريع](media/quick-segment-name.png "اسم وتقدير مقطع سريع")</span><span class="sxs-lookup"><span data-stu-id="f3ead-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="f3ead-246">أدخل **اسمًا** للمقطع الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="f3ead-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="f3ead-247">اختياريًا، أدخل **اسم العرض**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="f3ead-248">حدد **حفظ** لحفظ المقطع.</span><span class="sxs-lookup"><span data-stu-id="f3ead-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="f3ead-249">بعد انتهاء معالجة المقطع، يمكنك عرضه كأي مقطع آخر قمت بإنشائه.</span><span class="sxs-lookup"><span data-stu-id="f3ead-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="f3ead-250">بالنسبة للسيناريوهات التالية، فإننا نوصي باستخدام منشئ المقطع بدلاً من إمكانية المقاطع المُوصى بها:</span><span class="sxs-lookup"><span data-stu-id="f3ead-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="f3ead-251">إنشاء مقاطع باستخدام عوامل تصفية على حقول الفئة حيث يكون العامل مختلفًا عن العامل **Is**</span><span class="sxs-lookup"><span data-stu-id="f3ead-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="f3ead-252">إنشاء مقاطع باستخدام عوامل التصفية حيث يكون العامل مختلفًا عن العامل **Between** و **Greater than** و **Less than**.</span><span class="sxs-lookup"><span data-stu-id="f3ead-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="f3ead-253">إنشاء مقاطع باستخدام عوامل تصفية لحقول نوع التاريخ</span><span class="sxs-lookup"><span data-stu-id="f3ead-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="f3ead-254">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="f3ead-254">Next steps</span></span>

<span data-ttu-id="f3ead-255">[قم بتصدير مقطع](export-destinations.md) واستكشف [بطاقة العميل](customer-card-add-in.md) و [الموصلات](export-power-bi.md) للحصول على معلومات عن مستوى العميل.</span><span class="sxs-lookup"><span data-stu-id="f3ead-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]