---
title: تصدير بيانات Customer Insights إلى Dynamics 365 Sales
description: تعرف على كيفية تكوين الاتصال بتطبيق Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643802"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="36a4b-103">موصل لتطبيق Dynamics 365 Sales (معاينة)</span><span class="sxs-lookup"><span data-stu-id="36a4b-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="36a4b-104">استخدم بيانات العميل الخاصة بك لإنشاء قوائم تسويق ومتابعة عمليات سير العمل وإرسال العروض الترويجية باستخدام Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="36a4b-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="36a4b-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="36a4b-105">Prerequisite</span></span>

<span data-ttu-id="36a4b-106">سجلات جهات الاتصال [من Dynamics 365 Sales التي تم استيعابها باستخدام Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="36a4b-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="36a4b-107">تكوين موصل Sales</span><span class="sxs-lookup"><span data-stu-id="36a4b-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="36a4b-108">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.</span><span class="sxs-lookup"><span data-stu-id="36a4b-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="36a4b-109">ضمن **Dynamics 365 Sales**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="36a4b-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="36a4b-110">في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.</span><span class="sxs-lookup"><span data-stu-id="36a4b-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="36a4b-111">أدخل عنوان URL لتطبيق Sales في حقل **عنوان الخادم**.</span><span class="sxs-lookup"><span data-stu-id="36a4b-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="36a4b-112">في القسم **حساب مسؤول الخادم**، حدد **تسجيل الدخول** واختر حساب Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="36a4b-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="36a4b-113">عيّن حقل معرف العميل إلى معرف جهة الاتصال في Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="36a4b-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="36a4b-114">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="36a4b-114">Select **Next**.</span></span>

1. <span data-ttu-id="36a4b-115">اختر شريحة أو أكثر.</span><span class="sxs-lookup"><span data-stu-id="36a4b-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="36a4b-116">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="36a4b-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="36a4b-117">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="36a4b-117">Export the data</span></span>

<span data-ttu-id="36a4b-118">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="36a4b-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="36a4b-119">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="36a4b-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
