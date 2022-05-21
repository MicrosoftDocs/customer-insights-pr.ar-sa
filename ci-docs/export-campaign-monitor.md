---
title: تصدير بيانات Customer Insights إلى Campaign Monitor
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Campaign Monitor.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b351e491ee830b6360d4efe33d32a726c2e553ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645475"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>تصدير الشرائح إلى Campaign Monitor (إصدار أولي)

قم بتصدير شرائح ملفات تعريف العملاء الموحدة إلى Campaign Monitor واستخدامها في أنشطة التسويق.

## <a name="prerequisites"></a>المتطلبات الأساسية

-   لديك [حساب Campaign Monitor](https://www.campaignmonitor.com/) وبيانات اعتماد المسؤول المقابلة.
-   لديك [مقاطع مُكونة](segments.md) في Customer Insights.
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- يمكنك تصدير ما يصل إلى مليون ملف تعريف عميل لكل عملية تصدير إلى Campaign Monitor.
- يقتصر التصدير إلى Campaign Monitor على الشرائح.
- يمكن أن يستغرق تصدير ما يصل إلى مليون ملف تعريف عميل إلى Campaign Monitor ما يصل إلى 20 دقيقة حتى يكتمل. 
- يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى Campaign Monitor ومحدودًا على عقدك مع Campaign Monitor.

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

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل. يلزم تصدير شرائح إلى Campaign Monitor.

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لنقل البيانات إلى Campaign Monitor، فأنت تسمح بنقل البيانات خارج حدود الامتثال لـ Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات بموجب الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان ووفاء Campaign Monitor بأي خصوصية أو التزامات أمنية قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.