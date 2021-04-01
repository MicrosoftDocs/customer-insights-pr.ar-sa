---
title: قيود واستيعاب البيانات في الوقت الحقيقي
description: معلومات عامة حول القدرات في الوقت الحقيقي في رؤى الجمهور.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598553"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="a8400-103">استيعاب بيانات الوقت الحقيقي (معاينة)</span><span class="sxs-lookup"><span data-stu-id="a8400-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="a8400-104">تتيح لك الوظائف القريبة من الوقت الحقيقي رؤية، خلال ثواني، التفاعلات الأخيرة التي أجراها عملاؤك مع منتجاتك أو خدماتك.</span><span class="sxs-lookup"><span data-stu-id="a8400-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="a8400-105">تتضمن [عمليات التحديث المجدولة](system.md#schedule-tab) أعدادًا كبيرة من السجلات وعدة عمليات معقدة.</span><span class="sxs-lookup"><span data-stu-id="a8400-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="a8400-106">يتم أولاً سحب البيانات من مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="a8400-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="a8400-107">بعد ذلك، تكون البيانات موحدة، ثم يتم إثراؤها بمعلومات إضافية.</span><span class="sxs-lookup"><span data-stu-id="a8400-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="a8400-108">كل تشغيل لهذه العملية قد يستغرق من دقائق إلى ساعات.</span><span class="sxs-lookup"><span data-stu-id="a8400-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="a8400-109">توفر الوظائف في الوقت الحقيقي البيانات لاستهلاكها على الفور، حتى يقوم التحديث المجدول التالي بسحب هذه البيانات من مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="a8400-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="a8400-110">وتحتوي تحديثات الوقت الحقيقي على وقت انتهاء صلاحية لا تتجاوز القيمة من مصدر البيانات:</span><span class="sxs-lookup"><span data-stu-id="a8400-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="a8400-111">سيتم الاحتفاظ بتحديثات ملف التعريف لمدة 4 ساعات</span><span class="sxs-lookup"><span data-stu-id="a8400-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="a8400-112">سيتم الاحتفاظ بالأنشطة لمدة 30 يومًا</span><span class="sxs-lookup"><span data-stu-id="a8400-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="a8400-113">وتعتبر هذه القيم معلمات مكالمات API التي يمكن تغييرها.</span><span class="sxs-lookup"><span data-stu-id="a8400-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="a8400-114">إنها تهدف إلى التأكد من أن بيانات المصدر لديك تظل مصدر الحقيقة لديك.</span><span class="sxs-lookup"><span data-stu-id="a8400-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="a8400-115">إذا كنت ترغب في تضمين التحديثات في الوقت الحقيقي لمدة أطول، ستحتاج إلى إضافتها إلى مصدر البيانات بحيث يتم سحبها أثناء التحديث المجدول التالي.</span><span class="sxs-lookup"><span data-stu-id="a8400-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="a8400-116">تحديث الوقت الحقيقي لحقول ملف تعريف العميل الموحدة</span><span class="sxs-lookup"><span data-stu-id="a8400-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="a8400-117">سيتم عرض ملفات التعريف المحدّثة في طريقة عرض بطاقة العميل، أو أي مرئيات أخرى، في غضون ثوانٍ قليلة.</span><span class="sxs-lookup"><span data-stu-id="a8400-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="a8400-118">نظرًا لحدوث عمليات الوقت الحقيقي بعد حدوث توحيد البيانات، فإنها تنطبق فقط على ملفات تعريف العميل الموحدة.</span><span class="sxs-lookup"><span data-stu-id="a8400-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="a8400-119">ونتيجة لذلك، لن تقوم تغييرات ملف تعريف الوقت الحقيقي بتحديث المقاييس أو عضوية المقطع أو الإثراء.</span><span class="sxs-lookup"><span data-stu-id="a8400-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="a8400-120">القيود</span><span class="sxs-lookup"><span data-stu-id="a8400-120">Limitations</span></span>

- <span data-ttu-id="a8400-121">يمكن تحديث ملفات تعريف العملاء، ولكن لا يمكن إنشاؤها أو حذفها.</span><span class="sxs-lookup"><span data-stu-id="a8400-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="a8400-122">لا يمكن تصدير التحديثات في الوقت الحقيقي إلى أنظمة خارجية، مثل Power BI حاليًا.</span><span class="sxs-lookup"><span data-stu-id="a8400-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="a8400-123">إنشاء الأنشطة في الوقت الحقيقي</span><span class="sxs-lookup"><span data-stu-id="a8400-123">Real-time creation of activities</span></span>

<span data-ttu-id="a8400-124">تسمح لك واجهة برمجة التطبيقات (API) في الوقت الحقيقي بنشر نشاط جديد من النظام المصدر (سجل مصدر فردي) إلى ملف تعريف عميل موحد.</span><span class="sxs-lookup"><span data-stu-id="a8400-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="a8400-125">سيكون النشاط الجديد متوفرًا كنشاط موحد في المخطط الزمني لملف تعريف العميل الموحد ذلك خلال ثوان.</span><span class="sxs-lookup"><span data-stu-id="a8400-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="a8400-126">يمكنك رؤية المخطط الزمني في طريقة عرض بطاقة العميل أو اي تكامل آخر للمخطط الزمني قد قمت بتكوينه.</span><span class="sxs-lookup"><span data-stu-id="a8400-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="a8400-127">الأنشطة غير قابلة للتغيير.</span><span class="sxs-lookup"><span data-stu-id="a8400-127">Activities are immutable.</span></span> <span data-ttu-id="a8400-128">ولا تتغير بمجرد إنشائها.</span><span class="sxs-lookup"><span data-stu-id="a8400-128">They don't change once created.</span></span>
> - <span data-ttu-id="a8400-129">حاليًا، لا يتم تحديث الشرائح والمقاييس استنادًا إلى النشاط الجديد.</span><span class="sxs-lookup"><span data-stu-id="a8400-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="a8400-130">لا تُعد الأنشطة التي تتم إضافتها فقط من خلال واجهة برمجة التطبيقات (API) في الوقت الحقيقي جزءًا من التصديرات ولن يتم عرضها في PowerBI.</span><span class="sxs-lookup"><span data-stu-id="a8400-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="a8400-131">هناك طريقتان للاتصال بواجهة برمجة التطبيقات (API) في الوقت الحقيقي:</span><span class="sxs-lookup"><span data-stu-id="a8400-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="a8400-132">[بشكل غير مباشر](#connect-via-the-dynamics-365-customer-insights-connector)، باستخدام الموصل [Dynamics 365 Customer Insights ](/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="a8400-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="a8400-133">[بشكل مباشر](#connect-directly-to-the-real-time-api)، مع التعليمات البرمجية</span><span class="sxs-lookup"><span data-stu-id="a8400-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="a8400-134">كلا الطريقتين تشارك المتطلبات الأساسية التالية:</span><span class="sxs-lookup"><span data-stu-id="a8400-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="a8400-135">بيئة Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a8400-135">A Customer Insights environment</span></span>
- <span data-ttu-id="a8400-136">ملفات تعريف العميل الموحدة</span><span class="sxs-lookup"><span data-stu-id="a8400-136">Unified customer profiles</span></span>
- <span data-ttu-id="a8400-137">الأنشطة التي تم تكوينها وتشغيلها</span><span class="sxs-lookup"><span data-stu-id="a8400-137">Activities configured and run</span></span>
- <span data-ttu-id="a8400-138">أذونات المساهم أو المسؤول لمصادقه حسابك</span><span class="sxs-lookup"><span data-stu-id="a8400-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="a8400-139">الاتصال عبر الموصل Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="a8400-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="a8400-140">يمكن لواجهة برمجة التطبيقات (API) في الوقت الحقيقي أن تستوعب البيانات من موصل Power Platform مخصص، والموصل [Dynamics 365 Customer Insights](/connectors/customerinsights/)، دون الحاجة إلى كتابة أي تعليمات برمجية ونشرها.</span><span class="sxs-lookup"><span data-stu-id="a8400-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="a8400-141">يمكن للموصل أن يقوم بالإجراءات الخاصة بالوقت الحقيقي نفسها كواجهة برمجة التطبيقات (API).</span><span class="sxs-lookup"><span data-stu-id="a8400-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="a8400-142">تحتاج إلى ترخيص صالح للموصلات المتميزة.</span><span class="sxs-lookup"><span data-stu-id="a8400-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="a8400-143">للحصول على مزيد من المعلومات، راجع الأسئلة المتداولة حول ترخيص [Power Apps و Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="a8400-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="a8400-144">Power Platform [Power Apps و/أو Power Automate](/connectors/)</span><span class="sxs-lookup"><span data-stu-id="a8400-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="a8400-145">Azure [Logic Apps](/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="a8400-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="a8400-146">للحصول على تفاصيل حول إنشاء التدفقات، راجع وثائق [Power Automate ](/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="a8400-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="a8400-147">الاتصال مباشرة مع واجهة برمجة التطبيقات في الوقت الحقيقي</span><span class="sxs-lookup"><span data-stu-id="a8400-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="a8400-148">يمكنك استخدام قدرات الوقت الحقيقي من خلال إنشاء مسار خاص بك والاتصال مباشرةً بواجهة برمجة التطبيقات (API) في الوقت الحقيقي.</span><span class="sxs-lookup"><span data-stu-id="a8400-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="a8400-149">يمكنك نشر نشاط بتنسيق نظام المصدر أو بتنسيق UnifiedActivity‬.</span><span class="sxs-lookup"><span data-stu-id="a8400-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="a8400-150">احصل على التنسيق عن طريق إجراء مكالمة واجهة برمجة تطبيقات إلى/api/instances/ {instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="a8400-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="a8400-151">يمكن العثور على تفاصيل واجهة برمجه التطبيقات هذه، بما في ذلك المعلمات والاستجابات في القسم **EntityData** على [مرجع Customer Insights API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="a8400-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="a8400-152">لمزيد من المعلومات، راجع [التعامل مع Customer Insights API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="a8400-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="a8400-153">فهم استخدام الوقت الحقيقي مع قياس تتبع الاستخدام</span><span class="sxs-lookup"><span data-stu-id="a8400-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="a8400-154">يمكنك الحصول على نظرة عامة على حجم الطلبات لواجهة برمجة التطبيقات في الوقت الحقيقي ومعلومات حول المشكلات التي قد يواجهها النظام.</span><span class="sxs-lookup"><span data-stu-id="a8400-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="a8400-155">يمكنك الوصول إلى [بيانات تتبع الاستخدام في الوقت الحقيقي](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="a8400-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]