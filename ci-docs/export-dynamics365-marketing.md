---
title: تصدير بيانات Customer Insights إلى Dynamics 365 Marketing
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 7227f3f9e7699a9b5ad546789de5e568b56da579
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645456"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>استخدام الشرائح في Dynamics 365 Marketing (إصدار أولي)



استخدم [الشرائح](segments.md) لإنشاء حملات وتحسين مجموعات محددة من العملاء باستخدام Dynamics 365 Marketing. لمزيد من المعلومات، راجع [استخدام الشرائح من Dynamics 365 Customer Insights مع Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

إذا كنت تستخدم الإمكانيات الجديدة في Dynamics 365 Marketing لتنسيق رحلة العميل في الوقت الحقيقي في مؤسسة Dataverse، فلست بحاجة إلى إنشاء تصدير قياسي إلى Dynamics 365 Marketing. تتوفر جهات الاتصال والمقاطع من Customer Insights مباشرة في Dynamics 365 Marketing بعد ربط Marketing و Customer Insights. قبل حذف عمليات التصدير الحالية، راجع الوثائق حول [كيفية توصيل Customer Insights وDynamics 365 Marketing تنسيق رحلة العميل](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>المتطلبات الأساسية لاتصال

- يجب أن تكون سجلات جهات الاتصال موجودة في Dynamics 365 Marketing قبل تصدير شريحة من Customer Insights إلى Marketing. اقرأ المزيد حول كيفية استيعاب جهات الاتصال في [Dynamics 365 Marketing باستخدام Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > لن يؤدي تصدير المقاطع من Customer Insights إلى Marketing إلى إنشاء سجلات جهات اتصال جديدة في مثيلات Marketing. يجب استيعاب سجلات جهات الاتصال من Marketing في Customer Insights واستخدامها كمصدر بيانات. كما يلزم تضمينها في كيان العميل الموحد من أجل تعيين معرفات العملاء إلى معرفات جهات الاتصال قبل أن يصبح تصدير الشرائح ممكنًا.

## <a name="set-up-connection-to-marketing"></a>إعداد الاتصال بـ Marketing

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Dynamics 365 Marketing** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل عنوان URL لتطبيق Marketing‎ في حقل **عنوان الخادم**.

1. في القسم **حساب مسؤول الخادم**، حدد **تسجيل الدخول** واختر حساب Dynamics 365 Marketing‎.

1. تعيين حقل معرف جهة الاتصال في كيان العميل إلى معرف جهة اتصال Dynamics 365.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
