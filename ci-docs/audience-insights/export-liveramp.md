---
title: موصل LiveRamp
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760311"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="94461-103">تصدير شرائح إلى LiveRamp&reg; (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="94461-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="94461-104">قم بتنشيط البيانات في LiveRamp للاتصال بما يزيد على 500 نظام أساسي عبر أجهزة الكمبيوتر الرقمية، والوسائط الاجتماعية، وأجهزة التلفاز.</span><span class="sxs-lookup"><span data-stu-id="94461-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="94461-105">استخدام بياناتك في LiveRamp لاستهداف الحملات الإعلانية وإزالتها وتخصيصها.</span><span class="sxs-lookup"><span data-stu-id="94461-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="94461-106">المتطلبات الأساسية لاتصال</span><span class="sxs-lookup"><span data-stu-id="94461-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="94461-107">تحتاج إلى اشتراك LiveRamp لاستخدام هذا الموصل.</span><span class="sxs-lookup"><span data-stu-id="94461-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="94461-108">للحصول على اشتراك، [اتصل بـ LiveRamp‎](https://liveramp.com/contact/) بشكل مباشر.</span><span class="sxs-lookup"><span data-stu-id="94461-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="94461-109">[اعرف المزيد حول LiveRamp Onboarding‎](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="94461-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="94461-110">إعداد الاتصال بـ LiveRamp</span><span class="sxs-lookup"><span data-stu-id="94461-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="94461-111">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="94461-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="94461-112">حدد **إضافة اتصال** واختر **LiveRamp** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="94461-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="94461-113">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="94461-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="94461-114">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="94461-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="94461-115">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="94461-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="94461-116">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="94461-116">Choose who can use this connection.</span></span> <span data-ttu-id="94461-117">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="94461-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="94461-118">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="94461-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="94461-119">أدخل **اسم المستخدم** و **كلمة المرور** لحساب LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="94461-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="94461-120">قد تختلف بيانات الاعتماد هذه عن بيانات اعتماد LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="94461-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="94461-121">حدد **التحقق** لاختبار الاتصال بـ LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="94461-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="94461-122">وبعد التحقق الناجح، قدم موافقتك على **خصوصية البيانات والتوافق‬** من خلال تحديد خانة الاختيار **أوافق**.</span><span class="sxs-lookup"><span data-stu-id="94461-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="94461-123">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="94461-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="94461-124">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="94461-124">Configure an export</span></span>

<span data-ttu-id="94461-125">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="94461-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="94461-126">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="94461-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="94461-127">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="94461-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="94461-128">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="94461-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="94461-129">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="94461-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="94461-130">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="94461-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="94461-131">في الحقل **اختيار معرف المفتاح**، حدد **البريد الإلكتروني** أو **الاسم والعنوان** أو **الهاتف** لإرساله إلى LiveRamp لحل الهوية.</span><span class="sxs-lookup"><span data-stu-id="94461-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="94461-132">![موصل LiveRamp مع تعيين السمات](media/export-liveramp-segments.png "موصل LiveRamp مع تعيين السمات")</span><span class="sxs-lookup"><span data-stu-id="94461-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="94461-133">قم بتعيين السمات المناظرة من كيان العميل الموحد لمعرف المفتاح المحدد.</span><span class="sxs-lookup"><span data-stu-id="94461-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="94461-134">حدد **إضافة سمة** لتعيين مزيد من السمات لإرسالها إلى LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="94461-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="94461-135">من المحتمل أن يؤدي إرسال المزيد من سمات معرف المفتاح إلى LiveRamp للحصول على معدل تطابق أعلى.</span><span class="sxs-lookup"><span data-stu-id="94461-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="94461-136">حدد الشرائح التي تريد تصديرها إلى LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="94461-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="94461-137">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="94461-137">Select **Save**.</span></span>

<span data-ttu-id="94461-138">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="94461-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="94461-139">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="94461-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="94461-140">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="94461-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="94461-141">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="94461-141">Data privacy and compliance</span></span>

<span data-ttu-id="94461-142">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Liveramp، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="94461-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="94461-143">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Liveramp بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="94461-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="94461-144">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="94461-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="94461-145">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="94461-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
