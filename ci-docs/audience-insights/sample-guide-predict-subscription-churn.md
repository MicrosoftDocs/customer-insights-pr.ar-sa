---
title: دليل نموذج التنبؤ بخسارة الاشتراك‬
description: استخدم هذا النموذج للتعرف على النموذج الجاهز للتنبؤ بخسارة الاشتراك‬.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269820"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="62f92-103">دليل نموذج التنبؤ بخسارة الاشتراك‬ (معاينة)</span><span class="sxs-lookup"><span data-stu-id="62f92-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="62f92-104">سوف نرشدك عبر مثال شامل للتنبؤ بخسارة الاشتراك باستخدام البيانات المتوفرة أدناه.</span><span class="sxs-lookup"><span data-stu-id="62f92-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="62f92-105">السيناريو</span><span class="sxs-lookup"><span data-stu-id="62f92-105">Scenario</span></span>

<span data-ttu-id="62f92-106">إن Contoso هي شركه تنتج قهوة عالية الجودة وأجهزة عالية الجودة لصنع القهوة، تبيعها عبر موقع الويب Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="62f92-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="62f92-107">بدأت هذه الشركة مؤخرًا في أعمال الاشتراكات لعملائها للحصول على القهوة بشكل منتظم.</span><span class="sxs-lookup"><span data-stu-id="62f92-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="62f92-108">يركّز هدف هذه الشركة على معرفة العملاء المشتركين الذين قد يعملون على إلغاء اشتراكهم في الأشهر القليلة القادمة.</span><span class="sxs-lookup"><span data-stu-id="62f92-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="62f92-109">من شأن اطّلاع الشركة على الذين **سيتوقفون عن التعامل معها على الأرجح** أن يساعدها على توفير جهودها التسويقية من خلال التركيز على استبقائهم.</span><span class="sxs-lookup"><span data-stu-id="62f92-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="62f92-110">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="62f92-110">Prerequisites</span></span>

- <span data-ttu-id="62f92-111">على الأقل [أذونات المساهم](permissions.md) في Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="62f92-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="62f92-112">نحن ننصح بتنفيذ الخطوات التالية [في بيئة جديدة](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="62f92-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="62f92-113">المهمة 1 - استيعاب البيانات</span><span class="sxs-lookup"><span data-stu-id="62f92-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="62f92-114">راجع المقالات [حول استيعاب البيانات](data-sources.md) و[استيراد مصادر البيانات باستخدام موصلات Power Query](connect-power-query.md) على وجه التحديد.</span><span class="sxs-lookup"><span data-stu-id="62f92-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="62f92-115">تفترض المعلومات التالية أنك ملمّ باستيعاب البيانات بشكل عام.</span><span class="sxs-lookup"><span data-stu-id="62f92-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="62f92-116">استيعاب بيانات العملاء من النظام الأساسي للتجارة الإلكترونية</span><span class="sxs-lookup"><span data-stu-id="62f92-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="62f92-117">أنشئ مصدر بيانات باسم **التجارة الإلكترونية**، وحدد خيار الاستيراد، ثم حدد الموصل **النص/CSV**.</span><span class="sxs-lookup"><span data-stu-id="62f92-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="62f92-118">أدخل عنوان URL لجهات اتصال التجارة الإلكترونية https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="62f92-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="62f92-119">أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.</span><span class="sxs-lookup"><span data-stu-id="62f92-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="62f92-120">حدّث نوع البيانات للأعمدة المدرجة أدناه:</span><span class="sxs-lookup"><span data-stu-id="62f92-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="62f92-121">**DateOfBirth**: التاريخ</span><span class="sxs-lookup"><span data-stu-id="62f92-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="62f92-122">**CreatedOn**: التاريخ/الوقت/المنطقة</span><span class="sxs-lookup"><span data-stu-id="62f92-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="تحويل تاريخ الولادة إلى تاريخ.":::

1. <span data-ttu-id="62f92-124">في حقل **الاسم‏‎** في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام** إلى **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="62f92-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="62f92-125">احفظ مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="62f92-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="62f92-126">استيعاب بيانات العملاء من مخطط الولاء</span><span class="sxs-lookup"><span data-stu-id="62f92-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="62f92-127">أنشئ مصدر بيانات باسم **LoyaltyScheme**، وحدد خيار الاستيراد، ثم حدد الموصل **النص/CSV**.</span><span class="sxs-lookup"><span data-stu-id="62f92-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="62f92-128">أدخل عنوان URL لجهات اتصال التجارة الإلكترونية https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="62f92-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="62f92-129">أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.</span><span class="sxs-lookup"><span data-stu-id="62f92-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="62f92-130">حدّث نوع البيانات للأعمدة المدرجة أدناه:</span><span class="sxs-lookup"><span data-stu-id="62f92-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="62f92-131">**DateOfBirth**: التاريخ</span><span class="sxs-lookup"><span data-stu-id="62f92-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="62f92-132">**RewardsPoints**: عدد صحيح</span><span class="sxs-lookup"><span data-stu-id="62f92-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="62f92-133">**CreatedOn**: التاريخ/الوقت</span><span class="sxs-lookup"><span data-stu-id="62f92-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="62f92-134">في حقل **الاسم** في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام‏‎** إلى **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="62f92-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="62f92-135">احفظ مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="62f92-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="62f92-136">استيعاب معلومات الاشتراك</span><span class="sxs-lookup"><span data-stu-id="62f92-136">Ingest subscription information</span></span>

1. <span data-ttu-id="62f92-137">أنشئ مصدر بيانات باسم **SubscriptionHistory‎**، وحدد خيار الاستيراد، ثم حدد الموصل **النص/CSV**.</span><span class="sxs-lookup"><span data-stu-id="62f92-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="62f92-138">أدخل عنوان URL لجهات اتصال التجارة الإلكترونية https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="62f92-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="62f92-139">أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.</span><span class="sxs-lookup"><span data-stu-id="62f92-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="62f92-140">حدّث نوع البيانات للأعمدة المدرجة أدناه:</span><span class="sxs-lookup"><span data-stu-id="62f92-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="62f92-141">**SubscriptioID**: عدد صحيح</span><span class="sxs-lookup"><span data-stu-id="62f92-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="62f92-142">**SubscriptionAmount**: العملة</span><span class="sxs-lookup"><span data-stu-id="62f92-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="62f92-143">**SubscriptionEndDate**: التاريخ/الوقت</span><span class="sxs-lookup"><span data-stu-id="62f92-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="62f92-144">**SubscriptionStartDate**: التاريخ/الوقت</span><span class="sxs-lookup"><span data-stu-id="62f92-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="62f92-145">**TransactionDate**: التاريخ/الوقت</span><span class="sxs-lookup"><span data-stu-id="62f92-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="62f92-146">**IsRecurring**: صواب/خطأ</span><span class="sxs-lookup"><span data-stu-id="62f92-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="62f92-147">**Is_auto_renew**: صواب/خطأ</span><span class="sxs-lookup"><span data-stu-id="62f92-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="62f92-148">**RecurringFrequencyInMonths**: عدد صحيح</span><span class="sxs-lookup"><span data-stu-id="62f92-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="62f92-149">في حقل **الاسم** في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام‏‎** إلى **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="62f92-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="62f92-150">احفظ مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="62f92-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="62f92-151">استيعاب بيانات العملاء من مراجعات موقع الويب</span><span class="sxs-lookup"><span data-stu-id="62f92-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="62f92-152">أنشئ مصدر بيانات باسم **موقع الويب**، وحدد خيار الاستيراد، ثم حدد الموصل **النص/CSV**.</span><span class="sxs-lookup"><span data-stu-id="62f92-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="62f92-153">أدخل عنوان URL لجهات اتصال التجارة الإلكترونية https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="62f92-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="62f92-154">أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.</span><span class="sxs-lookup"><span data-stu-id="62f92-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="62f92-155">حدّث نوع البيانات للأعمدة المدرجة أدناه:</span><span class="sxs-lookup"><span data-stu-id="62f92-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="62f92-156">**ReviewRating**: عدد صحيح</span><span class="sxs-lookup"><span data-stu-id="62f92-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="62f92-157">**ReviewDate**: التاريخ</span><span class="sxs-lookup"><span data-stu-id="62f92-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="62f92-158">في حقل "الاسم" في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام** إلى **‎webReviews**</span><span class="sxs-lookup"><span data-stu-id="62f92-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="62f92-159">المهمة 2 - توحيد البيانات</span><span class="sxs-lookup"><span data-stu-id="62f92-159">Task 2 - Data unification</span></span>

<span data-ttu-id="62f92-160">بعد استيعاب البيانات، نبدأ الآن عملية **التعيين، المطابقة، الدمج** لإنشاء ملف تعريف عميل موحد.</span><span class="sxs-lookup"><span data-stu-id="62f92-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="62f92-161">لمزيد من المعلومات، راجع [توحيد البيانات](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="62f92-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="62f92-162">المخطط</span><span class="sxs-lookup"><span data-stu-id="62f92-162">Map</span></span>

1. <span data-ttu-id="62f92-163">بعد استيعاب البيانات، قم بتعيين جهات الاتصال من بيانات التجارة الإلكترونية والولاء إلى أنواع البيانات الشائعة.</span><span class="sxs-lookup"><span data-stu-id="62f92-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="62f92-164">انتقل إلى **البيانات** > **توحيد** > **تعيين**.</span><span class="sxs-lookup"><span data-stu-id="62f92-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="62f92-165">حدد الكيانات التي تمثل ملف تعريف العميل – **eCommerceContacts** و **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="62f92-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="توحيد مصادر بيانات التجارة الإلكترونية والولاء.":::

1. <span data-ttu-id="62f92-167">حدد **ContactId** كمفتاح أساسي لـ **eCommerceContacts** و **LoyaltyID** كمفتاح أساسي لـ **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="62f92-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="توحيد LoyaltyId كمفتاح أساسي.":::

### <a name="match"></a><span data-ttu-id="62f92-169">مطابقة</span><span class="sxs-lookup"><span data-stu-id="62f92-169">Match</span></span>

1. <span data-ttu-id="62f92-170">انتقل إلى علامة التبويب **مطابقة** وحدد **تعيين الأمر**.</span><span class="sxs-lookup"><span data-stu-id="62f92-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="62f92-171">من القائمة المنسدلة **أساسي**، اختر **eCommerceContacts : eCommerce** كمصدر أساسي وقم بتضمين جميع السجلات.</span><span class="sxs-lookup"><span data-stu-id="62f92-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="62f92-172">في القائمة المنسدلة **الكيان 2**، اختر **loyCustomers : LoyaltyScheme** وقم بتضمين جميع السجلات.</span><span class="sxs-lookup"><span data-stu-id="62f92-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="توحيد مطابقة التجارة الإلكترونية والولاء.":::

1. <span data-ttu-id="62f92-174">حدد **إنشاء قاعدة جديدة**</span><span class="sxs-lookup"><span data-stu-id="62f92-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="62f92-175">أضف الشرط الأول باستخدام FullName.</span><span class="sxs-lookup"><span data-stu-id="62f92-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="62f92-176">لخيار eCommerceContacts، حدد **FullName‎** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="62f92-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="62f92-177">لخيار loyCustomers، حدد **FullName‎** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="62f92-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="62f92-178">حدد القائمة المنسدلة **تسوية**، واختر **النوع (الهاتف والاسم والعنوان و...)**.</span><span class="sxs-lookup"><span data-stu-id="62f92-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="62f92-179">عيّن **مستوى الدقة**: **أساسي** و **قيمة**: **عالي**.</span><span class="sxs-lookup"><span data-stu-id="62f92-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="62f92-180">أدخل الاسم **FullName, Email** للقاعدة الجديدة.</span><span class="sxs-lookup"><span data-stu-id="62f92-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="62f92-181">أضف شرطًا ثانيًا لعنوان البريد الإلكتروني من خلال تحديد **إضافة شرط**</span><span class="sxs-lookup"><span data-stu-id="62f92-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="62f92-182">للكيان eCommerceContacts، حدد **EMail** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="62f92-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="62f92-183">للكيان loyCustomers، حدد **EMail** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="62f92-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="62f92-184">اترك الخيار "تسوية" فارغًا.</span><span class="sxs-lookup"><span data-stu-id="62f92-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="62f92-185">عيّن **مستوى الدقة**: **أساسي** و **قيمة**: **عالي**.</span><span class="sxs-lookup"><span data-stu-id="62f92-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="توحيد قاعدة مطابقة للاسم والبريد الإلكتروني.":::

7. <span data-ttu-id="62f92-187">حدد **حفظ** و **تشغيل**.</span><span class="sxs-lookup"><span data-stu-id="62f92-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="62f92-188">‏‏دمج</span><span class="sxs-lookup"><span data-stu-id="62f92-188">Merge</span></span>

1. <span data-ttu-id="62f92-189">انقر فوق علامة التبويب **دمج**.</span><span class="sxs-lookup"><span data-stu-id="62f92-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="62f92-190">على **ContactId** للكيان **loyCustomers** ، قم بتغيير الاسم المعروض إلى **ContactIdLOYALTY** لتمييزه عن المعرفات الأخرى التي تم استيعابها.</span><span class="sxs-lookup"><span data-stu-id="62f92-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="إعادة تسمية contactid من معرف الولاء.":::

1. <span data-ttu-id="62f92-192">حدد **حفظ** و **تشغيل** لبدء عملية الدمج.</span><span class="sxs-lookup"><span data-stu-id="62f92-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="62f92-193">المهمة 3 - تكوين التنبؤ بخسارة الاشتراك</span><span class="sxs-lookup"><span data-stu-id="62f92-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="62f92-194">من خلال وضع ملفات تعريف العملاء الموحدة، يمكننا الآن تشغيل التنبؤ بخسارة الاشتراك.</span><span class="sxs-lookup"><span data-stu-id="62f92-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="62f92-195">للحصول على خطوات تفصيلية، راجع المقالة [التنبؤ بخسارة الاشتراك (معاينة)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="62f92-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="62f92-196">انتقل إلى **الذكاء** > **اكتشاف** وحدد لاستخدام **نموذج خسارة العملاء**.</span><span class="sxs-lookup"><span data-stu-id="62f92-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="62f92-197">حدد الخيار **اشتراك‬‬** وحدد **الشروع في العمل** .</span><span class="sxs-lookup"><span data-stu-id="62f92-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="62f92-198">أدخل الاسم **OOB التنبؤ بخسارة الاشتراك OOB‬‬** للنموذج والاسم **OOBSubscriptionChurnPrediction** لكيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="62f92-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="62f92-199">قم بتعريف شرطين لنموذج الخسارة:</span><span class="sxs-lookup"><span data-stu-id="62f92-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="62f92-200">**عدد الأيام منذ انتهاء الاشتراك**: **60 يومًا على الأقل**.</span><span class="sxs-lookup"><span data-stu-id="62f92-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="62f92-201">إذا لم يقم العميل بتجديد اشتراكه في هذه الفترة بعد انتهاء اشتراكه، فسيتم اعتباره في فئة العملاء الذين تمت خسارتهم.</span><span class="sxs-lookup"><span data-stu-id="62f92-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="62f92-202">**تعريف الخسارة**: **93 يومًا على الأقل**.</span><span class="sxs-lookup"><span data-stu-id="62f92-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="62f92-203">المدة التي سيقوم النموذج فيها بالتنبؤ بالعملاء الذين قد تتم خسارتهم.</span><span class="sxs-lookup"><span data-stu-id="62f92-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="62f92-204">كلما تعمقت بالنظر إلى المستقبل، ستكون النتائج أقل دقة.</span><span class="sxs-lookup"><span data-stu-id="62f92-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="حدد نموذج إطار التنبؤ وتعريف الخسارة.":::

1. <span data-ttu-id="62f92-206">حدد **إضافة البيانات المطلوبة** وحدد **إضافة بيانات** لمحفوظات الاشتراكات.</span><span class="sxs-lookup"><span data-stu-id="62f92-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="62f92-207">أضف الكيان **الاشتراك : SubscriptionHistory** وعيّن الحقل من التجارة الإلكترونية إلى الحقول المناظرة التي يطلبها النموذج.</span><span class="sxs-lookup"><span data-stu-id="62f92-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="62f92-208">انضمّ إلى **الاشتراك : SubscriptionHistory** بالاسم **eCommerceContacts : eCommerce**، وقم بتسمية العلامة **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="62f92-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="الانضمام إلى كيانات التجارة الإلكترونية.":::

1. <span data-ttu-id="62f92-210">ضمن أنشطة العميل، أضف الكيان **webReviews: موقع الويب** وعيّن الحقول من webReviews إلى الحقول المناظرة التي يطلبها النموذج.</span><span class="sxs-lookup"><span data-stu-id="62f92-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="62f92-211">المفتاح الأساسي: ReviewId</span><span class="sxs-lookup"><span data-stu-id="62f92-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="62f92-212">الطابع الزمني: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="62f92-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="62f92-213">الحدث: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="62f92-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="62f92-214">كوّن نشاطًا لمراجعات موقع ويب.</span><span class="sxs-lookup"><span data-stu-id="62f92-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="62f92-215">حدد نشاط **المراجعة** وانضمّ إلى الكيان **webReviews: موقع الويب** مع **eCommerceContacts: التجارة الإلكترونية**.</span><span class="sxs-lookup"><span data-stu-id="62f92-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="62f92-216">حدد **التالي** لتعيين جدول النماذج.</span><span class="sxs-lookup"><span data-stu-id="62f92-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="62f92-217">يحتاج النموذج إلى التدريب بشكل منتظم للتعرف على الأنماط الجديدة عند وجود بيانات جديدة تم استيعابها.</span><span class="sxs-lookup"><span data-stu-id="62f92-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="62f92-218">لهذا المثال، حدد **شهري**.</span><span class="sxs-lookup"><span data-stu-id="62f92-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="62f92-219">بعد مراجعة كافة التفاصيل ، حدد **حفظ وتشغيل**.</span><span class="sxs-lookup"><span data-stu-id="62f92-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="62f92-220">المهمة 4 - مراجعة نتائج وتفسيرات النماذج</span><span class="sxs-lookup"><span data-stu-id="62f92-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="62f92-221">دع النموذج يكمل تدريب وتسجيل نقاط البيانات.</span><span class="sxs-lookup"><span data-stu-id="62f92-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="62f92-222">يمكنك الآن مراجعة تفسيرات نموذج خسارة بالاشتراك.</span><span class="sxs-lookup"><span data-stu-id="62f92-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="62f92-223">لمزيد من المعلومات، راجع [مراجعة حاله ونتائج التنبؤ](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="62f92-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="62f92-224">المهمة 5 - إنشاء شريحة من العملاء مخاطر خسارتهم عالية</span><span class="sxs-lookup"><span data-stu-id="62f92-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="62f92-225">يؤدي تشغيل نموذج الإنتاج إلى إنشاء كيان جديد يمكنك رؤيته في **البيانات** > **الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="62f92-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="62f92-226">يمكنك إنشاء شريحة جديدة استنادًا إلى الكيان الذي تم إنشاؤه بواسطة النموذج.</span><span class="sxs-lookup"><span data-stu-id="62f92-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="62f92-227">انتقل إلى **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="62f92-227">Go to **Segments**.</span></span> <span data-ttu-id="62f92-228">حدد **جديد** واختر **إنشاء من** > **الذكاء**.</span><span class="sxs-lookup"><span data-stu-id="62f92-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="إنشاء شريحة بواسطة إخراج النموذج.":::

1. <span data-ttu-id="62f92-230">حدد نقطة النهاية **OOBSubscriptionChurnPrediction** وحدد الشريحة:</span><span class="sxs-lookup"><span data-stu-id="62f92-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="62f92-231">الحقل: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="62f92-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="62f92-232">عامل التشغيل: أكبر من</span><span class="sxs-lookup"><span data-stu-id="62f92-232">Operator: greater than</span></span>
   - <span data-ttu-id="62f92-233">القيمة: 0.6</span><span class="sxs-lookup"><span data-stu-id="62f92-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="إعداد شريحة خسارة الاشتراك.":::

<span data-ttu-id="62f92-235">لديك الآن شريحة يتم تحديثها بشكل ديناميكي مما يحدد العملاء الذين تبدو مخاطر خسارتهم عالية‬ لعمل الاشتراك هذا.</span><span class="sxs-lookup"><span data-stu-id="62f92-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="62f92-236">لمزيد من المعلومات، راجع [إنشاء شرائح وإدارتها](segments.md).</span><span class="sxs-lookup"><span data-stu-id="62f92-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]