---
title: أنشطة العملاء
description: تحديد أنشطة العميل وعرضها في المخطط الزمني للعميل.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: fbfa9d7e00859cc80c24b98bd2dc806f1fda7803
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596713"
---
# <a name="customer-activities"></a><span data-ttu-id="2b81f-103">أنشطة العملاء</span><span class="sxs-lookup"><span data-stu-id="2b81f-103">Customer activities</span></span>

<span data-ttu-id="2b81f-104">ادمج أنشطة العملاء من [مصادر بيانات متنوعة](data-sources.md) في Dynamics 365 Customer Insights لإنشاء مخطط زمني للعميل يسرد الأنشطة بترتيب زمني.</span><span class="sxs-lookup"><span data-stu-id="2b81f-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="2b81f-105">يمكنك تضمين الخط الزمني في تطبيقات مشاركة العميل في Dynamics 365 عبر [الوظيفة الإضافية لبطاقة العميل ](customer-card-add-in.md)أو في لوحة معلومات Power BI.</span><span class="sxs-lookup"><span data-stu-id="2b81f-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="2b81f-106">تعريف نشاط</span><span class="sxs-lookup"><span data-stu-id="2b81f-106">Define an activity</span></span>

<span data-ttu-id="2b81f-107">تتضمن مصادر البيانات كيانات تحتوي على بيانات المعاملات والأنشطة من مصادر بيانات متعددة.</span><span class="sxs-lookup"><span data-stu-id="2b81f-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="2b81f-108">قم بتعريف هذه الكيانات وحدد الأنشطة التي ترغب في عرضها على المخطط الزمني للعميل.</span><span class="sxs-lookup"><span data-stu-id="2b81f-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="2b81f-109">اختر الكيان الذي يتضمن نشاطك (أو أنشطتك) المستهدف.</span><span class="sxs-lookup"><span data-stu-id="2b81f-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="2b81f-110">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **الأنشطة**.</span><span class="sxs-lookup"><span data-stu-id="2b81f-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="2b81f-111">حدد **إضافة نشاط**.</span><span class="sxs-lookup"><span data-stu-id="2b81f-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2b81f-112">يجب أن يحتوي الكيان على سمة واحدة على الأقل من نوع **التاريخ** كي يتم تضمينها في المخطط الزمني للعميل، ولا يمكنك إضافة كيانات من دون حقول **التاريخ‏‎**.</span><span class="sxs-lookup"><span data-stu-id="2b81f-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="2b81f-113">يتم تعطيل عنصر التحكم **إضافة نشاط** إذا لم يتم العثور على مثل هذا الكيان.</span><span class="sxs-lookup"><span data-stu-id="2b81f-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="2b81f-114">في جزء **إضافة نشاط**، قم بتعيين القيم للحقول التالية:</span><span class="sxs-lookup"><span data-stu-id="2b81f-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="2b81f-115">**الكيان**: حدد كيانًا يتضمن بيانات المعاملات أو الأنشطة.</span><span class="sxs-lookup"><span data-stu-id="2b81f-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="2b81f-116">**المفتاح الأساسي**: حدد الحقل الذي يعرّف السجل بشكل فريد.</span><span class="sxs-lookup"><span data-stu-id="2b81f-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="2b81f-117">وينبغي ألا يحتوي على أي قيم متكررة أو قيم فارغة أو قيم مفقودة.</span><span class="sxs-lookup"><span data-stu-id="2b81f-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="2b81f-118">**الطابع الزمني**: حدد الحقل الذي يمثل وقت بدء نشاطك.</span><span class="sxs-lookup"><span data-stu-id="2b81f-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="2b81f-119">**الحدث**: حدد الحقل الذي يمثل الحدث للنشاط.</span><span class="sxs-lookup"><span data-stu-id="2b81f-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="2b81f-120">**عنوان الويب**: حدد الحقل الذي يمثل عنوان URL الذي يوفر معلومات إضافية حول هذا النشاط.</span><span class="sxs-lookup"><span data-stu-id="2b81f-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="2b81f-121">على سبيل المثال، نظام المعاملات الذي يعمل كمصدر بيانات لهذا النشاط.</span><span class="sxs-lookup"><span data-stu-id="2b81f-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="2b81f-122">يمكن أن يكون عنوان URL هذا أي حقل من مصدر البيانات، أو يمكن إنشاؤه كحقل جديد باستخدام تحويل Power Query.</span><span class="sxs-lookup"><span data-stu-id="2b81f-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="2b81f-123">سيتم تخزين بيانات عنوان URL هذه في كيان النشاط الموحد، والذي يمكن أن يتم استهلاكه في اتجاه انتقال البيانات باستخدام واجهات برمجة التطبيقات.</span><span class="sxs-lookup"><span data-stu-id="2b81f-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="2b81f-124">**التفاصيل**: بشكل اختياري، حدد الحقل الذي تمت إضافته للحصول على مزيد من التفاصيل.</span><span class="sxs-lookup"><span data-stu-id="2b81f-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="2b81f-125">**الأيقونة**: بشكل اختياري، حدد الأيقونة‏‎ التي تمثل هذا النشاط.</span><span class="sxs-lookup"><span data-stu-id="2b81f-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="2b81f-126">**نوع النشاط**: تعريف مرجع نوع النشاط إلى نموذج البيانات العامة الذي يصف التعريف الدلالي للنشاط بشكل أفضل.</span><span class="sxs-lookup"><span data-stu-id="2b81f-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="2b81f-127">في القسم **إعداد العلاقة**، قم بتكوين التفاصيل لتوصيل بيانات النشاط الخاصة بك بالعميل المقابل لها.</span><span class="sxs-lookup"><span data-stu-id="2b81f-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="2b81f-128">**حقل كيان النشاط**: حدد الحقل في كيان النشاط الخاص بك الذي سيتم استخدامه لإنشاء علاقة مع كيان آخر.</span><span class="sxs-lookup"><span data-stu-id="2b81f-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="2b81f-129">**كيان العميل**: حدد كيان العميل المصدر المقابل الذي سيكون كيان النشاط الخاص بك في علاقة معه.</span><span class="sxs-lookup"><span data-stu-id="2b81f-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="2b81f-130">يمكنك الربط فقط بكيانات العملاء المصدر هذه المستخدمة في عملية توحيد البيانات.</span><span class="sxs-lookup"><span data-stu-id="2b81f-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="2b81f-131">**حقل كيان العميل**: يعرض هذا الحقل المفتاح الأساسي لكيان العميل المصدر كما هو محدد في عملية الخريطة.</span><span class="sxs-lookup"><span data-stu-id="2b81f-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="2b81f-132">يتم استخدام حقل المفتاح الأساسي هذا في كيان العميل المصدر لإنشاء علاقة مع كيان النشاط.</span><span class="sxs-lookup"><span data-stu-id="2b81f-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="2b81f-133">**الاسم**: في حالة وجود علاقة بين كيان النشاط هذا وكيان العميل المصدر المحدد بالفعل، سيكون اسم العلاقة في وضع القراءة فقط.</span><span class="sxs-lookup"><span data-stu-id="2b81f-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="2b81f-134">في حالة وجود مثل هذه العلاقة، سيتم إنشاء علاقة جديدة بالاسم المقدم هنا.</span><span class="sxs-lookup"><span data-stu-id="2b81f-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2b81f-135">![تعريف علاقة الكيان](media/activities-entities-define.png "تعريف علاقة الكيان")</span><span class="sxs-lookup"><span data-stu-id="2b81f-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="2b81f-136">حدد **حفظ** لتطبيق التغييرات التي أجريتها.</span><span class="sxs-lookup"><span data-stu-id="2b81f-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="2b81f-137">في الصفحة **الأنشطة**، حدد **تشغيل**.</span><span class="sxs-lookup"><span data-stu-id="2b81f-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="2b81f-138">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="2b81f-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2b81f-139">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="2b81f-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2b81f-140">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="2b81f-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2b81f-141">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="2b81f-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="2b81f-142">تحرير نشاط</span><span class="sxs-lookup"><span data-stu-id="2b81f-142">Edit an activity</span></span>

1. <span data-ttu-id="2b81f-143">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **الأنشطة**.</span><span class="sxs-lookup"><span data-stu-id="2b81f-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="2b81f-144">حدد كيان النشاط الذي تريد تحريره وقم بتحديد **تحرير**.</span><span class="sxs-lookup"><span data-stu-id="2b81f-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="2b81f-145">أو، يمكنك المرور فوق صف الكيان وتحديد الرمز **تحرير**.</span><span class="sxs-lookup"><span data-stu-id="2b81f-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="2b81f-146">انقر فوق الرمز **تحرير**.</span><span class="sxs-lookup"><span data-stu-id="2b81f-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="2b81f-147">في الجزء **تحرير النشاط**، قم بتحديث القيم وحدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="2b81f-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="2b81f-148">في الصفحة **الأنشطة**، حدد **تشغيل**.</span><span class="sxs-lookup"><span data-stu-id="2b81f-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="2b81f-149">حذف نشاط</span><span class="sxs-lookup"><span data-stu-id="2b81f-149">Delete an activity</span></span>

1. <span data-ttu-id="2b81f-150">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **الأنشطة**.</span><span class="sxs-lookup"><span data-stu-id="2b81f-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="2b81f-151">حدد كيان النشاط الذي تريد إزالته وقم بتحديد **حذف**.</span><span class="sxs-lookup"><span data-stu-id="2b81f-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="2b81f-152">أو، يمكنك المرور فوق صف الكيان وتحديد الرمز **حذف**.</span><span class="sxs-lookup"><span data-stu-id="2b81f-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="2b81f-153">بالإضافة إلى ذلك، يمكنك تحديد كيانات أنشطة متعددة ليتم حذفها مرة واحدة.</span><span class="sxs-lookup"><span data-stu-id="2b81f-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2b81f-154">![تحرير أو حذف علاقات الكيان](media/activities-entities-edit-delete.png "تحرير أو حذف علاقات الكيان.").</span><span class="sxs-lookup"><span data-stu-id="2b81f-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="2b81f-155">حدد الرمز **حذف**.</span><span class="sxs-lookup"><span data-stu-id="2b81f-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="2b81f-156">قم بتأكيد الحذف.</span><span class="sxs-lookup"><span data-stu-id="2b81f-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]