---
title: الشروع في العمل باستخدام iOS SDK
description: تعرف على كيفية تخصيص وتشغيل IOS SDK
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 09/15/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 68e4d0555d2fc377fae62ff5db64c032fcebcb04
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226198"
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

- بعد إنشاء مساحة عمل، انتقل إلى **المسؤول** > **مساحة العمل**، ثم حدد **دليل التثبيت**.

## <a name="configure-the-sdk"></a>تكوين SDK

وبمجرد تنزيل SDK، يمكنك العمل معه في Xcode لتمكين الأحداث وتحديدها. هناك طريقتان للقيام بذلك

### <a name="option-1-using-cocoapods-recommended"></a>الخيار 1: استخدام CocoaPods (مستحسن)
CocoaPods هو مدير تبعية لمشروعي Swift وObjective-C Cocoa. يجعل استخدامه دمج SDK لمشاركة المعلومات لنظام iOS أسهل. يتيح لك CocoaPods أيضًا الترقية إلى أحدث إصدار من SDK لمعلومات المشاركة. إليك كيفية استخدام CocoaPods لدمج SDK لمعلومات المشاركة في مشروع Xcode الخاص بك. 

1. قم بتثبيت CocoaPods 

1. أنشئ ملفًا جديدًا يسمى Podfile داخل الدليل الجذر لمشروعك وأضف العبارات التالية إليه.استبدل YOUR_TARGET_PROJECT_NAME باسم مشروع Xcode الخاص بك. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
يحتوي تكوين pod أعلاه على كل من إصدارات التصحيح والإصدار من SDK. اختر أيهما أفضل لمشروعك.

1. قم بتثبيت pod عن طريق تنفيذ الأمر التالي: `pod install --repo-update `

### <a name="option-2-using-download-link"></a>الخيار 2: استخدام ارتباط التنزيل

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
