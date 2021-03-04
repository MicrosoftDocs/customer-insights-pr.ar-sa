---
title: تصدير بيانات Customer Insights إلى Mailchimp
description: اعرف كيفية تكوين الاتصال بـ Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267157"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="c3742-103">موصل Mailchimp (معاينة)</span><span class="sxs-lookup"><span data-stu-id="c3742-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="c3742-104">يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة إلى Mailchimp لإنشاء رسائل إخبارية وحملات بواسطة البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="c3742-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c3742-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="c3742-105">Prerequisites</span></span>

-   <span data-ttu-id="c3742-106">لديك [حساب Mailchimp](https://mailchimp.com/) وبيانات اعتماد مسؤول مطابقة.</span><span class="sxs-lookup"><span data-stu-id="c3742-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="c3742-107">هناك شرائح جمهور موجودة في Mailchimp والمعرفات المناظرة.</span><span class="sxs-lookup"><span data-stu-id="c3742-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="c3742-108">لمزيد من المعلومات، راجع [شرائح جمهور Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="c3742-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="c3742-109">لقد قمت [بتكوين الشرائح](segments.md)</span><span class="sxs-lookup"><span data-stu-id="c3742-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="c3742-110">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="c3742-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="c3742-111">الاتصال بـ Mailchimp</span><span class="sxs-lookup"><span data-stu-id="c3742-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="c3742-112">انتقل إلى **المسؤول** > **وجهات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="c3742-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c3742-113">أسفل **Mailchimp**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="c3742-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="c3742-114">في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.</span><span class="sxs-lookup"><span data-stu-id="c3742-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c3742-115">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="c3742-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c3742-116">أدخل **[معرف جمهور Mailchimp](https://mailchimp.com/help/find-audience-id/)** وحدد **اتصال** لبدء الاتصال بـ Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c3742-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="c3742-117">حدد **المصادقة مع Mailchimp** وقد بيانات اعتماد Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c3742-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="c3742-118">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c3742-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="لقطة شاشة التصدير لاتصال Mailchimp":::

1. <span data-ttu-id="c3742-120">حدد **التالي** لتكوين التصدير.</span><span class="sxs-lookup"><span data-stu-id="c3742-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="c3742-121">تكوين الموصل</span><span class="sxs-lookup"><span data-stu-id="c3742-121">Configure the connector</span></span>

1. <span data-ttu-id="c3742-122">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="c3742-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="c3742-123">بشكل اختياري، يمكنك تصدير **الاسم الأول** و **اسم العائلة** كحقول إضافية لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة.</span><span class="sxs-lookup"><span data-stu-id="c3742-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="c3742-124">حدد **إضافة سمة** لتعيين هذه الحقول.</span><span class="sxs-lookup"><span data-stu-id="c3742-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="c3742-125">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="c3742-125">Select the segments you want to export.</span></span> <span data-ttu-id="c3742-126">يمكنك تصدير ما يصل إلى مليون من ملفات تعريف العملاء إلى Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c3742-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="حدد الحقول والشرائح لتصديرها إلى Mailchimp":::

1. <span data-ttu-id="c3742-128">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="c3742-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c3742-129">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="c3742-129">Export the data</span></span>

<span data-ttu-id="c3742-130">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c3742-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c3742-131">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c3742-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c3742-132">في Mailchimp، يمكنك الآن البحث عن الشرائح أسفل [شرائح جمهور Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="c3742-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c3742-133">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="c3742-133">Known limitations</span></span>

- <span data-ttu-id="c3742-134">حتى مليون من ملفات التعريف لكل تصدير إلى Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="c3742-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="c3742-135">يقتصر التصدير إلى Mailchimp على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="c3742-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="c3742-136">قد تستغرق عملية تصدير الشرائح التي تتضمن ما يصل إلى مليون ملف تعريف بشكل إجمالي ثلاث ساعات كحدٍ أقصى نتيجة للقيود من جانب الموفر.</span><span class="sxs-lookup"><span data-stu-id="c3742-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="c3742-137">يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى Mailchimp على العقد مع Mailchimp، وهذا العدد مقيد بالعقد.</span><span class="sxs-lookup"><span data-stu-id="c3742-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c3742-138">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="c3742-138">Data privacy and compliance</span></span>

<span data-ttu-id="c3742-139">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Mailchimp، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="c3742-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c3742-140">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Mailchimp بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="c3742-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c3742-141">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c3742-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c3742-142">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="c3742-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]