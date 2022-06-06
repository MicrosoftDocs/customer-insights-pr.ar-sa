---
title: الاتصال بالجداول في Microsoft Dataverse
description: استيراد البيانات من مخزن البيانات المُدار بواسطة Microsoft Dataverse.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 7140e9254108bc6f0d518b3ccf4b10fc33cde115
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800142"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>الاتصال بالبيانات في مستودع بيانات مُدار في Microsoft Dataverse

يوفر هذا المقال معلومات حول كيفية اتصال مستخدمي Dataverse بسرعة بالكيانات التحليلية في مستودع مُدار لـ Microsoft Dataverse. 

> [!NOTE]
> يجب أن تكون مسؤولاً في مؤسسة Dataverse للمتابعة وعرض قائمة الكيانات المتوفرة في المستودع المُدار.

## <a name="important-considerations"></a>اعتبارات هامة

1. قد يتم تخزين البيانات المخزنة في خدمات عبر الإنترنت مثل Azure Data Lake Storage في موقع يختلف عن الموقع حيث تتم معالجة البيانات أو تخزينها في Dynamics 365 Customer Insights. من خلال استيراد البيانات المخزنة في الخدمات عبر الإنترنت أو الاتصال بها، فأنت توافق على نقل هذه البيانات وتخزينها بواسطة Dynamics 365 Customer Insights. [اعرف المزيد في مركز توثيق Microsoft](https://www.microsoft.com/trust-center).
2. كيانات Dataverse التي تم [تمكين تعقب التغيير](/power-platform/admin/enable-change-tracking-control-data-synchronization) لها فقط هي المرئية. ويمكن تصدير هذه الكيانات إلى مستودع بيانات مدار لـ Dataverse واستخدامها في Customer Insights. يتم تمكين تعقب التغييرات لجداول Dataverse الجاهزة بشكل افتراضي. يلزم تشغيل تعقب التغييرات للجداول المخصصة. للتحقق من تمكين جداول Dataverse لتعقب التغييرات، انتقل إلى [Power Apps](https://make.powerapps.com) > **البيانات** > **الجداول**. ابحث عن الجدول الذي تهتم به وحدده. انتقل إلى **الإعدادات** > **الخيارات المتقدمة** وراجع إعداد **تعقب التغييرات**.

## <a name="connect-to-a-dataverse-managed-lake"></a>الاتصال بمستودع بيانات مُدار في Dataverse

1. في Customer Insights، انتقل إلى **البيانات** > **مصادر البيانات**.

2. حدد **إضافة مصدر بيانات**.

3. حدد **Microsoft Dataverse** وحدد **التالي**.

4. أدخل **اسمًا** لمصدر البيانات، وحدد **التالي‏‎**. 

5. قم بتوفير **عنوان الخادم** الخاص بمؤسسة Dataverse، وحدد **تسجيل الدخول**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="الشاشة في خطوة استيعاب البيانات حيث يمكن للمستخدم أن يُدخل عنوان URL لبيئة Dataverse.":::

6. حدد الجداول التي ترغب في استيعابها ككيانات في Customer Insights من القائمة المتاحة.    

   > [!NOTE]
   > إذا تم تحديد بعض الجداول بالفعل، فقد يتم استخدامها بواسطة تطبيقات Dynamics 365 أخرى (مثل Dynamics 365 Sales Insights أو Customer Service Insights). لا يمكنك تغيير التحديد. وسوف تتوفر هذه الجداول ككيانات بمجرد إنشاء مصدر البيانات.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="يظهر مربع الحوار قائمة الكيانات في بيئة Dataverse.":::

7. احفظ اختيارك لبدء مزامنة الجداول المحددة من Dataverse. ستعثر على الاتصال المضاف حديثًا في صفحة **مصادر البيانات**. سيتم وضعه في قائمة الانتظار للتحديث وعرض الكيان "عدد" على أنه 0 حتى تتم مزامنة جميع الجداول المحددة.

بإمكان مصدر بيانات واحد فقط من البيئة استخدام مستودع البيانات المُدار نفسه في Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>تحرير مصدر البيانات لمستودع بيانات مُدار في Dataverse

يمكنك تحرير تحديد الكيان فقط بعد إنشاء مصدر البيانات. على سبيل المثال، إذا تمت إضافة كيانات اضافيه إلى Dataverse وكنت تريد استيرادها أيضا.    
للاتصال Dataverse data lake مختلفة، [قم بإنشاء مجموعة جديدة من مصدر البيانات](#connect-to-a-dataverse-managed-lake).

1. انتقل إلى **البيانات** > **مصادر البيانات**.

2. إلى جانب مصدر البيانات الذي تريد تحديثه، حدد علامة القطع الرأسية (&vellip;).

3. حدد الخيار **تحرير** من القائمة.

4. حدد كيانات إضافية من قائمة الكيانات المتاحة وحدد **حفظ**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
