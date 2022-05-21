---
title: روبوت لـ Microsoft Teams
description: ابحث عن ملفات تعريف العملاء الموحدة في Microsoft Teams بمساعدة الروبوت.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 89a293d5b6f9f5452b2ccba495d2475002806019
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645574"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>روبوت Teams في Dynamics 365 Customer Insights (معاينة)

اتصل بتطبيق Microsoft Teams لتمكين الروبوت من البحث عن ملفات تعريف العملاء الموحدة في قنوات Teams.

> [!div class="mx-imgBorder"]
> ![يعرض روبوت Teams سجل العميل.](media/teams-bot.png "روبوت Teams يعرض سجل عميل")

## <a name="prerequisites"></a>المتطلبات الأساسية

لإعداد روبوت وتكوينه، يجب استيفاء المتطلبات الأساسية التالية:

- هناك [مصدر بيانات واحد مضاف](data-sources.md) على الأقل.
- اكتملت [عملية التوحيد](data-unification.md).
- تُضاف الحقول إلى [فهرس البحث والتصفية](search-filter-index.md).
- يوجد Customer Insights وTeams في المؤسسة نفسها.
- بيئتك لديها الجمهور المستهدف الأساسي الذي تم تعيينه للعملاء الفرديين. حسابات الأعمال غير مدعومة.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>تكوين الروبوت

1. انتقل إلى **المسؤول** > **وجهات التصدير**.
1. على الإطار المتجانب Microsoft Teams، حدد **إعداد**.
1. يُعاد توجيهك إلى منطقة **التطبيقات** في Teams. يمكنك أيضًا فتح Teams وتحديد **التطبيقات‏‎** في الزاوية السفلية اليسرى أو [الحصول عليها من AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) مباشرةً.
1. ابحث عن **Customer Insights** وحدد التطبيق.
1. حدد **إضافة**.
1. بعد تسجيل الدخول إلى Customer Insights في Teams، ستظهر لك رسالة ترحيب ويمكنك البدء.

## <a name="things-you-can-do-with-the-bot"></a>أشياء يمكنك القيام بها مع الروبوت

يوفر الروبوت إمكانيات البحث لملفات تعريف العملاء الموحدة.

- ادخل **بحث** يليه اسم أو عنوان بريد إلكتروني أو اي حقل آخر على ملف تعريف العميل الموحد الذي تمت إضافته إلى فهرس البحث والتصفية.

  ستحصل على بطاقة تتضمن ما يصل إلى 15 حقلاً من ملف تعريف العميل الناتج. تعيد تطابقات متعددة‬ قائمة بالنتائج حيث يمكنك تحديد ملف تعريف. يمكنك إضافة مصطلح البحث في علامات اقتباس مزدوجة للبحث عن تطابق تام.

- إذا كانت مؤسستك تحتفظ ببيئات Customer Insights متعددة في نفس المؤسسة، فيمكنك إدخال **switchinstance** لاختيار البيئة التي تريد توصيل الروبوت بها.

- أدخل **تعليمات** لرؤية قائمة بالأوامر المتوفرة للروبوت.  


[!INCLUDE [footer-include](includes/footer-banner.md)]