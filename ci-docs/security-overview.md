---
title: تكوين إعدادات الأمان
description: تعرف على إعدادات الأمان في Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387233"
---
# <a name="configure-security-settings"></a>تكوين إعدادات الأمان

قم بإدارة مفاتيح API والوصول إلى بيانات العملاء بإعداد ارتباط Azure الخاص.

## <a name="manage-api-keys"></a>إدارة مفاتيح API

عرض المفاتيح وإدارتها لاستخدام [واجهات برمجة التطبيقات في Customer Insights](apis.md) مع البيانات الموجودة في بيئتك..

1. انتقل إلى **المسؤول** > **الأمن**، ثم حدد علامة التبويب **APIs‎**.

1. إذا لم يتم إعداد وصول API إلى البيئة، حدد **تمكين**. أو ، لحظر وصول API إلى البيئة ، حدد **تعطيل** ثم قم بالتأكيد.

1. قم بإدارة مفاتيح API الأساسية والتعليمية:

   1. لعرض مفتاح API الرئيسي أو الثانوي، حدد الرمز **إظهار**.

   1. لنسخ مفتاح API الرئيسي أو الثانوي، حدد الرمز **نسخ**.

   1. لإنشاء مفاتيح API أساسية أو ثانوية جديدة ، حدد **إعادة إنشاء مفتاح أساسي** أو **إعادة إنشاء مفتاح ثانوي**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>الوصول الآمن إلى بيانات العميل باستخدام مربع تأمين العميل (إصدار أولي)

يستخدم Customer Insights إمكانية مربع تأمين العميل في Power Platform. يوفر مربع تأمين العميل واجهة لمراجعة طلبات الوصول إلى البيانات (أو رفضها) والموافقة عليها. تحدث هذه الطلبات عندما يكون الوصول إلى بيانات العميل مطلوبًا لحل حالة دعم. لاستخدام هذه الميزة، يجب أن يتوفر لدى Customer Insights اتصال موجود ببيئة Microsoft Dataverse في المستأجر.

لمزيد من المعلومات حول مربع تأمين العميل، راجع [ملخص](/power-platform/admin/about-lockbox#summary) مربع تأمين العميل في Power Platform. يصف هذا المقال أيضًا [سير العمل](/power-platform/admin/about-lockbox#workflow) و[الإعداد](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) المطلوب‏‎ لتمكين مربع تأمين العميل.

> [!IMPORTANT]
> بإمكان مسؤولي Power Platform العموميين أو مسؤولي Power Platform الموافقة على طلبات مربع تأمين العميل الصادرة لـ Customer Insights.

## <a name="set-up-an-azure-private-link"></a>إعداد ارتباط Azure الخاص

يسمح [Azure Private Link](/azure/private-link/private-link-overview) لـ Customer Insights بالاتصال بحسابك في Azure Data Lake Storage عبر نقطة نهاية خاصة في شبكتك الظاهرية. فيما يتعلق بالبيانات الموجودة في حساب تخزين، لا يظهر على الإنترنت العام، يمكّن الارتباط الخاص الاتصال بهذه الشبكة المقيدة.

> [!IMPORTANT]
> الحد الأدنى لمتطلبات الدور لإعداد اتصال ارتباط خاص:
>
> - Customer Insights: المسؤول
> - دور Azure المضمن: [مساهم في حساب التخزين](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - أذونات لدور Azure المخصص: [Microsoft.Storage/storageAccounts/read and Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. في Customer Insights، انتقل إلى **أمان** > **المشرف** وحدد علامة التبويب **روابط خاصة**.

1. حدد **إضافة ارتباط خاص**.

   يسرد الجزء **إضافة ارتباط خاص** حسابات التخزين من المستأجر الذي لديك أذونات لرؤيته.

1. حدد الاشتراك ومجموعة الموارد وحساب التخزين.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **حفظ.**.

1. انتقل إلى حساب مساحة تخزين البيانات المعروضة على الشاشة وافتح الارتباط المعروض على الشاشة.

1. موافقة الارتباط الخاص.


[!INCLUDE [footer-include](includes/footer-banner.md)]
