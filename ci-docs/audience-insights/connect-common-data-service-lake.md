---
title: الاتصال بالكيانات في مستودع البيانات المُدار في Common Data Service
description: استيراد البيانات من مخزن البيانات المُدار بواسطة Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 029857e2bbb5f6357a5c01138ceaad78887b7518
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643382"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="58d68-103">الاتصال بالبيانات في مستودع بيانات مُدار في Common Data Service</span><span class="sxs-lookup"><span data-stu-id="58d68-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="58d68-104">توفر هذه المقالة معلومات حول كيفيه قيام عملاء Dynamics 365 الموجودين بالاتصال بشكل سريع بالكيانات التحليلية الخاصة بهم في المخزن المُدار بواسطة Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="58d68-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="58d68-105">يجب أن تكون مسؤولا في مؤسسة Common Data Service للمتابعة والاطلاع على قائمة الكيانات المتوفرة في المخزن المُدار.</span><span class="sxs-lookup"><span data-stu-id="58d68-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="58d68-106">اعتبارات هامة</span><span class="sxs-lookup"><span data-stu-id="58d68-106">Important considerations</span></span>

<span data-ttu-id="58d68-107">قد يتم تخزين البيانات المخزنة في خدمات عبر الإنترنت مثل Azure Data Lake Storage في موقع يختلف عن الموقع حيث تتم معالجة البيانات أو تخزينها في Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="58d68-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="58d68-108"> من خلال استيراد البيانات المخزنة في الخدمات عبر الإنترنت، توافق أنت على نقل هذه البيانات وتخزينها بواسطة Dynamics 365 Customer Insights. [اعرف المزيد في مركز توثيق Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="58d68-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="58d68-109">الاتصال بمستودع بيانات مُدار في Common Data Service</span><span class="sxs-lookup"><span data-stu-id="58d68-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="58d68-110">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="58d68-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="58d68-111">حدد **إضافة مصدر بيانات**.</span><span class="sxs-lookup"><span data-stu-id="58d68-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="58d68-112">حدد **اتصال بـ Common Data Service** ثم حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="58d68-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="58d68-113">أدخل **اسمًا** لمصدر البيانات، وحدد **التالي‏‎**.</span><span class="sxs-lookup"><span data-stu-id="58d68-113">Enter a **Name** for the data source and select **Next**.</span></span>

5. <span data-ttu-id="58d68-114">أدخل **عنوان الخادم** لمؤسستك في Common Data Service، ثم حدد **تسجيل الدخول**.</span><span class="sxs-lookup"><span data-stu-id="58d68-114">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="58d68-115">![مربع حوار لإدخال عنوان الخادم في Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="58d68-115">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="58d68-116">حدد الكيانات التي ترغب في استيعابها من القائمة المتوفرة.</span><span class="sxs-lookup"><span data-stu-id="58d68-116">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="58d68-117">إذا كانت بعض الكيانات محددة، فمن المحتمل أن تكون قيد الاستخدام بواسطة تطبيقات Dynamics 365 أخرى (مثل Dynamics 365 Sales Insights or Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="58d68-117">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="58d68-118">لا يمكنك تغيير التحديد.</span><span class="sxs-lookup"><span data-stu-id="58d68-118">You can't change the selection.</span></span> <span data-ttu-id="58d68-119">ستصبح هذه الكيانات متاحة بمجرد إنشاء مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="58d68-119">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="58d68-120">![مربع حوار يعرض قائمة بالكيانات الموجودة في مؤسسة Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="58d68-120">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="58d68-121">احفظ التحديد لبدء مزامنة الكيانات المحددة إلى المستودع المُدار في Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="58d68-121">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="58d68-122">ستعثر على الاتصال المضاف حديثًا في صفحة **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="58d68-122">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="58d68-123">سيكون موضوعًا في قائمة انتظار كي يتم تحديثه، ويظهر عدد الكيانات كصفر حتى مزامنة كافة الكيانات.</span><span class="sxs-lookup"><span data-stu-id="58d68-123">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="58d68-124">بإمكان مصدر بيانات واحد فقط من البيئة استخدام مستودع البيانات المُدار نفسه في Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="58d68-124">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="58d68-125">تحرير مصدر البيانات لمستودع بيانات مُدار في Common Data Service</span><span class="sxs-lookup"><span data-stu-id="58d68-125">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="58d68-126">يمكنك تحرير تحديد الكيان فقط بعد إنشاء مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="58d68-126">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="58d68-127">على سبيل المثال، إذا تمت إضافة كيانات اضافيه إلى Common Data Service وكنت تريد استيرادها أيضا.</span><span class="sxs-lookup"><span data-stu-id="58d68-127">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="58d68-128">للاتصال بخدمة Common Data Service أخرى، يمكنك [إنشاء مصدر بيانات جديد](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="58d68-128">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="58d68-129">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="58d68-129">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="58d68-130">إلى جانب مصدر البيانات الذي تريد تحديثه، حدد علامة القطع.</span><span class="sxs-lookup"><span data-stu-id="58d68-130">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="58d68-131">حدد الخيار **تحرير** من القائمة.</span><span class="sxs-lookup"><span data-stu-id="58d68-131">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="58d68-132">حدد كيانات إضافية من قائمة الكيانات المتاحة وحدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="58d68-132">Select additional entities from the available list of entities and select **Save**.</span></span>
