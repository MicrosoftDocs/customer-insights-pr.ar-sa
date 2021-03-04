---
title: تصدير بيانات Customer Insights إلى Marketo
description: اعرف كيفية تكوين الاتصال بـ Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e0245f2d01aabc86f43532822c056965ff7ae67a
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267065"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="3db21-103">موصل Marketo (معاينة)</span><span class="sxs-lookup"><span data-stu-id="3db21-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="3db21-104">يمكنك تصدير الشرائح ملفات تعريف العملاء الموحدة لإنشاء الحملات وتقديم تسويق عبر البريد الإلكتروني واستخدام مجموعات محددة من العملاء باستخدام Marketo.</span><span class="sxs-lookup"><span data-stu-id="3db21-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3db21-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="3db21-105">Prerequisites</span></span>

-   <span data-ttu-id="3db21-106">لديك [حساب Marketo](https://login.marketo.com/) وبيانات اعتماد مسؤول مطابقة.</span><span class="sxs-lookup"><span data-stu-id="3db21-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="3db21-107">هناك قوائم موجودة في Marketo والمعرفات المناظرة.</span><span class="sxs-lookup"><span data-stu-id="3db21-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="3db21-108">لمزيد من المعلومات، راجع [قوائم Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="3db21-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="3db21-109">لقد قمت [بتكوين الشرائح](segments.md).</span><span class="sxs-lookup"><span data-stu-id="3db21-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="3db21-110">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="3db21-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="3db21-111">الاتصال بـ Marketo</span><span class="sxs-lookup"><span data-stu-id="3db21-111">Connect to Marketo</span></span>

1. <span data-ttu-id="3db21-112">انتقل إلى **المسؤول** > **وجهات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="3db21-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3db21-113">أسفل **Marketo**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="3db21-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="3db21-114">في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.</span><span class="sxs-lookup"><span data-stu-id="3db21-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3db21-115">أدخل **[معرف عميل Marketo، وسر العميل واسم مضيف نقطة نهاية REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="3db21-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="3db21-116">أدخل **[معرف قائمة Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="3db21-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="3db21-117">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬** وحدد **اتصال** لتهيئة الاتصال بـ Marketo.</span><span class="sxs-lookup"><span data-stu-id="3db21-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="3db21-118">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="3db21-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="لقطة شاشة التصدير لاتصال Marketo":::

1. <span data-ttu-id="3db21-120">حدد **التالي** لتكوين التصدير.</span><span class="sxs-lookup"><span data-stu-id="3db21-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="3db21-121">تكوين الموصل</span><span class="sxs-lookup"><span data-stu-id="3db21-121">Configure the connector</span></span>

1. <span data-ttu-id="3db21-122">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="3db21-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="3db21-123">بشكل اختياري، يمكنك تصدير **الاسم الأول** و **اسم العائلة** و **المدينة** و **الولاية** و **البلد/المنطقة** كحقول إضافية لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة.</span><span class="sxs-lookup"><span data-stu-id="3db21-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="3db21-124">حدد **إضافة سمة** لتعيين هذه الحقول.</span><span class="sxs-lookup"><span data-stu-id="3db21-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="3db21-125">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="3db21-125">Select the segments you want to export.</span></span> <span data-ttu-id="3db21-126">يمكنك تصدير ما يصل إلى مليون من ملفات تعريف العملاء إلى Marketo.</span><span class="sxs-lookup"><span data-stu-id="3db21-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="حدد الحقول والشرائح لتصديرها إلى Marketo":::

1. <span data-ttu-id="3db21-128">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="3db21-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3db21-129">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="3db21-129">Export the data</span></span>

<span data-ttu-id="3db21-130">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3db21-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3db21-131">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3db21-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3db21-132">في Marketo، يمكنك الآن البحث عن الشرائح أسفل [قوائم Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="3db21-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3db21-133">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="3db21-133">Known limitations</span></span>

- <span data-ttu-id="3db21-134">حتى مليون من ملفات التعريف لكل تصدير إلى Marketo.</span><span class="sxs-lookup"><span data-stu-id="3db21-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="3db21-135">يقتصر التصدير إلى Marketo على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="3db21-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="3db21-136">تستغرق عملية تصدير الشرائح التي تتضمن مليون ملف تعريف بشكل إجمالي حتى 3 ساعات.</span><span class="sxs-lookup"><span data-stu-id="3db21-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="3db21-137">يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى Marketo على العقد مع Marketo، وهذا العدد مقيد بالعقد.</span><span class="sxs-lookup"><span data-stu-id="3db21-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3db21-138">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="3db21-138">Data privacy and compliance</span></span>

<span data-ttu-id="3db21-139">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Marketo، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="3db21-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3db21-140">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Marketo بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="3db21-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3db21-141">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3db21-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3db21-142">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="3db21-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]