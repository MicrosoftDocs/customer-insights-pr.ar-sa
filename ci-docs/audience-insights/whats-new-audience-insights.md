---
title: الميزات الجديدة والقادمة
description: معلومات حول الميزات والتحسينات وإصلاحات الأخطاء الجديدة.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 9183c8af4fb9f9f08ac63d8d0cd37c6868bba310
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270416"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a><span data-ttu-id="06aae-103">ما الجديد في قدرة رؤى الجمهور في Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="06aae-103">What's new in the audience insights capability of Dynamics 365 Customer Insights</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="06aae-104">يسرنا الإعلان عن آخر التحديثات لدينا!</span><span class="sxs-lookup"><span data-stu-id="06aae-104">We're excited to announce our newest updates!</span></span> <span data-ttu-id="06aae-105">تلخص هذه المقالة ميزات المعاينة العامة وتحسينات التوفر العام وتحديثات الميزات.</span><span class="sxs-lookup"><span data-stu-id="06aae-105">This article summarizes public preview features, general availability enhancements, and feature updates.</span></span> <span data-ttu-id="06aae-106">للاطلاع على خطط الميزات على المدى الطويل، يمكنك إلقاء نظرة على خطط إصدار [Dynamics 365 وPower Platform](https://docs.microsoft.com/dynamics365/release-plans/).</span><span class="sxs-lookup"><span data-stu-id="06aae-106">To see the long-term feature plans, take a look at the [Dynamics 365 and Power Platform release plans](https://docs.microsoft.com/dynamics365/release-plans/).</span></span>

<span data-ttu-id="06aae-107">يمكنك أيضًا مشاهدة الفيديو التالي لمعرفة المزيد حول القدرات المخطط لها في آخر ستة أشهر.</span><span class="sxs-lookup"><span data-stu-id="06aae-107">You can also watch the following video to learn more about the capabilities planned for the last six months.</span></span>

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

<span data-ttu-id="06aae-108">نقوم بطرح التحديثات على أساس كل منطقة على حدة.</span><span class="sxs-lookup"><span data-stu-id="06aae-108">We roll out updates on a region-by-region basis.</span></span> <span data-ttu-id="06aae-109">وبالتالي، فقد ترى مناطق هذه الميزات قبل مناطق أخرى.</span><span class="sxs-lookup"><span data-stu-id="06aae-109">So certain regions might see features before others.</span></span> <span data-ttu-id="06aae-110">لن تحتاج إلى اتخاذ أي اجراء وسنقوم بتحديث التطبيق بشكل تلقائي من دون حدوث أي توقف، ما لم يتم تحديد عكس ذلك.</span><span class="sxs-lookup"><span data-stu-id="06aae-110">Unless specified differently, you don't need to take any action and we'll update the app automatically with no downtime.</span></span>

> [!TIP]
> <span data-ttu-id="06aae-111">لإرسال طلبات الميزات واقتراحات حول المنتجات والتصويت عليها، انتقل إلى [مدخل أفكار تطبيق Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).</span><span class="sxs-lookup"><span data-stu-id="06aae-111">To submit and vote on feature requests and product suggestions, go to the [Dynamics 365 Application Ideas portal](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).</span></span>

## <a name="january-2021-updates"></a><span data-ttu-id="06aae-112">تحديثات يناير 2021</span><span class="sxs-lookup"><span data-stu-id="06aae-112">January 2021 updates</span></span>

<span data-ttu-id="06aae-113">تشتمل التحديثات في يناير 2021 على العديد من الميزات وترقيات الأداء وإصلاحات الأخطاء.</span><span class="sxs-lookup"><span data-stu-id="06aae-113">The updates in January 2021 include several features, performance upgrades, and bug fixes.</span></span>

#### <a name="extensibility"></a><span data-ttu-id="06aae-114">إمكانية التوسعة</span><span class="sxs-lookup"><span data-stu-id="06aae-114">Extensibility</span></span>

- <span data-ttu-id="06aae-115">**وظائف موسعة وأداء محسن لتصدير SFTP** يمكنك الآن تصدير جميع كيانات الإخراج من Customer Insights إلى مضيف SFTP.</span><span class="sxs-lookup"><span data-stu-id="06aae-115">**Extended functionality and enhanced performance for SFTP export** You can now export all output entities from Customer Insights to an SFTP host.</span></span> <span data-ttu-id="06aae-116">في السابق، اقتصر التصدير على كيانات الشرائح.</span><span class="sxs-lookup"><span data-stu-id="06aae-116">Previously, export was limited to segment entities.</span></span> <span data-ttu-id="06aae-117">بالإضافة إلى ذلك، يتيح أداء تصدير SFTP المزيد من حجم البيانات في وقت أقل، بحسب أداء مضيف SFTP.</span><span class="sxs-lookup"><span data-stu-id="06aae-117">Additionally, the performance of the SFTP export allows more data volume in less time, depending on the performance of your SFTP host.</span></span>    
  <span data-ttu-id="06aae-118">لمزيد من المعلومات، راجع [موصل SFTP (إصدار أولي)](export-sftp.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-118">For more information, see [Connector for SFTP (preview)](export-sftp.md).</span></span>  

#### <a name="segments"></a><span data-ttu-id="06aae-119">الشرائح </span><span class="sxs-lookup"><span data-stu-id="06aae-119">Segments</span></span>

- <span data-ttu-id="06aae-120">**الشرائح المقترحة المشغلة بواسطة التعلم الآلي‬ لتحسين المقاييس** هناك طريقة جديدة لاكتشاف الشرائح وإنشائها.</span><span class="sxs-lookup"><span data-stu-id="06aae-120">**Machine learning powered suggested segments to improve metrics** There's a new way do discover and create segments.</span></span> <span data-ttu-id="06aae-121">يستخدم النظام نموذج الذكاء الاصطناعي لاقتراح شرائح يمكنها المساعدة على تحسين مؤشر الأداء الأساسي (مقياس) الذي تقوم بتعقبه بالفعل.</span><span class="sxs-lookup"><span data-stu-id="06aae-121">The system uses an AI model to suggest segments that can help improve a KPI (measure) you are already tracking.</span></span> <span data-ttu-id="06aae-122">نحن نعرض مدى تأثير السمات التي تحددها على مقياس أو سمة أساسية أخرى.</span><span class="sxs-lookup"><span data-stu-id="06aae-122">We show the extent of influence of attributes that you select on a measure or another primary attribute.</span></span> <span data-ttu-id="06aae-123">تساعد هذه المعلومات في العثور على الشرائح المحتملة التي يمكنها تقديم الفرص.</span><span class="sxs-lookup"><span data-stu-id="06aae-123">This information helps finding potential segments that present opportunities.</span></span>    
  <span data-ttu-id="06aae-124">لمزيد من المعلومات، راجع [‏‫الشرائح المقترحة‬ (إصدار أولي)](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-124">For more information, see [Suggested segments (preview)](suggested-segments.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="06aae-125">توحيد البيانات</span><span class="sxs-lookup"><span data-stu-id="06aae-125">Data unification</span></span>

- <span data-ttu-id="06aae-126">**تجربة تطابق محسنة** في منطقة توحيد البيانات، تم تحديث تجربة التطابق.</span><span class="sxs-lookup"><span data-stu-id="06aae-126">**Enhanced match experience** In the data unification area, the match experience was updated.</span></span> <span data-ttu-id="06aae-127">إنها تتيح لك تكوين قواعد المطابقة وعرضها، بما في ذلك الإحصائيات المفصلة لتقديم شرح معمق حول كيفية عمل التطابق.</span><span class="sxs-lookup"><span data-stu-id="06aae-127">It lets you configure and view the match rules, including detailed stats to further explain how matching works.</span></span> <span data-ttu-id="06aae-128">توجد خيارات لتعطيل قاعدة تطابق بحيث لا تعود نشطة مع الاحتفاظ التكوين وقواعد تطابق السحب والإفلات والمزيد.</span><span class="sxs-lookup"><span data-stu-id="06aae-128">There are options to disable a match rule so it's no longer active while retaining the configuration, drag and drop match rules, and more.</span></span>
  <span data-ttu-id="06aae-129">لمزيد من المعلومات، راجع [مطابقة الكيانات](match-entities.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-129">For more information, see [Match entities](match-entities.md).</span></span>

- <span data-ttu-id="06aae-130">**يتوفر إخراج إلغاء التكرار من عملية التطابق ككيان** تتم الآن كتابة إخراج عملية إلغاء التكرار من عملية المطابقة في كيان منفصل لإجراء المزيد من التحليلات.</span><span class="sxs-lookup"><span data-stu-id="06aae-130">**Deduplication output from the match process is available as an entity** Deduplication process output from the match process is now written into a separate entity for further analysis.</span></span> <span data-ttu-id="06aae-131">يتكوّن هذه الكيان من الحقول المستخدمة في عملية إلغاء التكرر وسجل الفائز والسجلات المناظرة البديلة التي يتم دمجها مع سجل الفائز.</span><span class="sxs-lookup"><span data-stu-id="06aae-131">This entity consists of the fields used in the deduplication process and the winner record and the corresponding alternate records that get merged with the winner record.</span></span>
  <span data-ttu-id="06aae-132">لمزيد من المعلومات، راجع [إخراج إلغاء تكرار ككيان](match-entities.md#deduplication-output-as-an-entity).</span><span class="sxs-lookup"><span data-stu-id="06aae-132">For more information, see [Deduplication output as an entity](match-entities.md#deduplication-output-as-an-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="06aae-133">إدارة النظام</span><span class="sxs-lookup"><span data-stu-id="06aae-133">System administration</span></span>

- <span data-ttu-id="06aae-134">**مشاركة البيانات بسلاسة مع Microsoft Dataverse** يمكنك الآن مشاركة إخراج Customer Insights مع تطبيقات Microsoft Dataverse باستخدام Data Lake المُدار في Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="06aae-134">**Seamlessly share data to Microsoft Dataverse** You can now share Customer Insights output with Microsoft Dataverse applications using the Microsoft Dataverse Managed Data Lake.</span></span> <span data-ttu-id="06aae-135">عندما تقوم بإقران بيئة Dataverse مع Customer Insights، يمكنك الحصول على خيار تمكين مشاركة البيانات.</span><span class="sxs-lookup"><span data-stu-id="06aae-135">Once you associate a Dataverse environment with Customer Insights, you get the option to enable data sharing.</span></span>
  <span data-ttu-id="06aae-136">لمزيد من المعلومات، راجع [إدارة البيئات](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-136">For more information, see [Manage environments](manage-environments.md).</span></span>


## <a name="december-2020-updates"></a><span data-ttu-id="06aae-137">تحديثات ديسمبر 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-137">December 2020 updates</span></span>

<span data-ttu-id="06aae-138">تشتمل التحديثات في ديسمبر 2020 العديد من الميزات وترقيات الأداء وإصلاحات الأخطاء.</span><span class="sxs-lookup"><span data-stu-id="06aae-138">The updates in December 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-december-2020"></a><span data-ttu-id="06aae-139">الميزات الجديدة والمحدثة في شهر ديسمبر 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-139">New and updated features in December 2020</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="06aae-140">إثراء البيانات</span><span class="sxs-lookup"><span data-stu-id="06aae-140">Data enrichment</span></span>

- <span data-ttu-id="06aae-141">**عمليات إثراء محسنة لتقارب العلامات التجارية والاهتمامات**</span><span class="sxs-lookup"><span data-stu-id="06aae-141">**Improved Brand and Interest affinity enrichments**</span></span>
  
  <span data-ttu-id="06aae-142">لقد قمنا بتبسيط درجات التقارب لتسهيل فهمها واستخدامها.</span><span class="sxs-lookup"><span data-stu-id="06aae-142">We simplified our affinity scores to make them easier to understand and use.</span></span> <span data-ttu-id="06aae-143">يمكنك الآن التعرف على العملاء بسرعة استنادًا إلى مدى تقاربهم مع علامة تجارية محددة أو اهتمام معين.</span><span class="sxs-lookup"><span data-stu-id="06aae-143">You can now quickly identify customers based on how much affinity they have for a given brand or interest.</span></span>

  <span data-ttu-id="06aae-144">بالإضافة إلى ذلك، أضفنا خيارات تكوين جديدة للتحكم بشكل أفضل في الطريقة التي ترغب في إثراء ملفات تعريف العملاء بها.</span><span class="sxs-lookup"><span data-stu-id="06aae-144">Additionally, we have added new configuration options to better control how you want your customer profiles to be enriched.</span></span> 

  <span data-ttu-id="06aae-145">لمزيد من المعلومات، راجع [إثراء ملفات تعريف العملاء باستخدام صلات الاهتمامات والعلامات التجارية](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-145">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

- <span data-ttu-id="06aae-146">**التحكم في اختيار ملفات التعريف التي ترغب في إثرائها**</span><span class="sxs-lookup"><span data-stu-id="06aae-146">**Control which profiles to enrich**</span></span>

  <span data-ttu-id="06aae-147">يمكنك الآن إثراء مجموعة فرعية فقط من ملفات تعريف العملاء باستخدام خيار تحديد كيان شريحة بدلاً من كيان العميل الافتراضي.</span><span class="sxs-lookup"><span data-stu-id="06aae-147">You can now enrich only a subset of your customer profiles with the option to select a segment entity instead of the default customer entity.</span></span> <span data-ttu-id="06aae-148">أنشئ شريحة باستخدام ملفات تعريف العملاء التي ترغب في إثرائها، وحددها في تكوين الإثراء لمجموعة بيانات العميل.</span><span class="sxs-lookup"><span data-stu-id="06aae-148">Create a segment with the customer profiles you would like to enrich and select it in the enrichment configuration for your customer data set.</span></span>
  <span data-ttu-id="06aae-149">هذه الميزة متوفرة حاليًا فقط لعمليات الإثراء التي توفرها Experian and HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="06aae-149">This feature is currently available only for enrichments provided by Experian and HERE Technologies.</span></span> <span data-ttu-id="06aae-150">سنعمل على تمكين هذه الإمكانية لمزيد من عمليات الإثراء في وقت قريب.</span><span class="sxs-lookup"><span data-stu-id="06aae-150">We will be enabling this capability to more enrichments soon.</span></span>

  <span data-ttu-id="06aae-151">لمزيد من المعلومات، راجع [إثراء ملفات تعريف العملاء بواسطة بيانات سكانية من Experian](enrichment-experian.md) أو [إثراء ملفات تعريف العملاء بواسطة HERE Technologies](enrichment-here.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-151">For more information, see [Enrich customer profiles with demographics from Experian](enrichment-experian.md) or [Enrichment of customer profiles with HERE Technologies](enrichment-here.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="06aae-152">إمكانية التوسعة</span><span class="sxs-lookup"><span data-stu-id="06aae-152">Extensibility</span></span>

- <span data-ttu-id="06aae-153">**تنشيط الشرائح عبر Autopilot‎**</span><span class="sxs-lookup"><span data-stu-id="06aae-153">**Activate your segments through Autopilot**</span></span>

  <span data-ttu-id="06aae-154">يمكنك تصدير الشرائح إلى Autopilot‎ واستخدامها لأغراض التسويق.</span><span class="sxs-lookup"><span data-stu-id="06aae-154">Export segments to Autopilot and use them for marketing purposes.</span></span> <span data-ttu-id="06aae-155">لمزيد من المعلومات، راجع [موصل Autopilot (إصدار أولي)](export-autopilot.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-155">For more information, see [Connector for Autopilot (preview)](export-autopilot.md).</span></span>

- <span data-ttu-id="06aae-156">**تنشيط الشرائح عبر SendGrid‎‎**</span><span class="sxs-lookup"><span data-stu-id="06aae-156">**Activate your segments through SendGrid**</span></span>

  <span data-ttu-id="06aae-157">يمكنك تصدير الشرائح إلى SendGrid‎ واستخدامها لأغراض التسويق.</span><span class="sxs-lookup"><span data-stu-id="06aae-157">Export segments to SendGrid and use them for marketing purposes.</span></span> <span data-ttu-id="06aae-158">لمزيد من المعلومات، راجع [موصل SendGrid‎](export-sendgrid.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-158">For more information, see [Connector for SendGrid](export-sendgrid.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="06aae-159">إدارة النظام</span><span class="sxs-lookup"><span data-stu-id="06aae-159">System administration</span></span>

- <span data-ttu-id="06aae-160">**تجربة إدارة البيئة المحدثة**</span><span class="sxs-lookup"><span data-stu-id="06aae-160">**Updated environment management experience**</span></span>
  
  <span data-ttu-id="06aae-161">يمكنك الآن إنشاء البيئات وتحريرها وحذفها وإعادة تعيينها مباشرة من منتقي البيئة في رأس التطبيق.</span><span class="sxs-lookup"><span data-stu-id="06aae-161">You can now create, edit, delete, and reset environments directly from the environment picker in the app header.</span></span> 
  
  <span data-ttu-id="06aae-162">بالإضافة إلى ذلك، سيتم تثبيت البيئة التي تستخدمها في الجزء العلوي من لوحة البيئة بحيث لن تحتاج إلى البحث عنها بعد الآن.</span><span class="sxs-lookup"><span data-stu-id="06aae-162">Additionally, the environment you are using will be pinned at the top of the environment panel so you don't need to search for it anymore.</span></span>

  <span data-ttu-id="06aae-163">لمزيد من المعلومات، راجع [إدارة البيئات](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-163">For more information, see [Manage environments](manage-environments.md).</span></span>

## <a name="november-2020-updates"></a><span data-ttu-id="06aae-164">تحديثات نوفمبر 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-164">November 2020 updates</span></span>

<span data-ttu-id="06aae-165">تشتمل التحديثات في نوفمبر 2020 العديد من الميزات وترقيات الأداء وإصلاحات الأخطاء.</span><span class="sxs-lookup"><span data-stu-id="06aae-165">The updates in November 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-november-2020"></a><span data-ttu-id="06aae-166">الميزات الجديدة والمحدثة في شهر نوفمبر 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-166">New and updated features in November 2020</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="06aae-167">إثراء البيانات</span><span class="sxs-lookup"><span data-stu-id="06aae-167">Data enrichment</span></span>

- <span data-ttu-id="06aae-168">**إحضار بياناتك الإثراء الخاصة بك عبر الاستيراد المخصص لبروتوكول نقل الملفات الآمن (SFTP)‬**</span><span class="sxs-lookup"><span data-stu-id="06aae-168">**Bring your own enrichment data via Secure File Transfer Protocol (SFTP) custom import**</span></span>
  
  <span data-ttu-id="06aae-169">يتيح لك الاستيراد المخصص لبروتوكول نقل الملفات الآمن (SFTP)‬ استيراد بيانات الإثراء من دون المرور عبر عملية توحيد البيانات.</span><span class="sxs-lookup"><span data-stu-id="06aae-169">SFTP custom import lets you import enrichment data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="06aae-170">اعرف المزيد حول الاستيراد المخصص لبروتوكول نقل الملفات الآمن (SFTP)‬.</span><span class="sxs-lookup"><span data-stu-id="06aae-170">Learn more about SFTP custom import.</span></span>

  <span data-ttu-id="06aae-171">لمزيد من المعلومات، راجع [إثراء ملفات تعريف العملاء بواسطة البيانات المخصصة (معاينة)](enrichment-SFTP-custom-import.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-171">For more information, see [Enrich customer profiles with custom data (preview)](enrichment-SFTP-custom-import.md).</span></span>
 
- <span data-ttu-id="06aae-172">**إثراء بيانات العملاء بواسطة بيانات الموقع من HERE Technologies**</span><span class="sxs-lookup"><span data-stu-id="06aae-172">**Enrich your customer data with location data from HERE Technologies**</span></span>

  <span data-ttu-id="06aae-173">باستخدام خدمات إثراء البيانات في HERE Technologies، يمكنك تكوين فهم أكثر دفة لموقع العملاء مع تسوية العناوين واستخراج خط الطول وخط العرض والمزيد.</span><span class="sxs-lookup"><span data-stu-id="06aae-173">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span> <span data-ttu-id="06aae-174">اعرف المزيد حول الإثراء باستخدام HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="06aae-174">Learn more about enriching with HERE Technologies.</span></span>

  <span data-ttu-id="06aae-175">لمزيد من المعلومات، راجع [إثراء ملفات تعريف العملاء بواسطة HERE Technologies](enrichment-here.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-175">For more information, see [Enrichment of customer profiles with HERE Technologies](enrichment-here.md).</span></span>

#### <a name="data-unification"></a><span data-ttu-id="06aae-176">توحيد البيانات</span><span class="sxs-lookup"><span data-stu-id="06aae-176">Data unification</span></span>

- <span data-ttu-id="06aae-177">**مرنة لتمكين تعريف البيانات على كيانات وحقول محددة من حساب التخزين**</span><span class="sxs-lookup"><span data-stu-id="06aae-177">**Flexibility to enable data profiling on selected entities and fields from your storage account**</span></span>

  <span data-ttu-id="06aae-178">يمكنك الإشارة إلى كيانات البيانات والحقول من مجلد نموذج البيانات العامة في حساب Azure Data Lake Storage المطلوب لتمكين تعريف البيانات كجزء من عمليه استيعاب البيانات.</span><span class="sxs-lookup"><span data-stu-id="06aae-178">You can indicate which data entities and fields from a Common Data Model folder in your Azure Data Lake storage account you want to enable data profiling as part of the data ingestion process.</span></span>

  <span data-ttu-id="06aae-179">لمزيد من المعلومات، راجع [الاتصال بمجلد نموذج البيانات العامة](connect-common-data-model.md#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="06aae-179">For more information, see [Connect to a Common Data Model folder](connect-common-data-model.md#connect-to-a-common-data-model-folder).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="06aae-180">إمكانية التوسعة</span><span class="sxs-lookup"><span data-stu-id="06aae-180">Extensibility</span></span>

- <span data-ttu-id="06aae-181">**تنشيط الشرائح عبر Google Ads**</span><span class="sxs-lookup"><span data-stu-id="06aae-181">**Activate your segments through Google Ads**</span></span>

  <span data-ttu-id="06aae-182">يمكنك تصدير الشرائح من قوائم جمهور Google Ads واستخدام هذه القوائم للإعلان على Google Search وGoogle Display Network وYouTubeوGmail.</span><span class="sxs-lookup"><span data-stu-id="06aae-182">Export segments from to Google Ads audience lists and use these lists to advertise on Google Search, Google Display Network, YouTube, and Gmail.</span></span> <span data-ttu-id="06aae-183">اعرف المزيد حول تنشيط الشرائح عبر Google Ads.</span><span class="sxs-lookup"><span data-stu-id="06aae-183">Learn more about activating your segments through Google Ads.</span></span>

  <span data-ttu-id="06aae-184">لمزيد من المعلومات، راجع [موصل Google Ads](export-google-ads.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-184">For more information, see [Connector for Google Ads](export-google-ads.md).</span></span>

- <span data-ttu-id="06aae-185">**تنشيط الشرائح عبر Marketo**</span><span class="sxs-lookup"><span data-stu-id="06aae-185">**Activate your segments through Marketo**</span></span>

  <span data-ttu-id="06aae-186">يمكنك تصدير الشرائح إلى شرائح جمهور Marketo واستخدم شرائح الجمهور هذه لأتمتة التسويق.</span><span class="sxs-lookup"><span data-stu-id="06aae-186">Export segments to Marketo audiences and use these audiences for marketing automation.</span></span> <span data-ttu-id="06aae-187">اعرف المزيد حول تنشيط الشرائح عبر Marketo.</span><span class="sxs-lookup"><span data-stu-id="06aae-187">Learn more about activating your segments through Marketo.</span></span> 

  <span data-ttu-id="06aae-188">لمزيد من المعلومات، راجع [موصل Marketo](export-marketo.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-188">For more information, see [Connector for Marketo](export-marketo.md).</span></span>

- <span data-ttu-id="06aae-189">**تنشيط الشرائح عبر DotDigital**</span><span class="sxs-lookup"><span data-stu-id="06aae-189">**Activate your segments through DotDigital**</span></span>

  <span data-ttu-id="06aae-190">يمكنك تصدير الشرائح واستخدامها لأغراض التسويق.</span><span class="sxs-lookup"><span data-stu-id="06aae-190">Export segments to DotDigital and use them for marketing purposes.</span></span> <span data-ttu-id="06aae-191">اعرف المزيد حول تنشيط الشرائح عبر DotDigital.</span><span class="sxs-lookup"><span data-stu-id="06aae-191">Learn more about activating your segments through DotDigital.</span></span> 

  <span data-ttu-id="06aae-192">لمزيد من المعلومات، راجع [موصل DotDigital](export-dotdigital.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-192">For more information, see [Connector for DotDigital](export-dotdigital.md).</span></span>

#### <a name="predictions"></a><span data-ttu-id="06aae-193">التنبؤات</span><span class="sxs-lookup"><span data-stu-id="06aae-193">Predictions</span></span>

- <span data-ttu-id="06aae-194">**التنبؤ بخسارة المعاملة**</span><span class="sxs-lookup"><span data-stu-id="06aae-194">**Predict transactional churn**</span></span>

  <span data-ttu-id="06aae-195">تمكّنك ميزة التنبؤ بخسارة المعاملة، من دون مساعدة عالم بيانات، من التنبؤ باحتمال توقف العميل عن شراء المنتجات أو الخدمات.</span><span class="sxs-lookup"><span data-stu-id="06aae-195">The transaction churn prediction feature enables you, without the help of a data scientist, to predict the likelihood of a customer to stop purchasing products or services.</span></span>  <span data-ttu-id="06aae-196">باستخدام نقاط التنبؤ، يمكنك دمج معلومات أخرى خاصة بالعملاء، مثل قيمة العميل، لإنشاء شرائح عملاء تبدو مخاطر خسارتهم عالية‬ أو عملاء ذي قيمة عالية.</span><span class="sxs-lookup"><span data-stu-id="06aae-196">Using the prediction score, you can combine other information about your customers, like customer value, to create segments of high churn risk or high value customers.</span></span> <span data-ttu-id="06aae-197">استخدم هذه الشريحة لاستهداف العملاء مباشرةً عبر الأنشطة التسويقية ودعم العملاء وسيناريوهات أخرى لتقليل خطر خسارة العملاء.</span><span class="sxs-lookup"><span data-stu-id="06aae-197">Use this segment to directly target customers through marketing activities, customer support, and other scenarios to reduce churn risk.</span></span>
 
  <span data-ttu-id="06aae-198">كوّن تعريف الخسارة كإطار قائم على الوقت خاص بأعمالك، وحدد الحالات التي يتم فيها اعتبار على أنك ستخسر العملاء.</span><span class="sxs-lookup"><span data-stu-id="06aae-198">Configure the definition of churn as a time-based window specific to your business and define when customers are considered churned.</span></span> <span data-ttu-id="06aae-199">على سبيل المثال، قد يعتبر متجر بقالة أنه خسر أحد العملاء إذا لم يقم هذا العميل بشراء أي شيء خلال الثلاثين (30) يومًا الماضية.</span><span class="sxs-lookup"><span data-stu-id="06aae-199">For example, a grocery store may want to consider a customer churned if they have not purchased anything in the past 30 days.</span></span>
 
  <span data-ttu-id="06aae-200">بينما تتابع إنشاء التنبؤ، سنقوم بإرشادك حول البيانات المطلوبة، وسنسمح لك بتعيين بيانات حول العمل إلى الحقول المطلوبة لتوقع التنبؤ لعملائك.</span><span class="sxs-lookup"><span data-stu-id="06aae-200">As you continue creating the prediction, we'll guide you what data is needed, and enable you to map data about your business to fields required to predict churn for your customers.</span></span> <span data-ttu-id="06aae-201">يمكنك أيضًا تعيين جدول لإعادة تدريب النموذج بناء على معلومات جديدة في النظام للتكيف مع ظروف العمل المتغيرة.</span><span class="sxs-lookup"><span data-stu-id="06aae-201">You can also set a schedule to retrain the model based on new information in your system to adapt to changing business circumstances.</span></span>
 
  <span data-ttu-id="06aae-202">للحصول على مزيد من المعلومات، راجع [التنبؤ بخسارة المعاملة (معاينة)](predict-transactional-churn.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-202">For more information, see [Transactional churn prediction (preview)](predict-transactional-churn.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="06aae-203">إدارة النظام</span><span class="sxs-lookup"><span data-stu-id="06aae-203">System administration</span></span>

- <span data-ttu-id="06aae-204">**إعادة تعيين البيئة**</span><span class="sxs-lookup"><span data-stu-id="06aae-204">**Reset environment**</span></span>

  <span data-ttu-id="06aae-205">أعد تعيين كل شيء في بيئة من مثيل محدد للبدء من جديد.</span><span class="sxs-lookup"><span data-stu-id="06aae-205">Reset everything in an environment of a selected instance to start fresh.</span></span>

  <span data-ttu-id="06aae-206">لمزيد من المعلومات، راجع [إعادة تعيين بيئة جديدة](manage-environments.md#reset-an-existing-environment).</span><span class="sxs-lookup"><span data-stu-id="06aae-206">For more information, see [Reset an existing environment](manage-environments.md#reset-an-existing-environment).</span></span>


- <span data-ttu-id="06aae-207">**الاتصال بحساب Azure Data Lake Storage باستخدام كيان خدمة**</span><span class="sxs-lookup"><span data-stu-id="06aae-207">**Connect to your Azure Data Lake storage account using a service principal**</span></span>

  <span data-ttu-id="06aae-208">اكتب بيانات الإخراج إلى حساب التخزين واقرأها منه باستخدام كيان خدمة Azure.</span><span class="sxs-lookup"><span data-stu-id="06aae-208">Write data output to and read data from your storage account using an Azure service principal.</span></span> <span data-ttu-id="06aae-209">بإمكان اتصالات حساب التخزين الموجودة مواصلة استخدام مفتاح الحساب.</span><span class="sxs-lookup"><span data-stu-id="06aae-209">Existing storage account connections can continue to use the account key.</span></span> <span data-ttu-id="06aae-210">كما تقدم خيار ترقية لاستخدام كيان الخدمة من الآن فصاعدًا.</span><span class="sxs-lookup"><span data-stu-id="06aae-210">They also offer an upgrade option to use the service principal moving forward.</span></span> <span data-ttu-id="06aae-211">ستعتمد الاتصالات الجديدة على أسلوب مصادقة كيان الخدمة لحساب التخزين الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="06aae-211">New connections will be based on the service principal authentication method for your storage account.</span></span>

  <span data-ttu-id="06aae-212">لمزيد من المعلومات، راجع [الاتصال بحساب Azure Data Lake Storage Gen2 بواسطة كيان خدمة Azure لرؤى الجمهور](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-212">For more information, see [Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights](connect-service-principal.md).</span></span>

## <a name="october-2020-updates"></a><span data-ttu-id="06aae-213">تحديثات أكتوبر 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-213">October 2020 updates</span></span>

<span data-ttu-id="06aae-214">تشتمل التحديثات في أكتوبر 2020 العديد من الميزات وترقيات الأداء وإصلاحات الأخطاء.</span><span class="sxs-lookup"><span data-stu-id="06aae-214">The updates in October 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-october-2020"></a><span data-ttu-id="06aae-215">الميزات الجديدة والمحدثة في شهر أكتوبر 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-215">New and updated features in October 2020</span></span>

#### <a name="extensibility"></a><span data-ttu-id="06aae-216">إمكانية التوسعة</span><span class="sxs-lookup"><span data-stu-id="06aae-216">Extensibility</span></span>

- <span data-ttu-id="06aae-217">**التصدير إلى Mailchimp**</span><span class="sxs-lookup"><span data-stu-id="06aae-217">**Export to Mailchimp**</span></span>

<span data-ttu-id="06aae-218">يمكنك تصدير الشرائح إلى قوائم شرائح جمهور موجودة في Mailchimp لتوفير تجربة بريد إلكتروني مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="06aae-218">Export segments to existing audience lists in Mailchimp to provide a personalized email experience for your customers.</span></span>

<span data-ttu-id="06aae-219">لمزيد من المعلومات، راجع [موصل Mailchimp](export-mailchimp.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-219">For more information, see [Connector for Mailchimp](export-mailchimp.md).</span></span>

#### <a name="data-enrichment"></a><span data-ttu-id="06aae-220">إثراء البيانات</span><span class="sxs-lookup"><span data-stu-id="06aae-220">Data enrichment</span></span>

- <span data-ttu-id="06aae-221">**إلغاء تكرار السجلات المصدر في كيان مطابقة**</span><span class="sxs-lookup"><span data-stu-id="06aae-221">**Deduplicate the source records in a Match entity**</span></span>

<span data-ttu-id="06aae-222">حدد قواعد إلغاء التكرار على الكيانات المستخدمة في عملية المطابقة لتحديد السجلات المكررة.</span><span class="sxs-lookup"><span data-stu-id="06aae-222">Specify deduplication rules on entities used in the match process to identify duplicate records.</span></span> <span data-ttu-id="06aae-223">ادمجها في سجل واحد واربط جميع السجلات المصدر بهذا السجل المدمج.</span><span class="sxs-lookup"><span data-stu-id="06aae-223">Merge them into one record and link all the source records to this merged record.</span></span> <span data-ttu-id="06aae-224">سيتم استخدام هذا السجل الملغى تكراره في عملية المطابقة عبر الكيانات.</span><span class="sxs-lookup"><span data-stu-id="06aae-224">This deduplicated record will then be used in the cross-entity matching process.</span></span>

<span data-ttu-id="06aae-225">لمزيد من المعلومات، راجع [تعريف إلغاء تكرار على كيان المطابقة](match-entities.md#define-deduplication-on-a-match-entity).</span><span class="sxs-lookup"><span data-stu-id="06aae-225">For more information, see [Define deduplication on a match entity](match-entities.md#define-deduplication-on-a-match-entity).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="06aae-226">إدارة النظام</span><span class="sxs-lookup"><span data-stu-id="06aae-226">System administration</span></span>

- <span data-ttu-id="06aae-227">**التزامن‬: خيار تحديث جديد في الدمج**</span><span class="sxs-lookup"><span data-stu-id="06aae-227">**Orchestration: New refresh option in Merge**</span></span>

<span data-ttu-id="06aae-228">حتى اليوم، عند تشغيل عملية الدمج، يقوم النظام بتنفيذ كافة عمليات ‏‫انتقال البيانات من الخادم‬‬ التي تعتمد على الدمج والعمليات اللاحقة.</span><span class="sxs-lookup"><span data-stu-id="06aae-228">Until today, when you run the merge process, the system ran all the downstream processes that depend on merge and subsequent processes.</span></span> <span data-ttu-id="06aae-229">يمكنك الآن التحقق من إخراج عملية الدمج (كيان العميل الموحد) قبل استخدامها في معالجة انتقال البيانات من الخادم مثل الشرائح أو المقاييس.</span><span class="sxs-lookup"><span data-stu-id="06aae-229">You can now verify the output of the merge process (the unified customer entity) before using it in downstream processing like segments or measures.</span></span>
<span data-ttu-id="06aae-230">في صفحة الدمج، يمكنك الآن اختيار تشغيل خطوة الدمج فقط وتشغيل هذه العملية فقط.</span><span class="sxs-lookup"><span data-stu-id="06aae-230">On the merge page, you can now choose to run only the merge step and run only this process.</span></span> <span data-ttu-id="06aae-231">لتحديث كافة عمليات انتقال البيانات من الخادم، يمكنك اختيار تشغيل الدمج وعمليات انتقال البيانات من الخادم.</span><span class="sxs-lookup"><span data-stu-id="06aae-231">To refresh all the downstream processes too, you can choose run merge and downstream processes.</span></span> 

## <a name="september-2020-updates"></a><span data-ttu-id="06aae-232">تحديثات سبتمبر 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-232">September 2020 updates</span></span>

<span data-ttu-id="06aae-233">تشتمل التحديثات في سبتمبر 2020 على العديد من الميزات وترقيات الأداء وإصلاحات الأخطاء.</span><span class="sxs-lookup"><span data-stu-id="06aae-233">The updates in September 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-september-2020"></a><span data-ttu-id="06aae-234">الميزات الجديدة والمحدثة في سبتمبر 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-234">New and updated features in September 2020</span></span>

#### <a name="activities"></a><span data-ttu-id="06aae-235">الأنشطة</span><span class="sxs-lookup"><span data-stu-id="06aae-235">Activities</span></span>

- <span data-ttu-id="06aae-236">**التنبؤ الذكي بدلالات السمات**</span><span class="sxs-lookup"><span data-stu-id="06aae-236">**Intelligent prediction of attribute semantics**</span></span>

<span data-ttu-id="06aae-237">تتنبأ هذه الميزة الجديدة بالأنواع الدلالية لسمات الإدخال التي يتم تمريرها إلى عملية توحيد البيانات.</span><span class="sxs-lookup"><span data-stu-id="06aae-237">This new feature predicts the semantic types of input attributes that are passed on to the data unification process.</span></span> <span data-ttu-id="06aae-238">تستخدم نماذج التعلم الآلي التي تعمل على تحسين الدقة وتوفير الوقت.</span><span class="sxs-lookup"><span data-stu-id="06aae-238">It uses machine learning models that improve accuracy and save time.</span></span>

#### <a name="enrichments"></a><span data-ttu-id="06aae-239">عمليات الإثراء</span><span class="sxs-lookup"><span data-stu-id="06aae-239">Enrichments</span></span>

- <span data-ttu-id="06aae-240">**إثراء الخصائص السكانية من Experian**</span><span class="sxs-lookup"><span data-stu-id="06aae-240">**Demographics enrichment from Experian**</span></span>

<span data-ttu-id="06aae-241">إثراء الخصائص السكانية من Experian متاح الآن في المعاينة.</span><span class="sxs-lookup"><span data-stu-id="06aae-241">The demographics enrichment from Experian is now available in preview.</span></span> <span data-ttu-id="06aae-242">إن Experian هي شركة عالمية رائدة في تقديم تقارير ائتمان المستهلك والأعمال وخدمات التسويق.</span><span class="sxs-lookup"><span data-stu-id="06aae-242">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="06aae-243">باستخدام [خدمات إثراء البيانات من Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage)، يمكنك بناء فهم أعمق لعملائك من خلال إثراء ملفات تعريف العملاء بالبيانات السكانية مثل حجم الأسرة والدخل وغير ذلك.</span><span class="sxs-lookup"><span data-stu-id="06aae-243">With [Experian’s data enrichment services](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

<span data-ttu-id="06aae-244">لاستخدام هذه الميزة، يجب أن يكون لديك اشتراك نشط في Experian.</span><span class="sxs-lookup"><span data-stu-id="06aae-244">To use this feature, you must have an active Experian subscription.</span></span>

<span data-ttu-id="06aae-245">لمزيد من المعلومات، راجع [إثراء ملفات تعريف العملاء بالخصائص السكانية من Experian](enrichment-experian.md)</span><span class="sxs-lookup"><span data-stu-id="06aae-245">For more information, see [Enrich customer profiles with demographics from Experian](enrichment-experian.md)</span></span>


#### <a name="system-administration"></a><span data-ttu-id="06aae-246">إدارة النظام</span><span class="sxs-lookup"><span data-stu-id="06aae-246">System administration</span></span>

- <span data-ttu-id="06aae-247">**جزء تفاصيل المهمة**</span><span class="sxs-lookup"><span data-stu-id="06aae-247">**Task details pane**</span></span>

<span data-ttu-id="06aae-248">يتيح لك جزء تفاصيل المهمة عرض تفاصيل حول المهام التي يعمل عليها النظام.</span><span class="sxs-lookup"><span data-stu-id="06aae-248">The task details pane enables you to see details about tasks that the system runs.</span></span> <span data-ttu-id="06aae-249">انها طريقه سهله لتحديد المشكلات المتعلقة بالتكوين والعثور علي حلول.</span><span class="sxs-lookup"><span data-stu-id="06aae-249">It's a handy way to identify issues with the configuration and find solutions.</span></span>
<span data-ttu-id="06aae-250">قم بمراجعه رسائل الخطا التي تعرف علي كيفيه مواجهه المشكلات المحتملة.</span><span class="sxs-lookup"><span data-stu-id="06aae-250">Review the error messages see how you address potential issues.</span></span>
 
- <span data-ttu-id="06aae-251">**معالجة المعلومات المضافة إلى المزيد من الصفحات**</span><span class="sxs-lookup"><span data-stu-id="06aae-251">**Processing information added to more pages**</span></span>

<span data-ttu-id="06aae-252">يقوم هذا التحسين باضافه معلومات حول حاله الكيانات في صفحة **الكيانات** و **العملاء**.</span><span class="sxs-lookup"><span data-stu-id="06aae-252">This improvement adds information about the status of your entities on the **Entities** and **Customers** page.</span></span>
 
<span data-ttu-id="06aae-253">بالاضافه إلى ذلك ، يمكنك العثور علي تفاصيل حول تقدم العمليات ، بالاضافه إلى تفاصيل المهمة في هذه الصفحات.</span><span class="sxs-lookup"><span data-stu-id="06aae-253">Additionally, you can find details about the progress of processes, along with the task details, on both of these pages.</span></span>

- <span data-ttu-id="06aae-254">**تحسينات على صفحة حالة النظام**</span><span class="sxs-lookup"><span data-stu-id="06aae-254">**Improvements to system status page**</span></span>

<span data-ttu-id="06aae-255">لقد قمنا بتحسين بنية جدول تفاصيل الحالة على **النظام** > **الحالة** عند مراجعة تقارير البيانات.</span><span class="sxs-lookup"><span data-stu-id="06aae-255">We improved the structure of the status details table on **System** > **Status** when reviewing data exports.</span></span>
 
<span data-ttu-id="06aae-256">بالإضافة إلى ذلك، أصبح عمود **التفاصيل** الآن أكثر تفصيلاً وقابلية للتنفيذ.</span><span class="sxs-lookup"><span data-stu-id="06aae-256">Additionally, errors in the **Details** column are now more detailed and actionable.</span></span> 
 
- <span data-ttu-id="06aae-257">**الإلغاء يعيد المهمة إلى حالتها السابقة**</span><span class="sxs-lookup"><span data-stu-id="06aae-257">**Cancel reverts job back to previous state**</span></span>

<span data-ttu-id="06aae-258">عندما تقوم بإلغاء مهمة ، على سبيل المثال ، في عملية المطابقة ، فإنها ستعود إلى حالتها الأخيرة.</span><span class="sxs-lookup"><span data-stu-id="06aae-258">When you cancel a task, for example, in the match process, it will revert back to its latest state.</span></span> <span data-ttu-id="06aae-259">على سبيل المثال ، إذا اكتملت عملية "المطابقة" أمس وقمت بإلغائها اليوم ، فسوف تعود إلى حالة الأمس الناجحة.</span><span class="sxs-lookup"><span data-stu-id="06aae-259">For example, if the Match process completed yesterday and you cancel it today, it will revert to yesterday's successful state.</span></span>


## <a name="august-2020-updates"></a><span data-ttu-id="06aae-260">تحديثات أغسطس 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-260">August 2020 updates</span></span>

<span data-ttu-id="06aae-261">تشتمل التحديثات في أغسطس 2020 على العديد من الميزات وترقيات الأداء وإصلاحات الأخطاء.</span><span class="sxs-lookup"><span data-stu-id="06aae-261">The updates in August 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-august-2020"></a><span data-ttu-id="06aae-262">الميزات الجديدة والمحدثة في أغسطس 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-262">New and updated features in August 2020</span></span>

#### <a name="data-unification"></a><span data-ttu-id="06aae-263">توحيد البيانات</span><span class="sxs-lookup"><span data-stu-id="06aae-263">Data unification</span></span>

- <span data-ttu-id="06aae-264">**تجربة محسنة لمرحلة الخريطة أثناء توحيد البيانات**</span><span class="sxs-lookup"><span data-stu-id="06aae-264">**Improved experience for the map stage during data unification**</span></span>

  <span data-ttu-id="06aae-265">تتيح لك تجربة مرحلة الخريطة في عملية توحيد البيانات تحديد الكيانات والسمات وتعريف الدلالات بطريقة أكثر سلاسة.</span><span class="sxs-lookup"><span data-stu-id="06aae-265">The experience to the map stage in the data unification process lets you select entities, attributes, and define semantics in a more seamless way.</span></span>

  <span data-ttu-id="06aae-266">تشمل التغييرات:</span><span class="sxs-lookup"><span data-stu-id="06aae-266">The changes include:</span></span>
  
  - <span data-ttu-id="06aae-267">مطلوب تفاعلات أقل لإضافة الكيانات والحقول</span><span class="sxs-lookup"><span data-stu-id="06aae-267">fewer interactions required to add entities and fields</span></span>
  - <span data-ttu-id="06aae-268">تحسين قدرات البحث على صفحة الخريطة</span><span class="sxs-lookup"><span data-stu-id="06aae-268">improved search capabilities on the map page</span></span>
  - <span data-ttu-id="06aae-269">تحديد مرئي وسهل لنوع المجال المقترح</span><span class="sxs-lookup"><span data-stu-id="06aae-269">visual and easy identification of the suggested field type</span></span>

#### <a name="enrichment"></a><span data-ttu-id="06aae-270">الإثراء</span><span class="sxs-lookup"><span data-stu-id="06aae-270">Enrichment</span></span>

- <span data-ttu-id="06aae-271">**إثراء تقارب الاهتمامات متوفر في مزيد من الأسواق**</span><span class="sxs-lookup"><span data-stu-id="06aae-271">**Interest affinities enrichment available in more markets**</span></span>

  <span data-ttu-id="06aae-272">إننا نقوم بتوسيع نطاق توافر إثراء تقارب الاهتمامات بما يتجاوز الولايات المتحدة إلى خمس أسواق أخرى وهي: كندا وأستراليا والمملكة المتحدة وفرنسا وألمانيا.</span><span class="sxs-lookup"><span data-stu-id="06aae-272">We're extending the availability of the interest affinities enrichment beyond the United States to five other markets: Canada, Australia, United Kingdom, France, and Germany.</span></span> <span data-ttu-id="06aae-273">ومن خلال هذا التوسع، يمكنك إثراء بيانات العميل بالمزيد من الاهتمامات المطبقة على هذه الأسواق.</span><span class="sxs-lookup"><span data-stu-id="06aae-273">With this extension, you can enrich your customer data with more interests applicable to these markets.</span></span> <span data-ttu-id="06aae-274">كما سنعمل أيضًا على تحسين ملفات تعريف العملاء الموجودة في هذه الأسواق باستخدام بيانات الملكية المحلية من Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="06aae-274">We'll also enrich your customer profiles that are located in these markets by using local proprietary data from Microsoft Graph.</span></span>
  <span data-ttu-id="06aae-275">لمزيد من المعلومات، راجع [إثراء ملفات تعريف العملاء باستخدام صلات الاهتمامات والعلامات التجارية](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="06aae-275">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md)</span></span>


## <a name="july-2020-updates"></a><span data-ttu-id="06aae-276">تحديثات يوليو 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-276">July 2020 updates</span></span>

<span data-ttu-id="06aae-277">تشتمل التحديثات في يوليو 2020 على العديد من الميزات وترقيات الأداء وإصلاحات الأخطاء.</span><span class="sxs-lookup"><span data-stu-id="06aae-277">The updates in July 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-july-2020"></a><span data-ttu-id="06aae-278">الميزات الجديدة والمحدثة في يوليو 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-278">New and updated features in July 2020</span></span>

#### <a name="extensibility"></a><span data-ttu-id="06aae-279">إمكانية التوسعة</span><span class="sxs-lookup"><span data-stu-id="06aae-279">Extensibility</span></span>

- <span data-ttu-id="06aae-280">**تشغيل Power Automate لعملية الدمج المكتملة**</span><span class="sxs-lookup"><span data-stu-id="06aae-280">**Power Automate trigger for completed unification process**</span></span>

  <span data-ttu-id="06aae-281">لقد قمنا بتوسيع مشغلاتنا لـ Power Automate وإتاحة إنشاء إعلام أو إجراء عند اكتمال تحديث عملية التوحيد (التعيين، المطابقة، الدمج).</span><span class="sxs-lookup"><span data-stu-id="06aae-281">We have extended our triggers for Power Automate and let you create a notification or action when a refresh of the unification process (map, match, merge) is completed.</span></span>    
  <span data-ttu-id="06aae-282">لمزيد من المعلومات، راجع [موصل Power Automate](export-power-automate.md)</span><span class="sxs-lookup"><span data-stu-id="06aae-282">For more information, see [Power Automate connector](export-power-automate.md)</span></span>

#### <a name="enrichment"></a><span data-ttu-id="06aae-283">الإثراء</span><span class="sxs-lookup"><span data-stu-id="06aae-283">Enrichment</span></span>

- <span data-ttu-id="06aae-284">**إثراء تقارب العلامات التجارية متوفر في مزيد من الأسواق**</span><span class="sxs-lookup"><span data-stu-id="06aae-284">**Brand affinities enrichment available in more markets**</span></span>

  <span data-ttu-id="06aae-285">إننا نقوم بتوسيع نطاق توافر إثراء تقارب العلامات التجارية بما يتجاوز الولايات المتحدة إلى خمس أسواق أخرى وهي: كندا وأستراليا والمملكة المتحدة وفرنسا وألمانيا.</span><span class="sxs-lookup"><span data-stu-id="06aae-285">We're extending the availability of the brand affinities enrichment beyond the United States to five other markets: Canada, Australia, United Kingdom, France, and Germany.</span></span> <span data-ttu-id="06aae-286">وبهذا التمديد، يمكنك إثراء بيانات العملاء في العلامات التجارية المحلية في هذه الأسواق.</span><span class="sxs-lookup"><span data-stu-id="06aae-286">With this extension, you can enrich your customer data with local brands in these markets.</span></span> <span data-ttu-id="06aae-287">كما سنعمل أيضًا على تحسين ملفات تعريف العملاء الموجودة في هذه الأسواق باستخدام بيانات الملكية المحلية من Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="06aae-287">We'll also enrich your customer profiles that are located in these markets by using local proprietary data from Microsoft Graph.</span></span>
  <span data-ttu-id="06aae-288">لمزيد من المعلومات، راجع [إثراء ملفات تعريف العملاء باستخدام صلات الاهتمامات والعلامات التجارية](enrichment-microsoft-graph.md)</span><span class="sxs-lookup"><span data-stu-id="06aae-288">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md)</span></span>

## <a name="june-2020-updates"></a><span data-ttu-id="06aae-289">تحديثات يونيه 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-289">June 2020 updates</span></span>

<span data-ttu-id="06aae-290">تشتمل التحديثات في يونيو 2020 على العديد من الميزات وترقيات الأداء وإصلاحات الأخطاء.</span><span class="sxs-lookup"><span data-stu-id="06aae-290">The updates in June 2020 include several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-june-2020"></a><span data-ttu-id="06aae-291">الميزات الجديدة والمحدثة في يونيه 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-291">New and updated features in June 2020</span></span>

#### <a name="enrichment"></a><span data-ttu-id="06aae-292">الإثراء</span><span class="sxs-lookup"><span data-stu-id="06aae-292">Enrichment</span></span>

- <span data-ttu-id="06aae-293">**الإثراء باستخدام بيانات الشركة من Leadspace**</span><span class="sxs-lookup"><span data-stu-id="06aae-293">**Enrichment with company data from Leadspace**</span></span>
  
  <span data-ttu-id="06aae-294">حدد الحقول الموجودة في ملفات تعريف العميل الموحدة المستخدمة للبحث عن بيانات الشركة ذات الصلة من Leadspace.</span><span class="sxs-lookup"><span data-stu-id="06aae-294">Define fields in unified customer profiles that are used to look up related company data from Leadspace.</span></span> <span data-ttu-id="06aae-295">وبعد تشغيل عملية الإثراء، يتم إثراء ملفات تعريف B2B بواسطة المزيد من السمات بما في ذلك حجم الشركة والموقع والمجال وغيرها.</span><span class="sxs-lookup"><span data-stu-id="06aae-295">After running the enrichment process, B2B profiles are enriched with more attributes including company size, location, industry, and more.</span></span>    
  <span data-ttu-id="06aae-296">ويتيح لك هذا التعاون تحسين جودة البيانات عند الإدخال من خدمات الجهات الخارجية.</span><span class="sxs-lookup"><span data-stu-id="06aae-296">This collaboration allows you to improve the quality of your data with input from third-party services.</span></span> <span data-ttu-id="06aae-297">ولاستخدام هذا الإثراء، ستحتاج إلى ترخيص من Leadspace للوصول إلى بيانات الشركة للتجارة بين الشركات.</span><span class="sxs-lookup"><span data-stu-id="06aae-297">To use this enrichment, you'll need a license from Leadspace to access its B2B company data.</span></span> <span data-ttu-id="06aae-298">سيقوم النظام باستخدام هذا الترخيص للمحافظة على إثراء البيانات بشكل متواصل.</span><span class="sxs-lookup"><span data-stu-id="06aae-298">The system will use that license to keep your data enriched continuously.</span></span>    
  <span data-ttu-id="06aae-299">لمزيد من المعلومات، راجع [إثراء ملفات تعريف الشركة باستخدام Leadspace](enrichment-leadspace.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-299">For more information, see [Enrichment of company profiles with Leadspace](enrichment-leadspace.md).</span></span>

- <span data-ttu-id="06aae-300">**صفحة مركز الإثراء**</span><span class="sxs-lookup"><span data-stu-id="06aae-300">**Enrichment hub page**</span></span>

  <span data-ttu-id="06aae-301">يتم تكوين كافة عمليات إثراء البيانات من موفري عمليات إثراء الطرف الأول والجهة الخارجية في نفس المكان.</span><span class="sxs-lookup"><span data-stu-id="06aae-301">All available data enrichment from first- and third-party enrichment providers gets configured in the same place.</span></span> <span data-ttu-id="06aae-302">وتكوين إثراء البيانات هو تجربة سلسة تتم إدارتها من مكان عام.</span><span class="sxs-lookup"><span data-stu-id="06aae-302">Configuring data enrichment is a seamless experience that is managed from a common place.</span></span>    
  <span data-ttu-id="06aae-303">لمزيد من المعلومات، راجع [إثراء ملفات تعريف العملاء](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-303">For more information, see [Enrichment for customer profiles](enrichment-hub.md).</span></span>

- <span data-ttu-id="06aae-304">**فصل إثراء صلة الاهتمام والعلامة التجارية**</span><span class="sxs-lookup"><span data-stu-id="06aae-304">**Separate brand and interest affinity enrichment**</span></span>

  <span data-ttu-id="06aae-305">تتوفر صلات الاهتمام والعلامات التجارية الآن كعمليتي إثراء منفصلتين.</span><span class="sxs-lookup"><span data-stu-id="06aae-305">The brands and interests affinities are now available as two independent enrichments.</span></span> <span data-ttu-id="06aae-306">يمنحك الإثراء المنفصل المرونة لتكوينه وإدارتها بشكل فردي، وذلك وفقًا لمتطلبات أو احتياجات العمل.</span><span class="sxs-lookup"><span data-stu-id="06aae-306">Separated enrichments give you the flexibility to configure and manage them individually, depending on your business requirements or needs.</span></span>    
  <span data-ttu-id="06aae-307">لمزيد من المعلومات، راجع [إثراء ملفات تعريف العملاء باستخدام صلات الاهتمامات والعلامات التجارية](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-307">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="06aae-308">إمكانية التوسعة</span><span class="sxs-lookup"><span data-stu-id="06aae-308">Extensibility</span></span>

- <span data-ttu-id="06aae-309">**عناوين URL القابلة للنقر للأنشطة الموحدة في الوظيفة الإضافية لبطاقة عميل Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="06aae-309">**Clickable URLs for unified activities on the Dynamics 365 Customer Card Add-in**</span></span>

  <span data-ttu-id="06aae-310">تعرض الآن الأنشطة الموحدة في الوظيفة الإضافية لبطاقة العميل عناوين URL قابلة للنقر إذا تم تعريف عناوين URL هذه أثناء تكوين الأنشطة.</span><span class="sxs-lookup"><span data-stu-id="06aae-310">The unified activities in the Customer Card Add-in are now showing clickable URLs if such URLs have been defined during the configuration of activities.</span></span>    
  <span data-ttu-id="06aae-311">لمزيد من المعلومات، راجع [الوظيفة الإضافية بطاقة العميل](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-311">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="06aae-312">**تتوفر صلات العلامات التجارية والاهتمامات في الوظيفة الإضافية لبطاقة عميل Dynamics 365**</span><span class="sxs-lookup"><span data-stu-id="06aae-312">**Brand and interest affinities available on the Dynamics 365 Customer Card Add-in**</span></span>

  <span data-ttu-id="06aae-313">يتيح لك عنصر التحكم الجديد في الوظيفة الإضافية لبطاقة عميل Dynamics 365 عرض عمليات إثراء العلامات التجارية والاهتمامات في جهات الاتصال الموجودة في تطبيقات مشاركة العميل في Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="06aae-313">A new control on the Dynamics 365 Customer Card Add-in lets you show brand and interest enrichments on your contacts in customer engagement apps in Dynamics 365.</span></span>    
  <span data-ttu-id="06aae-314">لمزيد من المعلومات، راجع [الوظيفة الإضافية بطاقة العميل](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-314">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="06aae-315">**المزيد من مشغلات Power Automate**</span><span class="sxs-lookup"><span data-stu-id="06aae-315">**More Power Automate triggers**</span></span>

  <span data-ttu-id="06aae-316">لقد تم تمديد مشغلات Power Automate وإضافة المشغلات التالية:</span><span class="sxs-lookup"><span data-stu-id="06aae-316">We have extended our triggers for Power Automate and added the following triggers:</span></span>
  - <span data-ttu-id="06aae-317">الحصول على إعلام أو تنفيذ إجراء عند اكتمال التحديث الكامل التلقائي (مصادر البيانات، التوحيد، الشرائح، المقاييس، عمليات التصدير)</span><span class="sxs-lookup"><span data-stu-id="06aae-317">Get a notification or perform an action when an automated full refresh (data sources, unification, segments, measures, exports) completes</span></span>
  - <span data-ttu-id="06aae-318">حدد حدًا لمقياس الأعمال.</span><span class="sxs-lookup"><span data-stu-id="06aae-318">Define a threshold for a business measure.</span></span> <span data-ttu-id="06aae-319">على سبيل المثال، يمكنك إنشاء اعلام يتم إرساله عند تمرير الحد المحدد.</span><span class="sxs-lookup"><span data-stu-id="06aae-319">For example, you can create a notification that gets sent when the defined threshold is passed.</span></span> <span data-ttu-id="06aae-320">وبالإضافة إلى ذلك، يحضر المشغل المعلومات التي تتيح لك إمكانية إنشاء مهام سير عمل أكثر تعقيدًا في Power Automate.</span><span class="sxs-lookup"><span data-stu-id="06aae-320">Additionally, the trigger brings information that allows you to build more complex workflows in Power Automate.</span></span>    
  <span data-ttu-id="06aae-321">لمزيد من المعلومات، راجع [موصل Power Automate](export-power-automate.md)</span><span class="sxs-lookup"><span data-stu-id="06aae-321">For more information, see [Power Automate connector](export-power-automate.md)</span></span>

- <span data-ttu-id="06aae-322">**تصدير إلى مدير إعلانات Facebook**</span><span class="sxs-lookup"><span data-stu-id="06aae-322">**Export to Facebook Ads Manager**</span></span>
  
  <span data-ttu-id="06aae-323">تتيح لك هذه القدرة تصدير الشرائح إلى Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="06aae-323">This capability lets you export segments to Facebook Ads Manager.</span></span> <span data-ttu-id="06aae-324">يتم تصدير الشرائح كشرائح جمهور مخصصة لاستخدام ملفات تعريف العميل الموحد في الحملات التسويقية والإعلانات في Facebook.</span><span class="sxs-lookup"><span data-stu-id="06aae-324">Segments are exported as custom audiences to use unified customer profiles in Facebook marketing campaigns and ads.</span></span> <span data-ttu-id="06aae-325">كما يمكن أيضًا استخدام الجمهور المخصص لإنشاء حملات على Instagram عبر مدير إعلانات Facebook.</span><span class="sxs-lookup"><span data-stu-id="06aae-325">The custom audiences are also usable to create campaigns on Instagram through Facebook Ads Manager.</span></span>    
  <span data-ttu-id="06aae-326">لمزيد من المعلومات، راجع [موصل مدير إعلانات Facebook](export-facebook.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-326">For more information, see [Connector for Facebook Ads Manager](export-facebook.md).</span></span>

#### <a name="predictions"></a><span data-ttu-id="06aae-327">التنبؤات</span><span class="sxs-lookup"><span data-stu-id="06aae-327">Predictions</span></span>

- <span data-ttu-id="06aae-328">**التنبؤ بخسارة الاشتراك**</span><span class="sxs-lookup"><span data-stu-id="06aae-328">**Subscription churn prediction**</span></span>

  <span data-ttu-id="06aae-329">اتبع تجربة إرشادية لإنشاء تنبؤ بالخسارة في مناطق الاشتراكات مثل الخدمات السحابية وعضوية العميل والقطاعات الأخرى.</span><span class="sxs-lookup"><span data-stu-id="06aae-329">Follow a guided experience to create churn prediction in subscription areas like cloud services, customer membership, and other sectors.</span></span> 

  <span data-ttu-id="06aae-330">تمكنك ميزة التنبؤ بخسارة الاشتراك من التنبؤ باحتمالية توقف أحد العملاء عن استخدام المنتجات أو الخدمات المستندة إلى الاشتراك دون اللجوء إلى عالم بيانات.</span><span class="sxs-lookup"><span data-stu-id="06aae-330">The subscription churn prediction feature enables you to predict the likelihood of a customer stopping the use of subscription-based products or services without engaging a data scientist.</span></span> <span data-ttu-id="06aae-331">وباستخدام نقاط التنبؤ، يمكنك دمج المعلومات الأخرى للعملاء لإنشاء شرائح مخاطر الخسارة المرتفعة.</span><span class="sxs-lookup"><span data-stu-id="06aae-331">Using the prediction score, you can combine other information about your customers to create segments of high churn risk.</span></span> <span data-ttu-id="06aae-332">بمساعدة هذه الشريحة، يمكنك استهداف العملاء مباشرةً عبر التسويق ودعم العملاء وسيناريوهات أخرى لتقليل خطر خسارة عملاء معينين لتحسين الإيرادات وتقليل التكلفة.</span><span class="sxs-lookup"><span data-stu-id="06aae-332">With the help of this segment, you can directly target customers in marketing, customer support, and other scenarios to reduce the risk of churn for specific customers to improve revenue and reduce cost.</span></span>

  <span data-ttu-id="06aae-333">ويمكنك من خلال التجربة تكوين تعريف الخسارة كنافذة خاصة بعملك تستند إلى الوقت.</span><span class="sxs-lookup"><span data-stu-id="06aae-333">Within the experience, you can configure the definition of churn as a time-based window specific to your business.</span></span> <span data-ttu-id="06aae-334">على سبيل المثال، قد تحتاج أعمال بث الفيديو التي تنطوي على عملية اشتراك شهرية إلى مراعاة خسارة العميل بعد 15 يومًا من انتهاء صلاحية اشتراكه.</span><span class="sxs-lookup"><span data-stu-id="06aae-334">For example, a video streaming business that has a monthly subscription process might want to consider a customer to have churned after 15 days after the expiration of their subscription.</span></span>

  <span data-ttu-id="06aae-335">وبمتابعة التنبؤ، سنرشدك من خلال البيانات المطلوبة ونتيح لك إمكانية تعيين بيانات حول العمل إلى الحقول المطلوبة للتنبؤ بخسارة العملاء.</span><span class="sxs-lookup"><span data-stu-id="06aae-335">As you continue through the prediction, we'll guide you through what data is needed, and enable you to map data about your business to fields required to predict churn for your customers.</span></span> <span data-ttu-id="06aae-336">وبتغيير معلومات العمل، يمكنك أيضًا تعيين جدول لإعادة التدرب على المعلومات الجديدة في النظام للتأقلم مع ظروف العمل المتغيرة.</span><span class="sxs-lookup"><span data-stu-id="06aae-336">As business information changes, you can also set a schedule to retrain on new information in your system to adapt to changing business circumstances.</span></span>    
  <span data-ttu-id="06aae-337">لمزيد من المعلومات، راجع [التنبؤ بخسارة الاشتراك (معاينة)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-337">For more information, see [Subscription churn prediction (preview)](predict-subscription-churn.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="06aae-338">الشرائح</span><span class="sxs-lookup"><span data-stu-id="06aae-338">Segments</span></span>

- <span data-ttu-id="06aae-339">**البحث عن العملاء المتشابهين**</span><span class="sxs-lookup"><span data-stu-id="06aae-339">**Find similar customers**</span></span>
  
  <span data-ttu-id="06aae-340">ابحث عن العملاء المتشابهين في قاعدة العملاء باستخدام الذكاء الاصطناعي.</span><span class="sxs-lookup"><span data-stu-id="06aae-340">Find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="06aae-341">يعين نموذج التعلم الآلي ثنائي التصنيف نقاط التشابه إلى العملاء في الشريحة الموسعة.</span><span class="sxs-lookup"><span data-stu-id="06aae-341">A binary classification machine learning model assigns a similarity score to customers in the expanded segment.</span></span> <span data-ttu-id="06aae-342">تستند النقاط إلى تماثل العملاء في الشريحة المصدر.</span><span class="sxs-lookup"><span data-stu-id="06aae-342">The score is based on the similarity to customers in the source segment.</span></span> <span data-ttu-id="06aae-343">وبناءًا على نقاط التشابه، تتم إضافة ملفات تعريف العملاء إلى الشريحة المنشأة حديثًا.</span><span class="sxs-lookup"><span data-stu-id="06aae-343">Depending on the similarity score, customer profiles are added to a newly created segment.</span></span>

  <span data-ttu-id="06aae-344">يُشار إليها في بعض الأحيان باسم نمذجة المماثل في التسويق الرقمي، وتستخدم نموذج الذكاء الاصطناعي للمساعدة في البحث عن عملاء مشابهين لشريحة أخرى من عملائك عن طريق وضع مزيد من السمات في الاعتبار.</span><span class="sxs-lookup"><span data-stu-id="06aae-344">Sometimes referred to as lookalike modeling in digital marketing, it uses an AI model to help find customers who are similar to another segment of your customers by factoring in more attributes.</span></span> <span data-ttu-id="06aae-345">ولا يسمح لك فقط بانتقاء السمات، ولكن يتيح لك أيضًا تحديد الحد الأقصى لعدد العملاء الذين يجب تواجدهم في هذه الشريحة الجديدة.</span><span class="sxs-lookup"><span data-stu-id="06aae-345">It not only allows you to pick the attributes but also allows you to specify the maximum number of customers who should be in this new segment.</span></span> <span data-ttu-id="06aae-346">يعمل نموذج الذكاء الاصطناعي بعد ذلك على حساب نقاط التشابه لكل عميل استنادًا إلى السمات المحددة والعثور على العملاء ذوي أعلى نقاط نشابه في المتوسط.</span><span class="sxs-lookup"><span data-stu-id="06aae-346">The AI model will then compute similarity scores for each customer based on your selected attributes and find customers with the higher average similarity score.</span></span> <span data-ttu-id="06aae-347">ستتضمن الشريحة الناتجة العملاء المشابهين للعميل في الشريحة الأصلية.</span><span class="sxs-lookup"><span data-stu-id="06aae-347">The resulting segment will include customers who look similar to the customer in your original segment.</span></span>    
  <span data-ttu-id="06aae-348">لمزيد من المعلومات، راجع [العملاء المتشابهين](find-similar-customer-segments.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-348">For more information, see [Similar Customers](find-similar-customer-segments.md).</span></span>

- <span data-ttu-id="06aae-349">**الفروق وتداخل الشرائح**</span><span class="sxs-lookup"><span data-stu-id="06aae-349">**Segment overlap and differentiators**</span></span>

  <span data-ttu-id="06aae-350">يتيح لك تداخل الشرائح معرفة عدد وماهية العملاء المشتركين في شريحتين أو أكثر.</span><span class="sxs-lookup"><span data-stu-id="06aae-350">Segment overlap lets you see how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="06aae-351">على سبيل المثال، كيفية تداخل شريحة المنفقين من المستوى العالي مع شريحة العملاء ذوي الرضا العالي، أو كيفية تداخل شريحة خسارة العميل مع شريحة العملاء ذات الرضا المنخفض.</span><span class="sxs-lookup"><span data-stu-id="06aae-351">For example, how a high-spenders segment overlaps with a high-satisfaction customers segment or how a churning customer segment overlaps with a low-satisfaction customers segment.</span></span> <span data-ttu-id="06aae-352">بالإضافة إلى ذلك، يمكنك تحليل كيف يتغير التداخل استنادًا إلى سمة إضافية من اختيارك.</span><span class="sxs-lookup"><span data-stu-id="06aae-352">Additionally, you can analyze how the overlap changes based on an extra attribute of your choice.</span></span>

  <span data-ttu-id="06aae-353">تكشف فروق الشرائح ما يميز شريحة عن باقي العملاء أو شريحة أخرى.</span><span class="sxs-lookup"><span data-stu-id="06aae-353">Segment differentiators reveal what differentiates one segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="06aae-354">كل ما تحتاج إلى فعله هو تحديد شريحة وسيتولى النظام تحديد سمات ملف التعريف ومقاييسه التي تميز الشريحة في شكل قائمة فروق مرتبة، من أقوى فرق إلى أضعف واحد.</span><span class="sxs-lookup"><span data-stu-id="06aae-354">All you need to do is identify a segment and the system will identify profile attributes and measures that distinguish the segment in the form of a ranked list of differentiators—from the strongest differentiator to the weakest.</span></span>    
  <span data-ttu-id="06aae-355">لمزيد من المعلومات، راجع [‏‫نتائج تحليلات الشرائح‬ (معاينة)](segment-insights.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-355">For more information, see [Segment insights (preview)](segment-insights.md).</span></span>

- <span data-ttu-id="06aae-356">**عمر الشريحة**</span><span class="sxs-lookup"><span data-stu-id="06aae-356">**Segment lifetime**</span></span>
  
  <span data-ttu-id="06aae-357">حدد جدولاً لتنشيط شريحة أو إلغاء تنشيطها.</span><span class="sxs-lookup"><span data-stu-id="06aae-357">Define a schedule to activate or deactivate a segment.</span></span>    
  <span data-ttu-id="06aae-358">لمزيد من المعلومات، راجع [إدارة الشرائح الموجودة](segments.md#manage-existing-segments).</span><span class="sxs-lookup"><span data-stu-id="06aae-358">For more information, see [Manage existing segments](segments.md#manage-existing-segments).</span></span>

## <a name="may-2020-updates"></a><span data-ttu-id="06aae-359">تحديثات مايو 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-359">May 2020 updates</span></span>

<span data-ttu-id="06aae-360">تتضمن تحديثات شهر مايو 2020 العديد من الميزات وترقيات الأداء وإصلاحات الأخطاء.</span><span class="sxs-lookup"><span data-stu-id="06aae-360">The updates in May 2020 includes several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-may-2020"></a><span data-ttu-id="06aae-361">الميزات الجديدة والمحدثة في شهر مايو 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-361">New and updated features in May 2020</span></span>

#### <a name="data-ingestion"></a><span data-ttu-id="06aae-362">استيعاب البيانات</span><span class="sxs-lookup"><span data-stu-id="06aae-362">Data ingestion</span></span>

- <span data-ttu-id="06aae-363">**استيعاب البيانات في الوقت الحقيقي: طرق عرض المحفوظات**</span><span class="sxs-lookup"><span data-stu-id="06aae-363">**Real-time data ingestion: history views**</span></span>

  <span data-ttu-id="06aae-364">عند استخدام واجهة برمجة التطبيقات (API) الخاصة بنا لاستيعاب التحديثات في الوقت الحقيقي، يمكنك الاطلاع على 30 يومًا من المحفوظات المجمعة لهذه التحديثات.</span><span class="sxs-lookup"><span data-stu-id="06aae-364">When using our API to ingest real-time updates, you can see up to 30 days of aggregated history for these updates.</span></span> <span data-ttu-id="06aae-365">يمكنك الوصول إلى تجميعات كافة استدعاءات API الناجحة أو الفاشلة بما في ذلك نتائجها والنظام المصدر وبيانات التعريف المفيدة الأخرى.</span><span class="sxs-lookup"><span data-stu-id="06aae-365">You have access to aggregates of all successful or failed API calls including their outcome, source system, and other useful metadata.</span></span>    
  <span data-ttu-id="06aae-366">لمزيد من المعلومات، راجع [استيعاب البيانات في الوقت الحقيقي](real-time-data-ingestion.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-366">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

- <span data-ttu-id="06aae-367">**استيعاب البيانات في الوقت الحقيقي: تحديثات ملفات التعريف‬‏‫**</span><span class="sxs-lookup"><span data-stu-id="06aae-367">**Real-time data ingestion: profile updates**</span></span>

  <span data-ttu-id="06aae-368">يسمح لك هذا التوسع لاستيعاب البيانات في الوقت الحقيقي برؤية التغييرات في حقول ملفات تعريف مستخدمين معينين خلال ثوانٍ.</span><span class="sxs-lookup"><span data-stu-id="06aae-368">This extension of the real-time data ingestion lets you see, within seconds, changes to specific user profile fields.</span></span>    
  <span data-ttu-id="06aae-369">بالإضافة إلى الوظائف في الوقت الحقيقي للأنشطة، يدعم النظام تحديثات زمن الوصول المنخفض لتعريف الحقول.</span><span class="sxs-lookup"><span data-stu-id="06aae-369">In addition to the real-time functionality for activities, the system supports low latency updates to profile fields.</span></span> <span data-ttu-id="06aae-370">يوجد وقت انتهاء صلاحية لتحديثات حقول ملف التعريف في الوقت الحقيقي، وهي ليست بالتالي بديلاً لعمليات التحديث المجدولة.</span><span class="sxs-lookup"><span data-stu-id="06aae-370">Real-time updates for profile fields have an expiration time and are therefore not a replacement for scheduled refreshes.</span></span>    
  <span data-ttu-id="06aae-371">لمزيد من المعلومات، راجع [استيعاب البيانات في الوقت الحقيقي](real-time-data-ingestion.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-371">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="06aae-372">إمكانية التوسعة</span><span class="sxs-lookup"><span data-stu-id="06aae-372">Extensibility</span></span>

- <span data-ttu-id="06aae-373">**تحديث المخطط الزمني والحدود الفاصلة للصفحات في الوظيفة الإضافية "بطاقة العميل"**</span><span class="sxs-lookup"><span data-stu-id="06aae-373">**Updated timeline and pagination on the Customer Card Add-in**</span></span>

  <span data-ttu-id="06aae-374">يتطابق المخطط الزمني لحل الوظيفة الإضافية لبطاقة العميل مع المخطط الزمني للأنشطة.</span><span class="sxs-lookup"><span data-stu-id="06aae-374">The timeline of the Customer Card Add-in solution matches the activity timeline.</span></span> <span data-ttu-id="06aae-375">تم تحسين الحدود الفاصلة للصفحات في المخطط الزمني، مما أدى إلى عرض 50 نشاطًا مرة واحدة.</span><span class="sxs-lookup"><span data-stu-id="06aae-375">The pagination of the timeline improved, showing up to 50 activities at once.</span></span> <span data-ttu-id="06aae-376">كما تسمح بتحميل مزيد من الأنشطة في المخطط الزمني.</span><span class="sxs-lookup"><span data-stu-id="06aae-376">It also allows loading more activities in the timeline.</span></span>    
  <span data-ttu-id="06aae-377">لمزيد من المعلومات، راجع [الوظيفة الإضافية بطاقة العميل](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-377">For more information, see [Customer Card Add-in](customer-card-add-in.md).</span></span>

- <span data-ttu-id="06aae-378">**مشغل Power Automate لتغييرات الشريحة**</span><span class="sxs-lookup"><span data-stu-id="06aae-378">**Power Automate trigger for segment changes**</span></span>

  <span data-ttu-id="06aae-379">تحدد مشغلات Power Automate ما يمكن إنشاء سير مهمة منه.</span><span class="sxs-lookup"><span data-stu-id="06aae-379">Triggers for Power Automate define what you can build a flow from.</span></span> <span data-ttu-id="06aae-380">يتيح لك المشغل المضاف حديثًا تعريف حد لشريحة.</span><span class="sxs-lookup"><span data-stu-id="06aae-380">The newly added trigger lets you define a threshold for a segment.</span></span> <span data-ttu-id="06aae-381">على سبيل المثال، يمكنك إنشاء اعلام يتم إرساله عند تمرير الحد المحدد.</span><span class="sxs-lookup"><span data-stu-id="06aae-381">For example, you can create a notification that gets sent when the defined threshold is passed.</span></span>    
  <span data-ttu-id="06aae-382">لمزيد من المعلومات، راجع [موصل Power Automate](export-power-automate.md)</span><span class="sxs-lookup"><span data-stu-id="06aae-382">For more information, see [Power Automate connector](export-power-automate.md).</span></span>

- <span data-ttu-id="06aae-383">**دعم عدة مستأجرين للنماذج المخصصة**</span><span class="sxs-lookup"><span data-stu-id="06aae-383">**Multitenant support for custom models**</span></span>

  <span data-ttu-id="06aae-384">يمكنك تكوين عمليات سير عمل للنماذج المخصصة باستخدام خدمة ويب لمستأجر آخر لخدمة التعلم الآلي من Azure.</span><span class="sxs-lookup"><span data-stu-id="06aae-384">Configure workflows for custom models with a web service of a different Azure Machine Learning tenant.</span></span> <span data-ttu-id="06aae-385">يمكنك تسجيل الدخول إلى مستأجر التعلم الآلي في Azure عند إنشاء سير عمل جديد للنماذج المخصصة.</span><span class="sxs-lookup"><span data-stu-id="06aae-385">You can sign in to the Azure Machine Learning tenant when creating a new workflow for custom models.</span></span> <span data-ttu-id="06aae-386">تعتبر هذه الإمكانية إضافة إلى القدرة الحالية على التكامل مع خدمة ويب التعلم الآلي من Azure‬ المخصصة الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="06aae-386">This capability is an addition to the existing capability of integrating with your own custom Azure Machine Learning web service.</span></span>    
  <span data-ttu-id="06aae-387">لمزيد من المعلومات، راجع [نماذج التعلم الآلي المخصصة](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-387">For more information, see [Custom machine learning models](custom-models.md).</span></span>

#### <a name="segments"></a><span data-ttu-id="06aae-388">الشرائح</span><span class="sxs-lookup"><span data-stu-id="06aae-388">Segments</span></span>

- <span data-ttu-id="06aae-389">**التنفيذ التلقائي لمسار الكيان**</span><span class="sxs-lookup"><span data-stu-id="06aae-389">**Entity path automation**</span></span>

  <span data-ttu-id="06aae-390">عند إنشاء شريحة، يحتاج المستخدمون إلى تحديد مسار الكيان.</span><span class="sxs-lookup"><span data-stu-id="06aae-390">When creating a segment, users need to define the entity path.</span></span> <span data-ttu-id="06aae-391">تنفذ هذه الإمكانية الخطوة الأولى في التنفيذ التلقائي لتعريف مسار الكيان بحيث يمكنك التركيز على معايير التقسيم التي تريدها.</span><span class="sxs-lookup"><span data-stu-id="06aae-391">This capability takes a first step at automating the entity path definition so you can focus on the segmentation criteria that you have in mind.</span></span>    
  <span data-ttu-id="06aae-392">إذا كان الكيان الذي تريد تقسيم العملاء وفقًا له يرتبط مباشرة بكيان العميل الموحد، فلن تحتاج إلى تحديد مسار الكيان فيما بعد.</span><span class="sxs-lookup"><span data-stu-id="06aae-392">If the entity by which you want to segment your customers is directly related to the unified customer entity, you won't need to define the entity path anymore.</span></span> <span data-ttu-id="06aae-393">ومع ذلك، إذا كان هناك أكثر من مسار كيان محتمل، فلا تزال بحاجة إلى تعريفه يدويًا.</span><span class="sxs-lookup"><span data-stu-id="06aae-393">However, if there is more than one possible entity path, you still need to define it manually.</span></span>

- <span data-ttu-id="06aae-394">**إجراءات على شرائح متعددة**</span><span class="sxs-lookup"><span data-stu-id="06aae-394">**Actions on multiple segments**</span></span>
  
  <span data-ttu-id="06aae-395">بإمكان المستخدمين تحديد عدة شرائح وتنفيذ إجراءات عليها، مثل تحديث الشرائح، بتنفيذ نقرة واحدة.</span><span class="sxs-lookup"><span data-stu-id="06aae-395">Users can select multiple segments and take actions on them, like refreshing the segments, with a single click.</span></span>    

- <span data-ttu-id="06aae-396">**تحديث الشرائح**</span><span class="sxs-lookup"><span data-stu-id="06aae-396">**Refresh segments**</span></span>

  <span data-ttu-id="06aae-397">بإمكان المستخدمين تحديث شريحة واحدة أو فقط الشرائح التي يريدون تحديثها.</span><span class="sxs-lookup"><span data-stu-id="06aae-397">Users can refresh a single segment or select only the segments they want to refresh.</span></span>    

  
- <span data-ttu-id="06aae-398">**تحسينات على الشرائح المركبة**</span><span class="sxs-lookup"><span data-stu-id="06aae-398">**Improvements to compounded segments**</span></span>

  <span data-ttu-id="06aae-399">بإمكان المستخدمين إنشاء شرائح تستند إلى شرائح أخرى وتحريرها وحذفها.</span><span class="sxs-lookup"><span data-stu-id="06aae-399">Users can create, edit, and delete segments that are based on other segments.</span></span> <span data-ttu-id="06aae-400">على سبيل المثال، شريحة مبنية على شريحة أخرى مبنية على شريحة ثالثة.</span><span class="sxs-lookup"><span data-stu-id="06aae-400">For example, a segment constructed on another segment that was constructed on a third segment.</span></span>    

- <span data-ttu-id="06aae-401">**صفحة قائمة الشرائح**</span><span class="sxs-lookup"><span data-stu-id="06aae-401">**Segment list page**</span></span>

  <span data-ttu-id="06aae-402">يستخدم التصميم الجديد لصفحة الشرائح تنسيق قائمة يتيح لك رؤية مزيد من الشرائح مرة واحدة.</span><span class="sxs-lookup"><span data-stu-id="06aae-402">The new design of the segments page uses a list format that lets you see more segments at once.</span></span> <span data-ttu-id="06aae-403">تمت إضافة حقل بحث للعثور على الشرائح بسرعة.</span><span class="sxs-lookup"><span data-stu-id="06aae-403">A search field is added to find segments quickly.</span></span> <span data-ttu-id="06aae-404">بإمكان المستخدمين الآن تطبيق إجراءات مثل التنزيل أو الحذف على شرائح متعددة في وقت واحد.</span><span class="sxs-lookup"><span data-stu-id="06aae-404">Users can now apply actions like downloading or deleting on multiple segments at once.</span></span> <span data-ttu-id="06aae-405">تم تقديم تجربة اتجاه جديدة للتعرف بسرعة على التغييرات المهمة في الشرائح.</span><span class="sxs-lookup"><span data-stu-id="06aae-405">A new trend experience is introduced to quickly identify significant changes on segments.</span></span>    
  <span data-ttu-id="06aae-406">لمزيد من المعلومات، راجع [إنشاء شرائح وإدارتها](segments.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-406">For more information, see [Create and manage segments](segments.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="06aae-407">إدارة النظام</span><span class="sxs-lookup"><span data-stu-id="06aae-407">System administration</span></span>

- <span data-ttu-id="06aae-408">**يتوفر Customer Insights في Microsoft Dynamics 365 Online Government**</span><span class="sxs-lookup"><span data-stu-id="06aae-408">**Customer Insights available in Microsoft Dynamics 365 Online Government**</span></span>

  <span data-ttu-id="06aae-409">مع وجود المزيد من القنوات للتفاعلات، تنتشر بيانات المواطنين عبر مجموعة كبيرة من الأنظمة، مما يؤدي إلى الحصول على بيانات موضوعة في المستودعات وطريقة عرض مجزأة للمعلومات حول تفاعلات المواطنين.</span><span class="sxs-lookup"><span data-stu-id="06aae-409">With more and more channels for interactions, citizen data is scattered across myriad systems, leading to siloed data, and a fragmented view of information about citizen interactions.</span></span> <span data-ttu-id="06aae-410">سيتعذر على الحكومات إجراء عمليات تحديث واسعة النطاق من دون الحصول على طريقة عرض كاملة لتفاعلات كل مواطن عبر القنوات.</span><span class="sxs-lookup"><span data-stu-id="06aae-410">Without a complete view of each citizen's interactions across channels, it's impossible for governments to modernize at scale.</span></span> <span data-ttu-id="06aae-411">تلتزم شركه Microsoft بدعم الاحتياجات التكنولوجية للحكومة تماشيًا مع توقعات المواطنين لتمكين الحصول على تجارب متناسقة ومتجاوبة.</span><span class="sxs-lookup"><span data-stu-id="06aae-411">Microsoft is committed to supporting the technology needs of government to keep up with citizen expectations for consistent and responsive experiences.</span></span>    
  <span data-ttu-id="06aae-412">مع الموجة 1 من الإصدار 2020، سيكون Dynamics 365 Customer Insights متوفرًا لسحابة القطاع الحكومي (GCC)، وهي عبارة عن بيئة مبنية لتلبية احتياجات الامتثال العالية للوكالات الحكومية الأمريكية.</span><span class="sxs-lookup"><span data-stu-id="06aae-412">With 2020 release wave 1, Dynamics 365 Customer Insights will be available for the Government Community Cloud (GCC), an environment built to meet the higher compliance needs of United States government agencies.</span></span> <span data-ttu-id="06aae-413">تكتسب الوكالات طريقة عرض موحدة للمواطنين وتستخدم الذكاء الاصطناعي المضمن لاستخراج المعلومات الدقيقة التي تحسن التفاعلات وتمكّن الموظفين وتدخل تغييرات على المجتمعات، مع تقليل مستوى التعقيدات في تقنية المعلومات وتلبية معايير الامتثال والأمان المعمول بها في الولايات المتحدة.</span><span class="sxs-lookup"><span data-stu-id="06aae-413">Agencies gain a unified view of citizens and use prebuilt AI to derive insights that improve interactions, empower employees, and transform communities, while reducing IT complexity and meeting United States compliance and security standards.</span></span> <span data-ttu-id="06aae-414">يلبي Dynamics 365 Government المتطلبات الملحة لبرنامج إدارة المخاطر والتخويل الفيدرالي (FedRAMP)، مما يسمح للوكالات الفيدرالية الأمريكية بالاستفادة من توفير التكاليف والأمان الصارم لسحابة Microsoft.</span><span class="sxs-lookup"><span data-stu-id="06aae-414">Dynamics 365 Government meets the demanding requirements of the US Federal Risk and Authorization Management Program (FedRAMP), enabling United States federal agencies to benefit from the cost savings and rigorous security of the Microsoft Cloud.</span></span>

## <a name="april-2020-updates"></a><span data-ttu-id="06aae-415">تحديثات أبريل 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-415">April 2020 updates</span></span>

<span data-ttu-id="06aae-416">تتضمن تحديثات شهر أبريل 2020 العديد من الميزات وترقيات الأداء وإصلاحات الأخطاء.</span><span class="sxs-lookup"><span data-stu-id="06aae-416">The updates in April 2020 includes several features, performance upgrades, and bug fixes.</span></span>

### <a name="new-and-updated-features-in-april-2020"></a><span data-ttu-id="06aae-417">الميزات الجديدة والمحدثة في شهر أبريل 2020</span><span class="sxs-lookup"><span data-stu-id="06aae-417">New and updated features in April 2020</span></span>

#### <a name="activities"></a><span data-ttu-id="06aae-418">الأنشطة</span><span class="sxs-lookup"><span data-stu-id="06aae-418">Activities</span></span>

- <span data-ttu-id="06aae-419">**تعيين كيان النشاط إلى نوع نشاط قياسي**</span><span class="sxs-lookup"><span data-stu-id="06aae-419">**Map activity entity to standard activity type**</span></span>
  
  <span data-ttu-id="06aae-420">في الوقت الحالي، يستند تكوين النشاط وتخزينه إلى تصميم ثابت لعرضه في مخطط زمني.</span><span class="sxs-lookup"><span data-stu-id="06aae-420">Activity configuration and storage are currently based on a static design to view them in a timeline.</span></span> <span data-ttu-id="06aae-421">لا يتم حاليًا استخدام المعنى الدلالي للأنشطة التي يمكن أن تنطوي على العديد من حالات الاستخدام في نماذج الذكاء الاصطناعي بشكل كامل.</span><span class="sxs-lookup"><span data-stu-id="06aae-421">The semantic meaning of activities, which has potential for multiple use-cases in AI models, isn't fully used at the moment.</span></span> <span data-ttu-id="06aae-422">نحن نخطط لجعل المخطط الزمني للنشاط أكثر ديناميكية، بناء على نوع النشاط وفهم دلالي أفضل للأنشطة.</span><span class="sxs-lookup"><span data-stu-id="06aae-422">We plan to make the activity timeline more dynamic, based on the activity type and better semantic understanding of the activities.</span></span> <span data-ttu-id="06aae-423">تهدف هذه الميزة إلى تحديد نوع النشاط كما هو محدد في نموذج البيانات العامة لأي نشاط تم استيعابه.</span><span class="sxs-lookup"><span data-stu-id="06aae-423">This feature aims to identify the activity type as defined in Common Data Model for any ingested activity.</span></span>
  <span data-ttu-id="06aae-424">لمزيد من المعلومات، راجع [أنشطة العميل](activities.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-424">For more information, see [Customer activities](activities.md).</span></span>

#### <a name="data-ingestion"></a><span data-ttu-id="06aae-425">استيعاب البيانات</span><span class="sxs-lookup"><span data-stu-id="06aae-425">Data ingestion</span></span>

- <span data-ttu-id="06aae-426">**استيعاب البيانات في الوقت الحقيقي: الأنشطة**</span><span class="sxs-lookup"><span data-stu-id="06aae-426">**Real-time data ingestion: activities**</span></span>
  
  <span data-ttu-id="06aae-427">يوفر استيعاب البيانات في الوقت الحقيقي البيانات لاستهلاكها على الفور، حتى يقوم التحديث المجدول التالي بسحب هذه البيانات من مصدر البيانات.</span><span class="sxs-lookup"><span data-stu-id="06aae-427">Real-time data ingestion provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>    
  <span data-ttu-id="06aae-428">لمزيد من المعلومات، راجع [استيعاب البيانات في الوقت الحقيقي](real-time-data-ingestion.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-428">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>

- <span data-ttu-id="06aae-429">**تحسينات في إعداد البيانات**</span><span class="sxs-lookup"><span data-stu-id="06aae-429">**Improvements to data preparation**</span></span>
  
  <span data-ttu-id="06aae-430">اعرف المزيد حول البيانات المستوعبة‬ في كيان.</span><span class="sxs-lookup"><span data-stu-id="06aae-430">Learn more about the data ingested in an entity.</span></span> <span data-ttu-id="06aae-431">مع ملخص البيانات، يمكنك فهم سمات جودة البيانات التي يمكن أن تساعد في اتخاذ الإجراء المناسب.</span><span class="sxs-lookup"><span data-stu-id="06aae-431">With the data summary, you can understand the data quality characteristics that can help to take appropriate action.</span></span>    
  <span data-ttu-id="06aae-432">لمزيد من المعلومات، راجع [استكشاف بيانات الكيان](entities.md#exploring-a-specific-entitys-data).</span><span class="sxs-lookup"><span data-stu-id="06aae-432">For more information, see [Explore entity data](entities.md#exploring-a-specific-entitys-data).</span></span>

- <span data-ttu-id="06aae-433">**استيعاب البيانات التحليلية من Dynamics 365 مع Common Data Service**</span><span class="sxs-lookup"><span data-stu-id="06aae-433">**Ingest analytical data from Dynamics 365 with Common Data Service**</span></span>
  
  <span data-ttu-id="06aae-434">تتوفر Common Data Service كطريقة لإنشاء مصادر البيانات.</span><span class="sxs-lookup"><span data-stu-id="06aae-434">Common Data Service is available as a way to create data sources.</span></span> <span data-ttu-id="06aae-435">بإمكان عملاء Dynamics 365 الموجودين استيعاب الكيانات التحليلية من Common Data Service إلى Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="06aae-435">Existing Dynamics 365 customers can ingest analytical entities from Common Data Service to Customer Insights.</span></span> <span data-ttu-id="06aae-436">بإمكان مصدر بيانات واحد استخدام مستودع نفسه مُدار من Common Data Service في بيئة Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="06aae-436">A single data source can simultaneously use the same Common Data Service-managed lake in a Customer Insights environment.</span></span>    
  <span data-ttu-id="06aae-437">لمزيد من المعلومات، راجع [الاتصال بالبيانات في مستودع بيانات مدار بواسطة Common Data Service](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-437">For more information, see [Connect to data in a Common Data Service managed data lake](connect-common-data-service-lake.md).</span></span>

#### <a name="extensibility"></a><span data-ttu-id="06aae-438">إمكانية التوسعة</span><span class="sxs-lookup"><span data-stu-id="06aae-438">Extensibility</span></span>

- <span data-ttu-id="06aae-439">**تصدير إلى LiveRamp**</span><span class="sxs-lookup"><span data-stu-id="06aae-439">**Export to LiveRamp**</span></span>

  <span data-ttu-id="06aae-440">قم بتنشيط بياناتك في LiveRamp® للاتصال بأكثر من 500 نظام أساسي عبر الأنظمة البيئية الرقمية والاجتماعية والتلفزيونية.</span><span class="sxs-lookup"><span data-stu-id="06aae-440">Activate your data in LiveRamp® to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="06aae-441">استخدم بياناتك في LiveRamp لاستهداف الحملات وحذفها وخصخصتها.</span><span class="sxs-lookup"><span data-stu-id="06aae-441">Use your data in LiveRamp for targeting, suppressing, and personalizing ad campaigns.</span></span>    
  <span data-ttu-id="06aae-442">لمزيد من المعلومات، راجع [موصل LiveRamp&reg;](export-liveramp.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-442">For more information, see [LiveRamp&reg; connector](export-liveramp.md).</span></span>

- <span data-ttu-id="06aae-443">**الوظيفة الإضافية Customer Insights Teams**</span><span class="sxs-lookup"><span data-stu-id="06aae-443">**Customer Insights Teams Add-in**</span></span>
  
  <span data-ttu-id="06aae-444">يوفر الروبوت إمكانيات البحث لملفات تعريف العملاء الموحدة.</span><span class="sxs-lookup"><span data-stu-id="06aae-444">The bot provides lookup capabilities for unified customer profiles.</span></span> <span data-ttu-id="06aae-445">وسيظهر بطاقة تتضمن 15 حقلاً كحدٍ أقصى من ملف تعريف العميل الناتج.</span><span class="sxs-lookup"><span data-stu-id="06aae-445">It will show a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="06aae-446">تعيد تطابقات متعددة‬ قائمة بالنتائج حيث يمكنك تحديد ملف تعريف.</span><span class="sxs-lookup"><span data-stu-id="06aae-446">Multiple matches return a list of results where you can select a profile.</span></span>    
  <span data-ttu-id="06aae-447">لمزيد من المعلومات، راجع [روبوت Teams لتطبيق Customer Insights](export-teams-bot.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-447">For more information, see [Teams bot for Customer Insights](export-teams-bot.md).</span></span>

#### <a name="measures"></a><span data-ttu-id="06aae-448">القياسات</span><span class="sxs-lookup"><span data-stu-id="06aae-448">Measures</span></span>

- <span data-ttu-id="06aae-449">**صفحة قائمة المقاييس**</span><span class="sxs-lookup"><span data-stu-id="06aae-449">**Measure list page**</span></span>
  
  <span data-ttu-id="06aae-450">تتضمن التحسينات التي تم إدخالها على صفحة قائمة المقاييس دعم الإجراءات على مقياس واحد أو عدة مقاييس في وقت واحد.</span><span class="sxs-lookup"><span data-stu-id="06aae-450">Improvements to the measures page include support for actions on a single measure and on multiple measures at once.</span></span> <span data-ttu-id="06aae-451">علاوةً على ذلك، ستجد حقل بحث للعثور على المقاييس وتعقبها بسرعة.</span><span class="sxs-lookup"><span data-stu-id="06aae-451">Additionally, you'll find a search field to find and track measures quickly.</span></span>    
  <span data-ttu-id="06aae-452">لمزيد من المعلومات، راجع [إنشاء شرائح وإدارتها](segments.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-452">For more information, see [Create and manage segments](segments.md).</span></span>

- <span data-ttu-id="06aae-453">**تحسينات على المقاييس المركبة**</span><span class="sxs-lookup"><span data-stu-id="06aae-453">**Improvements to compounded measures**</span></span>
  
  <span data-ttu-id="06aae-454">بإمكان المستخدمين إنشاء مقاييس تستند إلى مقاييس أخرى وتحريرها وحذفها.</span><span class="sxs-lookup"><span data-stu-id="06aae-454">Users can create, edit, and delete measures that are based on other measures.</span></span> <span data-ttu-id="06aae-455">على سبيل المثال، مقياس مبني على مقياس آخر مبني على مقياس ثالث.</span><span class="sxs-lookup"><span data-stu-id="06aae-455">For example, a measure constructed on another measure that was constructed on a third measure.</span></span>

#### <a name="segments"></a><span data-ttu-id="06aae-456">الشرائح </span><span class="sxs-lookup"><span data-stu-id="06aae-456">Segments</span></span>

- <span data-ttu-id="06aae-457">**عامل تشغيل آخر**</span><span class="sxs-lookup"><span data-stu-id="06aae-457">**Another operator**</span></span>
  
  <span data-ttu-id="06aae-458">يسمح عامل التشغيل In-set بتقسيم العملاء حسب عدة قيم سلاسل محتملة.</span><span class="sxs-lookup"><span data-stu-id="06aae-458">The In-set operator allows segmentation for customers by several possible string values.</span></span> <span data-ttu-id="06aae-459">قبل إضافة عامل التشغيل هذا، يتعين عليك إنشاء شرائح تتضمن عدة شروط OR.</span><span class="sxs-lookup"><span data-stu-id="06aae-459">Before this operator was added, you had to construct such segments with multiple OR conditions.</span></span> <span data-ttu-id="06aae-460">يتيح لك عامل التشغيل In-set القيام بذلك مع شرط واحد.</span><span class="sxs-lookup"><span data-stu-id="06aae-460">The In-set operator lets you do that with a single condition.</span></span>    
  <span data-ttu-id="06aae-461">لمزيد من المعلومات، راجع [إنشاء شرائح وإدارتها](segments.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-461">For more information, see [Create and manage segments](segments.md).</span></span>

#### <a name="system-administration"></a><span data-ttu-id="06aae-462">إدارة النظام</span><span class="sxs-lookup"><span data-stu-id="06aae-462">System administration</span></span>

- <span data-ttu-id="06aae-463">**نسخ إعدادات التكوين إلى بيئة جديدة**</span><span class="sxs-lookup"><span data-stu-id="06aae-463">**Copy configuration settings to a new environment**</span></span>
  
  <span data-ttu-id="06aae-464">انسخ التكوين من بيئة إلى أخرى.</span><span class="sxs-lookup"><span data-stu-id="06aae-464">Copy your configuration from one environment to another.</span></span> <span data-ttu-id="06aae-465">أثناء إنشاء بيئة جديدة، يمكنك تحديد بيئة موجودة تريد نسخ التكوين منها.</span><span class="sxs-lookup"><span data-stu-id="06aae-465">While creating a new environment, you can select an existing environment you want to copy the configuration from.</span></span> <span data-ttu-id="06aae-466">ندعم حاليًا مصادر البيانات وتوحيد البيانات والعلاقات والمقاييس والشرائح لنسخها.</span><span class="sxs-lookup"><span data-stu-id="06aae-466">We currently support data sources, data unification, relationships, measures, and segments to be copied.</span></span> <span data-ttu-id="06aae-467">لا يتم نسخ بيانات اعتماد مصدر البيانات والبيانات الفعلية.</span><span class="sxs-lookup"><span data-stu-id="06aae-467">Data source credentials and actual data aren't copied.</span></span>    
  <span data-ttu-id="06aae-468">لمزيد من المعلومات، راجع [إدارة البيئات](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="06aae-468">For more information, see [Manage environments](manage-environments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]