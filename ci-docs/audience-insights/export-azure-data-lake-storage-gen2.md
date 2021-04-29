---
title: تصدير بيانات Customer Insights إلى Azure Data Lake Storage Gen2
description: اعرف كيفية تكوين الاتصال بـ Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760035"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="e239d-103">إعداد الاتصال بـ Azure Data Lake Storage ‏Gen2 (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="e239d-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="e239d-104">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="e239d-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e239d-105">حدد **إضافة اتصال** واختر **Azure Data Lake Gen 2** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="e239d-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="e239d-106">اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**.</span><span class="sxs-lookup"><span data-stu-id="e239d-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e239d-107">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="e239d-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e239d-108">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="e239d-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e239d-109">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="e239d-109">Choose who can use this connection.</span></span> <span data-ttu-id="e239d-110">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="e239d-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e239d-111">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e239d-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e239d-112">أدخل **اسم الحساب**، و **مفتاح الحساب**، و **الحاوية** لـ Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="e239d-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="e239d-113">لمعرفة كيفية إنشاء حساب تخزين لاستخدامه مع Azure Data Lake Storage Gen2، راجع [إنشاء حساب تخزين](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="e239d-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="e239d-114">لمعرفة المزيد حول اسم حساب تخزين Azure Data Lake Gen2 ومفتاح الحساب، راجع [إدارة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="e239d-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="e239d-115">حدد **حفظ** لإكمال الاتصال.</span><span class="sxs-lookup"><span data-stu-id="e239d-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="e239d-116">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="e239d-116">Configure an export</span></span>

<span data-ttu-id="e239d-117">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="e239d-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e239d-118">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e239d-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e239d-119">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="e239d-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e239d-120">لإنشاء عملية تصدير جديدة، حدد **إضافة تصدير**.</span><span class="sxs-lookup"><span data-stu-id="e239d-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="e239d-121">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="e239d-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="e239d-122">إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="e239d-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e239d-123">حدد المربع إلى جانب كل كيان تريد تصديره إلى هذه الوجهة.</span><span class="sxs-lookup"><span data-stu-id="e239d-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="e239d-124">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="e239d-124">Select **Save**.</span></span>

<span data-ttu-id="e239d-125">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="e239d-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e239d-126">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e239d-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e239d-127">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e239d-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="e239d-128">يتم تخزين البيانات المصدرة في حاوية تخزين Azure Data Lake Gen 2 التي قمت بتكوينها.</span><span class="sxs-lookup"><span data-stu-id="e239d-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
