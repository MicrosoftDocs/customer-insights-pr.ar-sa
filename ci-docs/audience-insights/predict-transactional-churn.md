---
title: التنبؤ بخسارة المعاملة
description: يمكنك التنبؤ بما إذا كان العميل عرضة للخطر لعدم شراء منتجات شركتك أو خدماتها.
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f3cbbf99a6cecba2aab2cf85428d53e5df8346e4
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644387"
---
# <a name="transactional-churn-prediction-preview"></a><span data-ttu-id="3b224-103">التنبؤ بخسارة المعاملة (معاينة)</span><span class="sxs-lookup"><span data-stu-id="3b224-103">Transactional churn prediction (preview)</span></span>

<span data-ttu-id="3b224-104">يساعدك التنبؤ بخسارة المعاملة على التنبؤ بما إذا كان العميل سيتوقف عن شراء منتجاتك أو خدماتك في إطار زمني معين.</span><span class="sxs-lookup"><span data-stu-id="3b224-104">Transactional churn prediction helps predict if a customer will no longer purchase your products or services in a given time window.</span></span> <span data-ttu-id="3b224-105">يمكنك إنشاء تنبؤات جديدة بخسارة المعاملة على **الذكاء** > **التنبؤات**.</span><span class="sxs-lookup"><span data-stu-id="3b224-105">You can create new churn predictions on **Intelligence** > **Predictions**.</span></span> <span data-ttu-id="3b224-106">حدد **تنبؤاتي** لرؤية التنبؤات الأخرى التي قمت بإنشائها.</span><span class="sxs-lookup"><span data-stu-id="3b224-106">Select **My predictions** to see other predictions that you've created.</span></span>

> [!TIP]
> <span data-ttu-id="3b224-107">جرّب البرنامج التعليمي للتنبؤ بخسارة المعاملة باستخدام عينة بيانات: [دليل نموذج التنبؤ بخسارة المعاملة (معاينة)‬](sample-guide-predict-transactional-churn.md).</span><span class="sxs-lookup"><span data-stu-id="3b224-107">Try the tutorial for a translactional churn prediction using sample data: [Transactional churn prediction (preview) sample guide](sample-guide-predict-transactional-churn.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3b224-108">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="3b224-108">Prerequisites</span></span>

- <span data-ttu-id="3b224-109">على الأقل [أذونات المساهم](permissions.md) في Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3b224-109">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="3b224-110">معرفة بالأعمال لفهم تأثير الخسارة على أعمالك.</span><span class="sxs-lookup"><span data-stu-id="3b224-110">Business knowledge to understand what churn means for your business.</span></span> <span data-ttu-id="3b224-111">اننا ندعم تعريفات خسارة العملاء المستندة إلى الوقت، مما يعني أن الشركة خسرت العميل بعد مرور فترة لم يقم خلالها العميل بأي عملية شراء.</span><span class="sxs-lookup"><span data-stu-id="3b224-111">We support time-based churn definitions, meaning a customer is considered to have churned after a period of no purchases.</span></span>
- <span data-ttu-id="3b224-112">بيانات حول معاملاتك/مشترياتك ومحفوظاتها:</span><span class="sxs-lookup"><span data-stu-id="3b224-112">Data about your transactions/purchases and their history:</span></span>
    - <span data-ttu-id="3b224-113">معرفات المعاملات لتمييز المشتريات/المعاملات.</span><span class="sxs-lookup"><span data-stu-id="3b224-113">Transaction identifiers to distinguish purchases/transactions.</span></span>
    - <span data-ttu-id="3b224-114">معرفات العملاء لمطابقة المعاملات مع عملائك.</span><span class="sxs-lookup"><span data-stu-id="3b224-114">Customer identifiers to match transactions to your customers.</span></span>
    - <span data-ttu-id="3b224-115">تواريخ أحداث المعاملة، التي تحدد تواريخ حدوث المعاملة.</span><span class="sxs-lookup"><span data-stu-id="3b224-115">Transaction event dates, which define the dates the transaction occurred on.</span></span>
    - <span data-ttu-id="3b224-116">يتطلب مخطط البيانات الدلالي للمشتريات/المعاملات المعلومات التالية:</span><span class="sxs-lookup"><span data-stu-id="3b224-116">The semantic data schema for purchases/transactions requires the following information:</span></span>
        - <span data-ttu-id="3b224-117">**معرف المعاملة:** معرف فريد لعملية شراء أو معاملة.</span><span class="sxs-lookup"><span data-stu-id="3b224-117">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="3b224-118">**تاريخ المعاملة**: تاريخ الشراء أو المعاملة.</span><span class="sxs-lookup"><span data-stu-id="3b224-118">**Transaction Date:** The date of the purchase or transaction.</span></span>
        - <span data-ttu-id="3b224-119">**قيمة المعاملة:** مبلغ العملة/القيمة الرقمية للمعاملة/الصنف.</span><span class="sxs-lookup"><span data-stu-id="3b224-119">**Value of the transaction:** The currency/numerical value amount of the transaction/item.</span></span>
        - <span data-ttu-id="3b224-120">(اختياري) **معرف منتج فريد:** معرف المنتج أو الخدمة التي تم شراؤها إذا كانت البيانات الخاصة بك على مستوى عنصر بند.</span><span class="sxs-lookup"><span data-stu-id="3b224-120">(Optional) **Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="3b224-121">(اختياري) **ما إذا كانت هذه المعاملة عبارة عن إرجاع:** حقل صواب/خطأ يحدد ما إذا كانت المعامل عبارة عن إرجاع أم لا.</span><span class="sxs-lookup"><span data-stu-id="3b224-121">(Optional) **Whether this transaction was a return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="3b224-122">إذا كانت **قيمة المعاملة** سالبة، سنستخدم أيضًا هذه المعلومات لاستنتاج إرجاع.</span><span class="sxs-lookup"><span data-stu-id="3b224-122">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>
- <span data-ttu-id="3b224-123">(اختياري) بيانات حول أنشطة العملاء:</span><span class="sxs-lookup"><span data-stu-id="3b224-123">(Optional) Data about customer activities:</span></span>
    - <span data-ttu-id="3b224-124">معرفات النشاط لتمييز الأنشطة من نفس النوع.</span><span class="sxs-lookup"><span data-stu-id="3b224-124">Activity identifiers to distinguish activities of the same type.</span></span>
    - <span data-ttu-id="3b224-125">معرفات العملاء لتعيين الأنشطة إلى عملائك.</span><span class="sxs-lookup"><span data-stu-id="3b224-125">Customer identifiers to map activities to your customers.</span></span>
    - <span data-ttu-id="3b224-126">معلومات النشاط التي تحتوي على اسم وتاريخ النشاط.</span><span class="sxs-lookup"><span data-stu-id="3b224-126">Activity information containing the name and date of the activity.</span></span>
    - <span data-ttu-id="3b224-127">يتضمن مخطط البيانات الدلالية لأنشطة العملاء ما يلي:</span><span class="sxs-lookup"><span data-stu-id="3b224-127">The semantic data schema for customer activities includes:</span></span>
        - <span data-ttu-id="3b224-128">**المفتاح الأساسي:** معرف فريد لنشاط.</span><span class="sxs-lookup"><span data-stu-id="3b224-128">**Primary key:** A unique identifier for an activity.</span></span> <span data-ttu-id="3b224-129">على سبيل المثال، تمت تجربة عينة من منتجك من قِبل زيارة موقع ويب أو سجل استخدام يعرض تجربة العميل.</span><span class="sxs-lookup"><span data-stu-id="3b224-129">For example, a website visit or a usage record showing the customer tried a sample of your product.</span></span>
        - <span data-ttu-id="3b224-130">**الطابع الزمني:** تاريخ ووقت الحدث المعرف من قبل المفتاح الأساسي.</span><span class="sxs-lookup"><span data-stu-id="3b224-130">**Timestamp:** The date and time of the event identified by the primary key.</span></span>
        - <span data-ttu-id="3b224-131">**الحدث:** اسم الحدث الذي تريد استخدامه.</span><span class="sxs-lookup"><span data-stu-id="3b224-131">**Event:** The name of the event you want to use.</span></span> <span data-ttu-id="3b224-132">على سبيل المثال، قد يكون حقل مسمى "UserAction" في متجر بقالة عبارة عن قسيمة يستخدمها العميل.</span><span class="sxs-lookup"><span data-stu-id="3b224-132">For example, a field called "UserAction" in a grocery store might be a coupon use by the customer.</span></span>
        - <span data-ttu-id="3b224-133">**التفاصيل:** معلومات مفصلة حول الحدث.</span><span class="sxs-lookup"><span data-stu-id="3b224-133">**Details:** Detailed information about the event.</span></span> <span data-ttu-id="3b224-134">على سبيل المثال، قد يكون حقل مسمى "CouponValue" في متجر بقالة عبارة عن قيمة عملة القسيمة.</span><span class="sxs-lookup"><span data-stu-id="3b224-134">For example, a field called "CouponValue" in a grocery store might be the currency value of the coupon.</span></span>

## <a name="create-a-transactional-churn-prediction"></a><span data-ttu-id="3b224-135">إنشاء تنبؤ بخسارة المعاملة</span><span class="sxs-lookup"><span data-stu-id="3b224-135">Create a transactional churn prediction</span></span>

1. <span data-ttu-id="3b224-136">في Customer Insights، انتقل إلى **الذكاء** > **التنبؤات**.</span><span class="sxs-lookup"><span data-stu-id="3b224-136">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="3b224-137">حدد الإطار المتجانب **نموذج خسارة العملاء (معاينة‬)** وحدد **استخدام هذا النموذج**.</span><span class="sxs-lookup"><span data-stu-id="3b224-137">Select the **Customer churn model (preview)** tile and select **Use this model**.</span></span>
   
1. <span data-ttu-id="3b224-138">في الجزء **نموذج خسارة العملاء‬**، اختر **تعاملي** وحدد **الشروع في العمل**.</span><span class="sxs-lookup"><span data-stu-id="3b224-138">In the **Customer churn model** pane, choose **Transactional** and select **Get started**.</span></span>

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="لقطة شاشة تتضمن تحديد الخيار تعاملي في جزء نموذج خسارة العملاء.":::

### <a name="name-model"></a><span data-ttu-id="3b224-140">تسمية النموذج</span><span class="sxs-lookup"><span data-stu-id="3b224-140">Name model</span></span>

1. <span data-ttu-id="3b224-141">قم بتوفير اسم للنموذج لتمييزه عن النماذج الأخرى.</span><span class="sxs-lookup"><span data-stu-id="3b224-141">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="3b224-142">قم بتوفير اسم لكيان الإخراج باستخدام الأحرف والأرقام فقط، دون أي مسافات.</span><span class="sxs-lookup"><span data-stu-id="3b224-142">Provide a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="3b224-143">هذا هو الاسم الذي سيستخدمه كيان النموذج.</span><span class="sxs-lookup"><span data-stu-id="3b224-143">That's the name that the model entity will use.</span></span> 

1. <span data-ttu-id="3b224-144">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="3b224-144">Select **Next**.</span></span>

### <a name="define-customer-churn"></a><span data-ttu-id="3b224-145">تحديد خسارة العميل</span><span class="sxs-lookup"><span data-stu-id="3b224-145">Define customer churn</span></span>

1. <span data-ttu-id="3b224-146">قم بتعيين نافذة من الأيام للتنبؤ بخسارة العملاء في الحقل **تحديد العملاء الذين قد تتم خسارتهم خلال**.</span><span class="sxs-lookup"><span data-stu-id="3b224-146">Set a window of days to predict churn for in the **Identify customers who may churn in the next** field.</span></span> <span data-ttu-id="3b224-147">على سبيل المثال، يمكنك التنبؤ بخسارة عملائك على مدى التسعين (90) يومًا القادمة للتماشي مع جهودك التسويقية لاستبقاء العملاء.</span><span class="sxs-lookup"><span data-stu-id="3b224-147">For example, predict the risk of churn for your customers over the next 90 days to align to your marketing retention efforts.</span></span> <span data-ttu-id="3b224-148">بإمكان التنبؤ بخطر خسارة العملاء لفترة وقت أطول أو أقصر أن تزيد من صعوبة معالجة العوامل في ملف تعريف خطر خسارة العملاء، ولكن هذا الأمر يتوقف على متطلبات العمل الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="3b224-148">Predicting churn risk for a longer or shorter period of time can make it more difficult to address the factors in your churn risk profile, but it depends on your specific business requirements.</span></span> 
   >[!TIP]
   > <span data-ttu-id="3b224-149">يمكنك تحديد **حفظ وإغلاق** في أي وقت لحفظ التنبؤ كمسودة.</span><span class="sxs-lookup"><span data-stu-id="3b224-149">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="3b224-150">ستجد توقعات المسودة في علامة التبويب **التنبؤات الخاصة بي** للمتابعة.</span><span class="sxs-lookup"><span data-stu-id="3b224-150">You'll find the draft prediction in the **My predictions** tab to continue.</span></span>

1. <span data-ttu-id="3b224-151">ادخل عدد الأيام لتحديد خسارة العميل في الحقل **تتم خسارة العميل إذا لم يقم بأي عمليات شراء خلال**.</span><span class="sxs-lookup"><span data-stu-id="3b224-151">Enter the number of days to define churn in the **A customer has churned if they've made no purchases in:** field.</span></span> <span data-ttu-id="3b224-152">على سبيل المثال، إذا لم يقم العميل بأي عملية شراء خلال الثلاثين (30) يومًا الماضية، فقد يعني ذلك أن شركتك قد خسرت العميل.</span><span class="sxs-lookup"><span data-stu-id="3b224-152">For example, if a customer has made no purchases in the last 30 days, they might be considered as churned for your business.</span></span> 

1. <span data-ttu-id="3b224-153">حدد **التالي** للمتابعة.</span><span class="sxs-lookup"><span data-stu-id="3b224-153">Select **Next** to continue</span></span>

### <a name="add-required-data"></a><span data-ttu-id="3b224-154">إضافة البيانات المطلوبة</span><span class="sxs-lookup"><span data-stu-id="3b224-154">Add required data</span></span>

1. <span data-ttu-id="3b224-155">حدد **إضافة بيانات** لخيار **محفوظات الشراء** واختر الكيان الذي يوفر معلومات محفوظات المعاملات/الشراء كما هو موضح في [المتطلبات الأساسية](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="3b224-155">Select **Add data** for **Purchase history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="3b224-156">قم بتعيين الحقول الدلالية إلى السمات ضمن كيان محفوظات الشراء، وحدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="3b224-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="3b224-157">بالنسبة لأوصاف الحقول، قم بإلقاء نظرة على [المتطلبات الأساسية](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="3b224-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="تعيين الحقول الدلالية لكيان الشراء.":::

1. <span data-ttu-id="3b224-159">إذا لم يتم ملء الحقول الموجودة بالأسفل، فقم بتكوين العلاقة من كيان سجل الشراء إلى كيان العميل.</span><span class="sxs-lookup"><span data-stu-id="3b224-159">If the fields below aren't populated, configure the relationship from your purchase history entity to the Customer entity.</span></span>
    1. <span data-ttu-id="3b224-160">حدد **كيان محفوظات الشراء**.</span><span class="sxs-lookup"><span data-stu-id="3b224-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="3b224-161">حدد **الحقل** الذي يعرّف العميل في كيان محفوظات الشراء.</span><span class="sxs-lookup"><span data-stu-id="3b224-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="3b224-162">ينبغي أن يرتبط بمعرف العميل الرئيسي لكيان العميل الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="3b224-162">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="3b224-163">حدد **كيان العميل** الذي يطابق كيان العميل الأساسي الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="3b224-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="3b224-164">أدخل اسمًا يصف العلاقة.</span><span class="sxs-lookup"><span data-stu-id="3b224-164">Enter a name that describes the relationship.</span></span>

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="صفحة محفوظات الشراء تعرض إنشاء علاقة مع العميل.":::
   
1. <span data-ttu-id="3b224-166">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="3b224-166">Select **Next**.</span></span>

1. <span data-ttu-id="3b224-167">اختياريًا، حدد **إضافة بيانات** لخيار **أنشطة العميل**.</span><span class="sxs-lookup"><span data-stu-id="3b224-167">Optionally, select **Add data** for **Customer activities**.</span></span> <span data-ttu-id="3b224-168">اختر الكيان الذي يوفر معلومات نشاط العميل كما هو موضح في المتطلبات الأساسية.</span><span class="sxs-lookup"><span data-stu-id="3b224-168">Choose the entity that provides the customer activity information as described in the prerequisites.</span></span>

1. <span data-ttu-id="3b224-169">قم بتعيين الحقول الدلالية إلى السمات ضمن كيان نشاط العميل، وحدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="3b224-169">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span> <span data-ttu-id="3b224-170">بالنسبة لأوصاف الحقول، قم بإلقاء نظرة على [المتطلبات الأساسية](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="3b224-170">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="3b224-171">حدد نوع نشاط يطابق نوع نشاط العميل الذي تقوم بتكوينه.</span><span class="sxs-lookup"><span data-stu-id="3b224-171">Select an activity type that matches to the type of customer activity you're configuring.</span></span> <span data-ttu-id="3b224-172">حدد **إنشاء جديد** ثم اختر نوع نشاط متوفر أو أنشئ نوعًا جديدًا.</span><span class="sxs-lookup"><span data-stu-id="3b224-172">Select **Create new** and choose an available activity type or create a new type.</span></span>

1. <span data-ttu-id="3b224-173">سيتعين عليك تكوين العلاقة من كيان نشاط العميل الخاص بك إلى كيان العميل.</span><span class="sxs-lookup"><span data-stu-id="3b224-173">You'll need to configure the relationship from your customer activity entity to the Customer entity.</span></span>
    1. <span data-ttu-id="3b224-174">حدد الحقل الذي يعرّف العميل في جدول نشاط العميل.</span><span class="sxs-lookup"><span data-stu-id="3b224-174">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="3b224-175">قد يكون مرتبطًا بشكل مباشر بمعرف العميل الأساسي لكيان العميل.</span><span class="sxs-lookup"><span data-stu-id="3b224-175">It can be directly related to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="3b224-176">حدد كيان العميل الذي يطابق كيان العميل الرئيسي الخاص بك</span><span class="sxs-lookup"><span data-stu-id="3b224-176">Select the Customer entity that matches your primary Customer entity</span></span>
    1. <span data-ttu-id="3b224-177">أدخل اسمًا يصف العلاقة.</span><span class="sxs-lookup"><span data-stu-id="3b224-177">Enter a name that describes the relationship.</span></span>

1. <span data-ttu-id="3b224-178">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="3b224-178">Select **Save**.</span></span>

1. <span data-ttu-id="3b224-179">إذا كانت لديك أي أنشطه عميل أخرى ترغب في تضمينها، فكرر الخطوات الموضحة أعلاه.</span><span class="sxs-lookup"><span data-stu-id="3b224-179">If you have any other customer activities you would like to include, repeat the steps above.</span></span>

1. <span data-ttu-id="3b224-180">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="3b224-180">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="3b224-181">تعيين الجدول ومراجعة التكوين</span><span class="sxs-lookup"><span data-stu-id="3b224-181">Set schedule and review configuration</span></span>

1. <span data-ttu-id="3b224-182">قم بتعيين تكرار للاحتفاظ بالنموذج الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="3b224-182">Set a frequency to retrain your model.</span></span> <span data-ttu-id="3b224-183">يعد هذا الاعداد ضروريًا لتحديث دقه التنبؤات مع استيعاب البيانات الجديدة.</span><span class="sxs-lookup"><span data-stu-id="3b224-183">This setting is important to update the accuracy of predictions as new data is ingested.</span></span> <span data-ttu-id="3b224-184">يمكن لمعظم شركات الأعمال إجراء الاحتفاظ مرة واحدة في الشهر والحصول على دقة جيدة للتنبؤ الخاص بها.</span><span class="sxs-lookup"><span data-stu-id="3b224-184">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="3b224-185">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="3b224-185">Select **Next**.</span></span>

1. <span data-ttu-id="3b224-186">راجع تكوين التنبؤ.</span><span class="sxs-lookup"><span data-stu-id="3b224-186">Review the configuration of the prediction.</span></span> <span data-ttu-id="3b224-187">يمكنك الرجوع إلى الخطوات السابقة من خلال تحديد **تحرير** تحت القيمة المعروضة.</span><span class="sxs-lookup"><span data-stu-id="3b224-187">You can go back to prior steps by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="3b224-188">أو يمكنك تحديد خطوة تكوين من مؤشر التقدم.</span><span class="sxs-lookup"><span data-stu-id="3b224-188">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="3b224-189">وإذا كانت جميع القيم مكونة بشكل صحيح، فحدد **حفظ وتشغيل** لبدء عملية التنبؤ.</span><span class="sxs-lookup"><span data-stu-id="3b224-189">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="3b224-190">في علامة التبويب **التنبؤ**، يمكنك رؤية حالة التنبؤات الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="3b224-190">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="3b224-191">قد تستغرق العملية عدة ساعات للاكتمال وذلك وفقًا لكمية البيانات المستخدمة في التنبؤ.</span><span class="sxs-lookup"><span data-stu-id="3b224-191">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="3b224-192">مراجعة حاله التنبؤ والنتائج</span><span class="sxs-lookup"><span data-stu-id="3b224-192">Review a prediction status and results</span></span>

1. <span data-ttu-id="3b224-193">انتقل إلى **الذكاء** > **التنبؤات** وحدد علامة التبويب **التنبؤات الخاصة بي‬**.</span><span class="sxs-lookup"><span data-stu-id="3b224-193">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="3b224-194">حدد التنبؤ الذي تريد مراجعته.</span><span class="sxs-lookup"><span data-stu-id="3b224-194">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="3b224-195">**اسم التنبؤ**: اسم التنبؤ الذي تم توفيره عند إنشائه.</span><span class="sxs-lookup"><span data-stu-id="3b224-195">**Prediction name:** Name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="3b224-196">**نوع التنبؤ:** نوع النموذج المستخدم للتنبؤ</span><span class="sxs-lookup"><span data-stu-id="3b224-196">**Prediction type:** Type of model used for the prediction</span></span>
   - <span data-ttu-id="3b224-197">**كيان الإخراج:** اسم الكيان لتخزين إخراج التنبؤ.</span><span class="sxs-lookup"><span data-stu-id="3b224-197">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="3b224-198">يمكنك العثور على كيان بهذا الاسم في **البيانات** > **الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="3b224-198">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="3b224-199">**حقل متوقع‬**: يتم ملء هذا الحقل لبعض أنواع التنبؤ فقط، ولا يُستخدم في التنبؤ بخسارة العميل.</span><span class="sxs-lookup"><span data-stu-id="3b224-199">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="3b224-200">**الحالة:** حالة تشغيل التنبؤ.</span><span class="sxs-lookup"><span data-stu-id="3b224-200">**Status:** Status of the prediction run.</span></span>
        - <span data-ttu-id="3b224-201">**في قائمة الانتظار**: ينتظر التنبؤ تشغيل العمليات الأخرى.</span><span class="sxs-lookup"><span data-stu-id="3b224-201">**Queued:** Prediction is waiting for other processes to run.</span></span>
        - <span data-ttu-id="3b224-202">**تحديث:** يتم الآن تشغيل التنبؤ للحصول على نتائج ستتدفق إلى كيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="3b224-202">**Refreshing:** Prediction is currently running to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="3b224-203">**فشل:** فشل تشغيل التنبؤ.</span><span class="sxs-lookup"><span data-stu-id="3b224-203">**Failed:** Prediction run has failed.</span></span> <span data-ttu-id="3b224-204">[راجع السجلات](#troubleshoot-a-failed-prediction) لمزيد من التفاصيل.</span><span class="sxs-lookup"><span data-stu-id="3b224-204">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
        - <span data-ttu-id="3b224-205">**نجاح:** نجح التنبؤ.</span><span class="sxs-lookup"><span data-stu-id="3b224-205">**Succeeded:** Prediction has succeeded.</span></span> <span data-ttu-id="3b224-206">حدد **عرض** أسفل علامات الحذف الرأسية لمراجعة التنبؤ</span><span class="sxs-lookup"><span data-stu-id="3b224-206">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="3b224-207">**تم التحرير:** التاريخ الذي تم فيه تغيير تكوين التنبؤ.</span><span class="sxs-lookup"><span data-stu-id="3b224-207">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="3b224-208">**التحديث الأخير:** التاريخ الذي نتج عنه تحديث التنبؤ في كيان المخرجات.</span><span class="sxs-lookup"><span data-stu-id="3b224-208">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="3b224-209">حدد علامات الحذف الرأسية الموجودة بجوار التنبؤ الذي تريد مراجعة النتائج له وقم بتحديد **عرض**.</span><span class="sxs-lookup"><span data-stu-id="3b224-209">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>

   :::image type="content" source="media/model-subs-view.PNG" alt-text="عرض عنصر التحكم لرؤية نتائج التنبؤ.":::   

1. <span data-ttu-id="3b224-211">يوجد ثلاثة أقسام رئيسية من البيانات في صفحة النتائج:</span><span class="sxs-lookup"><span data-stu-id="3b224-211">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="3b224-212">**أداء نموذج التدريب:** والنتائج المحتملة A أو B أو C.</span><span class="sxs-lookup"><span data-stu-id="3b224-212">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="3b224-213">تشير هذه الدرجة إلى أداء التنبؤ، ويمكن أن تساعدك في اتخاذ قرار بشأن استخدام النتائج المخزنة في كيان المخرجات.</span><span class="sxs-lookup"><span data-stu-id="3b224-213">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="3b224-214">يتم تحديد نقاط الدرجات استنادًا إلى القواعد التالية:</span><span class="sxs-lookup"><span data-stu-id="3b224-214">Scores are determined based on the following rules:</span></span>
         
         - <span data-ttu-id="3b224-215">**أ** عندما توقع النموذج بشكل دقيق 50% على الأقل من إجمالي التنبؤات، وعندما تكون النسبة المئوية للتنبؤات الدقيقة للعملاء الذين تمت خسارتهم أكبر من معدل التنبؤ الأساسي بنسبة 10% على الأقل.</span><span class="sxs-lookup"><span data-stu-id="3b224-215">**A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is greater than the baseline rate by at least 10%.</span></span>
            
         - <span data-ttu-id="3b224-216">**ب** عندما توقع النموذج بشكل دقيق 50% على الأقل من إجمالي التنبؤات، وعندما تكون النسبة المئوية للتنبؤات الدقيقة للعملاء الذين تمت خسارتهم أكبر من التنبؤ الأساسي بنسبة 10%.</span><span class="sxs-lookup"><span data-stu-id="3b224-216">**B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is up to 10% greater than the baseline.</span></span>
            
         - <span data-ttu-id="3b224-217">**ج** عندما توقع النموذج بشكل دقيق 50% من إجمالي التنبؤات، أو عندما تكون النسبة المئوية للتنبؤات الدقيقة للعملاء الذين تمت خسارتهم أقل من التنبؤ الأساسي.</span><span class="sxs-lookup"><span data-stu-id="3b224-217">**C** when the model accurately predicted less 50% of the total predictions, or when the percentage of accurate predictions for customers who churned is less than the baseline.</span></span>
               
         - <span data-ttu-id="3b224-218">يأخذ **التنبؤ الأساسي** إدخال الإطار الزمني للتنبؤ الخاص بالنموذج (على سبيل المثال، سنة واحدة)، وينشئ النموذج كسور وقت مختلفة عن طريق تقسيمها على 2 حتى الوصول إلى شهر واحد أو أقل.</span><span class="sxs-lookup"><span data-stu-id="3b224-218">**Baseline** takes the prediction time window input for the model (for example, one year) and the model creates different fractions of time by dividing it by 2 until it reaches one month or less.</span></span> <span data-ttu-id="3b224-219">إنه يستخدم هذه الكسور لإنشاء قاعدة عمل للعملاء الذين لم يقوموا بأي عملية شراء خلال هذا الإطار الزمني.</span><span class="sxs-lookup"><span data-stu-id="3b224-219">It uses these fractions to create a business rule for customers who have not purchased in this time frame.</span></span> <span data-ttu-id="3b224-220">يعتبر هؤلاء العملاء في فئة العملاء الذين خسرتهم الشركة.</span><span class="sxs-lookup"><span data-stu-id="3b224-220">These customers are considered as churned.</span></span> <span data-ttu-id="3b224-221">يتم اختيار قاعدة العمل المستندة إلى الوقت مع أعلى قدرة للتنبؤ بالعميل الذين ستتم خسارته على الأرجح كنموذج تنبؤ أساسي.</span><span class="sxs-lookup"><span data-stu-id="3b224-221">The time-based business rule with the highest ability to predict who is likely to churn is chosen as baseline model.</span></span>
            
    1. <span data-ttu-id="3b224-222">**احتمالية الخسارة (عدد العملاء):** مجموعات العملاء وفقًا لمخاطر الخسارة المتوقعة.</span><span class="sxs-lookup"><span data-stu-id="3b224-222">**Likelihood to churn (number of customers):** Groups of customers based on their predicted risk of churn.</span></span> <span data-ttu-id="3b224-223">يمكن أن تساعدك هذه البيانات لاحقا إذا كنت ترغب في إنشاء شريحة من العملاء أصحاب مخاطر خسارة عالية.</span><span class="sxs-lookup"><span data-stu-id="3b224-223">This data can help you later if you want to create a segment of customers with high churn risk.</span></span> <span data-ttu-id="3b224-224">تساعدك هذه الشرائح في فهم المكان الذي ينبغي فيه عمل فصل لعضوية الشريحة.</span><span class="sxs-lookup"><span data-stu-id="3b224-224">Such segments help to understand where your cutoff should be for segment membership.</span></span>
       
    1. <span data-ttu-id="3b224-225">**العوامل الأكثر تأثيرًا:** ثمة العديد من العوامل التي يتم أخذها في الاعتبار عند إنشاء التنبؤ الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="3b224-225">**Most influential factors:** There are many factors that are taken into account when creating your prediction.</span></span> <span data-ttu-id="3b224-226">يتم حساب الأهمية الخاصة لكل واحد من هذه العوامل للتنبؤات المجمعة التي ينشئها النموذج.</span><span class="sxs-lookup"><span data-stu-id="3b224-226">Each of the factors has its importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="3b224-227">يمكنك استخدام هذه العوامل للمساعدة في التحقق من صحة نتائج التنبؤ.</span><span class="sxs-lookup"><span data-stu-id="3b224-227">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="3b224-228">أو يمكنك استخدام هذه المعلومات لاحقًا [لإنشاء شرائح](segments.md) يمكن أن تساعد في التأثير على خطر الخسارة للعملاء.</span><span class="sxs-lookup"><span data-stu-id="3b224-228">Or you can use this information later to [create segments](segments.md) that could help influence churn risk for customers.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="3b224-229">استكشاف أخطاء تنبؤ فاشل وإصلاحها</span><span class="sxs-lookup"><span data-stu-id="3b224-229">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="3b224-230">انتقل إلى **الذكاء** > **التنبؤات** وحدد علامة التبويب **التنبؤات الخاصة بي‬**.</span><span class="sxs-lookup"><span data-stu-id="3b224-230">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="3b224-231">حدد علامة القطع البيضاوية الموجودة بجوار التنبؤ الذي تريد عرض سجلات الأخطاء له.</span><span class="sxs-lookup"><span data-stu-id="3b224-231">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="3b224-232">حدد **السجلات‏‎**.</span><span class="sxs-lookup"><span data-stu-id="3b224-232">Select **Logs**.</span></span>

1. <span data-ttu-id="3b224-233">راجع كافة الأخطاء.</span><span class="sxs-lookup"><span data-stu-id="3b224-233">Review all the errors.</span></span> <span data-ttu-id="3b224-234">ثمة أنواع عديدة من الأخطاء يمكن أن تحدث، وهي تصف الحالة التي تسببت في الخطأ.</span><span class="sxs-lookup"><span data-stu-id="3b224-234">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="3b224-235">على سبيل المثال، في العادة يتم حل خطأ عدم وجود بيانات كافية للتنبؤ بدقة عن طريق تحميل بيانات إضافية إلى Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3b224-235">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="3b224-236">تحديث تنبؤ</span><span class="sxs-lookup"><span data-stu-id="3b224-236">Refresh a prediction</span></span>

<span data-ttu-id="3b224-237">سيتم تحديث التنبؤات تلقائيًا على وفقًا لنفس [جدول تحديثات البيانات الخاصة بك](system.md#schedule-tab) كما تم تكوينها في الإعدادات.</span><span class="sxs-lookup"><span data-stu-id="3b224-237">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="3b224-238">يمكنك تحديثها يدويًا أيضًا.</span><span class="sxs-lookup"><span data-stu-id="3b224-238">You can refresh them manually too.</span></span>

1. <span data-ttu-id="3b224-239">انتقل إلى **الذكاء** > **التنبؤات** وحدد علامة التبويب **التنبؤات الخاصة بي‬**.</span><span class="sxs-lookup"><span data-stu-id="3b224-239">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="3b224-240">حدد علامات الحذف الرأسية المجاورة للتنبؤ الذي ترغب في تحديثه.</span><span class="sxs-lookup"><span data-stu-id="3b224-240">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="3b224-241">حدد **تحديث**.</span><span class="sxs-lookup"><span data-stu-id="3b224-241">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="3b224-242">حذف التنبؤ</span><span class="sxs-lookup"><span data-stu-id="3b224-242">Delete a prediction</span></span>

<span data-ttu-id="3b224-243">يؤدي حذف تنبؤ إلى إزالة كيان الإخراج الخاص به أيضًا.</span><span class="sxs-lookup"><span data-stu-id="3b224-243">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="3b224-244">انتقل إلى **الذكاء** > **التنبؤات** وحدد علامة التبويب **التنبؤات الخاصة بي‬**.</span><span class="sxs-lookup"><span data-stu-id="3b224-244">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="3b224-245">حدد علامات الحذف الرأسية المجاورة للتنبؤ الذي ترغب في حذفه.</span><span class="sxs-lookup"><span data-stu-id="3b224-245">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="3b224-246">حدد **حذف**.</span><span class="sxs-lookup"><span data-stu-id="3b224-246">Select **Delete**.</span></span>
