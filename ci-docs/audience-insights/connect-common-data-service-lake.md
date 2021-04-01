---
title: الاتصال بالكيانات في مستودع البيانات المُدار في Common Data Service
description: استيراد البيانات من مخزن البيانات المُدار بواسطة Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596943"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="6b14c-103">الاتصال بالبيانات في مستودع بيانات مُدار في Common Data Service</span><span class="sxs-lookup"><span data-stu-id="6b14c-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6b14c-104">توفر هذه المقالة معلومات حول كيفيه قيام عملاء Dynamics 365 الموجودين بالاتصال بشكل سريع بالكيانات التحليلية الخاصة بهم في المخزن المُدار بواسطة Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6b14c-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="6b14c-105">يجب أن تكون مسؤولا في مؤسسة Common Data Service للمتابعة والاطلاع على قائمة الكيانات المتوفرة في المخزن المُدار.</span><span class="sxs-lookup"><span data-stu-id="6b14c-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="6b14c-106">اعتبارات هامة</span><span class="sxs-lookup"><span data-stu-id="6b14c-106">Important considerations</span></span>

<span data-ttu-id="6b14c-107">قد يتم تخزين البيانات المخزنة في خدمات عبر الإنترنت مثل Azure Data Lake Storage في موقع يختلف عن الموقع حيث تتم معالجة البيانات أو تخزينها في Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6b14c-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="6b14c-108"> من خلال استيراد البيانات المخزنة في الخدمات عبر الإنترنت، توافق أنت على نقل هذه البيانات وتخزينها بواسطة Dynamics 365 Customer Insights. [اعرف المزيد في مركز توثيق Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="6b14c-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="6b14c-109">الاتصال بمستودع بيانات مُدار في Common Data Service</span><span class="sxs-lookup"><span data-stu-id="6b14c-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="6b14c-110">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="6b14c-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="6b14c-111">حدد **إضافة مصدر بيانات**.</span><span class="sxs-lookup"><span data-stu-id="6b14c-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="6b14c-112">حدد **اتصال بـ Common Data Service** ثم حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="6b14c-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="6b14c-113">أدخل **اسمًا** لمصدر البيانات، وحدد **التالي‏‎**.</span><span class="sxs-lookup"><span data-stu-id="6b14c-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="6b14c-114">إرشادات الاسم:</span><span class="sxs-lookup"><span data-stu-id="6b14c-114">Name guidelines:</span></span> 
   - <span data-ttu-id="6b14c-115">يجب أن يبدأ الاسم بحرف</span><span class="sxs-lookup"><span data-stu-id="6b14c-115">Start with a letter.</span></span>
   - <span data-ttu-id="6b14c-116">استخدم الأحرف و الأرقام فقط.</span><span class="sxs-lookup"><span data-stu-id="6b14c-116">Use letters and numbers only.</span></span> <span data-ttu-id="6b14c-117">غير مسموح باستخدام الأحرف الخاصة والمسافات.</span><span class="sxs-lookup"><span data-stu-id="6b14c-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="6b14c-118">استخدم ما بين 3 و64 حرفًا.</span><span class="sxs-lookup"><span data-stu-id="6b14c-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="6b14c-119">أدخل **عنوان الخادم** لمؤسستك في Common Data Service، ثم حدد **تسجيل الدخول**.</span><span class="sxs-lookup"><span data-stu-id="6b14c-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6b14c-120">![مربع حوار لإدخال عنوان الخادم في Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="6b14c-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="6b14c-121">حدد الكيانات التي ترغب في استيعابها من القائمة المتوفرة.</span><span class="sxs-lookup"><span data-stu-id="6b14c-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="6b14c-122">إذا كانت بعض الكيانات محددة، فمن المحتمل أن تكون قيد الاستخدام بواسطة تطبيقات Dynamics 365 أخرى (مثل Dynamics 365 Sales Insights or Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="6b14c-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="6b14c-123">لا يمكنك تغيير التحديد.</span><span class="sxs-lookup"><span data-stu-id="6b14c-123">You can't change the selection.</span></span> <span data-ttu-id="6b14c-124">ستصبح هذه الكيانات متاحة بمجرد إنشاء مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="6b14c-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6b14c-125">![مربع حوار يعرض قائمة بالكيانات الموجودة في مؤسسة Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="6b14c-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="6b14c-126">احفظ التحديد لبدء مزامنة الكيانات المحددة إلى المستودع المُدار في Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6b14c-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="6b14c-127">ستعثر على الاتصال المضاف حديثًا في صفحة **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="6b14c-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="6b14c-128">سيكون موضوعًا في قائمة انتظار كي يتم تحديثه، ويظهر عدد الكيانات كصفر حتى مزامنة كافة الكيانات.</span><span class="sxs-lookup"><span data-stu-id="6b14c-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="6b14c-129">بإمكان مصدر بيانات واحد فقط من البيئة استخدام مستودع البيانات المُدار نفسه في Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6b14c-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="6b14c-130">تحرير مصدر البيانات لمستودع بيانات مُدار في Common Data Service</span><span class="sxs-lookup"><span data-stu-id="6b14c-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="6b14c-131">يمكنك تحرير تحديد الكيان فقط بعد إنشاء مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="6b14c-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="6b14c-132">على سبيل المثال، إذا تمت إضافة كيانات اضافيه إلى Common Data Service وكنت تريد استيرادها أيضا.</span><span class="sxs-lookup"><span data-stu-id="6b14c-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="6b14c-133">للاتصال بخدمة Common Data Service أخرى، يمكنك [إنشاء مصدر بيانات جديد](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="6b14c-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="6b14c-134">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="6b14c-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="6b14c-135">إلى جانب مصدر البيانات الذي تريد تحديثه، حدد علامة القطع.</span><span class="sxs-lookup"><span data-stu-id="6b14c-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="6b14c-136">حدد الخيار **تحرير** من القائمة.</span><span class="sxs-lookup"><span data-stu-id="6b14c-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="6b14c-137">حدد كيانات إضافية من قائمة الكيانات المتاحة وحدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="6b14c-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]