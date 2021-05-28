---
title: تصدير البيانات من Customer Insights
description: إدارة عمليات التصدير لمشاركة البيانات.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016575"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="d45a0-103">نظرة عامة على عمليات التصدير (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="d45a0-103">Exports (preview) overview</span></span>

<span data-ttu-id="d45a0-104">تعرض صفحة **عمليات التصدير** كل عمليات التصدير التي تم تكوينها.</span><span class="sxs-lookup"><span data-stu-id="d45a0-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="d45a0-105">تشترك عمليات التصدير في بيانات محددة مع تطبيقات متعددة.</span><span class="sxs-lookup"><span data-stu-id="d45a0-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="d45a0-106">يمكن أن تتضمن ملفات تعريف العملاء أو الكيانات، والتخططات، وتفاصيل التعيين.</span><span class="sxs-lookup"><span data-stu-id="d45a0-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="d45a0-107">تتطلب كل عملية تصدير [اتصالاً، والإعداد بواسطة مسؤول، لإدارة المصادقة والوصول](connections.md).</span><span class="sxs-lookup"><span data-stu-id="d45a0-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="d45a0-108">انتقل إلى **البيانات** > **عمليات التصدير** لعرض صفحة عمليات التصدير.</span><span class="sxs-lookup"><span data-stu-id="d45a0-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="d45a0-109">يكون لجميع أدوار المستخدمين حق الوصول لعرض عمليات التصدير التي تم تكوينها.</span><span class="sxs-lookup"><span data-stu-id="d45a0-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="d45a0-110">استخدم حقل البحث في شريط الأوامر للبحث عن عمليات تصدير من خلال اسمها أو اسمها أو نوع الاتصال الخاص بها.</span><span class="sxs-lookup"><span data-stu-id="d45a0-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="d45a0-111">إعداد تصدير جديد </span><span class="sxs-lookup"><span data-stu-id="d45a0-111">Set up a new export</span></span>

<span data-ttu-id="d45a0-112">لإعداد عملية تصدير أو تحريرها، ستحتاج إلى أن تتوفر لديك اتصالات.</span><span class="sxs-lookup"><span data-stu-id="d45a0-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="d45a0-113">تعتمد الاتصالات على [دور المستخدم](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="d45a0-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="d45a0-114">يمكن للمسؤولين الوصول إلى جميع الاتصالات.</span><span class="sxs-lookup"><span data-stu-id="d45a0-114">Administrators have access to all connections.</span></span> <span data-ttu-id="d45a0-115">كما يمكنهم إنشاء اتصالات جديدة عند إعداد عملية تصدير.</span><span class="sxs-lookup"><span data-stu-id="d45a0-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="d45a0-116">يمكن أن يكون للمساهمين إمكانية الوصول إلى اتصالات معينة.</span><span class="sxs-lookup"><span data-stu-id="d45a0-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="d45a0-117">وهي تعتمد على المسؤولين لتكوين الاتصالات ومشاركتها.</span><span class="sxs-lookup"><span data-stu-id="d45a0-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="d45a0-118">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d45a0-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="d45a0-119">يمكن فقط للمشاهدين عرض الصادرات الموجودة ولكن لا يمكنهم إنشائها.</span><span class="sxs-lookup"><span data-stu-id="d45a0-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="d45a0-120">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="d45a0-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d45a0-121">حدد **إضافة تصدير** لإنشاء وجهة تصدير جديدة.</span><span class="sxs-lookup"><span data-stu-id="d45a0-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="d45a0-122">في جزء **إعداد التصدير**، حدد الاتصال المراد استخدامه.</span><span class="sxs-lookup"><span data-stu-id="d45a0-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="d45a0-123">[الاتصالات](connections.md) المدارة بواسطة المسؤولين.</span><span class="sxs-lookup"><span data-stu-id="d45a0-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="d45a0-124">قم بتقديم التفاصيل المطلوبة وحدد **حفظ** لإنشاء التصدير.</span><span class="sxs-lookup"><span data-stu-id="d45a0-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="d45a0-125">تحرير تصدير</span><span class="sxs-lookup"><span data-stu-id="d45a0-125">Edit an export</span></span>

1. <span data-ttu-id="d45a0-126">حدد علامة القطع العمودية لوجهة التصدير التي ترغب في تحريرها.</span><span class="sxs-lookup"><span data-stu-id="d45a0-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="d45a0-127">حدد **تحرير** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="d45a0-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="d45a0-128">قم بتغيير القيم التي تريد تحديثها وحدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="d45a0-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="d45a0-129">عرض تفاصيل عمليات التصدير والتصدير</span><span class="sxs-lookup"><span data-stu-id="d45a0-129">View Exports and export details</span></span>

<span data-ttu-id="d45a0-130">بعد إنشاء وجهات التصدير، يتم سردها في **البيانات** > **عمليات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="d45a0-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="d45a0-131">يمكن لجميع المستخدمين معرفة البيانات التي تمت مشاركتها وآخر حالة لها.</span><span class="sxs-lookup"><span data-stu-id="d45a0-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="d45a0-132">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="d45a0-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d45a0-133">يحدد المستخدمون الذين ليس لديهم أذونات تحرير **عرض** بدلاً من **تحرير** للاطلاع على تفاصيل التصدير.</span><span class="sxs-lookup"><span data-stu-id="d45a0-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="d45a0-134">يوضح هذا الجزء الجانب إعداد هذا التصدير.</span><span class="sxs-lookup"><span data-stu-id="d45a0-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="d45a0-135">بدون أذونات التحرير، لا يمكنك تغيير القيم.</span><span class="sxs-lookup"><span data-stu-id="d45a0-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="d45a0-136">حدد **إغلاق** للعودة إلى صفحة التصدير.</span><span class="sxs-lookup"><span data-stu-id="d45a0-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="d45a0-137">تشغيل عمليات التصدير عند الطلب</span><span class="sxs-lookup"><span data-stu-id="d45a0-137">Run exports on demand</span></span>

<span data-ttu-id="d45a0-138">بعد تكوين التصدير، سيتم تشغيله مع كل [تحديث مجدول](system.md#schedule-tab) طالما أن له اتصال يعمل.</span><span class="sxs-lookup"><span data-stu-id="d45a0-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="d45a0-139">لتصدير البيانات دون انتظار التحديث المجدول، انتقل إلى **البيانات** > **عمليات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="d45a0-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="d45a0-140">لديك خيارين:</span><span class="sxs-lookup"><span data-stu-id="d45a0-140">You have two options:</span></span>

- <span data-ttu-id="d45a0-141">لتشغيل كافة عمليات التصدير، حدد **تشغيل الكل** في شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="d45a0-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="d45a0-142">لتشغيل عملية تصدير واحدة، قم بتحديد علامة الحذف (...) على عنصر قائمة ثم اختر **تشغيل**.</span><span class="sxs-lookup"><span data-stu-id="d45a0-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="d45a0-143">إزالة تصدير</span><span class="sxs-lookup"><span data-stu-id="d45a0-143">Remove an Export</span></span>

1. <span data-ttu-id="d45a0-144">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="d45a0-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d45a0-145">حدد علامة القطع العمودية للتصدير الذي ترغب في إزالته.</span><span class="sxs-lookup"><span data-stu-id="d45a0-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="d45a0-146">حدد **إزالة** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="d45a0-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="d45a0-147">حدد **إزالة** على شاشة التأكيد لتأكيد الإزالة.</span><span class="sxs-lookup"><span data-stu-id="d45a0-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
