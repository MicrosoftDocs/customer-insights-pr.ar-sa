---
title: الكيانات ومجموعات البيانات
description: عرض البيانات في صفحة الكيانات.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049378"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="abef1-103">الكيانات في رؤى الجمهور</span><span class="sxs-lookup"><span data-stu-id="abef1-103">Entities in audience insights</span></span>

<span data-ttu-id="abef1-104">بعد [تكوين مصادر البيانات الخاصة بك](data-sources.md)، انتقل إلى صفحة **الكيانات** لتقييم جودة البيانات المستوعبة.</span><span class="sxs-lookup"><span data-stu-id="abef1-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="abef1-105">تعتبر الكيانات بمثابة مجموعات بيانات.</span><span class="sxs-lookup"><span data-stu-id="abef1-105">Entities are considered datasets.</span></span> <span data-ttu-id="abef1-106">يتم بناء العديد من قدرات Dynamics 365 Customer Insights حول هذه الكيانات.</span><span class="sxs-lookup"><span data-stu-id="abef1-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="abef1-107">يُمكن أن يساعدك مراجعة هذه الكيانات بشكل كبير في التحقق من صحة إخراج هذه الإمكانيات. </span><span class="sxs-lookup"><span data-stu-id="abef1-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="abef1-108">تسرد صفحة **الكيانات** الكيانات وتتضمن العديد من الأعمدة:</span><span class="sxs-lookup"><span data-stu-id="abef1-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="abef1-109">**الاسم**: اسم كيان البيانات الخاص بك.</span><span class="sxs-lookup"><span data-stu-id="abef1-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="abef1-110">إذا شاهدت رمز تحذير بجوار اسم الكيان، فهذا يعني أن البيانات لهذا الكيان لم يتم تحميلها بنجاح.</span><span class="sxs-lookup"><span data-stu-id="abef1-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="abef1-111">**المصدر**: نوع مصدر البيانات المستوعبة في الكيان</span><span class="sxs-lookup"><span data-stu-id="abef1-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="abef1-112">**مُنشأ بواسطة**: اسم الشخص الذي أنشأ الكيان</span><span class="sxs-lookup"><span data-stu-id="abef1-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="abef1-113">**تم الإنشاء**: تاريخ ووقت إنشاء الكيان</span><span class="sxs-lookup"><span data-stu-id="abef1-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="abef1-114">**تم التحديث بواسطة**: اسم الشخص الذي قام بتحديث الكيان</span><span class="sxs-lookup"><span data-stu-id="abef1-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="abef1-115">**التحديث الأخير**: تاريخ ووقت آخر تحديث للكيان</span><span class="sxs-lookup"><span data-stu-id="abef1-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="abef1-116">**آخر تحديث**: تاريخ ووقت آخر تحديث للبيانات</span><span class="sxs-lookup"><span data-stu-id="abef1-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="abef1-117">استكشاف بيانات كيان معين</span><span class="sxs-lookup"><span data-stu-id="abef1-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="abef1-118">حدد كيانًا لاستكشاف الحقول والسجلات المختلفة المُضمنة في ذلك الكيان.</span><span class="sxs-lookup"><span data-stu-id="abef1-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="abef1-119">![تحديد كيان](media/data-manager-entities-data.png "حدد كيانًا")</span><span class="sxs-lookup"><span data-stu-id="abef1-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="abef1-120">تعرض علامة تبويب **البيانات** تفاصيل قائمة الجدول حول السجلات الفردية للكيان.</span><span class="sxs-lookup"><span data-stu-id="abef1-120">The **Data** tab shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="abef1-121">![جدول الحقول](media/data-manager-entities-fields.PNG "جدول الحقول")</span><span class="sxs-lookup"><span data-stu-id="abef1-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="abef1-122">يتم تحديد علامة التبويب **السمات** افتراضيا وهي تعرض جدولاً لمراجعة التفاصيل الخاصة بالكيانات المحددة، مثل أسماء الحقول وأنواع البيانات والأنواع.</span><span class="sxs-lookup"><span data-stu-id="abef1-122">The **Attributes** tab is selected by default and shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="abef1-123">يظهر عمود **النوع** الأنواع المقترنة بنموذج البيانات المشتركة، والتي تكون إما مُحددة تلقائيًا بواسطة النظام أو [مُعينة يدويًا](map-entities.md) بوسطة المستخدمين.</span><span class="sxs-lookup"><span data-stu-id="abef1-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="abef1-124">هذه هي الأنواع الدلالية التي يُمكن أن تختلف عن أنواع بيانات السمات- على سبيل المثال، يحتوي الحقل *البريد الإلكتروني* أدناه على نوع بيانات *النص* ولكن قد يكون نوع نموذج البيانات المشتركة (الدلالي) الخاصة به هو *البريد الإلكتروني* أو *EmailAddress*.</span><span class="sxs-lookup"><span data-stu-id="abef1-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="abef1-125">يظهر كلا الجدولين عينة لبيانات الكيان الخاص بك فقط.</span><span class="sxs-lookup"><span data-stu-id="abef1-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="abef1-126">لعرض مجموعة كاملة من البيانات، انتقل إلى صفحة **مصادر البيانات** ، وحدد كيانًا، ثم حدد **تحرير** ، ثم اعرض بيانات هذا الكيان باستخدام مُحرر Power Query على النحو الموضح في [مصادر البيانات](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="abef1-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="abef1-127">لمعرفة المزيد حول البيانات المستوعبة في الكيان، يوفر لك عمود **الملخص** بعض الخصائص الهامة للبيانات، مثل القيم الخالية والقيم المفقودة والقيم الفريدة والتوزيعات، على النحو المنطبق على بياناتك.</span><span class="sxs-lookup"><span data-stu-id="abef1-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="abef1-128">حدد أيقونة المخطط لرؤية ملخص البيانات.</span><span class="sxs-lookup"><span data-stu-id="abef1-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="abef1-129">![رمز الملخص](media/data-manager-entities-summary.png "جدول ملخص البيانات")</span><span class="sxs-lookup"><span data-stu-id="abef1-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="abef1-130">الخطوة التالية</span><span class="sxs-lookup"><span data-stu-id="abef1-130">Next step</span></span>

<span data-ttu-id="abef1-131">راجع موضوع [توحيد](data-unification.md) لمعرفة كيفية *تعيين* و *مطابقة* و *دمج* البيانات المستوعبة.</span><span class="sxs-lookup"><span data-stu-id="abef1-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
