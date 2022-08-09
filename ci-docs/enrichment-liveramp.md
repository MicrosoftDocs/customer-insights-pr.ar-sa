---
title: ‏‫إثراء ملفات تعريف العملاء ببيانات الهوية من LiveRamp (إصدار أولي)‬
description: إثراء ملفات تعريف العملاء ببيانات LiveRamp.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196332"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>‏‫إثراء ملفات تعريف العملاء ببيانات الهوية من LiveRamp (إصدار أولي)‬

يوفر LiveRamp دقة هوية قطعية في وضع عدم الاتصال ودمج بيانات العميل. يمكنك تعيين المعرفات الشخصية في بيانات العميل على الرسم البياني للهوية AbiliTec وتلقي معرفات AbiliTec. يمكنك بعد ذلك استخدام هذه المعرفات لتحسين توحيد بيانات العملاء.

## <a name="supported-countriesregions"></a>البلدان/المناطق المدعومة

نحن ندعم حاليًا ملفات تعريف العملاء المثرية ببيانات LiveRamp في الولايات المتحدة فقط.

## <a name="prerequisites"></a>المتطلبات

- اشتراك نشط في LiveRamp. للحصول على اشتراك، تواصل مع فريق حساب LiveRamp الخاص بك أو [dynamics@liveramp.com](mailto:dynamics@liveramp.com) لمزيد من المعلومات.

- اشتراك AbiliTec نشط مع معرف العميل وسر الوصول إلى واجهة برمجة التطبيقات. لمزيد من المعلومات، راجع [مركز مطوري AbiliTec API](https://developers.liveramp.com/abilitec-api/).

- [تكوين](#configure-the-connection-for-liveramp) [اتصال](connections.md) LiveRamp بواسطة مسؤول.

## <a name="configure-the-connection-for-liveramp"></a>تكوين الاتصال لـ LiveRamp

يجب أن تكون [مسؤولاً](permissions.md#admin) في Customer Insights وأن يكون لديك سر ومعرف عميل LiveRamp نشط.

1. حدد **إضافة اتصال** عند تكوين الإثراء أو انتقل إلى **المسؤول‏‎** > **الاتصالات‏‎** وحدد **الإعداد‏‎** على الإطار المتجانب لـ LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="جزء التكوين لإعداد الاتصال لخدمة LiveRamp Abili. ":::

1. أدخل اسمًا للاتصال وسر ومعرف عميل LiveRamp صالحين.

1. راجع [خصوصية البيانات والامتثال](#data-privacy-and-compliance) وقدم الموافقة عليها بتحديد **أوافق**.

1. حدد **التحقق** للتحقق من صحة التكوين ثم حدد **حفظ** .

### <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى LiveRamp، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم Microsoft بنقل هذه البيانات بناءً على التعليمات الخاصة بك، ولكنك مسؤول عن ضمان أن يفي LiveRamp بأي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.

## <a name="configure-the-enrichment"></a>تكوين الإثراء

1. انتقل إلى **البيانات** > **الإثراء** وحدد علامة التبويب **اكتشاف**.

1. حدد **إثراء بياناتي** على **الهوية** من الإطار المتجانب لـ LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="الإطار المتجانب الهوية في صفحة النظرة العامة على الإثراء.":::

1. راجع النظرة العامة، ثم حدد **التالي**.

1. حدد الاتصال. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. حدد **التالي**.

1. حدد **مجموعة بيانات العميل** واختر ملف التعريف أو المقطع التي ترغب في إثرائها بواسطة بيانات الهوية من LiveRamp. يقوم كيان *العميل* بإثراء جميع ملفات تعريف عملائك في حين تثري المقطع فقط ملفات تعريف العملاء الموجودة في تلك المقطع.

1. حدد أنواع الحقول من ملفات التعريف الموحدة التي يجب استخدامها لمطابقة بيانات الهوية من LiveRamp. يلزم وجود حقل واحد على الأقل من الحقول **الاسم والعنوان** أو **البريد الإلكتروني** أو **الهاتف**. للحصول على دقة تطابق أعلى، أضف المزيد من الحقول. حدد **التالي**.

1. عيّن حقولك إلى بيانات الهوية من LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="خيارات تعيين البيانات لإثراء LiveRamp.":::

1. حدد **التالي** لإكمال تعيين الحقل.

1. قم بتوفير **اسم** للإثراء و **اسم كيان الإخراج**.

1. حدد **حفظ الإثراء** بعد مراجعة اختياراتك.

1. حدد **تشغيل** لبدء عملية المعالجة، أو حدد إغلاق للعودة إلى صفحة **عمليات الإثراء**.

## <a name="view-enrichment-results"></a>عرض نتائج إثراء البيانات

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

يوفر الخيار **عدد العملاء الذين تم إثراؤهم بواسطة الحقل** التنقل لأسفل في تغطية كل حقل تم إثراؤه.

## <a name="next-steps"></a>الخطوات التالية

قم بالبناء أعلى بيانات العملاء التي تم إثرائها. استخدم معرفات AbiliTec لدمج ملفات تعريف العملاء في طريقة عرض تستند إلى الشخص.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
