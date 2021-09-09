---
title: تصدير بيانات Customer Insights إلى Klaviyo
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Klaviyo.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7c1297fd5381c00c07d6501186c51fe4798773d1
ms.sourcegitcommit: 205f931ec671a0ab1850f2c1c94df3307ffb62c9
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/13/2021
ms.locfileid: "7385772"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>تصدير قوائم الشرائح إلى Klaviyo (إصدار أولي)

قم بتصدير شرائح من ملفات تعريف العملاء الموحدة إلى Klaviyo واستخدمها في أنشطة التسويق.

## <a name="prerequisites"></a>المتطلبات الأساسية

-   لديك [حساب Klaviyo](https://www.klaviyo.com/) وبيانات اعتماد المسؤول المقابلة.
-   لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- يمكنك تصدير حتى 100'000 ملف تعريف لكل عملية تصدير إلى Klaviyo.
- يقتصر التصدير إلى Klaviyo على الشرائح.
- قد يستغرق استكمال تصدير ‎مليون ملف تعريف إلى Klaviyo حتى 20 دقيقة. 
- يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى Klaviyo ويتحدد بواسطة عقدك مع Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>إعداد اتصال بـ Klaviyo

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Klaviyo** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. قدم [مفتاح Klaviyo API](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) لمتابعة تسجيل الدخول. 

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **اتصال** لتهيئة الاتصال بـ Klaviyo.

1. حدد **المصادقة مع Klaviyo** ووفر بيانات اعتماد المسؤول لـ Klaviyo.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **اتصال للتصدير**، اختر اتصالا من قسم Klaviyo. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. أدخل [**معرف قائمة Klaviyo**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل. مطلوب لتصدير الشرائح إلى Klaviyo.

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عندما تقوم بتمكين Dynamics 365 Customer Insights لنقل البيانات إلى Klaviyo، يمكنك السماح بنقل البيانات خارج حدود التوافق ل Dynamics 365 Customer Insights، بما في ذلك البيانات التي قد تكون حساسة مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات في الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان وفاء Klaviyo بأية خصوصية أو واجبات أمنية قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.