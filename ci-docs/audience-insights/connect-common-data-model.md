---
title: توصيل بيانات نموذج البيانات العامة بحساب Azure Data Lake
description: اعمل مع بيانات نموذج البيانات العامة باستخدام Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 385406b706890d741fec2694c190c0fada7809d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596529"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="c33c5-103">الاتصال بمجلد نموذج البيانات العامة باستخدام حساب Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="c33c5-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="c33c5-104">توفر هذه المقالة معلومات حول كيفية استيعاب البيانات من مجلد نموذج البيانات العامة باستخدام حساب Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="c33c5-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="c33c5-105">اعتبارات هامة</span><span class="sxs-lookup"><span data-stu-id="c33c5-105">Important considerations</span></span>

- <span data-ttu-id="c33c5-106">يجب أن تتبع البيانات الموجودة في Azure Data Lake معيار نموذج البيانات العامة.</span><span class="sxs-lookup"><span data-stu-id="c33c5-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="c33c5-107">التنسيقات الأخرى غير مدعومة في الوقت الحالي.</span><span class="sxs-lookup"><span data-stu-id="c33c5-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="c33c5-108">يدعم استيعاب البيانات حسابات التخزين Azure Data Lake *Gen2* بشكل حصري.</span><span class="sxs-lookup"><span data-stu-id="c33c5-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="c33c5-109">لا يمكنك استخدام حسابات تخزين Azure Data Lake Gen1 لاستيعاب البيانات.</span><span class="sxs-lookup"><span data-stu-id="c33c5-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="c33c5-110">للمصادقة مع كيان خدمة Azure، تأكد من تكوينه في المستأجر.</span><span class="sxs-lookup"><span data-stu-id="c33c5-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="c33c5-111">لمزيد من المعلومات، راجع [توصيل رؤى الجمهور بحساب Azure Data Lake Storage Gen2 بواسطة كيان خدمة Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="c33c5-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="c33c5-112">يجب أن يكون Azure Data Lake الذي تريد الاتصال به واستيعاب البيانات منه في منطقة Azure نفسها حيث بيئة Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c33c5-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="c33c5-113">الاتصالات بمجلد نموذج البيانات العامة من مستودع البيانات في منطقة Azure مختلفة غير مدعومة.</span><span class="sxs-lookup"><span data-stu-id="c33c5-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="c33c5-114">لمعرفة منطقة Azure الخاصة بالبيئة، انتقل إلى **المسؤول** > **النظام** > **حول** في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="c33c5-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="c33c5-115">قد يتم تخزين البيانات المخزنة في الخدمات عبر الإنترنت في موقع مختلف عن موقع معالجة أو تخزين البيانات في Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c33c5-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="c33c5-116"> من خلال استيراد البيانات المخزنة في الخدمات عبر الإنترنت، توافق أنت على نقل هذه البيانات وتخزينها بواسطة Dynamics 365 Customer Insights. [اعرف المزيد في مركز توثيق Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="c33c5-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="c33c5-117">الاتصال بمجلد نموذج البيانات العامة</span><span class="sxs-lookup"><span data-stu-id="c33c5-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="c33c5-118">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="c33c5-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="c33c5-119">حدد **إضافة مصدر بيانات**.</span><span class="sxs-lookup"><span data-stu-id="c33c5-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="c33c5-120">حدد **الاتصال بمجلد نموذج البيانات العامة**، وأدخل **اسم** مصدر البيانات، ثم حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="c33c5-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span> <span data-ttu-id="c33c5-121">إرشادات الاسم:</span><span class="sxs-lookup"><span data-stu-id="c33c5-121">Name guidelines:</span></span> 
   - <span data-ttu-id="c33c5-122">يجب أن يبدأ الاسم بحرف</span><span class="sxs-lookup"><span data-stu-id="c33c5-122">Start with a letter.</span></span>
   - <span data-ttu-id="c33c5-123">استخدم الأحرف و الأرقام فقط.</span><span class="sxs-lookup"><span data-stu-id="c33c5-123">Use letters and numbers only.</span></span> <span data-ttu-id="c33c5-124">غير مسموح باستخدام الأحرف الخاصة والمسافات.</span><span class="sxs-lookup"><span data-stu-id="c33c5-124">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="c33c5-125">استخدم ما بين 3 و64 حرفًا.</span><span class="sxs-lookup"><span data-stu-id="c33c5-125">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="c33c5-126">يمكنك الاختيار بين استخدام خيار قائم على الموارد وخيار قائم على الاشتراكات للمصادقة.</span><span class="sxs-lookup"><span data-stu-id="c33c5-126">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="c33c5-127">لمزيد من المعلومات، راجع [توصيل رؤى الجمهور بحساب Azure Data Lake Storage Gen2 بواسطة كيان خدمة Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="c33c5-127">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="c33c5-128">أدخل معلومات **الحاوية** وحدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="c33c5-128">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c33c5-129">![مربع حوار لإدخال تفاصيل اتصال جديدة لـ Azure Data Lake‎](media/enter-new-storage-details.png)
   > </span><span class="sxs-lookup"><span data-stu-id="c33c5-129">![Dialog box to enter new connection details for Azure Data Lake](media/enter-new-storage-details.png)
   > </span></span>[!NOTE]
<span data-ttu-id="c33c5-130">ستحتاج إلى أحد الأدوار التالية إما في الحاوية أو حساب التخزين المشار إليه أعلاه لتكون قادرًا على الاتصال بمصدر بيانات أو إنشاء مصدر بيانات:</span><span class="sxs-lookup"><span data-stu-id="c33c5-130">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="c33c5-131">قارئ بيانات مخزن البيانات الثنائية الكبيرة</span><span class="sxs-lookup"><span data-stu-id="c33c5-131">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="c33c5-132">مالك بيانات مخزن البيانات الثنائية الكبيرة</span><span class="sxs-lookup"><span data-stu-id="c33c5-132">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="c33c5-133">المساهم في بيانات مخزن البيانات الثنائية الكبيرة</span><span class="sxs-lookup"><span data-stu-id="c33c5-133">Storage Blob Data Contributor</span></span>

1. <span data-ttu-id="c33c5-134">في مربع الحوار **تحديد مجلد نموذج البيانات العامة**، حدد الملف model.json أو manifest.json لاستيراد البيانات منه، ثم حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="c33c5-134">In the **Select a Common Data Model folder** dialog, select the model.json or manifest.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="c33c5-135">لن يظهر في القائمة أي ملف model.json أو manifest.json مرتبط بمصدر بيانات آخر في البيئة.</span><span class="sxs-lookup"><span data-stu-id="c33c5-135">Any model.json or manifest.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="c33c5-136">ستحصل على قائمة بالكيانات المتوفرة في ملف model.json أو manifest.json المحدد.</span><span class="sxs-lookup"><span data-stu-id="c33c5-136">You'll get a list of available entities in the selected model.json or manifest.json file.</span></span> <span data-ttu-id="c33c5-137">يمكنك المراجعة والتحديد من قائمة الكيانات المتاحة وحدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="c33c5-137">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="c33c5-138">سيتم استيعاب جميع الكيانات المحددة من مصدر البيانات الجديد.</span><span class="sxs-lookup"><span data-stu-id="c33c5-138">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c33c5-139">![مربع حوار يعرض قائمة بالكيانات من ملف model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="c33c5-139">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="c33c5-140">أشر إلى كيانات البيانات الذي تريد تمكين ‏‫تعريف البيانات‬ لها وحدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="c33c5-140">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="c33c5-141">تتيح ملفات تعريف البيانات التحليلات والإمكانيات الأخرى.</span><span class="sxs-lookup"><span data-stu-id="c33c5-141">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="c33c5-142">يمكنك تحديد الكيان بالكامل الذي يحدد كافة السمات من الكيان، أو تحديد سمات معينة من اختيارك.</span><span class="sxs-lookup"><span data-stu-id="c33c5-142">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="c33c5-143">بشكل افتراضي، لا يتم تمكين أي كيان لتعريف البيانات.</span><span class="sxs-lookup"><span data-stu-id="c33c5-143">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c33c5-144">![مربع الحوار يعرض تعريف البيانات](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="c33c5-144">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="c33c5-145">بعد حفظ التحديدات، تفتح صفحة **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="c33c5-145">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="c33c5-146">من المفترض أن ترى الآن مجلد نموذج البيانات العامة كمصدر بيانات.</span><span class="sxs-lookup"><span data-stu-id="c33c5-146">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="c33c5-147">بإمكان ملف model.json أو manifest.json أن يرتبط فقط بمصدر بيانات واحد في البيئة نفسها.</span><span class="sxs-lookup"><span data-stu-id="c33c5-147">A model.json file or manifest.json can only associate with one data source in the same environment.</span></span> <span data-ttu-id="c33c5-148">ومع ذلك، يمكن استخدام ملف model.json أو manifest.json نفسه لمصادر البيانات في بيئات متعددة.</span><span class="sxs-lookup"><span data-stu-id="c33c5-148">However, the same model.json or manifest.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="c33c5-149">تحرير مصدر بيانات مجلد نموذج بيانات عامة</span><span class="sxs-lookup"><span data-stu-id="c33c5-149">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="c33c5-150">يمكنك تحديث مفتاح الوصول لحساب التخزين الذي يحتوي على مجلد نموذج البيانات العامة.</span><span class="sxs-lookup"><span data-stu-id="c33c5-150">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="c33c5-151">يمكنك أيضا تغيير الملف model.json أو manifest.json.</span><span class="sxs-lookup"><span data-stu-id="c33c5-151">You may also change the model.json or manifest.json file.</span></span> <span data-ttu-id="c33c5-152">للاتصال بحاوية أخرى من حساب التخزين، أو تغيير اسم الحساب، عليك [إنشاء اتصال مصدر بيانات جديد](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="c33c5-152">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="c33c5-153">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="c33c5-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="c33c5-154">إلى جانب مصدر البيانات الذي تريد تحديثه، حدد علامة القطع.</span><span class="sxs-lookup"><span data-stu-id="c33c5-154">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="c33c5-155">حدد الخيار **تحرير** من القائمة.</span><span class="sxs-lookup"><span data-stu-id="c33c5-155">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="c33c5-156">بشكل اختياري، قم بتحديث **مفتاح الوصول** وحدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="c33c5-156">Optionally, update the **Access key** and select **Next**.</span></span>

   ![مربع حوار لتحرير مفتاح وصول وتحديثه لمصدر بيانات موجود](media/edit-access-key.png)

5. <span data-ttu-id="c33c5-158">بشكل اختياري، يمكنك التحديث من اتصال مفتاح حساب باتصال قائم على الموارد أو اتصال قائم على الاشتراكات.</span><span class="sxs-lookup"><span data-stu-id="c33c5-158">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="c33c5-159">لمزيد من المعلومات، راجع [توصيل رؤى الجمهور بحساب Azure Data Lake Storage Gen2 بواسطة كيان خدمة Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="c33c5-159">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="c33c5-160">لا يمكنك **تغيير** معلومات الحاوية عند تحديث الاتصال.</span><span class="sxs-lookup"><span data-stu-id="c33c5-160">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]

   > ![مربع حوار لإدخال تفاصيل اتصال Azure Data Lake بحساب تخزين موجود](media/enter-existing-storage-details.png)

   > [!NOTE]
   > <span data-ttu-id="c33c5-162">ستحتاج إلى أحد الأدوار التالية إما في الحاوية أو حساب التخزين المشار إليه أعلاه لتكون قادرًا على الاتصال بمصدر بيانات أو إنشاء مصدر بيانات:</span><span class="sxs-lookup"><span data-stu-id="c33c5-162">You need one of the following roles either to the container or the storage account referred above to be able to connect to and create a data source:</span></span>
   >  - <span data-ttu-id="c33c5-163">قارئ بيانات مخزن البيانات الثنائية الكبيرة</span><span class="sxs-lookup"><span data-stu-id="c33c5-163">Storage Blob Data Reader</span></span>
   >  - <span data-ttu-id="c33c5-164">مالك بيانات مخزن البيانات الثنائية الكبيرة</span><span class="sxs-lookup"><span data-stu-id="c33c5-164">Storage Blob Data Owner</span></span>
   >  - <span data-ttu-id="c33c5-165">المساهم في بيانات مخزن البيانات الثنائية الكبيرة</span><span class="sxs-lookup"><span data-stu-id="c33c5-165">Storage Blob Data Contributo</span></span>


6. <span data-ttu-id="c33c5-166">بشكل اختياري، اختر ملف model.json أو manifest.json مختلفًا مع مجموعة كيانات مختلفة من الحاوية.</span><span class="sxs-lookup"><span data-stu-id="c33c5-166">Optionally, choose a different model.json or manifest.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="c33c5-167">بشكل اختياري، يمكنك تحديد الكيانات الإضافية لاستيعابها.</span><span class="sxs-lookup"><span data-stu-id="c33c5-167">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="c33c5-168">يمكنك أيضا إزالة أية كيانات محددة بالفعل في حالة عدم وجود تبعيات.</span><span class="sxs-lookup"><span data-stu-id="c33c5-168">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="c33c5-169">في حال وجود تبعيات على ملف model.json أو manifest.json الموجود وعلى مجموعة الكيانات، فسترى رسالة خطأ ولا يمكنك تحديد ملف model.json أو manifest.json مختلف.</span><span class="sxs-lookup"><span data-stu-id="c33c5-169">If there are dependencies on the existing model.json or manifest.json file and the set of entities, you'll see an error message and can't select a different model.json or manifest.json file.</span></span> <span data-ttu-id="c33c5-170">يمكنك إزالة هذه التبعيات قبل تغيير الملف model.json أو manifest.json أو إنشاء ملف مصدر بيانات جديد باستخدام الملف model.json أو manifest.json والذي ترغب في استخدامه لتجنب إزالة التبعيات.</span><span class="sxs-lookup"><span data-stu-id="c33c5-170">Remove those dependencies before changing the model.json or manifest.json file or create a new data source with the model.json or manifest.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="c33c5-171">بشكل اختياري، يمكنك تحديد سمات أو كيانات إضافية لتمكين ملفات تعريف البيانات أو تعطيل تلك المحددة بالفعل.</span><span class="sxs-lookup"><span data-stu-id="c33c5-171">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   


[!INCLUDE[footer-include](../includes/footer-banner.md)]