---
title: الاتصال بالبيانات في مستودع بيانات مُدار في Microsoft Dataverse
description: استيراد البيانات من مخزن البيانات المُدار بواسطة Microsoft Dataverse.
ms.date: 07/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: b21150a1c51bdad35250cae7fde7f38a014ec876
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/28/2022
ms.locfileid: "9206937"
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

[!INCLUDE [footer-include](includes/footer-banner.md)]
