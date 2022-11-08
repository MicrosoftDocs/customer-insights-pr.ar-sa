---
title: تصدير المقاطع إلى Campaign Monitor (إصدار أولي)
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Campaign Monitor.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 82303c7bcb269ee68419c9639ee743e13451f273
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724532"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>تصدير المقاطع إلى Campaign Monitor (إصدار أولي)

قم بتصدير مقاطع ملفات تعريف العملاء الموحدة إلى Campaign Monitor واستخدامها في أنشطة التسويق.

## <a name="prerequisites"></a>المتطلبات

- [حساب Campaign Monitor](https://www.campaignmonitor.com/) وبيانات اعتماد المسؤول المقابلة.
- [معرف قائمة Campaign Monitor](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- [مفتاح API الذي تم إنشاؤه](https://www.campaignmonitor.com/api/getting-started/) من **إعدادات الحساب** في Campaign Monitor للحصول على معرف قائمة API.
- [مقاطع مُكونة](segments.md) في Customer Insights.
- تحتوي ملفات تعريف العملاء الموحدة في المقاطع المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>الحدود المعروفة

- الارتباط الخاص بالإضافة إلى إحضار مساحة التخزين الخاصة بك (BYOS) غير مدعوم.
- ما يصل إلى مليون ملف تعريف عميل لكل عملية تصدير إلى Campaign Monitor، والتي قد تستغرق ما يصل إلى 20 دقيقة حتى تكتمل. يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى Campaign Monitor على عقدك مع Campaign Monitor.
- المقاطع فقط.

## <a name="set-up-connection-to-campaign-monitor"></a>إعداد الاتصال بـ Campaign Monitor

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Campaign Monitor**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **الاتصال** لبدء الاتصال بـ Campaign Monitor.

1. حدد **المصادقة مع Campaign Monitor** ووفر بيانات اعتماد المسؤول الخاصة بك لـ Campaign Monitor.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء عملية تصدير جديدة، حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Campaign Monitor. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. أدخل **معرف قائمة Campaign Monitor**.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل. يلزم تصدير مقاطع إلى Campaign Monitor.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
