---
title: تصدير بيانات Customer Insights إلى Constant Contact
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Constant Contact.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 310de0355f71829346f0e35508487e5962d6e912
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645563"
---
# <a name="export-segments-to-constant-contact-preview"></a>تصدير الشرائح إلى Constant Contact (إصدار أولي)

قم بتصدير شرائح ملفات تعريف العملاء الموحدة إلى Constant Contact واستخدامها في أنشطة التسويق. 

## <a name="prerequisites-for-a-connection"></a>المتطلبات الأساسية لاتصال

-   لديك [حساب Constant Contact](https://www.constantcontact.com/account-home) وبيانات اعتماد المسؤول المقابلة.
-   لديك [مقاطع مُكونة](segments.md) في Customer Insights.
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- يمكنك تصدير ما يصل إلى مليون ملف تعريف عميل لكل عملية تصدير إلى Constant Contact.
- يقتصر التصدير إلى Constant Contact على الشرائح.
- يمكن أن يستغرق تصدير ما يصل إلى مليون ملف تعريف عميل إلى Constant Contact ما يصل إلى ساعة واحدة حتى يكتمل. 
- يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى Constant Contact ومحدودًا على عقدك مع Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>إعداد الاتصال بـ Constant Contact

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Constant Contact** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **الاتصال** لبدء الاتصال بـ Constant Contact.

1. حدد **المصادقة مع Constant Contact** ووفر بيانات اعتماد المسؤول الخاصة بك لـ Constant Contact. 

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Constant Contact. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. أدخل [**معرف قائمة Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). افتح قائمة في Constant Contact للعثور على معرف القائمة في URL.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل. يلزم تصدير شرائح إلى Constant Contact.

1. بشكل اختياري، يمكنك تصدير الاسم الأول واسم العائلة كحقول إضافية لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة. حدد **إضافة سمة** لتعيين هذه الحقول.

1. حدد الشرائح التي تريد تصديرها.

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لنقل البيانات إلى Constant Contact، فأنت تسمح بنقل البيانات خارج حدود الامتثال لـ Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات بموجب الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان ووفاء Constant Contact بأي خصوصية أو التزامات أمنية قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.
