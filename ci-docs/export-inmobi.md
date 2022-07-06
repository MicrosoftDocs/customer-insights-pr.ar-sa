---
title: تصدير بيانات Customer Insights إلى InMobi
description: تعرف على كيفية تكوين الاتصال والتصدير إلى InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056532"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>تصدير قائمة المقاطع والبيانات الأخرى إلى InMobi (إصدار أولي)

قم تصدير قوائم المقطع أو بيانات أخرى من مثيل Customer Insights إلى [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>المتطلبات

1. لديك [حساب InMobi](https://www.inmobi.com/) وبيانات اعتماد مسؤول.
1. لديك اسم حساب تخزين Azure Blob ومفتاح الحساب المقابل. لمزيد من المعلومات، راجع [إدارة إعدادات حساب تخزين في مدخل Azure](/azure/storage/common/storage-account-manage). هناك حاوية في حساب التخزين لتصدير بيانات inMobi إليها. لمزيد من المعلومات، راجع [إنشاء حاوية](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. سيعمل InMobi على إنشاء اتصالاً مباشرًا بمساحة تخزين Blob، وتكوين عملية استيراد تلقائية للبيانات إلى InMobi. اتصل بممثل InMobi لبدء العملية.

## <a name="known-limitations"></a>القيود المعروفة

1. بالنسبة إلى Azure Blob Storage، يمكنك الاختيار بين [الأداء القياسي ومستوى الأداء المتميز](/azure/storage/blobs/storage-blob-performance-tiers). إذا اخترت مستوى الأداء المتميز، فحدد [كائنات الكتل الثنائية المتميزة كنوع حساب](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>إعداد الاتصال بمساحة تخزين Azure Blob وتكوين تصدير

1. اتبع الإرشادات إلى [إعداد اتصال إلى مساحة تخزين Azure Blob الخاصة بك](export-azure-blob-storage.md).
2. اتبع الإرشادات [لتكوين تصدير](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
