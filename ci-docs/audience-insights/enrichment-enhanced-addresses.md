---
title: الإثراء لتعزيز العنوان
description: إثراء معلومات العنوان وضبطها لملفات تعريف العملاء باستخدام نماذج Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305416"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="ba230-103">إثراء ملفات تعريف العملاء من خلال العناوين المحسنة</span><span class="sxs-lookup"><span data-stu-id="ba230-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="ba230-104">قد تكون العناوين الموجودة في بياناتك غير مهيكلة أو غير مكتملة أو غير صحيحة.</span><span class="sxs-lookup"><span data-stu-id="ba230-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="ba230-105">استخدم نماذج Microsoft لضبط العناوين وإثراءها في [تنسيق نموذج البيانات العامة](/common-data-model/schema/core/applicationcommon/address) لتحقيق مزيد من الدقة والتحليلات.</span><span class="sxs-lookup"><span data-stu-id="ba230-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="ba230-106">كيفية تحسين العناوين</span><span class="sxs-lookup"><span data-stu-id="ba230-106">How we enhance addresses</span></span>

<span data-ttu-id="ba230-107">يمر نموذجنا بعملية من خطوتين لتحسين العنوان.</span><span class="sxs-lookup"><span data-stu-id="ba230-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="ba230-108">أولا، يتم تحليل العنوان لتحديد مكوناته ويضعها في تنسيق مهيكل.</span><span class="sxs-lookup"><span data-stu-id="ba230-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="ba230-109">بعد ذلك، الذكاء الاصطناعي تصحيح القيم في العنوان وإكمالها وتوحيدها.</span><span class="sxs-lookup"><span data-stu-id="ba230-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="ba230-110">مثال</span><span class="sxs-lookup"><span data-stu-id="ba230-110">Example</span></span>

<span data-ttu-id="ba230-111">قد تكون معلومات العنوان بتنسيق غير محتواه وتحتوي على أخطاء إملائية.</span><span class="sxs-lookup"><span data-stu-id="ba230-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="ba230-112">يمكن للنموذج إصلاح هذه المشكلات وإنشاء عناوين متسقة في ملفات تعريف العملاء الموحدة.</span><span class="sxs-lookup"><span data-stu-id="ba230-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="ba230-113">القيود</span><span class="sxs-lookup"><span data-stu-id="ba230-113">Limitations</span></span>

<span data-ttu-id="ba230-114">تعمل العناوين المحسنة مع القيم الموجودة بالفعل في بيانات العناوين التي تم استيعابها فقط.</span><span class="sxs-lookup"><span data-stu-id="ba230-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="ba230-115">النموذج لا يقوم بـ</span><span class="sxs-lookup"><span data-stu-id="ba230-115">The model doesn't:</span></span> 

1. <span data-ttu-id="ba230-116">التحقق مما إذا كان العنوان عنوانًا صالحًا أم لا.</span><span class="sxs-lookup"><span data-stu-id="ba230-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="ba230-117">التحقق مما إذا كانت أيًا من القيم صالحة أم لا، مثل الرموز البريدية أو أسماء الشوارع.</span><span class="sxs-lookup"><span data-stu-id="ba230-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="ba230-118">تغيير القيم التي لا يتعرف عليها.</span><span class="sxs-lookup"><span data-stu-id="ba230-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="ba230-119">يستخدم النموذج التقنيات القائمة على التعلم الآلي لتحسين العناوين.</span><span class="sxs-lookup"><span data-stu-id="ba230-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="ba230-120">بينما نقوم بتطبيق حد ثقة عال عند تغيير النموذج لقيمة إدخال، كما هو في أي نموذج يستند إلى التعليم الآلي، لا تكون دقة 100 بالمائة مضمونة.</span><span class="sxs-lookup"><span data-stu-id="ba230-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="ba230-121">البلدان أو المناطق المدعومة</span><span class="sxs-lookup"><span data-stu-id="ba230-121">Supported countries or regions</span></span>

<span data-ttu-id="ba230-122">ونحن حاليًا ندعم إثراء العناوين في هذه البلدان أو المناطق:</span><span class="sxs-lookup"><span data-stu-id="ba230-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="ba230-123">أستراليا</span><span class="sxs-lookup"><span data-stu-id="ba230-123">Australia</span></span>
- <span data-ttu-id="ba230-124">كندا</span><span class="sxs-lookup"><span data-stu-id="ba230-124">Canada</span></span>
- <span data-ttu-id="ba230-125">المملكة المتحدة</span><span class="sxs-lookup"><span data-stu-id="ba230-125">United Kingdom</span></span>
- <span data-ttu-id="ba230-126">الولايات المتحدة</span><span class="sxs-lookup"><span data-stu-id="ba230-126">United States</span></span>

<span data-ttu-id="ba230-127">يجب أن تحتوي العناوين على قيمة بلد/منطقة.</span><span class="sxs-lookup"><span data-stu-id="ba230-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="ba230-128">نحن لا نقوم بمعالجة عناوين البلدان أو المناطق غير المدعومة والعناوين التي لم يتم توفير بلد أو منطقة لها.</span><span class="sxs-lookup"><span data-stu-id="ba230-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="ba230-129">تكوين الإثراء</span><span class="sxs-lookup"><span data-stu-id="ba230-129">Configure the enrichment</span></span>

1. <span data-ttu-id="ba230-130">انتقل إلى **بيانات** > **إثراء**.</span><span class="sxs-lookup"><span data-stu-id="ba230-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="ba230-131">حدد **إثراء بياناتي** في الإطار المتجانب **العناوين المحسنة**.</span><span class="sxs-lookup"><span data-stu-id="ba230-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="لقطة شاشة لتجانب العناوين المحسنة.":::

1. <span data-ttu-id="ba230-133">حدد **مجموعة بيانات العميل** واختر الكيان الذي يحتوي على العناوين التي تريد إثراءها.</span><span class="sxs-lookup"><span data-stu-id="ba230-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="ba230-134">يمكنك تحديد كيان *العميل* لإثراء العناوين في كافة ملفات تعريف العميل أو تحديد كيان شريحة لإثراء العناوين فقط في ملفات تعريف العملاء الواردة في تلك الشريحة.</span><span class="sxs-lookup"><span data-stu-id="ba230-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="ba230-135">حدد كيفية تنسيق العناوين في مجموعة البيانات الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="ba230-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="ba230-136">اختر **عنوان سمة واحدة** إذا كانت العناوين الموجودة في بياناتك تستخدم حقلاً واحدًا.</span><span class="sxs-lookup"><span data-stu-id="ba230-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="ba230-137">اختر **عنوان متعدد السمات** إذا كانت العناوين الموجودة في بياناتك تستخدم أكثر من حقل بيانات واحد.</span><span class="sxs-lookup"><span data-stu-id="ba230-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ba230-138">البلد/المنطقة إجبارية في كل من عنواني السمة الواحدة والعناوين متعددة السمات.</span><span class="sxs-lookup"><span data-stu-id="ba230-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="ba230-139">لن يتم إثراء العناوين التي لا تحتوي على قيم بلد/منطقة صالحة أو مدعومة.</span><span class="sxs-lookup"><span data-stu-id="ba230-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="ba230-140">تعيين حقول العنوان من كيان العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="ba230-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="صفحة تعيين حقل عنوان محسن.":::

1. <span data-ttu-id="ba230-142">حدد **التالي** لإكمال تعيين الحقل.</span><span class="sxs-lookup"><span data-stu-id="ba230-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="ba230-143">أدخل اسمًا للإثراء ولكيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="ba230-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="ba230-144">حدد **حفظ الإثراء** بعد مراجعة اختياراتك.</span><span class="sxs-lookup"><span data-stu-id="ba230-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ba230-145">نتائج الإثراء</span><span class="sxs-lookup"><span data-stu-id="ba230-145">Enrichment results</span></span>

<span data-ttu-id="ba230-146">لبدء عملية الإثراء، حدد **تشغيل** من شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="ba230-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="ba230-147">يمكنك أيضًا السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من [التحديث المجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ba230-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ba230-148">يعتمد وقت المعالجة على حجم بيانات العميل.</span><span class="sxs-lookup"><span data-stu-id="ba230-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="ba230-149">بعد اكتمال عملية الإثراء، يمكنك مراجعة بيانات ملفات تعريف العملاء التي تم إثراؤها حديثًا ضمن **عمليات الإثراء الخاصة بي**.</span><span class="sxs-lookup"><span data-stu-id="ba230-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="ba230-150">بالإضافة إلى ذلك ، ستجد وقت التحديث الأخير وعدد ملفات التعريف التي تم إثراؤها.</span><span class="sxs-lookup"><span data-stu-id="ba230-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ba230-151">يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.</span><span class="sxs-lookup"><span data-stu-id="ba230-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ba230-152">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="ba230-152">Next steps</span></span>

<span data-ttu-id="ba230-153">قم بالبناء أعلى بيانات العملاء التي تم إثرائها.</span><span class="sxs-lookup"><span data-stu-id="ba230-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ba230-154">أنشئ [الشرائح](segments.md) و[القياسات](measures.md) وحتى [تصدير البيانات](export-destinations.md) لتسليم تجارب مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="ba230-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
