---
title: نماذج التعلم الآلي المخصصة | Microsoft Docs
description: استخدم النماذج المخصصة من خدمة التعلم الآلي من Azure في Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305602"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="011f8-103">نماذج التعلم الآلي المخصصة</span><span class="sxs-lookup"><span data-stu-id="011f8-103">Custom machine learning models</span></span>

<span data-ttu-id="011f8-104">يتيح لك **الذكاء‏‎** > **النماذج المخصصة** إدارة سير العمل استنادًا إلى نماذج التعلم الآلي من Azure.</span><span class="sxs-lookup"><span data-stu-id="011f8-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="011f8-105">تساعدك مهام سير العمل علي اختيار البيانات التي ترغب في إنشاء رؤى منها وتعيين النتائج إلى بيانات العميل الموحدة.</span><span class="sxs-lookup"><span data-stu-id="011f8-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="011f8-106">لمزيد من المعلومات حول إنشاء نماذج تعلم آلي مخصصة، راجع [استخدام النماذج المستندة إلى التعلم الآلي من Azure](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="011f8-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="011f8-107">الذكاء الاصطناعي المسؤول</span><span class="sxs-lookup"><span data-stu-id="011f8-107">Responsible AI</span></span>

<span data-ttu-id="011f8-108">تقدم التنبؤات قدرات لإنشاء تجارب عملاء أفضل وتحسين قدرات الأعمال وتدفقات الإيرادات.</span><span class="sxs-lookup"><span data-stu-id="011f8-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="011f8-109">نوصي بضرورة موازنة قيمة التنبؤ في مقابل تأثيره والأخطاء المقصودة التي قد يتم تقديمها بطريقة معنوية.</span><span class="sxs-lookup"><span data-stu-id="011f8-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="011f8-110">اعرف المزيد حول الطريقة التي تعمل Microsoft من خلالها على [معالجة الذكاء الاصطناعي المسؤول](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="011f8-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="011f8-111">يمكنك أيضًا التعرف على [تقنيات وعمليات التعلم الآلي المسؤول](/azure/machine-learning/concept-responsible-ml) الخاص بالتعلم الآلي من Azure.</span><span class="sxs-lookup"><span data-stu-id="011f8-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="011f8-112">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="011f8-112">Prerequisites</span></span>

- <span data-ttu-id="011f8-113">في الوقت الحالي، تدعم هذه الميزة خدمات الويب المنشورة عبر [استوديو التعلم الآلي (كلاسيكي)‬](https://studio.azureml.net)و [التدفقات الدُفعية للتعلم الآلي من Azure‬](/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="011f8-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="011f8-114">تحتاج إلى حساب تخزين Azure Data Lake Gen2 المقترن بمثيل استوديو Azure لاستخدام هذه الميزة.</span><span class="sxs-lookup"><span data-stu-id="011f8-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="011f8-115">لمزيد من المعلومات، راجع [إنشاء حساب تخزين Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="011f8-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="011f8-116">بالنسبة لمساحات عمل التعلم الآلي من Azure مع مسارات، ستحتاج إلى أذونات وصول المسؤول المالك أو المستخدم إلى مساحة عمل التعلم الآلي من Azure.</span><span class="sxs-lookup"><span data-stu-id="011f8-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="011f8-117">يتم نقل البيانات بين مثيلات Customer Insights وخدمات ويب Azure المحددة أو المسارات المحددة في سير العمل.</span><span class="sxs-lookup"><span data-stu-id="011f8-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="011f8-118">عند نقل البيانات إلى خدمة Azure، يرجى التأكد من أن الخدمة قد تم تكوينها لمعالجة البيانات بالطريقة والموقع اللازمين للامتثال لأي متطلبات قانونية أو تنظيمية لهذه البيانات لمؤسستك.</span><span class="sxs-lookup"><span data-stu-id="011f8-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="011f8-119">إضافة سير عمل جديد</span><span class="sxs-lookup"><span data-stu-id="011f8-119">Add a new workflow</span></span>

1. <span data-ttu-id="011f8-120">انتقل إلى **الذكاء** > **النماذج المخصصة** وحدد **سير عمل جديد**.</span><span class="sxs-lookup"><span data-stu-id="011f8-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="011f8-121">امنح الطراز المخصص اسمًا يمكن التعرف عليه في حقل **الاسم**.</span><span class="sxs-lookup"><span data-stu-id="011f8-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="011f8-122">![لقطة شاشة لجزء سير العمل الجديد](media/new-workflowv2.png "لقطة شاشة لجزء سير العمل الجديد")</span><span class="sxs-lookup"><span data-stu-id="011f8-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="011f8-123">حدد المؤسسة التي تحتوي على خدمة ويب في **المستأجر الذي يحتوي على خدمة الويب الخاصة بك**.</span><span class="sxs-lookup"><span data-stu-id="011f8-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="011f8-124">إذا كان اشتراك التعلم الآلي من Azure الخاص بك في مستأجر مختلف عن Customer Insights فحدد **تسجيل الدخول** باستخدام بيانات الاعتماد الخاصة بالمؤسسة المحددة.</span><span class="sxs-lookup"><span data-stu-id="011f8-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="011f8-125">حدد **مساحات العمل** المقترنة بخدمة الويب.</span><span class="sxs-lookup"><span data-stu-id="011f8-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="011f8-126">هناك قسمان مذكوران، أحدهما التعلم الآلي من Azure v1 (استوديو التعلم الآلي (كلاسيكي)) والتعلم الآلي من Azure v2 (التعلم الآلي من Azure).</span><span class="sxs-lookup"><span data-stu-id="011f8-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="011f8-127">إذا لم تكن متأكدًا من مساحة العمل المناسبة لخدمة الويب استوديو التعلم الآلي (كلاسيكي)‬، فحدد **أي واحد**.</span><span class="sxs-lookup"><span data-stu-id="011f8-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="011f8-128">اختر خدمة الويب استوديو التعلم الآلي (كلاسيكي) او تدفقات التعلم الآلي من Azure في القائمة المنسدلة **خدمة الويب التي تحتوي على نموذجك‬**.</span><span class="sxs-lookup"><span data-stu-id="011f8-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="011f8-129">ثم حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="011f8-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="011f8-130">اعرف المزيد حول [نشر خدمة ويب في استوديو التعلم الآلي (كلاسيكي)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="011f8-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="011f8-131">اعرف المزيد حول [نشر التدفقات في التعلم الآلي من Azure باستخدام المصمم](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) أو [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="011f8-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="011f8-132">يجب نشر التدفق تحت [نقطة نهاية التدفق](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="011f8-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="011f8-133">لكل **إدخال خدمة ويب**‬، حدد **الكيان** المطابق من رؤى الجمهور، وحدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="011f8-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="011f8-134">سيطبق سير عمل النموذج المخصص الاستكشافات لتعيين حقول إدخال خدمة ويب على سمات الكيان بالاستناد إلى اسم ونوع بيانات الحقل.</span><span class="sxs-lookup"><span data-stu-id="011f8-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="011f8-135">ستشاهد رسالة خطأ إذا تعذر تعيين حقل خدمة ويب إلى كيان.</span><span class="sxs-lookup"><span data-stu-id="011f8-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="011f8-136">![تكوين سير عمل](media/intelligence-screen2-updated.png "تكوين سير عمل")</span><span class="sxs-lookup"><span data-stu-id="011f8-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="011f8-137">في خطوة **معلمات إخراج النموذج**، قم بتعيين الخصائص التالية:</span><span class="sxs-lookup"><span data-stu-id="011f8-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="011f8-138">استوديو التعلم الآلي (كلاسيكي)</span><span class="sxs-lookup"><span data-stu-id="011f8-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="011f8-139">أدخل إخراج **اسم الكيان** الذي تريد ان تتدفق فيه نتائج إخراج خدمة الويب.</span><span class="sxs-lookup"><span data-stu-id="011f8-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="011f8-140">التعلم الآلي من Azure</span><span class="sxs-lookup"><span data-stu-id="011f8-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="011f8-141">أدخل إخراج **اسم الكيان** الذي تريد ان تتدفق فيه نتائج إخراج التدفقات.</span><span class="sxs-lookup"><span data-stu-id="011f8-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="011f8-142">حدد **اسم معلمة مخزن بيانات الإخراج‬** للتدفقات الدُفعية من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="011f8-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="011f8-143">حدد **اسم معلمة مسار الإخراج‬‬** للتدفقات الدُفعية من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="011f8-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="011f8-144">![جزء معلمات إخراج النموذج](media/intelligence-screen3-outputparameters.png "جزء معلمات إخراج النموذج")</span><span class="sxs-lookup"><span data-stu-id="011f8-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="011f8-145">حدد السمة المطابقة من القائمة المنسدلة **معرف العميل في النتائج** التي تحدد العملاء، وحدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="011f8-145">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="011f8-146">![ربط النتائج بجزء بيانات العميل](media/intelligence-screen4-relatetocustomer.png "ربط النتائج بجزء بيانات العميل")</span><span class="sxs-lookup"><span data-stu-id="011f8-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="011f8-147">ستشاهد شاشة **سير العمل المحفوظ** مع تفاصيل حول سير العمل.</span><span class="sxs-lookup"><span data-stu-id="011f8-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="011f8-148">إذا قمت بتكوين سير عمل لتدفق التعلم الآلي من Azure، فستتصل رؤى الجمهور بمساحة العمل التي تحتوي على التدفق.</span><span class="sxs-lookup"><span data-stu-id="011f8-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="011f8-149">ستحصل رؤى الجمهور على دور **المساهم** في مساحة عمل Azure.</span><span class="sxs-lookup"><span data-stu-id="011f8-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="011f8-150">حدد **تم**.</span><span class="sxs-lookup"><span data-stu-id="011f8-150">Select **Done**.</span></span>

1. <span data-ttu-id="011f8-151">يمكنك الآن تشغيل سير العمل من صفحة **النماذج المخصصة**.</span><span class="sxs-lookup"><span data-stu-id="011f8-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="011f8-152">تحرير سير عمل</span><span class="sxs-lookup"><span data-stu-id="011f8-152">Edit a workflow</span></span>

1. <span data-ttu-id="011f8-153">في صفحة **النماذج المخصصة**، حدد علامة القطع الرأسية في عمود **الإجراءات** إلى جانب سير أنشأته في وقت سابق، ثم حدد **تحرير**.</span><span class="sxs-lookup"><span data-stu-id="011f8-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="011f8-154">يمكنك تحديث الاسم الذي يسهل التعرف عليه لسير العمل في حقل **الاسم المعروض**، ولكن لا يمكنك تغيير خدمة الويب أو التدفق المكوّن.</span><span class="sxs-lookup"><span data-stu-id="011f8-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="011f8-155">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="011f8-155">Select **Next**.</span></span>

1. <span data-ttu-id="011f8-156">لكل **إدخال خدمة ويب**‬، يمكنك تحديث **الكيان** المطابق من رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="011f8-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="011f8-157">ثم حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="011f8-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="011f8-158">في خطوة **معلمات إخراج النموذج**، قم بتعيين الخصائص التالية:</span><span class="sxs-lookup"><span data-stu-id="011f8-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="011f8-159">استوديو التعلم الآلي (كلاسيكي)</span><span class="sxs-lookup"><span data-stu-id="011f8-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="011f8-160">أدخل إخراج **اسم الكيان** الذي تريد ان تتدفق فيه نتائج إخراج خدمة الويب.</span><span class="sxs-lookup"><span data-stu-id="011f8-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="011f8-161">التعلم الآلي من Azure</span><span class="sxs-lookup"><span data-stu-id="011f8-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="011f8-162">أدخل إخراج **اسم الكيان** الذي تريد ان تتدفق فيه نتائج إخراج التدفقات.</span><span class="sxs-lookup"><span data-stu-id="011f8-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="011f8-163">حدد **اسم معلمة مخزن بيانات الإخراج‬** لتدفقات الاختبار.</span><span class="sxs-lookup"><span data-stu-id="011f8-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="011f8-164">حدد **اسم معلمة مسار الإخراج‬‬** لتدفقات الاختبار.</span><span class="sxs-lookup"><span data-stu-id="011f8-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="011f8-165">حدد السمة المطابقة من القائمة المنسدلة **معرف العميل في النتائج** التي تحدد العملاء، وحدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="011f8-165">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="011f8-166">اختر سمة من إخراج الاستدلال بقيم تشبه عمود معرف العميل الخاص بكيان العميل.</span><span class="sxs-lookup"><span data-stu-id="011f8-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="011f8-167">إذا لم يكن لديك مثل هذا العمود في مجموعة البيانات، فاختر السمة التي تعرف الصف بشكل فريد.</span><span class="sxs-lookup"><span data-stu-id="011f8-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="011f8-168">تشغيل سير عمل</span><span class="sxs-lookup"><span data-stu-id="011f8-168">Run a workflow</span></span>

1. <span data-ttu-id="011f8-169">في صفحة **النماذج المخصصة**، حدد علامة القطع الرأسية في عمود **الإجراءات** إلى جانب سير أنشأته في وقت سابق.</span><span class="sxs-lookup"><span data-stu-id="011f8-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="011f8-170">حدد **تشغيل**.</span><span class="sxs-lookup"><span data-stu-id="011f8-170">Select **Run**.</span></span>

<span data-ttu-id="011f8-171">يتم أيضًا تشغيل سير العمل تلقائيًا مع كل تحديث مجدول.</span><span class="sxs-lookup"><span data-stu-id="011f8-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="011f8-172">اعرف المزيد حول [إعداد التحديثات المجدولة](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="011f8-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="011f8-173">حذف سير عمل</span><span class="sxs-lookup"><span data-stu-id="011f8-173">Delete a workflow</span></span>

1. <span data-ttu-id="011f8-174">في صفحة **النماذج المخصصة**، حدد علامة القطع الرأسية في عمود **الإجراءات** إلى جانب سير أنشأته في وقت سابق.</span><span class="sxs-lookup"><span data-stu-id="011f8-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="011f8-175">حدد **حذف**، وقم بتأكيد الحذف.</span><span class="sxs-lookup"><span data-stu-id="011f8-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="011f8-176">سيتم حذف سير عملك.</span><span class="sxs-lookup"><span data-stu-id="011f8-176">Your workflow will be deleted.</span></span> <span data-ttu-id="011f8-177">يستمر [الكيان](entities.md) الذي تم إنشاؤه عند إنشاء سير العمل، ويمكن عرضه‏‎ من صفحة **الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="011f8-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="011f8-178">النتائج</span><span class="sxs-lookup"><span data-stu-id="011f8-178">Results</span></span>

<span data-ttu-id="011f8-179">يتم تخزين النتائج من سير العمل في الكيان الذي تم تكوينه أثناء مرحلة معلمة إخراج النموذج.</span><span class="sxs-lookup"><span data-stu-id="011f8-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="011f8-180">يمكنك الوصول إلى هذه البيانات من [صفحة الكيانات](entities.md) أو من خلال [الوصول إلى API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="011f8-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="011f8-181">الوصول إلى API</span><span class="sxs-lookup"><span data-stu-id="011f8-181">API Access</span></span>

<span data-ttu-id="011f8-182">كي يتمكن استعلام OData المحدد من الحصول على بيانات من كيان نموذج مخصص، استخدم التنسيق التالي:</span><span class="sxs-lookup"><span data-stu-id="011f8-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="011f8-183">استبدل `<your instance id>` بمعرف بيئة Customer Insights، الذي يمكن العثور عليه في شريط العناوين في المستعرض عند الوصول إلى Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="011f8-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="011f8-184">استبدل `<custom model output entity>` باسم الكيان الذي قمت بتوفيره أثناء خطوة معلمات إخراج النموذج لتكوين النموذج المخصص.</span><span class="sxs-lookup"><span data-stu-id="011f8-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="011f8-185">استبدل `<guid value>` بمعرف العميل للعميل الذي ترغب في الوصول إلى سجله.</span><span class="sxs-lookup"><span data-stu-id="011f8-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="011f8-186">يمكنك العثور على هذا المعرف عادةً في [صفحة ملفات تعريف العملاء](customer-profiles.md) في حقل معرف العميل.</span><span class="sxs-lookup"><span data-stu-id="011f8-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="011f8-187">الأسئلة المتداولة</span><span class="sxs-lookup"><span data-stu-id="011f8-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="011f8-188">لماذا لا يمكنني رؤية مساري عند إعداد سير عمل نموذج مخصص؟</span><span class="sxs-lookup"><span data-stu-id="011f8-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="011f8-189">تحدث هذه المشكلة بشكل متكرر بسبب مشكلة في تكوين المسار.</span><span class="sxs-lookup"><span data-stu-id="011f8-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="011f8-190">تأكد من [تكوين معلمة الإدخال](azure-machine-learning-experiments.md#dataset-configuration) وأيضًا من تكوين [معلمات مخزن بيانات الإخراج ومعلمة مسار الإخراج‬](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights).</span><span class="sxs-lookup"><span data-stu-id="011f8-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="011f8-191">ما معنى الخطأ "لا يمكن حفظ سير عمل التحليل الذكي‬"؟</span><span class="sxs-lookup"><span data-stu-id="011f8-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="011f8-192">يرى المستخدمون رسالة الخطأ هذه عادةً إذا لم يكن لديهم امتيازات وصول المسؤول المالك أو المستخدم في مساحة العمل.</span><span class="sxs-lookup"><span data-stu-id="011f8-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="011f8-193">يحتاج المستخدم إلى مستوى أعلى من الأذونات لتمكين Customer Insights من معالجة سير العمل كخدمة بدلاً من استخدام بيانات اعتماد المستخدم لعمليات التشغيل اللاحقة لسير العمل.</span><span class="sxs-lookup"><span data-stu-id="011f8-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
