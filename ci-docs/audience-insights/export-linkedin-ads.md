---
title: تصدير بيانات Customer Insights إلى إعلانات LinkedIn
description: تعرف على كيفية تكوين الاتصال والتصدير إلى إعلانات LinkedIn.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124446"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="2dcd1-103">تصدير شرائح إلى إعلانات LinkedIn (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="2dcd1-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="2dcd1-104">يمكنك تصدير شرائح ملفات تعريف العملاء الموحدة إلى إعلانات LinkedIn لإنشاء شرائح جمهور مطابقة.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="2dcd1-105">استخدم شرائح الجمهور المطابقة لاستهداف الشركات واستهداف جهات الاتصال.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2dcd1-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="2dcd1-106">Prerequisites</span></span>

-   <span data-ttu-id="2dcd1-107">لديك [حساب LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) وبيانات اعتماد مسؤول مناظرة.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2dcd1-108">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2dcd1-109">تحتوي ملفات تعريف العملاء في الشرائح التي تم تصديرها على حقل يحتوي على عنوان بريد إلكتروني.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2dcd1-110">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="2dcd1-110">Known limitations</span></span>

- <span data-ttu-id="2dcd1-111">يمكنك تصدير حتى 100 ألف ملف تعريف لكل تصدير إلى إعلانات LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="2dcd1-112">يقتصر التصدير إلى إعلانات LinkedIn على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="2dcd1-113">قد يستغرق استكمال تصدير ما يصل إلى 100 ألف ملف تعريف إلى إعلانات LinkedIn ما يصل إلى 10 دقائق.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="2dcd1-114">إعداد الاتصال بإعلانات LinkedIn</span><span class="sxs-lookup"><span data-stu-id="2dcd1-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="2dcd1-115">من رؤى الجمهور، انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2dcd1-116">حدد **إضافة اتصال** واختر **إعلانات LinkedIn** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="2dcd1-117">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2dcd1-118">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2dcd1-119">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2dcd1-120">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-120">Choose who can use this connection.</span></span> <span data-ttu-id="2dcd1-121">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكون "المسؤولون".</span><span class="sxs-lookup"><span data-stu-id="2dcd1-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="2dcd1-122">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2dcd1-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2dcd1-123">قدم [معرف حساب LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="2dcd1-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="2dcd1-124">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2dcd1-125">حدد **الاتصال** لبدء الاتصال بـ Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="2dcd1-126">حدد **المصادقة مع LinkedIn** وقدم بيانات اعتماد المسؤول لـ LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="2dcd1-127">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2dcd1-128">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2dcd1-129">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="2dcd1-129">Configure an export</span></span>

<span data-ttu-id="2dcd1-130">يمكنك تكوين تصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="2dcd1-131">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2dcd1-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2dcd1-132">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2dcd1-133">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2dcd1-134">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم إعلانات LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="2dcd1-135">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2dcd1-136">اختر ما إذا كنت تريد تصدير البيانات من أجل [استهداف جهات الاتصال](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) أو [استهداف الشركات](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) على LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="2dcd1-137">في قسم **مطابقة البيانات**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني الخاص بالعميل.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2dcd1-138">يلزم تصدير الشرائح إلى إعلانات LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="2dcd1-139">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-139">Select the segments you want to export.</span></span> <span data-ttu-id="2dcd1-140">سيتم إنشاء شرائح الجمهور المطابقة في LinkedIn Campaign Manager بشكل تلقائي باسم الشرائح التي حددتها للتصدير.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="2dcd1-141">سينتج عن كل شريحة جمهور مطابق منفصل.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="2dcd1-142">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-142">Select **Save**.</span></span>

<span data-ttu-id="2dcd1-143">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2dcd1-144">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2dcd1-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2dcd1-145">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2dcd1-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2dcd1-146">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="2dcd1-146">Data privacy and compliance</span></span>

<span data-ttu-id="2dcd1-147">عند تمكين Dynamics 365 Customer Insights لنقل البيانات إلى LinkedIn، فأنت تسمح بنقل البيانات خارج حدود الامتثال لـ Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2dcd1-148">ستقوم Microsoft بنقل هذه البيانات بموجب الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان وفاء إعلانات LinkedIn بأي خصوصية أو التزامات أمنية قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="2dcd1-149">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2dcd1-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="2dcd1-150">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لوقف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="2dcd1-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
