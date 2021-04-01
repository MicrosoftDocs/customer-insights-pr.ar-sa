---
title: تصدير بيانات Customer Insights إلى Facebook Ads Manager
description: تعرف على كيفية تكوين الاتصال مع مدير الإعلانات في Facebook.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596646"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>موصل لمدير الإعلانات في Facebook (معاينة)

يمكنك تصدير شرائح من ملفات تعريف العملاء الموحدة إلى مدير الإعلانات في Facebook لإنشاء حملات على Facebook وInstagram.

## <a name="prerequisites"></a>المتطلبات الأساسية

- يجب أن يكون لديك [**حساب Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) يتضمن [**حساب عمل في Facebook**](https://business.facebook.com/).
- يجب أن تكون مسؤولاً على [**حساب Facebook Ad**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>الاتصال بمدير الإعلانات في Facebook

1. انتقل إلى **المسؤول** > **وجهات التصدير**.

1. ضمن **مدير الإعلانات في Facebook**، حدد **إعداد**.

1. في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.

1. حدد **المتابعة مع Facebook** لتسجيل الدخول إلى حساب الإعلانات في Facebook.

1. السماح بإذن **ads_management** مع المصادقة مع Facebook.

1. حدد **حساب الإعلانات في Facebook** الذي تريد استخدامه.

1. حدد **جمهور مخصص موجود** من القائمة المنسدلة أو قم بإنشاء **جمهور مخصص من**. لمزيد من المعلومات، راجع [**شرائح الجمهور في مدير الإعلانات في Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **التالي** لتكوين التصدير.

## <a name="configure-the-connector"></a>تكوين الموصل

1. في الحقل **اختر معرف المفتاح**، وحدد **البريد الإلكتروني** أو **الاسم والعنوان** أو **الهاتف** لإرساله إلى مدير الإعلانات في Facebook.

1. قم بتعيين السمات المناظرة من كيان العميل الموحد لمعرف المفتاح المحدد.
   > [تلميح] تحدث أفضل فرص حدوث تطابق إذا حددت **البريد الإلكتروني** كمعرف مفتاح. قد تؤدي إضافة معرفات إضافية إلى تحسين التطابق.

1. حدد **إضافة سمة** لتعيين سمات إضافية لإرسالها إلى مدير الإعلانات في Facebook. يتم تعيين السمات من مدير الإعلانات في Facebook إلى الأسماء المألوفة التالية للمستخدم: **FN** = **الاسم الأول**، **LN** = **اسم العائلة**, **FI** = **الحرف الأول للاسم**، **PHONE** = **الهاتف**، **GEN** = **الجنس**، **DOB** = **تاريخ الميلاد**، **ST** = **الولاية**، **CT** = **المدينة**، **ZIP** = **الرمز البريدي**، **COUNTRY** = **البلد / المنطقة**

1. حدد الشرائح التي تريد تصديرها.

1. حدد **حفظ**.

## <a name="export-the-data"></a>تصدير البيانات

يمكنك [تصدير البيانات عند الطلب](export-destinations.md). سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).

## <a name="known-limitations"></a>القيود المعروفة

- ما يصل إلى 10 مليون ملف تعريف عميل لكل عملية تصدير إلى مدير إعلانات Facebook 
- يقتصر التصدير إلى مدير إعلانات Facebook على الشرائح.
- تستغرق عملية تصدير الشرائح التي تتضمن 10 ملايين ملف تعريف بشكل إجمالي حتى 90 دقيقة.

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى  Facebook Ads Manager، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Facebook Ads بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.


[!INCLUDE[footer-include](../includes/footer-banner.md)]