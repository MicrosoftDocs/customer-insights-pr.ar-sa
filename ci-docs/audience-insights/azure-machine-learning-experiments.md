---
title: تجارب التعلم الآلي من Azure
description: استخدم نماذج قائمة على التعلم الآلي من Azure في Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267890"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="2a627-103">استخدام نماذج قائمة على التعلم الآلي من Azure</span><span class="sxs-lookup"><span data-stu-id="2a627-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="2a627-104">إن البيانات الموحدة في Dynamics 365 Customer Insights عبارة عن مصدر لبناء نماذج التعلم الآلي التي يمكنها إنشاء المزيد من رؤى الأعمال.</span><span class="sxs-lookup"><span data-stu-id="2a627-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="2a627-105">يتكامل Customer Insights مع استوديو التعلم الآلي (كلاسيكي) والتعلم الآلي من Azure لاستخدام نماذجك المخصصة.</span><span class="sxs-lookup"><span data-stu-id="2a627-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="2a627-106">يمكنك مراجعة [تجارب استوديو التعلم الآلي (كلاسيكي)‬](machine-learning-studio-experiments.md) للحصول على أمثلة عن تجارب مبنية على استوديو التعلم الآلي (كلاسيكي)‬.</span><span class="sxs-lookup"><span data-stu-id="2a627-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="2a627-107">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="2a627-107">Prerequisites</span></span>

- <span data-ttu-id="2a627-108">الوصول إلى Customer Insights</span><span class="sxs-lookup"><span data-stu-id="2a627-108">Access to Customer Insights</span></span>
- <span data-ttu-id="2a627-109">اشتراك نشط في Azure Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2a627-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="2a627-110">ملفات تعريف العميل الموحدة</span><span class="sxs-lookup"><span data-stu-id="2a627-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="2a627-111">[تصدير الكيان إلى مساحة تخزين Azure Blob](export-azure-blob-storage.md) المكوّنة</span><span class="sxs-lookup"><span data-stu-id="2a627-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="2a627-112">إعداد مساحة عمل التعلم الآلي من Azure‬</span><span class="sxs-lookup"><span data-stu-id="2a627-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="2a627-113">راجع [إنشاء مساحة عمل التعلم الآلي من Azure](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) للحصول على خيارات مختلفة لإنشاء مساحة العمل.</span><span class="sxs-lookup"><span data-stu-id="2a627-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="2a627-114">للحصول على أفضل أداء، قم بإنشاء مساحة العمل في منطقه Azure الأقرب جغرافيًا من بيئة Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2a627-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="2a627-115">انتقل إلى مساحة العمل من خلال [استوديو التعلم الآلي من Azure](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="2a627-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="2a627-116">هناك الكثير من [الطرق للتفاعل](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) مع مساحة عملك.</span><span class="sxs-lookup"><span data-stu-id="2a627-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="2a627-117">العمل مع مصمم التعلم الآلي من Azure</span><span class="sxs-lookup"><span data-stu-id="2a627-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="2a627-118">يوفر مصمم التعلم الآلي من Azure لوحة مرئية حيث يمكنك سحب وإفلات مجموعات البيانات والوحدات النمطية، بما يشبه استودي يشبه التعلم الآلي (كلاسيكي).</span><span class="sxs-lookup"><span data-stu-id="2a627-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="2a627-119">ويمكن دمج تدفقات دُفعية تم إنشاؤها من المصمم في Customer Insights إذا تم تكوينها وفقًا لذلك.</span><span class="sxs-lookup"><span data-stu-id="2a627-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="2a627-120">العمل مع SDK التعلم الآلي من Azure</span><span class="sxs-lookup"><span data-stu-id="2a627-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="2a627-121">يستخدم علماء البيانات ومطورو الذكاء الاصطناعي [SDK‏‎ التعلم الآلي من Azure](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) لبناء سير عمل التعلم الآلي.</span><span class="sxs-lookup"><span data-stu-id="2a627-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="2a627-122">في الوقت الحالي، لا يمكن دمج النماذج التي تم تدريبها باستخدام SDK مباشرةً مع Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2a627-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="2a627-123">يلزم وجود تدفقات استدلال دُفعية تستهلك هذا النموذج للتكامل مع Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2a627-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="2a627-124">متطلبات تدفقات الاستدلال الدُفعية للتكامل مع Customer Insights</span><span class="sxs-lookup"><span data-stu-id="2a627-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="2a627-125">تكوين مجموعة البيانات</span><span class="sxs-lookup"><span data-stu-id="2a627-125">Dataset Configuration</span></span>

<span data-ttu-id="2a627-126">تحتاج إلى إنشاء مجموعات بيانات لاستخدام بيانات الكيان من Customer Insights إلى تدفقات الاستدلال الدُفعية.</span><span class="sxs-lookup"><span data-stu-id="2a627-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="2a627-127">يجب تسجيل مجموعات البيانات هذه في مساحة العمل.</span><span class="sxs-lookup"><span data-stu-id="2a627-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="2a627-128">في الوقت الحالي، ندعم فقط [مجموعات البيانات الجدولية](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) بتنسيق csv.</span><span class="sxs-lookup"><span data-stu-id="2a627-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="2a627-129">يجب تعيين معلمة لمجموعات البيانات التي تتطابق مع كيان البيانات كمعلمة تدفقات.</span><span class="sxs-lookup"><span data-stu-id="2a627-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="2a627-130">معلمات مجموعة البيانات في المصمم</span><span class="sxs-lookup"><span data-stu-id="2a627-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="2a627-131">في المصمم، افتح **تحديد أعمدة في مجموعة البيانات**، وحدد **تعيين كمعلمة تدفق** حيث توفر اسمًا للمعلمة.</span><span class="sxs-lookup"><span data-stu-id="2a627-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="2a627-132">![تعيين معلمات مجموعة البيانات في المصمم](media/intelligence-designer-dataset-parameters.png "تعيين معلمات مجموعة البيانات في المصمم")</span><span class="sxs-lookup"><span data-stu-id="2a627-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="2a627-133">معلمة مجموعة البيانات في SDK‏ (Python)</span><span class="sxs-lookup"><span data-stu-id="2a627-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="2a627-134">تدفقات الاستدلال الدُفعية</span><span class="sxs-lookup"><span data-stu-id="2a627-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="2a627-135">في المصمم، يمكن استخدام تدفقات التدريب لإنشاء أو تحديث تدفقات الاستدلال.</span><span class="sxs-lookup"><span data-stu-id="2a627-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="2a627-136">يتم حاليًا دعم تدفقات الاستدلال الدُفعية فقط.</span><span class="sxs-lookup"><span data-stu-id="2a627-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="2a627-137">باستخدام SDK، يمكنك نشر التدفقات إلى نقطة النهاية.</span><span class="sxs-lookup"><span data-stu-id="2a627-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="2a627-138">في الوقت الحالي، يتكامل Customer Insights مع التدفقات الافتراضية في نقطة نهاية التدفقات الدُفعية في مساحة التعلم الآلي.</span><span class="sxs-lookup"><span data-stu-id="2a627-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="2a627-139">استيراد بيانات التدفقات إلى Customer Insights</span><span class="sxs-lookup"><span data-stu-id="2a627-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="2a627-140">يوفر المصمم [الوحدة النمطية لتصدير البيانات](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) التي تتيح لك تصدير إخراج التدفقات إلى مساحة تخزين Azure.</span><span class="sxs-lookup"><span data-stu-id="2a627-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="2a627-141">في الوقت الحالي، يجب أن تستخدم الوحدة النمطية نوع متجر البيانات **مساحة تخزين Azure Blob** وتعيين معلمة **متجر البيانات** و **المسار** النسبي.</span><span class="sxs-lookup"><span data-stu-id="2a627-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="2a627-142">يتجاوز Customer Insights المعلمتين أثناء تنفيذ التدفقات مع متجر بيانات ومسار يمكن للمنتج الوصول إليه.</span><span class="sxs-lookup"><span data-stu-id="2a627-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2a627-143">![تكوين الوحدة النمطية لتصدير البيانات](media/intelligence-designer-importdata.png "تكوين الوحدة النمطية لتصدير البيانات")</span><span class="sxs-lookup"><span data-stu-id="2a627-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="2a627-144">عند كتابة إخراج الاستدلال باستخدام التعليمات البرمجية، يمكنك تحميل الإخراج إلى مسار داخل *متجر بيانات مسجل* في مساحة العمل.</span><span class="sxs-lookup"><span data-stu-id="2a627-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="2a627-145">إذا تم تعيين معلمات للمسار ومتجر البيانات في التدفقات، فسيتمكن Customer insights من قراءة إخراج الاستدلال واستيراده.</span><span class="sxs-lookup"><span data-stu-id="2a627-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="2a627-146">في الوقت الحالي، يتم دعم إخراج جدولي فردي بتنسيق csv.</span><span class="sxs-lookup"><span data-stu-id="2a627-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="2a627-147">يجب أن يتضمن المسار الدليل واسم الملف.</span><span class="sxs-lookup"><span data-stu-id="2a627-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]