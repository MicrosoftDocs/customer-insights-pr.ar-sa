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
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896265"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="c2ade-103">إثراء ملفات تعريف العملاء بواسطة البيانات المخصصة (معاينة)</span><span class="sxs-lookup"><span data-stu-id="c2ade-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="c2ade-104">يمكّنك الاستيراد المخصص لبروتوكول نقل الملفات الآمن (SFTP) من استيراد البيانات التي لا تحتاج إلى المرور بعملية توحيد البيانات.</span><span class="sxs-lookup"><span data-stu-id="c2ade-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="c2ade-105">إنها عملية آمنة ومرنة وسهلة لإحضار بياناتك.</span><span class="sxs-lookup"><span data-stu-id="c2ade-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="c2ade-106">يمكن استخدام الاستيراد المخصص لبروتوكول SFTP بالتزامن مع [تصدير SFTP](export-sftp.md) الذي يتيح لك تصدير بيانات ملفات تعريف العملاء المطلوبة للإثراء.</span><span class="sxs-lookup"><span data-stu-id="c2ade-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="c2ade-107">يمكن بعد ذلك معالجة البيانات وإثراؤها، ويمكن استخدام الاستيراد المخصص لبروتوكول SFTP لإعادة البيانات التي تم إثراؤها إلى قدرة رؤى الجمهور في Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c2ade-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c2ade-108">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="c2ade-108">Prerequisites</span></span>

<span data-ttu-id="c2ade-109">لتكوين الاستيراد المخصص لبروتوكول SFTP، يجب استيفاء المتطلبات الأساسية التالية:</span><span class="sxs-lookup"><span data-stu-id="c2ade-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c2ade-110">لديك اسم الملف وموقعه (مساره) للملف الذي سيتم استيراده على مضيف SFTP.</span><span class="sxs-lookup"><span data-stu-id="c2ade-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="c2ade-111">يوجد ملف *model.json* الذي يحدد [خطط نموذج البيانات العامة](/common-data-model/) للبيانات المراد استيرادها.</span><span class="sxs-lookup"><span data-stu-id="c2ade-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="c2ade-112">يجب أن يكون هذا الملف في الدليل نفسه حيث الملف الذي سيتم استيراده.</span><span class="sxs-lookup"><span data-stu-id="c2ade-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="c2ade-113">تم بالفعل تكوين اتصال SFTP بواسطة المسؤول *أو* تحصل على أذونات [المسؤول](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="c2ade-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="c2ade-114">سوف تحتاج إلى بيانات اعتماد المستخدم وعنوان URL رقم المنفذ لموقع SFTP حيث تريد استيراد البيانات منه.</span><span class="sxs-lookup"><span data-stu-id="c2ade-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="c2ade-115">تكوين الاستيراد</span><span class="sxs-lookup"><span data-stu-id="c2ade-115">Configure the import</span></span>

1. <span data-ttu-id="c2ade-116">انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.</span><span class="sxs-lookup"><span data-stu-id="c2ade-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="c2ade-117">في **تجانب الاستيراد المخصص لـ SFTP**، حدد **إثراء بياناتي** ثم حدد **الشروع في العمل**.</span><span class="sxs-lookup"><span data-stu-id="c2ade-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="تجانب الاستيراد المخصص لـ SFTP":::

1. <span data-ttu-id="c2ade-119">حدد [اتصال](connections.md) من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="c2ade-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="c2ade-120">اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.</span><span class="sxs-lookup"><span data-stu-id="c2ade-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="c2ade-121">إذا كنت مسؤولاً ، يمكنك إنشاء اتصال عن طريق تحديد **إضافة اتصال** واختيار **الاستيراد المخصص لـ SFTP** من القائمة المنسدلة.</span><span class="sxs-lookup"><span data-stu-id="c2ade-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="c2ade-122">حدد **الاتصال بالاستيراد المخصص** لتأكيد الاتصال المحدد.</span><span class="sxs-lookup"><span data-stu-id="c2ade-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="c2ade-123">حدد **التالي** وأدخل **اسم الملف** و **المسار** الخاص بملف البيانات الذي تريد استيراده.</span><span class="sxs-lookup"><span data-stu-id="c2ade-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="لقطة شاشة عند إدخال موقع البيانات.":::

1. <span data-ttu-id="c2ade-125">حدد **التالي** وأدخل اسمًا للإثراء واسمًا لكيان الإخراج.</span><span class="sxs-lookup"><span data-stu-id="c2ade-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="c2ade-126">حدد **حفظ الإثراء** بعد مراجعة اختياراتك.</span><span class="sxs-lookup"><span data-stu-id="c2ade-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="c2ade-127">تكوين الاتصال لاستيراد SFTP المخصص</span><span class="sxs-lookup"><span data-stu-id="c2ade-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="c2ade-128">يلزم أن تكون المسؤول لتكوين الاتصالات.</span><span class="sxs-lookup"><span data-stu-id="c2ade-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="c2ade-129">حدد **إضافة اتصال** عند تكوين عملية إثراء *أو* انتقل إلى **المسؤول** > **الاتصالات** وحدد **إعداد** في تجانب الاستيراد المخصص.</span><span class="sxs-lookup"><span data-stu-id="c2ade-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="c2ade-130">أدخل اسما للاتصال في مربع **اسم العرض**.</span><span class="sxs-lookup"><span data-stu-id="c2ade-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="c2ade-131">أدخل اسم المستخدم وكلمة المرور وعنوان URL الصالح لاستضافة خادم STFP، والبيانات التي سيتم استيرادها موجودة فيه.</span><span class="sxs-lookup"><span data-stu-id="c2ade-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="c2ade-132">راجع وقدم موافقتك على **خصوصية البيانات والتوافق‬** من خلال تحديد خانة الاختيار **أوافق**.</span><span class="sxs-lookup"><span data-stu-id="c2ade-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="c2ade-133">حدد **التحقق** للتحقق من التكوين.</span><span class="sxs-lookup"><span data-stu-id="c2ade-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="c2ade-134">بمجرد الانتهاء من التحقق، يمكن حفظ الاتصال بالنقر فوق **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="c2ade-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="c2ade-135">![صفح تكوين الاتصال بـ Experian](media/enrichment-SFTP-connection.png "صفح تكوين الاتصال بـ Experian")</span><span class="sxs-lookup"><span data-stu-id="c2ade-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="c2ade-136">تعريف تعيينات الحقول</span><span class="sxs-lookup"><span data-stu-id="c2ade-136">Defining field mappings</span></span> 

<span data-ttu-id="c2ade-137">يجب أن يحتوي الدليل الذي يحتوي على الملف الذي سيتم استيراده على خادم SFTP على ملف *model.json*.</span><span class="sxs-lookup"><span data-stu-id="c2ade-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="c2ade-138">يحدد هذا الملف المخطط الذي سيتم استخدامه لاستيراد البيانات.</span><span class="sxs-lookup"><span data-stu-id="c2ade-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="c2ade-139">يجب على المخطط استخدام [نموذج البيانات العامة](/common-data-model/) لتحديد تعيين الحقول.</span><span class="sxs-lookup"><span data-stu-id="c2ade-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="c2ade-140">مثال بسيط لملف model.json يبدو كما يلي:</span><span class="sxs-lookup"><span data-stu-id="c2ade-140">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="c2ade-141">نتائج الإثراء</span><span class="sxs-lookup"><span data-stu-id="c2ade-141">Enrichment results</span></span>

<span data-ttu-id="c2ade-142">لبدء عملية الإثراء، حدد **تشغيل** من شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="c2ade-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="c2ade-143">يمكنك أيضًا السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من [التحديث المجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c2ade-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c2ade-144">سيعتمد وقت المعالجة على حجم البيانات التي سيتم استيرادها والاتصال بخادم SFTP.</span><span class="sxs-lookup"><span data-stu-id="c2ade-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="c2ade-145">بعد اكتمال عملية الإثراء، يمكنك مراجعة بيانات الإثراء المخصصة التي قمت باستيرادها مؤخرًا أسفل **عمليات الإثراء الخاصة بي‬**.</span><span class="sxs-lookup"><span data-stu-id="c2ade-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="c2ade-146">بالإضافة إلى ذلك ، ستجد وقت التحديث الأخير وعدد ملفات التعريف التي تم إثراؤها.</span><span class="sxs-lookup"><span data-stu-id="c2ade-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c2ade-147">يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.</span><span class="sxs-lookup"><span data-stu-id="c2ade-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c2ade-148">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="c2ade-148">Next steps</span></span>

<span data-ttu-id="c2ade-149">قم بالبناء أعلى بيانات العملاء التي تم إثرائها.</span><span class="sxs-lookup"><span data-stu-id="c2ade-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c2ade-150">أنشئ [شرائح](segments.md) و[مقاييس](measures.md)، و[صدّر البيانات](export-destinations.md) لتقديم تجارب مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="c2ade-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
