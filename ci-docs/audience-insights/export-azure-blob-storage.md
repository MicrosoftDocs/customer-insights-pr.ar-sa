---
title: تصدير بيانات Customer Insights إلى مساحة تخزين Azure Blob
description: تعرف على كيفية تكوين الاتصال بتخزين Azure Blob.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ecacf20365e78ced8859dfa54b1b16cb923c00eb
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269176"
---
# <a name="connector-for-azure-blob-storage-preview"></a>موصل تخزين Azure Blob‬ (معاينة)

قم بتخزين بيانات Customer Insights في مساحة تخزين Azure Blob أو استخدمها لنقل بياناتك إلى تطبيقات أخرى.

## <a name="configure-the-connector-for-azure-blob-storage"></a>تكوين موصل تخزين Azure Blob‬

1. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.

1. ضمن **تخزين Azure Blob**، حدد **إعداد**.

1. أدخل **اسم الحساب** و **مفتاح الحساب** و **الحاوية** لحساب تخزين Azure Blob.
    - لمعرفة المزيد حول كيفية العثور على اسم حساب مخزن البيانات الثنائية الكبيرة الحجز لـ Azure ومفتاح الحساب، راجع [أداة إعدادات حساب التخزين في مدخل Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - لمعرفة كيفية إنشاء حاوية، راجع [إنشاء حاوية](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. في حقل **الاسم المعروض**، أدخل اسمًا للوجهة سهل التمييز.

1. حدد **التالي**.

1. حدد المربع إلى جانب كل كيان تريد تصديره إلى هذه الوجهة.

1. حدد **حفظ**.

يتم تخزين البيانات التي تم تصديرها في حاوية تخزين Azure Blob التي قمت بتكوينها. يتم إنشاء مسارات المجلدات التالية بشكل تلقائي في حاويتك:

- بالنسبة للكيانات المصدر والكيانات التي تم إنشاؤها بواسطة النظام: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - مثال: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- سيكون model.json للكيانات المصدرة موجودًا على مستوى %ExportDestinationName%
  - مثال: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>تصدير البيانات

يمكنك [تصدير البيانات عند الطلب](export-destinations.md#export-data-on-demand). سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]