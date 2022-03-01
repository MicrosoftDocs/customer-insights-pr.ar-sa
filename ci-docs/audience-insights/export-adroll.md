---
title: تصدير بيانات Customer Insights إلى AdRoll
description: اعرف كيفية تكوين الاتصال بـ AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697058"
---
# <a name="connector-for-adroll-preview"></a>موصل AdRoll (إصدار أولي)

يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة إلى AdRoll واستخدامها في الإعلانات. 

## <a name="prerequisites"></a>المتطلبات الأساسية

-   لديك [حساب AdRoll](https://www.adroll.com/) وبيانات اعتماد مسؤول مطابقة.
-   لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="connect-to-adroll"></a>الاتصال بـ AdRoll

1. انتقل إلى **المسؤول** > **وجهات التصدير**.

1. أسفل **AdRoll**، حدد **إعداد**.

1. في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="جزء التكوين لاتصال AdRoll.":::

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **اتصال** لتهيئة الاتصال بـ AdRoll.

1. حدد **المصادقة مع AdRoll** وقدم بيانات اعتماد المسؤول لـ AdRoll. 

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. أدخل **معرف معلن AdRoll** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. حدد **التالي** لتكوين التصدير.

## <a name="configure-the-connector"></a>تكوين الموصل

1. في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل. يلزم تصدير شرائح إلى AdRoll.

1. حدد الشرائح التي تريد تصديرها. حدد شريحة تتضمن 100 عضو على الأقل. لا يمكنك تصدير شرائح أصغر. بالإضافة إلى ذلك، فإن الحد الأقصى لحجم شريحة ما لتصديرها هو ‎250'000 عضو لكل عملية تصدير. 

1. حدد **حفظ**.

## <a name="export-the-data"></a>تصدير البيانات

يمكنك [تصدير البيانات عند الطلب](export-destinations.md). سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).

## <a name="known-limitations"></a>القيود المعروفة

- يمكنك تصدير ما يصل إلى ‎250'000 ملف تعريف في كل عملية تصدير إلى AdRoll.
- لا يمكنك تصدير شرائح ذات ملفات تعريف أقل من 100 إلى AdRoll. 
- يقتصر التصدير إلى AdRoll على الشرائح.
- قد يستغرق استكمال تصدير ‎250'000 ملف تعريف إلى AdRoll حتى 10 دقائق. 
- يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى AdRoll على العقد مع AdRoll، وهذا العدد مقيد بالعقد.

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى AdRoll، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام AdRoll بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.
