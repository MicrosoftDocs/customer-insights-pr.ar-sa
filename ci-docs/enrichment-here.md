---
title: إثراء ملفات تعريف العملاء مع HERE Technologies (إصدار أولي)
description: معلومات عامة حول خدمات إثراء البيانات من طرف ثالث HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237842"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>إثراء ملفات تعريف العملاء مع HERE Technologies (إصدار أولي)

إن HERE Technologies عبارة عن شركة ذات منصة للبيانات المكانية توفر بيانات وخدمات تركّز على الموقع. تحسن خدمات إثراء البيانات في HERE Technologies دقة معلومات الموقع حول عملائك. وهي توفر معايرة العنوان‬ واستخراج خطي الطول والعرض، وغير ذلك الكثير.

## <a name="prerequisites"></a>المتطلبات

- اشتراك نشط في HERE Technologies للحصول على اشتراك، يمكنك [التسجيل هنا](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) أو [التواصل مع HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) مباشرةً. [اعرف المزيد حول إثراء الموقع من HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- [تكوين](#configure-the-connection-for-here-technologies) [اتصال](connections.md) HERE بواسطة مسؤول.

## <a name="configure-the-connection-for-here-technologies"></a>تكوين الاتصال لـ HERE Technologies

يجب أن تكون [مسؤولاً](permissions.md#admin) في Customer Insights وأن يكون لديك مفتاح API نشط لـ HERE Technologies.

1. حدد **إضافة اتصال** عند تكوين عملية إثراء أو انتقل إلى **المسؤول‏‎** > **الاتصالات‏‎** وحدد **Set up** على الإطار المتجانب HERE Technologies.

1. أدخل اسمًا للاتصال، ومفتاح API صالحًا لـ HERE Technologies.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **التحقق** للتحقق من صحة التكوين ثم حدد **حفظ** .

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="صفحة تكوين الاتصال بـ HERE technologies.":::

## <a name="configure-the-enrichment"></a>تكوين الإثراء

1. انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.

1. حدد **إثراء بياناتي** على **الموقع** من الإطار المتجانب لـ HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="الإطار المتجانب HERE Technologies.":::

1. راجع النظرة العامة، ثم حدد **التالي**.

1. حدد الاتصال. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. حدد **التالي**.

1. حدد **مجموعة بيانات العميل** واختر ملف التعريف أو المقطع التي ترغب في إثرائها بواسطة البيانات من HERE Technologies. يقوم كيان *العميل* بإثراء جميع ملفات تعريف عملائك في حين تثري المقطع فقط ملفات تعريف العملاء الموجودة في تلك المقطع.

1. حدد نوع الحقول من ملفات التعريف الموحدة التي تريد استخدامها لمطابق العنوان الأساسي و/أو العنوان الثانوي. يمكنك تحديد تعيين حقل لكل من العناوين وإثراء ملفات التعريف لكلا العناوين بشكل منفصل. على سبيل المثال، لعنوان المنزل وعنوان العمل. حدد **التالي**.

1. عيّن حقولك إلى البيانات من HERE Technologies. يجب تعبئة الحقلين **الشارع 1** و **الرمز البريدي** للعنوان الرئيسي و/أو الثانوي المحدد.‬ للحصول على دقة تطابق أعلى، أضف المزيد من الحقول.

1. حدد **التالي** لإكمال تعيين الحقل.

1. قم بتوفير **اسم** للإثراء و **اسم كيان الإخراج**.

1. حدد **حفظ الإثراء** بعد مراجعة اختياراتك.

1. حدد **تشغيل** لبدء عملية المعالجة، أو حدد إغلاق للعودة إلى صفحة **عمليات الإثراء**.

## <a name="view-enrichment-results"></a>عرض نتائج إثراء البيانات

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

يوفر الخيار **عدد العملاء الذين تم إثراؤهم بواسطة الحقل** التنقل لأسفل في تغطية كل حقل تم إثراؤه.

## <a name="next-steps"></a>الخطوات التالية

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
