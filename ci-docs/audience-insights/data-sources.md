---
title: استخدام مصادر بيانات لاستيعاب البيانات
description: تعرف على كيفية استيراد البيانات من مصادر متعددة.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643937"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="f8d8a-103">نظرة عامة حول مصادر البيانات</span><span class="sxs-lookup"><span data-stu-id="f8d8a-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f8d8a-104">تتصل قدرة رؤى الجمهور في Dynamics 365 Customer Insights بالبيانات من مجموعة واسعة من المصادر.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="f8d8a-105">غالبًا ما يشار إلى الاتصال بمصدر البيانات على أنه عملية *استيعاب بيانات*.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="f8d8a-106">بعد استيعاب البيانات، يمكنك [توحيدها](data-unification.md) واتخاذ إجراءات بشأنها.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="f8d8a-107">إضافة مصدر بيانات</span><span class="sxs-lookup"><span data-stu-id="f8d8a-107">Add a data source</span></span>

<span data-ttu-id="f8d8a-108">راجع المقالات التفصيلية حول كيفيه أضافه مصدر البيانات، وذلك حسب الخيار الذي تختاره.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="f8d8a-109">يمكنك إضافة مصدر البيانات بثلاثة طرق رئيسية:</span><span class="sxs-lookup"><span data-stu-id="f8d8a-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="f8d8a-110">عبر العشرات من موصلات Power Query</span><span class="sxs-lookup"><span data-stu-id="f8d8a-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="f8d8a-111">من مجلد نموذج البيانات العامة</span><span class="sxs-lookup"><span data-stu-id="f8d8a-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="f8d8a-112">من مخزن Common Data Service الخاص بك</span><span class="sxs-lookup"><span data-stu-id="f8d8a-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="f8d8a-113">لا يمكنك إضافة بيانات من مصادر البيانات المحلية حتى الآن.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="f8d8a-114">مراجعة البيانات المستوعبة</span><span class="sxs-lookup"><span data-stu-id="f8d8a-114">Review ingested data</span></span>

<span data-ttu-id="f8d8a-115">سترى اسم كل مصدر بيانات تم إدخاله وحالته وآخر مرة تم فيها تحديث البيانات لهذا المصدر.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="f8d8a-116">يمكنك فرز قائمة مصادر البيانات حسب كل عمود.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f8d8a-117">![مصدر بيانات تمت إضافته](media/configure-data-datasource-added.png "مصدر بيانات تمت إضافته")</span><span class="sxs-lookup"><span data-stu-id="f8d8a-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="f8d8a-118">الحالة </span><span class="sxs-lookup"><span data-stu-id="f8d8a-118">Status</span></span>  |<span data-ttu-id="f8d8a-119">الوصف </span><span class="sxs-lookup"><span data-stu-id="f8d8a-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="f8d8a-120">تمت بنجاح</span><span class="sxs-lookup"><span data-stu-id="f8d8a-120">Successful</span></span>   |<span data-ttu-id="f8d8a-121">يتم استيعاب مصادر البيانات بنجاح إذا تم ذكر الوقت في العمود **تم تحديثه**.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="f8d8a-122">لم تبدأ</span><span class="sxs-lookup"><span data-stu-id="f8d8a-122">Not started</span></span>   |<span data-ttu-id="f8d8a-123">لا يحتوي مصدر البيانات على بيانات تم استيعابها أو ما زالت في وضع المسودة.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="f8d8a-124">تحديث</span><span class="sxs-lookup"><span data-stu-id="f8d8a-124">Refreshing</span></span>    |<span data-ttu-id="f8d8a-125">استيعاب البيانات قيد التقدم.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-125">Data ingestion is in progress.</span></span> <span data-ttu-id="f8d8a-126">يُمكنك إلغاء هذه العملية من خلال تحديد **إيقاف التحديث** في عمود **إجراءات**.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="f8d8a-127">يؤدي إيقاف عملية تحديث مصدر البيانات إلى إرجاعها إلى حالة التحديث الأخيرة.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="f8d8a-128">‏‏فاشلة</span><span class="sxs-lookup"><span data-stu-id="f8d8a-128">Failed</span></span>     |<span data-ttu-id="f8d8a-129">تسبب استيعاب البيانات في تشغيل أخطاء.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="f8d8a-130">حدد **حالة التحديث** لمراجعة المزيد من التفاصيل حول حالة التحديث، بما في ذلك تفاصيل الخطأ وتحديثات عملية انتقال البيانات من الخادم‬‬.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="f8d8a-131">قد يستغرق تحميل البيانات بعض الوقت.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-131">Loading data can take some time.</span></span> <span data-ttu-id="f8d8a-132">بعد الانتهاء من التحديث بنجاح، يُمكنك مراجعة البيانات المستوعبة من صفحة **الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="f8d8a-133">للمزيد من المعلومات، راجع [التفاصيل](entities.md).</span><span class="sxs-lookup"><span data-stu-id="f8d8a-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="f8d8a-134">تحديث مصدر البيانات</span><span class="sxs-lookup"><span data-stu-id="f8d8a-134">Refresh a data source</span></span>

<span data-ttu-id="f8d8a-135">يمكن تحديث مصادر البيانات حسب جدول تلقائي أو يمكن تحديثها يدويًا عند الطلب.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="f8d8a-136">انتقل إلى **المسؤول** > **النظام** > [**الجدول**](system.md#schedule-tab) لتكوين عمليات تحديث مجدولة لجميع مصادر البيانات التي تم استيعابها.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="f8d8a-137">لتحديث مصدر البيانات حسب الطلب، اتبع الخطوات التالية:</span><span class="sxs-lookup"><span data-stu-id="f8d8a-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="f8d8a-138">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="f8d8a-139">حدد علامة القطع الرأس المجاورة لمصدر البيانات الذي تريد تحديثه، وحدد **تحديث** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="f8d8a-140">تم تشغيل مصدر البيانات الآن للحصول على تحديث يدوي.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="f8d8a-141">سيؤدي تحديث مصدر البيانات إلى تحديث مخطط الكيان بالإضافة إلى البيانات الخاصة بكافة الكيانات المحددة في مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="f8d8a-142">حدد **إيقاف التحديث** إذا كنت تريد إلغاء تحديث موجود وسيعود مصدر البيانات إلى حالة التحديث الأخيرة.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="f8d8a-143">حذف مصدر البيانات</span><span class="sxs-lookup"><span data-stu-id="f8d8a-143">Delete a data source</span></span>

1. <span data-ttu-id="f8d8a-144">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="f8d8a-145">حدد علامة الحذف الرأسية المجاورة لمصدر البيانات الذي تريد إزالته وحدد **حذف** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="f8d8a-146">قم بتأكيد الحذف.</span><span class="sxs-lookup"><span data-stu-id="f8d8a-146">Confirm your deletion.</span></span>
