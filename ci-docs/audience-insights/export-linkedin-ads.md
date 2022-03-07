---
title: تصدير بيانات Customer Insights إلى إعلانات LinkedIn
description: تعرف على كيفية تكوين الاتصال والتصدير إلى إعلانات LinkedIn.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7a6bb466652b8703a4784329a5e675965f557e82
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231087"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>تصدير شرائح إلى إعلانات LinkedIn (إصدار أولي)

يمكنك تصدير شرائح ملفات تعريف العملاء الموحدة إلى إعلانات LinkedIn لإنشاء شرائح جمهور مطابقة. استخدم شرائح الجمهور المطابقة لاستهداف الشركات واستهداف جهات الاتصال.

## <a name="prerequisites"></a>المتطلبات الأساسية

-   لديك [حساب LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) وبيانات اعتماد مسؤول مناظرة.
-   لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.
-   تحتوي ملفات تعريف العملاء في الشرائح التي تم تصديرها على حقل يحتوي على عنوان بريد إلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- يجب أن تحتوي شريحتك في Customer Insights على 300 ملف تعريف فريد على الأقل. 
- يمكنك تصدير ما يصل إلى 100 ألف ملف تعريف عميل لكل عملية تصدير إلى إعلانات LinkedIn.
- يقتصر التصدير إلى إعلانات LinkedIn على الشرائح.
- يمكن أن يستغرق تصدير ما يصل إلى 100 ألف ملف تعريف عميل إلى إعلانات LinkedIn ما يصل إلى 10 دقائق حتى يكتمل. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>إعداد الاتصال بإعلانات LinkedIn

1. من رؤى الجمهور، انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **إعلانات LinkedIn** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكون "المسؤولون". لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. قدم [معرف حساب LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **الاتصال** لبدء الاتصال بـ Campaign Monitor.

1. حدد **المصادقة مع LinkedIn** وقدم بيانات اعتماد المسؤول لـ LinkedIn Campaign Manager.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين تصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم إعلانات LinkedIn. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. اختر ما إذا كنت تريد تصدير البيانات من أجل [استهداف جهات الاتصال](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) أو [استهداف الشركات](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) على LinkedIn. 

1. في قسم **مطابقة البيانات** لاستهداف جهات الاتصال، حدد حقلًا واحدًا على الأقل يمثل عنوان البريد الإلكتروني للعميل، إعلان Apple ID أو Google Ad ID أو Google User ID أو الاسم الأول والأخير. إذا اخترت استهداف الشركة، فحدد حقلًا واحدًا على الأقل يمثل اسم الشركة أو مجال البريد الإلكتروني أو عنوان URL لصفحة LinkedIn أو رمز الأسهم أو موقع الويب. يمكن تحديد حقول إضافية لتعريف التصدير بشكل أكبر. 

1. حدد الشرائح التي تريد تصديرها. سيتم إنشاء شرائح الجمهور المطابقة في LinkedIn Campaign Manager بشكل تلقائي باسم الشرائح التي حددتها للتصدير. سينتج عن كل شريحة جمهور مطابق منفصل. 

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لنقل البيانات إلى LinkedIn، فأنت تسمح بنقل البيانات خارج حدود الامتثال لـ Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات بموجب الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان وفاء إعلانات LinkedIn بأي خصوصية أو التزامات أمنية قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لوقف استخدام هذه الوظيفة.
