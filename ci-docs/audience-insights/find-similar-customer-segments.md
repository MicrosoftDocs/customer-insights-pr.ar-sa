---
title: البحث عن عملاء مماثلين بواسطة الذكاء الاصطناعي
description: يمكنك العثور على شرائح من العملاء المماثلين باستخدام الذكاء الاصطناعي.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 8cdec4edd599b0249fcf144b5e5c0124504e1e14
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4404927"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="130eb-103">العملاء المماثلون (معاينة)</span><span class="sxs-lookup"><span data-stu-id="130eb-103">Similar Customers (preview)</span></span>

<span data-ttu-id="130eb-104">تتيح لك هذه الميزة العثور على عملاء مماثلين في قاعدة عملائك باستخدام الذكاء الاصطناعي.</span><span class="sxs-lookup"><span data-stu-id="130eb-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="130eb-105">تحتاج إلى إنشاء شريحة واحدة على الأقل لاستخدام هذه الميزة.</span><span class="sxs-lookup"><span data-stu-id="130eb-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="130eb-106">يؤدي توسيع معايير شريحة موجودة إلى المساعدة في العثور على العملاء المماثلين لهذه الشريحة.</span><span class="sxs-lookup"><span data-stu-id="130eb-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="130eb-107">يستخدم الخيار *البحث عن عملاء مماثلين* وسائل مؤتمتة لتقييم البيانات واجراء التنبؤ استنادًا إلى تلك البيانات، وبالتالي يمكن استخدامه كطريقة لإنشاء ملفات التعريف، كهذا المصطلح المحدد بواسطة القانون العام لحماية البيانات (“GDPR”).</span><span class="sxs-lookup"><span data-stu-id="130eb-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="130eb-108">قد يخضع استخدام العميل لهذه الميزة لمعالجة البيانات حسب قانون GDPR أو القوانين أو اللوائح الأخرى.</span><span class="sxs-lookup"><span data-stu-id="130eb-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="130eb-109">إذا كنت مسؤولاً عن التأكد من أن استخدام Dynamics 365 Customer Insights، بما في ذلك التنبؤات، يتوافق مع كافة القوانين واللوائح المعمول بها، بما في ذلك القوانين المتعلقة بالخصوصية والبيانات الشخصية وبيانات المقاييس الحيوية وحماية البيانات وسرية الاتصالات.</span><span class="sxs-lookup"><span data-stu-id="130eb-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="130eb-110">العثور على عملاء مماثلين (معاينة)</span><span class="sxs-lookup"><span data-stu-id="130eb-110">Finding similar customers</span></span>

1. <span data-ttu-id="130eb-111">في رؤى الجمهور، انتقل إلى **الشرائح** وحدد الشريحة التي تريد إسناد الشريحة الجديدة إليها.</span><span class="sxs-lookup"><span data-stu-id="130eb-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="130eb-112">هذا هي *الشريحة المصدر*.</span><span class="sxs-lookup"><span data-stu-id="130eb-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="130eb-113">في شريط الإجراءات، حدد **البحث عن عملاء مماثلين**.</span><span class="sxs-lookup"><span data-stu-id="130eb-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="130eb-114">راجع الاسم المقترح للشريحة الجديدة وقم بتغييره إذا لزم الأمر.</span><span class="sxs-lookup"><span data-stu-id="130eb-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="130eb-115">راجع الحقول التي تحدد شريحتك الجديدة.</span><span class="sxs-lookup"><span data-stu-id="130eb-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="130eb-116">تحدد هذه الحقول الأساس الذي سيحاول النظام من خلاله العثور على عملاء مماثلين لشريحتك المصدر.</span><span class="sxs-lookup"><span data-stu-id="130eb-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="130eb-117">سيقوم النظام بتحديد الحقول الموصى بها بشكل افتراضي.</span><span class="sxs-lookup"><span data-stu-id="130eb-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="130eb-118">تُستبعد بشكل تلقائي الحقول التي يمكنها أن تقلل بشكل ملحوظ من أداء النموذج:</span><span class="sxs-lookup"><span data-stu-id="130eb-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="130eb-119">الحقول التي تحتوي على أنواع البيانات التالية: StringType وBooleanType وCharType وLongType وIntType وDoubleType وFloatType وShortType</span><span class="sxs-lookup"><span data-stu-id="130eb-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="130eb-120">حقول ذات علاقة أساسية (عدد العناصر في حقل) أقل من 2 أو أكثر من 30</span><span class="sxs-lookup"><span data-stu-id="130eb-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="130eb-121">اختر ما إذا كنت ترغب في تضمين **كافة العملاء** أو فقط العملاء في **شريحة معينة موجودة** في شريحتك الجديدة.</span><span class="sxs-lookup"><span data-stu-id="130eb-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="130eb-122">يمكنك استبعاد عملاء في شريحتك المصدر بتحديد خانة الاختيار **استبعاد الكل في الشريحة المصدر**.</span><span class="sxs-lookup"><span data-stu-id="130eb-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="130eb-123">بشكل افتراضي، يقترح النظام تضمين 20% فقط من حجم الجمهور الهدف في الناتج.</span><span class="sxs-lookup"><span data-stu-id="130eb-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="130eb-124">يمكنك تحرير هذا الحد حسب الحاجة.</span><span class="sxs-lookup"><span data-stu-id="130eb-124">Edit this threshold as needed.</span></span> <span data-ttu-id="130eb-125">ستؤدي زيادة الحد إلى تقليل الدقة.</span><span class="sxs-lookup"><span data-stu-id="130eb-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="130eb-126">حدد **تشغيل** أسفل الصفحة لبدء مهمة تصنيف ثنائي (طريقه التعلم الآلي) تحلل مجموعة البيانات.</span><span class="sxs-lookup"><span data-stu-id="130eb-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="130eb-127">عرض الشريحة المماثلة</span><span class="sxs-lookup"><span data-stu-id="130eb-127">View the similar segment</span></span>

<span data-ttu-id="130eb-128">بعد معالجه الشريحة المماثلة، ستجد الشريحة الجديدة مدرجة في صفحة **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="130eb-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="130eb-129">![شريحة العملاء المماثلين](media/expanded-segment.png "شريحة العملاء المماثلين")</span><span class="sxs-lookup"><span data-stu-id="130eb-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="130eb-130">حدد **عرض** في شريط الإجراءات لفتح تفاصيل الشريحة.</span><span class="sxs-lookup"><span data-stu-id="130eb-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="130eb-131">تحتوي طريقه العرض هذه على معلومات حول توزيع النتائج عبر [عدد نقاط التماثل](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="130eb-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="130eb-132">كما ستجد قيم عدد نقاط التماثل في **معاينة أعضاء الشريحة**.</span><span class="sxs-lookup"><span data-stu-id="130eb-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="130eb-133">استخدام ناتج شريحة مماثلة</span><span class="sxs-lookup"><span data-stu-id="130eb-133">Use the output of a similar segment</span></span>

<span data-ttu-id="130eb-134">يمكنك [العمل مع الناتج من شريحة مماثلة](segments.md) كما تفعل مع الشرائح الأخرى.</span><span class="sxs-lookup"><span data-stu-id="130eb-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="130eb-135">على سبيل المثال، يمكنك تصدير الشريحة أو إنشاء مقياس.</span><span class="sxs-lookup"><span data-stu-id="130eb-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="130eb-136">تحديث وتحرير شريحة مماثلة</span><span class="sxs-lookup"><span data-stu-id="130eb-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="130eb-137">لتحديث شريحة مماثلة، حددها في صفحة **الشرائح** وحدد **تحديث** في شريط الإجراءات.</span><span class="sxs-lookup"><span data-stu-id="130eb-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="130eb-138">سيؤدي تحرير شريحة مماثلة إلى إعادة معالجة بياناتك.</span><span class="sxs-lookup"><span data-stu-id="130eb-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="130eb-139">يتم تحديث الشريحة التي تم إنشاؤها في السابق بواسطة لبيانات المحدثة.</span><span class="sxs-lookup"><span data-stu-id="130eb-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="130eb-140">لتحرير شريحة مماثلة، حددها في صفحة **الشرائح** وحدد **تحرير** في شريط الإجراءات.</span><span class="sxs-lookup"><span data-stu-id="130eb-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="130eb-141">طبّق تغييراتك وحدد **تشغيل** لبدء المعالجة.</span><span class="sxs-lookup"><span data-stu-id="130eb-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="130eb-142">حذف شريحة مماثلة</span><span class="sxs-lookup"><span data-stu-id="130eb-142">Delete a similar segment</span></span>

<span data-ttu-id="130eb-143">حدد الشريحة في صفحة **الشرائح** وحدد **حذف** في شريط الإجراءات.</span><span class="sxs-lookup"><span data-stu-id="130eb-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="130eb-144">ثم أكد عملية الحذف.</span><span class="sxs-lookup"><span data-stu-id="130eb-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="130eb-145">حول عدد نقاط التماثل</span><span class="sxs-lookup"><span data-stu-id="130eb-145">About similarity scores</span></span>

<span data-ttu-id="130eb-146">يعين نموذج التعلم الآلي للتصنيف الثنائي نقاطًا للعملاء في الشريحة المماثلة.</span><span class="sxs-lookup"><span data-stu-id="130eb-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="130eb-147">تستند النقاط إلى تماثل العملاء في الشريحة المصدر.</span><span class="sxs-lookup"><span data-stu-id="130eb-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="130eb-148">نقاط التماثل التي تقل عن 0.55 تتعلق بالعملاء الذين صنفهم النظام في خانة العملاء *غير المماثلين* في الشريحة المصدر</span><span class="sxs-lookup"><span data-stu-id="130eb-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="130eb-149">يتم تصنيف عدد نقاط التماثل من 0.55 إلى 0.7 في خانة العملاء *المماثلين إلى حد ما*</span><span class="sxs-lookup"><span data-stu-id="130eb-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="130eb-150">يتم تصنيف عدد نقاط التماثل من 0.7 إلى 0.85 في خانة العملاء *المماثلين*</span><span class="sxs-lookup"><span data-stu-id="130eb-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="130eb-151">يتعلق عدد نقاط التماثل من 0.85 إلى 1 بالعملاء الذين صنفهم النظام في خانة العملاء *المماثلين جدًا*</span><span class="sxs-lookup"><span data-stu-id="130eb-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="130eb-152">لا يتضمن ناتج النموذج العملاء الذين لديهم نقاط تماثل أقل من 0.4.</span><span class="sxs-lookup"><span data-stu-id="130eb-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="130eb-153">لا يعتبرهم النظام مماثلة بشكل كاف للشريحة المصدر.</span><span class="sxs-lookup"><span data-stu-id="130eb-153">The system doesn't consider them similar enough to the source segment.</span></span>
