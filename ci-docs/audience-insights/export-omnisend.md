---
title: تصدير بيانات Customer Insights إلى Omnisend
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124445"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="28044-103">تصدير شرائح إلى Omnisend (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="28044-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="28044-104">يمكنك تصدير شرائح ملفات تعريف العملاء الموحدة إلى Omnisend واستخدامها في أنشطة التسويق.</span><span class="sxs-lookup"><span data-stu-id="28044-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28044-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="28044-105">Prerequisites</span></span>

-   <span data-ttu-id="28044-106">لديك [حساب Omnisend](https://www.omnisend.com/) وبيانات اعتماد المسؤول المقابلة.</span><span class="sxs-lookup"><span data-stu-id="28044-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="28044-107">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="28044-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="28044-108">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="28044-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="28044-109">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="28044-109">Known limitations</span></span>

- <span data-ttu-id="28044-110">يمكنك تصدير ما يصل إلى مليون ملف تعريف لكل تصدير إلى Omnisend وقد يستغرق استكمال العملية ما يصل إلى 4 ساعات.</span><span class="sxs-lookup"><span data-stu-id="28044-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="28044-111">يقتصر التصدير إلى Omnisend على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="28044-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="28044-112">يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى Omnisend على عقدك مع Omnisend.</span><span class="sxs-lookup"><span data-stu-id="28044-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="28044-113">إعداد الاتصال بـ Omnisend</span><span class="sxs-lookup"><span data-stu-id="28044-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="28044-114">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="28044-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="28044-115">حدد **إضافة اتصال** واختر **Omnisend** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="28044-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="28044-116">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="28044-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="28044-117">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="28044-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="28044-118">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="28044-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="28044-119">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="28044-119">Choose who can use this connection.</span></span> <span data-ttu-id="28044-120">إنه المسؤول بشكل افتراضي.</span><span class="sxs-lookup"><span data-stu-id="28044-120">By default it's only administrators.</span></span> <span data-ttu-id="28044-121">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="28044-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="28044-122">أدخل [مفتاح واجهة برمجة تطبيقات Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="28044-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="28044-123">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="28044-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="28044-124">حدد **الاتصال** لبدء الاتصال بـ Omnisend.</span><span class="sxs-lookup"><span data-stu-id="28044-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="28044-125">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="28044-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="28044-126">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="28044-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="28044-127">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="28044-127">Configure an export</span></span>

<span data-ttu-id="28044-128">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="28044-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="28044-129">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="28044-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="28044-130">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="28044-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="28044-131">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="28044-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="28044-132">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Omnisend.</span><span class="sxs-lookup"><span data-stu-id="28044-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="28044-133">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="28044-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="28044-134">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="28044-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="28044-135">يلزم تصدير شرائح إلى Omnisend.</span><span class="sxs-lookup"><span data-stu-id="28044-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="28044-136">بشكل اختياري، يمكنك تصدير الاسم الأول، واسم العائلة، والعنوان، والبلد/المنطقة، والولاية، والمدينة والرمز البريدي لإنشاء رسائل بريد إلكتروني أكثر تخصيصًا.</span><span class="sxs-lookup"><span data-stu-id="28044-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="28044-137">حدد **إضافة سمة** لتعيين هذه الحقول.</span><span class="sxs-lookup"><span data-stu-id="28044-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="28044-138">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="28044-138">Select **Save**.</span></span>

<span data-ttu-id="28044-139">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="28044-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="28044-140">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="28044-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="28044-141">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="28044-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="28044-142">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="28044-142">Data privacy and compliance</span></span>

<span data-ttu-id="28044-143">عند تمكين Dynamics 365 Customer Insights لنقل البيانات إلى Ommisend ، فأنت تسمح بنقل البيانات خارج حدود الامتثال لـ Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="28044-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="28044-144">ستقوم Microsoft بنقل هذه البيانات بموجب الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان وفاء Omnisend بأي خصوصية أو التزامات أمنية قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="28044-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="28044-145">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="28044-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="28044-146">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="28044-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
