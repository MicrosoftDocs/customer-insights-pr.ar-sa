---
title: موصل LiveRamp
description: تعرف على كيفية تصدير البيانات إلى LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270142"
---
# <a name="liverampreg-connector-preview"></a>موصل&reg; LiveRamp‏‎ (معاينة)

قم بتنشيط بياناتك في LiveRamp‏‎ للاتصال بأكثر من 500 نظام أساسي عبر الأنظمة البيئية الرقمية والاجتماعية والتلفزيونية. استخدام بياناتك في LiveRamp لاستهداف الحملات الإعلانية وإزالتها وتخصيصها.

## <a name="prerequisites"></a>المتطلبات الأساسية

- تحتاج إلى اشتراك LiveRamp لاستخدام هذا الموصل.
- للحصول على اشتراك، [اتصل بـ LiveRamp‎](https://liveramp.com/contact/) بشكل مباشر. [اعرف المزيد حول LiveRamp Onboarding‎](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>الاتصال بـ LiveRamp‎

1. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.

1. في الإطار المتجانب **LiveRamp‎**، حدد **إعداد**.

1. في حقل **الاسم المعروض**، أدخل اسمًا للوجهة سهل التمييز.

1. أدخل **اسم المستخدم** و **كلمة المرور** لحساب LiveRamp Secure FTP (SFTP).
قد تختلف بيانات الاعتماد هذه عن بيانات اعتماد LiveRamp Onboarding.

1. حدد **التحقق** لاختبار الاتصال بـ LiveRamp.

1. وبعد التحقق الناجح، قدم موافقتك على **خصوصية البيانات والتوافق‬** من خلال تحديد خانة الاختيار **أوافق**.

1. حدد **التالي** لإعداد موصل LiveRamp.

## <a name="configure-the-connector"></a>تكوين الموصل

1. في الحقل **اختيار معرف المفتاح**، حدد **البريد الإلكتروني** أو **الاسم والعنوان** أو **الهاتف** لإرساله إلى LiveRamp لحل الهوية.

1. قم بتعيين السمات المناظرة من كيان العميل الموحد لمعرف المفتاح المحدد.

1. حدد **إضافة سمة** لتعيين سمات إضافية لإرسالها إلى LiveRamp.

   > [!TIP]
   > من المحتمل أن يؤدي إرسال المزيد من سمات معرف المفتاح إلى LiveRamp للحصول على معدل تطابق أعلى.

1. حدد الشرائح التي تريد تصديرها إلى LiveRamp.

1. حدد **حفظ**.

> [!div class="mx-imgBorder"]
> ![موصل LiveRamp مع تعيين السمات](media/export-liveramp-segments.png "موصل LiveRamp مع تعيين السمات")

## <a name="export-the-data"></a>تصدير البيانات

سيبدأ التصدير بعد قليل إذا تم استكمال جميع المتطلبات الأساسية للتصدير. سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).
بعد اكتمال التصدير بنجاح، يمكنك تسجيل الدخول إلى LiveRamp Onboarding لتنشيط البيانات وتوزيعها.

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Liveramp، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Liveramp بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.

[!INCLUDE[footer-include](../includes/footer-banner.md)]