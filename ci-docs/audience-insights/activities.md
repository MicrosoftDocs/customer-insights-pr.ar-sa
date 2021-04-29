---
title: أنشطة العملاء
description: تحديد أنشطة العميل وعرضها في المخطط الزمني للعميل.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866391"
---
# <a name="customer-activities"></a><span data-ttu-id="36ec6-103">أنشطة العملاء</span><span class="sxs-lookup"><span data-stu-id="36ec6-103">Customer activities</span></span>

<span data-ttu-id="36ec6-104">قم بدمج أنشطة العملاء من [مصادر بيانات متعددة](data-sources.md) في Dynamics 365 Customer Insights لإنشاء جدول زمني يسرد الأنشطة بترتيب زمني.</span><span class="sxs-lookup"><span data-stu-id="36ec6-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="36ec6-105">قم بتضمين المخطط الزمني في تطبيقات Dynamics 365 مع حل [الوظيفة الإضافية لبطاقة العميل](customer-card-add-in.md) أو في لوحة معلومات Power BI.</span><span class="sxs-lookup"><span data-stu-id="36ec6-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="36ec6-106">تعريف نشاط</span><span class="sxs-lookup"><span data-stu-id="36ec6-106">Define an activity</span></span>

<span data-ttu-id="36ec6-107">يمكن أن تتضمن مصادر البيانات كيانات تحتوي على بيانات المعاملات والأنشطة من مصادر بيانات متعددة.</span><span class="sxs-lookup"><span data-stu-id="36ec6-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="36ec6-108">قم بتعريف هذه الكيانات وحدد الأنشطة التي ترغب في عرضها على المخطط الزمني للعميل.</span><span class="sxs-lookup"><span data-stu-id="36ec6-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="36ec6-109">اختر الكيان الذي يتضمن نشاطك (أو أنشطتك) المستهدف.</span><span class="sxs-lookup"><span data-stu-id="36ec6-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="36ec6-110">يجب أن يحتوي الكيان على سمة واحدة على الأقل من نوع **التاريخ** كي يتم تضمينها في المخطط الزمني للعميل، ولا يمكنك إضافة كيانات من دون حقول **التاريخ‏‎**.</span><span class="sxs-lookup"><span data-stu-id="36ec6-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="36ec6-111">يتم تعطيل عنصر التحكم **إضافة نشاط** إذا لم يتم العثور على مثل هذا الكيان.</span><span class="sxs-lookup"><span data-stu-id="36ec6-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="36ec6-112">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **الأنشطة**.</span><span class="sxs-lookup"><span data-stu-id="36ec6-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="36ec6-113">حدد **إضافة نشاط** لبدء تجربة إرشادية لعملية إعداد النشاط.</span><span class="sxs-lookup"><span data-stu-id="36ec6-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="36ec6-114">في خطوة **بيانات النشاط**، قم بتعيين القيم الخاصة بالحقول التالية:</span><span class="sxs-lookup"><span data-stu-id="36ec6-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="36ec6-115">**اسم النشاط**: حدد اسمًا لنشاطك.</span><span class="sxs-lookup"><span data-stu-id="36ec6-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="36ec6-116">**الكيان**: حدد كيانًا يتضمن بيانات المعاملات أو الأنشطة.</span><span class="sxs-lookup"><span data-stu-id="36ec6-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="36ec6-117">**المفتاح الأساسي**: حدد الحقل الذي يعرّف السجل بشكل فريد.</span><span class="sxs-lookup"><span data-stu-id="36ec6-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="36ec6-118">وينبغي ألا يحتوي على أي قيم متكررة أو قيم فارغة أو قيم مفقودة.</span><span class="sxs-lookup"><span data-stu-id="36ec6-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="قم بإعداد بيانات النشاط بالاسم والكيانات والمفتاح الرئيسي.":::

1. <span data-ttu-id="36ec6-120">حدد **التالي** للذهاب إلى الخطوة التالية.</span><span class="sxs-lookup"><span data-stu-id="36ec6-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="36ec6-121">في خطوة **العلاقة**، قم بتكوين التفاصيل لربط بيانات نشاطك بالعميل المقابل لها.</span><span class="sxs-lookup"><span data-stu-id="36ec6-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="36ec6-122">تصور هذه الخطوة الاتصال بين الكيانات.</span><span class="sxs-lookup"><span data-stu-id="36ec6-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="36ec6-123">**أولاً**: حقل أجنبي في كيان النشاط سيتم استخدامه لإنشاء علاقة مع كيان آخر.</span><span class="sxs-lookup"><span data-stu-id="36ec6-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="36ec6-124">**ثانيًا**: كيان العميل المصدر المقابل الذي سيكون كيان النشاط الخاص بك على علاقة به.</span><span class="sxs-lookup"><span data-stu-id="36ec6-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="36ec6-125">يمكنك فقط ربط كيانات العميل المصدر التي تم استخدامها في عملية علاقات البيانات.</span><span class="sxs-lookup"><span data-stu-id="36ec6-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="36ec6-126">**ثالثًا**: إذا كانت هناك علاقة بين كيان النشاط هذا وبين كيان العميل المصدر المحدد موجودة بالفعل، سيكون اسم العلاقة في وضع القراءة فقط.</span><span class="sxs-lookup"><span data-stu-id="36ec6-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="36ec6-127">إذا لم تكن هناك علاقة من هذا النوع، سيتم إنشاء علاقة جديدة بالاسم الذي توفره في هذا المربع.</span><span class="sxs-lookup"><span data-stu-id="36ec6-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="قم بتحديد علاقة الكيان.":::

1. <span data-ttu-id="36ec6-129">حدد **التالي** للذهاب إلى الخطوة التالية.</span><span class="sxs-lookup"><span data-stu-id="36ec6-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="36ec6-130">في خطوة **توحيد النشاط**، اختر حدث النشاط ووقت بدء النشاط.</span><span class="sxs-lookup"><span data-stu-id="36ec6-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="36ec6-131">**الحقول المطلوبة**</span><span class="sxs-lookup"><span data-stu-id="36ec6-131">**Required fields**</span></span>
      1. <span data-ttu-id="36ec6-132">**نشاط الحدث**: الحقل الذي هو الحدث لهذا النشاط</span><span class="sxs-lookup"><span data-stu-id="36ec6-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="36ec6-133">**الطابع الزمني**: حقل يمثل وقت بدء النشاط.</span><span class="sxs-lookup"><span data-stu-id="36ec6-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="36ec6-134">**الحقول الاختيارية**</span><span class="sxs-lookup"><span data-stu-id="36ec6-134">**Optional fields**</span></span>
      1. <span data-ttu-id="36ec6-135">**تفاصيل إضافية**: حقل به معلومات ذات صلة لهذا النشاط.</span><span class="sxs-lookup"><span data-stu-id="36ec6-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="36ec6-136">**الرمز**: الرمز الذي يمثل أفضل ما يكون نوع النشاط هذا.</span><span class="sxs-lookup"><span data-stu-id="36ec6-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="36ec6-137">**عنوان ويب**: حقل يحتوي على عنوان URL يحتوي على معلومات حول هذا النشاط.</span><span class="sxs-lookup"><span data-stu-id="36ec6-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="36ec6-138">على سبيل المثال، نظام المعاملات الذي يعمل كمصدر بيانات لهذا النشاط.</span><span class="sxs-lookup"><span data-stu-id="36ec6-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="36ec6-139">يمكن أن يكون عنوان URL هذا أي حقل من مصدر البيانات، أو يمكن إنشاؤه كحقل جديد باستخدام تحويل Power Query.</span><span class="sxs-lookup"><span data-stu-id="36ec6-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="36ec6-140">سيتم تخزين بيانات URL في كيان *النشاط الموحد*، والذي يمكن استهلاكه لأسفل باستخدام [واجهات برمجة التطبيقات](apis.md).</span><span class="sxs-lookup"><span data-stu-id="36ec6-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="حدد بيانات نشاط العميل في كيان النشاط الموحد.":::

1. <span data-ttu-id="36ec6-142">حدد **التالي** للانتقال إلى الخطوة التالية.</span><span class="sxs-lookup"><span data-stu-id="36ec6-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="36ec6-143">يمكنك تحديد **إنهاء ومراجعة** لحفظ النشاط الآن مع تعيين نوع النشاط إلى **أخرى**.</span><span class="sxs-lookup"><span data-stu-id="36ec6-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="36ec6-144">في خطوة **نوع النشاط**، اختر نوع النشاط وحدد اختياريًا ما إذا كنت تريد تعيين بعض أنواع الأنشطة لغويًا لاستخدامها في مناطق أخرى من Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="36ec6-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="36ec6-145">في الوقت الحالي، يتم تعيين أنواع نشاط *الاشتراك* & *SalesOrderLine* لغويًا بعد الموافقة على تعيين الحقول.</span><span class="sxs-lookup"><span data-stu-id="36ec6-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="36ec6-146">إذا كان نوع النشاط غير مناسب للنشاط الجديد، يمكنك اختيار *أخرى* أو *إنشاء جديد* لنوع نشاط مخصص.</span><span class="sxs-lookup"><span data-stu-id="36ec6-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="36ec6-147">حدد **التالي** للانتقال إلى الخطوة التالية.</span><span class="sxs-lookup"><span data-stu-id="36ec6-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="36ec6-148">في خطوة **المراجعة**، تحقق من التحديدات التي أجريتها.</span><span class="sxs-lookup"><span data-stu-id="36ec6-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="36ec6-149">يمكنك الرجوع إلى أي من الخطوات السابقة وتحديث المعلومات عند الضرورة.</span><span class="sxs-lookup"><span data-stu-id="36ec6-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="راجع الحقول المحددة لنشاط ما.":::
   
1. <span data-ttu-id="36ec6-151">حدد **حفظ النشاط** لتطبيق التغييرات التي أجريتها وحدد **تم** للعودة إلى **البيانات** > **الأنشطة**.</span><span class="sxs-lookup"><span data-stu-id="36ec6-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="36ec6-152">وشاهد هنا الأنشطة التي تم تعيينها لإظهارها في المخطط الزمني.</span><span class="sxs-lookup"><span data-stu-id="36ec6-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="36ec6-153">في صفحة **الأنشطة**، حدد **تشغيل** لمعالجة النشاط.</span><span class="sxs-lookup"><span data-stu-id="36ec6-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="36ec6-154">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="36ec6-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="36ec6-155">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="36ec6-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="36ec6-156">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="36ec6-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="36ec6-157">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="36ec6-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="36ec6-158">إدارة الأنشطة الموجودة</span><span class="sxs-lookup"><span data-stu-id="36ec6-158">Manage existing activities</span></span>

<span data-ttu-id="36ec6-159">في **البيانات** > **الأنشطة**، يمكنك عرض جميع الأنشطة المحفوظة الخاصة بك وإدارتها.</span><span class="sxs-lookup"><span data-stu-id="36ec6-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="36ec6-160">يتم تمثيل كل نشاط من خلال صف يتضمن أيضا تفاصيل حول المصدر، والكيان، ونوع النشاط.</span><span class="sxs-lookup"><span data-stu-id="36ec6-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="36ec6-161">تتوفر الإجراءات التالية عند تحديد نشاط.</span><span class="sxs-lookup"><span data-stu-id="36ec6-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="36ec6-162">**تحرير**: يفتح إعداد النشاط في خطوة المراجعة.</span><span class="sxs-lookup"><span data-stu-id="36ec6-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="36ec6-163">يمكنك تغيير أي من التكوينات الحالية أو كلها من هذه الخطوة.</span><span class="sxs-lookup"><span data-stu-id="36ec6-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="36ec6-164">بعد تغيير التكوين، قم بتحديد **حفظ النشاط** ثم قم بتحديد **تشغيل** لمعالجة التغييرات.</span><span class="sxs-lookup"><span data-stu-id="36ec6-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="36ec6-165">**إعادة تسمية**: تفتح مربع حوار حيث يتم إدخال اسم مختلف للنشاط المحدد.</span><span class="sxs-lookup"><span data-stu-id="36ec6-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="36ec6-166">حدد **حفظ** لتطبيق التغييرات التي أجريتها.</span><span class="sxs-lookup"><span data-stu-id="36ec6-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="36ec6-167">**حذف**: افتح أحد مربعات الحوار لتأكيد حذف النشاط المحدد.</span><span class="sxs-lookup"><span data-stu-id="36ec6-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="36ec6-168">يمكنك أيضا حذف أكثر من نشاط واحد مرة واحدة بتحديد الأنشطة ثم تحديد رمز الحذف.</span><span class="sxs-lookup"><span data-stu-id="36ec6-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="36ec6-169">حدد **حذف** لتأكيد الحذف.</span><span class="sxs-lookup"><span data-stu-id="36ec6-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
