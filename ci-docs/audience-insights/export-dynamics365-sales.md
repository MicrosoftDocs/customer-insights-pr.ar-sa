---
title: تصدير بيانات Customer Insights إلى Dynamics 365 Sales
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976138"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="9b836-103">استخدام الشرائح في Dynamics 365 Sales (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="9b836-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9b836-104">استخدم بيانات العميل الخاصة بك لإنشاء قوائم تسويق ومتابعة عمليات سير العمل وإرسال العروض الترويجية باستخدام Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9b836-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="9b836-105">المتطلبات الأساسية للاتصال</span><span class="sxs-lookup"><span data-stu-id="9b836-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="9b836-106">يجب أن تكون سجلات جهات الاتصال موجودة في Dynamics 365 Sales قبل تصدير شريحة من Customer Insights إلى Sales.</span><span class="sxs-lookup"><span data-stu-id="9b836-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="9b836-107">اقرأ المزيد حول كيفية استيعاب جهات الاتصال في [Dynamics 365 Sales باستخدام Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="9b836-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="9b836-108">لن يؤدي تصدير الشرائح من رؤى الجمهور إلى Sales إلى إنشاء سجلات جهات اتصال جديدة في مثيلات Sales.</span><span class="sxs-lookup"><span data-stu-id="9b836-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="9b836-109">يجب استيعاب سجلات جهات الاتصال من Sales في رؤى الجمهور واستخدامها كمصدر بيانات.</span><span class="sxs-lookup"><span data-stu-id="9b836-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="9b836-110">كما يلزم تضمينها في كيان العميل الموحد من أجل تعيين معرفات العملاء إلى معرفات جهات الاتصال قبل أن يصبح تصدير الشرائح ممكنًا.</span><span class="sxs-lookup"><span data-stu-id="9b836-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="9b836-111">إعداد الاتصال بـ Sales</span><span class="sxs-lookup"><span data-stu-id="9b836-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="9b836-112">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="9b836-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9b836-113">حدد **إضافة اتصال** واختر **Dynamics 365 Sales** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="9b836-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="9b836-114">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="9b836-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9b836-115">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="9b836-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9b836-116">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="9b836-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9b836-117">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="9b836-117">Choose who can use this connection.</span></span> <span data-ttu-id="9b836-118">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="9b836-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9b836-119">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9b836-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="9b836-120">أدخل عنوان URL لتطبيق Sales في حقل **عنوان الخادم**.</span><span class="sxs-lookup"><span data-stu-id="9b836-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="9b836-121">في القسم **حساب مسؤول الخادم**، حدد **تسجيل الدخول** واختر حساب Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9b836-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="9b836-122">عيّن حقل معرف العميل إلى معرف جهة الاتصال في Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9b836-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="9b836-123">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="9b836-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="9b836-124">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="9b836-124">Configure an export</span></span>

<span data-ttu-id="9b836-125">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="9b836-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9b836-126">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9b836-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9b836-127">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="9b836-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9b836-128">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="9b836-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9b836-129">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="9b836-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="9b836-130">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="9b836-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="9b836-131">اختر شريحة أو أكثر.</span><span class="sxs-lookup"><span data-stu-id="9b836-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="9b836-132">حدد **حفظ**</span><span class="sxs-lookup"><span data-stu-id="9b836-132">Select **Save**</span></span>

<span data-ttu-id="9b836-133">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="9b836-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9b836-134">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9b836-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9b836-135">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9b836-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
