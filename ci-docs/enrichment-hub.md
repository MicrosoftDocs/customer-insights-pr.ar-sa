---
title: إثراء ملفات تعريف العملاء الموحدة
description: استخدم القدرات لإثراء بيانات العملاء.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 5c14e6c96d2f907ba161331b6f92277191cbdbef
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653507"
---
# <a name="enrichment-for-customer-profiles-preview"></a>الإثراء لملفات تعريف العملاء (معاينة)

استخدم البيانات من مصادر مثل Microsoft والشركاء الآخرين لإثراء بيانات العملاء.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="صفحة مركز الإثراء.":::

انتقل إلى **البيانات** > **إثراء** للعمل مع خيارات الإثراء.  

يجب أن يكون لديك أذونات المساهم أو المسؤول لإنشاء أو تحرير عمليات الإثراء. لمزيد من المعلومات، راجع [الأذونات](permissions.md).

في علامة التبويب **اكتشاف**، ستجد جميع خيارات الإثراء المدعومة.

# <a name="individual-consumers-b-to-c"></a>[المستهلكون الفرديون (B-to-C)](#tab/b2c)

- [العلامات التجارية](enrichment-microsoft.md) الموفرة بواسطة Microsoft
- [الاهتمامات](enrichment-microsoft.md) الموفرة بواسطة Microsoft
- [العناوين المحسنة](enrichment-enhanced-addresses.md) التي تقدمها Microsoft 
- [الخصائص السكانية](enrichment-experian.md) الموفرة بواسطة Experian
- [البيانات المخصصة](enrichment-SFTP-custom-import.md) عبر بروتوكول نقل الملفات الآمن (SFTP)‬ 
- تم توفير [خرائط Azure](enrichment-azure-maps.md) بواسطة Microsoft
- [بيانات الموقع](enrichment-here.md) مقدمة من HERE Technologies 
- [الهوية](enrichment-liveramp.md) الموفرة بواسطة LiveRamp Abili

# <a name="business-accounts-b-to-b"></a>[حسابات الأعمال (B-to-B)](#tab/b2b)

- [بيانات الشركة](enrichment-leadspace.md) مقدمة من Leadspace
- [العناوين المحسنة](enrichment-enhanced-addresses.md) التي تقدمها Microsoft 
- [بيانات الشركة المحسنة](enrichment-enhanced-company-data.md) المقدمة من Microsoft
- [بيانات الموقع](enrichment-here.md) مقدمة من HERE Technologies 
- [البيانات المخصصة](enrichment-SFTP-custom-import.md) عبر بروتوكول نقل الملفات الآمن (SFTP)‬ 
- تم توفير [خرائط Azure](enrichment-azure-maps.md) بواسطة Microsoft
- [بيانات الشركة](enrichment-dnb.md) المقدمة بواسطة Dun & Bradstreet
- [بيانات تفاعل الحساب](enrichment-office.md) المقدمة من Microsoft

---

في علامة التبويب **عمليات الإثراء الخاصة بي‬**، يمكنك رؤية عمليات الإثراء الذي قمت بتكوينها وتحرير خصائصها.

## <a name="manage-existing-enrichments"></a>إدارة ‏‫عمليات الإثراء الموجودة

انتقل إلى علامة التبويب **عمليات الإثراء الخاصة بي** لمعرفة جميع عمليات الإثراء التي تم تكوينها. يتم تمثيل كل عملية من ‏‫عمليات الإثراء كصف يتضمن معلومات إضافية حول ‏‫عملية الإثراء.

حدد الإثراء من أجل الاطلاع على الخيارات المتاحة. يمكنك أيضًا تحديد علامة الحذف (...) على عنصر قائمة لمشاهدة الخيارات. إذا قمت بتكوين العديد من عمليات الإثراء، يمكنك استخدام مربع البحث للعثور عليه بسرعة.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="خيارات إدارة عمليات الإثراء في قائمة عمليات الإثراء.":::

- **عرض** تفاصيل عمليات الإثراء باستخدام عدد ملفات تعريف العملاء الذين تم إثراؤهم.
- **تحرير** تكوين عملية الإثراء.
- **قم بتشغيل** الإثراء لتحديث ملفات تعريف العملاء بأحدث البيانات.
- **إلغاء تنشيط** عملية إثراء موجودة لإيقافها عن التحديث تلقائيًا بكل تحديث مجدول. ستظل البيانات من آخر تحديث ناجح متوفرة. **تنشيط** عملية إثراء غير نشطة لإعادة تشغيل التحديث التلقائي بكل تحديث مجدول.
- **حذف** الإثراء.

قم بتشغيل أو إلغاء تنشيط عمليات إثراء متعددة مرة واحدة عن طريق تحديدها في القائمة. لا تتوفر خيارات العرض والتحرير كإجراء مجمع. إنهم يعملون على إثراء واحد في المرة الواحدة.

## <a name="enrichments-and-connections"></a>عمليات الإثراء والاتصالات

يتم تكوين عمليات إثراء الأطراف الثالثة باستخدام [الاتصالات](connections.md)، التي يقوم المسؤول بإعدادها باستخدام بيانات الاعتماد ويقدم الموافقة على عمليات نقل البيانات. يمكن للمسؤولين والمساهمين استخدام الاتصالات لتكوين عمليات الإثراء.  

## <a name="multiple-enrichments-of-the-same-type"></a>عمليات إثراء متعددة من نفس النوع

يتم تحديد الكيان الذي سيتم إثراءه أثناء تكوين المنشط، والذي يسمح لك بإثراء مجموعة فرعية فقط من ملفات التعريف الخاصة بك. على سبيل المثال، إثراء البيانات لشريحة معينة فقط. يمكنك تكوين العديد من عمليات الإثراء من نفس النوع وإعادة استخدام نفس الاتصال. سيكون لبعض عمليات الإثراء حدود لعدد عمليات الإثراء من نفس النوع التي يمكن إنشاؤها. يمكن رؤية الحدود والاستخدام الحالي على صفحة **الإثراء**.

## <a name="enrich-data-sources-before-unification"></a>إثراء مصادر البيانات قبل التوحيد

يمكنك إثراء بيانات العميل قبل توحيد البيانات للمساعدة في زيادة جودة مطابقة البيانات. لمزيد من المعلومات، راجع [إثراء مصدر البيانات](data-sources-enrichment.md).

## <a name="see-the-progress-of-the-enrichment-process"></a>اطلع على التقدم المحرز في عملية الإثراء

يمكنك العثور على تفاصيل حول معالجة الإثراء، بما في ذلك حالته والمشكلات المحتملة أثناء التحديث أو بعد اكتمال التحديث. افهم العمليات المتضمنة لتحديث الإثراء والوقت المستغرق لتشغيل العمليات. حالة الإثراء مدعومة لـ Experian وLeadspace وHERE Technologies واستيراد SFTP وخرائط Azure.

لمعرفة حالة الإثراء

1. انتقل إلى **بيانات** > **إثراء**. 
1. في علامة التبويب **عمليات الإثراء الخاصة بي**، حدد حالة الإثراء لفتح جزء جانبي. 
1. في جزء **تفاصيل التقدم**، قم بتوسيع قسم **عمليات الإثراء**. 
1. ضمن الإثراء الذي تريد أن ترى التقدم فيه، حدد **راجع التفاصيل**. 
1. في جزء **تفاصيل المهمة**، حدد **إظهار التفاصيل** لمعرفة العمليات التي ينطوي عليها تحديث الإثراء وحالتها. 

## <a name="enrichment-results"></a>نتائج الإثراء

بعد اكتمال تشغيل الإثراء، يمكنك مراجعة نتائج الإثراء.

1. انتقل إلى **بيانات** > **إثراء**. 
1. حدد الإثراء الذي تريد معلومات عنه.

تظهر عمليات الإثراء معلومات أساسية مثل عدد ملفات التعريف التي تم إثراؤها، وإصدار أولي لكيان الإثراء الذي تم إنشاؤه، وعدد ملفات التعريف التي تم إثراؤها مع مرور الوقت. يوفر **عدد العملاء الذين تم إثراؤهم بواسطة الحقل**، إن كان متوفرًا، التنقل لأسفل في تغطية كل حقل تم إثراؤه.

:::image type="content" source="media/enrichments-results.png" alt-text="صفحة نتائج عمليات الإثراء.":::

كما تظهر بعض عمليات الإثراء أيضًا معلومات خاصة بنوع الإثراء. راجع وثائق الإثراء ذي الصلة لمزيد من المعلومات.


[!INCLUDE [footer-include](includes/footer-banner.md)]