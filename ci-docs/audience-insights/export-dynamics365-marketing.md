---
title: تصدير بيانات Customer Insights إلى Dynamics 365 Marketing
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: bd8189f8daee1a6aea75e75e116186f62a360ba4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692465"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>استخدام الشرائح في Dynamics 365 Marketing (إصدار أولي)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

استخدم [الشرائح](segments.md) لإنشاء حملات وتحسين مجموعات محددة من العملاء باستخدام Dynamics 365 Marketing. لمزيد من المعلومات ، راجع [استخدام الشرائح من Dynamics 365 Customer Insights مع Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite-for-a-connection"></a>المتطلبات الأساسية لاتصال

- يجب أن تكون سجلات جهات الاتصال موجودة في Dynamics 365 Marketing قبل تصدير شريحة من Customer Insights إلى Marketing. اقرأ المزيد حول كيفية استيعاب جهات الاتصال في [Dynamics 365 Marketing باستخدام Microsoft Dataverse](connect-power-query.md).

  > [!NOTE]
  > لن يؤدي تصدير الشرائح من رؤى الجمهور إلى Marketing إلى إنشاء سجلات جهات اتصال جديدة في مثيلات Marketing. يجب استيعاب سجلات جهات الاتصال من Marketing في رؤى الجمهور واستخدامها كمصدر بيانات. كما يلزم تضمينها في كيان العميل الموحد من أجل تعيين معرفات العملاء إلى معرفات جهات الاتصال قبل أن يصبح تصدير الشرائح ممكنًا.

## <a name="set-up-connection-to-marketing"></a>إعداد الاتصال بـ Marketing

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Dynamics 365 Marketing** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل عنوان URL لتطبيق Marketing‎ في حقل **عنوان الخادم**.

1. في القسم **حساب مسؤول الخادم**، حدد **تسجيل الدخول** واختر حساب Dynamics 365 Marketing‎.

1. عيّن حقل معرف العميل إلى معرف جهة الاتصال في Dynamics 365.

1. حدد **حفظ** لإكمال الاتصال. 

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Dynamics 365 Marketing. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. اختر شريحة أو أكثر.

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
