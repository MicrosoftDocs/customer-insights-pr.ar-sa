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
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="b08cf-103">روبوت Teams في Dynamics 365 Customer Insights (معاينة)</span><span class="sxs-lookup"><span data-stu-id="b08cf-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="b08cf-104">اتصل بتطبيق Microsoft Teams لتمكين الروبوت من البحث عن ملفات تعريف العملاء الموحدة في قنوات Teams.</span><span class="sxs-lookup"><span data-stu-id="b08cf-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b08cf-105">![روبوت Teams يعرض سجل عميل](media/teams-bot.png "روبوت Teams يعرض سجل عميل")</span><span class="sxs-lookup"><span data-stu-id="b08cf-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b08cf-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="b08cf-106">Prerequisites</span></span>

<span data-ttu-id="b08cf-107">لإعداد روبوت وتكوينه، يجب استيفاء المتطلبات الأساسية التالية:</span><span class="sxs-lookup"><span data-stu-id="b08cf-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="b08cf-108">هناك [مصدر بيانات واحد مضاف](data-sources.md) على الأقل.</span><span class="sxs-lookup"><span data-stu-id="b08cf-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="b08cf-109">اكتملت [عملية التوحيد](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="b08cf-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="b08cf-110">تُضاف الحقول إلى [فهرس البحث والتصفية](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="b08cf-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="b08cf-111">يوجد Customer Insights وTeams في المؤسسة نفسها.</span><span class="sxs-lookup"><span data-stu-id="b08cf-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="b08cf-112">تكوين الروبوت</span><span class="sxs-lookup"><span data-stu-id="b08cf-112">Configure the bot</span></span>

1. <span data-ttu-id="b08cf-113">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **وجهات التصدير‬**.</span><span class="sxs-lookup"><span data-stu-id="b08cf-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="b08cf-114">على الإطار المتجانب Microsoft Teams، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="b08cf-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="b08cf-115">يُعاد توجيهك إلى منطقة **التطبيقات** في Teams.</span><span class="sxs-lookup"><span data-stu-id="b08cf-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="b08cf-116">يمكنك أيضًا فتح Teams وتحديد **التطبيقات‏‎** في الزاوية السفلية اليسرى أو [الحصول عليها من AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) مباشرةً.</span><span class="sxs-lookup"><span data-stu-id="b08cf-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="b08cf-117">ابحث عن **Customer Insights** وحدد التطبيق.</span><span class="sxs-lookup"><span data-stu-id="b08cf-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="b08cf-118">حدد **إضافة**.</span><span class="sxs-lookup"><span data-stu-id="b08cf-118">Select **Add**.</span></span>
1. <span data-ttu-id="b08cf-119">بعد تسجيل الدخول إلى Customer Insights في Teams، ستظهر لك رسالة ترحيب ويمكنك البدء.</span><span class="sxs-lookup"><span data-stu-id="b08cf-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="b08cf-120">أشياء يمكنك القيام بها مع الروبوت</span><span class="sxs-lookup"><span data-stu-id="b08cf-120">Things you can do with the bot</span></span>

<span data-ttu-id="b08cf-121">يوفر الروبوت إمكانيات البحث لملفات تعريف العملاء الموحدة.</span><span class="sxs-lookup"><span data-stu-id="b08cf-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="b08cf-122">ادخل **بحث** يليه اسم أو عنوان بريد إلكتروني أو اي حقل آخر على ملف تعريف العميل الموحد الذي تمت إضافته إلى فهرس البحث والتصفية.</span><span class="sxs-lookup"><span data-stu-id="b08cf-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="b08cf-123">ستحصل على بطاقة تتضمن ما يصل إلى 15 حقلاً من ملف تعريف العميل الناتج.</span><span class="sxs-lookup"><span data-stu-id="b08cf-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="b08cf-124">تعيد تطابقات متعددة‬ قائمة بالنتائج حيث يمكنك تحديد ملف تعريف.</span><span class="sxs-lookup"><span data-stu-id="b08cf-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="b08cf-125">يمكنك إضافة مصطلح البحث في علامات اقتباس مزدوجة للبحث عن تطابق تام.</span><span class="sxs-lookup"><span data-stu-id="b08cf-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="b08cf-126">إذا كانت مؤسستك تحتفظ ببيئات Customer Insights متعددة في نفس المؤسسة، فيمكنك إدخال **switchinstance** لاختيار البيئة التي تريد توصيل الروبوت بها.</span><span class="sxs-lookup"><span data-stu-id="b08cf-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="b08cf-127">أدخل **تعليمات** لرؤية قائمة بالأوامر المتوفرة للروبوت.</span><span class="sxs-lookup"><span data-stu-id="b08cf-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]