---
title: إعدادات النظام في Customer Insights
description: التعرف على إعدادات النظام في Dynamics 365 Customer Insights.
ms.date: 04/21/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-schedule
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 3aa4c6529d705698e612adad86587e3c3a4db35b
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653600"
---
# <a name="system-configuration"></a>تكوين النظام

للوصول إلى تكوينات النظام، انتقل إلى **المسؤول** > **النظام** لعرض قائمة بمهام النظام وعملياته.

تتضمن صفحة **النظام** علامات التبويب التالية:
- [‏الحالة](#status-tab)
- [جدول](#schedule-tab)
- [استخدام واجهة برمجة التطبيقات](#api-usage-tab)
- [حول](#about-tab)
- [عام ](#general-tab)

:::image type="content" source="media/system-tabs.png" alt-text="علامات تبويب الإعدادات في صفحة النظام.":::

## <a name="status-tab"></a>علامة التبويب "الحالة"

تتيح لك **علامة التبويب الحالة** تعقب تقدم المهام، وحذف البيانات، وتصدير البيانات، وعددا من عمليات المنتجات الهامة الأخرى. راجع المعلومات في علامة التبويب هذه للتأكد من اكتمال المهام والعمليات النشطة.

تتضمن علامة التبويب هذه جداول تحتوي على معلومات عن الحالة والمعالجة لعمليات متنوعة. يتتبع كل جدول **اسم** المهمة وكيانها المقابل، و **وحالة** التشغيل الأحدث لها، ومتى تم **تحديثها آخر مرة**. يمكنك عرض تفاصيل آخر عدة تشغيل من خلال تحديد اسم المهمة أو العملية. 

حدد الحالة المجاورة للمهمة أو العملية في عمود **الحالة** لفتح جزء **تفاصيل التقدم**.

   :::image type="content" source="media/system-progress-details.png" alt-text="جزء تفاصيل تقدم النظام":::

### <a name="status-definitions"></a>تعريفات الحالة

يستخدم النظام الحالات التالية للمهام والعمليات:

|‏الحالة  |التعريف  |
|---------|---------|
|مُلغى |تم إلغاء المعالجة بواسطة المستخدم قبل انتهائها.   |
|‏‏فاشلة   |تسبب استيعاب البيانات في تشغيل أخطاء.         |
|فشل  |فشلت المعالجة.  |
|لم يبدأ   |لا يحتوي مصدر البيانات على بيانات تم استيعابها أو ما زالت في وضع المسودة.         |
|قيد المعالجة  |المهمة أو العملية في التقدم.  |
|تحديث    |استيعاب البيانات قيد التقدم. يُمكنك إلغاء هذه العملية من خلال تحديد **إيقاف التحديث** في عمود **إجراءات**. سيؤدي إيقاف تحديث مصدر البيانات إلى إعادته إلى آخر حالة تحديث له.       |
|تم التخطي  |تم تخطي المهمة أو العملية. فشلت واحدة أو أكثر من العمليات اللاحقة التي تعتمد عليها هذه المهمة أو تم تخطيها.|
|تمت بنجاح  |اكتملت المهمة أو العملية بنجاح. بالنسبة لمصادر البيانات، تشير إلى أنه قد تم استخدام البيانات بنجاح إذا تم ذكر وقت في العمود **تم تحديثه**.|
|موضوع في قائمة انتظار | تكون المعالجة في قائمة انتظار وستبدأ بمجرد اكتمال كافة المهام والعمليات الخاصة بانتقال البيانات إلى الخادم. لمزيد من المعلومات، راجع [عمليات التحديث](#refresh-processes).|

### <a name="refresh-processes"></a>تحديث العمليات

يتم تشغيل التحديث للمهام والعمليات وفقا [لجدولة مكونة](#schedule-tab). 

|معالجة  |الوصف   |
|---------|---------|
|النشاط  |يعمل يدويا (تحديث في وقت واحد). يعتمد على عملية الدمج. تعتمد المعلومات على معالجتها.|
|ربط التحليل |يعمل يدويا (تحديث في وقت واحد). تعتمد على المقاطع.  |
|إعداد التحليل |يعمل يدويا (تحديث في وقت واحد). تعتمد على المقاطع.  |
|تحضير البيانات   |يحتاج إلى كيان لتشغيله. تعتمد كيانات مصدر البياناتعلى الاستيعاب. تعتمد الكيانات التي تم إثرائها على عمليات الإثراء. يعتمد كيان العميل على الدمج.  |
|مصادر البيانات   |لا تعتمد على أي عملية أخرى. تعتمد المطابقة على الإكمال الناجح لهذه العملية.  |
|عمليات الإثراء   |يعمل يدويا (تحديث في وقت واحد). يعتمد على عملية الدمج. |
|وجهات التصدير |يعمل يدويا (تحديث في وقت واحد). تعتمد على المقاطع.  |
|الرؤى |يعمل يدويا (تحديث في وقت واحد). تعتمد على المقاطع.  |
|المعلومات   |تعتمد على الدمج.   |
|مطابقة |تعتمد على معالجة مصادر البيانات المستخدمة في تعريف المطابقة.      |
|المقاييس  |يعمل يدويا (تحديث في وقت واحد). يعتمد على عملية الدمج.  |
|‏‏دمج   |يعتمد على إكمال عملية المطابقة. تعتمد المقاطع والمقاييس والإثراء والبحث والأنشطة والتنبؤات وإعداد البيانات على الإكمال الناجح لهذه العملية.   |
|ملفات التعريف   |يعمل يدويا (تحديث في وقت واحد). يعتمد على عملية الدمج. |
|بحث    |يعمل يدويا (تحديث في وقت واحد). يعتمد على عملية الدمج. |
|المقاطع  |يعمل يدويا (تحديث في وقت واحد). يعتمد على عملية الدمج. تعتمد المعلومات على معالجتها.|
|النظام   |يعتمد على إكمال عملية المطابقة. تعتمد المقاطع والمقاييس والإثراء والبحث والأنشطة والتنبؤات وإعداد البيانات على الإكمال الناجح لهذه العملية.   |
|المستخدم   |يعمل يدويا (تحديث في وقت واحد). يعتمد على الكيانات.  |

حدد حالة العملية لرؤية تفاصيل التقدم الخاص بالوظيفة بأكملها التي كانت فيها. يمكن أن تساعد عمليات التحديث الواردة أعلاه على فهم ما يمكنك فعله لمعالجة مهمة أو عملية **تم تخطيها** أو **وضعها في قائمة انتظار**.

## <a name="schedule-tab"></a>علامة التبويب الجدولة

استخدم علامة التبويب **الجدول** لجدولة عمليات التحديث التلقائي لجميع [مصادر البيانات التي تم استيعابها](data-sources.md). يساعد التحديث التلقائي في التأكد من أن التحديثات من مصادر البيانات تنعكس في ملفات تعريف العميل الموحدة.

> [!NOTE]
> يتم تحديث مصادر البيانات التي تديرها وفقًا لجداولها الخاصة. لجدولة تحديث مصادر البيانات التي تديرها، قم بتكوين إعدادات التحديث في مصدر البيانات المحدد هذا من صفحة **Data sources (مصادر البيانات )**.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platformإعدادات تحديث تدفق البيانات":::

1. انتقل إلى **المسؤول** > **النظام**، ثم حدد علامة التبويب **جدولة**.

2. الحالة الافتراضية للتحديث المجدول على الوضع **إيقاف التشغيل**. لتمكين التحديثات المجدولة، قم بتغيير التبديل الموجود أعلى الشاشة إلى **تشغيل**.

3. اختر ما بين التحديثات **الأسبوعية** (افتراضية) و **اليومية**. إذا كنت تعتزم جدولة عمليات التحديث الأسبوعية، فقم بتحديد يوم واحد أو أكثر من الأيام التي ترغب في إجراء التحديث بها.

4. قم بتعيين **المنطقة الزمنية**، ثم استخدم القائمة المنسدلة **للوقت** لتعيين توقيت التحديث الخاص بك. عند الانتهاء، حدد **تعيين**. إذا كنت ترغب في جدولة عمليات تحديث متعددة في يوم واحد، حدد **إضافة وقت آخر**.

5. حدد **حفظ** لتطبيق التغييرات التي أجريتها.

## <a name="about-tab"></a>علامة التبويب "حول"

تحتوي علامة التبويب **حول** على **اسم العرض** الخاص بالمؤسسة و **معرف البيئة** النشط و **المنطقة** و **معرف جلسة العمل** الخاصة بك. إذا كان لديك أكثر من بيئة عمل واحدة، فيجب إدخال اسم معروض يمكن التعرف عليه بسهولة لكل واحدة منها.

## <a name="general-tab"></a>علامة التبويب عام

يمكنك تغيير اللغة وتنسيق البلد/المنطقة في علامة التبويب **عام.**

يدعم Customer Insights [العديد من اللغات](/dynamics365/get-started/availability). يستخدم التطبيق تفضيلات لغتك لعرض عناصر مثل القائمة ونص التسمية ورسائل النظام بلغتك المفضلة.

البيانات والمعلومات المستوردة التي أدخلتها يدويًا غير مترجمة.

### <a name="update-the-settings"></a>تحديث الإعدادات

لتغيير اللغة المفضلة الخاصة بك، اختر **لغة** من القائمة المنسدلة.

لتغيير التنسيق المفضل للتواريخ والوقت والأرقام، استخدم القائمة المنسدلة **تنسيق البلد/المنطقة**. يتم عرض معاينة التنسيق ضمن هذا الحقل. سيقوم النظام تلقائيًا باقتراح تحديد عند اختيار لغة جديدة.

حدد **حفظ** لتأكيد تحديداتك.

## <a name="api-usage-tab"></a>علامة تبويب استخدام API

يمكنك البحث عن تفاصيل حول استخدام API في الوقت الحقيقي ورؤية الأحداث التي وقعت في إطار زمني معين. يمكنك اختيار إطار زمني في القائمة المنسدلة **تحديد إطار زمني**. 

يتضمن **استخدام API** ثلاثة أقسام: 
- **استدعاءات واجهة برمجة التطبيقات (API)‬** - مخطط يقدم رسمًا مرئيًا لعدد المكالمات المجمع في واجهة API في الإطار الزمني المحدد.

- **نقل البيانات** - مخطط يوضح كمية البيانات التي تم نقلها عبر API في الإطار الزمني المحدد.

-  **العمليات** - جدول يحتوي على صفوف لكل عملية API متوفرة وتفاصيل حول استخدام العمليات. يمكنك تحديد اسم عملية للذهاب إلى [مرجع API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   وتحتوي العمليات التي تستخدم [الاحتواء على البيانات في الوقت الحقيقي](real-time-data-ingestion.md) على زر يحتوي على رمز منفرد لعرض استخدام API في الوقت الحقيقي. حدد الزر لفتح جزء جانبي يحتوي على تفاصيل الاستخدام الخاصة باستخدام API في الوقت الحقيقي في البيئة الحالية.   
   استخدم المرعب **تجميع حسب** تجميع حسب **استخدام واجهة API في الوقت الحقيقي** لاختيار أفضل طريقة لتقديم تفاعلاتك الوقت الحقيقي. يمكنك تجميع البيانات حسب أسلوب واجهة برمجة التطبيقات (API)، أو اسم الكيان المؤهل (الكيان المضمن)، والذي تم إنشاؤه بواسطة (مصدر الحدث)، أو النتيجة (النجاح أو الفشل) أو رموز الخطأ. تتوفر البيانات كمخطط تاريخي وكجدول.


[!INCLUDE [footer-include](includes/footer-banner.md)]