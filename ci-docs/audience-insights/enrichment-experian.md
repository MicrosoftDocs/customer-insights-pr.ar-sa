---
title: إثراء البيانات بواسطة خدمات إثراء البيانات من طرف ثالث Experian
description: معلومات عامة حول خدمات إثراء البيانات من طرف ثالث Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896357"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="1d900-103">إثراء ملفات تعريف العملاء بالخصائص السكانية من Experian (معاينة)</span><span class="sxs-lookup"><span data-stu-id="1d900-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="1d900-104">إن Experian هي شركة عالمية رائدة في تقديم تقارير ائتمان المستهلك والأعمال وخدمات التسويق.</span><span class="sxs-lookup"><span data-stu-id="1d900-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="1d900-105">باستخدام خدمات إثراء البيانات من Experian ، يمكنك بناء فهم أعمق لعملائك من خلال إثراء ملفات تعريف العملاء بالبيانات السكانية مثل حجم الأسرة والدخل وغير ذلك.</span><span class="sxs-lookup"><span data-stu-id="1d900-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1d900-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="1d900-106">Prerequisites</span></span>

<span data-ttu-id="1d900-107">لتكوين Experian، يجب استيفاء المتطلبات الأساسية التالية:</span><span class="sxs-lookup"><span data-stu-id="1d900-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="1d900-108">أن يكون لديك اشتراك Experian نشط.</span><span class="sxs-lookup"><span data-stu-id="1d900-108">You have an active Experian subscription.</span></span> <span data-ttu-id="1d900-109">للحصول على اشتراك، [اتصل بشركة Experian](https://www.experian.com/marketing-services/contact) مباشرةً.</span><span class="sxs-lookup"><span data-stu-id="1d900-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="1d900-110">[تعرف على المزيد حول إثراء البيانات من Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="1d900-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="1d900-111">تم بالفعل تكوين اتصال Experian بواسطة المسؤول *أو* تحصل على أذونات [المسؤول](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="1d900-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="1d900-112">تحتاج أيضًا إلى معرف المستخدم ومعرف الطرف ورقم الطراز لحساب النقل الآمن (ST) الذي تم تمكينه بواسطة SSH والذي أنشأته Experian لك.</span><span class="sxs-lookup"><span data-stu-id="1d900-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="1d900-113">تكوين الإثراء</span><span class="sxs-lookup"><span data-stu-id="1d900-113">Configure the enrichment</span></span>

1. <span data-ttu-id="1d900-114">انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.</span><span class="sxs-lookup"><span data-stu-id="1d900-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="1d900-115">حدد **إثراء البيانات الخاصة بي** على تجانب Experian.</span><span class="sxs-lookup"><span data-stu-id="1d900-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="1d900-116">![تجانب Experian](media/experian-tile.png "تجانب Experian")</span><span class="sxs-lookup"><span data-stu-id="1d900-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="1d900-117">حدد [اتصال](connections.md) من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="1d900-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="1d900-118">اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.</span><span class="sxs-lookup"><span data-stu-id="1d900-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="1d900-119">إذا كنت مسؤولاً، يمكنك إنشاء اتصال عن طريق تحديد **إضافة اتصال** واختيار Experian من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="1d900-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="1d900-120">حدد **الاتصال بـ Experian** لتأكيد تحديد الاتصال.</span><span class="sxs-lookup"><span data-stu-id="1d900-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="1d900-121">حدد **التالي** واختر **تعيين بيانات العميل** تريد إثراء البيانات الديموغرافية من Experian.</span><span class="sxs-lookup"><span data-stu-id="1d900-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="1d900-122">يمكنك تحديد كيان **العميل** لإثراء جميع ملفات تعريف العملاء أو تحديد كيان شريحة لإثراء فقط ملفات تعريف العملاء الموجودة في تلك الشريحة.</span><span class="sxs-lookup"><span data-stu-id="1d900-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="لقطة شاشة عند اختيار مجموعة بيانات العميل.":::

1. <span data-ttu-id="1d900-124">حدد **التالي** وحدد نوع الحقول من ملفات التعريف الموحدة التي يجب استخدامها للبحث عن بيانات التركيبة السكانية المتطابقة من Experian.</span><span class="sxs-lookup"><span data-stu-id="1d900-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="1d900-125">واحد على الأقل من حقول **الاسم والعنوان** أو **الهاتف** أو **البريد الإلكتروني** مطلوب</span><span class="sxs-lookup"><span data-stu-id="1d900-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="1d900-126">للحصول على دقة تطابق أعلى، يمكن إضافة حتى حقلين آخرين.</span><span class="sxs-lookup"><span data-stu-id="1d900-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="1d900-127">سيؤثر هذا التحديد على حقول التعيين التي يمكنك الوصول إليها في الخطوة التالية.</span><span class="sxs-lookup"><span data-stu-id="1d900-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="1d900-128">من المحتمل أن تؤدي المزيد من سمات معرف المفاتيح المرسلة إلى Experian إلى معدل تطابق أعلى.</span><span class="sxs-lookup"><span data-stu-id="1d900-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="1d900-129">حدد **التالي** لبدء تعيين الحقل.</span><span class="sxs-lookup"><span data-stu-id="1d900-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="1d900-130">حدد الحقول من ملفات التعريف الموحدة التي يجب استخدامها للبحث عن بيانات التركيبة السكانية المتطابقة من Experian.</span><span class="sxs-lookup"><span data-stu-id="1d900-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="1d900-131">تم تمييز الحقول المطلوبة.</span><span class="sxs-lookup"><span data-stu-id="1d900-131">Required fields are marked.</span></span>

1. <span data-ttu-id="1d900-132">أدخل اسمًا للإثراء واسمًا لكيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="1d900-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="1d900-133">حدد **حفظ الإثراء** بعد مراجعة اختياراتك.</span><span class="sxs-lookup"><span data-stu-id="1d900-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="1d900-134">تكوين الاتصال لـ Experian</span><span class="sxs-lookup"><span data-stu-id="1d900-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="1d900-135">يلزم أن تكون المسؤول لتكوين الاتصالات.</span><span class="sxs-lookup"><span data-stu-id="1d900-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="1d900-136">حدد **إضافة اتصال** عند تكوين عملية إثراء *أو* انتقل إلى **المسؤول** > **الاتصالات** وحدد **إعداد** في تجانب Experian.</span><span class="sxs-lookup"><span data-stu-id="1d900-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="1d900-137">حدد **بدء الاستخدام‬**.</span><span class="sxs-lookup"><span data-stu-id="1d900-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="1d900-138">أدخل اسما للاتصال في مربع **اسم العرض**.</span><span class="sxs-lookup"><span data-stu-id="1d900-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="1d900-139">أدخل معرف المستخدم ومعرف الطرف ورقم الطراز صالحًا لحساب Experian Secure Transport.</span><span class="sxs-lookup"><span data-stu-id="1d900-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="1d900-140">راجع وقدم موافقتك على **خصوصية البيانات والتوافق‬** من خلال تحديد خانة الاختيار **أوافق**</span><span class="sxs-lookup"><span data-stu-id="1d900-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="1d900-141">حدد **التحقق** للتحقق من التكوين.</span><span class="sxs-lookup"><span data-stu-id="1d900-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="1d900-142">بعد إكمال التحقق، حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="1d900-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="جزء تكوين اتصال Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="1d900-144">نتائج الإثراء</span><span class="sxs-lookup"><span data-stu-id="1d900-144">Enrichment results</span></span>

<span data-ttu-id="1d900-145">لبدء عملية الإثراء، حدد **تشغيل** من شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="1d900-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="1d900-146">يمكنك أيضًا السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من [التحديث المجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1d900-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1d900-147">يعتمد وقت المعالجة على حجم بيانات العميل وعمليات الإثراء التي تم إعدادها لحسابك بواسطة Experian.</span><span class="sxs-lookup"><span data-stu-id="1d900-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="1d900-148">بعد اكتمال عملية الإثراء، يمكنك مراجعة بيانات ملفات تعريف العملاء التي تم إثراؤها حديثًا ضمن **عمليات الإثراء الخاصة بي**.</span><span class="sxs-lookup"><span data-stu-id="1d900-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="1d900-149">بالإضافة إلى ذلك ، ستجد وقت التحديث الأخير وعدد ملفات التعريف التي تم إثراؤها.</span><span class="sxs-lookup"><span data-stu-id="1d900-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="1d900-150">يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.</span><span class="sxs-lookup"><span data-stu-id="1d900-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1d900-151">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="1d900-151">Next steps</span></span>

<span data-ttu-id="1d900-152">قم بالبناء أعلى بيانات العملاء التي تم إثرائها.</span><span class="sxs-lookup"><span data-stu-id="1d900-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="1d900-153">أنشئ [الشرائح](segments.md)، و[المقاييس](measures.md)، وقم كذلك [بتصدير البيانات](export-destinations.md) لتقديم تجارب مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="1d900-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1d900-154">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="1d900-154">Data privacy and compliance</span></span>

<span data-ttu-id="1d900-155">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Experian، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="1d900-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1d900-156">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Experian بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="1d900-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1d900-157">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1d900-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="1d900-158">بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="1d900-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
