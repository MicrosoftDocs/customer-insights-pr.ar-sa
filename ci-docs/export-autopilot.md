---
title: تصدير مقاطع إلى Autopilot (إصدار أولي)
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى إعلانات Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 449d2c5e32697e4a5d2c9dff4a5a1cbdb26aeb4d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195044"
---
# <a name="export-segments-to-autopilot-preview"></a>تصدير مقاطع إلى Autopilot (إصدار أولي)

يمكنك تصدير مقاطع من ملفات تعريف العملاء الموحدة‬ إلى Autopilot واستخدامها في الحملات والتسويق عبر البريد الإلكتروني في Autopilot.

## <a name="prerequisites-for-a-connection"></a>المتطلبات الأساسية لاتصال

- [حساب Autopilot](https://www.autopilothq.com/) وبيانات اعتماد مسؤول مقابلة.
- [مفتاح Autopilot API](https://autopilot.docs.apiary.io/#)
- [مقاطع مُكونة](segments.md) في Customer Insights.
- تحتوي ملفات تعريف العملاء الموحدة في المقاطع المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- ما يصل إلى 100000 ملف تعريف عميل لكل عملية تصدير إلى الطيار الآلي، والتي يمكن أن تستغرق ما يصل إلى بضع ساعات حتى تكتمل. يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى Autopilot على عقدك مع Autopilot.
- المقاطع فقط.

## <a name="set-up-connection-to-autopilot"></a>إعداد الاتصال بـ Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Autopilot**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل مفتاح واجهة برمجة تطبيقات Autopilot.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **اتصال** لتهيئة الاتصال.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Autopilot. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل.

1. بشكل اختياري، يمكن تصدير حقول أخرى مثل **الاسم الأول** و **اسم العائلة**.

1. حدد الأجزاء التي تريد تصديرها باتباع القيود المعروفة.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
