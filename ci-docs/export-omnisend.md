---
title: تصدير مقاطع إلى Omnisend (إصدار أولي)
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Omnisend.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c23d6d3538c4df6006c14064f95379169af06622
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196148"
---
# <a name="export-segments-to-omnisend-preview"></a>تصدير مقاطع إلى Omnisend (إصدار أولي)

يمكنك تصدير مقاطع ملفات تعريف العملاء الموحدة إلى Omnisend واستخدامها في أنشطة التسويق.

## <a name="prerequisites"></a>المتطلبات

- [حساب Omnisend](https://www.omnisend.com/) وبيانات اعتماد المسؤول المقابلة.
- [مفتاح Omnisend Api](https://support.omnisend.com/en/articles/1061890-generating-api-key).
- [مقاطع مُكونة](segments.md) في Customer Insights.
- تحتوي ملفات تعريف العملاء الموحدة في المقاطع المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- ما يصل إلى مليون ملف تعريف عميل لكل عملية تصدير إلى Omnisend، والتي يمكن أن تستغرق ما يصل إلى أربع ساعات حتى تكتمل. يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى Omnisend على عقدك مع Omnisend.
- المقاطع فقط.

## <a name="set-up-connection-to-omnisend"></a>إعداد الاتصال بـ Omnisend

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Omnisend**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل مفتاح واجهة برمجة تطبيقات Omnisend.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **اتصال** لتهيئة الاتصال.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Omnisend. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل.

1. بشكل اختياري، قم بتصدير **الاسم الأول**، و **اسم العائلة**، و **العنوان**، و **البلد/المنطقة**، و **الولاية**، و **المدينة**، و **الرمز البريدي** لإنشاء رسائل بريد إلكتروني أكثر تخصيصًا. حدد **إضافة سمة** لتعيين هذه الحقول.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
