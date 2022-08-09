---
title: روبوت Teams في Dynamics 365 Customer Insights (معاينة)
description: ابحث عن ملفات تعريف العملاء الموحدة في Microsoft Teams بمساعدة الروبوت.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195826"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>روبوت Teams في Dynamics 365 Customer Insights (معاينة)

اتصل بتطبيق Microsoft Teams لتمكين الروبوت من البحث عن ملفات تعريف العملاء الموحدة في قنوات Teams.

:::image type="content" source="media/teams-bot.png" alt-text="روبوت Teams يعرض سجل عميل":::

## <a name="prerequisites"></a>المتطلبات

- هناك [مصدر بيانات واحد مضاف](data-sources.md) على الأقل.
- اكتملت [عملية التوحيد](data-unification.md).
- تُضاف الحقول إلى [فهرس البحث والتصفية](search-filter-index.md).
- يوجد Customer Insights وTeams في المؤسسة نفسها.
- بيئتك لديها الجمهور المستهدف الأساسي الذي تم تعيينه للعملاء الفرديين. حسابات الأعمال غير مدعومة.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>تكوين الروبوت

1. انتقل إلى **المسؤول** > **الاتصالات**.
1. على الإطار المتجانب Microsoft Teams، حدد **إعداد**.
1. يُعاد توجيهك إلى منطقة **التطبيقات** في Teams. يمكنك أيضًا فتح Teams وتحديد **التطبيقات‏‎** في الزاوية السفلية اليسرى أو [الحصول عليها من AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) مباشرةً.
1. ابحث عن **Customer Insights** وحدد التطبيق.
1. حدد **إضافة**.
1. سجل دخولك إلى Customer Insights في Teams. يتم عرض رسالة ترحيب.

## <a name="things-you-can-do-with-the-bot"></a>أشياء يمكنك القيام بها مع الروبوت

يوفر الروبوت إمكانيات البحث لملفات تعريف العملاء الموحدة.

- ادخل **بحث** يليه اسم أو عنوان بريد إلكتروني أو اي حقل آخر على ملف تعريف العميل الموحد الذي تمت إضافته إلى فهرس البحث والتصفية.

  ستحصل على بطاقة تتضمن ما يصل إلى 15 حقلاً من ملف تعريف العميل الناتج. تعيد تطابقات متعددة‬ قائمة بالنتائج حيث يمكنك تحديد ملف تعريف. للبحث عن تطابق تام، أضف مصطلح البحث بين علامتي اقتباس.

- إذا كانت مؤسستك تحتفظ ببيئات Customer Insights متعددة في نفس المؤسسة، أدخل **switchinstance** لاختيار البيئة التي تريد توصيل الروبوت بها.

- أدخل **تعليمات** لرؤية قائمة بالأوامر المتوفرة للروبوت.  

[!INCLUDE [footer-include](includes/footer-banner.md)]