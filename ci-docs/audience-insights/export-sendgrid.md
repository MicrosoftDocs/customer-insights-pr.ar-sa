---
title: تصدير بيانات Customer Insights إلى SendGrid
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976876"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="f5ab9-103">تصدير شرائح إلى SendGrid (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="f5ab9-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="f5ab9-104">يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة‬ إلى قوائم جهات اتصال SendGrid واستخدامها في الحملات والتسويق عبر البريد الإلكتروني في SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f5ab9-105">المتطلبات الأساسية لاتصال</span><span class="sxs-lookup"><span data-stu-id="f5ab9-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f5ab9-106">لديك [حساب SendGrid](https://sendgrid.com/) وبيانات اعتماد مسؤول مطابقة.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f5ab9-107">هناك قوائم جهات اتصال موجودة في SendGrid والمعرفات المناظرة.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="f5ab9-108">لمزيد من المعلومات، راجع [SendGrid - إدارة جهات الاتصال‎](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="f5ab9-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="f5ab9-109">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f5ab9-110">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f5ab9-111">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="f5ab9-111">Known limitations</span></span>

- <span data-ttu-id="f5ab9-112">حتى ‎100'000 من ملفات التعريف بشكل إجمالي إلى SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="f5ab9-113">يقتصر التصدير إلى SendGrid على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="f5ab9-114">قد يحتاج اكتمال تصدير حتى ‎100'000 ملف تعريف إلى SendGrid إلى ساعات قليلة.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="f5ab9-115">يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى SendGrid على العقد مع SendGrid، وهذا العدد مقيد بالعقد.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="f5ab9-116">إعداد الاتصال بـ SendGrid</span><span class="sxs-lookup"><span data-stu-id="f5ab9-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="f5ab9-117">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f5ab9-118">حدد **إضافة اتصال** واختر **SendGrid** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="f5ab9-119">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f5ab9-120">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f5ab9-121">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f5ab9-122">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-122">Choose who can use this connection.</span></span> <span data-ttu-id="f5ab9-123">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f5ab9-124">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f5ab9-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f5ab9-125">أدخل **مفتاح SendGrid API** [مفتاح SendGrid API](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="f5ab9-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="f5ab9-126">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f5ab9-127">حدد **اتصال** لتهيئة الاتصال بـ SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="f5ab9-128">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f5ab9-129">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="f5ab9-130">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="f5ab9-130">Configure an export</span></span>

<span data-ttu-id="f5ab9-131">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f5ab9-132">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f5ab9-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f5ab9-133">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f5ab9-134">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f5ab9-135">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="f5ab9-136">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f5ab9-137">أدخل **[معرف قائمة SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**</span><span class="sxs-lookup"><span data-stu-id="f5ab9-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="f5ab9-138">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f5ab9-139">كرر نفس الخطوات للحقول الاختيارية الأخرى مثل **الاسم الأول** و **اسم العائلة** و **البلد/المنطقة** و **الولاية** و **المدينة** و **الرمز البريدي**.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="f5ab9-140">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-140">Select the segments you want to export.</span></span> <span data-ttu-id="f5ab9-141">نحن **نوصي بعدم تصدير أكثر من ‎100'000 من ملفات تعريف العملاء بشكل إجمالي** إلى SendGrid.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="f5ab9-142">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-142">Select **Save**.</span></span>

<span data-ttu-id="f5ab9-143">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f5ab9-144">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f5ab9-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f5ab9-145">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f5ab9-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f5ab9-146">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="f5ab9-146">Data privacy and compliance</span></span>

<span data-ttu-id="f5ab9-147">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى SendGrid، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f5ab9-148">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام SendGrid بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f5ab9-149">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f5ab9-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f5ab9-150">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]