---
title: إثراء ملفات تعريف الشركات بواسطة خدمات إثراء البيانات من طرف ثالث Leadspace‬
description: معلومات عامة حول خدمات إثراء البيانات من طرف ثالث Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305186"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="73e60-103">إثراء ملفات تعريف الشركات من خلال Leadspace (معاينة)</span><span class="sxs-lookup"><span data-stu-id="73e60-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="73e60-104">Leadspace هي شركة مختصة في علوم البيانات توفر نظامًا أساسيًا لبيانات العميل من عمل لعمل.</span><span class="sxs-lookup"><span data-stu-id="73e60-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="73e60-105">وهي تمكن العملاء من خلال ملفات تعريف العملاء الموحدة للشركات من إثراء بياناتهم.</span><span class="sxs-lookup"><span data-stu-id="73e60-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="73e60-106">تشمل عمليات الإثراء المزيد من السمات مثل حجم الشركة والموقع والصناعة والمزيد.</span><span class="sxs-lookup"><span data-stu-id="73e60-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="73e60-107">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="73e60-107">Prerequisites</span></span>

<span data-ttu-id="73e60-108">لتكوين Leadspace، يجب استيفاء المتطلبات الأساسية التالية:</span><span class="sxs-lookup"><span data-stu-id="73e60-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="73e60-109">لديك ترخيص Leadspace نشط.</span><span class="sxs-lookup"><span data-stu-id="73e60-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="73e60-110">لديك [ملفات تعريف عملاء موحدة](customer-profiles.md) للشركات.</span><span class="sxs-lookup"><span data-stu-id="73e60-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="73e60-111">تم بالفعل تكوين اتصال Leadspace بواسطة مسؤول أو لديك أذونات [المسؤول](permissions.md#administrator) و "المفتاح الدائم" (المشار إليه بـ **رمز Leadspace المميز**).</span><span class="sxs-lookup"><span data-stu-id="73e60-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="73e60-112">اتصل بـ [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) مباشرةً للاطلاع على تفاصيل حول منتجها.</span><span class="sxs-lookup"><span data-stu-id="73e60-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="73e60-113">تكوين الإثراء</span><span class="sxs-lookup"><span data-stu-id="73e60-113">Configure the enrichment</span></span>

1. <span data-ttu-id="73e60-114">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **الإثراء**.</span><span class="sxs-lookup"><span data-stu-id="73e60-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="73e60-115">حدد **إثراء بياناتي** في الإطار المتجانب Leadspace وحدد **الشروع في العمل**.</span><span class="sxs-lookup"><span data-stu-id="73e60-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="لقطة شاشة للإطار المتجانب Leadspace.":::

1. <span data-ttu-id="73e60-117">حدد [اتصالاً](connections.md) من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="73e60-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="73e60-118">اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.</span><span class="sxs-lookup"><span data-stu-id="73e60-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="73e60-119">إذا كنت أحد المسؤول، يمكنك إنشاء اتصال بتحديد **إضافة اتصال** واختيار **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="73e60-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="73e60-120">حدد **الاتصال بـ Leadspace** لتأكيد الاتصال.</span><span class="sxs-lookup"><span data-stu-id="73e60-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="73e60-121">حدد **التالي** واختر **مجموعة بيانات العميل** التي تريد إثراؤها باستخدام بيانات الشركة من Leadspace.</span><span class="sxs-lookup"><span data-stu-id="73e60-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="73e60-122">يمكنك تحديد كيان **العميل** لإثراء جميع ملفات تعريف العملاء أو تحديد كيان شريحة لإثراء فقط ملفات تعريف العملاء الموجودة في تلك الشريحة.</span><span class="sxs-lookup"><span data-stu-id="73e60-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="لقطة شاشة عند اختيار مجموعة بيانات العميل.":::

1. <span data-ttu-id="73e60-124">حدد **التالي** وحدد الحقول من ملفات التعريف الموحدة المستخدمة للبحث عن بيانات الشركة المطابقة من Leadspace.</span><span class="sxs-lookup"><span data-stu-id="73e60-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="73e60-125">الحقل **اسم الشركة** مطلوب.</span><span class="sxs-lookup"><span data-stu-id="73e60-125">The **Name of company** field is required.</span></span> <span data-ttu-id="73e60-126">للحصول على دقة مطابقه أعلى، يمكن إضافة الحقلين **موقع ويب للشركة** و **موقع الشركة**.</span><span class="sxs-lookup"><span data-stu-id="73e60-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="جزء تعيين حقول Leadspace.":::

1. <span data-ttu-id="73e60-128">حدد **التالي** لإكمال تعيين الحقل.</span><span class="sxs-lookup"><span data-stu-id="73e60-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="73e60-129">قدم اسمًا لعملية الإثراء وحدد **حفظ الإثراء** بعد مراجعة خياراتك.</span><span class="sxs-lookup"><span data-stu-id="73e60-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="73e60-130">تكوين الاتصال لـ Leadspace</span><span class="sxs-lookup"><span data-stu-id="73e60-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="73e60-131">يلزم أن تكون المسؤول لتكوين الاتصالات.</span><span class="sxs-lookup"><span data-stu-id="73e60-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="73e60-132">حدد **إضافة اتصال** عند تكوين عملية إثراء *أو* انتقل إلى **المسؤول** > **الاتصالات** وحدد **إعداد** في تجانب Leadspace.</span><span class="sxs-lookup"><span data-stu-id="73e60-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="73e60-133">حدد **بدء الاستخدام‬**.</span><span class="sxs-lookup"><span data-stu-id="73e60-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="73e60-134">أدخل اسما للاتصال في مربع **اسم العرض**.</span><span class="sxs-lookup"><span data-stu-id="73e60-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="73e60-135">قدم رمز Leadspace مميزًا وصالحًا.</span><span class="sxs-lookup"><span data-stu-id="73e60-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="73e60-136">راجع **خصوصية البيانات والامتثال** وقدم الموافقة عليها بتحديد **أوافق**.</span><span class="sxs-lookup"><span data-stu-id="73e60-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="73e60-137">حدد **التحقق** للتحقق من التكوين.</span><span class="sxs-lookup"><span data-stu-id="73e60-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="73e60-138">بعد إكمال التحقق، حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="73e60-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="صفحة تكوين الاتصال بـ Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="73e60-140">نتائج الإثراء</span><span class="sxs-lookup"><span data-stu-id="73e60-140">Enrichment results</span></span>

<span data-ttu-id="73e60-141">بعد تحديث الإثراء، يمكنك مراجعة بيانات الشركة التي تم إثراؤها حديثًا والموجودة ضمن [عمليات الإثراء الخاصة بي‬](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="73e60-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="73e60-142">يمكنك العثور على وقت آخر تحديث وعدد ملفات تعريف التي تم إثراؤها.</span><span class="sxs-lookup"><span data-stu-id="73e60-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="73e60-143">يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.</span><span class="sxs-lookup"><span data-stu-id="73e60-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="73e60-144">لمزيد من المعلومات، راجع [مؤشرات الأداء الأساسية API لـ Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="73e60-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="73e60-145">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="73e60-145">Next steps</span></span>

<span data-ttu-id="73e60-146">قم بالبناء أعلى بيانات العملاء التي تم إثرائها.</span><span class="sxs-lookup"><span data-stu-id="73e60-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="73e60-147">أنشئ [الشرائح](segments.md) و[القياسات](measures.md) وحتى [تصدير البيانات](export-destinations.md) لتسليم تجارب مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="73e60-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="73e60-148">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="73e60-148">Data privacy and compliance</span></span>

<span data-ttu-id="73e60-149">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Leadspace، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="73e60-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="73e60-150">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Leadspace بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="73e60-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="73e60-151">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="73e60-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="73e60-152">بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="73e60-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
