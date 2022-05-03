---
title: إثراء البيانات باستخدام الاستيراد المخصص لبروتوكول SFTP‬
description: معلومات عامة حول إثراء البيانات باستخدام الاستيراد المخصص لبروتوكول SFTP‬‬
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f52d24cbe793bee7948ad2af31059cd3edf40f94
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645462"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>إثراء ملفات تعريف العملاء بواسطة البيانات المخصصة (معاينة)

يتيح لك الاستيراد المخصص لبروتوكول نقل الملفات الآمن (SFTP)‬ استيراد البيانات التي ليست بحاجة إلى المرور عبر عملية توحيد البيانات. إنها عملية آمنة ومرنة وسهلة لإحضار بياناتك. يمكن استخدام الاستيراد المخصص لبروتوكول SFTP بالتزامن مع [تصدير SFTP](export-sftp.md) الذي يتيح لك تصدير بيانات ملفات تعريف العملاء المطلوبة للإثراء. يمكن بعد ذلك معالجة البيانات وإثرائها، ويمكن استخدام استيراد SFTP المخصص لإعادة البيانات المحسنة إلى Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>المتطلبات

لتكوين الاستيراد المخصص لبروتوكول SFTP، يجب استيفاء المتطلبات الأساسية التالية:

- لديك اسم الملف وموقع (المسار) للملف المطلوب استيراده على مضيف SFTP.
- يوجد ملف *model.json* الذي يحدد [خطط نموذج البيانات العامة](/common-data-model/) للبيانات المراد استيرادها. يجب أن يكون هذا الملف في الدليل نفسه حيث الملف الذي سيتم استيراده.
- تم بالفعل تكوين اتصال SFTP بواسطة المسؤول *أو* تحصل على أذونات [المسؤول](permissions.md#admin). سوف تحتاج إلى بيانات اعتماد المستخدم وعنوان URL رقم المنفذ لموقع SFTP حيث تريد استيراد البيانات منه.


## <a name="configure-the-import"></a>تكوين الاستيراد

1. انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.

1. في **تجانب الاستيراد المخصص لـ SFTP**، حدد **إثراء بياناتي** ثم حدد **الشروع في العمل**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="تجانب الاستيراد المخصص لـ SFTP":::

1. حدد [اتصالاً](connections.md) من القائمة المنسدلة. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر. إذا كنت أحد المسؤول، يمكنك إنشاء اتصال عن طريق تحديد **إضاف اتصال** واختيار **استيراد SFTP المخصص** من القائمة المنسدلة.

1. حدد **الاتصال بالاستيراد المخصص** لتأكيد الاتصال المحدد.

1.  حدد **التالي** وأدخل **المسار** و **اسم الملف** الخاصين بملف البيانات الذي تريد استيراده.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="لقطة شاشة عند إدخال موقع البيانات.":::

1. حدد **التالي** واختر مجموعة بيانات العملاء. يمكن أن يكون هذا إما جميع ملفات تعريف العملاء أو مقطعًا.

1. حدد **التالي** وأدخل اسمًا للإثراء واسمًا لكيان الإخراج. 

1. حدد **حفظ الإثراء** بعد مراجعة اختياراتك.

## <a name="configure-the-connection-for-sftp-custom-import"></a>تكوين الاتصال لاستيراد SFTP المخصص 

يلزم أن تكون المسؤول لتكوين الاتصالات. حدد **إضافة اتصال** عند تكوين عملية إثراء *أو* انتقل إلى **المسؤول** > **الاتصالات** وحدد **إعداد** في تجانب الاستيراد المخصص.

1. أدخل اسما للاتصال في مربع **اسم العرض**.

1. أدخل اسم مستخدم صالح وكلمة مرور وعنوان URL لاستضافة خادم SFTP الذي توجد البيانات المطلوب استيرادها فيه.

1. راجع وقدم موافقتك على **خصوصية البيانات والتوافق‬** من خلال تحديد خانة الاختيار **أوافق**.

1. حدد **التحقق** للتحقق من التكوين.

1. بمجرد الانتهاء من التحقق، يمكن حفظ الاتصال بتحديد **حفظ**.

   > [!div class="mx-imgBorder"]
   > ![صفحة تكوين اتصال Experian.](media/enrichment-SFTP-connection.png "صفحة تكوين اتصال Experian")


## <a name="defining-field-mappings"></a>تعريف تعيينات الحقول 

يجب أن يحتوي الدليل الذي يحتوي على الملف الذي سيتم استيراده على خادم SFTP على ملف *model.json*. يحدد هذا الملف المخطط الذي سيتم استخدامه لاستيراد البيانات. يجب أن يستخدم المخطط [Common Data Model](/common-data-model/) لتحديد تعيين الحقل. مثال بسيط لملف model.json يبدو كما يلي:

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

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
