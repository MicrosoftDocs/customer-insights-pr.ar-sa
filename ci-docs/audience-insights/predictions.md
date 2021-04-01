---
title: إكمال البيانات الجزئية باستخدام التنبؤ
description: استخدم التنبؤات لملء بيانات العميل غير المكتملة.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595885"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="14685-103">أكمل البيانات الجزئية باستخدام التنبؤات</span><span class="sxs-lookup"><span data-stu-id="14685-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="14685-104">تتيح لك التنبؤات إنشاء القيم المتوقعة التي يمكنها تحسين فهمك لعميل ما بسهولة.</span><span class="sxs-lookup"><span data-stu-id="14685-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="14685-105">في صفحة **الذكاء** > **التنبؤات**، يمكنك تحديد **التنبؤات الخاصة بي‬** لرؤية التنبؤات التي قمت بتكوينها في أجزاء أخرى من رؤى الجمهور، والسماح لك بتخصيصها بشكل أكبر.</span><span class="sxs-lookup"><span data-stu-id="14685-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="14685-106">لا يمكنك استخدام هذه الميزة إذا كانت البيئة تستخدم تخزين Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="14685-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="14685-107">وتستخدم ميزه التنبؤات العلامات التلقائية لتقييم البيانات وإنشاء التنبؤات استنادًا إلى تلك البيانات، وبالتالي يكون لديه القدرة على الاستخدام كطريقة لإنشاء الملفات، التي يتم تعريفها بواسطة القانون العام لحماية البيانات ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="14685-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="14685-108">قد يخضع استخدام العميل لهذه الميزة لمعالجة البيانات حسب قانون GDPR أو القوانين أو اللوائح الأخرى.</span><span class="sxs-lookup"><span data-stu-id="14685-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="14685-109">إذا كنت مسؤولاً عن التأكد من أن استخدام Dynamics 365 Customer Insights، بما في ذلك التنبؤات، يتوافق مع كافة القوانين واللوائح المعمول بها، بما في ذلك القوانين المتعلقة بالخصوصية والبيانات الشخصية وبيانات المقاييس الحيوية وحماية البيانات وسرية الاتصالات.</span><span class="sxs-lookup"><span data-stu-id="14685-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="14685-110">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="14685-110">Prerequisites</span></span>

<span data-ttu-id="14685-111">قبل أن تتمكن مؤسستك من استخدام ميزة التنبؤات، تأكد من استيفاء المتطلبات الأساسية التالية:</span><span class="sxs-lookup"><span data-stu-id="14685-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="14685-112">لدي مؤسستك مثيل [تم إعداده في Common Data Service](/ai-builder/build-model#prerequisites) وهو في نفس المؤسسة حيث Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="14685-112">Your organization has an instance [set up in the Common Data Service](/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="14685-113">بيئتك مرفقة بمثيل Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="14685-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="14685-114">إذا كنت تقوم [بإنشاء البيئة الأولى](manage-environments.md)، قم بتكيونها في مربع الحوار **إنشاء بيئة** وحدد **خيارات متقدمة**.</span><span class="sxs-lookup"><span data-stu-id="14685-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="14685-115">إذا كنت قد قمت بإنشاء بيئة بالفعل، انتقل إلى الإعدادات الخاصة بها وحدد **خيارات متقدمة**.</span><span class="sxs-lookup"><span data-stu-id="14685-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="14685-116">في كلا الحالتين، في قسم **استخدام التنبؤات**، أدخل عنوان URL لمثيل Common Data Service الذي ترغب في إرفاق البيئة به.</span><span class="sxs-lookup"><span data-stu-id="14685-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="14685-117">إنشاء تنبؤ في كيان العميل</span><span class="sxs-lookup"><span data-stu-id="14685-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="14685-118">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="14685-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="14685-119">حدد الكيان **العميل**.</span><span class="sxs-lookup"><span data-stu-id="14685-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="14685-120">في الكيان **العميل: CustomerInsights**، حدد علامة التبويب **الحقول**.</span><span class="sxs-lookup"><span data-stu-id="14685-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="14685-121">ابحث عن اسم السمة التي ترغب في التنبؤ بقيم لها، ثم حدد أيقونة **نظرة عامة** في العمود **الملخص**.</span><span class="sxs-lookup"><span data-stu-id="14685-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="14685-122">![أيقونة نظرة عامة](media/intelligence-overviewicon.png "أيقونة نظرة عامة")</span><span class="sxs-lookup"><span data-stu-id="14685-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="14685-123">إذا كان هناك معدل عال لقيم مفقودة للسمة الخاصة بك، حدد **التنبؤ بالقيم المفقودة** لمتابعة التنبؤ الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="14685-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="14685-124">![الزر حالة النظرة العامة والتنبؤ بالقيم المفقودة يظهر](media/intelligence-overviewpredictmissingvalues.png "الزر حالة النظرة العامة والتنبؤ بالقيم المفقودة يظهر")</span><span class="sxs-lookup"><span data-stu-id="14685-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="14685-125">قم بتوفير **اسم العرض** و **اسم كيان الإخراج** لنتائج التنبؤ.</span><span class="sxs-lookup"><span data-stu-id="14685-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="14685-126">ستُظهر قائمة منشورة مسبقًا المكان الذي يمكنك فيه تعيين القيم إلى فئة متوقعة.</span><span class="sxs-lookup"><span data-stu-id="14685-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="14685-127">في هذه الحالة، ستكون خيارات الفئة الوحيدة هي 0 أو 1، كما يتم تعيينها إلى الطبيعة الصحيحة/الخاطئة أو الثنائية للتنبؤ.</span><span class="sxs-lookup"><span data-stu-id="14685-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="14685-128">في عمود الفئة، قم بتعيين قيم الحقول التي ترغب في تصنيفها ك "0" في التنبؤ النهائي إلى "0"، والعناصر التي ترغب في تصنيفها ك "1" في التنبؤ النهائي إلى "1".</span><span class="sxs-lookup"><span data-stu-id="14685-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="14685-129">![مثال يوضح قيم الحقول المعينة إلى الفئات](media/intelligence-categorymapping.png "مثال يوضح قيم الحقول المعينة إلى الفئات")</span><span class="sxs-lookup"><span data-stu-id="14685-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="14685-130">قم بتحديد **تم** وستتم معالجة التنبؤ.</span><span class="sxs-lookup"><span data-stu-id="14685-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="14685-131">ستستغرق عملية المعالجة بعض الوقت، وذلك وفقًا لحجم البيانات وتعقيدها.</span><span class="sxs-lookup"><span data-stu-id="14685-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="14685-132">ستتوافر النتائج متوفرة في كيان جديد استنادًا إلى **اسم كيان الإخراج** للتنبؤ الذي قمت بإنشاءه.</span><span class="sxs-lookup"><span data-stu-id="14685-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="14685-133">إنشاء تنبؤ أثناء إنشاء مقطع</span><span class="sxs-lookup"><span data-stu-id="14685-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="14685-134">كما يُعد التنبؤ بالقيم المفقودة لسمة معينة من اختيارك أمرًا ممكنًا عند إنشاء مقطع.</span><span class="sxs-lookup"><span data-stu-id="14685-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="14685-135">وبشكل خاص، عندما تقوم بشكل سريع بإنشاء مقطع استنادًا إلى إما كيان Customer الموحد أو كيان Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="14685-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="14685-136">كجزء من هذا التدفق، ستختار سمة معينة لإنشاء المقطع الخاص بك على سبيل المثال، مثل رضا العميل أو مبلغ الشراء.</span><span class="sxs-lookup"><span data-stu-id="14685-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="14685-137">عند إنشاء مقطع، سيقترح النظام طريقه للتنبؤ بأية قيم مفقودة لهذه السمة.</span><span class="sxs-lookup"><span data-stu-id="14685-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="14685-138">في رؤى الجمهور ، انتقل إلى **الشرائح**، وحدد الإطار المتجانب **ملفات التعريف**.</span><span class="sxs-lookup"><span data-stu-id="14685-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="14685-139">اختر **حقل** لإنشاء مقطع وحدد **عامل**، ثم حدد **مراجعة**.</span><span class="sxs-lookup"><span data-stu-id="14685-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="14685-140">قم بتوفير **اسم** و **اسم العرض** للمقطع.</span><span class="sxs-lookup"><span data-stu-id="14685-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="14685-141">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="14685-141">Select **Save**.</span></span>

5. <span data-ttu-id="14685-142">إذا كان المقطع الذي قمت بإنشائه يحتوي على بيانات غير كاملة في الحقل المصدر، يمكنك اختيار التنبؤ بالقيم المفقودة.</span><span class="sxs-lookup"><span data-stu-id="14685-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="14685-143">![زر التنبؤ](media/segments-predictoption.png "زر التنبؤ")</span><span class="sxs-lookup"><span data-stu-id="14685-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="14685-144">قم بتوفير **اسم العرض** و **اسم كيان الإخراج** لنتائج التنبؤ.</span><span class="sxs-lookup"><span data-stu-id="14685-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="14685-145">حدد **تم**.</span><span class="sxs-lookup"><span data-stu-id="14685-145">Select **Done**.</span></span> <span data-ttu-id="14685-146">سيتم إنشاء التنبؤ الخاص بك قريبًا في كيان جديد بالاسم الذي قمت بتوفيره لـ **اسم كيان الإخراج**.</span><span class="sxs-lookup"><span data-stu-id="14685-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="14685-147">عرض تنبؤ</span><span class="sxs-lookup"><span data-stu-id="14685-147">View a prediction</span></span>

1. <span data-ttu-id="14685-148">في رؤى الجمهور، انتقل إلى **الذكاء** > **التنبؤات** > **التنبؤات الخاصة بي**.</span><span class="sxs-lookup"><span data-stu-id="14685-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="14685-149">حدد التنبؤ الذي تريد مراجعته.</span><span class="sxs-lookup"><span data-stu-id="14685-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="14685-150">قم بتحديد علامة الحذف في العمود **الإجراءات** واختر **عرض**.</span><span class="sxs-lookup"><span data-stu-id="14685-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="14685-151">سيظهر لك عددًا من نقاط البيانات في طريقة عرض التنبؤ.</span><span class="sxs-lookup"><span data-stu-id="14685-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="14685-152">![صفحة التنبؤات](media/intelligence-predictionsviewpage.png "صفحة التنبؤات")</span><span class="sxs-lookup"><span data-stu-id="14685-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="14685-153">**القيم المتنبأ بها** تُظهر التعيين الذي قمت بإنشاءه أثناء مرحلة تعيين قيمة الحقل إلى الفئة.</span><span class="sxs-lookup"><span data-stu-id="14685-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="14685-154">هذه هي القيم الموجودة في مجموعة البيانات والتي تم تعيينها إلى فئة معينة.</span><span class="sxs-lookup"><span data-stu-id="14685-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="14685-155">-**أهم المؤثرين** هم العوامل الموجودة في مجموعة البيانات التي كانت تؤثر على الأرجح في ثقة التنبؤ بقيمة الحقل الخاص بك والتي يتم تعيينها إلى فئة معينة.</span><span class="sxs-lookup"><span data-stu-id="14685-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="14685-156">**الأداء** يشير إلى الطريقة التي يتم بها القيام بالتنبؤات.</span><span class="sxs-lookup"><span data-stu-id="14685-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="14685-157">حدد الارتباط لمعرفة المزيد.</span><span class="sxs-lookup"><span data-stu-id="14685-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="14685-158">**المعاينة** تُظهر نماذج مجموعة بيانات المخرجات من التنبؤ والاحتمال الخاصين بك، أو من ثقتنا، بالقيمة المتوقعة حيث يكون 0 قيمة غير محددة و 1 قيمة محددة.</span><span class="sxs-lookup"><span data-stu-id="14685-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="14685-159">تحديث تنبؤ</span><span class="sxs-lookup"><span data-stu-id="14685-159">Update a prediction</span></span>

1. <span data-ttu-id="14685-160">في رؤى الجمهور، انتقل إلى **الذكاء** > **التنبؤات** > **التنبؤات الخاصة بي**.</span><span class="sxs-lookup"><span data-stu-id="14685-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="14685-161">حدد التنبؤ الذي ترغب في تحديثه وحدد أيقونة **تحديث**.</span><span class="sxs-lookup"><span data-stu-id="14685-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="14685-162">ستتم جدولة التنبؤ للمعالجة.</span><span class="sxs-lookup"><span data-stu-id="14685-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="14685-163">يمكنك الاطلاع على الوقت الذي تم التحديث به آخر مرة في العمود **تم التحديث** في الصفحة **التنبؤات**.</span><span class="sxs-lookup"><span data-stu-id="14685-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="14685-164">تحرير التنبؤ</span><span class="sxs-lookup"><span data-stu-id="14685-164">Edit a prediction</span></span>

<span data-ttu-id="14685-165">بعد أن تقوم تنبؤ، فإنه يمكنك تخصيص النموذج في AI Builder لزيادة فعالية النموذج الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="14685-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="14685-166">في رؤى الجمهور، انتقل إلى **الذكاء** > **التنبؤات** > **التنبؤات الخاصة بي**.</span><span class="sxs-lookup"><span data-stu-id="14685-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="14685-167">حدد التنبؤ الذي تريد تحريره.</span><span class="sxs-lookup"><span data-stu-id="14685-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="14685-168">قم بتحديد علامة الحذف في العمود **الإجراءات** واختر **عرض**.</span><span class="sxs-lookup"><span data-stu-id="14685-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="14685-169">حدد **تخصيص في AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="14685-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="14685-170">قم بتحديث النموذج الخاص بك في AI Builder.</span><span class="sxs-lookup"><span data-stu-id="14685-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="14685-171">[تعرف على المزيد حول إدارة النماذج في AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="14685-171">[Learn more about managing models in the AI builder](/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="14685-172">سيستخدم التشغيل التالي للتنبؤ الخاص بك النموذج المحدث الذي قمت بإنشاءه.</span><span class="sxs-lookup"><span data-stu-id="14685-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="14685-173">لن يتم عرض النماذج الجديدة التي تم إنشاؤها في AI Builder في رؤى الجمهور إلا إذا تم إنشاء النموذج من التجارب المذكورة أعلاه.</span><span class="sxs-lookup"><span data-stu-id="14685-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="14685-174">قم بإزالة تنبؤ</span><span class="sxs-lookup"><span data-stu-id="14685-174">Remove a prediction</span></span>

1. <span data-ttu-id="14685-175">في رؤى الجمهور، انتقل إلى **الذكاء** > **التنبؤات** > **التنبؤات الخاصة بي**.</span><span class="sxs-lookup"><span data-stu-id="14685-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="14685-176">حدد التنبؤ الذي ترغب في حذفه.</span><span class="sxs-lookup"><span data-stu-id="14685-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="14685-177">قم بتحديد علامة الحذف في العمود **الإجراءات** واختر **حذف**.</span><span class="sxs-lookup"><span data-stu-id="14685-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="14685-178">قم بتأكيد الحذف.</span><span class="sxs-lookup"><span data-stu-id="14685-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="14685-179">استكشاف الأخطاء وإصلاحها</span><span class="sxs-lookup"><span data-stu-id="14685-179">Troubleshooting</span></span>

<span data-ttu-id="14685-180">إذا لم تتمكن من إكمال عمليه الإرفاق Common Data Service بسبب خطأ ما، فيمكنك محاولة إكمال العملية يدويًا.</span><span class="sxs-lookup"><span data-stu-id="14685-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="14685-181">هناك نوعان من المشكلات المعروفة التي يمكن أن تحدث في عملية الإرفاق:</span><span class="sxs-lookup"><span data-stu-id="14685-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="14685-182">حل الوظيفة الإضافية لبطاقة العميل غير مثبت.</span><span class="sxs-lookup"><span data-stu-id="14685-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="14685-183">أكمل التعليمات لتثبيت [الحل وتكوينه](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="14685-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="14685-184">لم يتم منح أذونات التطبيق.</span><span class="sxs-lookup"><span data-stu-id="14685-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="14685-185">اذهب إلى [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="14685-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="14685-186">حدد **البيئات**.</span><span class="sxs-lookup"><span data-stu-id="14685-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="14685-187">حدد علامة القطع المجاورة للبيئة التي تريد إضافة الإذن إليها وحدد **الإعدادات**.</span><span class="sxs-lookup"><span data-stu-id="14685-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="14685-188">قم بتوسيع **المستخدمين + الأذونات** وحدد **المستخدمين**.</span><span class="sxs-lookup"><span data-stu-id="14685-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="14685-189">حدد **+ جديد** وحدد **المستخدم**.</span><span class="sxs-lookup"><span data-stu-id="14685-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="14685-190">حدد **مستخدم التطبيق** إذا لم يكن محددًا بالفعل ثم أدخل المعلومات التالية:</span><span class="sxs-lookup"><span data-stu-id="14685-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="14685-191">**اسم المستخدم:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="14685-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="14685-192">**مُعرِّف التطبيق:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="14685-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="14685-193">**الاسم الأول:** العميل</span><span class="sxs-lookup"><span data-stu-id="14685-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="14685-194">**الاسم الأخير:** Insights</span><span class="sxs-lookup"><span data-stu-id="14685-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="14685-195">**البريد الإلكتروني الرئيسي:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="14685-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="14685-196">حدد **حفظ وإغلاق**.</span><span class="sxs-lookup"><span data-stu-id="14685-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="14685-197">حدد المستخدم الذي أنشأته الآن.</span><span class="sxs-lookup"><span data-stu-id="14685-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="14685-198">حدد **إدارة الأدوار** في شريط القوائم العلوي.</span><span class="sxs-lookup"><span data-stu-id="14685-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="14685-199">حدد **مسؤول النظام**، ثم حدد **موافق**.</span><span class="sxs-lookup"><span data-stu-id="14685-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]