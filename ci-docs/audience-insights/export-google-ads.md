---
title: تصدير بيانات Customer Insights إلى Google Ads
description: اعرف كيفية تكوين الاتصال بـ Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568394"
---
# <a name="connector-for-google-ads-preview"></a>موصل Google Ads (معاينة)

يمكنك تصدير شرائح ملفات تعريف العملاء الموحدة إلى قوائم جمهور Google Ads واستخدامها للإعلان على Google Search وGmail وYouTubeوGoogle Display Network. 

## <a name="prerequisites"></a>المتطلبات الأساسية

-   لديك [حساب Google Ads](https://ads.google.com/) وبيانات اعتماد مسؤول مطابقة.
-   هناك شرائح جمهور موجودة في Google Ads والمعرفات المناظرة. لمزيد من المعلومات، راجع [شرائح جمهور Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   لقد قمت [بتكوين الشرائح](segments.md)
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقول تمثل عنوان البريد الإلكتروني والاسم الأول واسم العائلة.

## <a name="connect-to-google-ads"></a>الاتصال بـ Google Ads

1. انتقل إلى **المسؤول** > **وجهات التصدير**.

1. ضمن **Google Ads**، حدد **إعداد**.

1. في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.

1. أدخل **[معرف عميل Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. أدخل **[الرمز المميز لمطور Google Ads الموافق عليه](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. أدخل **[معرف جمهور Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** وحدد **اتصال** لبدء الاتصال بـ Google Ads.

1. حدد **المصادقة مع Google Ads** وقد بيانات اعتماد Google Ads.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="لقطة شاشة التصدير لاتصال Google Ads":::

1. حدد **التالي** لتكوين التصدير.

## <a name="configure-the-connector"></a>تكوين الموصل

1. في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل. كرر نفس الخطوات الخاصة للحقلين **الاسم الأول** و **اسم العائلة**.

1. حدد الشرائح التي تريد تصديرها. يمكنك تصدير ما يصل إلى مليون من ملفات تعريف العملاء إلى Google Ads.

1. حدد **حفظ**.

## <a name="export-the-data"></a>تصدير البيانات

يمكنك [تصدير البيانات عند الطلب](export-destinations.md). سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab). في Google Ads، يمكنك الآن البحث عن الشرائح أسفل [شرائح جمهور Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>القيود المعروفة

- حتى مليون من ملفات التعريف لكل تصدير إلى Google Ads.
- يقتصر التصدير إلى Google Ads على الشرائح.
- قد تستغرق عملية تصدير الشرائح التي تتضمن ما يصل إلى مليون ملف تعريف بشكل إجمالي 5 دقائق كحدٍ أقصى نتيجة للقيود من جانب الموفر. 
- قد يستغرق التطابق في Google Ads ما يصل إلى 48 ساعة.

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Google Ads، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Google Ads بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.
