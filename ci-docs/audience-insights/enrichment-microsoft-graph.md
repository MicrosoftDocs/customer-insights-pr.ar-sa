---
title: إثراء ملفات تعريف العملاء بواسطة Microsoft Graph
description: استخدم بيانات مملوكة من Microsoft Graph لإثراء بيانات العملاء باستخدام العلامة التجارية وصلات الاهتمامات.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: aa46dac4f9c0d27881371877b14a92a6725710da
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596437"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="b12c2-103">إثراء ملفات تعريف العملاء بالعلامات التجارية وصلات الاهتمامات (معاينة)</span><span class="sxs-lookup"><span data-stu-id="b12c2-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="b12c2-104">استخدم بيانات مملوكة من Microsoft Graph لإثراء بيانات العملاء باستخدام العلامة التجارية وصلات الاهتمامات.</span><span class="sxs-lookup"><span data-stu-id="b12c2-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="b12c2-105">يتم تحديد أوجه التشابه هذه استنادًا إلى بيانات من أشخاص لديهم نفس التركيبة السكانية لعملائك.</span><span class="sxs-lookup"><span data-stu-id="b12c2-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="b12c2-106">تساعدك هذه المعلومات على فهم عملائك وتقسيمهم بشكل أفضل بناءً على انتماءاتهم بعلامات تجارية ومصالح محددة.</span><span class="sxs-lookup"><span data-stu-id="b12c2-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="b12c2-107">في رؤى الجمهور، انتقل إلى **البيانات** > **إثراء** من أجل [تكوين الإثراءات وعرضها](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="b12c2-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="b12c2-108">لتكوين إثراء لصلات العلامات التجارية، انتقل إلى علامة التبويب **اكتشاف** وحدد **إثراء بياناتي** في تجانب **العلامات التجارية**.</span><span class="sxs-lookup"><span data-stu-id="b12c2-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="b12c2-109">لتكوين أثراء لصلات الاهتمامات، انتقل إلى علامة التبويب **اكتشاف** وحدد **إثراء بياناتي** في تجانب **الاهتمامات**.</span><span class="sxs-lookup"><span data-stu-id="b12c2-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b12c2-110">![تجانبات العلامات التجارية والاهتمامات](media/BrandsInterest-tile-Hub.png "تجانبات العلامات التجارية والاهتمامات")</span><span class="sxs-lookup"><span data-stu-id="b12c2-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="b12c2-111">حول Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="b12c2-111">About Microsoft Graph</span></span>

<span data-ttu-id="b12c2-112">نحن نستخدم بيانات البحث عبر الإنترنت من Microsoft Graph للعثور علي صلات العلامات التجارية والاهتمامات عبر الشرائح السكانية المتعددة (محددة حسب العمر أو الجنس أو الموقع).</span><span class="sxs-lookup"><span data-stu-id="b12c2-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="b12c2-113">يحدد حجم البحث عبر الإنترنت الخاص بإحدي العلامات التجارية أو الاهتمام مدى العلاقة بين المقطع السكانية للصلة مقارنة بالمقاطع الأخرى وعلاقتها بتلك العلامة التجارية أو الاهتمام.</span><span class="sxs-lookup"><span data-stu-id="b12c2-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="b12c2-114">[اعرف المزيد حول Microsoft Graph](/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="b12c2-114">[Learn more about Microsoft Graph](/graph/overview).</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="b12c2-115">مستوى التقارب ودرجة التقارب</span><span class="sxs-lookup"><span data-stu-id="b12c2-115">Affinity level and score</span></span>

<span data-ttu-id="b12c2-116">في كل ملف تعريف عملاء تم إثراؤه، نقدم قيمتين مرتبطتين - مستوى التقارب ودرجة التقارب.</span><span class="sxs-lookup"><span data-stu-id="b12c2-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="b12c2-117">تساعدك هذه القيم في تحديد مدى قوة التقارب بالنسبة للشريحة السكانية في ملف التعريف، بالنسبة لعلامة تجارية أو اهتمام، مقارنة بالشرائح السكانية الأخرى.</span><span class="sxs-lookup"><span data-stu-id="b12c2-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="b12c2-118">يتكوّن *مستوى التقارب* من أربعة مستويات، ويتم حساب *درجة التقارب* على مقياس من 100 نقطة يتم تعيينه إلى مستويات التقارب.</span><span class="sxs-lookup"><span data-stu-id="b12c2-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="b12c2-119">مستوى التقارب</span><span class="sxs-lookup"><span data-stu-id="b12c2-119">Affinity level</span></span> |<span data-ttu-id="b12c2-120">درجة التقارب</span><span class="sxs-lookup"><span data-stu-id="b12c2-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="b12c2-121">مرتفع جدًا</span><span class="sxs-lookup"><span data-stu-id="b12c2-121">Very high</span></span>     | <span data-ttu-id="b12c2-122">85-100</span><span class="sxs-lookup"><span data-stu-id="b12c2-122">85-100</span></span>       |
|<span data-ttu-id="b12c2-123">عالي</span><span class="sxs-lookup"><span data-stu-id="b12c2-123">High</span></span>     | <span data-ttu-id="b12c2-124">70-84</span><span class="sxs-lookup"><span data-stu-id="b12c2-124">70-84</span></span>        |
|<span data-ttu-id="b12c2-125">متوسط </span><span class="sxs-lookup"><span data-stu-id="b12c2-125">Medium</span></span>     | <span data-ttu-id="b12c2-126">35-69</span><span class="sxs-lookup"><span data-stu-id="b12c2-126">35-69</span></span>        |
|<span data-ttu-id="b12c2-127">منخفض</span><span class="sxs-lookup"><span data-stu-id="b12c2-127">Low</span></span>     | <span data-ttu-id="b12c2-128">1-34</span><span class="sxs-lookup"><span data-stu-id="b12c2-128">1-34</span></span>        |

<span data-ttu-id="b12c2-129">بالاستناد إلى مستوى النقاوة الذي ترغب فيه لقياس التقارب، يمكنك استخدام مستوى التقارب أو درجة التقارب.</span><span class="sxs-lookup"><span data-stu-id="b12c2-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="b12c2-130">تمنحك درجة التقارب القدرة على التحكم بشكل أدق.</span><span class="sxs-lookup"><span data-stu-id="b12c2-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="b12c2-131">البلدان/المناطق المدعومة</span><span class="sxs-lookup"><span data-stu-id="b12c2-131">Supported countries/regions</span></span>

<span data-ttu-id="b12c2-132">ندعم حاليًا خيارات البلدان/المناطق التالية: أستراليا أو كندا (الإنجليزية) أو فرنسا أو ألمانيا أو المملكة المتحدة أو الولايات المتحدة (الإنجليزية).</span><span class="sxs-lookup"><span data-stu-id="b12c2-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="b12c2-133">ولتحديد بلد، افتح **إثراء العلامات التجارية** أو **إثراء الاهتمام** وحدد **تغيير** بجوار **البلد/المنطقة**.</span><span class="sxs-lookup"><span data-stu-id="b12c2-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="b12c2-134">في جزء **إعدادات البلد/المنطقة**، اختر خيارًا وحدد **تطبيق**.</span><span class="sxs-lookup"><span data-stu-id="b12c2-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="b12c2-135">العواقب المتعلقة بتحديد البلد</span><span class="sxs-lookup"><span data-stu-id="b12c2-135">Implications related to country selection</span></span>

- <span data-ttu-id="b12c2-136">عند [اختيار علاماتك التجارية الخاصة](#define-your-brands-or-interests)، يوفر النظام اقتراحات بالاستناد إلى البلد أو المنطقة المحددة.</span><span class="sxs-lookup"><span data-stu-id="b12c2-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="b12c2-137">عند [اختيار مجال ما](#define-your-brands-or-interests)، ستحصل على العلامات التجارية أو الاهتمامات الأكثر صلة بالاستناد إلى البلد أو المنطقة المحددة.‬</span><span class="sxs-lookup"><span data-stu-id="b12c2-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="b12c2-138">عند [إثراء ملفات التعريف](#refresh-enrichment)، سنقوم بإثراء جميع ملفات تعريف العملاء التي نحصل منها على بيانات للعلامات التجارية والاهتمامات المحددة.</span><span class="sxs-lookup"><span data-stu-id="b12c2-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="b12c2-139">بما في ذلك ملفات التعريف غير الموجودة في البلد أو المنطقة المحددة.</span><span class="sxs-lookup"><span data-stu-id="b12c2-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="b12c2-140">على سبيل المثال، عند تحديد ألمانيا، سيتم إثراء ملفات التعريف الموجودة في الولايات المتحدة في حالة توفر بيانات Microsoft Graph للعلامات التجارية المحددة والاهتمامات الموجودة في الولايات المتحدة.</span><span class="sxs-lookup"><span data-stu-id="b12c2-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="b12c2-141">تكوين الإثراء</span><span class="sxs-lookup"><span data-stu-id="b12c2-141">Configure Enrichment</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="b12c2-142">تحديد العلامات التجارية أو الاهتمامات</span><span class="sxs-lookup"><span data-stu-id="b12c2-142">Define your brands or interests</span></span>

<span data-ttu-id="b12c2-143">حدد واحدًا من الخيارات التالية:</span><span class="sxs-lookup"><span data-stu-id="b12c2-143">Select one of the following options:</span></span>

- <span data-ttu-id="b12c2-144">**الصناعة**: يحدد النظام أفضل العلامات التجارية أو الاهتمامات المتعلقة بمجالك ويقوم بإثراء بيانات العميل بها.</span><span class="sxs-lookup"><span data-stu-id="b12c2-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="b12c2-145">**اختيار ما يخصك**: حدد ما يصل إلى خمسة عناصر من قائمة العلامات التجارية أو الاهتمامات الأكثر صله بالمؤسسة.</span><span class="sxs-lookup"><span data-stu-id="b12c2-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="b12c2-146">لإضافة علامة تجارية أو ذات أهمية، قم بإدخالها في منطقة الإدخال للحصول على اقتراحات استنادًا إلى المصطلحات المطابقة.</span><span class="sxs-lookup"><span data-stu-id="b12c2-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="b12c2-147">إذا لم تقم بسرد العلامات التجارية أو الاهتمامات التي تبحث عنها، قم بإرسال ملاحظاتك باستخدام الارتباط **اقتراح**.</span><span class="sxs-lookup"><span data-stu-id="b12c2-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="b12c2-148">مراجعة تفضيلات الإثراء</span><span class="sxs-lookup"><span data-stu-id="b12c2-148">Review enrichment preferences</span></span>

<span data-ttu-id="b12c2-149">راجع تفضيلات الإثراء الافتراضية وحدّثها حسب الحاجة.</span><span class="sxs-lookup"><span data-stu-id="b12c2-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="لقطة شاشة لنافذة تفضيلات الإثراء.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="b12c2-151">تحديد كيان لإثرائه</span><span class="sxs-lookup"><span data-stu-id="b12c2-151">Select entity to enrich</span></span>

<span data-ttu-id="b12c2-152">حدد **الكيان الذي تم إثراؤه‬** واختر مجموعة البيانات التي ترغب في إثرائها من خلال بيانات الشركة من Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="b12c2-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft Graph.</span></span> <span data-ttu-id="b12c2-153">يمكنك تحديد كيان العميل لإثراء جميع ملفات تعريف العملاء أو تحديد كيان شريحة لإثراء فقط ملفات تعريف العملاء الموجودة في تلك الشريحة.</span><span class="sxs-lookup"><span data-stu-id="b12c2-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="b12c2-154">تعيين الحقول الخاصة بك</span><span class="sxs-lookup"><span data-stu-id="b12c2-154">Map your fields</span></span>

<span data-ttu-id="b12c2-155">يمكنك تعيين حقول من كيان العميل الموحد لتحديد الشريحة السكانية التي ترغب في أن يستخدمها النظام لإثراء بيانات العميل.</span><span class="sxs-lookup"><span data-stu-id="b12c2-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="b12c2-156">ويمكنك تعيين البلد/المنطقة وسمات تاريخ الميلاد أو الجنس على الأقل.</span><span class="sxs-lookup"><span data-stu-id="b12c2-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="b12c2-157">بالإضافة إلى ذلك، يجب تعيين رمز مدينة (ولاية/إقليم) أو رمز بريدي واحد على الأقل.</span><span class="sxs-lookup"><span data-stu-id="b12c2-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="b12c2-158">حدد **تحرير** لتحديد تعيين الحقول وقم بتحديد **تطبيق** عند الانتهاء.</span><span class="sxs-lookup"><span data-stu-id="b12c2-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="b12c2-159">حدد **حفظ** لإكمال تعيين الحقل.</span><span class="sxs-lookup"><span data-stu-id="b12c2-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="b12c2-160">تحظى التنسيقات والقيم التالية بالدعم، والقيم ليست حساسة لحالة الأحرف:</span><span class="sxs-lookup"><span data-stu-id="b12c2-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="b12c2-161">**تاريخ الميلاد**: يستحسن تحويل تاريخ الميلاد إلى نوع التاريخ والوقت خلال ‏‫استيعاب البيانات‬.</span><span class="sxs-lookup"><span data-stu-id="b12c2-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="b12c2-162">ويمكن بدلاً من ذلك أن يكون سلسلة في [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) بالتنسيق "س س س-ش ش-ي ي أو "yyyy-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="b12c2-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="b12c2-163">**النوع**: ذكر، أنثى، غير معروف</span><span class="sxs-lookup"><span data-stu-id="b12c2-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="b12c2-164">**الرمز البريدي**: رمز بريدي مكون من خمسة أرقام للولايات المتحدة، والرمز البريدي القياسي في أي مكان آخر</span><span class="sxs-lookup"><span data-stu-id="b12c2-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="b12c2-165">**المدينة**: اسم المدينة باللغة الإنجليزية</span><span class="sxs-lookup"><span data-stu-id="b12c2-165">**City**: City name in English</span></span>
- <span data-ttu-id="b12c2-166">**الولاية/المقاطعة**: اختصار من حرفين للولايات المتحدة وكندا.</span><span class="sxs-lookup"><span data-stu-id="b12c2-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="b12c2-167">اختصار من حرفين أو ثلاثة لأستراليا.</span><span class="sxs-lookup"><span data-stu-id="b12c2-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="b12c2-168">لا ينطبق هذا على فرنسا أو ألمانيا أو المملكة المتحدة.</span><span class="sxs-lookup"><span data-stu-id="b12c2-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="b12c2-169">**الدولة/المنطقة**:</span><span class="sxs-lookup"><span data-stu-id="b12c2-169">**Country/Region**:</span></span>

  - <span data-ttu-id="b12c2-170">الولايات المتحدة: الولايات المتحدة الأمريكية، USA، US، أمريكا</span><span class="sxs-lookup"><span data-stu-id="b12c2-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="b12c2-171">CA: كندا، CA</span><span class="sxs-lookup"><span data-stu-id="b12c2-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="b12c2-172">GB: المملكة المتحدة، UK، بريطانيا العظمى، GB، المملكة المتحدة لبريطانيا العظمى وأيرلندا الشمالية، المملكة المتحدة لبريطانيا العظمى</span><span class="sxs-lookup"><span data-stu-id="b12c2-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="b12c2-173">AU: أستراليا، AU، كومنولث أستراليا</span><span class="sxs-lookup"><span data-stu-id="b12c2-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="b12c2-174">FR: فرنسا، FR، الجمهورية الفرنسية</span><span class="sxs-lookup"><span data-stu-id="b12c2-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="b12c2-175">DE: ألمانيا، DE، جمهورية ألمانيا الاتحادية، جمهورية ألمانيا</span><span class="sxs-lookup"><span data-stu-id="b12c2-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="b12c2-176">تحديث عملية الإثراء</span><span class="sxs-lookup"><span data-stu-id="b12c2-176">Refresh enrichment</span></span>

<span data-ttu-id="b12c2-177">قم بتشغيل الإثراء بعد تكوين العلامات التجارية والاهتمامات وتعيين الحقول للمخططات السكانية.</span><span class="sxs-lookup"><span data-stu-id="b12c2-177">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="b12c2-178">لبدء العملية، حدد **تشغيل** في صفحة تكوين العلامة التجارية أو الاهتمام.</span><span class="sxs-lookup"><span data-stu-id="b12c2-178">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="b12c2-179">بالإضافة إلى ذلك، يمكنك السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من التحديث المجدول.</span><span class="sxs-lookup"><span data-stu-id="b12c2-179">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="b12c2-180">ووفقًا لحجم بيانات العملاء، قد يستغرق الأمر عدة ثوان لإكمال تشغيل الإثراء.</span><span class="sxs-lookup"><span data-stu-id="b12c2-180">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="b12c2-181">هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات.</span><span class="sxs-lookup"><span data-stu-id="b12c2-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="b12c2-182">بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="b12c2-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="b12c2-183">يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها.</span><span class="sxs-lookup"><span data-stu-id="b12c2-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="b12c2-184">بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.</span><span class="sxs-lookup"><span data-stu-id="b12c2-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="b12c2-185">نتائج الإثراء</span><span class="sxs-lookup"><span data-stu-id="b12c2-185">Enrichment results</span></span>

<span data-ttu-id="b12c2-186">بعد تشغيل عملية الإثراء، انتقل إلى **عمليات الإثراء الخاصة بي** لمراجعة إجمالي عدد العملاء الذين تم إثرائهم وتصنيف العلامات التجارية أو الاهتمامات في ملفات تعريف العملاء الذين تم إثرائهم.</span><span class="sxs-lookup"><span data-stu-id="b12c2-186">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="معاينه النتائج بعد تشغيل عمليه الإثراء":::

<span data-ttu-id="b12c2-188">راجع البيانات التي تم إثرائها من خلال تحديد **عرض البيانات التي تم إثراؤها‬** في المخطط.</span><span class="sxs-lookup"><span data-stu-id="b12c2-188">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="b12c2-189">تنتقل بيانات العلامات التجارية التي تم إثرائها إلى الكيان **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="b12c2-189">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="b12c2-190">بيانات الاهتمامات في الكيان **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="b12c2-190">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="b12c2-191">كما ستجد هذه الكيانات المدرجة في مجموعه **الإثراء**  في **البيانات** > **الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="b12c2-191">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="b12c2-192">راجع بيانات الإثراء على بطاقة العملاء</span><span class="sxs-lookup"><span data-stu-id="b12c2-192">See enrichment data on the customer card</span></span>

<span data-ttu-id="b12c2-193">كما يمكن عرض أوجه تشابه العلامات التجارية والاهتمامات في بطاقات العملاء الفردية.</span><span class="sxs-lookup"><span data-stu-id="b12c2-193">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="b12c2-194">انتقل إلى **العملاء** وحدد ملف التعريف الخاص بالعميل.</span><span class="sxs-lookup"><span data-stu-id="b12c2-194">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="b12c2-195">وفي بطاقة العملاء، ستجد مخططات لكل من العلامات التجارية أو الاهتمام التي لها صلة بالأشخاص في ملف التعريف السكاني لهذا العميل.</span><span class="sxs-lookup"><span data-stu-id="b12c2-195">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="بطاقة العملاء مع البيانات التي تم إثراؤها":::

## <a name="next-steps"></a><span data-ttu-id="b12c2-197">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="b12c2-197">Next steps</span></span>

<span data-ttu-id="b12c2-198">قم بالبناء أعلى بيانات العملاء التي تم إثرائها.</span><span class="sxs-lookup"><span data-stu-id="b12c2-198">Build on top of your enriched customer data.</span></span> <span data-ttu-id="b12c2-199">أنشئ [الشرائح](segments.md)، و[المقاييس](measures.md)، وقم كذلك [بتصدير البيانات](export-destinations.md) لتقديم تجارب مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="b12c2-199">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]