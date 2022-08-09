---
title: تصدير البيانات إلى Azure Blob Storage (إصدار أولي)
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى مساحة تخزين Blob storage.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195688"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>تصدير البيانات إلى Azure Blob Storage (إصدار أولي)

قم بتخزين بيانات Customer Insights في مساحة تخزين Blob Storage أو استخدمها لنقل بياناتك إلى تطبيقات أخرى.

## <a name="prerequisites"></a>المتطلبات

- اسم [حساب مساحة تخزين Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) ومفتاح الحساب. للعثور على الاسم والمفتاح، راجع [إدارة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).
- [حاوية مساحة تخزين Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>القيود المعروفة

- بالنسبة إلى Azure Blob Storage، اختر من بين [الأداء القياسي ومستوى الأداء المتميز](/azure/storage/blobs/storage-blob-performance-tiers). إذا اخترت مستوى الأداء المتميز، فحدد [كائنات الكتل الثنائية المتميزة كنوع حساب](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>إعداد الاتصال بمساحة تخزين Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Azure Blob Storage**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **اسم الحساب**، و **مفتاح الحساب**، و **الحساب** لحسابك في حساب مساحة تخزين Blob storage الخاصة بك.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

لتكوين هذا التصدير، يجب أن يكون لديك [إذن](export-destinations.md#set-up-a-new-export) لهذا النوع من الاتصال.

> [!IMPORTANT]
> إذا قمت بتشغيل [إعداد الحذف البرمجي](/azure/storage/blobs/soft-delete-blob-enable) لحساب مساحة تخزين Azure Blob Storage، فستفشل عمليات التصدير. إيقاف تشغيل الحذف لتصدير البيانات إلى blobs.

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم مساحة تخزين Azure Blob Storage, اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. أدخل اسم المجلد لتخزين Blob.

1. حدد المربع إلى جانب كل كيان تريد تصديره إلى هذه الوجهة.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

يتم تخزين البيانات المصدرة في حاوية مساحة تخزين Blob storage التي قمت بتكوينها. يتم إنشاء مسارات المجلدات التالية بشكل تلقائي في حاويتك:

- بالنسبة للكيانات المصدر والكيانات التي تم إنشاؤها بواسطة النظام:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  مثال: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > يمكن أن يؤدي تصدير الكيانات التي تحتوي على كمية كبيرة من البيانات إلى الحصول على ملفات CSV متعددة في نفس المجلد لكل عملية تصدير. يحدث تقسيم الصادرات لأسباب تتعلق بالأداء لتقليل الوقت الذي يستغرقه اكتمال التصدير.

- يوجد الملف model.json للكيانات المصدّرة على مستوى *%ExportDestinationName%*.  
  
  مثال: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
