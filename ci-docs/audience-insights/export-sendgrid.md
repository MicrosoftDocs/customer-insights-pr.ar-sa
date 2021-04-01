---
title: تصدير بيانات Customer Insights إلى SendGrid
description: اعرف كيفية تكوين الاتصال بـ SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597265"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="932fa-103">موصل SendGrid (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="932fa-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="932fa-104">يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة‬ إلى قوائم جهات اتصال SendGrid واستخدامها في الحملات والتسويق عبر البريد الإلكتروني في SendGrid.</span><span class="sxs-lookup"><span data-stu-id="932fa-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="932fa-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="932fa-105">Prerequisites</span></span>

-   <span data-ttu-id="932fa-106">لديك [حساب SendGrid](https://sendgrid.com/) وبيانات اعتماد مسؤول مطابقة.</span><span class="sxs-lookup"><span data-stu-id="932fa-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="932fa-107">هناك قوائم جهات اتصال موجودة في SendGrid والمعرفات المناظرة.</span><span class="sxs-lookup"><span data-stu-id="932fa-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="932fa-108">لمزيد من المعلومات، راجع [SendGrid - إدارة جهات الاتصال‎](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="932fa-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="932fa-109">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="932fa-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="932fa-110">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="932fa-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="932fa-111">الاتصال بـ SendGrid</span><span class="sxs-lookup"><span data-stu-id="932fa-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="932fa-112">انتقل إلى **المسؤول** > **وجهات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="932fa-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="932fa-113">أسفل **SendGrid**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="932fa-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="932fa-114">في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.</span><span class="sxs-lookup"><span data-stu-id="932fa-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="جزء تكوين تصدير SendGrid.":::

1. <span data-ttu-id="932fa-116">أدخل **مفتاح SendGrid API** [مفتاح SendGrid API](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="932fa-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="932fa-117">أدخل **[معرف قائمة SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**</span><span class="sxs-lookup"><span data-stu-id="932fa-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="932fa-118">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="932fa-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="932fa-119">حدد **اتصال** لتهيئة الاتصال بـ SendGrid.</span><span class="sxs-lookup"><span data-stu-id="932fa-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="932fa-120">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="932fa-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="932fa-121">حدد **التالي** لتكوين التصدير.</span><span class="sxs-lookup"><span data-stu-id="932fa-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="932fa-122">تكوين الموصل</span><span class="sxs-lookup"><span data-stu-id="932fa-122">Configure the connector</span></span>

1. <span data-ttu-id="932fa-123">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="932fa-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="932fa-124">كرر نفس الخطوات للحقول الاختيارية الأخرى مثل **الاسم الأول** و **اسم العائلة** و **البلد/المنطقة** و **الولاية** و **المدينة** و **الرمز البريدي**.</span><span class="sxs-lookup"><span data-stu-id="932fa-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="932fa-125">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="932fa-125">Select the segments you want to export.</span></span> <span data-ttu-id="932fa-126">نحن **نوصي بعدم تصدير أكثر من ‎100'000 من ملفات تعريف العملاء بشكل إجمالي** إلى SendGrid.</span><span class="sxs-lookup"><span data-stu-id="932fa-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="932fa-127">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="932fa-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="932fa-128">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="932fa-128">Export the data</span></span>

<span data-ttu-id="932fa-129">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="932fa-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="932fa-130">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="932fa-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="932fa-131">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="932fa-131">Known limitations</span></span>

- <span data-ttu-id="932fa-132">حتى ‎100'000 من ملفات التعريف بشكل إجمالي إلى SendGrid.</span><span class="sxs-lookup"><span data-stu-id="932fa-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="932fa-133">يقتصر التصدير إلى SendGrid على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="932fa-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="932fa-134">قد يحتاج اكتمال تصدير حتى ‎100'000 ملف تعريف إلى SendGrid إلى ساعات قليلة.</span><span class="sxs-lookup"><span data-stu-id="932fa-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="932fa-135">يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى SendGrid على العقد مع SendGrid، وهذا العدد مقيد بالعقد.</span><span class="sxs-lookup"><span data-stu-id="932fa-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="932fa-136">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="932fa-136">Data privacy and compliance</span></span>

<span data-ttu-id="932fa-137">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى SendGrid، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="932fa-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="932fa-138">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام SendGrid بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="932fa-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="932fa-139">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="932fa-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="932fa-140">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="932fa-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]