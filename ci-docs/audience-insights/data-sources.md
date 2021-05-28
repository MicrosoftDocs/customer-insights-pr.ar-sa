---
title: استخدام مصادر بيانات لاستيعاب البيانات
description: تعرف على كيفية استيراد البيانات من مصادر متعددة.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085514"
---
# <a name="data-sources-overview"></a><span data-ttu-id="41ef5-103">نظرة عامة مصادر البيانات</span><span class="sxs-lookup"><span data-stu-id="41ef5-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="41ef5-104">تتصل قدرة رؤى الجمهور في Dynamics 365 Customer Insights بالبيانات من مجموعة واسعة من المصادر.</span><span class="sxs-lookup"><span data-stu-id="41ef5-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="41ef5-105">غالبًا ما يشار إلى الاتصال بمصدر البيانات على أنه عملية *استيعاب بيانات*.</span><span class="sxs-lookup"><span data-stu-id="41ef5-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="41ef5-106">بعد استيعاب البيانات، يمكنك [توحيدها](data-unification.md) واتخاذ إجراءات بشأنها.</span><span class="sxs-lookup"><span data-stu-id="41ef5-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="41ef5-107">إضافة مصدر بيانات</span><span class="sxs-lookup"><span data-stu-id="41ef5-107">Add a data source</span></span>

<span data-ttu-id="41ef5-108">راجع المقالات التفصيلية حول كيفيه أضافه مصدر البيانات، وذلك حسب الخيار الذي تختاره.</span><span class="sxs-lookup"><span data-stu-id="41ef5-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="41ef5-109">يمكنك إضافة مصدر البيانات بثلاثة طرق رئيسية:</span><span class="sxs-lookup"><span data-stu-id="41ef5-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="41ef5-110">عبر العشرات من موصلات Power Query</span><span class="sxs-lookup"><span data-stu-id="41ef5-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="41ef5-111">من مجلد نموذج البيانات العامة</span><span class="sxs-lookup"><span data-stu-id="41ef5-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="41ef5-112">من مخزن Common Data Service الخاص بك</span><span class="sxs-lookup"><span data-stu-id="41ef5-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="41ef5-113">إضافة البيانات من مصادر البيانات المحلية</span><span class="sxs-lookup"><span data-stu-id="41ef5-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="41ef5-114">يتم دعم استيعاب البيانات من مصادر البيانات المحلية في Audience Insights استنادًا إلى تدفقات بيانات Power Platform.</span><span class="sxs-lookup"><span data-stu-id="41ef5-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="41ef5-115">يمكن تمكين تدفقات البيانات في Customer Insights عن طريق [توفير عنوان URL لبيئة Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) عند إعداد البيئة.</span><span class="sxs-lookup"><span data-stu-id="41ef5-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="41ef5-116">ستستخدم مصادر البيانات التي تم إنشاؤها بعد ربط بيئة Dataverse بـ Customer Insights [تدفقات بيانات Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) بشكل افتراضي.</span><span class="sxs-lookup"><span data-stu-id="41ef5-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="41ef5-117">تدعم تدفقات البيانات الاتصال المحلي باستخدام بوابة البيانات.</span><span class="sxs-lookup"><span data-stu-id="41ef5-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="41ef5-118">قم بإزالة وإعادة إنشاء مصادر البيانات التي كانت موجودة قبل ربط بيئة Dataverse لأجل [استخدام بوابات البيانات المحلية](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="41ef5-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="41ef5-119">ستظهر بوابات البيانات من بيئة Power BI أو Power Apps موجودة ويمكنك إعادة استخدامها في Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="41ef5-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="41ef5-120">تعرض صفحة مصادر البيانات ارتباطات للانتقال إلى بيئة Power Platform، حيث يمكنك عرض وتكوين بوابات البيانات المحلية.</span><span class="sxs-lookup"><span data-stu-id="41ef5-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="41ef5-121">مراجعة البيانات المستوعبة</span><span class="sxs-lookup"><span data-stu-id="41ef5-121">Review ingested data</span></span>

<span data-ttu-id="41ef5-122">سترى اسم كل مصدر بيانات تم إدخاله وحالته وآخر مرة تم فيها تحديث البيانات لهذا المصدر.</span><span class="sxs-lookup"><span data-stu-id="41ef5-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="41ef5-123">يمكنك فرز قائمة مصادر البيانات حسب كل عمود.</span><span class="sxs-lookup"><span data-stu-id="41ef5-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="41ef5-124">![مصدر بيانات تمت إضافته](media/configure-data-datasource-added.png "مصدر بيانات تمت إضافته")</span><span class="sxs-lookup"><span data-stu-id="41ef5-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="41ef5-125">الحالة </span><span class="sxs-lookup"><span data-stu-id="41ef5-125">Status</span></span>  |<span data-ttu-id="41ef5-126">الوصف </span><span class="sxs-lookup"><span data-stu-id="41ef5-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="41ef5-127">تمت بنجاح</span><span class="sxs-lookup"><span data-stu-id="41ef5-127">Successful</span></span>   |<span data-ttu-id="41ef5-128">يتم استيعاب مصادر البيانات بنجاح إذا تم ذكر الوقت في العمود **تم تحديثه**.</span><span class="sxs-lookup"><span data-stu-id="41ef5-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="41ef5-129">لم تبدأ</span><span class="sxs-lookup"><span data-stu-id="41ef5-129">Not started</span></span>   |<span data-ttu-id="41ef5-130">لا يحتوي مصدر البيانات على بيانات تم استيعابها أو ما زالت في وضع المسودة.</span><span class="sxs-lookup"><span data-stu-id="41ef5-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="41ef5-131">تحديث</span><span class="sxs-lookup"><span data-stu-id="41ef5-131">Refreshing</span></span>    |<span data-ttu-id="41ef5-132">استيعاب البيانات قيد التقدم.</span><span class="sxs-lookup"><span data-stu-id="41ef5-132">Data ingestion is in progress.</span></span> <span data-ttu-id="41ef5-133">يُمكنك إلغاء هذه العملية من خلال تحديد **إيقاف التحديث** في عمود **إجراءات**.</span><span class="sxs-lookup"><span data-stu-id="41ef5-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="41ef5-134">يؤدي إيقاف عملية تحديث مصدر البيانات إلى إرجاعها إلى حالة التحديث الأخيرة.</span><span class="sxs-lookup"><span data-stu-id="41ef5-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="41ef5-135">‏‏فاشلة</span><span class="sxs-lookup"><span data-stu-id="41ef5-135">Failed</span></span>     |<span data-ttu-id="41ef5-136">تسبب استيعاب البيانات في تشغيل أخطاء.</span><span class="sxs-lookup"><span data-stu-id="41ef5-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="41ef5-137">حدد القيمة في عمود **الحالة** لأي مصدر بيانات لمراجعة المزيد من التفاصيل.</span><span class="sxs-lookup"><span data-stu-id="41ef5-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="41ef5-138">في جزء **تفاصيل التقدم**، قم بتوسيع **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="41ef5-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="41ef5-139">حدد **راجع التفاصيل** لمراجعة المزيد من التفاصيل حول حالة التحديث، بما في ذلك تفاصيل الخطأ وتحديثات عملية انتقال البيانات من الخادم‬‬.</span><span class="sxs-lookup"><span data-stu-id="41ef5-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="41ef5-140">قد يستغرق تحميل البيانات بعض الوقت.</span><span class="sxs-lookup"><span data-stu-id="41ef5-140">Loading data can take some time.</span></span> <span data-ttu-id="41ef5-141">بعد الانتهاء من التحديث بنجاح، يُمكنك مراجعة البيانات المستوعبة من صفحة **الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="41ef5-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="41ef5-142">للمزيد من المعلومات، راجع [التفاصيل](entities.md).</span><span class="sxs-lookup"><span data-stu-id="41ef5-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="41ef5-143">تحديث مصدر البيانات</span><span class="sxs-lookup"><span data-stu-id="41ef5-143">Refresh a data source</span></span>

<span data-ttu-id="41ef5-144">يمكن تحديث مصادر البيانات حسب جدول تلقائي أو يمكن تحديثها يدويًا عند الطلب.</span><span class="sxs-lookup"><span data-stu-id="41ef5-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="41ef5-145">انتقل إلى **المسؤول** > **النظام** > [**الجدول**](system.md#schedule-tab) لتكوين عمليات تحديث مجدولة لجميع مصادر البيانات التي تم استيعابها.</span><span class="sxs-lookup"><span data-stu-id="41ef5-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="41ef5-146">لتحديث مصدر البيانات حسب الطلب، اتبع الخطوات التالية:</span><span class="sxs-lookup"><span data-stu-id="41ef5-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="41ef5-147">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="41ef5-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="41ef5-148">حدد علامة القطع الرأس المجاورة لمصدر البيانات الذي تريد تحديثه، وحدد **تحديث** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="41ef5-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="41ef5-149">تم تشغيل مصدر البيانات الآن للحصول على تحديث يدوي.</span><span class="sxs-lookup"><span data-stu-id="41ef5-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="41ef5-150">سيؤدي تحديث مصدر البيانات إلى تحديث كل من مخطط الكيان والبيانات لجميع الكيانات المحددة في مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="41ef5-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="41ef5-151">حدد **إيقاف التحديث** إذا كنت تريد إلغاء تحديث موجود وسيعود مصدر البيانات إلى حالة التحديث الأخيرة.</span><span class="sxs-lookup"><span data-stu-id="41ef5-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="41ef5-152">حذف مصدر البيانات</span><span class="sxs-lookup"><span data-stu-id="41ef5-152">Delete a data source</span></span>

1. <span data-ttu-id="41ef5-153">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="41ef5-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="41ef5-154">حدد علامة الحذف الرأسية المجاورة لمصدر البيانات الذي تريد إزالته وحدد **حذف** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="41ef5-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="41ef5-155">قم بتأكيد الحذف.</span><span class="sxs-lookup"><span data-stu-id="41ef5-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
