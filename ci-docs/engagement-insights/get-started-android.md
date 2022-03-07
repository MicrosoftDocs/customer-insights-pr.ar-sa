---
title: الشروع في العمل باستخدام Android SDK
description: تعرف على كيفية تخصيص وتشغيل Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/19/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: c678c2dafbb77926269b5602bca363c678ec6b3f
ms.sourcegitcommit: ef823f3d7fa28d3a90cfde9409be9465ffa2cf09
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 10/19/2021
ms.locfileid: "7655326"
---
# <a name="get-started-with-the-android-sdk"></a>الشروع في العمل باستخدام Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

يرشدك هذا البرنامج التعليمي خلال عملية تجهيز تطبيق Android باستخدام SDK لمعلومات المشاركة في Dynamics 365 Customer Insights. ستبدأ في مشاهدة الأحداث في المدخل الخاص بك خلال خمس دقائق أو بدء تشغيلها.

## <a name="configuration-options"></a>خيارات التكوين
يمكن تمرير خيارات التكوين التالية إلى SDK:

- **ingestionKey**: يُستخدم مفتاح الإدخال لإرسال الأحداث إلى مساحة عملك.

## <a name="prerequisites"></a>المتطلبات الأساسية

- Android Studio

- الحد الأدنى لمستوى Android API: 16 (Jelly Bean)

- مفتاح الإدخال (انظر التعليمات أدناه لمعرفة كيفية الحصول عليه)

## <a name="integrate-the-sdk-into-your-application"></a>دمج SDK في التطبيق
ابدأ العملية من خلال تحديد مساحة عمل للعمل بها، وتحديد النظام الأساسي المحمول لـ Android وتنزيل Android SDK.

- استخدم مفتاح تبديل مساحة العمل في جزء التنقل الأيسر لتحديد مساحة العمل الخاصة بك.

- إذا لم يكن لديك مساحة عمل موجودة، فحدد **مساحة عمل جديدة** واتبع الخطوات اللازمة لإنشاء [مساحة عمل جديدة](create-workspace.md).

- بعد إنشاء مساحة عمل، انتقل إلى **المسؤول** > **مساحة العمل**، ثم حدد **دليل التثبيت**.

## <a name="configure-the-sdk"></a>تكوين SDK

وبمجرد تنزيل SDK، يمكنك العمل معه في Android Studio لتمكين الأحداث وتحديدها. هناك طريقتان للقيام بذلك:
### <a name="option-1-use-jitpack-recommended"></a>الخيار 1: استخدام JitPack (مستحسن)
1. أضف مستودع JitPack إلى الجذر الخاص بك `build.gradle`:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. أضف التبعية:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>الخيار 2. استخدام ارتباط التنزيل
1. قم بتنزيل [Android SDKلمعلومات المشاركة](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip)، وضع ملف `eiandroidsdk-debug.aar` في مجلد `libs`.

1. افتح ملف `build.gradle` على مستوى المشروع وأضف المقتطفات التالية:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

## <a name="enable-auto-instrumentation"></a>تمكين الأدوات التلقائية

1. أضف إذن للشبكة والإنترنت في ملف `AndroidManifest.xml` الخاص بك والموجود ضمن مجلد `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. قم بإعداد تكوين SDK لمعلومات المشاركة من خلال ملف `AndroidManifest.xml` الخاص بك.

1. انسخ قصاصة XML البرمجية من **دليل التثبيت**. يجب تعبئة `Your-Ingestion-Key` تلقائيًا.

   > [!NOTE]
   > لست بحاجة إلى استبدال قسم `${applicationId}`. يتم ملؤه تلقائيًا.


   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. قم بتمكين أو تعطيل الالتقاط التلقائي لـ `View` الأحداث عن طريق تعيين حقل `autoCapture` إلى `true` أو `false`. 

   >[!NOTE]
   >يجب إضافة أحداث `Action` بشكل يدوي.

1. (اختياري) تتضمن التكوينات الأخرى تعيين عنوان URL لمجمع نقطة النهاية. يمكن إضافتها ضمن بيانات تعريف مفتاح الإدخال في `AndroidManifest.xml`:

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>تنفيذ الأحداث المخصصة

بعد تهيئة SDK، يمكنك العمل مع الأحداث خصائصها في بيئة `MainActivity`.


Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>تعيين الخاصية لكل الأحداث (اختياري)

Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

يتم دعم الأنواع التالية لخصائص أحداث السياق:
- السلسلة‬
- التاريخ‬
- مزدوج
- طويل
- Boolean
- UUID

### <a name="track-an-event"></a>تعقب حدث

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>تعيين تفاصيل المستخدم للحدث الخاص بك (اختياري)

يتيح SDK تعريف معلومات المستخدم التي يمكن إرسالها مع كل حدث. يمكنك تحديد معلومات المستخدم من خلال استدعاء واجهة برمجة تطبيقات `setUser(user: User)` على مستوى `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

وتحتوي فئة بيانات `User` على خصائص السلسلة التالية:

- **localId**: معرف المستخدم المحلي.
- **authId**: معرف المستخدم المصادق عليه.
- **authType**: نوع المصادقة المستخدم للحصول على معرف المستخدم المصادق عليه.
- **الاسم**: اسم المستخدم.
- **البريد الإلكتروني**: عنوان البريد الإلكتروني للمستخدم

[!INCLUDE[footer-include](../includes/footer-banner.md)]
