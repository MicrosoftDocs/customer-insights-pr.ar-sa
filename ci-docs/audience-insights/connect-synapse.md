---
title: استيعاب البيانات من:Azure Synapse Analytics
description: استخدم قاعدة بيانات في Azure Synapseباعتبارها مصدر بيانات في Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356012"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>وصل مصدر بيانات من Azure Synapse (إصدار أولي)

Azure Synapse Analytics هي خدمة تحليلات مؤسسية تُسرع من الوصول إلى الخدمةتحليلات عبر مستودعات البيانات وأنظمة البيانات الكبيرة. Azure Synapse Analyticsيجمع بين أفضل تقنيات SQL المستخدمة في تخزين بيانات المؤسسة، وتقنيات Spark المستخدمة للبيانات الكبيرة، ومستكشف البيانات لتحليلات سلسلة التسجيل والوقت، ومسارات لتكامل البيانات وETL/ELT، بالإضافة إلى التكامل العميق مع خدمات Azure الأخرى ومنها Power BI وCosmos DBو AzureML.

لمزيد من المعلومات، راجع [نظرة عامة على Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>المتطلبات

يجب تلبية المتطلبات الأساسية التالية لتهيئة الاتصال من Customer Insights إلى Azure Synapse.

> [!IMPORTANT]
> تأكد من تعيين جميع **تعيينات الدور** كما هو موضح.  

## <a name="prerequisites-in-customer-insights"></a>المتطلبات الأساسية في Customer Insights

* لديك دور **المسؤول** في Customer Insights. لمعرفة المزيد [أذونات المستخدم في رؤى الجمهور](permissions.md#assign-roles-and-permissions).

في Azure: 

- اشتراك Azure نشط.

- في حالة استخدام حساب Azure Data Lake Storage Gen2، فإن *مبدأ الخدمة لمعلومات الجمهور* يجتاج إلى إذن **مساهم بيانات مخزن البيانات الثنائية الكبيرة**. تعرف على المزيد [ بشأن الاتصال بكيان خدمة من Azure Data Lake Storage لمعلومات الجمهور ](connect-service-principal.md). إن Data Lake Storage Gen2 **يجب** أن يتضمن [مساحة أسماء هرمية](/azure/storage/blobs/data-lake-storage-namespace) قيد التمكين.

- في مجموعة الموارد التي توجد بها مساحة عمل Azure Synapse، فإن *مبدأ الخدمة* و *المستخدم لمعلومات الجمهور* يحتاج  تعيين أذونات **قارئ** له على الأقل. لمزيد من المعلومات، راجع [تعيين أدوار Azure باستخدام مدخل Azure](/azure/role-based-access-control/role-assignments-portal).

- يحتاج *المستخدم* إلى أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة** في حساب Azure Data Lake Storage Gen2 في المكان الذي توجد فيه البيانات وترتبط بمساحة عمل Azure Synapse. تعلم المزيد حول [استخدام مدخل Azure لتعيين دور Azure للوصول إلى بيانات الكائن الثنائي كبير الحجم والصف](/azure/storage/common/storage-auth-aad-rbac-portal) و[أذونات مساهم بيانات مخزن البيانات الثنائية الكبيرة](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- تحتاج *[الهوية المدارة بمساحة عمل Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* إلى أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة** في حساب Azure Data Lake Storage Gen2 في المكان الذي توجد فيه البيانات وترتبط بمساحة عمل Azure Synapse. تعلم المزيد حول [استخدام مدخل Azure لتعيين دور Azure للوصول إلى بيانات الكائن الثنائي كبير الحجم والصف](/azure/storage/common/storage-auth-aad-rbac-portal) و[أذونات مساهم بيانات مخزن البيانات الثنائية الكبيرة](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- في مساحة عمل Azure Synapse، يحتاج *مبدأ الخدمة لمعلومات الجمهور* إلى تعيين دور **مسؤول  Synapse**. لمزيد من المعلومات، راجع [كيفية إعداد عنصر تحكم الوصول لمساحة عمل Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control) الخاصة بك.

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>اتصل بقواعد بيانات مستودع البيانات في Azure Synapse Analytics

1. انتقل إلى **البيانات** > **مصادر البيانات**.

1. حدد **إضافة مصدر بيانات**.

1. اختر الطريقة **Azure Synapse Analytics (إصدار أولي**).

1. أدخل **اسمًا** لمصدر البيانات، وحدد **التالي** لإنشاء المصدر البيانات. 

1. اختر [اتصالاً متوفرًا ](connections.md) بـ Azure Synapse Analytics أو قم بإنشاء اتصال جديد.

1. اختر **Lake Database (قاعدة بيانات المستودع)** من مساحة العمل المتصلة في Azure Synapse Analytics الاتصال المحدد وحدد **Next (التالي)**.

1. حدد الكيانات لاستيعابها من قاعدة البيانات المتصلة. 

1. بشكل اختياري، اختر كيانات البيانات للسماح بتصنيف البيانات. 

1. حدد **Save (حفظ)** لتطبيق اختيارك وابدأ استيعاب البيانات من مصدر البيانات التي تم إنشاؤها مؤخرًا المرتبط بجداول قاعدة بيانات المستودع في Azure Synapse Analytics.
