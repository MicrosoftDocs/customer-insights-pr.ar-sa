---
title: إدارة قواعد الموافقة الافتراضية على الشرائح
description: باستخدام إمكانية إدارة الموافقة، يمكنك تعطيل أو تغيير قواعد الموافقة الافتراضية إذا تم تمكين التجاوزات.
ms.date: 12/01/2021
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 764eeca9d99c95a34d9bd4c11d79f8b8e90701e2
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755200"
---
# <a name="disable-or-change-default-consent-rules"></a>تعطيل قواعد الموافقة الافتراضية أو تغييرها

إذا كانت مؤسستك تستخدم [إمكانية إدارة الموافقة](consent-management/overview.md) مع Dynamics 365 Customer Insights، [يمكن للمسؤولين فرض قواعد الموافقة](activate-consent.md) للشرائح. 

ومع وجود قواعد الموافقة المفروضة في منطقة الجزء، تبلغ كل شريحة عن حالة التحقق من الموافقة وقواعدها. إذا كانت التجاوزات مسموحا بها، يتم إيقاف تشغيل قواعد الموافقة الافتراضية لشرائح معينة. يمكن لكل منشئ مقطع إضافة المزيد من قواعد الموافقة أعلى القواعد الافتراضية إلى أحد المقاطع. 

## <a name="for-administrators"></a>للمسؤولين

:::image type="content" source="consent-management/media/consent-rules-segment.png" alt-text="منشئ الشرائح مع خيارات قاعدة الموافقة.":::

**إلغاء تنشيط قواعد الموافقة الافتراضية:**

1. في إعلام **قواعد الموافقة**، حدد **راجع التفاصيل**. 

1. تعيين زر تبديل **قواعد الموافقة الافتراضية** على **إيقاف**.

**إضافة قواعد موافقة إضافية:**

1. في إعلام **قواعد الموافقة**، حدد **راجع التفاصيل**. 

1. حدد **إضافة قواعد موافقة** واختر قاعدة الموافقة من القائمة المنسدلة **تحديد نوع بيانات الموافقة**.

1. حدد **حفظ** لتطبيق القاعدة الجديدة على المقطع.

## <a name="for-contributors"></a>للمساهمين

لإنشاء مقطع دون قواعد الموافقة المفروضة، يجب عليك العمل مع المسؤول لتعطيلها في المقطع الخاص بك. ومع ذلك، يمكنك إضافة قواعد الموافقة الخاصة بك إلى مقاطع تمتلكها وتديرها.

وهي عملية من ثلاث خطوات: 
1. [قم بإنشاء المقطع](segments.md) في Customer Insights واحفظه. 

1. شارك اسم المقطع مع المسؤول لديك واطلب منه [تمكين التجاوزات للمقطع الخاص بك](activate-consent.md). 

1. افتح المقاطع مرة أخرى. في إعلام **قواعد الموافقة**، حدد **راجع التفاصيل** وأضف قواعد الموافقة التي ترغب في تطبيقها. بعد ذلك، قم بـ **حفظ** المقطع و **تشغيله**.



[!INCLUDE [footer-include](includes/footer-banner.md)] 