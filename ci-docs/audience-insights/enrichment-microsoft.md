---
title: إثراء ملفات تعريف العملاء بالبيانات من Microsoft
description: استخدم البيانات المسجلة الملكية من Microsoft لإثراء بيانات العملاء بعلامات تجارية وتقارب المصالح.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: be042dd139607849b795c903fa58da2edb9ff589
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064875"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="db048-103">إثراء ملفات تعريف العملاء بالعلامات التجارية وصلات الاهتمامات (معاينة)</span><span class="sxs-lookup"><span data-stu-id="db048-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="db048-104">استخدم البيانات المسجلة الملكية من Microsoft لإثراء بيانات العملاء بعلامات تجارية وتقارب المصالح.</span><span class="sxs-lookup"><span data-stu-id="db048-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="db048-105">يتم تحديد أوجه التشابه هذه استنادًا إلى بيانات من أشخاص لديهم نفس التركيبة السكانية لعملائك.</span><span class="sxs-lookup"><span data-stu-id="db048-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="db048-106">تساعدك هذه المعلومات على فهم عملائك وتقسيمهم بشكل أفضل بناءً على انتماءاتهم بعلامات تجارية ومصالح محددة.</span><span class="sxs-lookup"><span data-stu-id="db048-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="db048-107">في رؤى الجمهور، انتقل إلى **البيانات** > **إثراء** من أجل [تكوين الإثراءات وعرضها](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="db048-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="db048-108">لتكوين إثراء لصلات العلامات التجارية، انتقل إلى علامة التبويب **اكتشاف** وحدد **إثراء بياناتي** في تجانب **العلامات التجارية**.</span><span class="sxs-lookup"><span data-stu-id="db048-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="db048-109">لتكوين أثراء لصلات الاهتمامات، انتقل إلى علامة التبويب **اكتشاف** وحدد **إثراء بياناتي** في تجانب **الاهتمامات**.</span><span class="sxs-lookup"><span data-stu-id="db048-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="db048-110">![تجانبات العلامات التجارية والاهتمامات](media/BrandsInterest-tile-Hub.png "تجانبات العلامات التجارية والاهتمامات")</span><span class="sxs-lookup"><span data-stu-id="db048-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="db048-111">كيف يمكن تحديد التشابهات</span><span class="sxs-lookup"><span data-stu-id="db048-111">How we determine affinities</span></span>

<span data-ttu-id="db048-112">نستخدم بيانات البحث عبر الإنترنت الخاصة ب Microsoft للبحث عن تشابهات العلامات التجارية و الاهتمامات عبر الشرائح السكانية المختلفة (معرفة حسب العمر أو الاستخدام أو الموقع).</span><span class="sxs-lookup"><span data-stu-id="db048-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="db048-113">يحدد حجم البحث عبر الإنترنت الخاص بإحدي العلامات التجارية أو الاهتمام مدى العلاقة بين المقطع السكانية للصلة مقارنة بالمقاطع الأخرى وعلاقتها بتلك العلامة التجارية أو الاهتمام.</span><span class="sxs-lookup"><span data-stu-id="db048-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="db048-114">مستوى التقارب ودرجة التقارب</span><span class="sxs-lookup"><span data-stu-id="db048-114">Affinity level and score</span></span>

<span data-ttu-id="db048-115">في كل ملف تعريف عملاء تم إثراؤه، نقدم قيمتين مرتبطتين - مستوى التقارب ودرجة التقارب.</span><span class="sxs-lookup"><span data-stu-id="db048-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="db048-116">تساعدك هذه القيم في تحديد مدى قوة التقارب بالنسبة للشريحة السكانية في ملف التعريف، بالنسبة لعلامة تجارية أو اهتمام، مقارنة بالشرائح السكانية الأخرى.</span><span class="sxs-lookup"><span data-stu-id="db048-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="db048-117">يتكوّن *مستوى التقارب* من أربعة مستويات، ويتم حساب *درجة التقارب* على مقياس من 100 نقطة يتم تعيينه إلى مستويات التقارب.</span><span class="sxs-lookup"><span data-stu-id="db048-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="db048-118">مستوى التقارب</span><span class="sxs-lookup"><span data-stu-id="db048-118">Affinity level</span></span> |<span data-ttu-id="db048-119">درجة التقارب</span><span class="sxs-lookup"><span data-stu-id="db048-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="db048-120">مرتفع جدًا</span><span class="sxs-lookup"><span data-stu-id="db048-120">Very high</span></span>     | <span data-ttu-id="db048-121">85-100</span><span class="sxs-lookup"><span data-stu-id="db048-121">85-100</span></span>       |
|<span data-ttu-id="db048-122">عالي</span><span class="sxs-lookup"><span data-stu-id="db048-122">High</span></span>     | <span data-ttu-id="db048-123">70-84</span><span class="sxs-lookup"><span data-stu-id="db048-123">70-84</span></span>        |
|<span data-ttu-id="db048-124">متوسط </span><span class="sxs-lookup"><span data-stu-id="db048-124">Medium</span></span>     | <span data-ttu-id="db048-125">35-69</span><span class="sxs-lookup"><span data-stu-id="db048-125">35-69</span></span>        |
|<span data-ttu-id="db048-126">منخفض</span><span class="sxs-lookup"><span data-stu-id="db048-126">Low</span></span>     | <span data-ttu-id="db048-127">1-34</span><span class="sxs-lookup"><span data-stu-id="db048-127">1-34</span></span>        |

<span data-ttu-id="db048-128">بالاستناد إلى مستوى النقاوة الذي ترغب فيه لقياس التقارب، يمكنك استخدام مستوى التقارب أو درجة التقارب.</span><span class="sxs-lookup"><span data-stu-id="db048-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="db048-129">تمنحك درجة التقارب القدرة على التحكم بشكل أدق.</span><span class="sxs-lookup"><span data-stu-id="db048-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="db048-130">البلدان/المناطق المدعومة</span><span class="sxs-lookup"><span data-stu-id="db048-130">Supported countries/regions</span></span>

<span data-ttu-id="db048-131">ندعم حاليًا خيارات البلدان/المناطق التالية: أستراليا أو كندا (الإنجليزية) أو فرنسا أو ألمانيا أو المملكة المتحدة أو الولايات المتحدة (الإنجليزية).</span><span class="sxs-lookup"><span data-stu-id="db048-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="db048-132">ولتحديد بلد، افتح **إثراء العلامات التجارية** أو **إثراء الاهتمام** وحدد **تغيير** بجوار **البلد/المنطقة**.</span><span class="sxs-lookup"><span data-stu-id="db048-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="db048-133">في جزء **إعدادات البلد/المنطقة**، اختر خيارًا وحدد **تطبيق**.</span><span class="sxs-lookup"><span data-stu-id="db048-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="db048-134">العواقب المتعلقة بتحديد البلد</span><span class="sxs-lookup"><span data-stu-id="db048-134">Implications related to country selection</span></span>

- <span data-ttu-id="db048-135">عند [اختيار علاماتك التجارية الخاصة](#define-your-brands-or-interests)، يوفر النظام اقتراحات بالاستناد إلى البلد أو المنطقة المحددة.</span><span class="sxs-lookup"><span data-stu-id="db048-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="db048-136">عند [اختيار مجال ما](#define-your-brands-or-interests)، ستحصل على العلامات التجارية أو الاهتمامات الأكثر صلة بالاستناد إلى البلد أو المنطقة المحددة.‬</span><span class="sxs-lookup"><span data-stu-id="db048-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="db048-137">عند [إثراء ملفات التعريف](#refresh-enrichment)، سنقوم بإثراء جميع ملفات تعريف العملاء التي نحصل منها على بيانات للعلامات التجارية والاهتمامات المحددة.</span><span class="sxs-lookup"><span data-stu-id="db048-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="db048-138">بما في ذلك ملفات التعريف غير الموجودة في البلد أو المنطقة المحددة.</span><span class="sxs-lookup"><span data-stu-id="db048-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="db048-139">على سبيل المثال، إذا اخترت ألمانيا، فسوف نقوم بإثراء ملفات التعريف الموجودة في الولايات المتحدة إذا كانت لدينا بيانات متوفرة للعلامة التجارية و الاهتمامات المحددة في الولايات المتحدة.</span><span class="sxs-lookup"><span data-stu-id="db048-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="db048-140">تكوين الإثراء</span><span class="sxs-lookup"><span data-stu-id="db048-140">Configure Enrichment</span></span>

<span data-ttu-id="db048-141">تساعدك تجربة إرشادية من خلال تكوين الأجهزة المهينة.</span><span class="sxs-lookup"><span data-stu-id="db048-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="db048-142">تحديد العلامات التجارية أو الاهتمامات</span><span class="sxs-lookup"><span data-stu-id="db048-142">Define your brands or interests</span></span>

<span data-ttu-id="db048-143">حدد واحدًا من الخيارات التالية:</span><span class="sxs-lookup"><span data-stu-id="db048-143">Select one of the following options:</span></span>

- <span data-ttu-id="db048-144">**الصناعة**: يحدد النظام أفضل العلامات التجارية أو الاهتمامات المتعلقة بمجالك ويقوم بإثراء بيانات العميل بها.</span><span class="sxs-lookup"><span data-stu-id="db048-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="db048-145">**اختيار ما يخصك**: حدد ما يصل إلى خمسة عناصر من قائمة العلامات التجارية أو الاهتمامات الأكثر صله بالمؤسسة.</span><span class="sxs-lookup"><span data-stu-id="db048-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="db048-146">لإضافة علامة تجارية أو ذات أهمية، قم بإدخالها في منطقة الإدخال للحصول على اقتراحات استنادًا إلى المصطلحات المطابقة.</span><span class="sxs-lookup"><span data-stu-id="db048-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="db048-147">إذا لم تقم بسرد العلامات التجارية أو الاهتمامات التي تبحث عنها، قم بإرسال ملاحظاتك باستخدام الارتباط **اقتراح**.</span><span class="sxs-lookup"><span data-stu-id="db048-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="db048-148">مراجعة تفضيلات الإثراء</span><span class="sxs-lookup"><span data-stu-id="db048-148">Review enrichment preferences</span></span>

<span data-ttu-id="db048-149">راجع تفضيلات الإثراء الافتراضية وحدّثها حسب الحاجة.</span><span class="sxs-lookup"><span data-stu-id="db048-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="لقطة شاشة لنافذة تفضيلات الإثراء.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="db048-151">تحديد كيان لإثرائه</span><span class="sxs-lookup"><span data-stu-id="db048-151">Select entity to enrich</span></span>

<span data-ttu-id="db048-152">حدد **الكيان الذي تم إثراؤه** واختر مجموعة البيانات التي تريد إثرائها ببيانات الشركة من Microsoft.</span><span class="sxs-lookup"><span data-stu-id="db048-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="db048-153">يمكنك تحديد كيان العميل لإثراء جميع ملفات تعريف العملاء أو تحديد كيان شريحة لإثراء فقط ملفات تعريف العملاء الموجودة في تلك الشريحة.</span><span class="sxs-lookup"><span data-stu-id="db048-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="db048-154">تعيين الحقول الخاصة بك</span><span class="sxs-lookup"><span data-stu-id="db048-154">Map your fields</span></span>

<span data-ttu-id="db048-155">يمكنك تعيين حقول من كيان العميل الموحد لتحديد الشريحة السكانية التي ترغب في أن يستخدمها النظام لإثراء بيانات العميل.</span><span class="sxs-lookup"><span data-stu-id="db048-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="db048-156">ويمكنك تعيين البلد/المنطقة وسمات تاريخ الميلاد أو الجنس على الأقل.</span><span class="sxs-lookup"><span data-stu-id="db048-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="db048-157">بالإضافة إلى ذلك، يجب تعيين رمز مدينة (ولاية/إقليم) أو رمز بريدي واحد على الأقل.</span><span class="sxs-lookup"><span data-stu-id="db048-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="db048-158">حدد **تحرير** لتحديد تعيين الحقول وقم بتحديد **تطبيق** عند الانتهاء.</span><span class="sxs-lookup"><span data-stu-id="db048-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="db048-159">حدد **حفظ** لإكمال تعيين الحقل.</span><span class="sxs-lookup"><span data-stu-id="db048-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="db048-160">تحظى التنسيقات والقيم التالية بالدعم، والقيم ليست حساسة لحالة الأحرف:</span><span class="sxs-lookup"><span data-stu-id="db048-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="db048-161">**تاريخ الميلاد**: يستحسن تحويل تاريخ الميلاد إلى نوع التاريخ والوقت خلال ‏‫استيعاب البيانات‬.</span><span class="sxs-lookup"><span data-stu-id="db048-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="db048-162">ويمكن بدلاً من ذلك أن يكون سلسلة في [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) بالتنسيق "س س س-ش ش-ي ي أو "yyyy-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="db048-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="db048-163">**النوع**: ذكر، أنثى، غير معروف</span><span class="sxs-lookup"><span data-stu-id="db048-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="db048-164">**الرمز البريدي**: رمز بريدي مكون من خمسة أرقام للولايات المتحدة، والرمز البريدي القياسي في أي مكان آخر</span><span class="sxs-lookup"><span data-stu-id="db048-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="db048-165">**المدينة**: اسم المدينة باللغة الإنجليزية</span><span class="sxs-lookup"><span data-stu-id="db048-165">**City**: City name in English</span></span>
- <span data-ttu-id="db048-166">**الولاية/المقاطعة**: اختصار من حرفين للولايات المتحدة وكندا.</span><span class="sxs-lookup"><span data-stu-id="db048-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="db048-167">اختصار من حرفين أو ثلاثة لأستراليا.</span><span class="sxs-lookup"><span data-stu-id="db048-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="db048-168">لا ينطبق هذا على فرنسا أو ألمانيا أو المملكة المتحدة.</span><span class="sxs-lookup"><span data-stu-id="db048-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="db048-169">**الدولة/المنطقة**:</span><span class="sxs-lookup"><span data-stu-id="db048-169">**Country/Region**:</span></span>

  - <span data-ttu-id="db048-170">الولايات المتحدة: الولايات المتحدة الأمريكية، USA، US، أمريكا</span><span class="sxs-lookup"><span data-stu-id="db048-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="db048-171">CA: كندا، CA</span><span class="sxs-lookup"><span data-stu-id="db048-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="db048-172">GB: المملكة المتحدة، UK، بريطانيا العظمى، GB، المملكة المتحدة لبريطانيا العظمى وأيرلندا الشمالية، المملكة المتحدة لبريطانيا العظمى</span><span class="sxs-lookup"><span data-stu-id="db048-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="db048-173">AU: أستراليا، AU، كومنولث أستراليا</span><span class="sxs-lookup"><span data-stu-id="db048-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="db048-174">FR: فرنسا، FR، الجمهورية الفرنسية</span><span class="sxs-lookup"><span data-stu-id="db048-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="db048-175">DE: ألمانيا، DE، جمهورية ألمانيا الاتحادية، جمهورية ألمانيا</span><span class="sxs-lookup"><span data-stu-id="db048-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="db048-176">مراجعة الإثراء وتسميته</span><span class="sxs-lookup"><span data-stu-id="db048-176">Review and name the enrichment</span></span>

<span data-ttu-id="db048-177">أخيرًا، يمكنك مراجعة المعلومات وتوفير اسم للإثراء.</span><span class="sxs-lookup"><span data-stu-id="db048-177">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="صفحة مراجعة وتسمية الاهتمامات.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="db048-179">تحديث عملية الإثراء</span><span class="sxs-lookup"><span data-stu-id="db048-179">Refresh enrichment</span></span>

<span data-ttu-id="db048-180">قم بتشغيل الإثراء بعد تكوين العلامات التجارية والاهتمامات وتعيين الحقول للمخططات السكانية.</span><span class="sxs-lookup"><span data-stu-id="db048-180">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="db048-181">لبدء العملية، حدد **تشغيل** في صفحة تكوين العلامة التجارية أو الاهتمام.</span><span class="sxs-lookup"><span data-stu-id="db048-181">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="db048-182">بالإضافة إلى ذلك، يمكنك السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من التحديث المجدول.</span><span class="sxs-lookup"><span data-stu-id="db048-182">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="db048-183">ووفقًا لحجم بيانات العملاء، قد يستغرق الأمر عدة ثوان لإكمال تشغيل الإثراء.</span><span class="sxs-lookup"><span data-stu-id="db048-183">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="db048-184">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="db048-184">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="db048-185">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="db048-185">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="db048-186">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="db048-186">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="db048-187">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="db048-187">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="db048-188">نتائج الإثراء</span><span class="sxs-lookup"><span data-stu-id="db048-188">Enrichment results</span></span>

<span data-ttu-id="db048-189">بعد تشغيل عملية الإثراء، انتقل إلى **عمليات الإثراء الخاصة بي** لمراجعة إجمالي عدد العملاء الذين تم إثرائهم وتصنيف العلامات التجارية أو الاهتمامات في ملفات تعريف العملاء الذين تم إثرائهم.</span><span class="sxs-lookup"><span data-stu-id="db048-189">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="معاينه النتائج بعد تشغيل عمليه الإثراء":::

<span data-ttu-id="db048-191">راجع البيانات التي تم إثرائها من خلال تحديد **عرض البيانات التي تم إثراؤها‬** في المخطط.</span><span class="sxs-lookup"><span data-stu-id="db048-191">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="db048-192">تنتقل بيانات العلامات التجارية التي تم إثرائها إلى الكيان **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="db048-192">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="db048-193">بيانات الاهتمامات في الكيان **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="db048-193">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="db048-194">كما ستجد هذه الكيانات المدرجة في مجموعه **الإثراء**  في **البيانات** > **الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="db048-194">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="db048-195">راجع بيانات الإثراء على بطاقة العملاء</span><span class="sxs-lookup"><span data-stu-id="db048-195">See enrichment data on the customer card</span></span>

<span data-ttu-id="db048-196">كما يمكن عرض أوجه تشابه العلامات التجارية والاهتمامات في بطاقات العملاء الفردية.</span><span class="sxs-lookup"><span data-stu-id="db048-196">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="db048-197">انتقل إلى **العملاء** وحدد ملف التعريف الخاص بالعميل.</span><span class="sxs-lookup"><span data-stu-id="db048-197">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="db048-198">وفي بطاقة العملاء، ستجد مخططات لكل من العلامات التجارية أو الاهتمام التي لها صلة بالأشخاص في ملف التعريف السكاني لهذا العميل.</span><span class="sxs-lookup"><span data-stu-id="db048-198">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="بطاقة العملاء مع البيانات التي تم إثراؤها":::

## <a name="next-steps"></a><span data-ttu-id="db048-200">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="db048-200">Next steps</span></span>

<span data-ttu-id="db048-201">قم بالبناء أعلى بيانات العملاء التي تم إثرائها.</span><span class="sxs-lookup"><span data-stu-id="db048-201">Build on top of your enriched customer data.</span></span> <span data-ttu-id="db048-202">أنشئ [الشرائح](segments.md)، و[المقاييس](measures.md)، وقم كذلك [بتصدير البيانات](export-destinations.md) لتقديم تجارب مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="db048-202">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
