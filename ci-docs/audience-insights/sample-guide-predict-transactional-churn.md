---
title: دليل نموذج التنبؤ بخسارة المعاملة
description: استخدم هذا النموذج للتعرف على النموذج الجاهز للتنبؤ بخسارة المعاملة‬.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306104"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a>دليل نموذج التنبؤ بخسارة المعاملة (معاينة)

سيرشدك هذا الدليل عبر مثال شامل للتنبؤ بخسارة المعاملة في Customer Insights باستخدام البيانات المتوفرة أدناه. جميع البيانات المستخدمة في هذا الدليل ليست بيانات عميل حقيقية وهي جزء من مجموعة بيانات Contoso الموجودة في بيئة *العرض التوضيحي* داخل اشتراك Customer Insights الخاص بك.

## <a name="scenario"></a>السيناريو

Contoso هي شركة تنتج قهوة وماكينات لصنع القهوة عالية الجودة، تقوم ببيعها عبر موقع Contoso Coffee على الويب. هدف هذه الشركة هو التعرّف على العملاء الذين يشترون عادةً منتجاتهم بشكل منتظم، والذين لن يعودوا من العملاء النشطاء خلال الستين يومًا القادمة. من شأن اطّلاع الشركة على الذين **سيتوقفون عن التعامل معها على الأرجح** أن يساعدها على توفير جهودها التسويقية من خلال التركيز على استبقائهم.

## <a name="prerequisites"></a>المتطلبات الأساسية

- على الأقل [أذونات المساهم](permissions.md) في Customer Insights.
- نحن ننصح بتنفيذ الخطوات التالية [في بيئة جديدة](manage-environments.md).

## <a name="task-1---ingest-data"></a>المهمة 1 - استيعاب البيانات

راجع المقالات [حول استيعاب البيانات](data-sources.md) و[استيراد مصادر البيانات باستخدام موصلات Power Query](connect-power-query.md) على وجه التحديد. تفترض المعلومات التالية أنك ملمّ باستيعاب البيانات بشكل عام. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>استيعاب بيانات العملاء من النظام الأساسي للتجارة الإلكترونية

1. أنشئ مصدر بيانات باسم **التجارة الإلكترونية**، وحدد خيار الاستيراد، ثم حدد الموصل **النص/CSV**.

1. أدخل عنوان URL لجهات اتصال التجارة الإلكترونية https://aka.ms/ciadclasscontacts.

1. أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.

1. حدّث نوع البيانات للأعمدة المدرجة أدناه:

   - **DateOfBirth**: التاريخ
   - **CreatedOn**: التاريخ/الوقت/المنطقة

   [!div class="mx-imgBorder"]
   ![تحويل DoB إلى تاريخ](media/ecommerce-dob-date.PNG "تحويل تاريخ الولادة إلى تاريخ")

1. في حقل **الاسم‏‎** في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام** إلى **eCommerceContacts**

1. احفظ مصدر البيانات.

### <a name="ingest-online-purchase-data"></a>استيعاب بيانات شراء عبر الإنترنت

1. أضف مجموعة بيانات أخرى إلى مصدر البيانات **التجارة الإلكترونية**. اختر الموصل **النص/CSV** مرة أخرى.

1. أدخل عنوان URL لبيانات **المشتريات عبر الإنترنت** https://aka.ms/ciadclassonline.

1. أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.

1. حدّث نوع البيانات للأعمدة المدرجة أدناه:

   - **PurchasedOn**: التاريخ/الوقت
   - **TotalPrice**: العملة
   
1. في حقل **الاسم** في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام‏‎** إلى **eCommercePurchases**.

1. احفظ مصدر البيانات.

### <a name="ingest-customer-data-from-loyalty-schema"></a>استيعاب بيانات العملاء من مخطط الولاء

1. أنشئ مصدر بيانات باسم **LoyaltyScheme**، وحدد خيار الاستيراد، ثم حدد الموصل **النص/CSV**.

1. أدخل عنوان URL لجهات اتصال التجارة الإلكترونية https://aka.ms/ciadclasscustomerloyalty.

1. أثناء تحرير البيانات، حدد **تحويل**، ثم حدد **استخدام الصف الأول كرؤوس**.

1. حدّث نوع البيانات للأعمدة المدرجة أدناه:

   - **DateOfBirth**: التاريخ
   - **RewardsPoints**: عدد صحيح
   - **CreatedOn**: التاريخ/الوقت

1. في حقل **الاسم** في الجزء الأيمن، أعد تسمية مصدر البيانات من **استعلام‏‎** إلى **loyCustomers**.

1. احفظ مصدر البيانات.


## <a name="task-2---data-unification"></a>المهمة 2 - توحيد البيانات

بعد استيعاب البيانات، نبدأ الآن عملية **التعيين، المطابقة، الدمج** لإنشاء ملف تعريف عميل موحد. لمزيد من المعلومات، راجع [توحيد البيانات](data-unification.md).

### <a name="map"></a>المخطط

1. بعد استيعاب البيانات، قم بتعيين جهات الاتصال من بيانات التجارة الإلكترونية والولاء إلى أنواع البيانات الشائعة. انتقل إلى **البيانات** > **توحيد** > **تعيين**.

1. حدد الكيانات التي تمثل ملف تعريف العميل – **eCommerceContacts** و **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="توحيد مصادر بيانات التجارة الإلكترونية والولاء.":::

1. حدد **ContactId** كمفتاح أساسي لـ **eCommerceContacts** و **LoyaltyID** كمفتاح أساسي لـ **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="توحيد LoyaltyId كمفتاح أساسي.":::

### <a name="match"></a>مطابقة

1. انتقل إلى علامة التبويب **مطابقة** وحدد **تعيين الأمر**.

1. في القائمة المنسدلة **الرئيسية**، اختر **eCommerceContacts : eCommerce** باعتباره المصدر الرئيسي وقم بتضمين جميع السجلات.

1. في القائمة المنسدلة **الكيان 2**، اختر **loyCustomers : LoyaltyScheme** وقم بتضمين جميع السجلات.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="توحيد مطابقة التجارة الإلكترونية والولاء.":::

1. حدد **إنشاء قاعدة جديدة**

1. أضف الشرط الأول باستخدام FullName.

   * بالنسبة إلى eCommerceContacts، حدد **FullName** في القائمة المنسدلة.
   * بالنسبة إلى loyCustomers، حدد **FullName** في القائمة المنسدلة.
   * حدد القائمة المنسدلة **تسوية**، واختر **النوع (الهاتف والاسم والعنوان و...)**.
   * عيّن **مستوى الدقة**: **أساسي** و **قيمة**: **عالي**.

1. أدخل الاسم **FullName, Email** للقاعدة الجديدة.

   * أضف شرطًا ثانيًا لعنوان البريد الإلكتروني من خلال تحديد **إضافة شرط**
   * بالنسبة للكيان eCommerceContacts، اختر **البريد الإلكتروني** في القائمة المنسدلة.
   * بالنسبة للكيان loyCustomers، اختر **البريد الإلكتروني** في القائمة المنسدلة. 
   * اترك الخيار "تسوية" فارغًا. 
   * عيّن **مستوى الدقة**: **أساسي** و **قيمة**: **عالي**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="توحيد قاعدة مطابقة للاسم والبريد الإلكتروني.":::

7. حدد **حفظ** و **تشغيل**.

### <a name="merge"></a>‏‏دمج

1. انقر فوق علامة التبويب **دمج**.

1. على **ContactId** للكيان **loyCustomers** ، قم بتغيير الاسم المعروض إلى **ContactIdLOYALTY** لتمييزه عن المعرفات الأخرى التي تم استيعابها.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="إعادة تسمية contactid من معرف الولاء.":::

1. حدد **حفظ** و **تشغيل** لبدء عملية الدمج.



## <a name="task-3---configure-transaction-churn-prediction"></a>المهمة 3 - تكوين التنبؤ بخسارة المعاملة‬

من خلال وضع ملفات تعريف العملاء الموحدة، يمكننا الآن تشغيل التنبؤ بخسارة الاشتراك. للحصول على خطوات تفصيلية، راجع المقالة [التنبؤ بخسارة الاشتراك (معاينة)](predict-subscription-churn.md). 

1. انتقل إلى **الذكاء** > **اكتشاف** وحدد لاستخدام **نموذج خسارة العملاء**.

1. حدد الخيار **تعاملي‬‬** وحدد **الشروع في العمل** .

1. أدخل الاسم **OOB التنبؤ بخسارة معاملة التجارة الإلكترونية OOB‬‬** للنموذج والاسم **OOBeCommerceChurnPrediction** لكيان الإخراج.

1. قم بتعريف شرطين لنموذج الخسارة:

   * **إطار التنبؤ**: **60 يومًا على الأقل**. يحدد هذا الاعداد إلى أي مدى في المستقبل نرغب في التنبؤ بخسارة العملاء؟

   * **تعريف الخسارة**: **60 يومًا على الأقل**. المدة من دون إجراء أي عملية شراء والتي يعتبر بعدها أن الشركة خسرت العميل.

     :::image type="content" source="media/model-levers.PNG" alt-text="حدد نموذج إطار التنبؤ وتعريف الخسارة.":::

1. حدد **محفوظات الشراء (مطلوبة)** وحدد **إضافة بيانات** لمحفوظات الشراء.

1. أضف الكيان **eCommercePurchases : eCommerce** وعيّن الحقل من التجارة الإلكترونية إلى الحقول المناظرة التي يطلبها النموذج.

1. انضم إلى الكيان **eCommercePurchases : eCommerce** مع **eCommerceContacts : eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="الانضمام إلى كيانات التجارة الإلكترونية.":::

1. حدد **التالي** لتعيين جدول النماذج.

   يحتاج النموذج إلى التدريب بشكل منتظم للتعرف على الأنماط الجديدة عند وجود بيانات جديدة تم استيعابها. لهذا المثال، حدد **شهري**.

1. بعد مراجعة كافة التفاصيل ، حدد **حفظ وتشغيل**.

## <a name="task-4---review-model-results-and-explanations"></a>المهمة 4 - مراجعة نتائج وتفسيرات النماذج

دع النموذج يكمل تدريب وتسجيل نقاط البيانات. يمكنك الآن مراجعة تفسيرات نموذج خسارة بالاشتراك. لمزيد من المعلومات، راجع [مراجعة حاله ونتائج التنبؤ](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>المهمة 5 - إنشاء شريحة من العملاء مخاطر خسارتهم عالية

يؤدي تشغيل نموذج الإنتاج إلى إنشاء كيان جديد يمكنك رؤيته في **البيانات** > **الكيانات**.   

يمكنك إنشاء شريحة جديدة استنادًا إلى الكيان الذي تم إنشاؤه بواسطة النموذج.

1.  انتقل إلى **الشرائح**. حدد **جديد** واختر **إنشاء من** > **الذكاء**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="إنشاء شريحة بواسطة إخراج النموذج.":::

1. حدد نقطة النهاية **OOBSubscriptionChurnPrediction** وحدد الشريحة: 
   - الحقل: ChurnScore
   - عامل التشغيل: أكبر من
   - القيمة: 0.6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="إعداد شريحة خسارة الاشتراك.":::

لديك الآن شريحة يتم تحديثها بشكل ديناميكي مما يحدد العملاء الذين تبدو مخاطر خسارتهم عالية‬ لعمل الاشتراك هذا.

لمزيد من المعلومات، راجع [إنشاء شرائح وإدارتها](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]