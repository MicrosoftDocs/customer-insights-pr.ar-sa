---
title: تصدير بيانات Customer Insights إلى Azure Data Lake Storage Gen2
description: اعرف كيفية تكوين الاتصال بـ Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 8b14992f8312d333d8a12501e8a28496c8434779
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645487"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>تصدير قائمة المقاطع والبيانات الأخرى إلى Azure Data Lake Storage ‏Gen2 (إصدار أولي)

قم بتخزين بيانات Customer Insights في حساب Data Lake Storage Gen2 أو استخدمها لنقل بياناتك إلى تطبيقات أخرى.

## <a name="known-limitations"></a>القيود المعروفة

1. بالنسبة إلى Azure Data Lake Storage ‏Gen2 يمكنك الاختيار بين [الأداء القياسي ومستوى الأداء المتميز](/azure/storage/blobs/create-data-lake-storage-account) عند إنشاء حساب تخزين لمستودع البيانات الخاص بك. إذا اخترت مستوى الأداء المتميز، فحدد كائنات الكتل الثنائية المتميزة كنوع حساب. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>إعداد الاتصال بـ Azure Data Lake Storage ‏Gen2 


1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Azure Data Lake Gen 2** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **اسم الحساب**، و **مفتاح الحساب**، و **الحاوية** لـ Azure Data Lake Storage Gen2.
    - لمعرفة كيفية إنشاء حساب تخزين لاستخدامه مع Azure Data Lake Storage Gen2، راجع [إنشاء حساب تخزين](/azure/storage/blobs/create-data-lake-storage-account). 
    - لمعرفة المزيد حول اسم حساب تخزين Azure Data Lake Gen2 ومفتاح الحساب، راجع [إدارة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).

1. حدد **حفظ** لإكمال الاتصال. 

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء عملية تصدير جديدة، حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم **Azure Data Lake**. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. حدد المربع إلى جانب كل كيان تريد تصديره إلى هذه الوجهة.

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 

يتم تخزين البيانات المصدرة في حاوية تخزين Azure Data Lake Gen 2 التي قمت بتكوينها. 

[!INCLUDE [footer-include](includes/footer-banner.md)]
