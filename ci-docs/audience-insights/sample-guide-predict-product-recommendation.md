---
title: دليل عينة التنبؤ بتوصيات المنتج
description: استخدم دليل العينة هذا للتعرف على النموذج الجاهز للتنبؤ بتوصيات المنتج‬.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b136084316da5ae17a8428236381f69e5c21f9ea
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129883"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="7ad72-103">دليل عينة التنبؤ بتوصيات المنتج (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="7ad72-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="7ad72-104">سوف نرشدك عبر مثال شامل للتنبؤ بتوصيات المنتج‬ باستخدام عينة البيانات المتوفرة أدناه.</span><span class="sxs-lookup"><span data-stu-id="7ad72-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="7ad72-105">السيناريو</span><span class="sxs-lookup"><span data-stu-id="7ad72-105">Scenario</span></span>

<span data-ttu-id="7ad72-106">Contoso هي شركة تنتج قهوة وماكينات لصنع القهوة عالية الجودة، تقوم ببيعها عبر موقع Contoso Coffee على الويب.</span><span class="sxs-lookup"><span data-stu-id="7ad72-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="7ad72-107">هدف هذه الشركة هو فهم المنتجات التي ينبغي أن يوصى بها للعملاء المتكررين.</span><span class="sxs-lookup"><span data-stu-id="7ad72-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="7ad72-108">من شأن معرفة الأصناف التي **من المرجح أن يشتريها** العملاء أن تساعد على توفير الجهود التسويقية من خلال التركيز على أصناف معينة.</span><span class="sxs-lookup"><span data-stu-id="7ad72-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7ad72-109">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="7ad72-109">Prerequisites</span></span>

- <span data-ttu-id="7ad72-110">على الأقل [أذونات المساهم](permissions.md) في Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7ad72-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="7ad72-111">نحن ننصح بتنفيذ الخطوات التالية [في بيئة جديدة](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="7ad72-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="7ad72-112">المهمة 1 - استيعاب البيانات</span><span class="sxs-lookup"><span data-stu-id="7ad72-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="7ad72-113">راجع المقالات [حول استيعاب البيانات](data-sources.md) و[استيراد مصادر البيانات باستخدام موصلات Power Query](connect-power-query.md) على وجه التحديد.</span><span class="sxs-lookup"><span data-stu-id="7ad72-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="7ad72-114">تفترض المعلومات التالية أنك ملمّ باستيعاب البيانات بشكل عام.</span><span class="sxs-lookup"><span data-stu-id="7ad72-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="7ad72-115">استيعاب بيانات العملاء من النظام الأساسي للتجارة الإلكترونية</span><span class="sxs-lookup"><span data-stu-id="7ad72-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="7ad72-116">أنشئ مصدر بيانات باسم **التجارة الإلكترونية**، وحدد خيار الاستيراد، ثم حدد الموصل **النص/CSV**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="7ad72-117">أدخل عنوان URL لجهات اتصال التجارة الإلكترونية https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="7ad72-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="7ad72-118">أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7ad72-119">حدّث نوع البيانات للأعمدة المدرجة أدناه:</span><span class="sxs-lookup"><span data-stu-id="7ad72-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="7ad72-120">**DateOfBirth**: التاريخ</span><span class="sxs-lookup"><span data-stu-id="7ad72-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="7ad72-121">**CreatedOn**: التاريخ/الوقت/المنطقة</span><span class="sxs-lookup"><span data-stu-id="7ad72-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="تحويل تاريخ الولادة إلى تاريخ.":::

5. <span data-ttu-id="7ad72-123">في حقل "الاسم" في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام** إلى **‎eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="7ad72-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="7ad72-124">**احفظ** مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="7ad72-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="7ad72-125">استيعاب بيانات شراء عبر الإنترنت</span><span class="sxs-lookup"><span data-stu-id="7ad72-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="7ad72-126">أضف مجموعة بيانات أخرى إلى مصدر البيانات **التجارة الإلكترونية**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="7ad72-127">اختر الموصل **النص/CSV** مرة أخرى.</span><span class="sxs-lookup"><span data-stu-id="7ad72-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="7ad72-128">أدخل عنوان URL لبيانات **المشتريات عبر الإنترنت** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="7ad72-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="7ad72-129">أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7ad72-130">حدّث نوع البيانات للأعمدة المدرجة أدناه:</span><span class="sxs-lookup"><span data-stu-id="7ad72-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="7ad72-131">**PurchasedOn**: التاريخ/الوقت</span><span class="sxs-lookup"><span data-stu-id="7ad72-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="7ad72-132">**TotalPrice**: العملة</span><span class="sxs-lookup"><span data-stu-id="7ad72-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="7ad72-133">في حقل **الاسم** في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام‏‎** إلى **مشتريات التجارة الإلكترونية**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="7ad72-134">**احفظ** مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="7ad72-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="7ad72-135">استيعاب بيانات العملاء من مخطط الولاء</span><span class="sxs-lookup"><span data-stu-id="7ad72-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="7ad72-136">أنشئ مصدر بيانات باسم **LoyaltyScheme**، وحدد خيار الاستيراد، ثم حدد الموصل **النص/CSV**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="7ad72-137">أدخل عنوان URL لجهات اتصال التجارة الإلكترونية https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="7ad72-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="7ad72-138">أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7ad72-139">حدّث نوع البيانات للأعمدة المدرجة أدناه:</span><span class="sxs-lookup"><span data-stu-id="7ad72-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="7ad72-140">**DateOfBirth**: التاريخ</span><span class="sxs-lookup"><span data-stu-id="7ad72-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="7ad72-141">**RewardsPoints**: عدد صحيح</span><span class="sxs-lookup"><span data-stu-id="7ad72-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="7ad72-142">**CreatedOn**: التاريخ/الوقت</span><span class="sxs-lookup"><span data-stu-id="7ad72-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="7ad72-143">في حقل **الاسم** في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام‏‎** إلى **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="7ad72-144">**احفظ** مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="7ad72-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="7ad72-145">المهمة 2 - توحيد البيانات</span><span class="sxs-lookup"><span data-stu-id="7ad72-145">Task 2 - Data unification</span></span>

<span data-ttu-id="7ad72-146">بعد استيعاب البيانات، نبدأ الآن عملية توحيد البيانات لإنشاء ملف تعريف عميل موحد.</span><span class="sxs-lookup"><span data-stu-id="7ad72-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="7ad72-147">لمزيد من المعلومات، راجع [توحيد البيانات](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="7ad72-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="7ad72-148">المخطط</span><span class="sxs-lookup"><span data-stu-id="7ad72-148">Map</span></span>

1. <span data-ttu-id="7ad72-149">بعد استيعاب البيانات، قم بتعيين جهات الاتصال من بيانات التجارة الإلكترونية والولاء إلى أنواع البيانات الشائعة.</span><span class="sxs-lookup"><span data-stu-id="7ad72-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="7ad72-150">انتقل إلى **البيانات** > **توحيد** > **تعيين**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="7ad72-151">حدد الكيانات التي تمثل ملف تعريف العميل – **eCommerceContacts** و **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![توحيد مصادر بيانات التجارة الإلكترونية والولاء.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="7ad72-153">حدد **ContactId** كمفتاح أساسي لـ **eCommerceContacts** و **LoyaltyID** كمفتاح أساسي لـ **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![توحيد LoyaltyId كمفتاح أساسي.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="7ad72-155">مطابقة</span><span class="sxs-lookup"><span data-stu-id="7ad72-155">Match</span></span>

1. <span data-ttu-id="7ad72-156">انتقل إلى علامة التبويب **مطابقة** وحدد **تعيين الأمر**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="7ad72-157">من القائمة المنسدلة **أساسي**، اختر **eCommerceContacts : eCommerce** كمصدر أساسي وقم بتضمين جميع السجلات.</span><span class="sxs-lookup"><span data-stu-id="7ad72-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="7ad72-158">في القائمة المنسدلة **الكيان 2**، اختر **loyCustomers : LoyaltyScheme** وقم بتضمين جميع السجلات.</span><span class="sxs-lookup"><span data-stu-id="7ad72-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![توحيد مطابقة التجارة الإلكترونية والولاء.](media/unify-match-order.png)

4. <span data-ttu-id="7ad72-160">حدد **إنشاء قاعدة جديدة**</span><span class="sxs-lookup"><span data-stu-id="7ad72-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="7ad72-161">أضف الشرط الأول باستخدام FullName.</span><span class="sxs-lookup"><span data-stu-id="7ad72-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="7ad72-162">لخيار eCommerceContacts، حدد **FullName‎** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="7ad72-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="7ad72-163">لخيار loyCustomers، حدد **FullName‎** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="7ad72-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="7ad72-164">حدد القائمة المنسدلة **تسوية**، واختر **النوع (الهاتف والاسم والعنوان و...)**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="7ad72-165">عيّن **مستوى الدقة**: **أساسي** و **قيمة**: **عالي**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="7ad72-166">أدخل الاسم **FullName, Email** للقاعدة الجديدة.</span><span class="sxs-lookup"><span data-stu-id="7ad72-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="7ad72-167">أضف شرطًا ثانيًا لعنوان البريد الإلكتروني من خلال تحديد **إضافة شرط**</span><span class="sxs-lookup"><span data-stu-id="7ad72-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="7ad72-168">للكيان eCommerceContacts، حدد **EMail** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="7ad72-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="7ad72-169">للكيان loyCustomers، حدد **EMail** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="7ad72-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="7ad72-170">اترك الخيار "تسوية" فارغًا.</span><span class="sxs-lookup"><span data-stu-id="7ad72-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="7ad72-171">عيّن **مستوى الدقة**: **أساسي** و **قيمة**: **عالي**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![توحيد قاعدة مطابقة للاسم والبريد الإلكتروني.](media/unify-match-rule.png)

7. <span data-ttu-id="7ad72-173">حدد **حفظ** و **تشغيل**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="7ad72-174">‏‏دمج</span><span class="sxs-lookup"><span data-stu-id="7ad72-174">Merge</span></span>

1. <span data-ttu-id="7ad72-175">انقر فوق علامة التبويب **دمج**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="7ad72-176">على **ContactId** للكيان **loyCustomers** ، قم بتغيير الاسم المعروض إلى **ContactIdLOYALTY** لتمييزه عن المعرفات الأخرى التي تم استيعابها.</span><span class="sxs-lookup"><span data-stu-id="7ad72-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![إعادة تسمية contactid من معرف الولاء.](media/unify-merge-contactid.png)

1. <span data-ttu-id="7ad72-178">حدد **حفظ** و **تشغيل** لبدء عملية الدمج.</span><span class="sxs-lookup"><span data-stu-id="7ad72-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="7ad72-179">المهمة 3 - تكوين التنبؤ بتوصيات المنتج‬</span><span class="sxs-lookup"><span data-stu-id="7ad72-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="7ad72-180">من خلال وضع ملفات تعريف العملاء الموحدة، يمكننا الآن تشغيل التنبؤ بخسارة الاشتراك.</span><span class="sxs-lookup"><span data-stu-id="7ad72-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="7ad72-181">انتقل إلى **الذكاء** > **التنبؤ** واختر **توصيات المنتج**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="7ad72-182">ثم حدد **بدء الاستخدام‬**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-182">Select **Get started**.</span></span>

1. <span data-ttu-id="7ad72-183">أدخل **تنبؤ نموذج توصيات المنتجات OOB** كاسم للنموذج و **OOBProductRecommendationModelPrediction** كاسم لكيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="7ad72-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="7ad72-184">قم بتعريف ثلاثة شروط للنموذج:</span><span class="sxs-lookup"><span data-stu-id="7ad72-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="7ad72-185">**عدد المنتجات**: عيّن هذه القيمة إلى **5**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="7ad72-186">يحدد هذا الإعداد عدد المنتجات التي ترغب في التوصية بها لعملائك.</span><span class="sxs-lookup"><span data-stu-id="7ad72-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="7ad72-187">**توقع المشتريات المتكررة‬**: حدد **نعم** للإشارة إلى أنك تريد أن تضمّن في التوصية المنتجات التي اشتراها العملاء من قبل.</span><span class="sxs-lookup"><span data-stu-id="7ad72-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="7ad72-188">**نافذة الرجوع‬:** حدد **365 يومًا** على الأقل.</span><span class="sxs-lookup"><span data-stu-id="7ad72-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="7ad72-189">يحدد هذا الإعداد المدة التي يعود بها النموذج إلى الوراء للنظر في نشاط العميل لاستخدامه كإدخال لتوصياته.</span><span class="sxs-lookup"><span data-stu-id="7ad72-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="تفضيلات النموذج لنموذج توصيات المنتج.":::

1. <span data-ttu-id="7ad72-191">حدد **البيانات المطلوبة** وحدد **إضافة بيانات** لمحفوظات الشراء.</span><span class="sxs-lookup"><span data-stu-id="7ad72-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="7ad72-192">أضف الكيان **eCommercePurchases : eCommerce** وعيّن الحقل من التجارة الإلكترونية إلى الحقول المناظرة التي يطلبها النموذج.</span><span class="sxs-lookup"><span data-stu-id="7ad72-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="7ad72-193">انضم إلى الكيان **eCommercePurchases : eCommerce** مع **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![الانضمام إلى كيانات التجارة الإلكترونية.](media/model-purchase-join.png)

1. <span data-ttu-id="7ad72-195">حدد **التالي** لتعيين جدول النماذج.</span><span class="sxs-lookup"><span data-stu-id="7ad72-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="7ad72-196">يحتاج النموذج إلى التدريب بشكل منتظم للتعرف على الأنماط الجديدة عند وجود بيانات جديدة تم استيعابها.</span><span class="sxs-lookup"><span data-stu-id="7ad72-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="7ad72-197">لهذا المثال، حدد **شهري**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="7ad72-198">بعد مراجعة كافة التفاصيل ، حدد **حفظ وتشغيل**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="7ad72-199">المهمة 4 - مراجعة نتائج وتفسيرات النماذج</span><span class="sxs-lookup"><span data-stu-id="7ad72-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="7ad72-200">دع النموذج يكمل تدريب وتسجيل نقاط البيانات.</span><span class="sxs-lookup"><span data-stu-id="7ad72-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="7ad72-201">يمكنك الآن مراجعة تفسيرات نموذج توصيات المنتج.</span><span class="sxs-lookup"><span data-stu-id="7ad72-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="7ad72-202">لمزيد من المعلومات، راجع [مراجعة حاله ونتائج التنبؤ](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="7ad72-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="7ad72-203">المهمة 5 - إنشاء شريحة من المنتجات ذات مستويات شراء عالية</span><span class="sxs-lookup"><span data-stu-id="7ad72-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="7ad72-204">يؤدي تشغيل نموذج الإنتاج إلى إنشاء كيان جديد يمكنك رؤيته في **البيانات** > **الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="7ad72-205">يمكنك إنشاء شريحة جديدة استنادًا إلى الكيان الذي تم إنشاؤه بواسطة النموذج.</span><span class="sxs-lookup"><span data-stu-id="7ad72-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="7ad72-206">انتقل إلى **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-206">Go to **Segments**.</span></span> <span data-ttu-id="7ad72-207">حدد **جديد** واختر **إنشاء من** > **الذكاء**.</span><span class="sxs-lookup"><span data-stu-id="7ad72-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![إنشاء شريحة بواسطة إخراج النموذج.](media/segment-intelligence.png)

1. <span data-ttu-id="7ad72-209">حدد نقطة النهاية **OOBProductRecommendationModelPrediction** وحدد الشريحة:</span><span class="sxs-lookup"><span data-stu-id="7ad72-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="7ad72-210">الحقل: ProductID</span><span class="sxs-lookup"><span data-stu-id="7ad72-210">Field: ProductID</span></span>
   - <span data-ttu-id="7ad72-211">عامل التشغيل: القيمة</span><span class="sxs-lookup"><span data-stu-id="7ad72-211">Operator: Value</span></span>
   - <span data-ttu-id="7ad72-212">القيمة: حدد معرفات أهم ثلاثة منتجات</span><span class="sxs-lookup"><span data-stu-id="7ad72-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="إنشاء شريحة من نتائج النموذج.":::

<span data-ttu-id="7ad72-214">لديك الآن شريحة يتم تم تحديثها بطريقة ديناميكية تحدد العملاء الأكثر رغبة في شراء أفضل ثلاثة منتجات مستحسنة‬</span><span class="sxs-lookup"><span data-stu-id="7ad72-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="7ad72-215">لمزيد من المعلومات، راجع [إنشاء شرائح وإدارتها](segments.md).</span><span class="sxs-lookup"><span data-stu-id="7ad72-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
