---
title: تصدير بيانات Customer Insights إلى DotDigital
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى إعلانات DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124395"
---
# <a name="export-segments-to-dotdigital-preview"></a><span data-ttu-id="f942d-103">تصدير الشرائح إلى DotDigital (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="f942d-103">Export segments to DotDigital (preview)</span></span>

<span data-ttu-id="f942d-104">يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة إلى دفاتر عناوين DotDigital واستخدامها للحملات والتسويق بواسطة البريد الإلكتروني ولإنشاء شرائح العملاء بواسطة DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f942d-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="f942d-105">المتطلبات الأساسية لاتصال</span><span class="sxs-lookup"><span data-stu-id="f942d-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="f942d-106">لديك [حساب DotDigital](https://dotdigital.com/) وبيانات اعتماد مسؤول مطابقة.</span><span class="sxs-lookup"><span data-stu-id="f942d-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f942d-107">هناك دفاتر عناوين موجودة في DotDigital والمعرفات المناظرة.</span><span class="sxs-lookup"><span data-stu-id="f942d-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="f942d-108">يمكن العثور على المعرف في URL عندما تقوم بتحديد وفتح دفتر عناوين.</span><span class="sxs-lookup"><span data-stu-id="f942d-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="f942d-109">لمزيد من المعلومات، راجع [دفاتر عناوين DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="f942d-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="f942d-110">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="f942d-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f942d-111">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="f942d-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f942d-112">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="f942d-112">Known limitations</span></span>

- <span data-ttu-id="f942d-113">حتى مليون من ملفات التعريف لكل تصدير إلى DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f942d-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="f942d-114">يقتصر التصدير إلى DotDigital على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="f942d-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="f942d-115">قد تستغرق عملية تصدير الشرائح التي تتضمن ما يصل إلى مليون ملف تعريف بشكل إجمالي ثلاث ساعات كحدٍ أقصى نتيجة للقيود من جانب الموفر.</span><span class="sxs-lookup"><span data-stu-id="f942d-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="f942d-116">يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى DotDigital على العقد مع DotDigital، وهذا العدد مقيد بالعقد.</span><span class="sxs-lookup"><span data-stu-id="f942d-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="f942d-117">إعداد الاتصال بـ DotDigital</span><span class="sxs-lookup"><span data-stu-id="f942d-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="f942d-118">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="f942d-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f942d-119">حدد **إضافة اتصال** واختر **DotDigital** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="f942d-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="f942d-120">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="f942d-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f942d-121">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="f942d-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f942d-122">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="f942d-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f942d-123">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="f942d-123">Choose who can use this connection.</span></span> <span data-ttu-id="f942d-124">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="f942d-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f942d-125">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f942d-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f942d-126">أدخل **اسم المستخدم وكلمة المرور في DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="f942d-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="f942d-127">أدخل **[معرف دفتر عناوين DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="f942d-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="f942d-128">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="f942d-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f942d-129">حدد **اتصال** لتهيئة الاتصال بـ DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f942d-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="f942d-130">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f942d-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f942d-131">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="f942d-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="f942d-132">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="f942d-132">Configure an export</span></span>

<span data-ttu-id="f942d-133">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="f942d-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f942d-134">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f942d-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f942d-135">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="f942d-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f942d-136">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="f942d-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f942d-137">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f942d-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="f942d-138">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="f942d-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="f942d-139">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="f942d-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f942d-140">كرر نفس الخطوات للحقول الاختيارية الأخرى مثل **الاسم الأول** و **اسم العائلة** و **الاسم الكامل** و **الجنس** و **الرمز البريدي**.</span><span class="sxs-lookup"><span data-stu-id="f942d-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="f942d-141">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="f942d-141">Select the segments you want to export.</span></span> <span data-ttu-id="f942d-142">يمكنك تصدير ما يصل إلى مليون من ملفات تعريف العملاء إلى DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f942d-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="f942d-143">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="f942d-143">Select **Save**.</span></span>

<span data-ttu-id="f942d-144">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="f942d-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f942d-145">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f942d-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f942d-146">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f942d-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="f942d-147">في DotDigital، يمكنك الآن العثور على الشرائح في [دفاتر عناوين DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="f942d-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f942d-148">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="f942d-148">Data privacy and compliance</span></span>

<span data-ttu-id="f942d-149">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى DotDigital، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="f942d-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f942d-150">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام DotDigital بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="f942d-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f942d-151">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f942d-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f942d-152">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="f942d-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
