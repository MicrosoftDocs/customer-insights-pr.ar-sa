---
title: تصدير بيانات Customer Insights إلى Constant Contact
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760456"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="e4739-103">تصدير قوائم الشرائح إلى Constant Contact (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="e4739-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="e4739-104">قم بتصدير شرائح ملفات تعريف العملاء الموحدة إلى Constant Contact واستخدامها في أنشطة التسويق.</span><span class="sxs-lookup"><span data-stu-id="e4739-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e4739-105">المتطلبات الأساسية لاتصال</span><span class="sxs-lookup"><span data-stu-id="e4739-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e4739-106">لديك [حساب Constant Contact](https://www.constantcontact.com/account-home) وبيانات اعتماد المسؤول المقابلة.</span><span class="sxs-lookup"><span data-stu-id="e4739-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e4739-107">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="e4739-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e4739-108">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="e4739-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e4739-109">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="e4739-109">Known limitations</span></span>

- <span data-ttu-id="e4739-110">يمكنك تصدير حتى 1 مليوت ملف تعريف لكل تصدير إلى Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e4739-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="e4739-111">يقتصر التصدير إلى Constant Contact على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="e4739-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="e4739-112">قد يستغرق تصدير ما يصل إلى مليون ملف تعريف إلى Constant Contact ما يصل إلى 1 ساعة حتى الاكتمال.</span><span class="sxs-lookup"><span data-stu-id="e4739-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="e4739-113">عدد الملفات الشخصية التي يمكنك تصديرها إلى Constant Contact يعتمد ويقتصر على عقدك مع Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e4739-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="e4739-114">إعداد الاتصال بـ Constant Contact</span><span class="sxs-lookup"><span data-stu-id="e4739-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="e4739-115">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="e4739-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e4739-116">حدد **إضافة اتصال** واختر **Constant Contact** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="e4739-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="e4739-117">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="e4739-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e4739-118">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="e4739-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e4739-119">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="e4739-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e4739-120">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="e4739-120">Choose who can use this connection.</span></span> <span data-ttu-id="e4739-121">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="e4739-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e4739-122">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e4739-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e4739-123">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="e4739-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e4739-124">حدد **الاتصال** لبدء الاتصال بـ Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e4739-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="e4739-125">حدد **المصادقة مع AdRoll** ووفر بيانات اعتماد المسؤول الخاصة بك لـ Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e4739-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="e4739-126">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e4739-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e4739-127">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="e4739-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e4739-128">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="e4739-128">Configure an export</span></span>

<span data-ttu-id="e4739-129">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="e4739-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e4739-130">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e4739-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e4739-131">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="e4739-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e4739-132">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="e4739-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e4739-133">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e4739-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="e4739-134">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="e4739-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e4739-135">أدخل [**معرف قائمة Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="e4739-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="e4739-136">افتح قائمة في Constant Contact للعثور على معرف القائمة في URL.</span><span class="sxs-lookup"><span data-stu-id="e4739-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="e4739-137">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="e4739-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e4739-138">يلزم تصدير شرائح إلى Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="e4739-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="e4739-139">بشكل اختياري، يمكنك تصدير الاسم الأول واسم العائلة كحقول إضافية لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة.</span><span class="sxs-lookup"><span data-stu-id="e4739-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="e4739-140">حدد **إضافة سمة** لتعيين هذه الحقول.</span><span class="sxs-lookup"><span data-stu-id="e4739-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e4739-141">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="e4739-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="e4739-142">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="e4739-142">Select **Save**.</span></span>

<span data-ttu-id="e4739-143">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="e4739-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e4739-144">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e4739-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e4739-145">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e4739-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e4739-146">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="e4739-146">Data privacy and compliance</span></span>

<span data-ttu-id="e4739-147">عند تمكين Dynamics 365 Customer Insights لنقل البيانات إلى Constant Contact، فأنت تسمح بنقل البيانات خارج حدود الامتثال لـ Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="e4739-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e4739-148">ستقوم Microsoft بنقل هذه البيانات بموجب الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان ووفاء Constant Contact بأي خصوصية أو التزامات أمنية قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="e4739-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e4739-149">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e4739-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e4739-150">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="e4739-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
