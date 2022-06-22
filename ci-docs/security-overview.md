---
title: إعدادات الأمان في Customer Insights
description: تعرف على إعدادات الأمان في Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947399"
---
# <a name="security-settings-in-customer-insights"></a>إعدادات الأمان في Customer Insights

تسرد **الأمان** خيارات لتكوين أذونات المستخدم والميزات التي تساعد في جعل Dynamics 365 Customer Insights أكثر أمانًا. يمكن للمسؤولين فقط الوصول إلى هذه الصفحة.

انتقل إلى **المسؤول** > **الأمان** لتكوين الإعدادات.

تتضمن صفحة **الأمان** علامات التبويب التالية:

- [المستخدمون](#users-tab)
- [واجهات API](#apis-tab)
- [ارتباطات خاصة](#private-links-tab)
- [Key Vault](#key-vault-tab)
- [الوصول الآمن إلى بيانات العميل باستخدام مربع تأمين العميل (إصدار أولي)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>علامة التبويب "المستخدمين"

يقتصر الوصول إلى Customer Insights على المستخدمين في مؤسستك الذين أضافهم أحد المسؤولين إلى التطبيق. وتتيح لك علامة التبويب **المستخدمين** إدارة وصول المستخدمين وأذوناتهم. لمزيد من المعلومات، راجع [أذونات المستخدم](permissions.md).

## <a name="apis-tab"></a>علامة التبويب "واجهات برمجة التطبيقات"

عرض المفاتيح وإدارتها لاستخدام [واجهات برمجة التطبيقات في Customer Insights](apis.md) باستخدام بيانات بيئتك.

يمكنك إنشاء مفتاحين أساسيين وثانويين جديدين عن طريق تحديد **إعادة إنشاء مفتاح أساسي** أو **إعادة إنشاء مفتاح ثانوي**. 

لحظر وصول واجهة برمجة التطبيقات إلى البيئة، حدد **تعطيل**. إذا كانت واجهات برمجة التطبيقات معطلة، يمكنك تحديد **تمكين** لمنح الوصول مرة أخرى.

## <a name="private-links-tab"></a>علامة التبويب "ارتباطات خاصة"

يسمح [Azure Private Link](/azure/private-link/private-link-overview) لـ Customer Insights بالاتصال بحسابك في Azure Data Lake Storage عبر نقطة نهاية خاصة في شبكتك الظاهرية. فيما يتعلق بالبيانات الموجودة في حساب تخزين، لا يظهر على الإنترنت العام، يمكّن الارتباط الخاص الاتصال بهذه الشبكة المقيدة.

> [!IMPORTANT]
> الحد الأدنى لمتطلبات الدور لإعداد اتصال ارتباط خاص:
>
> - Customer Insights: المسؤول
> - دور Azure المضمن: [مساهم في حساب التخزين](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - أذونات لدور Azure المخصص: [Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

تتكون عملية إعداد ارتباط خاص في Customer Insights من خطوتين. تقوم أولاً بتهيئة إنشاء ارتباط خاص من **المسؤول** > **الأمان** > **ارتباطات خاصة** في Customer Insights. يسرد الجزء **إضافة ارتباط خاص** حسابات التخزين من المستأجر الذي لديك أذونات لرؤيته. حدد حساب التخزين وقدم الموافقة لإنشاء الارتباط الخاص.

بعد ذلك، تحتاج إلى الموافقة على الارتباط الخاص على جانب الحساب Data Lake Storage. افتح الارتباط المعروض على الشاشة للموافقة على الارتباط الخاص الجديد.

## <a name="key-vault-tab"></a>علامة التبويب "Key Vault"

تسمح علامة التبويب **Key Vault** بربط [Azure key vault](/azure/key-vault/general/basic-concepts) الخاصة بك بالبيئة وإدارتها.
يمكن استخدام مخزن المفاتيح المخصص لتنظيم الأسرار واستخدامها في حدود امتثال المؤسسة. يمكن لـ Customer Insights استخدام الأسرار الموجودة في Azure Key Vault [لإعداد الاتصالات](connections.md) بأنظمة الجهات الخارجية.

لمزيد من المعلومات، راجع [جلب Azure key vault الخاص بك](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>الوصول الآمن إلى بيانات العميل باستخدام مربع تأمين العميل (إصدار أولي)

يستخدم Customer Insights إمكانية مربع تأمين العميل في Power Platform. يوفر مربع تأمين العميل واجهة لمراجعة طلبات الوصول إلى البيانات (أو رفضها) والموافقة عليها. تحدث هذه الطلبات عندما يكون الوصول إلى بيانات العميل مطلوبًا لحل حالة دعم. لاستخدام هذه الميزة، يجب أن يتوفر لدى Customer Insights اتصال موجود ببيئة Microsoft Dataverse في المستأجر.

لمزيد من المعلومات حول مربع تأمين العميل، راجع [ملخص](/power-platform/admin/about-lockbox#summary) مربع تأمين العميل في Power Platform. يصف هذا المقال أيضًا [سير العمل](/power-platform/admin/about-lockbox#workflow) و[الإعداد](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) المطلوب‏‎ لتمكين مربع تأمين العميل.

> [!IMPORTANT]
> بإمكان مسؤولي Power Platform العموميين أو مسؤولي Power Platform الموافقة على طلبات مربع تأمين العميل الصادرة لـ Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
