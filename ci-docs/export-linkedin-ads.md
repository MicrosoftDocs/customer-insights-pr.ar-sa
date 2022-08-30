---
title: تصدير مقاطع إلى إعلانات LinkedIn (إصدار أولي)
description: تعرف على كيفية تكوين الاتصال والتصدير إلى إعلانات LinkedIn.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304687"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>تصدير مقاطع إلى إعلانات LinkedIn (إصدار أولي)

يمكنك تصدير مقاطع ملفات تعريف العملاء الموحدة إلى إعلانات LinkedIn لإنشاء مقاطع جمهور مطابقة. استخدم مقاطع الجمهور المطابقة لاستهداف الشركات واستهداف جهات الاتصال.

## <a name="prerequisites"></a>المتطلبات

- [حساب LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) وبيانات اعتماد المسؤول المقابلة.
- [معرف حساب LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).
- [مقاطع مُكونة](segments.md) في Customer Insights.
- تحتاج الأجزاء التي تم تصديرها إلى حقل محدد واحد على الأقل بناءً على ما إذا كنت تختار [استهداف جهات الاتصال](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) أو [استهداف الشركة](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) على LinkedIn. يتم سرد الحقول المحتملة في خطوة **مطابقة البيانات** عند [تكوين التصدير](#configure-an-export).

## <a name="known-limitations"></a>الحدود المعروفة

- ما يصل إلى 100,000 ملف تعريف عميل لكل عملية تصدير إلى LinkedIn Ads، والتي قد تستغرق ما يصل إلى 10 دقائق حتى تكتمل.
- المقاطع فقط. يجب أن تحتوي المقطع على 300 ملف تعريف فريد على الأقل.

## <a name="set-up-connection-to-linkedin-ads"></a>إعداد الاتصال بـ LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **LinkedIn Ads**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. قدم معرف حساب LinkedIn Campaign Manager.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **اتصال** لتهيئة الاتصال.

1. حدد **المصادقة مع LinkedIn** وقدم بيانات اعتماد المسؤول لـ LinkedIn Campaign Manager.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم إعلانات LinkedIn. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. اختر ما إذا كنت تريد تصدير البيانات من أجل [استهداف جهات الاتصال](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) أو [استهداف الشركات](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) على LinkedIn.

1. في قسم **مطابقة البيانات** لاستهداف جهات الاتصال، حدد حقلًا واحدًا على الأقل يمثل عنوان البريد الإلكتروني للعميل، إعلان Apple ID أو Google Ad ID أو Google User ID أو الاسم الأول والأخير. إذا اخترت استهداف الشركة، فحدد حقلًا واحدًا على الأقل يمثل اسم الشركة أو مجال البريد الإلكتروني أو عنوان URL لصفحة LinkedIn أو رمز الأسهم أو موقع الويب.

1. بشكل اختياري، أضف الحقول لتعريف التصدير بشكل أكبر. حدد **إضافة سمة** لتعيين هذه الحقول.

1. حدد المقاطع التي تريد تصديرها. سيتم إنشاء مقاطع الجمهور المطابقة في LinkedIn Campaign Manager بشكل تلقائي باسم المقاطع التي حددتها للتصدير. سينتج عن كل مقطع جمهور مطابق منفصل.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
