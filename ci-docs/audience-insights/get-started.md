---
title: ابدأ بإمكانية رؤى الجمهور في Dynamics 365 Customer Insights
description: نظرة عامة على رؤى الجمهور تساعد الموارد على البدء بسرعة.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5e8545bc9bf0d953150248fa859c6ca71a12f9cf
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645248"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>ابدأ بإمكانية رؤى الجمهور في Dynamics 365 Customer Insights

يمكن أن تساعدك رؤى الجمهور في بناء فهم أعمق لعملائك. قم بتوصيل البيانات من مصادر متعددة المعاملات والسلوكية والرصدية لإنشاء طريقة عرض من 360 درجة للعملاء. استخدم هذه المعارف لتعزيز التجارب والعمليات التي تركز على العملاء. توحيد بيانات العملاء وفهمها والاستفادة منها لتكوين رؤى وإجراءات ذكية.

## <a name="step-1-create-an-environment"></a>الخطوة 1: إنشاء بيئة

للبدء، عليك أولاً إنشاء بيئة للعمل فيها. إذا كانت مؤسستك قد اشترت ترخيصًا بالفعل، فراجع [إنشاء بيئة](create-environment.md). لبدء تشغيل إصدار تجريبي لرؤى الجمهور، راجع [إعداد بيئة إصدار تجريبي](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>الخطوة 2: استكشاف رؤى الجمهور

في المرة الأولى التي تسجّل فيها الدخول إلى رؤى الجمهور، يمكنك تكوين الإعدادات واستكشاف المنتج.

1. [قم بتسجيل الدخول إلى رؤى الجمهور](https://home.ci.ai.dynamics.com) باستخدام حساب مستخدم Microsoft Azure Active Directory ‏(AAD).

1. [تغيير البيئة](manage-environments.md#switch-environments) لمشاهدة بيانات العرض التوضيحي و[استكشاف رؤى الجمهور](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>الخطوة 3: استيعاب وتوحيد وإعداد العلاقات لبياناتك

ملفات التعريف الموحدة هي الأساس للحصول على رؤى واتخاذ إجراءات بشأن البيانات. قم بإحضار البيانات من مصادر مختلفة وتشغيل عملية توحيد البيانات لدمج ملفات تعريف موحدة. حدد العلاقات بين الكيانات التي تم استيعابها باستخدام ميزات الإثراء لإضافة معلومات إلى ملفات التعريف. 

1. استيعاب البيانات عن طريق إنشاء مصادر البيانات من خيارات متعددة. اختر من بين [موصلات Power Query](connect-power-query.md)، أو [مجلد نموذج البيانات العامة](connect-common-data-model.md)، أو [Microsoft Dataverse](connect-common-data-service-lake.md). 

1. قم بتشغيل [عملية توحيد البيانات](data-unification.md) من خلال المرور على مراحل [الخريطة](map-entities.md)، و[المطابقة](match-entities.md)، و[الدمج](merge-entities.md).

1. تعرف إلى [الكيانات التي ينشئها النظام](entities.md) وأنشئ [العلاقات بين الكيانات المستوعبة](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>الخطوة الرابعة: تحسين ملفات التعريف الموحدة بالتنبؤات والأنشطة والقياسات

من خلال إعداد ملفات التعريف الموحدة، يمكنك تحسين بياناتك وزيادة المعلومات التي تقدمها.

1. اختر من مكتبة موسعة لمقدمي الإثراء من أجل [إثراء بيانات العملاء](enrichment-hub.md).

1. استخدم [النماذج الجاهزة](predictions-overview.md) للتنبؤ باحتمالية الخسارة أو الإيرادات المتوقعة.

1. [قم بتكوين الأنشطة](activities.md) استنادًا إلى البيانات التي تم إدخالها وتصور التفاعلات مع العملاء في مخطط بترتيب زمني. 

1. [إنشاء القياسات](measures.md) لقياس أهداف عملك ومؤشرات الأداء الأساسية.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>الخطوة 5: إنشاء مقاطع وتنشيط البيانات من خلال خيارات التصدير المختلفة

الآن وقد اكتملت بياناتك وتحتوي على مجموعة واسعة من المعلومات حول عملائك، فقد حان الوقت للبحث عن طرق لاتخاذ إجراء بشأن تلك البيانات. 

1. [أنشئ مقاطع](segments.md)، مجموعات فرعية من قاعدة عملائك، للتأكد من أن أفعالك ملائمة للعملاء المستهدفين.

1. تصفح الكتالوج الموسع لـ [خيارات التصدير](export-destinations.md) حيث يمكنك استخدام بيانات العملاء. على سبيل المثال، يمكنك استخدام البيانات لإدارة العروض الترويجية والتواصل مع التسويق الرقمي.

1. راجع خيارات التكامل، على سبيل المثال مع [الاتصال المباشر بمعلومات المشاركة](../engagement-insights/integrate-audience-insights-engagement-insights.md) أو تطبيقات Dynamics 365 مع [الوظيفة الإضافية لبطاقة عميل](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
