---
title: تصدير بيانات Customer Insights إلى مضيفي SFTP
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى موقع SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760403"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="06778-103">تصدير قوائم الشرائح والبيانات الأخرى إلى SFTP (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="06778-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="06778-104">استخدم بيانات العميل في تطبيقات طرف ثالث من خلال تصديرها إلى موقع بروتوكول نقل الملفات الآمنة (SFTP).</span><span class="sxs-lookup"><span data-stu-id="06778-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="06778-105">المتطلبات الأساسية للاتصال</span><span class="sxs-lookup"><span data-stu-id="06778-105">Prerequisites for connection</span></span>

- <span data-ttu-id="06778-106">توفر مضيف SFTP وبيانات الاعتماد المقابلة.</span><span class="sxs-lookup"><span data-stu-id="06778-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="06778-107">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="06778-107">Known limitations</span></span>

- <span data-ttu-id="06778-108">يعتمد وقت تشغيل أي تصدير على أداء النظام.</span><span class="sxs-lookup"><span data-stu-id="06778-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="06778-109">نوصي بمركزين لوحدة المعالجة المركزية وذاكرة بسعة غيغابايت واحد كحدٍ أدنى لتكوين الخادم.</span><span class="sxs-lookup"><span data-stu-id="06778-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="06778-110">قد يستغرق تصدير الكيانات مع 100 مليون من ملفات تعريف العملاء 90 دقيقة عند استخدام الحد الأدنى من التكوين الموصى به من مركزين لوحدة المعالجة المركزية وذاكرة بسعة غيغابايت واحد.</span><span class="sxs-lookup"><span data-stu-id="06778-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="06778-111">إعداد اتصال بـ SFTP</span><span class="sxs-lookup"><span data-stu-id="06778-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="06778-112">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="06778-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="06778-113">حدد **إضافة اتصال** واختر **SFTP** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="06778-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="06778-114">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="06778-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="06778-115">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="06778-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="06778-116">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="06778-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="06778-117">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="06778-117">Choose who can use this connection.</span></span> <span data-ttu-id="06778-118">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="06778-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="06778-119">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="06778-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="06778-120">أدخل **اسم المستخدم** و **كلمة المرور** و **اسم المضيف** و **مجلد التصدير** لحساب SFTP.</span><span class="sxs-lookup"><span data-stu-id="06778-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="06778-121">حدد **تحقق** لاختبار الاتصال.</span><span class="sxs-lookup"><span data-stu-id="06778-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="06778-122">اختر ما إذا كنت ترغب في تصدير بياناتك **المضغوطة** أو **المفكوك ضغطها** و **محدد المجال** للملفات المصدرة.</span><span class="sxs-lookup"><span data-stu-id="06778-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="06778-123">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="06778-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="06778-124">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="06778-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="06778-125">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="06778-125">Configure an export</span></span>

<span data-ttu-id="06778-126">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="06778-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="06778-127">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="06778-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="06778-128">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="06778-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="06778-129">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="06778-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="06778-130">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم SFTP.</span><span class="sxs-lookup"><span data-stu-id="06778-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="06778-131">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="06778-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="06778-132">حدد الكيانات، على سبيل المثال الشرائح، التي ترغب في تصديرها.</span><span class="sxs-lookup"><span data-stu-id="06778-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="06778-133">سيتم تقسيم كل كيان محدد إلى ما يصل إلى خمسة ملفات إخراج عند تصديرها.</span><span class="sxs-lookup"><span data-stu-id="06778-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="06778-134">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="06778-134">Select **Save**.</span></span>

<span data-ttu-id="06778-135">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="06778-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="06778-136">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="06778-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="06778-137">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="06778-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="06778-138">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="06778-138">Data privacy and compliance</span></span>

<span data-ttu-id="06778-139">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات عبر SFTP Technologies، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="06778-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="06778-140">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام وجهة التصدير بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="06778-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="06778-141">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="06778-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="06778-142">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="06778-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
