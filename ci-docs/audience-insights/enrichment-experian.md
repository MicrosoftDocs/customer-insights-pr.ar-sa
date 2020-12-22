---
title: إثراء البيانات بواسطة خدمات إثراء البيانات من طرف ثالث Experian
description: معلومات عامة حول خدمات إثراء البيانات من طرف ثالث Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668780"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="2402c-103">إثراء ملفات تعريف العملاء بالخصائص السكانية من Experian (معاينة)</span><span class="sxs-lookup"><span data-stu-id="2402c-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="2402c-104">إن Experian هي شركة عالمية رائدة في تقديم تقارير ائتمان المستهلك والأعمال وخدمات التسويق.</span><span class="sxs-lookup"><span data-stu-id="2402c-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="2402c-105">باستخدام خدمات إثراء البيانات من Experian ، يمكنك بناء فهم أعمق لعملائك من خلال إثراء ملفات تعريف العملاء بالبيانات السكانية مثل حجم الأسرة والدخل وغير ذلك.</span><span class="sxs-lookup"><span data-stu-id="2402c-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2402c-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="2402c-106">Prerequisites</span></span>

<span data-ttu-id="2402c-107">لتكوين Experian، يجب استيفاء المتطلبات الأساسية التالية:</span><span class="sxs-lookup"><span data-stu-id="2402c-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="2402c-108">أن يكون لديك اشتراك Experian نشط.</span><span class="sxs-lookup"><span data-stu-id="2402c-108">You have an active Experian subscription.</span></span> <span data-ttu-id="2402c-109">للحصول على اشتراك، [اتصل بشركة Experian](https://www.experian.com/marketing-services/contact) مباشرةً.</span><span class="sxs-lookup"><span data-stu-id="2402c-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="2402c-110">[تعرف على المزيد حول إثراء البيانات من Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="2402c-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="2402c-111">لديك معرف المستخدم ومعرف الطرف ورقم الطراز لحساب النقل الآمن (ST) الذي تم تمكينه بواسطة SSH والذي أنشأته Experian لك.</span><span class="sxs-lookup"><span data-stu-id="2402c-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="2402c-112">لديك أذونات [المسؤول](permissions.md#administrator) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="2402c-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="2402c-113">التكوين</span><span class="sxs-lookup"><span data-stu-id="2402c-113">Configuration</span></span>

1. <span data-ttu-id="2402c-114">انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.</span><span class="sxs-lookup"><span data-stu-id="2402c-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="2402c-115">حدد **إثراء البيانات الخاصة بي** على تجانب Experian.</span><span class="sxs-lookup"><span data-stu-id="2402c-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2402c-116">![تجانب Experian](media/experian-tile.png "تجانب Experian")</span><span class="sxs-lookup"><span data-stu-id="2402c-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="2402c-117">حدد **الشروع في العمل** وقم بإدخال معرف المستخدم ومعرف الطرف ورقم النموذج لحساب النقل الأمن من Experian.</span><span class="sxs-lookup"><span data-stu-id="2402c-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="2402c-118">راجع وقدم موافقتك على **خصوصية البيانات والتوافق‬** من خلال تحديد خانة الاختيار **أوافق**.</span><span class="sxs-lookup"><span data-stu-id="2402c-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="2402c-119">قم بتأكيد كافة الإدخالات من خلال تحديد **تطبيق**.</span><span class="sxs-lookup"><span data-stu-id="2402c-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="2402c-120">تعيين الحقول الخاصة بك</span><span class="sxs-lookup"><span data-stu-id="2402c-120">Map your fields</span></span>

1. <span data-ttu-id="2402c-121">حدد **إضافة بيانات** واختر معرفات المفاتيح من **الاسم والعنوان** أو **البريد الإلكتروني** أو **الهاتف** للإرسال إلى Experian لحل الهوية.</span><span class="sxs-lookup"><span data-stu-id="2402c-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="2402c-122">من المحتمل أن تؤدي المزيد من سمات معرف المفاتيح المرسلة إلى Experian إلى معدل تطابق أعلى.</span><span class="sxs-lookup"><span data-stu-id="2402c-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="2402c-123">حدد **التالي** وقم بتعيين السمات المقابلة لها من كيان عميل موحد لحقول معرفات المفاتيح المحددة.</span><span class="sxs-lookup"><span data-stu-id="2402c-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="2402c-124">حدد **إضافة سمة** لتعيين أي سمات إضافية ترغب في إرسالها إلى Experian.</span><span class="sxs-lookup"><span data-stu-id="2402c-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="2402c-125">حدد **حفظ** لإكمال تعيين الحقل.</span><span class="sxs-lookup"><span data-stu-id="2402c-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2402c-126">![تعيين حقل Experian](media/experian-field-mapping.png "تعيين حقل Experian")</span><span class="sxs-lookup"><span data-stu-id="2402c-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2402c-127">نتائج الإثراء</span><span class="sxs-lookup"><span data-stu-id="2402c-127">Enrichment results</span></span>

<span data-ttu-id="2402c-128">لبدء عملية الإثراء، حدد **تشغيل** من شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="2402c-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="2402c-129">يمكنك أيضًا السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من [التحديث المجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2402c-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2402c-130">يعتمد وقت المعالجة على حجم بيانات العميل وعمليات الإثراء التي تم إعدادها لحسابك بواسطة Experian.</span><span class="sxs-lookup"><span data-stu-id="2402c-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="2402c-131">بعد اكتمال عملية الإثراء، يمكنك مراجعة بيانات ملفات تعريف العملاء التي تم إثراؤها حديثًا ضمن **عمليات الإثراء الخاصة بي**.</span><span class="sxs-lookup"><span data-stu-id="2402c-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="2402c-132">بالإضافة إلى ذلك ، ستجد وقت التحديث الأخير وعدد ملفات التعريف التي تم إثراؤها.</span><span class="sxs-lookup"><span data-stu-id="2402c-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="2402c-133">يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.</span><span class="sxs-lookup"><span data-stu-id="2402c-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2402c-134">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="2402c-134">Next steps</span></span>

<span data-ttu-id="2402c-135">قم بالبناء أعلى بيانات العملاء التي تم إثرائها.</span><span class="sxs-lookup"><span data-stu-id="2402c-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2402c-136">أنشئ [الشرائح](segments.md)، و[المقاييس](measures.md)، وقم كذلك [بتصدير البيانات](export-destinations.md) لتقديم تجارب مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="2402c-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2402c-137">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="2402c-137">Data privacy and compliance</span></span>

<span data-ttu-id="2402c-138">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Experian، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="2402c-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2402c-139">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Experian بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="2402c-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2402c-140">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2402c-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2402c-141">بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="2402c-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
