---
title: تصدير بيانات Customer Insights إلى DotDigital
description: اعرف كيفية تكوين الاتصال بـ DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598000"
---
# <a name="connector-for-dotdigital-preview"></a>موصل DotDigital (معاينة)

يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة إلى دفاتر عناوين DotDigital واستخدامها للحملات والتسويق بواسطة البريد الإلكتروني ولإنشاء شرائح العملاء بواسطة DotDigital. 

## <a name="prerequisites"></a>المتطلبات الأساسية

-   لديك [حساب DotDigital](https://dotdigital.com/) وبيانات اعتماد مسؤول مطابقة.
-   هناك دفاتر عناوين موجودة في DotDigital والمعرفات المناظرة. يمكن العثور على المعرف في URL عندما تقوم بتحديد وفتح دفتر عناوين. لمزيد من المعلومات، راجع [دفاتر عناوين DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="connect-to-dotdigital"></a>الاتصال بـ DotDigital

1. انتقل إلى **المسؤول** > **وجهات التصدير**.

1. أسفل **DotDigital**، حدد **إعداد**.

1. في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="جزء التكوين لتصدير DotDigital.":::

1. أدخل **اسم المستخدم وكلمة المرور في DotDigital**.

1. أدخل **[معرف دفتر عناوين DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **اتصال** لتهيئة الاتصال بـ DotDigital.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **التالي** لتكوين التصدير.

## <a name="configure-the-connector"></a>تكوين الموصل

1. في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل. كرر نفس الخطوات للحقول الاختيارية الأخرى مثل **الاسم الأول** و **اسم العائلة** و **الاسم الكامل** و **الجنس** و **الرمز البريدي**.

1. حدد الشرائح التي تريد تصديرها. يمكنك تصدير ما يصل إلى مليون من ملفات تعريف العملاء إلى DotDigital.

1. حدد **حفظ**.

## <a name="export-the-data"></a>تصدير البيانات

يمكنك [تصدير البيانات عند الطلب](export-destinations.md). سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab). في DotDigital، يمكنك الآن العثور على الشرائح في [دفاتر عناوين DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>القيود المعروفة

- حتى مليون من ملفات التعريف لكل تصدير إلى DotDigital.
- يقتصر التصدير إلى DotDigital على الشرائح.
- قد تستغرق عملية تصدير الشرائح التي تتضمن ما يصل إلى مليون ملف تعريف بشكل إجمالي ثلاث ساعات كحدٍ أقصى نتيجة للقيود من جانب الموفر. 
- يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى DotDigital على العقد مع DotDigital، وهذا العدد مقيد بالعقد.

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى DotDigital، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام DotDigital بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.


[!INCLUDE[footer-include](../includes/footer-banner.md)]