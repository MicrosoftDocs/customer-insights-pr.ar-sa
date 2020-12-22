---
title: تصدير بيانات Customer Insights إلى Google Ads
description: اعرف كيفية تكوين الاتصال بـ Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568394"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="730c0-103">موصل Google Ads (معاينة)</span><span class="sxs-lookup"><span data-stu-id="730c0-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="730c0-104">يمكنك تصدير شرائح ملفات تعريف العملاء الموحدة إلى قوائم جمهور Google Ads واستخدامها للإعلان على Google Search وGmail وYouTubeوGoogle Display Network.</span><span class="sxs-lookup"><span data-stu-id="730c0-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="730c0-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="730c0-105">Prerequisites</span></span>

-   <span data-ttu-id="730c0-106">لديك [حساب Google Ads](https://ads.google.com/) وبيانات اعتماد مسؤول مطابقة.</span><span class="sxs-lookup"><span data-stu-id="730c0-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="730c0-107">هناك شرائح جمهور موجودة في Google Ads والمعرفات المناظرة.</span><span class="sxs-lookup"><span data-stu-id="730c0-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="730c0-108">لمزيد من المعلومات، راجع [شرائح جمهور Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="730c0-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="730c0-109">لقد قمت [بتكوين الشرائح](segments.md)</span><span class="sxs-lookup"><span data-stu-id="730c0-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="730c0-110">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقول تمثل عنوان البريد الإلكتروني والاسم الأول واسم العائلة.</span><span class="sxs-lookup"><span data-stu-id="730c0-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="730c0-111">الاتصال بـ Google Ads</span><span class="sxs-lookup"><span data-stu-id="730c0-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="730c0-112">انتقل إلى **المسؤول** > **وجهات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="730c0-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="730c0-113">ضمن **Google Ads**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="730c0-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="730c0-114">في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.</span><span class="sxs-lookup"><span data-stu-id="730c0-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="730c0-115">أدخل **[معرف عميل Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="730c0-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="730c0-116">أدخل **[الرمز المميز لمطور Google Ads الموافق عليه](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="730c0-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="730c0-117">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="730c0-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="730c0-118">أدخل **[معرف جمهور Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** وحدد **اتصال** لبدء الاتصال بـ Google Ads.</span><span class="sxs-lookup"><span data-stu-id="730c0-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="730c0-119">حدد **المصادقة مع Google Ads** وقد بيانات اعتماد Google Ads.</span><span class="sxs-lookup"><span data-stu-id="730c0-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="730c0-120">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="730c0-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="لقطة شاشة التصدير لاتصال Google Ads":::

1. <span data-ttu-id="730c0-122">حدد **التالي** لتكوين التصدير.</span><span class="sxs-lookup"><span data-stu-id="730c0-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="730c0-123">تكوين الموصل</span><span class="sxs-lookup"><span data-stu-id="730c0-123">Configure the connector</span></span>

1. <span data-ttu-id="730c0-124">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="730c0-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="730c0-125">كرر نفس الخطوات الخاصة للحقلين **الاسم الأول** و **اسم العائلة**.</span><span class="sxs-lookup"><span data-stu-id="730c0-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="730c0-126">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="730c0-126">Select the segments you want to export.</span></span> <span data-ttu-id="730c0-127">يمكنك تصدير ما يصل إلى مليون من ملفات تعريف العملاء إلى Google Ads.</span><span class="sxs-lookup"><span data-stu-id="730c0-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="730c0-128">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="730c0-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="730c0-129">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="730c0-129">Export the data</span></span>

<span data-ttu-id="730c0-130">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="730c0-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="730c0-131">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="730c0-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="730c0-132">في Google Ads، يمكنك الآن البحث عن الشرائح أسفل [شرائح جمهور Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="730c0-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="730c0-133">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="730c0-133">Known limitations</span></span>

- <span data-ttu-id="730c0-134">حتى مليون من ملفات التعريف لكل تصدير إلى Google Ads.</span><span class="sxs-lookup"><span data-stu-id="730c0-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="730c0-135">يقتصر التصدير إلى Google Ads على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="730c0-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="730c0-136">قد تستغرق عملية تصدير الشرائح التي تتضمن ما يصل إلى مليون ملف تعريف بشكل إجمالي 5 دقائق كحدٍ أقصى نتيجة للقيود من جانب الموفر.</span><span class="sxs-lookup"><span data-stu-id="730c0-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="730c0-137">قد يستغرق التطابق في Google Ads ما يصل إلى 48 ساعة.</span><span class="sxs-lookup"><span data-stu-id="730c0-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="730c0-138">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="730c0-138">Data privacy and compliance</span></span>

<span data-ttu-id="730c0-139">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Google Ads، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="730c0-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="730c0-140">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Google Ads بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="730c0-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="730c0-141">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="730c0-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="730c0-142">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="730c0-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
