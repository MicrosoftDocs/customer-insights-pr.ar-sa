---
title: تصدير بيانات Customer Insights إلى مساحة تخزين Azure Blob Storage
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى مساحة تخزين Blob storage.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976118"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="2cb9a-103">تصدير قائمة الشرائح والبيانات الأخرى إلى مساحة تخزين Azure Blob Storage (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="2cb9a-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="2cb9a-104">قم بتخزين بيانات Customer Insights في مساحة تخزين Blob Storage أو استخدمها لنقل بياناتك إلى تطبيقات أخرى.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="2cb9a-105">إعداد الاتصال بمساحة تخزين Blob Storage</span><span class="sxs-lookup"><span data-stu-id="2cb9a-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="2cb9a-106">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2cb9a-107">حدد **إضافة اتصال** واختر **مساحة تخزين Azure Blob Storage** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="2cb9a-108">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2cb9a-109">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2cb9a-110">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2cb9a-111">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-111">Choose who can use this connection.</span></span> <span data-ttu-id="2cb9a-112">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2cb9a-113">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2cb9a-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2cb9a-114">أدخل **اسم الحساب**، و **مفتاح الحساب**، و **الحساب** لحسابك في مساحة تخزين Blob storage.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="2cb9a-115">لمعرفة المزيد حول كيفية العثور على اسم حساب مساحة تخزين اسم حساب تخزين Blob storage ومفتاح الحساب، راجع [إدارة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="2cb9a-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="2cb9a-116">لمعرفة كيفية إنشاء حاوية، راجع [إنشاء حاوية](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="2cb9a-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="2cb9a-117">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="2cb9a-118">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="2cb9a-118">Configure an export</span></span>

<span data-ttu-id="2cb9a-119">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2cb9a-120">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2cb9a-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2cb9a-121">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2cb9a-122">لإنشاء اتصال جديد، حدد **إضافة وجهة**.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2cb9a-123">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم مساحة تخزين Azure Blob Storage,</span><span class="sxs-lookup"><span data-stu-id="2cb9a-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="2cb9a-124">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2cb9a-125">حدد المربع إلى جانب كل كيان تريد تصديره إلى هذه الوجهة.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="2cb9a-126">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-126">Select **Save**.</span></span>

<span data-ttu-id="2cb9a-127">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2cb9a-128">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2cb9a-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="2cb9a-129">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2cb9a-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="2cb9a-130">يتم تخزين البيانات المصدرة في حاوية مساحة تخزين Blob storage التي قمت بتكوينها.</span><span class="sxs-lookup"><span data-stu-id="2cb9a-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="2cb9a-131">يتم إنشاء مسارات المجلدات التالية بشكل تلقائي في حاويتك:</span><span class="sxs-lookup"><span data-stu-id="2cb9a-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="2cb9a-132">بالنسبة للكيانات المصدر والكيانات التي تم إنشاؤها بواسطة النظام: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="2cb9a-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="2cb9a-133">مثال: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="2cb9a-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="2cb9a-134">سيكون model.json للكيانات المصدرة في مستوى %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="2cb9a-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="2cb9a-135">مثال: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="2cb9a-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
