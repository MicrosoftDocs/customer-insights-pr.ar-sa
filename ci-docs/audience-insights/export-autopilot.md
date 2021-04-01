---
title: تصدير بيانات Customer Insights إلى Autopilot
description: اعرف كيفية تكوين الاتصال بـ Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596101"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="f1749-103">موصل Autopilot (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="f1749-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="f1749-104">يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة‬ إلى Autopilot واستخدامها في الحملات والتسويق عبر البريد الإلكتروني في Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f1749-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f1749-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="f1749-105">Prerequisites</span></span>

-   <span data-ttu-id="f1749-106">لديك [حساب Autopilot](https://www.autopilothq.com/) وبيانات اعتماد مسؤول مطابقة.</span><span class="sxs-lookup"><span data-stu-id="f1749-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f1749-107">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="f1749-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f1749-108">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="f1749-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="f1749-109">الاتصال بـ AutoPilot</span><span class="sxs-lookup"><span data-stu-id="f1749-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="f1749-110">انتقل إلى **المسؤول** > **وجهات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="f1749-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f1749-111">أسفل **Autopilot**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="f1749-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="f1749-112">في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.</span><span class="sxs-lookup"><span data-stu-id="f1749-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="جزء التكوين لاتصال Autopilot.":::

1. <span data-ttu-id="f1749-114">أدخل **مفتاح Autopilot API** [مفتاح Autopilot API](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="f1749-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="f1749-115">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="f1749-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f1749-116">حدد **اتصال** لتهيئة الاتصال بـ Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f1749-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="f1749-117">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f1749-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f1749-118">حدد **التالي** لتكوين التصدير.</span><span class="sxs-lookup"><span data-stu-id="f1749-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f1749-119">تكوين الموصل</span><span class="sxs-lookup"><span data-stu-id="f1749-119">Configure the connector</span></span>

1. <span data-ttu-id="f1749-120">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="f1749-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f1749-121">كرر نفس الخطوات للحقول الاختيارية الأخرى مثل **الاسم الأول** و **اسم العائلة**.</span><span class="sxs-lookup"><span data-stu-id="f1749-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="f1749-122">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="f1749-122">Select the segments you want to export.</span></span> <span data-ttu-id="f1749-123">نحن **نوصي بعدم تصدير أكثر من ‎100'000 من ملفات تعريف العملاء بشكل إجمالي** إلى Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f1749-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="f1749-124">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="f1749-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f1749-125">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="f1749-125">Export the data</span></span>

<span data-ttu-id="f1749-126">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f1749-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f1749-127">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f1749-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f1749-128">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="f1749-128">Known limitations</span></span>

- <span data-ttu-id="f1749-129">يمكنك تصدير ما يصل إلى ‎100'000 من ملفات تعريف العملاء إلى Autopilot.</span><span class="sxs-lookup"><span data-stu-id="f1749-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="f1749-130">يقتصر التصدير إلى Autopilot على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="f1749-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="f1749-131">قد يحتاج اكتمال تصدير حتى ‎100'000 ملف تعريف إلى Autopilot إلى ساعات قليلة.</span><span class="sxs-lookup"><span data-stu-id="f1749-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="f1749-132">يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى Autopilot على العقد مع Autopilot، وهذا العدد مقيد بالعقد.</span><span class="sxs-lookup"><span data-stu-id="f1749-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f1749-133">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="f1749-133">Data privacy and compliance</span></span>

<span data-ttu-id="f1749-134">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Autopilot، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="f1749-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f1749-135">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Autopilot بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="f1749-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f1749-136">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f1749-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f1749-137">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="f1749-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]