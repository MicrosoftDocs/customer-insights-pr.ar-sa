---
title: تصدير بيانات Customer Insights إلى Campaign Monitor
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760457"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a><span data-ttu-id="4d738-103">تصدير قوائم الشرائح إلى Campaign Monitor (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="4d738-103">Export segment lists to Campaign Monitor (preview)</span></span>

<span data-ttu-id="4d738-104">قم بتصدير شرائح ملفات تعريف العملاء الموحدة إلى Campaign Monitor واستخدامها في أنشطة التسويق.</span><span class="sxs-lookup"><span data-stu-id="4d738-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4d738-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="4d738-105">Prerequisites</span></span>

-   <span data-ttu-id="4d738-106">لديك [حساب Campaign Monitor](https://www.campaignmonitor.com/) وبيانات اعتماد المسؤول المقابلة.</span><span class="sxs-lookup"><span data-stu-id="4d738-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4d738-107">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="4d738-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="4d738-108">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="4d738-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4d738-109">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="4d738-109">Known limitations</span></span>

- <span data-ttu-id="4d738-110">يمكنك تصدير حتى 1 مليوت ملف تعريف لكل تصدير إلى Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="4d738-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="4d738-111">يقتصر التصدير إلى Campaign Monitor على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="4d738-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="4d738-112">قد يستغرق تصدير ما يصل إلى مليون ملف تعريف إلى Campaign Monitor ما يصل إلى 20 دقيقة حتى الاكتمال.</span><span class="sxs-lookup"><span data-stu-id="4d738-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="4d738-113">عدد الملفات الشخصية التي يمكنك تصديرها إلى Campaign Monitor يعتمد ويقتصر على عقدك مع Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="4d738-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="4d738-114">إعداد الاتصال بـ Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="4d738-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="4d738-115">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="4d738-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4d738-116">حدد **إضافة اتصال** واختر **Campaign Monitor** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="4d738-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="4d738-117">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="4d738-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4d738-118">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="4d738-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4d738-119">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="4d738-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4d738-120">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="4d738-120">Choose who can use this connection.</span></span> <span data-ttu-id="4d738-121">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="4d738-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4d738-122">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4d738-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4d738-123">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="4d738-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4d738-124">حدد **الاتصال** لبدء الاتصال بـ Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="4d738-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="4d738-125">حدد **المصادقة مع Campaign Monitor** ووفر بيانات اعتماد المسؤول الخاصة بك لـ Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="4d738-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="4d738-126">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4d738-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="4d738-127">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="4d738-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4d738-128">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="4d738-128">Configure an export</span></span>

<span data-ttu-id="4d738-129">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="4d738-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4d738-130">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4d738-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4d738-131">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="4d738-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4d738-132">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="4d738-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4d738-133">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="4d738-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="4d738-134">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="4d738-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4d738-135">أدخل [**معرف قائمة Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="4d738-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="4d738-136">[إنشاء مفتاح واجهة برمجة التطبيقات](https://www.campaignmonitor.com/api/getting-started/) من **إعدادات الحساب** في Campaign Monitor أولاً لعرض معرف قائمة واجهة برمجة التطبيقات.</span><span class="sxs-lookup"><span data-stu-id="4d738-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="4d738-137">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="4d738-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="4d738-138">يلزم تصدير شرائح إلى Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="4d738-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="4d738-139">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="4d738-139">Select **Save**.</span></span>

<span data-ttu-id="4d738-140">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="4d738-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4d738-141">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4d738-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4d738-142">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4d738-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4d738-143">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="4d738-143">Data privacy and compliance</span></span>

<span data-ttu-id="4d738-144">عند تمكين Dynamics 365 Customer Insights لنقل البيانات إلى Campaign Monitor، فأنت تسمح بنقل البيانات خارج حدود الامتثال لـ Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="4d738-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4d738-145">ستقوم Microsoft بنقل هذه البيانات بموجب الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان ووفاء Campaign Monitor بأي خصوصية أو التزامات أمنية قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="4d738-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4d738-146">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4d738-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="4d738-147">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="4d738-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
