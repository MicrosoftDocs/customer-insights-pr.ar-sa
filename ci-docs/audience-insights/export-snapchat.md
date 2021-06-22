---
title: تصدير بيانات Customer Insights إلى Snapchat
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6565ab81599abcc0f94465e1153f08e0bc119839
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124027"
---
# <a name="export-segments-to-snapchat-preview"></a><span data-ttu-id="62fe8-103">تصدير الشرائح إلى Snapchat (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="62fe8-103">Export segments to Snapchat (preview)</span></span>

<span data-ttu-id="62fe8-104">قم بتصدير شرائح ملفات تعريف العملاء الموحدة إلى Snapchat واستخدامها في الإعلانات.</span><span class="sxs-lookup"><span data-stu-id="62fe8-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="62fe8-105">المتطلبات الأساسية لاتصال</span><span class="sxs-lookup"><span data-stu-id="62fe8-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="62fe8-106">لديك [حساب Snapchat Business](https://business.snapchat.com/)، و[حساب Snapchat Ads](https://ads.snapchat.com/)، وبيانات اعتماد المسؤول المقابلة.</span><span class="sxs-lookup"><span data-stu-id="62fe8-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="62fe8-107">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="62fe8-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="62fe8-108">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="62fe8-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="62fe8-109">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="62fe8-109">Known limitations</span></span>

- <span data-ttu-id="62fe8-110">يقتصر التصدير إلى Snapchat على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="62fe8-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="62fe8-111">قد يستغرق تصدير ما يصل إلى مليون ملف تعريف إلى Snapchat ما يصل إلى 15 دقيقة حتى الاكتمال.</span><span class="sxs-lookup"><span data-stu-id="62fe8-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="62fe8-112">إعداد الاتصال بـ Snapchat</span><span class="sxs-lookup"><span data-stu-id="62fe8-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="62fe8-113">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="62fe8-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="62fe8-114">حدد **إضافة اتصال** واختر **Snapchat** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="62fe8-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="62fe8-115">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="62fe8-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="62fe8-116">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="62fe8-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="62fe8-117">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="62fe8-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="62fe8-118">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="62fe8-118">Choose who can use this connection.</span></span> <span data-ttu-id="62fe8-119">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="62fe8-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="62fe8-120">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="62fe8-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="62fe8-121">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="62fe8-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="62fe8-122">حدد **الاتصال** لبدء الاتصال بـ Snapchat.</span><span class="sxs-lookup"><span data-stu-id="62fe8-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="62fe8-123">حدد **المصادقة مع Snapchat** ووفر بيانات اعتماد المسؤول الخاصة بك لـ Snapchat.</span><span class="sxs-lookup"><span data-stu-id="62fe8-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="62fe8-124">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="62fe8-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="62fe8-125">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="62fe8-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="62fe8-126">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="62fe8-126">Configure an export</span></span>

<span data-ttu-id="62fe8-127">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="62fe8-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="62fe8-128">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="62fe8-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="62fe8-129">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="62fe8-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="62fe8-130">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="62fe8-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="62fe8-131">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Snapchat.</span><span class="sxs-lookup"><span data-stu-id="62fe8-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="62fe8-132">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="62fe8-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="62fe8-133">أدخل [**معرف جمهور Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="62fe8-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="62fe8-134">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="62fe8-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="62fe8-135">يلزم تصدير شرائح إلى Snapchat.</span><span class="sxs-lookup"><span data-stu-id="62fe8-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="62fe8-136">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="62fe8-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="62fe8-137">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="62fe8-137">Select **Save**.</span></span>

<span data-ttu-id="62fe8-138">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="62fe8-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="62fe8-139">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="62fe8-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="62fe8-140">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="62fe8-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="62fe8-141">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="62fe8-141">Data privacy and compliance</span></span>

<span data-ttu-id="62fe8-142">عند تمكين Dynamics 365 Customer Insights لنقل البيانات إلى Snapchat، فأنت تسمح بنقل البيانات خارج حدود الامتثال لـ Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="62fe8-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="62fe8-143">ستقوم Microsoft بنقل هذه البيانات بموجب الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان ووفاء Snapchat بأي خصوصية أو التزامات أمنية قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="62fe8-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="62fe8-144">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="62fe8-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="62fe8-145">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="62fe8-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
