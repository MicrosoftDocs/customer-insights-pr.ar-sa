---
title: موصل LiveRamp
description: تعرف على كيفية تصدير البيانات إلى LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597541"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="e448e-103">موصل&reg; LiveRamp‏‎ (معاينة)</span><span class="sxs-lookup"><span data-stu-id="e448e-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="e448e-104">قم بتنشيط بياناتك في LiveRamp‏‎ للاتصال بأكثر من 500 نظام أساسي عبر الأنظمة البيئية الرقمية والاجتماعية والتلفزيونية.</span><span class="sxs-lookup"><span data-stu-id="e448e-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="e448e-105">استخدام بياناتك في LiveRamp لاستهداف الحملات الإعلانية وإزالتها وتخصيصها.</span><span class="sxs-lookup"><span data-stu-id="e448e-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e448e-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="e448e-106">Prerequisites</span></span>

- <span data-ttu-id="e448e-107">تحتاج إلى اشتراك LiveRamp لاستخدام هذا الموصل.</span><span class="sxs-lookup"><span data-stu-id="e448e-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="e448e-108">للحصول على اشتراك، [اتصل بـ LiveRamp‎](https://liveramp.com/contact/) بشكل مباشر.</span><span class="sxs-lookup"><span data-stu-id="e448e-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="e448e-109">[اعرف المزيد حول LiveRamp Onboarding‎](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="e448e-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="e448e-110">الاتصال بـ LiveRamp‎</span><span class="sxs-lookup"><span data-stu-id="e448e-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="e448e-111">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.</span><span class="sxs-lookup"><span data-stu-id="e448e-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e448e-112">في الإطار المتجانب **LiveRamp‎**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="e448e-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="e448e-113">في حقل **الاسم المعروض**، أدخل اسمًا للوجهة سهل التمييز.</span><span class="sxs-lookup"><span data-stu-id="e448e-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e448e-114">أدخل **اسم المستخدم** و **كلمة المرور** لحساب LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="e448e-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="e448e-115">قد تختلف بيانات الاعتماد هذه عن بيانات اعتماد LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="e448e-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="e448e-116">حدد **التحقق** لاختبار الاتصال بـ LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="e448e-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="e448e-117">وبعد التحقق الناجح، قدم موافقتك على **خصوصية البيانات والتوافق‬** من خلال تحديد خانة الاختيار **أوافق**.</span><span class="sxs-lookup"><span data-stu-id="e448e-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="e448e-118">حدد **التالي** لإعداد موصل LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="e448e-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e448e-119">تكوين الموصل</span><span class="sxs-lookup"><span data-stu-id="e448e-119">Configure the connector</span></span>

1. <span data-ttu-id="e448e-120">في الحقل **اختيار معرف المفتاح**، حدد **البريد الإلكتروني** أو **الاسم والعنوان** أو **الهاتف** لإرساله إلى LiveRamp لحل الهوية.</span><span class="sxs-lookup"><span data-stu-id="e448e-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="e448e-121">قم بتعيين السمات المناظرة من كيان العميل الموحد لمعرف المفتاح المحدد.</span><span class="sxs-lookup"><span data-stu-id="e448e-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="e448e-122">حدد **إضافة سمة** لتعيين سمات إضافية لإرسالها إلى LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="e448e-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="e448e-123">من المحتمل أن يؤدي إرسال المزيد من سمات معرف المفتاح إلى LiveRamp للحصول على معدل تطابق أعلى.</span><span class="sxs-lookup"><span data-stu-id="e448e-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="e448e-124">حدد الشرائح التي تريد تصديرها إلى LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="e448e-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="e448e-125">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="e448e-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="e448e-126">![موصل LiveRamp مع تعيين السمات](media/export-liveramp-segments.png "موصل LiveRamp مع تعيين السمات")</span><span class="sxs-lookup"><span data-stu-id="e448e-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e448e-127">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="e448e-127">Export the data</span></span>

<span data-ttu-id="e448e-128">سيبدأ التصدير بعد قليل إذا تم استكمال جميع المتطلبات الأساسية للتصدير.</span><span class="sxs-lookup"><span data-stu-id="e448e-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="e448e-129">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e448e-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="e448e-130">بعد اكتمال التصدير بنجاح، يمكنك تسجيل الدخول إلى LiveRamp Onboarding لتنشيط البيانات وتوزيعها.</span><span class="sxs-lookup"><span data-stu-id="e448e-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e448e-131">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="e448e-131">Data privacy and compliance</span></span>

<span data-ttu-id="e448e-132">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Liveramp، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="e448e-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e448e-133">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Liveramp بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="e448e-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e448e-134">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e448e-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e448e-135">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="e448e-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]