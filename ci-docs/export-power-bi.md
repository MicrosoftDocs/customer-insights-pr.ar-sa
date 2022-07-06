---
title: موصل Power BI (معاينة)
description: تعرّ على كيفية استخدام موصل Dynamics 365 Customer Insights في Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 72daf6d4ef3b6afb8049c622b57e7ec44762fb21
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051253"
---
# <a name="power-bi-connector-preview"></a>موصل Power BI (معاينة)

قم بإنشاء الرسوم المرئية لبياناتك باستخدام Microsoft Power BI Desktop. قم بإنشاء معارف دقيقة إضافية وقم بإنشاء تقارير باستخدام بيانات العميل الموحدة الخاصة بك.

## <a name="prerequisites"></a>المتطلبات الأساسية

- لديك تعريف العملاء الموحدة.
- تم تثبيت أحدث إصدار من [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) على الكمبيوتر. [تعرف على المزيد حول Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>تكوين الموصل لـ Power BI

1. في Power BI Desktop، حدد **ملف** > **الحصول على بيانات**.

1. حدد **مشاهدة المزيد** وابحث عن **Dynamics 365 Customer Insights**

1. حدد **اتصال**.

1. **قم بتسجيل الدخول** باستخدام الحساب المؤسسي نفسه الذي تستخدمه لـ Customer Insights وحدد **اتصال**.
   > [!NOTE]
   > يتم استخدام الحساب الذي أشرت إليه في هذه الخطوة لجلب البيانات من Customer Insights ولا يلزم أن يكون هو نفسه الذي سجلت الدخول إليه في Power BI. لإعادة تعيين الحساب المستخدم لإحضار البيانات، افتح Power BI وانتقل إلى **ملف** > **خيارات** > **إعدادات** > **إعدادات مصدر البيانات**. في قائمة مصادر البيانات، حدد **تسجيل الدخول إلى Dynamics 365 Customer Insights** وحدد **مسح الأذونات**.  

1. في مربع الحوار **المتصفح**. سترى قائمة بجميع البيئات التي يمكنك الوصول إليها. قم بتوسيع بيئة وافتح أي واحد من المجلدات (الكيانات والمقاييس والشرائح وعمليات الإثراء). على سبيل المثال، افتح مجلد **الكيانات** لرؤية كافة الكيانات التي يمكنك استيرادها.

   مستعرض موصل ![Power BI.](media/power-bi-navigator.png "متصفح موصل Power BI")

1. حدد خانات الاختيار المجاورة للكيانات التي سيتم تضمينها **وتحميلها**. يُمكنك تحديد كيانات متعددة من البيئات المتعددة.

1. سوف ترى مُربع تحميل في أثناء تحميل كياناتك. بمجرد أن يتم تحميل كافة الكيانات المحددة، يمكنك استخدام قدرات Power BI لتمثيل البيانات مرئيًا.

## <a name="large-data-sets"></a>مجموعات البيانات الكبيرة

تم تصميم موصل Customer Insights لـ Power BI للعمل مع مجموعات البيانات التي تحتوي على ما يصل إلى مليون ملف تعريف للعملاء. قد تعمل عملية استيراد مجموعات بيانات أكبر، ولكنها تستغرق وقتًا طويلاً. علاوةً على ذلك، قد يتم تنفيذ هذه العملية ضمن مهلة بسبب قيود Power BI. لمزيد من المعلومات، راجع [Power BI: توصيات بشأن مجموعات البيانات الكبيرة](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>التعامل مع مجموعة فرعية من البيانات

يمكنك العمل مع مجموعة فرعية من بياناتك. علي سبيل المثال، يمكنك إنشاء [شرائح](segments.md) بدلاً من تصدير كافة سجلات العملاء إلى Power BI.

## <a name="troubleshooting"></a>استكشاف الأخطاء وإصلاحها

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>لا تظهر بيئة Customer Insights في Power BI

لن تتوفر البيئات التي تحتوي على أكثر من [علاقة](relationships.md) محددة بين كيانين متطابقين في Customer Insights في موصل Power BI.

يمكنك تحديد العلاقات المكررة وإزالتها.

1. انتقل إلى **البيانات** > **العلاقات** في البيئة التي تفتقدها في Power BI.
2. حدد العلاقات المكررة:
   - تحقق مما إذا كان هناك أكثر من علاقة واحدة محددة بين نفس الكيانين.
   - تحقق مما إذا كانت هناك علاقة تم إنشاؤها بين كيانين مضمنين في عملية التوحيد. هناك علاقة ضمنية محددة بين جميع الكيانات المضمنة في عملية التوحيد.
3. قم بإزالة أية علاقات مكررة تم تحديدها.

بعد إزالة العلاقات المكررة، حاول تكوين موصل Power BI مرة أخرى. من المفترض أن تصبح البيئة متاحة الآن.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>أخطاء في حقول التاريخ عند تحميل الكيانات في Power BI Desktop

عند تحميل كيانات تحتوي على حقول بتنسيق تاريخ مثل MM/DD/YYYY، يمكن أن تواجه أخطاء بسبب عدم تطابق التنسيقات المحلية. يحدث عدم التطابق عندما يتم تعيين ملف Power BI Desktop الخاص بك على لغة أخرى غير اللغة الإنجليزية (الولايات المتحدة)، لأنه يتم حفظ حقول التاريخ في Customer Insights بتنسيق الولايات المتحدة.

يحتوي ملف Power BI Desktop على إعداد محلي واحد، والذي يتم تطبيقه عند استرداد البيانات. قم بتفسير حقول التاريخ هذه بشكل صحيح، وقم بتعيين إعداد محلي لملف BPI إلى English (الولايات المتحدة). [تعرف على كيفية تغيير اللغة المحلية لملف Power BI desktop](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE [footer-include](includes/footer-banner.md)]
