---
title: إثراء ملفات تعريف العملاء بالبيانات من Microsoft
description: استخدم البيانات المسجلة الملكية من Microsoft لإثراء بيانات العملاء بعلامات تجارية وتقارب المصالح.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245691"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="3716a-103">إثراء ملفات تعريف العملاء بالعلامات التجارية وصلات الاهتمامات (معاينة)</span><span class="sxs-lookup"><span data-stu-id="3716a-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="3716a-104">استخدم البيانات المسجلة الملكية من Microsoft لإثراء بيانات العملاء بعلامات تجارية وتقارب المصالح.</span><span class="sxs-lookup"><span data-stu-id="3716a-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="3716a-105">يتم تحديد أوجه التشابه هذه استنادًا إلى بيانات من أشخاص لديهم نفس التركيبة السكانية لعملائك.</span><span class="sxs-lookup"><span data-stu-id="3716a-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="3716a-106">تساعدك هذه المعلومات على فهم عملائك وتقسيمهم بشكل أفضل بناءً على انتماءاتهم بعلامات تجارية ومصالح محددة.</span><span class="sxs-lookup"><span data-stu-id="3716a-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="3716a-107">في رؤى الجمهور، انتقل إلى **البيانات** > **إثراء** من أجل [تكوين الإثراءات وعرضها](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="3716a-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="3716a-108">لتكوين إثراء لصلات العلامات التجارية، انتقل إلى علامة التبويب **اكتشاف** وحدد **إثراء بياناتي** في تجانب **العلامات التجارية**.</span><span class="sxs-lookup"><span data-stu-id="3716a-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="3716a-109">لتكوين أثراء لصلات الاهتمامات، انتقل إلى علامة التبويب **اكتشاف** وحدد **إثراء بياناتي** في تجانب **الاهتمامات**.</span><span class="sxs-lookup"><span data-stu-id="3716a-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3716a-110">![تجانبات العلامات التجارية والاهتمامات](media/BrandsInterest-tile-Hub.png "تجانبات العلامات التجارية والاهتمامات")</span><span class="sxs-lookup"><span data-stu-id="3716a-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="3716a-111">كيف يمكن تحديد التشابهات</span><span class="sxs-lookup"><span data-stu-id="3716a-111">How we determine affinities</span></span>

<span data-ttu-id="3716a-112">نستخدم بيانات البحث عبر الإنترنت الخاصة ب Microsoft للبحث عن تشابهات العلامات التجارية و الاهتمامات عبر الشرائح السكانية المختلفة (معرفة حسب العمر أو الاستخدام أو الموقع).</span><span class="sxs-lookup"><span data-stu-id="3716a-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="3716a-113">يحدد حجم البحث عبر الإنترنت الخاص بإحدي العلامات التجارية أو الاهتمام مدى العلاقة بين المقطع السكانية للصلة مقارنة بالمقاطع الأخرى وعلاقتها بتلك العلامة التجارية أو الاهتمام.</span><span class="sxs-lookup"><span data-stu-id="3716a-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="3716a-114">مستوى التقارب ودرجة التقارب</span><span class="sxs-lookup"><span data-stu-id="3716a-114">Affinity level and score</span></span>

<span data-ttu-id="3716a-115">في كل ملف تعريف عملاء تم إثراؤه، نقدم قيمتين مرتبطتين - مستوى التقارب ودرجة التقارب.</span><span class="sxs-lookup"><span data-stu-id="3716a-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="3716a-116">تساعدك هذه القيم في تحديد مدى قوة التقارب بالنسبة للشريحة السكانية في ملف التعريف، بالنسبة لعلامة تجارية أو اهتمام، مقارنة بالشرائح السكانية الأخرى.</span><span class="sxs-lookup"><span data-stu-id="3716a-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="3716a-117">يتكوّن *مستوى التقارب* من أربعة مستويات، ويتم حساب *درجة التقارب* على مقياس من 100 نقطة يتم تعيينه إلى مستويات التقارب.</span><span class="sxs-lookup"><span data-stu-id="3716a-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="3716a-118">مستوى التقارب</span><span class="sxs-lookup"><span data-stu-id="3716a-118">Affinity level</span></span> |<span data-ttu-id="3716a-119">درجة التقارب</span><span class="sxs-lookup"><span data-stu-id="3716a-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="3716a-120">مرتفع جدًا</span><span class="sxs-lookup"><span data-stu-id="3716a-120">Very high</span></span>     | <span data-ttu-id="3716a-121">85-100</span><span class="sxs-lookup"><span data-stu-id="3716a-121">85-100</span></span>       |
|<span data-ttu-id="3716a-122">عالي</span><span class="sxs-lookup"><span data-stu-id="3716a-122">High</span></span>     | <span data-ttu-id="3716a-123">70-84</span><span class="sxs-lookup"><span data-stu-id="3716a-123">70-84</span></span>        |
|<span data-ttu-id="3716a-124">متوسط </span><span class="sxs-lookup"><span data-stu-id="3716a-124">Medium</span></span>     | <span data-ttu-id="3716a-125">35-69</span><span class="sxs-lookup"><span data-stu-id="3716a-125">35-69</span></span>        |
|<span data-ttu-id="3716a-126">منخفض</span><span class="sxs-lookup"><span data-stu-id="3716a-126">Low</span></span>     | <span data-ttu-id="3716a-127">1-34</span><span class="sxs-lookup"><span data-stu-id="3716a-127">1-34</span></span>        |

<span data-ttu-id="3716a-128">بالاستناد إلى مستوى النقاوة الذي ترغب فيه لقياس التقارب، يمكنك استخدام مستوى التقارب أو درجة التقارب.</span><span class="sxs-lookup"><span data-stu-id="3716a-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="3716a-129">تمنحك درجة التقارب القدرة على التحكم بشكل أدق.</span><span class="sxs-lookup"><span data-stu-id="3716a-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="3716a-130">البلدان/المناطق المدعومة</span><span class="sxs-lookup"><span data-stu-id="3716a-130">Supported countries/regions</span></span>

<span data-ttu-id="3716a-131">ندعم حاليًا خيارات البلدان/المناطق التالية: أستراليا أو كندا (الإنجليزية) أو فرنسا أو ألمانيا أو المملكة المتحدة أو الولايات المتحدة (الإنجليزية).</span><span class="sxs-lookup"><span data-stu-id="3716a-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="3716a-132">ولتحديد بلد، افتح **إثراء العلامات التجارية** أو **إثراء الاهتمام** وحدد **تغيير** بجوار **البلد/المنطقة**.</span><span class="sxs-lookup"><span data-stu-id="3716a-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="3716a-133">في جزء **إعدادات البلد/المنطقة**، اختر خيارًا وحدد **تطبيق**.</span><span class="sxs-lookup"><span data-stu-id="3716a-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="3716a-134">العواقب المتعلقة بتحديد البلد</span><span class="sxs-lookup"><span data-stu-id="3716a-134">Implications related to country selection</span></span>

- <span data-ttu-id="3716a-135">عند [اختيار علاماتك التجارية الخاصة](#define-your-brands-or-interests)، يوفر النظام اقتراحات بالاستناد إلى البلد أو المنطقة المحددة.</span><span class="sxs-lookup"><span data-stu-id="3716a-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="3716a-136">عند [اختيار مجال ما](#define-your-brands-or-interests)، ستحصل على العلامات التجارية أو الاهتمامات الأكثر صلة بالاستناد إلى البلد أو المنطقة المحددة.‬</span><span class="sxs-lookup"><span data-stu-id="3716a-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="3716a-137">عند [إثراء ملفات التعريف](#refresh-enrichment)، سنقوم بإثراء جميع ملفات تعريف العملاء التي نحصل منها على بيانات للعلامات التجارية والاهتمامات المحددة.</span><span class="sxs-lookup"><span data-stu-id="3716a-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="3716a-138">بما في ذلك ملفات التعريف غير الموجودة في البلد أو المنطقة المحددة.</span><span class="sxs-lookup"><span data-stu-id="3716a-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="3716a-139">على سبيل المثال، إذا اخترت ألمانيا، فسوف نقوم بإثراء ملفات التعريف الموجودة في الولايات المتحدة إذا كانت لدينا بيانات متوفرة للعلامة التجارية و الاهتمامات المحددة في الولايات المتحدة.</span><span class="sxs-lookup"><span data-stu-id="3716a-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="3716a-140">تكوين الإثراء</span><span class="sxs-lookup"><span data-stu-id="3716a-140">Configure Enrichment</span></span>

<span data-ttu-id="3716a-141">تساعدك تجربة إرشادية من خلال تكوين الأجهزة المهينة.</span><span class="sxs-lookup"><span data-stu-id="3716a-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="3716a-142">تحديد العلامات التجارية أو الاهتمامات</span><span class="sxs-lookup"><span data-stu-id="3716a-142">Define your brands or interests</span></span>

<span data-ttu-id="3716a-143">يمكنك اختيار ما يصل إلى خمس علامات تجارية أو اهتمامات باستخدام أحد هذه الخيارات أو كلها.</span><span class="sxs-lookup"><span data-stu-id="3716a-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="3716a-144">**المجال**: حدد المجال من القائمة المنسدلة، ثم اختر من أهم العلامات التجارية أو الاهتمامات لذلك المجال.</span><span class="sxs-lookup"><span data-stu-id="3716a-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="3716a-145">**اختيار ما يخصك‬**: أدخل علامة تجارية أو اهتمامًا يتعلق بمؤسستك، ثم اختر من الاقتراحات المطابقة.</span><span class="sxs-lookup"><span data-stu-id="3716a-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="3716a-146">إذا لم تقم بسرد العلامات التجارية أو الاهتمامات التي تبحث عنها، قم بإرسال ملاحظاتك باستخدام الارتباط **اقتراح**.</span><span class="sxs-lookup"><span data-stu-id="3716a-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="3716a-147">مراجعة تفضيلات الإثراء</span><span class="sxs-lookup"><span data-stu-id="3716a-147">Review enrichment preferences</span></span>

<span data-ttu-id="3716a-148">راجع تفضيلات الإثراء الافتراضية وحدّثها حسب الحاجة.</span><span class="sxs-lookup"><span data-stu-id="3716a-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="لقطة شاشة لنافذة تفضيلات الإثراء.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="3716a-150">تحديد كيان لإثرائه</span><span class="sxs-lookup"><span data-stu-id="3716a-150">Select entity to enrich</span></span>

<span data-ttu-id="3716a-151">حدد **الكيان الذي تم إثراؤه** واختر مجموعة البيانات التي تريد إثرائها ببيانات الشركة من Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3716a-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="3716a-152">يمكنك تحديد كيان العميل لإثراء جميع ملفات تعريف العملاء أو تحديد كيان شريحة لإثراء فقط ملفات تعريف العملاء الموجودة في تلك الشريحة.</span><span class="sxs-lookup"><span data-stu-id="3716a-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="3716a-153">تعيين الحقول الخاصة بك</span><span class="sxs-lookup"><span data-stu-id="3716a-153">Map your fields</span></span>

<span data-ttu-id="3716a-154">يمكنك تعيين حقول من كيان العميل الموحد لتحديد الشريحة السكانية التي ترغب في أن يستخدمها النظام لإثراء بيانات العميل.</span><span class="sxs-lookup"><span data-stu-id="3716a-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="3716a-155">ويمكنك تعيين البلد/المنطقة وسمات تاريخ الميلاد أو الجنس على الأقل.</span><span class="sxs-lookup"><span data-stu-id="3716a-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="3716a-156">بالإضافة إلى ذلك، يجب تعيين رمز مدينة (ولاية/إقليم) أو رمز بريدي واحد على الأقل.</span><span class="sxs-lookup"><span data-stu-id="3716a-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="3716a-157">حدد **تحرير** لتحديد تعيين الحقول وقم بتحديد **تطبيق** عند الانتهاء.</span><span class="sxs-lookup"><span data-stu-id="3716a-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="3716a-158">حدد **حفظ** لإكمال تعيين الحقل.</span><span class="sxs-lookup"><span data-stu-id="3716a-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="3716a-159">تحظى التنسيقات والقيم التالية بالدعم، والقيم ليست حساسة لحالة الأحرف:</span><span class="sxs-lookup"><span data-stu-id="3716a-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="3716a-160">**تاريخ الميلاد**: يستحسن تحويل تاريخ الميلاد إلى نوع التاريخ والوقت خلال ‏‫استيعاب البيانات‬.</span><span class="sxs-lookup"><span data-stu-id="3716a-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="3716a-161">ويمكن بدلاً من ذلك أن يكون سلسلة في [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) بالتنسيق "س س س-ش ش-ي ي أو "yyyy-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="3716a-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="3716a-162">**النوع**: ذكر، أنثى، غير معروف</span><span class="sxs-lookup"><span data-stu-id="3716a-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="3716a-163">**الرمز البريدي**: رمز بريدي مكون من خمسة أرقام للولايات المتحدة، والرمز البريدي القياسي في أي مكان آخر</span><span class="sxs-lookup"><span data-stu-id="3716a-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="3716a-164">**المدينة**: اسم المدينة باللغة الإنجليزية</span><span class="sxs-lookup"><span data-stu-id="3716a-164">**City**: City name in English</span></span>
- <span data-ttu-id="3716a-165">**الولاية/المقاطعة**: اختصار من حرفين للولايات المتحدة وكندا.</span><span class="sxs-lookup"><span data-stu-id="3716a-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="3716a-166">اختصار من حرفين أو ثلاثة لأستراليا.</span><span class="sxs-lookup"><span data-stu-id="3716a-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="3716a-167">لا ينطبق هذا على فرنسا أو ألمانيا أو المملكة المتحدة.</span><span class="sxs-lookup"><span data-stu-id="3716a-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="3716a-168">**الدولة/المنطقة**:</span><span class="sxs-lookup"><span data-stu-id="3716a-168">**Country/Region**:</span></span>

  - <span data-ttu-id="3716a-169">الولايات المتحدة: الولايات المتحدة الأمريكية، USA، US، أمريكا</span><span class="sxs-lookup"><span data-stu-id="3716a-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="3716a-170">CA: كندا، CA</span><span class="sxs-lookup"><span data-stu-id="3716a-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="3716a-171">GB: المملكة المتحدة، UK، بريطانيا العظمى، GB، المملكة المتحدة لبريطانيا العظمى وأيرلندا الشمالية، المملكة المتحدة لبريطانيا العظمى</span><span class="sxs-lookup"><span data-stu-id="3716a-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="3716a-172">AU: أستراليا، AU، كومنولث أستراليا</span><span class="sxs-lookup"><span data-stu-id="3716a-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="3716a-173">FR: فرنسا، FR، الجمهورية الفرنسية</span><span class="sxs-lookup"><span data-stu-id="3716a-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="3716a-174">DE: ألمانيا، DE، جمهورية ألمانيا الاتحادية، جمهورية ألمانيا</span><span class="sxs-lookup"><span data-stu-id="3716a-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="3716a-175">مراجعة الإثراء وتسميته</span><span class="sxs-lookup"><span data-stu-id="3716a-175">Review and name the enrichment</span></span>

<span data-ttu-id="3716a-176">أخيرًا، يمكنك مراجعة المعلومات وتوفير اسم للإثراء.</span><span class="sxs-lookup"><span data-stu-id="3716a-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="صفحة مراجعة وتسمية الاهتمامات.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="3716a-178">تحديث عملية الإثراء</span><span class="sxs-lookup"><span data-stu-id="3716a-178">Refresh enrichment</span></span>

<span data-ttu-id="3716a-179">قم بتشغيل الإثراء بعد تكوين العلامات التجارية والاهتمامات وتعيين الحقول للمخططات السكانية.</span><span class="sxs-lookup"><span data-stu-id="3716a-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="3716a-180">لبدء العملية، حدد **تشغيل** في صفحة تكوين العلامة التجارية أو الاهتمام.</span><span class="sxs-lookup"><span data-stu-id="3716a-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="3716a-181">بالإضافة إلى ذلك، يمكنك السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من التحديث المجدول.</span><span class="sxs-lookup"><span data-stu-id="3716a-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="3716a-182">ووفقًا لحجم بيانات العملاء، قد يستغرق الأمر عدة ثوان لإكمال تشغيل الإثراء.</span><span class="sxs-lookup"><span data-stu-id="3716a-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="3716a-183">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="3716a-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3716a-184">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="3716a-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3716a-185">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="3716a-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3716a-186">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="3716a-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="3716a-187">نتائج الإثراء</span><span class="sxs-lookup"><span data-stu-id="3716a-187">Enrichment results</span></span>

<span data-ttu-id="3716a-188">بعد تشغيل عملية الإثراء، انتقل إلى **عمليات الإثراء الخاصة بي** لمراجعة إجمالي عدد العملاء الذين تم إثرائهم وتصنيف العلامات التجارية أو الاهتمامات في ملفات تعريف العملاء الذين تم إثرائهم.</span><span class="sxs-lookup"><span data-stu-id="3716a-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="معاينه النتائج بعد تشغيل عمليه الإثراء":::

<span data-ttu-id="3716a-190">راجع البيانات التي تم إثرائها من خلال تحديد **عرض البيانات التي تم إثراؤها‬** في المخطط.</span><span class="sxs-lookup"><span data-stu-id="3716a-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="3716a-191">تنتقل بيانات العلامات التجارية التي تم إثرائها إلى الكيان **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="3716a-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="3716a-192">بيانات الاهتمامات في الكيان **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="3716a-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="3716a-193">كما ستجد هذه الكيانات المدرجة في مجموعه **الإثراء**  في **البيانات** > **الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="3716a-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="3716a-194">راجع بيانات الإثراء على بطاقة العملاء</span><span class="sxs-lookup"><span data-stu-id="3716a-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="3716a-195">كما يمكن عرض أوجه تشابه العلامات التجارية والاهتمامات في بطاقات العملاء الفردية.</span><span class="sxs-lookup"><span data-stu-id="3716a-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="3716a-196">انتقل إلى **العملاء** وحدد ملف التعريف الخاص بالعميل.</span><span class="sxs-lookup"><span data-stu-id="3716a-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="3716a-197">وفي بطاقة العملاء، ستجد مخططات لكل من العلامات التجارية أو الاهتمام التي لها صلة بالأشخاص في ملف التعريف السكاني لهذا العميل.</span><span class="sxs-lookup"><span data-stu-id="3716a-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="بطاقة العملاء مع البيانات التي تم إثراؤها":::

## <a name="next-steps"></a><span data-ttu-id="3716a-199">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="3716a-199">Next steps</span></span>

<span data-ttu-id="3716a-200">قم بالبناء أعلى بيانات العملاء التي تم إثرائها.</span><span class="sxs-lookup"><span data-stu-id="3716a-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3716a-201">أنشئ [الشرائح](segments.md)، و[المقاييس](measures.md)، وقم كذلك [بتصدير البيانات](export-destinations.md) لتقديم تجارب مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="3716a-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
