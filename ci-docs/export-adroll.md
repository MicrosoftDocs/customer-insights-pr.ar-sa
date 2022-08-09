---
title: تصدير المقاطع إلى AdRoll (إصدار أولي)
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى AdRoll.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8110eab199920ab8fc2ea15678139faf264a242a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195734"
---
# <a name="export-segments-to-adroll-preview"></a>تصدير المقاطع إلى AdRoll (إصدار أولي)

يمكنك تصدير مقاطع من ملفات تعريف العملاء الموحدة إلى AdRoll واستخدامها في الإعلانات.

## <a name="prerequisites"></a>المتطلبات

- [حساب AdRoll](https://www.adroll.com/) وبيانات اعتماد مسؤول مقابلة.
- [معرف معلن AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [مقاطع مُكونة](segments.md) في Customer Insights.
- تحتوي ملفات تعريف العملاء الموحدة في المقاطع المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- ما يصل إلى 250000 ملف تعريف عميل لكل عملية تصدير إلى AdRoll، والتي قد تستغرق ما يصل إلى 10 دقائق حتى تكتمل. يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى AdRoll على عقدك مع AdRoll.
- المقاطع فقط. يجب أن تحتوي المقطع على 100 ملف تعريف عميل على الأقل.

## <a name="set-up-connection-to-adroll"></a>إعداد الاتصال بـ AdRoll

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **AdRoll**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **اتصال** لتهيئة الاتصال.

1. حدد **المصادقة مع AdRoll** وقدم بيانات اعتماد المسؤول لـ AdRoll.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم AdRoll. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. أدخل **معرف معلن AdRoll**.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
