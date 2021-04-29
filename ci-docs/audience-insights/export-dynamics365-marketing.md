---
title: تصدير بيانات Customer Insights إلى Dynamics 365 Marketing
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759593"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="ff837-103">استخدام الشرائح في Dynamics 365 Marketing (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="ff837-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ff837-104">استخدم [الشرائح](segments.md) لإنشاء حملات وتحسين مجموعات محددة من العملاء باستخدام Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="ff837-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="ff837-105">لمزيد من المعلومات ، راجع [استخدام الشرائح من Dynamics 365 Customer Insights مع Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="ff837-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="ff837-106">المتطلبات الأساسية لاتصال</span><span class="sxs-lookup"><span data-stu-id="ff837-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="ff837-107">يجب أن تكون سجلات جهات الاتصال موجودة في Dynamics 365 Marketing قبل تصدير شريحة من Customer Insights إلى Marketing.</span><span class="sxs-lookup"><span data-stu-id="ff837-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="ff837-108">اقرأ المزيد حول كيفية استيعاب جهات الاتصال في [Dynamics 365 Marketing باستخدام Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ff837-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="ff837-109">لن يؤدي تصدير الشرائح من رؤى الجمهور إلى Marketing إلى إنشاء سجلات جهات اتصال جديدة في مثيلات Marketing.</span><span class="sxs-lookup"><span data-stu-id="ff837-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="ff837-110">يجب استيعاب سجلات جهات الاتصال من Marketing في رؤى الجمهور واستخدامها كمصدر بيانات.</span><span class="sxs-lookup"><span data-stu-id="ff837-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="ff837-111">كما يلزم تضمينها في كيان العميل الموحد من أجل تعيين معرفات العملاء إلى معرفات جهات الاتصال قبل أن يصبح تصدير الشرائح ممكنًا.</span><span class="sxs-lookup"><span data-stu-id="ff837-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="ff837-112">إعداد الاتصال بـ Marketing</span><span class="sxs-lookup"><span data-stu-id="ff837-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="ff837-113">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="ff837-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ff837-114">حدد **إضافة اتصال** واختر **Dynamics 365 Marketing** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="ff837-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="ff837-115">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="ff837-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ff837-116">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="ff837-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ff837-117">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="ff837-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ff837-118">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="ff837-118">Choose who can use this connection.</span></span> <span data-ttu-id="ff837-119">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="ff837-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ff837-120">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ff837-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ff837-121">أدخل عنوان URL لتطبيق Marketing‎ في حقل **عنوان الخادم**.</span><span class="sxs-lookup"><span data-stu-id="ff837-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="ff837-122">في القسم **حساب مسؤول الخادم**، حدد **تسجيل الدخول** واختر حساب Dynamics 365 Marketing‎.</span><span class="sxs-lookup"><span data-stu-id="ff837-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="ff837-123">عيّن حقل معرف العميل إلى معرف جهة الاتصال في Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ff837-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="ff837-124">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="ff837-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="ff837-125">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="ff837-125">Configure an export</span></span>

<span data-ttu-id="ff837-126">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="ff837-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ff837-127">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ff837-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ff837-128">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="ff837-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ff837-129">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="ff837-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ff837-130">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="ff837-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="ff837-131">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="ff837-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ff837-132">اختر شريحة أو أكثر.</span><span class="sxs-lookup"><span data-stu-id="ff837-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="ff837-133">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="ff837-133">Select **Save**.</span></span>

<span data-ttu-id="ff837-134">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="ff837-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ff837-135">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ff837-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ff837-136">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ff837-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
