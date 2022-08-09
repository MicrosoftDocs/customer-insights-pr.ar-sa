---
title: إثراء ملفات تعريف الشركة باستخدام Dun & Bradstreet (إصدار أولي)
description: معلومات عامة حول إثراء الطرف الثالث Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 71b35e4295e19c13edadc6548ac79715555e8183
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196010"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>إثراء ملفات تعريف الشركة باستخدام Dun & Bradstreet (إصدار أولي)

يوفر Dun & Bradstreet البيانات التجارية والتحليلات والرؤى للشركات. وهي تمكن العملاء من خلال ملفات تعريف العملاء الموحدة للشركات من إثراء بياناتهم. تشمل عمليات الإثراء على سمات مثل رقم DUNS وحجم الشركة والموقع والصناعة وغير ذلك الكثير.

## <a name="prerequisites"></a>المتطلبات

- ترخيص [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) نشط.
- [ملفات تعريف العملاء الموحدة](customer-profiles.md) للشركات.
- إعداد [مشروع](#set-up-your-dun--bradstreet-project) Dun & Bradstreet.
- [تكوين](#configure-a-connection-for-dun--bradstreet) [اتصال](connections.md) Dun & Bradstreet بواسطة مسؤول.

## <a name="set-up-your-dun--bradstreet-project"></a>إعداد مشروع Dun & Bradstreet

بصفتك مستخدمًا مرخصًا لـ Dun & Bradstreet، يمكنك إعداد مشروع في [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. سجّل الدخول إلى [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). لاسترداد بيانات الاعتماد، [استعادة كلمة المرور](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. قم بتنزيل [ملف نموذج csv الخاص بنا](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) الذي سيتم استخدامه لتعيين حقول Customer Insights لحقول Dun & Bradstreet المقابلة.

1. قم بتحميل الملف في خطوة **تحميل البيانات** الخاصة بخبرة إنشاء مشروع Dun &Uploadstreet.

1. حدد النقاط الأفقية تحت **المصدر** ذي الصلة في مشروع Dun & Bradstreet الذي تم إنشاؤه حديثًا لمعرفة الخيارات المتاحة.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="لقطة شاشة من النقاط في مشروع Dun & Bradstreet.":::

1. اختر **تفاصيل الحصول على S3**. قم بتخزين هذه المعلومات في مكان آمن. ستحتاج إليه من أجل [إعداد الاتصال للإثراء](#configure-a-connection-for-dun--bradstreet) في Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="لقطة شاشة لتحديد معلومات حول s3 في مشروع Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>تكوين اتصال لـ Dun & Bradstreet

يجب أن تكون [مسؤول](permissions.md#admin) Customer Insights وأن تتوفر لديك بيانات الاعتماد من Dun & Bradstreet Connect.

1. حدد **إضافة اتصال** عند تكوين إثراء أو انتقل إلى **المسؤول‏‎** > **اتصالات** وحدد **الإعداد** على الإطار المتجانب Dun & Bradstreet.

1. أدخل اسماً للاتصال.

1. قدم بيانات اعتماد Dun & Bradstreet صالحة وتفاصيل مشروع Dun & Bradstreet *المنطقة ومسار مجلد الإسقاط واسم مجلد الإسقاط*. يمكنك [الحصول على هذه المعلومات](#set-up-your-dun--bradstreet-project) من مشروع Dun & Bradstreet.

1. راجع [خصوصية البيانات والامتثال](#data-privacy-and-compliance) وقدم الموافقة عليها بتحديد **أوافق**.

1. حدد **التحقق** للتحقق من صحة التكوين ثم حدد **حفظ** .

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="صفحة تكوين اتصال Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Dun & Bradstreet، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات بناءً على التعليمات الخاصة بك، ولكنك مسؤول عن ضمان أن يفي Dun & Bradstreet بأي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.

## <a name="supported-countries-or-regions"></a>البلدان أو المناطق المدعومة

نحن ندعم حاليًا خيارات البلد/المنطقة التالية: كندا (الإنجليزية) أو الولايات المتحدة (الإنجليزية).

## <a name="configure-the-enrichment"></a>تكوين الإثراء

1. انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.

1. حدد **إثراء بياناتي‬** على **بيانات الشركة** للإطار المتجانب Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="لقطة شاشة للإطار المتجانب Dun &Screenshotstreet.":::

1. راجع النظرة العامة، ثم حدد **التالي**.

1. حدد الاتصال وأكده. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. حدد **التالي**.

1. حدد **مجموعة بيانات العميل** واختر ملف التعريف أو المقطع التي ترغب في إثرائها بواسطة بيانات الشركة من Dun & Bradstreet. يقوم كيان *العميل* بإثراء جميع ملفات تعريف عملائك في حين تثري المقطع فقط ملفات تعريف العملاء الموجودة في تلك المقطع.

1. حدد أنواع الحقول من ملفات التعريف الموحدة التي يجب استخدامها لمطابقة بيانات الشركة من Dun & Bradstreet. واحد على الأقل من حقول **الاسم والعنوان** أو **الهاتف** أو **البريد الإلكتروني** مطلوب

1. حدد **التالي**

1. عيّن حقولك إلى بيانات الشركة من Dun & Bradstreet. يلزم وجود حقلي **رقمDUNS** أو **اسم الشركة** و **البلد**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="جزء تعيين حقل Dun & Bradstreet.":::

1. حدد **التالي** لإكمال تعيين الحقل.

1. قم بتوفير **اسم** للإثراء و **اسم كيان الإخراج**.

1. حدد **حفظ الإثراء** بعد مراجعة اختياراتك.

1. حدد **تشغيل** لبدء عملية المعالجة، أو حدد إغلاق للعودة إلى صفحة **عمليات الإثراء**.

## <a name="view-enrichment-results"></a>عرض نتائج إثراء البيانات

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>الخطوات التالية

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
