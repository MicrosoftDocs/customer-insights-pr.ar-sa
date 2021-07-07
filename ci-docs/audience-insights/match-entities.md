---
title: مطابقة الكيانات لتوحيد البيانات
description: مطابقة الكيانات لإنشاء ملفات تعريف العملاء الموحدة.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 50b11e7d6f62d7a25eb25a0f2b1c4ad7d859def1
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306012"
---
# <a name="match-entities"></a><span data-ttu-id="32744-103">تطابق الكيانات</span><span class="sxs-lookup"><span data-stu-id="32744-103">Match entities</span></span>

<span data-ttu-id="32744-104">تحدد مرحلة المطابقة كيفية دمج مجموعات البيانات الخاصة بك في مجموعة بيانات موحدة لملف تعريف العميل.</span><span class="sxs-lookup"><span data-stu-id="32744-104">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="32744-105">بعد إكمال [خطوة التعيين](map-entities.md) في عملية توحيد البيانات، تصبح جاهزًا لمطابقة الكيانات.</span><span class="sxs-lookup"><span data-stu-id="32744-105">After completing the [map step](map-entities.md) in the data unification process, you're ready to match your entities.</span></span> <span data-ttu-id="32744-106">تتطلب مرحلة المطابقة كيانين معيّنين على الأقل.</span><span class="sxs-lookup"><span data-stu-id="32744-106">The match phase requires at least two mapped entities.</span></span>

<span data-ttu-id="32744-107">تتكون صفحة المطابقة من ثلاثة أقسام:</span><span class="sxs-lookup"><span data-stu-id="32744-107">The match page consists of three sections:</span></span> 
- <span data-ttu-id="32744-108">المقاييس الأساسية التي تلخص عدد السجلات المتطابقة</span><span class="sxs-lookup"><span data-stu-id="32744-108">Key metrics that summarize the number of matched records</span></span>
- <span data-ttu-id="32744-109">ترتيب المطابقة وقواعد المطابقة عبر الكيانات</span><span class="sxs-lookup"><span data-stu-id="32744-109">Match order and rules for cross-entity matching</span></span>
- <span data-ttu-id="32744-110">قواعد إلغاء تكرار الكيانات المتطابقة</span><span class="sxs-lookup"><span data-stu-id="32744-110">Rules for deduplication of match entities</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="32744-111">حدد ترتيب المطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-111">Specify the match order</span></span>

<span data-ttu-id="32744-112">انتقل إلى **البيانات** > **توحيد** > **مطابقة** وحدد **تعيين الترتيب** لبدء مرحلة المطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-112">Go to **Data** > **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="32744-113">يقوم كل تطابق بتوحيد كيانين أو أكثر في كيان واحد مدمج.</span><span class="sxs-lookup"><span data-stu-id="32744-113">Each match unifies two or more entities into a single, consolidated entity.</span></span> <span data-ttu-id="32744-114">وفي الوقت نفسه، يحتفظ بسجلات العملاء الفريدة.</span><span class="sxs-lookup"><span data-stu-id="32744-114">At the same time, it keeps the unique customer records.</span></span> <span data-ttu-id="32744-115">على سبيل المثال، قمنا باختيار كيانين: **eCommerce:eCommerceContacts** ككيان أساسي و **LoyaltyScheme:loyCustomers** ككيان ثانٍ.</span><span class="sxs-lookup"><span data-stu-id="32744-115">For example, we selected two entities: **eCommerce:eCommerceContacts** as the primary entity and **LoyaltyScheme:loyCustomers** as second entity.</span></span> <span data-ttu-id="32744-116">يحدد ترتيب الكيانات الترتيب الذي سيحاول النظام من خلاله مطابقة السجلات.</span><span class="sxs-lookup"><span data-stu-id="32744-116">The order of the entities specifies in which order the system will try to match the records.</span></span>

:::image type="content" source="media/match-page.png" alt-text="لقطة شاشة لصفحة المطابقة في منطقة التوحيد لعملية توحيد البيانات.":::
  
<span data-ttu-id="32744-118">تتم مطابقة الكيان الأساسي *eCommerce:eCommerceContacts* مع الكيان التالي *LoyaltyScheme:loyCustomers*.</span><span class="sxs-lookup"><span data-stu-id="32744-118">The primary entity *eCommerce:eCommerceContacts* is matched with the next entity *LoyaltyScheme:loyCustomers*.</span></span> <span data-ttu-id="32744-119">تتطابق مجموعة البيانات التي تنتج عن خطوة المطابقة الأولى مع الكيان التالي إذا كان لديك أكثر من كيانين.</span><span class="sxs-lookup"><span data-stu-id="32744-119">The dataset that results from the first match step is matched with the following entity if you have more than two entities.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32744-120">سيعمل الكيان الذي تختاره ككيان أساسي بمثابة أساس لمجموعة بيانات ملفات التعريف الموحدة.</span><span class="sxs-lookup"><span data-stu-id="32744-120">The entity that you choose as your primary entity will serve as the basis for your unified profiles dataset.</span></span> <span data-ttu-id="32744-121">ستتم إضافة الكيانات الإضافية المحددة خلال مرحلة المطابقة إلى هذا الكيان.</span><span class="sxs-lookup"><span data-stu-id="32744-121">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="32744-122">لا يعني ذلك أن الكيان الموحد سيتضمن *جميع* البيانات المتضمنة في هذا الكيان.</span><span class="sxs-lookup"><span data-stu-id="32744-122">This doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="32744-123">هناك اعتبارين يمكنهم مساعدتك في اختيار التسلسل الهرمي للكيانات الخاصة بك:</span><span class="sxs-lookup"><span data-stu-id="32744-123">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="32744-124">اختر الكيان الذي تتوفر فيه بيانات ملف التعريف الأكثر اكتمالاً وموثوقية حول عملائك ككيان أساسي.</span><span class="sxs-lookup"><span data-stu-id="32744-124">Choose the entity with the most complete and reliable profile data about your customers as primary entity.</span></span>
> - <span data-ttu-id="32744-125">اختر الكيان الذي لديه العديد من السمات المشتركة مع الكيانات الأخرى (على سبيل المثال، الاسم أو رقم الهاتف أو عنوان البريد الإلكتروني) ككيان أساسي.</span><span class="sxs-lookup"><span data-stu-id="32744-125">Choose the entity that hast several attributes in common with other entities (for example, name, phone number, or email address) as primary entity.</span></span>

<span data-ttu-id="32744-126">بعد تحديد ترتيب المطابقة، سترى أزواج المطابقة المحددة في القسم **تفاصيل السجلات المتطابقة‬** في **البيانات** > **توحيد** > **مطابقة‬**.</span><span class="sxs-lookup"><span data-stu-id="32744-126">After specifying the match order, you'll see the defined match pairs in the **Matched records details** section on **Data** > **Unify** > **Match**.</span></span> <span data-ttu-id="32744-127">ستكون المقاييس الأساسية فارغة إلى أن تكتمل عملية المطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-127">The key metrics will be empty until the match process completes.</span></span>

## <a name="define-rules-for-match-pairs"></a><span data-ttu-id="32744-128">تحديد قواعد أزواج المطابقة</span><span class="sxs-lookup"><span data-stu-id="32744-128">Define rules for match pairs</span></span>

<span data-ttu-id="32744-129">تحدد قواعد المطابقة المنطق الذي سيتم من خلاله مطابقة زوج معين من الكيانات.</span><span class="sxs-lookup"><span data-stu-id="32744-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

<span data-ttu-id="32744-130">يشير تحذير **يحتاج قواعد** إلى جانب اسم كيان إلى عدم تحديد قاعدة مطابقة لزوج مطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-130">The **Needs rules** warning next to an entity name suggests that no match rule is defined for a match pair.</span></span> 

:::image type="content" source="media/match-rule-add.png" alt-text="لقطة شاشة لقسم تفاصيل السجلات المتطابقة‬ مع عنصر تحكم لإضافة القواعد التي تم تمييزها.":::

1. <span data-ttu-id="32744-132">حدد **إضافة قواعد** ضمن كيان في القسم **تفاصيل السجلات المتطابقة** لتحديد قواعد المطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-132">Select **Add rules** under an entity in the **Matched records details** section to define match rules.</span></span>

1. <span data-ttu-id="32744-133">في الجزء **إنشاء قاعدة**، كوّن شروط القاعدة.</span><span class="sxs-lookup"><span data-stu-id="32744-133">In the **Create rule** pane, configure the conditions for the rule.</span></span>

   :::image type="content" source="media/match-rule-conditions.png" alt-text="لقطة شاشة لقاعدة مطابقة مفتوحة مع إضافة شروط.":::

   - <span data-ttu-id="32744-135">**الكيان/الحقل (الصف الأول)**: اختر كيانًا ذا صلة وسمة لتحديد خاصية السجل التي من المحتمل أن تكون فريدة بالنسبة إلى عميل.</span><span class="sxs-lookup"><span data-stu-id="32744-135">**Entity/Field (first row)**: Choose a related entity and an attribute to specify a record property that is likely unique to a customer.</span></span> <span data-ttu-id="32744-136">على سبيل المثال، رقم هاتف أو عنوان بريد إلكتروني.</span><span class="sxs-lookup"><span data-stu-id="32744-136">For example, a phone number or email address.</span></span> <span data-ttu-id="32744-137">تجنب المطابقة حسب السمات من نوع النشاط.</span><span class="sxs-lookup"><span data-stu-id="32744-137">Avoid matching by activity-type attributes.</span></span> <span data-ttu-id="32744-138">على سبيل المثال، من المرجح عدم عثور معرف الشراء على أي مطابقة في أنواع السجلات الأخرى.</span><span class="sxs-lookup"><span data-stu-id="32744-138">For example, a purchase ID will likely find no match in other record types.</span></span>

   - <span data-ttu-id="32744-139">**الكيان/الحقل (الصف الثاني)**: اختر سمة ترتبط بسمة الكيان المحدد في الصف الأول.</span><span class="sxs-lookup"><span data-stu-id="32744-139">**Entity/Field (second row)**: Choose an attribute that relates to the attribute of the entity specified in the first row.</span></span>

   - <span data-ttu-id="32744-140">**تسوية**: حدد من خيارات التسوية التالية للسمات المحددة.</span><span class="sxs-lookup"><span data-stu-id="32744-140">**Normalize**: Select from following normalization options for the selected attributes.</span></span> 
     - <span data-ttu-id="32744-141">مسافة فارغة‬: إزالة كافة المسافات.</span><span class="sxs-lookup"><span data-stu-id="32744-141">Whitespace: Removes all spaces.</span></span> <span data-ttu-id="32744-142">يتحوّل *Hello   World* إلى *HelloWorld*.</span><span class="sxs-lookup"><span data-stu-id="32744-142">*Hello   World* becomes *HelloWorld*.</span></span>
     - <span data-ttu-id="32744-143">الرموز: إزالة كافة الرموز والأحرف الخاصة.</span><span class="sxs-lookup"><span data-stu-id="32744-143">Symbols: Removes all symbols and special characters.</span></span> <span data-ttu-id="32744-144">يتحوّل *Head&Shoulder* إلى *HeadShoulder*.</span><span class="sxs-lookup"><span data-stu-id="32744-144">*Head&Shoulder* becomes *HeadShoulder*.</span></span>
     - <span data-ttu-id="32744-145">تحويل النص إلى أحرف صغيرة: تحويل كل الأحرف إلى أحرف صغيرة.</span><span class="sxs-lookup"><span data-stu-id="32744-145">Text to lower case: Converts all character to lower case.</span></span> <span data-ttu-id="32744-146">يتحوّل *ALL CAPS and Title Case* إلى *all caps and title case*.</span><span class="sxs-lookup"><span data-stu-id="32744-146">*ALL CAPS and Title Case* becomes *all caps and title case*.</span></span>
     - <span data-ttu-id="32744-147">Unicode إلى ASCII: تحويل رموز Unicode إلى أحرف ASCII.</span><span class="sxs-lookup"><span data-stu-id="32744-147">Unicode to ASCII: Converts unicode notation to ASCII characters.</span></span> <span data-ttu-id="32744-148">يتحوّل */u00B2* إلى *2*.</span><span class="sxs-lookup"><span data-stu-id="32744-148">*/u00B2* becomes *2*.</span></span>
     - <span data-ttu-id="32744-149">الأرقام: تحويل أنظمة رقمية أخرى، مثل الأرقام الرومانية، إلى أرقام عربية.</span><span class="sxs-lookup"><span data-stu-id="32744-149">Numerals: Converts other numeral systems, such as Roman numerals, to Arabic numerals.</span></span> <span data-ttu-id="32744-150">يتحوّل *VIII* إلى *8*.</span><span class="sxs-lookup"><span data-stu-id="32744-150">*VIII* becomes *8*.</span></span>
     - <span data-ttu-id="32744-151">الأنواع الدلالية: توحيد الأسماء والمسميات الوظيفية وأرقام الهاتف والعناوين وما إلى ذلك.</span><span class="sxs-lookup"><span data-stu-id="32744-151">Semantic types: Standardizes names, titles, phone numbers, addresses, etc.</span></span> 

   - <span data-ttu-id="32744-152">**الدقة**: تعيين مستوى الدقة لتطبيق هذا الشرط.</span><span class="sxs-lookup"><span data-stu-id="32744-152">**Precision**: Set the level of precision to apply for this condition.</span></span> 
     - <span data-ttu-id="32744-153">**أساسي**: اختر *منخفض* و *متوسط* و *مرتفع* و *دقيق*.</span><span class="sxs-lookup"><span data-stu-id="32744-153">**Basic**: Choose from *Low*, *Medium*, *High*, and *Exact*.</span></span> <span data-ttu-id="32744-154">حدد **دقيق** لمطابقة السجلات التي تتطابق بنسبة 100 بالمائة.</span><span class="sxs-lookup"><span data-stu-id="32744-154">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="32744-155">حدد أحد المستويات الأخرى لمطابقة السجلات غير المتطابقة بنسبة 100 بالمائة.</span><span class="sxs-lookup"><span data-stu-id="32744-155">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
     - <span data-ttu-id="32744-156">**مخصص**: تعيين نسبة مئوية تحتاج السجلات إلى مطابقتها.</span><span class="sxs-lookup"><span data-stu-id="32744-156">**Custom**: Set a percentage that records need to match.</span></span> <span data-ttu-id="32744-157">سيطابق النظام فقط السجلات التي تجتاز هذا الحد.</span><span class="sxs-lookup"><span data-stu-id="32744-157">The system will only match records passing this threshold.</span></span>

1. <span data-ttu-id="32744-158">قدم **اسمًا** للقاعدة.</span><span class="sxs-lookup"><span data-stu-id="32744-158">Provide a **Name** for the rule.</span></span>

1. <span data-ttu-id="32744-159">[أضف المزيد من الشروط](#add-conditions-to-a-rule) أو حدد **تم** لإكمال القاعدة.</span><span class="sxs-lookup"><span data-stu-id="32744-159">[Add more conditions](#add-conditions-to-a-rule) or select **Done** to finalize the rule.</span></span>

1. <span data-ttu-id="32744-160">بشكل اختياري، [أضف المزيد من القواعد](#add-rules-to-a-match-pair).</span><span class="sxs-lookup"><span data-stu-id="32744-160">Optionally, [add more rules](#add-rules-to-a-match-pair).</span></span>

1. <span data-ttu-id="32744-161">حدد **حفظ** لتطبيق التغييرات التي أجريتها.</span><span class="sxs-lookup"><span data-stu-id="32744-161">Select **Save** to apply your changes.</span></span>

### <a name="add-conditions-to-a-rule"></a><span data-ttu-id="32744-162">إضافة شروط إلى قاعدة</span><span class="sxs-lookup"><span data-stu-id="32744-162">Add conditions to a rule</span></span>

<span data-ttu-id="32744-163">لمطابقة الكيانات فقط إذا كانت السمات تفي بشروط متعددة، أضف المزيد من الشروط إلى قاعدة مطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-163">To match entities only if attributes meet multiple conditions, add more conditions to a match rule.</span></span> <span data-ttu-id="32744-164">يتم توصيل الشروط بعامل التشغيل المنطقي AND وبالتالي يتم تنفيذها فقط إذا تم استيفاء جميع الشروط.</span><span class="sxs-lookup"><span data-stu-id="32744-164">Conditions are connected with a logical AND operator and thus only executed if all conditions are met.</span></span>

1. <span data-ttu-id="32744-165">انتقل إلى **البيانات** > **توحيد** > **مطابقة** وحدد **تحرير** على القاعدة التي تريد إضافة الشروط إليها.</span><span class="sxs-lookup"><span data-stu-id="32744-165">Go to **Data** > **Unify** > **Match** and select **Edit** on the rule you want to add conditions to.</span></span>

1. <span data-ttu-id="32744-166">في جزء **تحرير القاعدة** ، حدد **إضافة شرط**.</span><span class="sxs-lookup"><span data-stu-id="32744-166">In the **Edit rule** pane, select **Add condition**.</span></span>

1. <span data-ttu-id="32744-167">حدد **تم** لحفظ القاعدة.</span><span class="sxs-lookup"><span data-stu-id="32744-167">Select **Done** so save the rule.</span></span>

### <a name="add-rules-to-a-match-pair"></a><span data-ttu-id="32744-168">إضافة قواعد إلى زوج مطابقة</span><span class="sxs-lookup"><span data-stu-id="32744-168">Add rules to a match pair</span></span>

<span data-ttu-id="32744-169">تمثل قواعد المطابقة مجموعات من الشروط.</span><span class="sxs-lookup"><span data-stu-id="32744-169">Match rules represent sets of conditions.</span></span> <span data-ttu-id="32744-170">لمطابقة الكيانات حسب الشروط استنادًا إلى سمات متعددة، أضف المزيد من القواعد.</span><span class="sxs-lookup"><span data-stu-id="32744-170">To match entities by conditions based on multiple attributes, add more rules</span></span>

1.  <span data-ttu-id="32744-171">انتقل إلى **البيانات** > **توحيد** > **مطابقة** وحدد **إضافة قاعدة** على الكيان الذي تريد إضافة القواعد إليه.</span><span class="sxs-lookup"><span data-stu-id="32744-171">Go to **Data** > **Unify** > **Match** and select **Add rule** on the entity you want to add rules to.</span></span>

2. <span data-ttu-id="32744-172">اتبع الخطوات في [تحديد قواعد أزواج المطابقة‬](#define-rules-for-match-pairs).</span><span class="sxs-lookup"><span data-stu-id="32744-172">Follow the steps in [Define rules for match pairs](#define-rules-for-match-pairs).</span></span>

> [!NOTE]
> <span data-ttu-id="32744-173">يعتد ترتيب القواعد أمراً مهماً.</span><span class="sxs-lookup"><span data-stu-id="32744-173">The order of rules matters.</span></span> <span data-ttu-id="32744-174">تحاول خوارزمية المطابقة إجراء المطابقة بالاستناد إلى قاعدتك الأولى، وتتابع إلى القاعدة الثانية فقط في حالة عدم تحديد أي مطابقات مع القاعدة الأولى.</span><span class="sxs-lookup"><span data-stu-id="32744-174">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified with the first rule.</span></span>

### <a name="change-the-entity-order-in-match-rules"></a><span data-ttu-id="32744-175">تغيير ترتيب الكيان في قواعد المطابقة</span><span class="sxs-lookup"><span data-stu-id="32744-175">Change the entity order in match rules</span></span>

<span data-ttu-id="32744-176">يمكنك إعادة ترتيب الكيانات لقواعد المطابقة لتغيير الترتيب الذي تتم معالجتها به.</span><span class="sxs-lookup"><span data-stu-id="32744-176">You can reorder entities for match rules to change the order in which they are processed.</span></span> <span data-ttu-id="32744-177">سوف تتم إزالة القواعد التي تكون متضاربة بسبب تغيير الأمر.</span><span class="sxs-lookup"><span data-stu-id="32744-177">Rules that are conflicting because of a changed order will be removed.</span></span> <span data-ttu-id="32744-178">يجب عليك إعادة إنشاء القواعد التي تمت إزالتها باستخدام تكوين محدث.</span><span class="sxs-lookup"><span data-stu-id="32744-178">You have to recreate removed rules with an updated configuration.</span></span>

1. <span data-ttu-id="32744-179">انتقل إلى **البيانات** > **توحيد** > **مطابقة** وحدد **تحرير**.</span><span class="sxs-lookup"><span data-stu-id="32744-179">Go to **Data** > **Unify** > **Match** and select **Edit**.</span></span>

1. <span data-ttu-id="32744-180">من جزء **تحرير القاعدة**، قم بتحديد عنصر تحكم **التحرك لأعلى/لأسفل** أو قم بسحب وإفلات الكيانات لتغيير الترتيب.</span><span class="sxs-lookup"><span data-stu-id="32744-180">In the **Edit rule** pane, select the **Move up/down** control or drag and drop entities to change the order.</span></span>

   :::image type="content" source="media/reorder-match-rules.png" alt-text="الخيارات لتغيير ترتيب معالجة كيانات في مرحلة المطابقة.":::

1. <span data-ttu-id="32744-182">حدد **تم** لحفظ القاعدة.</span><span class="sxs-lookup"><span data-stu-id="32744-182">Select **Done** so save the rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="32744-183">تعريف إلغاء التكرار على كيان مطابقة</span><span class="sxs-lookup"><span data-stu-id="32744-183">Define deduplication on a match entity</span></span>

<span data-ttu-id="32744-184">بالإضافة إلى [قواعد المطابقة عبر الكيانات](#define-rules-for-match-pairs)، يمكنك أيضًا تحديد قواعد إلغاء التكرارات.</span><span class="sxs-lookup"><span data-stu-id="32744-184">In addition to [cross-entity match rules](#define-rules-for-match-pairs), you can also specify deduplications rules.</span></span> <span data-ttu-id="32744-185">عملية *إلغاء التكرار* هي عملية أخرى عند مطابقة السجلات.</span><span class="sxs-lookup"><span data-stu-id="32744-185">*Deduplication* is another process when matching records.</span></span> <span data-ttu-id="32744-186">إنها تحدد السجلات المكررة وتدمجها في سجل واحد.</span><span class="sxs-lookup"><span data-stu-id="32744-186">It identifies duplicate records and merges them into one record.</span></span> <span data-ttu-id="32744-187">ترتبط السجلات المصدر بالسجل المدمج باستخدام معرفات بديلة.</span><span class="sxs-lookup"><span data-stu-id="32744-187">Source records get linked to the merged record with alternate IDs.</span></span>

<span data-ttu-id="32744-188">سيتم استخدام السجلات الملغى تكرارها في عملية المطابقة عبر الكيانات.</span><span class="sxs-lookup"><span data-stu-id="32744-188">Deduplicated records will be used in the cross-entity matching process.</span></span> <span data-ttu-id="32744-189">تحدث عملية إلغاء التكرار على كيانات فردية، ويمكن تكوينها على كل كيان يتم استخدامه في أزواج المطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-189">Deduplication happens on individual entities and can be configured every entity used in match pairs.</span></span>

<span data-ttu-id="32744-190">تحديد قواعد إلغاء التكرار غير إلزامي.</span><span class="sxs-lookup"><span data-stu-id="32744-190">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="32744-191">إذا لم يتم تكوين مثل هذه القواعد، فسيتم تطبيق القواعد المحددة من قبل النظام.</span><span class="sxs-lookup"><span data-stu-id="32744-191">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="32744-192">إنها تجمع كافة السجلات في سجل واحد قبل تمرير بيانات الكيان إلى المطابقة عبر الكيانات للحصول على أداء محسن.</span><span class="sxs-lookup"><span data-stu-id="32744-192">They combine all records into a single record before passing the entity data to cross-entity matching for enhanced performance.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="32744-193">إضافة قواعد إلغاء التكرار</span><span class="sxs-lookup"><span data-stu-id="32744-193">Add deduplication rules</span></span>

1. <span data-ttu-id="32744-194">انتقل إلى **البيانات** > **توحيد** > **مطابقة**.</span><span class="sxs-lookup"><span data-stu-id="32744-194">Go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="32744-195">في قسم **التكرارات المدمجة**‬، حدد **تعيين الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="32744-195">In the **Merged duplicates** section, select **Set entities**.</span></span> <span data-ttu-id="32744-196">في حال تم إنشاء قواعد إلغاء التكرار، حدد **تحرير**.</span><span class="sxs-lookup"><span data-stu-id="32744-196">In case deduplication rules are already created, select **Edit**.</span></span>

1. <span data-ttu-id="32744-197">في الجزء **دمج التفضيلات**، اختر الكيانات التي تريد تطبيق إلغاء التكرار عليها.</span><span class="sxs-lookup"><span data-stu-id="32744-197">In the **Merge preferences** pane, choose the entities you want to run deduplication on.</span></span>

1. <span data-ttu-id="32744-198">حدد طريقة دمج السجلات المكررة واختر أحد الخيارات الثلاثة التالية:</span><span class="sxs-lookup"><span data-stu-id="32744-198">Specify how to combine the duplicate records and choose one of three options:</span></span>
   - <span data-ttu-id="32744-199">**الأكثر تعبئة**: لتعريف السجل الذي يتضمن حقول السمات الأكثر تعبئة تعبئة كالسجل الفائز.</span><span class="sxs-lookup"><span data-stu-id="32744-199">**Most filled**: Identifies the record with most populated attribute fields as the winner record.</span></span> <span data-ttu-id="32744-200">إنه خيار الدمج الافتراضي.</span><span class="sxs-lookup"><span data-stu-id="32744-200">It's the default merge option.</span></span>
   - <span data-ttu-id="32744-201">**الأحدث**: لتعريف السجل الفائز بالاستناد إلى الأكثر حداثة.</span><span class="sxs-lookup"><span data-stu-id="32744-201">**Most recent**: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="32744-202">يتطلب حقل تاريخ أو حقلاً رقميًا لتعريف الحداثة.</span><span class="sxs-lookup"><span data-stu-id="32744-202">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="32744-203">**الأقل حداثة**: لتعريف السجل الفائز بالاستناد إلى الأقل حداثة.</span><span class="sxs-lookup"><span data-stu-id="32744-203">**Least recent**: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="32744-204">يتطلب حقل تاريخ أو حقلاً رقميًا لتعريف الحداثة.</span><span class="sxs-lookup"><span data-stu-id="32744-204">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="32744-205">![الخطوة 1 لقواعد إلغاء التكرار](media/match-selfconflation.png "الخطوة 1 لقواعد إلغاء التكرار")</span><span class="sxs-lookup"><span data-stu-id="32744-205">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="32744-206">بعد تحديد الكيانات وتعيين تفضيلات الدمج لها، حدد **إضافة قاعدة** لتحديد قواعد إلغاء التكرار على مستوى الكيان.</span><span class="sxs-lookup"><span data-stu-id="32744-206">Once the entities are selected and their merge preference is set, select **Add rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="32744-207">الخيار **تحديد حقل** يسرد جميع الحقول المتوفرة من ذلك الكيان.</span><span class="sxs-lookup"><span data-stu-id="32744-207">**Select field** lists all the available fields from that entity.</span></span> <span data-ttu-id="32744-208">اختر الحقل الذي ترغب في التحقق من وجود تكرارات فيه.</span><span class="sxs-lookup"><span data-stu-id="32744-208">Choose the field you want to check for duplicates.</span></span> <span data-ttu-id="32744-209">اختر الحقول التي من المرجح أن تكون فريدة لكل عميل.</span><span class="sxs-lookup"><span data-stu-id="32744-209">Choose fields that are likely unique for every single customer.</span></span> <span data-ttu-id="32744-210">على سبيل المثال، عنوان البريد الإلكتروني أو مجموعة مكوّنة من الاسم والمدينة ورقم الهاتف.</span><span class="sxs-lookup"><span data-stu-id="32744-210">For example, an email address, or the combination of name, city, and phone number.</span></span>
   - <span data-ttu-id="32744-211">حدد إعدادات التسوية والدقة.</span><span class="sxs-lookup"><span data-stu-id="32744-211">Specify the normalization and precision settings.</span></span>
   - <span data-ttu-id="32744-212">حدد شروط إضافية عن طريق تحديد **إضافة شرط**.</span><span class="sxs-lookup"><span data-stu-id="32744-212">Define more conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="32744-213">![الخطوة 2 لقواعد إلغاء التكرار](media/match-selfconflation-rules.png "الخطوة 2 لقواعد إلغاء التكرار")</span><span class="sxs-lookup"><span data-stu-id="32744-213">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="32744-214">يمكنك إنشاء قواعد إلغاء تكرار متعددة لكيان.</span><span class="sxs-lookup"><span data-stu-id="32744-214">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="32744-215">يؤدي تشغيل عملية المطابقة الآن إلى تجميع السجلات استنادًا إلى الشروط المحددة في قواعد إلغاء التكرار.</span><span class="sxs-lookup"><span data-stu-id="32744-215">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="32744-216">بعد تجميع السجلات، يتم تطبيق سياسة الدمج لتحديد السجل الفائز.</span><span class="sxs-lookup"><span data-stu-id="32744-216">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="32744-217">بعد ذلك يتم تمرير السجل الفائز هذا إلى المطابقة عبر الكيانات، بالإضافة إلى السجلات غير الفائزة (على سبيل المثال، المعرفات البديلة) لتحسين جودة المطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-217">This winner record is then passed on to the cross-entity matching, along with the non-winner records (for example, alternate IDs) to improve the matching quality.</span></span>

1. <span data-ttu-id="32744-218">ستقوم قواعد المطابقة المخصصة التي تم تعريفها بإبطال قواعد إلغاء التكرار.‬</span><span class="sxs-lookup"><span data-stu-id="32744-218">Any custom match rules defined overwrite deduplication rules.</span></span> <span data-ttu-id="32744-219">إذا قامت قاعدة إلغاء التكرار بتعريف سجلات مطابقة، وإذا تم تعيين قاعدة مطابقة مخصصة لعدم مطابقة هذه السجلات إطلاقًا، فلن تتم مطابقة هذين السجلين.</span><span class="sxs-lookup"><span data-stu-id="32744-219">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="32744-220">بعد [تشغيل عملية المطابقة](#run-the-match-process)، سترى إحصاءات إلغاء التكرار. في الإطارات المتجانبة للمقاييس الأساسية‬.</span><span class="sxs-lookup"><span data-stu-id="32744-220">After [running the match process](#run-the-match-process), you will see the deduplication stats in the key metrics tiles.</span></span>

### <a name="deduplication-output-as-an-entity"></a><span data-ttu-id="32744-221">إخراج إلغاء التكرار ككيان</span><span class="sxs-lookup"><span data-stu-id="32744-221">Deduplication output as an entity</span></span>

<span data-ttu-id="32744-222">تقوم عملية إلغاء التكرار بإنشاء كيان جديد لكل كيان من أزواج المطابقة لتحديد السجلات الملغى تكرارها.</span><span class="sxs-lookup"><span data-stu-id="32744-222">The deduplication process creates a new entity for every entity from the match pairs to identify the deduplicated records.</span></span> <span data-ttu-id="32744-223">يمكن العثور على هذه الكيانات إلى جانب **ConflationMatchPairs:CustomerInsights** في قسم **النظام** في صفحة **الكيانات**، بالاسم **Deduplication_DataSource_Entity**.</span><span class="sxs-lookup"><span data-stu-id="32744-223">These entities can be found along with the **ConflationMatchPairs:CustomerInsights** in the **System** section in the **Entities** page, with the name **Deduplication_DataSource_Entity**.</span></span>

<span data-ttu-id="32744-224">يحتوي كيان إخراج إلغاء التكرار على المعلومات التالية:</span><span class="sxs-lookup"><span data-stu-id="32744-224">A deduplication output entity contains the following information:</span></span>
- <span data-ttu-id="32744-225">المعرفات / المفاتيح</span><span class="sxs-lookup"><span data-stu-id="32744-225">IDs / Keys</span></span>
  - <span data-ttu-id="32744-226">حقل المفتاح الأساسي، وحقل المعرفات البديلة.</span><span class="sxs-lookup"><span data-stu-id="32744-226">Primary key field and its alternate IDs field.</span></span> <span data-ttu-id="32744-227">يتكون حقل المعرفات البديلة من كافة المعرفات البديلة المحددة للسجل.</span><span class="sxs-lookup"><span data-stu-id="32744-227">Alternate IDs field consists of all the alternate IDs identified for a record.</span></span>
  - <span data-ttu-id="32744-228">يعرض الحقل Deduplication_GroupId المجموعة المحددة ضمن كيان يجمع جميع السجلات المماثلة بالاستناد إلى حقول إلغاء التكرار المحددة.</span><span class="sxs-lookup"><span data-stu-id="32744-228">Deduplication_GroupId field shows the group or cluster identified within an entity that groups all the similar records based on the specified deduplication fields.</span></span> <span data-ttu-id="32744-229">يُستخدم لأغراض معالجة النظام.</span><span class="sxs-lookup"><span data-stu-id="32744-229">It's used for system processing purposes.</span></span> <span data-ttu-id="32744-230">إذا لم تكن هناك قواعد إلغاء تكرار يدوية محددة وكانت قواعد إلغاء التكرار محددة من قبل النظام مطبقة، فقد لا تجد هذا الحقل في كيان إخراج إلغاء التكرار.</span><span class="sxs-lookup"><span data-stu-id="32744-230">If there are no manual deduplication rules specified and system defined deduplication rules apply, you may not find this field in the deduplication output entity.</span></span>
  - <span data-ttu-id="32744-231">Deduplication_WinnerId: يحتوي هذا الحقل على معرف الفائز من المجموعات المحددة.</span><span class="sxs-lookup"><span data-stu-id="32744-231">Deduplication_WinnerId: This field contains the winner ID from the identified groups or clusters.</span></span> <span data-ttu-id="32744-232">إذا كان Deduplication_WinnerId مماثلاً لقيمة المفتاح الأساسي لسجل ما، فهذا يعني أن السجل هو السجل الفائز.</span><span class="sxs-lookup"><span data-stu-id="32744-232">If the Deduplication_WinnerId is same as the Primary key value for a record, it means that the record is the winner record.</span></span>
- <span data-ttu-id="32744-233">الحقول التي تُستخدم لتعريف قواعد إلغاء تكرار الحقول.</span><span class="sxs-lookup"><span data-stu-id="32744-233">Fields used to define the deduplication rules.</span></span>
- <span data-ttu-id="32744-234">حقول القاعدة والدرجة للإشارة إلى قواعد إلغاء التكرار التي تم تطبيقها و الدرجة التي أرجعتها الخوارزمية المطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-234">Rule and Score fields to denote which of the deduplication rules got applied and the score returned by the matching algorithm.</span></span>
   
## <a name="run-the-match-process"></a><span data-ttu-id="32744-235">تشغيل عملية المطابقة</span><span class="sxs-lookup"><span data-stu-id="32744-235">Run the match process</span></span>

<span data-ttu-id="32744-236">باستخدام قواعد المطابقة المكوّنة، بما في ذلك المطابقة عبر الكيانات وقواعد إلغاء التكرار، يمكنك تشغيل عملية المطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-236">With configured match rules, including cross-entity matching and deduplication rules, you can run the match process.</span></span> 

<span data-ttu-id="32744-237">انتقل إلى **البيانات** > **توحيد** > **مطابقة** وحدد **تشغيل** لبدء العملية.</span><span class="sxs-lookup"><span data-stu-id="32744-237">Go to **Data** > **Unify** > **Match** and select **Run** to start the process.</span></span> <span data-ttu-id="32744-238">يستغرق استكمال خوارزمية المطابقة بعض الوقت، ولا يمكنك تغيير التكوين حتى تكتمل.</span><span class="sxs-lookup"><span data-stu-id="32744-238">The matching algorithm takes some time to complete and you can't change the configuration until it completes.</span></span> <span data-ttu-id="32744-239">لإجراء تغييرات، يمكنك إلغاء التشغيل.</span><span class="sxs-lookup"><span data-stu-id="32744-239">To make changes, you can cancel the run.</span></span> <span data-ttu-id="32744-240">حدد حالة المهمة، وحدد **إلغاء المهمة** في جزء **تفاصيل التقدم**.</span><span class="sxs-lookup"><span data-stu-id="32744-240">Select the status of the job and select **Cancel job** on the **Progress details** pane.</span></span>

<span data-ttu-id="32744-241">ستجد نتيجة عملية التشغيل الناجحة، كيان ملف تعريف العميل الموحد، في صفحة **الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="32744-241">You'll find the result of a successful run, the unified customer profile entity, on the **Entities** page.</span></span> <span data-ttu-id="32744-242">يطلق على كيان العميل الموحد اسم **العملاء** في قسم **ملفات التعريف**.</span><span class="sxs-lookup"><span data-stu-id="32744-242">Your unified customer entity is called **Customers** in the **Profiles** section.</span></span> <span data-ttu-id="32744-243">تقوم أول عملية تشغيل مطابقة ناجحة بإنشاء كيان *العميل* الموحد.</span><span class="sxs-lookup"><span data-stu-id="32744-243">The first successful match run creates the unified *Customer* entity.</span></span> <span data-ttu-id="32744-244">تعمل كافة عمليات تشغيل المطابقات اللاحقة على توسيع هذا الكيان.</span><span class="sxs-lookup"><span data-stu-id="32744-244">All subsequent match runs expand that entity.</span></span>

> [!TIP]
> <span data-ttu-id="32744-245">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="32744-245">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="32744-246">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="32744-246">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="32744-247">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="32744-247">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="32744-248">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="32744-248">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="32744-249">مراجعة المطابقات والتحقق من صحتها</span><span class="sxs-lookup"><span data-stu-id="32744-249">Review and validate your matches</span></span>

<span data-ttu-id="32744-250">انتقل إلى **البيانات** > **توحيد** > **مطابقة** لتقييم جودة أزواج المطابقة وتحسينها إذا لزم الأمر.</span><span class="sxs-lookup"><span data-stu-id="32744-250">Go to **Data** > **Unify** > **Match** to evaluate the quality of your match pairs and refine them if necessary.</span></span>

<span data-ttu-id="32744-251">تُظهر الإطارات المتجانبة في أعلى الصفحة المقاييس الأساسية، وتلخص عدد السجلات المطابقة والتكرارات.</span><span class="sxs-lookup"><span data-stu-id="32744-251">The tiles on top of the page show key metrics, summarizing the number of matched records and duplicates.</span></span>

:::image type="content" source="media/match-KPIs.png" alt-text="لقطة شاشة مقتطعة للمقاييس الأساسية على صفحة المطابقة مع أرقام وتفاصيل.":::

- <span data-ttu-id="32744-253">تعرض **سجلات المصدر الفريدة** عدد سجلات المصدر الفردية التي تمت معالجتها في عملية تشغيل المطابقة الأخيرة.</span><span class="sxs-lookup"><span data-stu-id="32744-253">**Unique source records** shows the number of individual source records that were processed in last match run.</span></span>
- <span data-ttu-id="32744-254">تميّز **السجلات المتطابقة وغير المتطابقة‬** عدد السجلات الفريدة المتبقية بعد معالجة قواعد المطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-254">**Matched and non-matched records** highlights how many unique records remain after processing the match rules.</span></span>
- <span data-ttu-id="32744-255">تعرض **السجلات المتطابقة فقط‬** عدد المطابقات بين جميع أزواج المطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-255">**Matched records only** shows the number of matches across all of your match pairs.</span></span>

<span data-ttu-id="32744-256">يمكنك تقييم نتائج كل زوج مطابقة وقواعده في جدول **تفاصيل السجلات المتطابقة‬**.</span><span class="sxs-lookup"><span data-stu-id="32744-256">You can assess the results of each match pair and its rules in the **Matched records details** table.</span></span> <span data-ttu-id="32744-257">قارن عدد السجلات التي تأتي من زوج مطابقة في مقابل النسبة المئوية للسجلات التي تمت مطابقتها بنجاح.</span><span class="sxs-lookup"><span data-stu-id="32744-257">Compare the number of records that came from a match pair against the percentage of successfully matched records.</span></span>

<span data-ttu-id="32744-258">راجع قواعد زوج مطابقة لمعرفة النسبة المئوية للسجلات التي تمت مطابقتها بنجاح على مستوى القاعدة.</span><span class="sxs-lookup"><span data-stu-id="32744-258">Review the rules of a match pair to see the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="32744-259">حدد علامة القطع (...) ثم حدد **معاينة المطابقة‬** لعرض جميع هذه السجلات على مستوى القاعدة.</span><span class="sxs-lookup"><span data-stu-id="32744-259">Select the ellipsis (...) and then select **Match preview** to view all these records on the rule level.</span></span> <span data-ttu-id="32744-260">من المستحسن أن تلقي نظرة على بعض السجلات للتحقق من مطابقتها بشكل صحيح.</span><span class="sxs-lookup"><span data-stu-id="32744-260">We recommend that you take a look at some records to validate that they were matched correctly.</span></span>

<span data-ttu-id="32744-261">حاول استخدام مستويات دقة مختلفة على الشروط للعثور على القيمة المثلى.</span><span class="sxs-lookup"><span data-stu-id="32744-261">Try different precision thresholds on conditions to find the optimal value.</span></span>

  1. <span data-ttu-id="32744-262">حدد علامة (...) للقاعدة التي تريد تجربتها، وحدد **تحرير**.</span><span class="sxs-lookup"><span data-stu-id="32744-262">Select the ellipsis (...) for the rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="32744-263">غيّر قيم الدقة في الشروط التي تريد مراجعتها.</span><span class="sxs-lookup"><span data-stu-id="32744-263">Change the precisions values in the conditions you want to revise.</span></span>

  3. <span data-ttu-id="32744-264">حدد **معاينة** لرؤية عدد السجلات المطابقة وغير المطابقة للشرط المحدد.</span><span class="sxs-lookup"><span data-stu-id="32744-264">Select **Preview** so see the number of matched and unmatched records for the selected condition.</span></span>

## <a name="manage-match-rules"></a><span data-ttu-id="32744-265">إدارة المطابقة</span><span class="sxs-lookup"><span data-stu-id="32744-265">Manage match rules</span></span>

<span data-ttu-id="32744-266">يمكنك إعادة تكوين معظم معلمات المطابقة وضبطها.</span><span class="sxs-lookup"><span data-stu-id="32744-266">You can reconfigure and fine-tune most of the match parameters.</span></span>

:::image type="content" source="media/match-rules-management.png" alt-text="لقطة شاشة من القائمة المنسدلة باستخدام خيارات قاعدة تطابق.":::

- <span data-ttu-id="32744-268">**قم بتغيير ترتيب القواعد** إذا قمت بتعريف قواعد متعددة.</span><span class="sxs-lookup"><span data-stu-id="32744-268">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="32744-269">يمكنك إعادة ترتيب قواعد مطابقة عن طريق تحديد الخيارين **تحريك لأعلى** و **تحريك لأسفل** أو عن طريق السحب والإفلات.</span><span class="sxs-lookup"><span data-stu-id="32744-269">You can reorder the match rules by selecting the **Move Up** and **Move Down** options or by drag and drop.</span></span>

- <span data-ttu-id="32744-270">**غيّر شروط القاعدة** من خلال تحديد **تحرير** واختيار حقول مختلفة.</span><span class="sxs-lookup"><span data-stu-id="32744-270">**Change rule conditions** by selecting **Edit** and choose different fields.</span></span>

- <span data-ttu-id="32744-271">**إلغاء تنشيط قاعدة** للاحتفاظ بقاعدة مطابقة مع استبعادها من عملية المطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-271">**Deactivate a rule** to retain a match rule while excluding it from the matching process.</span></span>

- <span data-ttu-id="32744-272">**تكرار القواعد** إذا قمت بتحديد قاعدة مطابقة وأردت إنشاء قاعدة مماثلة مع تعديلات، فحدد **تكرار**.</span><span class="sxs-lookup"><span data-stu-id="32744-272">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications, select **Duplicate**.</span></span>

- <span data-ttu-id="32744-273">**احذف قاعدة** عن طريق تحديد الرمز **حذف**.</span><span class="sxs-lookup"><span data-stu-id="32744-273">**Delete a rule** by selecting the **Delete** symbol.</span></span>

## <a name="specify-custom-match-conditions"></a><span data-ttu-id="32744-274">تحديد شروط مطابقة مخصصة</span><span class="sxs-lookup"><span data-stu-id="32744-274">Specify custom match conditions</span></span>

<span data-ttu-id="32744-275">يمكنك تحديد الشروط التي يجب أن تتطابق معها سجلات معينة دائمًا أو لا تطابقها أبدًا.</span><span class="sxs-lookup"><span data-stu-id="32744-275">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="32744-276">يمكن تحميل هذه القواعد لتجاوز عملية المطابقة القياسية.</span><span class="sxs-lookup"><span data-stu-id="32744-276">These rules can be uploaded to override the standard match process.</span></span> <span data-ttu-id="32744-277">على سبيل المثال، عند وجود محمد زايد 1 ومحمد زايد 2 في سجلاتنا، فقد يطابقهما النظام كشخص واحد.</span><span class="sxs-lookup"><span data-stu-id="32744-277">For example, if there are John Doe I and John Doe II in our records, the system might match them as one person.</span></span> <span data-ttu-id="32744-278">تسمح لك قواعد المطابقة المخصصة بتحديد أن ملفات تعريفهم تشير إلى أشخاص مختلفين.</span><span class="sxs-lookup"><span data-stu-id="32744-278">Custom match rules let you specify that their profiles refer to different people.</span></span> 

1. <span data-ttu-id="32744-279">انتقل إلى **البيانات** > **توحيد** > **مطابقة** وحدد **مطابقة مخصصة** في القسم **تفاصيل السجلات المتطابقة‬**.</span><span class="sxs-lookup"><span data-stu-id="32744-279">Go to **Data** > **Unify** > **Match** and select **Custom match** in the **Matched records details** section.</span></span>

  :::image type="content" source="media/custom-match-create.png" alt-text="لقطة شاشة لقسم قواعد المطابقة‬ مع تمييز سجل المطابقة المخصصة.":::

1. <span data-ttu-id="32744-281">إذا لم يكن لديك قواعد مطابقة مخصصة، فسترى جزء **مطابقة مخصصة** جديدًا مع المزيد من التفاصيل.</span><span class="sxs-lookup"><span data-stu-id="32744-281">If you have no custom match rules set, you'll see a new **Custom match** pane with more details.</span></span>

1. <span data-ttu-id="32744-282">حدد **‏‫ملء القالب‬** للحصول على ملف قالب يمكنه تحديد السجلات التي يجب أن تتطابق معها الكيانات دائمًا أو لا تطابقها أبدًا.</span><span class="sxs-lookup"><span data-stu-id="32744-282">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="32744-283">سوف تحتاج إلى ملء سجلات "مطابقة دائمًا" بشكل منفصل وسجلات "عدم المطابقة مطلقًا" في ملفين مختلفين.</span><span class="sxs-lookup"><span data-stu-id="32744-283">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

1. <span data-ttu-id="32744-284">يحتوي القالب على حقول لتحديد الكيان وقيم مفتاح الكيان الأساسي المطلوب استخدامها في المطابقة المخصصة.</span><span class="sxs-lookup"><span data-stu-id="32744-284">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="32744-285">على سبيل المثال، إذا أردت أن يتطابق دائمًا المفتاح الأساسي *12345* من كيان *المبيعات* مع المفتاح الأساسي *34567* من كيان *جهة الاتصال*، فعليك ملء القالب:</span><span class="sxs-lookup"><span data-stu-id="32744-285">For example, if you want primary key *12345* from *Sales* entity to always match with primary key *34567* from *Contact* entity, fill in the template:</span></span>
    - <span data-ttu-id="32744-286">الكيان 1: المبيعات</span><span class="sxs-lookup"><span data-stu-id="32744-286">Entity1: Sales</span></span>
    - <span data-ttu-id="32744-287">مفتاح الكيان 1: 12345</span><span class="sxs-lookup"><span data-stu-id="32744-287">Entity1Key: 12345</span></span>
    - <span data-ttu-id="32744-288">الكيان 2: جهة الاتصال</span><span class="sxs-lookup"><span data-stu-id="32744-288">Entity2: Contact</span></span>
    - <span data-ttu-id="32744-289">مفتاح الكيان 2: 34567</span><span class="sxs-lookup"><span data-stu-id="32744-289">Entity2Key: 34567</span></span>

   <span data-ttu-id="32744-290">يمكن لنفس ملف القالب تحديد سجلات المطابقة المخصصة من كيانات متعددة.</span><span class="sxs-lookup"><span data-stu-id="32744-290">The same template file can specify custom match records from multiple entities.</span></span>
   
   <span data-ttu-id="32744-291">إذا أردت تحديد مطابقة مخصصة لإلغاء التكرار على كيان ما، فعليك توفير الكيان نفسه كالكيان1 والكيان2 وتعيين قيم المفتاح الأساسي المختلفة.</span><span class="sxs-lookup"><span data-stu-id="32744-291">If you want to specify custom matching for deduplication on an entity, provide the same entity as both Entity1 and Entity2 and set the different primary key values.</span></span>

1. <span data-ttu-id="32744-292">بعد إضافة جميع التجاوزات التي تريد تطبيقها ، احفظ ملف القالب.</span><span class="sxs-lookup"><span data-stu-id="32744-292">After adding all the overrides you want to apply, save the template file.</span></span>

1. <span data-ttu-id="32744-293">انتقل إلى **البيانات** > **مصادر البيانات** لاستيعاب ملفات القوالب ككيانات جديدة.</span><span class="sxs-lookup"><span data-stu-id="32744-293">Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="32744-294">بمجرد تناولها، يمكنك استخدامها لتحديد تكوين مطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-294">Once ingested, you can use them to specify the Match configuration.</span></span>

1. <span data-ttu-id="32744-295">بعد تحميل الملفات والكيانات المتوفرة، حدد خيار **المطابقة المخصصة** مرة أخرى.</span><span class="sxs-lookup"><span data-stu-id="32744-295">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="32744-296">ستري خيارات لتحديد الكيانات التي ترغب في تضمينها.</span><span class="sxs-lookup"><span data-stu-id="32744-296">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="32744-297">حدد الكيانات المطلوبة من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="32744-297">Select the required entities from the dropdown menu.</span></span>

   :::image type="content" source="media/custom-match-overrides.png" alt-text="لقطة شاشة لمربع الحوار لاختيار تجاوزات سيناريو المطابقة المخصصة.":::

1. <span data-ttu-id="32744-299">حدد الكيانات التي ترغب في استخدامها لـ **المطابقة الدائمة** و **عدم المطابقة مطلقًا**، وقم بتحديد **تم**.</span><span class="sxs-lookup"><span data-stu-id="32744-299">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

1. <span data-ttu-id="32744-300">حدد **حفظ** في صفحة **المطابقة** لتطبيق تكوين المطابقة المخصصة.</span><span class="sxs-lookup"><span data-stu-id="32744-300">Select **Save** on the **Match** page to apply the custom match configuration.</span></span>

1. <span data-ttu-id="32744-301">حدد **تشغيل** في صفحة **المطابقة** لبدء عملية المطابقة.</span><span class="sxs-lookup"><span data-stu-id="32744-301">Select **Run** on the **Match** page to start the matching process.</span></span> <span data-ttu-id="32744-302">يتم تجاوز قواعد المطابقة المحددة الأخرى بواسطة تكوين المطابقة المخصصة.</span><span class="sxs-lookup"><span data-stu-id="32744-302">Other specified match rules are overridden by the custom match configuration.</span></span>

> [!TIP]
> <span data-ttu-id="32744-303">انتقل إلى **البيانات** > **الكيانات** وراجع الكيان **ConflationMatchPair** للتأكد من تطبيق التجاوزات.</span><span class="sxs-lookup"><span data-stu-id="32744-303">Go to **Data** > **Entities** and review the **ConflationMatchPair** entity to confirm that the overrides are applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="32744-304">الخطوة التالية</span><span class="sxs-lookup"><span data-stu-id="32744-304">Next step</span></span>

<span data-ttu-id="32744-305">بعد إكمال عملية المطابقة لزوج تطابق واحد على الأقل، فقد تتمكن من حل التناقضات المحتملة في بياناتك من خلال الانتقال إلى موضوع [**دمج**](merge-entities.md) .</span><span class="sxs-lookup"><span data-stu-id="32744-305">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
