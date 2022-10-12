---
title: جدولة تحديث النظام
description: جدولة الوقت الذي ينبغي تحديث النظام فيه
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610312"
---
# <a name="schedule-system-refresh"></a>جدولة تحديث النظام

جدولة التحديثات التلقائية لجميع ملفات [مصادر البيانات المبتلعة](data-sources.md). يساعد التحديث التلقائي في التأكد من أن التحديثات من مصادر البيانات تنعكس في ملفات تعريف العميل الموحدة.

> [!NOTE]
> Power Query يتم تحديث مصادر البيانات التي تديرها وفقًا لجداولها الخاصة. لجدولة تحديث Power Query مصادر البيانات التي تديرها، قم بتكوين إعدادات التحديث في مصدر البيانات المحدد هذا من صفح **Data sources**. عليك مواءمة الوقت مع جدول تحديث البيانات النهائي لتفادي حدوث التحديثات كلها في وقت واحد.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platformإعدادات تحديث تدفق البيانات":::

## <a name="set-system-refresh-schedule"></a>قم بتعيين جدول تحديث النظام

1. انتقل إلى **المسؤول** > **النظام**، ثم حدد علامة التبويب **جدولة**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="جدولة علامة تبويب التحديث من صفحة النظام.":::

1. الحالة الافتراضية للتحديث المجدول على الوضع **إيقاف التشغيل**. لتمكين التحديثات المجدولة، قم بتغيير التبديل الموجود أعلى الشاشة إلى **تشغيل**.

1. اختر ما بين التحديثات **الأسبوعية** (افتراضية) و **اليومية**. إذا كنت تعتزم جدولة عمليات التحديث الأسبوعية، فقم بتحديد يوم واحد أو أكثر من الأيام التي ترغب في إجراء التحديث بها.

1. قم بتعيين **المنطقة الزمنية**، ثم استخدم القائمة المنسدلة **للوقت** لتعيين توقيت التحديث الخاص بك. إذا كنت ترغب في جدولة عمليات تحديث متعددة في يوم واحد، حدد **إضافة وقت آخر**. يمكنك إضافة أربعة تحديثات كحدٍ أقصى.

1. حدد **حفظ** لتطبيق التغييرات التي أجريتها.

[!INCLUDE [footer-include](includes/footer-banner.md)]
