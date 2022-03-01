---
title: وجهات التصدير
description: تصدير البيانات وإدارة وجهات التصدير.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643847"
---
# <a name="export-destinations-preview"></a>وجهات التصدير (معاينة)

تعرض صفحة **وجهات التصدير** كل المواقع التي قمت بإعدادها لتصدير البيانات إليها. يمكنك أيضًا إضافة وجهات تصدير جديدة. علاوةً على ذلك، يعرض خيارات التصدير المتوفرة حاليًا. يمكنك الحصول على نظرة عامة سريعة واعرف ما يمكنك تنفيذه باستخدام كل خيار من خيارات التوسعة. قم بتصدير ملفات تعريف ومقاييس وشرائح موحدة إلى التطبيقات المدعومة الملائمة لأعمالك.

انتقل إلى **المسؤول** > **وجهات التصدير** للعثور على خيارات قابلية التوسعة التالية:

- [الوظيفة الإضافية بطاقة العميل في Dynamics 365](customer-card-add-in.md)
- [موصل مدير إعلانات Facebook](export-facebook.md)
- [موصل Power Automate](export-power-automate.md)
- [موصل Power Apps](export-power-apps.md)
- [موصل Power BI](export-power-bi.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [مخزن البيانات الثنائية كبيرة الحجم لـ Azure](export-azure-blob-storage.md)
- [موصل LiveRamp&reg;](export-liveramp.md)
- [روبوت لـ Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Customer Insights API](apis.md)

## <a name="add-a-new-export-destination"></a>إضافة وجهة تصدير جديدة

لإضافة وجهات التصدير، لديك [أذونات المسؤول](permissions.md). إذا قمت بالتصدير إلى خدمات Microsoft، فنحن نفترض وجود الخدمتين في المؤسسة نفسها.

1. انتقل إلى **المسؤول** > **وجهات التصدير**.

1. قم بالتبديل إلى علامة التبويب **وجهات التصدير الخاصة بي‬**.

1. حدد **إضافة وجهة** لإنشاء وجهة تصدير جديدة.

1. في الجزء **إضافة وجهة**، حدد **نوع** وجهة التصدير في القائمة المنسدلة.

1. أدخل التفاصيل المطلوبة، ثم حدد **التالي** لإنشاء وجهة التصدير.

يمكنك أيضًا تحديد **إعداد** على إطار متجانب في علامة التبويب **اكتشاف**.

## <a name="view-export-destinations"></a>عرض وجهات التصدير

بعد إنشاء وجهات التصدير، سوف تعثر عليها في جدول على علامة التبويب **وجهات التصدير الخاصة بي**. يحتوي هذا الجدول على ثلاثة أعمدة:

- **الاسم المعروض**: الاسم الذي قمت بإدخاله عند إنشاء الوجهة.
- **النوع**: نوع وجهة التصدير الذي قمت بتعيينه عند إنشاء الوجهة.
- **تاريخ الإنشاء**: تاريخ إنشاء الوجهة.

## <a name="edit-an-export-destination"></a>تحرير وجهة تصدير

1. حدد علامة القطع العمودية لوجهة التصدير التي ترغب في تحريرها.

   > [!div class="mx-imgBorder"]
   > ![علامة قطع عمودية](media/export-destinations-page-ellipsis.png "علامة قطع عمودية")

1. حدد **تحرير** من القائمة المنسدلة.

1. قم بتغيير القيم التي تحتاج إلى تحديث، وحدد **حفظ**.

## <a name="export-data-on-demand"></a>تصدير البيانات عند الطلب

بعد تكوين موصل لوجهة تصدير، سوف تعمل عمليات التصدير مع كل [تحديث مجدول](system.md#schedule-tab).

لتصدير البيانات من دون انتظار تحديث مجدول، انتقل إلى علامة التبويب **وجهات التصدير الخاصة بي** على **المسؤول** > **وجهات التصدير**.

> [!div class="mx-imgBorder"]
> ![علامة قطع عمودية](media/export-destinations-page-ellipsis.png "علامة قطع عمودية")

- حدد **تصدير** في أعلى القائمة لتشغيل التصدير إلى جميع وجهات التصدير في وقت واحد.
- حدد علامة القطع (...) بعد عنصر قائمة، ثم حدد الخيار **تصدير** لتشغيل عملية التصدير لوجهة تصدير واحدة.

## <a name="remove-an-export-destination"></a>إزالة وجهة تصدير

لإزالة وجهة تصدير، ابدأ من صفحة **وجهات التصدير** الرئيسية.

1. حدد علامة القطع العمودية لوجهة التصدير التي ترغب في إزالتها.

   > [!div class="mx-imgBorder"]
   > ![علامة قطع عمودية](media/export-destinations-page-ellipsis.png "علامة قطع عمودية")

2. حدد **إزالة** من القائمة المنسدلة.

3. حدد **إزالة** على شاشة التأكيد لتأكيد الإزالة.
