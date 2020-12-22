---
title: توصيل بيانات نموذج البيانات العامة بحساب Azure Data Lake
description: اعمل مع بيانات نموذج البيانات العامة باستخدام Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643442"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="e29f3-103">الاتصال بمجلد نموذج البيانات العامة باستخدام حساب Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="e29f3-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="e29f3-104">توفر هذه المقالة معلومات حول كيفية استيعاب البيانات من مجلد نموذج البيانات العامة باستخدام حساب Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="e29f3-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="e29f3-105">اعتبارات هامة</span><span class="sxs-lookup"><span data-stu-id="e29f3-105">Important considerations</span></span>

- <span data-ttu-id="e29f3-106">يجب أن تتبع البيانات الموجودة في Azure Data Lake معيار نموذج البيانات العامة.</span><span class="sxs-lookup"><span data-stu-id="e29f3-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="e29f3-107">التنسيقات الأخرى غير مدعومة في الوقت الحالي.</span><span class="sxs-lookup"><span data-stu-id="e29f3-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="e29f3-108">يدعم استيعاب البيانات حسابات التخزين Azure Data Lake *Gen2* بشكل حصري.</span><span class="sxs-lookup"><span data-stu-id="e29f3-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="e29f3-109">لا يمكنك استخدام حسابات تخزين Azure Data Lake Gen1 لاستيعاب البيانات.</span><span class="sxs-lookup"><span data-stu-id="e29f3-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="e29f3-110">للمصادقة مع كيان خدمة Azure، تأكد من تكوينه في المستأجر.</span><span class="sxs-lookup"><span data-stu-id="e29f3-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="e29f3-111">لمزيد من المعلومات، راجع [توصيل رؤى الجمهور بحساب Azure Data Lake Storage Gen2 بواسطة كيان خدمة Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="e29f3-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="e29f3-112">يجب أن يكون Azure Data Lake الذي تريد الاتصال به واستيعاب البيانات منه في منطقة Azure نفسها حيث بيئة Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e29f3-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="e29f3-113">الاتصالات بمجلد نموذج البيانات العامة من مستودع البيانات في منطقة Azure مختلفة غير مدعومة.</span><span class="sxs-lookup"><span data-stu-id="e29f3-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="e29f3-114">لمعرفة منطقة Azure الخاصة بالبيئة، انتقل إلى **المسؤول** > **النظام** > **حول** في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="e29f3-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="e29f3-115">قد يتم تخزين البيانات المخزنة في الخدمات عبر الإنترنت في موقع مختلف عن موقع معالجة أو تخزين البيانات في Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e29f3-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="e29f3-116"> من خلال استيراد البيانات المخزنة في الخدمات عبر الإنترنت، توافق أنت على نقل هذه البيانات وتخزينها بواسطة Dynamics 365 Customer Insights. [اعرف المزيد في مركز توثيق Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="e29f3-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="e29f3-117">الاتصال بمجلد نموذج البيانات العامة</span><span class="sxs-lookup"><span data-stu-id="e29f3-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="e29f3-118">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="e29f3-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="e29f3-119">حدد **إضافة مصدر بيانات**.</span><span class="sxs-lookup"><span data-stu-id="e29f3-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="e29f3-120">حدد **الاتصال بمجلد نموذج البيانات العامة**، وأدخل **اسم** مصدر البيانات، ثم حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="e29f3-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="e29f3-121">يمكنك الاختيار بين استخدام خيار قائم على الموارد وخيار قائم على الاشتراكات للمصادقة.</span><span class="sxs-lookup"><span data-stu-id="e29f3-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="e29f3-122">لمزيد من المعلومات، راجع [توصيل رؤى الجمهور بحساب Azure Data Lake Storage Gen2 بواسطة كيان خدمة Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="e29f3-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="e29f3-123">أدخل معلومات **الحاوية** وحدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="e29f3-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e29f3-124">![مربع حوار لإدخال تفاصيل الاتصال لـ Azure Data Lake](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="e29f3-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="e29f3-125">في مربع الحوار **تحديد مجلد نموذج البيانات العامة**، حدد الملف model.json لاستيراد البيانات منه، ثم حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="e29f3-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="e29f3-126">لن يظهر في القائمة أي ملف model.json مرتبط بمصدر بيانات آخر في البيئة.</span><span class="sxs-lookup"><span data-stu-id="e29f3-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="e29f3-127">ستحصل على قائمة بالكيانات المتوفرة في ملف model.json المحدد.</span><span class="sxs-lookup"><span data-stu-id="e29f3-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="e29f3-128">يمكنك المراجعة والتحديد من قائمة الكيانات المتاحة وحدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="e29f3-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="e29f3-129">سيتم استيعاب جميع الكيانات المحددة من مصدر البيانات الجديد.</span><span class="sxs-lookup"><span data-stu-id="e29f3-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e29f3-130">![مربع حوار يعرض قائمة بالكيانات من ملف model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="e29f3-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="e29f3-131">أشر إلى كيانات البيانات الذي تريد تمكين ‏‫تعريف البيانات‬ لها وحدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="e29f3-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="e29f3-132">تتيح ملفات تعريف البيانات التحليلات والإمكانيات الأخرى.</span><span class="sxs-lookup"><span data-stu-id="e29f3-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="e29f3-133">يمكنك تحديد الكيان بالكامل الذي يحدد كافة السمات من الكيان، أو تحديد سمات معينة من اختيارك.</span><span class="sxs-lookup"><span data-stu-id="e29f3-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="e29f3-134">بشكل افتراضي، لا يتم تمكين أي كيان لتعريف البيانات.</span><span class="sxs-lookup"><span data-stu-id="e29f3-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e29f3-135">![مربع الحوار يعرض تعريف البيانات](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="e29f3-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="e29f3-136">بعد حفظ التحديدات، تفتح صفحة **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="e29f3-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="e29f3-137">من المفترض أن ترى الآن مجلد نموذج البيانات العامة كمصدر بيانات.</span><span class="sxs-lookup"><span data-stu-id="e29f3-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="e29f3-138">بإمكان ملف model.json أن يرتبط فقط بمصدر بيانات واحد في البيئة نفسها.</span><span class="sxs-lookup"><span data-stu-id="e29f3-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="e29f3-139">ومع ذلك، يمكن استخدام ملف model.json نفسه لمصادر البيانات في بيئات متعددة.</span><span class="sxs-lookup"><span data-stu-id="e29f3-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="e29f3-140">تحرير مصدر بيانات مجلد نموذج بيانات عامة</span><span class="sxs-lookup"><span data-stu-id="e29f3-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="e29f3-141">يمكنك تحديث مفتاح الوصول لحساب التخزين الذي يحتوي على مجلد نموذج البيانات العامة.</span><span class="sxs-lookup"><span data-stu-id="e29f3-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="e29f3-142">يمكنك أيضًا تغيير ملف model.json.</span><span class="sxs-lookup"><span data-stu-id="e29f3-142">You may also change the model.json file.</span></span> <span data-ttu-id="e29f3-143">للاتصال بحاوية أخرى من حساب التخزين، أو تغيير اسم الحساب، عليك [إنشاء اتصال مصدر بيانات جديد](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="e29f3-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="e29f3-144">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="e29f3-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="e29f3-145">إلى جانب مصدر البيانات الذي تريد تحديثه، حدد علامة القطع.</span><span class="sxs-lookup"><span data-stu-id="e29f3-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="e29f3-146">حدد الخيار **تحرير** من القائمة.</span><span class="sxs-lookup"><span data-stu-id="e29f3-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="e29f3-147">بشكل اختياري، قم بتحديث **مفتاح الوصول** وحدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="e29f3-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![مربع حوار لتحرير مفتاح وصول وتحديثه لمصدر بيانات موجود](media/edit-access-key.png)

5. <span data-ttu-id="e29f3-149">بشكل اختياري، يمكنك التحديث من اتصال مفتاح حساب باتصال قائم على الموارد أو اتصال قائم على الاشتراكات.</span><span class="sxs-lookup"><span data-stu-id="e29f3-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="e29f3-150">لمزيد من المعلومات، راجع [توصيل رؤى الجمهور بحساب Azure Data Lake Storage Gen2 بواسطة كيان خدمة Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="e29f3-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="e29f3-151">لا يمكنك **تغيير** معلومات الحاوية عند تحديث الاتصال.</span><span class="sxs-lookup"><span data-stu-id="e29f3-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e29f3-152">![مربع حوار لإدخال تفاصيل الاتصال لـ Azure Data Lake](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="e29f3-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="e29f3-153">بشكل اختياري، اختر ملف model.json آخر مع مجموعة مختلفة من الكيانات من الحاوية.</span><span class="sxs-lookup"><span data-stu-id="e29f3-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="e29f3-154">بشكل اختياري، يمكنك تحديد الكيانات الإضافية لاستيعابها.</span><span class="sxs-lookup"><span data-stu-id="e29f3-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="e29f3-155">يمكنك أيضا إزالة أية كيانات محددة بالفعل في حالة عدم وجود تبعيات.</span><span class="sxs-lookup"><span data-stu-id="e29f3-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="e29f3-156">في حال وجود تبعيات على ملف model.json الموجود ومجموعة الكيانات، فستظهر رسالة خطا وسيتعذر عليك تحديد ملف model.json آخر.</span><span class="sxs-lookup"><span data-stu-id="e29f3-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="e29f3-157">قم بإزالة هذه التبعيات قبل تغيير ملف model.json أو قم بإنشاء مصدر بيانات جديد باستخدام الملف ملف model.json الذي تريد استخدامه لتجنب إزالة التبعيات.</span><span class="sxs-lookup"><span data-stu-id="e29f3-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="e29f3-158">بشكل اختياري، يمكنك تحديد سمات أو كيانات إضافية لتمكين ملفات تعريف البيانات أو تعطيل تلك المحددة بالفعل.</span><span class="sxs-lookup"><span data-stu-id="e29f3-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
