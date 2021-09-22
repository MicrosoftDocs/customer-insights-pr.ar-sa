---
title: عينة Android SDK
description: نموذج مشروع للتعرف على Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035810"
---
# <a name="run-the-android-sdk-sample"></a>تشغيل نموذج Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

يساعدك مشروع Android العينة هذا على فهم كيفية عمل SDK في التطبيق. ولست بحاجة إلى كتابة تعليمات برمجية. فقط أضف مفتاح الابتعاد الخاص بك ويمكن رؤية الأحداث في مساحة العمل الخاصة بك على الفور.

## <a name="prerequisites"></a>المتطلبات الأساسية

- [Android Studio](https://developer.android.com/studio)
- [مفتاح الاستيعاب](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>تنزيل نموذج Android SDK

1. [قم بتنزيل نموذج Android SDK لمعلومات المشاركة](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. قم بفك الملف المضغوط `ei-android-sample.zip`.
1. افتح المجلد غير المضغوط في Android Studio.
1. في ملف `AndroidManifest.xml`، استبدل السلسلة `"Your-Ingestion-Key"` بمفتاح استيعاب مساحة العمل لديك من معلومات المشاركة ضمن **المسؤول** > **مساحة العمل** > **دليل التثبيت**. 

   > [!NOTE]
   > لست بحاجة إلى استبدال قسم `${applicationId}`. يتم ملؤه تلقائيًا.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. حدد **تشغيل** لبدء المشروع النموذج.
1. اعرض الأحداث في مساحة العمل الخاصة بك.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
