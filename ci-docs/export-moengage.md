---
title: تصدير المقاطع إلى MoEngage
description: تعرف على كيفية تكوين الاتصال والتصدير إلى MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199064"
---
# <a name="export-segments-to-moengage-preview"></a>تصدير مقاطع إلى MoEngage (إصدار أولي)

يمكنك تصدير مقاطع من ملفات تعريف العملاء الموحدة‬ إلى MoEngage واستخدامها في الحملات والتسويق عبر البريد الإلكتروني في MoEngage.

## <a name="prerequisites-for-a-connection"></a>المتطلبات الأساسية لاتصال

- [حساب MoEngage](https://www.moengage.com/) وبيانات اعتماد المسؤول المطابقة.
- مفتاح MoEngage API من الإعدادات > API في MoEngage.
- [مقاطع مُكونة](segments.md) في Customer Insights.

## <a name="known-limitations"></a>القيود المعروفة

- ما يصل إلى 100000 ملف تعريف عميل لكل عملية تصدير إلى MoEngage، والتي يمكن أن تستغرق ما يصل إلى 15 دقيقة. يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى MoEngage على عقدك مع MoEngage.
- المقاطع فقط.

## <a name="set-up-connection-to-moengage"></a>إعداد الاتصال بـ MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **"إضافة اتصال** واختر **MoEngage** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل [مفتاح API ومعرف API لبيانات MoEngage](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **الاتصال** لبدء الاتصال بـ MoEngage.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء عملية تصدير جديدة، حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم MoEngage. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل. كرر نفس الخطوات للحقول الاختيارية الأخرى.

1. حدد المقاطع التي تريد تصديرها. سننشئ مقطع واحدة أو أكثر بنفس اسم المقاطع المحددة في MoEngage ضمن **المقاطع** > **المقاطع المخصصة**.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
