---
title: تصدير بيانات Customer Insights إلى Azure Synapse Analytics
description: تعرف على كيفية تكوين الاتصال بـ Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 772fe0978362ccd829077a8133e2a3e74043f3f8
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741487"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>تصدير البيانات إلى Azure Synapse Analytics (إصدار أولي)

Azure Synapse iهو خدمة تحليلات تعمل على تسريع وقت التحليل المتعمق في مستودعات البيانات وأنظمت البيانات الكبيرة. يمكنك استيعاب بيانات Customer Insights الخاصة بك واستخدامها في [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>المتطلبات الأساسية

يجب تلبية المتطلبات الأساسية التالية لتهيئة الاتصال من Customer Insights إلى Azure Synapse.

> [!NOTE]
> تأكد من تعيين جميع **تعيينات الدور** كما هو موضح.  

## <a name="prerequisites-in-customer-insights"></a>المتطلبات الأساسية في Customer Insights

* يوجد لدى مستخدم حساب Azure Active Directory (AD) دور **المسؤول** في Customer Insights. تعرف على المزيد حول [تعيين أذونات المستخدم](permissions.md#assign-roles-and-permissions).

في Azure: 

- اشتراك Azure نشط.

- إذا كنت تستخدم حساب Azure Data Lake Storage Gen2 جديدًا، يحتاج *كيان الخدمة لـ Customer Insights* إلى أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة**. تعرف على المزيد حول [الاتصال بحساب Azure Data Lake Storage Gen2 مع أساس خدمة Azure لـ Customer Insights](connect-service-principal.md). إن Data Lake Storage Gen2 **يجب** أن يتضمن [مساحة أسماء هرمية](/azure/storage/blobs/data-lake-storage-namespace) قيد التمكين.

- على مجموعة الموارد حيث توجد Azure Synapse workspace، يجب تعيين أذونات **القارئ** لكل من *كيان الخدمة* و *مستخدم Azure AD الذي لديه أذونات المسؤول في Customer Insights*. لمزيد من المعلومات، راجع [تعيين أدوار Azure باستخدام مدخل Azure](/azure/role-based-access-control/role-assignments-portal).

- يحتاج *مستخدم Azure AD الذي لديه أذونات المسؤول في Customer Insights* إلى أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة** على حساب Azure Data Lake Storage Gen2 حيث توجد البيانات وترتبط بـ Azure Synapse workspace. تعلم المزيد حول [استخدام مدخل Azure لتعيين دور Azure للوصول إلى بيانات الكائن الثنائي كبير الحجم والصف](/azure/storage/common/storage-auth-aad-rbac-portal) و[أذونات مساهم بيانات مخزن البيانات الثنائية الكبيرة](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- تحتاج *[الهوية المدارة بمساحة عمل Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* إلى أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة** في حساب Azure Data Lake Storage Gen2 في المكان الذي توجد فيه البيانات وترتبط بمساحة عمل Azure Synapse. تعلم المزيد حول [استخدام مدخل Azure لتعيين دور Azure للوصول إلى بيانات الكائن الثنائي كبير الحجم والصف](/azure/storage/common/storage-auth-aad-rbac-portal) و[أذونات مساهم بيانات مخزن البيانات الثنائية الكبيرة](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- في Azure Synapse workspace، يحتاج *كيان الخدمة لـ Customer Insights* إلى دور **مسؤول Synapse**. لمزيد من المعلومات، راجع [كيفية إعداد عنصر تحكم الوصول لمساحة عمل Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control) الخاصة بك.

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>إعداد الاتصال والتصدير إلى Azure Synapse

### <a name="configure-a-connection"></a>تكوين اتصال

لإنشاء اتصال، يحتاج كل من كيان الخدمة وحساب المستخدم في Customer Insights إلى أذونات **قارئ** في *مجموعة الموارد* التي توجد بها مساحة عمل Synapse Analytics. بالإضافة إلى ذلك، يحتاج كل من كيان الخدمة والمستخدم في مساحة عمل Synapse Analytics إلى أذونات **مسؤول Synapse**. 

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **Add connection (إضافة اتصال)** واختر **Azure Synapse Analytics** أو حدد **Set up (الإعداد)** في الإطار المتجانب **Azure Synapse Analytics** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل الاسم المعروض. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. حدد الاشتراك الذي ترغب في استخدامه في بيانات Customer Insights أو ابحث عنه. بمجرد تحديد اشتراك، يمكنك أيضا تحديد **مساحة العمل** و **حساب مساحة التخزين** و **الحاوية**.

1. حدد **حفظ** لحفظ الاتصال.

### <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لتكوين التصدير من خلال اتصال مشترك، ستحتاج على الأقل إلى الحصول على أذونات **المساهم** في Customer Insights. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء عملية تصدير جديدة، حدد **إضافة تصدير**.

1. في حقل **Connection for export (الاتصال للتصدير)**، اختر اتصالاً من قسم **Azure Synapse Analytics**. إذا لم تشاهد اسم القسم هذا، لن تكون هناك [اتصالات](connections.md) من هذا النوع متوفرة لك.

1. قم بتوفير **اسم العرض** يمكن التعرف عليه لعملية التصدير الخاصة بك و **اسم قاعدة البيانات**.

1. حدد أي الكيانات التي ترغب في تصديرها إلى Azure Synapse Analytics.
   > [!NOTE]
   > لا يتم دعم مصادر البيانات المستندة إلى [مجلد ‏‫نموذج البيانات العامة](connect-common-data-model.md).

2. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand).

للاستعلام عن البيانات التي تم تصديرها إلى Synapse Analytics، تحتاج إلى وصول **‏‫قارئ بيانات التخزين كبيرة الحجم‬** إلى التخزين الوجهة في مساحة عمل عمليات التصدير. 

### <a name="update-an-export"></a>تحديث عملية تصدير

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **تحرير** في عملية التصدير التي تريد تحديثها.

   - **أضف** أو **أزل** الكيانات من الاختيار. في حالة إزالة الكيانات من التحديد، لا يتم حذفها من قاعدة بيانات Synapse Analytics. ومع ذلك، لن تؤدي عمليات تحديث البيانات المستقبلية إلى تحديث الكيانات التي تمت إزالتها في قاعدة البيانات هذه.

   - يؤدي **تغيير اسم قاعدة البيانات** إلى إنشاء قاعدة بيانات Synapse Analytics جديدة. لن تتلقى قاعدة البيانات بالاسم الذي تم تكوينه في السابق أي تحديثات في عمليات التحديث المستقبلة.
