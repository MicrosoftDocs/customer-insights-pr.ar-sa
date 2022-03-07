---
title: تصدير بيانات Customer Insights إلى Constant Contact
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 30dfe4d6c2374ba9979827ea70a71c52a1334b45dd3e36ccb1de90fae0c61ad9
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031825"
---
# <a name="export-segments-to-constant-contact-preview"></a>تصدير الشرائح إلى Constant Contact (إصدار أولي)

قم بتصدير شرائح ملفات تعريف العملاء الموحدة إلى Constant Contact واستخدامها في أنشطة التسويق. 

## <a name="prerequisites-for-a-connection"></a>المتطلبات الأساسية لاتصال

-   لديك [حساب Constant Contact](https://www.constantcontact.com/account-home) وبيانات اعتماد المسؤول المقابلة.
-   لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- يمكنك تصدير حتى 1 مليوت ملف تعريف لكل تصدير إلى Constant Contact.
- يقتصر التصدير إلى Constant Contact على الشرائح.
- قد يستغرق تصدير ما يصل إلى مليون ملف تعريف إلى Constant Contact ما يصل إلى 1 ساعة حتى الاكتمال. 
- عدد الملفات الشخصية التي يمكنك تصديرها إلى Constant Contact يعتمد ويقتصر على عقدك مع Constant Contact.

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

1. في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل. يلزم تصدير شرائح إلى Constant Contact.

1. بشكل اختياري، يمكنك تصدير الاسم الأول واسم العائلة كحقول إضافية لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة. حدد **إضافة سمة** لتعيين هذه الحقول.

1. حدد الشرائح التي تريد تصديرها.

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لنقل البيانات إلى Constant Contact، فأنت تسمح بنقل البيانات خارج حدود الامتثال لـ Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات بموجب الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان ووفاء Constant Contact بأي خصوصية أو التزامات أمنية قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.
