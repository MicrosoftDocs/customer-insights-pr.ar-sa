---
title: تصدير المقاطع إلى Braze (إصدار أولي)
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725200"
---
# <a name="export-segments-to-braze-preview"></a>تصدير المقاطع إلى Braze (إصدار أولي)

تصدير مقاطع من Unified Customer Profiles إلى Braze واستخدامها في أنشطة التسويق.

## <a name="prerequisites"></a>المتطلبات

- [حساب Braze](https://www.braze.com/) وبيانات اعتماد المسؤول المطابقة.
- [مفتاح Braze API](https://www.braze.com/docs/api/basics/)
- [نقطة نهاية Braze REST](https://www.braze.com/docs/api/basics/#api-definitions) الخاصة بك 
- [مقاطع مُكونة](segments.md) في Customer Insights.
- تحتوي Unified customer profiles في المقاطع التي تم تصديرها على حقل يمثل عنوان بريد إلكتروني ومعرف عميل Braze.

## <a name="known-limitations"></a>الحدود المعروفة

- الارتباط الخاص بالإضافة إلى إحضار مساحة التخزين الخاصة بك (BYOS) غير مدعوم.
- ما يصل إلى مليون ملف تعريف عميل لـ Braze، والتي يمكن أن تستغرق ما يصل إلى 40 دقيقة لإكمالها. يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى Braze على عقدك مع Braze.
- المقاطع فقط.
- لا يتم دعم Azure Private Link لتصدير Braze.

## <a name="set-up-connection-to-braze"></a>إعداد اتصال بـ Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Braze**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. قم بتوفير مفتاح Braze API للمتابعة لتسجيل الدخول.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **اتصال** لتهيئة الاتصال.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Braze. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. أدخل نقطة نهاية REST في حقل **Hostname** بالتنسيق التالي: `rest.iad-03.braze.com`.

1. إدخال اسمًا للتصدير.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل. في الحقل **معرف العميل**، حدد الحقل الذي يمثل معرف Braze للعميل. سيتم إنشاء المقاطع في Braze بنفس اسم المقطع كما في Dynamics 365 Customer Insights. يمكنك اختيار حقول إضافية اختيارية لمطابقة البيانات.

1. حدد الكيانات أو المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
