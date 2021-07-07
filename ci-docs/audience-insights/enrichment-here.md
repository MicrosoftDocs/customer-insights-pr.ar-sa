---
title: الإثراء باستخدام HERE Technologies لجهة خارجية
description: معلومات عامة حول خدمات إثراء البيانات من طرف ثالث HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305278"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="c7d33-103">إثراء ملفات تعريف العملاء بواسطة HERE Technologies (معاينة)</span><span class="sxs-lookup"><span data-stu-id="c7d33-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="c7d33-104">إن HERE Technologies عبارة عن شركة ذات منصة للبيانات المكانية توفر بيانات وخدمات تركّز على الموقع.</span><span class="sxs-lookup"><span data-stu-id="c7d33-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="c7d33-105">باستخدام خدمات إثراء البيانات في HERE Technologies، يمكنك تكوين فهم أكثر دفة لموقع العملاء مع تسوية العناوين واستخراج خط الطول وخط العرض والمزيد.</span><span class="sxs-lookup"><span data-stu-id="c7d33-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c7d33-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="c7d33-106">Prerequisites</span></span>

<span data-ttu-id="c7d33-107">لتكوين عمليات إثراء HERE Technologies، يجب استيفاء المتطلبات الأساسية التالية:</span><span class="sxs-lookup"><span data-stu-id="c7d33-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c7d33-108">لديك اشتراك نشط في HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c7d33-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="c7d33-109">للحصول على اشتراك، يمكنك [التسجيل هنا](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) أو [الاتصال بشركة HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) مباشرةً.</span><span class="sxs-lookup"><span data-stu-id="c7d33-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="c7d33-110">اعرف المزيد حول إثراء الموقع من HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c7d33-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="c7d33-111">يتوفر [اتصال](connections.md) HERE *أو* لديك أذونات [المسؤول](permissions.md#administrator) ومفتاح HERE Technologies API.</span><span class="sxs-lookup"><span data-stu-id="c7d33-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="c7d33-112">تكوين الإثراء</span><span class="sxs-lookup"><span data-stu-id="c7d33-112">Configure the enrichment</span></span>

1. <span data-ttu-id="c7d33-113">انتقل إلى **بيانات** > **إثراء**.</span><span class="sxs-lookup"><span data-stu-id="c7d33-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="c7d33-114">حدد **إثراء بياناتي** في الإطار المتجانب HERE Technologies وحدد **الشروع في العمل**.</span><span class="sxs-lookup"><span data-stu-id="c7d33-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7d33-115">![الإطار المتجانب HERE Technologies](media/HERE-tile.png "الإطار المتجانب HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="c7d33-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="c7d33-116">حدد [اتصالاً](connections.md) من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="c7d33-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="c7d33-117">اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.</span><span class="sxs-lookup"><span data-stu-id="c7d33-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="c7d33-118">إذا كنت أحد المسؤول، يمكنك إنشاء اتصال بتحديد **إضافة اتصال**.</span><span class="sxs-lookup"><span data-stu-id="c7d33-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="c7d33-119">اختر **HERE Technologies** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="c7d33-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="c7d33-120">حدد **الاتصال بـ HERE Technologies** لتأكيد التحديد.</span><span class="sxs-lookup"><span data-stu-id="c7d33-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="c7d33-121">حدد **التالي** واختر **مجموعة بيانات العميل** التي تريد إثراؤها باستخدام بيانات الموقع من HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c7d33-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="c7d33-122">يمكنك تحديد كيان **العميل** لإثراء جميع ملفات تعريف العملاء أو تحديد كيان شريحة لإثراء فقط ملفات تعريف العملاء الموجودة في تلك الشريحة.</span><span class="sxs-lookup"><span data-stu-id="c7d33-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="لقطة شاشة عند اختيار مجموعة بيانات العميل.":::

1. <span data-ttu-id="c7d33-124">اختر إذا كنت تريد تعيين الحقول إلى العنوان الرئيسي و/أو الثانوي.</span><span class="sxs-lookup"><span data-stu-id="c7d33-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="c7d33-125">يمكنك تحديد تعيين حقل لكل من العناوين وإثراء ملفات التعريف لكلا العناوين بشكل منفصل.</span><span class="sxs-lookup"><span data-stu-id="c7d33-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="c7d33-126">على سبيل المثال، إذا كان هناك المنزل وعنوان العمل.</span><span class="sxs-lookup"><span data-stu-id="c7d33-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="c7d33-127">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="c7d33-127">Select **Next**.</span></span>

1. <span data-ttu-id="c7d33-128">حدد الحقول التي سيتم استخدامها من ملفات التعريف الموحدة للبحث عن بيانات الموقع المطابقة من تقنيات HERE</span><span class="sxs-lookup"><span data-stu-id="c7d33-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="c7d33-129">يجب تعبئة الحقلين **الشارع 1** و **الرمز البريدي** للعنوان الرئيسي و/أو الثانوي المحدد.‬</span><span class="sxs-lookup"><span data-stu-id="c7d33-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="c7d33-130">للحصول على دقة مطابقة أعلى، يمكن إضافة المزيد من الحقول.</span><span class="sxs-lookup"><span data-stu-id="c7d33-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7d33-131">![صفحة تكوين إثراء HERE Technologies](media/enrichment-HERE-configuration.png "صفحة تكوين إثراء HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="c7d33-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="c7d33-132">حدد **التالي** لإكمال تعيين الحقل.</span><span class="sxs-lookup"><span data-stu-id="c7d33-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="c7d33-133">قدم اسمًا لعملية الإثراء.</span><span class="sxs-lookup"><span data-stu-id="c7d33-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="c7d33-134">حدد **حفظ الإثراء** بعد مراجعة اختياراتك.</span><span class="sxs-lookup"><span data-stu-id="c7d33-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="c7d33-135">تكوين الاتصال لـ HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="c7d33-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="c7d33-136">يلزم أن تكون المسؤول لتكوين الاتصالات.</span><span class="sxs-lookup"><span data-stu-id="c7d33-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="c7d33-137">حدد **إضافة اتصال** عند تكوين عملية إثراء *أو* انتقل إلى **المسؤول** > **الاتصالات** وحدد **إعداد** في تجانب HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c7d33-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="c7d33-138">أدخل اسما للاتصال في مربع **اسم العرض**.</span><span class="sxs-lookup"><span data-stu-id="c7d33-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="c7d33-139">قم بتوفير مفتاح واجهة برمجة تطبيقات صالح لـ HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c7d33-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="c7d33-140">راجع **خصوصية البيانات والامتثال** وقدم الموافقة عليها بتحديد **أوافق**.</span><span class="sxs-lookup"><span data-stu-id="c7d33-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="c7d33-141">حدد **التحقق** للتحقق من التكوين.</span><span class="sxs-lookup"><span data-stu-id="c7d33-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="c7d33-142">بعد إكمال التحقق، حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="c7d33-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7d33-143">![صفحة تكوين الاتصال بـ HERE technologies](media/enrichment-HERE-connection.png "صفحة تكوين الاتصال بـ HERE technologies")</span><span class="sxs-lookup"><span data-stu-id="c7d33-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="c7d33-144">نتائج الإثراء</span><span class="sxs-lookup"><span data-stu-id="c7d33-144">Enrichment results</span></span>

<span data-ttu-id="c7d33-145">لبدء عملية الإثراء، حدد **تشغيل** من شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="c7d33-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="c7d33-146">يمكنك أيضًا السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من [التحديث المجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c7d33-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c7d33-147">سيعتمد وقت المعالجة على حجم بيانات العملاء وأوقات استجابة API من HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="c7d33-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="c7d33-148">بعد اكتمال عملية الإثراء، يمكنك مراجعة بيانات ملفات تعريف العملاء التي تم إثراؤها حديثًا ضمن **عمليات الإثراء الخاصة بي**.</span><span class="sxs-lookup"><span data-stu-id="c7d33-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="c7d33-149">بالإضافة إلى ذلك ، ستجد وقت التحديث الأخير وعدد ملفات التعريف التي تم إثراؤها.</span><span class="sxs-lookup"><span data-stu-id="c7d33-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c7d33-150">يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.</span><span class="sxs-lookup"><span data-stu-id="c7d33-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c7d33-151">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="c7d33-151">Next steps</span></span>

<span data-ttu-id="c7d33-152">قم بالبناء أعلى بيانات العملاء التي تم إثرائها.</span><span class="sxs-lookup"><span data-stu-id="c7d33-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c7d33-153">أنشئ [الشرائح](segments.md) و[القياسات](measures.md) وحتى [تصدير البيانات](export-destinations.md) لتسليم تجارب مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="c7d33-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c7d33-154">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="c7d33-154">Data privacy and compliance</span></span>

<span data-ttu-id="c7d33-155">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى HERE Technologies، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="c7d33-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c7d33-156">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام HERE Technologies بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="c7d33-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c7d33-157">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c7d33-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c7d33-158">بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="c7d33-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
