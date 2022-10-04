---
title: تصدير بيانات Customer Insights إلى HubSpot
description: تعرف على كيفية تكوين الاتصال والتصدير إلى HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588896"
---
# <a name="export-segments-to-hubspot-preview"></a>تصدير شرائح إلى HubSpot (إصدار أولي)

يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة‬ إلى HubSpot واستخدامها في التسويق بالبريد الإلكتروني.

## <a name="prerequisites-for-a-connection"></a>المتطلبات الأساسية لاتصال

- لديك [حساب HubSpot](https://www.hubspot.com/) وبيانات اعتماد المسؤول المناظرة.
- [مفتاح API](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) من HubSpot.
- [مقاطع مُكونة](segments.md) في Customer Insights.

## <a name="known-limitations"></a>الحدود المعروفة

- حتى 100'000 من ملفات تعريف العملاء لكل عملية تصدير إلى HubSpot، والتي قد تستغرق ما يصل إلى 15 دقيقة حتى تكتمل. عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى HubSpot يعتمد ويقتصر على عقدك مع HubSpot.
- المقاطع فقط.

## <a name="set-up-connection-to-hubspot"></a>إعداد الاتصال بـ HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **HubSpot** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل بيانات اعتمادك في HubSpot، عندما تطالب بذلك.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **اتصال** لبدء الاتصال بـ HubSpot.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء عملية تصدير جديدة، حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم HubSpot. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل. كرر نفس الخطوات للحقول الاختيارية الأخرى.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
