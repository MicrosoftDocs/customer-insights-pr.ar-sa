---
title: الاتصال بالجداول في Microsoft Dataverse
description: استيراد البيانات من مخزن البيانات المُدار بواسطة Microsoft Dataverse.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033064"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>الاتصال بالبيانات في مستودع بيانات مُدار في Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

توفر هذه المقالة معلومات حول كيفية اتصال مستخدمي Dataverse بسرعة بكياناتهم التحليلية في حالة المستودع المُدار بواسطة Dataverse. يجب أن تكون مسؤولا في مؤسسة Dataverse للمتابعة والاطلاع على قائمة الكيانات المتوفرة في المخزن المُدار.

## <a name="important-considerations"></a>اعتبارات هامة

قد يتم تخزين البيانات المخزنة في خدمات عبر الإنترنت مثل Azure Data Lake Storage في موقع يختلف عن الموقع حيث تتم معالجة البيانات أو تخزينها في Dynamics 365 Customer Insights. من خلال استيراد البيانات المخزنة في الخدمات عبر الإنترنت، توافق أنت على نقل هذه البيانات وتخزينها بواسطة Dynamics 365 Customer Insights. [اعرف المزيد في مركز توثيق Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>الاتصال بمستودع بيانات مُدار في Dataverse

1. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.

2. حدد **إضافة مصدر بيانات**.

3. حدد **الاتصال بالمستودع المُدار بواسطة Microsoft Dataverse** وحدد **التالي**.

4. أدخل **اسمًا** لمصدر البيانات، وحدد **التالي‏‎**. إرشادات الاسم: 
   - يجب أن يبدأ الاسم بحرف
   - استخدم الأحرف و الأرقام فقط. غير مسموح باستخدام الأحرف الخاصة والمسافات.
   - استخدم ما بين 3 و64 حرفًا.

5. قم بتوفير **عنوان الخادم** الخاص بمؤسسة Dataverse، وحدد **تسجيل الدخول**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="الشاشة في خطوة استيعاب البيانات حيث يمكن للمستخدم أن يُدخل عنوان URL لبيئة Dataverse.":::

6. حدد الجداول التي ترغب في تناولها ككيانات لمعلومات الجمهور من القائمة المتوفرة.    

   > [!NOTE]
   > إذا تم تحديد بعض الجداول بالفعل، فقد يتم استخدامها بواسطة تطبيقات Dynamics 365 أخرى (مثل Dynamics 365 Sales Insights أو Customer Service Insights). لا يمكنك تغيير التحديد. وسوف تتوفر هذه الجداول ككيانات بمجرد إنشاء مصدر البيانات.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="يظهر مربع الحوار قائمة الكيانات في بيئة Dataverse.":::

7. احفظ اختيارك لبدء مزامنة الجداول المحددة من Dataverse. ستعثر على الاتصال المضاف حديثًا في صفحة **مصادر البيانات**. سيتم وضعه في قائمة الانتظار للتحديث وعرض الكيان "عدد" على أنه 0 حتى تتم مزامنة جميع الجداول المحددة.

بإمكان مصدر بيانات واحد فقط من البيئة استخدام مستودع البيانات المُدار نفسه في Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>تحرير مصدر البيانات لمستودع بيانات مُدار في Dataverse

يمكنك تحرير تحديد الكيان فقط بعد إنشاء مصدر البيانات. على سبيل المثال، إذا تمت إضافة كيانات اضافيه إلى Dataverse وكنت تريد استيرادها أيضا.    
للاتصال Dataverse data lake مختلفة، [قم بإنشاء مجموعة جديدة من مصدر البيانات](#connect-to-a-dataverse-managed-lake).

1. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.

2. إلى جانب مصدر البيانات الذي تريد تحديثه، حدد علامة القطع.

3. حدد الخيار **تحرير** من القائمة.

4. حدد كيانات إضافية من قائمة الكيانات المتاحة وحدد **حفظ**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]