---
title: جلب Azure key vault الخاص بك لإدارة الأسرار
description: تعرف على كيفية تكوين Customer Insights لاستخدام Azure key vault الخاص بك.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 418575f724090628da8bd01e2569a4cb9e646337
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376492"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>جلب Azure key vault الخاص بك (إصدار أولي)

يساعد ربط [Azure key vault](/azure/key-vault/general/basic-concepts) ببيئة رؤى الجمهور المؤسسات لتلبية متطلبات الامتثال.
يمكن استخدام مخزن المفاتيح المخصص لتنظيم الأسرار واستخدامها في حدود امتثال المؤسسة. يمكن لرؤى الجمهور استخدام الأسرار الموجودة في Azure Key Vault [لإعداد الاتصالات](connections.md) بأنظمة الجهات الخارجية.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>ربط المخزن الرئيسي ببيئة رؤى الجمهور

### <a name="prerequisites"></a>المتطلبات الأساسية

لتكوين المخزن الأساسي في رؤى الجمهور، يجب تلبية المتطلبات التالية:

- لديك اشتراك Azure نشط.

- لديك دور [المسؤول](permissions.md#admin) في معلومات الجمهور. لمعرفة المزيد [أذونات المستخدم في رؤى الجمهور](permissions.md#assign-roles-and-permissions).

- لديك أدوار [المساهم](/azure/role-based-access-control/built-in-roles#contributor) و[مسؤول وصول المستخدم](/azure/role-based-access-control/built-in-roles#user-access-administrator) في المخزن الرئيسي أو مجموعة الموارد التي ينتمي إليها المخزن الرئيسي. لمزيد من المعلومات، راجع [إضافة أو إزالة تعيينات أدوار Azure باستخدام مدخل Azure](/azure/role-based-access-control/role-assignments-portal). إذا لم يكن لديك دور مسؤول وصول المستخدم في مخزن المفاتيح، فيجب عليك إعداد أذونات التحكم في الوصول المستند إلى الدور لمدير خدمة Azure لـ Dynamics 365 Customer Insights بشكل منفصل. اتبع الخطوات [لاستخدام مدير خدمة Azure](connect-service-principal.md) للمخزن الرئيسي الذي يجب ربطه.

- يجب أن يحتوي المخزن الرئيسي على جدار حماية Key Vault في حالة **ممكّن**.

- يوجد المخزن الرئيسي في نفس [موقع Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) مثل بيئة رؤى الجمهور. منطقة البيئة في رؤى الجمهور مدرجة ضمن **المسؤول** > **النظام** > **حول** > **المنطقة**.

### <a name="link-a-key-vault-to-the-environment"></a>ربط مخزن رئيسي بالبيئة

1. انتقل إلى **المسؤول** > **النظام**، ثم حدد علامة التبويب **الأمان**.
1. في تجانب **Key Vault**، حدد **إعداد**.
1. اختر **اشتراكًا**.
1. اختر مخزنًا رئيسيًا من القائمة المنسدلة **Key Vault**. في حالة ظهور عدد كبير جدًا من المخازن الرئيسية، حدد مجموعة موارد للحد من نتائج البحث.
1. اقبل بيان **خصوصية البيانات وتوافقها**.
1. حدد **حفظ**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="خطوات إعداد مخزن رئيسي مرتبط في رؤى الجمهور.":::

يوضح تجانب **Key Vault** اسم المخزن الرئيسي المرتبط ومجموعة الموارد والاشتراك. إنه جاهز للاستخدم في إعداد الاتصال.
للحصول على تفاصيل حول الأذونات في المخزن الرئيسي التي يتم منحها لرؤى الجمهور، انتقل إلى[الأذونات الممنوحة في المخزن الرئيسي لرؤى الجمهور](#permissions-granted-on-the-key-vault-to-audience-insights)، لاحقًا في هذه المقالة.

## <a name="use-the-key-vault-in-the-connection-setup"></a>استخدام المخزن الرئيسي في إعداد الاتصال

عند [إعداد الاتصال](connections.md) بأنظمة الجهات الخارجية، يمكن استخدام الأسرار من Key Vault المرتبط لتكوين الاتصالات.

1. انتقل إلى **المسؤول** > **الاتصالات**.
1. حدد **إضافة اتصال**.
1. بالنسبة لأنواع الاتصال المدعومة، يتوفر تبديل **استخدام Key Vault** إذا قمت بالربط بمخزن رئيسي.
1. بدلاً من إدخال السر يدويًا، يمكنك اختيار الاسم السري الذي يشير إلى القيمة السرية في المخزن الرئيسي.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="جزء الاتصال مع اتصال SFTP الذي يستخدم سر Key Vault.":::

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>الأذونات الممنوحة في المخزن الأساسي لرؤى الجمهور

يتم منح الأذونات التالية لرؤى الجمهور في مخزن رئيسي مرتبط في حالة تمكين إما [سياسة الوصول إلى Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) أو تمكين [عنصر التحكم في الوصول المستند إلى دور Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

### <a name="key-vault-access-policy"></a>سياسة الوصول إلى Key Vault

| النوع        | الأذونات          |
| ----------- | -------------------- |
| مفتاح         | [الحصول على المفاتيح](/rest/api/keyvault/get-keys)، [الحصول على المفتاح](/rest/api/keyvault/get-key)                                 |
| سر      | [الحصول على الأسرار](/rest/api/keyvault/get-secrets)، [الحصول على السر](/rest/api/keyvault/get-secret)                     |
| شهادة | [الحصول على الشهادات](/rest/api/keyvault/get-certificates)، [الحصول على الشهادة](/rest/api/keyvault/get-certificate) |

القيم السابقة هي الحد الأدنى لسردها وقراءتها أثناء التنفيذ.

### <a name="azure-role-based-access-control"></a>عنصر تحكم الوصول المستند إلى دور Azure

ستتم إضافة أدوار مستخدم قارئ Key Vault وأسرار Key Vault لرؤى الجمهور. للحصول على تفاصيل حول هذه الأدوار، انتقل إلى [الأدوار المضمنة في Azure لعمليات مستوى بيانات Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>التوصيات

- استخدم المخزن الرئيسي المنفصل أو المخصص الذي يحتوي فقط على الأسرار المطلوبة لرؤى الجمهور. اقرأ المزيد حول [سبب التوصية بالمخازن الرئيسية المنفصلة](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- اتبع [أفضل الممارسات لاستخدام Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) للتحكم في خيارات الوصول والنسخ الاحتياطي والتدقيق والاسترداد.

## <a name="frequently-asked-questions"></a>الأسئلة الشائعة

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>هل تستطيع رؤى الجمهور كتابة أسرار أو استبدالها في المخزن الرئيسي؟

لا. تم فقط منح أذونات القراءة والقائمة الموضحة في قسم [الأذونات الممنوحة](#permissions-granted-on-the-key-vault-to-audience-insights) لاحقًا في هذه المقالة لرؤى الجمهور. لا يمكن للنظام إضافة أو حذف أو الكتابة فوق الأسرار الموجودة في المخزن الرئيسي. وهذا أيضًا هو سبب عدم قدرتك على إدخال بيانات الاعتماد عندما يستخدم الاتصال Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>هل يمكنني تغيير الاتصال من استخدام أسرار Key Vault إلى المصادقة الافتراضية؟

لا. لا يمكنك العودة إلى اتصال افتراضي بعد تكوينه باستخدام سر من مخزن رئيسي مرتبط. أنشئ اتصالاً منفصلاً واحذف الاتصال القديم إذا لم تعد بحاجة إليه.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>كيف يمكنني إبطال الوصول إلى مخزن رئيسي لرؤى الجمهور؟

اعتمادًا على ما إذا كان تم تمكين [سياسة الوصول إلى Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) أو [التحكم في الوصول المستند إلى دور Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli)، تحتاج إلى إزالة أذونات مدير الخدمة `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` بالاسم `Dynamics 365 AI for Customer Insights`. ستتوقف جميع الاتصالات التي تستخدم المخزن الرئيسي عن العمل.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>تمت إزالة السر المستخدم في الاتصال من المخزن الرئيسي. ماذا يمكنني أن أفعل؟

يظهر إشعار في رؤى الجمهور عندما يتعذر الوصول إلى سر تم تكوينه من المخزن الرئيسي بعد الآن. قم بتمكين [الحذف البرمجي](/azure/key-vault/general/soft-delete-overview) في المخزن الرئيسي لاستعادة الأسرار إذا تم إزالتها عن طريق الخطأ.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>اتصال لا يعمل، لكن سري في المخزن الرئيسي. ماذا قد يكون السبب؟

يظهر إشعار في رؤى الجمهور عندما يتعذر عليه الوصول إلى المخزن الرئيسي. قد يكون السبب:

- تمت إزالة أذونات مدير خدمة رؤى الجمهور. يجب استعادتها يدويًا.

- تم تمكين جدار الحماية الموجود في المخزن الرئيسي. يجب تعطيل جدار الحماية لإتاحة الوصول إلى المخزن الرئيسي لرؤى الجمهور مرة أخرى.
