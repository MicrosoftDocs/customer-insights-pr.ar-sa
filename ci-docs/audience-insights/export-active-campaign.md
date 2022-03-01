---
title: تصدير بيانات Customer Insights إلى ActiveCampaign
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314569"
---
# <a name="export-segments-to-activecampaign-preview"></a>تصدير شرائح إلى ActiveCampaign (معاينة)

قم بتصدير شرائح من ملفات تعريف العملاء الموحدين إلى ActiveCampaign واستخدامها في أنشطة التسويق.

## <a name="prerequisites"></a>المتطلبات الأساسية

-   لديك [حساب ActiveCampaign](https://www.activecampaign.com/) وبيانات اعتماد المسؤول المقابلة.
-   لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح التي تم تصديرها على حقل يحتوي على عنوان بريد إلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- يمكن تصدير ما يصل إلى مليون ملف تعريف لكل عملية تصدير إلى ActiveCampaign وقد يستغرق حتى 90 دقيقة حتى تكتمل.
- يقتصر التصدير إلى ActiveCampaign على الشرائح.
- يعتمد عدد ملفات التعريف التي يمكنك تصديرها إلى ActiveCampaign على العقد الخاص بك مع ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>إعداد اتصال بـ ActiveCampaign

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **ActiveCampaign** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل [مفتاح ActiveCampaign API واسم المضيف لنقطة نهاية REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). اسم المضيف نقطة النهاية REST هو اسم المضيف فقط، بدون https://. 

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **اتصال** لتهيئة الاتصال بـ ActiveCampaign.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين تصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **اتصال للتصدير**، اختر اتصالا من قسم ActiveCampaign. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. أدخل [**معرف قائمة ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

3. في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل. مطلوب لتصدير الشرائح إلى ActiveCampaign. بشكل اختياري، يمكنك تصدير الاسم الأول، واسم العائلة، والهاتف لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة. حدد إضافة سمة لتعيين هذه الحقول.

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عندما تقوم بتمكين Dynamics 365 Customer Insights لنقل البيانات إلى ActiveCampaign، يمكنك السماح بنقل البيانات خارج حدود التوافق ل Dynamics 365 Customer Insights، بما في ذلك البيانات التي قد تكون حساسة مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات في الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان وفاء ActiveCampaign بأية خصوصية أو واجبات أمنية قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.
