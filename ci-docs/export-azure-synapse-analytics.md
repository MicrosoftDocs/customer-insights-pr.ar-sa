---
title: تصدير البيانات إلى Azure Synapse Analytics (إصدار أولي)
description: تعرف على كيفية تكوين الاتصال بـ Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 0e953cfff12df433d033717d58b28c2834468916
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259828"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>تصدير البيانات إلى Azure Synapse Analytics (إصدار أولي)

Azure Synapse iهو خدمة تحليلات تعمل على تسريع وقت التحليل المتعمق في مستودعات البيانات وأنظمت البيانات الكبيرة. يمكنك استيعاب بيانات Customer Insights الخاصة بك واستخدامها في [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>المتطلبات

> [!NOTE]
> تأكد من تعيين جميع **تعيينات الدور** كما هو موضح.

- في Customer Insights، يجب أن يشتمل حساب مستخدم Azure Active Directory (AD) الخاص بك على [دور المسؤول](permissions.md#add-users).

في Azure:

- اشتراك Azure نشط.

- إذا كنت تستخدم حساب Azure Data Lake Storage Gen2 جديدًا، يحتاج [كيان الخدمة لـ Customer Insights](connect-service-principal.md) إلى أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة**. إن Data Lake Storage Gen2 **يجب** أن يتضمن [مساحة أسماء هرمية](/azure/storage/blobs/data-lake-storage-namespace) قيد التمكين.

- في مجموعة الموارد حيث يوجد Azure Synapse ‏workspace، إن كلاًّ من *كيان الخدمة* و *مستخدم Azure AD الذي لديه أذونات المسؤول في Customer Insights* يجب على الأقل أن يتم لهما تعيين **أذونات** [القارئ](/azure/role-based-access-control/role-assignments-portal).

- يمتلك *مستخدم Azure AD الذي لديه أذونات المسؤول في Customer Insights* أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة** على حساب Azure Data Lake Storage ‏Gen2 حيث توجد البيانات وترتبط بـ Azure Synapse workspace. تعلم المزيد حول [استخدام مدخل Azure لتعيين دور Azure للوصول إلى بيانات الكائن الثنائي كبير الحجم والصف](/azure/storage/common/storage-auth-aad-rbac-portal) و[أذونات مساهم بيانات مخزن البيانات الثنائية الكبيرة](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- تتضمن *[الهوية المدارة بواسطة Azure Synapse ‏workspace](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة** في حساب Azure Data Lake Storage ‏Gen2 في المكان الذي توجد فيه البيانات وترتبط بـ Azure Synapse ‏workspace. تعلم المزيد حول [استخدام مدخل Azure لتعيين دور Azure للوصول إلى بيانات الكائن الثنائي كبير الحجم والصف](/azure/storage/common/storage-auth-aad-rbac-portal) و[أذونات مساهم بيانات مخزن البيانات الثنائية الكبيرة](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- في Azure Synapse ‏workspace، إن *مدير الخدمة في Customer Insights* تم تعيين دور **مسؤول Synapse** [له](/azure/synapse-analytics/security/how-to-set-up-access-control).

- إذا كانت بيئة Customer Insights [تخزن Azure Data Lake Storage](own-data-lake-storage.md)، المستخدم الذي يقوم بإعداد الاتصال إلى Azure Synapse Analytics يحتاج على الأقل المدمج في **القارئ** دور في حساب Data Lake Storage. لمزيد من المعلومات، راجع [تعيين أدوار Azure باستخدام مدخل Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="set-up-connection-to-azure-synapse"></a>إعداد اتصال بـ Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Azure Synapse Analytics**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. حدد الاشتراك الذي ترغب في استخدامه في بيانات Customer Insights أو ابحث عنه. بمجرد تحديد اشتراك، يمكنك أيضا تحديد **مساحة العمل** و **حساب مساحة التخزين** و **الحاوية**.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)] لتكوين التصدير من خلال اتصال مشترك، ستحتاج على الأقل إلى الحصول على أذونات **المساهم** في Customer Insights.

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Azure Synapse Analytics. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. قم بتوفير **اسم العرض** يمكن التعرف عليه لعملية التصدير الخاصة بك و **اسم قاعدة البيانات**. سيعمل التصدير على إنشاء [Azure Synapse قاعدة بيانات مستودع](/azure/synapse-analytics/database-designer/concepts-lake-database) جديدة في مساحة العمل المحددة في الاتصال.

1. حدد أي الكيانات التي ترغب في تصديرها إلى Azure Synapse Analytics.
   > [!NOTE]
   > لا يتم دعم مصادر البيانات المستندة إلى [مجلد ‏‫نموذج البيانات العامة](connect-common-data-model.md).

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

للاستعلام عن البيانات التي تم تصديرها إلى Synapse Analytics، تحتاج إلى وصول **‏‫قارئ بيانات التخزين كبيرة الحجم‬** إلى التخزين الوجهة في مساحة عمل عمليات التصدير.

## <a name="update-an-export"></a>تحديث عملية تصدير

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **تحرير** في عملية التصدير التي تريد تحديثها.

   - **أضف** أو **أزل** الكيانات من الاختيار. في حالة إزالة الكيانات من التحديد، لا يتم حذفها من قاعدة بيانات Synapse Analytics. ومع ذلك، لن تؤدي عمليات تحديث البيانات المستقبلية إلى تحديث الكيانات التي تمت إزالتها في قاعدة البيانات هذه.

   - يؤدي **تغيير اسم قاعدة البيانات** إلى إنشاء قاعدة بيانات Synapse Analytics جديدة. لن تتلقى قاعدة البيانات بالاسم الذي تم تكوينه في السابق أي تحديثات في عمليات التحديث المستقبلة.

[!INCLUDE [footer-include](includes/footer-banner.md)]
