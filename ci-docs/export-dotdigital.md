---
title: تصدير المقاطع إلى DotDigital (إصدار أولي)
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى إعلانات DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724970"
---
# <a name="export-segments-to-dotdigital-preview"></a>تصدير المقاطع إلى DotDigital (إصدار أولي)

يمكنك تصدير مقاطع من ملفات تعريف العملاء الموحدة إلى دفاتر عناوين DotDigital واستخدامها للحملات والتسويق بواسطة البريد الإلكتروني ولإنشاء مقاطع العملاء بواسطة DotDigital.

## <a name="prerequisites"></a>المتطلبات

- [حساب DotDigital](https://dotdigital.com/) و[مستخدم API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- معرف DotDigital من دفتر عناوين [جديد](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) أو موجود في DotDigital. يمكن العثور على المعرف في URL عندما تقوم بتحديد وفتح دفتر عناوين.
- [مقاطع مُكونة](segments.md) في Customer Insights.
- تحتوي ملفات تعريف العملاء الموحدة في المقاطع المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>الحدود المعروفة

- الارتباط الخاص بالإضافة إلى إحضار مساحة التخزين الخاصة بك (BYOS) غير مدعوم.
- ما يصل إلى مليون ملف تعريف عميل لكل عملية تصدير إلى DotDigital، والتي قد تستغرق ما يصل إلى ثلاث ساعات حتى تكتمل بسبب القيود من جانب المزود. يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى DotDigital على عقدك مع DotDigital.
- المقاطع فقط.

## <a name="set-up-connection-to-dotdigital"></a>إعداد الاتصال بـ DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **DotDigital**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **اسم مستخدم وكلمة مرور واجهة برمجة تطبيقات DotDigital**.

1. أدخل **معرف دفتر عناوين DotDigital**.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **اتصال** لتهيئة الاتصال.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم DotDigital. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل.

1. بشكل اختياري، قم بتصدير **الاسم الأول**، و **اسم العائلة**، و **الاسم الكامل**، و **النوع**، و **الرمز البريدي**.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

في DotDigital، ابحث عن المقاطع في [دفاتر عناوين DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
