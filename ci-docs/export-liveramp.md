---
title: تصدير مقاطع إلى LiveRamp (إصدار أولي)
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196700"
---
# <a name="export-segments-to-liverampreg-preview"></a>تصدير مقاطع إلى LiveRamp&reg; (إصدار أولي)

قم بتنشيط البيانات في LiveRamp للاتصال بما يزيد على 500 نظام أساسي عبر أجهزة الكمبيوتر الرقمية، والوسائط الاجتماعية، وأجهزة التلفاز. استخدام بياناتك في LiveRamp لاستهداف الحملات الإعلانية وإزالتها وتخصيصها.

## <a name="prerequisites"></a>المتطلبات

- اشتراك LiveRamp لاستخدام هذا الموصل. للحصول على اشتراك، [اتصل بـ LiveRamp‎](https://liveramp.com/contact/) بشكل مباشر. [اعرف المزيد حول LiveRamp Onboarding‎](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>القيود المعروفة

- يستخدم تصدير LiveRamp عملية تصدير SFTP. وجهات SFTP خلف جدران الحماية غير مدعومة حاليًا.
- إذا كنت تستخدم مفتاح SSH للمصادقة، فتأكد من [إنشاء مفتاحك الخاص](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) بتنسيق PEM أو SSH.COM. إذا كنت تستخدم Putty، فقم بتحويل مفتاحك الخاص عن طريق التصدير إلى Open SSH. يتم دعم تنسيقات المفاتيح الخاصة التالية:
  - RSA بتنسيق OpenSSL PEM وssh.com
  - DSA بتنسيق OpenSSL PEM وssh.com
  - ECDSA 256/384/521 بتنسيق OpenSSL PEM
  - ED25519 وRSA بتنسيق مفتاح OpenSSH
- يعتمد وقت تشغيل أي تصدير على أداء النظام. نوصي بمركزين لوحدة المعالجة المركزية وذاكرة بسعة غيغابايت واحد كحدٍ أدنى لتكوين الخادم.
- قد يستغرق تصدير الكيانات مع 100 مليون من ملفات تعريف العملاء 90 دقيقة عند استخدام الحد الأدنى من التكوين الموصى به من مركزين لوحدة المعالجة المركزية وذاكرة بسعة غيغابايت واحد.
- يعتمد العدد الفعلي للملفات الشخصية (أو البيانات) التي يمكنك تصديرها إلى LiveRamp على اشتراكك في LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>إعداد الاتصال بـ LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **LiveRamp**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. اختر ما إذا كنت تريد المصادقة من خلال SSH أو اسم المستخدم/كلمة المرور لاتصالك وقدم التفاصيل اللازمة.

1. حدد **التحقق** لاختبار الاتصال بـ LiveRamp.

1. بعد عملية تحقق ناجحة، راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم LiveRamp. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. في الحقل **توصيل البيانات**، حدد **البريد الإلكتروني** أو **الاسم والعنوان** أو **الهاتف** لإرساله إلى LiveRamp لحل الهوية.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="موصل LiveRamp مع تعيين السمات.":::

1. قم بتعيين السمات المقابلة من كيان *العميل* لمعرف المفتاح المحدد.

1. حدد **إضافة سمة** لتعيين مزيد من السمات لإرسالها إلى LiveRamp.

   > [!TIP]
   > من المحتمل أن يؤدي إرسال المزيد من سمات معرف المفتاح إلى LiveRamp للحصول على معدل تطابق أعلى.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
