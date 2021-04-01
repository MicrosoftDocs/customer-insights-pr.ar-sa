---
title: إثراء البيانات باستخدام الاستيراد المخصص لبروتوكول SFTP‬
description: معلومات عامة حول إثراء البيانات باستخدام الاستيراد المخصص لبروتوكول SFTP‬‬
ms.date: 11/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d9e095ef793cbd25415864f76a541dce68fafe47
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595839"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="e6a3c-103">إثراء ملفات تعريف العملاء بواسطة البيانات المخصصة (معاينة)</span><span class="sxs-lookup"><span data-stu-id="e6a3c-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="e6a3c-104">يتيح لك الاستيراد المخصص لبروتوكول نقل الملفات الآمن (SFTP)‬ استيراد البيانات التي ليست بحاجة إلى المرور عبر عملية توحيد البيانات.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="e6a3c-105">إنها عملية آمنة ومرنة وسهلة لإحضار بياناتك.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="e6a3c-106">يمكن استخدام الاستيراد المخصص لبروتوكول SFTP بالتزامن مع [تصدير SFTP](export-sftp.md) الذي يتيح لك تصدير بيانات ملفات تعريف العملاء المطلوبة للإثراء.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="e6a3c-107">يمكن بعد ذلك معالجة البيانات وإثراؤها، ويمكن استخدام الاستيراد المخصص لبروتوكول SFTP لإعادة البيانات التي تم إثراؤها إلى قدرة رؤى الجمهور في Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6a3c-108">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="e6a3c-108">Prerequisites</span></span>

<span data-ttu-id="e6a3c-109">لتكوين الاستيراد المخصص لبروتوكول SFTP، يجب استيفاء المتطلبات الأساسية التالية:</span><span class="sxs-lookup"><span data-stu-id="e6a3c-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="e6a3c-110">تتوفر لديك بيانات اعتماد المستخدم (اسم المستخدم وكملة المرور) لموقع SFTP حيث توجد البيانات التي سيتم الاستيراد منها.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="e6a3c-111">لديك عنوان URL ورقم المنفذ (عادةً 22) لمضيف STFP.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="e6a3c-112">لديك اسم الملف وموقف الملف الذي سيتم استيراده على مضيف SFTP.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="e6a3c-113">يوجد ملف *model.json* الذي يحدد مخطط البيانات التي سيتم استيرادها.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="e6a3c-114">يجب أن يكون هذا الملف في الدليل نفسه حيث الملف الذي سيتم استيراده.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="e6a3c-115">لديك إذن [المسؤول](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="e6a3c-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="e6a3c-116">التكوين</span><span class="sxs-lookup"><span data-stu-id="e6a3c-116">Configuration</span></span>

1. <span data-ttu-id="e6a3c-117">انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="e6a3c-118">على الإطار المتجانب **الاستيراد المخصص لبروتوكول SFTP‬**، حدد **إثراء بياناتي**.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e6a3c-119">![الإطار المتجانب الاستيراد المخصص لبروتوكول SFTP](media/SFTP_Custom_Import_tile.png "الإطار المتجانب الاستيراد المخصص لبروتوكول SFTP")</span><span class="sxs-lookup"><span data-stu-id="e6a3c-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="e6a3c-120">حدد **الشروع في العمل**، وقدم بيانات اعتماد وعنوان خادم SFTP.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="e6a3c-121">على سبيل المثال، sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="e6a3c-122">أدخل اسم الملف الذي يحتوي على البيانات والمسار إلى الملف على خادم SFTP إذا لم يكن موجودًا في المجلد الجذر.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="e6a3c-123">أكد كافة الإدخالات من خلال تحديد **الاتصال بالاستيراد المخصص**.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="e6a3c-124">![القائمة المنبثقة تكوين الاستيراد المخصص لبروتوكول SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "القائمة المنبثقة تكوين الاستيراد المخصص لبروتوكول SFTP")</span><span class="sxs-lookup"><span data-stu-id="e6a3c-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="e6a3c-125">تعريف تعيينات الحقول</span><span class="sxs-lookup"><span data-stu-id="e6a3c-125">Defining field mappings</span></span> 

<span data-ttu-id="e6a3c-126">يجب أن يحتوي الدليل الذي يحتوي على الملف الذي سيتم استيراده على خادم SFTP على ملف *model.json*.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="e6a3c-127">يحدد هذا الملف المخطط الذي سيتم استخدامه لاستيراد البيانات.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="e6a3c-128">يجب على المخطط استخدام [نموذج البيانات العامة](/common-data-model/) لتحديد تعيين الحقول.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-128">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="e6a3c-129">مثال بسيط لملف model.json يبدو كما يلي:</span><span class="sxs-lookup"><span data-stu-id="e6a3c-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="e6a3c-130">نتائج الإثراء</span><span class="sxs-lookup"><span data-stu-id="e6a3c-130">Enrichment results</span></span>

<span data-ttu-id="e6a3c-131">لبدء عملية الإثراء، حدد **تشغيل** من شريط الأوامر.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="e6a3c-132">يمكنك أيضًا السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من [التحديث المجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e6a3c-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e6a3c-133">سيعتمد وقت المعالجة على حجم البيانات التي سيتم استيرادها والاتصال بخادم SFTP.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="e6a3c-134">بعد اكتمال عملية الإثراء، يمكنك مراجعة بيانات الإثراء المخصصة التي قمت باستيرادها مؤخرًا أسفل **عمليات الإثراء الخاصة بي‬**.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="e6a3c-135">بالإضافة إلى ذلك ، ستجد وقت التحديث الأخير وعدد ملفات التعريف التي تم إثراؤها.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="e6a3c-136">يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="e6a3c-137">الخطوات التالية</span><span class="sxs-lookup"><span data-stu-id="e6a3c-137">Next steps</span></span>

<span data-ttu-id="e6a3c-138">قم بالبناء أعلى بيانات العملاء التي تم إثرائها.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="e6a3c-139">أنشئ [شرائح](segments.md) و[مقاييس](measures.md)، و[صدّر البيانات](export-destinations.md) لتقديم تجارب مخصصة لعملائك.</span><span class="sxs-lookup"><span data-stu-id="e6a3c-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]