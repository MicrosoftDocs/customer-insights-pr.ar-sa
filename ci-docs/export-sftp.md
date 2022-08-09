---
title: تصدير بيانات Customer Insights إلى مضيفي SFTP (إصدار أولي) (يحتوي على فيديو)
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى موقع SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207213"
---
# <a name="export-data-to-sftp-hosts-preview"></a>تصدير البيانات إلى مضيفي SFTP (إصدار أولي)

استخدم بيانات العميل في تطبيقات طرف ثالث من خلال تصديرها إلى موقع بروتوكول نقل الملفات الآمنة (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>المتطلبات

- توفر مضيف SFTP وبيانات الاعتماد المقابلة.

## <a name="known-limitations"></a>القيود المعروفة

- وجهات SFTP خلف جدران الحماية غير مدعومة حاليًا.
- يعتمد وقت تشغيل أي تصدير على أداء النظام. نوصي بمركزين لوحدة المعالجة المركزية وذاكرة بسعة غيغابايت واحد كحدٍ أدنى لتكوين الخادم.
- قد يستغرق تصدير الكيانات مع 100 مليون من ملفات تعريف العملاء 90 دقيقة عند استخدام الحد الأدنى من التكوين الموصى به من مركزين لوحدة المعالجة المركزية وذاكرة بسعة غيغابايت واحد.
- إذا كنت تستخدم مفتاح SSH للمصادقة، فتأكد من [إنشاء مفتاحك الخاص](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) بتنسيق PEM أو SSH.COM. إذا كنت تستخدم Putty، فقم بتحويل مفتاحك الخاص عن طريق التصدير إلى Open SSH. يتم دعم تنسيقات المفاتيح الخاصة التالية:
  - RSA بتنسيق OpenSSL PEM وssh.com
  - DSA بتنسيق OpenSSL PEM وssh.com
  - ECDSA 256/384/521 بتنسيق OpenSSL PEM
  - ED25519 وRSA بتنسيق مفتاح OpenSSH

## <a name="set-up-connection-to-sftp"></a>إعداد اتصال بـ SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **SFTP**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. اختر ما إذا كنت تريد المصادقة من خلال SSH أو اسم المستخدم/كلمة المرور لاتصالك وقدم التفاصيل اللازمة. إذا كنت تستخدم مفتاح SSH للمصادقة، فتأكد من [إنشاء مفتاحك الخاص](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) بتنسيق PEM أو SSH.COM. إذا كنت تستخدم Putty، فقم بتحويل مفتاحك الخاص عن طريق التصدير إلى Open SSH. يتم دعم تنسيقات المفاتيح الخاصة التالية:
   - RSA بتنسيق OpenSSL PEM وssh.com
   - DSA بتنسيق OpenSSL PEM وssh.com
   - ECDSA 256/384/521 بتنسيق OpenSSL PEM
   - ED25519 وRSA بتنسيق مفتاح OpenSSH

1. حدد **تحقق** لاختبار الاتصال.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم SFTP. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. اختر ما إذا كنت ترغب في تصدير بياناتك **المضغوطة** أو **المفكوك ضغطها** و **محدد المجال** للملفات المصدرة.

1. حدد الكيانات، على سبيل المثال المقاطع، التي ترغب في تصديرها.

   > [!NOTE]
   > سيتم تقسيم كل كيان محدد إلى خمسة ملفات إخراج بحد أقصى عند التصدير.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!TIP]
> يمكن أن يؤدي تصدير الكيانات التي تحتوي على كمية كبيرة من البيانات إلى الحصول على ملفات CSV متعددة في نفس المجلد لكل عملية تصدير. يحدث تقسيم الصادرات لأسباب تتعلق بالأداء لتقليل الوقت الذي يستغرقه اكتمال التصدير.

[!INCLUDE [footer-include](includes/footer-banner.md)]
