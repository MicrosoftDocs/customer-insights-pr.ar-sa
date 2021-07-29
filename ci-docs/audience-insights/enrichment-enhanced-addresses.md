---
title: الإثراء لتعزيز العنوان
description: إثراء معلومات العنوان وضبطها لملفات تعريف العملاء باستخدام نماذج Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305416"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>إثراء ملفات تعريف العملاء من خلال العناوين المحسنة

قد تكون العناوين الموجودة في بياناتك غير مهيكلة أو غير مكتملة أو غير صحيحة. استخدم نماذج Microsoft لضبط العناوين وإثراءها في [تنسيق نموذج البيانات العامة](/common-data-model/schema/core/applicationcommon/address) لتحقيق مزيد من الدقة والتحليلات.

## <a name="how-we-enhance-addresses"></a>كيفية تحسين العناوين

يمر نموذجنا بعملية من خطوتين لتحسين العنوان. أولا، يتم تحليل العنوان لتحديد مكوناته ويضعها في تنسيق مهيكل. بعد ذلك، الذكاء الاصطناعي تصحيح القيم في العنوان وإكمالها وتوحيدها.

### <a name="example"></a>مثال

قد تكون معلومات العنوان بتنسيق غير محتواه وتحتوي على أخطاء إملائية. يمكن للنموذج إصلاح هذه المشكلات وإنشاء عناوين متسقة في ملفات تعريف العملاء الموحدة.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>القيود

تعمل العناوين المحسنة مع القيم الموجودة بالفعل في بيانات العناوين التي تم استيعابها فقط. النموذج لا يقوم بـ 

1. التحقق مما إذا كان العنوان عنوانًا صالحًا أم لا.
2. التحقق مما إذا كانت أيًا من القيم صالحة أم لا، مثل الرموز البريدية أو أسماء الشوارع.
3. تغيير القيم التي لا يتعرف عليها.

يستخدم النموذج التقنيات القائمة على التعلم الآلي لتحسين العناوين. بينما نقوم بتطبيق حد ثقة عال عند تغيير النموذج لقيمة إدخال، كما هو في أي نموذج يستند إلى التعليم الآلي، لا تكون دقة 100 بالمائة مضمونة.

## <a name="supported-countries-or-regions"></a>البلدان أو المناطق المدعومة

ونحن حاليًا ندعم إثراء العناوين في هذه البلدان أو المناطق: 

- أستراليا
- كندا
- المملكة المتحدة
- الولايات المتحدة

يجب أن تحتوي العناوين على قيمة بلد/منطقة. نحن لا نقوم بمعالجة عناوين البلدان أو المناطق غير المدعومة والعناوين التي لم يتم توفير بلد أو منطقة لها.

## <a name="configure-the-enrichment"></a>تكوين الإثراء

1. انتقل إلى **بيانات** > **إثراء**.

1. حدد **إثراء بياناتي** في الإطار المتجانب **العناوين المحسنة**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="لقطة شاشة لتجانب العناوين المحسنة.":::

1. حدد **مجموعة بيانات العميل** واختر الكيان الذي يحتوي على العناوين التي تريد إثراءها. يمكنك تحديد كيان *العميل* لإثراء العناوين في كافة ملفات تعريف العميل أو تحديد كيان شريحة لإثراء العناوين فقط في ملفات تعريف العملاء الواردة في تلك الشريحة.

1. حدد كيفية تنسيق العناوين في مجموعة البيانات الخاصة بك. اختر **عنوان سمة واحدة** إذا كانت العناوين الموجودة في بياناتك تستخدم حقلاً واحدًا. اختر **عنوان متعدد السمات** إذا كانت العناوين الموجودة في بياناتك تستخدم أكثر من حقل بيانات واحد.

   > [!NOTE]
   > البلد/المنطقة إجبارية في كل من عنواني السمة الواحدة والعناوين متعددة السمات. لن يتم إثراء العناوين التي لا تحتوي على قيم بلد/منطقة صالحة أو مدعومة.

1.  تعيين حقول العنوان من كيان العميل الموحد.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="صفحة تعيين حقل عنوان محسن.":::

1. حدد **التالي** لإكمال تعيين الحقل.

1. أدخل اسمًا للإثراء ولكيان الإخراج.

1. حدد **حفظ الإثراء** بعد مراجعة اختياراتك.

## <a name="enrichment-results"></a>نتائج الإثراء

لبدء عملية الإثراء، حدد **تشغيل** من شريط الأوامر. يمكنك أيضًا السماح للنظام بتشغيل الإثراء تلقائيًا كجزء من [التحديث المجدول](system.md#schedule-tab). يعتمد وقت المعالجة على حجم بيانات العميل.

بعد اكتمال عملية الإثراء، يمكنك مراجعة بيانات ملفات تعريف العملاء التي تم إثراؤها حديثًا ضمن **عمليات الإثراء الخاصة بي**. بالإضافة إلى ذلك ، ستجد وقت التحديث الأخير وعدد ملفات التعريف التي تم إثراؤها.

يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.

## <a name="next-steps"></a>الخطوات التالية

قم بالبناء أعلى بيانات العملاء التي تم إثرائها. أنشئ [الشرائح](segments.md) و[القياسات](measures.md) وحتى [تصدير البيانات](export-destinations.md) لتسليم تجارب مخصصة لعملائك.

[!INCLUDE[footer-include](../includes/footer-banner.md)]