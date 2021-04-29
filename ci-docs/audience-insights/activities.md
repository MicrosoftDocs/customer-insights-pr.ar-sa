---
title: أنشطة العملاء
description: تحديد أنشطة العميل وعرضها في المخطط الزمني للعميل.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866391"
---
# <a name="customer-activities"></a>أنشطة العملاء

قم بدمج أنشطة العملاء من [مصادر بيانات متعددة](data-sources.md) في Dynamics 365 Customer Insights لإنشاء جدول زمني يسرد الأنشطة بترتيب زمني. قم بتضمين المخطط الزمني في تطبيقات Dynamics 365 مع حل [الوظيفة الإضافية لبطاقة العميل](customer-card-add-in.md) أو في لوحة معلومات Power BI.

## <a name="define-an-activity"></a>تعريف نشاط

يمكن أن تتضمن مصادر البيانات كيانات تحتوي على بيانات المعاملات والأنشطة من مصادر بيانات متعددة. قم بتعريف هذه الكيانات وحدد الأنشطة التي ترغب في عرضها على المخطط الزمني للعميل. اختر الكيان الذي يتضمن نشاطك (أو أنشطتك) المستهدف.

> [!NOTE]
> يجب أن يحتوي الكيان على سمة واحدة على الأقل من نوع **التاريخ** كي يتم تضمينها في المخطط الزمني للعميل، ولا يمكنك إضافة كيانات من دون حقول **التاريخ‏‎**. يتم تعطيل عنصر التحكم **إضافة نشاط** إذا لم يتم العثور على مثل هذا الكيان.

1. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **الأنشطة**.

1. حدد **إضافة نشاط** لبدء تجربة إرشادية لعملية إعداد النشاط.

1. في خطوة **بيانات النشاط**، قم بتعيين القيم الخاصة بالحقول التالية:

   - **اسم النشاط**: حدد اسمًا لنشاطك.
   - **الكيان**: حدد كيانًا يتضمن بيانات المعاملات أو الأنشطة.
   - **المفتاح الأساسي**: حدد الحقل الذي يعرّف السجل بشكل فريد. وينبغي ألا يحتوي على أي قيم متكررة أو قيم فارغة أو قيم مفقودة.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="قم بإعداد بيانات النشاط بالاسم والكيانات والمفتاح الرئيسي.":::

1. حدد **التالي** للذهاب إلى الخطوة التالية.

1. في خطوة **العلاقة**، قم بتكوين التفاصيل لربط بيانات نشاطك بالعميل المقابل لها. تصور هذه الخطوة الاتصال بين الكيانات.  

   - **أولاً**: حقل أجنبي في كيان النشاط سيتم استخدامه لإنشاء علاقة مع كيان آخر.
   - **ثانيًا**: كيان العميل المصدر المقابل الذي سيكون كيان النشاط الخاص بك على علاقة به. يمكنك فقط ربط كيانات العميل المصدر التي تم استخدامها في عملية علاقات البيانات.
   - **ثالثًا**: إذا كانت هناك علاقة بين كيان النشاط هذا وبين كيان العميل المصدر المحدد موجودة بالفعل، سيكون اسم العلاقة في وضع القراءة فقط. إذا لم تكن هناك علاقة من هذا النوع، سيتم إنشاء علاقة جديدة بالاسم الذي توفره في هذا المربع.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="قم بتحديد علاقة الكيان.":::

1. حدد **التالي** للذهاب إلى الخطوة التالية. 

1. في خطوة **توحيد النشاط**، اختر حدث النشاط ووقت بدء النشاط. 
   - **الحقول المطلوبة**
      1. **نشاط الحدث**: الحقل الذي هو الحدث لهذا النشاط
      2. **الطابع الزمني**: حقل يمثل وقت بدء النشاط.

   - **الحقول الاختيارية**
      1. **تفاصيل إضافية**: حقل به معلومات ذات صلة لهذا النشاط.
      2. **الرمز**: الرمز الذي يمثل أفضل ما يكون نوع النشاط هذا.
      3. **عنوان ويب**: حقل يحتوي على عنوان URL يحتوي على معلومات حول هذا النشاط. على سبيل المثال، نظام المعاملات الذي يعمل كمصدر بيانات لهذا النشاط. يمكن أن يكون عنوان URL هذا أي حقل من مصدر البيانات، أو يمكن إنشاؤه كحقل جديد باستخدام تحويل Power Query. سيتم تخزين بيانات URL في كيان *النشاط الموحد*، والذي يمكن استهلاكه لأسفل باستخدام [واجهات برمجة التطبيقات](apis.md).
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="حدد بيانات نشاط العميل في كيان النشاط الموحد.":::

1. حدد **التالي** للانتقال إلى الخطوة التالية. يمكنك تحديد **إنهاء ومراجعة** لحفظ النشاط الآن مع تعيين نوع النشاط إلى **أخرى**. 

1. في خطوة **نوع النشاط**، اختر نوع النشاط وحدد اختياريًا ما إذا كنت تريد تعيين بعض أنواع الأنشطة لغويًا لاستخدامها في مناطق أخرى من Customer Insights. في الوقت الحالي، يتم تعيين أنواع نشاط *الاشتراك* & *SalesOrderLine* لغويًا بعد الموافقة على تعيين الحقول. إذا كان نوع النشاط غير مناسب للنشاط الجديد، يمكنك اختيار *أخرى* أو *إنشاء جديد* لنوع نشاط مخصص.

1. حدد **التالي** للانتقال إلى الخطوة التالية. 

1. في خطوة **المراجعة**، تحقق من التحديدات التي أجريتها. يمكنك الرجوع إلى أي من الخطوات السابقة وتحديث المعلومات عند الضرورة.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="راجع الحقول المحددة لنشاط ما.":::
   
1. حدد **حفظ النشاط** لتطبيق التغييرات التي أجريتها وحدد **تم** للعودة إلى **البيانات** > **الأنشطة**. وشاهد هنا الأنشطة التي تم تعيينها لإظهارها في المخطط الزمني. 

1. في صفحة **الأنشطة**، حدد **تشغيل** لمعالجة النشاط. 

> [!TIP]
> هناك [ستة أنواع للحالة](system.md#status-types) للمهام/العمليات. بالإضافة إلى ذلك، تعتمد معظم العمليات [على العمليات اللاحقة الأخرى](system.md#refresh-policies). يمكنك تحديد حالة العملية لمعرفة تفاصيل التقدم الخاصة بالمهمة بأكملها. بعد تحديد **الاطلاع على التفاصيل** لإحدى مهام الوظيفة، يمكنك العثور علي معلومات اضافيه: وقت المعالجة ، وتاريخ آخر معالجه ، وكافة الأخطاء والتحذيرات المقترنة بالمهمة.


## <a name="manage-existing-activities"></a>إدارة الأنشطة الموجودة

في **البيانات** > **الأنشطة**، يمكنك عرض جميع الأنشطة المحفوظة الخاصة بك وإدارتها. يتم تمثيل كل نشاط من خلال صف يتضمن أيضا تفاصيل حول المصدر، والكيان، ونوع النشاط.

تتوفر الإجراءات التالية عند تحديد نشاط. 

- **تحرير**: يفتح إعداد النشاط في خطوة المراجعة. يمكنك تغيير أي من التكوينات الحالية أو كلها من هذه الخطوة. بعد تغيير التكوين، قم بتحديد **حفظ النشاط** ثم قم بتحديد **تشغيل** لمعالجة التغييرات.

- **إعادة تسمية**: تفتح مربع حوار حيث يتم إدخال اسم مختلف للنشاط المحدد. حدد **حفظ** لتطبيق التغييرات التي أجريتها.

- **حذف**: افتح أحد مربعات الحوار لتأكيد حذف النشاط المحدد. يمكنك أيضا حذف أكثر من نشاط واحد مرة واحدة بتحديد الأنشطة ثم تحديد رمز الحذف. حدد **حذف** لتأكيد الحذف.

[!INCLUDE[footer-include](../includes/footer-banner.md)]