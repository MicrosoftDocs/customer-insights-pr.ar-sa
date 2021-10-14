---
title: تشغيل نموذج iOS SDK
description: نموذج مشروع للتعرف على IOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036812"
---
# <a name="run-the-ios-sdk-sample"></a>تشغيل نموذج iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

يساعدك مشروع iOS العينة هذا على فهم كيفية عمل SDK في التطبيق. ولست بحاجة إلى كتابة تعليمات برمجية. فقط أضف مفتاح الابتعاد الخاص بك ويمكن رؤية الأحداث في مساحة العمل الخاصة بك على الفور.

## <a name="prerequisites"></a>المتطلبات الأساسية

- [Xcode الإصدار 9+](https://developer.apple.com/xcode/downloads/)
- [مفتاح الاستيعاب](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>تنزيل نموذج iOS SDK

1. [قم بتنزيل نموذج iOS SDK لمعلومات المشاركة](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. قم بفك الملف المضغوط `ei-ios-sample.zip`.
1. افتح نموذج مشروع التطبيق في Xcode.
1. في ملف `EIConfig.plist`، استبدل السلسلة `“YOUR-INGESTION-KEY”` في الحقل `ingestionKey` بمفتاح استيعاب مساحة العمل لديك من معلومات المشاركة ضمن **المسؤول** > **مساحة العمل** > **دليل التثبيت**.
1. حدد **تشغيل** لبدء المشروع النموذج.
1. اعرض الأحداث في مساحة العمل الخاصة بك.

[!INCLUDE[footer-include](../includes/footer-banner.md)]