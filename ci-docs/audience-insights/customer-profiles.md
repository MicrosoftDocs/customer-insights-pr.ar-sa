---
title: عرض ملفات تعريف العملاء
description: احصل على طريقة عرض مجمعة لبيانات العملاء الموحدة.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a5d928ae518f3cb1afbf8e2b197e51b27665f6e0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269728"
---
# <a name="customer-profiles"></a><span data-ttu-id="6582b-103">ملفات تعريف العملاء</span><span class="sxs-lookup"><span data-stu-id="6582b-103">Customer profiles</span></span>

<span data-ttu-id="6582b-104">تعرض صفحة **العملاء** طريقة عرض مجمعة للعملاء، بالاستناد إلى بيانات ملفات التعريف المجمعة من [جميع مصادر البيانات](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="6582b-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="6582b-105">تتوفر ملفات تعريف العملاء بمجرد أن تقوم [بإنشاء كيان عميل موحد](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="6582b-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="6582b-106">تأكد من إتمام عملية توحيد البيانات للحصول على طرق عرض أغنى لعملائك.</span><span class="sxs-lookup"><span data-stu-id="6582b-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="6582b-107">تتيح لك الصفحة أيضًا البحث عن العملاء.</span><span class="sxs-lookup"><span data-stu-id="6582b-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="6582b-108">يمكن أن يكون العملاء أفرادًا أو مؤسسات (معاينة).</span><span class="sxs-lookup"><span data-stu-id="6582b-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="6582b-109">يتم تمثيل كل ملف تعريف لأحد العملاء أو المؤسسات بإطار متجانب.</span><span class="sxs-lookup"><span data-stu-id="6582b-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="6582b-110">حدد إطارًا للإطلاع على معلومات إضافية حول ذلك العميل المحدد أو المؤسسة المحددة.</span><span class="sxs-lookup"><span data-stu-id="6582b-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="6582b-111">استخدم عناصر التحكم في الترقيم في الجزء السفلي من الصفحة لعرض السجلات الإضافية.</span><span class="sxs-lookup"><span data-stu-id="6582b-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="6582b-112">![ملف تعريف العميل متاجرة عمل-مستهلك](media/profiles-customers.png "ملف تعريف العميل متاجرة عمل-مستهلك")</span><span class="sxs-lookup"><span data-stu-id="6582b-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="6582b-113">المؤسسات (معاينة)</span><span class="sxs-lookup"><span data-stu-id="6582b-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="6582b-114">![ملفات تعريف العميل متاجرة عمل-مستهلك](media/profile-customers-b2b.png "ملفات تعريف العميل متاجرة عمل-مستهلك")</span><span class="sxs-lookup"><span data-stu-id="6582b-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="6582b-115">إذا لم تتمكن من رؤية الإطارات المتجانبه عند تحديد **العملاء** في التنقل، سيحتاج المسؤول إلى [تعريف سمة واحدة قابلة للبحث على الأقل](search-filter-index.md) في **فهرس البحث & التصفية**.</span><span class="sxs-lookup"><span data-stu-id="6582b-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="6582b-116">البحث عن العملاء</span><span class="sxs-lookup"><span data-stu-id="6582b-116">Search for customers</span></span>

<span data-ttu-id="6582b-117">ابحث عن العملاء عن طريق إدخال اسم أو بعض السمات الأخرى في مربع البحث.</span><span class="sxs-lookup"><span data-stu-id="6582b-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="6582b-118">يعمل البحث فقط داخل كيان ملف تعريف العميل الذي تم إنشاؤه أثناء عملية توحيد البيانات.</span><span class="sxs-lookup"><span data-stu-id="6582b-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="6582b-119">كمسؤول، يمكنك تكوين سمات قابلة للبحث باستخدام الصفحة **فهرس البحث والتصفية**.</span><span class="sxs-lookup"><span data-stu-id="6582b-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="6582b-120">لمزيد من المعلومات، راجع [إدارة فهرس البحث والتصفية](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="6582b-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="6582b-121">تصفية العملاء</span><span class="sxs-lookup"><span data-stu-id="6582b-121">Filter customers</span></span>

<span data-ttu-id="6582b-122">يمكنك تصفية العملاء حسب حقول كيان ملف تعريف العميل.</span><span class="sxs-lookup"><span data-stu-id="6582b-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="6582b-123">وبشكل مشابه للبحث، سيحتاج المسؤول الخاص بك أولاً إلى تعريف الحقول كحقول قابلة للتصفية باستخدام الصفحة **فهرس البحث والتصفية**.</span><span class="sxs-lookup"><span data-stu-id="6582b-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="6582b-124">حدد **تصفية** في صفحة **العملاء**.</span><span class="sxs-lookup"><span data-stu-id="6582b-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="6582b-125">حدد الخانات الموجودة بحانب السمات التي تريد تصفية العملاء حسبها.</span><span class="sxs-lookup"><span data-stu-id="6582b-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="6582b-126">![ملفات تعريف العملاء](media/profiles-customers3.png "ملفات تعريف العملاء")</span><span class="sxs-lookup"><span data-stu-id="6582b-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="6582b-127">قم بإزالة عوامل التصفية من خلال تحديد **مسح عوامل التصفية** في صفحة **العملاء**.</span><span class="sxs-lookup"><span data-stu-id="6582b-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="6582b-128">صفحة تفاصيل العملاء</span><span class="sxs-lookup"><span data-stu-id="6582b-128">Customer details page</span></span>

<span data-ttu-id="6582b-129">حدد أي واحد من الإطارات المتجانبة للعميل لفتح **صفحة تفاصيل العملاء**.</span><span class="sxs-lookup"><span data-stu-id="6582b-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="6582b-130">تحتوي طريقة العرض هذه على معلومات موحدة للعميل المحدد.</span><span class="sxs-lookup"><span data-stu-id="6582b-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="6582b-131">تتضمن تفاصيل العميل:</span><span class="sxs-lookup"><span data-stu-id="6582b-131">Customer details include:</span></span>

-   <span data-ttu-id="6582b-132">**الإطار المتجانب لملف تعريف العميل:** يعرض هذا الإطار القيم المختلفة من كيان ملف تعريف العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="6582b-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="6582b-133">بإمكان هذه التفاصيل أن تتضمن عنوان البريد الإلكتروني والاسم والمدينة وغير ذلك.</span><span class="sxs-lookup"><span data-stu-id="6582b-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="6582b-134">**الاهتمامات المحتملة، العلامات التجارية المحتملة:** تعرض إذا قمت بتكوين إثراء من طرف أول.</span><span class="sxs-lookup"><span data-stu-id="6582b-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="6582b-135">إنها تمثل الاهتمامات والصلات المحتملة للعلامات التجارية التي قد تكون موجودة لدى عميل لديه ملف تعريف مماثل لهذا العميل.</span><span class="sxs-lookup"><span data-stu-id="6582b-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="6582b-136">لمزيد من المعلومات، راجع [إثراء ملفات تعريف العملاء باستخدام صلات الاهتمامات والعلامات التجارية](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="6582b-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="6582b-137">**المقاييس:** تظهر إذا قمت بتكوين مقياس واحد أو أكثر من نوع معين: مقاييس سمات العميل.</span><span class="sxs-lookup"><span data-stu-id="6582b-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="6582b-138">وهي تتضمن مؤشرات الأداء الأساسية المحسوبة حول العملاء على المستوي الفردي للعميل.</span><span class="sxs-lookup"><span data-stu-id="6582b-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="6582b-139">لمزيد من المعلومات، راجع [تحديد المقاييس وإدارتها](measures.md).</span><span class="sxs-lookup"><span data-stu-id="6582b-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="6582b-140">**المخطط الزمني للأنشطة:** يعرض ما إذا كنت قد قمت بتكوين الأنشطة.</span><span class="sxs-lookup"><span data-stu-id="6582b-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="6582b-141">تحتوي طريقة عرض الخط الزمني على الأنشطة التي تم فرزها بطريقة زمنية لهذا العميل، اعتبارًا من النشاط الأحدث.</span><span class="sxs-lookup"><span data-stu-id="6582b-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="6582b-142">لمزيد من المعلومات، راجع [أنشطة العميل](activities.md).</span><span class="sxs-lookup"><span data-stu-id="6582b-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="6582b-143">حدد **عودة إلى العملاء‬** للعودة إلى صفحة البحث عن العملاء.</span><span class="sxs-lookup"><span data-stu-id="6582b-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6582b-144">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="6582b-144">Next steps</span></span>

<span data-ttu-id="6582b-145">[أضف المزيد من مصادر البيانات](data-sources.md) أو [إنشاء شرائح العميل](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6582b-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]