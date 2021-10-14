---
title: إدارة مساحات العمل والبيئات
description: كيفية إنشاء مساحة عمل وبيئات وإعادة تسميتها وحذفها.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 09/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: a5b48db5ae23ea65bf608d67348d493bfdc7678f
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486019"
---
# <a name="manage-environments-and-workspaces"></a>إدارة البيئات ومساحات العمل

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>نظرة عامة‬

مساحة العمل هي مساحة لتخزين الأحداث والتقارير وإدارتها. وهو المكان الذي يمكنك فيه عرض نشاط المستخدم في الوقت الحقيقي. وعند إنشاء مساحة عمل، يتم تحديد نوع البيانات التي يتم إرسالها إلى مساحة العمل. حاليا، يتم دعم بيانات الويب وتطبيقات الجوال.

البيئة هي مساحة تقوم فيها بإدارة مساحات العمل والاتصالات الخاصة بك. تعتمد كيفية استخدام البيئات على مؤسستك حالة الاستخدام الخاصة بك. على سبيل المثال، يمكنك إنشاء:

-   بيئة واحدة.
-   بيئات منفصلة للاختبار والإنتاج.
-   بيئات منفصلة لفرق أو أقسام معينة في مؤسستك تحتوي على أحداث ذات صلة لكل الجمهور.
-   بيئات منفصلة للفروع العالمية المختلفة في شركتك.
-   عمليات توصيل إمكانية رؤى الجمهور Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>اختيار بيئة وإنشاء مساحة عمل 

يجب أن يكون كل مساحة عمل في بيئة. يمكنك تحديد بيئة موجودة مسبقا أو إنشاء بيئة جديدة عند إنشاء مساحة عمل. بعد ذلك، يمكنك اختيار إضافة أعضاء مساحة عمل وبدء تجميع البيانات.

**لإنشاء مساحة العمل الأولى**

1. في رؤى الارتباط، قم بتحديد **جديد** من مفتاح تبديل مساحة العمل. 

   :::image type="content" source="media/New-workspace.png" alt-text="منتقي مساحة عمل صفحة Customer Insights.":::

1. اختر بيئة من القائمة أو حدد **إنشاء بيئة جديدة**.

1. أدخل اسما في **اسم مساحة العمل**. 

1. حدد نوع البيئة التي ترغب في إنشائها، اعتمادا على ما إذا كنت ترغب في قياس ما يحدث على موقع ويب أو في تطبيق محمول. 

1. يمكنك إضافة أعضاء وتعيين مستوى الأذونات لهم من قائمة **الدور**. ثم حدد **إنهاء** لإنشاء مساحة العمل أو **التالي** لتثبيت التعليمة البرمجية. 

1. قم بتثبيت قصاصة برمجية لبدء تلقي البيانات ثم قم بتحديد **تم**. 

## <a name="manage-a-workspace"></a>إدارة مساحة عمل

يمكنك الاحتفاظ بعدة مساحة عمل بشكل متزامن في بيئة ما. يحدد [دورك](user-roles.md) كيفية العمل بها. 

 - يجب أن تكون مسؤول بيئة أو مسؤول مساحة عمل لإدارة مساحة العمل.
 - كمسؤول في مساحة العمل، يمكنك إعادة تسمية مساحة العمل الموجودة أو حذفها. 

### <a name="edit-a-workspace-name"></a>تعديل اسم مساحة العمل

1. انتقل إلى **الإدارة** > **مساحة العمل** وحدد **الإعدادات**.

1. **اسم مساحة العمل**، أدخل اسمًا جديدًا. 

1. حدد **حفظ** لتطبيق التغييرات التي أجريتها.

### <a name="delete-a-workspace"></a>حذف مساحة عمل

سيؤدي حذف مساحة العمل إلى إزالة كافة محتوياتها وبياناتها وإعداداتها وأذوناتها بشكل دائم. لا يمكن التراجع عن هذا الإجراء.

1. انتقل إلى **الإدارة** > **مساحة العمل** وحدد **الإعدادات**.

1. حدد **حذف مساحة العمل**. 

1. في مربع الحوار **حذف مساحة العمل**، أدخل **تأكيد الحذف**. 

1. حدد **حذف** لحذف مساحة العمل نهائيًا.

### <a name="manage-workspace-members"></a>إدارة أعضاء مساحة العمل

1. انتقل إلى **الإدارة** > **مساحة العمل** وحدد **الأعضاء**.

1. حدد **إضافة أعضاء**  لإعطاء حق الوصول و[تعيين الأدوار](user-roles.md). لا يتوفر حاليا إلا **مسؤول مساحة العمل** فقط.

1. حدد **إضافة أعضاء** إضافتهم إلى مساحة العمل الخاصة بك.

## <a name="manage-an-environment"></a>إدارة بيئة

كمسؤول للبيئة، يمكنك الوصول إلى بيئة من جزء التنقل الأيسر. يمكنك تكوين إعدادات البيئة ومسؤولي البيئة الآخرين ومساحات العمل. حدد علامات التبويب للتنقل بين منطقتين مختلفتين في مركز الإدارة.

:::image type="content" source="media/New-environment.png" alt-text="مركز إدارة البيئة.":::

### <a name="create-an-environment"></a>إنشاء بيئة

1. في منتقي مساحة عمل، حدد **+جديد**.

1. في تجربة إرشادية، افتح القائمة المنسدلة **البيئة** وحدد **إنشاء بيئة جديدة**. 

1. توفير **اسم البيئة**.

   :::image type="content" source="media/create-environment.png" alt-text="خطوة في تجربة إرشادية لتحديد تفاصيل البيئة.":::

1. اختر **المنطقة** وحدد **التالي**. 

1. قم بتوفير اسم مساحة عمل واختر نوع مساحة العمل التي ترغب في إنشائها. 

1.  بشكل اختياري، قم بإضافة الأعضاء ونسخ قصاصة التعليمات البرمجية لإكمال عملية الإنشاء.

### <a name="rename-an-environment"></a>إعادة تسمية البيئة

1. انتقل إلى **الإدارة** > **البيئة** وحدد **الإعدادات**.

1. قم بتحديث **اسم البيئة** وحدد **حفظ** لتطبيق التغييرات.

### <a name="manage-environment-members"></a>إدارة أعضاء بيئة

1. انتقل إلى **الإدارة** > **البيئة** وحدد **الأعضاء**.

1. حدد **إضافة أعضاء**  لتحديث الأعضاء و[تعيين الأدوار](user-roles.md). لا يتوفر حاليا إلا **إدارة البيئة** فقط.

1. حدد **إضافة أعضاء** لإضافتهم إلى بيئتك.

### <a name="delete-an-environment"></a>حذف بيئة

يمكن لمسؤولي البيئة حذف البيئات. قبل أن تتمكن من حذف بيئة، يجب إزالة كافة مساحة العمل تحتها.

1. انتقل إلى **الإدارة** > **البيئة** وحدد **الإعدادات**.

1. حدد **حذف بيئة**. 

1. في مربع الحوار **حذف مساحة العمل**، أدخل **تأكيد الحذف**. 

1. حدد **حذف** لحذف البيئة نهائيًا.

## <a name="manage-connections"></a>إدارة الاتصالات

يتيح لك إنشاء الجمهور لرؤى العملاء رؤية التقارير برؤى مشاركة استنادا إلى ملفات تعريف العملاء الموحدة. 

لمزيد من المعلومات، راجع [إنشاء ارتباط بين رؤى الجمهور ورؤى المشاركة](integrate-audience-insights-engagement-insights.md)

## <a name="manage-personal-data"></a>إدارة البيانات الشخصية

لحماية البيانات الشخصية للعميل، يمكنك حذف بيانات تعريف المستخدم النهائي أو تصديرها.

لمزيد من المعلومات، راجع [حذف بيانات الأحداث التي تحتوي على معلومات شخصية وتصديرها](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]