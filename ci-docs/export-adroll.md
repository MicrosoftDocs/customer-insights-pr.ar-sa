---
title: تصدير بيانات Customer Insights إلى AdRoll
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى AdRoll.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ec7d2d4d137f2f0e3e1ff2ec0d09bff8ac4f28ea
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645479"
---
# <a name="export-segments-to-adroll-preview"></a>تصدير الشرائح إلى AdRoll (إصدار أولي)

يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة إلى AdRoll واستخدامها في الإعلانات. 

## <a name="prerequisites-for-a-connection"></a>المتطلبات الأساسية لاتصال

-   لديك [حساب AdRoll](https://www.adroll.com/) وبيانات اعتماد مسؤول مطابقة.
-   لديك [مقاطع مُكونة](segments.md) في Customer Insights.
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- يمكنك تصدير ما يصل إلى 250000 ملف تعريف عميل في وقت واحد إلى AdRoll.
- لا يمكنك تصدير شرائح تحتوي على أقل من 100 ملف تعريف عميل إلى AdRoll. 
- يقتصر التصدير إلى AdRoll على الشرائح.
- يمكن أن يستغرق تصدير ما يصل إلى 250000 ملف تعريف عميل إلى AdRoll ما يصل إلى 10 دقائق حتى يكتمل. 
- يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى AdRoll على عقدك مع AdRoll.

## <a name="set-up-connection-to-adroll"></a>إعداد الاتصال بـ AdRoll

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **AdRoll** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **اتصال** لتهيئة الاتصال بـ AdRoll.

1. حدد **المصادقة مع AdRoll** وقدم بيانات اعتماد المسؤول لـ AdRoll. 

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم AdRoll. إذا لم تشاهد اسم المقطع هذا، فلا توجد اتصالات من هذا النوع متوفرة لك.

1. أدخل **معرف معلن AdRoll**. لمزيد من المعلومات، راجع [ملفات تعريف المعلنين على AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل. يلزم تصدير شرائح إلى AdRoll.

1. حدد الشرائح التي تريد تصديرها. حدد شريحة تتضمن 100 عضو على الأقل. لا يمكنك تصدير شرائح أصغر. بالإضافة إلى ذلك، فإن الحد الأقصى لحجم شريحة ما لتصديرها هو ‎250,000 عضو لكل عملية تصدير. 

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). 

يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى AdRoll، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام AdRoll بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.