---
title: إنشاء البيئات في Customer Insights
description: خطوات إنشاء البيئات باشتراك مرخص في Dynamics 365 Customer Insights.
ms.date: 10/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 914af46d2d82f3556d149f2836680c902f826d50
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673306"
---
# <a name="create-an-environment-in-audience-insights"></a>إنشاء بيئة في رؤى الجماهير

تشرح هذه المقالة كيفية إنشاء بيئة جديدة بعد شراء مؤسستك لاشتراك Dynamics 365 Customer Insights. 

يمكن أن تقوم المؤسسات بإنشاء *اثنتين* من البيئات لكل ترخيص Customer Insights. إذا اشترت مؤسستك أكثر من ترخيص واحد، [فاتصل بفريق الدعم لدينا](https://go.microsoft.com/fwlink/?linkid=2079641) لزيادة عدد البيئات المتوفرة. لمزيد من المعلومات حول السعة و‏‫الوظيفة الإضافية للسعة، قم بتنزيل [دليل ترخيص Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> إذا كنت تبحث عن تجربة الخدمة، فشاهد [إعداد بيئة إصدار تجريبي](../trial-signup.md).

## <a name="create-a-new-environment"></a>إنشاء بيئة جديدة

بعد شراء ترخيص اشتراك لـ Customer Insights، يتلقى المسؤول العمومي لمستأجر Microsoft 365 رسالة بريد إلكتروني تدعوه لإنشاء البيئة. انتقل إلى [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) لبدء الاستخدام. 

تساعدك التجربة الموجهة من خلال الخطوات لجمع كل المعلومات المطلوبة لبيئة جديدة. تحتاج إلى [أذونات المسؤول](permissions.md) في رؤى الجمهور لإنشاء البيئات أو إدارتها.

1. في رؤى الجمهور، افتح منتقي البيئة وحدد **+ جديد**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="تحديد منتقي البيئة.":::

1. اتبع التجربة الإرشادية الموضحة في الأقسام التالية.

### <a name="step-1-provide-environment-information"></a>الخطوة 1: توفير معلومات البيئة

في خطوة **المعلومات الأساسية**، اختر ما إذا كنت تريد إنشاء بيئة من البداية أو [نسخ البيانات من بيئة أخرى](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="مربع حوار لإنشاء بيئة Customer Insights جديدة.":::

أدخل التفاصيل التالية:
   - **الاسم**: اسم لهذه البيئة. يتم ملء هذا الحقل بشكل مسبق إذا قمت بالنسخ من بيئة موجودة، ولكن يمكنك تغييره.
   - **اختر عملك**: اختر الجمهور الأساسي للبيئة الجديدة. يمكنك العمل مع العملاء الفرديين (متاجرة عمل-مستهلك) أو [حسابات الأعمال](work-with-business-accounts.md) (شركة إلى شركة).
   - **النوع**: قم بتحديد ما إذا كنت ترغب في إنشاء بيئة إنتاج أو بيئة اختبار معزولة. لا تسمح بيئات الاختبار المعزولة بتحديث البيانات المجدولة وتكون مخصصة للتنفيذ والاختبار المسبق. تستخدم بيئات Sandbox نفس الجمهور الأساسي مثل بيئة الإنتاج المحددة حاليًا.
   - **المنطقة**: المنطقة التي يتم فيها نشر الخدمة واستضافتها.

### <a name="step-2-configure-data-storage"></a>الخطوة 2: تكوين مخزن البيانات

في خطوة **تخزين البيانات**، اختر مكان تخزين البيانات من رؤى الجمهور.

سيكون لديك خياران: **مساحة تخزين Customer Insights** ‏(مستودع بيانات Azure مُدار بواسطة فريق Customer Insights) **وAzure Data Lake Storage** (Azure Data Lake Storage الخاص بك). يكون خيار مساحة تخزين Customer Insights محددًا بشكل افتراضي.

:::image type="content" source="media/data-storage-environment.png" alt-text="اختر Azure Data Lake Storage لتخزين بيانات رؤى الجمهور فيه.":::

من خلال حفظ البيانات في Azure Data Lake Storage، فإنك توافق على أنه سيتم نقل البيانات وتخزينها في الموقع الجغرافي المناسب لحساب تخزين Azure هذا. قد يختلف هذا الموقع عن مكان تخزين البيانات في Dynamics 365 Customer Insights. اعرف المزيد في [مركز توثيق Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> يدعم Customer Insights حاليًا ما يلي:
> - الكيانات التي تم تحليلها من تدفقات بيانات Power BI المخزنة في Data Lake مدار بواسطة Microsoft Dataverse.  
> - حسابات Azure Data Lake Storage من نفس منطقة Azure التي قمت بتحديدها عند إنشاء البيئة.
> - حسابات Azure Data Lake Storage التي قامت بتمكين *مساحة اسم التدرج الهرمي*.

بالنسبة لخيار Azure Data Lake Storage، يمكنك الاختيار بين خيار مستند إلى المورد أو خيار مستند إلى الاشتراك للمصادقة. لمزيد من المعلومات، راجع [الاتصال بحساب Azure Data Lake Storage باستخدام كيان Azure service](connect-service-principal.md). اسم **الحاوية** سيكون `customerinsights` ولا يمكن تغييره.

عند اكتمال عمليات النظام مثل نقل البيانات، يقوم النظام بإنشاء مجلدات مقابلة في حساب التخزين الذي حددته. يتم إنشاء ملفات البيانات وملفات *model.json* وإضافتها إلى المجلدات استنادًا إلى اسم العملية.

إذا قمت بإنشاء بيئات متعددة من Customer Insights واخترت حفظ كيانات الإخراج من تلك البيئات في حساب التخزين الخاص بك، فإن Customer Insights ينشئ مجلدات منفصلة لكل بيئة باستخدام `ci_environmentID` في الحاوية.

### <a name="step-3-connect-to-microsoft-dataverse"></a>الخطوة 3: الاتصال بـ Microsoft Dataverse
   
تتيح لك خطوة **Microsoft Dataverse** توصيل Customer Insights ببيئة Dataverse الخاصة بك.

لاستخدام [نماذج التنبؤ الجاهزة](predictions-overview.md#out-of-box-models)، قم بتكوين مشاركة البيانات باستخدام Dataverse. أو يمكنك تمكين عرض البيانات من مصادر البيانات المحلية، مما يوفر عنوان URL لبيئة Microsoft Dataverse التي تديرها مؤسستك. حدِّد **تمكين مشاركة البيانات** لمشاركة بيانات إخراج Customer Insights مع مستودع بيانات مُدار بواسطة Dataverse.

:::image type="content" source="media/dataverse-data-sharing.png" alt-text="خيارات التكوين لتمكين مشاركة البيانات مع Microsoft Dataverse.":::

> [!NOTE]
> لا يدعم Customer Insights سيناريوهات مشاركة البيانات التالية:
> - إذا قمت بحفظ جميع البيانات في Azure Data Lake Storage الخاص بك، فلن تتمكن من تمكين مشاركة البيانات باستخدام مستودع بيانات مُدار بواسطة Dataverse.
> - إذا قمت بتمكين مشاركة البيانات باستخدام Dataverse، فلن تتمكن من [إنشاء قيم تم التنبؤ بها أو مفقودة في إحدى الكيانات](predictions.md).

### <a name="step-4-finalize-the-settings"></a>الخطوة 4: إنهاء الإعدادات

في خطوة **المراجعة**، تنقل خلال جميع الإعدادات المحددة. عندما يبدو كل شيء مكتملاً، حدد **إنشاء** لإعداد البيئة. 

يمكنك أيضًا تغيير معظم الإعدادات لاحقًا. لمزيد من المعلومات، راجع [إدارة البيئات](manage-environments.md).

## <a name="work-with-your-new-environment"></a>التعامل مع بيئتك الجديدة

راجع المقالات التالية من أجل مساعدتك على الشروع في تكوين Customer Insights: 

- [إضافة مزيد من المستخدمين وتعيين الأذونات](permissions.md).
- [استيعاب مصادر البيانات](data-sources.md) وتشغيلها عبر [عملية توحيد البيانات](data-unification.md) للحصول على [ملفات تعريف موحدة للعملاء](customer-profiles.md).
- [إثراء ملفات التعريف الموحدة للعملاء](enrichment-hub.md) أو [تشغيل النماذج التنبؤية](predictions-overview.md)
- [إنشاء مقاطع](segments.md) لتصنيف العملاء ضمن مجموعة، [والقياسات](measures.md) لمراجعة مؤشرات KPI.
- [إعداد الاتصالات](connections.md) و [التصديرات](export-destinations.md) لمعالجة مجموعات فرعية من بياناتك في تطبيقات أخرى.
