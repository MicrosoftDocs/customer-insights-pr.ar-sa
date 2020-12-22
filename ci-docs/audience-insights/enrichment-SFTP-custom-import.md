---
title: إثراء البيانات باستخدام الاستيراد المخصص لبروتوكول SFTP‬
description: معلومات عامة حول إثراء البيانات باستخدام الاستيراد المخصص لبروتوكول SFTP‬‬
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568396"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>إثراء ملفات تعريف العملاء بواسطة البيانات المخصصة (معاينة)

يتيح لك الاستيراد المخصص لبروتوكول نقل الملفات الآمن (SFTP)‬ استيراد البيانات التي ليست بحاجة إلى المرور عبر عملية توحيد البيانات. إنها عملية آمنة ومرنة وسهلة لإحضار بياناتك. يمكن استخدام الاستيراد المخصص لبروتوكول SFTP بالتزامن مع [تصدير SFTP](export-sftp.md) الذي يتيح لك تصدير بيانات ملفات تعريف العملاء المطلوبة للإثراء. يمكن بعد ذلك معالجة البيانات وإثراؤها، ويمكن استخدام الاستيراد المخصص لبروتوكول SFTP لإعادة البيانات التي تم إثراؤها إلى قدرة رؤى الجمهور في Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>المتطلبات الأساسية

لتكوين الاستيراد المخصص لبروتوكول SFTP، يجب استيفاء المتطلبات الأساسية التالية:

- تتوفر لديك بيانات اعتماد المستخدم (اسم المستخدم وكملة المرور) لموقع SFTP حيث توجد البيانات التي سيتم الاستيراد منها.
- لديك عنوان URL ورقم المنفذ (عادةً 22) لمضيف STFP.
- لديك اسم الملف وموقف الملف الذي سيتم استيراده على مضيف SFTP.
- يوجد ملف *model.json* الذي يحدد مخطط البيانات التي سيتم استيرادها. يجب أن يكون هذا الملف في الدليل نفسه حيث الملف الذي سيتم استيراده.
- لديك إذن [المسؤول](permissions.md#administrator).

## <a name="configuration"></a>التكوين

1. انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.

1. على الإطار المتجانب **الاستيراد المخصص لبروتوكول SFTP‬**، حدد **إثراء بياناتي**.

   > [!div class="mx-imgBorder"]
   > ![الإطار المتجانب الاستيراد المخصص لبروتوكول SFTP](media/SFTP_Custom_Import_tile.png "الإطار المتجانب الاستيراد المخصص لبروتوكول SFTP")

1. حدد **الشروع في العمل**، وقدم بيانات اعتماد وعنوان خادم SFTP. على سبيل المثال، sftp://mysftpserver.com:22.

1. أدخل اسم الملف الذي يحتوي على البيانات والمسار إلى الملف على خادم SFTP إذا لم يكن موجودًا في المجلد الجذر.

1. أكد كافة الإدخالات من خلال تحديد **الاتصال بالاستيراد المخصص**.

   > [!div class="mx-imgBorder"]
   > ![القائمة المنبثقة تكوين الاستيراد المخصص لبروتوكول SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "القائمة المنبثقة تكوين الاستيراد المخصص لبروتوكول SFTP")

## <a name="defining-field-mappings"></a>تعريف تعيينات الحقول 

يجب أن يحتوي الدليل الذي يحتوي على الملف الذي سيتم استيراده على خادم SFTP على ملف *model.json*. يحدد هذا الملف المخطط الذي سيتم استخدامه لاستيراد البيانات. يجب على المخطط استخدام [نموذج البيانات العامة](https://docs.microsoft.com/common-data-model/) لتحديد تعيين الحقول. مثال بسيط لملف model.json يبدو كما يلي:

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

## <a name="enrichment-results"></a>نتائج الإثراء

لبدء عملية الإثراء، حدد **تشغيل** من شريط الأوامر. يمكنك أيضًا السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من [التحديث المجدول](system.md#schedule-tab). سيعتمد وقت المعالجة على حجم البيانات التي سيتم استيرادها والاتصال بخادم SFTP.

بعد اكتمال عملية الإثراء، يمكنك مراجعة بيانات الإثراء المخصصة التي قمت باستيرادها مؤخرًا أسفل **عمليات الإثراء الخاصة بي‬**. بالإضافة إلى ذلك ، ستجد وقت التحديث الأخير وعدد ملفات التعريف التي تم إثراؤها.

يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.

## <a name="next-steps"></a>الخطوات التالية

قم بالبناء أعلى بيانات العملاء التي تم إثرائها. أنشئ [شرائح](segments.md) و[مقاييس](measures.md)، و[صدّر البيانات](export-destinations.md) لتقديم تجارب مخصصة لعملائك.


