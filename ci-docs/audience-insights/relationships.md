---
title: العلاقات بين الكيانات ومسارات الكيانات
description: إنشاء العلاقات بين الكيانات من مصادر بيانات متعددة وإدارتها.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171148"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="21f5e-103">العلاقات بين الكيانات</span><span class="sxs-lookup"><span data-stu-id="21f5e-103">Relationships between entities</span></span>

<span data-ttu-id="21f5e-104">تقوم العلاقات بتوصيل الكيانات وتحدد رسمًا بيانيًا لبياناتك عندما تتشارك الكيانات في معرف عام، وهو مفتاح أجنبي.</span><span class="sxs-lookup"><span data-stu-id="21f5e-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="21f5e-105">يمكن الإشارة إلى هذا المفتاح الخارجي من كيان إلى آخر.</span><span class="sxs-lookup"><span data-stu-id="21f5e-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="21f5e-106">تمكّن الكيانات المتصلة تعريف الشرائح والمقاييس استنادًا إلى مصادر بيانات متعددة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="21f5e-107">هناك ثلاثة أنواع من العلاقات:</span><span class="sxs-lookup"><span data-stu-id="21f5e-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="21f5e-108">علاقات النظام غير القابلة للتحرير، التي يقوم النظام بإنشائها النظام كجزء من عملية توحيد البيانات</span><span class="sxs-lookup"><span data-stu-id="21f5e-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="21f5e-109">العلاقات المتوارثة غير القابلة للتحرير، والتي يتم إنشاؤها بشكل تلقائي نتيجة استيعاب مصادر البيانات</span><span class="sxs-lookup"><span data-stu-id="21f5e-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="21f5e-110">العلاقات المخصصة القابلة للتحرير، التي يتم إنشاؤها وتكوينها بواسطة المستخدمين</span><span class="sxs-lookup"><span data-stu-id="21f5e-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="21f5e-111">علاقات النظام غير القابلة للتحرير</span><span class="sxs-lookup"><span data-stu-id="21f5e-111">Non-editable system relationships</span></span>

<span data-ttu-id="21f5e-112">أثناء تحديث البيانات، يتم إنشاء علاقات النظام بشكل تلقائي بالاستناد إلى التطابق الذكي.</span><span class="sxs-lookup"><span data-stu-id="21f5e-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="21f5e-113">بإمكان هذه العلاقات أن تساعد على ربط ملف تعريف بالعميل بالسجلات المناظرة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="21f5e-114">يوضح المخطط التالي إنشاء العلاقات الثلاث القائمة على النظام.</span><span class="sxs-lookup"><span data-stu-id="21f5e-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="21f5e-115">تتم مطابقة كيان العميل مع الكيانات الأخرى لإنتاج كيان *العميل* الموحد.</span><span class="sxs-lookup"><span data-stu-id="21f5e-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="مخطط مع مسارات علاقات كيان العميل مع ثلاث علاقات واحد إلى متعدد.":::

- <span data-ttu-id="21f5e-117">تم إنشاء **العلاقة *CustomerToContact*** بين كيان *العميل* وكيان *جهة الاتصال* .</span><span class="sxs-lookup"><span data-stu-id="21f5e-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="21f5e-118">يتلقى كيان *العميل*  حقل المفتاح **Contact_contactID** للربط بحقل المفتاح **contactID** للكيان *جهة الاتصال*.</span><span class="sxs-lookup"><span data-stu-id="21f5e-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="21f5e-119">تم إنشاء العلاقة **العلاقة *CustomerToAccount*** بين كيان *العلاقة* وكيان *الحساب*.</span><span class="sxs-lookup"><span data-stu-id="21f5e-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="21f5e-120">يتلقى كيان *العميل* حقل المفتاح **Account_accountID** للربط بحقل المفتاح **accountID** لكيان *الحساب*.</span><span class="sxs-lookup"><span data-stu-id="21f5e-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="21f5e-121">تم إنشاء **العلاقة *CustomerToWebAccount*** بين كيان *العميل* وكيان *WebAccount* .</span><span class="sxs-lookup"><span data-stu-id="21f5e-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="21f5e-122">يتلقى كيان *العميل* حقل المفتاح **WebAccount_webaccountID** لربط مفتاح الحقل **webaccountID** بالكيان *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="21f5e-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="21f5e-123">العلاقات المتوارثة غير القابلة للتحرير</span><span class="sxs-lookup"><span data-stu-id="21f5e-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="21f5e-124">أثناء عملية استيعاب البيانات، يتحقق النظام من مصادر البيانات للعلاقات الموجودة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="21f5e-125">في حال عدم وجود علاقات، يقوم النظام بإنشائها تلقائيًا.</span><span class="sxs-lookup"><span data-stu-id="21f5e-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="21f5e-126">وتُستخدم هذه العلاقات أيضًا في العمليات النهائية.</span><span class="sxs-lookup"><span data-stu-id="21f5e-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="21f5e-127">إنشاء علاقة مخصصة</span><span class="sxs-lookup"><span data-stu-id="21f5e-127">Create a custom relationship</span></span>

<span data-ttu-id="21f5e-128">تتكون العلاقة من *كيان مصدر* يحتوي على المفتاح الخارجي، ومن *كيان هدف* يشير إليه المفتاح الخارجي للكيان المصدر.</span><span class="sxs-lookup"><span data-stu-id="21f5e-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="21f5e-129">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **العلاقات**.</span><span class="sxs-lookup"><span data-stu-id="21f5e-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="21f5e-130">حدد **علاقة جديدة**.</span><span class="sxs-lookup"><span data-stu-id="21f5e-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="21f5e-131">في الجزء **علاقة جديدة**، أدخل المعلومات التالية:</span><span class="sxs-lookup"><span data-stu-id="21f5e-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="الجزء الجانبي للعلاقة الجديدة مع حقول إدخال فارغة.":::

   - <span data-ttu-id="21f5e-133">**اسم العلاقة**: الاسم الذي يعكس الغرض من العلاقة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="21f5e-134">مثال: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="21f5e-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="21f5e-135">**الوصف**: وصف العلاقة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="21f5e-136">**الكيان المصدر**: الكيان المستخدم كمصدر في العلاقة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="21f5e-137">مثال: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="21f5e-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="21f5e-138">**الكيان الهدف**: الكيان المستخدم كهدف في العلاقة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="21f5e-139">مثال: العميل.</span><span class="sxs-lookup"><span data-stu-id="21f5e-139">Example: Customer.</span></span>
   - <span data-ttu-id="21f5e-140">**العلاقة الأساسية للمصدر**: تحديد العلاقة الأساسية للكيان المصدر.</span><span class="sxs-lookup"><span data-stu-id="21f5e-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="21f5e-141">تصف العلاقة الأساسية عدد العناصر المحتملة في مجموعة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="21f5e-142">وهي ترتبط دائمًا بالعلاقة الأساسية الهدف.</span><span class="sxs-lookup"><span data-stu-id="21f5e-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="21f5e-143">يمكنك الاختيار بين **واحد** و **متعدد**.</span><span class="sxs-lookup"><span data-stu-id="21f5e-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="21f5e-144">لا يتم دعم سوى العلاقات متعدد إلى واحد وواحد إلى واحد فقط.</span><span class="sxs-lookup"><span data-stu-id="21f5e-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="21f5e-145">متعدد إلى واحد: بإمكان سجلا مصدر متعددة أن ترتبط بسجل هدف واحد.</span><span class="sxs-lookup"><span data-stu-id="21f5e-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="21f5e-146">مثال: حالات دعم متعددة من عميل واحد.</span><span class="sxs-lookup"><span data-stu-id="21f5e-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="21f5e-147">واحد إلى واحد: يرتبط سجل مصدر واحد بسجل هدف واحد.</span><span class="sxs-lookup"><span data-stu-id="21f5e-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="21f5e-148">مثال: معرف ولاء واحد لعميل واحد.</span><span class="sxs-lookup"><span data-stu-id="21f5e-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="21f5e-149">يمكن إنشاء علاقات متعدد إلى متعدد باستخدام علاقتين من النوع متعدد إلى واحد وكيان ربط، يقوم بتوصيل الكيان المصدر بالكيان الهدف.</span><span class="sxs-lookup"><span data-stu-id="21f5e-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="21f5e-150">**علاقة الهدف الأساسية**: حدد العلاقة الأساسية لسجلات الكيان الهدف.</span><span class="sxs-lookup"><span data-stu-id="21f5e-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="21f5e-151">**حقل المفتاح المصدر**: حقل المفتاح الخارجي في الكيان المصدر.</span><span class="sxs-lookup"><span data-stu-id="21f5e-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="21f5e-152">مثال: قد تستخدم SupportCase معرف CaseID كحقل مفتاح خارجي.</span><span class="sxs-lookup"><span data-stu-id="21f5e-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="21f5e-153">**حقل المفتاح الهدف**: حقل المفتاح للكيان الهدف.</span><span class="sxs-lookup"><span data-stu-id="21f5e-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="21f5e-154">مثال: قد يستخدم العميل مفتاح الحقل **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="21f5e-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="21f5e-155">حدد **حفظ** لإنشاء العلاقة المخصصة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="21f5e-156">عرض العلاقات</span><span class="sxs-lookup"><span data-stu-id="21f5e-156">View relationships</span></span>

<span data-ttu-id="21f5e-157">تسرد صفحة العلاقات جميع العلاقات التي تم إنشاؤها.</span><span class="sxs-lookup"><span data-stu-id="21f5e-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="21f5e-158">يمثل كل صف علاقة، والتي تتضمن أيضًا تفاصيل حول الكيان المصدر، والكيان الهدف، والعلاقة الأساسية.</span><span class="sxs-lookup"><span data-stu-id="21f5e-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="قائمة العلاقات والخيارات في شريط الإجراءات في صفحة العلاقات.":::

<span data-ttu-id="21f5e-160">توفر هذه الصفحة مجموعة من الخيارات للعلاقات الجديدة والموجودة:</span><span class="sxs-lookup"><span data-stu-id="21f5e-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="21f5e-161">**علاقة جديدة**: [إنشاء علاقة مخصصة](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="21f5e-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="21f5e-162">**المصور المرئي**: [استكشف المصور المرئي للعلاقات](#explore-the-relationship-visualizer) لرؤية مخطط شبكة يتضمن العلاقات الموجودة وعلاقاتها الأساسية.</span><span class="sxs-lookup"><span data-stu-id="21f5e-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="21f5e-163">**التصفية حسب**: اختر نوع العلاقات لعرضها في القائمة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="21f5e-164">**بحث في العلاقات** : استخدم بحثًا نصيًا على خصائص العلاقات.</span><span class="sxs-lookup"><span data-stu-id="21f5e-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="21f5e-165">استكشاف المصور المرئي للعلاقات</span><span class="sxs-lookup"><span data-stu-id="21f5e-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="21f5e-166">يعرض المصور المرئي للعلاقات مخطط شبكة يتضمن العلاقات الموجودة بين الكيانات المتصلة وعلاقاتها الأساسية.</span><span class="sxs-lookup"><span data-stu-id="21f5e-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="21f5e-167">لتخصيص طريقة العرض، يمكنك تغيير موقع المربعات من خلال سحبها إلى اللوحة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="لقطة شاشة لمخطط شبكة المصور المرئي للعلاقات مع اتصالات بين الكيانات المرتبطة.":::

<span data-ttu-id="21f5e-169">الخيارات المتوفرة:</span><span class="sxs-lookup"><span data-stu-id="21f5e-169">Available options:</span></span> 
- <span data-ttu-id="21f5e-170">**تصدير كصورة**: حفظ طريقة العرض الحالية كملف صورة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="21f5e-171">**تغيير إلى تخطيط أفقي/عمودي**: اختر محاذاة الكيانات والعلاقات.</span><span class="sxs-lookup"><span data-stu-id="21f5e-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="21f5e-172">**تحرير**: تحديث خصائص العلاقات المخصصة في جزء التحرير وحفظ التغييرات.</span><span class="sxs-lookup"><span data-stu-id="21f5e-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="21f5e-173">إدارة العلاقات الموجودة</span><span class="sxs-lookup"><span data-stu-id="21f5e-173">Manage existing relationships</span></span> 

<span data-ttu-id="21f5e-174">في صفحة العلاقات، يتم تمثيل كل علاقة بصف.</span><span class="sxs-lookup"><span data-stu-id="21f5e-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="21f5e-175">حدد علاقة واختر أحد الخيارات التالية:</span><span class="sxs-lookup"><span data-stu-id="21f5e-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="21f5e-176">**تحرير**: تحديث خصائص العلاقات المخصصة في جزء التحرير وحفظ التغييرات.</span><span class="sxs-lookup"><span data-stu-id="21f5e-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="21f5e-177">**حذف**: حذف العلاقات المخصصة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="21f5e-178">**عرض**: عرض العلاقات التي أنشأها النظام والعلاقات المتوارثة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="21f5e-179">الخطوة التالية</span><span class="sxs-lookup"><span data-stu-id="21f5e-179">Next step</span></span>

<span data-ttu-id="21f5e-180">يتم استخدام علاقات النظام والعلاقات المخصصة من أجل [إنشاء شرائح](segments.md) بالاستناد إلى مصادر بيانات متعددة لم تعد معزولة.</span><span class="sxs-lookup"><span data-stu-id="21f5e-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
