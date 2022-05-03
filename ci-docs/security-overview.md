---
title: إعدادات الأمان في Dynamics 365 Customer Insights
description: تعرف على إعدادات الأمان في Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653692"
---
# <a name="security-overview-page"></a>صفحة نظرة عامة على الأمان

تسرد **الأمان** خيارات لتكوين أذونات المستخدم والميزات التي تساعد في جعل Dynamics 365 Customer Insights أكثر أمانًا. يمكن للمسؤولين فقط الوصول إلى هذه الصفحة. 

انتقل إلى **المسؤول** > **الأمان** لتكوين الإعدادات.

تتضمن صفحة **الأمان** علامات التبويب التالية:
- [المستخدمون](#users-tab)
- [واجهات API](#apis-tab)
- [Key Vault](#key-vault-tab)

## <a name="users-tab"></a>علامة التبويب "المستخدمين"

يقتصر الوصول إلى Customer Insights على المستخدمين في مؤسستك الذين أضافهم أحد المسؤولين إلى التطبيق. وتتيح لك علامة التبويب **المستخدمين** إدارة وصول المستخدمين وأذوناتهم. لمزيد من المعلومات، راجع [أذونات المستخدم](permissions.md).

## <a name="apis-tab"></a>علامة التبويب "واجهات برمجة التطبيقات"

عرض المفاتيح وإدارتها لاستخدام [واجهات برمجة التطبيقات في Customer Insights](apis.md) باستخدام بيانات بيئتك.

يمكنك إنشاء مفتاحين أساسيين وثانويين جديدين عن طريق تحديد **إعادة إنشاء مفتاح أساسي** أو **إعادة إنشاء مفتاح ثانوي**. 

لحظر وصول واجهة برمجة التطبيقات إلى البيئة، حدد **تعطيل**. إذا كانت واجهات برمجة التطبيقات معطلة، يمكنك تحديد **تمكين** لمنح الوصول مرة أخرى.

## <a name="key-vault-tab"></a>علامة التبويب "Key Vault"

تسمح علامة التبويب **Key Vault** بربط [Azure key vault](/azure/key-vault/general/basic-concepts) الخاصة بك بالبيئة وإدارتها.
يمكن استخدام مخزن المفاتيح المخصص لتنظيم الأسرار واستخدامها في حدود امتثال المؤسسة. يمكن لـ Customer Insights استخدام الأسرار الموجودة في Azure Key Vault [لإعداد الاتصالات](connections.md) بأنظمة الجهات الخارجية.

لمزيد من المعلومات، راجع [جلب Azure key vault الخاص بك](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
