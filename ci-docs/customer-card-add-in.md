---
title: الوظيفة الإضافية لبطاقة عميل تطبيقات Dynamics 365 (يحتوي على فيديو)
description: اعرض بيانات ملف تعريف العميل من Customer Insights في تطبيقات Dynamics 365 باستخدام هذه الوظيفة الإضافية.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-search-filter
- ci-customer-card
- customerInsights
ms.openlocfilehash: 8508880bb3274bb491a314a043a5222d4d381073
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755620"
---
# <a name="customer-card-add-in-preview"></a>الوظيفة الإضافية لبطاقة عميل (معاينة)

احصل على طريقة عرض 360 درجة لعملائك مباشرةً في تطبيقات Dynamics 365. مع تثبيت الوظيفة الإضافية لبطاقة العميل في تطبيق Dynamics 365 مدعوم، يمكنك اختيار عرض حقول ملف تعريف العميل والرؤى والمخطط الزمني للنشاط. سوف تسترد الوظيفة الإضافية البيانات من Customer Insights دون التأثير على البيانات في تطبيق Dynamics 365 المتصل.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>المتطلبات الأساسية

- تعمل هذه الوظيفة الإضافية فقط مع تطبيقات Dynamics 365 التي تعتمد على نموذج، مثل Sales أو Customer Service الإصدار 9.0 وما يليه.
- لكي يتم تعيين بيانات Dynamics 365 إلى ملفات تعريف العملاء لـ Customer Insights، نوصي بأن [استيعابها من تطبيق Dynamics 365 باستخدام موصل Microsoft Dataverse](connect-power-query.md). إذا كنت تستخدم طريقة مختلفة لاستيعاب جهات اتصال (أو حسابات) Dynamics 365، فلا بد من التأكد من أن الحقل `contactid` (أو `accountid`) قد تم تعيينه كـ [مفتاح أساسي لمصدر البيانات هذا في خطوة الخريطة لعملية توحيد البيانات](map-entities.md#select-primary-key-and-semantic-type-for-attributes).
- يجب إضافة جميع مستخدمي Dynamics 365 للوظيفة الإضافية لبطاقة العميل [كمستخدمين](permissions.md) في Customer Insights للاطلاع على البيانات.
- تُطلب ميزتي [البحث المُكون وإمكانيات التصفية](search-filter-index.md) في Customer Insights للبحث عن البيانات للعمل.
- يعتمد كل عنصر من عناصر تحكم الوظيفة الإضافية على بيانات محددة في Customer Insights. تتوفر بعض البيانات وعناصر التحكم فقط في بيئات من أنواع معينة. سيخبرك تكوين الوظيفة الإضافية في حالة عدم توفر عنصر تحكم بسبب نوع البيئة المحدد. اعرف المزيد حول [حالات استخدام البيئات](work-with-business-accounts.md).
  - **التحكم في القياس**: يتطلب [القياسات المكونة](measures.md) من نوع سمات العميل.
  - **التحكم في المعلومات المهنية**: يتطلب بيانات تم إنشاؤها باستخدام [التنبؤات أو النماذج المخصصة](predictions-overview.md).
  - **التحكم في تفاصيل العميل**: جميع الحقول من ملف التعريف متاحة في ملف تعريف العميل الموحد.
  - **عنصر تحكم الإثراء**: يتطلب تطبيق [عمليات الإثراء](enrichment-hub.md) النشطة على ملفات تعريف العملاء. تدعم هذه الوظائف الإضافية للبطاقة هذه الإثراءات: [العلامات التجارية](enrichment-microsoft.md) المقدمة من Microsoft، [والاهتمامات](enrichment-microsoft.md) المقدمة من Microsoft، و[بيانات تفاعل Office](enrichment-office.md) المقدمة من Microsoft.
  - **التحكم في جهات الاتصال**: يتطلب تعريف الكيان الدلالي لنوع جهات الاتصال.
  - **التحكم في المخطط الزمني**: يتطلب [الأنشطة المكونة](activities.md).

## <a name="install-the-customer-card-add-in"></a>تثبيت الوظيفة الإضافية لبطاقة عميل

تعتبر الوظيفة الإضافية لبطاقات العملاء حلاً لتطبيقات customer engagement في Dynamics 365. لتثبيت الحل، انتقل إلى AppSource وابحث عن **بطاقة عميل Dynamics**. حدد [تشغيل الوظيفة الإضافية لبطاقة العميل AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) وحدد **احصل عليها الآن**.

قد تحتاج إلى تسجيل الدخول باستخدام بيانات المسؤول الخاصة بك لتطبيق Dynamics 365 لتثبيت الحل. يمكن أن يستغرق تثبيت الحل للبيئة الخاصة بك بعض الوقت.

## <a name="configure-the-customer-card-add-in"></a>تكوين الوظيفة الإضافية لبطاقة العميل

1. بصفتك مسؤول، انتقل إلى قسم **الإعدادات** في Dynamics 365، ثم حدد **الحلول**.

1. حدد الارتباط **اسم العرض** لحل **Dynamics 365 Customer Insights الوظيفة الإضافية لبطاقة العميل (معاينة)**.

   > [!div class="mx-imgBorder"]
   > ![تحديد اسم العرض.](media/select-display-name.png "تحديد اسم العرض.")

1. حدد **تسجيل الدخول** وأدخل بيانات الاعتماد الخاصة بحساب المسؤول الذي تستخدمه لتكوين Customer Insights.

   > [!NOTE]
   > تحقق من عدم قيام أداة حظر العناصر المنبثقة في المستعرض بحظر نافذة المصادقة عندما تقوم بتحديد زر **تسجيل الدخول**.

1. حدد بيئة Customer Insights التي تريد إحضار البيانات منها.

1. قم بتعريف تعيين الحقل للسجلات في تطبيق Dynamics 365. تبعًا لبياناتك في Customer Insights، يمكنك اختيار تعيين الخيارات التالية:
   - للتعيين مع جهة اتصال، حدد الحقل الموجود في كيان العميل الذي يتطابق مع معرف كيان جهة الاتصال.
   - للتعيين مع حساب، حدد الحقل الموجود في كيان العميل الذي يتطابق مع معرف كيان الحساب.

   > [!div class="mx-imgBorder"]
   > ![حقل مُعرف جهة الاتصال.](media/contact-id-field.png "حقل مُعرف جهة الاتصال.")

1. حدد **حفظ التكوين** لحفظ الإعدادات.

1. بعد ذلك، يجب عليك تعيين أدوار أمان في Dynamics 365 حتى يتمكن المستخدمون من تخصيص بطاقة العملاء ومراجعتها. في Dynamics 365، انتقل إلى **الإعدادات** > **الأمان** > **المستخدمون**. حدد المستخدمين لتحرير أدوار المستخدم وحدد **إدارة الأدوار**.

1. تعيين دور **مخصص بطاقة Customer Insights** بالنسبة للمستخدمين الذين سيقومون بتخصيص المحتوى المعروض على البطاقة للمؤسسة بالكامل.

## <a name="add-customer-card-controls-to-forms"></a>إضافة عناصر تحكم بطاقة العميل إلى النماذج

بناء على السيناريو الخاص بك، يمكنك اختيار إضافة عناصر تحكم إما إلى نموذج **جهة الاتصال** أو نموذج **الحساب**. إذا كانت بيئة Customer Insights مخصصة لحسابات الأعمال، فإننا نوصي بإضافة عناصر التحكم إلى نموذج الحساب. في هذه الحالة، استبدل كلمة "جهة الاتصال" في الخطوات أدناه بكلمة "الحساب".

1. لإضافة عناصر تحكم بطاقة العميل إلى نموذج جهة الاتصال الخاص بك، انتقل إلى **الإعدادات** > **تخصيصات** في Dynamics 365.

1. حدد **تخصيص النظام**.

1. استعرض إلى كيان **جهة الاتصال**، وقم بتوسيعه وحدد **النماذج**.

1. حدد نموذج جهة الاتصال الذي تريد إضافة عناصر تحكم بطاقة العميل إليه.

    > [!div class="mx-imgBorder"]
    > ![تحديد نموذج جهة اتصال.](media/contact-active-forms.png "تحديد نموذج جهة اتصال.")

1. لإضافة عنصر تحكم، في مُحرر النماذج، قم بسحب أي حقل من **مستكشف الحقول** إلى حيث تريد أن يظهر عنصر التحكم.

1. حدد الحقل الذي أضفته للتو وحدد **تغيير الخصائص**.

1. انتقل إلى علامة تبويب **عناصر التحكم**، ثم حدد **إضافة عنصر تحكم**. اختر أحد عناصر التحكم المخصصة المتوفرة وحدد **إضافة**.

1. في مربع حوار **خصائص الحقل**، قم بمسح خانة اختيار **‏‫عرض التسمية على النموذج‬**. 

1. حدد الخيار **الويب** لعنصر التحكم. بالنسبة لعنصر التحكم الإثراء، حدد نوع الإثراء الذي ترغب في عرضه عن طريق تكوين الحقل **enrichmentType**. أضف عنصر تحكم منفصل للإثراء لكل نوع من أنواع الإثراء‬.

1. حدد **حفظ** و **نشر** لنشر نموذج جهة الاتصال المحدثة.

1. الانتقال إلى نموذج جهة الاتصال المنشور. ستشاهد عنصر التحكم المضاف حديثًا. قد تحتاج إلى تسجيل الدخول في المرة الأولى الذي تستخدمه فيها.

1. لتخصيص ما تريد عرضه في عنصر التحكم مخصص، قم بتحديد الزر تحرير في الزاوية العلوية اليُمنى.

## <a name="upgrade-customer-card-add-in"></a>ترقية الوظيفة الإضافية لبطاقة العميل

لا تتم ترقية الوظيفة الإضافية لبطاقة العميل بشكل تلقائي. للترقية إلى أحدث إصدار، اتبع هذه الخطوات في تطبيق Dynamics 365 الذي تم تثبيت الوظيفة الإضافية عليه.

1. في تطبيق Dynamics 365، انتقل إلى **الإعدادات** > **تخصيص** وحدد **الحلول**.

1. في جدول الوظائف الإضافية، ابحث عن **CustomerInsightsCustomerCard** وحدد الصف.

1. حدد **تطبيق ترقية الحل** في شريط الإجراءات.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="ترقية الحل في منطقة التخصيص في تطبيقات Dynamics 365.":::

1. بعد بدء عملية الترقية، سوف تشاهد مؤشر تحميل حتى تكتمل الترقية. إذا لم يكن هناك إصدار جديد، فإن الترقية ستعرض رسالة خطأ.

## <a name="troubleshooting"></a>استكشاف الأخطاء وإصلاحها

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>لا تعثر عناصر التحكم من الوظيفة الإضافية لبطاقة العميل على البيانات

**المشكلة:**

حتى مع تكوين حقول المعرفات بشكل صحيح، لا يمكن لعناصر التحكم العثور على بيانات لأي عميل.  

**الحل:**

1. تأكد من تكوين الوظيفة الإضافية للبطاقة وفقًا للإرشادات: [تكوين الوظيفة الإضافية لبطاقة العميل](#configure-the-customer-card-add-in)

1. راجع تكوين استيعاب البيانات. قم بتحرير مصدر البيانات لنظام Dynamics 365 الذي يحتوي على معرّف GUID لجهة الاتصال. إذا تم عرض GUID لمعرف جهة الاتصال بأحرف كبيرة في محرر Power Query، فجرب الخطوات التالية:
    1. قم بتحرير مصدر البيانات لفتح مصدر البيانات في محرر Power Query.
    1. حدد عمود معرف جهة الاتصال.
    1. حدد **التحويل** في شريط الرأس لرؤية الإجراءات المتوفرة.
    1. حدد **أحرف صغيرة**. تحقق من صحة ما إذا كانت معرفات GUID في الجدول أصبحت الآن صغيرة.
    1. احفظ مصدر البيانات.
    1. شغّل استيعاب البيانات وتوحيدها وعمليات نقل البيانات لنشر التغييرات على المعرف الفريد العمومي (GUID).

بعد أن يكمل النظام التحديث الكامل، يجب أن تعرض عناصر التحكم في الوظيفة الإضافية لبطاقة العميل البيانات المتوقعة.

[!INCLUDE [footer-include](includes/footer-banner.md)]