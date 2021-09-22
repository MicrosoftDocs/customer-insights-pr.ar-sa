---
title: البدء في استخدام إمكانية رؤية المشاركة
description: نظرة عامة على موارد المساعدة للبدء بسرعة.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405342"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>البدء في استخدام إمكانية رؤية المشاركة Dynamics 365 Customer Insights (إصدار أولي للاستخدام العام)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

تتيح لك رؤى المشاركة، وهي قدرة على جمع وقياس سلوك العملاء على موقعك على الويب. وهو يتكامل مع القدرة على رؤى الجمهور بحيث يمكنك رؤية تحليلات سلوكية غنية في الوقت الحقيقي جنبا إلى جنب مع تقارير ملف تعريف العميل. تساعدك الارتباطات في هذه المقالة على تكوين البيئة وإعدادها بسرعة.

## <a name="step-1-review-prerequisites"></a>الخطوة 1: مراجعة ‏‫المتطلبات الأساسية

أولاً، يجب أن يكون لديك حساب مستخدم نشط ل Microsoft Azure Active Directory. ثم، اقرأ المقالات التالية قبل إعداد مساحة عمل رؤى المشاركات.

- راجع ووافق على [شروط الخدمة](terms-of-service.md) مع Microsoft.  
- اقرأ مقالة [إدارة ملفات تعريف الارتباط وموافقة المستخدم](user-consent-storage.md). بعد مراجعة هذه المقالة، قم بتقييم ما إذا كنت بحاجة إلى تحديث إعلام موافقة المستخدم. إذا لم يكن لديك ملفات تعريف ارتباط "غير أساسية"، فمن المرجح أن تحتاج إلى تحديث سياسة موقعك.
- راجع [المسرد](glossary.md) للحصول على مقدمة سريعة للمصطلحات والمفاهيم الرئيسية.

## <a name="step-2-explore-engagement-insights"></a>الخطوة 2: استكشاف رؤى المشاركة

في المرة الأولى التي تزور فيها رؤى المشاركة، يمكنك تكوين الإعدادات ومراجعة السياسات واستكشاف المنتج.

1. تسجيل الدخول إلى [مدخل إمكانية رؤى المشاركة](https://pi.dynamics.com) باستخدام حساب مستخدم Microsoft Azure Active Directory الخاص بك. (يمكن أن يكون حساب المدرسة أو العمل الخاص بك.)

1. حدد منطقتك، واستخدم خانة الاختيار للإشارة إلى ما إذا كنت ترغب في الاشتراك لتلقي التحديثات والعروض عبر البريد الإلكتروني.

1. راجع **شروط استخدام رؤى المشاركة (الإصدار الأولي)** و **بيان الخصوصية**، ثم حدد **استكشاف العرض التوضيحي** لقبولها.

1. استكشف المنتج باستخدام مجموعة من بيانات العينة.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>الخطوة 3: إعداد مساحة عمل وإضافة رمز إلى موقعك على الويب

مساحة العمل هي المكان الذي يمكنك عرض نشاط المستخدم في الوقت الفعلي، وتخزين التقارير وإدارتها. إضافة رمز إلى موقع الويب الخاص بك لبدء جمع *الأحداث*، وبيانات النشاط التي تأتي من المستخدمين.

1. [إنشاء مساحة عمل](create-workspace.md) وإضافة الأعضاء.

1. [أضف رمزًا إلى موقعك](instrument-website.md) أو [تطبيق الأجهزة المحمولة](developer-resources.md#capture-events-from-mobile-apps) لمعرفة نشاط المستخدم الذي يصل إلى مساحة العمل الخاصة بك.

1. عرض [تقرير في الوقت الفعلي](view-reports.md) يعرض المستخدمين النشطين حسب المتصفح والجهاز ونظام التشغيل والموقع واللغة. يمكنك أيضا إنشاء [تقارير مخصصة](custom-reports.md) لإنشاء مرئيات خاصة بك.
    
## <a name="step-4-export-data-to-other-channels"></a>الخطوة 4: تصدير البيانات إلى قنوات أخرى

يمكنك إنشاء *أحداث مكررة* (عرض افتراضي) لبيانات تحليلات الويب. ثم قم بتصفية البيانات وتصديرها إلى Azure Data Lake Storage. يمكنك استخدام البيانات التي تم تصديرها كمصدر بيانات. لمزيد من المعلومات، راجع [إنشاء ارتباط بين رؤى الجمهور ورؤى المشاركة](integrate-audience-insights-engagement-insights.md)

1. [إنشاء أحداث مكررة](refined-events.md) للتصدير.

1. [تصدير البيانات](export-events.md) إلى Data Lake Storage.

1. تعرف على كيفية [حذف بيانات الأحداث التي تحتوي على معلومات شخصية وتصديرها](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>الخطوة الخامسة: ابق على اتصال

نحن نقدر مشاركتك النشطة ونعتزم النظر في جميع الملاحظات ذات الصلة في تطوير الإصدارات المستقبلية. شارك ملاحظاتك والإبلاغ عن المشاكل بواسطة إحدى هذه القنوات:
- [المجتمع](https://go.microsoft.com/fwlink/?linkid=2141648)
- [تقديم تعليقات](https://go.microsoft.com/fwlink/?linkid=2143222)
- [طلب الدعم](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
