---
title: تصدير بيانات Customer Insights إلى RollWorks
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760458"
---
# <a name="export-segment-lists-to-rollworks-preview"></a>تصدير قوائم الشرائح إلى RollWorks (إصدار أولي)

قم بتصدير شرائح ملفات تعريف العملاء الموحدة إلى RollWorks واستخدامها في الإعلانات. 

## <a name="prerequisites-for-a-connection"></a>المتطلبات الأساسية لاتصال

-   لديك [حساب RollWorks](https://www.rollworks.com/) وبيانات اعتماد المسؤول المقابلة.
-   لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- يمكنك تصدير حتى 250000 ملف تعريف لكل تصدير إلى RollWorks.
- لا يمكنك تصدير الشرائح التي يقل عدد ملفات تعريفها عن 100 ملف تعريف إلى RollWorks. 
- يقتصر التصدير إلى RollWorks على الشرائح.
- يمكن أن يستغرق تصدير ما يصل إلى 250 ألف ملف تعريف إلى RollWorks ما يصل إلى 10 دقائق حتى يكتمل. 
- عدد الملفات الشخصية التي يمكنك تصديرها إلى RollWorks يعتمد ويقتصر على عقدك مع RollWorks.

## <a name="set-up-connection-to-rollworks"></a>إعداد الاتصال بـ RollWorks

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **RollWorks** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **الاتصال** لبدء الاتصال بـ RollWorks.

1. حدد **المصادقة مع RollWorks** ووفر بيانات اعتماد المسؤول الخاصة بك لـ RollWorks.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم RollWorks. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. أدخل **معرف معلن RollWorks** [RollWorks للإعلان](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل. يلزم تصدير شرائح إلى RollWorks.

1. حدد الشرائح التي تريد تصديرها. حدد شريحة تتضمن 100 عضو على الأقل. لا يمكنك تصدير شرائح أصغر. بالإضافة إلى ذلك، فإن الحد الأقصى لحجم شريحة ما لتصديرها هو ‎250'000 عضو لكل عملية تصدير. 

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لنقل البيانات إلى RollWorks، فأنت تسمح بنقل البيانات خارج حدود الامتثال لـ Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات بموجب الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان ووفاء RollWorks بأي خصوصية أو التزامات أمنية قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.