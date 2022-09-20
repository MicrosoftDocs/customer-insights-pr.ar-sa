---
title: الاتصال بمصدر البيانات Power Query (يحتوي على فيديو)
description: استيعاب البيانات من خلال موصل Power Query (يحتوي على فيديو).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 6a25e332bafab414c9def4e1e6b461139dd24ea6
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463249"
---
# <a name="connect-to-a-power-query-data-source"></a>الاتصال بمصدر بيانات Power Query

يوفر Power Query مجموعة واسعة من الموصلات لاستيعاب البيانات. معظم هذه الموصلات مدعومة من Dynamics 365 Customer Insights.

تتبع إضافة مصادر البيانات استنادًا إلى موصلات Power Query بشكل عام الخطوات الملخصة في هذا القسم. ومع ذلك، بناءً على الموصل الذي تستخدمه، يلزم توفر معلومات مختلفة. لمعرفة المزيد، راجع الوثائق حول الموصلات المفردة في [مرجع موصل Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>إنشاء مصدر بيانات جديد

1. انتقل إلى **البيانات** > **مصادر البيانات**.

1. حدد **إضافة مصدر بيانات**.

1. حدد **Microsoft Power Query**.

1. أدخل **اسمًا** و **وصفًا** اختياريًا لمصدر البيانات، ثم حدد **التالي**.

1. اختر أحد [الموصلات المتوفرة](#available-power-query-data-sources). في هذا المثال، نقوم بتحديد موصل **Text/CSV**.

1. أدخل التفاصيل المطلوبة في **إعدادات الاتصال** الخاصة بالرابط المحدد وحدد **التالي** للاطلاع على معاينة البيانات.

1. حدد **نقل البيانات**.

1. يتيح مربع حوار **Power Query - تحرير الاستعلامات** لك مراجعة البيانات وتنقيحها. تظهر الكيانات التي حددتها الأنظمة في مصدر بياناتك المحدد في الجزء الأيمن.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="مربع حوار تحرير الاستعلامات":::

1. يُمكنك أيضًا تحويل بياناتك. حدد كيانًا لتحريره أو تحويله. استخدم الخيارات الموجودة في إطار Power Query لتطبيق التحويلات. يكون كل تحويل مدرجًا ضمن **الخطوات المطبقة**. يوفر Power Query العديد من خيارات [التحويل المضمنة مسبقًا](/power-query/power-query-what-is-power-query#transformations).

   من المستحسن استخدام التحويلات التالية:

   - إذا كنت بصدد إدخال بيانات من ملف CSV، فغالبًا ما يحتوي الصف الأول على رؤوس. انتقل إلى **تحويل**، وحدد **استخدام الصف الأول كعناوين**.
   - تأكد من تعيين نوع البيانات بشكل صحيح. على سبيل المثال، بالنسبة لحقول التاريخ، حدد نوع التاريخ.

1. لإضافة كيانات إضافية إلى مصدر البيانات في مربع الحوار **تحرير الاستعلامات**، انتقل إلى **الصفحة الرئيسية**، وحدد **الحصول على البيانات**. كرر الخطوات من 5 إلى 10 حتى تضيف جميع الكيانات لمصدر البيانات هذا. إذا كانت لديك قاعدة بيانات تتضمن مجموعات بيانات متعددة، تكون كل مجموعة بيانات كيان خاص بذاتها.

1. حدد **حفظ.**. تفتح صفحة **مصادر‏‎ البيانات** التي تعرض مصدر البيانات الجديد في الحالة **جارٍ التحديث**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

قد يستغرق تحميل البيانات وقتا. بعد الانتهاء من التحديث بنجاح، يُمكنك مراجعة البيانات المستوعبة من صفحة [**الكيانات**](entities.md).

> [!CAUTION]
>
> - يقوم مصدر بيانات مستند إلى Power Query بإنشاء [تدفق بيانات في Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). لا تقم بتغيير اسم تدفق بيانات في مركز مسؤولي Power Platform المستخدم في Customer Insights. تؤدي إعادة تسمية تدفق البيانات إلى حدوث مشكلات في المراجع بين مصدر بيانات Customer Insights وتدفق بيانات Dataverse.
> - يكون للتقييمات المتزامنة لمصادر بيانات Power Query في Customer Insights نفس [حدود التحديث مثل تدفق البيانات في PowerBI.com](/power-query/power-query-online-limits#refresh-limits). في حالة فشل تحديث البيانات لأنه وصل إلى حد التقييم، نوصي بضبط جدول التحديث لكل تدفق بيانات لضمان عدم معالجة مصادر البيانات في نفس الوقت.

### <a name="available-power-query-data-sources"></a>مصادر بيانات Power Query المتوفرة

راجع [مرجع موصل Power Query](/power-query/connectors/) للاطلاع على قائمة بالموصلات التي يمكنك استخدامها لاستيراد بيانات إلى Customer Insights.

تتوفر موصلات بعلامة اختيار في عمود **Customer Insights (تدفقات البيانات)** لإنشاء مصادر بيانات جديدة تستند إلى Power Query. راجع وثائق موصل معين للتعرف على مزيد من المعلومات حول متطلباته الأساسية و[قيود الاستعلام](/power-query/power-query-online-limits) وتفاصيل أخرى.

## <a name="add-data-from-on-premises-data-sources"></a>إضافة البيانات من مصادر البيانات المحلية

يتم دعم استيعاب البيانات من مصادر البيانات المحلية استنادًا إلى تدفقات بيانات Microsoft Power Platform (PPDFs). يمكنك تمكين تدفقات البيانات في Customer Insights من خلال [توفير عنوان URL لبيئة Microsoft Dataverse](create-environment.md) عند إعداد البيئة.

تستخدم مصادر البيانات التي يتم إنشاؤها بعد ربط بيئة Dataverse مع Customer Insights تدفقات بيانات [Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) بشكل افتراضي. تدعم تدفقات البيانات الاتصال المحلي باستخدام بوابة البيانات. يمكنك إزالة وإعادة إنشاء مصادر البيانات التي كانت موجودة قبل اقتران بيئة Dataverse[باستخدام بوابات البيانات الداخلية](/data-integration/gateway/service-gateway-app).

ستظهر بوابات البيانات مبيئة Power BI أو Power Apps الحالية ويمكنك إعادة استخدامها في Customer Insights إذا كانت بوابة البيانات وبيئة Customer Insights في نفس منطقة Azure. تعرض صفحة مصادر البيانات ارتباطات للوصول إلى بيئةMicrosoft Power Platform، حيث يمكنك عرض محلي بوابات البيانات المحلية وتكوينها.

> [!IMPORTANT]
> تأكد من تحديث البوابات إلى أحدث إصدار. يمكنك تثبيت تحديث وإعادة تكوين بوابة من موجه يتم عرضه على شاشة البوابة مباشرة [أو تنزيل أحدث إصدار](https://powerapps.microsoft.com/downloads/). إذا لم تستخدم أحدث إصدار من البوابة، يفشل تحديث تدفق البيانات مع ظهور رسائل خطأ مثل **الكلمة الأساسية غير مدعومة: خصائص التكوين. اسم المعلمة: الكلمة الأساسية**.
>
> غالبًا ما تحدث أخطاء في بوابات البيانات المحلية في Customer Insights بسبب مشكلات التكوين. لمزيد من المعلومات حول استكشاف مشكلات بوابات البيانات وإصلاحها، راجع [استكشاف أخطاء بوابة البيانات المحلية وإصلاحها](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>تحرير مصدر بيانات Power Query

> [!NOTE]
> قد لا يكون من الممكن إجراء تغييرات على مصادر البيانات التي يتم استخدامها حاليًا في إحدى عمليات التطبيق (التقسيم أو توحيد البيانات على سبيل المثال).
>
> في صفحة **الإعدادات**، يُمكنك تعقب تقدم كل عملية نشطة. عند اكتمال أحد العمليات، يُمكنك الرجوع إلى صفحة **مصادر البيانات** وإجراء التغييرات.

1. انتقل إلى **البيانات** > **مصادر البيانات**.

1. إلى جانب مصدر البيانات الذي تريد تحديثه، حدد **تحرير**.

1. قم بتطبيق التغييرات والتحولات في مربع الحوار **Power Query - تحرير الاستعلامات** كما هو موضح في قسم [إنشاء مصدر بيانات جديد](#create-a-new-data-source).

1. حدد **حفظ** لتطبيق تغييرات، ثم عد إلى صفحة **مصادر‏‎ البيانات**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
