---
title: تصدير بيانات Customer Insights إلى Dynamics 365 Sales
description: تعرف على كيفية تكوين الاتصال بتطبيق Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643802"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>موصل لتطبيق Dynamics 365 Sales (معاينة)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

استخدم بيانات العميل الخاصة بك لإنشاء قوائم تسويق ومتابعة عمليات سير العمل وإرسال العروض الترويجية باستخدام Dynamics 365 Sales.

## <a name="prerequisite"></a>المتطلبات الأساسية

سجلات جهات الاتصال [من Dynamics 365 Sales التي تم استيعابها باستخدام Common Data Service](connect-power-query.md).

## <a name="configure-the-connector-for-sales"></a>تكوين موصل Sales

1. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.

1. ضمن **Dynamics 365 Sales**، حدد **إعداد**.

1. في حقل **الاسم المعروض**، أدخل اسمًا سهل التمييز لوجهة التصدير.

1. أدخل عنوان URL لتطبيق Sales في حقل **عنوان الخادم**.

1. في القسم **حساب مسؤول الخادم**، حدد **تسجيل الدخول** واختر حساب Dynamics 365 Sales.

1. عيّن حقل معرف العميل إلى معرف جهة الاتصال في Dynamics 365.

1. حدد **التالي**.

1. اختر شريحة أو أكثر.

1. حدد **حفظ**.

## <a name="export-the-data"></a>تصدير البيانات

يمكنك [تصدير البيانات عند الطلب](export-destinations.md). سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).
