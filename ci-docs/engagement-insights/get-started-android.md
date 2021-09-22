---
title: الشروع في العمل باستخدام Android SDK
description: تعرف على كيفية تخصيص وتشغيل Android SDK
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036902"
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

## <a name="step-1-integrate-the-sdk-into-your-application"></a>الخطوة 1. دمج SDK في التطبيق
ابدأ العملية من خلال تحديد مساحة عمل للعمل بها، وتحديد النظام الأساسي المحمول لـ Android وتنزيل Android SDK.

- استخدم مفتاح تبديل مساحة العمل في جزء التنقل الأيسر لتحديد مساحة العمل الخاصة بك.

- إذا لم يكن لديك مساحة عمل موجودة، فحدد **مساحة عمل جديدة** واتبع الخطوات اللازمة لإنشاء [مساحة عمل جديدة](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>الخطوة 2. تكوين SDK

1. بعد إنشاء مساحة عمل، انتقل إلى **المسؤول** > **مساحة العمل**، ثم حدد **دليل التثبيت**. 

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

1. إعداد تكوين SDK لمعلومات المشاركة من خلال ملف `AndroidManifest.xml` الخاص بك الموجود ضمن مجلد `manifests`. 
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

1. (اختياري) تتضمن التكوينات الأخرى تعيين عنوان URL لمجمع نقطة النهاية. يمكن إضافتها ضمن بيانات تعريف مفتاح الإدخال في `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>الخطوة 3. تهيئة SDK من MainActivity 

بعد تهيئة SDK، يمكنك العمل مع الأحداث خصائصها في بيئة MainActivity.

    
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

### <a name="set-user-details-for-your-event-optional"></a>تعيين تفاصيل المستخدم للحدث الخاص بك (اختياري)

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
