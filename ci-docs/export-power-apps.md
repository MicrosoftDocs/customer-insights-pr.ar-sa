---
title: موصل Power Apps
description: الاتصال بـ Power Apps وPower Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: e99d7d4f231eb2ade67f27c9e52c61af3a21b99d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645578"
---
# <a name="microsoft-power-apps-connector-preview"></a>موصل Microsoft Power Apps (معاينة)

إحضار ملفات تعريف العميل الموحدة إلى تطبيقاتك المخصصة باستخدام Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>توصيل Power Apps وDynamics 365 Customer Insights

يُعد Customer Insights بمثابة واحدًا من العديد من [المصادر المتوفرة للبيانات الموجودة في Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

ارجع إلى وثائق Power Apps لمعرفة كيفية [إضافة اتصال بيانات إلى تطبيق](/powerapps/maker/canvas-apps/add-data-connection). يمستحسن أيضًا مراجعة [كيفية استخدام Power Apps تفويض لمعالجة مجموعات البيانات الكبيرة في تطبيقات اللوحة](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>الكيانات المتوفرة

بعد إضافة Customer Insights كاتصال بيانات، يمكنك اختيار الكيانات التالية في Power Apps:

- **العميل**: لاستخدام البيانات من [ملف تعريف العميل الموحد](customer-profiles.md).
- **UnifiedActivity**: لعرض [مخطط زمني النشاط ](activities.md) في التطبيق.
- **ContactProfile**: لعرض جهات اتصال العميل. يتوفر هذا الكيان فقط في بيئات Customer Insights لحسابات الأعمال.

## <a name="limitations"></a>القيود

### <a name="retrievable-entities"></a>الكيانات القابلة للاسترداد

يمكنك فقط استرداد كيانات **العميل**، و **UnifiedActivity**، و **المقاطع**، و **ContactProfile** من خلال موصل Power Apps. يتوفر ContactProfile فقط في مثيل Customer Insights لحسابات الأعمال. تظهر الكيانات الأخرى لأن الموصل الأساسي يدعمها من خلال المشغلات الموجودة في Power Automate.

يمكنك إجراء 100 مكالمة كحد أقصى لكل 60 ثانية. يمكنك استدعاء نقطة نهاية API عدة مرات باستخدام المعلمة $ skip. [تعرف على المزيد حول معلمة $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>تفويض

يعمل التفويض لكيان **العميل** وكيان **UnifiedActivity**. 

- تفويض كيان **العميل** entity: لاستخدام التفويض لهذا الكيان، يجب فهرسة الحقول في [فهرس البحث والتصفية](search-filter-index.md).  
- تفويض لكيان **UnifiedActivity**: يعمل التفويض لهذا الكيان فقط للحقلين **ActivityId** و **CustomerId**.  
- تفويض **ContactProfile**: يعمل تفويض هذا الكيان فقط للحقلين **ContactId** و **CustomerId**. يتوفر ContactProfile فقط في بيئات Customer Insights لحسابات الأعمال.

لمزيد من المعلومات حول التفويض، انتقل إلى [ووظائف وعمليات Power Apps القابلة للتفويض](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>مثال على عنصر تحكم المعرض

يمكنك إضافة ملفات تعريف العملاء إلى [عنصر تحكم المعرض](/powerapps/maker/canvas-apps/add-gallery).

1. قم بإضافة عنصر تحكم **المعرض** إلى تطبيق تقوم بإنشائه.

    > [!div class="mx-imgBorder"]
    > ![إضافة عنصر معرض.](media/connector-powerapps9.png "إضافة عنصر معرض.")

2. قم بتحديد **العميل** كمصدر البيانات للعناصر.

    > [!div class="mx-imgBorder"]
    > ![تحديد مصدر بيانات.](media/choose-datasource-powerapps.png "تحديد مصدر بيانات.")

3. يُمكنك تغيير لوحة البيانات الموجودة على اليمين لتحديد أي حقول كيان العميل الذي سوف يتم عرضه في المعرض.

4. إذا كنت ترغب في إظهار أي حقل من العميل المُحدد في المعرض، فقم بملء خاصية **النص** للتسمية باستخدام **{Name_of_the_gallery}.محدد.{property_name}**  
    - على سبيل المثال: _Gallery1.Selected.address1_city_

5. لعرض المخطط الزمني الموحد لعميل، قم بإضافة عنصر معرض، وإضافة خاصية **العناصر** باستخدام **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - على سبيل المثال: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
