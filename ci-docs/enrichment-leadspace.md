---
title: إثراء ملفات تعريف الشركات بواسطة خدمات إثراء البيانات من طرف ثالث Leadspace‬
description: معلومات عامة حول خدمات إثراء البيانات من طرف ثالث Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 08a4c56eb1c387015fd9e985a0c9484a13236fcf
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645511"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>إثراء ملفات تعريف الشركات من خلال Leadspace (معاينة)

Leadspace هي شركة متخصصة في علوم البيانات، توفر نظامًا أساسيًا لبيانات عملاء معاملات شركة إلى شركة. إنه يمكّن البيئات ذات ملفات تعريف العملاء الموحدة بناءً على الحسابات لإثراء بياناتهم. قم بإثراء *ملفات تعريف العملاء* بسمات مثل حجم الشركة أو الموقع أو الصناعة. قم بإثراء *ملفات تعريف جهات الاتصال* بسمات مثل العنوان أو الشخصية أو التحقق من البريد الإلكتروني.

## <a name="prerequisites"></a>المتطلبات الأساسية

لتكوين Leadspace، يجب استيفاء المتطلبات الأساسية التالية:

- لديك ترخيص Leadspace نشط.
- لديك [ملفات تعريف العملاء الموحدة](customer-profiles.md) استنادًا إلى الحسابات.
- تم بالفعل تكوين اتصال Leadspace بواسطة مسؤول أو لديك أذونات [المسؤول](permissions.md#admin) و "المفتاح الدائم" (المشار إليه بـ **رمز Leadspace المميز**). اتصل بـ [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) مباشرةً للاطلاع على تفاصيل حول منتجها.

## <a name="configure-the-enrichment"></a>تكوين الإثراء

1. انتقل إلى **بيانات** > **إثراء**.

1. حدد **إثراء بياناتي** في الإطار المتجانب Leadspace وحدد **الشروع في العمل**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="لقطة شاشة للإطار المتجانب Leadspace.":::

1. حدد [اتصالاً](connections.md) من القائمة المنسدلة. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر. إذا كنت أحد المسؤول، يمكنك إنشاء اتصال بتحديد **إضافة اتصال** واختيار **Leadspace**. 

1. حدد **الاتصال بـ Leadspace** لتأكيد الاتصال.

1. حدد **التالي** واختر **مجموعة بيانات العميل** التي تريد إثراؤها باستخدام بيانات الشركة من Leadspace. يمكنك تحديد كيان **العميل** لإثراء جميع ملفات تعريف العملاء أو تحديد كيان شريحة لإثراء فقط ملفات تعريف العملاء الموجودة في تلك الشريحة.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="لقطة شاشة عند اختيار مجموعة بيانات العميل.":::

1. حدد **التالي** وحدد الحقول من ملفات التعريف الموحدة المستخدمة للبحث عن بيانات الشركة المطابقة من Leadspace. الحقل **اسم الشركة** مطلوب. للحصول على دقة مطابقه أعلى، يمكن إضافة الحقلين **موقع ويب للشركة** و **موقع الشركة**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="جزء تعيين حقول Leadspace.":::

1. حدد **التالي** لإكمال تعيين الحقل.

1. حدد مربع الاختيار إذا كانت لديك *ملفات تعريف جهات الاتصال* التي ترغب في إثرائها. سيعين Customer Insights الحقول المطلوبة تلقائيًا.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="إثراء سجلات جهات اتصال Leadspace.":::
 
1. قدم اسمًا لعملية الإثراء وحدد **حفظ الإثراء** بعد مراجعة خياراتك.


## <a name="configure-the-connection-for-leadspace"></a>تكوين الاتصال لـ Leadspace 

يلزم أن تكون المسؤول لتكوين الاتصالات. حدد **إضافة اتصال** عند تكوين عملية إثراء *أو* انتقل إلى **المسؤول** > **الاتصالات** وحدد **إعداد** في تجانب Leadspace.

1. حدد **بدء الاستخدام‬**. 

1. أدخل اسما للاتصال في مربع **اسم العرض**.

1. قدم رمز Leadspace مميزًا وصالحًا.

1. راجع **خصوصية البيانات والامتثال** وقدم الموافقة عليها بتحديد **أوافق**.

1. حدد **التحقق** للتحقق من التكوين.

1. بعد إكمال التحقق، حدد **حفظ**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="صفحة تكوين الاتصال بـ Leadspace.":::

## <a name="enrichment-results"></a>نتائج الإثراء

بعد تحديث الإثراء، يمكنك مراجعة بيانات الشركة التي تم إثراؤها حديثًا والموجودة ضمن [عمليات الإثراء الخاصة بي‬](enrichment-hub.md). يمكنك العثور على وقت آخر تحديث وعدد ملفات تعريف التي تم إثراؤها.

يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.

لمزيد من المعلومات، راجع [مؤشرات الأداء الأساسية API لـ Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>الخطوات التالية


[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Leadspace، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Leadspace بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.


[!INCLUDE [footer-include](includes/footer-banner.md)]
