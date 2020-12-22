---
title: موصل Power Automate  | Microsoft Docs
description: إنشاء عمليات سير العمل في Microsoft Power Automate من Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4404895"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="45234-103">موصل Power Automate (معاينة)</span><span class="sxs-lookup"><span data-stu-id="45234-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="45234-104">قم بتشغيل أحداث معينة لكي تحدث تلقائيًا عند تغيير بياناتك وأدر مزيدًا من عمليات سير المهام المعقدة مباشرةً في [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="45234-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="45234-105">Power Automate المشغلات</span><span class="sxs-lookup"><span data-stu-id="45234-105">Power Automate triggers</span></span>

<span data-ttu-id="45234-106">يمكنك استخدام العديد من المشغلات التي تتيح لك إنشاء سير عمل لتنفيذ المهام المتكررة تلقائيا، مثل الإعلامات أو الإجراءات الأكثر تقدمًا.</span><span class="sxs-lookup"><span data-stu-id="45234-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="45234-107">التشغيل عند فشل تحديث مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="45234-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="45234-108">التشغيل عند نجاح تحديث مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="45234-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="45234-109">التشغيل عند تخطي الحد في شريحة.</span><span class="sxs-lookup"><span data-stu-id="45234-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="45234-110">يقتصر التشغيل على تجاوز الحد.</span><span class="sxs-lookup"><span data-stu-id="45234-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="45234-111">التشغيل عند تخطي الحد في إجراء أعمال.</span><span class="sxs-lookup"><span data-stu-id="45234-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="45234-112">يقتصر التشغيل على تجاوز الحد.</span><span class="sxs-lookup"><span data-stu-id="45234-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="45234-113">التشغيل عند اكتمال عملية تحديث كاملة (مصادر البيانات والشرائح والمقاييس,...).</span><span class="sxs-lookup"><span data-stu-id="45234-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="45234-114">تشغيل عند اكتمال تحديث عملية التوحيد (التعيين، المطابقة، الدمج).</span><span class="sxs-lookup"><span data-stu-id="45234-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="45234-115">[تكوين المشغلات في Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="45234-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="45234-116">إجراءات Power Automate</span><span class="sxs-lookup"><span data-stu-id="45234-116">Power Automate actions</span></span>
<span data-ttu-id="45234-117">يوفر موصل Power Automate إجراءات أخرى بخلاف المشغلات المتوفرة.</span><span class="sxs-lookup"><span data-stu-id="45234-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="45234-118">لمزيد من المعلومات، راجع [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="45234-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="45234-119">إنشاء سير مهام Power Automate في رؤى الجمهور</span><span class="sxs-lookup"><span data-stu-id="45234-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="45234-120">في رؤى الجمهور، انتقل إلى **المسؤول‏‎** > **النظام**.</span><span class="sxs-lookup"><span data-stu-id="45234-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="45234-121">في الصفحة **النظام**، حدد علامة التبويب **الحالة**.</span><span class="sxs-lookup"><span data-stu-id="45234-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="45234-122">في القسم **مصادر البيانات**، قم بتحديد **عمليات سير المهام** وحدد **إنشاء عملية سير المهام** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="45234-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="45234-123">موصل ![Power Automate يوضح إنشاء إجراء سير العمل](media/power-automate-connector-create-flow.png "موصل Power Automate يوضح إنشاء إجراء سير العمل")</span><span class="sxs-lookup"><span data-stu-id="45234-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="45234-124">في Power Automate، حدد أحد المشغلات المتوفرة لإنشاء عملية سير المهام المفضلة لديك.</span><span class="sxs-lookup"><span data-stu-id="45234-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="45234-125">إذا كنت تقوم بإنشاء التدفق الأول، ستحتاج المصادقة مع الموصل Power Automate أولاً.</span><span class="sxs-lookup"><span data-stu-id="45234-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
