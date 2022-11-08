---
title: تصدير مقاطع إلى Marketo (إصدار أولي)
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724924"
---
# <a name="export-segments-to-marketo-preview"></a>تصدير مقاطع إلى Marketo (إصدار أولي)

يمكنك تصدير المقاطع ملفات تعريف العملاء الموحدة لإنشاء الحملات وتقديم تسويق عبر البريد الإلكتروني واستخدام مجموعات محددة من العملاء باستخدام Marketo.

## <a name="prerequisites"></a>المتطلبات

- [حساب Marketo](https://login.marketo.com/) وبيانات اعتماد مسؤول مطابقة.
- [معرف عميل Marketo، وسر العميل واسم مضيف نقطة نهاية REST](https://developers.marketo.com/rest-api/authentication/).
- [قوائم موجودة في Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) والمعرفات المناظرة.
- [المقاطع المكونة](segments.md).
- تحتوي ملفات تعريف العملاء الموحدة في المقاطع المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>الحدود المعروفة

- الارتباط الخاص بالإضافة إلى إحضار مساحة التخزين الخاصة بك (BYOS) غير مدعوم.
- ما يصل إلى مليون ملف تعريف عميل لكل عملية تصدير إلى Marketo، والتي يمكن أن تستغرق ما يصل إلى 3 ساعات. يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى Marketo على عقدك مع Marketo.
- المقاطع فقط.

## <a name="set-up-connection-to-marketo"></a>إعداد الاتصال بـ Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Marketo**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **معرف عميل Marketo، وسر العميل واسم مضيف نقطة نهاية REST**. اسم المضيف نقطة النهاية REST هو اسم المضيف فقط، بدون https://. مثال: xyz-abc-123.mktorest.com.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **اتصال** لتهيئة الاتصال.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Marketo. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. أدخل **معرف قائمة Marketo** الخاص بك. معرف القائمة هو قيمة رقمية خالصة. على سبيل المثال، إذا كان معرف قائمة Marketo هو ST12345A7، فأزل الحرف قبل الأرقام وبعدها وأدخل *12345*.

1. في قسم **مطابقة البيانات**، حدد حقلاً واحدًا على الأقل يمثل عنوان البريد الإلكتروني للعميل أو معرف Marketo الخاص بالعميل.

1. بشكل اختياري، قم بتصدير **الاسم الأول**، و **اسم العائلة**، و **المدينة**، و **الحالة**، و **البلد/المنطقة** لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة. حدد **إضافة سمة** لتعيين هذه الحقول.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

في Marketo، يمكنك الآن البحث عن المقاطع أسفل [قوائم Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
