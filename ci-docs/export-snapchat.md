---
title: تصدير المقاطع إلى Snapchat (إصدار أولي)
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195366"
---
# <a name="export-segments-to-snapchat-preview"></a>تصدير المقاطع إلى Snapchat (إصدار أولي)

قم بتصدير مقاطع ملفات تعريف العملاء الموحدة إلى Snapchat واستخدامها في الإعلانات.

## <a name="prerequisites"></a>المتطلبات

- [حساب Snapchat Business](https://business.snapchat.com/)، و[حساب Snapchat Ads](https://ads.snapchat.com/)، وبيانات اعتماد المسؤول المقابلة. يجب أن تكون عضوًا في حساب مؤسسة ومدير بيانات على الأقل لحساب إعلانات معين.
- جمهور واحد على الأقل في Snapchat Audience Manager من النوع SAM (Snap Audience Match).
- [معرف مقطع/جمهور Snapchat](https://businesshelp.snapchat.com/s/article/custom-audiences). يمكن العثور على معرف الجمهور في عنوان URL بعد تحديد الجمهور في Snapchat Audience Manager.
- [مقاطع مُكونة](segments.md) في Customer Insights.
- تحتوي ملفات تعريف العملاء الموحدة في المقاطع المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- ما يصل إلى مليون ملف تعريف عميل، ويمكن أن تستغرق هذا العدد ما يصل إلى 15 دقيقة لإكماله.
- المقاطع فقط.

## <a name="set-up-connection-to-snapchat"></a>إعداد الاتصال بـ Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Snapchat**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **اتصال** لتهيئة الاتصال.

1. حدد **المصادقة مع Snapchat** ووفر بيانات اعتماد المسؤول الخاصة بك لـ Snapchat.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Snapchat. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. أدخل **معرف مقطع/جمهور Snapchat**.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
