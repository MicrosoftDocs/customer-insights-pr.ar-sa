---
title: تصدير بيانات Customer Insights إلى SendGrid
description: اعرف كيفية تكوين الاتصال بـ SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597265"
---
# <a name="connector-for-sendgrid-preview"></a>موصل SendGrid (إصدار أولي)

يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة‬ إلى قوائم جهات اتصال SendGrid واستخدامها في الحملات والتسويق عبر البريد الإلكتروني في SendGrid. 

## <a name="prerequisites"></a>المتطلبات الأساسية

-   لديك [حساب SendGrid](https://sendgrid.com/) وبيانات اعتماد مسؤول مطابقة.
-   هناك قوائم جهات اتصال موجودة في SendGrid والمعرفات المناظرة. لمزيد من المعلومات، راجع [SendGrid - إدارة جهات الاتصال‎](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   لقد قمت [بتكوين الشرائح](segments.md) في رؤى الجمهور.
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="connect-to-sendgrid"></a>الاتصال بـ SendGrid

1. انتقل إلى **المسؤول** > **وجهات التصدير**.

1. أسفل **SendGrid**، حدد **إعداد**.

1. في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="جزء تكوين تصدير SendGrid.":::

1. أدخل **مفتاح SendGrid API** [مفتاح SendGrid API](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. أدخل **[معرف قائمة SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **اتصال** لتهيئة الاتصال بـ SendGrid.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **التالي** لتكوين التصدير.

## <a name="configure-the-connector"></a>تكوين الموصل

1. في القسم **مطابقة البيانات**، في حقل **البريد الإلكتروني**، حدد الحقل في ملف تعريف العميل الموحد الذي يمثل عنوان البريد الإلكتروني للعميل. كرر نفس الخطوات للحقول الاختيارية الأخرى مثل **الاسم الأول** و **اسم العائلة** و **البلد/المنطقة** و **الولاية** و **المدينة** و **الرمز البريدي**.

1. حدد الشرائح التي تريد تصديرها. نحن **نوصي بعدم تصدير أكثر من ‎100'000 من ملفات تعريف العملاء بشكل إجمالي** إلى SendGrid. 

1. حدد **حفظ**.

## <a name="export-the-data"></a>تصدير البيانات

يمكنك [تصدير البيانات عند الطلب](export-destinations.md). سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).

## <a name="known-limitations"></a>القيود المعروفة

- حتى ‎100'000 من ملفات التعريف بشكل إجمالي إلى SendGrid.
- يقتصر التصدير إلى SendGrid على الشرائح.
- قد يحتاج اكتمال تصدير حتى ‎100'000 ملف تعريف إلى SendGrid إلى ساعات قليلة. 
- يتوقف عدد ملفات التعريف التي يمكنك تصديرها إلى SendGrid على العقد مع SendGrid، وهذا العدد مقيد بالعقد.

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى SendGrid، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام SendGrid بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.


[!INCLUDE[footer-include](../includes/footer-banner.md)]