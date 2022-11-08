---
title: تصدير المقاطع إلى Iterable (إصدار أولي)
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 69e2bd207c98fc2530620018bf95dd869d1798f6
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724465"
---
# <a name="export-segments-to-iterable-preview"></a>تصدير المقاطع إلى Iterable (إصدار أولي)

تصدير مقاطع من Unified Customer Profiles إلى Iterable واستخدامها في أنشطة التسويق.

## <a name="prerequisites"></a>المتطلبات

- [حساب Iterable](https://iterable.com/) وبيانات اعتماد المسؤول المقابلة.
- [مفتاح Iterable API](https://support.iterable.com/hc/en-us/articles/360043464871)
- [مقاطع مُكونة](segments.md) في Customer Insights.
- تحتوي ملفات تعريف العملاء الموحدة في المقاطع المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>الحدود المعروفة

- الارتباط الخاص بالإضافة إلى إحضار مساحة التخزين الخاصة بك (BYOS) غير مدعوم.
- ما يصل إلى مليون ملف تعريف عميل لـ Iterable، والتي يمكن أن تستغرق ما يصل إلى 30 دقيقة لإكمالها. يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى Iterable على عقدك مع Iterable.
- المقاطع فقط.

## <a name="set-up-connection-to-iterable"></a>إعداد اتصال بـ Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Iterable**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. قم بتوفير مفتاح Iterable API للمتابعة لتسجيل الدخول.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **اتصال** لتهيئة الاتصال.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Iterable. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل. ستتلقى القائمة التي تم إنشاؤها في Iterable نفس اسم المقطع الخاص بك في Dynamics 365 Customer Insights.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
