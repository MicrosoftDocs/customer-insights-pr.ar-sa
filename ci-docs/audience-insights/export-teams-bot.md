---
title: روبوت لـ Microsoft Teams
description: ابحث عن ملفات تعريف العملاء الموحدة في Microsoft Teams بمساعدة الروبوت.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267936"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>روبوت Teams في Dynamics 365 Customer Insights (معاينة)

اتصل بتطبيق Microsoft Teams لتمكين الروبوت من البحث عن ملفات تعريف العملاء الموحدة في قنوات Teams.

> [!div class="mx-imgBorder"]
> ![روبوت Teams يعرض سجل عميل](media/teams-bot.png "روبوت Teams يعرض سجل عميل")

## <a name="prerequisites"></a>المتطلبات الأساسية

لإعداد روبوت وتكوينه، يجب استيفاء المتطلبات الأساسية التالية:

- هناك [مصدر بيانات واحد مضاف](data-sources.md) على الأقل.
- اكتملت [عملية التوحيد](data-unification.md).
- تُضاف الحقول إلى [فهرس البحث والتصفية](search-filter-index.md).
- يوجد Customer Insights وTeams في المؤسسة نفسها.

## <a name="configure-the-bot"></a>تكوين الروبوت

1. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.
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


[!INCLUDE[footer-include](../includes/footer-banner.md)]