---
title: موصل Power BI (معاينة)
description: تعرّ على كيفية استخدام موصل Dynamics 365 Customer Insights في Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196654"
---
# <a name="power-bi-connector-preview"></a>موصل Power BI (معاينة)

قم بإنشاء الرسوم المرئية لبياناتك باستخدام Microsoft Power BI Desktop. قم بإنشاء معارف دقيقة إضافية وقم بإنشاء تقارير باستخدام بيانات العميل الموحدة الخاصة بك.

## <a name="prerequisites"></a>المتطلبات

- ملفات تعريف العملاء الموحدة.
- تم تثبيت أحدث إصدار من [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) على الكمبيوتر. [تعرف على المزيد حول Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>تكوين الموصل لـ Power BI

1. في Power BI Desktop، حدد **ملف** > **الحصول على بيانات**.

1. حدد **مشاهدة المزيد** وابحث عن **Dynamics 365 Customer Insights**

1. حدد **اتصال**.

1. **قم بتسجيل الدخول** باستخدام الحساب المؤسسي نفسه الذي تستخدمه لـ Customer Insights وحدد **اتصال**.
   > [!NOTE]
   > يتم استخدام الحساب الذي أشرت إليه في هذه الخطوة لجلب البيانات من Customer Insights ولا يلزم أن يكون هو نفسه الذي سجلت الدخول إليه في Power BI. لإعادة تعيين الحساب المستخدم لإحضار البيانات، افتح Power BI وانتقل إلى **ملف** > **خيارات** > **إعدادات** > **إعدادات مصدر البيانات**. في قائمة مصادر البيانات، حدد **تسجيل الدخول إلى Dynamics 365 Customer Insights** وحدد **مسح الأذونات**.  

1. في مربع الحوار **متنقل**، يمكنك عرض قائمة بجميع البيئات التي يمكنك الوصول إليها. قم بتوسيع بيئة وافتح أي واحد من المجلدات (الكيانات والمقاييس والمقاطع وعمليات الإثراء). على سبيل المثال، افتح مجلد **الكيانات** لرؤية كافة الكيانات التي يمكنك استيرادها.

   مستعرض موصل :::image type="content" source="media/power-bi-navigator.png" alt-text="Power BI.":::

1. حدد خانات الاختيار المجاورة للكيانات التي سيتم تضمينها **وتحميلها**. يُمكنك تحديد كيانات متعددة من البيئات المتعددة.

   يتم عرض مربع حوار التحميل أثناء تحميل الكيانات الخاصة بك. بمجرد أن يتم تحميل كافة الكيانات المحددة، استخدم قدرات Power BI لتمثيل البيانات مرئيًا.

## <a name="large-data-sets"></a>مجموعات البيانات الكبيرة

تم تصميم موصل Customer Insights لـ Power BI للعمل مع مجموعات البيانات التي تحتوي على ما يصل إلى مليون ملف تعريف للعملاء. قد ينجح استيراد مجموعات أكبر من البيانات، ولكنه يستغرق وقتًا طويلاً ويمكن أن تنتهي المهلة بسبب قيود Power BI. لمزيد من المعلومات، راجع [Power BI: توصيات بشأن مجموعات البيانات الكبيرة](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>التعامل مع مجموعة فرعية من البيانات

يمكنك العمل مع مجموعة فرعية من بياناتك. علي سبيل المثال، قم بإنشاء [مقاطع](segments.md) بدلاً من تصدير كافة سجلات العملاء إلى Power BI.

## <a name="troubleshooting"></a>استكشاف الأخطاء وإصلاحها

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>لا تظهر بيئة Customer Insights في Power BI

لن تتوفر البيئات التي تحتوي على أكثر من [علاقة](relationships.md) محددة بين كيانين متطابقين في Customer Insights في موصل Power BI.

حدد العلاقات المكررة وقم بإزالتها.

1. انتقل إلى **البيانات** > **العلاقات** في البيئة التي تفتقدها في Power BI.
1. حدد العلاقات المكررة:
   - تحقق مما إذا كان هناك أكثر من علاقة واحدة محددة بين نفس الكيانين.
   - تحقق مما إذا كانت هناك علاقة تم إنشاؤها بين كيانين مضمنين في عملية التوحيد. هناك علاقة ضمنية محددة بين جميع الكيانات المضمنة في عملية التوحيد.
1. قم بإزالة أية علاقات مكررة تم تحديدها.

بعد إزالة العلاقات المكررة، حاول تكوين موصل Power BI مرة أخرى.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>أخطاء في حقول التاريخ عند تحميل الكيانات في Power BI Desktop

عند تحميل كيانات تحتوي على حقول بتنسيق تاريخ مثل MM/DD/YYYY، يمكن أن تواجه أخطاء بسبب عدم تطابق التنسيقات المحلية. يحدث عدم التطابق عندما يتم تعيين ملف Power BI Desktop الخاص بك على لغة أخرى غير اللغة الإنجليزية (الولايات المتحدة)، لأنه يتم حفظ حقول التاريخ في Customer Insights بتنسيق الولايات المتحدة.

يحتوي ملف Power BI Desktop على إعداد محلي واحد، والذي يتم تطبيقه عند استرداد البيانات. لإصلاح أخطاء التاريخ، [قم بتعيين إعداد محلي لملف BPI](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) إلى English (الولايات المتحدة).

[!INCLUDE [footer-include](includes/footer-banner.md)]
