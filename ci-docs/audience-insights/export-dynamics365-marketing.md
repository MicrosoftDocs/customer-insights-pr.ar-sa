---
title: تصدير بيانات Customer Insights إلى Dynamics 365 Marketing
description: تعرف على كيفية تكوين الاتصال بتطبيق Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269038"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="33e8c-103">موصل لتطبيق Dynamics 365 Marketing (معاينة)</span><span class="sxs-lookup"><span data-stu-id="33e8c-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="33e8c-104">استخدم [الشرائح](segments.md) لإنشاء حملات وتحسين مجموعات محددة من العملاء باستخدام Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="33e8c-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="33e8c-105">لمزيد من المعلومات ، راجع [استخدام الشرائح من Dynamics 365 Customer Insights مع Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="33e8c-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="33e8c-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="33e8c-106">Prerequisite</span></span>

- <span data-ttu-id="33e8c-107">يجب أن تكون سجلات جهات الاتصال موجودة في Dynamics 365 Marketing قبل تصدير شريحة من Customer Insights إلى Marketing.</span><span class="sxs-lookup"><span data-stu-id="33e8c-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="33e8c-108">اقرأ المزيد حول كيفية استيعاب جهات الاتصال في [Dynamics 365 Marketing باستخدام Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="33e8c-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="33e8c-109">لن يؤدي تصدير الشرائح من رؤى الجمهور إلى Marketing إلى إنشاء سجلات جهات اتصال جديدة في مثيلات Marketing.</span><span class="sxs-lookup"><span data-stu-id="33e8c-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="33e8c-110">يجب استيعاب سجلات جهات الاتصال من Marketing في رؤى الجمهور واستخدامها كمصدر بيانات.</span><span class="sxs-lookup"><span data-stu-id="33e8c-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="33e8c-111">كما يلزم تضمينها في كيان العميل الموحد من أجل تعيين معرفات العملاء إلى معرفات جهات الاتصال قبل أن يصبح تصدير الشرائح ممكنًا.</span><span class="sxs-lookup"><span data-stu-id="33e8c-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="33e8c-112">تكوين موصل Marketing</span><span class="sxs-lookup"><span data-stu-id="33e8c-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="33e8c-113">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.</span><span class="sxs-lookup"><span data-stu-id="33e8c-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="33e8c-114">ضمن **Dynamics 365 Marketing‎**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="33e8c-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="33e8c-115">في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.</span><span class="sxs-lookup"><span data-stu-id="33e8c-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="33e8c-116">أدخل عنوان URL لتطبيق Marketing‎ في حقل **عنوان الخادم**.</span><span class="sxs-lookup"><span data-stu-id="33e8c-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="33e8c-117">في القسم **حساب مسؤول الخادم**، حدد **تسجيل الدخول** واختر حساب Dynamics 365 Marketing‎.</span><span class="sxs-lookup"><span data-stu-id="33e8c-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="33e8c-118">عيّن حقل معرف العميل إلى معرف جهة الاتصال في Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="33e8c-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="33e8c-119">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="33e8c-119">Select **Next**.</span></span>

1. <span data-ttu-id="33e8c-120">اختر شريحة أو أكثر.</span><span class="sxs-lookup"><span data-stu-id="33e8c-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="33e8c-121">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="33e8c-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="33e8c-122">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="33e8c-122">Export the data</span></span>

<span data-ttu-id="33e8c-123">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="33e8c-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="33e8c-124">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="33e8c-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]