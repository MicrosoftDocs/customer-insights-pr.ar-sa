---
title: تصدير بيانات Customer Insights إلى Dynamics 365 Sales
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 4c1b5eaa3568b5c73013024d2da7e65276142f72
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455814"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a>استخدام الشرائح في Dynamics 365 Sales (إصدار أولي)



استخدم بيانات العميل الخاصة بك لإنشاء قوائم تسويق ومتابعة عمليات سير العمل وإرسال العروض الترويجية باستخدام Dynamics 365 Sales.

## <a name="known-limitations"></a>القيود المعروفة

- تقتصر الصادرات إلى Dynamics 365 Sales على 100 ألف عضو لكل مقطع.
- يمكن أن تستغرق عمليات تصدير المقطع إلى Dynamics 365 Sales ما يصل إلى 3 ساعات حتى تكتمل. 

## <a name="prerequisite-for-connection"></a>المتطلبات الأساسية للاتصال

1. يجب أن تكون سجلات جهات الاتصال موجودة في Dynamics 365 Sales قبل تصدير شريحة من Customer Insights إلى Sales. اقرأ المزيد عن كيفية استيعاب جهات الاتصال من [Dynamics 365 Sales باستخدام Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > لن يؤدي تصدير الشرائح من رؤى الجمهور إلى Sales إلى إنشاء سجلات جهات اتصال جديدة في مثيلات Sales. يجب استيعاب سجلات جهات الاتصال من Sales في رؤى الجمهور واستخدامها كمصدر بيانات. كما يلزم تضمينها في كيان العميل الموحد من أجل تعيين معرفات العملاء إلى معرفات جهات الاتصال قبل أن يصبح تصدير الشرائح ممكنًا.

## <a name="set-up-the-connection-to-sales"></a>إعداد الاتصال بـ Sales

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Dynamics 365 Sales** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل عنوان URL لتطبيق Sales في حقل **عنوان الخادم**.

1. في القسم **حساب مسؤول الخادم**، حدد **تسجيل الدخول** واختر حساب Dynamics 365 Sales.

1. عيّن حقل معرف العميل إلى معرف جهة الاتصال في Dynamics 365.

1. حدد **حفظ** لإكمال الاتصال. 

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Dynamics 365 Sales. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. اختر شريحة أو أكثر.

1. حدد **حفظ**

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
