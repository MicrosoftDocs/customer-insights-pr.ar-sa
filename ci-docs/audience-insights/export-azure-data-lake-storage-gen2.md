---
title: تصدير بيانات Customer Insights إلى Azure Data Lake Storage Gen2
description: اعرف كيفية تكوين الاتصال بـ Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477163"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>موصل Azure Data Lake Storage Gen2 (إصدار أولي)

خزّن بيانات Customer Insights في Azure Data Lake Storage Gen2 أو استخدمها لنقل بياناتك إلى تطبيقات أخرى.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>تكوين موصل Azure Data Lake Storage Gen2

1. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.

1. أسفل **Azure Data Lake Storage Gen2**، حدد **إعداد‏‎**.

1. في حقل **الاسم المعروض**، أدخل اسمًا للوجهة سهل التمييز.

1. أدخل **اسم الحساب**، و **مفتاح الحساب**، و **الحاوية** لـ Azure Data Lake Storage Gen2.
    - لمعرفة كيفية إنشاء حساب تخزين لاستخدامه مع Azure Data Lake Storage Gen2، راجع [إنشاء حساب تخزين](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - لمعرفة المزيد حول كيفية العثور على اسم حساب تخزين Azure Data Lake Gen2 ومفتاح الحساب، راجع [إدارة إعدادات حساب التخزين في مدخل Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. حدد **التالي**.

1. حدد المربع إلى جانب كل كيان تريد تصديره إلى هذه الوجهة.

1. حدد **حفظ**.

## <a name="export-the-data"></a>تصدير البيانات

يمكنك [تصدير البيانات عند الطلب](export-destinations.md#export-data-on-demand). سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).
