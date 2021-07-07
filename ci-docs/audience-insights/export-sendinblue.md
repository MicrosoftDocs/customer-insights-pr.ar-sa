---
title: تصدير بيانات Customer Insights إلى Sendinblue
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314568"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="9d1ab-103">تصدير شرائح إلى Sendinblue (معاينة)</span><span class="sxs-lookup"><span data-stu-id="9d1ab-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="9d1ab-104">قم بتصدير شرائح من ملفات تعريف العملاء الموحدة لإنشاء حملات، وتوفير التسويق عبر البريد الإلكتروني واستخدام مجموعات محددة من العملاء باستخدام Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="9d1ab-105">المتطلبات الأساسية للاتصال</span><span class="sxs-lookup"><span data-stu-id="9d1ab-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="9d1ab-106">لديك [حساب Sendinblue](https://www.sendinblue.com/) وبيانات اعتماد المسؤول المقابلة.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9d1ab-107">هناك قوائم موجودة في Sendinblue والمعرفات المقابلة.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="9d1ab-108">لقد قمت [بتكوين الشرائح](segments.md).</span><span class="sxs-lookup"><span data-stu-id="9d1ab-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="9d1ab-109">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9d1ab-110">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="9d1ab-110">Known limitations</span></span>

- <span data-ttu-id="9d1ab-111">ما يصل إلى مليون ملف تعريف لكل عملية تصدير إلى Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="9d1ab-112">يقتصر التصدير إلى Sendinblue على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="9d1ab-113">قد يستغرق تصدير الشرائح التي يصل إجمالي ملفات تعريفها إلى مليون ملف تعريف ما يصل إلى 90 دقيقة.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="9d1ab-114">يعتمد عدد ملفات التعريف التي يمكنك تصديرها إلى Sendinblue على العقد الخاص بك مع Sendinblue ومحدودة.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="9d1ab-115">إعداد اتصال بـ Sendinblue</span><span class="sxs-lookup"><span data-stu-id="9d1ab-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="9d1ab-116">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9d1ab-117">حدد **إضافة اتصال** واختر **Sendinblue** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="9d1ab-118">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9d1ab-119">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9d1ab-120">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9d1ab-121">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-121">Choose who can use this connection.</span></span> <span data-ttu-id="9d1ab-122">إنه المسؤول بشكل افتراضي.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-122">By default it's only administrators.</span></span> <span data-ttu-id="9d1ab-123">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9d1ab-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9d1ab-124">أدخل **[مفتاح SendinBlue API](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="9d1ab-125">حدد **أوافق** لتأكيد **خصوصية البيانات وتوافقها** وحدد **اتصال** لبدء الاتصال بـ Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="9d1ab-126">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9d1ab-127">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9d1ab-128">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="9d1ab-128">Configure an export</span></span>

<span data-ttu-id="9d1ab-129">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9d1ab-130">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9d1ab-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9d1ab-131">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9d1ab-132">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9d1ab-133">في حقل **اتصال للتصدير**، اختر اتصالا من قسم Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="9d1ab-134">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9d1ab-135">أدخل **معرف قائمة Sendinblue**</span><span class="sxs-lookup"><span data-stu-id="9d1ab-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="9d1ab-136">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="9d1ab-137">بشكل اختياري، يمكنك تصدير **الاسم الأول**، و **اسم العائلة**، و **الهاتف**  لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="9d1ab-138">حدد **إضافة سمة** لتعيين هذه الحقول.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="9d1ab-139">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="9d1ab-140">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-140">Select **Save**.</span></span>

<span data-ttu-id="9d1ab-141">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9d1ab-142">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9d1ab-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9d1ab-143">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9d1ab-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9d1ab-144">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="9d1ab-144">Data privacy and compliance</span></span>

<span data-ttu-id="9d1ab-145">عندما تقوم بتمكين Dynamics 365 Customer Insights لنقل البيانات إلى Sendinblue، يمكنك السماح بنقل البيانات خارج حدود التوافق ل Dynamics 365 Customer Insights، بما في ذلك البيانات التي قد تكون حساسة مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9d1ab-146">ستقوم Microsoft بنقل هذه البيانات في الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان وفاء Sendinblue بأية خصوصية أو واجبات أمنية قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9d1ab-147">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9d1ab-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9d1ab-148">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="9d1ab-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
