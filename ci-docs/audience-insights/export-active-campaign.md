---
title: تصدير بيانات Customer Insights إلى ActiveCampaign
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314569"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="6cf6a-103">تصدير شرائح إلى ActiveCampaign (معاينة)</span><span class="sxs-lookup"><span data-stu-id="6cf6a-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="6cf6a-104">قم بتصدير شرائح من ملفات تعريف العملاء الموحدين إلى ActiveCampaign واستخدامها في أنشطة التسويق.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6cf6a-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="6cf6a-105">Prerequisites</span></span>

-   <span data-ttu-id="6cf6a-106">لديك [حساب ActiveCampaign](https://www.activecampaign.com/) وبيانات اعتماد المسؤول المقابلة.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6cf6a-107">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6cf6a-108">تحتوي ملفات تعريف العملاء الموحدة في الشرائح التي تم تصديرها على حقل يحتوي على عنوان بريد إلكتروني.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6cf6a-109">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="6cf6a-109">Known limitations</span></span>

- <span data-ttu-id="6cf6a-110">يمكن تصدير ما يصل إلى مليون ملف تعريف لكل عملية تصدير إلى ActiveCampaign وقد يستغرق حتى 90 دقيقة حتى تكتمل.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="6cf6a-111">يقتصر التصدير إلى ActiveCampaign على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="6cf6a-112">يعتمد عدد ملفات التعريف التي يمكنك تصديرها إلى ActiveCampaign على العقد الخاص بك مع ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="6cf6a-113">إعداد اتصال بـ ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="6cf6a-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="6cf6a-114">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6cf6a-115">حدد **إضافة اتصال** واختر **ActiveCampaign** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="6cf6a-116">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6cf6a-117">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6cf6a-118">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6cf6a-119">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-119">Choose who can use this connection.</span></span> <span data-ttu-id="6cf6a-120">إنه المسؤول بشكل افتراضي.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-120">By default, it's only administrators.</span></span> <span data-ttu-id="6cf6a-121">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6cf6a-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6cf6a-122">أدخل [مفتاح ActiveCampaign API واسم المضيف لنقطة نهاية REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="6cf6a-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="6cf6a-123">اسم المضيف نقطة النهاية REST هو اسم المضيف فقط، بدون https://.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="6cf6a-124">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6cf6a-125">حدد **اتصال** لتهيئة الاتصال بـ ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="6cf6a-126">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6cf6a-127">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6cf6a-128">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="6cf6a-128">Configure an export</span></span>

<span data-ttu-id="6cf6a-129">يمكنك تكوين تصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="6cf6a-130">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6cf6a-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6cf6a-131">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6cf6a-132">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6cf6a-133">في حقل **اتصال للتصدير**، اختر اتصالا من قسم ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="6cf6a-134">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6cf6a-135">أدخل [**معرف قائمة ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="6cf6a-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="6cf6a-136">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6cf6a-137">مطلوب لتصدير الشرائح إلى ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="6cf6a-138">بشكل اختياري، يمكنك تصدير الاسم الأول، واسم العائلة، والهاتف لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="6cf6a-139">حدد إضافة سمة لتعيين هذه الحقول.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="6cf6a-140">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-140">Select **Save**.</span></span>

<span data-ttu-id="6cf6a-141">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6cf6a-142">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6cf6a-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6cf6a-143">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6cf6a-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6cf6a-144">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="6cf6a-144">Data privacy and compliance</span></span>

<span data-ttu-id="6cf6a-145">عندما تقوم بتمكين Dynamics 365 Customer Insights لنقل البيانات إلى ActiveCampaign، يمكنك السماح بنقل البيانات خارج حدود التوافق ل Dynamics 365 Customer Insights، بما في ذلك البيانات التي قد تكون حساسة مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6cf6a-146">ستقوم Microsoft بنقل هذه البيانات في الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان وفاء ActiveCampaign بأية خصوصية أو واجبات أمنية قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6cf6a-147">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6cf6a-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="6cf6a-148">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="6cf6a-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
