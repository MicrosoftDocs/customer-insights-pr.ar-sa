---
title: الشروع في العمل باستخدام iOS SDK
description: تعرف على كيفية تخصيص وتشغيل IOS SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036857"
---
# <a name="get-started-with-the-ios-sdk"></a>الشروع في العمل باستخدام iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

يرشدك هذا البرنامج التعليمي خلال عملية تجهيز تطبيق iOS باستخدام SDK لمعلومات المشاركة في Dynamics 365 Customer Insights. ستبدأ في مشاهدة الأحداث في المدخل الخاص بك خلال خمس دقائق أو بدء تشغيلها.

## <a name="configuration-options"></a>خيارات التكوين

يمكن تمرير خيارات التكوين التالية إلى SDK من خلال ملف `EIConfig.plist` الموفر:

- **ingestionKey**: مفتاح العرض المُستخدم لإرسال الأحداث إلى مشروعك.
- **autocollectAction**: قيمة منطقية لتمكين أو تعطيل الأدوات التلقائية لحدث الإجراء.
- **autocollectView**: قيمة منطقية لتمكين أو تعطيل الأدوات التلقائية لحدث العرض.
- **endpointUrl**: عنوان URL لنقطة النهاية حيث سيتم توجيه الأحداث.

## <a name="prerequisites"></a>المتطلبات الأساسية

- Xcode الإصدار 9+
- iOS الإصدار 8.2+
- مفتاح الإدخال (انظر التعليمات أدناه للحصول عليها)

## <a name="integrate-the-sdk-into-your-application"></a>دمج SDK في التطبيق

ابدأ العملية من خلال تحديد مساحة عمل للعمل بها، وتحديد النظام الأساسي المحمول ل iOS، وتنزيل SDK.

- استخدم مفتاح تبديل مساحة العمل في جزء التنقل الأيسر لتحديد مساحة العمل الخاصة بك.

- إذا لم يكن لديك مساحة عمل موجودة، فحدد **مساحة عمل جديدة** واتبع الخطوات اللازمة لإنشاء [مساحة عمل جديدة](create-workspace.md).

## <a name="configure-the-sdk"></a>تكوين SDK

وبمجرد تنزيل SDK، يمكنك العمل معه في Xcode لتمكين الأحداث وتحديدها.

1. بعد إنشاء مساحة عمل، انتقل إلى **المسؤول** > **مساحة العمل**، ثم حدد **دليل التثبيت**.

1. قم بتنزيل [iOS SDK لمعلومات المشاركة](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip)، وضع ملف `EIObjC.xcframework` في مجلد `Frameworks`.

1. إذا لم يكن مجلد `Frameworks` موجودا، فقم بإنشاء مجلد في مجلد المشروع.

## <a name="enable-auto-instrumentation"></a>تمكين الأدوات التلقائية
 
يمكنك بسهولة تمكين الأدوات التلقائية دون ترميز. وعند تشغيل المشروع، سيتعقب أحداث `view` و`action` تلقائيًا باستخدام مفتاح الإدخال المكون. 

1. قم بتحديث وتضمين ملف `EIConfig.plist` الموفر في مجلد دليل المشروع الخاص بك للحقول التالية:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = YES
    - autocollectAction = YES

2. ثم أضف ملف `EIConfig.plist` إلى مشروعك في Xcode. 



لتعطيل الأدوات التلقائية، قم بتحديث الحقول التالية في ملف `EIConfig.plist` الموفر في مجلد دليل المشروع لديك. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>تنفيذ الأحداث المخصصة

1. افتح مشروعك في Xcode، وانتقل إلى الإعدادات **العامة**. 
1. أضف `EIObjC.xcframework` إلى المشروع ضمن قسم "إطارات العمل، والمكتبات، والمحتوى المضمن".

1. قم باستيراد ملف رأس إطار العمل في AppDelegate.m بالمقتطف التالي:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. قم بتهيئة SDK لمعلومات المشاركة من التطبيق: didFinishLaunchingWithOptions.
1. انسخ قصاصة XML البرمجية من **دليل التثبيت**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. تعقب حدث:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>تعيين تفاصيل المستخدم للحدث الخاص بك

يتيح SDK تعريف معلومات المستخدم التي يمكن إرسالها مع كل حدث. يمكنك تحديد معلومات المستخدم من خلال استدعاء واجهة برمجة تطبيقات `setUser:(nonnull EIUser *)user` على SDK.

يعني تحديد تفاصيل المستخدم على مستوى `Analytics` أن جميع قياسات تتبع الاستخدام سوف تحصل على هذه المعلومات. ومع ذلك، إذا قمت بتحديد مستوى الحدث من خلال استدعاء واجهة برمج تطبيقات `setUser:(nonnull EIUser *)user` على كائن EIEvent، فقط ذلك الحدث المحدد سيحتوي على المعلومات.

وتحتوي فئة بيانات `EIUser` على خصائص NSString التالية:

- **localId**: معرف المستخدم المحلي.
- **authId**: معرف المستخدم المصادق عليه.
- **authType**: نوع المصادقة المستخدمة للحصول على معرف المستخدم المصادقة.
- **الاسم**: اسم المستخدم.
- **البريد الإلكتروني**: عنوان البريد الإلكتروني للمستخدم


[!INCLUDE[footer-include](../includes/footer-banner.md)]
