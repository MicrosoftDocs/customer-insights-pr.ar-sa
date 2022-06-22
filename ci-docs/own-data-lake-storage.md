---
title: استخدام حساب Azure Data Lake Storage Gen2
author: mukeshpo
description: تعرف على متطلبات استخدام حسابك Azure Data Lake Storage لتخزين بيانات Customer Insights.
ms.author: mukeshpo
ms.date: 06/08/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 5acb58906c1a9db54337f3b4dc2ab7891db7954e
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011917"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>استخدام حساب Azure Data Lake Storage Gen2

يمنحك Dynamics 365 Customer Insights خيار تخزين جميع البيانات في [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

من خلال حفظ البيانات في Data Lake Storage، فإنك توافق على أنه سيتم نقل البيانات وتخزينها في الموقع الجغرافي المناسب لحساب تخزين Azure هذا. لمزيد من المعلومات، راجع [مركز توثيق Microsoft‬](https://www.microsoft.com/trust-center).

بإمكان المسؤولين في Customer Insights [إنشاء بيئات](create-environment.md) و[تحديد خيار تخزين البيانات](create-environment.md#step-2-configure-data-storage) في العملية.

## <a name="prerequisites-to-use-your-storage-account"></a>المتطلبات الأساسية لاستخدام حساب التخزين

- يجب أن تكون حسابات Azure Data Lake Storage في نفس منطقة Azure التي قمت بتحديدها عند إنشاء بيئة Customer Insights. يمكنك التحقق من منطقة بيئة Customer Insights ضمن **المسؤول‏‎** > **النظام‏‎** > **حول**.
- يجب أن يكون حساب Data Lake Storage من النوع Gen2 وأن تكون ميزة [مساحة الاسم الهرمي](/azure/storage/blobs/create-data-lake-storage-account) ممكّنة فيه. حسابات تخزين Gen1 غير مدعومة.
- يجب أن توجد حاوية تسمى `customerinsights` في حساب التخزين. يجب إنشاؤه قبل استخدام Data Lake Storage في Customer Insights. يحتاج المسؤول الذي يعمل على إعداد بيئة Customer Insights إلى دور قارئ بيانات مخزن البيانات الثنائية الكبيرة أو مساهم بيانات مخزن البيانات الثنائية الكبيرة على حساب التخزين أو حاوية `customerinsights`. لمزيد من المعلومات حول تعيين إذن في حساب تخزين، راجع [إنشاء حساب تخزين](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>توصيل Customer Insights بحساب التخزين

عند إنشاء بيئة جديدة، تأكد من وجود حساب Data Lake Storage ومن تلبية جميع المتطلبات الأساسية.

1. في خطوة **تخزين البيانات** أثناء إنشاء البيئة، عيّن الخيار **حفظ بيانات الإخراج** إلى **Azure Data Lake Storage Gen2**.
1. اختر طريقة **توصيل مساحة التخزين**. يمكنك الاختيار بين خيار مستند إلى المورد أو خيار مستند إلى الاشتراك للمصادقة. لمزيد من المعلومات، راجع [الاتصال بحساب Azure Data Lake Storage باستخدام كيان خدمة Azure](connect-service-principal.md).
   - بالنسبة إلى **اشتراك Azure**، اختر **الاشتراك** و **مجموعة الموارد** و **حساب التخزين** الذي يحتوي على حاوية `customerinsights`.
   - بالنسبة إلى **مفتاح الحساب**، قدم **اسم الحساب** و **مفتاح الحساب** لحساب Data Lake Storage. يشير استخدام طريقة المصادقة هذه إلى إخطارك إذا كانت مؤسستك تقوم بتدوير المفاتيح. يجب [تحديث تكوين البيئة](manage-environments.md#edit-an-existing-environment) بالمفتاح الجديد عند تدويره.
1. اختر ما إذا كنت ترغب في استخدام Azure Private Link للاتصال بحساب التخزين و[أنشئ الاتصال بالارتباط الخاص](security-overview.md#private-links-tab) من خلال تنفيذ عملية من خطوتين.

عند اكتمال عمليات النظام مثل استيعاب البيانات، يقوم النظام بإنشاء مجلدات مقابلة في حساب التخزين. يتم إنشاء ملفات البيانات وملفات *model.json* وإضافتها إلى المجلدات استنادًا إلى اسم العملية.

إذا قمت بإنشاء بيئات متعددة من Customer Insights واخترت حفظ كيانات الإخراج من تلك البيئات في حساب التخزين الخاص بك، فإن Customer Insights ينشئ مجلدات منفصلة لكل بيئة باستخدام `ci_environmentID` في الحاوية.
