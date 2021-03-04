---
title: إثراء ملفات تعريف الشركات بواسطة خدمات إثراء البيانات من طرف ثالث Leadspace‬
description: معلومات عامة حول خدمات إثراء البيانات من طرف ثالث Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269406"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="72ca6-103">إثراء ملفات تعريف الشركات من خلال Leadspace (معاينة)</span><span class="sxs-lookup"><span data-stu-id="72ca6-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="72ca6-104">Leadspace هي شركة مختصة في علوم البيانات توفر نظامًا أساسيًا لبيانات العميل من عمل لعمل.</span><span class="sxs-lookup"><span data-stu-id="72ca6-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="72ca6-105">وهي تمكن العملاء من خلال ملفات تعريف العملاء الموحدة للشركات من إثراء بياناتهم.</span><span class="sxs-lookup"><span data-stu-id="72ca6-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="72ca6-106">يتضمن الإثراء سمات إضافية مثل حجم الشركة والموقع والصناعة والمزيد.</span><span class="sxs-lookup"><span data-stu-id="72ca6-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="72ca6-107">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="72ca6-107">Prerequisites</span></span>

<span data-ttu-id="72ca6-108">لتكوين Leadspace، يجب استيفاء المتطلبات الأساسية التالية:</span><span class="sxs-lookup"><span data-stu-id="72ca6-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="72ca6-109">لديك ترخيص Leadspace نشط و"المفتاح الدائم" (يشار اليه باسم **الرمز المميز لـ Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="72ca6-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="72ca6-110">تواصل مباشرةً مع [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) للحصول على تفاصيل حول منتجاتهم.</span><span class="sxs-lookup"><span data-stu-id="72ca6-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="72ca6-111">لديك أذونات [المسؤول](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="72ca6-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="72ca6-112">لديك [ملفات تعريف عملاء موحدة](customer-profiles.md) للشركات.</span><span class="sxs-lookup"><span data-stu-id="72ca6-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="72ca6-113">التكوين</span><span class="sxs-lookup"><span data-stu-id="72ca6-113">Configuration</span></span>

1. <span data-ttu-id="72ca6-114">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **الإثراء**.</span><span class="sxs-lookup"><span data-stu-id="72ca6-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="72ca6-115">حدد **إثراء بياناتي** على تجانب Leadspace.</span><span class="sxs-lookup"><span data-stu-id="72ca6-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="لقطة شاشة للإطار المتجانب Leadspace.":::

1. <span data-ttu-id="72ca6-117">حدد **الشروع في العمل**، ثم أدخل **الرمز المميز لـ Leadspace** (المفتاح الدائم).</span><span class="sxs-lookup"><span data-stu-id="72ca6-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="72ca6-118">راجع وقدم موافقتك على **خصوصية البيانات والتوافق‬** من خلال تحديد خانة الاختيار **أوافق**.</span><span class="sxs-lookup"><span data-stu-id="72ca6-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="72ca6-119">أكد الإدخالين عن طريق تحديد **اتصال بـ Leadspace‎**.</span><span class="sxs-lookup"><span data-stu-id="72ca6-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="72ca6-120">حدد **تعيين البيانات** واختر مجموعة بيانات العميل التي ترغب في إثرائها بواسطة بيانات الشركة من Leadspace.</span><span class="sxs-lookup"><span data-stu-id="72ca6-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="72ca6-121">يمكنك تحديد كيان *العميل* لإثراء جميع ملفات تعريف العملاء أو تحديد كيان شريحة لإثراء فقط ملفات تعريف العملاء الموجودة في تلك الشريحة.</span><span class="sxs-lookup"><span data-stu-id="72ca6-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="اختر بين ملف تعريف العميل وإثراء الشرائح.":::

1. <span data-ttu-id="72ca6-123">انقر فوق **التالي** وحدد الحقول من ملفات التعريف الموحدة التي سيتم استخدامها للبحث عن بيانات الشركة المطابقة من Leadspace.</span><span class="sxs-lookup"><span data-stu-id="72ca6-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="72ca6-124">الحقل **اسم الشركة** مطلوب.</span><span class="sxs-lookup"><span data-stu-id="72ca6-124">The **Name of company** field is required.</span></span> <span data-ttu-id="72ca6-125">للحصول على دقة مطابقه أعلى، يمكن إضافة الحقلين **موقع ويب للشركة** و **موقع الشركة**.</span><span class="sxs-lookup"><span data-stu-id="72ca6-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="جزء تعيين حقول Leadspace.":::
   
1. <span data-ttu-id="72ca6-127">حدد **تطبيق** لإكمال تعيين الحقول.</span><span class="sxs-lookup"><span data-stu-id="72ca6-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="72ca6-128">حدد **تشغيل** لإثراء ملفات تعريف الشركة.</span><span class="sxs-lookup"><span data-stu-id="72ca6-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="72ca6-129">تتوقف الفترة التي يستغرقها الإثراء على عدد ملفات تعريف العملاء الموحدة.</span><span class="sxs-lookup"><span data-stu-id="72ca6-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="72ca6-130">نتائج الإثراء</span><span class="sxs-lookup"><span data-stu-id="72ca6-130">Enrichment results</span></span>

<span data-ttu-id="72ca6-131">بعد تحديث الإثراء، يمكنك مراجعة بيانات الشركة التي تم إثراؤها حديثًا والموجودة ضمن [عمليات الإثراء الخاصة بي‬](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="72ca6-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="72ca6-132">يمكنك العثور على وقت آخر تحديث وعدد ملفات تعريف التي تم إثراؤها.</span><span class="sxs-lookup"><span data-stu-id="72ca6-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="72ca6-133">يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.</span><span class="sxs-lookup"><span data-stu-id="72ca6-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="72ca6-134">لمزيد من المعلومات، راجع [مؤشرات الأداء الأساسية API لـ Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="72ca6-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="72ca6-135">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="72ca6-135">Next steps</span></span>

<span data-ttu-id="72ca6-136">قم بالبناء أعلى بيانات العملاء التي تم إثرائها.</span><span class="sxs-lookup"><span data-stu-id="72ca6-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="72ca6-137">أنشئ [الشرائح](segments.md)، و[المقاييس](measures.md)، وقم كذلك [بتصدير البيانات](export-destinations.md) لتقديم تجارب مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="72ca6-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="72ca6-138">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="72ca6-138">Data privacy and compliance</span></span>

<span data-ttu-id="72ca6-139">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Leadspace، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="72ca6-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="72ca6-140">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Leadspace بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="72ca6-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="72ca6-141">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="72ca6-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="72ca6-142">بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="72ca6-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]