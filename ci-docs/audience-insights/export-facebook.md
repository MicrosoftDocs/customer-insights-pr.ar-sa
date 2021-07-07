---
title: تصدير بيانات Customer Insights إلى Facebook Ads Manager
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى مدير إعلانات Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305094"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="ac9b8-103">تصدير قائمة الشرائح إلى مدير إعلانات Facebook (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="ac9b8-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="ac9b8-104">يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة إلى مدير الإعلانات في Facebook لإنشاء حملات على Facebook وInstagram.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ac9b8-105">المتطلبات الأساسية للاتصال</span><span class="sxs-lookup"><span data-stu-id="ac9b8-105">Prerequisites for connection</span></span>

- <span data-ttu-id="ac9b8-106">يجب أن يكون لديك [**حساب إعلانات Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) الذي يشمل [**حساب أعمال Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="ac9b8-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="ac9b8-107">يلزم أن تكون المسؤول في [**حساب إعلانات Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="ac9b8-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ac9b8-108">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="ac9b8-108">Known limitations</span></span>

- <span data-ttu-id="ac9b8-109">ما يصل إلى 10 مليون ملف تعريف عميل لكل عملية تصدير إلى مدير إعلانات Facebook.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="ac9b8-110">يقتصر التصدير إلى مدير إعلانات Facebook على الشرائح.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="ac9b8-111">إنشاء أو تحديث الجمهور المخصص في Facebook من نوع *قائمة العملاء* فقط.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="ac9b8-112">تستغرق عملية تصدير الشرائح التي تتضمن 10 ملايين ملف تعريف بشكل إجمالي حتى 90 دقيقة.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="ac9b8-113">إعداد الاتصال بمدير إعلانات Facebook</span><span class="sxs-lookup"><span data-stu-id="ac9b8-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="ac9b8-114">قبل أن يستطيع المستخدمون إنشاء عملية تصدير، المسؤول على المستخدمين تكوين الاتصال بالخدمة والسماح للمساهمين باستخدام الاتصال.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="ac9b8-115">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ac9b8-116">حدد **إضافة اتصال** واختر **مدير إعلانات Facebook** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="ac9b8-117">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ac9b8-118">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ac9b8-119">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ac9b8-120">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-120">Choose who can use this connection.</span></span> <span data-ttu-id="ac9b8-121">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ac9b8-122">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ac9b8-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ac9b8-123">مصادقة باستخدام إعلانات Facebook:</span><span class="sxs-lookup"><span data-stu-id="ac9b8-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="ac9b8-124">حدد **الاستمرار في Facebook** لتسجيل الدخول إلى حساب إعلانات Facebook الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="ac9b8-125">السماح بإذن **ads_management** مع المصادقة مع Facebook.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="ac9b8-126">حدد **حساب الإعلانات في Facebook** الذي تريد استخدامه.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="ac9b8-127">حدد **الجمهور المخصص الحالي** من القائمة المنسدلة أو قم بإنشاء **جمهور مخصص جديد**.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="ac9b8-128">لمزيد من المعلومات، راجع [**شرائح الجمهور في مدير الإعلانات في Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="ac9b8-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="ac9b8-129">يمكنك فقط إنشاء أو تحديث الجماهير المخصصة في Facebook من نوع *قائمة العملاء* مع هذا التصدير.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="ac9b8-130">وفي بعض الحالات، تشاهد مجموعات مخصصة من أنواع مختلفة في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="ac9b8-131">يؤدي تحديد نوع مختلف عن *قائمة العملاء* إلى فشل التصدير.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="ac9b8-132">راجع **خصوصية البيانات والامتثال** وحدد **أوافق**.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="ac9b8-133">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ac9b8-134">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="ac9b8-134">Configure an export</span></span>

<span data-ttu-id="ac9b8-135">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ac9b8-136">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ac9b8-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ac9b8-137">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ac9b8-138">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="ac9b8-139">في **الاتصال للتصدير** اختر اتصالاً من قسم **مدير إعلانات Facebook**.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="ac9b8-140">إذا لم تشاهد اسم المقطع هذا، فلا توجد اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="ac9b8-141">في الحقل **اختر معرف المفتاح**، وحدد **البريد الإلكتروني** أو **الاسم والعنوان** أو **الهاتف** لإرساله إلى مدير الإعلانات في Facebook.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="ac9b8-142">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="ac9b8-143">قم بتعيين السمات المناظرة من كيان العميل الموحد لمعرف المفتاح المحدد.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="ac9b8-144">تحدث أفضل فرص حدوث تطابق إذا حددت **البريد الإلكتروني** كمعرف مفتاح.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="ac9b8-145">قد تؤدي إضافة معرفات إضافية إلى تحسين التطابق.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="ac9b8-146">حدد **إضافة سمة** لتعيين مزيد من السمات لإرسالها إلى مدير إعلانات Facebook.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="ac9b8-147">يتم تعيين السمات من مدير الإعلانات في Facebook إلى الأسماء المألوفة التالية للمستخدم: **FN** = **الاسم الأول**، **LN** = **اسم العائلة**, **FI** = **الحرف الأول للاسم**، **PHONE** = **الهاتف**، **GEN** = **الجنس**، **DOB** = **تاريخ الميلاد**، **ST** = **الولاية**، **CT** = **المدينة**، **ZIP** = **الرمز البريدي**، **COUNTRY** = **البلد/المنطقة**</span><span class="sxs-lookup"><span data-stu-id="ac9b8-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="ac9b8-148">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="ac9b8-149">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-149">Select **Save**.</span></span>

<span data-ttu-id="ac9b8-150">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ac9b8-151">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ac9b8-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="ac9b8-152">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ac9b8-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ac9b8-153">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="ac9b8-153">Data privacy and compliance</span></span>

<span data-ttu-id="ac9b8-154">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى  Facebook Ads Manager، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ac9b8-155">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Facebook Ads بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ac9b8-156">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ac9b8-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ac9b8-157">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="ac9b8-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
