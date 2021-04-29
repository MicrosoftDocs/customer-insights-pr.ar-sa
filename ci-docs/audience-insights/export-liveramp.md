---
title: موصل LiveRamp
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760311"
---
# <a name="export-segments-to-liverampreg-preview"></a>تصدير شرائح إلى LiveRamp&reg; (إصدار أولي)

قم بتنشيط البيانات في LiveRamp للاتصال بما يزيد على 500 نظام أساسي عبر أجهزة الكمبيوتر الرقمية، والوسائط الاجتماعية، وأجهزة التلفاز. استخدام بياناتك في LiveRamp لاستهداف الحملات الإعلانية وإزالتها وتخصيصها.

## <a name="prerequisites-for-a-connection"></a>المتطلبات الأساسية لاتصال

- تحتاج إلى اشتراك LiveRamp لاستخدام هذا الموصل.
- للحصول على اشتراك، [اتصل بـ LiveRamp‎](https://liveramp.com/contact/) بشكل مباشر. [اعرف المزيد حول LiveRamp Onboarding‎](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>إعداد الاتصال بـ LiveRamp

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **LiveRamp** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **اسم المستخدم** و **كلمة المرور** لحساب LiveRamp Secure FTP (SFTP).
قد تختلف بيانات الاعتماد هذه عن بيانات اعتماد LiveRamp Onboarding.

1. حدد **التحقق** لاختبار الاتصال بـ LiveRamp.

1. وبعد التحقق الناجح، قدم موافقتك على **خصوصية البيانات والتوافق‬** من خلال تحديد خانة الاختيار **أوافق**.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم LiveRamp. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. في الحقل **اختيار معرف المفتاح**، حدد **البريد الإلكتروني** أو **الاسم والعنوان** أو **الهاتف** لإرساله إلى LiveRamp لحل الهوية.
   > [!div class="mx-imgBorder"]
   > ![موصل LiveRamp مع تعيين السمات](media/export-liveramp-segments.png "موصل LiveRamp مع تعيين السمات")

1. قم بتعيين السمات المناظرة من كيان العميل الموحد لمعرف المفتاح المحدد.

1. حدد **إضافة سمة** لتعيين مزيد من السمات لإرسالها إلى LiveRamp.

   > [!TIP]
   > من المحتمل أن يؤدي إرسال المزيد من سمات معرف المفتاح إلى LiveRamp للحصول على معدل تطابق أعلى.

1. حدد الشرائح التي تريد تصديرها إلى LiveRamp.

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Liveramp، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Liveramp بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
