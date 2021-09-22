---
title: تشغيل عينة SDK على الويب
description: تعرف على كيفية تخصيص عينة SDK على الويب وتشغيلها.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036587"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>تشغيل نموذج SDK على الويب للحصول على إمكانية رؤى الارتباط Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

مكتبة ويب SDK الخاصة بالقدرة على رؤى الارتباط هي مكتبة JavaScript ذات عينة من التعليمات البرمجية التي يمكنك استخدامها على موقع الويب الخاص بك.

## <a name="prerequisites"></a>المتطلبات الأساسية

- تثبيت [Visual Studio Code](https://code.visualstudio.com/).
- [قم بتثبيت امتداد خادم Live](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) في Visual Studio Code واطلع على كيفية تشغيل خادم مباشر.
- يجب أن يكون لديك [مفتاح الحذف](instrument-website.md).

## <a name="run-sample"></a>تشغيل عينة

1. [قم بتنزيل نموذج SDK على الويب](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. قم بفك الملف المضغوط `ei_websdk_sample.zip`.

1. افتح المجلد المفكوك في Visual Studio Code.

1. في الملف `ei_websdk_sample.html`، استبدل السلسلة "INGESTION_KEY" بمفتاح الاستيعاب من مدخل إمكانية رؤى الارتباط، واسم السلسلة "NAME" بالاسم العام الذي تريد SDK أن يتم فتحه على الفور. تأكد من استبدال جميع التكرارات.

1. افتح الملف `ei_websdk_sample.html` باستخدام خادم Live Server في Visual Studio Code عن طريق تحديد **تشغيل مباشر** من شريط الحالة.

1. في فتح الصفحة، ينبغي إرسال حدث طريقة عرض تلقائيا. يؤدي النقر فوق أي من الأزرار في الصفحة إلى إرسال أحداث الإجراء. سيرسل الزر **تعقب الأحداث** أيضا أحداثا مخصصة. سيرسل تحديد الزر **الانتقال إلى Bing** حدث إجراء قبل التنقل إلى موقع ويب Bing.

1. انظر إلى الأحداث المتدفقة عند الانتقال إلى مساحة العمل الخاصة بك. يتم ربط مساحة العمل هذه بمفتاح الاقتباس الذي تم إدخاله في الخطوة 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]