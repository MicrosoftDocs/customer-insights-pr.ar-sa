---
title: تصدير بيانات Customer Insights إلى Microsoft Advertising
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f8a4cbb9590f9c5311789154319283530e0a10343cccbe9c7aec99765b4fbf2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031432"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>تصدير شرائح إلى Microsoft Advertising (إصدار أولي)

يمكنك تصدير شرائح Customer Insights إلى Microsoft Advertising لإنشاء شرائح جمهور مطابقة العملاء. استخدم شرائح الجمهور هذه لحملاتك الإعلانية.

## <a name="prerequisites"></a>المتطلبات الأساسية

-   [حساب Microsoft Advertising](https://ads.microsoft.com/) وبيانات اعتماد المسؤول المقابلة.
-   قبلت شروط استخدام "مطابقة العملاء". 
-   [شرائح مكوّنة](segments.md) في رؤى الجمهور.
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح التي تم تصديرها على حقل يحتوي على عنوان بريد إلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- يمكنك تصدير حتى 500 ألف ملف تعريف لكل تصدير إلى Microsoft Advertising.
- يقتصر التصدير إلى Microsoft Advertising على الشرائح.
- قد يستغرق استكمال تصدير ما يصل إلى 500 ألف ملف تعريف إلى Microsoft Advertising ما يصل إلى 10 دقائق. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>إعداد الاتصال بـ Microsoft Advertising

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Microsoft Advertising** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. الإعداد الافتراضي هو "المسؤولون". لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **اتصال** لبدء الاتصال بـ Microsoft Advertising.

1. حدد **المصادقة مع Microsoft Advertising** وقدم بيانات اعتماد المسؤول الخاصة بك لـ Microsoft Advertising.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Microsoft Advertising. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. حدد الشرائح التي تريد تصديرها. يتم شرائح جمهور "مطابقة العملاء" في Microsoft Advertising بشكل تلقائي باسم الشرائح المحددة للتصدير. سينتج عن كل شريحة جمهور منفصل لمطابقة العملاء. 

1. أدخل **معرف العميل ومعرف الحساب لـ Microsoft Advertising**. يمكنك العثور على معرف العميل (`cid`) ومعرف الحساب (`aid`) في معلمات عنوان URL عندما تسجل دخولك إلى Microsoft Advertising.

1. في قسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد باستخدام عنوان البريد الإلكتروني الخاص بالعميل. يلزم تصدير الشرائح إلى Microsoft Advertising.

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لنقل البيانات إلى Microsoft Advertising، فأنت تسمح بنقل البيانات خارج حدود الامتثال لـ Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات بموجب الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان وفاء Microsoft Advertising بأي خصوصية أو التزامات أمنية قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لوقف استخدام هذه الوظيفة.
