---
title: البدء في استخدام إمكانية رؤية المشاركة
description: نظرة عامة على موارد المساعدة للبدء بسرعة.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494578"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>البدء في استخدام إمكانية رؤية المشاركة Dynamics 365 Customer Insights (إصدار أولي للاستخدام العام)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

تتيح لك رؤى المشاركة، وهي قدرة على جمع وقياس سلوك العملاء على موقعك على الويب. وهو يتكامل مع القدرة على رؤى الجمهور بحيث يمكنك رؤية تحليلات سلوكية غنية في الوقت الحقيقي جنبا إلى جنب مع تقارير ملف تعريف العميل. تساعدك الارتباطات في هذه المقالة على تكوين البيئة وإعدادها بسرعة.

## <a name="step-1-review-prerequisites"></a>الخطوة 1: مراجعة ‏‫المتطلبات الأساسية

أولاً، يجب أن يكون لديك حساب مستخدم نشط Microsoft Azure Active Directory (‏AAD). ثم، اقرأ المقالات التالية قبل إعداد مساحة عمل رؤى المشاركات.

- راجع ووافق على [شروط الخدمة](terms-of-service.md) مع Microsoft.  
- اقرأ مقالة [إدارة ملفات تعريف الارتباط وموافقة المستخدم](user-consent-storage.md). بعد ذلك، قم بتقييم ما إذا كنت بحاجة إلى تحديث إشعار موافقة المستخدم الخاص بك. إذا لم يكن لديك ملفات تعريف ارتباط "غير أساسية"، فمن المرجح أن تحتاج إلى تحديث سياسة موقعك.
- راجع [المسرد](glossary.md) للحصول على مقدمة سريعة للمصطلحات والمفاهيم الرئيسية.

## <a name="step-2-explore-engagement-insights"></a>الخطوة 2: استكشاف رؤى المشاركة

في المرة الأولى التي تزور فيها معلومات المشاركة، يمكنك تكوين الإعدادات ومراجعة السياسات واستكشاف الإمكانية.

1. قم بتسجيل الدخول إلى [مدخل إمكانية معلومات المشاركة](https://home.ci.ai.dynamics.com/app/engagement-insights) باستخدام حساب مستخدم Microsoft AAD (المدرسة أو العمل) الخاص بك.

1. حدد منطقتك، وحدد المربع إذا كنت تريد الاشتراك لتلقي تحديثات وعروض البريد الإلكتروني.

1. راجع **شروط استخدام معلومات المشاركة (إصدار أولي)** و **بيان الخصوصية**، ثم حدد **استكشاف العرض التوضيحي** لقبول هذه الإعدادات.

1. استكشف المنتج باستخدام مجموعة من بيانات العينة.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>الخطوة 3: إعداد مساحة عمل وإضافة رمز إلى موقعك على الويب

مساحة العمل هي المكان الذي يمكنك فيه عرض نشاط المستخدم في الوقت الفعلي، وتخزين التقارير وإدارتها. إضافة رمز إلى موقع الويب الخاص بك لبدء جمع *الأحداث*، وبيانات النشاط التي تأتي من المستخدمين.

1. [إنشاء مساحة عمل](create-workspace.md) وإضافة الأعضاء.

1. [أضف رمزًا إلى موقعك](instrument-website.md) أو [تطبيق الأجهزة المحمولة](developer-resources.md#capture-events-from-mobile-apps) لمعرفة نشاط المستخدم الذي يصل إلى مساحة العمل الخاصة بك.

1. اعرض [التقرير في الوقت الحقيقي](view-reports.md) الذي يُظهر المستخدمين النشطين حسب المتصفح والجهاز ونظام التشغيل والموقع واللغة. يمكنك أيضا إنشاء [تقارير مخصصة](custom-reports.md) لإنشاء مرئيات خاصة بك.
    
## <a name="step-4-export-data-to-other-channels"></a>الخطوة 4: تصدير البيانات إلى قنوات أخرى

يمكنك إنشاء *أحداث مكررة* (عرض افتراضي) لبيانات تحليلات الويب. ثم قم بتصفية البيانات وتصديرها إلى Azure Data Lake Storage. يمكنك استخدام البيانات التي تم تصديرها كمصدر بيانات. لمزيد من المعلومات، راجع [إنشاء ارتباط بين رؤى الجمهور ورؤى المشاركة](integrate-audience-insights-engagement-insights.md)

1. [إنشاء أحداث مكررة](refined-events.md) للتصدير.

1. [تصدير البيانات](export-events.md) إلى Data Lake Storage.

1. [أنشئ رابطًا بين رؤى الجمهور ومعلومات المشاركة](integrate-audience-insights-engagement-insights.md) لمشاركة البيانات بين الإمكانات.

1. تعرف على كيفية [حذف بيانات الأحداث التي تحتوي على معلومات شخصية وتصديرها](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>الخطوة الخامسة: ابق على اتصال

نحن نقدر مشاركتك النشطة، ونأخذ في الاعتبار جميع التعليقات ذات الصلة في تطوير الإصدارات المستقبلية. شارك ملاحظاتك والإبلاغ عن المشاكل بواسطة إحدى هذه القنوات:
- [المجتمع](https://go.microsoft.com/fwlink/?linkid=2141648)
- [تقديم تعليقات](https://go.microsoft.com/fwlink/?linkid=2143222)
- [طلب الدعم](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
