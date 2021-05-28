---
title: موصل Power Automate  | Microsoft Docs
description: إنشاء عمليات سير المهام في Microsoft Power Automate من Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976072"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="b3e1d-103">موصل Power Automate (معاينة)</span><span class="sxs-lookup"><span data-stu-id="b3e1d-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="b3e1d-104">قم بتشغيل أحداث معينة لكي تحدث تلقائيًا عند تغيير بياناتك وأدر مزيدًا من عمليات سير المهام المعقدة مباشرةً في [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="b3e1d-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="b3e1d-105">Power Automate المشغلات</span><span class="sxs-lookup"><span data-stu-id="b3e1d-105">Power Automate triggers</span></span>

<span data-ttu-id="b3e1d-106">استخدم المشغلات لإنشاء عمليات سير مهام في السحابة وأتمتة المهام المتكررة، مثل الإعلامات أو إجراءات أكثر تقدمًا.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="b3e1d-107">التشغيل عند فشل تحديث مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="b3e1d-108">التشغيل عند نجاح تحديث مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="b3e1d-109">التشغيل عند تخطي الحد في شريحة.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="b3e1d-110">يقتصر التشغيل على تجاوز الحد.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="b3e1d-111">التشغيل عند تخطي الحد في إجراء أعمال.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="b3e1d-112">يتم دعم فقط مقاييس العمل بدون بُعد.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="b3e1d-113">يقتصر التشغيل على تجاوز الحد.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="b3e1d-114">التشغيل عند اكتمال عملية تحديث كاملة (مصادر البيانات والشرائح والمقاييس,...).</span><span class="sxs-lookup"><span data-stu-id="b3e1d-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="b3e1d-115">تشغيل عند اكتمال تحديث عملية التوحيد (التعيين، المطابقة، الدمج).</span><span class="sxs-lookup"><span data-stu-id="b3e1d-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="b3e1d-116">[تكوين المشغلات في Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="b3e1d-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="b3e1d-117">إجراءات Power Automate</span><span class="sxs-lookup"><span data-stu-id="b3e1d-117">Power Automate actions</span></span>
<span data-ttu-id="b3e1d-118">يوفر موصل Power Automate إجراءات أخرى بخلاف المشغلات المتوفرة.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="b3e1d-119">لمزيد من المعلومات، راجع [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="b3e1d-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="b3e1d-120">إنشاء سير مهام Power Automate</span><span class="sxs-lookup"><span data-stu-id="b3e1d-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="b3e1d-121">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b3e1d-122">على الإطار المتجانب **Power Automate**، حدد **إعداد‏‎**.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="b3e1d-123">يفتح موصل Customer Insights (إصدار أولي) في Power Automate.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="b3e1d-124">**سجل دخولك إلى** to Power Automate.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="b3e1d-125">اختر أحد المشغلات المتوفرة وأضف المزيد من الخطوات إلى سير المهام الجديد.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="b3e1d-126">لمزيد من المعلومات، راجع [إنشاء سير مهام في السحابة في Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="b3e1d-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="b3e1d-127">أمثلة حول كيفية استخدام سير المهام:</span><span class="sxs-lookup"><span data-stu-id="b3e1d-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="b3e1d-128">نشر رسالة إلى قناة Microsoft Teams في حالة فشل تحديث مصدر بيانات.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="b3e1d-129">إرسال بريد إلكتروني إلى مالكي البيانات عند تجاوز حد ما على الشريحة.</span><span class="sxs-lookup"><span data-stu-id="b3e1d-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
