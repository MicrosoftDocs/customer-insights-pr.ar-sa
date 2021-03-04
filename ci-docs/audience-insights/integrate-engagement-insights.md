---
title: تكامل بيانات الويب من رؤى المشاركة مع رؤى الجمهور
description: إحضار معلومات ويب حول العملاء من رؤى المشاركة إلى رؤى الجمهور.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mukeshpo
manager: shellyha
ms.openlocfilehash: ba1cf6c7e85b8fe90baf34018f1309095573adf1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267660"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="9531f-103">تكامل بيانات الويب من رؤى المشاركة مع رؤى الجمهور</span><span class="sxs-lookup"><span data-stu-id="9531f-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="9531f-104">يستخدم العملاء في أغلب الأحيان مواقع الويب للقيام بمعاملاتهم اليومية عبر الإنترنت.</span><span class="sxs-lookup"><span data-stu-id="9531f-104">Customers often do their day to day transactions online using web sites.</span></span> <span data-ttu-id="9531f-105">تُعتبر إمكانية رؤى المشاركة في Dynamics 365 Customer Insights حلاً مفيدًا لتكامل بيانات الويب كمصدر.</span><span class="sxs-lookup"><span data-stu-id="9531f-105">The engagement insights capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="9531f-106">بالإضافة إلى البيانات الخاصة بالمعاملات أو البيانات السكانية أو السلوكية، يمكننا رؤية أنشطة على الويب في ملفات تعريف العملاء الموحدة.</span><span class="sxs-lookup"><span data-stu-id="9531f-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="9531f-107">يمكننا استخدام ملف التعريف هذا للحصول على رؤى إضافية مثل الشرائح أو المقاييس أو التنبؤات لتنشيط الجمهور.</span><span class="sxs-lookup"><span data-stu-id="9531f-107">We can use this profile to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="9531f-108">تصف هذه المقالة الخطوات اللازمة لإحضار بيانات نشاط الويب الخاصة بالعميل من رؤى المشاركة إلى بيئة رؤى الجمهور الحالية.</span><span class="sxs-lookup"><span data-stu-id="9531f-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="9531f-109">في هذا المثال، نفترض أنه باستطاعة البيئة أن تحتوي على ملفات تعريف العملاء الموحدة.</span><span class="sxs-lookup"><span data-stu-id="9531f-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="9531f-110">تم توحيد ملفات التعريف بواسطة مصادر من الاستطلاعات ومبيعات التجزئة ونظام إصدار التذاكر.</span><span class="sxs-lookup"><span data-stu-id="9531f-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="9531f-111">كما تعرض الأنشطة ذات الصلة للعملاء.</span><span class="sxs-lookup"><span data-stu-id="9531f-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="9531f-112">نريد الآن معرفة ما إذا كان العميل يزور مواقعنا على الويب ويفهم أنشطتها.</span><span class="sxs-lookup"><span data-stu-id="9531f-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="9531f-113">تشمل الأنشطة، على سبيل المثال، مواقع ويب التي تمت زيارتها أو صفحات المنتجات التي تم عرضها من ارتباط تم استلامه في رسالة بريد إلكتروني.</span><span class="sxs-lookup"><span data-stu-id="9531f-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9531f-114">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="9531f-114">Prerequisites</span></span>

<span data-ttu-id="9531f-115">لتمكين تكامل البيانات من رؤى المشاركة، يلزم تحقيق بعض المتطلبات الأساسية:</span><span class="sxs-lookup"><span data-stu-id="9531f-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="9531f-116">تكامل SDK رؤى المشاركة مع موقعك على الويب.</span><span class="sxs-lookup"><span data-stu-id="9531f-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="9531f-117">لمزيد من المعلومات، راجع [بدء استخدام SDK‎ الويب](../engagement-insights/instrument-website.md).</span><span class="sxs-lookup"><span data-stu-id="9531f-117">For more information, see [Get started with the web SDK](../engagement-insights/instrument-website.md).</span></span>
- <span data-ttu-id="9531f-118">يتطلب تصدير أحداث الويب من رؤى المشاركة الوصول إلى حساب تخزين ADLS Gen 2 الذي سيتم استخدامه لاستيعاب بيانات أحداث الويب في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="9531f-118">Exporting web events from engagement insights requires access to an ADLS Gen 2 storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="9531f-119">لمزيد من المعلومات، راجع [تصدير الأحداث](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="9531f-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="9531f-120">تكوين الأحداث المحسّنة في رؤى المشاركة</span><span class="sxs-lookup"><span data-stu-id="9531f-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="9531f-121">بعد قيام المسؤول بتجهيز موقع ويب باستخدام SDK رؤى المشاركة، يتم تجميع *الأحداث الأساسية* عندما يقوم المستخدم بعرض صفحة ويب أو النقر في مكان ما.</span><span class="sxs-lookup"><span data-stu-id="9531f-121">After an administrator instrumented a website with the engagement insights SDK, *base events* are gathered when a user views a web page or clicks somewhere.</span></span> <span data-ttu-id="9531f-122">تميل الأحداث الأساسية إلى الاحتواء على العديد من التفاصيل.</span><span class="sxs-lookup"><span data-stu-id="9531f-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="9531f-123">بحسب حالة الاستخدام، ستحتاج فقط إلى مجموعة فرعية من البيانات في حدث أساسي.</span><span class="sxs-lookup"><span data-stu-id="9531f-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="9531f-124">تسمح لك رؤى المشاركة بإنشاء *أحداث محسّنة* تحتوي فقط على خصائص حدث أساسي تحدده.</span><span class="sxs-lookup"><span data-stu-id="9531f-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="9531f-125">لمزيد من المعلومات، راجع [إنشاء الأحداث المحسّنة وتعديلها](../engagement-insights/refined-events.md).</span><span class="sxs-lookup"><span data-stu-id="9531f-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="9531f-126">اعتبارات عند إنشاء أحداث محسّنة:</span><span class="sxs-lookup"><span data-stu-id="9531f-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="9531f-127">توفير اسم ذي معنى للحدث المحسّن.</span><span class="sxs-lookup"><span data-stu-id="9531f-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="9531f-128">يتم استخدامه كاسم نشاط في رؤى المشاركة.</span><span class="sxs-lookup"><span data-stu-id="9531f-128">It's be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="9531f-129">حدد الخصائص التالية على الأقل لإنشاء نشاط في رؤى الجمهور:</span><span class="sxs-lookup"><span data-stu-id="9531f-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="9531f-130">Signal.Action.Name - الإشارة إلى تفاصيل النشاط</span><span class="sxs-lookup"><span data-stu-id="9531f-130">Signal.Action.Name - indicating the activity details</span></span>
    - <span data-ttu-id="9531f-131">Signal.User.Id - يُستخدم للتعيين بواسطة معرف العميل</span><span class="sxs-lookup"><span data-stu-id="9531f-131">Signal.User.Id - used to map with the customer ID</span></span>
    - <span data-ttu-id="9531f-132">Signal.View.Uri - يُستخدم كعنوان ويب كأساس للشرائح أو المقاييس</span><span class="sxs-lookup"><span data-stu-id="9531f-132">Signal.View.Uri - used as a web address as a basis for segments or measures</span></span>
    - <span data-ttu-id="9531f-133">Signal.Export.Id - لاستخدامه كمفتاح أساسي للأحداث</span><span class="sxs-lookup"><span data-stu-id="9531f-133">Signal.Export.Id - to use as a primary key for events</span></span> <!-- system generated, do we need to list?-->
    - <span data-ttu-id="9531f-134">Signal.Timestamp - لتحديد تاريخ ووقت النشاط</span><span class="sxs-lookup"><span data-stu-id="9531f-134">Signal.Timestamp - to determine the date and time for the activity</span></span>

<span data-ttu-id="9531f-135">حدد عوامل التصفية للتركيز على الأحداث والصفحات التي تهم حالة الاستخدام.</span><span class="sxs-lookup"><span data-stu-id="9531f-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="9531f-136">في هذا المثال، سوف نستخدم اسم الإجراء "ترويج بالبريد الإلكتروني".</span><span class="sxs-lookup"><span data-stu-id="9531f-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="9531f-137">تصدير أحداث الويب المحسّنة</span><span class="sxs-lookup"><span data-stu-id="9531f-137">Export the Refined Web Events</span></span> 

<span data-ttu-id="9531f-138">بعد تعريف الحدث المحسّن، يجب تكوين تصدير بيانات الحدث إلى Azure Data Lake Storage، الذي يمكن تعيينه كمصدر بيانات لاستيعابه في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="9531f-138">After defining the refined event is defined, you have to configure the export of the event data to an Azure Data Lake Storage, that can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="9531f-139">تحدث عمليات التصدير بشكل ثابت مع تدفق الأحداث من خاصية الويب.</span><span class="sxs-lookup"><span data-stu-id="9531f-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="9531f-140">لمزيد من المعلومات، راجع [تصدير الأحداث](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="9531f-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="9531f-141">استيعاب بيانات الأحداث لرؤى الجمهور</span><span class="sxs-lookup"><span data-stu-id="9531f-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="9531f-142">بعد أن قمت بتعريف الحدث المحسّن وتكوين تصديره، سننتقل إلى استيعاب البيانات لرؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="9531f-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="9531f-143">يلزمك إنشاء مصدر بيانات جديد بالاستناد إلى مجلد نموذج البيانات العامة.</span><span class="sxs-lookup"><span data-stu-id="9531f-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="9531f-144">أدخل تفاصيل حساب التخزين الذي تقوم بتصدير الأحداث إليه.</span><span class="sxs-lookup"><span data-stu-id="9531f-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="9531f-145">في الملف *default.cdm.json*، حدد الحدث المحسّن لاستيعابه وإنشاء كيان في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="9531f-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="9531f-146">لمزيد من المعلومات، راجع [الاتصال بمجلد نموذج البيانات العامة باستخدام حساب Azure Data Lake](connect-common-data-model.md)</span><span class="sxs-lookup"><span data-stu-id="9531f-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md)</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="9531f-147">ربط بيانات الأحداث المحسّنة كنشاط لملف تعريف العميل</span><span class="sxs-lookup"><span data-stu-id="9531f-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="9531f-148">بعد إكمال استيعاب الكيان، يمكنك تكوين النشاط لملف تعريف العميل.</span><span class="sxs-lookup"><span data-stu-id="9531f-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="9531f-149">لمزيد من المعلومات، راجع [أنشطة العميل](activities.md).</span><span class="sxs-lookup"><span data-stu-id="9531f-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="صفحة الأنشطة مع الجزء الموسع "تحرير النشاط" وحقول تمت تعبئتها بالبيانات.":::

<span data-ttu-id="9531f-151">تكوين النشاط الجديد من خلال التعيين التالي:</span><span class="sxs-lookup"><span data-stu-id="9531f-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="9531f-152">**المفتاح الأساسي:** Signal.Export.Id، معرف فريد يتوفر لك سجل حدث في رؤى المشاركة.</span><span class="sxs-lookup"><span data-stu-id="9531f-152">**Primary Key:** Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="9531f-153">يتم إنشاء هذه الخاصية بشكل تلقائي.</span><span class="sxs-lookup"><span data-stu-id="9531f-153">This property is automatically generated.</span></span>

- <span data-ttu-id="9531f-154">**الطابع الزمني:** Signal.Timestamp في خاصية الحدث.</span><span class="sxs-lookup"><span data-stu-id="9531f-154">**Timestamp:** Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="9531f-155">**الحدث:** Signal.Name، اسم الحدث الذي تريد تعقبه.</span><span class="sxs-lookup"><span data-stu-id="9531f-155">**Event:** Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="9531f-156">**عنوان ويب:** Signal.View.Uri يشير إلى uri الصفحة التي أنشأت الحدث.</span><span class="sxs-lookup"><span data-stu-id="9531f-156">**Web address:** Signal.View.Uri referring to the uri of the page that created the event.</span></span>

- <span data-ttu-id="9531f-157">**التفاصيل:** Signal.Action.Name لتمثيل المعلومات لربطها بالحدث.</span><span class="sxs-lookup"><span data-stu-id="9531f-157">**Details:** Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="9531f-158">تشير الخاصية المحددة في هذه الحالة إلى أن الحدث هو للترويج بالبريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="9531f-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="9531f-159">**نوع النشاط:** في هذا المثال، نختار نوع النشاط الموجود WebLog.</span><span class="sxs-lookup"><span data-stu-id="9531f-159">**Activity type:** In this example, we choose the exsting activity type WebLog.</span></span> <span data-ttu-id="9531f-160">هذا التحديد هو خيار تصفية مفيد لتشغيل نماذج التنبؤ أو إنشاء شرائح استنادًا إلى نوع النشاط هذا.</span><span class="sxs-lookup"><span data-stu-id="9531f-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="9531f-161">**إعداد العلاقة:** يقوم هذا الإعداد المهم بربط النشاط بملفات تعريف العميل الموجودة.</span><span class="sxs-lookup"><span data-stu-id="9531f-161">**Set up relationship:** This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="9531f-162">**Signal.User.Id** هو المعرف المكوّن في SDK لتجميعه والمرتبط بمعرف المستخدم في مصادر البيانات الأخرى التي تم تكوينها في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="9531f-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="9531f-163">في هذا المثال، نقوم بتكوين العلاقة بين Signal.User.Id وRetailCustomers:CustomerRetailId، وهو المفتاح الأساسي الذي تم تعريفه في خطوة الخريطة لعملية توحيد البيانات.</span><span class="sxs-lookup"><span data-stu-id="9531f-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was deinfed in the map step of the data unification process.</span></span>


<span data-ttu-id="9531f-164">بعد معالجة الأنشطة، يمكنك مراجعة سجلات العملاء وفتح بطاقة عميل لرؤية الأنشطة من رؤى المشاركة في المخطط الزمني.</span><span class="sxs-lookup"><span data-stu-id="9531f-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="9531f-165">للعثور على معرف عميل لديه نشاط رؤى مشاركة، انتقل إلى **الكيانات** وعاين البيانات لكيان UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="9531f-165">To find a customer id that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="9531f-166">ActivityTypeDisplay = WebLog يحتوي على نشاط رؤى المشاركة المكوّن في المثال أعلاه.</span><span class="sxs-lookup"><span data-stu-id="9531f-166">ActivityTypeDisplay = WebLog contain the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="9531f-167">انسخ معرف العميل لأحد هذه السجلات ولذلك المعرف على صفحة **العملاء**.</span><span class="sxs-lookup"><span data-stu-id="9531f-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9531f-168">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="9531f-168">Next Steps</span></span>

<span data-ttu-id="9531f-169">يمكنك الآن إنشاء [شرائح](segments.md) و[مقاييس](measures.md) و[تنبؤات](predictions.md) لإنشاء اتصال ذي معنى مع العملاء.</span><span class="sxs-lookup"><span data-stu-id="9531f-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]