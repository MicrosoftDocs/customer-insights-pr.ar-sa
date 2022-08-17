---
title: إثراء ملفات تعريف العملاء بخصائص سكانية من Experian (معاينة)
description: معلومات عامة عن إثراء Experian التابع لجهة خارجية.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fccb37cde3f05a70009c18b6c52db01a5ede094d
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237980"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>إثراء ملفات تعريف العملاء بخصائص سكانية من Experian (معاينة)

Experian هي شركة رائدة على مستوى العالم في مجال إعداد تقارير ائتمانات العملاء والأعمال وخدمات التسويق. من خلال خدمات إثراء البيانات في Experian يمكن بناء فهم أكبر للعملاء من خلال إثراء ملفات تعريف العملاء بالبيانات السكانية مثل حجم البنية الأساسية والدخل وأية معلومات أخرى.

## <a name="supported-countriesregions"></a>البلدان/المناطق المدعومة

ونحن ندعم حاليا إثراء ملفات تعريف العملاء في الولايات المتحدة فقط.

## <a name="prerequisites"></a>المتطلبات

- اشتراك نشط في Experian. للحصول على اشتراك، [اتصل بـ Experian](https://www.experian.com/marketing-services/contact) مباشرةً. [تعرف على المزيد حول إثراء البيانات في Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- [تكوين](#configure-the-connection-for-experian) [اتصال](connections.md) Experian بواسطة مسؤول.

- ستحتاج إلى معرف المستخدم في Experian بالإضافة إلى معرف الطرف ورقم النموذج لحساب النقل الآمن (ST) أنشأه Experian لك.

## <a name="configure-the-connection-for-experian"></a>تكوين الاتصال لـ Experian

يجب أن تكون [مسؤولاً](permissions.md#admin) في Customer Insights وأن يكون لديك معرف مستخدم ومعرف طرف ورقم النموذج في Experian.

1. حدد **إضافة اتصال** عند تكوين إثراء أو انتقل إلى **المسؤول‏‎** > **الاتصالات‏‎** وحدد **إعداد** على الإطار المتجانب Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="جزء تكوين اتصال Experian.":::

1. أدخل اسمًا للاتصال ومعرف المستخدم ومعرف الطرف ورقم نموذج صالحًا لحساب Experian Secure Transport .

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **التحقق** للتحقق من صحة التكوين ثم حدد **حفظ** .

## <a name="configure-the-enrichment"></a>تكوين الإثراء

1. انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.

1. حدد **إثراء بياناتي** على **البيانات السكانية** من الإطار المتجانب Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="الإطار المتجانب Experian في صفحة النظرة العامة على الإثراء. ":::

1. راجع النظرة العامة، ثم حدد **التالي**.

1. حدد الاتصال. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. حدد **التالي**.

1. حدد **مجموعة بيانات العميل** واختر ملف التعريف أو المقطع التي ترغب في إثرائها بواسطة البيانات السكانية من Experian. يقوم كيان *العميل* بإثراء جميع ملفات تعريف عملائك في حين تثري المقطع فقط ملفات تعريف العملاء الموجودة في تلك المقطع.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="لقطة شاشة عند اختيار مجموعة بيانات العميل.":::

1. حدد أنواع الحقول من ملفات التعريف الموحدة التي يجب استخدامها لمطابقة البيانات السكانية من Experian. واحد على الأقل من حقول **الاسم والعنوان** أو **الهاتف** أو **البريد الإلكتروني** مطلوب للحصول على دقة تطابق أعلى، أضف المزيد من الحقول. حدد **التالي**.

1. عيّن حقولك إلى البيانات السكانية من Experian.

1. حدد **التالي** لإكمال تعيين الحقل.

1. قم بتوفير **اسم** للإثراء و **اسم كيان الإخراج**.

1. حدد **حفظ الإثراء** بعد مراجعة اختياراتك.

1. حدد **تشغيل** لبدء عملية المعالجة، أو حدد إغلاق للعودة إلى صفحة **عمليات الإثراء**.

## <a name="view-enrichment-results"></a>عرض نتائج إثراء البيانات

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

يوفر الخيار **عدد العملاء الذين تم إثراؤهم بواسطة الحقل** التنقل لأسفل في تغطية كل حقل تم إثراؤه.

## <a name="next-steps"></a>الخطوات التالية

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
