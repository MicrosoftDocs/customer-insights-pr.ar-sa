---
title: إثراء ملفات تعريف العملاء مع ‏‫استيراد مخصص عبر SFTP‬ (إصدار أولي)
description: معلومات عامة حول إثراء البيانات باستخدام الاستيراد المخصص لبروتوكول SFTP‬‬
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 88fc366ab9478c3b67034af794e237ff4573da7c
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080725"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>إثراء ملفات تعريف العملاء مع ‏‫استيراد مخصص عبر SFTP‬ (إصدار أولي)

يتيح لك الاستيراد المخصص لبروتوكول نقل الملفات الآمن (SFTP)‬ استيراد البيانات التي ليست بحاجة إلى المرور عبر عملية توحيد البيانات. إنها عملية آمنة ومرنة وسهلة لإحضار بياناتك. يمكن استخدام الاستيراد المخصص لبروتوكول SFTP بالتزامن مع [تصدير SFTP](export-sftp.md) الذي يتيح لك تصدير بيانات ملفات تعريف العملاء المطلوبة للإثراء. يمكن بعد ذلك معالجة البيانات وإثرائها، ويمكن استخدام استيراد SFTP المخصص لإعادة البيانات المحسنة إلى Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>المتطلبات

- اسم الملف وموقع (مسار) الملف المطلوب استيراده على مضيف SFTP معروف.

- يتوفر ملف *model.json* الذي يحدد مخطط نموذج البيانات العامة للبيانات التي سيتم استيرادها. يجب أن يكون هذا الملف في الدليل نفسه حيث الملف الذي سيتم استيراده.

- تم [تكوين](#configure-the-connection-for-sftp-custom-import) [اتصال](connections.md) SFTP.

## <a name="file-schema-example"></a>مثال عن مخطط ملف

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>تكوين الاتصال لاستيراد SFTP المخصص

يجب أن تكون [المسؤول](permissions.md#admin) في Customer Insights وأن تكون لديك بيانات اعتماد المستخدم وعنوان URL ورقم المنفذ لموقع SFTP الذي تريد استيراد البيانات منه.

1. حدد **إضافة اتصال** عند تكوين عملية إثراء أو انتقل إلى **المسؤول‏‎** > **الاتصالات‏‎** وحدد **إعداد‏‎** على الإطار المتجانب "استيراد مخصص".

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="صفحة تكوين اتصال الاستيراد المخصص.":::

1. أدخل اسماً للاتصال.

1. أدخل اسم مستخدم صالح وكلمة مرور وعنوان URL لاستضافة خادم SFTP الذي توجد البيانات المطلوب استيرادها فيه.

1. راجع [خصوصية البيانات والامتثال](#data-privacy-and-compliance) وقدم الموافقة عليها بتحديد **أوافق**.

1. حدد **التحقق** للتحقق من صحة التكوين ثم حدد **حفظ** .

### <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات باستخدام الاستيراد المخصص، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم Microsoft بنقل مثل هذه البيانات بناءً على تعليماتك، ولكنك مسؤول عن ضمان وفاء البيانات بأي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.

## <a name="configure-the-import"></a>تكوين الاستيراد

1. انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.

1. حدد **إثراء بياناتي** في الإطار المتجانب **استيراد مخصص عبر SFTP‬**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="تجانب الاستيراد المخصص لـ SFTP":::

1. راجع النظرة العامة، ثم حدد **التالي**.

1. حدد الاتصال. اتصل بمسؤول إذا لم يكن أحدهم متوفرًا.

1. حدد **مجموعة بيانات العميل** واختر ملف التعريف أو الشريحة التي ترغب في إثرائها. يقوم كيان *العميل* بإثراء جميع ملفات تعريف عملائك في حين تثري الشريحة فقط ملفات تعريف العملاء الموجودة في تلك الشريحة.

1. حدد **التالي**.

1. أدخل **المسار** و **اسم الملف** لملف البيانات الذي تريد استيراده.

1. حدد **التالي**.

1. قم بتوفير **اسم** للإثراء و **اسم كيان الإخراج**.

1. حدد **حفظ الإثراء** بعد مراجعة اختياراتك.

1. حدد **تشغيل** لبدء عملية المعالجة، أو حدد إغلاق للعودة إلى صفحة **عمليات الإثراء**.

## <a name="view-enrichment-results"></a>عرض نتائج إثراء البيانات

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>الخطوات التالية

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
