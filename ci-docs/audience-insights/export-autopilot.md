---
title: تصدير بيانات Customer Insights إلى Autopilot
description: اعرف كيفية تكوين الاتصال بـ Autopilot.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 33a8cd1ae4a77ce2248bc2805d25687c9a2c2732
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269222"
---
# <a name="connector-for-autopilot-preview"></a>موصل Autopilot (إصدار أولي)

يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة‬ إلى Autopilot واستخدامها في الحملات والتسويق عبر البريد الإلكتروني في Autopilot. 

## <a name="prerequisites"></a>المتطلبات الأساسية

-   لديك [حساب Autopilot](https://www.autopilothq.com/) وبيانات اعتماد مسؤول مطابقة.
-   لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="connect-to-autopilot"></a>الاتصال بـ AutoPilot

1. انتقل إلى **المسؤول** > **وجهات التصدير**.

1. أسفل **Autopilot**، حدد **إعداد**.

1. في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.

   :::image type="content" source="media/export-autopilot.PNG" alt-text="جزء التكوين لاتصال Autopilot.":::

1. أدخل **مفتاح Autopilot API** [مفتاح Autopilot API](https://autopilot.docs.apiary.io/#).

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **اتصال** لتهيئة الاتصال بـ Autopilot.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **التالي** لتكوين التصدير.

## <a name="configure-the-connector"></a>تكوين الموصل

1. في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل. كرر نفس الخطوات للحقول الاختيارية الأخرى مثل **الاسم الأول** و **اسم العائلة**.

1. حدد الشرائح التي تريد تصديرها. نحن **نوصي بعدم تصدير أكثر من ‎100'000 من ملفات تعريف العملاء بشكل إجمالي** إلى Autopilot. 

1. حدد **حفظ**.

## <a name="export-the-data"></a>تصدير البيانات

يمكنك [تصدير البيانات عند الطلب](export-destinations.md). سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).

## <a name="known-limitations"></a>القيود المعروفة

- يمكنك تصدير ما يصل إلى ‎100'000 من ملفات تعريف العملاء إلى Autopilot.
- يقتصر التصدير إلى Autopilot على الشرائح.
- قد يحتاج اكتمال تصدير حتى ‎100'000 ملف تعريف إلى Autopilot إلى ساعات قليلة. 
- يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى Autopilot على العقد مع Autopilot، وهذا العدد مقيد بالعقد.

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Autopilot، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Autopilot بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.


[!INCLUDE[footer-include](../includes/footer-banner.md)]