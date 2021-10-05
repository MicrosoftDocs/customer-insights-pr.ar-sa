---
title: سيناريوهات SDK ويب متقدمة
description: سيناريوهات متقدمة يجب مراعاتها عند استخدام أداة موقع الويب الخاص بك باستخدام SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 4c6646ecadbb604000d6c95b685cf6e420969a6d
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558685"
---
# <a name="advanced-web-sdk-instrumentation"></a>أجهزة SDK متقدمة على الويب

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

ترشدك هذه المقالة خلال سيناريوهات متقدمة لتراعيها عند [استخدام أداة موقع الويب الخاص بك](instrument-website.md) باستخدام إمكانية رؤية المشاركة SDK Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>إعداد تفاصيل المستخدم للحدث

يتيح SDK تعريف معلومات المستخدم التي يمكن إرسالها مع كل حدث. يمكنك تحديد تفاصيل المستخدم في خاصية تسمى `user` (البيانات المتوقعة لهذه الخاصية هي الكائن `IUser`)، على غرار `src`، و`name` و`cfg` في تكوين قصاصة برمجية.

يحتوي الكائن `IUser` على خصائص السلسلة التالية:

- **localId**: معرف المستخدم المحلي.
- **authId**: معرف المستخدم المصادق عليه.
- **authType**: نوع المصادقة المستخدمة للحصول على معرف المستخدم المصادقة.
- **الاسم**: اسم المستخدم.
- **البريد الإلكتروني**: عنوان البريد الإلكتروني للمستخدم

يوضح المثال التالي قصاصة برمجية إرسال معلومات المستخدم. عندما ترى الوظائف التي يسبقها رمز * النجمة، استبدل الوظيفة بتنفيذك المخصص:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

يمكنك أيضًا تحديد معلومات المستخدم من خلال استدعاء واجهة برمجة تطبيقات `setUser(user: IUser)`. سوف يحتوي قياس تتبع الاستخدام المرسل بعد استدعاء واجهة برمجة تطبيقات `setUser` على معلومات المستخدم.

## <a name="adding-custom-properties-for-each-event"></a>إضافة خصائص مخصصة لكل حدث

يتيح SDK تحديد الخصائص المخصصة التي يمكن إرسالها مع كل حدث. يمكنك تحديد الخصائص المخصصة ككائن يحتوي على أزواج قيمة المفتاح (يمكن أن تكون القيمة من النوع `string | number | boolean`). يمكنك إضافة الكائن في خاصية تسمى `props`، مشابهة لـ `src`، و`name`، و`cfg` في تكوين القصاصة البرمجية.

يوضح المثال التالي قصاصة برمجية إرسال الخصائص المخصصة:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

يمكنك أيضًا تحديد خصائص مخصصة بشكل فردي عن طريق استدعاء واجهة برمجة تطبيقات `setProperty(name: string, value: string | number | boolean)`.

## <a name="sending-custom-events"></a>إرسال أحداث مخصصة

يمكنك استخدام SDK لإرسال أحداث مخصصة. يجب تحديد اسم للحدث والخصائص التي سيتم إرسالها مع الحدث.

يوضح المثال التالي قصاصة برمجية تتبع حدث مخصص. "NAME" هي القيمة الموجودة في المفتاح `name` في تكوين قصاصة برمجية. كما أنه اسم المتغير في كائن الإطار حيث يتم تحميل SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
