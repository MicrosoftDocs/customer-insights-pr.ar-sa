---
title: تصدير مقاطع إلى Microsoft Advertising (إصدار أولي)
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196516"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>تصدير مقاطع إلى Microsoft Advertising (إصدار أولي)

يمكنك تصدير مقاطع Customer Insights إلى Microsoft Advertising لإنشاء جماهير Customer Match. استخدم مقاطع الجمهور هذه لحملاتك الإعلانية.

## <a name="prerequisites"></a>المتطلبات

- [حساب Microsoft Advertising](https://ads.microsoft.com/) وبيانات اعتماد المسؤول المقابلة.
- معرف العميل ومعرف الحساب لـ Microsoft Advertising. ابحث عن معرف العميل (`cid`) ومعرف الحساب (`aid`) في معلمات عنوان URL عندما تسجل دخولك إلى Microsoft Advertising.
- تم قبول شروط استخدام Customer Match.
- [مقاطع مُكونة](segments.md) في Customer Insights.
- تحتوي ملفات تعريف العملاء الموحدة في المقاطع المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- ما يصل إلى 500000 ملف تعريف عميل لكل عملية تصدير إلى Microsoft Advertising، والتي يمكن أن تستغرق ما يصل إلى 10 دقائق.
- المقاطع فقط.

## <a name="set-up-connection-to-microsoft-advertising"></a>إعداد الاتصال بـ Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Microsoft Advertising**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. الإعداد الافتراضي هو "المسؤولون". لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **معرف عميل Microsoft Advertising**.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **اتصال** لتهيئة الاتصال.

1. حدد **المصادقة مع Microsoft Advertising** وقدم بيانات اعتماد المسؤول الخاصة بك لـ Microsoft Advertising.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Microsoft Advertising. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. حدد المقاطع التي تريد تصديرها. يتم إنشاء جماهير Customer Match في Microsoft Advertising بشكل تلقائي باسم المقاطع المحددة للتصدير. سينتج عن كل مقطع جمهور منفصل لـ Customer Match.

1. أدخل **معرف العميل ومعرف الحساب لـ Microsoft Advertising**.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل بعنوان البريد الإلكتروني للعميل.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
