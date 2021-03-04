---
title: إثراء البيانات بواسطة خدمات إثراء البيانات من طرف ثالث HERE Technologies
description: معلومات عامة حول خدمات إثراء البيانات من طرف ثالث HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269498"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>إثراء ملفات تعريف العملاء بواسطة HERE Technologies (معاينة)

إن HERE Technologies عبارة عن شركة ذات منصة للبيانات المكانية توفر بيانات وخدمات تركّز على الموقع. باستخدام خدمات إثراء البيانات في HERE Technologies، يمكنك تكوين فهم أكثر دفة لموقع العملاء مع تسوية العناوين واستخراج خط الطول وخط العرض والمزيد.

## <a name="prerequisites"></a>المتطلبات الأساسية

لتكوين عمليات إثراء HERE Technologies، يجب استيفاء المتطلبات الأساسية التالية:

- لديك اشتراك نشط في HERE Technologies. للحصول على اشتراك، يمكنك [التسجيل هنا](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) أو [الاتصال بشركة HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) مباشرةً. [اعرف المزيد حول إثراء الموقع من HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- لديك مفتاح API لـ HERE Technologies.

- لديك أذونات [المسؤول](permissions.md#administrator).

## <a name="configuration"></a>التكوين

1. انتقل إلى **بيانات** > **إثراء**.

1. حدد **إثراء بياناتي** على الإطار المتجانب HERE Technologies‬.

   > [!div class="mx-imgBorder"]
   > ![الإطار المتجانب HERE Technologies](media/HERE-tile.png "الإطار المتجانب HERE Technologies")

1. أدخل **مفتاح HERE Technologies API** نشطًا. راجع وقدم موافقتك على **خصوصية البيانات والتوافق‬** من خلال تحديد خانة الاختيار **أوافق**. 

1. أكد الإدخالين عن طريق تحديد **اتصال بـ HERE**.

1.  حدد **إضافة بيانات** واختر **مجموعة بيانات العميل** التي ترغب في إثرائها بواسطة بيانات الموقع من HERE Technologies. يمكنك تحديد كيان **العميل** لإثراء جميع ملفات تعريف العملاء أو تحديد كيان شريحة لإثراء فقط ملفات تعريف العملاء الموجودة في تلك الشريحة.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="لقطة شاشة عند اختيار مجموعة بيانات العميل.":::

1. اختر إذا كنت تريد تعيين الحقول إلى العنوان الرئيسي و/أو الثانوي. يمكنك تحديد تعيين الحقول للعنوانين (على سبيل المثال، عنوان المنزل وعنوان العمل) واعمل على إثراء ملفات التعريف للعنوانين على حدة. حدد **التالي**.

1. حدد الحقول التي سيتم استخدامها من ملفات التعريف الموحدة للبحث عن بيانات الموقع المطابقة من تقنيات HERE يجب تعبئة الحقلين **الشارع 1** و **الرمز البريدي** للعنوان الرئيسي و/أو الثانوي المحدد.‬ للحصول على دقة مطابقة أعلى، يمكن إضافة المزيد من الحقول.

   > [!div class="mx-imgBorder"]
   > ![صفحة تكوين إثراء HERE Technologies](media/enrichment-HERE-configuration.png "صفحة تكوين إثراء HERE Technologies")

1. حدد **تطبيق** لإكمال تعيين الحقول.

## <a name="enrichment-results"></a>نتائج الإثراء

لبدء عملية الإثراء، حدد **تشغيل** من شريط الأوامر. يمكنك أيضًا السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من [التحديث المجدول](system.md#schedule-tab). سيعتمد وقت المعالجة على حجم بيانات العملاء وأوقات استجابة API من HERE Technologies.

بعد اكتمال عملية الإثراء، يمكنك مراجعة بيانات ملفات تعريف العملاء التي تم إثراؤها حديثًا ضمن **عمليات الإثراء الخاصة بي**. بالإضافة إلى ذلك ، ستجد وقت التحديث الأخير وعدد ملفات التعريف التي تم إثراؤها.

يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.

## <a name="next-steps"></a>الخطوات التالية

قم بالبناء أعلى بيانات العملاء التي تم إثرائها. أنشئ [الشرائح](segments.md)، و[المقاييس](measures.md)، وقم كذلك [بتصدير البيانات](export-destinations.md) لتقديم تجارب مخصصة لعملائك.

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى HERE Technologies، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام HERE Technologies بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.


[!INCLUDE[footer-include](../includes/footer-banner.md)]