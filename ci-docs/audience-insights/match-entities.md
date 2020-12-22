---
title: مطابقة الكيانات لتوحيد البيانات
description: مطابقة الكيانات لإنشاء ملفات تعريف العملاء الموحدة.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4404936"
---
# <a name="match-entities"></a><span data-ttu-id="e2fc4-103">تطابق الكيانات</span><span class="sxs-lookup"><span data-stu-id="e2fc4-103">Match entities</span></span>

<span data-ttu-id="e2fc4-104">بعد الانتهاء من مرحلة المخطط، تكون جاهزًا لمطابقة كياناتك.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-104">After completing the map phase, you're ready to match your entities.</span></span> <span data-ttu-id="e2fc4-105">تحدد مرحلة المطابقة كيفية دمج مجموعات البيانات الخاصة بك في مجموعة بيانات موحدة لملف تعريف العميل.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-105">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="e2fc4-106">تتطلب مرحلة المطابقة [كيانين معيّنين على الأقل](map-entities.md).</span><span class="sxs-lookup"><span data-stu-id="e2fc4-106">The match phase requires at least [two mapped entities](map-entities.md).</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="e2fc4-107">حدد ترتيب المطابقة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-107">Specify the match order</span></span>

<span data-ttu-id="e2fc4-108">انتقل إلى **توحيد** > **المطابقة** وحدد **تعيين ترتيب** لبدء مرحلة المطابقة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-108">Go to **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="e2fc4-109">تُوحد كل مطابقة كيانين أو أكثر في كيان واحد، في حين يستمر كل سجل عميل فريدًا.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-109">Each match unifies two or more entities into a single entity, while persisting each unique customer record.</span></span> <span data-ttu-id="e2fc4-110">في المثال التالي ، حددنا ثلاثة كيانات: **ContactCSV: TestData** بصفته كيان **أساسي** ، و **WebAccountCSV: TestData** بصفته **كيان رقم 2**، و **CallRecordSmall: TestData** بصفته **كيان رقم 3**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-110">In the following example, we selected three entities: **ContactCSV: TestData** as the **Primary** entity, **WebAccountCSV: TestData** as **Entity 2**, and **CallRecordSmall: TestData** as **Entity 3**.</span></span> <span data-ttu-id="e2fc4-111">يوضح الرسم البياني أعلى التحديدات كيف سيتم تنفيذ ترتيب المطابقة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-111">The diagram above the selections illustrates how the match order will be executed.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e2fc4-112">![تحرير ترتيب تطابق البيانات](media/configure-data-match-order-edit-page.png "تحرير ترتيب تطابق البيانات")</span><span class="sxs-lookup"><span data-stu-id="e2fc4-112">![Edit the data match order](media/configure-data-match-order-edit-page.png "Edit the data match order")</span></span>
  
<span data-ttu-id="e2fc4-113">يتطابق الكيان **الأساسي** مع **الكيان 2**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-113">The **Primary** entity is matched with **Entity 2**.</span></span> <span data-ttu-id="e2fc4-114">وتتطابق مجموعة البيانات التي تنتج عن المطابقة الأولى مع **الكيان 3**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-114">The dataset that results from the first match is matched with **Entity 3**.</span></span>
<span data-ttu-id="e2fc4-115">في هذا المثال، حددنا فقط مطابقتين، ولكن يمكن للنظام أن يدعم أكثر.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-115">In this example, we only selected two matches, but the system can support more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2fc4-116">سيكون الكيان الذي تختاره بصفته كيان **أساسي** بمثابة أساس لمجموعة البيانات الرئيسية الموحدة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-116">The entity that you choose as your **Primary** entity will serve as the basis for your unified master dataset.</span></span> <span data-ttu-id="e2fc4-117">ستتم إضافة الكيانات الإضافية المحددة خلال مرحلة المطابقة إلى هذا الكيان.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-117">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="e2fc4-118">وفي الوقت نفسه، لا يعني هذا أن الكيان الموحد سيتضمن *جميع* البيانات المضمنة في هذا الكيان.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-118">At the same time, this doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="e2fc4-119">هناك اعتبارين يمكنهم مساعدتك في اختيار التسلسل الهرمي للكيانات الخاصة بك:</span><span class="sxs-lookup"><span data-stu-id="e2fc4-119">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="e2fc4-120">ما هو الكيان الذي تعتقد أنه يمتلك البيانات الأكثر اكتمالا وموثوقية عن عملائك؟</span><span class="sxs-lookup"><span data-stu-id="e2fc4-120">What entity do you consider having the most complete and reliable data about your customers?</span></span>
> - <span data-ttu-id="e2fc4-121">هل لدى الكيان الذي قمت بتعريفه للتو سمات تشترك فيها كيانات أخرى أيضًا (على سبيل المثال، الاسم أو رقم الهاتف أو عنوان البريد الإلكتروني)؟</span><span class="sxs-lookup"><span data-stu-id="e2fc4-121">Does the entity that you just identified have attributes that are also shared by other entities (for example, name, phone number, or email address)?</span></span> <span data-ttu-id="e2fc4-122">إذا لم يكن كذلك، فاختر كيانك الثاني الأكثر موثوقية.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-122">If not, choose your second most reliable entity.</span></span>

<span data-ttu-id="e2fc4-123">اختر **تم** لحفظ ترتيب المطابقة الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-123">Select **Done** to save your match order.</span></span>

## <a name="define-rules-for-your-first-match-pair"></a><span data-ttu-id="e2fc4-124">تعريف القواعد لزوج التطابق الأول الخاص بك</span><span class="sxs-lookup"><span data-stu-id="e2fc4-124">Define rules for your first match pair</span></span>

<span data-ttu-id="e2fc4-125">بعد تحديد ترتيب المطابقة، سترى التطابقات المحددة في صفحة **المطابقة**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-125">After specifying the match order, you'll see the defined matches on the **Match** page.</span></span> <span data-ttu-id="e2fc4-126">ستكون الإطارات المتجانبة في الجزء العلوي من الشاشة فارغة حتى تقوم بتشغيل ترتيب المطابقة الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-126">The tiles at the top of the screen will be empty until you run your match order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e2fc4-127">![تعريف القواعد](media/configure-data-match-need-rules.png "تعريف القواعد")</span><span class="sxs-lookup"><span data-stu-id="e2fc4-127">![Define rules](media/configure-data-match-need-rules.png "Define rules")</span></span>

<span data-ttu-id="e2fc4-128">يشير تحذير **قواعد الاحتياجات** إلى عدم تحديد قاعدة مطابقة لزوج المطابقة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-128">The **Needs Rules** warning suggests that no match rule is defined for a match pair.</span></span> <span data-ttu-id="e2fc4-129">تحدد قواعد المطابقة المنطق الذي سيتم من خلاله مطابقة زوج معين من الكيانات.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

1. <span data-ttu-id="e2fc4-130">لتحديد القاعدة الأولى، افتح جزء **تعريف القاعدة** عن طريق تحديد صف المطابقة المقابل في جدول المطابقات (1) ثم حدد **إنشاء قاعدة جديدة** (2).</span><span class="sxs-lookup"><span data-stu-id="e2fc4-130">To define your first rule, open the **Rule Definition** pane by selecting the corresponding match row in the matches table (1) and then selecting **Create new rule** (2).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2fc4-131">![إنشاء قاعدة جديدة](media/configure-data-match-new-rule2.png "إنشاء قاعدة جديدة")</span><span class="sxs-lookup"><span data-stu-id="e2fc4-131">![Create new rule](media/configure-data-match-new-rule2.png "Create new rule")</span></span>

2. <span data-ttu-id="e2fc4-132">في الجزء **تحرير قاعدة** ، قم بتكوين الشروط الخاصة بهذه القاعدة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-132">In the **Edit Rule** pane, configure the conditions for that rule.</span></span> <span data-ttu-id="e2fc4-133">يتم تمثيل كل شرط بواسطة صفين يتضمنان اختيارات إلزامية.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-133">Each condition is represented by two rows that include mandatory selections.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2fc4-134">![جزء القاعدة الجديدة](media/configure-data-match-new-rule-condition.png "جزء القاعدة الجديدة")</span><span class="sxs-lookup"><span data-stu-id="e2fc4-134">![New rule pane](media/configure-data-match-new-rule-condition.png "New rule pane")</span></span>

   <span data-ttu-id="e2fc4-135">الكيان/الحقل (الأول) - السمة التي سيتم استخدامها للمطابقة من كيان زوج التطابق الأول.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-135">Entity/Field (first) - An attribute that will be used for matching from the first match pair entity.</span></span> <span data-ttu-id="e2fc4-136">يمكن أن تشمل الأمثلة رقم الهاتف أو عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-136">Examples could include a phone number or email address.</span></span> <span data-ttu-id="e2fc4-137">اختر سمة من المحتمل أن تكون فريدة للعميل.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-137">Choose an attribute that is likely to be unique to the customer.</span></span>

   > [!TIP]
   > <span data-ttu-id="e2fc4-138">تجنب المطابقة على أساس سمات نوع النشاط.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-138">Avoid matching on the basis of activity-type attributes.</span></span> <span data-ttu-id="e2fc4-139">وبمعنى آخر، إذا كانت السمة تبدو نشاطًا، فقد تكون معايير سيئة للتطابق معها.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-139">In other words, if an attribute seems to be an activity, then it might be a poor criteria to match by.</span></span>  

   <span data-ttu-id="e2fc4-140">الكيان/الحقل (الثاني) - السمة التي سيتم استخدامها للمطابقة من كيان زوج التطابق الثاني.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-140">Entity/Field (Second) - An attribute that will be used for matching from the second match pair entity.</span></span>

   <span data-ttu-id="e2fc4-141">الضبط - **طريقة الضبط**: تتوفر خيارات الضبط المختلفة للسمات المحددة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-141">Normalize - **Normalization method**: Various normalization options are available for the selected attributes.</span></span> <span data-ttu-id="e2fc4-142">على سبيل المثال، إزالة علامات الترقيم أو إزالة المسافات</span><span class="sxs-lookup"><span data-stu-id="e2fc4-142">For example, removing punctuation or removing spaces</span></span>

   <span data-ttu-id="e2fc4-143">بالنسبة لضبط سم المؤسسة (معاينة)، يمكنك أيضًا تحديد **نوع (هاتف، اسم، مؤسسة)**</span><span class="sxs-lookup"><span data-stu-id="e2fc4-143">For Organization name normalization (Preview), you can also select **Type (Phone, Name, Organization)**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2fc4-144">![الضبط-B2B](media/match-normalization-b2b.png "الضبط-B2B")</span><span class="sxs-lookup"><span data-stu-id="e2fc4-144">![Normalization-B2B](media/match-normalization-b2b.png "Normalization-B2B")</span></span>

   <span data-ttu-id="e2fc4-145">مستوي الدقة-مستوى الدقة الذي سيتم استخدامه لهذا الشرط.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-145">Precision level - The level of precision that will be used for this condition.</span></span> <span data-ttu-id="e2fc4-146">يمكن أن يكون لتحديد مستوى الدقة لشرط المطابقة نوعين: **أساسي** و **مخصص**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-146">Setting a precision level for a match condition can have two types: **Basic** and **Custom**.</span></span>  
   - <span data-ttu-id="e2fc4-147">أساسي: يوفر لك أربعة خيارات للاختيار من بينها: منخفض، متوسط​، مرتفع، ودقيق.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-147">Basic: Provides you with four options to select from: Low, Medium, High, and Exact.</span></span> <span data-ttu-id="e2fc4-148">حدد **دقيق** لمطابقة السجلات التي تتطابق بنسبة 100 بالمائة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-148">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="e2fc4-149">حدد أحد المستويات الأخرى لمطابقة السجلات غير المتطابقة بنسبة 100 بالمائة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-149">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
   - <span data-ttu-id="e2fc4-150">مخصص: استخدم شريط التمرير لتحديد النسبة المئوية المخصصة التي تحتاج السجلات إلى مطابقتها أو إدخال قيمة في الحقل **مخصص** .</span><span class="sxs-lookup"><span data-stu-id="e2fc4-150">Custom: Use the slider to define the custom percentage that records need to match or enter a value in the **Custom** field.</span></span> <span data-ttu-id="e2fc4-151">سوف يقوم هذا النظام بمطابقة السجلات التي تتجاوز هذا الحد فقط كأزواج مُطابقة مُدمجة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-151">The system will only match records passing this threshold as conflated match pairs.</span></span> <span data-ttu-id="e2fc4-152">تكون القيم الموجودة في شريط التمرير بين 0 و 1.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-152">Values on the slider are between 0 and 1.</span></span> <span data-ttu-id="e2fc4-153">وبالتالي فإن 0.64 تمثل 64%.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-153">So 0.64 represents 64 percent.</span></span>

3. <span data-ttu-id="e2fc4-154">حدد **تم** لحفظ القاعدة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-154">Select **Done** to save the rule.</span></span>

### <a name="add-multiple-conditions"></a><span data-ttu-id="e2fc4-155">إضافة شروط متعددة</span><span class="sxs-lookup"><span data-stu-id="e2fc4-155">Add multiple conditions</span></span>

<span data-ttu-id="e2fc4-156">لمطابقة الكيانات الخاصة بك فقط إذا تم استيفاء شروط متعددة، أضف المزيد من الشروط المرتبطة من خلال عامل التشغيل AND.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-156">To match your entities only if multiple conditions are met, add more conditions that are linked through an AND operator.</span></span>

1. <span data-ttu-id="e2fc4-157">في جزء **تحرير القاعدة** ، حدد **إضافة شرط**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-157">In the **Edit rule** pane, select **Add condition**.</span></span> <span data-ttu-id="e2fc4-158">يمكنك أيضًا حذف الشروط عن طريق تحديد زر الإزالة الموجود بجوار شرط موجود.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-158">You can also delete conditions by selecting the remove button next to an existing condition.</span></span>

2. <span data-ttu-id="e2fc4-159">حدد **تم** لحفظ القاعدة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-159">Select **Done** so save the rule.</span></span>

## <a name="add-multiple-rules"></a><span data-ttu-id="e2fc4-160">إضافة قواعد متعددة</span><span class="sxs-lookup"><span data-stu-id="e2fc4-160">Add multiple rules</span></span>

<span data-ttu-id="e2fc4-161">ينطبق كل شرط على زوج واحد من السمات، في حين تمثل القواعد مجموعات من الشروط.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-161">Each condition applies to a single pair of attributes, while rules represent sets of conditions.</span></span> <span data-ttu-id="e2fc4-162">لجعل الكيانات الخاصة بك متطابقة بمجموعات مختلفة من السمات، يمكنك إضافة المزيد من القواعد.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-162">To have your entities matched by different sets of attributes, you can add more rules.</span></span>

1. <span data-ttu-id="e2fc4-163">في رؤى الجمهور، انتقل إلى **البيانات** > **توحيد** > **مطابقة**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-163">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

2. <span data-ttu-id="e2fc4-164">حدد الكيان الذي تريد تحديثه وحدد **إضافة قواعد**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-164">Select the entity you want to update and select **Add rules**.</span></span>

3. <span data-ttu-id="e2fc4-165">اتبع الإجراء كما هو موضح في [تعريف القواعد لزوج المطابقة الأول](#define-rules-for-your-first-match-pair).</span><span class="sxs-lookup"><span data-stu-id="e2fc4-165">Follow the procedure as outlined in [Define rules for your first match pair](#define-rules-for-your-first-match-pair).</span></span>

> [!NOTE]
> <span data-ttu-id="e2fc4-166">يُعد ترتيب القواعد أمرًا هامًا.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-166">The rule order matters.</span></span> <span data-ttu-id="e2fc4-167">تحاول خوارزمية المطابقة إجراء عملية التطابق على أساس القاعدة الأولى وتستمر إلي القاعدة الثانية فقط إذا لم يتم تحديد أي تطابقات تحت القاعدة الأولى.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-167">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified under the first rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="e2fc4-168">تعريف إلغاء التكرار على كيان مطابقة</span><span class="sxs-lookup"><span data-stu-id="e2fc4-168">Define deduplication on a match entity</span></span>

<span data-ttu-id="e2fc4-169">بالإضافة إلى تحديد قواعد المطابقة عبر الكيانات كما هو موضح في الأقسام السابقة، يمكنك أيضًا تحديد قواعد إلغاء التكرار.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-169">Along with specifying cross entity matching rules as outlined in the above sections, you can also specify deduplications rules.</span></span> <span data-ttu-id="e2fc4-170">*إلغاء التكرار* هو عملية.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-170">*Deduplication* is a process.</span></span> <span data-ttu-id="e2fc4-171">تحدد هذه العملية السجلات المكررة، وتدمجها في سجل واحد، وتربط جميع السجلات المصدر بهذا السجل المدمج باستخدام معرفات بديلة للسجل المدمج.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-171">It identifies duplicate records, merges them into one record, and links all the source records to this merged record with alternate IDs to the merged record.</span></span>

<span data-ttu-id="e2fc4-172">بعد التعرّف على سجل مكرر، سيتم استخدام هذا السجل في عملية المطابقة عبر الكيانات.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-172">After a deduplicated record is identified, that record will be used in the cross-entity matching process.</span></span> <span data-ttu-id="e2fc4-173">يتم تطبيق إلغاء التكرار على مستوى الكيان ويمكن تطبيقه على كل كيان مستخدم في عملية المطابقة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-173">Deduplication is implemented at the entity level and can be applied to every entity used in the Match process.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="e2fc4-174">إضافة قواعد إلغاء التكرار</span><span class="sxs-lookup"><span data-stu-id="e2fc4-174">Add deduplication rules</span></span>

1. <span data-ttu-id="e2fc4-175">في رؤى الجمهور، انتقل إلى **البيانات** > **توحيد** > **مطابقة**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-175">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="e2fc4-176">في قسم **التكرارات المدمجة**‬، حدد **تعيين الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-176">In the **Merged duplicates** section, select **Set entities**.</span></span>

1. <span data-ttu-id="e2fc4-177">في قسم **تفضيلات الدمج**، حدد الكيانات التي تريد تطبيق إلغاء التكرار عليها.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-177">In the **Merge preferences** section, select the entities you want to apply deduplication to.</span></span>

1. <span data-ttu-id="e2fc4-178">حدد طريقة دمج السجلات المكررة واختر أحد خيارات الدمج الثلاثة التالية:</span><span class="sxs-lookup"><span data-stu-id="e2fc4-178">Specify how to merge the duplicate records and choose one of three merge options:</span></span>
   - <span data-ttu-id="e2fc4-179">*الأكثر تعبئة*: لتعريف السجل الأكثر تعبئة بالسمات كالسجل الفائز.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-179">*Most filled*: Identifies the record with most filled attributes as the winner record.</span></span> <span data-ttu-id="e2fc4-180">هذا هو خيار الدمج الافتراضي.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-180">This is the default merge option.</span></span>
   - <span data-ttu-id="e2fc4-181">*الأحدث*: لتعريف السجل الفائز بالاستناد إلى الأكثر حداثة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-181">*Most recent*: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="e2fc4-182">يتطلب حقل تاريخ أو حقلاً رقميًا لتعريف الحداثة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-182">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="e2fc4-183">*الأقل حداثة*: لتعريف السجل الفائز بالاستناد إلى الأقل حداثة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-183">*Least recent*: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="e2fc4-184">يتطلب حقل تاريخ أو حقلاً رقميًا لتعريف الحداثة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-184">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2fc4-185">![الخطوة 1 لقواعد إلغاء التكرار](media/match-selfconflation.png "الخطوة 1 لقواعد إلغاء التكرار")</span><span class="sxs-lookup"><span data-stu-id="e2fc4-185">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="e2fc4-186">بعد تحديد الكيانات وتعيين تفضيلات الدمج لها، حدد **إنشاء قاعدة جديدة** لتحديد قواعد إلغاء التكرار على مستوى الكيان.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-186">Once the entities are selected and their merge preference is set, select **Create new rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="e2fc4-187">يسرد الخيار **تحديد الحقل** كافة الحقول المتوفرة من الكيان الذي ترغب في إلغاء تكرار البيانات المصدر عليه.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-187">**Select field** lists all the available fields from that entity you want to deduplicate source data on.</span></span>
   - <span data-ttu-id="e2fc4-188">حدد إعدادات التسوية والدقة بطريقه مماثلة لما هو محدد في المطابقة عبر الكيانات.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-188">Specify the normalization and precision settings in similar way as specified in the cross entity matching.</span></span>
   - <span data-ttu-id="e2fc4-189">يمكنك تحديد شروط إضافية عن طريق تحديد **إضافة شرط**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-189">You can define additional conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2fc4-190">![الخطوة 2 لقواعد إلغاء التكرار](media/match-selfconflation-rules.png "الخطوة 2 لقواعد إلغاء التكرار")</span><span class="sxs-lookup"><span data-stu-id="e2fc4-190">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="e2fc4-191">يمكنك إنشاء قواعد إلغاء تكرار متعددة لكيان.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-191">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="e2fc4-192">يؤدي تشغيل عملية المطابقة الآن إلى تجميع السجلات استنادًا إلى الشروط المحددة في قواعد إلغاء التكرار.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-192">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="e2fc4-193">بعد تجميع السجلات، يتم تطبيق سياسة الدمج لتحديد السجل الفائز.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-193">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="e2fc4-194">ثم يتم تمرير هذا السجل الفائز إلى المطابقة عبر الكيانات.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-194">This winner record is then passed on to the cross-entity matching.</span></span>

1. <span data-ttu-id="e2fc4-195">ستقوم قواعد المطابقة المخصصة التي تم تعريفها للمطابقة دائمًا وعدم المطابقة إطلاقًا بإبطال قواعد إلغاء التكرار.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-195">Any custom match rules defined for always match and never match overrule deduplication rules.</span></span> <span data-ttu-id="e2fc4-196">إذا قامت قاعدة إلغاء التكرار بتعريف سجلات مطابقة، وإذا تم تعيين قاعدة مطابقة مخصصة لعدم مطابقة هذه السجلات إطلاقًا، فلن تتم مطابقة هذين السجلين.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-196">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="e2fc4-197">بعد تشغيل عملية المطابقة، سترى إحصاءات إلغاء التكرار.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-197">After running the match process, you will see the deduplication stats.</span></span>
   
> [!NOTE]
> <span data-ttu-id="e2fc4-198">تحديد قواعد إلغاء التكرار غير إلزامي.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-198">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="e2fc4-199">إذا لم يتم تكوين مثل هذه القواعد، فسيتم تطبيق القواعد المحددة من قبل النظام.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-199">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="e2fc4-200">إنها تقوم بطي جميع السجلات التي تشارك في مجموعة القيم نفسها (مطابقة تامة) من المفتاح الأساسي والحقول في قواعد المطابقة في سجل واحد قبل تمرير بيانات الكيان إلى المطابقة عبر الكيانات للأداء المحسن وصحة النظام.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-200">They collapse all records that share the same value combination (exact match) from primary key and the fields in the matching rules into a single record before passing the entity data to cross-entity matching for enhanced performance and system sanity.</span></span>

## <a name="run-your-match-order"></a><span data-ttu-id="e2fc4-201">تشغيل ترتيب المطابقة الخاص بك</span><span class="sxs-lookup"><span data-stu-id="e2fc4-201">Run your match order</span></span>

<span data-ttu-id="e2fc4-202">بعد تعريف قواعد المطابقة، بما في ذلك المطابقة عبر الكيانات وقواعد إلغاء التكرتر، يمكنك تشغيل أمر المطابقة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-202">After defining the match rules, including cross-entity matching and deduplication rules, you can run the match order.</span></span> <span data-ttu-id="e2fc4-203">في صفحة **المطابقة** ، قم بتحديد **تشغيل** لبدء العملية.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-203">On the **Match** page, select **Run** to start the process.</span></span> <span data-ttu-id="e2fc4-204">قد تستغرق خوارزمية المطابقة بعض الوقت للاكتمال.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-204">The matching algorithm might take some time to complete.</span></span> <span data-ttu-id="e2fc4-205">لا يمكنك تغيير الخصائص في صفحة **المطابقة** حتى تكتمل عملية المطابقة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-205">You can't change properties on the **Match** page until the match process completes.</span></span> <span data-ttu-id="e2fc4-206">سوف تجد كيان ملف تعريف العميل الموحد الذي تم إنشاؤه في صفحة **الكيانات** .</span><span class="sxs-lookup"><span data-stu-id="e2fc4-206">You'll find the unified customer profile entity that was created on the **Entities** page.</span></span> <span data-ttu-id="e2fc4-207">يسمى كيان العميل الموحد **ConflationMatchPairs : CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-207">Your unified customer entity is called **ConflationMatchPairs:CustomerInsights**.</span></span>

<span data-ttu-id="e2fc4-208">لإجراء تغييرات إضافية وإعادة تشغيل الخطوة، فإنه يمكنك إلغاء مطابقة قيد التقدم.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-208">To make additional changes and rerun the step, you can cancel a match in progress.</span></span> <span data-ttu-id="e2fc4-209">حدد النص **جار التحديث...** وحدد **إلغاء المهمة** في أسفل الجزء الجانبي الذي يظهر.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-209">Select the **Refreshing ...** text and select **Cancel job** at the bottom of the side pane that appears.</span></span>

<span data-ttu-id="e2fc4-210">عند اكتمال عملية المطابقة، سيتم تغيير النص **جار التحديث...** إلى **ناجح** ويمكنك استخدام كافة وظائف الصفحة مرة أخرى.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-210">When the match process is complete, the **Refreshing ...** text will change to **Successful** and you can use all functionality of the page again.</span></span>

<span data-ttu-id="e2fc4-211">تؤدي عملية المطابقة الأولى إلى إنشاء كيان رئيسي موحد.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-211">The first match process results in the creation of a unified master entity.</span></span> <span data-ttu-id="e2fc4-212">ينتج عن جميع عمليات تشغيل المطابقة اللاحقة توسيع هذا الكيان.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-212">All subsequent match runs result in the expansion of that entity.</span></span>

> [!TIP]
> <span data-ttu-id="e2fc4-213">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-213">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="e2fc4-214">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="e2fc4-214">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="e2fc4-215">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-215">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="e2fc4-216">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-216">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="e2fc4-217">مراجعة المطابقات والتحقق من صحتها</span><span class="sxs-lookup"><span data-stu-id="e2fc4-217">Review and validate your matches</span></span>

<span data-ttu-id="e2fc4-218">قيّم جودة أزواج المطابقة الخاصة بك وقم بتحسينها:</span><span class="sxs-lookup"><span data-stu-id="e2fc4-218">Evaluate the quality of your match pairs and refine it:</span></span>

- <span data-ttu-id="e2fc4-219">في صفحة **المطابقة** ، ستجد إطارين متجانبيين يعرضان رؤى أولية حول بياناتك.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-219">On the **Match** page, you'll find two tiles showing initial insights about your data.</span></span>

  - <span data-ttu-id="e2fc4-220">**العملاء الفريدون**: يوضح عدد ملفات التعريف الفريدة التي حددها النظام.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-220">**Unique customers**: shows the number of unique profiles that the system identified.</span></span>
  - <span data-ttu-id="e2fc4-221">**السجلات المتطابقة**: تعرض عدد التطابقات في جميع أزواج المطابقة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-221">**Matched records**: shows the number of matches across all of your match pairs.</span></span>

- <span data-ttu-id="e2fc4-222">في جدول **ترتيب المطابقة** ، يمكنك تقييم نتائج كل زوج مطابقة عن طريق مقارنة عدد السجلات التي تأتي من كيان زوج المطابقة هذا في مقابل النسبة المئوية للسجلات التي تمت مطابقتها بنجاح.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-222">In the **Match order** table, you can assess the results of each match pair by comparing the number of records that came from this match-pair entity against the percentage of successfully matched records.</span></span>

- <span data-ttu-id="e2fc4-223">في قسم **القواعد** لكيان في جدول **ترتيب المطابقة** ، ستجد النسبة المئوية للسجلات المطابقة بنجاح على مستوى القاعدة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-223">In the **Rules** section of an entity in the **Match order** table, you'll find the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="e2fc4-224">ومن خلال تحديد رمز الجدول بجوار القاعدة، يمكنك عرض كل هذه السجلات على مستوى القاعدة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-224">By selecting the table symbol next to a rule, you can view all these records on the rule level.</span></span> <span data-ttu-id="e2fc4-225">نوصي بمراجعة مجموعة فرعية من السجلات للتحقق من مطابقتها بشكل صحيح.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-225">We recommend that you review a subset of the records to validate that they were matched correctly.</span></span>

- <span data-ttu-id="e2fc4-226">الاختبار باستخدام حدود الدقة المختلفة حول شروطك لتحديد القيمة المثلي.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-226">Experiment with different precision thresholds around your conditions to identify the optimal value.</span></span>

  1. <span data-ttu-id="e2fc4-227">حدد علامة القطع (...) لقاعدة زوج المطابقة التي تريد اختبارها وحدد **تحرير**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-227">Select the ellipsis (...) for the match pair rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="e2fc4-228">حدد الشرط الذي تريد تجربته.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-228">Select the condition that you want to experiment with.</span></span> <span data-ttu-id="e2fc4-229">يتم تمثيل كل معيار بواسطة صف واحد في جزء **قاعدة المطابقة** .</span><span class="sxs-lookup"><span data-stu-id="e2fc4-229">Each criterion is represented by one row in the **Match rule** pane.</span></span>

  3. <span data-ttu-id="e2fc4-230">ما ستراه في صفحة **معاينة المعايير** يعتمد على مستوى الدقة الذي حددته لأحد الشروط.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-230">What you'll see on the **Criteria preview** page depends on the precision level you've selected for a condition.</span></span> <span data-ttu-id="e2fc4-231">ابحث عن عدد السجلات المتطابقة وغير المتطابقة للشرط المحدد.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-231">Find the number of matched and unmatched records for the selected condition.</span></span>

     <span data-ttu-id="e2fc4-232">احصل على فهم أغني لتأثيرات مستويات الحد المختلفة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-232">Get a rich understanding of the effects of different threshold levels.</span></span> <span data-ttu-id="e2fc4-233">يمكنك مقارنة عدد السجلات التي سيتم مطابقتها تحت كل مستوى من المستويات، وعرض السجلات الموجودة تحت كل خيار.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-233">You can compare how many records will be matched under each of the threshold levels, and view the records under each option.</span></span> <span data-ttu-id="e2fc4-234">حدد كل من الإطارات المتجانبة وقم بمراجعة البيانات الموجودة في قسم الجدول.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-234">Select each of the tiles and review the data in the table section.</span></span>

## <a name="optimize-your-matches"></a><span data-ttu-id="e2fc4-235">تحسين المطابقات الخاصة بك</span><span class="sxs-lookup"><span data-stu-id="e2fc4-235">Optimize your matches</span></span>

<span data-ttu-id="e2fc4-236">قم بزيادة الجودة عن طريق إعادة تكوين بعض معلمات المطابقة الخاصة بك:</span><span class="sxs-lookup"><span data-stu-id="e2fc4-236">Increase the quality by reconfiguring some of your match parameters:</span></span>

- <span data-ttu-id="e2fc4-237">**قم بتغيير ترتيب المطابقة** بتحديد **تحرير** وقم بتغيير حقول ترتيب المطابقة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-237">**Change the match order** by selecting **Edit** and change the match order fields.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e2fc4-238">![تحرير بيانات ترتيب المطابقة](media/configure-data-match-order-edit.png "تحرير ترتيب مطابقة البيانات")</span><span class="sxs-lookup"><span data-stu-id="e2fc4-238">![Edit data match order](media/configure-data-match-order-edit.png "Edit data match order")</span></span>

- <span data-ttu-id="e2fc4-239">**قم بتغيير ترتيب القواعد** إذا قمت بتعريف قواعد متعددة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-239">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="e2fc4-240">يمكنك إعادة ترتيب قواعد المطابقة بتحديد خيارات **تحريك لأعلي** و **تحريك لأسفل** في شبكة قواعد المطابقة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-240">You can reorder the match rules by selecting the **Move Up** and **Move Down** options in the match rules grid.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e2fc4-241">![تغيير ترتيب القاعدة](media/configure-data-change-rule-order.png "تغيير ترتيب القاعدة")</span><span class="sxs-lookup"><span data-stu-id="e2fc4-241">![Change rule order](media/configure-data-change-rule-order.png "Change rule order")</span></span>

- <span data-ttu-id="e2fc4-242">**تكرار القواعد الخاصة بك** إذا قمت بتعريف قاعدة مطابقة وكنت ترغب في إنشاء قاعدة مشابهه مع إجراء بعض التعديلات.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-242">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications.</span></span> <span data-ttu-id="e2fc4-243">قم بذلك عن طريق تحديد **تكرار**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-243">Do so by selecting **Duplicate**.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="e2fc4-244">![تكرار قاعدة](media/configure-data-duplicate-rule.png "تكرار قاعدة")</span><span class="sxs-lookup"><span data-stu-id="e2fc4-244">![Duplicate a rule](media/configure-data-duplicate-rule.png "Duplicate a rule")</span></span>

- <span data-ttu-id="e2fc4-245">**تحرير القواعد الخاصة بك** من خلال تحديد رمز **تحرير** .</span><span class="sxs-lookup"><span data-stu-id="e2fc4-245">**Edit your rules** by selecting the **Edit** symbol.</span></span> <span data-ttu-id="e2fc4-246">يمكنك أيضًا إجراء التغييرات التالية:</span><span class="sxs-lookup"><span data-stu-id="e2fc4-246">You can apply the following changes:</span></span>

  - <span data-ttu-id="e2fc4-247">تغيير السمات لشرط: حدد سمات جديدة في صف الشرط المحدد.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-247">Change attributes for a condition: Select new attributes within the specific condition row.</span></span>
  - <span data-ttu-id="e2fc4-248">تغيير الحد لشرط ما: قم بضبط ‏‫شريط تمرير الدقة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-248">Change the threshold for a condition: Adjust the precision slider.</span></span>
  - <span data-ttu-id="e2fc4-249">تغيير طريقه الضبط لشرط ما: قم بتحديث طريقه الضبط.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-249">Change the normalization method for a condition: Update the normalization method.</span></span>

## <a name="specify-your-custom-match-records"></a><span data-ttu-id="e2fc4-250">تحديد سجلات المطابقة المخصصة الخاصة بك</span><span class="sxs-lookup"><span data-stu-id="e2fc4-250">Specify your custom match records</span></span>

<span data-ttu-id="e2fc4-251">يمكنك تحديد الشروط التي يجب أن تتطابق معها سجلات معينة دائمًا أو لا تطابقها أبدًا.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-251">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="e2fc4-252">يمكن تحميل هذه القواعد بشكل مجمع إلى عملية المطابقة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-252">These rules can be uploaded in bulk to the match process.</span></span>

1. <span data-ttu-id="e2fc4-253">حدد خيار **المطابقة المخصصة** علي شاشة **ترتيب المطابقة** .</span><span class="sxs-lookup"><span data-stu-id="e2fc4-253">Select the **Custom match** option on the **Match order** screen.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2fc4-254">![إنشاء مطابقة مخصصة](media/custom-match-create.png "إنشاء مطابقة مخصصة")</span><span class="sxs-lookup"><span data-stu-id="e2fc4-254">![Create a custom match](media/custom-match-create.png "Create a custom match")</span></span>

2. <span data-ttu-id="e2fc4-255">إذا لم تكن لديك كيانات تم تحميلها، سيظهر لك مربع حوار **مطابقة مخصصة** جديد يتطلب منك تعبئة بعض التفاصيل.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-255">If you have no uploaded entities, you'll see a new **Custom match** dialog box that requires you to fill in some details.</span></span> <span data-ttu-id="e2fc4-256">إذا كنت قد قمت بتوفير هذه التفاصيل في وقت سابق، فانتقل إلى الخطوة رقم 8.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-256">If you've provided these details earlier, skip to step 8.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2fc4-257">![مربع حوار مطابقة مخصصة جديد](media/custom-match-new-dialog-box.png "مربع حوار مطابقة مخصصة جديد")</span><span class="sxs-lookup"><span data-stu-id="e2fc4-257">![New custom match dialog box](media/custom-match-new-dialog-box.png "New custom match dialog box")</span></span>

3. <span data-ttu-id="e2fc4-258">حدد **‏‫ملء القالب‬** للحصول على ملف قالب يمكنه تحديد السجلات التي يجب أن تتطابق معها الكيانات دائمًا أو لا تطابقها أبدًا.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-258">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="e2fc4-259">سوف تحتاج إلى ملء سجلات "مطابقة دائمًا" بشكل منفصل وسجلات "عدم المطابقة مطلقًا" في ملفين مختلفين.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-259">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

4. <span data-ttu-id="e2fc4-260">يحتوي القالب على حقول لتحديد الكيان وقيم مفتاح الكيان الأساسي المطلوب استخدامها في المطابقة المخصصة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-260">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="e2fc4-261">على سبيل المثال، إذا كنت تريد أن يكون المفتاح الأساسي 12345 من كيان المبيعات مطابقًا دائمًا للمفتاح الأساسي 34567 من كيان جهة الاتصال، فستحتاج إلى تحديد ما يلي:</span><span class="sxs-lookup"><span data-stu-id="e2fc4-261">For example, if you want primary key 12345 from Sales entity to always match with primary key 34567 from Contact entity, you'll need to specify as follows:</span></span>
    - <span data-ttu-id="e2fc4-262">الكيان 1: المبيعات</span><span class="sxs-lookup"><span data-stu-id="e2fc4-262">Entity1: Sales</span></span>
    - <span data-ttu-id="e2fc4-263">مفتاح الكيان 1: 12345</span><span class="sxs-lookup"><span data-stu-id="e2fc4-263">Entity1Key: 12345</span></span>
    - <span data-ttu-id="e2fc4-264">الكيان 2: جهة الاتصال</span><span class="sxs-lookup"><span data-stu-id="e2fc4-264">Entity2: Contact</span></span>
    - <span data-ttu-id="e2fc4-265">مفتاح الكيان 2: 34567</span><span class="sxs-lookup"><span data-stu-id="e2fc4-265">Entity2Key: 34567</span></span>

   <span data-ttu-id="e2fc4-266">يمكن لنفس ملف القالب تحديد سجلات المطابقة المخصصة من كيانات متعددة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-266">The same template file can specify custom match records from multiple entities.</span></span>

5. <span data-ttu-id="e2fc4-267">بعد إضافة جميع التجاوزات التي تريد تطبيقها ، احفظ ملف القالب.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-267">After adding all the overrides you want to apply, save the template file.</span></span>

<span data-ttu-id="e2fc4-268">6.انتقل إلى **البيانات** > **مصادر البيانات** لاستيعاب ملفات القوالب ككيانات جديدة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-268">6.Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="e2fc4-269">بمجرد تناولها، يمكنك استخدامها لتحديد تكوين مطابقة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-269">Once ingested, you can use them to specify the Match configuration.</span></span>

7. <span data-ttu-id="e2fc4-270">بعد تحميل الملفات والكيانات المتوفرة، حدد خيار **المطابقة المخصصة** مرة أخرى.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-270">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="e2fc4-271">ستري خيارات لتحديد الكيانات التي ترغب في تضمينها.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-271">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="e2fc4-272">حدد الكيانات المطلوبة من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-272">Select the required entities from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e2fc4-273">![تجاوزات مطابقة مخصصة](media/custom-match-overrides.png "تجاوزات مطابقة مخصصة")</span><span class="sxs-lookup"><span data-stu-id="e2fc4-273">![Custom match overrides](media/custom-match-overrides.png "Custom match overrides")</span></span>

8. <span data-ttu-id="e2fc4-274">حدد الكيانات التي ترغب في استخدامها لـ **المطابقة الدائمة** و **عدم المطابقة مطلقًا**، وقم بتحديد **تم**.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-274">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

9. <span data-ttu-id="e2fc4-275">حدد **حفظ** في صفحة **المطابقة** لتكوين المطابقة المخصصة التي قمت بإعدادها.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-275">Select **Save** on the **Match** page for the custom match configuration you just set up.</span></span>

10. <span data-ttu-id="e2fc4-276">حدد **تشغيل** علي صفحة **المطابقة** لبدء عمليه المطابقة، وسيتم وضع تكوين المطابقة المخصصة في حيز التنفيذ.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-276">Select **Run** on the **Match** page to start the matching process, and the custom match configuration will be taken into effect.</span></span> <span data-ttu-id="e2fc4-277">يتم تجاوز أي قواعد مطابقة للنظام بواسطة مجموعة التكوين.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-277">Any system matched rules are overridden by the configuration set.</span></span>

11. <span data-ttu-id="e2fc4-278">بمجرد اكتمال المطابقة، يمكنك التحقق من الكيان **ConflationMatchPair** لتأكيد تطبيق التجاوزات في مطابقات الدمج.</span><span class="sxs-lookup"><span data-stu-id="e2fc4-278">Once the matching is complete, you can verify the **ConflationMatchPair** entity to confirm that the overrides are applied in the conflation matches.</span></span>

## <a name="next-step"></a><span data-ttu-id="e2fc4-279">الخطوة التالية</span><span class="sxs-lookup"><span data-stu-id="e2fc4-279">Next step</span></span>

<span data-ttu-id="e2fc4-280">بعد إكمال عملية المطابقة لزوج تطابق واحد على الأقل، فقد تتمكن من حل التناقضات المحتملة في بياناتك من خلال الانتقال إلى موضوع [**دمج**](merge-entities.md) .</span><span class="sxs-lookup"><span data-stu-id="e2fc4-280">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>
