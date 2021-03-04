---
title: تصدير بيانات Customer Insights إلى Mailchimp
description: اعرف كيفية تكوين الاتصال بـ Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267157"
---
# <a name="connector-for-mailchimp-preview"></a>موصل Mailchimp (معاينة)

يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة إلى Mailchimp لإنشاء رسائل إخبارية وحملات بواسطة البريد الإلكتروني.

## <a name="prerequisites"></a>المتطلبات الأساسية

-   لديك [حساب Mailchimp](https://mailchimp.com/) وبيانات اعتماد مسؤول مطابقة.
-   هناك شرائح جمهور موجودة في Mailchimp والمعرفات المناظرة. لمزيد من المعلومات، راجع [شرائح جمهور Mailchimp](https://mailchimp.com/help/create-audience/).
-   لقد قمت [بتكوين الشرائح](segments.md)
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="connect-to-mailchimp"></a>الاتصال بـ Mailchimp

1. انتقل إلى **المسؤول** > **وجهات التصدير**.

1. أسفل **Mailchimp**، حدد **إعداد**.

1. في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. أدخل **[معرف جمهور Mailchimp](https://mailchimp.com/help/find-audience-id/)** وحدد **اتصال** لبدء الاتصال بـ Mailchimp.

1. حدد **المصادقة مع Mailchimp** وقد بيانات اعتماد Mailchimp.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="لقطة شاشة التصدير لاتصال Mailchimp":::

1. حدد **التالي** لتكوين التصدير.

## <a name="configure-the-connector"></a>تكوين الموصل

1. في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل. 

1. بشكل اختياري، يمكنك تصدير **الاسم الأول** و **اسم العائلة** كحقول إضافية لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة. حدد **إضافة سمة** لتعيين هذه الحقول.

1. حدد الشرائح التي تريد تصديرها. يمكنك تصدير ما يصل إلى مليون من ملفات تعريف العملاء إلى Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="حدد الحقول والشرائح لتصديرها إلى Mailchimp":::

1. حدد **حفظ**.

## <a name="export-the-data"></a>تصدير البيانات

يمكنك [تصدير البيانات عند الطلب](export-destinations.md). سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab). في Mailchimp، يمكنك الآن البحث عن الشرائح أسفل [شرائح جمهور Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>القيود المعروفة

- حتى مليون من ملفات التعريف لكل تصدير إلى Mailchimp.
- يقتصر التصدير إلى Mailchimp على الشرائح.
- قد تستغرق عملية تصدير الشرائح التي تتضمن ما يصل إلى مليون ملف تعريف بشكل إجمالي ثلاث ساعات كحدٍ أقصى نتيجة للقيود من جانب الموفر. 
- يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى Mailchimp على العقد مع Mailchimp، وهذا العدد مقيد بالعقد.

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Mailchimp، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Mailchimp بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.


[!INCLUDE[footer-include](../includes/footer-banner.md)]