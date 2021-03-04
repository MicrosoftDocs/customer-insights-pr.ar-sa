---
title: تصدير بيانات Customer Insights إلى Dynamics 365 Sales
description: تعرف على كيفية تكوين الاتصال بتطبيق Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268992"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="b1f55-103">موصل لتطبيق Dynamics 365 Sales (معاينة)</span><span class="sxs-lookup"><span data-stu-id="b1f55-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b1f55-104">استخدم بيانات العميل الخاصة بك لإنشاء قوائم تسويق ومتابعة عمليات سير العمل وإرسال العروض الترويجية باستخدام Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b1f55-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="b1f55-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="b1f55-105">Prerequisite</span></span>

1. <span data-ttu-id="b1f55-106">يجب أن تكون سجلات جهات الاتصال موجودة في Dynamics 365 Sales قبل تصدير شريحة من Customer Insights إلى Sales.</span><span class="sxs-lookup"><span data-stu-id="b1f55-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="b1f55-107">اقرأ المزيد حول كيفية استيعاب جهات الاتصال في [Dynamics 365 Sales باستخدام Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b1f55-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="b1f55-108">لن يؤدي تصدير الشرائح من رؤى الجمهور إلى Sales إلى إنشاء سجلات جهات اتصال جديدة في مثيلات Sales.</span><span class="sxs-lookup"><span data-stu-id="b1f55-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="b1f55-109">يجب استيعاب سجلات جهات الاتصال من Sales في رؤى الجمهور واستخدامها كمصدر بيانات.</span><span class="sxs-lookup"><span data-stu-id="b1f55-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="b1f55-110">كما يلزم تضمينها في كيان العميل الموحد من أجل تعيين معرفات العملاء إلى معرفات جهات الاتصال قبل أن يصبح تصدير الشرائح ممكنًا.</span><span class="sxs-lookup"><span data-stu-id="b1f55-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="b1f55-111">تكوين موصل Sales</span><span class="sxs-lookup"><span data-stu-id="b1f55-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="b1f55-112">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.</span><span class="sxs-lookup"><span data-stu-id="b1f55-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b1f55-113">ضمن **Dynamics 365 Sales**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="b1f55-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="b1f55-114">في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.</span><span class="sxs-lookup"><span data-stu-id="b1f55-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b1f55-115">أدخل عنوان URL لتطبيق Sales في حقل **عنوان الخادم**.</span><span class="sxs-lookup"><span data-stu-id="b1f55-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="b1f55-116">في القسم **حساب مسؤول الخادم**، حدد **تسجيل الدخول** واختر حساب Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b1f55-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="b1f55-117">عيّن حقل معرف العميل إلى معرف جهة الاتصال في Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b1f55-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="b1f55-118">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="b1f55-118">Select **Next**.</span></span>

1. <span data-ttu-id="b1f55-119">اختر شريحة أو أكثر.</span><span class="sxs-lookup"><span data-stu-id="b1f55-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="b1f55-120">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="b1f55-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b1f55-121">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="b1f55-121">Export the data</span></span>

<span data-ttu-id="b1f55-122">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b1f55-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b1f55-123">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b1f55-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]