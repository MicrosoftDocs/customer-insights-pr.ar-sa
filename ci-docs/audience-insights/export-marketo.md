---
title: تصدير بيانات Customer Insights إلى Marketo
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0d5eaa769973c861d89287bba0ed29509ab2efc653bdd8e177cc49b3560c698e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033477"
---
# <a name="export-segments-to-marketo-preview"></a>تصدير شرائح إلى Marketo (إصدار أولي)

يمكنك تصدير الشرائح ملفات تعريف العملاء الموحدة لإنشاء الحملات وتقديم تسويق عبر البريد الإلكتروني واستخدام مجموعات محددة من العملاء باستخدام Marketo.

## <a name="prerequisites-for-connection"></a>المتطلبات الأساسية للاتصال

-   لديك [حساب Marketo](https://login.marketo.com/) وبيانات اعتماد مسؤول مطابقة.
-   هناك قوائم موجودة في Marketo والمعرفات المناظرة. لمزيد من المعلومات، راجع [قوائم Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   لقد قمت [بتكوين الشرائح](segments.md).
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- حتى مليون من ملفات التعريف لكل تصدير إلى Marketo.
- يقتصر التصدير إلى Marketo على الشرائح.
- تستغرق عملية تصدير الشرائح التي تتضمن مليون ملف تعريف بشكل إجمالي حتى 3 ساعات. 
- يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى Marketo على العقد مع Marketo، وهذا العدد مقيد بالعقد.

## <a name="set-up-connection-to-marketo"></a>إعداد الاتصال بـ Marketo

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Marketo** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **[معرف عميل Marketo، وسر العميل واسم مضيف نقطة نهاية REST](https://developers.marketo.com/rest-api/authentication/)**. اسم المضيف نقطة النهاية REST هو اسم المضيف فقط، بدون `https://`. مثال:`xyz-abc-123.mktorest.com`. 

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬** وحدد **اتصال** لتهيئة الاتصال بـ Marketo.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Marketo. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. أدخل **[معرف قائمة Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** الخاص بك. معرف القائمة هو قيمة رقمية خالصة. على سبيل المثال، إذا كان معرف قائمة Marketo هو ST12345A7، فأزل الحرف قبل الأرقام وبعدها وأدخل `12345`. 

1. في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل. 

1. بشكل اختياري، يمكنك تصدير **الاسم الأول**، و **اسم العائلة**، و **المدينة**، و **الحالة**، و **البلد/المنطقة** لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة. حدد **إضافة سمة** لتعيين هذه الحقول.

1. حدد الشرائح التي تريد تصديرها. يمكنك تصدير ما يصل إلى مليون من ملفات تعريف العملاء إلى Marketo.

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). في Marketo، يمكنك الآن البحث عن الشرائح أسفل [قوائم Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Marketo، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Marketo بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
