---
title: تصدير البيانات Azure Data Lake Storage Gen2 (إصدار أولي)
description: اعرف كيفية تكوين الاتصال بـ Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196424"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>تصدير البيانات Azure Data Lake Storage Gen2 (إصدار أولي)

قم بتخزين بيانات Customer Insights في حساب Data Lake Storage Gen2 أو استخدمها لنقل بياناتك إلى تطبيقات أخرى.

## <a name="prerequisites"></a>المتطلبات

- [حساب تخزين لاستخدامه مع Azure Data Lake Gen 2](/azure/storage/blobs/create-data-lake-storage-account). لعثور على اسم ومفتاح حساب التخزين، راجع [إدارة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).
- [حاوية مساحة تخزين Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>القيود المعروفة

- بالنسبة إلى Azure Data Lake Storage Gen2، اختر من بين [الأداء القياسي ومستوى الأداء المتميز](/azure/storage/blobs/create-data-lake-storage-account). إذا اخترت مستوى الأداء المتميز، فحدد [كائنات الكتل الثنائية المتميزة كنوع حساب](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>إعداد الاتصال بـ Azure Data Lake Storage ‏Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Azure Data Lake Gen 2**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **اسم الحساب**، و **مفتاح الحساب**، و **الحاوية** لـ Azure Data Lake Storage Gen2.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم Azure Data Lake. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. أدخل اسم المجلد لتخزين Azure Data Lake Storage ‏Gen2.

1. حدد المربع إلى جانب كل كيان تريد تصديره إلى هذه الوجهة.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

يتم تخزين البيانات المصدرة في حاوية تخزين Azure Data Lake Gen 2 التي قمت بتكوينها.

> [!TIP]
> يمكن أن يؤدي تصدير الكيانات التي تحتوي على كمية كبيرة من البيانات إلى الحصول على ملفات CSV متعددة في نفس المجلد لكل عملية تصدير. يحدث تقسيم الصادرات لأسباب تتعلق بالأداء لتقليل الوقت الذي يستغرقه اكتمال التصدير.

[!INCLUDE [footer-include](includes/footer-banner.md)]
