---
title: استيعاب البيانات من:Azure Synapse Analytics
description: استخدم قاعدة بيانات في Azure Synapseباعتبارها مصدر بيانات في Dynamics 365 Customer Insights.
ms.date: 03/25/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 6f94cdbcc203fc4518544f7a945bd80e871b36c1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011411"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>وصل مصدر بيانات من Azure Synapse Analytics (إصدار أولي)

Azure Synapse Analytics هي خدمة تحليلات مؤسسية تُسرع من الوصول إلى الخدمةتحليلات عبر مستودعات البيانات وأنظمة البيانات الكبيرة. Azure Synapse Analyticsيجمع بين أفضل تقنيات SQL المستخدمة في تخزين بيانات المؤسسة، وتقنيات Spark المستخدمة للبيانات الكبيرة، ومستكشف البيانات لتحليلات سلسلة التسجيل والوقت، ومسارات لتكامل البيانات وETL/ELT، بالإضافة إلى التكامل العميق مع خدمات Azure الأخرى ومنها Power BI وCosmos DBو AzureML.

لمزيد من المعلومات، راجع [نظرة عامة على Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>المتطلبات

> [!IMPORTANT]
> تأكد من تعيين جميع **تعيينات الدور** كما هو موضح.  

**في Customer Insights**:

* لديك دور **المسؤول** في Customer Insights. لمعرفة المزيد [أذونات المستخدم في Customer Insights](permissions.md#assign-roles-and-permissions).

**في Azure**:

- اشتراك Azure نشط.

- إذا كنت تستخدم حساب Azure Data Lake Storage Gen2 جديدًا، يحتاج *كيان الخدمة لـ Customer Insights* إلى أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة**. تعرف على المزيد حول [الاتصال بـ Azure Data Lake Storage باستخدام كيان خدمة لـ Customer Insights](connect-service-principal.md). إن Data Lake Storage Gen2 **يجب** أن يتضمن [مساحة أسماء هرمية](/azure/storage/blobs/data-lake-storage-namespace) قيد التمكين.

- في مجموعة الموارد، توجد Azure Synapse workspace، ويحتاج *كيان الخدمة* و *مستخدم Customer Insights* إلى تعيين أذونات **القارئ** على الأقل . لمزيد من المعلومات، راجع [تعيين أدوار Azure باستخدام مدخل Azure](/azure/role-based-access-control/role-assignments-portal).

- يحتاج *المستخدم* إلى أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة** في حساب Azure Data Lake Storage Gen2 في المكان الذي توجد فيه البيانات وترتبط بمساحة عمل Azure Synapse. تعلم المزيد حول [استخدام مدخل Azure لتعيين دور Azure للوصول إلى بيانات الكائن الثنائي كبير الحجم والصف](/azure/storage/common/storage-auth-aad-rbac-portal) و[أذونات مساهم بيانات مخزن البيانات الثنائية الكبيرة](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- تحتاج *[الهوية المدارة بمساحة عمل Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* إلى أذونات **مساهم بيانات مخزن البيانات الثنائية الكبيرة** في حساب Azure Data Lake Storage Gen2 في المكان الذي توجد فيه البيانات وترتبط بمساحة عمل Azure Synapse. تعلم المزيد حول [استخدام مدخل Azure لتعيين دور Azure للوصول إلى بيانات الكائن الثنائي كبير الحجم والصف](/azure/storage/common/storage-auth-aad-rbac-portal) و[أذونات مساهم بيانات مخزن البيانات الثنائية الكبيرة](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- في Azure Synapse workspace، يحتاج *كيان الخدمة لـ Customer Insights* إلى دور **مسؤول Synapse**. لمزيد من المعلومات، راجع [كيفية إعداد عنصر تحكم الوصول لمساحة عمل Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control) الخاصة بك.

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>الاتصال بقاعدة بيانات مستودع البيانات في Azure Synapse Analytics

1. انتقل إلى **البيانات** > **مصادر البيانات**.

1. حدد **إضافة مصدر بيانات**.

1. اختر الطريقة **Azure Synapse Analytics (إصدار أولي**).

   :::image type="content" source="media/data_sources_synapse.png" alt-text="مربع الحوار للاتصال ببيانات Synapse Analytics":::
  
1. أدخل **اسمًا** لمصدر البيانات و **وصفًا** اختياريًا.

1. اختر [اتصالاً متوفرًا ](connections.md) بـ Azure Synapse Analytics أو قم بإنشاء اتصال جديد.

1. اختر **قاعدة بيانات** من مساحة العمل المتصلة في اتصال Azure Synapse Analytics المحدد وحدد **التالي**.

1. حدد الكيانات لاستيعابها من قاعدة البيانات المتصلة وحدد **التالي**.

1. بشكل اختياري، اختر كيانات البيانات للسماح بتصنيف البيانات.

1. حدد **Save (حفظ)** لتطبيق اختيارك وابدأ استيعاب البيانات من مصدر البيانات التي تم إنشاؤها مؤخرًا المرتبط بجداول قاعدة بيانات المستودع في Azure Synapse Analytics. تفتح صفحة **مصادر‏‎ البيانات** التي تعرض مصدر البيانات الجديد في الحالة **جارٍ التحديث**.
