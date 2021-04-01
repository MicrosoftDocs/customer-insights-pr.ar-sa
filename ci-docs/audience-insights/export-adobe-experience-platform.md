---
title: تصدير بيانات Customer Insights إلى Adobe Experience Platform
description: اعرف كيفية استخدام شرائح رؤى الجمهور في Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596253"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="c36a6-103">استخدام شرائح Customer Insights في Adobe Experience Platform (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="c36a6-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="c36a6-104">بصفتك مستخدم رؤى الجمهور في Dynamics 365 Customer Insights، من المحتمل أن تكون قد أنشأت شرائح لزيادة مستوى فعالية حملاتك التسويقية من خلال استهداف شرائح جمهور ذات صلة.</span><span class="sxs-lookup"><span data-stu-id="c36a6-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="c36a6-105">لاستخدام شريحة من رؤى الجمهور في Adobe Experience Platform وتطبيقات مثل Adobe Campaign Standard، يلزمك اتباع بعض الخطوات الملخصة في هذه المقالة.</span><span class="sxs-lookup"><span data-stu-id="c36a6-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="مخطط العملية للخطوات الملخصة في هذه المقالة.":::

## <a name="prerequisites"></a><span data-ttu-id="c36a6-107">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="c36a6-107">Prerequisites</span></span>

-   <span data-ttu-id="c36a6-108">ترخيص Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="c36a6-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="c36a6-109">ترخيص Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="c36a6-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="c36a6-110">ترخيص Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c36a6-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="c36a6-111">حساب Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="c36a6-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="c36a6-112">نظرة عامة حول الحملة</span><span class="sxs-lookup"><span data-stu-id="c36a6-112">Campaign Overview</span></span>

<span data-ttu-id="c36a6-113">لتكوين فهم أفضل لكيفية استخدام شرائح من رؤى الجمهور في Adobe Experience Platform، سنلقي نظرة على عينة حملة وهمية.</span><span class="sxs-lookup"><span data-stu-id="c36a6-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="c36a6-114">لنفترض أن شركتك تقدم خدمة شهرية قائمة على اشتراك لعملائك في الولايات المتحدة.</span><span class="sxs-lookup"><span data-stu-id="c36a6-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="c36a6-115">تريد تحديد العملاء الذين من المقرر تجديد اشتراكاتهم في الأيام الثمانية القادمة، ولكنهم لم يجددوا اشتراكهم بعد.</span><span class="sxs-lookup"><span data-stu-id="c36a6-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="c36a6-116">للمحافظة على هؤلاء العملاء، تريد إرسال عرض ترويجي لهم عبر البريد الإلكتروني، باستخدام Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c36a6-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="c36a6-117">في هذا المثال، نريد تشغيل حملة البريد الإلكتروني الترويجية مرة واحدة.</span><span class="sxs-lookup"><span data-stu-id="c36a6-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="c36a6-118">لا تتناول هذه المقالة حالة استخدام تشغيل الحملة أكثر من مرة.</span><span class="sxs-lookup"><span data-stu-id="c36a6-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="c36a6-119">تحديد الجمهور المستهدف</span><span class="sxs-lookup"><span data-stu-id="c36a6-119">Identify your target audience</span></span>

<span data-ttu-id="c36a6-120">في السيناريو لدينا، نفترض أن عناوين البريد الإلكتروني الخاصة بالعملاء متوفرة في رؤى الجمهور‬، وأنه قد تم تحليل وتفضيلاتهم الترويجية لتحديد أعضاء الشريحة.</span><span class="sxs-lookup"><span data-stu-id="c36a6-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="c36a6-121">تسمى [الشريحة التي حددتها في رؤى الجمهور‬](segments.md) is called **ChurnProneCustomers**، وتريد إرسال العرض الترويجي إلى هؤلاء العملاء بالبريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="c36a6-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="لقطة شاشة لصفحة الشرائح باستخدام الشريحة ChurnProneCustomers التي تم إنشاؤها.":::

<span data-ttu-id="c36a6-123">سيحتوي العرض الذي تريد إرسال بالبريد الإلكتروني على الاسم الأول واسم العائلة وتاريخ انتهاء اشتراك العميل.</span><span class="sxs-lookup"><span data-stu-id="c36a6-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="c36a6-124">كما يعلم العملاء بالتخفيض الذي سيحصلون عليه في حالة قيامهم بتجديد اشتراكهم قبل انتهاء مدته.</span><span class="sxs-lookup"><span data-stu-id="c36a6-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="c36a6-125">تصدير الجمهور المستهدف</span><span class="sxs-lookup"><span data-stu-id="c36a6-125">Export your target audience</span></span>

<span data-ttu-id="c36a6-126">ومن خلال تحديد الجمهور المستهدف، يمكننا تكوين التصدير من رؤى الجمهور إلى حساب Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="c36a6-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="c36a6-127">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.</span><span class="sxs-lookup"><span data-stu-id="c36a6-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c36a6-128">في الإطار المتجانب **Azure Blob Storage**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="c36a6-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="الإطار المتجانب لتكوين Azure Blob Storage.":::

1. <span data-ttu-id="c36a6-130">أدخل **اسمًا معروضًا** لوجهة التصدير الجديدة هذه، ثم أدخل **اسم الحساب** و **مفتاح الحساب** و **الحاوية** لحساب Azure Blob Storage الذي تريد تصدير الشريحة إليه.</span><span class="sxs-lookup"><span data-stu-id="c36a6-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="لقطة شاشة لتكوين حساب التخزين. "::: 

   - <span data-ttu-id="c36a6-132">لمعرفة المزيد حول كيفية العثور على اسم حساب مخزن البيانات الثنائية الكبيرة الحجز لـ Azure ومفتاح الحساب، راجع [أداة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="c36a6-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="c36a6-133">لمعرفة كيفية إنشاء حاوية، راجع [إنشاء حاوية](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="c36a6-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="c36a6-134">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="c36a6-134">Select **Next**.</span></span>

1. <span data-ttu-id="c36a6-135">اختر الشريحة التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="c36a6-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="c36a6-136">في هذا المثال، هي **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c36a6-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="لقطة شاشة لواجهة مستخدم تحديد الشريحة مع تحديد الشريحة ChurnProneCustomers.":::

1. <span data-ttu-id="c36a6-138">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="c36a6-138">Select **Save**.</span></span>

<span data-ttu-id="c36a6-139">بعد حفظ وجهة التصدير، يمكك العثور عليه في **المسؤول** > **التصديرات‬** > **وجهات التصدير الخاصة بي‬**.</span><span class="sxs-lookup"><span data-stu-id="c36a6-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="لقطة شاشة مع قائمة تصديرات وعينة شريحة مميزة.":::

<span data-ttu-id="c36a6-141">يمكنك الآن [تصدير الشريحة عند الطلب](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c36a6-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="c36a6-142">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md).</span><span class="sxs-lookup"><span data-stu-id="c36a6-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c36a6-143">تأكد من أن عدد السجلات في الشريحة المصدّرة هو ضمن الحد المسموح به في ترخيص Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c36a6-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="c36a6-144">يتم تخزين البيانات المصدّرة في حاوية Azure Blob storage التي قمت بتكوينها أعلاه.</span><span class="sxs-lookup"><span data-stu-id="c36a6-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="c36a6-145">يتم إنشاء مسار المجلد التالي بشكل تلقائي في حاويتك:</span><span class="sxs-lookup"><span data-stu-id="c36a6-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="c36a6-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="c36a6-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="c36a6-147">مثال: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="c36a6-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="c36a6-148">يقيم الملف *model.json* للكيانات المصدّرة على مستوى *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="c36a6-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="c36a6-149">مثال: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="c36a6-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="c36a6-150">تعريف نموذج بيانات التجربة (XDM) في Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="c36a6-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="c36a6-151">قبل أن يمكن استخدام البيانات المصدّرة من رؤى الجمهور داخل Adobe Experience Platform، نحتاج إلى تعريف مخطط نموذج بيانات التجربة و[تكوين البيانات لملف تعريف العميل في الوقت الحقيقي](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="c36a6-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="c36a6-152">تعرف على [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) وافهم [أساسيات تركيب المخطط](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="c36a6-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="c36a6-153">استيراد البيانات إلى Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="c36a6-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="c36a6-154">الآن وقد تم تنظيم كل شيء، نحتاج إلى استيراد بيانات الجمهور التي قمنا بإعدادها من رؤى الجمهور إلى Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c36a6-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="c36a6-155">أولاً، [أنشئ اتصال مصدر Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="c36a6-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="c36a6-156">بعد تعريف اتصال المصدر، يمكنك [تكوين تدفق بيانات](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) لاتصال دُفعي لمساحة تخزين سحابية لاستيراد إخراج الشرائح من رؤى الجمهور إلى Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c36a6-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="c36a6-157">إنشاء جمهور في Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c36a6-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="c36a6-158">لإرسال البريد الإلكتروني لهذه الحملة، سوف نستخدم Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c36a6-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="c36a6-159">بعد استيراد البيانات إلى Adobe Experience Platform، يلزمنا [إنشاء جمهور](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) في Adobe Campaign Standard باستخدام البيانات في Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c36a6-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="c36a6-160">اعرف كيفية [استخدام منشئ الشرائح](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) في Adobe Campaign Standard لتعريف جمهور استنادًا إلى البيانات في Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="c36a6-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="c36a6-161">إنشاء البريد الإلكتروني وإرساله باستخدام Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c36a6-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="c36a6-162">أنشئ محتوى البريد الإلكتروني، ثم [اختبر وأرسل](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="c36a6-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="عينة بريد إلكتروني مع عرض التجديد من Adobe Campaign Standard.":::