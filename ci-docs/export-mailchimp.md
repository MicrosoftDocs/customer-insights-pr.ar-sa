---
title: تصدير المقاطع إلى Mailchimp (إصدار أولي)
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Mailchimp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 54aec10e24b6356e2e4317cf33e740a1a086a2dd
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196838"
---
# <a name="export-segments-to-mailchimp-preview"></a>تصدير المقاطع إلى Mailchimp (إصدار أولي)

يمكنك تصدير مقاطع من ملفات تعريف العملاء الموحدة إلى Mailchimp لإنشاء رسائل إخبارية وحملات بواسطة البريد الإلكتروني.

## <a name="prerequisites"></a>المتطلبات

- [حساب Mailchimp](https://mailchimp.com/) وبيانات اعتماد مسؤول مطابقة.
- [جماهير موجودة في Mailchimp](https://mailchimp.com/help/create-audience/) ومعرفات [الجماهير المناظرة](https://mailchimp.com/help/find-audience-id/).
- [المقاطع المكونة](segments.md).
- تحتوي ملفات تعريف العملاء الموحدة في المقاطع المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- ما يصل إلى مليون ملف تعريف عميل لكل عملية تصدير إلى Mailchimp، والتي يمكن أن تستغرق ما يصل إلى ثلاث ساعات. يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى Mailchimp على عقدك مع Mailchimp.
- المقاطع فقط.

## <a name="set-up-connection-to-mailchimp"></a>إعداد الاتصال بـ Mailchimp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Mailchimp**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **اتصال** لتهيئة الاتصال.

1. حدد **المصادقة مع Mailchimp** وقد بيانات اعتماد Mailchimp.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Mailchimp. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. أدخل **معرف جمهور Mailchimp**.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل.

1. بشكل اختياري، قم بتصدير **الاسم الأول** و **اسم العائلة** لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة. حدد **إضافة سمة** لتعيين هذه الحقول.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
