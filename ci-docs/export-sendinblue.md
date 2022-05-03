---
title: تصدير بيانات Customer Insights إلى Sendinblue
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Sendinblue.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e6d63e0017caa50379426cd5f9b663571b568de7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645486"
---
# <a name="export-segments-to-sendinblue-preview"></a>تصدير شرائح إلى Sendinblue (معاينة)

قم بتصدير شرائح من ملفات تعريف العملاء الموحدة لإنشاء حملات، وتوفير التسويق عبر البريد الإلكتروني واستخدام مجموعات محددة من العملاء باستخدام Sendinblue.

## <a name="prerequisites-for-connection"></a>المتطلبات الأساسية للاتصال

-   لديك [حساب Sendinblue](https://www.sendinblue.com/) وبيانات اعتماد المسؤول المقابلة.
-   هناك قوائم موجودة في Sendinblue والمعرفات المقابلة.
-   لقد قمت [بتكوين الشرائح](segments.md).
-   تحتوي ملفات تعريف العملاء الموحدة في الشرائح المصدّرة على حقل يمثل عنوان البريد الإلكتروني.

## <a name="known-limitations"></a>القيود المعروفة

- ما يصل إلى مليون ملف تعريف عميل لكل عملية تصدير إلى Sendinblue.
- يقتصر التصدير إلى Sendinblue على الشرائح.
- يمكن أن يستغرق تصدير مقاطع بإجمالي مليون ملف تعريف عميل ما يصل إلى 90 دقيقة. 
- يعتمد عدد ملفات تعريف العملاء التي يمكنك تصديرها إلى Sendinblue ومحدودًا على عقدك مع Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>إعداد اتصال بـ Sendinblue

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Sendinblue** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **[مفتاح SendinBlue API](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. حدد **أوافق** لتأكيد **خصوصية البيانات وتوافقها** وحدد **اتصال** لبدء الاتصال بـ Sendinblue.

1. حدد **إضافة نفسك كمستخدم تصدير** ووفر بيانات اعتماد Customer Insights.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **اتصال للتصدير**، اختر اتصالا من قسم Sendinblue. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. أدخل **معرف قائمة Sendinblue** 

1. في قسم **مطابقة البيانات** في حقل **البريد الإلكتروني**، حدد الحقل الذي يمثل عنوان البريد الإلكتروني للعميل. 

1. بشكل اختياري، يمكنك تصدير **الاسم الأول**، و **اسم العائلة**، و **الهاتف**  لإنشاء المزيد من رسائل البريد الإلكتروني المخصصة. حدد **إضافة سمة** لتعيين هذه الحقول.

1. حدد الشرائح التي تريد تصديرها. 

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عندما تقوم بتمكين Dynamics 365 Customer Insights لنقل البيانات إلى Sendinblue، يمكنك السماح بنقل البيانات خارج حدود التوافق ل Dynamics 365 Customer Insights، بما في ذلك البيانات التي قد تكون حساسة مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات في الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان وفاء Sendinblue بأية خصوصية أو واجبات أمنية قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.


[!INCLUDE [footer-include](includes/footer-banner.md)]
