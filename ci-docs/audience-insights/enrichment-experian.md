---
title: الإثراء باستخدام Experian لجهة خارجية
description: معلومات عامة عن إثراء Experian التابع لجهة خارجية.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309804"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="3f259-103">إثراء ملفات تعريف العملاء بخصائص سكانية من Experian (معاينة)</span><span class="sxs-lookup"><span data-stu-id="3f259-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="3f259-104">Experian هي شركة رائدة على مستوى العالم في مجال إعداد تقارير ائتمانات العملاء والأعمال وخدمات التسويق.</span><span class="sxs-lookup"><span data-stu-id="3f259-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="3f259-105">من خلال خدمات إثراء البيانات في Experian يمكن بناء فهم أكبر للعملاء من خلال إثراء ملفات تعريف العملاء بالبيانات السكانية مثل حجم البنية الأساسية والدخل وأية معلومات أخرى.</span><span class="sxs-lookup"><span data-stu-id="3f259-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3f259-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="3f259-106">Prerequisites</span></span>

<span data-ttu-id="3f259-107">لتكوين Experian، يجب الوفاء بالمتطلبات الأساسية التالية: </span><span class="sxs-lookup"><span data-stu-id="3f259-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="3f259-108">لديك اشتراك Experian نشط.</span><span class="sxs-lookup"><span data-stu-id="3f259-108">You have an active Experian subscription.</span></span> <span data-ttu-id="3f259-109">للحصول على اشتراك، [اتصل بـ Experian](https://www.experian.com/marketing-services/contact) مباشرةً.</span><span class="sxs-lookup"><span data-stu-id="3f259-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="3f259-110">[تعرف على المزيد حول إثراء البيانات في Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="3f259-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="3f259-111">تم بالفعل تكوين اتصال Experian بواسطة المسؤول *أو* تحصل على أذونات [المسؤول](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="3f259-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="3f259-112">كما تحتاج أيضا إلى "تعريف المستخدم" و"رقم الطرف" و"رقم النموذج" لحساب النقل الآمن (ST) الممكن لـ SSH الذي أنشاته Experian من أجلك.</span><span class="sxs-lookup"><span data-stu-id="3f259-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="3f259-113">البلدان/المناطق المدعومة</span><span class="sxs-lookup"><span data-stu-id="3f259-113">Supported countries/regions</span></span>

<span data-ttu-id="3f259-114">ونحن ندعم حاليا إثراء ملفات تعريف العملاء في الولايات المتحدة فقط.</span><span class="sxs-lookup"><span data-stu-id="3f259-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="3f259-115">تكوين الإثراء</span><span class="sxs-lookup"><span data-stu-id="3f259-115">Configure the enrichment</span></span>

1. <span data-ttu-id="3f259-116">انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.</span><span class="sxs-lookup"><span data-stu-id="3f259-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="3f259-117">حدد **إثراء البيانات** في تجانب Experian.</span><span class="sxs-lookup"><span data-stu-id="3f259-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3f259-118">![Experian متجانبة أخرى](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="3f259-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="3f259-119">حدد [اتصالاً](connections.md) من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="3f259-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="3f259-120">اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.</span><span class="sxs-lookup"><span data-stu-id="3f259-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="3f259-121">إذا كنت أحد المسؤول، يمكنك إنشاء اتصال عن طريق تحديد **إضافة اتصال** واختيار Experian من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="3f259-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="3f259-122">حدد **الاتصال بـ Experian** لتأكيد تحديد الاتصال.</span><span class="sxs-lookup"><span data-stu-id="3f259-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="3f259-123">حدد **التالي** واختر **مجموعة بيانات العميل** التي تريد إثراؤها ببيانات الخصائص السكانية من Experian.</span><span class="sxs-lookup"><span data-stu-id="3f259-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="3f259-124">يمكنك تحديد كيان **العميل** لإثراء جميع ملفات تعريف العملاء أو تحديد كيان شريحة لإثراء فقط ملفات تعريف العملاء الموجودة في تلك الشريحة.</span><span class="sxs-lookup"><span data-stu-id="3f259-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="لقطة شاشة عند اختيار مجموعة بيانات العميل.":::

1. <span data-ttu-id="3f259-126">حدد **التالي** وحدد نوع الحقول من ملفات التعريف الموحدة التي ينبغي استخدامها للبحث عن البيانات السكانية المتطابقة من Experian.</span><span class="sxs-lookup"><span data-stu-id="3f259-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="3f259-127">واحد على الأقل من حقول **الاسم والعنوان** أو **الهاتف** أو **البريد الإلكتروني** مطلوب</span><span class="sxs-lookup"><span data-stu-id="3f259-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="3f259-128">للحصول على دقة تطابق أعلى، يمكن إضافة حتى حقلين آخرين.</span><span class="sxs-lookup"><span data-stu-id="3f259-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="3f259-129">سيؤثر هذا التحديد على حقول التعيين التي يمكنك الوصول إليها في الخطوة التالية.</span><span class="sxs-lookup"><span data-stu-id="3f259-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="3f259-130">من المرجح أن تؤدي المزيد من سمات المعرف الأساسي المرسلة إلى Experian إلى زيادة معدل تطابق.</span><span class="sxs-lookup"><span data-stu-id="3f259-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="3f259-131">حدد **التالي** لبدء تعيين الحقل.</span><span class="sxs-lookup"><span data-stu-id="3f259-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="3f259-132">حدد نوع الحقول من ملفات التعريف الموحدة التي ينبغي استخدامها للبحث عن البيانات السكانية المتطابقة من Experian.</span><span class="sxs-lookup"><span data-stu-id="3f259-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="3f259-133">تم تمييز الحقول المطلوبة.</span><span class="sxs-lookup"><span data-stu-id="3f259-133">Required fields are marked.</span></span>

1. <span data-ttu-id="3f259-134">أدخل اسمًا للإثراء واسمًا لكيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="3f259-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="3f259-135">حدد **حفظ الإثراء** بعد مراجعة اختياراتك.</span><span class="sxs-lookup"><span data-stu-id="3f259-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="3f259-136">تكوين الاتصال لـ Experian</span><span class="sxs-lookup"><span data-stu-id="3f259-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="3f259-137">يلزم أن تكون المسؤول لتكوين الاتصالات.</span><span class="sxs-lookup"><span data-stu-id="3f259-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="3f259-138">حدد **إضافة اتصال** عند تكوين إثراء *أو* انتقل إلى **المسؤول** > **الاتصالات** وحدد **إعداد** في تجانب Experian.</span><span class="sxs-lookup"><span data-stu-id="3f259-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="3f259-139">حدد **بدء الاستخدام‬**.</span><span class="sxs-lookup"><span data-stu-id="3f259-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="3f259-140">أدخل اسما للاتصال في مربع **اسم العرض**.</span><span class="sxs-lookup"><span data-stu-id="3f259-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="3f259-141">أدخل "رقم تعريف المستخدم" و"رقم الطرف" و"رقم النموذج" لحساب النقل الآمن في Experian.</span><span class="sxs-lookup"><span data-stu-id="3f259-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="3f259-142">راجع **خصوصية البيانات والامتثال** وقدم الموافقة عليها بتحديد **أوافق**.</span><span class="sxs-lookup"><span data-stu-id="3f259-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="3f259-143">حدد **التحقق** للتحقق من التكوين.</span><span class="sxs-lookup"><span data-stu-id="3f259-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="3f259-144">بعد إكمال التحقق، حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="3f259-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="جزء تكوين اتصال Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="3f259-146">نتائج الإثراء</span><span class="sxs-lookup"><span data-stu-id="3f259-146">Enrichment results</span></span>

<span data-ttu-id="3f259-147">لبدء عملية الإثراء، حدد **تشغيل** من شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="3f259-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="3f259-148">يمكنك أيضًا السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من [التحديث المجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3f259-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3f259-149">يعتمد وقت المعالجة على حجم بيانات العميل والعمليات التي يتم إعدادها لحسابك من خلال Experian.</span><span class="sxs-lookup"><span data-stu-id="3f259-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="3f259-150">بعد اكتمال عملية الإثراء، يمكنك مراجعة بيانات ملفات تعريف العملاء التي تم إثراؤها حديثًا ضمن **عمليات الإثراء الخاصة بي**.</span><span class="sxs-lookup"><span data-stu-id="3f259-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="3f259-151">بالإضافة إلى ذلك ، ستجد وقت التحديث الأخير وعدد ملفات التعريف التي تم إثراؤها.</span><span class="sxs-lookup"><span data-stu-id="3f259-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="3f259-152">يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.</span><span class="sxs-lookup"><span data-stu-id="3f259-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3f259-153">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="3f259-153">Next steps</span></span>

<span data-ttu-id="3f259-154">قم بالبناء أعلى بيانات العملاء التي تم إثرائها.</span><span class="sxs-lookup"><span data-stu-id="3f259-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="3f259-155">أنشئ [الشرائح](segments.md) و[القياسات](measures.md) وحتى [تصدير البيانات](export-destinations.md) لتسليم تجارب مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="3f259-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3f259-156">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="3f259-156">Data privacy and compliance</span></span>

<span data-ttu-id="3f259-157">عندما تقوم بتمكين Dynamics 365 Customer Insights لنقل البيانات إلى Experian، يمكنك السماح بنقل البيانات خارج حدود التوافق لـ Dynamics 365 Customer Insights، بما في ذلك البيانات التي قد تكون حساسة مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="3f259-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3f259-158">ستقوم Microsoft بنقل هذه البيانات في الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان وفاء Experian بأية خصوصية أو واجبات أمنية قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="3f259-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3f259-159">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3f259-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3f259-160">بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="3f259-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
