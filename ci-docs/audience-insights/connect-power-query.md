---
title: استيعاب البيانات من خلال موصل Power Query
description: موصلات لمصادر البيانات تستند إلى Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d51a7efa5fd9f7336d1662500eb804a674738493
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267752"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="b3222-103">الاتصال بمصدر بيانات Power Query</span><span class="sxs-lookup"><span data-stu-id="b3222-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="b3222-104">يوفر Power Query مجموعة واسعة من الموصلات لاستيعاب البيانات.</span><span class="sxs-lookup"><span data-stu-id="b3222-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="b3222-105">معظم هذه الموصلات مدعومة من Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b3222-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="b3222-106">عادةً ما تتبع إضافة مصادر البيانات استنادًا إلى موصلات Power Query الخطوات الموضحة في القسم التالي.</span><span class="sxs-lookup"><span data-stu-id="b3222-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="b3222-107">ومع ذلك ، بناءً على الموصل الذي تستخدمه ، يلزم توفر معلومات مختلفة.</span><span class="sxs-lookup"><span data-stu-id="b3222-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="b3222-108">لمزيد من المعلومات ، راجع الوثائق الخاصة بالموصلات الفردية في [مرجع موصل Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="b3222-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="b3222-109">إنشاء مصدر بيانات جديد</span><span class="sxs-lookup"><span data-stu-id="b3222-109">Create a new data source</span></span>

1. <span data-ttu-id="b3222-110">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="b3222-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="b3222-111">حدد **إضافة مصدر بيانات**.</span><span class="sxs-lookup"><span data-stu-id="b3222-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="b3222-112">اختر طريقة **استيراد البيانات** ثم قم بتحديد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="b3222-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="b3222-113">أدخل **اسمًا** لمصدر البيانات، وحدد **التالي** لإنشاء المصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="b3222-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="b3222-114">إرشادات الاسم:</span><span class="sxs-lookup"><span data-stu-id="b3222-114">Name guidelines:</span></span> 
   - <span data-ttu-id="b3222-115">يجب أن يبدأ الاسم بحرف</span><span class="sxs-lookup"><span data-stu-id="b3222-115">Start with a letter.</span></span>
   - <span data-ttu-id="b3222-116">استخدم الأحرف و الأرقام فقط.</span><span class="sxs-lookup"><span data-stu-id="b3222-116">Use letters and numbers only.</span></span> <span data-ttu-id="b3222-117">غير مسموح باستخدام الأحرف الخاصة والمسافات.</span><span class="sxs-lookup"><span data-stu-id="b3222-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="b3222-118">استخدم ما بين 3 و64 حرفًا.</span><span class="sxs-lookup"><span data-stu-id="b3222-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="b3222-119">اختر أحد [الموصلات المتوفرة](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="b3222-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="b3222-120">علي سبيل المثال، نقوم بتحديد موصل **Text/CSV**.</span><span class="sxs-lookup"><span data-stu-id="b3222-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="b3222-121">أدخل التفاصيل المطلوبة في **إعدادات الاتصال** الخاصة بالرابط المحدد وحدد **التالي** للاطلاع على معاينة البيانات.</span><span class="sxs-lookup"><span data-stu-id="b3222-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="b3222-122">حدد **نقل البيانات**.</span><span class="sxs-lookup"><span data-stu-id="b3222-122">Select **Transform data**.</span></span> <span data-ttu-id="b3222-123">في هذه الخطوة، سوف تقوم بإضافة الكيانات إلى مصدر البيانات الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="b3222-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="b3222-124">الكيانات هي مجموعات البيانات.</span><span class="sxs-lookup"><span data-stu-id="b3222-124">Entities are datasets.</span></span> <span data-ttu-id="b3222-125">إذا كانت لديك قاعدة بيانات تتضمن مجموعات بيانات متعددة، تكون كل مجموعة بيانات كيان خاص بذاتها.</span><span class="sxs-lookup"><span data-stu-id="b3222-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="b3222-126">يتيح لك مربع الحوار **Power Query - تحرير الاستعلامات** مراجعة البيانات وتحسينها.</span><span class="sxs-lookup"><span data-stu-id="b3222-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="b3222-127">تظهر الكيانات التي حددتها الأنظمة في مصدر بياناتك المحدد في الجزء الأيمن.</span><span class="sxs-lookup"><span data-stu-id="b3222-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b3222-128">![مربع حوار تحرير الاستعلامات](media/data-manager-configure-edit-queries.png "مربع حوار تحرير الاستعلامات")</span><span class="sxs-lookup"><span data-stu-id="b3222-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="b3222-129">يُمكنك أيضًا تحويل بياناتك.</span><span class="sxs-lookup"><span data-stu-id="b3222-129">You can also transform your data.</span></span> <span data-ttu-id="b3222-130">حدد كيانًا لتحريره أو تحويله.</span><span class="sxs-lookup"><span data-stu-id="b3222-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="b3222-131">استخدم الخيارات الموجودة في نافذة Power Query لتطبيق عمليات التحويل.</span><span class="sxs-lookup"><span data-stu-id="b3222-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="b3222-132">يتم سرد كل عملية نقل ضمن **الخطوات المطبقة**.</span><span class="sxs-lookup"><span data-stu-id="b3222-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="b3222-133">كما يوفر Power Query العديد من خيارات التحويل التي تم إنشاؤها مسبقا.</span><span class="sxs-lookup"><span data-stu-id="b3222-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="b3222-134">لمزيد من المعلومات، راجع [عمليات تحويل Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="b3222-134">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="b3222-135">يُمكن إضافة كيانات إضافية لمصدر بياناتك عن طريق تحديد **الحصول على بيانات** في مربع حوار **تحرير الاستعلامات**.</span><span class="sxs-lookup"><span data-stu-id="b3222-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="b3222-136">يوصى بشدة بهذه التحويلات:</span><span class="sxs-lookup"><span data-stu-id="b3222-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="b3222-137">إذا كنت بصدد إدخال بيانات من ملف CSV ، فغالبًا ما يحتوي الصف الأول على رؤوس.</span><span class="sxs-lookup"><span data-stu-id="b3222-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="b3222-138">انتقل إلى **جدول التحويل** وحدد **استخدام الرؤوس كصف أول**.</span><span class="sxs-lookup"><span data-stu-id="b3222-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="b3222-139">تأكد من تعيين نوع البيانات بشكل صحيح.</span><span class="sxs-lookup"><span data-stu-id="b3222-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="b3222-140">حدد **حفظ** في الجزء السفلي من نافذة Power Query عمليات التحويل.</span><span class="sxs-lookup"><span data-stu-id="b3222-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="b3222-141">وبعد الحفظ، ستجد مصدر البيانات في **البيانات** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="b3222-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="b3222-142">في صفحة **مصادر البيانات**، ستلاحظ وجود مصدر البيانات الجديد في حالة **التحديث**.</span><span class="sxs-lookup"><span data-stu-id="b3222-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="b3222-143">مصادر بيانات Power Query المتوفرة</span><span class="sxs-lookup"><span data-stu-id="b3222-143">Available Power Query data sources</span></span>

<span data-ttu-id="b3222-144">راجع [مرجع موصل Power Query](https://docs.microsoft.com/power-query/connectors/) للحصول على قائمة محدثة بالموصلات التي يمكنك تحديدها لاستيراد البيانات إلى Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b3222-144">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="b3222-145">تتوفر الموصلات التي تتضمن علامة اختيار في عمود **Customer Insights (تدفقات البيانات)** لإنشاء مصادر بيانات جديدة استنادًا إلى Power Query.</span><span class="sxs-lookup"><span data-stu-id="b3222-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="b3222-146">راجع وثائق موصل معين لمعرفة المزيد حول متطلباته الأساسية وقيوده وتفاصيل أخرى.</span><span class="sxs-lookup"><span data-stu-id="b3222-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="b3222-147">تحرير مصادر بيانات Power Query</span><span class="sxs-lookup"><span data-stu-id="b3222-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="b3222-148">قد لا يكون من الممكن إجراء تغييرات على مصادر البيانات المستخدمة حاليًا في أحد عمليات التطبيق (*التقسيم* أو *المطابقة* أو *الدمج*، على سبيل المثال).</span><span class="sxs-lookup"><span data-stu-id="b3222-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="b3222-149">باستخدام صفحة **الإعدادات**، يُمكنك تعقب تقدم كل عملية نشطة.</span><span class="sxs-lookup"><span data-stu-id="b3222-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="b3222-150">عند اكتمال أحد العمليات، يُمكنك الرجوع إلى صفحة **مصادر البيانات** وإجراء التغييرات.</span><span class="sxs-lookup"><span data-stu-id="b3222-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="b3222-151">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="b3222-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b3222-152">حدد علامة الحذف الرأسية المجاورة لمصدر البيانات الذي تريد تغييره وحدد **تحرير** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="b3222-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b3222-153">![خيار التحرير](media/edit-option-data-sources.png "خيار التحرير")</span><span class="sxs-lookup"><span data-stu-id="b3222-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="b3222-154">قم بتطبيق التغييرات والتحويلات في مربع حوار **Power Query - تحرير الاستعلامات** كما هو موضح في قسم [إنشاء مصدر بيانات جديد](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="b3222-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="b3222-155">حدد **حفظ** في Power Query بعد إكمال عمليات التحرير الخاصة بك لحفظ التغييرات التي أجريتها.</span><span class="sxs-lookup"><span data-stu-id="b3222-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]