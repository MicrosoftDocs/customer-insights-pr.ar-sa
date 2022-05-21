---
title: مطابقة الكيانات لتوحيد البيانات
description: مطابقة الكيانات لإنشاء ملفات تعريف العملاء الموحدة.
recommendations: false
ms.date: 05/05/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bc470dd932c2c981adc5840bb52d60f8dfe0de61
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740933"
---
# <a name="match-conditions"></a>شروط المطابقة

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

تحدد هذه الخطوة في التوحيد ترتيب المطابقة وقواعد المطابقة عبر الكيانات. تتطلب هذه الخطوة كيانين على الأقل.

> [!NOTE]
> بمجرد إنشاء شروط المطابقة وتحديد **التالي**، لا يمكنك إزالة الكيان أو السمة المحددة. إذا لزم الأمر، حدد **السابق** لمراجعة الكيانات والسمات المحددة قبل المتابعة.

## <a name="include-enriched-entities-preview"></a>تضمين الكيانات التي تم إثراؤها (إصدار أولي)

إذا قمت بإثراء الكيانات على مستوى مصدر البيانات للمساعدة في تحسين نتائج التوحيد، فحددها. لمزيد من المعلومات، راجع [الإثراء لمصادر البيانات](data-sources-enrichment.md). إذا قمت بتحديد الكيانات الغنية في صفحة **السجلات المكررة**، فلن تحتاج إلى تحديدها مرة أخرى.

1. في صفحة **شروط المطابقة**، حدد **استخدام الكيانات الغنية** بأعلى الصفحة.

1. من جزء **استخدام الكيانات التي تم إثراؤها**، اختر كيانًا واحدًا أو أكثر من الكيانات التي تم إثراؤها.

1. حدِّد **تم**.

## <a name="specify-the-match-order"></a>حدد ترتيب المطابقة.

يقوم كل تطابق بتوحيد كيانين أو أكثر في كيان واحد مدمج. وفي الوقت نفسه، يحتفظ بسجلات العملاء الفريدة. يشير ترتيب المطابقة إلى الترتيب الذي يحاول النظام مطابقة السجلات به.

> [!IMPORTANT]
> الكيان الأول في القائمة يسمى الكيان الأساسي. يعمل الكيان الأساسي كأساس لمجموعة بيانات ملفات التعريف الموحدة. ستتم إضافة الكيانات الإضافية التي تم تحديدها إلى هذا الكيان.
>
> اعتبارات مهمة:
>
> - اختر الكيان الذي يحتوي على بيانات الملف الشخصي الأكثر اكتمالا وموثوقية حول عملائك ككيان أساسي.
> - اختر الكيان الذي له العديد من السمات المشتركة مع الكيانات الأخرى (على سبيل المثال، الاسم أو رقم الهاتف أو عنوان البريد الإلكتروني) ككيان أساسي.

1. في صفحة **شروط المطابقة**، استخدم سهمي التحريك لأعلى ولأسفل لنقل الكيانات بالترتيب الذي تريده، أو قم بسحبها وإفلاتها. على سبيل المثال، حدد **Contacts:eCommerce** باعتباره الكيان الأساسي و **CustomerLoyalty:Loyalty** باعتباره الكيان الثاني.

1. للحصول على كل سجل في الكيان كعميل فريد بغض النظر عما إذا تم العثور على تطابق، حدد **تضمين كل السجلات**. يتم تضمين أي سجلات في هذا الكيان لا تتطابق مع السجلات في أي كيانات أخرى في ملف التعريف الموحد. السجلات التي ليس لها تطابق تسمى الفردي.
  
تتم مطابقة الكيان الأساسي *Contacts:eCommerce* مع الكيان التالي *CustomerLoyalty:Loyalty*. تتم مطابقة مجموعة البيانات الناتجة من خطوة المطابقة الأولى مع الكيان التالي إذا كان لديك أكثر من كيانين.

:::image type="content" source="media/m3_match.png" alt-text="لقطة شاشة لترتيب المطابقة المحدد للكيانات." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>تحديد قواعد أزواج المطابقة

تحدد قواعد المطابقة المنطق الذي سيتم من خلاله مطابقة زوج معين من الكيانات. تتكون القاعدة من شرط واحد أو أكثر.

يعني التحذير الموجود بجوار اسم الكيان أنه لم يتم تحديد قاعدة مطابقة لزوج مطابقة.

1. حدد **إضافة قاعدة** لزوج كيان لتحديد قواعد المطابقة.

1. في جزء **إضافة القاعدة**، قم بتكوين الشروط للقاعدة.

   :::image type="content" source="media/m3_add_rule.png" alt-text="لقطة شاشة لجزء إضافة القاعدة.":::

   - **تحديد الكيان/الحقل (الصف الأول)**: اختر كيانًا ذا صلة وسمة لتحديد خاصية سجل من المحتمل أن تكون فريدة للعميل. على سبيل المثال، رقم هاتف أو عنوان بريد إلكتروني. تجنب المطابقة حسب السمات من نوع النشاط. على سبيل المثال، من المرجح عدم عثور معرف الشراء على أي مطابقة في أنواع السجلات الأخرى.

   - **تحديد الكيان/الحقل (الصف الثاني)**: اختر سمة تتعلق بسمة الكيان المحدد في الصف الأول.

   - **تسوية**: حدد من خيارات التسوية التالية للسمات المحددة.
     - **الأرقام**: تحويل أنظمة رقمية أخرى، مثل الأرقام الرومانية، إلى أرقام عربية. يتحوّل *VIII* إلى *8*.
     - **الرموز**: إزالة كافة الرموز والأحرف الخاصة. يتحوّل *Head&Shoulder* إلى *HeadShoulder*.
     - **تحويل النص إلى أحرف صغيرة**: تحويل كل الأحرف إلى أحرف صغيرة. يتحوّل *ALL CAPS and Title Case* إلى *all caps and title case*.
     - **النوع (الهاتف، الاسم، العنوان، المؤسسة)**: توحيد الأسماء والعناوين وأرقام الهواتف والعناوين والمؤسسات.
     - **Unicode إلى ASCII**: تحويل رموز Unicode إلى أحرف ASCII. يتحوّل */u00B2* إلى *2*.
     - **مسافة فارغة**: إزالة كافة المسافات. يتحوّل *Hello   World* إلى *HelloWorld*.

   - **الدقة**: تعيين مستوى الدقة لتطبيق هذا الشرط.
     - **أساسي**: اختر من *منخفض (30%)*، و *متوسط (60%)*، و *مرتفع (80%)* و *دقيق (100%)*. حدد **تام** لمطابقة السجلات التي تطابق 100 بالمائة فقط.
     - **مخصص**: تعيين نسبة مئوية تحتاج السجلات إلى مطابقتها. سيطابق النظام فقط السجلات التي تجتاز هذا الحد.

   - **الاسم**: اسم القاعدة.

1. لمطابقة الكيانات فقط إذا كانت السمات تفي بشروط متعددة، حدد **إضافة** > **إضافة شرط** لإضافة المزيد من الشروط إلى قاعدة المطابقة. يتم توصيل الشروط بعامل التشغيل المنطقي AND وبالتالي يتم تنفيذها فقط إذا تم استيفاء جميع الشروط.

1. بشكل اختياري، ضع في اعتبارك الخيارات المتقدمة مثل [الاستثناءات](#add-exceptions-to-a-rule) أو [شروط المطابقة المخصصة](#specify-custom-match-conditions).

1. حدد **تم** لإنهاء القاعدة.

1. بشكل اختياري، [أضف المزيد من القواعد](#add-rules-to-a-match-pair).

1. انقر فوق **التالي**.

> [!div class="nextstepaction"]
> [الخطوة التالية: توحيد الحقول](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>إضافة قواعد إلى زوج مطابقة

تمثل قواعد المطابقة مجموعات من الشروط. لمطابقة الكيانات حسب الشروط استنادًا إلى سمات متعددة، أضف المزيد من القواعد.

1. حدد **إضافة قاعدة** للكيان الذي ترغب في إضافة قواعد إليه.

1. اتبع الخطوات في [تحديد قواعد أزواج المطابقة‬](#define-rules-for-match-pairs).

> [!NOTE]
> يعتد ترتيب القواعد أمراً مهماً. تحاول خوارزمية المطابقة مطابقة سجل عميل معين على أساس القاعدة الأولى وتستمر في القاعدة الثانية فقط إذا لم يتم تحديد مطابقات مع القاعدة الأولى.

## <a name="advanced-options"></a>خيارات متقدمة

### <a name="add-exceptions-to-a-rule"></a>إضافة استثناءات إلى قاعدة

في معظم الحالات، يؤدي الكيان المطابق إلى ملفات تعريف عميل فريدة ببيانات مدمجة. لمعالجة الحالات النادرة للنتائج الإيجابية الخاطئة والسلبيات الخاطئة ديناميكيًا، يمكنك تحديد الاستثناءات لقاعدة المطابقة. يتم تطبيق الاستثناءات بعد معالجة قواعد المطابقة وتجنب مطابقة كافة السجلات التي تفي بمعايير الاستثناء.

على سبيل المثال، إذا كانت قاعدة المطابقة الخاصة بك تجمع بين الاسم الأخير والمدينة وتاريخ الميلاد، فسيحدد النظام التوائم الذين يحملون نفس الاسم الأخير ويعيشون في نفس المدينة مثل نفس الملف الشخصي. يمكنك تحديد استثناء لا يتطابق مع الملفات الشخصية إذا كان الاسم الأول في الكيانات التي تدمجها مختلفًا.

1. في جزء **تحرير القاعدة**، حدد **إضافة** > **إضافة استثناء**.

1. حدد معايير الاستثناء.

1. حدد **تم** لحفظ القاعدة.

### <a name="specify-custom-match-conditions"></a>تحديد شروط مطابقة مخصصة

يمكنك تحديد الشروط التي تتجاوز منطق التطابق الافتراضي. هناك أربعة خيارات متاحة:

|خيار  |الوصف  |مثال  |
|---------|---------|---------|
|المطابقة دائمًا     | يحدد القيم المطابقة دائمًا.         |  قم دائمًا بمطابقة *Mike* و *MikeR*.       |
|عدم المطابقة     | تحديد قيم لا تتطابق مطلقًا.        | لا تقم أبدًا بمطابقة *John* و *Jonathan*.        |
|التجاوز المخصص     | تحديد القيم التي يجب على النظام تجاهلها دائمًا في مرحلة المطابقة. |  تجاهل القيم *11111* و *غير معروف* أثناء المطابقة.        |
|تعيين الاسم المستعار    | تحديد القيم التي يجب أن يعتبرها النظام نفس القيمة.         | اعتبر أن *Joe* يساوي *Joseph*.        |

1. حدد **مخصص**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="الزر المخصص":::

1. اختر **النوع المخصص** وحدد **تنزيل القالب**. ستحتاج إلى قالب منفصل لكل خيار مطابقة.

1. افتح ملف النموذج الذي تم تنزيله واملأ التفاصيل. يحتوي القالب على حقول لتحديد الكيان وقيم مفتاح الكيان الأساسي المطلوب استخدامها في المطابقة المخصصة. على سبيل المثال، إذا أردت أن يتطابق دائمًا المفتاح الأساسي *12345* من كيان *المبيعات* مع المفتاح الأساسي *34567* من كيان *جهة الاتصال*، فعليك ملء القالب:
    - الكيان 1: المبيعات
    - مفتاح الكيان 1: 12345
    - الكيان 2: جهة الاتصال
    - مفتاح الكيان 2: 34567

   يمكن لنفس ملف القالب تحديد سجلات المطابقة المخصصة من كيانات متعددة.

   إذا أردت تحديد مطابقة مخصصة لإلغاء التكرار على كيان ما، فعليك توفير الكيان نفسه كالكيان1 والكيان2 وتعيين قيم المفتاح الأساسي المختلفة.

1. بعد إضافة كل التجاوزات، احفظ ملف القالب.

1. انتقل إلى **البيانات** > **مصادر البيانات** لاستيعاب ملفات القوالب ككيانات جديدة.

1. بعد تحميل الملفات، حدد الخيار **المخصص** مرة أخرى. حدد الكيانات المطلوبة من القائمة المنسدلة وحدد **تم**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="لقطة شاشة لمربع الحوار لاختيار تجاوزات سيناريو المطابقة المخصصة.":::

1. يعتمد تطبيق المطابقة المخصصة على خيار المطابقة الذي تريد استخدامه.

   - بالنسبة إلى **المطابقة دائمًا** أو **عدم المطابقة**، تابع الإجراء إلى الخطوة التالية.
   - بالنسبة إلى **التجاوز** أو **تعيين الاسم المستعار**، حدد **تحرير** على قاعدة مطابقة حالية أو أنشئ قاعدة جديدة. في القائمة المنسدلة التسويات، اختر خيار **التجاوز المخصص** أو **تعيين الاسم المستعار**، ثم حدد **تم**.

1. حدد **تم** في الجزء **المخصص** لتطبيق تكوين المطابقة المخصصة.

> [!div class="nextstepaction"]
> [الخطوة التالية: توحيد الحقول](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]