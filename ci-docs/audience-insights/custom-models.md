---
title: نماذج التعلم الآلي المخصصة | Microsoft Docs
description: استخدم النماذج المخصصة من خدمة التعلم الآلي من Azure في Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267218"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="54674-103">نماذج التعلم الآلي المخصصة</span><span class="sxs-lookup"><span data-stu-id="54674-103">Custom machine learning models</span></span>

<span data-ttu-id="54674-104">يتيح لك **الذكاء‏‎** > **النماذج المخصصة** إدارة سير العمل استنادًا إلى نماذج التعلم الآلي من Azure.</span><span class="sxs-lookup"><span data-stu-id="54674-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="54674-105">تساعدك مهام سير العمل علي اختيار البيانات التي ترغب في إنشاء رؤى منها وتعيين النتائج إلى بيانات العميل الموحدة.</span><span class="sxs-lookup"><span data-stu-id="54674-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="54674-106">لمزيد من المعلومات حول إنشاء نماذج تعلم آلي مخصصة، راجع [استخدام النماذج المستندة إلى التعلم الآلي من Azure](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="54674-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="54674-107">الذكاء الاصطناعي المسؤول</span><span class="sxs-lookup"><span data-stu-id="54674-107">Responsible AI</span></span>

<span data-ttu-id="54674-108">تقدم التنبؤات قدرات لإنشاء تجارب عملاء أفضل وتحسين قدرات الأعمال وتدفقات الإيرادات.</span><span class="sxs-lookup"><span data-stu-id="54674-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="54674-109">نوصي بضرورة موازنة قيمة التنبؤ في مقابل تأثيره والأخطاء المقصودة التي قد يتم تقديمها بطريقة معنوية.</span><span class="sxs-lookup"><span data-stu-id="54674-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="54674-110">اعرف المزيد حول الطريقة التي تعمل Microsoft من خلالها على [معالجة الذكاء الاصطناعي المسؤول](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="54674-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="54674-111">يمكنك أيضًا التعرف على [تقنيات وعمليات التعلم الآلي المسؤول](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) الخاص بالتعلم الآلي من Azure.</span><span class="sxs-lookup"><span data-stu-id="54674-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="54674-112">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="54674-112">Prerequisites</span></span>

- <span data-ttu-id="54674-113">في الوقت الحالي، تدعم هذه الميزة خدمات الويب المنشورة عبر [استوديو التعلم الآلي (كلاسيكي)‬](https://studio.azureml.net)و [التدفقات الدُفعية للتعلم الآلي من Azure‬](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="54674-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="54674-114">تحتاج إلى حساب تخزين Azure Data Lake Gen2 المقترن بمثيل استوديو Azure لاستخدام هذه الميزة.</span><span class="sxs-lookup"><span data-stu-id="54674-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="54674-115">لمزيد من المعلومات، راجع [إنشاء حساب تخزين Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="54674-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="54674-116">إضافة سير عمل جديد</span><span class="sxs-lookup"><span data-stu-id="54674-116">Add a new workflow</span></span>

1. <span data-ttu-id="54674-117">انتقل إلى **الذكاء** > **النماذج المخصصة** وحدد **سير عمل جديد**.</span><span class="sxs-lookup"><span data-stu-id="54674-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="54674-118">امنح الطراز المخصص اسمًا يمكن التعرف عليه في حقل **الاسم**.</span><span class="sxs-lookup"><span data-stu-id="54674-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="54674-119">![لقطة شاشة لجزء سير العمل الجديد](media/new-workflowv2.png "لقطة شاشة لجزء سير العمل الجديد")</span><span class="sxs-lookup"><span data-stu-id="54674-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="54674-120">حدد المؤسسة التي تحتوي على خدمة ويب في **المستأجر الذي يحتوي على خدمة الويب الخاصة بك**.</span><span class="sxs-lookup"><span data-stu-id="54674-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="54674-121">إذا كان اشتراك التعلم الآلي من Azure الخاص بك في مستأجر مختلف عن Customer Insights فحدد **تسجيل الدخول** باستخدام بيانات الاعتماد الخاصة بالمؤسسة المحددة.</span><span class="sxs-lookup"><span data-stu-id="54674-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="54674-122">حدد **مساحات العمل** المقترنة بخدمة الويب.</span><span class="sxs-lookup"><span data-stu-id="54674-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="54674-123">هناك قسمان مذكوران، أحدهما التعلم الآلي من Azure v1 (استوديو التعلم الآلي (كلاسيكي)) والتعلم الآلي من Azure v2 (التعلم الآلي من Azure).</span><span class="sxs-lookup"><span data-stu-id="54674-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="54674-124">إذا لم تكن متأكدًا من مساحة العمل المناسبة لخدمة الويب استوديو التعلم الآلي (كلاسيكي)‬، فحدد **أي واحد**.</span><span class="sxs-lookup"><span data-stu-id="54674-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="54674-125">اختر خدمة الويب استوديو التعلم الآلي (كلاسيكي) او تدفقات التعلم الآلي من Azure في القائمة المنسدلة **خدمة الويب التي تحتوي على نموذجك‬**.</span><span class="sxs-lookup"><span data-stu-id="54674-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="54674-126">ثم حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="54674-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="54674-127">اعرف المزيد حول [نشر خدمة ويب في استوديو التعلم الآلي (كلاسيكي)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="54674-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="54674-128">اعرف المزيد حول [نشر التدفقات في التعلم الآلي من Azure باستخدام المصمم](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) أو [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="54674-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="54674-129">يجب نشر التدفق تحت [نقطة نهاية التدفق](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="54674-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="54674-130">لكل **إدخال خدمة ويب**‬، حدد **الكيان** المطابق من رؤى الجمهور، وحدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="54674-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="54674-131">سيطبق سير عمل النموذج المخصص الاستكشافات لتعيين حقول إدخال خدمة ويب على سمات الكيان بالاستناد إلى اسم ونوع بيانات الحقل.</span><span class="sxs-lookup"><span data-stu-id="54674-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="54674-132">ستشاهد رسالة خطأ إذا تعذر تعيين حقل خدمة ويب إلى كيان.</span><span class="sxs-lookup"><span data-stu-id="54674-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="54674-133">![تكوين سير عمل](media/intelligence-screen2-updated.png "تكوين سير عمل")</span><span class="sxs-lookup"><span data-stu-id="54674-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="54674-134">في خطوة **معلمات إخراج النموذج**، قم بتعيين الخصائص التالية:</span><span class="sxs-lookup"><span data-stu-id="54674-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="54674-135">استوديو التعلم الآلي (كلاسيكي)</span><span class="sxs-lookup"><span data-stu-id="54674-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="54674-136">أدخل إخراج **اسم الكيان** الذي تريد ان تتدفق فيه نتائج إخراج خدمة الويب.</span><span class="sxs-lookup"><span data-stu-id="54674-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="54674-137">التعلم الآلي من Azure</span><span class="sxs-lookup"><span data-stu-id="54674-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="54674-138">أدخل إخراج **اسم الكيان** الذي تريد ان تتدفق فيه نتائج إخراج التدفقات.</span><span class="sxs-lookup"><span data-stu-id="54674-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="54674-139">حدد **اسم معلمة مخزن بيانات الإخراج‬** للتدفقات الدُفعية من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="54674-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="54674-140">حدد **اسم معلمة مسار الإخراج‬‬** للتدفقات الدُفعية من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="54674-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="54674-141">![جزء معلمات إخراج النموذج](media/intelligence-screen3-outputparameters.png "جزء معلمات إخراج النموذج")</span><span class="sxs-lookup"><span data-stu-id="54674-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="54674-142">حدد السمة المطابقة من القائمة المنسدلة **معرف العميل في النتائج**‬ التي تحدد العملاء، ثم حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="54674-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="54674-143">![ربط النتائج بجزء بيانات العميل](media/intelligence-screen4-relatetocustomer.png "ربط النتائج بجزء بيانات العميل")</span><span class="sxs-lookup"><span data-stu-id="54674-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="54674-144">ستشاهد شاشة **سير العمل المحفوظ** مع تفاصيل حول سير العمل.</span><span class="sxs-lookup"><span data-stu-id="54674-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="54674-145">إذا قمت بتكوين سير عمل لتدفق التعلم الآلي من Azure، فستتصل رؤى الجمهور بمساحة العمل التي تحتوي على التدفق.</span><span class="sxs-lookup"><span data-stu-id="54674-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="54674-146">ستحصل رؤى الجمهور على دور **المساهم** في مساحة عمل Azure.</span><span class="sxs-lookup"><span data-stu-id="54674-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="54674-147">حدد **تم**.</span><span class="sxs-lookup"><span data-stu-id="54674-147">Select **Done**.</span></span>

1. <span data-ttu-id="54674-148">يمكنك الآن تشغيل سير العمل من صفحة **النماذج المخصصة**.</span><span class="sxs-lookup"><span data-stu-id="54674-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="54674-149">تحرير سير عمل</span><span class="sxs-lookup"><span data-stu-id="54674-149">Edit a workflow</span></span>

1. <span data-ttu-id="54674-150">في صفحة **النماذج المخصصة**، حدد علامة القطع الرأسية في عمود **الإجراءات** إلى جانب سير أنشأته في وقت سابق، ثم حدد **تحرير**.</span><span class="sxs-lookup"><span data-stu-id="54674-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="54674-151">يمكنك تحديث الاسم الذي يسهل التعرف عليه لسير العمل في حقل **الاسم المعروض**، ولكن لا يمكنك تغيير خدمة الويب أو التدفق المكوّن.</span><span class="sxs-lookup"><span data-stu-id="54674-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="54674-152">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="54674-152">Select **Next**.</span></span>

1. <span data-ttu-id="54674-153">لكل **إدخال خدمة ويب**‬، يمكنك تحديث **الكيان** المطابق من رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="54674-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="54674-154">ثم حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="54674-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="54674-155">في خطوة **معلمات إخراج النموذج**، قم بتعيين الخصائص التالية:</span><span class="sxs-lookup"><span data-stu-id="54674-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="54674-156">استوديو التعلم الآلي (كلاسيكي)</span><span class="sxs-lookup"><span data-stu-id="54674-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="54674-157">أدخل إخراج **اسم الكيان** الذي تريد ان تتدفق فيه نتائج إخراج خدمة الويب.</span><span class="sxs-lookup"><span data-stu-id="54674-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="54674-158">التعلم الآلي من Azure</span><span class="sxs-lookup"><span data-stu-id="54674-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="54674-159">أدخل إخراج **اسم الكيان** الذي تريد ان تتدفق فيه نتائج إخراج التدفقات.</span><span class="sxs-lookup"><span data-stu-id="54674-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="54674-160">حدد **اسم معلمة مخزن بيانات الإخراج‬** لتدفقات الاختبار.</span><span class="sxs-lookup"><span data-stu-id="54674-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="54674-161">حدد **اسم معلمة مسار الإخراج‬‬** لتدفقات الاختبار.</span><span class="sxs-lookup"><span data-stu-id="54674-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="54674-162">حدد السمة المطابقة من القائمة المنسدلة **معرف العميل في النتائج**‬ التي تحدد العملاء، ثم حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="54674-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="54674-163">تحتاج إلى اختيار سمة من إخراج الاستدلال بقيم تشبه عمود معرف العميل الخاص بكيان العميل.</span><span class="sxs-lookup"><span data-stu-id="54674-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="54674-164">إذا لم يكن لديك مثل هذا العمود في مجموعة البيانات، فاختر السمة التي تعرف الصف بشكل فريد.</span><span class="sxs-lookup"><span data-stu-id="54674-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="54674-165">تشغيل سير عمل</span><span class="sxs-lookup"><span data-stu-id="54674-165">Run a workflow</span></span>

1. <span data-ttu-id="54674-166">في صفحة **النماذج المخصصة**، حدد علامة القطع الرأسية في عمود **الإجراءات** إلى جانب سير أنشأته في وقت سابق.</span><span class="sxs-lookup"><span data-stu-id="54674-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="54674-167">حدد **تشغيل**.</span><span class="sxs-lookup"><span data-stu-id="54674-167">Select **Run**.</span></span>

<span data-ttu-id="54674-168">يتم أيضًا تشغيل سير العمل تلقائيًا مع كل تحديث مجدول.</span><span class="sxs-lookup"><span data-stu-id="54674-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="54674-169">اعرف المزيد حول [إعداد التحديثات المجدولة](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="54674-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="54674-170">حذف سير عمل</span><span class="sxs-lookup"><span data-stu-id="54674-170">Delete a workflow</span></span>

1. <span data-ttu-id="54674-171">في صفحة **النماذج المخصصة**، حدد علامة القطع الرأسية في عمود **الإجراءات** إلى جانب سير أنشأته في وقت سابق.</span><span class="sxs-lookup"><span data-stu-id="54674-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="54674-172">حدد **حذف**، وقم بتأكيد الحذف.</span><span class="sxs-lookup"><span data-stu-id="54674-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="54674-173">سيتم حذف سير عملك.</span><span class="sxs-lookup"><span data-stu-id="54674-173">Your workflow will be deleted.</span></span> <span data-ttu-id="54674-174">يستمر [الكيان](entities.md) الذي تم إنشاؤه عند إنشاء سير العمل، ويمكن عرضه‏‎ من صفحة **الكيانات**.</span><span class="sxs-lookup"><span data-stu-id="54674-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]