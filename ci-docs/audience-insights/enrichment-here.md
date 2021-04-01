---
title: إثراء البيانات بواسطة خدمات إثراء البيانات من طرف ثالث HERE Technologies
description: معلومات عامة حول خدمات إثراء البيانات من طرف ثالث HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597725"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="c17fe-103">إثراء ملفات تعريف العملاء بواسطة HERE Technologies (معاينة)</span><span class="sxs-lookup"><span data-stu-id="c17fe-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="c17fe-104">إن HERE Technologies عبارة عن شركة ذات منصة للبيانات المكانية توفر بيانات وخدمات تركّز على الموقع.</span><span class="sxs-lookup"><span data-stu-id="c17fe-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="c17fe-105">باستخدام خدمات إثراء البيانات في HERE Technologies، يمكنك تكوين فهم أكثر دفة لموقع العملاء مع تسوية العناوين واستخراج خط الطول وخط العرض والمزيد.</span><span class="sxs-lookup"><span data-stu-id="c17fe-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c17fe-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="c17fe-106">Prerequisites</span></span>

<span data-ttu-id="c17fe-107">لتكوين عمليات إثراء HERE Technologies، يجب استيفاء المتطلبات الأساسية التالية:</span><span class="sxs-lookup"><span data-stu-id="c17fe-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c17fe-108">لديك اشتراك نشط في HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c17fe-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="c17fe-109">للحصول على اشتراك، يمكنك [التسجيل هنا](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) أو [الاتصال بشركة HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) مباشرةً.</span><span class="sxs-lookup"><span data-stu-id="c17fe-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="c17fe-110">اعرف المزيد حول إثراء الموقع من HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c17fe-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="c17fe-111">لديك مفتاح API لـ HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c17fe-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="c17fe-112">لديك أذونات [المسؤول](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="c17fe-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="c17fe-113">التكوين</span><span class="sxs-lookup"><span data-stu-id="c17fe-113">Configuration</span></span>

1. <span data-ttu-id="c17fe-114">انتقل إلى **بيانات** > **إثراء**.</span><span class="sxs-lookup"><span data-stu-id="c17fe-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="c17fe-115">حدد **إثراء بياناتي** على الإطار المتجانب HERE Technologies‬.</span><span class="sxs-lookup"><span data-stu-id="c17fe-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c17fe-116">![الإطار المتجانب HERE Technologies](media/HERE-tile.png "الإطار المتجانب HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="c17fe-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="c17fe-117">أدخل **مفتاح HERE Technologies API** نشطًا.</span><span class="sxs-lookup"><span data-stu-id="c17fe-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="c17fe-118">راجع وقدم موافقتك على **خصوصية البيانات والتوافق‬** من خلال تحديد خانة الاختيار **أوافق**.</span><span class="sxs-lookup"><span data-stu-id="c17fe-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="c17fe-119">أكد الإدخالين عن طريق تحديد **اتصال بـ HERE**.</span><span class="sxs-lookup"><span data-stu-id="c17fe-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="c17fe-120">حدد **إضافة بيانات** واختر **مجموعة بيانات العميل** التي ترغب في إثرائها بواسطة بيانات الموقع من HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c17fe-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="c17fe-121">يمكنك تحديد كيان **العميل** لإثراء جميع ملفات تعريف العملاء أو تحديد كيان شريحة لإثراء فقط ملفات تعريف العملاء الموجودة في تلك الشريحة.</span><span class="sxs-lookup"><span data-stu-id="c17fe-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="لقطة شاشة عند اختيار مجموعة بيانات العميل.":::

1. <span data-ttu-id="c17fe-123">اختر إذا كنت تريد تعيين الحقول إلى العنوان الرئيسي و/أو الثانوي.</span><span class="sxs-lookup"><span data-stu-id="c17fe-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="c17fe-124">يمكنك تحديد تعيين الحقول للعنوانين (على سبيل المثال، عنوان المنزل وعنوان العمل) واعمل على إثراء ملفات التعريف للعنوانين على حدة.</span><span class="sxs-lookup"><span data-stu-id="c17fe-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="c17fe-125">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="c17fe-125">Select **Next**.</span></span>

1. <span data-ttu-id="c17fe-126">حدد الحقول التي سيتم استخدامها من ملفات التعريف الموحدة للبحث عن بيانات الموقع المطابقة من تقنيات HERE</span><span class="sxs-lookup"><span data-stu-id="c17fe-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="c17fe-127">يجب تعبئة الحقلين **الشارع 1** و **الرمز البريدي** للعنوان الرئيسي و/أو الثانوي المحدد.‬</span><span class="sxs-lookup"><span data-stu-id="c17fe-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="c17fe-128">للحصول على دقة مطابقة أعلى، يمكن إضافة المزيد من الحقول.</span><span class="sxs-lookup"><span data-stu-id="c17fe-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c17fe-129">![صفحة تكوين إثراء HERE Technologies](media/enrichment-HERE-configuration.png "صفحة تكوين إثراء HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="c17fe-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="c17fe-130">حدد **تطبيق** لإكمال تعيين الحقول.</span><span class="sxs-lookup"><span data-stu-id="c17fe-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="c17fe-131">نتائج الإثراء</span><span class="sxs-lookup"><span data-stu-id="c17fe-131">Enrichment results</span></span>

<span data-ttu-id="c17fe-132">لبدء عملية الإثراء، حدد **تشغيل** من شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="c17fe-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="c17fe-133">يمكنك أيضًا السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من [التحديث المجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c17fe-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c17fe-134">سيعتمد وقت المعالجة على حجم بيانات العملاء وأوقات استجابة API من HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c17fe-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="c17fe-135">بعد اكتمال عملية الإثراء، يمكنك مراجعة بيانات ملفات تعريف العملاء التي تم إثراؤها حديثًا ضمن **عمليات الإثراء الخاصة بي**.</span><span class="sxs-lookup"><span data-stu-id="c17fe-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="c17fe-136">بالإضافة إلى ذلك ، ستجد وقت التحديث الأخير وعدد ملفات التعريف التي تم إثراؤها.</span><span class="sxs-lookup"><span data-stu-id="c17fe-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c17fe-137">يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.</span><span class="sxs-lookup"><span data-stu-id="c17fe-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c17fe-138">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="c17fe-138">Next steps</span></span>

<span data-ttu-id="c17fe-139">قم بالبناء أعلى بيانات العملاء التي تم إثرائها.</span><span class="sxs-lookup"><span data-stu-id="c17fe-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c17fe-140">أنشئ [الشرائح](segments.md)، و[المقاييس](measures.md)، وقم كذلك [بتصدير البيانات](export-destinations.md) لتقديم تجارب مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="c17fe-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c17fe-141">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="c17fe-141">Data privacy and compliance</span></span>

<span data-ttu-id="c17fe-142">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى HERE Technologies، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="c17fe-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c17fe-143">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام HERE Technologies بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="c17fe-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c17fe-144">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c17fe-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c17fe-145">بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="c17fe-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]