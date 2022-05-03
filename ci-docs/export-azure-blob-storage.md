---
title: تصدير بيانات Customer Insights إلى مساحة تخزين Azure Blob Storage
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى مساحة تخزين Blob storage.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 42095f369c47553e5ddf5fada54e559202c943a9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645507"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>تصدير قائمة الشرائح والبيانات الأخرى إلى مساحة تخزين Azure Blob Storage (إصدار أولي)

قم بتخزين بيانات Customer Insights في مساحة تخزين Blob Storage أو استخدمها لنقل بياناتك إلى تطبيقات أخرى.

## <a name="known-limitations"></a>القيود المعروفة

1. بالنسبة إلى Azure Blob Storage، يمكنك الاختيار بين [الأداء القياسي ومستوى الأداء المتميز](/azure/storage/blobs/storage-blob-performance-tiers). إذا اخترت مستوى الأداء المتميز، فحدد [كائنات الكتل الثنائية المتميزة كنوع حساب](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>إعداد الاتصال بمساحة تخزين Blob Storage

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **مساحة تخزين Azure Blob Storage** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **اسم الحساب**، و **مفتاح الحساب**، و **الحساب** لحسابك في حساب مساحة تخزين Blob storage الخاصة بك.
    - لمعرفة المزيد حول كيفية العثور على اسم حساب مساحة تخزين اسم حساب تخزين Blob storage ومفتاح الحساب، راجع [إدارة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).
    - لمعرفة كيفية إنشاء حاوية، راجع [إنشاء حاوية](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. حدد **حفظ** لإكمال الاتصال. 

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> إذا قمت بتشغيل إعداد الحذف لحساب مساحة تخزين Azure Blob Storage، فستفشل عمليات التصدير. إيقاف تشغيل الحذف لتصدير البيانات إلى blobs. لمزيد من المعلومات، راجع [تمكين حذف blob](/azure/storage/blobs/soft-delete-blob-enable.md)

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم مساحة تخزين Azure Blob Storage, إذا لم تشاهد اسم المقطع هذا، فلا توجد اتصالات من هذا النوع متوفرة لك.

1. حدد المربع إلى جانب كل كيان تريد تصديره إلى هذه الوجهة.

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).     

يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 

يتم تخزين البيانات المصدرة في حاوية مساحة تخزين Blob storage التي قمت بتكوينها. يتم إنشاء مسارات المجلدات التالية بشكل تلقائي في حاويتك:

- بالنسبة للكيانات المصدر والكيانات التي تم إنشاؤها بواسطة النظام:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - مثال: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- سيكون model.json للكيانات المصدرة في مستوى %ExportDestinationName%.  
  - مثال: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE [footer-include](includes/footer-banner.md)]
