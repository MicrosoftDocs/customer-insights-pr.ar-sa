---
title: إثراء ملفات تعريف العملاء الموحدة
description: استخدم القدرات لإثراء بيانات العملاء.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c8e4a7247ccf575a62440038180010916b09d51b
ms.sourcegitcommit: f9e2fa3f11ecf11a5d9cccc376fdeb1ecea54880
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/28/2021
ms.locfileid: "5954471"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="c299b-103">الإثراء لملفات تعريف العملاء (معاينة)</span><span class="sxs-lookup"><span data-stu-id="c299b-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="c299b-104">استخدم البيانات من مصادر مثل Microsoft والشركاء الآخرين لإثراء بيانات العملاء.</span><span class="sxs-lookup"><span data-stu-id="c299b-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="صفحة مركز الإثراء":::

<span data-ttu-id="c299b-106">في رؤى الجمهور، انتقل إلى **البيانات** > **إثراء** للعمل مع خيارات الإثراء.</span><span class="sxs-lookup"><span data-stu-id="c299b-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="c299b-107">يجب أن يكون لديك أذونات المساهم أو المسؤول لإنشاء أو تحرير عمليات الإثراء.</span><span class="sxs-lookup"><span data-stu-id="c299b-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="c299b-108">لمزيد من المعلومات، راجع [الأذونات](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="c299b-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="c299b-109">في علامة التبويب **اكتشاف**، ستجد عمليات الإثراء التالية:</span><span class="sxs-lookup"><span data-stu-id="c299b-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="c299b-110">[العلامات التجارية](enrichment-microsoft.md) الموفرة بواسطة Microsoft</span><span class="sxs-lookup"><span data-stu-id="c299b-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="c299b-111">[الاهتمامات](enrichment-microsoft.md) الموفرة بواسطة Microsoft</span><span class="sxs-lookup"><span data-stu-id="c299b-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="c299b-112">[العناوين المحسنة](enrichment-enhanced-addresses.md) التي تقدمها Microsoft</span><span class="sxs-lookup"><span data-stu-id="c299b-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="c299b-113">[بيانات الشركة](enrichment-leadspace.md) مقدمة من Leadspace</span><span class="sxs-lookup"><span data-stu-id="c299b-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="c299b-114">[الخصائص السكانية](enrichment-experian.md) تم توفيرها بواسطة Experian</span><span class="sxs-lookup"><span data-stu-id="c299b-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="c299b-115">[بيانات الموقع](enrichment-here.md) مقدمة من HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="c299b-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="c299b-116">[البيانات المخصصة](enrichment-SFTP-custom-import.md) عبر بروتوكول نقل الملفات الآمن (SFTP)‬</span><span class="sxs-lookup"><span data-stu-id="c299b-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="c299b-117">في علامة التبويب **عمليات الإثراء الخاصة بي‬**، يمكنك رؤية عمليات الإثراء الذي قمت بتكوينها وتحرير خصائصها.</span><span class="sxs-lookup"><span data-stu-id="c299b-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="c299b-118">إدارة ‏‫عمليات الإثراء الموجودة</span><span class="sxs-lookup"><span data-stu-id="c299b-118">Manage existing enrichments</span></span>

<span data-ttu-id="c299b-119">انتقل إلى **‏‫عمليات الإثراء** للاطلاع على كل ‏‫عمليات الإثراء التي تم تكوينها.</span><span class="sxs-lookup"><span data-stu-id="c299b-119">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="c299b-120">يتم تمثيل كل عملية من ‏‫عمليات الإثراء كصف يتضمن معلومات إضافية حول ‏‫عملية الإثراء.</span><span class="sxs-lookup"><span data-stu-id="c299b-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="c299b-121">حدد ‏‫عملية إثراء للاطلاع على الخيارات المتوفرة.</span><span class="sxs-lookup"><span data-stu-id="c299b-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="c299b-122">يمكنك أيضًا تحديد علامة الحذف (...) على عنصر قائمة لمشاهدة الخيارات.</span><span class="sxs-lookup"><span data-stu-id="c299b-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="خيارات إدارة عمليات الإثراء في قائمة عمليات الإثراء":::

- <span data-ttu-id="c299b-124">**عرض** تفاصيل عمليات الإثراء باستخدام عدد ملفات تعريف العملاء الذين تم إثراؤهم.</span><span class="sxs-lookup"><span data-stu-id="c299b-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="c299b-125">**تحرير** تكوين عملية الإثراء.</span><span class="sxs-lookup"><span data-stu-id="c299b-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="c299b-126">**قم بتشغيل** الإثراء لتحديث ملفات تعريف العملاء بأحدث البيانات.</span><span class="sxs-lookup"><span data-stu-id="c299b-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="c299b-127">**إلغاء تنشيط** عملية إثراء موجودة لإيقافها عن التحديث تلقائيًا بكل تحديث مجدول.</span><span class="sxs-lookup"><span data-stu-id="c299b-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="c299b-128">تظل البيانات من آخر تحديث ناجح متاحة.</span><span class="sxs-lookup"><span data-stu-id="c299b-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="c299b-129">**تنشيط** عملية إثراء غير نشطة لإعادة تشغيل التحديث التلقائي بكل تحديث مجدول.</span><span class="sxs-lookup"><span data-stu-id="c299b-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="c299b-130">**حذف** إثراء.</span><span class="sxs-lookup"><span data-stu-id="c299b-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="c299b-131">يمكنك تشغيل أو إلغاء تنشيط العديد من عمليات الإثراء مرة واحدة عن طريق تحديدها في القائمة.</span><span class="sxs-lookup"><span data-stu-id="c299b-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="c299b-132">خيارات العرض والتحرير غير متاحة كإجراء مجمع ولا تعمل إلا على عملية إثراء واحدة في كل مرة.</span><span class="sxs-lookup"><span data-stu-id="c299b-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="c299b-133">عمليات الإثراء والاتصالات</span><span class="sxs-lookup"><span data-stu-id="c299b-133">Enrichments and connections</span></span>

<span data-ttu-id="c299b-134">يتم تكوين عمليات إثراء الأطراف الثالثة باستخدام [الاتصالات](connections.md)، التي يقوم المسؤول بإعدادها باستخدام بيانات الاعتماد ويقدم الموافقة على عمليات نقل البيانات.</span><span class="sxs-lookup"><span data-stu-id="c299b-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="c299b-135">يمكن للمسؤولين والمساهمين استخدام الاتصال لتكوين عمليات الإثراء.</span><span class="sxs-lookup"><span data-stu-id="c299b-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="c299b-136">عمليات إثراء متعددة من نفس النوع</span><span class="sxs-lookup"><span data-stu-id="c299b-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="c299b-137">يتم تحديد الكيان الذي سيتم إثراءه أثناء تكوين المنشط، والذي يسمح لك بإثراء مجموعة فرعية فقط من ملفات التعريف الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="c299b-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="c299b-138">بالنسبة إلى المثال، قم بإثراء البيانات فقط لشرائح معينة.</span><span class="sxs-lookup"><span data-stu-id="c299b-138">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="c299b-139">يمكنك تكوين العديد من عمليات الإثراء من نفس النوع وإعادة استخدام نفس الاتصال.</span><span class="sxs-lookup"><span data-stu-id="c299b-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="c299b-140">سيكون لبعض عمليات الإثراء حدود لعدد عمليات الإثراء من نفس النوع التي يمكن إنشاؤها.</span><span class="sxs-lookup"><span data-stu-id="c299b-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="c299b-141">يمكن رؤية الحدود والاستخدام الحالي على صفحة **الإثراء**.</span><span class="sxs-lookup"><span data-stu-id="c299b-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
