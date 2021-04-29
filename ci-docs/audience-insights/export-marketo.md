---
title: تصدير بيانات Customer Insights إلى Marketo
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759805"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="5c5af-103">تصدير شرائح إلى Marketo (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="5c5af-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="5c5af-104">يمكنك تصدير الشرائح ملفات تعريف العملاء الموحدة لإنشاء الحملات وتقديم تسويق عبر البريد الإلكتروني واستخدام مجموعات محددة من العملاء باستخدام Marketo.</span><span class="sxs-lookup"><span data-stu-id="5c5af-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="5c5af-105">المتطلبات الأساسية للاتصال</span><span class="sxs-lookup"><span data-stu-id="5c5af-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="5c5af-106">لديك [حساب Marketo](https://login.marketo.com/) وبيانات اعتماد مسؤول مطابقة.</span><span class="sxs-lookup"><span data-stu-id="5c5af-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="5c5af-107">هناك قوائم موجودة في Marketo والمعرفات المناظرة.</span><span class="sxs-lookup"><span data-stu-id="5c5af-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="5c5af-108">لمزيد من المعلومات، راجع [قوائم Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="5c5af-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="5c5af-109">لقد قمت [بتكوين الشرائح](segments.md).</span><span class="sxs-lookup"><span data-stu-id="5c5af-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="5c5af-110">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="5c5af-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="5c5af-111">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="5c5af-111">Known limitations</span></span>

- <span data-ttu-id="5c5af-112">حتى مليون من ملفات التعريف لكل تصدير إلى Marketo.</span><span class="sxs-lookup"><span data-stu-id="5c5af-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="5c5af-113">يقتصر التصدير إلى Marketo على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="5c5af-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="5c5af-114">تستغرق عملية تصدير الشرائح التي تتضمن مليون ملف تعريف بشكل إجمالي حتى 3 ساعات.</span><span class="sxs-lookup"><span data-stu-id="5c5af-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="5c5af-115">يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى Marketo على العقد مع Marketo، وهذا العدد مقيد بالعقد.</span><span class="sxs-lookup"><span data-stu-id="5c5af-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="5c5af-116">إعداد الاتصال بـ Marketo</span><span class="sxs-lookup"><span data-stu-id="5c5af-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="5c5af-117">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="5c5af-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="5c5af-118">حدد **إضافة اتصال** واختر **Marketo** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="5c5af-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="5c5af-119">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="5c5af-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="5c5af-120">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="5c5af-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="5c5af-121">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="5c5af-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="5c5af-122">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="5c5af-122">Choose who can use this connection.</span></span> <span data-ttu-id="5c5af-123">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="5c5af-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="5c5af-124">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5c5af-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="5c5af-125">أدخل **[معرف عميل Marketo، وسر العميل واسم مضيف نقطة نهاية REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="5c5af-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="5c5af-126">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬** وحدد **اتصال** لتهيئة الاتصال بـ Marketo.</span><span class="sxs-lookup"><span data-stu-id="5c5af-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="5c5af-127">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5c5af-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="5c5af-128">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="5c5af-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="5c5af-129">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="5c5af-129">Configure an export</span></span>

<span data-ttu-id="5c5af-130">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="5c5af-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="5c5af-131">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="5c5af-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="5c5af-132">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="5c5af-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="5c5af-133">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="5c5af-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="5c5af-134">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Marketo.</span><span class="sxs-lookup"><span data-stu-id="5c5af-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="5c5af-135">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="5c5af-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="5c5af-136">أدخل **[معرف قائمة Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="5c5af-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="5c5af-137">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="5c5af-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="5c5af-138">بشكل اختياري، يمكنك تصدير **الاسم الأول**، و **اسم العائلة**، و **المدينة**، و **الحالة**، و **البلد/المنطقة** لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة.</span><span class="sxs-lookup"><span data-stu-id="5c5af-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="5c5af-139">حدد **إضافة سمة** لتعيين هذه الحقول.</span><span class="sxs-lookup"><span data-stu-id="5c5af-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="5c5af-140">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="5c5af-140">Select the segments you want to export.</span></span> <span data-ttu-id="5c5af-141">يمكنك تصدير ما يصل إلى مليون من ملفات تعريف العملاء إلى Marketo.</span><span class="sxs-lookup"><span data-stu-id="5c5af-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="5c5af-142">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="5c5af-142">Select **Save**.</span></span>

<span data-ttu-id="5c5af-143">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="5c5af-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="5c5af-144">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="5c5af-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="5c5af-145">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="5c5af-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="5c5af-146">في Marketo، يمكنك الآن البحث عن الشرائح أسفل [قوائم Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="5c5af-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="5c5af-147">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="5c5af-147">Data privacy and compliance</span></span>

<span data-ttu-id="5c5af-148">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Marketo، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="5c5af-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="5c5af-149">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Marketo بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="5c5af-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="5c5af-150">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="5c5af-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="5c5af-151">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="5c5af-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]