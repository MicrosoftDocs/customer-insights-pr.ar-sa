---
title: تصدير بيانات Customer Insights إلى Dynamics 365 Sales
description: تعرف على كيفية تكوين الاتصال بتطبيق Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 39ecdf528c6be4d8fb420a52a6ed998317e43bcd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598093"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>موصل لتطبيق Dynamics 365 Sales (معاينة)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

استخدم بيانات العميل الخاصة بك لإنشاء قوائم تسويق ومتابعة عمليات سير العمل وإرسال العروض الترويجية باستخدام Dynamics 365 Sales.

## <a name="prerequisite"></a>المتطلبات الأساسية

1. يجب أن تكون سجلات جهات الاتصال موجودة في Dynamics 365 Sales قبل تصدير شريحة من Customer Insights إلى Sales. اقرأ المزيد حول كيفية استيعاب جهات الاتصال في [Dynamics 365 Sales باستخدام Common Data Services](connect-power-query.md).

   > [!NOTE]
   > لن يؤدي تصدير الشرائح من رؤى الجمهور إلى Sales إلى إنشاء سجلات جهات اتصال جديدة في مثيلات Sales. يجب استيعاب سجلات جهات الاتصال من Sales في رؤى الجمهور واستخدامها كمصدر بيانات. كما يلزم تضمينها في كيان العميل الموحد من أجل تعيين معرفات العملاء إلى معرفات جهات الاتصال قبل أن يصبح تصدير الشرائح ممكنًا.

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]