---
title: التعرف على أحداث الويب من الزائرين المصادق عليهم مسبقًا باستخدام ميزة ‏‫من غير معروف إلى معروف
description: تتيح لك ميزة ‏‫من غير معروف إلى معروف إقران الأحداث على موقع ويب بالزائرين الذين تمت مصادقتهم مسبقًا.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036767"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>التعرف على أحداث الويب من الزائرين المصادق عليهم مسبقًا

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

تتيح الميزة **من غير معروف إلى معروف** في إمكانية معلومات المشاركة على ربط الأحداث على موقع الويب بالزائرين الذين تمت مصادقتهم مسبقًا. إذا تم تعطيل الميزة، فلن يتم تحديد الزائرين الذين صادقوا خلال زيارة سابقة ثم غادروا إذا لم يقوموا بالمصادقة مرة أخرى عند العودة. 

على سبيل المثال، قام شخص ما بزيارة أحد مواقع الويب الأسبوع الماض ، وقام بتسجيل الدخول إلى حساب المستخدم الخاص به على الموقع، واستعرض كتالوج المنتجات. يرجع الشخص خلال الأسبوع التالي لاستعراض مزيد من المنتجات دون تسجيل الدخول إلى حسابه. سيعرف مالك الموقع الذي يستخدم الميزة **من غير معروف إلى معروف** أن نفس الشخص قد عاد مرة أخرى وما هو الذي قاموا باستعراضه على الموقع. ويسمح ذلك بإعداد تقارير أكثر دقة وتحليل لأنشطة الموقع.

## <a name="enable-unknown-to-known"></a>تمكين الميزة "من غير معروف إلى معروف"

يجب أن تكون [مسؤول مساحة العمل](user-roles.md) لتمكين هذه الميزة. 

1. في معلومات المشاركة، انتقل إلى **مسؤول** > **مساحة عمل**. 
2. حدد علامة التبويب **إعدادات**.
3. في القسم **من غير معروف إلى معروف**، قم بتعيين التبديل إلى **تمكين**.

![تمكين الميزة "من غير معروف إلى معروف"](media/U2Ktoggle.png "تمكين الميزة &quot;من غير معروف إلى معروف&quot;")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>إضافة تعليمات برمجية لـ JavaScript إلى قصاصة التعليمات البرمجية تعقب موقعك

يمكن لأي موقع ويب التقاط **user authId** مع عينة JavaScript التالية باستخدام [معلومات مشاركة الويب SDK](advanced-SDK-implementation.md) لكي تعمل ميزة **من غير معروف إلى معروف**، يلزمك التقاط معرّف المصادقة *و* تمكين تعيين المستخدم: صحيح في قصاصة JavaScript الخاصة بك كما في النموذج أدناه.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
