---
title: موصل Power BI
description: تعرّ على كيفية استخدام موصل Dynamics 365 Customer Insights في Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4404900"
---
# <a name="connector-for-power-bi-preview"></a>موصل لـ Power BI (معاينة)

أنشئ رسومًا مرئية لبياناتك باستخدام Power BI Desktop. قم بإنشاء معارف دقيقة إضافية وقم بإنشاء تقارير باستخدام بيانات العميل الموحدة الخاصة بك.

## <a name="prerequisites"></a>المتطلبات الأساسية

- لديك تعريف العملاء الموحدة.
- تم تثبيت الإصدار الأخير من [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) على الكمبيوتر. [تعرف على المزيد حول Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>تكوين الموصل لـ Power BI

1. في Power BI Desktop، حدد **ملف** > **الحصول على بيانات**.

1. حدد **مشاهدة المزيد** وابحث عن **Dynamics 365 Customer Insights**

1. حدد النتيجة وحدد **اتصال**.

1. **قم بتسجيل الدخول** باستخدام الحساب المؤسسي نفسه الذي تستخدمه لـ Customer Insights وحدد **اتصال**.
   > [!NOTE]
   > يتم استخدام الحساب الذي أشرت إليه في هذه الخطوة لجلب البيانات من Customer Insights ولا يلزم أن يكون هو نفسه الذي سجلت الدخول إليه في Power BI. لإعادة تعيين الحساب المستخدم لإحضار البيانات، افتح Power BI وانتقل إلى **ملف** > **خيارات** > **إعدادات** > **إعدادات مصدر البيانات**. في قائمة مصادر البيانات، حدد **تسجيل الدخول إلى Dynamics 365 Customer Insights** وحدد **مسح الأذونات**.  

1. في مربع الحوار **المتصفح**. سترى قائمة بجميع البيئات التي يمكنك الوصول إليها. قم بتوسيع بيئة وافتح أي واحد من المجلدات (الكيانات والمقاييس والشرائح وعمليات الإثراء). على سبيل المثال، افتح مجلد **الكيانات** لرؤية كافة الكيانات التي يمكنك استيرادها.

   متصفح موصل ![Power BI](media/power-bi-navigator.png "متصفح موصل Power BI")

1. حدد خانات الاختيار المجاورة للكيانات التي سيتم تضمينها **وتحميلها**. يُمكنك تحديد كيانات متعددة من البيئات المتعددة.

1. سوف ترى مُربع تحميل في أثناء تحميل كياناتك. بمجرد أن يتم تحميل كافة الكيانات المحددة، يمكنك استخدام قدرات Power BI لتمثيل البيانات مرئيًا.

## <a name="large-data-sets"></a>مجموعات البيانات الكبيرة

تم تصميم موصل Customer Insights لـ Power BI للعمل مع مجموعات البيانات التي تحتوي على ما يصل إلى مليون ملف تعريف للعملاء. قد تعمل عملية استيراد مجموعات بيانات أكبر، ولكنها تستغرق وقتًا طويلاً. علاوةً على ذلك، قد يتم تنفيذ هذه العملية ضمن مهلة بسبب قيود Power BI. لمزيد من المعلومات، راجع [Power BI: توصيات بشأن مجموعات البيانات الكبيرة](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>التعامل مع مجموعة فرعية من البيانات

يمكنك العمل مع مجموعة فرعية من بياناتك. علي سبيل المثال، يمكنك إنشاء [شرائح](segments.md) بدلاً من تصدير كافة سجلات العملاء إلى Power BI.
