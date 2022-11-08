---
title: تصدير مقاطع إلى مدير إعلانات Facebook (إصدار أولي) (يحتوي على فيديو)
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى مدير إعلانات Facebook.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724560"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>تصدير مقاطع إلى مدير إعلانات Facebook (إصدار أولي)

يمكنك تصدير مقاطع من ملفات تعريف العملاء الموحدة إلى مدير الإعلانات في Facebook لإنشاء حملات على Facebook وInstagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>المتطلبات

- [حساب إعلانات Facebook](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) يتضمن [حساب أعمال على Facebook](https://business.facebook.com/).
- امتيازات المسؤول على [حساب إعلانات Facebook](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- يجب على المستخدم الذي يعمل على إعداد الاتصال في Customer Insights قبول شروط الحضور المخصصة.

## <a name="known-limitations"></a>الحدود المعروفة

- ما يصل إلى 10 ملايين ملف تعريف عميل لكل عملية تصدير إلى مدير إعلانات Facebook، والتي يمكن أن تستغرق ما يصل إلى 90 دقيقة.
- المقاطع فقط.
- لا يدعم تكامل إعلانات Facebook المستخدمين الذين لديهم أكثر من 25 حسابًا إعلانيًا.
- نوع Facebook *قائمة العميل* في [الجماهير المخصصة](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) فقط.
  > [!NOTE]
  > وفي بعض الحالات، قد تشاهد مجموعات مخصصة من أنواع مختلفة في القائمة المنسدلة. إذا حددت نوعًا مختلفًا غير *قائمة العملاء*، يفشل التصدير.

## <a name="set-up-connection-to-facebook-ads-manager"></a>إعداد الاتصال بمدير إعلانات Facebook

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **مدير إعلانات Facebook**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. مصادقة باستخدام إعلانات Facebook:

   1. حدد **الاستمرار في Facebook** لتسجيل الدخول إلى حساب إعلانات Facebook الخاص بك.

   1. السماح بإذن **ads_management** مع المصادقة مع Facebook.

   1. حدد **حساب الإعلانات في Facebook** الذي تريد استخدامه.

   1. حدد **الجمهور المخصص الحالي** من القائمة المنسدلة أو قم بإنشاء **جمهور مخصص جديد**.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم مدير إعلانات Facebook. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. في حقل **توصيل البيانات**، حدد **البريد الإلكتروني** أو **الاسم والعنوان** أو **الهاتف** لإرساله إلى مدير الإعلانات في Facebook.

1. قم بتعيين السمات المناظرة من كيان العميل الموحد لمعرف المفتاح المحدد.
   > [!TIP]
   > تحدث أفضل فرص حدوث تطابق إذا حددت **البريد الإلكتروني** كمعرف مفتاح. قد تؤدي إضافة معرفات إضافية إلى تحسين التطابق.

1. حدد **إضافة سمة** لتعيين مزيد من السمات لإرسالها إلى مدير إعلانات Facebook. يتم تعيين السمات من مدير الإعلانات في Facebook إلى الأسماء المألوفة التالية للمستخدم: **FN** = **الاسم الأول**، **LN** = **اسم العائلة**, **FI** = **الحرف الأول للاسم**، **PHONE** = **الهاتف**، **GEN** = **الجنس**، **DOB** = **تاريخ الميلاد**، **ST** = **الولاية**، **CT** = **المدينة**، **ZIP** = **الرمز البريدي**، **COUNTRY** = **البلد/المنطقة**

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
