---
title: تصدير بيانات Customer Insights إلى Iterable
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 714a1323521be7d2f29ccaacd7799b2174e2937d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645573"
---
# <a name="export-segment-lists-to-iterable-preview"></a>تصدير قوائم المقاطع إلى Iterable (إصدار أولي)

تصدير مقاطع من Unified Customer Profiles إلى Iterable واستخدامها في أنشطة التسويق.

## <a name="prerequisites"></a>المتطلبات

-   لديك [حساب Iterable](https://iterable.com/) وبيانات اعتماد المسؤول المطابقة.
-   لديك [مقاطع مُكونة](segments.md) في Customer Insights.
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- يقتصر التصدير إلى Iterable على المقاطع.
- يمكن أن يستغرق تصدير ما يصل إلى مليون ملف تعريف عميل إلى Iterable ما يصل إلى 30 دقيقة حتى يكتمل. 
- عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى Iterable يعتمد ويقتصر على عقدك مع Iterable.

## <a name="set-up-connection-to-iterable"></a>إعداد اتصال بـ Iterable

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **"إضافة اتصال** واختر **Iterable** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. قم بتوفير [مفتاح Iterable API](https://support.iterable.com/hc/en-us/articles/360043464871) للمتابعة لتسجيل الدخول. 

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **اتصال** لبدء الاتصال بـ Iterable.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Iterable. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

3. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل. من المطلوب تصدير مقاطع إلى Iterable. ستتلقى القائمة التي تم إنشاؤها في Iterable نفس اسم المقطع الخاص بك في Dynamics 365 Customer Insights.

1. حدد **حفظ.**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Iterable، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات بناءً على التعليمات الخاصة بك ، ولكنك مسؤول عن ضمان أن يفي Iterable بأي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.