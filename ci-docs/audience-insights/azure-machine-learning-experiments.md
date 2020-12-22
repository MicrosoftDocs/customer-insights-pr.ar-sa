---
title: تجارب التعلم الآلي من Azure
description: استخدم نماذج قائمة على التعلم الآلي من Azure في Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: 6f00d3202dc29d810bdd218d06c7d04e551846e8
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668752"
---
# <a name="use-azure-machine-learning-based-models"></a>استخدام نماذج قائمة على التعلم الآلي من Azure

إن البيانات الموحدة في Dynamics 365 Customer Insights عبارة عن مصدر لبناء نماذج التعلم الآلي التي يمكنها إنشاء المزيد من رؤى الأعمال. يتكامل Customer Insights مع استوديو التعلم الآلي (كلاسيكي) والتعلم الآلي من Azure لاستخدام نماذجك المخصصة. يمكنك مراجعة [تجارب استوديو التعلم الآلي (كلاسيكي)‬](machine-learning-studio-experiments.md) للحصول على أمثلة عن تجارب مبنية على استوديو التعلم الآلي (كلاسيكي)‬. 

## <a name="prerequisites"></a>المتطلبات الأساسية

- الوصول إلى Customer Insights
- اشتراك نشط في Azure Enterprise.
- [ملفات تعريف العميل الموحدة](data-unification.md)
- [تصدير الكيان إلى مساحة تخزين Azure Blob](export-azure-blob-storage.md) المكوّنة

## <a name="set-up-azure-machine-learning-workspace"></a>إعداد مساحة عمل التعلم الآلي من Azure‬

1. راجع [إنشاء مساحة عمل التعلم الآلي من Azure](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) للحصول على خيارات مختلفة لإنشاء مساحة العمل. للحصول على أفضل أداء، قم بإنشاء مساحة العمل في منطقه Azure الأقرب جغرافيًا من بيئة Customer Insights.

1. انتقل إلى مساحة العمل من خلال [استوديو التعلم الآلي من Azure](https://ml.azure.com/). هناك الكثير من [الطرق للتفاعل](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) مع مساحة عملك.

## <a name="work-with-azure-machine-learning-designer"></a>العمل مع مصمم التعلم الآلي من Azure

يوفر مصمم التعلم الآلي من Azure لوحة مرئية حيث يمكنك سحب وإفلات مجموعات البيانات والوحدات النمطية، بما يشبه استودي يشبه التعلم الآلي (كلاسيكي). ويمكن دمج تدفقات دُفعية تم إنشاؤها من المصمم في Customer Insights إذا تم تكوينها وفقًا لذلك. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>العمل مع SDK التعلم الآلي من Azure

يستخدم علماء البيانات ومطورو الذكاء الاصطناعي [SDK‏‎ التعلم الآلي من Azure](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) لبناء سير عمل التعلم الآلي. في الوقت الحالي، لا يمكن دمج النماذج التي تم تدريبها باستخدام SDK مباشرةً مع Customer Insights. يلزم وجود تدفقات استدلال دُفعية تستهلك هذا النموذج للتكامل مع Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>متطلبات تدفقات الاستدلال الدُفعية للتكامل مع Customer Insights

### <a name="dataset-configuration"></a>تكوين مجموعة البيانات

تحتاج إلى إنشاء مجموعات بيانات لاستخدام بيانات الكيان من Customer Insights إلى تدفقات الاستدلال الدُفعية. يجب تسجيل مجموعات البيانات هذه في مساحة العمل. في الوقت الحالي، ندعم فقط [مجموعات البيانات الجدولية](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) بتنسيق csv. يجب تعيين معلمة لمجموعات البيانات التي تتطابق مع كيان البيانات كمعلمة تدفقات.
   
* معلمات مجموعة البيانات في المصمم
   
     في المصمم، افتح **تحديد أعمدة في مجموعة البيانات**، وحدد **تعيين كمعلمة تدفق** حيث توفر اسمًا للمعلمة.

     > [!div class="mx-imgBorder"]
     > ![تعيين معلمات مجموعة البيانات في المصمم](media/intelligence-designer-dataset-parameters.png "تعيين معلمات مجموعة البيانات في المصمم")
   
* معلمة مجموعة البيانات في SDK‏ (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>تدفقات الاستدلال الدُفعية
  
* في المصمم، يمكن استخدام تدفقات التدريب لإنشاء أو تحديث تدفقات الاستدلال. يتم حاليًا دعم تدفقات الاستدلال الدُفعية فقط.

* باستخدام SDK، يمكنك نشر التدفقات إلى نقطة النهاية. في الوقت الحالي، يتكامل Customer Insights مع التدفقات الافتراضية في نقطة نهاية التدفقات الدُفعية في مساحة التعلم الآلي.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>استيراد بيانات التدفقات إلى Customer Insights

* يوفر المصمم [الوحدة النمطية لتصدير البيانات](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) التي تتيح لك تصدير إخراج التدفقات إلى مساحة تخزين Azure. في الوقت الحالي، يجب أن تستخدم الوحدة النمطية نوع متجر البيانات **مساحة تخزين Azure Blob** وتعيين معلمة **متجر البيانات** و **المسار** النسبي. يتجاوز Customer Insights المعلمتين أثناء تنفيذ التدفقات مع متجر بيانات ومسار يمكن للمنتج الوصول إليه.
   > [!div class="mx-imgBorder"]
   > ![تكوين الوحدة النمطية لتصدير البيانات](media/intelligence-designer-importdata.png "تكوين الوحدة النمطية لتصدير البيانات")
   
* عند كتابة إخراج الاستدلال باستخدام التعليمات البرمجية، يمكنك تحميل الإخراج إلى مسار داخل *متجر بيانات مسجل* في مساحة العمل. إذا تم تعيين معلمات للمسار ومتجر البيانات في التدفقات، فسيتمكن Customer insights من قراءة إخراج الاستدلال واستيراده. في الوقت الحالي، يتم دعم إخراج جدولي فردي بتنسيق csv. يجب أن يتضمن المسار الدليل واسم الملف.

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
