---
title: تصدير بيانات Customer Insights إلى Adobe Campaign Standard
description: اعرف كيفية استخدام شرائح رؤى الجمهور في Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596299"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="302cb-103">استخدام شرائح Customer Insights في Adobe Campaign Standard (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="302cb-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="302cb-104">بصفتك مستخدم رؤى الجمهور في Dynamics 365 Customer Insights، من المحتمل أن تكون قد أنشأت شرائح لزيادة مستوى فعالية حملاتك التسويقية من خلال استهداف شرائح جمهور ذات صلة.</span><span class="sxs-lookup"><span data-stu-id="302cb-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="302cb-105">لاستخدام شريحة من رؤى الجمهور في Adobe Experience Platform وتطبيقات مثل Adobe Campaign Standard، يلزمك اتباع بعض الخطوات الملخصة في هذه المقالة.</span><span class="sxs-lookup"><span data-stu-id="302cb-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="مخطط العملية للخطوات الملخصة في هذه المقالة.":::

## <a name="prerequisites"></a><span data-ttu-id="302cb-107">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="302cb-107">Prerequisites</span></span>

-   <span data-ttu-id="302cb-108">ترخيص Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="302cb-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="302cb-109">ترخيص Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="302cb-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="302cb-110">حساب Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="302cb-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="302cb-111">نظرة عامة حول الحملة</span><span class="sxs-lookup"><span data-stu-id="302cb-111">Campaign Overview</span></span>

<span data-ttu-id="302cb-112">لتكوين فهم أفضل لكيفية استخدام شرائح من رؤى الجمهور في Adobe Experience Platform، سنلقي نظرة على عينة حملة وهمية.</span><span class="sxs-lookup"><span data-stu-id="302cb-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="302cb-113">لنفترض أن شركتك تقدم خدمة شهرية قائمة على اشتراك لعملائك في الولايات المتحدة.</span><span class="sxs-lookup"><span data-stu-id="302cb-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="302cb-114">تريد تحديد العملاء الذين من المقرر تجديد اشتراكاتهم في الأيام الثمانية القادمة، ولكنهم لم يجددوا اشتراكهم بعد.</span><span class="sxs-lookup"><span data-stu-id="302cb-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="302cb-115">للمحافظة على هؤلاء العملاء، تريد إرسال عرض ترويجي لهم عبر البريد الإلكتروني، باستخدام Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="302cb-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="302cb-116">في هذا المثال، نريد تشغيل حملة البريد الإلكتروني الترويجية مرة واحدة.</span><span class="sxs-lookup"><span data-stu-id="302cb-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="302cb-117">لا تتناول هذه المقالة حالة استخدام تشغيل الحملة أكثر من مرة.</span><span class="sxs-lookup"><span data-stu-id="302cb-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="302cb-118">ومع ذلك، يمكنك تكوين رؤى الجمهور وAdobe Campaign Standard بحيث يعملان لسيناريو حملة متكررة أيضًا.</span><span class="sxs-lookup"><span data-stu-id="302cb-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="302cb-119">تحديد الجمهور المستهدف</span><span class="sxs-lookup"><span data-stu-id="302cb-119">Identify your target audience</span></span>

<span data-ttu-id="302cb-120">في السيناريو لدينا، نفترض أن عناوين البريد الإلكتروني الخاصة بالعملاء متوفرة في رؤى الجمهور‬، وأنه قد تم تحليل وتفضيلاتهم الترويجية لتحديد أعضاء الشريحة.</span><span class="sxs-lookup"><span data-stu-id="302cb-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="302cb-121">تسمى [الشريحة التي حددتها في رؤى الجمهور‬](segments.md) is called **ChurnProneCustomers**، وتريد إرسال العرض الترويجي إلى هؤلاء العملاء بالبريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="302cb-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="لقطة شاشة لصفحة الشرائح باستخدام الشريحة ChurnProneCustomers التي تم إنشاؤها.":::

<span data-ttu-id="302cb-123">سيحتوي العرض الذي تريد إرسال بالبريد الإلكتروني على الاسم الأول واسم العائلة وتاريخ انتهاء اشتراك العميل.</span><span class="sxs-lookup"><span data-stu-id="302cb-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="302cb-124">كما يعلم العملاء بالتخفيض الذي سيحصلون عليه في حالة قيامهم بتجديد اشتراكهم قبل انتهاء مدته.</span><span class="sxs-lookup"><span data-stu-id="302cb-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="302cb-125">تصدير الجمهور المستهدف</span><span class="sxs-lookup"><span data-stu-id="302cb-125">Export your target audience</span></span>

<span data-ttu-id="302cb-126">ومن خلال تحديد الجمهور المستهدف، يمكننا تكوين التصدير من رؤى الجمهور إلى حساب Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="302cb-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="302cb-127">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.</span><span class="sxs-lookup"><span data-stu-id="302cb-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="302cb-128">في الإطار المتجانب **حملة Adobe‎**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="302cb-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="الإطار المتجانب لتكوين Adobe Campaign Standard.":::

1. <span data-ttu-id="302cb-130">أدخل **اسمًا معروضًا** لوجهة التصدير الجديدة هذه، ثم أدخل **اسم الحساب** و **مفتاح الحساب** و **الحاوية** لحساب Azure Blob Storage الذي تريد تصدير الشريحة إليه.</span><span class="sxs-lookup"><span data-stu-id="302cb-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="لقطة شاشة لتكوين حساب التخزين. "::: 

   - <span data-ttu-id="302cb-132">لمعرفة المزيد حول كيفية العثور على اسم حساب مخزن البيانات الثنائية الكبيرة الحجز لـ Azure ومفتاح الحساب، راجع [أداة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="302cb-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="302cb-133">لمعرفة كيفية إنشاء حاوية، راجع [إنشاء حاوية](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="302cb-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="302cb-134">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="302cb-134">Select **Next**.</span></span>

1. <span data-ttu-id="302cb-135">اختر الشريحة التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="302cb-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="302cb-136">في هذا المثال، هي **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="302cb-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="لقطة شاشة لواجهة مستخدم تحديد الشريحة مع تحديد الشريحة ChurnProneCustomers.":::

1. <span data-ttu-id="302cb-138">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="302cb-138">Select **Next**.</span></span>

1. <span data-ttu-id="302cb-139">سنقوم الآن بتعيين حقول **المصدر** من شريحة رؤى الجمهور إلى أسماء حقول **الهدف** في مخطط ملف تعريف Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="302cb-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="تعيين الحقول لموصل Adobe Campaign Standard.":::

   <span data-ttu-id="302cb-141">إذا كنت ترغب في إضافة مزيد من السمات، فحدد **إضافة سمة**.</span><span class="sxs-lookup"><span data-stu-id="302cb-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="302cb-142">بإمكان اسم الحقل الهدف أن يكون مختلفًا عن اسم الحقل المصدر بحيث يبقى باستطاعتك تعيين إخراج الشرائح من رؤى الجمهور إلى Adobe Campaign Standard إذا لم يكن لدى الحقول الاسم نفسه في النظامين.</span><span class="sxs-lookup"><span data-stu-id="302cb-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="302cb-143">يتم استخدام عنوان البريد الإلكتروني كحقل هوية، ولكن يمكنك استخدام أي معرف آخر من ملف تعريف عميل رؤى الجمهور لتعيين البيانات إلى Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="302cb-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="302cb-144">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="302cb-144">Select **Save**.</span></span>

<span data-ttu-id="302cb-145">بعد حفظ وجهة التصدير، يمكك العثور عليه في **المسؤول** > **التصديرات‬** > **وجهات التصدير الخاصة بي‬**.</span><span class="sxs-lookup"><span data-stu-id="302cb-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="لقطة شاشة مع قائمة تصديرات وعينة شريحة مميزة.":::

<span data-ttu-id="302cb-147">يمكنك الآن [تصدير الشريحة عند الطلب](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="302cb-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="302cb-148">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md).</span><span class="sxs-lookup"><span data-stu-id="302cb-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="302cb-149">تأكد من أن عدد السجلات في الشريحة المصدّرة هو ضمن الحد المسموح به في ترخيص Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="302cb-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="302cb-150">يتم تخزين البيانات المصدّرة في حاوية Azure Blob storage التي قمت بتكوينها أعلاه.</span><span class="sxs-lookup"><span data-stu-id="302cb-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="302cb-151">يتم إنشاء مسار المجلد التالي بشكل تلقائي في حاويتك:</span><span class="sxs-lookup"><span data-stu-id="302cb-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="302cb-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="302cb-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="302cb-153">مثال: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="302cb-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="302cb-154">تكوين Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="302cb-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="302cb-155">تحتوي الشريحة، عند تصديرها من رؤى الجمهور، على الأعمدة التي حددتها أثناء تعريف وجهة التصدير في الخطوة السابقة.</span><span class="sxs-lookup"><span data-stu-id="302cb-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="302cb-156">يمكن استخدام هذه البيانات في عملية [إنشاء ملفات تعريف في Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="302cb-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="302cb-157">لاستخدام الشريحة في Adobe Campaign Standard، يلزمنا توسيع مخطط ملف التعريف في Adobe Campaign Standard بحيث يتضمن حقلين إضافيين.</span><span class="sxs-lookup"><span data-stu-id="302cb-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="302cb-158">اعرف كيفية [توسيع مورد ملف التعريف](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) باستخدام حقول جديدة في Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="302cb-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="302cb-159">في المثال الذي قدمناه، هذه الحقول هي *اسم الشريحة وتاريخ الشريحة (اختياري).*</span><span class="sxs-lookup"><span data-stu-id="302cb-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="302cb-160">سوف نستخدم هذه الحقول لتحديد ملفات التعريف في Adobe Campaign Standard التي نريد استهدافها لهذه الحملة.</span><span class="sxs-lookup"><span data-stu-id="302cb-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="302cb-161">إذا لم تكن هناك سجلات أخرى في Adobe Campaign Standard، غير تلك التي ستقوم باستيرادها، فيمكنك تخطي هذه الخطوة.</span><span class="sxs-lookup"><span data-stu-id="302cb-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="302cb-162">استيراد البيانات إلى Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="302cb-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="302cb-163">الآن وقد تم تنظيم كل شيء، نحتاج إلى استيراد بيانات الجمهور التي قمنا بإعدادها من رؤى الجمهور إلى Adobe Campaign Standard لإنشاء ملفات تعريف.</span><span class="sxs-lookup"><span data-stu-id="302cb-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="302cb-164">اعرف [كيفية استيراد ملفات التعريفي في Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) باستخدام سير عمل.</span><span class="sxs-lookup"><span data-stu-id="302cb-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="302cb-165">تم تكوين سير عمل الاستيراد في الصورة أدناه كي يتم تشغيله كل 8 ساعات ويبحث عن شرائح الجمهور المصدّرة (ملف csv. في Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="302cb-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="302cb-166">يستخرج سير العمل محتوى ملف csv. في ترتيب أعمدة محدد.</span><span class="sxs-lookup"><span data-stu-id="302cb-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="302cb-167">تم بناء سير العمل هذا لتنفيذ معالجة أخطاء أساسية والتأكد من أن كل سجل يحتوي على عنوان بريد إلكتروني قبل ترحيل البيانات إلى Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="302cb-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="302cb-168">كما يستخرج سير العمل اسم الشريحة من اسم الملف قبل تحديثها وإدراجها داخل بيانات ملف تعريف ACS.</span><span class="sxs-lookup"><span data-stu-id="302cb-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="لقطة شاشة لسير عمل عملية استيراد في واجهة مستخدم Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="302cb-170">استرداد الجمهور في Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="302cb-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="302cb-171">بعد استيراد البيانات إلى Adobe Campaign Standard، [يمكنك إنشاء سير عمل](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) و [استعلام](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) العملاء استنادًا إلى *اسم الشريحة* و *تاريخ الشريحة* لتحديد ملفات التعريف التي تم تعريفها لعينة الحملة.</span><span class="sxs-lookup"><span data-stu-id="302cb-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="302cb-172">إنشاء البريد الإلكتروني وإرساله باستخدام Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="302cb-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="302cb-173">أنشئ محتوى البريد الإلكتروني، ثم [اختبر وأرسل](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="302cb-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="عينة بريد إلكتروني مع عرض التجديد من Adobe Campaign Standard.":::