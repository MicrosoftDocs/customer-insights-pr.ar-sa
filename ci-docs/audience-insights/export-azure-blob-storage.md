---
title: تصدير بيانات Customer Insights إلى مساحة تخزين Azure Blob Storage
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى مساحة تخزين Blob storage.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976118"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>تصدير قائمة الشرائح والبيانات الأخرى إلى مساحة تخزين Azure Blob Storage (إصدار أولي)

قم بتخزين بيانات Customer Insights في مساحة تخزين Blob Storage أو استخدمها لنقل بياناتك إلى تطبيقات أخرى.

## <a name="set-up-the-connection-to-blob-storage"></a>إعداد الاتصال بمساحة تخزين Blob Storage

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **مساحة تخزين Azure Blob Storage** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **اسم الحساب**، و **مفتاح الحساب**، و **الحساب** لحسابك في مساحة تخزين Blob storage.
    - لمعرفة المزيد حول كيفية العثور على اسم حساب مساحة تخزين اسم حساب تخزين Blob storage ومفتاح الحساب، راجع [إدارة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).
    - لمعرفة كيفية إنشاء حاوية، راجع [إنشاء حاوية](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. حدد **حفظ** لإكمال الاتصال. 

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم مساحة تخزين Azure Blob Storage, إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. حدد المربع إلى جانب كل كيان تريد تصديره إلى هذه الوجهة.

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab).     
يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 

يتم تخزين البيانات المصدرة في حاوية مساحة تخزين Blob storage التي قمت بتكوينها. يتم إنشاء مسارات المجلدات التالية بشكل تلقائي في حاويتك:

- بالنسبة للكيانات المصدر والكيانات التي تم إنشاؤها بواسطة النظام: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - مثال: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- سيكون model.json للكيانات المصدرة في مستوى %ExportDestinationName%
  - مثال: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]