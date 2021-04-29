---
title: تصدير بيانات Customer Insights إلى Adobe Campaign Standard
description: اعرف كيفية استخدام شرائح رؤى الجمهور في Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760265"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="72e62-103">استخدام شرائح Customer Insights في Adobe Campaign Standard (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="72e62-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="72e62-104">بصفتك مستخدم رؤى الجمهور في Dynamics 365 Customer Insights، من المحتمل أن تكون قد أنشأت شرائح لزيادة مستوى فعالية حملاتك التسويقية من خلال استهداف شرائح جمهور ذات صلة.</span><span class="sxs-lookup"><span data-stu-id="72e62-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="72e62-105">لاستخدام شريحة من رؤى الجمهور في Adobe Experience Platform وتطبيقات مثل Adobe Campaign Standard، يلزمك اتباع بعض الخطوات الملخصة في هذه المقالة.</span><span class="sxs-lookup"><span data-stu-id="72e62-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="مخطط العملية للخطوات الملخصة في هذه المقالة.":::

## <a name="prerequisites"></a><span data-ttu-id="72e62-107">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="72e62-107">Prerequisites</span></span>

-   <span data-ttu-id="72e62-108">ترخيص Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="72e62-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="72e62-109">ترخيص Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="72e62-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="72e62-110">حساب Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="72e62-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="72e62-111">نظرة عامة حول الحملة</span><span class="sxs-lookup"><span data-stu-id="72e62-111">Campaign Overview</span></span>

<span data-ttu-id="72e62-112">لتكوين فهم أفضل لكيفية استخدام شرائح من رؤى الجمهور في Adobe Experience Platform، سنلقي نظرة على عينة حملة وهمية.</span><span class="sxs-lookup"><span data-stu-id="72e62-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="72e62-113">لنفترض أن شركتك تقدم خدمة شهرية قائمة على اشتراك لعملائك في الولايات المتحدة.</span><span class="sxs-lookup"><span data-stu-id="72e62-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="72e62-114">تريد تحديد العملاء الذين من المقرر تجديد اشتراكاتهم في الأيام الثمانية القادمة، ولكنهم لم يجددوا اشتراكهم بعد.</span><span class="sxs-lookup"><span data-stu-id="72e62-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="72e62-115">للمحافظة على هؤلاء العملاء، تريد إرسال عرض ترويجي لهم عبر البريد الإلكتروني، باستخدام Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="72e62-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="72e62-116">في هذا المثال، نريد تشغيل حملة البريد الإلكتروني الترويجية مرة واحدة.</span><span class="sxs-lookup"><span data-stu-id="72e62-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="72e62-117">لا تتناول هذه المقالة حالة استخدام تشغيل الحملة أكثر من مرة.</span><span class="sxs-lookup"><span data-stu-id="72e62-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="72e62-118">ومع ذلك، يمكنك تكوين رؤى الجمهور وAdobe Campaign Standard بحيث يعملان لسيناريو حملة متكررة أيضًا.</span><span class="sxs-lookup"><span data-stu-id="72e62-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="72e62-119">تحديد الجمهور المستهدف</span><span class="sxs-lookup"><span data-stu-id="72e62-119">Identify your target audience</span></span>

<span data-ttu-id="72e62-120">في السيناريو لدينا، نفترض أن عناوين البريد الإلكتروني الخاصة بالعملاء متوفرة في رؤى الجمهور‬، وأنه قد تم تحليل وتفضيلاتهم الترويجية لتحديد أعضاء الشريحة.</span><span class="sxs-lookup"><span data-stu-id="72e62-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="72e62-121">تسمى [الشريحة التي حددتها في رؤى الجمهور‬](segments.md) is called **ChurnProneCustomers**، وتريد إرسال العرض الترويجي إلى هؤلاء العملاء بالبريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="72e62-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="لقطة شاشة لصفحة الشرائح باستخدام الشريحة ChurnProneCustomers التي تم إنشاؤها.":::

<span data-ttu-id="72e62-123">سيحتوي العرض الذي تريد إرسال بالبريد الإلكتروني على الاسم الأول واسم العائلة وتاريخ انتهاء اشتراك العميل.</span><span class="sxs-lookup"><span data-stu-id="72e62-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="72e62-124">كما يعلم العملاء بالتخفيض الذي سيحصلون عليه في حالة قيامهم بتجديد اشتراكهم قبل انتهاء مدته.</span><span class="sxs-lookup"><span data-stu-id="72e62-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="72e62-125">تصدير الجمهور المستهدف</span><span class="sxs-lookup"><span data-stu-id="72e62-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="72e62-126">تكوين اتصال</span><span class="sxs-lookup"><span data-stu-id="72e62-126">Configure a connection</span></span>

<span data-ttu-id="72e62-127">ومن خلال تحديد الجمهور المستهدف، يمكننا تكوين التصدير من رؤى الجمهور إلى حساب Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="72e62-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="72e62-128">من رؤى الجمهور، انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="72e62-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="72e62-129">حدد **إضافة اتصال** واختر **حملة Adobe** لتكوين الاتصال أو حدد **إعداد** في تجانب **حملة Adobe**</span><span class="sxs-lookup"><span data-stu-id="72e62-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="الإطار المتجانب لتكوين Adobe Campaign Standard.":::

1. <span data-ttu-id="72e62-131">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="72e62-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="72e62-132">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="72e62-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="72e62-133">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="72e62-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="72e62-134">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="72e62-134">Choose who can use this connection.</span></span> <span data-ttu-id="72e62-135">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="72e62-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="72e62-136">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="72e62-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="72e62-137">أدخل **اسم الحساب**، و **مفتاح الحساب**، و **الحاوية** لحساب تخزين Azure Blob حيث تريد تصدير الشريحة إليه.</span><span class="sxs-lookup"><span data-stu-id="72e62-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="لقطة شاشة لتكوين حساب التخزين. "::: 

   - <span data-ttu-id="72e62-139">لمعرفة المزيد حول كيفية العثور على اسم حساب مخزن البيانات الثنائية الكبيرة الحجز لـ Azure ومفتاح الحساب، راجع [أداة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="72e62-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="72e62-140">لمعرفة كيفية إنشاء حاوية، راجع [إنشاء حاوية](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="72e62-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="72e62-141">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="72e62-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="72e62-142">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="72e62-142">Configure an export</span></span>

<span data-ttu-id="72e62-143">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="72e62-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="72e62-144">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="72e62-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="72e62-145">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="72e62-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="72e62-146">لإنشاء عملية تصدير جديدة، حدد **إضافة تصدير**.</span><span class="sxs-lookup"><span data-stu-id="72e62-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="72e62-147">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم حملة Adobe.</span><span class="sxs-lookup"><span data-stu-id="72e62-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="72e62-148">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="72e62-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="72e62-149">اختر الشريحة التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="72e62-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="72e62-150">في هذا المثال، هي **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="72e62-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="لقطة شاشة لواجهة مستخدم تحديد الشريحة مع تحديد الشريحة ChurnProneCustomers.":::

1. <span data-ttu-id="72e62-152">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="72e62-152">Select **Next**.</span></span>

1. <span data-ttu-id="72e62-153">سنقوم الآن بتعيين حقول **المصدر** من شريحة رؤى الجمهور إلى أسماء حقول **الهدف** في مخطط ملف تعريف Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="72e62-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="تعيين الحقول لموصل Adobe Campaign Standard.":::

   <span data-ttu-id="72e62-155">إذا كنت ترغب في إضافة مزيد من السمات، فحدد **إضافة سمة**.</span><span class="sxs-lookup"><span data-stu-id="72e62-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="72e62-156">بإمكان اسم الحقل الهدف أن يكون مختلفًا عن اسم الحقل المصدر بحيث يبقى باستطاعتك تعيين إخراج الشرائح من رؤى الجمهور إلى Adobe Campaign Standard إذا لم يكن لدى الحقول الاسم نفسه في النظامين.</span><span class="sxs-lookup"><span data-stu-id="72e62-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="72e62-157">يتم استخدام عنوان البريد الإلكتروني كحقل هوية، ولكن يمكنك استخدام أي معرف آخر من ملف تعريف عميل رؤى الجمهور لتعيين البيانات إلى Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="72e62-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="72e62-158">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="72e62-158">Select **Save**.</span></span>

<span data-ttu-id="72e62-159">بعد حفظ وجهة التصدير، تجدها في **البيانات** > **عمليات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="72e62-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="72e62-160">يمكنك الآن [تصدير الشريحة عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="72e62-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="72e62-161">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md).</span><span class="sxs-lookup"><span data-stu-id="72e62-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="72e62-162">تأكد من أن عدد السجلات في الشريحة المصدّرة هو ضمن الحد المسموح به في ترخيص Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="72e62-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="72e62-163">يتم تخزين البيانات المصدّرة في حاوية Azure Blob storage التي قمت بتكوينها أعلاه.</span><span class="sxs-lookup"><span data-stu-id="72e62-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="72e62-164">يتم إنشاء مسار المجلد التالي بشكل تلقائي في حاويتك:</span><span class="sxs-lookup"><span data-stu-id="72e62-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="72e62-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="72e62-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="72e62-166">مثال: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="72e62-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="72e62-167">تكوين Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="72e62-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="72e62-168">تحتوي الشريحة، عند تصديرها من رؤى الجمهور، على الأعمدة التي حددتها أثناء تعريف وجهة التصدير في الخطوة السابقة.</span><span class="sxs-lookup"><span data-stu-id="72e62-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="72e62-169">يمكن استخدام هذه البيانات في عملية [إنشاء ملفات تعريف في Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="72e62-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="72e62-170">لاستخدام الشريحة في Adobe Campaign Standard، يلزمنا توسيع مخطط ملف التعريف في Adobe Campaign Standard بحيث يتضمن حقلين إضافيين.</span><span class="sxs-lookup"><span data-stu-id="72e62-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="72e62-171">اعرف كيفية [توسيع مورد ملف التعريف](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) باستخدام حقول جديدة في Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="72e62-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="72e62-172">في المثال الذي قدمناه، هذه الحقول هي *اسم الشريحة وتاريخ الشريحة (اختياري).*</span><span class="sxs-lookup"><span data-stu-id="72e62-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="72e62-173">سوف نستخدم هذه الحقول لتحديد ملفات التعريف في Adobe Campaign Standard التي نريد استهدافها لهذه الحملة.</span><span class="sxs-lookup"><span data-stu-id="72e62-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="72e62-174">إذا لم تكن هناك سجلات أخرى في Adobe Campaign Standard، غير تلك التي ستقوم باستيرادها، فيمكنك تخطي هذه الخطوة.</span><span class="sxs-lookup"><span data-stu-id="72e62-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="72e62-175">استيراد البيانات إلى Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="72e62-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="72e62-176">الآن وقد تم تنظيم كل شيء، نحتاج إلى استيراد بيانات الجمهور التي قمنا بإعدادها من رؤى الجمهور إلى Adobe Campaign Standard لإنشاء ملفات تعريف.</span><span class="sxs-lookup"><span data-stu-id="72e62-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="72e62-177">اعرف [كيفية استيراد ملفات التعريفي في Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) باستخدام سير عمل.</span><span class="sxs-lookup"><span data-stu-id="72e62-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="72e62-178">تم تكوين سير عمل الاستيراد في الصورة أدناه كي يتم تشغيله كل 8 ساعات ويبحث عن شرائح الجمهور المصدّرة (ملف csv. في Azure Blob Storage).</span><span class="sxs-lookup"><span data-stu-id="72e62-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="72e62-179">يستخرج سير العمل محتوى ملف csv. في ترتيب أعمدة محدد.</span><span class="sxs-lookup"><span data-stu-id="72e62-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="72e62-180">تم بناء سير العمل هذا لتنفيذ معالجة أخطاء أساسية والتأكد من أن كل سجل يحتوي على عنوان بريد إلكتروني قبل ترحيل البيانات إلى Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="72e62-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="72e62-181">كما يستخرج سير العمل اسم الشريحة من اسم الملف قبل تحديثها وإدراجها داخل بيانات ملف تعريف ACS.</span><span class="sxs-lookup"><span data-stu-id="72e62-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="لقطة شاشة لسير عمل عملية استيراد في واجهة مستخدم Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="72e62-183">استرداد الجمهور في Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="72e62-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="72e62-184">بعد استيراد البيانات إلى Adobe Campaign Standard، [يمكنك إنشاء سير عمل](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) و [استعلام](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) العملاء استنادًا إلى *اسم الشريحة* و *تاريخ الشريحة* لتحديد ملفات التعريف التي تم تعريفها لعينة الحملة.</span><span class="sxs-lookup"><span data-stu-id="72e62-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="72e62-185">إنشاء البريد الإلكتروني وإرساله باستخدام Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="72e62-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="72e62-186">أنشئ محتوى البريد الإلكتروني، ثم [اختبر وأرسل](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) البريد الإلكتروني.</span><span class="sxs-lookup"><span data-stu-id="72e62-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="عينة بريد إلكتروني مع عرض التجديد من Adobe Campaign Standard.":::
