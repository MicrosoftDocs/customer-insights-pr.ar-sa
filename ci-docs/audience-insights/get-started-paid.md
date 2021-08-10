---
title: إنشاء ترخيص مدفوع لـ Customer Insights وتكوينه
description: خطوات الحصول على اشتراك مرخص لـ Dynamics 365 Customer Insights وتكوينه.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f8cf1be97ee8af46145a450009fd278b1821f8fe
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650440"
---
# <a name="get-started-with-a-paid-subscription"></a>‏‫بدء استخدام الاشتراك المدفوع

تشرح هذه المقالة كيفية إنشاء بيئة جديدة بعد شراء مؤسستك لاشتراك Dynamics 365 Customer Insights. إذا كنت ترغب في شراء Customer Insights، يتم سرد خيارات جهة الاتصال الخاصة بنا على موقع [Dynamics 365 Customer Insights الإلكتروني](https://dynamics.microsoft.com/ai/customer-insights/). 

إذا كنت تبحث عن تجربة الخدمة والميزات، فراجع [إعداد بيئة تجريبية](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>إنشاء بيئة في مؤسسة موجودة

بعد شراء ترخيص اشتراك لـ Customer Insights، يتلقى المسؤول العمومي لمستأجر Microsoft 365 رسالة بريد إلكتروني تدعوه لإنشاء البيئة. انتقل إلى [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) لبدء الاستخدام. 

لا يتم ترخيص Customer Insights لكل مستخدم، لذلك لن يتم عرضها في منطقة التراخيص. إذا كنت تبحث عن الترخيص في مركز إدارة Microsoft 365، فانتقل إلى **منتجاتك**. 

> [!NOTE]
> يمكن أن تقوم المؤسسات بإنشاء *اثنتين* من البيئات لكل ترخيص Customer Insights. إذا اشترت مؤسستك أكثر من ترخيص واحد، فيرجى [الاتصال بفريق الدعم](https://go.microsoft.com/fwlink/?linkid=2079641) لزيادة عدد البيئات المتاحة. لمزيد من المعلومات حول السعة و‏‫الوظيفة الإضافية للسعة، قم بتنزيل [دليل ترخيص Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

لإنشاء بيئة:

1. في مربع حوار **إنشاء بيئة**، قم بتحديد **بيئة جديدة**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="مربع حوار لإنشاء بيئة Customer Insights جديدة.":::

   يُستحسن بدء إعداد بيئة من البداية. ومع ذلك، إذا كنت مسؤول أو عضو في بيئة تجريبية، يمكنك [نسخ البيانات من بيئة أخرى](manage-environments.md#copy-the-environment-configuration)، عن طريق اختيار **نسخ من بيئة موجودة**. سترى قائمة تتضمن جميع البيئات المتوفرة في مؤسستك حيث يمكنك نسخ البيانات منها.

1. أدخل التفاصيل التالية:
   - **الاسم**: اسم لهذه البيئة. يتم ملء هذا الحقل بشكل مسبق إذا قمت بالنسخ من بيئة موجودة، ولكن يمكنك تغييره.
   - **المنطقة**: المنطقة التي يتم فيها نشر الخدمة واستضافتها.
   - **النوع**: قم بتحديد ما إذا كنت ترغب في إنشاء بيئة إنتاج أو بيئة اختبار معزولة. لا تسمح بيئات الاختبار المعزولة بتحديث البيانات المجدولة وتكون مخصصة للتنفيذ والاختبار المسبق.
   
1. يمكنك بشكل اختياري تحديد **الإعدادات المتقدمة**:

   - **حفظ كافة البيانات إلى**: يحدد المكان الذي تريده لتخزين بيانات الإخراج التي تم إنشاؤها من Customer Insights. سيكون لديك خياران: **مساحة تخزين Customer Insights** ‏(Azure Data Lake مُدارة بواسطة Customer Insights) و **Azure Data Lake Storage** (Azure Data Lake Storage الخاص بك). يكون خيار مساحة تخزين Customer Insights محددًا بشكل افتراضي.

     > [!NOTE]
     > من خلال حفظ البيانات في Azure Data Lake Storage، فأنت توافق على أنه سيتم نقل البيانات وتخزينها في الموقع الجغرافي المناسب لحساب تخزين Azure هذا، وذلك قد يختلف عن المكان الذي تُخزَّن فيه البيانات في Dynamics 365 Customer Insights. [اعرف المزيد في مركز توثيق Microsoft.](https://www.microsoft.com/trust-center)
     >
     > في الوقت الحالي، يتم دائمًا تخزين الكيانات المستوعبة من تدفقات البيانات‬ Power BI في Data Lake المُدارة بواسطة Microsoft Dataverse 
     > 
     > ندعم حسابات Azure Data Lake Storage من نفس منطقة Azure التي حددتها فقط عند إنشاء البيئة. 
     > 
     > وندعم حسابات Azure Data Lake Storage التي تم تمكين مساحة الاسم الهرمية لها فقط.


   - بالنسبة لخيار Azure Data Lake Storage، يمكنك الاختيار بين خيار مستند إلى المورد أو خيار مستند إلى الاشتراك للمصادقة. لمزيد من المعلومات، راجع [توصيل رؤى الجمهور بحساب Azure Data Lake Storage Gen2 بواسطة كيان خدمة Azure](connect-service-principal.md). لا يمكن تغيير اسم **الحاوية** وسيكون `customerinsights`.
   
   - إذا كنت ترغب في استخدام [النماذج المبتكرة](predictions-overview.md#out-of-box-models)، قم بتهيئة مشاركة البيانات مع Microsoft Dataverse، أو قم بتمكين استيعاب البيانات من مصادر البيانات المحلية، وقم بتوفير عنوان URL لبيئة Microsoft Dataverse ضمن **تكوين مشاركة البيانات مع Microsoft Dataverse وتمكين إمكانات إضافية**. حدد **تمكين مشاركة البيانات** لمشاركة بيانات إخراج Customer Insights مع Data Lake مُدار في Microsoft Dataverse

     > [!NOTE]
     > - في الوقت الحالي، مشاركة البيانات مع Data Lake مُدار في Microsoft Dataverse غير مدعوم عندما تحفظ جميع البيانات إلى Azure Data Lake Storage الخاص بك.
     > - [التنبؤ بالقيم المفقودة في كيان](predictions.md) غير مدعوم حاليًا عند قيامك بتمكين مشاركة البيانات مع Data Lake المُدار في Microsoft Dataverse.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="خيارات التكوين لتمكين مشاركة البيانات مع Microsoft Dataverse.":::

   عند اكتمال عمليات النظام مثل اكتمال عملية استيعاب البيانات، ينشئ النظام مجلدات مقابلة في حساب التخزين الذي حددته. يتم إنشاء ملفات البيانات وملفات model.json وإضافتها إلى المجلدات استنادًا إلى اسم العملية.

   إذا قمت بإنشاء العديد من بيئات Customer Insights واخترت حفظ كيانات المخرجات من هذه البيئات الموجودة في حساب التخزين، سيتم إنشاء مجلدات منفصلة لكل بيئة تتضمن ci_<environmentid> في الحاوية.

1. حدد **إنشاء** لإعداد البيئة. 

## <a name="configure-an-environment"></a>تكوين بيئة

راجع المقالات التالية لمساعدتك في البدء في تكوين Customer Insights. 

- [إضافة مزيد من المستخدمين وتعيين الأذونات](permissions.md).
- [استيعاب مصادر البيانات](data-sources.md) وتشغيلها عبر [عملية توحيد البيانات](data-unification.md) للحصول على [ملفات تعريف موحدة للعملاء](customer-profiles.md).
- [إثراء ملفات التعريف الموحدة للعملاء](enrichment-hub.md) أو [تشغيل النماذج التنبؤية](predictions-overview.md)
- إنشاء [شرائح](segments.md) لتجميع العملاء، ومراجعة [القياسات](measures.md) لمؤشرات KPIs.
- إعداد [الاتصالات](connections.md) و [التصديرات](export-destinations.md) لمعالجة مجموعات فرعية من بياناتك في تطبيقات أخرى.
