---
title: إثراء ملفات تعريف العملاء الموحدة
description: استخدم القدرات لإثراء بيانات العملاء.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667078"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="f2e90-103">الإثراء لملفات تعريف العملاء (معاينة)</span><span class="sxs-lookup"><span data-stu-id="f2e90-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="f2e90-104">استخدم البيانات من مصادر مثل Microsoft والشركاء الآخرين لإثراء بيانات العملاء.</span><span class="sxs-lookup"><span data-stu-id="f2e90-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="صفحة مركز الإثراء":::

<span data-ttu-id="f2e90-106">في رؤى الجمهور، انتقل إلى **البيانات** > **إثراء** للعمل مع خيارات الإثراء.</span><span class="sxs-lookup"><span data-stu-id="f2e90-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="f2e90-107">يجب أن يكون لديك أذونات المساهم أو المسؤول لإنشاء أو تحرير عمليات الإثراء.</span><span class="sxs-lookup"><span data-stu-id="f2e90-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="f2e90-108">لمزيد من المعلومات، راجع [الأذونات](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f2e90-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="f2e90-109">في علامة التبويب **اكتشاف**، ستجد عمليات الإثراء التالية:</span><span class="sxs-lookup"><span data-stu-id="f2e90-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="f2e90-110">[العلامات التجارية](enrichment-microsoft-graph.md) مقدمة من Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="f2e90-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="f2e90-111">[الاهتمامات](enrichment-microsoft-graph.md) مقدمة من Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="f2e90-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="f2e90-112">[بيانات الشركة](enrichment-leadspace.md) مقدمة من Leadspace</span><span class="sxs-lookup"><span data-stu-id="f2e90-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="f2e90-113">[الخصائص السكانية](enrichment-experian.md) تم توفيرها بواسطة Experian</span><span class="sxs-lookup"><span data-stu-id="f2e90-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="f2e90-114">[بيانات الموقع](enrichment-here.md) مقدمة من HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="f2e90-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="f2e90-115">[البيانات المخصصة](enrichment-SFTP-custom-import.md) عبر بروتوكول نقل الملفات الآمن (SFTP)‬</span><span class="sxs-lookup"><span data-stu-id="f2e90-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="f2e90-116">في علامة التبويب **عمليات الإثراء الخاصة بي‬**، يمكنك رؤية عمليات الإثراء الذي قمت بتكوينها وتحرير خصائصها.</span><span class="sxs-lookup"><span data-stu-id="f2e90-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="f2e90-117">إدارة ‏‫عمليات الإثراء الموجودة</span><span class="sxs-lookup"><span data-stu-id="f2e90-117">Manage existing enrichments</span></span>

<span data-ttu-id="f2e90-118">انتقل إلى **‏‫عمليات الإثراء** للاطلاع على كل ‏‫عمليات الإثراء التي تم تكوينها.</span><span class="sxs-lookup"><span data-stu-id="f2e90-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="f2e90-119">يتم تمثيل كل عملية من ‏‫عمليات الإثراء كصف يتضمن معلومات إضافية حول ‏‫عملية الإثراء.</span><span class="sxs-lookup"><span data-stu-id="f2e90-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="f2e90-120">حدد ‏‫عملية إثراء للاطلاع على الخيارات المتوفرة.</span><span class="sxs-lookup"><span data-stu-id="f2e90-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="f2e90-121">ويمكنك بدلاً من ذلك تحديد علامة القطع (...) على عنصر قائمة لمشاهدة الخيارات.</span><span class="sxs-lookup"><span data-stu-id="f2e90-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="خيارات إدارة عمليات الإثراء في قائمة عمليات الإثراء":::

- <span data-ttu-id="f2e90-123">**عرض** تفاصيل عمليات الإثراء باستخدام عدد ملفات تعريف العملاء الذين تم إثراؤهم.</span><span class="sxs-lookup"><span data-stu-id="f2e90-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="f2e90-124">**تحرير** تكوين عملية الإثراء.</span><span class="sxs-lookup"><span data-stu-id="f2e90-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="f2e90-125">**قم بتشغيل** الإثراء لتحديث ملفات تعريف العملاء بأحدث البيانات.</span><span class="sxs-lookup"><span data-stu-id="f2e90-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="f2e90-126">**إلغاء تنشيط** عملية إثراء موجودة لإيقافها عن التحديث تلقائيًا بكل تحديث مجدول.</span><span class="sxs-lookup"><span data-stu-id="f2e90-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="f2e90-127">تظل البيانات من آخر تحديث ناجح متاحة.</span><span class="sxs-lookup"><span data-stu-id="f2e90-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="f2e90-128">**تنشيط** عملية إثراء غير نشطة لإعادة تشغيل التحديث التلقائي بكل تحديث مجدول.</span><span class="sxs-lookup"><span data-stu-id="f2e90-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="f2e90-129">**حذف** إثراء.</span><span class="sxs-lookup"><span data-stu-id="f2e90-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="f2e90-130">يمكنك تشغيل أو إلغاء تنشيط العديد من عمليات الإثراء مرة واحدة عن طريق تحديدها في القائمة.</span><span class="sxs-lookup"><span data-stu-id="f2e90-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="f2e90-131">خيارات العرض والتحرير غير متاحة كإجراء مجمع ولا تعمل إلا على عملية إثراء واحدة في كل مرة.</span><span class="sxs-lookup"><span data-stu-id="f2e90-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>
