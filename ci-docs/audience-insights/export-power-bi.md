---
title: موصل Power BI
description: تعرّ على كيفية استخدام موصل Dynamics 365 Customer Insights في Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4404900"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="e6a3a-103">موصل لـ Power BI (معاينة)</span><span class="sxs-lookup"><span data-stu-id="e6a3a-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="e6a3a-104">أنشئ رسومًا مرئية لبياناتك باستخدام Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="e6a3a-105">قم بإنشاء معارف دقيقة إضافية وقم بإنشاء تقارير باستخدام بيانات العميل الموحدة الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6a3a-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="e6a3a-106">Prerequisites</span></span>

- <span data-ttu-id="e6a3a-107">لديك تعريف العملاء الموحدة.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="e6a3a-108">تم تثبيت الإصدار الأخير من [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) على الكمبيوتر.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="e6a3a-109">[تعرف على المزيد حول Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="e6a3a-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="e6a3a-110">تكوين الموصل لـ Power BI</span><span class="sxs-lookup"><span data-stu-id="e6a3a-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="e6a3a-111">في Power BI Desktop، حدد **ملف** > **الحصول على بيانات**.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="e6a3a-112">حدد **مشاهدة المزيد** وابحث عن **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="e6a3a-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="e6a3a-113">حدد النتيجة وحدد **اتصال**.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="e6a3a-114">**قم بتسجيل الدخول** باستخدام الحساب المؤسسي نفسه الذي تستخدمه لـ Customer Insights وحدد **اتصال**.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="e6a3a-115">يتم استخدام الحساب الذي أشرت إليه في هذه الخطوة لجلب البيانات من Customer Insights ولا يلزم أن يكون هو نفسه الذي سجلت الدخول إليه في Power BI.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="e6a3a-116">لإعادة تعيين الحساب المستخدم لإحضار البيانات، افتح Power BI وانتقل إلى **ملف** > **خيارات** > **إعدادات** > **إعدادات مصدر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="e6a3a-117">في قائمة مصادر البيانات، حدد **تسجيل الدخول إلى Dynamics 365 Customer Insights** وحدد **مسح الأذونات**.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="e6a3a-118">في مربع الحوار **المتصفح**.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="e6a3a-119">سترى قائمة بجميع البيئات التي يمكنك الوصول إليها.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="e6a3a-120">قم بتوسيع بيئة وافتح أي واحد من المجلدات (الكيانات والمقاييس والشرائح وعمليات الإثراء).</span><span class="sxs-lookup"><span data-stu-id="e6a3a-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="e6a3a-121">على سبيل المثال، افتح مجلد **الكيانات** لرؤية كافة الكيانات التي يمكنك استيرادها.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="e6a3a-122">متصفح موصل ![Power BI](media/power-bi-navigator.png "متصفح موصل Power BI")</span><span class="sxs-lookup"><span data-stu-id="e6a3a-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="e6a3a-123">حدد خانات الاختيار المجاورة للكيانات التي سيتم تضمينها **وتحميلها**.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="e6a3a-124">يُمكنك تحديد كيانات متعددة من البيئات المتعددة.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="e6a3a-125">سوف ترى مُربع تحميل في أثناء تحميل كياناتك.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="e6a3a-126">بمجرد أن يتم تحميل كافة الكيانات المحددة، يمكنك استخدام قدرات Power BI لتمثيل البيانات مرئيًا.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="e6a3a-127">مجموعات البيانات الكبيرة</span><span class="sxs-lookup"><span data-stu-id="e6a3a-127">Large data sets</span></span>

<span data-ttu-id="e6a3a-128">تم تصميم موصل Customer Insights لـ Power BI للعمل مع مجموعات البيانات التي تحتوي على ما يصل إلى مليون ملف تعريف للعملاء.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="e6a3a-129">قد تعمل عملية استيراد مجموعات بيانات أكبر، ولكنها تستغرق وقتًا طويلاً.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="e6a3a-130">علاوةً على ذلك، قد يتم تنفيذ هذه العملية ضمن مهلة بسبب قيود Power BI.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="e6a3a-131">لمزيد من المعلومات، راجع [Power BI: توصيات بشأن مجموعات البيانات الكبيرة](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="e6a3a-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="e6a3a-132">التعامل مع مجموعة فرعية من البيانات</span><span class="sxs-lookup"><span data-stu-id="e6a3a-132">Work with a subset of data</span></span>

<span data-ttu-id="e6a3a-133">يمكنك العمل مع مجموعة فرعية من بياناتك.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="e6a3a-134">علي سبيل المثال، يمكنك إنشاء [شرائح](segments.md) بدلاً من تصدير كافة سجلات العملاء إلى Power BI.</span><span class="sxs-lookup"><span data-stu-id="e6a3a-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
