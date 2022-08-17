---
title: جلب Azure key vault الخاص بك (إصدار أولي)
description: تعرف على كيفية تكوين Customer Insights لاستخدام Azure key vault الخاص بك لإدارة الأسرار.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246139"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>جلب Azure key vault الخاص بك (إصدار أولي)

يساعد ربط [Azure key vault](/azure/key-vault/general/basic-concepts) إلى بيئة Customer Insights تساعد المؤسسات على تلبية متطلبات الامتثال.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>ربط المخزن الرئيسي ببيئة Customer Insights

قم بإعداد مخزن المفاتيح المخصص لوضع الأسرار واستخدمها في حدود امتثال المؤسسة.

### <a name="prerequisites"></a>المتطلبات

- اشتراك Azure نشط.

- [دور](permissions.md#admin) المسئول [المكلف](permissions.md#add-users) في Customer Insights.

-   [المساهم](/azure/role-based-access-control/built-in-roles#contributor) و[مسؤول وصول المستخدم](/azure/role-based-access-control/built-in-roles#user-access-administrator) في المخزن الرئيسي أو مجموعة الموارد التي ينتمي إليها المخزن الرئيسي. لمزيد من المعلومات، راجع [إضافة أو إزالة تعيينات أدوار Azure باستخدام مدخل Azure](/azure/role-based-access-control/role-assignments-portal). إذا لم يكن لديك دور مسؤول وصول المستخدم في مخزن المفاتيح ، فقم بإعداد أذونات التحكم في الوصول المستند إلى الدور لمدير خدمة Azure لـ Dynamics 365 Customer Insights بشكل منفصل. اتبع الخطوات [لاستخدام مدير خدمة Azure](connect-service-principal.md) للمخزن الرئيسي الذي يجب ربطه.

- يجب أن يحتوي مخزن المفاتيح على جدار حماية Key Vault **ممكّن**.

- يوجد المخزن الرئيسي في نفس [موقع Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) مثل بيئة Customer Insights. في Customer Insights، انتقل إلى **المسئول** > **النظام** و **علامة التبويب لمحة** لعرض منطقة البيئة.

### <a name="recommendations"></a>التوصيات

- [استخدم المخزن الرئيسي المنفصل أو المخصص](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) اللذي يحتوي فقط على الأسرار المطلوبة لـ Customer Insights.

- اتبع [أفضل الممارسات لاستخدام Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) للتحكم في خيارات الوصول والنسخ الاحتياطي والتدقيق والاسترداد.

### <a name="link-a-key-vault-to-the-environment"></a>ربط مخزن رئيسي بالبيئة

1. انتقل إلى **المسؤول** > **الأمان**، ثم حدد علامة التبويب **Key Vault**.
1. في تجانب **Key Vault**، حدد **إعداد**.
1. اختر **اشتراكًا**.
1. اختر مخزنًا رئيسيًا من القائمة المنسدلة **Key Vault**. في حالة توفر عدد كبير جدًا من خزائن المفاتيح ، حدد مجموعة موارد للحد من نتائج البحث.
1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.
1. حدد **حفظ.**.

يوضح تجانب **Key Vault** يعرض المربع اسم مخزن المفاتيح المرتبط والاشتراك ومجموعة الموارد. إنه جاهز للاستخدم في إعداد الاتصال.
للحصول على تفاصيل حول الأذونات في key vault التي يتم منحها لـ Customer Insights، انتقل إلى [الأذونات الممنوحة في key vault](#permissions-granted-on-the-key-vault)،

## <a name="use-the-key-vault-in-the-connection-setup"></a>استخدام المخزن الرئيسي في إعداد الاتصال

عند [‎إعداد الاتصال](connections.md) إلى [طرف ثالث معتمد](#supported-connection-types) الأنظمة ، استخدم الأسرار من Key Vault المرتبط لتهيئة الاتصالات..

1. انتقل إلى **المسؤول** > **الاتصالات**.
1. حدد **إضافة اتصال**.
1. بالنسبة لأنواع الاتصال المدعومة، يتوفر تبديل **استخدام Key Vault** إذا قمت بالربط بمخزن رئيسي.
1. بدلاً من إدخال السر يدويًا ، اختر الاسم السري الذي يشير إلى القيمة السرية في خزينة المفاتيح.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="جزء الاتصال مع اتصال SFTP الذي يستخدم سر Key Vault.":::

1. حدد **حفظ** لإنشاء الاتصال.

## <a name="supported-connection-types"></a>أنواع الاتصال المدعومة

اتصالات [التصدير](export-destinations.md) التالية مدعومة:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>الأذونات الممنوحة في key vault

يتم منح الأذونات التالية لـ Customer Insights في key vault المرتبط في حالة تمكين إما [سياسة الوصول إلى Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) أو تمكين [عنصر التحكم في الوصول المستند إلى دور Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

### <a name="key-vault-access-policy"></a>سياسة الوصول إلى Key Vault

| النوع        | الأذونات          |
| ----------- | -------------------- |
| مفتاح         | [الحصول على المفاتيح](/rest/api/keyvault/keys/get-keys/get-keys)، [الحصول على المفتاح](/rest/api/keyvault/keys/get-key/get-key)                                 |
| سر      | [الحصول على الأسرار](/rest/api/keyvault/secrets/get-secrets/get-secrets)، [الحصول على السر](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| شهادة | [الحصول على الشهادات](/rest/api/keyvault/certificates/get-certificates/get-certificates)، [الحصول على الشهادة](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

القيم السابقة هي الحد الأدنى لسردها وقراءتها أثناء التنفيذ.

### <a name="azure-role-based-access-control"></a>عنصر تحكم الوصول المستند إلى دور Azure

ستتم [إضافة أدوار مستخدم قارئ Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli) وأسرار Key Vault لـ Customer Insights.

## <a name="frequently-asked-questions"></a>الأسئلة المتداولة

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>هل تستطيع Customer Insights كتابة أسرار أو استبدالها في key vault؟

لا. تم فقط منح أذونات القراءة والقائمة الموضحة في قسم [الأذونات الممنوحة](#permissions-granted-on-the-key-vault) لـ Customer Insights. لا يمكن للنظام إضافة أو حذف أو الكتابة فوق الأسرار الموجودة في المخزن الرئيسي. وهذا أيضًا هو سبب عدم قدرتك على إدخال بيانات الاعتماد عندما يستخدم الاتصال Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>هل يمكنني تغيير الاتصال من استخدام أسرار Key Vault إلى المصادقة الافتراضية؟

لا. لا يمكنك العودة إلى اتصال افتراضي بعد تكوينه باستخدام سر من مخزن رئيسي مرتبط. أنشئ اتصالاً منفصلاً واحذف الاتصال القديم إذا لم تعد بحاجة إليه.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>كيف يمكنني إبطال الوصول إلى مخزن رئيسي لـ Customer Insights؟

اعتمادًا على ما إذا كان تم تمكين [سياسة الوصول إلى Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) أو [Azure التحكم في الوصول المستند إلى الدور](/azure/key-vault/general/rbac-guide?tabs=azure-cli)، تحتاج إلى إزالة أذونات مدير الخدمة `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` بالاسم `Dynamics 365 AI for Customer Insights`. ستتوقف جميع الاتصالات التي تستخدم المخزن الرئيسي عن العمل.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>تمت إزالة السر المستخدم في الاتصال من المخزن الرئيسي. ماذا يمكنني أن أفعل؟

يظهر إشعار في Customer Insights عندما يتعذر الوصول إلى سر تم تكوينه من المخزن الرئيسي بعد الآن. قم بتمكين [الحذف البرمجي](/azure/key-vault/general/soft-delete-overview) في المخزن الرئيسي لاستعادة الأسرار إذا تم إزالتها عن طريق الخطأ.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>اتصال لا يعمل، لكن سري في المخزن الرئيسي. ماذا قد يكون السبب؟

يظهر إشعار في Customer Insights عندما يتعذر عليه الوصول إلى key vault. قد يكون السبب:

- تمت إزالة أذونات مدير خدمة Customer Insights. يجب استعادتها يدويًا.

- تم تمكين جدار الحماية الموجود في المخزن الرئيسي. يجب تعطيل جدار الحماية لإتاحة الوصول إلى key vault لـ Customer Insights مرة أخرى.
