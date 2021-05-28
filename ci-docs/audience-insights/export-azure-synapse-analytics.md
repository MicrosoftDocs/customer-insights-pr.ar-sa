---
title: تصدير بيانات Customer Insights إلى Azure Synapse Analytics
description: تعرف على كيفية تهيئة الاتصال بـ Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977361"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="20a16-103">تصدير البيانات إلى Azure Synapse Analytics (معاينة)</span><span class="sxs-lookup"><span data-stu-id="20a16-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="20a16-104">Azure Synapse iهو خدمة تحليلات تعمل على تسريع وقت التحليل المتعمق في مستودعات البيانات وأنظمت البيانات الكبيرة.</span><span class="sxs-lookup"><span data-stu-id="20a16-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="20a16-105">يمكنك استيعاب بيانات Customer Insights الخاصة بك واستخدامها في [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="20a16-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="20a16-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="20a16-106">Prerequisites</span></span>

<span data-ttu-id="20a16-107">يجب تلبية المتطلبات الأساسية التالية لتهيئة الاتصال من Customer Insights إلى Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="20a16-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="20a16-108">تأكد من تعيين جميع **تعيينات الدور** كما هو موضح.</span><span class="sxs-lookup"><span data-stu-id="20a16-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="20a16-109">المتطلبات الأساسية في Customer Insights</span><span class="sxs-lookup"><span data-stu-id="20a16-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="20a16-110">لديك دور **المسؤول** في معلومات الجمهور.</span><span class="sxs-lookup"><span data-stu-id="20a16-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="20a16-111">اعرف المزيد حول [تعيين أذونات المستخدم في معلومات الجمهور](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="20a16-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="20a16-112">في Azure:</span><span class="sxs-lookup"><span data-stu-id="20a16-112">In Azure:</span></span> 

- <span data-ttu-id="20a16-113">اشتراك Azure نشط.</span><span class="sxs-lookup"><span data-stu-id="20a16-113">An active Azure subscription.</span></span>

- <span data-ttu-id="20a16-114">في حالة استخدام حساب Azure Data Lake Storage Gen2، فإن *مبدأ الخدمة لمعلومات الجمهور* يجتاج إلى إذن **مساهم بيانات مخزن البيانات الثنائية الكبيرة**.</span><span class="sxs-lookup"><span data-stu-id="20a16-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="20a16-115">اعرف على المزيد حول [الاتصال بحساب Azure Data Lake Storage Gen2 باستخدام مبدأ خدمة Azure لمعلومات الجمهور](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="20a16-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="20a16-116">إن Data Lake Storage Gen2 **يجب** أن يتضمن [مساحة أسماء هرمية](/azure/storage/blobs/data-lake-storage-namespace) قيد التمكين.</span><span class="sxs-lookup"><span data-stu-id="20a16-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="20a16-117">في مجموعة الموارد التي توجد بها مساحة عمل Azure Synapse، فإن *مبدأ الخدمة* و *المستخدم لمعلومات الجمهور* يحتاج  تعيين أذونات **قارئ** له على الأقل.</span><span class="sxs-lookup"><span data-stu-id="20a16-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="20a16-118">لمزيد من المعلومات، راجع [تعيين أدوار Azure باستخدام مدخل Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="20a16-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="20a16-119">يحتاج *المستخدم* إلى أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة** في حساب Azure Data Lake Storage Gen2 في المكان الذي توجد فيه البيانات وترتبط بمساحة عمل Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="20a16-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="20a16-120">تعلم المزيد حول [استخدام مدخل Azure لتعيين دور Azure للوصول إلى بيانات الكائن الثنائي كبير الحجم والصف](/azure/storage/common/storage-auth-aad-rbac-portal) و[أذونات مساهم بيانات مخزن البيانات الثنائية الكبيرة](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="20a16-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="20a16-121">تحتاج *[الهوية المدارة بمساحة عمل Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* إلى أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة** في حساب Azure Data Lake Storage Gen2 في المكان الذي توجد فيه البيانات وترتبط بمساحة عمل Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="20a16-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="20a16-122">تعلم المزيد حول [استخدام مدخل Azure لتعيين دور Azure للوصول إلى بيانات الكائن الثنائي كبير الحجم والصف](/azure/storage/common/storage-auth-aad-rbac-portal) و[أذونات مساهم بيانات مخزن البيانات الثنائية الكبيرة](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="20a16-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="20a16-123">في مساحة عمل Azure Synapse، يحتاج *مبدأ الخدمة لمعلومات الجمهور* إلى تعيين دور **مسؤول  Synapse**.</span><span class="sxs-lookup"><span data-stu-id="20a16-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="20a16-124">لمزيد من المعلومات، راجع [كيفية إعداد عنصر تحكم الوصول لمساحة عمل Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control) الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="20a16-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="20a16-125">إعداد الاتصال والتصدير إلى Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="20a16-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="20a16-126">تكوين اتصال</span><span class="sxs-lookup"><span data-stu-id="20a16-126">Configure a connection</span></span>

1. <span data-ttu-id="20a16-127">انتقل إلى **المسؤول** > **الاتصالات**.</span><span class="sxs-lookup"><span data-stu-id="20a16-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="20a16-128">حدد **إضافة اتصال** واختر **Azure Synapse Analytics** أو حدد **إعداد** في تجانب **Azure Synapse Analytics** لتكوين الاتصال.</span><span class="sxs-lookup"><span data-stu-id="20a16-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="20a16-129">اعط اتصالك اسمًا يمكن التعرف عليه في حقل الاسم المعروض.</span><span class="sxs-lookup"><span data-stu-id="20a16-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="20a16-130">يصف الاسم ونوع الاتصال هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="20a16-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="20a16-131">ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.</span><span class="sxs-lookup"><span data-stu-id="20a16-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="20a16-132">اختر الشخص الذي يمكنه استخدام هذا الاتصال.</span><span class="sxs-lookup"><span data-stu-id="20a16-132">Choose who can use this connection.</span></span> <span data-ttu-id="20a16-133">إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين.</span><span class="sxs-lookup"><span data-stu-id="20a16-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="20a16-134">لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="20a16-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="20a16-135">حدد الاشتراك الذي ترغب في استخدامه في بيانات Customer Insights أو ابحث عنه.</span><span class="sxs-lookup"><span data-stu-id="20a16-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="20a16-136">بمجرد تحديد اشتراك، يمكنك أيضا تحديد **مساحة العمل** و **حساب مساحة التخزين** و **الحاوية**.</span><span class="sxs-lookup"><span data-stu-id="20a16-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="20a16-137">حدد **حفظ** لحفظ الاتصال.</span><span class="sxs-lookup"><span data-stu-id="20a16-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="20a16-138">تكوين تصدير</span><span class="sxs-lookup"><span data-stu-id="20a16-138">Configure an export</span></span>

<span data-ttu-id="20a16-139">يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع.</span><span class="sxs-lookup"><span data-stu-id="20a16-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="20a16-140">لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="20a16-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="20a16-141">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="20a16-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="20a16-142">لإنشاء عملية تصدير جديدة، حدد **إضافة تصدير**.</span><span class="sxs-lookup"><span data-stu-id="20a16-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="20a16-143">في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="20a16-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="20a16-144">إذا لم تشاهد اسم القسم هذا، لن تكون هناك [اتصالات](connections.md) من هذا النوع متوفرة لك.</span><span class="sxs-lookup"><span data-stu-id="20a16-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="20a16-145">قم بتوفير **اسم العرض** يمكن التعرف عليه لعملية التصدير الخاصة بك و **اسم قاعدة البيانات**.</span><span class="sxs-lookup"><span data-stu-id="20a16-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="20a16-146">حدد الكيانات التي ترغب في تصديرها إلى Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="20a16-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="20a16-147">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="20a16-147">Select **Save**.</span></span>

<span data-ttu-id="20a16-148">لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.</span><span class="sxs-lookup"><span data-stu-id="20a16-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="20a16-149">يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="20a16-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="20a16-150">يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="20a16-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="20a16-151">تحديث عملية تصدير</span><span class="sxs-lookup"><span data-stu-id="20a16-151">Update an export</span></span>

1. <span data-ttu-id="20a16-152">انتقل إلى **البيانات** > **التصديرات**.</span><span class="sxs-lookup"><span data-stu-id="20a16-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="20a16-153">حدد **تحرير** في عملية التصدير التي تريد تحديثها.</span><span class="sxs-lookup"><span data-stu-id="20a16-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="20a16-154">**أضف** أو **أزل** الكيانات من الاختيار.</span><span class="sxs-lookup"><span data-stu-id="20a16-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="20a16-155">في حالة إزالة الكيانات من التحديد، لا يتم حذفها من قاعدة بيانات Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="20a16-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="20a16-156">ومع ذلك، لن تؤدي عمليات تحديث البيانات المستقبلية إلى تحديث الكيانات التي تمت إزالتها في قاعدة البيانات هذه.</span><span class="sxs-lookup"><span data-stu-id="20a16-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="20a16-157">يؤدي **تغيير اسم قاعدة البيانات** إلى إنشاء قاعدة بيانات Synapse Analytics جديدة.</span><span class="sxs-lookup"><span data-stu-id="20a16-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="20a16-158">لن تتلقى قاعدة البيانات بالاسم الذي تم تكوينه في السابق أي تحديثات في عمليات التحديث المستقبلة.</span><span class="sxs-lookup"><span data-stu-id="20a16-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
