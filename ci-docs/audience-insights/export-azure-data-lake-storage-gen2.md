---
title: تصدير بيانات Customer Insights إلى Azure Data Lake Storage Gen2
description: اعرف كيفية تكوين الاتصال بـ Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477163"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="b0a0c-103">موصل Azure Data Lake Storage Gen2 (إصدار أولي)</span><span class="sxs-lookup"><span data-stu-id="b0a0c-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="b0a0c-104">خزّن بيانات Customer Insights في Azure Data Lake Storage Gen2 أو استخدمها لنقل بياناتك إلى تطبيقات أخرى.</span><span class="sxs-lookup"><span data-stu-id="b0a0c-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="b0a0c-105">تكوين موصل Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="b0a0c-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="b0a0c-106">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.</span><span class="sxs-lookup"><span data-stu-id="b0a0c-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b0a0c-107">أسفل **Azure Data Lake Storage Gen2**، حدد **إعداد‏‎**.</span><span class="sxs-lookup"><span data-stu-id="b0a0c-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="b0a0c-108">في حقل **الاسم المعروض**، أدخل اسمًا للوجهة سهل التمييز.</span><span class="sxs-lookup"><span data-stu-id="b0a0c-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b0a0c-109">أدخل **اسم الحساب**، و **مفتاح الحساب**، و **الحاوية** لـ Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="b0a0c-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="b0a0c-110">لمعرفة كيفية إنشاء حساب تخزين لاستخدامه مع Azure Data Lake Storage Gen2، راجع [إنشاء حساب تخزين](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="b0a0c-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="b0a0c-111">لمعرفة المزيد حول كيفية العثور على اسم حساب تخزين Azure Data Lake Gen2 ومفتاح الحساب، راجع [إدارة إعدادات حساب التخزين في مدخل Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="b0a0c-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="b0a0c-112">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="b0a0c-112">Select **Next**.</span></span>

1. <span data-ttu-id="b0a0c-113">حدد المربع إلى جانب كل كيان تريد تصديره إلى هذه الوجهة.</span><span class="sxs-lookup"><span data-stu-id="b0a0c-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="b0a0c-114">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="b0a0c-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b0a0c-115">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="b0a0c-115">Export the data</span></span>

<span data-ttu-id="b0a0c-116">يمكنك [تصدير البيانات عند الطلب](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b0a0c-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="b0a0c-117">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b0a0c-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
