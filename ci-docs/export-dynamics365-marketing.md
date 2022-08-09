---
title: تصدير المقاطع إلى Dynamics 365 Marketing (إصدار أولي)
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196608"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>تصدير المقاطع إلى Dynamics 365 Marketing (إصدار أولي)

استخدم [المقاطع](segments.md) لإنشاء حملات وتحسين مجموعات محددة من العملاء باستخدام [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

إذا كنت تستخدم الإمكانيات الجديدة في Dynamics 365 Marketing لتنسيق رحلة العميل في الوقت الحقيقي في مؤسسة Dataverse، فلست بحاجة إلى إنشاء تصدير قياسي إلى Dynamics 365 Marketing. تتوفر جهات الاتصال والمقاطع من Customer Insights مباشرة في Dynamics 365 Marketing بعد ربط Marketing و Customer Insights. قبل حذف عمليات التصدير الحالية، راجع الوثائق حول [كيفية توصيل Customer Insights وDynamics 365 Marketing تنسيق رحلة العميل](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>المتطلب الأساسي

يجب أن تكون سجلات جهات الاتصال موجودة في Dynamics 365 Marketing قبل تصدير مقطع من Customer Insights إلى Marketing. اقرأ المزيد حول كيفية استيعاب جهات الاتصال في [Dynamics 365 Marketing باستخدام Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> لن يؤدي تصدير المقاطع من Customer Insights إلى Marketing إلى إنشاء سجلات جهات اتصال جديدة في مثيلات Marketing. يجب استيعاب سجلات جهات الاتصال من Marketing في Customer Insights واستخدامها كمصدر بيانات. كما يلزم تضمينها في كيان العميل الموحد من أجل تعيين معرفات العملاء إلى معرفات جهات الاتصال قبل أن يصبح تصدير المقاطع ممكنًا.

## <a name="set-up-connection-to-marketing"></a>إعداد الاتصال بـ Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Dynamics 365 Marketing**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل عنوان URL لتطبيق Marketing‎ في حقل **عنوان الخادم**.

1. في القسم **حساب مسؤول الخادم**، حدد **تسجيل الدخول** واختر حساب Dynamics 365 Marketing‎.

1. تعيين حقل معرف جهة الاتصال في كيان العميل إلى معرف جهة اتصال Dynamics 365.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Dynamics 365 Marketing. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. حدد حقل معرف جهة الاتصال في كيان العميل الذي يتطابق مع معرف جهة اتصال Dynamics 365.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
