---
title: تصدير بيانات Customer Insights إلى Dynamics 365 Marketing
description: تعرف على كيفية تكوين الاتصال بتطبيق Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597587"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="a5188-103">موصل لتطبيق Dynamics 365 Marketing (معاينة)</span><span class="sxs-lookup"><span data-stu-id="a5188-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a5188-104">استخدم [الشرائح](segments.md) لإنشاء حملات وتحسين مجموعات محددة من العملاء باستخدام Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a5188-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="a5188-105">لمزيد من المعلومات ، راجع [استخدام الشرائح من Dynamics 365 Customer Insights مع Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="a5188-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a5188-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="a5188-106">Prerequisite</span></span>

- <span data-ttu-id="a5188-107">يجب أن تكون سجلات جهات الاتصال موجودة في Dynamics 365 Marketing قبل تصدير شريحة من Customer Insights إلى Marketing.</span><span class="sxs-lookup"><span data-stu-id="a5188-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="a5188-108">اقرأ المزيد حول كيفية استيعاب جهات الاتصال في [Dynamics 365 Marketing باستخدام Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a5188-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a5188-109">لن يؤدي تصدير الشرائح من رؤى الجمهور إلى Marketing إلى إنشاء سجلات جهات اتصال جديدة في مثيلات Marketing.</span><span class="sxs-lookup"><span data-stu-id="a5188-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="a5188-110">يجب استيعاب سجلات جهات الاتصال من Marketing في رؤى الجمهور واستخدامها كمصدر بيانات.</span><span class="sxs-lookup"><span data-stu-id="a5188-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="a5188-111">كما يلزم تضمينها في كيان العميل الموحد من أجل تعيين معرفات العملاء إلى معرفات جهات الاتصال قبل أن يصبح تصدير الشرائح ممكنًا.</span><span class="sxs-lookup"><span data-stu-id="a5188-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="a5188-112">تكوين موصل Marketing</span><span class="sxs-lookup"><span data-stu-id="a5188-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="a5188-113">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.</span><span class="sxs-lookup"><span data-stu-id="a5188-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a5188-114">ضمن **Dynamics 365 Marketing‎**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="a5188-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="a5188-115">في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.</span><span class="sxs-lookup"><span data-stu-id="a5188-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a5188-116">أدخل عنوان URL لتطبيق Marketing‎ في حقل **عنوان الخادم**.</span><span class="sxs-lookup"><span data-stu-id="a5188-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a5188-117">في القسم **حساب مسؤول الخادم**، حدد **تسجيل الدخول** واختر حساب Dynamics 365 Marketing‎.</span><span class="sxs-lookup"><span data-stu-id="a5188-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="a5188-118">عيّن حقل معرف العميل إلى معرف جهة الاتصال في Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a5188-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a5188-119">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="a5188-119">Select **Next**.</span></span>

1. <span data-ttu-id="a5188-120">اختر شريحة أو أكثر.</span><span class="sxs-lookup"><span data-stu-id="a5188-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="a5188-121">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="a5188-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a5188-122">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="a5188-122">Export the data</span></span>

<span data-ttu-id="a5188-123">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a5188-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a5188-124">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a5188-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]