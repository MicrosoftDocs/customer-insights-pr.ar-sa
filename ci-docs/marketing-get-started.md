---
title: استخدام ملفات التعريف الموحدة في Dynamics 365 Marketing
description: تعرف على طريقة دمج ملفات التعريف والمقاطع باستخدام Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99ec463299a24ea81cfe26bb785e36bdefdcd080
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054416"
---
# <a name="use-unified-customer-profiles-in-dynamics-365-marketing"></a>استخدم unified customer profiles في Dynamics 365 Marketing

يرتقي [Dynamics 365 Marketing](/dynamics365/marketing/overview) بمستوى تجارب العملاء، ما يتيح تنسيق الرحلات الشخصية عبر جميع نقاط الاتصال لتعزيز العلاقات وكسب الولاء. يعمل تطبيق Dynamics 365 Marketing بسلاسة مع Dynamics 365 Sales، وDynamics 365 Customer Insights، وMicrosoft Teams، والمنتجات الأخرى، ويسمح لك باتخاذ قرارات أسرع وأفضل باستخدام قوة البيانات والذكاء الاصطناعي.

من خلال ربط بيانات Customer Insights مع Marketing، يمكنك:

- استهداف ملفات التعريف الموحدة للعملاء والمقاطع. يمكّنك هذا من إشراك كل عميل، بغض النظر عن موقع بيانات العميل.
- ضع محتوى ديناميكيًا (مثل الرموز المميزة المخصصة) في رسائل البريد الإلكتروني والرسائل النصية القصيرة والإشعارات المنبثقة حول إجراءات مثل حالة الولاء أو تاريخ تجديد الاشتراك أو حساب الوالدين أو أي إجراء آخر قمت بالتقاطه في ملف تعريف Customer Insights الموحد.
- قم بتحميل البيانات من Marketing إلى Customer Insights ودمجها مع بيانات العملاء من مصادر أخرى.
- قم بتطبيق أدوات تنقية وإثراء البيانات والمطابقة غير الواضحة في Customer Insights.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>استخدام ملفات تعريف العملاء المنسّقة في التسويق في الوقت الفعلي

يسمح التسويق في الوقت الفعلي بإنشاء [مشغلات مخصصة](/dynamics365/marketing/real-time-marketing-custom-triggers) تطلق رحلات العملاء بناءً على أي إجراء يتخذه العميل. كلما كانت بياناتك أكثر تخصيصًا، زادت أهمية رحلاتك وتخصيصها. هذا ما يجعل الدمج بين Marketing وCustomer Insights قويًا للغاية. يمكنك [توحيد البيانات](data-unification.md) من أي مصدر، ومن ثَمَّ استخدامها لتغذية رحلات العملاء شديدة التخصيص.

تعرف على المزيد: [استخدم ملفات تعريف ومقاطع Customer Insights في التسويق في الوقت الفعلي](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>استخدام مقاطع موحدة مع رحلات العملاء الصادرة

يتيح Customer Insights تحسين البيانات من العديد من المصادر ودمجها في مقاطع عملاء مجمّعة. من خلال [ربط Customer Insights بالتسويق الصادر](export-dynamics365-marketing.md)، ستظهر هذه المقاطع تلقائيًا *و* يتم تحديثها تلقائيًا في مصمم رحلة العميل.

معرفة المزيد: [استخدام مقاطع من Dynamics 365 Customer Insights مع Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>سحب البيانات من بياناتك الخاصة على Azure Data Lake Storage

لست مقيدًا بالتخزين السحابي إذا كنت ترغب في استخدام بيانات Customer Insights مع Marketing. إذا كان لديك بالفعل إعداد Azure Data Lake Storage الخاص بك، فيمكنك الاتصال بـ Customer Insights، ثم مشاركة البيانات مع تطبيق Marketing تمامًا كما تفعل مع الإعداد المستند إلى السحابة.

معرفة المزيد: [تمكين مشاركة البيانات مع Dataverse من بياناتك الخاصة في Azure Data Lake Storage](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
