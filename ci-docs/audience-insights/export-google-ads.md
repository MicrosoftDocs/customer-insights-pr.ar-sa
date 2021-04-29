---
title: تصدير بيانات Customer Insights إلى Google Ads
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى إعلانات Google.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759677"
---
# <a name="export-segments-to-google-ads-preview"></a>تصدير شرائح إلى إعلانات Google (إصدار أولي)

يمكنك تصدير شرائح ملفات تعريف العملاء الموحدة إلى قوائم جمهور Google Ads واستخدامها للإعلان على Google Search وGmail وYouTubeوGoogle Display Network. 

## <a name="prerequisites-for-connection"></a>المتطلبات الأساسية للاتصال

-   لديك [حساب Google Ads](https://ads.google.com/) وبيانات اعتماد مسؤول مطابقة.
-   لديك رمز [مطور إعلانات Google معتمد](https://developers.google.com/google-ads/api/docs/first-call/dev-token) 
-   أنت تفي بمتطلبات [سياسة مطابقة العملاء](https://support.google.com/adspolicy/answer/6299717)
-   أنت تفي بمتطلبات [أحجام قائمة تجديد النشاط التسويقي](https://support.google.com/google-ads/answer/7558048) 

-   هناك شرائح جمهور موجودة في Google Ads والمعرفات المناظرة. لمزيد من المعلومات، راجع [شرائح جمهور Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   لقد قمت [بتكوين الشرائح](segments.md)
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقول تمثل عنوان البريد الإلكتروني والاسم الأول واسم العائلة.

## <a name="known-limitations"></a>القيود المعروفة

- حتى مليون من ملفات التعريف لكل تصدير إلى Google Ads.
- يقتصر التصدير إلى Google Ads على الشرائح.
- قد تستغرق عملية تصدير الشرائح التي تتضمن ما يصل إلى مليون ملف تعريف بشكل إجمالي 5 دقائق كحدٍ أقصى نتيجة للقيود من جانب الموفر. 
- قد يستغرق التطابق في Google Ads ما يصل إلى 48 ساعة.

## <a name="set-up-connection-to-google-ads"></a>إعداد الاتصال بإعلانات Google

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **إعلانات Google** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **[معرف عميل Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. أدخل **[الرمز المميز لمطور Google Ads الموافق عليه](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **المصادقة مع Google Ads** وقد بيانات اعتماد Google Ads.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال. 

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم إعلانات Google. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. أدخل **[معرف جمهور Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** وحدد **اتصال** لبدء الاتصال بـ Google Ads.

1. في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل. كرر نفس الخطوات الخاصة للحقلين **الاسم الأول** و **اسم العائلة**.

1. حدد الشرائح التي تريد تصديرها. يمكنك تصدير ما يصل إلى مليون من ملفات تعريف العملاء إلى Google Ads.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Google Ads، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Google Ads بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.


[!INCLUDE[footer-include](../includes/footer-banner.md)]