---
title: موصل Power Apps
description: الاتصال بـ Power Apps وPower Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031733"
---
# <a name="microsoft-power-apps-connector-preview"></a>موصل Microsoft Power Apps (معاينة)

إحضار ملفات تعريف العميل الموحدة إلى تطبيقاتك المخصصة باستخدام Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>توصيل Power Apps وDynamics 365 Customer Insights

يُعد Customer Insights بمثابة واحدًا من العديد من [المصادر المتوفرة للبيانات الموجودة في Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

ارجع إلى وثائق Power Apps لمعرفة كيفية [إضافة اتصال بيانات إلى تطبيق](/powerapps/maker/canvas-apps/add-data-connection). يمستحسن أيضًا مراجعة [كيفية استخدام Power Apps تفويض لمعالجة مجموعات البيانات الكبيرة في تطبيقات اللوحة](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>الكيانات المتوفرة

بعد إضافة Customer Insights كاتصال بيانات، يمكنك اختيار الكيانات التالية في Power Apps:

- العميل: لاستخدام بيانات من [ملف تعريف العميل الموحد](customer-profiles.md).
- UnifiedActivity: لعرض [المخطط الزمني للنشاط](activities.md) على التطبيق.

## <a name="limitations"></a>القيود

### <a name="retrievable-entities"></a>الكيانات القابلة للاسترداد

يمكنك فقط استرداد كيانات **العميل** و **UnifiedActivity** و **الشرائح** من خلال موصل Power Apps. تظهر الكيانات الأخرى لأن الموصل الأساسي يدعمها من خلال المشغلات الموجودة في Power Automate.  

### <a name="delegation"></a>تفويض

يعمل التفويض لكيان العميل وكيان UnifiedActivity. 

- تفويض كيان **العميل** entity: لاستخدام التفويض لهذا الكيان، يجب فهرسة الحقول في [فهرس البحث والتصفية](search-filter-index.md).  

- تفويض لكيان **UnifiedActivity**: يعمل التفويض لهذا الكيان فقط للحقلين **ActivityId** و **CustomerId**.  

- لمزيد من المعلومات حول التفويض، راجع [الوظائف والعمليات القابلة للتفويض في Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>مثال على عنصر تحكم المعرض

على سبيل المثال، يمكنك إضافة ملفات تعريف العملاء إلى [عنصر تحكم المعرض](/powerapps/maker/canvas-apps/add-gallery).

1. قم بإضافة عنصر تحكم **المعرض** إلى تطبيق تقوم بإنشاءه.

> [!div class="mx-imgBorder"]
> ![إضافة عنصر معرض.](media/connector-powerapps9.png "إضافة عنصر معرض")

1. قم بتحديد **العميل** كمصدر البيانات للعناصر.

    > [!div class="mx-imgBorder"]
    > ![تحديد مصدر بيانات.](media/choose-datasource-powerapps.png "تحديد مصدر بيانات")

1. يُمكنك تغيير لوحة البيانات الموجودة على اليمين لتحديد أي حقول كيان العميل الذي سوف يتم عرضه في المعرض.

1. إذا كنت ترغب في إظهار أي حقل من العميل المُحدد في المعرض، فقم بملء خاصية النص للتسمية:  **{Name_of_the_gallery}.{property_name}** مُحدد

    مثال: Gallery1.Selected.address1_city

1. لعرض المخطط الزمني الموحد لعميل، قم بإضافة عنصر معرض، وإضافة خاصية العناصر: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    مثال: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]