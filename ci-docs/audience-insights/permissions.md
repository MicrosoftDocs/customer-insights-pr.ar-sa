---
title: إدارة أذونات المستخدم
description: تعرف على الأذونات وأدوار المستخدم.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760357"
---
# <a name="user-permissions"></a><span data-ttu-id="db1b8-103">أذونات المستخدم</span><span class="sxs-lookup"><span data-stu-id="db1b8-103">User permissions</span></span>

<span data-ttu-id="db1b8-104">تشكل صفحة **الأذونات** المكان الذي ستقوم فيه بإعداد الأدوار والأذونات لاستخدام رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="db1b8-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="db1b8-105">يجب أن يكون لديك أذونات المسؤول لرؤية الصفحة.</span><span class="sxs-lookup"><span data-stu-id="db1b8-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="db1b8-106">للوصول إلى صفحة الأذونات في رؤى الجمهور، انتقل إلى **المسؤول** > **الأذونات**.</span><span class="sxs-lookup"><span data-stu-id="db1b8-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="db1b8-107">توجد ثلاثة أنواع من الأدوار:</span><span class="sxs-lookup"><span data-stu-id="db1b8-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="db1b8-108">العارض</span><span class="sxs-lookup"><span data-stu-id="db1b8-108">Viewer</span></span>

- <span data-ttu-id="db1b8-109">استكشف الرؤى والشرائح داخل صفحات **الرئيسية** و **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="db1b8-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="db1b8-110">بحث وتصفية ملفات تعريف العملاء باستخدام صفحة **العملاء** .</span><span class="sxs-lookup"><span data-stu-id="db1b8-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="db1b8-111">يجب أن تكون الحقول قابلة للبحث.</span><span class="sxs-lookup"><span data-stu-id="db1b8-111">Fields must be searchable.</span></span>
- <span data-ttu-id="db1b8-112">اعرض واستكشف صفحة **الإثراء**.</span><span class="sxs-lookup"><span data-stu-id="db1b8-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="db1b8-113">استكشف الكيانات وقم بتصديرها باستخدام صفحة **الكيانات** .</span><span class="sxs-lookup"><span data-stu-id="db1b8-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="db1b8-114">عرض حالة عمليات النظام باستخدام صفحة **النظام** .</span><span class="sxs-lookup"><span data-stu-id="db1b8-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="db1b8-115">اعرض عمليات التصدير في صفحة **عمليات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="db1b8-115">View exports in **Exports** page.</span></span>
- <span data-ttu-id="db1b8-116">تثبيت لوحة معلومات **Power BI Customer Insights** واستخدامها.</span><span class="sxs-lookup"><span data-stu-id="db1b8-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="db1b8-117">المساهم</span><span class="sxs-lookup"><span data-stu-id="db1b8-117">Contributor</span></span>

- <span data-ttu-id="db1b8-118">تكون جميع الأذونات متاحة للعارض.</span><span class="sxs-lookup"><span data-stu-id="db1b8-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="db1b8-119">تحميل البيانات وتحويلها باستخدام صفحة **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="db1b8-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="db1b8-120">إكمال أقسام *توحيد البيانات*(**تعيين** و **مطابقة** و **دمج**) والتي ينتج عنها كيان ملف تعريف العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="db1b8-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="db1b8-121">تحديد **العلاقات** و **الأنشطة**.</span><span class="sxs-lookup"><span data-stu-id="db1b8-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="db1b8-122">إنشاء شرائح باستخدام صفحة **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="db1b8-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="db1b8-123">قم بإنشاء مقاييس باستخدام صفحة **المقاييس** .</span><span class="sxs-lookup"><span data-stu-id="db1b8-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="db1b8-124">إدارة التكوين وإثراء ملفات تعريف العملاء من صفحة **الإثراء** (مع عمليات إثراء الطرف الأول فقط).</span><span class="sxs-lookup"><span data-stu-id="db1b8-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>
- <span data-ttu-id="db1b8-125">قم بإدارة وإنشاء عمليات التصدير بناءً على الاتصالات المشتركة مع المساهمين.</span><span class="sxs-lookup"><span data-stu-id="db1b8-125">Manage and create exports based on connections shared with contributors.</span></span> <span data-ttu-id="db1b8-126">[تعرف على المزيد حول كيف يسمح المسؤولون للمساهمين باستخدام اتصال لعمليات التصدير](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="db1b8-126">[Learn more about how administrators allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

## <a name="administrator"></a><span data-ttu-id="db1b8-127">المسؤول </span><span class="sxs-lookup"><span data-stu-id="db1b8-127">Administrator</span></span>

- <span data-ttu-id="db1b8-128">تكون جميع الأذونات متاحة للمساهم.</span><span class="sxs-lookup"><span data-stu-id="db1b8-128">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="db1b8-129">تغيير الإعدادات على صفحة **النظام**، بما في ذلك اللغة قيد التشغيل وجداول التحديث لعمليات النظام لديك.</span><span class="sxs-lookup"><span data-stu-id="db1b8-129">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="db1b8-130">استعراض وإضافة الأذونات باستخدام صفحة **الأذونات**.</span><span class="sxs-lookup"><span data-stu-id="db1b8-130">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="db1b8-131">تعيين تعريفات البحث والتصفية لصفحة العملاء باستخدام صفحة **فهرس البحث والتصفية** (يمكن الوصول إليها عبر صفحة **العملاء**).</span><span class="sxs-lookup"><span data-stu-id="db1b8-131">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="db1b8-132">قم بإدارة الاتصالات والسماح لها بأدوار المستخدمين الآخرين في صفحة **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="db1b8-132">Manage connections and allow them for other user roles on **Connections** page.</span></span>
- <span data-ttu-id="db1b8-133">إدارة التكوين وإثراء ملفات تعريف العملاء من صفحة **الإثراء** (لجميع عمليات الإثراء).</span><span class="sxs-lookup"><span data-stu-id="db1b8-133">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="db1b8-134">قمب إدارة عمليات التصدير وإنشائها في صفحة **عمليات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="db1b8-134">Manage and create exports on **Exports** page.</span></span>
- <span data-ttu-id="db1b8-135">قم بتثبيت واستخدام **الوظيفة الإضافية لبطاقة عميل**.</span><span class="sxs-lookup"><span data-stu-id="db1b8-135">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="db1b8-136">إضافة موصل **Power Apps** واستخدامه.</span><span class="sxs-lookup"><span data-stu-id="db1b8-136">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="db1b8-137">تمكين استخدام [واجهات API في Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="db1b8-137">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="db1b8-138">تعيين الأدوار والأذونات</span><span class="sxs-lookup"><span data-stu-id="db1b8-138">Assign roles and permissions</span></span>

1. <span data-ttu-id="db1b8-139">في رؤى الجمهور، انتقل إلى **المسؤول‏‎** > **الأذونات**.</span><span class="sxs-lookup"><span data-stu-id="db1b8-139">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="db1b8-140">حدد **إضافة مستخدمين** لجزء **إضافة/تحرير الأذونات**.</span><span class="sxs-lookup"><span data-stu-id="db1b8-140">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="db1b8-141">استخدم حقل **البحث** للعثور على مستخدم أو مجموعة Azure Active Directory التي ترغب في ضبط الأذونات الخاصة بها.</span><span class="sxs-lookup"><span data-stu-id="db1b8-141">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="db1b8-142">حدد **دورًا** لتعيينه لهذا المستخدم أو المجموعة.</span><span class="sxs-lookup"><span data-stu-id="db1b8-142">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="db1b8-143">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="db1b8-143">Select **Save**.</span></span> <span data-ttu-id="db1b8-144">ستتم مشاركة البيئة الحالية تلقائيًا مع المستخدم أو أعضاء المجموعة التي قمت بتغيير الأذونات الخاصة بها.</span><span class="sxs-lookup"><span data-stu-id="db1b8-144">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="db1b8-145">يمكن للمستخدمين الوصول إلى تطبيق Customer Insights والعمل وفقا للدور المحدد لهم.</span><span class="sxs-lookup"><span data-stu-id="db1b8-145">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="db1b8-146">عرض الأذونات الحالية</span><span class="sxs-lookup"><span data-stu-id="db1b8-146">View current permissions</span></span>

<span data-ttu-id="db1b8-147">في رؤى الجمهور، انتقل إلى **المسؤول** > **الأذونات** للاطلاع على التعيينات النشطة حاليًا.</span><span class="sxs-lookup"><span data-stu-id="db1b8-147">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="db1b8-148">يحدد عمود **النوع** مستخدمًا واحدًا أو مجموعة أو تطبيقًا واحدًا.</span><span class="sxs-lookup"><span data-stu-id="db1b8-148">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="db1b8-149">يدعم النظام المجموعات والمستخدمين الفرديين.</span><span class="sxs-lookup"><span data-stu-id="db1b8-149">The system supports individual users and groups.</span></span>
- <span data-ttu-id="db1b8-150">يتم تحديد الأدوار ضمن عمود **الدور** .</span><span class="sxs-lookup"><span data-stu-id="db1b8-150">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="db1b8-151">حدد أي عنوان عمود لفرز النتائج حسب قيمة هذا العمود.</span><span class="sxs-lookup"><span data-stu-id="db1b8-151">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="db1b8-152">استخدم حقل **بحث** في أعلى الصفحة لتحديد موقع مستخدمين محددين.</span><span class="sxs-lookup"><span data-stu-id="db1b8-152">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
