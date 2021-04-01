---
title: التحديث التزايدي لمصادر البيانات المستندة إلى Power Query
description: قم بتحديث البيانات الجديدة والمحدثة لمصادر البيانات الكبيرة استناداً إلى Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 03f76bcfc7336d8430146e8a26ffa649c6a17db0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596805"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="0bb0b-103">تحديث تزايدي لمصادر البيانات المستندة إلى Power Query</span><span class="sxs-lookup"><span data-stu-id="0bb0b-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="0bb0b-104">يوفر التحديث التزايدي لمصادر البيانات المزايا التالية:</span><span class="sxs-lookup"><span data-stu-id="0bb0b-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="0bb0b-105">**عمليات التحديث السريع** - يتم تحديث البيانات التي تم تغييرها فقط.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="0bb0b-106">على سبيل المثال، يمكنك تحديث الأيام الخمسة الماضية فقط من مجموعة بيانات تاريخية.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="0bb0b-107">**زيادة الموثوقية** - مع عمليات التحديث الأصغر، لن تحتاج إلى الحفاظ على الاتصالات بأنظمة المصادر المتقلبة لفترة طويلة، مما يقلل من مخاطر مشكلات الاتصال.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="0bb0b-108">**تقليل استهلاك الموارد** - يؤدي تحديث مجموعة فرعية فقط من إجمالي بياناتك إلى استخدام أكثر كفاءة لموارد الحوسبة ويقلل من الأثر البيئي.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="0bb0b-109">تكوين التحديث التزايدي</span><span class="sxs-lookup"><span data-stu-id="0bb0b-109">Configure incremental refresh</span></span>

<span data-ttu-id="0bb0b-110">تسمح رؤى الجمهور بالتحديث التزايدي لمصادر البيانات التي تم استيرادها من خلال Power Query والتي تدعم الاستيعاب التزايدي.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="0bb0b-111">على سبيل المثال، قواعد بيانات Azure SQL مع حقول التاريخ والوقت، والتي تشير إلى تاريخ آخر تحديث لسجلات البيانات.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="0bb0b-112">[إنشاء مصدر بيانات جديد استنادًا إلى Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="0bb0b-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="0bb0b-113">قدم اسمًا لمصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="0bb0b-114">حدد مصدر بيانات يدعم التحديث التزايدي، مثل قاعدة بيانات Azure SQL.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="0bb0b-115">حدد الكيانات أو الجداول المراد استيعابها.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="0bb0b-116">أكمل خطوات التحويل وحدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="0bb0b-117">في مربع الحوار **إعداد التحديث التزايدي**، حدد **إعداد** لفتح **إعدادات التحديث التزايدي**.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="0bb0b-118">إذا حددت **تخطي**، سيقوم المصدر البيانات بتحديث مجموعة البيانات بأكملها.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="0bb0b-119">يمكنك أيضًا تطبيق التحديث التزايدي لاحقًا عن طريق تحرير مصدر بيانات موجود.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="0bb0b-120">في **إعدادات التحديث التزايدي**، سنقوم بتكوين التحديث التزايدي لجميع الكيانات التي حددتها عند إنشاء مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0bb0b-121">![تكوين الكيانات في مصدر بيانات للتحديث التزايدي](media/incremental-refresh-settings.png "تكوين الكيانات في مصدر بيانات للتحديث التزايدي")</span><span class="sxs-lookup"><span data-stu-id="0bb0b-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="0bb0b-122">حدد كيانًا، وقم بتوفير التفاصيل التالية:</span><span class="sxs-lookup"><span data-stu-id="0bb0b-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="0bb0b-123">**تحديد المفتاح الأساسي**: حدد مفتاحًا أساسيًا للكيان أو الجدول.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="0bb0b-124">**حقل تحديد "تاريخ التحديث الأخير"**: سيعرض هذا الحقل سمات من نوع التاريخ أو الوقت.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="0bb0b-125">حدد سمة تشير إلى الوقت الذي تم فيه تحديث السجلات أخر مرة.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="0bb0b-126">سيتم استخدامه لتحديد السجلات التي تقع ضمن الإطار الزمني للتحديث التزايدي.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="0bb0b-127">**التحقق من وجود تحديثات كل‬**: حدد المدة التي تريدها للإطار الزمني للتحديث التزايدي.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="0bb0b-128">حدد **حفظ** لإكمال إنشاء مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="0bb0b-129">سيكون تحديث البيانات الأولي تحديثًا كاملاً.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="0bb0b-130">بعد ذلك، يتم تحديث البيانات التزايدي كما تم تكوينه في الخطوة السابقة.</span><span class="sxs-lookup"><span data-stu-id="0bb0b-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]