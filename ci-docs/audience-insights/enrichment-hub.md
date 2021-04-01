---
title: إثراء ملفات تعريف العملاء الموحدة
description: استخدم القدرات لإثراء بيانات العملاء.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597679"
---
# <a name="enrichment-for-customer-profiles-preview"></a>الإثراء لملفات تعريف العملاء (معاينة)

استخدم البيانات من مصادر مثل Microsoft والشركاء الآخرين لإثراء بيانات العملاء.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="صفحة مركز الإثراء":::

في رؤى الجمهور، انتقل إلى **البيانات** > **إثراء** للعمل مع خيارات الإثراء.    
يجب أن يكون لديك أذونات المساهم أو المسؤول لإنشاء أو تحرير عمليات الإثراء. لمزيد من المعلومات، راجع [الأذونات](permissions.md).

في علامة التبويب **اكتشاف**، ستجد عمليات الإثراء التالية:

- [العلامات التجارية](enrichment-microsoft-graph.md) مقدمة من Microsoft Graph
- [الاهتمامات](enrichment-microsoft-graph.md) مقدمة من Microsoft Graph
- [بيانات الشركة](enrichment-leadspace.md) مقدمة من Leadspace
- [الخصائص السكانية](enrichment-experian.md) تم توفيرها بواسطة Experian
- [بيانات الموقع](enrichment-here.md) مقدمة من HERE Technologies
- [البيانات المخصصة](enrichment-SFTP-custom-import.md) عبر بروتوكول نقل الملفات الآمن (SFTP)‬

في علامة التبويب **عمليات الإثراء الخاصة بي‬**، يمكنك رؤية عمليات الإثراء الذي قمت بتكوينها وتحرير خصائصها.

## <a name="manage-existing-enrichments"></a>إدارة ‏‫عمليات الإثراء الموجودة

انتقل إلى **‏‫عمليات الإثراء** للاطلاع على كل ‏‫عمليات الإثراء التي تم تكوينها. يتم تمثيل كل عملية من ‏‫عمليات الإثراء كصف يتضمن معلومات إضافية حول ‏‫عملية الإثراء.

حدد ‏‫عملية إثراء للاطلاع على الخيارات المتوفرة. ويمكنك بدلاً من ذلك تحديد علامة القطع (...) على عنصر قائمة لمشاهدة الخيارات.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="خيارات إدارة عمليات الإثراء في قائمة عمليات الإثراء":::

- **عرض** تفاصيل عمليات الإثراء باستخدام عدد ملفات تعريف العملاء الذين تم إثراؤهم.
- **تحرير** تكوين عملية الإثراء.
- **قم بتشغيل** الإثراء لتحديث ملفات تعريف العملاء بأحدث البيانات.
- **إلغاء تنشيط** عملية إثراء موجودة لإيقافها عن التحديث تلقائيًا بكل تحديث مجدول. تظل البيانات من آخر تحديث ناجح متاحة. **تنشيط** عملية إثراء غير نشطة لإعادة تشغيل التحديث التلقائي بكل تحديث مجدول.
- **حذف** إثراء.

يمكنك تشغيل أو إلغاء تنشيط العديد من عمليات الإثراء مرة واحدة عن طريق تحديدها في القائمة. خيارات العرض والتحرير غير متاحة كإجراء مجمع ولا تعمل إلا على عملية إثراء واحدة في كل مرة.


[!INCLUDE[footer-include](../includes/footer-banner.md)]