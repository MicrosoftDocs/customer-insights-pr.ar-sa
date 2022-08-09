---
title: تصدير المقاطع إلى Dynamics 365 Sales (إصدار أولي)
description: تعرف على كيفية تكوين الاتصال والتصدير إلى Dynamics 365 Sales.
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
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195965"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>تصدير المقاطع إلى Dynamics 365 Sales (إصدار أولي)

استخدم بيانات العميل الخاصة بك لإنشاء قوائم تسويق ومتابعة عمليات سير العمل وإرسال العروض الترويجية باستخدام Dynamics 365 Sales.

## <a name="prerequisites"></a>المتطلبات

يجب أن تكون سجلات جهات الاتصال موجودة في Dynamics 365 Sales قبل تصدير مقطع من Customer Insights إلى Sales. اقرأ المزيد عن كيفية استيعاب جهات الاتصال من [Dynamics 365 Sales باستخدام Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > لن يؤدي تصدير المقاطع من Customer Insights إلى Sales إلى إنشاء سجلات جهات اتصال جديدة في مثيلات Sales. يجب استيعاب سجلات جهات الاتصال من Sales في Customer Insights واستخدامها كمصدر بيانات. كما يلزم تضمينها في كيان العميل الموحد من أجل تعيين معرفات العملاء إلى معرفات جهات الاتصال قبل أن يصبح تصدير المقاطع ممكنًا.

## <a name="known-limitations"></a>القيود المعروفة

تقتصر عمليات التصدير إلى Dynamics 365 Sales على 100000 لكل مقطع، وهو ما قد يستغرق ما يصل إلى 3 ساعات حتى يكتمل.

## <a name="set-up-connection-to-sales"></a>إعداد الاتصال بـ Sales

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Dynamics 365 Sales**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل عنوان URL لتطبيق Sales في حقل **عنوان الخادم**.

1. في القسم **حساب مسؤول الخادم**، حدد **تسجيل الدخول** واختر حساب Dynamics 365 Sales.

1. عيّن حقل معرف العميل إلى معرف جهة الاتصال في Dynamics 365.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Dynamics 365 Sales. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. حدد حقل معرف جهة الاتصال في كيان العميل الذي يتطابق مع معرف جهة اتصال Dynamics 365.

1. حدد المقاطع التي تريد تصديرها.

1. حدد **حفظ**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
