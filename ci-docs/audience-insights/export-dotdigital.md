---
title: تصدير بيانات Customer Insights إلى DotDigital
description: اعرف كيفية تكوين الاتصال بـ DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598000"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="f40d3-103">موصل DotDigital (معاينة)</span><span class="sxs-lookup"><span data-stu-id="f40d3-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="f40d3-104">يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة إلى دفاتر عناوين DotDigital واستخدامها للحملات والتسويق بواسطة البريد الإلكتروني ولإنشاء شرائح العملاء بواسطة DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f40d3-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f40d3-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="f40d3-105">Prerequisites</span></span>

-   <span data-ttu-id="f40d3-106">لديك [حساب DotDigital](https://dotdigital.com/) وبيانات اعتماد مسؤول مطابقة.</span><span class="sxs-lookup"><span data-stu-id="f40d3-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f40d3-107">هناك دفاتر عناوين موجودة في DotDigital والمعرفات المناظرة.</span><span class="sxs-lookup"><span data-stu-id="f40d3-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="f40d3-108">يمكن العثور على المعرف في URL عندما تقوم بتحديد وفتح دفتر عناوين.</span><span class="sxs-lookup"><span data-stu-id="f40d3-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="f40d3-109">لمزيد من المعلومات، راجع [دفاتر عناوين DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="f40d3-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="f40d3-110">لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="f40d3-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="f40d3-111">تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="f40d3-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="f40d3-112">الاتصال بـ DotDigital</span><span class="sxs-lookup"><span data-stu-id="f40d3-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="f40d3-113">انتقل إلى **المسؤول** > **وجهات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="f40d3-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f40d3-114">أسفل **DotDigital**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="f40d3-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="f40d3-115">في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.</span><span class="sxs-lookup"><span data-stu-id="f40d3-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="جزء التكوين لتصدير DotDigital.":::

1. <span data-ttu-id="f40d3-117">أدخل **اسم المستخدم وكلمة المرور في DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="f40d3-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="f40d3-118">أدخل **[معرف دفتر عناوين DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="f40d3-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="f40d3-119">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="f40d3-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f40d3-120">حدد **اتصال** لتهيئة الاتصال بـ DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f40d3-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="f40d3-121">حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f40d3-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f40d3-122">حدد **التالي** لتكوين التصدير.</span><span class="sxs-lookup"><span data-stu-id="f40d3-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f40d3-123">تكوين الموصل</span><span class="sxs-lookup"><span data-stu-id="f40d3-123">Configure the connector</span></span>

1. <span data-ttu-id="f40d3-124">في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل.</span><span class="sxs-lookup"><span data-stu-id="f40d3-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f40d3-125">كرر نفس الخطوات للحقول الاختيارية الأخرى مثل **الاسم الأول** و **اسم العائلة** و **الاسم الكامل** و **الجنس** و **الرمز البريدي**.</span><span class="sxs-lookup"><span data-stu-id="f40d3-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="f40d3-126">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="f40d3-126">Select the segments you want to export.</span></span> <span data-ttu-id="f40d3-127">يمكنك تصدير ما يصل إلى مليون من ملفات تعريف العملاء إلى DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f40d3-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="f40d3-128">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="f40d3-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f40d3-129">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="f40d3-129">Export the data</span></span>

<span data-ttu-id="f40d3-130">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f40d3-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f40d3-131">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f40d3-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f40d3-132">في DotDigital، يمكنك الآن العثور على الشرائح في [دفاتر عناوين DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="f40d3-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f40d3-133">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="f40d3-133">Known limitations</span></span>

- <span data-ttu-id="f40d3-134">حتى مليون من ملفات التعريف لكل تصدير إلى DotDigital.</span><span class="sxs-lookup"><span data-stu-id="f40d3-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="f40d3-135">يقتصر التصدير إلى DotDigital على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="f40d3-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="f40d3-136">قد تستغرق عملية تصدير الشرائح التي تتضمن ما يصل إلى مليون ملف تعريف بشكل إجمالي ثلاث ساعات كحدٍ أقصى نتيجة للقيود من جانب الموفر.</span><span class="sxs-lookup"><span data-stu-id="f40d3-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="f40d3-137">يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى DotDigital على العقد مع DotDigital، وهذا العدد مقيد بالعقد.</span><span class="sxs-lookup"><span data-stu-id="f40d3-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f40d3-138">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="f40d3-138">Data privacy and compliance</span></span>

<span data-ttu-id="f40d3-139">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى DotDigital، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="f40d3-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f40d3-140">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام DotDigital بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="f40d3-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f40d3-141">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f40d3-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f40d3-142">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="f40d3-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]