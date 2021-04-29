---
title: تصدير بيانات Customer Insights إلى Autopilot
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى إعلانات Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760081"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="fbe96-103">تصدير شرائح إلى Autopilot (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="fbe96-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="fbe96-104">يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة‬ إلى Autopilot واستخدامها في الحملات والتسويق عبر البريد الإلكتروني في Autopilot.</span><span class="sxs-lookup"><span data-stu-id="fbe96-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="fbe96-105">المتطلبات الأساسية لاتصال</span><span class="sxs-lookup"><span data-stu-id="fbe96-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="fbe96-106">لديك [حساب Autopilot](https://www.autopilothq.com/) وبيانات اعتماد مسؤول مطابقة.</span><span class="sxs-lookup"><span data-stu-id="fbe96-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="fbe96-107">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="fbe96-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="fbe96-108">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="fbe96-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="fbe96-109">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="fbe96-109">Known limitations</span></span>

- <span data-ttu-id="fbe96-110">يمكنك تصدير ما يصل إلى ‎100'000 من ملفات تعريف العملاء إلى Autopilot.</span><span class="sxs-lookup"><span data-stu-id="fbe96-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="fbe96-111">يقتصر التصدير إلى Autopilot على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="fbe96-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="fbe96-112">قد يحتاج اكتمال تصدير حتى ‎100'000 ملف تعريف إلى Autopilot إلى ساعات قليلة.</span><span class="sxs-lookup"><span data-stu-id="fbe96-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="fbe96-113">يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى Autopilot على العقد مع Autopilot، وهذا العدد مقيد بالعقد.</span><span class="sxs-lookup"><span data-stu-id="fbe96-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="fbe96-114">إعداد الاتصال بـ Autopilot</span><span class="sxs-lookup"><span data-stu-id="fbe96-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="fbe96-115">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="fbe96-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="fbe96-116">حدد **إضافة اتصال** واختر **Autopilot** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="fbe96-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="fbe96-117">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="fbe96-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="fbe96-118">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="fbe96-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="fbe96-119">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="fbe96-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="fbe96-120">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="fbe96-120">Choose who can use this connection.</span></span> <span data-ttu-id="fbe96-121">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="fbe96-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="fbe96-122">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="fbe96-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="fbe96-123">أدخل [مفتاح واجهة برمجة تطبيقات Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="fbe96-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="fbe96-124">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="fbe96-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="fbe96-125">حدد **اتصال** لتهيئة الاتصال بـ Autopilot.</span><span class="sxs-lookup"><span data-stu-id="fbe96-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="fbe96-126">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="fbe96-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="fbe96-127">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="fbe96-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="fbe96-128">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="fbe96-128">Configure an export</span></span>

<span data-ttu-id="fbe96-129">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="fbe96-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="fbe96-130">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="fbe96-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="fbe96-131">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="fbe96-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="fbe96-132">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="fbe96-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="fbe96-133">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Autopilot.</span><span class="sxs-lookup"><span data-stu-id="fbe96-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="fbe96-134">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="fbe96-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="fbe96-135">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="fbe96-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="fbe96-136">كرر نفس الخطوات للحقول الاختيارية الأخرى مثل **الاسم الأول** و **اسم العائلة**.</span><span class="sxs-lookup"><span data-stu-id="fbe96-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="fbe96-137">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="fbe96-137">Select the segments you want to export.</span></span> <span data-ttu-id="fbe96-138">نحن **نوصي بعدم تصدير أكثر من ‎100'000 من ملفات تعريف العملاء بشكل إجمالي** إلى Autopilot.</span><span class="sxs-lookup"><span data-stu-id="fbe96-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="fbe96-139">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="fbe96-139">Select **Save**.</span></span>

<span data-ttu-id="fbe96-140">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="fbe96-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="fbe96-141">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="fbe96-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="fbe96-142">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="fbe96-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="fbe96-143">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="fbe96-143">Data privacy and compliance</span></span>

<span data-ttu-id="fbe96-144">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Autopilot، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="fbe96-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="fbe96-145">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Autopilot بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="fbe96-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="fbe96-146">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="fbe96-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="fbe96-147">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="fbe96-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
