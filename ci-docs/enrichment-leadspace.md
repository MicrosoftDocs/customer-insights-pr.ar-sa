---
title: إثراء ملفات تعريف الشركة باستخدام Leadspace (إصدار أولي)
description: معلومات عامة حول خدمات إثراء البيانات من طرف ثالث Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 3f23fe7177f931db3e3179970915d0cd3c736f87
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196194"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>إثراء ملفات تعريف الشركة باستخدام Leadspace (إصدار أولي)

Leadspace هي شركة متخصصة في علوم البيانات، توفر نظامًا أساسيًا لبيانات عملاء حركات شركة إلى شركة. إنه يمكّن البيئات ذات ملفات تعريف العملاء الموحدة بناءً على الحسابات لإثراء بياناتهم. قم بإثراء *ملفات تعريف العملاء* بسمات مثل حجم الشركة أو الموقع أو الصناعة. قم بإثراء *ملفات تعريف جهات الاتصال* بسمات مثل العنوان أو الشخصية أو التحقق من البريد الإلكتروني.

## <a name="prerequisites"></a>المتطلبات

- ترخيص Leadspace نشط.
- [ملفات تعريف العملاء الموحدة](customer-profiles.md) استنادًا إلى الحسابات.
- [تكوين](#configure-the-connection-for-leadspace) [اتصال](connections.md) Leadspace بواسطة مسؤول. اتصل بـ [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) مباشرةً للاطلاع على تفاصيل حول منتجها.

## <a name="configure-the-connection-for-leadspace"></a>تكوين الاتصال لـ Leadspace

يجب أن تكون [مسؤولاً](permissions.md#admin) في Customer Insights ولديك "المفتاح الدائم" (يُشار إليه باعتباره **الرمز المميز Leadspace**).

1. حدد **إضافة اتصال** عند تكوين عملية إثراء أو انتقل إلى **المسؤول‏‎** > **الاتصالات‏‎** وحدد **إعداد** على الإطار المتجانب لـ Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="صفحة تكوين الاتصال بـ Leadspace.":::

1. أدخل اسمًا للاتصال، ورمزًا مميزًا صالحًا لـ Leadspace.

1. راجع [خصوصية البيانات والامتثال](#data-privacy-and-compliance) وقدم الموافقة عليها بتحديد **أوافق**.

1. حدد **التحقق** للتحقق من صحة التكوين ثم حدد **حفظ** .

### <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Leadspace، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Leadspace بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.

## <a name="configure-the-enrichment"></a>تكوين الإثراء

1. انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.

1. حدد **إثراء البيانات** على **بيانات الشركة** من الإطار المتجانب Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="لقطة شاشة للإطار المتجانب Leadspace.":::

1. راجع النظرة العامة، ثم حدد **التالي**.

1. حدد الاتصال. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. حدد **التالي**.

1. حدد **مجموعة بيانات العميل** واختر ملف التعريف أو المقطع التي ترغب في إثرائها بواسطة بيانات الشركة من Leadspace. يقوم كيان *العميل* بإثراء جميع ملفات تعريف عملائك في حين تثري المقطع فقط ملفات تعريف العملاء الموجودة في تلك المقطع.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="لقطة شاشة عند اختيار مجموعة بيانات العميل.":::

1. حدد نوع الحقول من ملفات التعريف الموحدة التي تريد استخدامها لمطابق العنوان الأساسي و/أو العنوان الثانوي. يمكنك تحديد تعيين حقل لكل من العناوين وإثراء ملفات التعريف لكلا العناوين بشكل منفصل. على سبيل المثال، لعنوان المنزل وعنوان العمل. حدد **التالي**.

1. عيّن حقولك إلى بيانات الشركة من Leadspace. الحقل **اسم الشركة** مطلوب. للحصول على دقة مطابقه أعلى، يمكن إضافة الحقلين **موقع ويب للشركة** و **موقع الشركة**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="جزء تعيين حقول Leadspace.":::

1. حدد **التالي** لإكمال تعيين الحقل.

1. حدد مربع الاختيار إذا كانت لديك *ملفات تعريف جهات الاتصال* التي ترغب في إثرائها. سيعين Customer Insights الحقول المطلوبة تلقائيًا.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="إثراء سجلات جهات اتصال Leadspace.":::

1. حدد **التالي**.

1. قم بتوفير **اسم** للإثراء و **اسم كيان الإخراج**.

1. حدد **حفظ الإثراء** بعد مراجعة اختياراتك.

1. حدد **تشغيل** لبدء عملية المعالجة، أو حدد إغلاق للعودة إلى صفحة **عمليات الإثراء**.

## <a name="view-enrichment-results"></a>عرض نتائج إثراء البيانات

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

لمزيد من المعلومات، راجع [مؤشرات الأداء الأساسية API لـ Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>الخطوات التالية

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
