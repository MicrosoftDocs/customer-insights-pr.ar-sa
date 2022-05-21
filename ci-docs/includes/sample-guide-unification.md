---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755528"
---
بعد استيعاب البيانات، ابدأ عملية توحيد البيانات لإنشاء ملف تعريف عميل موحد. لمزيد من المعلومات، راجع [توحيد البيانات](../data-unification.md).

### <a name="select-source-fields"></a>تحديد الحقول المصدر

1. بعد استيعاب البيانات، قم بتعيين جهات الاتصال من بيانات التجارة الإلكترونية والولاء إلى أنواع البيانات الشائعة. انتقل إلى **البيانات** > **توحيد**.

1. حدد الكيانات التي تمثل ملف تعريف العميل – **eCommerceContacts** و **loyCustomers**.

   ![توحيد مصادر بيانات التجارة الإلكترونية والولاء.](../media/unify-ecommerce-loyalty.png)

1. حدد **ContactId** كمفتاح أساسي لـ **eCommerceContacts** و **LoyaltyID** كمفتاح أساسي لـ **loyCustomers**.

1. حدد **التالي**. تخطي السجلات المكررة وحدد **التالي**.

### <a name="match-conditions"></a>شروط المطابقة

1. اختر **eCommerceContacts : eCommerce** ككيان أساسي وتضمين جميع السجلات.

1. اختر **loyCustomers : LoyaltyScheme** وقم بتضمين جميع السجلات.

1. إضافة قاعدة:
   - حدد **FullName** لكلٍّ من eCommerceContacts وloyCustomers.
   - حدد **النوع (الهاتف، الاسم، العنوان، ...)** من أجل **الضبط**.
   - عيّن **مستوى الدقة**: **أساسي** و **قيمة**: **عالي**.
   - أدخل **FullName، البريد الإلكتروني** للاسم.

1. أضف شرطًا ثانيًا لعنوان البريد الإلكتروني:
   - حدد **البريد الإلكتروني** لكلٍّ من eCommerceContacts وloyCustomers.
   - اترك الخيار "تسوية" فارغًا.
   - عيّن **مستوى الدقة**: **أساسي** و **قيمة**: **عالي**.

   ![توحيد قاعدة مطابقة للاسم والبريد الإلكتروني.](../media/unify-match-rule.png)

1. حدِّد **تم**.

1. حدد **التالي**.

### <a name="unify-fields"></a>توحيد الحقول

1. أعد تسمية **ContactId** لكيان **loyCustomers** إلى **ContactIdLOYALTY** لتمييزه عن المعرفات الأخرى المستوعبة.

1. حدد **التالي** لمراجعة ثم تحديد **إنشاء ملفات تعريف العملاء**.