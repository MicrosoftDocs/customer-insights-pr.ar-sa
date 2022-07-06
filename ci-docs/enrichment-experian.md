---
title: إثراء ملفات تعريف العملاء بخصائص سكانية من Experian (معاينة)
description: معلومات عامة عن إثراء Experian التابع لجهة خارجية.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: a30e98b06ed07590ab95cae1d8db8023e49ff7f9
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053005"
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

1. راجع [خصوصية البيانات والامتثال](#data-privacy-and-compliance) وقدم الموافقة عليها بتحديد **أوافق**.

1. حدد **التحقق** للتحقق من صحة التكوين ثم حدد **حفظ** .

### <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عندما تقوم بتمكين Dynamics 365 Customer Insights لنقل البيانات إلى Experian، يمكنك السماح بنقل البيانات خارج حدود التوافق لـ Dynamics 365 Customer Insights، بما في ذلك البيانات التي قد تكون حساسة مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات في الإرشادات التي تقدمها، ولكنك مسؤول عن ضمان وفاء Experian بأية خصوصية أو واجبات أمنية قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.

## <a name="configure-the-enrichment"></a>تكوين الإثراء

1. انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.

1. حدد **إثراء بياناتي** على **البيانات السكانية** من الإطار المتجانب Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="الإطار المتجانب Experian في صفحة النظرة العامة على الإثراء. ":::

1. راجع النظرة العامة، ثم حدد **التالي**.

1. حدد الاتصال. اتصل بمسؤول إذا لم يكن أحدهم متوفرًا.

1. حدد **التالي**.

1. حدد **مجموعة بيانات العميل** واختر ملف التعريف أو الشريحة التي ترغب في إثرائها بواسطة البيانات السكانية من Experian. يقوم كيان *العميل* بإثراء جميع ملفات تعريف عملائك في حين تثري الشريحة فقط ملفات تعريف العملاء الموجودة في تلك الشريحة.

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
