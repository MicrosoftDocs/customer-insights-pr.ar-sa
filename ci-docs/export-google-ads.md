---
title: تصدير مقاطع إلى Google Ads (إصدار أولي)
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725062"
---
# <a name="export-segments-to-google-ads-preview"></a>تصدير مقاطع إلى Google Ads (إصدار أولي)

تصدير أجزاء من الملفات الشخصية الموحدة للعملاء إلى قائمة جمهور Google Ads واستخدامها للإعلان على بحث Google و Gmail وYouTube وشبكة عرض Google.

## <a name="prerequisites"></a>المتطلبات

- [حساب Google Ads](https://ads.google.com/) وبيانات اعتماد مسؤول مقابلة.
- [معرف عميل Google Ads](https://support.google.com/google-ads/answer/1704344).
- تم الوفاء بمتطلبات [سياسة Customer Match](https://support.google.com/adspolicy/answer/6299717).
- تم الوفاء بمتطلبات [أحجام قائمة تجديد النشاط التسويقي](https://support.google.com/google-ads/answer/7558048).
- [المقاطع المكونة](segments.md).
- تحتوي ‏‫Unified Customer Profiles‬ في المقاطع التي تم تصديرها على حقول تمثل عنوان البريد الإلكتروني أو الهاتف أو معرف معلن الجوال أو معرف مستخدم الطرف الثالث أو العنوان.

## <a name="known-limitations"></a>الحدود المعروفة

- الارتباط الخاص بالإضافة إلى إحضار مساحة التخزين الخاصة بك (BYOS) غير مدعوم.
- قم بتصدير ما يصل إلى مليون ملف تعريف عميل لكل عملية تصدير إلى Google Ads، والتي قد تستغرق ما يصل إلى 30 دقيقة حتى تكتمل بسبب القيود من جانب المزود.
- المقاطع فقط.
- قد تستغرق المطابقة في Google Ads ما يصل إلى 48 ساعة.

## <a name="set-up-connection-to-google-ads"></a>إعداد الاتصال بGoogle Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Google Ads**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل معرف عميل Google Ads.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **المصادقة مع Google Ads** وقد بيانات اعتماد Google Ads.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Google Ads. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. اختر ما إذا كنت تريد استخدام جمهور حالي أو إنشاء جمهور جديد:
   - لتحديث جمهور Google Ads موجود، أدخل [معرف جمهور Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - لإنشاء جمهور جديد، اترك حقل معرف جمهور Google فارغًا. سيقوم Customer Insights تلقائيًا بإنشاء جمهور جديد في حساب Google Ads واستخدام اسم المقطع الذي تم تصديره.

1. في مقطع **مطابقة البيانات**، حدد حقل بيانات واحدًا أو أكثر لتصديره، وحدد الحقل الذي يمثل حقول البيانات المقابلة في Customer Insights.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
