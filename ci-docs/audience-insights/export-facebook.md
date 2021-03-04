---
title: تصدير بيانات Customer Insights إلى Facebook Ads Manager
description: تعرف على كيفية تكوين الاتصال مع مدير الإعلانات في Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269958"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="317f2-103">موصل لمدير الإعلانات في Facebook (معاينة)</span><span class="sxs-lookup"><span data-stu-id="317f2-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="317f2-104">يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة إلى مدير الإعلانات في Facebook لإنشاء حملات على Facebook وInstagram.</span><span class="sxs-lookup"><span data-stu-id="317f2-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="317f2-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="317f2-105">Prerequisites</span></span>

- <span data-ttu-id="317f2-106">يجب أن يكون لديك [**حساب Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) يتضمن [**حساب عمل في Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="317f2-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="317f2-107">يجب أن تكون مسؤولاً على [**حساب Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="317f2-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="317f2-108">الاتصال بمدير الإعلانات في Facebook</span><span class="sxs-lookup"><span data-stu-id="317f2-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="317f2-109">انتقل إلى **المسؤول** > **وجهات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="317f2-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="317f2-110">ضمن **مدير الإعلانات في Facebook**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="317f2-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="317f2-111">في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.</span><span class="sxs-lookup"><span data-stu-id="317f2-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="317f2-112">حدد **المتابعة مع Facebook** لتسجيل الدخول إلى حساب الإعلانات في Facebook.</span><span class="sxs-lookup"><span data-stu-id="317f2-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="317f2-113">السماح بإذن **ads_management** مع المصادقة مع Facebook.</span><span class="sxs-lookup"><span data-stu-id="317f2-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="317f2-114">حدد **حساب الإعلانات في Facebook** الذي تريد استخدامه.</span><span class="sxs-lookup"><span data-stu-id="317f2-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="317f2-115">حدد **جمهور مخصص موجود** من القائمة المنسدلة أو قم بإنشاء **جمهور مخصص من**.</span><span class="sxs-lookup"><span data-stu-id="317f2-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="317f2-116">لمزيد من المعلومات، راجع [**شرائح الجمهور في مدير الإعلانات في Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="317f2-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="317f2-117">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="317f2-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="317f2-118">حدد **التالي** لتكوين التصدير.</span><span class="sxs-lookup"><span data-stu-id="317f2-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="317f2-119">تكوين الموصل</span><span class="sxs-lookup"><span data-stu-id="317f2-119">Configure the connector</span></span>

1. <span data-ttu-id="317f2-120">في الحقل **اختر معرف المفتاح**، وحدد **البريد الإلكتروني** أو **الاسم والعنوان** أو **الهاتف** لإرساله إلى مدير الإعلانات في Facebook.</span><span class="sxs-lookup"><span data-stu-id="317f2-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="317f2-121">قم بتعيين السمات المناظرة من كيان العميل الموحد لمعرف المفتاح المحدد.</span><span class="sxs-lookup"><span data-stu-id="317f2-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="317f2-122">[تلميح] تحدث أفضل فرص حدوث تطابق إذا حددت **البريد الإلكتروني** كمعرف مفتاح.</span><span class="sxs-lookup"><span data-stu-id="317f2-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="317f2-123">قد تؤدي إضافة معرفات إضافية إلى تحسين التطابق.</span><span class="sxs-lookup"><span data-stu-id="317f2-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="317f2-124">حدد **إضافة سمة** لتعيين سمات إضافية لإرسالها إلى مدير الإعلانات في Facebook.</span><span class="sxs-lookup"><span data-stu-id="317f2-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="317f2-125">يتم تعيين السمات من مدير الإعلانات في Facebook إلى الأسماء المألوفة التالية للمستخدم: **FN** = **الاسم الأول**، **LN** = **اسم العائلة**, **FI** = **الحرف الأول للاسم**، **PHONE** = **الهاتف**، **GEN** = **الجنس**، **DOB** = **تاريخ الميلاد**، **ST** = **الولاية**، **CT** = **المدينة**، **ZIP** = **الرمز البريدي**، **COUNTRY** = **البلد / المنطقة**</span><span class="sxs-lookup"><span data-stu-id="317f2-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="317f2-126">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="317f2-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="317f2-127">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="317f2-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="317f2-128">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="317f2-128">Export the data</span></span>

<span data-ttu-id="317f2-129">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="317f2-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="317f2-130">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="317f2-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="317f2-131">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="317f2-131">Known limitations</span></span>

- <span data-ttu-id="317f2-132">ما يصل إلى 10 مليون ملف تعريف عميل لكل عملية تصدير إلى مدير إعلانات Facebook</span><span class="sxs-lookup"><span data-stu-id="317f2-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="317f2-133">يقتصر التصدير إلى مدير إعلانات Facebook على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="317f2-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="317f2-134">تستغرق عملية تصدير الشرائح التي تتضمن 10 ملايين ملف تعريف بشكل إجمالي حتى 90 دقيقة.</span><span class="sxs-lookup"><span data-stu-id="317f2-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="317f2-135">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="317f2-135">Data privacy and compliance</span></span>

<span data-ttu-id="317f2-136">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى  Facebook Ads Manager، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="317f2-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="317f2-137">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Facebook Ads بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="317f2-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="317f2-138">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="317f2-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="317f2-139">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="317f2-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]