---
title: دليل نموذج التنبؤ بخسارة المعاملة
description: استخدم هذا النموذج للتعرف على النموذج الجاهز للتنبؤ بخسارة المعاملة‬.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306104"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="f28ba-103">دليل نموذج التنبؤ بخسارة المعاملة (معاينة)</span><span class="sxs-lookup"><span data-stu-id="f28ba-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="f28ba-104">سيرشدك هذا الدليل عبر مثال شامل للتنبؤ بخسارة المعاملة في Customer Insights باستخدام البيانات المتوفرة أدناه.</span><span class="sxs-lookup"><span data-stu-id="f28ba-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="f28ba-105">جميع البيانات المستخدمة في هذا الدليل ليست بيانات عميل حقيقية وهي جزء من مجموعة بيانات Contoso الموجودة في بيئة *العرض التوضيحي* داخل اشتراك Customer Insights الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="f28ba-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="f28ba-106">السيناريو</span><span class="sxs-lookup"><span data-stu-id="f28ba-106">Scenario</span></span>

<span data-ttu-id="f28ba-107">Contoso هي شركة تنتج قهوة وماكينات لصنع القهوة عالية الجودة، تقوم ببيعها عبر موقع Contoso Coffee على الويب.</span><span class="sxs-lookup"><span data-stu-id="f28ba-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="f28ba-108">هدف هذه الشركة هو التعرّف على العملاء الذين يشترون عادةً منتجاتهم بشكل منتظم، والذين لن يعودوا من العملاء النشطاء خلال الستين يومًا القادمة.</span><span class="sxs-lookup"><span data-stu-id="f28ba-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="f28ba-109">من شأن اطّلاع الشركة على الذين **سيتوقفون عن التعامل معها على الأرجح** أن يساعدها على توفير جهودها التسويقية من خلال التركيز على استبقائهم.</span><span class="sxs-lookup"><span data-stu-id="f28ba-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f28ba-110">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="f28ba-110">Prerequisites</span></span>

- <span data-ttu-id="f28ba-111">على الأقل [أذونات المساهم](permissions.md) في Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f28ba-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="f28ba-112">نحن ننصح بتنفيذ الخطوات التالية [في بيئة جديدة](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="f28ba-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="f28ba-113">المهمة 1 - استيعاب البيانات</span><span class="sxs-lookup"><span data-stu-id="f28ba-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="f28ba-114">راجع المقالات [حول استيعاب البيانات](data-sources.md) و[استيراد مصادر البيانات باستخدام موصلات Power Query](connect-power-query.md) على وجه التحديد.</span><span class="sxs-lookup"><span data-stu-id="f28ba-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="f28ba-115">تفترض المعلومات التالية أنك ملمّ باستيعاب البيانات بشكل عام.</span><span class="sxs-lookup"><span data-stu-id="f28ba-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="f28ba-116">استيعاب بيانات العملاء من النظام الأساسي للتجارة الإلكترونية</span><span class="sxs-lookup"><span data-stu-id="f28ba-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="f28ba-117">أنشئ مصدر بيانات باسم **التجارة الإلكترونية**، وحدد خيار الاستيراد، ثم حدد الموصل **النص/CSV**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f28ba-118">أدخل عنوان URL لجهات اتصال التجارة الإلكترونية https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="f28ba-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="f28ba-119">أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f28ba-120">حدّث نوع البيانات للأعمدة المدرجة أدناه:</span><span class="sxs-lookup"><span data-stu-id="f28ba-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f28ba-121">**DateOfBirth**: التاريخ</span><span class="sxs-lookup"><span data-stu-id="f28ba-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="f28ba-122">**CreatedOn**: التاريخ/الوقت/المنطقة</span><span class="sxs-lookup"><span data-stu-id="f28ba-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="f28ba-123">![تحويل DoB إلى تاريخ](media/ecommerce-dob-date.PNG "تحويل تاريخ الولادة إلى تاريخ")</span><span class="sxs-lookup"><span data-stu-id="f28ba-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="f28ba-124">في حقل **الاسم‏‎** في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام** إلى **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="f28ba-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="f28ba-125">احفظ مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="f28ba-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="f28ba-126">استيعاب بيانات شراء عبر الإنترنت</span><span class="sxs-lookup"><span data-stu-id="f28ba-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="f28ba-127">أضف مجموعة بيانات أخرى إلى مصدر البيانات **التجارة الإلكترونية**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="f28ba-128">اختر الموصل **النص/CSV** مرة أخرى.</span><span class="sxs-lookup"><span data-stu-id="f28ba-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="f28ba-129">أدخل عنوان URL لبيانات **المشتريات عبر الإنترنت** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="f28ba-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="f28ba-130">أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f28ba-131">حدّث نوع البيانات للأعمدة المدرجة أدناه:</span><span class="sxs-lookup"><span data-stu-id="f28ba-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f28ba-132">**PurchasedOn**: التاريخ/الوقت</span><span class="sxs-lookup"><span data-stu-id="f28ba-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="f28ba-133">**TotalPrice**: العملة</span><span class="sxs-lookup"><span data-stu-id="f28ba-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="f28ba-134">في حقل **الاسم** في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام‏‎** إلى **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="f28ba-135">احفظ مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="f28ba-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="f28ba-136">استيعاب بيانات العملاء من مخطط الولاء</span><span class="sxs-lookup"><span data-stu-id="f28ba-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="f28ba-137">أنشئ مصدر بيانات باسم **LoyaltyScheme**، وحدد خيار الاستيراد، ثم حدد الموصل **النص/CSV**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="f28ba-138">أدخل عنوان URL لجهات اتصال التجارة الإلكترونية https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="f28ba-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="f28ba-139">أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="f28ba-140">حدّث نوع البيانات للأعمدة المدرجة أدناه:</span><span class="sxs-lookup"><span data-stu-id="f28ba-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="f28ba-141">**DateOfBirth**: التاريخ</span><span class="sxs-lookup"><span data-stu-id="f28ba-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="f28ba-142">**RewardsPoints**: عدد صحيح</span><span class="sxs-lookup"><span data-stu-id="f28ba-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="f28ba-143">**CreatedOn**: التاريخ/الوقت</span><span class="sxs-lookup"><span data-stu-id="f28ba-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="f28ba-144">في حقل **الاسم** في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام‏‎** إلى **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="f28ba-145">احفظ مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="f28ba-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="f28ba-146">المهمة 2 - توحيد البيانات</span><span class="sxs-lookup"><span data-stu-id="f28ba-146">Task 2 - Data unification</span></span>

<span data-ttu-id="f28ba-147">بعد استيعاب البيانات، نبدأ الآن عملية **التعيين، المطابقة، الدمج** لإنشاء ملف تعريف عميل موحد.</span><span class="sxs-lookup"><span data-stu-id="f28ba-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="f28ba-148">لمزيد من المعلومات، راجع [توحيد البيانات](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="f28ba-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="f28ba-149">المخطط</span><span class="sxs-lookup"><span data-stu-id="f28ba-149">Map</span></span>

1. <span data-ttu-id="f28ba-150">بعد استيعاب البيانات، قم بتعيين جهات الاتصال من بيانات التجارة الإلكترونية والولاء إلى أنواع البيانات الشائعة.</span><span class="sxs-lookup"><span data-stu-id="f28ba-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="f28ba-151">انتقل إلى **البيانات** > **توحيد** > **تعيين**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="f28ba-152">حدد الكيانات التي تمثل ملف تعريف العميل – **eCommerceContacts** و **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="توحيد مصادر بيانات التجارة الإلكترونية والولاء.":::

1. <span data-ttu-id="f28ba-154">حدد **ContactId** كمفتاح أساسي لـ **eCommerceContacts** و **LoyaltyID** كمفتاح أساسي لـ **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="توحيد LoyaltyId كمفتاح أساسي.":::

### <a name="match"></a><span data-ttu-id="f28ba-156">مطابقة</span><span class="sxs-lookup"><span data-stu-id="f28ba-156">Match</span></span>

1. <span data-ttu-id="f28ba-157">انتقل إلى علامة التبويب **مطابقة** وحدد **تعيين الأمر**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="f28ba-158">في القائمة المنسدلة **الرئيسية**، اختر **eCommerceContacts : eCommerce** باعتباره المصدر الرئيسي وقم بتضمين جميع السجلات.</span><span class="sxs-lookup"><span data-stu-id="f28ba-158">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="f28ba-159">في القائمة المنسدلة **الكيان 2**، اختر **loyCustomers : LoyaltyScheme** وقم بتضمين جميع السجلات.</span><span class="sxs-lookup"><span data-stu-id="f28ba-159">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="توحيد مطابقة التجارة الإلكترونية والولاء.":::

1. <span data-ttu-id="f28ba-161">حدد **إنشاء قاعدة جديدة**</span><span class="sxs-lookup"><span data-stu-id="f28ba-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="f28ba-162">أضف الشرط الأول باستخدام FullName.</span><span class="sxs-lookup"><span data-stu-id="f28ba-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="f28ba-163">بالنسبة إلى eCommerceContacts، حدد **FullName** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="f28ba-163">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="f28ba-164">بالنسبة إلى loyCustomers، حدد **FullName** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="f28ba-164">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="f28ba-165">حدد القائمة المنسدلة **تسوية**، واختر **النوع (الهاتف والاسم والعنوان و...)**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="f28ba-166">عيّن **مستوى الدقة**: **أساسي** و **قيمة**: **عالي**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="f28ba-167">أدخل الاسم **FullName, Email** للقاعدة الجديدة.</span><span class="sxs-lookup"><span data-stu-id="f28ba-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="f28ba-168">أضف شرطًا ثانيًا لعنوان البريد الإلكتروني من خلال تحديد **إضافة شرط**</span><span class="sxs-lookup"><span data-stu-id="f28ba-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="f28ba-169">بالنسبة للكيان eCommerceContacts، اختر **البريد الإلكتروني** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="f28ba-169">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="f28ba-170">بالنسبة للكيان loyCustomers، اختر **البريد الإلكتروني** في القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="f28ba-170">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="f28ba-171">اترك الخيار "تسوية" فارغًا.</span><span class="sxs-lookup"><span data-stu-id="f28ba-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="f28ba-172">عيّن **مستوى الدقة**: **أساسي** و **قيمة**: **عالي**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="توحيد قاعدة مطابقة للاسم والبريد الإلكتروني.":::

7. <span data-ttu-id="f28ba-174">حدد **حفظ** و **تشغيل**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="f28ba-175">‏‏دمج</span><span class="sxs-lookup"><span data-stu-id="f28ba-175">Merge</span></span>

1. <span data-ttu-id="f28ba-176">انقر فوق علامة التبويب **دمج**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="f28ba-177">على **ContactId** للكيان **loyCustomers** ، قم بتغيير الاسم المعروض إلى **ContactIdLOYALTY** لتمييزه عن المعرفات الأخرى التي تم استيعابها.</span><span class="sxs-lookup"><span data-stu-id="f28ba-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="إعادة تسمية contactid من معرف الولاء.":::

1. <span data-ttu-id="f28ba-179">حدد **حفظ** و **تشغيل** لبدء عملية الدمج.</span><span class="sxs-lookup"><span data-stu-id="f28ba-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="f28ba-180">المهمة 3 - تكوين التنبؤ بخسارة المعاملة‬</span><span class="sxs-lookup"><span data-stu-id="f28ba-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="f28ba-181">من خلال وضع ملفات تعريف العملاء الموحدة، يمكننا الآن تشغيل التنبؤ بخسارة الاشتراك.</span><span class="sxs-lookup"><span data-stu-id="f28ba-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="f28ba-182">للحصول على خطوات تفصيلية، راجع المقالة [التنبؤ بخسارة الاشتراك (معاينة)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="f28ba-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="f28ba-183">انتقل إلى **الذكاء** > **اكتشاف** وحدد لاستخدام **نموذج خسارة العملاء**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="f28ba-184">حدد الخيار **تعاملي‬‬** وحدد **الشروع في العمل** .</span><span class="sxs-lookup"><span data-stu-id="f28ba-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="f28ba-185">أدخل الاسم **OOB التنبؤ بخسارة معاملة التجارة الإلكترونية OOB‬‬** للنموذج والاسم **OOBeCommerceChurnPrediction** لكيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="f28ba-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="f28ba-186">قم بتعريف شرطين لنموذج الخسارة:</span><span class="sxs-lookup"><span data-stu-id="f28ba-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="f28ba-187">**إطار التنبؤ**: **60 يومًا على الأقل**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="f28ba-188">يحدد هذا الاعداد إلى أي مدى في المستقبل نرغب في التنبؤ بخسارة العملاء؟</span><span class="sxs-lookup"><span data-stu-id="f28ba-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="f28ba-189">**تعريف الخسارة**: **60 يومًا على الأقل**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="f28ba-190">المدة من دون إجراء أي عملية شراء والتي يعتبر بعدها أن الشركة خسرت العميل.</span><span class="sxs-lookup"><span data-stu-id="f28ba-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="حدد نموذج إطار التنبؤ وتعريف الخسارة.":::

1. <span data-ttu-id="f28ba-192">حدد **محفوظات الشراء (مطلوبة)** وحدد **إضافة بيانات** لمحفوظات الشراء.</span><span class="sxs-lookup"><span data-stu-id="f28ba-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="f28ba-193">أضف الكيان **eCommercePurchases : eCommerce** وعيّن الحقل من التجارة الإلكترونية إلى الحقول المناظرة التي يطلبها النموذج.</span><span class="sxs-lookup"><span data-stu-id="f28ba-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="f28ba-194">انضم إلى الكيان **eCommercePurchases : eCommerce** مع **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="الانضمام إلى كيانات التجارة الإلكترونية.":::

1. <span data-ttu-id="f28ba-196">حدد **التالي** لتعيين جدول النماذج.</span><span class="sxs-lookup"><span data-stu-id="f28ba-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="f28ba-197">يحتاج النموذج إلى التدريب بشكل منتظم للتعرف على الأنماط الجديدة عند وجود بيانات جديدة تم استيعابها.</span><span class="sxs-lookup"><span data-stu-id="f28ba-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="f28ba-198">لهذا المثال، حدد **شهري**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="f28ba-199">بعد مراجعة كافة التفاصيل ، حدد **حفظ وتشغيل**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="f28ba-200">المهمة 4 - مراجعة نتائج وتفسيرات النماذج</span><span class="sxs-lookup"><span data-stu-id="f28ba-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="f28ba-201">دع النموذج يكمل تدريب وتسجيل نقاط البيانات.</span><span class="sxs-lookup"><span data-stu-id="f28ba-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="f28ba-202">يمكنك الآن مراجعة تفسيرات نموذج خسارة بالاشتراك.</span><span class="sxs-lookup"><span data-stu-id="f28ba-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="f28ba-203">لمزيد من المعلومات، راجع [مراجعة حاله ونتائج التنبؤ](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="f28ba-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="f28ba-204">المهمة 5 - إنشاء شريحة من العملاء مخاطر خسارتهم عالية</span><span class="sxs-lookup"><span data-stu-id="f28ba-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="f28ba-205">يؤدي تشغيل نموذج الإنتاج إلى إنشاء كيان جديد يمكنك رؤيته في **البيانات** > **الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="f28ba-206">يمكنك إنشاء شريحة جديدة استنادًا إلى الكيان الذي تم إنشاؤه بواسطة النموذج.</span><span class="sxs-lookup"><span data-stu-id="f28ba-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="f28ba-207">انتقل إلى **الشرائح**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-207">Go to **Segments**.</span></span> <span data-ttu-id="f28ba-208">حدد **جديد** واختر **إنشاء من** > **الذكاء**.</span><span class="sxs-lookup"><span data-stu-id="f28ba-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="إنشاء شريحة بواسطة إخراج النموذج.":::

1. <span data-ttu-id="f28ba-210">حدد نقطة النهاية **OOBSubscriptionChurnPrediction** وحدد الشريحة:</span><span class="sxs-lookup"><span data-stu-id="f28ba-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="f28ba-211">الحقل: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="f28ba-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="f28ba-212">عامل التشغيل: أكبر من</span><span class="sxs-lookup"><span data-stu-id="f28ba-212">Operator: greater than</span></span>
   - <span data-ttu-id="f28ba-213">القيمة: 0.6</span><span class="sxs-lookup"><span data-stu-id="f28ba-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="إعداد شريحة خسارة الاشتراك.":::

<span data-ttu-id="f28ba-215">لديك الآن شريحة يتم تحديثها بشكل ديناميكي مما يحدد العملاء الذين تبدو مخاطر خسارتهم عالية‬ لعمل الاشتراك هذا.</span><span class="sxs-lookup"><span data-stu-id="f28ba-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="f28ba-216">لمزيد من المعلومات، راجع [إنشاء شرائح وإدارتها](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f28ba-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]