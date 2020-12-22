---
title: تصدير بيانات Customer Insights إلى Dynamics 365 Marketing
description: تعرف على كيفية تكوين الاتصال بتطبيق Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643757"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="141bb-103">موصل لتطبيق Dynamics 365 Marketing (معاينة)</span><span class="sxs-lookup"><span data-stu-id="141bb-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="141bb-104">استخدم [الشرائح](segments.md) لإنشاء حملات وتحسين مجموعات محددة من العملاء باستخدام Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="141bb-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="141bb-105">لمزيد من المعلومات ، راجع [استخدام الشرائح من Dynamics 365 Customer Insights مع Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="141bb-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="141bb-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="141bb-106">Prerequisite</span></span>

<span data-ttu-id="141bb-107">سجلات جهات الاتصال [من Dynamics 365 Marketing التي تم استيعابها باستخدام Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="141bb-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="141bb-108">تكوين موصل Marketing</span><span class="sxs-lookup"><span data-stu-id="141bb-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="141bb-109">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.</span><span class="sxs-lookup"><span data-stu-id="141bb-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="141bb-110">ضمن **Dynamics 365 Marketing‎**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="141bb-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="141bb-111">في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.</span><span class="sxs-lookup"><span data-stu-id="141bb-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="141bb-112">أدخل عنوان URL لتطبيق Marketing‎ في حقل **عنوان الخادم**.</span><span class="sxs-lookup"><span data-stu-id="141bb-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="141bb-113">في القسم **حساب مسؤول الخادم**، حدد **تسجيل الدخول** واختر حساب Dynamics 365 Marketing‎.</span><span class="sxs-lookup"><span data-stu-id="141bb-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="141bb-114">عيّن حقل معرف العميل إلى معرف جهة الاتصال في Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="141bb-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="141bb-115">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="141bb-115">Select **Next**.</span></span>

1. <span data-ttu-id="141bb-116">اختر شريحة أو أكثر.</span><span class="sxs-lookup"><span data-stu-id="141bb-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="141bb-117">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="141bb-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="141bb-118">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="141bb-118">Export the data</span></span>

<span data-ttu-id="141bb-119">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="141bb-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="141bb-120">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="141bb-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
