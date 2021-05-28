---
title: إنشاء شرائج وإدارتها
description: قم بإنشاء شرائح العملاء لتجميعهم استنادًا إلى العديد من السمات.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064921"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="1d6f4-103">إنشاء شرائج وإدارتها</span><span class="sxs-lookup"><span data-stu-id="1d6f4-103">Create and manage segments</span></span>

<span data-ttu-id="1d6f4-104">تعريف عوامل التصفية المعقدة بشأن كيان العميل الموحد والكيانات المرتبطة به.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="1d6f4-105">تعمل كل شريحة، بعد المعالجة، على إنشاء مجموعة من سجلات العملاء التي يمكنك تصديرها وتنفيذ إجراء عليها.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="1d6f4-106">تُدار الشرائح في صفحة **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="1d6f4-107">يوضح المثال التالي قدرة التقسيم إلى شرائح.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="1d6f4-108">لقد قمنا بتحديد مقطع العملاء الذين قاموا بطلب بضائع بمبلغ 500 دولار أمريكي على الأقل في 90 يومًا الأخيرة *و* الذين تم تضمينهم في مكالمة خدمة العملاء التي تم تصعيدها.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="لقطة شاشة لواجهة مستخدم منشئ الشرائح مع مجموعتين لتحدد شريحة عملاء.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="1d6f4-110">إنشاء مقطع جديد</span><span class="sxs-lookup"><span data-stu-id="1d6f4-110">Create a new segment</span></span>

<span data-ttu-id="1d6f4-111">هناك العديد من الطرق لإنشاء شريحة جديدة.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="1d6f4-112">يصف هذا القسم كيفية إنشاء *شريحة فارغة* من البداية.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="1d6f4-113">يمكنك أيضا إنشاء *شريحة سريعة* استنادا إلى الكيانات الموجودة أو استخدام نماذج التعلم الآلي للحصول على *الشرائح المقترحة*.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="1d6f4-114">مزيد من المعلومات: [نظرة عامة على الشرائح](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1d6f4-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="1d6f4-115">أثناء إنشاء شريحة، يمكنك حفظ مسودة.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="1d6f4-116">سيتم حفظها كشريحة غير نشط، ولا يمكن تنشيطها إذا تم إنهائها بتكوين صالح.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="1d6f4-117">انتقل إلى الصفحة **مقاطع**.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="1d6f4-118">حدد **جديد** > **مقطع فارغ**.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="1d6f4-119">في جزء **الشريحة الجديد**، اختر نوع شريحة:</span><span class="sxs-lookup"><span data-stu-id="1d6f4-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="1d6f4-120">**الشرائح الديناميكية** [تحديث](segments.md#refresh-segments) وفقًا لجدول متكرر.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="1d6f4-121">يتم تشغيل **الشرائح الثابتة** مرة واحدة عند إنشائها.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="1d6f4-122">قم بتوفير **اسم كيان إخراج** للشريحة.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="1d6f4-123">اختياريًا، أطلق اسم عرض ووصف يساعدك على تعريف المقطع.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="1d6f4-124">حدد **التالي** للوصول إلى الصفحة **مُنشئ المقطع** حيث يمكنك تعريف مجموعة.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="1d6f4-125">المجموعة هي مجموعة من العملاء.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="1d6f4-126">اختر الكيان الذي يتضمن السمة التي تريد وضع المقطع بها.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="1d6f4-127">اختر السمة المراد التقسيم وفقًا لها.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="1d6f4-128">يمكن أن تحتوي هذه السمة على نوع واحد من أنواع القيم الأربعة: رقمي أو سلسلة أو تاريخ أو منطقي.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="1d6f4-129">اختر عامل وقيمة للسمة المحددة.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1d6f4-130">![عامل تصفية مخصص للمجموعة](media/customer-group-numbers.png "عامل تصفية مجموعة العميل")</span><span class="sxs-lookup"><span data-stu-id="1d6f4-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="1d6f4-131">الرقم‬</span><span class="sxs-lookup"><span data-stu-id="1d6f4-131">Number</span></span> |<span data-ttu-id="1d6f4-132">تعريف</span><span class="sxs-lookup"><span data-stu-id="1d6f4-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="1d6f4-133">1 </span><span class="sxs-lookup"><span data-stu-id="1d6f4-133">1</span></span>     |<span data-ttu-id="1d6f4-134">الكيان </span><span class="sxs-lookup"><span data-stu-id="1d6f4-134">Entity</span></span>          |
   |<span data-ttu-id="1d6f4-135">2 </span><span class="sxs-lookup"><span data-stu-id="1d6f4-135">2</span></span>     |<span data-ttu-id="1d6f4-136">السمة </span><span class="sxs-lookup"><span data-stu-id="1d6f4-136">Attribute</span></span>          |
   |<span data-ttu-id="1d6f4-137">3 </span><span class="sxs-lookup"><span data-stu-id="1d6f4-137">3</span></span>    |<span data-ttu-id="1d6f4-138">عامل</span><span class="sxs-lookup"><span data-stu-id="1d6f4-138">Operator</span></span>         |
   |<span data-ttu-id="1d6f4-139">4</span><span class="sxs-lookup"><span data-stu-id="1d6f4-139">4</span></span>    |<span data-ttu-id="1d6f4-140">قيمة</span><span class="sxs-lookup"><span data-stu-id="1d6f4-140">Value</span></span>         |

   1. <span data-ttu-id="1d6f4-141">لإضافة المزيد من الشروط إلى مجموعة، فإنه يمكنك استخدام عاملين منطقيين:</span><span class="sxs-lookup"><span data-stu-id="1d6f4-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="1d6f4-142">العامل **AND**: يجب استيفاء كلا الشرطين كجزء من عملية التقسيم.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="1d6f4-143">يكون هذا الخيار أكثر إفادة عندما تقوم بتعريف الشروط عبر الكيانات المختلفة.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="1d6f4-144">العامل **OR**: إما واحدًا من احتياجات الشروط التي يجب استيفائها كجزء من عملية التقسيم.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="1d6f4-145">يكون هذا الخيار أكثر إفادة عندما تقوم بتعريف شروط متعددة للكيان نفسه.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="1d6f4-146">![عامل OR حيث يلزم استيفاء أي من الشرطين](media/segmentation-either-condition.png "عامل OR حيث يلزم استيفاء أي من الشرطين")</span><span class="sxs-lookup"><span data-stu-id="1d6f4-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="1d6f4-147">من الممكن حاليًا إدخال عامل **OR** ضمن عامل **AND**، وليس الطريقة الأخرى.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="1d6f4-148">كل مجموعة تطابق مجموعة من العملاء.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-148">Each group matches set of customers.</span></span> <span data-ttu-id="1d6f4-149">يمكنك دمج المجموعات لكي تتضمن العملاء المطلوبين في حالة العمل الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="1d6f4-150">حدد **إضافة مجموعة**.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="1d6f4-151">![مجموعة العميل إضافة مجموعة](media/customer-group-add-group.png "مجموعة العميل إضافة مجموعة")</span><span class="sxs-lookup"><span data-stu-id="1d6f4-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="1d6f4-152">حدد أحد عوامل تشغيل المجموعة: **اتحاد** أو **تقاطع**  أو **استثناء**.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1d6f4-153">![مجموعة العميل إضافة اتحاد](media/customer-group-union.png "مجموعة العميل إضافة اتحاد")</span><span class="sxs-lookup"><span data-stu-id="1d6f4-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="1d6f4-154">**Union** يوحد المجموعتين.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="1d6f4-155">**Intersect** يعمل على تداخل المجموعتين.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="1d6f4-156">في المجموعة الموحدة، يتم الاحتفاظ فقط بالبيانات *المشتركة* بين المجموعتين.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="1d6f4-157">**باستثناء** يعمل على دمج المجموعتين.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-157">**Except** combines the two groups.</span></span> <span data-ttu-id="1d6f4-158">يتم الاحتفاظ فقط بالبيانات في المجموعة A *غير المشتركة* مع البيانات في المجموعة B.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="1d6f4-159">إذا كان الكيان متصلاً بكيان عميل موحد من خلال [العلاقات](relationships.md)، ستحتاج إلى تحديد مسار العلاقة لإنشاء مقطع صالح.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="1d6f4-160">قم بإضافة الكيانات من مسار العلاقة حتى يمكنك تحديد الكيان **العميل: CustomerInsights** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="1d6f4-161">بعد ذلك، اختر **كافة السجلات** لكل خطوة.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1d6f4-162">![مسار العلاقة أثناء إنشاء المقطع](media/segments-multiple-relationships.png "مسار العلاقة أثناء إنشاء المقطع")</span><span class="sxs-lookup"><span data-stu-id="1d6f4-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="1d6f4-163">بشكل افتراضي، تنشئ الشرائح كيان إخراج يحتوي على كافة سمات ملفات تعريف العملاء التي تطابق عوامل التصفية المعرّفة.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="1d6f4-164">إذا كانت شريحة تستند إلى كيانات أخرى غير كيان *العميل*، فيمكنك إضافة المزيد من السمات من هذه الكيانات إلى كيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="1d6f4-165">حدد **سمات المشروع** لاختيار السمات التي سيتم إلحاقها بكيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="1d6f4-166">مثال: تستند شريحة إلى كيان يحتوي على بيانات نشاط العميل المرتبطة بكيان *العميل*.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="1d6f4-167">تبحث الشريحة عن جميع العملاء الذين اتصلوا بمكتب المساعدة في آخر 60 يومًا.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="1d6f4-168">يمكنك اختيار إلحاق مدة المكالمة وعدد المكالمات بجميع سجلات العملاء المتطابقة في كيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="1d6f4-169">قد تكون هذه المعلومات مفيدة لإرسال بريد إلكتروني يتضمن ارتباطات مفيدة إلى مقالات المساعدة عبر الإنترنت والأسئلة المتداولة للعملاء الذين اتصلوا بشكل متكرر.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="1d6f4-170">تعمل السمات المتوقعة فقط مع الكيانات التي تربطها علاقة واحد إلى متعددة مع كيان العميل.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="1d6f4-171">على سبيل المثال، يمكن أن يكون لدى عميل واحد اشتراكات متعددة.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="1d6f4-172">يمكنك فقط توقع السمات من كيان يتم استخدامه في كل مجموعة من استعلام الشرائح الذي تقوم ببنائه.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="1d6f4-173">يتم وضع السمات المتوقعة في الاعتبار عند استخدام عوامل تشغيل المجموعة.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="1d6f4-174">حدد **حفظ** لحفظ المقطع.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="1d6f4-175">سيتم حفظ المقطع الخاص بك ومعالجته في حالة التحقق من صحة كافة المتطلبات.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="1d6f4-176">وإلا، سيتم حفظه كمسودة.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="1d6f4-177">قم بتحديد **رجوع إلى الشرائح** للعودة إلى صفحة **المقاطع**.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="1d6f4-178">مقاطع سريعة</span><span class="sxs-lookup"><span data-stu-id="1d6f4-178">Quick segments</span></span>

<span data-ttu-id="1d6f4-179">تسمح لك الشرائح السريعة ببناء شرائح بسيطة باستخدام عامل تشغيل واحد بسرعة للحصول على معلومات أسرع.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="1d6f4-180">في صفحة **الشرائح**، حدد **جديد** > **إنشاء من**.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="1d6f4-181">حدد خيار **ملفات التعريف** لإنشاء شريحة تستند إلى كيان *العميل الموحد*.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="1d6f4-182">حدد خيار **القياسات** لبناء شريحة حول القياسات التي قمت إنشاؤها مسبقًا.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="1d6f4-183">حدد الخيار **ذكاء** لإنشاء مقطع حول أحد كيانات الإخراج التي قمت بإنشاءها باستخدام إمكانات إما **التنبؤات** أو **نماذج مخصصة**.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="1d6f4-184">في مربع الحوار **مقطع سريع جديد**، حدد سمة من القائمة المنسدلة **الحقل**.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="1d6f4-185">سيوفر النظام بعض المعلومات الإضافية التي تساعدك في إنشاء مقاطع أفضل للعملاء.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="1d6f4-186">بالنسبة لحقول الفئات، سنقوم بإظهار أهم 10 حسابات للعملاء.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="1d6f4-187">اختر **القيمة** وحدد **المراجعة**.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="1d6f4-188">بالنسبة للسمة الرقمية، سيظهر النظام قيمة السمة التي تقع ضمن كل قيمة مئوية للعميل.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="1d6f4-189">اختر **عامل** و **قيمة**، ثم حدد **مراجعة**.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="1d6f4-190">سيوفر لك النظام **حجم مقطع مقدر**.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="1d6f4-191">يمكنك اختيار إما إنشاء المقطع الذي قمت بتحديده، أو إعادة زيارته أولاً للحصول على حجم قطعة مختلف.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="1d6f4-192">![اسم وتقدير مقطع سريع](media/quick-segment-name.png "اسم وتقدير مقطع سريع")</span><span class="sxs-lookup"><span data-stu-id="1d6f4-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="1d6f4-193">أدخل **اسمًا** للمقطع الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="1d6f4-194">اختياريًا، أدخل **اسم العرض**.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="1d6f4-195">حدد **حفظ** لحفظ المقطع.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="1d6f4-196">بعد انتهاء معالجة المقطع، يمكنك عرضه كأي مقطع آخر قمت بإنشائه.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1d6f4-197">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="1d6f4-197">Next steps</span></span>

<span data-ttu-id="1d6f4-198">[قم بتصدير مقطع](export-destinations.md) واستكشف [بطاقة العميل](customer-card-add-in.md) و [الموصلات](export-power-bi.md) للحصول على معلومات عن مستوى العميل.</span><span class="sxs-lookup"><span data-stu-id="1d6f4-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
