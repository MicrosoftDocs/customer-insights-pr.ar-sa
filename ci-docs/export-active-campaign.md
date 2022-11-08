---
title: تصدير المقاطع إلى ActiveCampaign
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725384"
---
# <a name="export-segments-to-activecampaign-preview"></a>تصدير مقاطع إلى ActiveCampaign (معاينة)

قم بتصدير مقاطع من ملفات تعريف العملاء الموحدين إلى ActiveCampaign واستخدامها في أنشطة التسويق.

## <a name="prerequisites"></a>المتطلبات

- [حساب ActiveCampaign](https://www.activecampaign.com/) وبيانات اعتماد المسؤول المقابلة.
- [معرف قائمة ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).
- [مفتاح ActiveCampaign API](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) واسم مضيف نقطة نهاية REST.
- [مقاطع مُكونة](segments.md) في Customer Insights.
- تحتوي ملفات تعريف العملاء الموحدة في المقاطع المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>الحدود المعروفة

- الارتباط الخاص بالإضافة إلى إحضار مساحة التخزين الخاصة بك (BYOS) غير مدعوم.
- ما يصل إلى مليون ملف تعريف عميل لكل عملية تصدير إلى ActiveCampaign، والتي قد تستغرق ما يصل إلى 90 دقيقة حتى تكتمل. يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى ActiveCampaign على عقدك مع ActiveCampaign.
- المقاطع فقط.

## <a name="set-up-connection-to-activecampaign"></a>إعداد اتصال بـ ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **ActiveCampaign**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل مفتاح ActiveCampaign API واسم المضيف لنقطة نهاية REST. اسم المضيف نقطة النهاية REST هو اسم المضيف فقط، بدون https://.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **اتصال** لتهيئة الاتصال.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **اتصال للتصدير**، اختر اتصالا من قسم ActiveCampaign. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. أدخل **معرف قائمة ActiveCampaign**.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل.

1. بشكل اختياري، قم بتصدير **الاسم الأول**، و **اسم العائلة**، و **الهاتف**  لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة. حدد **إضافة سمة** لتعيين هذه الحقول.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
