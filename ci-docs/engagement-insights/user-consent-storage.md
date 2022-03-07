---
title: إدارة ملفات تعريف الارتباط وموافقة المستخدم لتخزين بيانات المستخدم في Dynamics 365 Customer Insights
description: افهم كيفية استخدام ملفات تعريف الارتباط وموافقة المستخدم لتحديد زائري موقع الويب.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228969"
---
# <a name="manage-cookies-and-user-consent"></a>إدارة ملفات تعريف الارتباط وموافقة المستخدم

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

تستخدم إمكانية معلومات مشاركة Dynamics 365 Customer Insights ملفات تعريف الارتباط ومفاتيح (`localStorage`) لتحديد زائري موقع الويب.

ملفات تعريف الارتباط هي ملفات صغيرة تقوم بتخزين معلومات صغيرة حول تفاعل المستخدم مع موقع الويب. يتم تخزينها في مستعرضات الويب. عندما يقوم المستخدمون بزيارة موقع ويب الذي قام المستخدمون بتخزين ملفات تعريف الارتباط له، يقوم المستعرض بإرسال هذه المعلومات إلى الخادم، والذي يقوم بإرجاع معلومات فريدة للمستخدم. هذه هي التقنية التي تسمح، على سبيل المثال، لمستخدم عبر الإنترنت بالإبقاء على عناصر محددة فيه حتى إذا انتقل أحد المستخدمين من موقع الويب.

## <a name="user-consent"></a>موافقة المستخدم

[اللائحة العامة لحماية البيانات (GDPR)](/dynamics365/get-started/gdpr/)هي اللائحة الخاصة بالاتحاد الأوروبي (EU) التي تتعامل مع الكيفية التي ينبغي على المؤسسات من خلالها التعامل مع خصوصية المستخدمين والأمان لديهم. عادة ما تقوم ملفات تعريف الارتباط بتخزين "البيانات الشخصية" أو تجميعها، مثل المعرف عبر الإنترنت، الذي يغطيه المعرف .. إذا كان عملك يوظف و/أو يبيع إلى موضوعات بيانات الاتحاد الأوروبي، يؤثر عليك .. [تعرف على المزيد حول كيفية مساعدة Microsoft لك في الامتثال إلى هذه المعلومات](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

للسماح رؤى الارتباط SDK بتخزين ملفات تعريف الارتباط أو المعلومات الحساسة الأخرى، يجب تحديد ما إذا كان المستخدمون قد وافقوا أم لا. يحدث هذا عند تهيئة SDK عن طريق تعيين حقل `userConsent` في التكوين.

وفي حالة الإشارة إلى عدم وجود موافقة المستخدم، لن تقوم SDK بتخزين أية بيانات ولن تقوم بإرسال الأحداث التي يمكن استخدامها لتعقب سلوك المستخدم. سيتم حذف أية بيانات تم تخزينها مسبقا من المستعرض.

وفي حالة عدم تحديد قيمة موافقة المستخدم، ستفترض SDK أن المستخدم قد وافق. وهذا يعني أنك (كعميلنا) لا تحدد قيمة لموافقة المستخدم في SDK، سيتم جمع البيانات. ومع ذلك، إذا تم تحديد أن قيمة موافقة المستخدم بحاجة إلى أن تكون "صحيحة"، فلن يتم جمع البيانات إذا قام المستخدم برفض الموافقة الصريحة أو فشل في تقديم الموافقة الصريحة.

فيما يلي قصاصة برمجية لتهيئة SDK على الويب بموافقة المستخدم:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>تخزين بيانات الزائر في إمكانية رؤى الارتباط

### <a name="cookies"></a>بسكويت

- _msei
    - يقوم بتخزين هوية المستخدم المجهول. يتم تعيين ملف تعريف الارتباط في مجال العميل وينتهي صلاحيته خلال 365 يوما.

### <a name="local-storage"></a>التخزين المحلي

كما تستخدم إمكانية معلومات المشاركة مفاتيح (`localStorage`) لتعقب البيانات غير الحساسة. يتم تخزين هذه البيانات بالكامل في المستعرض نفسه، دون إرسال أي حركة بيانات إلى أو من الخوادم الخاصة بك.

- *EISession.Id*
    - تخزين معلومات حول جلسة عمل المستخدم المستمرة، مثل معرف جلسة العمل، ومتى بدأت، ومتى تنتهي صلاحيتها.
- *EISession.Previous*
    - يقوم بتخزين عنوان URL للصفحة التي تم زيارتها مسبقا في الجلسة الحالية.

لا تنتهي صلاحية المفاتيح في مساحة التخزين المحلية تلقائيًا، وسوف يتم إعادة تعيينها أثناء جلسة عمل SDK التالية.

## <a name="deleting-cookies"></a>حذف ملفات تعريف الارتباط

يمكن لعملائك حذف ملفات تعريف الارتباط ومفاتيح التخزين المحلية يدويا في أي وقت من خلال إعدادات المستعرضات الخاصة بهم.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
