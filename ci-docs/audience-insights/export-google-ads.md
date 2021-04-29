---
title: تصدير بيانات Customer Insights إلى Google Ads
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى إعلانات Google.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759677"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="71f66-103">تصدير شرائح إلى إعلانات Google (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="71f66-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="71f66-104">يمكنك تصدير شرائح ملفات تعريف العملاء الموحدة إلى قوائم جمهور Google Ads واستخدامها للإعلان على Google Search وGmail وYouTubeوGoogle Display Network.</span><span class="sxs-lookup"><span data-stu-id="71f66-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="71f66-105">المتطلبات الأساسية للاتصال</span><span class="sxs-lookup"><span data-stu-id="71f66-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="71f66-106">لديك [حساب Google Ads](https://ads.google.com/) وبيانات اعتماد مسؤول مطابقة.</span><span class="sxs-lookup"><span data-stu-id="71f66-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="71f66-107">لديك رمز [مطور إعلانات Google معتمد](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="71f66-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="71f66-108">أنت تفي بمتطلبات [سياسة مطابقة العملاء](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="71f66-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="71f66-109">أنت تفي بمتطلبات [أحجام قائمة تجديد النشاط التسويقي](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="71f66-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="71f66-110">هناك شرائح جمهور موجودة في Google Ads والمعرفات المناظرة.</span><span class="sxs-lookup"><span data-stu-id="71f66-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="71f66-111">لمزيد من المعلومات، راجع [شرائح جمهور Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="71f66-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="71f66-112">لقد قمت [بتكوين الشرائح](segments.md)</span><span class="sxs-lookup"><span data-stu-id="71f66-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="71f66-113">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقول تمثل عنوان البريد الإلكتروني والاسم الأول واسم العائلة.</span><span class="sxs-lookup"><span data-stu-id="71f66-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="71f66-114">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="71f66-114">Known limitations</span></span>

- <span data-ttu-id="71f66-115">حتى مليون من ملفات التعريف لكل تصدير إلى Google Ads.</span><span class="sxs-lookup"><span data-stu-id="71f66-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="71f66-116">يقتصر التصدير إلى Google Ads على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="71f66-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="71f66-117">قد تستغرق عملية تصدير الشرائح التي تتضمن ما يصل إلى مليون ملف تعريف بشكل إجمالي 5 دقائق كحدٍ أقصى نتيجة للقيود من جانب الموفر.</span><span class="sxs-lookup"><span data-stu-id="71f66-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="71f66-118">قد يستغرق التطابق في Google Ads ما يصل إلى 48 ساعة.</span><span class="sxs-lookup"><span data-stu-id="71f66-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="71f66-119">إعداد الاتصال بإعلانات Google</span><span class="sxs-lookup"><span data-stu-id="71f66-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="71f66-120">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="71f66-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="71f66-121">حدد **إضافة اتصال** واختر **إعلانات Google** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="71f66-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="71f66-122">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="71f66-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="71f66-123">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="71f66-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="71f66-124">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="71f66-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="71f66-125">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="71f66-125">Choose who can use this connection.</span></span> <span data-ttu-id="71f66-126">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="71f66-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="71f66-127">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="71f66-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="71f66-128">أدخل **[معرف عميل Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="71f66-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="71f66-129">أدخل **[الرمز المميز لمطور Google Ads الموافق عليه](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="71f66-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="71f66-130">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="71f66-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="71f66-131">حدد **المصادقة مع Google Ads** وقد بيانات اعتماد Google Ads.</span><span class="sxs-lookup"><span data-stu-id="71f66-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="71f66-132">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="71f66-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="71f66-133">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="71f66-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="71f66-134">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="71f66-134">Configure an export</span></span>

<span data-ttu-id="71f66-135">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="71f66-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="71f66-136">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="71f66-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="71f66-137">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="71f66-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="71f66-138">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="71f66-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="71f66-139">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم إعلانات Google.</span><span class="sxs-lookup"><span data-stu-id="71f66-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="71f66-140">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="71f66-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="71f66-141">أدخل **[معرف جمهور Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** وحدد **اتصال** لبدء الاتصال بـ Google Ads.</span><span class="sxs-lookup"><span data-stu-id="71f66-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="71f66-142">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="71f66-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="71f66-143">كرر نفس الخطوات الخاصة للحقلين **الاسم الأول** و **اسم العائلة**.</span><span class="sxs-lookup"><span data-stu-id="71f66-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="71f66-144">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="71f66-144">Select the segments you want to export.</span></span> <span data-ttu-id="71f66-145">يمكنك تصدير ما يصل إلى مليون من ملفات تعريف العملاء إلى Google Ads.</span><span class="sxs-lookup"><span data-stu-id="71f66-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="71f66-146">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="71f66-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="71f66-147">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="71f66-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="71f66-148">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="71f66-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="71f66-149">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="71f66-149">Data privacy and compliance</span></span>

<span data-ttu-id="71f66-150">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Google Ads، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="71f66-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="71f66-151">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Google Ads بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="71f66-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="71f66-152">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="71f66-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="71f66-153">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="71f66-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
