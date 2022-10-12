---
title: الاتصال بالبيانات في مستودع بيانات مُدار في Microsoft Dataverse
description: استيراد البيانات من مخزن البيانات المُدار بواسطة Microsoft Dataverse.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609775"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>الاتصال بالبيانات في مستودع بيانات مُدار في Microsoft Dataverse

بإمكان مستخدمي Microsoft Dataverse الاتصال بسرعة بالكيانات التحليلية في مستودع Microsoft Dataverse المُدار. بإمكان مصدر بيانات واحد فقط من البيئة استخدام مستودع البيانات المُدار نفسه في Dataverse.

> [!NOTE]
> يجب أن تكون مسؤولاً في مؤسسة Dataverse للمتابعة وعرض قائمة الكيانات المتوفرة في المستودع المُدار.

## <a name="prerequisites"></a>المتطلبات

- قد يتم تخزين البيانات المخزنة في خدمات عبر الإنترنت مثل Azure Data Lake Storage في موقع يختلف عن الموقع حيث تتم معالجة البيانات أو تخزينها في Dynamics 365 Customer Insights. من خلال استيراد البيانات المخزنة في الخدمات عبر الإنترنت أو الاتصال بها، فأنت توافق على نقل هذه البيانات وتخزينها بواسطة Dynamics 365 Customer Insights. [اعرف المزيد في مركز توثيق Microsoft](https://www.microsoft.com/trust-center).

- كيانات Dataverse التي تم [تمكين تعقب التغيير](/power-platform/admin/enable-change-tracking-control-data-synchronization) لها فقط هي المرئية. ويمكن تصدير هذه الكيانات إلى مستودع بيانات مدار لـ Dataverse واستخدامها في Customer Insights. يتم تمكين تعقب التغييرات لجداول Dataverse الجاهزة بشكل افتراضي. يلزم تشغيل تعقب التغييرات للجداول المخصصة. للتحقق من تمكين جداول Dataverse لتعقب التغييرات، انتقل إلى [Power Apps](https://make.powerapps.com) > **البيانات** > **الجداول**. ابحث عن الجدول الذي تهتم به وحدده. انتقل إلى **الإعدادات** > **الخيارات المتقدمة** وراجع إعداد **تعقب التغييرات**.

## <a name="connect-to-a-dataverse-managed-lake"></a>الاتصال بمستودع بيانات مُدار في Dataverse

1. انتقل إلى **البيانات** > **مصادر البيانات**.

1. حدد **إضافة مصدر بيانات**.

1. حدد **Microsoft Dataverse**.

1. أدخل **اسمًا** لمصدر البيانات و **وصفًا** اختياريًا.

1. قم بتوفير **عنوان الخادم** الخاص بمؤسسة Dataverse، وحدد **تسجيل الدخول**.

1. حدد الجداول التي ترغب في استيعابها ككيانات في Customer Insights من القائمة المتاحة.

   > [!NOTE]
   > إذا تم تحديد بعض الجداول بالفعل، فقد يتم استخدامها بواسطة تطبيقات Dynamics 365 أخرى (مثل Dynamics 365 Sales Insights أو Customer Service Insights). لا يمكنك تغيير التحديد. وسوف تتوفر هذه الجداول ككيانات بمجرد إنشاء مصدر البيانات.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="يظهر مربع الحوار قائمة الكيانات في بيئة Dataverse.":::

1. احفظ اختيارك لبدء مزامنة الجداول المحددة من Dataverse. ستعثر على الاتصال المضاف حديثًا في صفحة **مصادر البيانات**. سيتم وضعه في قائمة الانتظار للتحديث وعرض الكيان "عدد" على أنه 0 حتى تتم مزامنة جميع الجداول المحددة.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

قد يستغرق تحميل البيانات وقتا. بعد الانتهاء من التحديث بنجاح، يُمكنك مراجعة البيانات المستوعبة من صفحة [**الكيانات**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>تحرير مصدر البيانات لمستودع بيانات مُدار في Dataverse

يمكنك تحرير تحديد الكيان فقط بعد إنشاء مصدر البيانات. على سبيل المثال، إذا تمت إضافة كيانات اضافيه إلى Dataverse وكنت تريد استيرادها أيضا.
للاتصال Dataverse data lake مختلفة، [قم بإنشاء مجموعة جديدة من مصدر البيانات](#connect-to-a-dataverse-managed-lake).

1. انتقل إلى **البيانات** > **مصادر البيانات**.

1. إلى جانب مصدر البيانات الذي تريد تحديثه، حدد **تحرير**.

1. حدد كيانات إضافية من قائمة الكيانات المتاحة.

1. انقر فوق **حفظ** لتطبيق تغييرات، ثم عد إلى صفحة **مصادر‏‎ البيانات**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>الأسباب الشائعة لأخطاء الاستيعاب أو البيانات التالفة

يتم إجراء عمليات التحقق التالية على البيانات التي تم إدخالها لكشف السجلات التالفة:

- لا تتطابق قيمة الحقل مع نوع بيانات العمود الخاصة به.
- تحتوي الحقول على أحرف تتسبب في عدم تطابق الأعمدة مع المخطط المتوقع. على سبيل المثال: علامات الاقتباس المنسقة بشكل غير صحيح أو علامات الاقتباس التي لم يتم تجاوزها أو أحرف السطر الجديد.
- في حالة وجود أعمدة التاريخ والوقت/التاريخ/datetimeoffset، يجب تحديد تنسيقها في النموذج إذا لم تكن تتبع تنسيق ISO القياسي.

### <a name="schema-or-data-type-mismatch"></a>عدم تطابق المخطط أو نوع البيانات

إذا لم تكن البيانات متوافقة مع المخطط، فيتم تصنيف السجلات على أنها تالفة. صحح إما مصدر البيانات أو المخطط ثم أعد استيعاب البيانات.

### <a name="datetime-fields-in-the-wrong-format"></a>حقول التاريخ والوقت بالتنسيق الخاطئ

حقول التاريخ والوقت في الكيان ليست بتنسيقات ISO أو en-US. تنسيق التاريخ والوقت الافتراضي في Customer Insights هو تنسيق en-US. يجب أن تكون كافة حقول التاريخ والوقت في الكيان بنفس التنسيق. يدعم Customer Insights التنسيقات الأخرى شريطة إنشاء التعليقات أو الخصائص على مستوى المصدر أو الكيان في النموذج أو manifest.json. على سبيل المثال: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  في manifest.json، يمكن تحديد تنسيق التاريخ والوقت على مستوى الكيان أو على مستوى السمة. على مستوى الكيان، استخدم "exhibitsTraits" في الكيان في *.manifest.cdm.json لتحديد تنسيق التاريخ والوقت. على مستوى السمة، استخدم "appliedTraits" في السمة في entityname.cdm.json.

**Manifest.json على مستوى الكيان**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Manifest.json على مستوى السمة**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
