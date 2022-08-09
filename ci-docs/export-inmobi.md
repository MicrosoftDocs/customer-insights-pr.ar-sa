---
title: تصدير بيانات Customer Insights إلى InMobi
description: تعرف على كيفية تكوين الاتصال والتصدير إلى InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195872"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>تصدير بيانات Customer Insights إلى InMobi (إصدار أولي)

قم تصدير قوائم المقطع أو بيانات أخرى من مثيل Customer Insights إلى [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>المتطلبات

- [حساب InMobi](https://www.inmobi.com/) وبيانات اعتماد مسؤول.
- اسم [حساب مساحة تخزين Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) ومفتاح الحساب. للعثور على الاسم والمفتاح، راجع [إدارة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).
- [حاوية Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) لتصدير بيانات InMobi إليها.
- سيعمل InMobi على إنشاء اتصالاً مباشرًا بمساحة تخزين Blob، وتكوين عملية استيراد تلقائية للبيانات إلى InMobi. اتصل بممثل InMobi لبدء العملية.

## <a name="known-limitations"></a>القيود المعروفة

- بالنسبة إلى Azure Blob Storage، اختر من بين [الأداء القياسي ومستوى الأداء المتميز](/azure/storage/blobs/storage-blob-performance-tiers). إذا اخترت مستوى الأداء المتميز، فحدد [كائنات الكتل الثنائية المتميزة كنوع حساب](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>إعداد الاتصال بـ Azure Blob Storage

[إعداد الاتصال بـ Azure Blob Storage لديك](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>تكوين تصدير

[تكوين تصدير](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
