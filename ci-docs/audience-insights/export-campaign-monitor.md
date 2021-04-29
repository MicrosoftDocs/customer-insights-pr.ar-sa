---
title: تصدير بيانات Customer Insights إلى Campaign Monitor
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7fd6af37b40e21d030a1ace0cd5f8fcc7861c3fa
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760457"
---
# <a name="export-segment-lists-to-campaign-monitor-preview"></a>تصدير قوائم الشرائح إلى Campaign Monitor (إصدار أولي)

قم بتصدير شرائح ملفات تعريف العملاء الموحدة إلى Campaign Monitor واستخدامها في أنشطة التسويق.

## <a name="prerequisites"></a>المتطلبات الأساسية

-   لديك [حساب Campaign Monitor](https://www.campaignmonitor.com/) وبيانات اعتماد المسؤول المقابلة.
-   لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- يمكنك تصدير حتى 1 مليوت ملف تعريف لكل تصدير إلى Campaign Monitor.
- يقتصر التصدير إلى Campaign Monitor على الشرائح.
- قد يستغرق تصدير ما يصل إلى مليون ملف تعريف إلى Campaign Monitor ما يصل إلى 20 دقيقة حتى الاكتمال. 
- عدد الملفات الشخصية التي يمكنك تصديرها إلى Campaign Monitor يعتمد ويقتصر على عقدك مع Campaign Monitor.

## <a name="set-up-connection-to-campaign-monitor"></a>إعداد الاتصال بـ Campaign Monitor

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Campaign Monitor** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **الاتصال** لبدء الاتصال بـ Campaign Monitor.

1. حدد **المصادقة مع Campaign Monitor** ووفر بيانات اعتماد المسؤول الخاصة بك لـ Campaign Monitor.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Campaign Monitor. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. أدخل [**معرف قائمة Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [إنشاء مفتاح واجهة برمجة التطبيقات](https://www.campaignmonitor.com/api/getting-started/) من **إعدادات الحساب** في Campaign Monitor أولاً لعرض معرف قائمة واجهة برمجة التطبيقات.  

3. في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل. يلزم تصدير شرائح إلى Campaign Monitor.

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لنقل البيانات إلى Campaign Monitor، فأنت تسمح بنقل البيانات خارج حدود الامتثال لـ Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات بموجب الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان ووفاء Campaign Monitor بأي خصوصية أو التزامات أمنية قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.
