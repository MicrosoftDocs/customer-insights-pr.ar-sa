---
title: دليل نموذجي لتنبؤات القيمة العمرية للعميل
description: استخدم هذا الدليل النموذجي لتجربة نموذج تنبؤات القيمة العمرية للعميل.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129929"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="df42b-103">الدليل النموذجي لتنبؤات القيمة العمرية للعميل (CLV)</span><span class="sxs-lookup"><span data-stu-id="df42b-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="df42b-104">سينقلك هذا الدليل عبر مثال شامل عن تنبؤات القيمة العمرية للعميل (CLV) في Customer Insights باستخدام عينة بيانات.</span><span class="sxs-lookup"><span data-stu-id="df42b-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="df42b-105">السيناريو</span><span class="sxs-lookup"><span data-stu-id="df42b-105">Scenario</span></span>

<span data-ttu-id="df42b-106">تتميز شركة Contoso بإنتاج قهوة عالية الجودة إلى جانب آلات لصنع القهوة.</span><span class="sxs-lookup"><span data-stu-id="df42b-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="df42b-107">وهي تبيع منتجاتها عبر موقع Contoso Coffee website.</span><span class="sxs-lookup"><span data-stu-id="df42b-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="df42b-108">تريد الشركة فهم القيمة (الإيرادات) التي يمكن لعملائها توليدها خلال الأشهر الـ 12 المقبلة.</span><span class="sxs-lookup"><span data-stu-id="df42b-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="df42b-109">من شأن معرفة القيمة المتوقعة لعملائها في الأشهر الـ 12 المقبلة أن يساعدها على توجيه جهودها التسويقية على العملاء من ذوي القيمة العالية.</span><span class="sxs-lookup"><span data-stu-id="df42b-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="df42b-110">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="df42b-110">Prerequisites</span></span>

- <span data-ttu-id="df42b-111">[أذونات المساهم](permissions.md) على الأقل في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="df42b-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="df42b-112">نحن ننصح بتنفيذ الخطوات التالية [في بيئة جديدة](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="df42b-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="df42b-113">المهمة 1 - استيعاب البيانات</span><span class="sxs-lookup"><span data-stu-id="df42b-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="df42b-114">راجع المقالات [حول استيعاب البيانات](data-sources.md) و [استيراد مصادر البيانات باستخدام موصلات Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="df42b-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="df42b-115">تفترض المعلومات التالية أنك ملمّ باستيعاب البيانات بشكل عام.</span><span class="sxs-lookup"><span data-stu-id="df42b-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="df42b-116">استيعاب بيانات العملاء من النظام الأساسي للتجارة الإلكترونية</span><span class="sxs-lookup"><span data-stu-id="df42b-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="df42b-117">أنشئ مصدر بيانات باسم  **التجارة الإلكترونية** , وحدد خيار الاستيراد، ثم حدد الموصل **النص/CSV**.</span><span class="sxs-lookup"><span data-stu-id="df42b-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="df42b-118">أدخل عنوان URL لجهات اتصال التجارة الإلكترونية [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="df42b-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="df42b-119">أثناء تحرير البيانات، حدد  **تحويل‏‎**، ثم حدد  **استخدام الصف الأول كرؤوس**.</span><span class="sxs-lookup"><span data-stu-id="df42b-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="df42b-120">حدّث نوع البيانات للأعمدة المدرجة أدناه:</span><span class="sxs-lookup"><span data-stu-id="df42b-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="df42b-121">**DateOfBirth**: التاريخ</span><span class="sxs-lookup"><span data-stu-id="df42b-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="df42b-122">**CreatedOn**: التاريخ/الوقت/المنطقة</span><span class="sxs-lookup"><span data-stu-id="df42b-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="تحويل تاريخ الولادة إلى تاريخ.":::

1. <span data-ttu-id="df42b-124">في حقل "الاسم" في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام** إلى **‎eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="df42b-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="df42b-125">**احفظ** مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="df42b-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="df42b-126">استيعاب بيانات شراء عبر الإنترنت</span><span class="sxs-lookup"><span data-stu-id="df42b-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="df42b-127">أضف مجموعة بيانات أخرى إلى مصدر البيانات **التجارة الإلكترونية**.</span><span class="sxs-lookup"><span data-stu-id="df42b-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="df42b-128">اختر الموصل **النص/CSV** مرة أخرى.</span><span class="sxs-lookup"><span data-stu-id="df42b-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="df42b-129">أدخل عنوان URL لبيانات **المشتريات عبر الإنترنت** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="df42b-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="df42b-130">أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.</span><span class="sxs-lookup"><span data-stu-id="df42b-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="df42b-131">حدّث نوع البيانات للأعمدة المدرجة أدناه:</span><span class="sxs-lookup"><span data-stu-id="df42b-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="df42b-132">**PurchasedOn**: التاريخ/الوقت</span><span class="sxs-lookup"><span data-stu-id="df42b-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="df42b-133">**TotalPrice**: العملة</span><span class="sxs-lookup"><span data-stu-id="df42b-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="df42b-134">في حقل **الاسم** في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام‏‎** إلى **مشتريات التجارة الإلكترونية**.</span><span class="sxs-lookup"><span data-stu-id="df42b-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="df42b-135">**احفظ** مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="df42b-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="df42b-136">استيعاب بيانات العملاء من مخطط الولاء</span><span class="sxs-lookup"><span data-stu-id="df42b-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="df42b-137">أنشئ مصدر بيانات باسم **LoyaltyScheme**، وحدد خيار الاستيراد، ثم حدد الموصل **النص/CSV**.</span><span class="sxs-lookup"><span data-stu-id="df42b-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="df42b-138">أدخل عنوان URL لجهات اتصال التجارة الإلكترونية https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="df42b-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="df42b-139">أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.</span><span class="sxs-lookup"><span data-stu-id="df42b-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="df42b-140">حدّث نوع البيانات للأعمدة المدرجة أدناه:</span><span class="sxs-lookup"><span data-stu-id="df42b-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="df42b-141">**DateOfBirth**: التاريخ</span><span class="sxs-lookup"><span data-stu-id="df42b-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="df42b-142">**RewardsPoints**: عدد صحيح</span><span class="sxs-lookup"><span data-stu-id="df42b-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="df42b-143">**CreatedOn**: التاريخ/الوقت</span><span class="sxs-lookup"><span data-stu-id="df42b-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="df42b-144">في حقل **الاسم** في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام‏‎** إلى **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="df42b-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="df42b-145">**احفظ** مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="df42b-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="df42b-146">استيعاب بيانات العملاء من مراجعات موقع الويب</span><span class="sxs-lookup"><span data-stu-id="df42b-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="df42b-147">أنشئ مصدر بيانات باسم **موقع الويب**، وحدد خيار الاستيراد، ثم حدد الموصل **النص/CSV**.</span><span class="sxs-lookup"><span data-stu-id="df42b-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="df42b-148">أدخل عنوان URL لجهات اتصال التجارة الإلكترونية https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="df42b-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="df42b-149">أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.</span><span class="sxs-lookup"><span data-stu-id="df42b-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="df42b-150">حدّث نوع البيانات للأعمدة المدرجة أدناه:</span><span class="sxs-lookup"><span data-stu-id="df42b-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="df42b-151">**ReviewRating**: عدد عشري</span><span class="sxs-lookup"><span data-stu-id="df42b-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="df42b-152">**ReviewDate**: التاريخ</span><span class="sxs-lookup"><span data-stu-id="df42b-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="df42b-153">في احقل "الاسم" في الجزء الأيسر، أعد تسمية مصدر البيانات من **استعلام** إلى **مراجعات**.</span><span class="sxs-lookup"><span data-stu-id="df42b-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="df42b-154">**احفظ** مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="df42b-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="df42b-155">المهمة 2 - توحيد البيانات</span><span class="sxs-lookup"><span data-stu-id="df42b-155">Task 2 - Data unification</span></span>

<span data-ttu-id="df42b-156">بعد استيعاب البيانات، نبدأ الآن عملية توحيد البيانات لإنشاء ملف تعريف عميل موحد.</span><span class="sxs-lookup"><span data-stu-id="df42b-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="df42b-157">لمزيد من المعلومات، راجع [توحيد البيانات](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="df42b-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="df42b-158">المخطط</span><span class="sxs-lookup"><span data-stu-id="df42b-158">Map</span></span>

1. <span data-ttu-id="df42b-159">بعد استيعاب البيانات، قم بتعيين جهات الاتصال من بيانات التجارة الإلكترونية والولاء إلى أنواع البيانات الشائعة.</span><span class="sxs-lookup"><span data-stu-id="df42b-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="df42b-160">انتقل إلى **البيانات** > **توحيد** > **تعيين**.</span><span class="sxs-lookup"><span data-stu-id="df42b-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="df42b-161">حدد الكيانات التي تمثل ملف تعريف العميل – **eCommerceContacts** و **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="df42b-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="df42b-162">ثم حدد **تطبيق**.</span><span class="sxs-lookup"><span data-stu-id="df42b-162">Then, select **Apply**.</span></span>

   ![توحيد مصادر بيانات التجارة الإلكترونية والولاء.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="df42b-164">حدد **ContactId** كمفتاح أساسي لـ **eCommerceContacts** و **LoyaltyID** كمفتاح أساسي لـ **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="df42b-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![توحيد LoyaltyId كمفتاح أساسي.](media/unify-loyaltyid.png)

1. <span data-ttu-id="df42b-166">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="df42b-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="df42b-167">مطابقة</span><span class="sxs-lookup"><span data-stu-id="df42b-167">Match</span></span>

1. <span data-ttu-id="df42b-168">انتقل إلى علامة التبويب **مطابقة** وحدد **تعيين الأمر**.</span><span class="sxs-lookup"><span data-stu-id="df42b-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="df42b-169">من القائمة المنسدلة **أساسي**، اختر **eCommerceContacts : eCommerce** كمصدر أساسي وقم بتضمين جميع السجلات.</span><span class="sxs-lookup"><span data-stu-id="df42b-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="df42b-170">في القائمة المنسدلة **الكيان 2**، اختر **loyCustomers : LoyaltyScheme** وقم بتضمين جميع السجلات.</span><span class="sxs-lookup"><span data-stu-id="df42b-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![توحيد مطابقة التجارة الإلكترونية والولاء.](media/unify-match-order.png)

1. <span data-ttu-id="df42b-172">حدد **إضافة قاعدة**</span><span class="sxs-lookup"><span data-stu-id="df42b-172">Select **Add rule**</span></span>

1. <span data-ttu-id="df42b-173">أضف الشرط الأول باستخدام FullName.</span><span class="sxs-lookup"><span data-stu-id="df42b-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="df42b-174">لخيار eCommerceContacts، حدد **FullName‎** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="df42b-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="df42b-175">لخيار loyCustomers، حدد **FullName‎** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="df42b-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="df42b-176">حدد القائمة المنسدلة **تسوية**، واختر **النوع (الهاتف والاسم والعنوان و...)**.</span><span class="sxs-lookup"><span data-stu-id="df42b-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="df42b-177">عيّن **مستوى الدقة**: **أساسي** و **قيمة**: **عالي**.</span><span class="sxs-lookup"><span data-stu-id="df42b-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="df42b-178">أدخل الاسم **FullName, Email** للقاعدة الجديدة.</span><span class="sxs-lookup"><span data-stu-id="df42b-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="df42b-179">أضف شرطًا ثانيًا لعنوان البريد الإلكتروني من خلال تحديد **إضافة شرط**</span><span class="sxs-lookup"><span data-stu-id="df42b-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="df42b-180">للكيان eCommerceContacts، حدد **EMail** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="df42b-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="df42b-181">للكيان loyCustomers، حدد **EMail** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="df42b-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="df42b-182">اترك الخيار "تسوية" فارغًا.</span><span class="sxs-lookup"><span data-stu-id="df42b-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="df42b-183">عيّن **مستوى الدقة**: **أساسي** و **قيمة**: **عالي**.</span><span class="sxs-lookup"><span data-stu-id="df42b-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![توحيد قاعدة مطابقة للاسم والبريد الإلكتروني.](media/unify-match-rule.png)

1. <span data-ttu-id="df42b-185">حدد **تم**.</span><span class="sxs-lookup"><span data-stu-id="df42b-185">Select **Done**.</span></span>

1. <span data-ttu-id="df42b-186">حدد **حفظ** و **تشغيل**.</span><span class="sxs-lookup"><span data-stu-id="df42b-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="df42b-187">‏‏دمج</span><span class="sxs-lookup"><span data-stu-id="df42b-187">Merge</span></span>

1. <span data-ttu-id="df42b-188">انقر فوق علامة التبويب **دمج**.</span><span class="sxs-lookup"><span data-stu-id="df42b-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="df42b-189">على **ContactId** للكيان **loyCustomers** ، قم بتغيير الاسم المعروض إلى **ContactIdLOYALTY** لتمييزه عن المعرفات الأخرى التي تم استيعابها.</span><span class="sxs-lookup"><span data-stu-id="df42b-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![إعادة تسمية contactid من معرف الولاء.](media/unify-merge-contactid.png)

1. <span data-ttu-id="df42b-191">حدد **حفظ** و **تشغيل عمليات الدمج والعمليات النهائية**.</span><span class="sxs-lookup"><span data-stu-id="df42b-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="df42b-192">المهمة 3 - تكوين تنبؤ القيمة العمرية للعميل.</span><span class="sxs-lookup"><span data-stu-id="df42b-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="df42b-193">مع إنشاء ملفات تعريف العملاء الموحدة، يمكننا الآن تشغيل تنبؤ القيمة العمرية للعميل.‬</span><span class="sxs-lookup"><span data-stu-id="df42b-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="df42b-194">للاطلاع على الخطوات المفصلة، راجع [تنبؤ القيمة العمرية للعميل‬ (معاينة)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="df42b-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="df42b-195">انتقل إلى  **الذكاء**  > **التنبؤات**  وحدد **نموذج القيمة العمرية للعميل**.</span><span class="sxs-lookup"><span data-stu-id="df42b-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="df42b-196">تنقل عبر المعلومات الموجودة في الجزء الجانبي وحدد **الشروع في العمل**.</span><span class="sxs-lookup"><span data-stu-id="df42b-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="df42b-197">قم بتسمية النموذج **OOB eCommerce CLV Prediction** وكيان الإخراج  **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="df42b-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="df42b-198">عدد تفضيلات النموذج لنموذج القيمة العمرية للعميل:</span><span class="sxs-lookup"><span data-stu-id="df42b-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="df42b-199">**الفترة الزمنية للتنبؤ‬**: **12 شهرًا أو سنة واحدة**.</span><span class="sxs-lookup"><span data-stu-id="df42b-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="df42b-200">يحدد هذا الإعداد إلى أي مدى في المستقبل تريد التنبؤ بالقيمة العمرية العميل.</span><span class="sxs-lookup"><span data-stu-id="df42b-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="df42b-201">**العملاء النشطاء**: حدد ما يعنيه العملاء النشطاء لأعمالك.</span><span class="sxs-lookup"><span data-stu-id="df42b-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="df42b-202">عيّن الإطار الزمني السابق الذي يجب على العميل أن يكون قد نفّذ خلاله حركة واحدة على الأقل يمكن اعتبارها نشطة.</span><span class="sxs-lookup"><span data-stu-id="df42b-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="df42b-203">سيتنبأ النموذج قيمة مدى بقاء العميل للعملاء النشطاء فقط.</span><span class="sxs-lookup"><span data-stu-id="df42b-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="df42b-204">اختر بين السماح للنموذج بحساب الفترة الزمنية بالاستناد إلى بيانات الحركات السابقة أو قدّم إطارًا زمنيًا محددًا.</span><span class="sxs-lookup"><span data-stu-id="df42b-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="df42b-205">في هذا الدليل النموذجي سنختار **السماح للنموذج بحساب الفاصل الزمني الشراء**، وهو الخيار الافتراضي.</span><span class="sxs-lookup"><span data-stu-id="df42b-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="df42b-206">**العملاء ذوو القيمة العالية**: تعريف العملاء ذوو القيمة العالية كقيمة مئوية لأهم العملاء من ناحية الدفع.</span><span class="sxs-lookup"><span data-stu-id="df42b-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="df42b-207">يستخدم النموذج هذا الإدخال لتوفير نتائج تناسب تعريف أعمالك للعملاء من ذوي القيمة العالية.</span><span class="sxs-lookup"><span data-stu-id="df42b-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="df42b-208">يمكنك أن تختار السماح للنموذج بتحديد العملاء ذوي القيمة العالية.</span><span class="sxs-lookup"><span data-stu-id="df42b-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="df42b-209">إنه يستخدم قاعدة استكشافية تشتق منها القيمة المئوية.</span><span class="sxs-lookup"><span data-stu-id="df42b-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="df42b-210">يمكنك أيضًا تعريف العملاء ذوي القيمة العالية كقيمة مئوية لأهم العملاء من ناحية الدفع في المستقبل.</span><span class="sxs-lookup"><span data-stu-id="df42b-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="df42b-211">في هذا الدليل النموذجي، سنقوم يدويًا بتعريف العملاء ذوي القيمة العالية على أنهم **أهم 30% من العملاء النشطاء من ناحية الدفع** ثم نحدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="df42b-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="خطوة التفضيلات في التجربة موجهة لنموذج القيمة العمرية للعميل.":::

1. <span data-ttu-id="df42b-213">في الخطوة **البيانات المطلوبة**، حدد **إضافة بيانات** لتوفير بيانات سجل الحركة.</span><span class="sxs-lookup"><span data-stu-id="df42b-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="df42b-214">أضف الكيان **eCommercePurchases : التجارة الإلكترونية** وعيّن السمات المطلوبة بواسطة النموذج:</span><span class="sxs-lookup"><span data-stu-id="df42b-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="df42b-215">معرف الحركة: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="df42b-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="df42b-216">تاريخ الحركة: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="df42b-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="df42b-217">مبلغ الحركة: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="df42b-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="df42b-218">معرف المنتج: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="df42b-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="df42b-219">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="df42b-219">Select **Next**.</span></span>

1. <span data-ttu-id="df42b-220">قم بإعداد العلاقة بين الكيان **eCommercePurchases : التجارة الإلكترونية** و **eCommerceContacts : التجارة الإلكترونية**.</span><span class="sxs-lookup"><span data-stu-id="df42b-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="df42b-221">تتيح لك خطوة **البيانات الإضافية (اختيارية)** إضافة المزيد من بيانات نشاط العميل.</span><span class="sxs-lookup"><span data-stu-id="df42b-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="df42b-222">يمكن أن تساعدك هذه البيانات في الحصول على مزيد من الرؤى لتفاعلات العملاء مع أعمالك، مما يمكنه المساهمة في القيمة العمرية للعميل.</span><span class="sxs-lookup"><span data-stu-id="df42b-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="df42b-223">قد تؤدي إضافة تفاعلات العملاء الرئيسية مثل سجلات الويب أو سجلات خدمة العملاء أو محفوظات برنامج المكافآت إلى تحسين دقة التنبؤات.</span><span class="sxs-lookup"><span data-stu-id="df42b-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="df42b-224">حدد **إضافة بيانات** لتضمين المزيد من بيانات نشاط العميل.</span><span class="sxs-lookup"><span data-stu-id="df42b-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="df42b-225">أضف كيان نشاط العميل و قم بتعيين أسماء حقوله إلى الحقول المناظرة المطلوبة من قبل النموذج:</span><span class="sxs-lookup"><span data-stu-id="df42b-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="df42b-226">كيان نشاط العميل: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="df42b-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="df42b-227">المفتاح الأساسي: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="df42b-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="df42b-228">الطابع الزمني: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="df42b-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="df42b-229">الحدث (اسم النشاط): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="df42b-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="df42b-230">التفاصيل (المبلغ أو القيمة): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="df42b-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="df42b-231">حدد **التالي** وقم بتكوين النشاط والعلاقة بين بيانات الحركة وبيانات العميل:</span><span class="sxs-lookup"><span data-stu-id="df42b-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="df42b-232">نوع النشاط: اختر الموجود</span><span class="sxs-lookup"><span data-stu-id="df42b-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="df42b-233">تسمية النشاط: مراجعة</span><span class="sxs-lookup"><span data-stu-id="df42b-233">Activity label: Review</span></span>
   - <span data-ttu-id="df42b-234">التسمية المناظرة: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="df42b-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="df42b-235">كيان العميل: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="df42b-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="df42b-236">العلاقة: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="df42b-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="df42b-237">حدد **التالي** لتعيين جدول النماذج.</span><span class="sxs-lookup"><span data-stu-id="df42b-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="df42b-238">يحتاج النموذج إلى التدريب بشكل منتظم للتعرف على أنماط جديدة عند وجود بيانات جديدة تم استيعابها.</span><span class="sxs-lookup"><span data-stu-id="df42b-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="df42b-239">لهذا المثال، اختر **شهريًا**.</span><span class="sxs-lookup"><span data-stu-id="df42b-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="df42b-240">بعد مراجعة كافة التفاصيل، حدد **حفظ وتشغيل**.</span><span class="sxs-lookup"><span data-stu-id="df42b-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="df42b-241">المهمة 4 - مراجعة نتائج وتفسيرات النماذج</span><span class="sxs-lookup"><span data-stu-id="df42b-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="df42b-242">دع النموذج يكمل تدريب وتسجيل نقاط البيانات.</span><span class="sxs-lookup"><span data-stu-id="df42b-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="df42b-243">بعد ذلك، يمكنك مراجعة نتائج نموذج القيمة العمرية للعميل وشروحاتها.</span><span class="sxs-lookup"><span data-stu-id="df42b-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="df42b-244">لمزيد من المعلومات، راجع [مراجعة حاله ونتائج التنبؤ](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="df42b-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="df42b-245">المهمة 5 - إنشاء شريحة من العملاء ذوي القيمة العالية</span><span class="sxs-lookup"><span data-stu-id="df42b-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="df42b-246">يؤدي تشغيل النموذج إلى إنشاء كيان جديد، يكون مذكورًا في **البيانات** > **الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="df42b-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="df42b-247">يمكنك إنشاء شريحة عميل جديدة بالاستناد إلى الكيان الذي تم إنشاؤه بواسطة النموذج.</span><span class="sxs-lookup"><span data-stu-id="df42b-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="df42b-248">انتقل إلى **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="df42b-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="df42b-249">حدد **جديد** واختر **إنشاء من** > **الذكاء**.</span><span class="sxs-lookup"><span data-stu-id="df42b-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![إنشاء شريحة بواسطة إخراج النموذج.](media/segment-intelligence.png)

1. <span data-ttu-id="df42b-251">حدد الكيان  **OOBeCommerceCLVPrediction** وحدد الشريحة:</span><span class="sxs-lookup"><span data-stu-id="df42b-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="df42b-252">الحقل: CLVScore</span><span class="sxs-lookup"><span data-stu-id="df42b-252">Field: CLVScore</span></span>
  - <span data-ttu-id="df42b-253">عامل التشغيل: أكبر من</span><span class="sxs-lookup"><span data-stu-id="df42b-253">Operator: greater than</span></span>
  - <span data-ttu-id="df42b-254">القيمة: 1500</span><span class="sxs-lookup"><span data-stu-id="df42b-254">Value: 1500</span></span>

1. <span data-ttu-id="df42b-255">حدد **مراجعة** و **حفظ** الشريحة.</span><span class="sxs-lookup"><span data-stu-id="df42b-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="df42b-256">لديك الآن شريحة تحدد العملاء الذين تم التنبؤ بقدرتهم على توليد أكثر من 1500 دولار من الإيرادات خلال الأشهر الـ 12 المقبلة.</span><span class="sxs-lookup"><span data-stu-id="df42b-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="df42b-257">يتم تحديث هذه الشريحة بطريقة ديناميكية إذا تم استيعاب المزيد من البيانات.</span><span class="sxs-lookup"><span data-stu-id="df42b-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="df42b-258">لمزيد من المعلومات، راجع [إنشاء شرائح وإدارتها](segments.md).</span><span class="sxs-lookup"><span data-stu-id="df42b-258">For more information, see [Create and manage segments](segments.md).</span></span>
