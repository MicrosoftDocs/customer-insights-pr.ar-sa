---
title: الاتصالات بالخدمات الأخرى من Customer Insights.
description: مشاركة البيانات مع الخدمات الأخرى.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304956"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="aeec7-103">نظرة عامة على الاتصالات (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="aeec7-103">Connections (preview) overview</span></span>

<span data-ttu-id="aeec7-104">الاتصالات هي المفتاح لتمكين مشاركة البيانات من وإلى Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="aeec7-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="aeec7-105">ينشئ كل اتصال مشاركة البيانات مع خدمة معينة.</span><span class="sxs-lookup"><span data-stu-id="aeec7-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="aeec7-106">الاتصالات هي الأساس [لتكوين عمليات إثراء الأطراف الثالثة](enrichment-hub.md) و[تكوين التصديرات](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="aeec7-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="aeec7-107">يمكن استخدام الاتصال نفسه عدة مرات.</span><span class="sxs-lookup"><span data-stu-id="aeec7-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="aeec7-108">على سبيل المثال، يعمل اتصال واحد بـ Dynamics 365 Marketing من أجل عمليات تصدير متعددة، ويمكن استخدام اتصال Leadspace واحد لعدة عمليات إثراء.</span><span class="sxs-lookup"><span data-stu-id="aeec7-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="aeec7-109">انتقل إلى **المسؤول** > **الاتصالات** لإنشاء الاتصالات وعرضها.</span><span class="sxs-lookup"><span data-stu-id="aeec7-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="aeec7-110">تعرض علامة التبويب **الاتصالات** جميع الاتصالات النشطة.</span><span class="sxs-lookup"><span data-stu-id="aeec7-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="aeec7-111">تُظهر القائمة صفًا لكل اتصال.</span><span class="sxs-lookup"><span data-stu-id="aeec7-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="aeec7-112">احصل على نظرة عامة سريعة ووصف واكتشف ما يمكنك القيام به مع كل خيار من خيارات القابلية للتوسعة في علامة التبويب **اكتشاف**.</span><span class="sxs-lookup"><span data-stu-id="aeec7-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="aeec7-113">التصديرات</span><span class="sxs-lookup"><span data-stu-id="aeec7-113">Exports</span></span>

<span data-ttu-id="aeec7-114">يمكن للمسؤولين فقط تكوين اتصالات جديدة، ولكن يمكنهم منح حق الوصول إلى المساهمين لاستخدام الاتصالات الموجودة.</span><span class="sxs-lookup"><span data-stu-id="aeec7-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="aeec7-115">يمكن للمسؤولين التحكم في المكان الذي يمكن فيه نقل البيانات، يحدد المساهمون الحمولة وتكرار تلبية احتياجاتهم.</span><span class="sxs-lookup"><span data-stu-id="aeec7-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="aeec7-116">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="aeec7-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="aeec7-117">عمليات الإثراء</span><span class="sxs-lookup"><span data-stu-id="aeec7-117">Enrichments</span></span>

<span data-ttu-id="aeec7-118">يمكن للمسؤولين فقط تكوين اتصالات جديدة، غير أن الاتصالات التي تم إنشاؤها تكون دائما متوفرة لكل من المسؤولين والمساهمين.</span><span class="sxs-lookup"><span data-stu-id="aeec7-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="aeec7-119">يدير المسؤولون بيانات الاعتماد ويمنحون الموافقة على عمليات نقل البيانات.</span><span class="sxs-lookup"><span data-stu-id="aeec7-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="aeec7-120">ويمكن استخدام هذه الاتصالات بعد ذلك في عمليات المنشطين من جانب كل من المسؤولين والمساهمين.</span><span class="sxs-lookup"><span data-stu-id="aeec7-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="aeec7-121">إضافة اتصال جديد</span><span class="sxs-lookup"><span data-stu-id="aeec7-121">Add a new connection</span></span>

<span data-ttu-id="aeec7-122">لإضافة اتصالات، يلزم أن يكون لديك [أذونات المسؤول](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="aeec7-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="aeec7-123">إذا قمت بالاتصال بخدمات Microsoft أخرى، فإننا نفترض أن كلتا الخدمتين في نفس المؤسسة.</span><span class="sxs-lookup"><span data-stu-id="aeec7-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="aeec7-124">انتقل إلى **المسؤول** > **الاتصالات (إصدار أولي)**.</span><span class="sxs-lookup"><span data-stu-id="aeec7-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="aeec7-125">انتقل إلى علامة التبويب **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="aeec7-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="aeec7-126">لإنشاء اتصال جديد، حدد **إضافة اتصال**.</span><span class="sxs-lookup"><span data-stu-id="aeec7-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="aeec7-127">اختر من القائمة المنسدلة نوع الاتصال الذي ترغب في إنشائه.</span><span class="sxs-lookup"><span data-stu-id="aeec7-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="aeec7-128">في جزء **إعداد الاتصال**، قم بتقديم التفاصيل المطلوبة.</span><span class="sxs-lookup"><span data-stu-id="aeec7-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="aeec7-129">يصف **اسم العرض** ونوع الاتصال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="aeec7-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="aeec7-130">ننصح باختيار اسم يوضح الغرض والهدف من هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="aeec7-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="aeec7-131">تعتمد الحقول تحديدا على الخدمة التي تتصل بها.</span><span class="sxs-lookup"><span data-stu-id="aeec7-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="aeec7-132">يمكنك التعرف على تفاصيل نوع اتصال محدد حول المقالة حول الخدمة الهدف.</span><span class="sxs-lookup"><span data-stu-id="aeec7-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="aeec7-133">لإنشاء الاتصال، حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="aeec7-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="aeec7-134">يمكنك أيضًا تحديد **إعداد** على إطار متجانب في علامة التبويب **اكتشاف**.</span><span class="sxs-lookup"><span data-stu-id="aeec7-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="aeec7-135">السماح للمساهمين باستخدام اتصال للتصديرات</span><span class="sxs-lookup"><span data-stu-id="aeec7-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="aeec7-136">عند إعداد اتصال تصدير أو تحريره، يمكنك اختيار المستخدمين المسموح لهم باستخدام هذا الاتصال المحدد لتحديد [التصديرات](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="aeec7-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="aeec7-137">يكون الاتصال متوفرا بشكل افتراضي للمستخدمين الذين لديهم المسؤول استخدام.</span><span class="sxs-lookup"><span data-stu-id="aeec7-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="aeec7-138">يمكنك تغيير هذا الإعداد ضمن **اختيار من يمكنه استخدام هذا الاتصال** والسماح للمستخدمين الذين لهم دور مساهم باستخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="aeec7-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="aeec7-139">لن يتمكن المساهمون من عرض الاتصال أو تحريره.</span><span class="sxs-lookup"><span data-stu-id="aeec7-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="aeec7-140">وسيشاهدون فقط اسم العرض ونوعه عند إنشاء عملية تصدير.</span><span class="sxs-lookup"><span data-stu-id="aeec7-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="aeec7-141">ومن خلال مشاركة الاتصال، تسمح للمساهمين باستخدام الاتصال.</span><span class="sxs-lookup"><span data-stu-id="aeec7-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="aeec7-142">سيشاهد المساهمون اتصالات مشتركة عند إعداد عمليات التصدير.</span><span class="sxs-lookup"><span data-stu-id="aeec7-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="aeec7-143">فهم يمكنهم إدارة كل عملية تصدير تستخدم هذا الاتصال المعين.</span><span class="sxs-lookup"><span data-stu-id="aeec7-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="aeec7-144">يمكنك تغيير هذا الإعداد مع الاحتفاظ بالصديرات التي تم تعريفها بالفعل بواسطة المساهمون.</span><span class="sxs-lookup"><span data-stu-id="aeec7-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="aeec7-145">تحرير اتصال</span><span class="sxs-lookup"><span data-stu-id="aeec7-145">Edit a connection</span></span>

1. <span data-ttu-id="aeec7-146">انتقل إلى **المسؤول** > **الاتصالات (إصدار أولي)**.</span><span class="sxs-lookup"><span data-stu-id="aeec7-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="aeec7-147">انتقل إلى علامة التبويب **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="aeec7-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="aeec7-148">حدد علامة القطع الرأسية للاتصال الذي تريد تحريره.</span><span class="sxs-lookup"><span data-stu-id="aeec7-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="aeec7-149">حدد **تحرير**.</span><span class="sxs-lookup"><span data-stu-id="aeec7-149">Select **Edit**.</span></span>

1. <span data-ttu-id="aeec7-150">قم بتغيير القيم التي تريد تحديثها وحدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="aeec7-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="aeec7-151">إزالة اتصال</span><span class="sxs-lookup"><span data-stu-id="aeec7-151">Remove a connection</span></span>

<span data-ttu-id="aeec7-152">إذا كان الاتصال الذي تقوم بإزالته مستخدما بواسطة الوحدات الخاصة أو التصدير، يجب أولا تحويلها إلى برنامج أو إزالتها.</span><span class="sxs-lookup"><span data-stu-id="aeec7-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="aeec7-153">سيرشدك مربع الحوار "إزالة" إلى المراجع أو عمليات التصدير ذات الصلة.</span><span class="sxs-lookup"><span data-stu-id="aeec7-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="aeec7-154">تصبح عمليات التصدير والتصدير التي تم تحويلها إلى منتجات غير نشطة.</span><span class="sxs-lookup"><span data-stu-id="aeec7-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="aeec7-155">يمكنك إعادة تنشيطها عن طريق إضافة اتصال آخر إليها في صفحة [عمليات الإثراء](enrichment-hub.md) أو [التصديرات](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="aeec7-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="aeec7-156">انتقل إلى **المسؤول** > **الاتصالات (إصدار أولي)**.</span><span class="sxs-lookup"><span data-stu-id="aeec7-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="aeec7-157">انتقل إلى علامة التبويب **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="aeec7-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="aeec7-158">حدد علامة القطع الرأسية للاتصال الذي تريد إزالته.</span><span class="sxs-lookup"><span data-stu-id="aeec7-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="aeec7-159">حدد **إزالة** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="aeec7-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="aeec7-160">يظهر حوار التأكيد.</span><span class="sxs-lookup"><span data-stu-id="aeec7-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="aeec7-161">في حالة وجود عمليات تصدير أو عمليات تصدير باستخدام هذا الاتصال، حدد الزر لمعرفة ما يستخدم الاتصال.</span><span class="sxs-lookup"><span data-stu-id="aeec7-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="aeec7-162">**عمليات التصدير**: يمكنك اختيار إزالة أو قطع اتصال عمليات التصدير حتى تتمكن من إزالة الاتصال.</span><span class="sxs-lookup"><span data-stu-id="aeec7-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="aeec7-163">لقطع اتصال عملية تصدير، يمكن للمسؤولين استخدام إجراء **قطع الاتصال**.</span><span class="sxs-lookup"><span data-stu-id="aeec7-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="aeec7-164">يتوفر هذا الإجراء للتصدير الفردي ومتعدد المحدد.</span><span class="sxs-lookup"><span data-stu-id="aeec7-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="aeec7-165">بقطع الاتصال، ستحتفظ بتكوين التصدير، لكن لن يتم تشغيله حتى تتم إضافة اتصال آخر إليه.</span><span class="sxs-lookup"><span data-stu-id="aeec7-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="aeec7-166">**عمليات الإثراء**: يمكنك اختيار إما إزالة أو إلغاء تنشيط الإثراء لتتمكن من إزالة الاتصال.</span><span class="sxs-lookup"><span data-stu-id="aeec7-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="aeec7-167">بمجرد عدم احتواء الاتصال على المزيد من التبعيات، ارجع إلى **المسؤول** > **الاتصالات** وحاول إزالة الاتصال مرة أخرى.</span><span class="sxs-lookup"><span data-stu-id="aeec7-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="aeec7-168">لتأكيد الحذف، حدد **إزالة**.</span><span class="sxs-lookup"><span data-stu-id="aeec7-168">To confirm the deletion, select **Remove**.</span></span>

