---
title: تصدير بيانات Customer Insights إلى RollWorks
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760458"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="df824-103">تصدير قوائم الشرائح إلى RollWorks (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="df824-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="df824-104">قم بتصدير شرائح ملفات تعريف العملاء الموحدة إلى RollWorks واستخدامها في الإعلانات.</span><span class="sxs-lookup"><span data-stu-id="df824-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="df824-105">المتطلبات الأساسية لاتصال</span><span class="sxs-lookup"><span data-stu-id="df824-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="df824-106">لديك [حساب RollWorks](https://www.rollworks.com/) وبيانات اعتماد المسؤول المقابلة.</span><span class="sxs-lookup"><span data-stu-id="df824-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="df824-107">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="df824-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="df824-108">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="df824-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="df824-109">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="df824-109">Known limitations</span></span>

- <span data-ttu-id="df824-110">يمكنك تصدير حتى 250000 ملف تعريف لكل تصدير إلى RollWorks.</span><span class="sxs-lookup"><span data-stu-id="df824-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="df824-111">لا يمكنك تصدير الشرائح التي يقل عدد ملفات تعريفها عن 100 ملف تعريف إلى RollWorks.</span><span class="sxs-lookup"><span data-stu-id="df824-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="df824-112">يقتصر التصدير إلى RollWorks على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="df824-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="df824-113">يمكن أن يستغرق تصدير ما يصل إلى 250 ألف ملف تعريف إلى RollWorks ما يصل إلى 10 دقائق حتى يكتمل.</span><span class="sxs-lookup"><span data-stu-id="df824-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="df824-114">عدد الملفات الشخصية التي يمكنك تصديرها إلى RollWorks يعتمد ويقتصر على عقدك مع RollWorks.</span><span class="sxs-lookup"><span data-stu-id="df824-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="df824-115">إعداد الاتصال بـ RollWorks</span><span class="sxs-lookup"><span data-stu-id="df824-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="df824-116">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="df824-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="df824-117">حدد **إضافة اتصال** واختر **RollWorks** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="df824-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="df824-118">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="df824-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="df824-119">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="df824-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="df824-120">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="df824-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="df824-121">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="df824-121">Choose who can use this connection.</span></span> <span data-ttu-id="df824-122">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="df824-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="df824-123">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="df824-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="df824-124">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="df824-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="df824-125">حدد **الاتصال** لبدء الاتصال بـ RollWorks.</span><span class="sxs-lookup"><span data-stu-id="df824-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="df824-126">حدد **المصادقة مع RollWorks** ووفر بيانات اعتماد المسؤول الخاصة بك لـ RollWorks.</span><span class="sxs-lookup"><span data-stu-id="df824-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="df824-127">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="df824-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="df824-128">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="df824-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="df824-129">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="df824-129">Configure an export</span></span>

<span data-ttu-id="df824-130">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="df824-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="df824-131">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="df824-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="df824-132">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="df824-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="df824-133">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="df824-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="df824-134">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم RollWorks.</span><span class="sxs-lookup"><span data-stu-id="df824-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="df824-135">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="df824-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="df824-136">أدخل **معرف معلن RollWorks** [RollWorks للإعلان](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="df824-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="df824-137">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="df824-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="df824-138">يلزم تصدير شرائح إلى RollWorks.</span><span class="sxs-lookup"><span data-stu-id="df824-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="df824-139">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="df824-139">Select the segments you want to export.</span></span> <span data-ttu-id="df824-140">حدد شريحة تتضمن 100 عضو على الأقل.</span><span class="sxs-lookup"><span data-stu-id="df824-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="df824-141">لا يمكنك تصدير شرائح أصغر.</span><span class="sxs-lookup"><span data-stu-id="df824-141">You can't export smaller segments.</span></span> <span data-ttu-id="df824-142">بالإضافة إلى ذلك، فإن الحد الأقصى لحجم شريحة ما لتصديرها هو ‎250'000 عضو لكل عملية تصدير.</span><span class="sxs-lookup"><span data-stu-id="df824-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="df824-143">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="df824-143">Select **Save**.</span></span>

<span data-ttu-id="df824-144">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="df824-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="df824-145">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="df824-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="df824-146">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="df824-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="df824-147">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="df824-147">Data privacy and compliance</span></span>

<span data-ttu-id="df824-148">عند تمكين Dynamics 365 Customer Insights لنقل البيانات إلى RollWorks، فأنت تسمح بنقل البيانات خارج حدود الامتثال لـ Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="df824-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="df824-149">ستقوم Microsoft بنقل هذه البيانات بموجب الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان ووفاء RollWorks بأي خصوصية أو التزامات أمنية قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="df824-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="df824-150">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="df824-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="df824-151">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="df824-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
