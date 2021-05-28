---
title: تصدير بيانات Customer Insights إلى Mailchimp
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 35848998e738c7ecc1642f2b75912ff78d85f79e
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976139"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="a6ef8-103">تصدير قوائم الشرائح إلى Mailchimp (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="a6ef8-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="a6ef8-104">يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة إلى Mailchimp لإنشاء رسائل إخبارية وحملات بواسطة البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="a6ef8-105">المتطلبات الأساسية للاتصال</span><span class="sxs-lookup"><span data-stu-id="a6ef8-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="a6ef8-106">لديك [حساب Mailchimp](https://mailchimp.com/) وبيانات اعتماد مسؤول مطابقة.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a6ef8-107">هناك شرائح جمهور موجودة في Mailchimp والمعرفات المناظرة.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="a6ef8-108">لمزيد من المعلومات، راجع [شرائح جمهور Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="a6ef8-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="a6ef8-109">لقد قمت [بتكوين الشرائح](segments.md)</span><span class="sxs-lookup"><span data-stu-id="a6ef8-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="a6ef8-110">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a6ef8-111">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="a6ef8-111">Known limitations</span></span>

- <span data-ttu-id="a6ef8-112">حتى مليون من ملفات التعريف لكل تصدير إلى Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="a6ef8-113">يقتصر التصدير إلى Mailchimp على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="a6ef8-114">قد يستغرق تصدير الشرائح التي يصل حجم ملفاتها إلى 1 مليون ملف تعريف ما يصل إلى ثلاث ساعات.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="a6ef8-115">يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى Mailchimp على العقد مع Mailchimp، وهذا العدد مقيد بالعقد.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="a6ef8-116">إعداد الاتصال بـ Mailchimp</span><span class="sxs-lookup"><span data-stu-id="a6ef8-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="a6ef8-117">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a6ef8-118">حدد **إضافة اتصال** واختر **Autopilot** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="a6ef8-119">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a6ef8-120">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a6ef8-121">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a6ef8-122">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-122">Choose who can use this connection.</span></span> <span data-ttu-id="a6ef8-123">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a6ef8-124">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a6ef8-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a6ef8-125">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a6ef8-126">حدد **الاتصال** لبدء الاتصال بـ Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="a6ef8-127">حدد **المصادقة مع Mailchimp** وقد بيانات اعتماد Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="a6ef8-128">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a6ef8-129">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="a6ef8-130">تكوين الموصل</span><span class="sxs-lookup"><span data-stu-id="a6ef8-130">Configure the connector</span></span>

<span data-ttu-id="a6ef8-131">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a6ef8-132">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a6ef8-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a6ef8-133">انتقل إلى **البيانات**> **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="a6ef8-134">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a6ef8-135">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="a6ef8-136">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a6ef8-137">أدخل **[معرف جمهور Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="a6ef8-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="a6ef8-138">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="a6ef8-139">بشكل اختياري، يمكنك تصدير **الاسم الأول** و **اسم العائلة** لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="a6ef8-140">حدد **إضافة سمة** لتعيين هذه الحقول.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="a6ef8-141">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-141">Select the segments you want to export.</span></span> <span data-ttu-id="a6ef8-142">يمكنك تصدير ما يصل إلى مليون من ملفات تعريف العملاء إلى Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="a6ef8-143">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-143">Select **Save**.</span></span>

<span data-ttu-id="a6ef8-144">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a6ef8-145">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a6ef8-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a6ef8-146">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a6ef8-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a6ef8-147">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="a6ef8-147">Data privacy and compliance</span></span>

<span data-ttu-id="a6ef8-148">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Mailchimp، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a6ef8-149">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Mailchimp بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a6ef8-150">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a6ef8-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a6ef8-151">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="a6ef8-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
