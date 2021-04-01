---
title: الاتصال بالكيانات في مستودع البيانات المُدار في Common Data Service
description: استيراد البيانات من مخزن البيانات المُدار بواسطة Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596943"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>الاتصال بالبيانات في مستودع بيانات مُدار في Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

توفر هذه المقالة معلومات حول كيفيه قيام عملاء Dynamics 365 الموجودين بالاتصال بشكل سريع بالكيانات التحليلية الخاصة بهم في المخزن المُدار بواسطة Common Data Service. يجب أن تكون مسؤولا في مؤسسة Common Data Service للمتابعة والاطلاع على قائمة الكيانات المتوفرة في المخزن المُدار.

## <a name="important-considerations"></a>اعتبارات هامة

قد يتم تخزين البيانات المخزنة في خدمات عبر الإنترنت مثل Azure Data Lake Storage في موقع يختلف عن الموقع حيث تتم معالجة البيانات أو تخزينها في Dynamics 365 Customer Insights. من خلال استيراد البيانات المخزنة في الخدمات عبر الإنترنت، توافق أنت على نقل هذه البيانات وتخزينها بواسطة Dynamics 365 Customer Insights. [اعرف المزيد في مركز توثيق Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>الاتصال بمستودع بيانات مُدار في Common Data Service

1. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.

2. حدد **إضافة مصدر بيانات**.

3. حدد **اتصال بـ Common Data Service** ثم حدد **التالي**.

4. أدخل **اسمًا** لمصدر البيانات، وحدد **التالي‏‎**. إرشادات الاسم: 
   - يجب أن يبدأ الاسم بحرف
   - استخدم الأحرف و الأرقام فقط. غير مسموح باستخدام الأحرف الخاصة والمسافات.
   - استخدم ما بين 3 و64 حرفًا.

5. أدخل **عنوان الخادم** لمؤسستك في Common Data Service، ثم حدد **تسجيل الدخول**.

   > [!div class="mx-imgBorder"]
   > ![مربع حوار لإدخال عنوان الخادم في Common Data Service](media/enter-CDS-org-details.png)

6. حدد الكيانات التي ترغب في استيعابها من القائمة المتوفرة.    

   > [!NOTE]
   > إذا كانت بعض الكيانات محددة، فمن المحتمل أن تكون قيد الاستخدام بواسطة تطبيقات Dynamics 365 أخرى (مثل Dynamics 365 Sales Insights or Customer Service Insights). لا يمكنك تغيير التحديد. ستصبح هذه الكيانات متاحة بمجرد إنشاء مصدر البيانات.

   > [!div class="mx-imgBorder"]
   > ![مربع حوار يعرض قائمة بالكيانات الموجودة في مؤسسة Common Data Service](media/select-analytical-entities.png)

7. احفظ التحديد لبدء مزامنة الكيانات المحددة إلى المستودع المُدار في Common Data Service. ستعثر على الاتصال المضاف حديثًا في صفحة **مصادر البيانات**. سيكون موضوعًا في قائمة انتظار كي يتم تحديثه، ويظهر عدد الكيانات كصفر حتى مزامنة كافة الكيانات.

بإمكان مصدر بيانات واحد فقط من البيئة استخدام مستودع البيانات المُدار نفسه في Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>تحرير مصدر البيانات لمستودع بيانات مُدار في Common Data Service

يمكنك تحرير تحديد الكيان فقط بعد إنشاء مصدر البيانات. على سبيل المثال، إذا تمت إضافة كيانات اضافيه إلى Common Data Service وكنت تريد استيرادها أيضا.    
للاتصال بخدمة Common Data Service أخرى، يمكنك [إنشاء مصدر بيانات جديد](#connect-to-a-common-data-service-managed-lake).

1. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.

2. إلى جانب مصدر البيانات الذي تريد تحديثه، حدد علامة القطع.

3. حدد الخيار **تحرير** من القائمة.

4. حدد كيانات إضافية من قائمة الكيانات المتاحة وحدد **حفظ**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]