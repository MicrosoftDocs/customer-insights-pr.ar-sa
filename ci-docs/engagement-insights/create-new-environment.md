---
title: إنشاء بيئة جديدة
description: الغرض من البيئة وكيفية إنشاء بيئة جديدة.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648101"
---
# <a name="create-a-new-environment"></a>إنشاء بيئة جديدة 

## <a name="overview"></a>نظرة عامة‬

البيئة هي مساحة تقوم فيها بإدارة مساحات العمل والاتصالات الخاصة بك. تعتمد كيفية استخدام البيئات على مؤسستك حالة الاستخدام الخاصة بك. على سبيل المثال، يمكنك إنشاء:

- بيئة واحدة.
- بيئات منفصلة للاختبار والإنتاج.
- بيئات منفصلة لفرق أو أقسام معينة في مؤسستك تحتوي على أحداث ذات صلة لكل الجمهور.
- بيئات منفصلة للفروع العالمية المختلفة في شركتك.
- عمليات توصيل إمكانية رؤى الجمهور Customer Insights.

## <a name="create-a-new-environment"></a>إنشاء بيئة جديدة

1. على الجانب الأيمن من الشعار الرئيسي، حدد منتقي البيئة، ثم **+جديد**.

   :::image type="content" source="media/environment-picker.png" alt-text="تحديد منتقي البيئة.":::

1. في جزء **الإعداد**، اكتب **اسم البيئة**.

1. اختر **نوع** الحساب، بناء على نوع الخطة.

1. اختر **المنطقة** وحدد **التالي**. 

1. اكتب **اسم مساحة العمل**، والتي تمكنك من جمع البيانات لموقع أو تطبيقات معينة. لمزيد من المعلومات، راجع [إنشاء مساحة عمل](create-workspace.md).

1. اختر **نوع مساحة العمل** (الويب أو الهاتف المحمول) الذي تريد إنشاؤه. 

1. حدد **إظهار الإعدادات المتقدمة** لتمكين هذه الإعدادات الاختيارية أو تعطيلها:

   - قم بتبديل **غير معروف إلى معروف** إلى "ممكّن" لربط أحداث الويب بالمستخدمين الذين تمت مصادقتهم مسبقًا. لمزيد من المعلومات، راجع [التعرف على أحداث الويب من الزائرين الذين تمت مصادقتهم مسبقًا](unknown-to-known.md)
   - قم بتبديل **تصفية حركة مرور الروبوت** إلى "ممكّن" لإزالة حركة البيانات على الويب بواسطة الروبوتات في مساحة العمل هذه. 

1. حدد **مكتمل** عند الانتهاء. 

1. قم بتثبيت قصاصة برمجية لبدء تلقي البيانات، ثم حدد **إنهاء** لإنشاء مساحة العمل. لمزيد من المعلومات، راجع [نظرة عامة على موارد المطورين](developer-resources.md).

> [!NOTE]
> يمكنك الآن إضافة أعضاء وتعيين مستوى الإذن لهم من قائمة **الدور**. لمزيد من المعلومات، راجع [الأدوار والأذونات](user-roles.md). 

لمزيد من المعلومات، راجع [إدارة مساحات العمل والبيئات](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>التعامل مع بيئتك الجديدة

- [إنشاء مساحة عمل](../engagement-insights/create-workspace.md) وإضافة الأعضاء.
- [أضف الرمز إلى موقع الويب](../engagement-insights/instrument-website.md) أو [تطبيق الأجهزة المحمولة](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- اعرض [تقريرًا في الوقت الحقيقي](../engagement-insights/view-reports.md) أو أنشئ [تقارير مخصصة](../engagement-insights/custom-reports.md).
- [إنشاء أحداث مكررة](../engagement-insights/refined-events.md) للتصدير.
- [تصدير البيانات](../engagement-insights/export-events.md) إلى Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
