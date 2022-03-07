---
title: الإثراء باستخدام HERE Technologies لجهة خارجية
description: معلومات عامة حول خدمات إثراء البيانات من طرف ثالث HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 00be15367001a5f4342d60bb284726ef7154d05c
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555291"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>إثراء ملفات تعريف العملاء بواسطة HERE Technologies (معاينة)

إن HERE Technologies عبارة عن شركة ذات منصة للبيانات المكانية توفر بيانات وخدمات تركّز على الموقع. باستخدام خدمات إثراء البيانات في HERE Technologies، يمكنك تكوين فهم أكثر دفة لموقع العملاء مع تسوية العناوين واستخراج خط الطول وخط العرض والمزيد.

## <a name="prerequisites"></a>المتطلبات الأساسية

لتكوين عمليات إثراء HERE Technologies، يجب استيفاء المتطلبات الأساسية التالية:

- لديك اشتراك نشط في HERE Technologies. للحصول على اشتراك، يمكنك [التسجيل هنا](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) أو [الاتصال بشركة HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) مباشرةً. [اعرف المزيد حول إثراء الموقع من HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- يتوفر [اتصال](connections.md) HERE *أو* لديك أذونات [المسؤول](permissions.md#administrator) ومفتاح HERE Technologies API.

## <a name="configure-the-enrichment"></a>تكوين الإثراء

1. انتقل إلى **بيانات** > **إثراء**. 

1. حدد **إثراء بياناتي** في الإطار المتجانب HERE Technologies وحدد **الشروع في العمل**.

   > [!div class="mx-imgBorder"]
   > ![الإطار المتجانب HERE Technologies.](media/HERE-tile.png "الإطار المتجانب HERE Technologies")

1. حدد [اتصالاً](connections.md) من القائمة المنسدلة. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر. إذا كنت أحد المسؤول، يمكنك إنشاء اتصال بتحديد **إضافة اتصال**. اختر **HERE Technologies** من القائمة المنسدلة. 

1. حدد **الاتصال بـ HERE Technologies** لتأكيد التحديد.

1.  حدد **التالي** واختر **مجموعة بيانات العميل** التي تريد إثراؤها باستخدام بيانات الموقع من HERE Technologies. يمكنك تحديد كيان **العميل** لإثراء جميع ملفات تعريف العملاء أو تحديد كيان شريحة لإثراء فقط ملفات تعريف العملاء الموجودة في تلك الشريحة.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="لقطة شاشة عند اختيار مجموعة بيانات العميل.":::

1. اختر إذا كنت تريد تعيين الحقول إلى العنوان الرئيسي و/أو الثانوي. يمكنك تحديد تعيين حقل لكل من العناوين وإثراء ملفات التعريف لكلا العناوين بشكل منفصل. على سبيل المثال، إذا كان هناك المنزل وعنوان العمل. حدد **التالي**.

1. حدد الحقول التي سيتم استخدامها من ملفات التعريف الموحدة للبحث عن بيانات الموقع المطابقة من تقنيات HERE يجب تعبئة الحقلين **الشارع 1** و **الرمز البريدي** للعنوان الرئيسي و/أو الثانوي المحدد.‬ للحصول على دقة مطابقة أعلى، يمكن إضافة المزيد من الحقول.

   > [!div class="mx-imgBorder"]
   > ![صفحة تكوين إثراء HERE Technologies.](media/enrichment-HERE-configuration.png "صفحة تكوين إثراء HERE Technologies")

1. حدد **التالي** لإكمال تعيين الحقل.

1. قدم اسمًا لعملية الإثراء. 

1. حدد **حفظ الإثراء** بعد مراجعة اختياراتك.

## <a name="configure-the-connection-for-here-technologies"></a>تكوين الاتصال لـ HERE Technologies 

يلزم أن تكون المسؤول لتكوين الاتصالات. حدد **إضافة اتصال** عند تكوين عملية إثراء *أو* انتقل إلى **المسؤول** > **الاتصالات** وحدد **إعداد** في تجانب HERE Technologies.

1. أدخل اسما للاتصال في مربع **اسم العرض**.

1. قم بتوفير مفتاح واجهة برمجة تطبيقات صالح لـ HERE Technologies.

1. راجع **خصوصية البيانات والامتثال** وقدم الموافقة عليها بتحديد **أوافق**.

1. حدد **التحقق** للتحقق من التكوين.

1. بعد إكمال التحقق، حدد **حفظ**.

   > [!div class="mx-imgBorder"]
   > ![صفحة تكوين الاتصال بـ HERE technologies.](media/enrichment-HERE-connection.png "صفحة تكوين الاتصال بـ HERE technologies")

## <a name="enrichment-results"></a>نتائج الإثراء

لبدء عملية الإثراء، حدد **تشغيل** من شريط الأوامر. يمكنك أيضًا السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من [التحديث المجدول](system.md#schedule-tab). سيعتمد وقت المعالجة على حجم بيانات العملاء وأوقات استجابة API من HERE Technologies.

بعد اكتمال عملية الإثراء، يمكنك مراجعة بيانات ملفات تعريف العملاء التي تم إثراؤها حديثًا ضمن **عمليات الإثراء الخاصة بي**. بالإضافة إلى ذلك ، ستجد وقت التحديث الأخير وعدد ملفات التعريف التي تم إثراؤها.

يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.

## <a name="next-steps"></a>الخطوات التالية

قم بالبناء أعلى بيانات العملاء التي تم إثرائها. أنشئ [الشرائح](segments.md) و[القياسات](measures.md) وحتى [تصدير البيانات](export-destinations.md) لتسليم تجارب مخصصة لعملائك.

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى HERE Technologies، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام HERE Technologies بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
