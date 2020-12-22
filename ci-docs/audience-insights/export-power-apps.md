---
title: موصل Power Apps
description: الاتصال بـ Power Apps وPower Automate.
ms.date: 08/21/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b6ec103e29e218b2f27bfc1193300ea793a6b30b
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4404897"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="d13d0-103">موصل Microsoft Power Apps (معاينة)</span><span class="sxs-lookup"><span data-stu-id="d13d0-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="d13d0-104">إحضار ملفات تعريف العميل الموحدة إلى تطبيقاتك المخصصة باستخدام Power Apps.</span><span class="sxs-lookup"><span data-stu-id="d13d0-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="d13d0-105">توصيل Power Apps وDynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d13d0-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="d13d0-106">يُعد Customer Insights بمثابة واحدًا من العديد من [المصادر المتوفرة للبيانات الموجودة في Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="d13d0-106">Customer Insights is one of the many [available sources for data in Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="d13d0-107">ارجع إلى وثائق Power Apps لمعرفة كيفية [إضافة اتصال بيانات إلى تطبيق](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="d13d0-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="d13d0-108">يمستحسن أيضًا مراجعة [كيفية استخدام Power Apps تفويض لمعالجة مجموعات البيانات الكبيرة في تطبيقات اللوحة](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="d13d0-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="d13d0-109">الكيانات المتوفرة</span><span class="sxs-lookup"><span data-stu-id="d13d0-109">Available entities</span></span>

<span data-ttu-id="d13d0-110">بعد إضافة Customer Insights كاتصال بيانات، يمكنك اختيار الكيانات التالية في Power Apps:</span><span class="sxs-lookup"><span data-stu-id="d13d0-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="d13d0-111">العميل: لاستخدام بيانات من [ملف تعريف العميل الموحد](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d13d0-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="d13d0-112">نشاط العميل الموحد: لعرض [المخطط الزمني للنشاط](activities.md) على التطبيق.</span><span class="sxs-lookup"><span data-stu-id="d13d0-112">Unified Customer Activity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="d13d0-113">القيود</span><span class="sxs-lookup"><span data-stu-id="d13d0-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="d13d0-114">الكيانات القابلة للاسترداد</span><span class="sxs-lookup"><span data-stu-id="d13d0-114">Retrievable entities</span></span>

<span data-ttu-id="d13d0-115">يمكنك فقط استرداد كيانات **العميل** و **UnifiedActivity** و **الشرائح** من خلال موصل Power Apps.</span><span class="sxs-lookup"><span data-stu-id="d13d0-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="d13d0-116">تظهر الكيانات الأخرى لأن الموصل الأساسي يدعمها من خلال المشغلات الموجودة في Power Automate.</span><span class="sxs-lookup"><span data-stu-id="d13d0-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="d13d0-117">تفويض</span><span class="sxs-lookup"><span data-stu-id="d13d0-117">Delegation</span></span>

<span data-ttu-id="d13d0-118">يعمل التفويض لكيان العميل وكيان UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="d13d0-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="d13d0-119">تفويض كيان **العميل** entity: لاستخدام التفويض لهذا الكيان، يجب فهرسة الحقول في [فهرس البحث والتصفية](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="d13d0-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="d13d0-120">تفويض لكيان **UnifiedActivity**: يعمل التفويض لهذا الكيان فقط للحقلين **ActivityId** و **CustomerId**.</span><span class="sxs-lookup"><span data-stu-id="d13d0-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="d13d0-121">لمزيد من المعلومات حول التفويض، راجع [الوظائف والعمليات القابلة للتفويض في Power Apps](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="d13d0-121">For more information about delegation, see [Power Apps delegable functions and operations](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="d13d0-122">مثال على عنصر تحكم المعرض</span><span class="sxs-lookup"><span data-stu-id="d13d0-122">Example gallery control</span></span>

<span data-ttu-id="d13d0-123">على سبيل المثال، يمكنك إضافة ملفات تعريف العملاء إلى [عنصر تحكم المعرض](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="d13d0-123">For example, you add customer profiles to a [gallery control](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="d13d0-124">قم بإضافة عنصر تحكم **المعرض** إلى تطبيق تقوم بإنشاءه.</span><span class="sxs-lookup"><span data-stu-id="d13d0-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d13d0-125">![إضافة عنصر معرض](media/connector-powerapps9.png "إضافة عنصر معرض")</span><span class="sxs-lookup"><span data-stu-id="d13d0-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="d13d0-126">قم بتحديد **العميل** كمصدر البيانات للعناصر.</span><span class="sxs-lookup"><span data-stu-id="d13d0-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d13d0-127">![تحديد مصدر بيانات](media/choose-datasource-powerapps.png "تحديد مصدر بيانات")</span><span class="sxs-lookup"><span data-stu-id="d13d0-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="d13d0-128">يُمكنك تغيير لوحة البيانات الموجودة على اليمين لتحديد أي حقول كيان العميل الذي سوف يتم عرضه في المعرض.</span><span class="sxs-lookup"><span data-stu-id="d13d0-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="d13d0-129">إذا كنت ترغب في إظهار أي حقل من العميل المُحدد في المعرض، فقم بملء خاصية النص للتسمية:  **{Name_of_the_gallery}.{property_name}** مُحدد</span><span class="sxs-lookup"><span data-stu-id="d13d0-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="d13d0-130">مثال: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="d13d0-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="d13d0-131">لعرض المخطط الزمني الموحد لعميل، قم بإضافة عنصر معرض، وإضافة خاصية العناصر: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="d13d0-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="d13d0-132">مثال: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="d13d0-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>
