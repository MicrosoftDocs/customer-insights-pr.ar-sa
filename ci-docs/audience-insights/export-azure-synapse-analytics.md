---
title: تصدير بيانات Customer Insights إلى Azure Synapse Analytics
description: تعرف على كيفية تهيئة الاتصال بـ Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977361"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>تصدير البيانات إلى Azure Synapse Analytics (معاينة)

Azure Synapse iهو خدمة تحليلات تعمل على تسريع وقت التحليل المتعمق في مستودعات البيانات وأنظمت البيانات الكبيرة. يمكنك استيعاب بيانات Customer Insights الخاصة بك واستخدامها في [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>المتطلبات الأساسية

يجب تلبية المتطلبات الأساسية التالية لتهيئة الاتصال من Customer Insights إلى Azure Synapse.

> [!NOTE]
> تأكد من تعيين جميع **تعيينات الدور** كما هو موضح.  

## <a name="prerequisites-in-customer-insights"></a>المتطلبات الأساسية في Customer Insights

* لديك دور **المسؤول** في معلومات الجمهور. اعرف المزيد حول [تعيين أذونات المستخدم في معلومات الجمهور](permissions.md#assign-roles-and-permissions)

في Azure: 

- اشتراك Azure نشط.

- في حالة استخدام حساب Azure Data Lake Storage Gen2، فإن *مبدأ الخدمة لمعلومات الجمهور* يجتاج إلى إذن **مساهم بيانات مخزن البيانات الثنائية الكبيرة**. اعرف على المزيد حول [الاتصال بحساب Azure Data Lake Storage Gen2 باستخدام مبدأ خدمة Azure لمعلومات الجمهور](connect-service-principal.md). إن Data Lake Storage Gen2 **يجب** أن يتضمن [مساحة أسماء هرمية](/azure/storage/blobs/data-lake-storage-namespace) قيد التمكين.

- في مجموعة الموارد التي توجد بها مساحة عمل Azure Synapse، فإن *مبدأ الخدمة* و *المستخدم لمعلومات الجمهور* يحتاج  تعيين أذونات **قارئ** له على الأقل. لمزيد من المعلومات، راجع [تعيين أدوار Azure باستخدام مدخل Azure](/azure/role-based-access-control/role-assignments-portal).

- يحتاج *المستخدم* إلى أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة** في حساب Azure Data Lake Storage Gen2 في المكان الذي توجد فيه البيانات وترتبط بمساحة عمل Azure Synapse. تعلم المزيد حول [استخدام مدخل Azure لتعيين دور Azure للوصول إلى بيانات الكائن الثنائي كبير الحجم والصف](/azure/storage/common/storage-auth-aad-rbac-portal) و[أذونات مساهم بيانات مخزن البيانات الثنائية الكبيرة](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- تحتاج *[الهوية المدارة بمساحة عمل Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* إلى أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة** في حساب Azure Data Lake Storage Gen2 في المكان الذي توجد فيه البيانات وترتبط بمساحة عمل Azure Synapse. تعلم المزيد حول [استخدام مدخل Azure لتعيين دور Azure للوصول إلى بيانات الكائن الثنائي كبير الحجم والصف](/azure/storage/common/storage-auth-aad-rbac-portal) و[أذونات مساهم بيانات مخزن البيانات الثنائية الكبيرة](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- في مساحة عمل Azure Synapse، يحتاج *مبدأ الخدمة لمعلومات الجمهور* إلى تعيين دور **مسؤول  Synapse**. لمزيد من المعلومات، راجع [كيفية إعداد عنصر تحكم الوصول لمساحة عمل Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control) الخاصة بك.

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>إعداد الاتصال والتصدير إلى Azure Synapse

### <a name="configure-a-connection"></a>تكوين اتصال

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Azure Synapse Analytics** أو حدد **إعداد** في تجانب **Azure Synapse Analytics** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل الاسم المعروض. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. حدد الاشتراك الذي ترغب في استخدامه في بيانات Customer Insights أو ابحث عنه. بمجرد تحديد اشتراك، يمكنك أيضا تحديد **مساحة العمل** و **حساب مساحة التخزين** و **الحاوية**.

1. حدد **حفظ** لحفظ الاتصال.

### <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء عملية تصدير جديدة، حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم **Azure Synapse Analytics**. إذا لم تشاهد اسم القسم هذا، لن تكون هناك [اتصالات](connections.md) من هذا النوع متوفرة لك.

1. قم بتوفير **اسم العرض** يمكن التعرف عليه لعملية التصدير الخاصة بك و **اسم قاعدة البيانات**.

1. حدد الكيانات التي ترغب في تصديرها إلى Azure Synapse Analytics.

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>تحديث عملية تصدير

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **تحرير** في عملية التصدير التي تريد تحديثها.

   - **أضف** أو **أزل** الكيانات من الاختيار. في حالة إزالة الكيانات من التحديد، لا يتم حذفها من قاعدة بيانات Synapse Analytics. ومع ذلك، لن تؤدي عمليات تحديث البيانات المستقبلية إلى تحديث الكيانات التي تمت إزالتها في قاعدة البيانات هذه.

   - يؤدي **تغيير اسم قاعدة البيانات** إلى إنشاء قاعدة بيانات Synapse Analytics جديدة. لن تتلقى قاعدة البيانات بالاسم الذي تم تكوينه في السابق أي تحديثات في عمليات التحديث المستقبلة.