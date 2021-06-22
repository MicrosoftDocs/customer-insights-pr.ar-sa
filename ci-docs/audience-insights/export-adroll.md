---
title: تصدير بيانات Customer Insights إلى AdRoll
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dbebc3ee3978ca6ee9d1ad1c15c226479876709f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124349"
---
# <a name="export-segments-to-adroll-preview"></a><span data-ttu-id="1cdfb-103">تصدير الشرائح إلى AdRoll (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="1cdfb-103">Export segments to AdRoll (preview)</span></span>

<span data-ttu-id="1cdfb-104">يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة إلى AdRoll واستخدامها في الإعلانات.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="1cdfb-105">المتطلبات الأساسية لاتصال</span><span class="sxs-lookup"><span data-stu-id="1cdfb-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="1cdfb-106">لديك [حساب AdRoll](https://www.adroll.com/) وبيانات اعتماد مسؤول مطابقة.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1cdfb-107">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1cdfb-108">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1cdfb-109">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="1cdfb-109">Known limitations</span></span>

- <span data-ttu-id="1cdfb-110">يمكنك تصدير ما يصل إلى ‎250'000 ملف تعريف في كل عملية تصدير إلى AdRoll.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="1cdfb-111">لا يمكنك تصدير شرائح ذات ملفات تعريف أقل من 100 إلى AdRoll.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="1cdfb-112">يقتصر التصدير إلى AdRoll على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="1cdfb-113">قد يستغرق استكمال تصدير ‎250'000 ملف تعريف إلى AdRoll حتى 10 دقائق.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="1cdfb-114">يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى AdRoll على العقد مع AdRoll، وهذا العدد مقيد بالعقد.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="1cdfb-115">إعداد الاتصال بـ AdRoll</span><span class="sxs-lookup"><span data-stu-id="1cdfb-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="1cdfb-116">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1cdfb-117">حدد **إضافة اتصال** واختر **AdRoll** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="1cdfb-118">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1cdfb-119">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1cdfb-120">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1cdfb-121">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-121">Choose who can use this connection.</span></span> <span data-ttu-id="1cdfb-122">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="1cdfb-123">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1cdfb-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1cdfb-124">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1cdfb-125">حدد **اتصال** لتهيئة الاتصال بـ AdRoll.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="1cdfb-126">حدد **المصادقة مع AdRoll** وقدم بيانات اعتماد المسؤول لـ AdRoll.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="1cdfb-127">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1cdfb-128">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1cdfb-129">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="1cdfb-129">Configure an export</span></span>

<span data-ttu-id="1cdfb-130">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1cdfb-131">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1cdfb-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1cdfb-132">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1cdfb-133">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1cdfb-134">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم AdRoll.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="1cdfb-135">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1cdfb-136">أدخل **معرف معلن AdRoll** لمزيد من المعلومات، راجع [ملفات تعريف معلنين AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="1cdfb-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="1cdfb-137">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="1cdfb-138">يلزم تصدير شرائح إلى AdRoll.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="1cdfb-139">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-139">Select the segments you want to export.</span></span> <span data-ttu-id="1cdfb-140">حدد شريحة تتضمن 100 عضو على الأقل.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="1cdfb-141">لا يمكنك تصدير شرائح أصغر.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-141">You can't export smaller segments.</span></span> <span data-ttu-id="1cdfb-142">بالإضافة إلى ذلك، فإن الحد الأقصى لحجم شريحة ما لتصديرها هو ‎250'000 عضو لكل عملية تصدير.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="1cdfb-143">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-143">Select **Save**.</span></span>

<span data-ttu-id="1cdfb-144">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1cdfb-145">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1cdfb-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1cdfb-146">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1cdfb-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1cdfb-147">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="1cdfb-147">Data privacy and compliance</span></span>

<span data-ttu-id="1cdfb-148">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى AdRoll، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1cdfb-149">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام AdRoll بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1cdfb-150">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1cdfb-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="1cdfb-151">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="1cdfb-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
