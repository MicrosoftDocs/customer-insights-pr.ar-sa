---
title: تصدير بيانات Customer Insights إلى Dynamics 365 Marketing
description: تعرف على كيفية تكوين الاتصال بتطبيق Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643757"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>موصل لتطبيق Dynamics 365 Marketing (معاينة)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

استخدم [الشرائح](segments.md) لإنشاء حملات وتحسين مجموعات محددة من العملاء باستخدام Dynamics 365 Marketing. لمزيد من المعلومات ، راجع [استخدام الشرائح من Dynamics 365 Customer Insights مع Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>المتطلبات الأساسية

سجلات جهات الاتصال [من Dynamics 365 Marketing التي تم استيعابها باستخدام Common Data Service](connect-power-query.md).

## <a name="configure-the-connector-for-marketing"></a>تكوين موصل Marketing

1. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.

1. ضمن **Dynamics 365 Marketing‎**، حدد **إعداد**.

1. في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.

1. أدخل عنوان URL لتطبيق Marketing‎ في حقل **عنوان الخادم**.

1. في القسم **حساب مسؤول الخادم**، حدد **تسجيل الدخول** واختر حساب Dynamics 365 Marketing‎.

1. عيّن حقل معرف العميل إلى معرف جهة الاتصال في Dynamics 365.

1. حدد **التالي**.

1. اختر شريحة أو أكثر.

1. حدد **حفظ**.

## <a name="export-the-data"></a>تصدير البيانات

يمكنك [تصدير البيانات عند الطلب](export-destinations.md). سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).
