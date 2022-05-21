---
title: إثراء ملفات تعريف الشركة باستخدام Dun & Bradstreet
description: معلومات عامة حول إثراء الطرف الثالث Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755384"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>إثراء ملفات تعريف الشركة باستخدام Dun & Bradstreet (إصدار أولي)

يوفر Dun & Bradstreet البيانات التجارية والتحليلات والرؤى للشركات. وهي تمكن العملاء من خلال ملفات تعريف العملاء الموحدة للشركات من إثراء بياناتهم. تشمل عمليات الإثراء على سمات مثل رقم DUNS وحجم الشركة والموقع والصناعة وغير ذلك الكثير.

## <a name="prerequisites"></a>المتطلبات

لتكوين إثراء Dun & Bradstreet، يجب استيفاء المتطلبات الأساسية التالية:

- لديك ترخيص [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights) نشط.
- لديك [ملفات تعريف عملاء موحدة](customer-profiles.md) للشركات.
- تم تكوين [اتصال](connections.md) Dun & Bradstreet بواسطة المسؤول. يمكنك إنشائه إذا كان لديك أذونات [المسؤول](permissions.md#admin) وبيانات الاعتماد من Dun & Bradstreet Connect.

## <a name="setting-up-your-dun--bradstreet-project"></a>إعداد مشروع Dun & Bradstreet الخاص بك

بصفتك مستخدمًا مرخصًا لـ Dun & Bradstreet ، يمكنك إعداد مشروع في [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).


1. سجّل الدخول إلى [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). لاسترداد بيانات الاعتماد، [استعادة كلمة المرور](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. قم بتنزيل [ملف نموذج csv الخاص بنا](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) الذي سيتم استخدامه لتعيين حقول Customer Insights لحقول Dun & Bradstreet المقابلة.

1. قم بتحميل الملف في خطوة **تحميل البيانات** الخاصة بخبرة إنشاء مشروع Dun &Uploadstreet.

1. حدد النقاط الأفقية تحت **المصدر** ذي الصلة في مشروع Dun & Bradstreet الذي تم إنشاؤه حديثًا لمعرفة الخيارات المتاحة.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="لقطة شاشة من النقاط في مشروع Dun & Bradstreet.":::

1. اختر **تفاصيل الحصول على S3**. قم بتخزين هذه المعلومات في مكان آمن. ستحتاج إليه من أجل [إعداد الاتصال للإثراء](#configure-a-connection-for-dun--bradstreet) في Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="لقطة شاشة لتحديد معلومات حول s3 في مشروع Dun & Bradstreet.":::

## <a name="configure-the-enrichment"></a>تكوين الإثراء

1. انتقل إلى **بيانات** > **إثراء**.

1. حدد **إثراء بياناتي** في مربع Dun & Bradstreet وحدد **‬‏‫‏‫البدء في الاستخدام**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="لقطة شاشة للإطار المتجانب Dun &Screenshotstreet.":::

1. حدد [اتصالاً](connections.md) من القائمة المنسدلة. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر. إذا كنت مسؤولاً، يمكنك إنشاء اتصال. حدد **إضافة اتصال** واختر **Dun & Bradstreet**.

1. حدد **الاتصال بـ Dun &Connectstreet** لتأكيد الاتصال.

1. حدد **التالي** واختر **مجموعة بيانات العملاء** التي تريد إثرائها ببيانات الشركة من Dun & Bradstreet. يمكنك تحديد كيان **العميل** لإثراء جميع ملفات تعريف العملاء أو تحديد كيان مقطع لإثراء فقط ملفات تعريف العملاء الموجودة في ذلك المقطع.

1. حدد **التالي** وحدد الحقول من ملفات التعريف الموحدة المستخدمة للبحث عن بيانات الشركة المطابقة من Dun & Bradstreet. يلزم وجود حقلي **رقمDUNS** أو **اسم الشركة** و **البلد**. يدعم حقل البلد [رموز البلد المكونة من حرفين أو ثلاثة أحرف](https://www.iso.org/iso-3166-country-codes.html)، واسم البلد باللغة الإنجليزية، واسم البلد باللغة الأم، و بادئة الهاتف. تتضمن بعض المتغيرات المشتركة بين البلدان ما يلي:

- US: الولايات المتحدة الأمريكية، الولايات المتحدة الأمريكية، أمريكا.
- CA: كندا.
- GB: المملكة المتحدة، UK، بريطانيا العظمى، GB، المملكة المتحدة لبريطانيا العظمى وأيرلندا الشمالية، المملكة المتحدة لبريطانيا العظمى.
- AU: أستراليا، اكومنولث أستراليا.
- FR: فرنسا، الجمهورية الفرنسية.
- DE: ألمانيا، ألمانيا، دويتشلاند، ألماني، جمهورية ألمانيا الاتحادية، جمهورية ألمانيا.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="جزء تعيين حقل Dun & Bradstreet.":::

1. حدد **التالي** لإكمال تعيين الحقل.

1. قدم اسمًا لعملية الإثراء وحدد **حفظ الإثراء** بعد مراجعة خياراتك.

## <a name="configure-a-connection-for-dun--bradstreet"></a>تكوين اتصال لـ Dun & Bradstreet

يلزم أن تكون المسؤول لتكوين الاتصالات. حدد **إضافة اتصال** عند تكوين إثراء *أو* انتقل إلى **المسؤول** > **اتصالات** وحدد **الإعداد** على الإطار المتجانب Dun & Bradstreet.

1. حدد **بدء الاستخدام‬**.

1. أدخل اسما للاتصال في مربع **اسم العرض**.

1. قدم بيانات اعتماد Dun & Bradstreet صالحة وتفاصيل مشروع Dun & Bradstreet *المنطقة ومسار مجلد الإسقاط واسم مجلد الإسقاط*. يمكنك [الحصول على هذه المعلومات](#setting-up-your-dun--bradstreet-project) من مشروع Dun & Bradstreet.

1. راجع **خصوصية البيانات والامتثال** وقدم الموافقة عليها بتحديد **أوافق**.

1. حدد **التحقق** للتحقق من التكوين.

1. بعد إكمال التحقق، حدد **حفظ**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="صفحة تكوين اتصال Dun & Bradstreet.":::

## <a name="enrichment-results"></a>نتائج الإثراء

بعد تحديث الإثراء، يمكنك مراجعة بيانات الشركة التي تم إثراؤها حديثًا والموجودة ضمن [عمليات الإثراء الخاصة بي‬](enrichment-hub.md). يمكنك العثور على وقت آخر تحديث وعدد ملفات تعريف التي تم إثراؤها.

يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.

## <a name="next-steps"></a>الخطوات التالية

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Dun & Bradstreet، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات بناءً على التعليمات الخاصة بك ، ولكنك مسؤول عن ضمان أن يفي Dun & Bradstreet بأي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.

[!INCLUDE[footer-include](includes/footer-banner.md)]
