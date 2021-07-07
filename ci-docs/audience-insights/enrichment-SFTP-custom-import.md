---
title: إثراء البيانات باستخدام الاستيراد المخصص لبروتوكول SFTP‬
description: معلومات عامة حول إثراء البيانات باستخدام الاستيراد المخصص لبروتوكول SFTP‬‬
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304634"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="a2f84-103">إثراء ملفات تعريف العملاء بواسطة البيانات المخصصة (معاينة)</span><span class="sxs-lookup"><span data-stu-id="a2f84-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="a2f84-104">يتيح لك الاستيراد المخصص لبروتوكول نقل الملفات الآمن (SFTP)‬ استيراد البيانات التي ليست بحاجة إلى المرور عبر عملية توحيد البيانات.</span><span class="sxs-lookup"><span data-stu-id="a2f84-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="a2f84-105">إنها عملية آمنة ومرنة وسهلة لإحضار بياناتك.</span><span class="sxs-lookup"><span data-stu-id="a2f84-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="a2f84-106">يمكن استخدام الاستيراد المخصص لبروتوكول SFTP بالتزامن مع [تصدير SFTP](export-sftp.md) الذي يتيح لك تصدير بيانات ملفات تعريف العملاء المطلوبة للإثراء.</span><span class="sxs-lookup"><span data-stu-id="a2f84-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="a2f84-107">ويمكن بعد ذلك معالجة البيانات وإثراؤها، كما يمكن استخدام استيراد SFTP المخصص لإحضار البيانات المثرية مرة أخرى إلى معلومات الجمهور الخاصة بـ Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a2f84-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a2f84-108">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="a2f84-108">Prerequisites</span></span>

<span data-ttu-id="a2f84-109">لتكوين الاستيراد المخصص لبروتوكول SFTP، يجب استيفاء المتطلبات الأساسية التالية:</span><span class="sxs-lookup"><span data-stu-id="a2f84-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="a2f84-110">لديك اسم الملف وموقع (المسار) للملف المطلوب استيراده على مضيف SFTP.</span><span class="sxs-lookup"><span data-stu-id="a2f84-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="a2f84-111">يوجد ملف *model.json* الذي يحدد [خطط نموذج البيانات العامة](/common-data-model/) للبيانات المراد استيرادها.</span><span class="sxs-lookup"><span data-stu-id="a2f84-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="a2f84-112">يجب أن يكون هذا الملف في الدليل نفسه حيث الملف الذي سيتم استيراده.</span><span class="sxs-lookup"><span data-stu-id="a2f84-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="a2f84-113">تم بالفعل تكوين اتصال SFTP بواسطة المسؤول *أو* تحصل على أذونات [المسؤول](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="a2f84-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="a2f84-114">سوف تحتاج إلى بيانات اعتماد المستخدم وعنوان URL رقم المنفذ لموقع SFTP حيث تريد استيراد البيانات منه.</span><span class="sxs-lookup"><span data-stu-id="a2f84-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="a2f84-115">تكوين الاستيراد</span><span class="sxs-lookup"><span data-stu-id="a2f84-115">Configure the import</span></span>

1. <span data-ttu-id="a2f84-116">انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.</span><span class="sxs-lookup"><span data-stu-id="a2f84-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="a2f84-117">في **تجانب الاستيراد المخصص لـ SFTP**، حدد **إثراء بياناتي** ثم حدد **الشروع في العمل**.</span><span class="sxs-lookup"><span data-stu-id="a2f84-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="تجانب الاستيراد المخصص لـ SFTP":::

1. <span data-ttu-id="a2f84-119">حدد [اتصالاً](connections.md) من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="a2f84-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="a2f84-120">اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.</span><span class="sxs-lookup"><span data-stu-id="a2f84-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="a2f84-121">إذا كنت أحد المسؤول، يمكنك إنشاء اتصال عن طريق تحديد **إضاف اتصال** واختيار **استيراد SFTP المخصص** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="a2f84-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="a2f84-122">حدد **الاتصال بالاستيراد المخصص** لتأكيد الاتصال المحدد.</span><span class="sxs-lookup"><span data-stu-id="a2f84-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="a2f84-123">حدد **التالي** وأدخل **المسار** و **اسم الملف** الخاصين بملف البيانات الذي تريد استيراده.</span><span class="sxs-lookup"><span data-stu-id="a2f84-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="لقطة شاشة عند إدخال موقع البيانات.":::

1. <span data-ttu-id="a2f84-125">حدد **التالي** وأدخل اسمًا للإثراء واسمًا لكيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="a2f84-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="a2f84-126">حدد **حفظ الإثراء** بعد مراجعة اختياراتك.</span><span class="sxs-lookup"><span data-stu-id="a2f84-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="a2f84-127">تكوين الاتصال لاستيراد SFTP المخصص</span><span class="sxs-lookup"><span data-stu-id="a2f84-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="a2f84-128">يلزم أن تكون المسؤول لتكوين الاتصالات.</span><span class="sxs-lookup"><span data-stu-id="a2f84-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="a2f84-129">حدد **إضافة اتصال** عند تكوين عملية إثراء *أو* انتقل إلى **المسؤول** > **الاتصالات** وحدد **إعداد** في تجانب الاستيراد المخصص.</span><span class="sxs-lookup"><span data-stu-id="a2f84-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="a2f84-130">أدخل اسما للاتصال في مربع **اسم العرض**.</span><span class="sxs-lookup"><span data-stu-id="a2f84-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="a2f84-131">أدخل اسم مستخدم صالح وكلمة مرور وعنوان URL لاستضافة خادم SFTP الذي توجد البيانات المطلوب استيرادها فيه.</span><span class="sxs-lookup"><span data-stu-id="a2f84-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="a2f84-132">راجع وقدم موافقتك على **خصوصية البيانات والتوافق‬** من خلال تحديد خانة الاختيار **أوافق**.</span><span class="sxs-lookup"><span data-stu-id="a2f84-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="a2f84-133">حدد **التحقق** للتحقق من التكوين.</span><span class="sxs-lookup"><span data-stu-id="a2f84-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="a2f84-134">بمجرد الانتهاء من التحقق، يمكن حفظ الاتصال بتحديد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="a2f84-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a2f84-135">![صفحة تكوين اتصال Experian](media/enrichment-SFTP-connection.png "صفحة تكوين اتصال Experian")</span><span class="sxs-lookup"><span data-stu-id="a2f84-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="a2f84-136">تعريف تعيينات الحقول</span><span class="sxs-lookup"><span data-stu-id="a2f84-136">Defining field mappings</span></span> 

<span data-ttu-id="a2f84-137">يجب أن يحتوي الدليل الذي يحتوي على الملف الذي سيتم استيراده على خادم SFTP على ملف *model.json*.</span><span class="sxs-lookup"><span data-stu-id="a2f84-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="a2f84-138">يحدد هذا الملف المخطط الذي سيتم استخدامه لاستيراد البيانات.</span><span class="sxs-lookup"><span data-stu-id="a2f84-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="a2f84-139">يجب أن يستخدم المخطط [Common Data Model](/common-data-model/) لتحديد تعيين الحقل.</span><span class="sxs-lookup"><span data-stu-id="a2f84-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="a2f84-140">مثال بسيط لملف model.json يبدو كما يلي:</span><span class="sxs-lookup"><span data-stu-id="a2f84-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="a2f84-141">نتائج الإثراء</span><span class="sxs-lookup"><span data-stu-id="a2f84-141">Enrichment results</span></span>

<span data-ttu-id="a2f84-142">لبدء عملية الإثراء، حدد **تشغيل** من شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="a2f84-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="a2f84-143">يمكنك أيضًا السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من [التحديث المجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a2f84-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a2f84-144">سيعتمد وقت المعالجة على حجم البيانات التي سيتم استيرادها والاتصال بخادم SFTP.</span><span class="sxs-lookup"><span data-stu-id="a2f84-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="a2f84-145">بعد اكتمال عملية الإثراء، يمكنك مراجعة بيانات الإثراء المخصصة التي قمت باستيرادها مؤخرًا أسفل **عمليات الإثراء الخاصة بي‬**.</span><span class="sxs-lookup"><span data-stu-id="a2f84-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="a2f84-146">بالإضافة إلى ذلك ، ستجد وقت التحديث الأخير وعدد ملفات التعريف التي تم إثراؤها.</span><span class="sxs-lookup"><span data-stu-id="a2f84-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="a2f84-147">يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.</span><span class="sxs-lookup"><span data-stu-id="a2f84-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a2f84-148">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="a2f84-148">Next steps</span></span>

<span data-ttu-id="a2f84-149">قم بالبناء أعلى بيانات العملاء التي تم إثرائها.</span><span class="sxs-lookup"><span data-stu-id="a2f84-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="a2f84-150">أنشئ [الشرائح](segments.md) و[القياسات](measures.md) و[تصدير البيانات](export-destinations.md) لتسليم تجارب مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="a2f84-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
