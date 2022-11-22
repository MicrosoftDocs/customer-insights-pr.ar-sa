---
title: تصدير مقاطع إلى Criteo (إصدار أولي)
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 811752da943cd5e40608d48644a1744c7971d3c8
ms.sourcegitcommit: 40ae3322ac95913e485607494754dd03814e42bb
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760010"
---
# <a name="export-segments-to-criteo-preview"></a>تصدير مقاطع إلى Criteo (إصدار أولي)

يمكنك تصدير مقاطع ملفات تعريف عملاء موحدة لإنشاء الحملات، وتقديم حملات التسويق عبر البريد الإلكتروني واستخدام مجموعات محددة من العملاء باستخدام Criteo.

## <a name="prerequisites"></a>المتطلبات

- [حساب إعادة توجيه ديناميكي لـ Criteo](https://www.criteo.com/login/) وبيانات اعتماد المسؤول المقابلة.
- [المقاطع المكونة](segments.md).
- تحتوي ملفات تعريف العملاء الموحدة في المقاطع المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- ما يصل إلى مليون ملف تعريف عميل لكل عملية تصدير إلى Criteo، والتي قد تستغرق ما يصل إلى 30 دقيقة حتى تكتمل. يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى Criteo على عقدك مع Criteo.
- المقاطع فقط.

## <a name="set-up-connection-to-criteo"></a>إعداد اتصال بـ Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Criteo**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **اتصال** لتهيئة الاتصال.

1. حدد **المصادقة مع Criteo** وقدم اسم المستخدم المسؤول وبيانات الاعتماد الخاصة بك لـ Criteo.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Criteo. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
