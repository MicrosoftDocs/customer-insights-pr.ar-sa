---
title: إنشاء بيئة جديدة
description: خطوات لإنشاء بيئات في Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304227"
---
# <a name="create-a-new-environment"></a>إنشاء بيئة جديدة

بعد [شراء ترخيص اشتراك لـ Dynamics 365 Customer Insights](paid-license.md)، يتلقى المسؤول العمومي لمستأجر Microsoft 365 بريدًا إلكترونيًا يدعوه لإنشاء البيئة. انتقل إلى [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) لبدء الاستخدام. في هذا السيناريو، ابدأ بـ [الخطوة 1: توفير المعلومات الأساسية](#step-1-provide-basic-information).

بعد إنشاء البيئة الأولى، بإمكان المسؤول العمومي لمستأجر Microsoft 365 [إضافة مستخدمين من مؤسسته كمسؤولين](permissions.md). يمكن لهؤلاء المسؤولين بعد ذلك إدارة المستخدمين والبيئات. إذا اشترت مؤسستك أكثر من ترخيص واحد لـ Customer Insights، [فاتصل بفريق الدعم لدينا](https://go.microsoft.com/fwlink/?linkid=2079641) لزيادة عدد البيئات المتوفرة. لمزيد من المعلومات حول السعة وسعة الوظائف الإضافية، راجع [دليل ترخيص Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). بمجرد أن تكون لديك القدرة على إنشاء بيئات إضافية، انتقل إلى [ابدأ عملية إنشاء البيئة](#start-the-environment-creation-process).

> [!TIP]
> إذا كنت تبحث عن تجربة الخدمة، فشاهد [إعداد بيئة إصدار تجريبي](trial-signup.md).

## <a name="prerequisites"></a>المتطلبات

[أذونات المسؤول](permissions.md) في Customer Insights

## <a name="start-the-environment-creation-process"></a>بدء عملية إنشاء البيئة

1. افتح منتقي البيئة وحدد **+ جديد**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="تحديد منتقي البيئة.":::

1. اتبع التجربة الإرشادية الملخصة في الأقسام التالية لتوفير كافة المعلومات المطلوبة لبيئة جديدة.

## <a name="step-1-provide-basic-information"></a>الخطوة 1: توفير معلومات أساسية

1. اختر ما إذا كنت تريد إنشاء بيئة من البداية أو نسخ البيانات من بيئة أخرى. يتطلب [نسخ البيانات من بيئة أخرى](#copy-the-environment-configuration) خطوات إضافية.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="مربع حوار لإنشاء بيئة Customer Insights جديدة.":::

1. أدخل التفاصيل التالية:

   - **الاسم**: اسم لهذه البيئة. يتم ملء هذا الحقل بشكل مسبق إذا قمت بالنسخ من بيئة موجودة، ولكن يمكنك تغييره.
   - **اختيار أعمالك**: الجمهور الأساسي للبيئة الجديدة: المستهلكين الأفراد (متاجرة عمل-مستهلك) أو [حسابات الأعمال](work-with-business-accounts.md) (متاجرة شركة إلى شركة). إذا كانت مؤسستك تقوم بشكل أساسي بممارسة الأعمال التجارية مع أفراد، مثل بائع التجزئة أو مقهى، فاختر مستهلكين فرديين. إذا كان جمهورك الرئيسي عبارة عن شركات أخرى، مثل شركة تصنيع سيارات أو شركة ورقيات، فاختر حسابات الأعمال.
   - **النوع**: نوع البيئة: بيئة إنتاج أو بيئة اختبار معزولة. لا تسمح بيئات الاختبار المعزولة بتحديث البيانات المجدولة وتكون مخصصة للتنفيذ والاختبار المسبق. تستخدم بيئات Sandbox نفس الجمهور الأساسي مثل بيئة الإنتاج المحددة حاليًا.
   - **المنطقة**: المنطقة التي يتم فيها نشر الخدمة واستضافتها. كي تتمكن من [استخدام حسابك الخاص في Azure Data Lake Storage](own-data-lake-storage.md) أو [الاتصال بمؤسسة Microsoft Dataverse موجودة](customer-insights-dataverse.md)، يجب أن تكون بيئة Customer Insights في المنطقة نفسها.

1. حدد **التالي**.

## <a name="step-2-configure-data-storage"></a>الخطوة 2: تكوين مخزن البيانات

1. اختر مكان تخزين بيانات Customer Insights:

   - **تخزين Customer Insights**: يتم إدارة تخزين البيانات تلقائيًا. هذا هو الخيار الافتراضي، وما لم تكن هناك متطلبات معينة لتخزين البيانات في حساب التخزين الخاص بك، فإننا نوصي باستخدام هذا الخيار.
   - **Azure Data Lake Storage**: حسابك الخاص في Azure Data Lake Storage لتخزين البيانات بحيث يتوفر لديك التحكم الكامل في المكان حيث تم تخزين البيانات. اتبع الخطوات الخاصة بـ [استخدام حساب Azure Data Lake Storage الخاص بك](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="حدد الخيار المفضل لتخزين بياناتك.":::

1. حدد **التالي**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>الخطوة 3: الاتصال بـ Microsoft Dataverse

إذا كانت لديك بيئة Dataverse، فقم بتوصيل Customer Insights. شارك البيانات مع Dataverse لاستخدامها مع تطبيقات الأعمال استنادًا إلى Dataverse، مثل Dynamics 365 Marketing أو التطبيقات التي تستند إلى النموذج في Power Apps.

1. اتبع الخطوات الواردة في [التعامل مع بيانات Customer Insights في Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="تمكين مشاركة البيانات مع Microsoft Dataverse بشكل تلقائي للبيئات الجديدة الصافية.":::

1. حدد **التالي**.

## <a name="step-4-finalize-the-settings"></a>الخطوة 4: إنهاء الإعدادات

راجع الإعدادات المحددة. عندما يبدو كل شيء مكتملاً، حدد **إنشاء** لإعداد البيئة.

لتغيير بعض الإعدادات لاحقًا، راجع [إدارة البيئات](manage-environments.md).

## <a name="work-with-your-new-environment"></a>التعامل مع بيئتك الجديدة

راجع المقالات التالية من أجل مساعدتك على الشروع في تكوين Customer Insights:

- [إضافة مزيد من المستخدمين وتعيين الأذونات](permissions.md).
- [استيعاب مصادر البيانات](data-sources.md) وتشغيلها عبر [عملية توحيد البيانات](data-unification.md) للحصول على [ملفات تعريف موحدة للعملاء](customer-profiles.md).
- [إثراء ملفات التعريف الموحدة للعملاء](enrichment-hub.md) أو [تشغيل النماذج التنبؤية](predictions-overview.md)
- [إنشاء مقاطع](segments.md) لتصنيف العملاء ضمن مجموعة، [والقياسات](measures.md) لمراجعة مؤشرات KPI.
- [إعداد الاتصالات](connections.md) و [التصديرات](export-destinations.md) لمعالجة مجموعات فرعية من بياناتك في تطبيقات أخرى.

## <a name="copy-the-environment-configuration"></a>نسخ تكوين البيئة

بصفتك مسؤولاً، إذا اخترت نسخ التكوين من بيئة موجودة، فحدد من قائمة جميع البيئات المتاحة في مؤسستك.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="لقطة شاشة من خيارات الإعدادات في إعدادات البيئة.":::

يتم نسخ إعدادات التكوين التالية:

- مصادر البيانات المستوردة عبر Power Query
- تكوين توحيد البيانات
- Segments
- القياسات
- العلاقات
- النشاطات
- فهرس البحث والتصفية
- التصديرات
- تحديث الجدولة
- عمليات الإثراء
- نماذج التنبؤ
- تعيينات الأدوار

### <a name="set-up-a-copied-environment"></a>إعداد بيئة منسوخة

عند نسخ تكوين البيئة، تظهر رسالة تأكيد عند إنشاء البيئة المنسوخة. نفذ الخطوات التالية لتأكيد بيانات الاعتماد.

1. حدد **انتقال إلى مصادر البيانات** لرؤية قائمة مصادر البيانات. تعرض جميع مصادر البيانات حالة **بيانات الاعتماد المطلوبة**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="قائمة مصادر البيانات التي تم نسخها وتحتاج إلى مصادقة.":::

1. قم بتحرير مصادر البيانات وأدخل بيانات الاعتماد لتحديثها. يجب إنشاء مصادر البيانات من مجلد "نموذج البيانات العامة" وDataverse يدويًا بالاسم نفسه كما في بيئة المصدر.

1. بعد تحديث مصادر البيانات، انتقل إلى **البيانات** > **توحيد**. هنا ستجد إعدادات من بيئة المصدر. قم بتحريرها حسب الحاجة أو حدد **توحيد** > **توحيد ملفات تعريف العملاء والتبعيات** لبدء عملية توحيد البيانات وإنشاء كيان عميل موحد.

   > [!TIP]
   > بالنسبة للحسابات وجهات الاتصال، حدد **"توحيد الحسابات** > **توحيد ملفات التعريف والتبعيات**.

1. عند اكتمال عملية توحيد البيانات، انتقل إلى **المقاييس** و **المقاطع** لتحديثها.

1. انتقل إلى **المسؤول** > **الاتصالات** لإعادة مصادقة الاتصالات في بيئتك الجديدة.‬

1. انتقل إلى **البيانات** > **الإثراء** و **البيانات** > **الصادرات** لإعادة تنشيطها.

[!INCLUDE [footer-include](includes/footer-banner.md)]
