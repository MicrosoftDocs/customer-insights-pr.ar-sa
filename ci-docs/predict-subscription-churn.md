---
title: التنبؤ بخسارة الاشتراك (يحتوي على فيديو)
description: توقع ما إذا كان العميل عرضة للخطر لعدم استخدام منتجات شركتك أو خدماتها الخاصة بالاشتراك بعد الآن.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 415cd5d675512b4f434998afaa8265c8e45c562b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645565"
---
# <a name="subscription-churn-prediction"></a>التنبؤ بخسارة الاشتراك

يساعدك توقع خسارة الاشتراك في توقع ما إذا كان العميل عرضة للخطر لعدم استخدام منتجات شركتك أو خدماتها الخاصة بالاشتراك بعد الآن. يمكنك إنشاء تنبؤ خسارة اشتراك جديدة في صفحة **ذكاء** > **التنبؤات**. حدد **تنبؤاتي** لرؤية التنبؤات الأخرى التي قمت بإنشائها.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> جرّب البرنامج التعليمي للتنبؤ بخسارة الاشتراك باستخدام عينة بيانات: [دليل نموذج التنبؤ بخسارة الاشتراك (معاينة)‬](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>المتطلبات الأساسية

- [أذونات المساهم](permissions.md) على الأقل.
- معرفة بالأعمال لفهم تأثير الخسارة على أعمالك. نحن ندعم تعريفات الخسارة المعتمدة على الوقت، ما يعني أنه يتم اعتبار خسارة العميل بعد انتهاء اشتراكه بفترة من الوقت.
- بيانات حول اشتراكاتك ومحفوظاتها:
    - معرفات الاشتراكات لتمييز الاشتراكات.
    - معرفات العملاء لمطابقة الاشتراكات مع عملائك.
    - تواريخ أحداث الاشتراك، والتي تحدد تواريخ البدء والانتهاء والتواريخ التي حدثت بها أحداث الاشتراك.
    - معلومات الاشتراك لتحديد ما إذا كان اشتراكًا متكررًا وعدد مرات تجديده.
    - يتطلب مخطط البيانات الدلالية للاشتراكات المعلومات التالية:
        - **معرف الاشتراك:** وهو معرف فريد للاشتراك.
        - **تاريخ انتهاء الاشتراك:** تاريخ انتهاء صلاحية الاشتراك للعميل.
        - **تاريخ بداية الاشتراك:** تاريخ بداية الاشتراك للعميل.
        - **تاريخ الحركة:** تاريخ حدوث تغيير في الاشتراك. على سبيل المثال، قيام أحد العملاء بشراء اشتراك أو إلغائه.
        - **هو اشتراك متكرر:** حقل منطقي بقية صحيح/خطأ يحدد ما إذا كان الاشتراك سيتجدد باستخدام نفس معرف الاشتراك دون تدخل العميل أم لا
        - **تكرار الحدوث (بالشهور):** مع الاشتراكات المتكررة، تكون هذه هي الفترة التي سيتم تجديد الاشتراك لها. ويتم تمثيلها بالشهور. على سبيل المثال، الاشتراك السنوي الذي يتجدد تلقائيًا لعميل كل عام لسنة أخرى يكون بالقيمة 12.
        - (اختياري) **مبلغ الاشتراك:** مبلغ العملة التي يدفعها العميل لتجديد الاشتراك. ويمكن أن يساعد في تحديد أنماط للمستويات المختلفة من الاشتراكات.
- بيانات حول أنشطة العملاء:
    - معرفات النشاط لتمييز الأنشطة من نفس النوع.
    - معرفات العملاء لتعيين الأنشطة إلى عملائك.
    - معلومات النشاط التي تحتوي على اسم وتاريخ النشاط.
    - يتضمن مخطط البيانات الدلالية لأنشطة العملاء ما يلي:
        - **المفتاح الأساسي:** معرف فريد لنشاط. على سبيل المثال، زيارة موقع ويب أو سجل استخدام يظهر العميل الذي عرض إحدى الحلقات التلفزيونية.
        - **الطابع الزمني:** تاريخ ووقت الحدث المعرف من قبل المفتاح الأساسي.
        - **الحدث:** اسم الحدث الذي تريد استخدامه. على سبيل المثال، قد يكون حقل مسمى "UserAction" في خدمة بث الفيديو بالقيمة "تمت مشاهدته".
        - **التفاصيل:** معلومات مفصلة حول الحدث. على سبيل المثال، قد يكون حقل مسمى "ShowTitle" في خدمة بث الفيديو بالقيمة "فيديو شاهده العميل".
- خصائص البيانات المقترحة:
    - بيانات وتاريخية كافية: بيانات الاشتراك لضعف النافذة الزمنية المحددة على الأقل. يفضل أن يكون من عامين إلى ثلاثة من بيانات الاشتراك.
    - حالة الاشتراك: تتضمن البيانات اشتراكات نشطة وغير نشطة لكل عميل بحيث تكون هناك إدخالات متعددة لكل معرف عميل.
    - عدد العملاء: 10 ملفات تعريف عملاء على الأقل، ويفضل أن يكون أكثر من 1000 عميل فريد. سيفشل النموذج بأقل من 10 عملاء والبيانات والتاريخ غير كافية.
    - اكتمال البيانات: أقل من 20٪ من القيم المفقودة في حقل البيانات للكيان الذي تم توفيره.
   
   > [!NOTE]
   > ستحتاج إلى وجود سجلين على الأقل من سجلات الأنشطة لنسبة 50% من العملاء الذين ترغب في حساب خسارتهم.

## <a name="create-a-subscription-churn-prediction"></a>إنشاء توقع خسارة الاشتراك

1. انتقل إلى **تحليل المعلومات** > **‏‫التنبؤات**.
1. حدد لوحة **نموذج خسارة الاشتراك‎**، وحدد **استخدم هذا النموذج**.
   > [!div class="mx-imgBorder"]
   > ![الإطار المتجانب ‏‫نموذج خسارة الاشتراك مع الزر "استخدام هذا النموذج".](media/subscription-churn-usethismodel.PNG "تجانب نموذج خسارة الاشتراك مع استخدم زر النموذج هذا")

### <a name="name-model"></a>تسمية النموذج

1. قم بتوفير اسم للنموذج لتمييزه عن النماذج الأخرى.
1. قم بتوفير اسم لكيان الإخراج باستخدام الأحرف والأرقام فقط، دون أي مسافات. هذا هو الاسم الذي سيستخدمه كيان النموذج. ثم حدد **التالي**.

### <a name="define-customer-churn"></a>تحديد خسارة العميل

1. أدخل عدد **الأيام منذ انتهاء الاشتراك** الذي تعتبر فيه شركتك أن العميل بالحالة "تمت خسارته". وعادة ما ترتبط هذه الفترة بأنشطة الأعمال مثل العروض أو مجهودات التسويق الأخرى التي تحاول منع خسارة العميل.
1. أدخل عدد **الأيام للبحث في المستقبل للتنبؤ بالخسارة لها** لتعيين نافذة للتنبؤ بالخسارة فيها. على سبيل المثال، للتنبؤ بمخاطر خسارة العملاء على مدى الأيام التسعين القادمة لمواءمة جهود الاستبقاء التسويقية. قد يزيد خطر حدوث مخاطرة خلال فترات زمنية أطول أو أقصر من صعوبة التعامل مع العوامل التي قد تكون في ملف تعريف مخاطرتك، وذلك وفقا لمتطلبات العمل الخاصة بك. حدد **التالي** للمتابعة.
   >[!TIP]
   > يمكنك تحديد **حفظ المسودة** في أي وقت لحفظ تنبؤ كمسودة. ستجد توقعات المسودة في علامة التبويب **التنبؤات الخاصة بي** للمتابعة.

### <a name="add-required-data"></a>إضافة البيانات المطلوبة

1. حدد **إضافة بيانات** لـ **محفوظات الاشتراك** واختر الكيان الذي يوفر معلومات محفوظات الاشتراك كما هو موضح في [المتطلبات الأساسية](#prerequisites).
1. إذا لم يتم ملء الحقول الموجودة أدناه، فقم بتكوين العلاقة من كيان محفوظات الاشتراك الخاص بك إلى كيان العميل.
    1. حدد **كيان محفوظات الاشتراك**.
    1. حدد **الحقل** الذي يحدد العميل في كيان محفوظات الاشتراكات. ينبغي أن يرتبط بمعرف العميل الرئيسي لكيان العميل الخاص بك.
    1. حدد **كيان العميل** الذي يطابق كيان العميل الأساسي الخاص بك.
    1. أدخل اسمًا يصف العلاقة.
       > [!div class="mx-imgBorder"]
       > ![صفحة محفوظات الاشتراك توضح إنشاء علاقة إلى العميل.](media/subscription-churn-subscriptionhistoryrelationship.PNG "صفحة محفوظات الاشتراك توضح إنشاء علاقة إلى العميل")
1. حدد **التالي**.
1. قم بتعيين الحقول الدلالية إلى السمات داخل كيان محفوظات الاشتراك الخاص بك وحدد **حفظ**. بالنسبة لأوصاف الحقول، قم بإلقاء نظرة على [المتطلبات الأساسية](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![صفحه محفوظات الاشتراك تظهر سمات دلالية يتم تعيينها إلى الحقول في كيان محفوظات الاشتراك المحدد.](media/subscription-churn-subscriptionhistorymapping.PNG "صفحه محفوظات الاشتراك تظهر سمات دلالية يتم تعيينها إلى الحقول في كيان محفوظات الاشتراك المحدد")
1. حدد **إضافة بيانات** لـ **أنشطة العميل** واختر الكيان الذي يوفر معلومات نشاط العميل كما هو موضح في المتطلبات الأساسية.
1. حدد نوع نشاط يطابق نوع نشاط العميل الذي تقوم بتكوينه.  حدد **إنشاء جديد** وقم بإدخال اسم إذا لم يظهر لك خيار يتطابق مع نوع النشاط الذي تريده.
1. سيتعين عليك تكوين العلاقة من كيان نشاط العميل الخاص بك إلى كيان العميل.
    1. حدد الحقل الذي يحدد العميل في جدول نشاط العميل، والذي يمكن أن يرتبط مباشرة بمعرف العميل الرئيسي لكيان العميل الخاص بك.
    1. حدد كيان العميل الذي يطابق كيان العميل الرئيسي الخاص بك
    1. أدخل اسمًا يصف العلاقة.
1. حدد **التالي**.
1. قم بتعيين الحقول الدلالية إلى السمات داخل كيان نشاط العميل الخاص بك وحدد **حفظ**. بالنسبة لأوصاف الحقول، قم بإلقاء نظرة على [المتطلبات الأساسية](#prerequisites).
1. (اختياري) إذا كانت لديك أية أنشطة عملاء أخرى ترغب في تضمينها، فكرر الخطوات الموضحة أعلاه.
   > [!div class="mx-imgBorder"]
   > ![قم بتحديد علاقة الكيان.](media/subscription-churn-customeractivitiesmapping.PNG "صفحه أنشطة العملاء تظهر سمات دلالية يتم تعيينها إلى الحقول في كيان نشاط العميل المحدد")
1. حدد **التالي**.

### <a name="set-schedule-and-review-configuration"></a>تعيين الجدول ومراجعة التكوين

1. قم بتعيين تكرار للاحتفاظ بالنموذج الخاص بك. يُعد هذا الإعداد من الأهمية بمكان لحديث دقة التنبؤات حيث يتم استيعاب البيانات الجديدة في Customer Insights. يمكن لمعظم شركات الأعمال إجراء الاحتفاظ مرة واحدة في الشهر والحصول على دقة جيدة للتنبؤ الخاص بها.
1. حدد **التالي**.
1. مراجعة التكوين يمكنك الرجوع إلى أي جزء من تكوين التنبؤ من خلال تحديد **تحرير** أسفل القيمة المعروضة. أو يمكنك تحديد خطوة تكوين من مؤشر التقدم.
1. وإذا كانت جميع القيم مكونة بشكل صحيح، فحدد **حفظ وتشغيل** لبدء عملية التنبؤ. في علامة التبويب **التنبؤ**، يمكنك رؤية حالة التنبؤات الخاصة بك. قد تستغرق العملية عدة ساعات للاكتمال وذلك وفقًا لكمية البيانات المستخدمة في التنبؤ.

## <a name="review-a-prediction-status-and-results"></a>مراجعة حاله التنبؤ والنتائج

1. انتقل إلى علامة التبويب **التنبؤات الخاصة بي** على **الذكاء** > **التنبؤات**.
   > [!div class="mx-imgBorder"]
   > ![عرض صفحة التنبؤات الخاصة بي.](media/subscription-churn-mypredictions.PNG "عرض صفحة التنبؤات الخاصة بي")
1. حدد التنبؤ الذي تريد مراجعته.
   - **اسم التنبؤ:** اسم التنبؤ الذي تم توفيره عند إنشائه.
   - **نوع التنبؤ:** نوع النموذج المستخدم للتنبؤ
   - **كيان الإخراج:** اسم الكيان لتخزين إخراج التنبؤ. يمكنك العثور على كيان بهذا الاسم في **البيانات** > **الكيانات**.    
     في كيان الإخراج، *ChurnScore* هو الحتمال المتوقع للخسارة و *IsChurn* هي تسمية ثنائية تعتمد على *ChurnScore* مع الحد 0.5. قد لا يعمل الحد الافتراضي مع السيناريو الخاص بك. [قم بإنشاء شريحة جديدة](segments.md#create-a-new-segment) بالحد المفضل لديك.
   - **الحقل المتوقع:** لا يتم ملء هذا الحقل إلا لبعض أنواع التنبؤات، ولا يتم استخدامه في تنبؤ خسارة الاشتراك.
   - **الحالة:** الحالة الحالية لتشغيل التنبؤ.
        - **‏‫في قائمة الانتظار‬:** التنبؤ ينتظر حاليًا تشغيل عمليات أخرى.
        - **تحديث:** يجري حاليًا تشغيل التنبؤ في مرحلة "النتيجة" من المعالجة لإخراج النتائج التي ستتدفق إلى كيان المخرجات.
        - **فشل:** فشل التنبؤ. حدد **السجلات** لمزيد من التفاصيل.
        - **نجح:** نجح التنبؤ. حدد **عرض** أسفل علامات الحذف الرأسية لمراجعة التنبؤ
   - **تم التحرير:** التاريخ الذي تم فيه تغيير تكوين التنبؤ.
   - **التحديث الأخير:** التاريخ الذي نتج عنه تحديث التنبؤ في كيان المخرجات.
1. حدد علامات الحذف الرأسية الموجودة بجوار التنبؤ الذي تريد مراجعة النتائج له وقم بتحديد **عرض**.
   > [!div class="mx-imgBorder"]
   > ![عرض الخيارات في قائمة علامات الحذف الرأسية للتنبؤ بما في ذلك التحرير والتحديث والعرض والسجلات والحذف.](media/subscription-churn-verticalellipses.PNG "عرض الخيارات في قائمة علامات الحذف الرأسية للتنبؤ بما في ذلك التحرير والتحديث والعرض والسجلات والحذف")
1. يوجد ثلاثة أقسام رئيسية من البيانات في صفحة النتائج:
    1. **أداء نموذج التدريب:** والنتائج المحتملة A أو B أو C. تشير هذه الدرجة إلى أداء التنبؤ، ويمكن أن تساعدك في اتخاذ قرار بشأن استخدام النتائج المخزنة في كيان المخرجات.
        - يتم تحديد نقاط الدرجات استنادًا إلى القواعد التالية:
            - **أ** عندما يتنبأ النموذج بدقة بنسبة 50% على الأقل من إجمالي التوقعات، وعندما تكون النسبة المئوية للتنبؤات الدقيقة للعملاء الذين لم يجددوا اشتراكهم أكبر من المتوسط ​​السابق لإلغاء الاشتراك بنسبة 10% على الأقل من المتوسط ​​التاريخي لإلغاء الاشتراك.
            - **ب** عندما يتنبأ النموذج بدقة بنسبة 50% على الأقل من إجمالي التوقعات، وعندما تكون النسبة المئوية للتنبؤات الدقيقة للعملاء الذين لم يجددوا اشتراكهم أكبر من المتوسط ​​السابق لإلغاء الاشتراك بنسبة أكبر تصل حتى 10% من المتوسط ​​التاريخي لإلغاء الاشتراك.
            - **ج** عندما توقع النموذج بشكل دقيق أقل من 50% من إجمالي التوقعات، أو عندما تكون النسبة المئوية للتوقعات الدقيقة للعملاء الذين لم يجددوا الاشتراك أقل من المتوسط ​​التاريخي لإلغاء الاشتراك.‬
               > [!div class="mx-imgBorder"]
               > ![عرض نتيجة أداء النموذج.](media/subscription-churn-modelperformance.PNG "عرض نتيجة أداء النموذج")
    1. **احتمالية الخسارة (عدد العملاء):** مجموعات العملاء وفقًا لمخاطر الخسارة المتوقعة. يمكن أن تساعدك هذه البيانات لاحقا إذا كنت ترغب في إنشاء شريحة من العملاء أصحاب مخاطر خسارة عالية. تساعدك هذه الشرائح في فهم المكان الذي ينبغي فيه عمل فصل لعضوية الشريحة.
       > [!div class="mx-imgBorder"]
       > ![رسم بياني يوضح توزيع نتائج الخسارة، وهو مقسم إلى نطاقات من 0-100%.](media/subscription-churn-resultdistribution.PNG "رسم بياني يوضح توزيع نتائج الخسارة، وهو مقسم إلى نطاقات من 0-100%")
    1. **العوامل الأكثر تأثيرًا:** ثمة العديد من العوامل التي يتم أخذها في الاعتبار عند إنشاء التنبؤ الخاص بك. ويتم حساب أهمية كل واحد من هذه العوامل للتنبؤات المجمعة التي ينشئها النموذج. يمكنك استخدام هذه العوامل للمساعدة في التحقق من صحة نتائج التنبؤ. أو يمكنك استخدام هذه المعلومات لاحقًا [لإنشاء شرائح](segments.md) يمكن أن تساعد في التأثير على خطر الخسارة للعملاء.
       > [!div class="mx-imgBorder"]
       > ![قائمة توضح العوامل المؤثرة وأهميتها في التنبؤ بنتيجة الخسارة.](media/subscription-churn-influentialfactors.PNG "قائمة توضح العوامل المؤثرة وأهميتها في التنبؤ بنتيجة الخسارة")

## <a name="manage-predictions"></a>إدارة التنبؤات

من الممكن تحسين التنبؤات أو استكشاف أخطائها وإصلاحها أو تحديثها أو حذفها. راجع تقرير إمكانية استخدام بيانات الإدخال لمعرفة كيفية جعل التنبؤ أسرع وأكثر موثوقية. لمزيد من المعلومات، راجع [إدارة التنبؤات](manage-predictions.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]