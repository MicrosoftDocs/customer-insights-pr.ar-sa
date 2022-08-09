---
title: استخدام موافقة العميل
description: احترم تفضيلات موافقة العملاء في Customer Insights عن طريق استيراد بيانات الموافقة.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99fe24cb47a8c20f629182d9a1c6adfd36a1eaf7
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188031"
---
# <a name="use-customer-consent"></a>استخدام موافقة العميل

توفر لوائح حماية البيانات والخصوصية للأفراد الحق في التحكم في كيفية استخدام المؤسسة لبياناتهم الشخصية. ومن الأمثلة عن هذه اللوائح القانون العام لحماية البيانات في الاتحاد الأوروبي أو قانون خصوصية المستهلك في كاليفورنيا في الولايات المتحدة. وتسمح هذه اللوائح للأشخاص برفض الموافقة على جمع بياناتهم الشخصية أو معالجتها أو مشاركتها مع جهات خارجية.  

بإمكان العملاء اختيار سحب أو حجب موافقتهم على أشكال محددة من الاتصال. قد يطلبون منك أيضًا إلغاء اشتراكهم في جمع بياناتهم الشخصية أو تخزينها أو استخدامها أو بيعها. من الضروري أن تحترم مؤسستك موافقة جميع العملاء وتفضيلات الخصوصية.  

يساعدك Dynamics 365 Customer Insights على احترام طلبات العملاء من خلال استيراد تفضيلاتهم وتخزينها كجزء من ملفات تعريف العملاء الموحدة.

في حالة تخزين بيانات الموافقة بشكل منفصل عن ملفات تعريف العميل، فيمكنك [إضافة بيانات الموافقة كمصدر بيانات جديد](#import-and-unify-consent-data). يُضاف مصدر البيانات الذي يحتوي على بيانات الموافقة إلى عملية توحيد البيانات. بعد ذلك، يؤدي التوحيد الناجح لبيانات الموافقة وملفات تعريف العملاء إلى ملفات تعريف عملاء موحدة تحتوي على معلومات الموافقة. بالنسبة إلى ملفات تعريف العملاء التي تحتوي على معلومات الموافقة، انتقل مباشرة إلى القسم [استخدام بيانات الموافقة](#use-consent-data).

## <a name="prerequisites"></a>المتطلبات

يجب أن تكون المعلومات التالية متاحة في بياناتك المصدر لتوحيد بيانات الموافقة مع ملفات تعريف العملاء الأخرى:

- مفتاح بديل لتعيين معلومات الموافقة إلى ملفات تعريف المستخدمين في Customer Insights. على سبيل المثال، عنوان بريد إلكتروني أو رقم هاتف.
- قيمة الموافقة لتحديد حالة موافقة العميل.

يمكنك إضافة المعلومات *الاختيارية* التالية:

- مفتاح أساسي لتحديث حالة الموافقة إذا طلب أحد العملاء تغييرًا.
- نوع الموافقة، إذا كانت هناك أكثر من طريقة لمعالجة معلومات العميل.
- تاريخ الموافقة أو أي نوع آخر من البيانات ذات الصلة بسيناريوهات الموافقة الخاصة بك.

مثال عن جدول قاعدة بيانات موافقة بسيطة مع خيارات موافقة متعددة:

|معرف الموافقة (مفتاح أساسي)   |بريد إلكتروني (مفتاح بديل)  |خيار الموافقة  |قيمة الموافقة  |
|---------|---------|---------|---------|
|1     |  holly@contoso.com       |  الرسالة الإخبارية       |  خطأ       |
|2     |  holly@contoso.com       |  تحديثات المنتج       |  صواب       |
|3     |  frank@contoso.com       |  الرسالة الإخبارية       | صواب        |
|4    |  frank@contoso.com       |  تحديثات المنتج       |  خطأ       |

## <a name="import-and-unify-consent-data"></a>استيراد بيانات الموافقة وتوحيدها

استورد بيانات الموافقة بنفس الطريقة التي تستورد بها مصادر البيانات الأخرى إلى Customer Insights. لمزيد من المعلومات حول مصادر البيانات المدعومة وكيفية استيرادها، راجع [نظرة عامة حول مصادر البيانات](data-sources.md).

لمزيد من المعلومات حول توحيد مصادر البيانات، راجع [نظرة عامة على توحيد البيانات](data-unification.md).

## <a name="use-consent-data"></a>استخدام بيانات الموافقة

بمجرد أن تكون بيانات موافقتك جزءًا من ملفات تعريف العملاء الموحدة، يمكنك استخدامها في Customer Insights. على سبيل المثال، أنشئ مقطع مع قاعدة لضمان احترام خصوصية عملائك وتفضيلات حماية البيانات. تُستخدم القواعد التي تدعم تفضيلات الموافقة لاستبعاد المستخدمين من مقطع بالاستناد إلى سمات ملف التعريف. أضف قاعدة إلى مقطع تستبعد ملفات تعريف العملاء التي لم توفر الموافقة على الاتصال.

بالإشارة إلى عينة الجدول أعلاه، قد تحتوي إحدى المقاطع على هذه القاعدة: `Consent option=Newsletter & Consent value=True`. يؤدي هذا التكوين إلى تقسيم مقطع تحترم تفضيلات الاتصال لإرسال رسالة إخبارية.

لمزيد من المعلومات حول بناء المقاطع، راجع [إنشاء مقاطع](segment-builder.md).

بمجرد إنشاء المقطع، يمكنك استخدام خيار من [خيارات التصدير](export-destinations.md) المتعددة لاستخدام المقطع في تطبيقات أخرى.

## <a name="ensure-updated-consent-status"></a>ضمان حالة الموافقة المحدّثة

من الضروري المحافظة على تحديث حالة الموافقة للعملاء. يقوم التحديث المجدول في Customer Insights دائمًا باستيراد الحالة الأحدث لمصادر بياناتك. بعد ذلك، تتم معالجة هذه المعلومات من خلال توحيد البيانات ويتم تحديث النتائج في ملفات تعريف العملاء المحدثة. ويتم عندئذٍ استخدام ملفات التعريف المحدثة هذه لتحديث المقاطع للتأكد من أنك تعمل مع أحدث المعلومات.

بتعابير أخرى، تأكد من أن البيانات المصدر التي يتم استيرادها إلى Customer Insights تتضمن دائمًا أحدث المعلومات.

لمزيد من المعلومات، راجع [تحديث المقاطع يدويًا](segments.md#refresh-segments) أو [تكوين تحديث مجدول](system.md#schedule-tab).

[!INCLUDE [footer-include](includes/footer-banner.md)]