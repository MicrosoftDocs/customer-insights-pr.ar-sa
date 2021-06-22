---
title: تصدير بيانات Customer Insights إلى Microsoft Advertising
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124444"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="a4554-103">تصدير شرائح إلى Microsoft Advertising (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="a4554-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="a4554-104">يمكنك تصدير شرائح Customer Insights إلى Microsoft Advertising لإنشاء شرائح جمهور مطابقة العملاء.</span><span class="sxs-lookup"><span data-stu-id="a4554-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="a4554-105">استخدم شرائح الجمهور هذه لحملاتك الإعلانية.</span><span class="sxs-lookup"><span data-stu-id="a4554-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a4554-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="a4554-106">Prerequisites</span></span>

-   <span data-ttu-id="a4554-107">[حساب Microsoft Advertising](https://ads.microsoft.com/) وبيانات اعتماد المسؤول المقابلة.</span><span class="sxs-lookup"><span data-stu-id="a4554-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a4554-108">قبلت شروط استخدام "مطابقة العملاء".</span><span class="sxs-lookup"><span data-stu-id="a4554-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="a4554-109">[شرائح مكوّنة](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="a4554-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a4554-110">تحتوي ملفات تعريف العملاء الموحدة في الشرائح التي تم تصديرها على حقل يحتوي على عنوان بريد إلكتروني.</span><span class="sxs-lookup"><span data-stu-id="a4554-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a4554-111">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="a4554-111">Known limitations</span></span>

- <span data-ttu-id="a4554-112">يمكنك تصدير حتى 500 ألف ملف تعريف لكل تصدير إلى Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="a4554-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="a4554-113">يقتصر التصدير إلى Microsoft Advertising على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="a4554-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="a4554-114">قد يستغرق استكمال تصدير ما يصل إلى 500 ألف ملف تعريف إلى Microsoft Advertising ما يصل إلى 10 دقائق.</span><span class="sxs-lookup"><span data-stu-id="a4554-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="a4554-115">إعداد الاتصال بـ Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="a4554-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="a4554-116">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="a4554-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a4554-117">حدد **إضافة اتصال** واختر **Microsoft Advertising** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="a4554-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="a4554-118">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="a4554-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a4554-119">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="a4554-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a4554-120">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="a4554-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a4554-121">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="a4554-121">Choose who can use this connection.</span></span> <span data-ttu-id="a4554-122">الإعداد الافتراضي هو "المسؤولون".</span><span class="sxs-lookup"><span data-stu-id="a4554-122">The default is administrators.</span></span> <span data-ttu-id="a4554-123">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a4554-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a4554-124">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="a4554-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a4554-125">حدد **اتصال** لبدء الاتصال بـ Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="a4554-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="a4554-126">حدد **المصادقة مع Microsoft Advertising** وقدم بيانات اعتماد المسؤول الخاصة بك لـ Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="a4554-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="a4554-127">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a4554-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a4554-128">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="a4554-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a4554-129">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="a4554-129">Configure an export</span></span>

<span data-ttu-id="a4554-130">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="a4554-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a4554-131">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a4554-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a4554-132">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="a4554-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a4554-133">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="a4554-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a4554-134">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="a4554-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="a4554-135">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="a4554-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a4554-136">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="a4554-136">Select the segments to export.</span></span> <span data-ttu-id="a4554-137">يتم شرائح جمهور "مطابقة العملاء" في Microsoft Advertising بشكل تلقائي باسم الشرائح المحددة للتصدير.</span><span class="sxs-lookup"><span data-stu-id="a4554-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="a4554-138">سينتج عن كل شريحة جمهور منفصل لمطابقة العملاء.</span><span class="sxs-lookup"><span data-stu-id="a4554-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="a4554-139">أدخل **معرف العميل ومعرف الحساب لـ Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="a4554-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="a4554-140">يمكنك العثور على معرف العميل (`cid`) ومعرف الحساب (`aid`) في معلمات عنوان URL عندما تسجل دخولك إلى Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="a4554-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="a4554-141">في قسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد باستخدام عنوان البريد الإلكتروني الخاص بالعميل.</span><span class="sxs-lookup"><span data-stu-id="a4554-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="a4554-142">يلزم تصدير الشرائح إلى Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="a4554-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="a4554-143">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="a4554-143">Select **Save**.</span></span>

<span data-ttu-id="a4554-144">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="a4554-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a4554-145">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a4554-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a4554-146">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a4554-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a4554-147">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="a4554-147">Data privacy and compliance</span></span>

<span data-ttu-id="a4554-148">عند تمكين Dynamics 365 Customer Insights لنقل البيانات إلى Microsoft Advertising، فأنت تسمح بنقل البيانات خارج حدود الامتثال لـ Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="a4554-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a4554-149">ستقوم Microsoft بنقل هذه البيانات بموجب الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان وفاء Microsoft Advertising بأي خصوصية أو التزامات أمنية قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="a4554-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a4554-150">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a4554-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a4554-151">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لوقف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="a4554-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
