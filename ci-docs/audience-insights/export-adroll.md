---
title: تصدير بيانات Customer Insights إلى AdRoll
description: اعرف كيفية تكوين الاتصال بـ AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697058"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="51c62-103">موصل AdRoll (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="51c62-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="51c62-104">يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة إلى AdRoll واستخدامها في الإعلانات.</span><span class="sxs-lookup"><span data-stu-id="51c62-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="51c62-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="51c62-105">Prerequisites</span></span>

-   <span data-ttu-id="51c62-106">لديك [حساب AdRoll](https://www.adroll.com/) وبيانات اعتماد مسؤول مطابقة.</span><span class="sxs-lookup"><span data-stu-id="51c62-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="51c62-107">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="51c62-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="51c62-108">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="51c62-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="51c62-109">الاتصال بـ AdRoll</span><span class="sxs-lookup"><span data-stu-id="51c62-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="51c62-110">انتقل إلى **المسؤول** > **وجهات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="51c62-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="51c62-111">أسفل **AdRoll**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="51c62-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="51c62-112">في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.</span><span class="sxs-lookup"><span data-stu-id="51c62-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="جزء التكوين لاتصال AdRoll.":::

1. <span data-ttu-id="51c62-114">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="51c62-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="51c62-115">حدد **اتصال** لتهيئة الاتصال بـ AdRoll.</span><span class="sxs-lookup"><span data-stu-id="51c62-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="51c62-116">حدد **المصادقة مع AdRoll** وقدم بيانات اعتماد المسؤول لـ AdRoll.</span><span class="sxs-lookup"><span data-stu-id="51c62-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="51c62-117">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="51c62-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="51c62-118">أدخل **معرف معلن AdRoll** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="51c62-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="51c62-119">حدد **التالي** لتكوين التصدير.</span><span class="sxs-lookup"><span data-stu-id="51c62-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="51c62-120">تكوين الموصل</span><span class="sxs-lookup"><span data-stu-id="51c62-120">Configure the connector</span></span>

1. <span data-ttu-id="51c62-121">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="51c62-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="51c62-122">يلزم تصدير شرائح إلى AdRoll.</span><span class="sxs-lookup"><span data-stu-id="51c62-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="51c62-123">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="51c62-123">Select the segments you want to export.</span></span> <span data-ttu-id="51c62-124">حدد شريحة تتضمن 100 عضو على الأقل.</span><span class="sxs-lookup"><span data-stu-id="51c62-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="51c62-125">لا يمكنك تصدير شرائح أصغر.</span><span class="sxs-lookup"><span data-stu-id="51c62-125">You can't export smaller segments.</span></span> <span data-ttu-id="51c62-126">بالإضافة إلى ذلك، فإن الحد الأقصى لحجم شريحة ما لتصديرها هو ‎250'000 عضو لكل عملية تصدير.</span><span class="sxs-lookup"><span data-stu-id="51c62-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="51c62-127">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="51c62-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="51c62-128">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="51c62-128">Export the data</span></span>

<span data-ttu-id="51c62-129">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="51c62-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="51c62-130">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="51c62-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="51c62-131">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="51c62-131">Known limitations</span></span>

- <span data-ttu-id="51c62-132">يمكنك تصدير ما يصل إلى ‎250'000 ملف تعريف في كل عملية تصدير إلى AdRoll.</span><span class="sxs-lookup"><span data-stu-id="51c62-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="51c62-133">لا يمكنك تصدير شرائح ذات ملفات تعريف أقل من 100 إلى AdRoll.</span><span class="sxs-lookup"><span data-stu-id="51c62-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="51c62-134">يقتصر التصدير إلى AdRoll على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="51c62-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="51c62-135">قد يستغرق استكمال تصدير ‎250'000 ملف تعريف إلى AdRoll حتى 10 دقائق.</span><span class="sxs-lookup"><span data-stu-id="51c62-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="51c62-136">يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى AdRoll على العقد مع AdRoll، وهذا العدد مقيد بالعقد.</span><span class="sxs-lookup"><span data-stu-id="51c62-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="51c62-137">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="51c62-137">Data privacy and compliance</span></span>

<span data-ttu-id="51c62-138">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى AdRoll، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="51c62-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="51c62-139">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام AdRoll بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="51c62-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="51c62-140">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="51c62-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="51c62-141">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="51c62-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
