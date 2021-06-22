---
title: المهام المشتركة لسيناريوهات التنبؤ المحتملة
description: تعرف على كيفية إدارة التنبؤات واستكشاف الأخطاء فيها وإصلاحها وتحسينها.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095680"
---
# <a name="manage-predictions"></a><span data-ttu-id="c09ec-103">إدارة التنبؤات</span><span class="sxs-lookup"><span data-stu-id="c09ec-103">Manage predictions</span></span>

<span data-ttu-id="c09ec-104">تناقش هذه المقالة بعض المهام التي تشارك فيها معظم سيناريوهات التنبؤ.</span><span class="sxs-lookup"><span data-stu-id="c09ec-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="c09ec-105">استكشاف أخطاء تنبؤ فاشل وإصلاحها</span><span class="sxs-lookup"><span data-stu-id="c09ec-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="c09ec-106">انتقل إلى **الذكاء** > **التنبؤات** وحدد علامة التبويب **التنبؤات الخاصة بي‬**.</span><span class="sxs-lookup"><span data-stu-id="c09ec-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="c09ec-107">حدد علامة القطع البيضاوية الموجودة بجوار التنبؤ الذي تريد عرض سجلات الأخطاء له.</span><span class="sxs-lookup"><span data-stu-id="c09ec-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="c09ec-108">حدد **السجلات‏‎**.</span><span class="sxs-lookup"><span data-stu-id="c09ec-108">Select **Logs**.</span></span>

1. <span data-ttu-id="c09ec-109">راجع كافة الأخطاء.</span><span class="sxs-lookup"><span data-stu-id="c09ec-109">Review all the errors.</span></span> <span data-ttu-id="c09ec-110">ثمة أنواع عديدة من الأخطاء يمكن أن تحدث، وهي تصف الحالة التي تسببت في الخطأ.</span><span class="sxs-lookup"><span data-stu-id="c09ec-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="c09ec-111">على سبيل المثال، في العادة يتم حل خطأ عدم وجود بيانات كافية للتنبؤ بدقة عن طريق تحميل بيانات إضافية إلى Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c09ec-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="c09ec-112">تقرير إمكانية استخدام بيانات الإدخال</span><span class="sxs-lookup"><span data-stu-id="c09ec-112">Input data usability report</span></span>

<span data-ttu-id="c09ec-113">يوفر تقرير إمكانية استخدام بيانات الإدخال طريقة عرض مدمجة للأخطاء والتحذيرات التي قد تقوم التنبؤات الجاهزة بإنشائها.</span><span class="sxs-lookup"><span data-stu-id="c09ec-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="c09ec-114">كما يقدم توصيات حول كيفية تحسين أداء النموذج.</span><span class="sxs-lookup"><span data-stu-id="c09ec-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="c09ec-115">يتوفر التقرير بعد أن يستكمل النموذج عملية تدريبه.</span><span class="sxs-lookup"><span data-stu-id="c09ec-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="c09ec-116">يتم إنشاؤه لكل نموذج بشكل منفصل، بصرف النظر عما إذا كان قد اكتمل بنجاح أم لا.</span><span class="sxs-lookup"><span data-stu-id="c09ec-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="c09ec-117">في الوقت الحالي، تعمل هذه الميزة فقط مع نموذج خسارة الحركة‬.</span><span class="sxs-lookup"><span data-stu-id="c09ec-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="c09ec-118">عرض تقرير إمكانية استخدام بيانات الإدخال</span><span class="sxs-lookup"><span data-stu-id="c09ec-118">View the input data usability report</span></span>

<span data-ttu-id="c09ec-119">بعد أن يكمل النموذج الجاهز خطوة التدريب الخاصة به، استعرض التقرير:</span><span class="sxs-lookup"><span data-stu-id="c09ec-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="c09ec-120">حدد علامة القطع إلى جانب اسم النموذج واختر **تقرير إمكانية استخدام بيانات الإدخال**.</span><span class="sxs-lookup"><span data-stu-id="c09ec-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="c09ec-121">حدد حالة نموذج، وحدد **راجع تقرير إمكانية استخدام بيانات الإدخال‬** في الجزء الجانبي.</span><span class="sxs-lookup"><span data-stu-id="c09ec-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="c09ec-122">حدد أحد النماذج في القائمة وحدد **تقرير إمكانية استخدام بيانات الإدخال** في شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="c09ec-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="c09ec-123">افتح صفحة نتائج النموذج وحدد **تقرير إمكانية استخدام بيانات الإدخال** في شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="c09ec-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="c09ec-124">معلومات في تقرير إمكانية استخدام بيانات الإدخال‬.</span><span class="sxs-lookup"><span data-stu-id="c09ec-124">Information in the input data usability report</span></span>

<span data-ttu-id="c09ec-125">تحتوي الأعمدة التالية في التقرير على معلومات مفيدة لتحسين بيانات النموذج.</span><span class="sxs-lookup"><span data-stu-id="c09ec-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="مثال على تقرير إمكانية استخدام بيانات الإدخال يعرض جدولاً يحتوي على أخطاء وتحذيرات وتوصيات.":::

- <span data-ttu-id="c09ec-127">الاسم: اسم وصفي للخطأ أو التحذير أو التوصية.</span><span class="sxs-lookup"><span data-stu-id="c09ec-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="c09ec-128">الخطوة: مرحلة النموذج، التدريب أو النتيجة، التي تشير إليها المعلومات.</span><span class="sxs-lookup"><span data-stu-id="c09ec-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="c09ec-129">الحالة: خطورة المعلومات (خطأ، تحذير، توصية).</span><span class="sxs-lookup"><span data-stu-id="c09ec-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="c09ec-130">اسم العمود: عمود في كيان يلزم تعديله لتحسين أداء النموذج.</span><span class="sxs-lookup"><span data-stu-id="c09ec-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="c09ec-131">اسم الكيان: اسم الكيان الذي يلزم تعديله لتحسين أداء النموذج.</span><span class="sxs-lookup"><span data-stu-id="c09ec-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="c09ec-132">التفاصيل: تفاصيل حول الخطأ أو التحذير أو التوصية.</span><span class="sxs-lookup"><span data-stu-id="c09ec-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="c09ec-133">تحديث تنبؤ</span><span class="sxs-lookup"><span data-stu-id="c09ec-133">Refresh a prediction</span></span>

<span data-ttu-id="c09ec-134">سيتم تحديث التنبؤات تلقائيًا على وفقًا لنفس [جدول تحديثات البيانات الخاصة بك](system.md#schedule-tab) كما تم تكوينها في الإعدادات.</span><span class="sxs-lookup"><span data-stu-id="c09ec-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="c09ec-135">يمكنك تحديثها يدويًا أيضًا.</span><span class="sxs-lookup"><span data-stu-id="c09ec-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="c09ec-136">انتقل إلى **الذكاء** > **التنبؤات** وحدد علامة التبويب **التنبؤات الخاصة بي‬**.</span><span class="sxs-lookup"><span data-stu-id="c09ec-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="c09ec-137">حدد علامات الحذف الرأسية المجاورة للتنبؤ الذي ترغب في تحديثه.</span><span class="sxs-lookup"><span data-stu-id="c09ec-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="c09ec-138">حدد **تحديث**.</span><span class="sxs-lookup"><span data-stu-id="c09ec-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="c09ec-139">حذف التنبؤ</span><span class="sxs-lookup"><span data-stu-id="c09ec-139">Delete a prediction</span></span>

<span data-ttu-id="c09ec-140">يؤدي حذف تنبؤ إلى إزالة كيان الإخراج الخاص به أيضًا.</span><span class="sxs-lookup"><span data-stu-id="c09ec-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="c09ec-141">انتقل إلى **الذكاء** > **التنبؤات** وحدد علامة التبويب **التنبؤات الخاصة بي‬**.</span><span class="sxs-lookup"><span data-stu-id="c09ec-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="c09ec-142">حدد علامات الحذف الرأسية المجاورة للتنبؤ الذي ترغب في حذفه.</span><span class="sxs-lookup"><span data-stu-id="c09ec-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="c09ec-143">حدد **حذف**.</span><span class="sxs-lookup"><span data-stu-id="c09ec-143">Select **Delete**.</span></span>
