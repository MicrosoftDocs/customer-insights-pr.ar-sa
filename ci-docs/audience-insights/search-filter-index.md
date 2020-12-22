---
title: بحث عن ملفات تعريف العملاء وتصفيتها
description: البحث سريعًا عن معلومات حول ملفات تعريف العملاء الموحدة والتصفية لسمات مُحددة.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4404942"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="0b78c-103">ملفات تعريف العملاء: فهرس البحث & التصفيه</span><span class="sxs-lookup"><span data-stu-id="0b78c-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="0b78c-104">تكون نتيجة توحيد بيانات عميلك هو كيان ملف تعريف العميل الذي يوفر طريقة عرض موحدة إلى إجمالي قاعدة العملاء الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="0b78c-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="0b78c-105">لـ [البحث بسرعة عن عميل مُعين أو مجموعة عملاء](customer-profiles.md)، يُمكنك تكوين إمكانيات **البحث** و **التصفية** على صفحة **العملاء**.</span><span class="sxs-lookup"><span data-stu-id="0b78c-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="0b78c-106">اقرأ للتعرف على كيف يُمكن للمسؤولين تحرير السمات في صفحة **مؤشر البحث والتصفية** ، المتاح للمستخدمين للبحث والتصفية.</span><span class="sxs-lookup"><span data-stu-id="0b78c-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="0b78c-107">![عامل تصفية البحث](media/search-filter.png "عامل تصفية البحث")</span><span class="sxs-lookup"><span data-stu-id="0b78c-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="0b78c-108">إضافة حقول وتحديد سمات</span><span class="sxs-lookup"><span data-stu-id="0b78c-108">Add fields and specify attributes</span></span>

<span data-ttu-id="0b78c-109">إذا كانت هذه هي المرة الأولى التي تقوم فيها بتحديد سمات قابلة للبحث كمسؤول، سوف تحتاج إلى تعريف الحقول المفهرسة أولًا.</span><span class="sxs-lookup"><span data-stu-id="0b78c-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="0b78c-110">نقترح عليك اختيار كافة السمات التي يُمكن للمستخدمين من خلالها البحث عن العملاء وتصفيتهم على صفحة **العملاء**.</span><span class="sxs-lookup"><span data-stu-id="0b78c-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="0b78c-111">يمكنك فقط تحديد السمات الموجودة في كيان ملف تعريف العميل الذي قمت بإنشاءه في أثناء عملية توحيد البيانات.</span><span class="sxs-lookup"><span data-stu-id="0b78c-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="0b78c-112">افتح **صفحة العملاء** وحدد **فهرس البحث والتصفية**.</span><span class="sxs-lookup"><span data-stu-id="0b78c-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="0b78c-113">نقوم بإنشاء تكوين فهرس بحث افتراضي على السمات المتوفرة في كيان العميل من الأنواع الدلالية التالية كما هو محدد في صفحه المخطط.</span><span class="sxs-lookup"><span data-stu-id="0b78c-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="0b78c-114">الاسم الأول والاسم الأخير والاسم الأوسط والاسم الكامل للشخص</span><span class="sxs-lookup"><span data-stu-id="0b78c-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="0b78c-115">اسم المؤسسة</span><span class="sxs-lookup"><span data-stu-id="0b78c-115">Organization Name</span></span>
> - <span data-ttu-id="0b78c-116">عنوان البريد الإلكتروني</span><span class="sxs-lookup"><span data-stu-id="0b78c-116">Email address</span></span>
> - <span data-ttu-id="0b78c-117">رقم الهاتف</span><span class="sxs-lookup"><span data-stu-id="0b78c-117">Phone number</span></span>
> - <span data-ttu-id="0b78c-118">معلومات الموقع</span><span class="sxs-lookup"><span data-stu-id="0b78c-118">Location information</span></span>

2. <span data-ttu-id="0b78c-119">حدد **+ إضافة** لتحديد الحقول المفهرسة.</span><span class="sxs-lookup"><span data-stu-id="0b78c-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="0b78c-120">حدد السمات الموجودة في القائمة التي تريد إضافتها كحقول مفهرسة.</span><span class="sxs-lookup"><span data-stu-id="0b78c-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="0b78c-121">يُمكنك دائمًا إضافة المزيد من السمات عن طريقة تحديد **إضافة**.</span><span class="sxs-lookup"><span data-stu-id="0b78c-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="0b78c-122">يمكنك أيضا إزالة أية سمات محددة من خلال تحديد رمز **إزالة**.</span><span class="sxs-lookup"><span data-stu-id="0b78c-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="0b78c-123">استكشف جدول حقول العميل المفهرسة</span><span class="sxs-lookup"><span data-stu-id="0b78c-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="0b78c-124">يتم عرض المعلومات التالية في الجدول.</span><span class="sxs-lookup"><span data-stu-id="0b78c-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="0b78c-125">**الاسم**: يمثل اسم السمة كما يظهر في كيان ملف تعريف العميل.</span><span class="sxs-lookup"><span data-stu-id="0b78c-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="0b78c-126">**نوع البيانات**: يُحدد ما إذا كان نوع البيانات هو سلسلة أو رقم أو تاريخ.</span><span class="sxs-lookup"><span data-stu-id="0b78c-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="0b78c-127">**مُضمن في البحث**: يُحدد ما إذا كان يُمكن استخدام هذه السمة للبحث عن العملاء في صفحة **العملاء** باستخدام حقل **البحث**.</span><span class="sxs-lookup"><span data-stu-id="0b78c-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="0b78c-128">**إضافة عامل تصفية**: يتحكم في تحديد كيفية استخدام هذه السمة للتصفية على صفحة **العملاء**.</span><span class="sxs-lookup"><span data-stu-id="0b78c-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="0b78c-129">تحرير خيارات التصفية لسمة مُعينة</span><span class="sxs-lookup"><span data-stu-id="0b78c-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="0b78c-130">يُمكن أن تتضمن قائمة **التصفية** على صفحة **العملاء** عددًا متغيرًا من مستويات السمات (على سبيل المثال، مجموعات عمر مختلفة لتصفية العملاء وفقًا لها).</span><span class="sxs-lookup"><span data-stu-id="0b78c-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="0b78c-131">حدد **إضافة عامل تصفية** لسمة مُعينة في صفحة **فهرس البحث والتصفية**.</span><span class="sxs-lookup"><span data-stu-id="0b78c-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="0b78c-132">يمكنك تحديد عدد النتائج والترتيب الذي سيتم تنظيمها به.</span><span class="sxs-lookup"><span data-stu-id="0b78c-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="0b78c-133">اعتمادًا على نوع بيانات السمة، سوف يظهر أحد الجزئين التاليين.</span><span class="sxs-lookup"><span data-stu-id="0b78c-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="0b78c-134">السمات من نوع السلسلة‬: حدد عدد النتائج المرغوبة على لوحة **خيارات تصفية السلسلة** وسياسة الترتيب التي سوف يتم التنظيم وفقًا لها.</span><span class="sxs-lookup"><span data-stu-id="0b78c-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="0b78c-135">السمات من النوع العددي‬: حدد عدد الفترات الزمنية المضمنة في جزء **خيارات تصفية الأعداد** وسياسة الترتيب التي سوف يتم التنظيم وفقًا لها.</span><span class="sxs-lookup"><span data-stu-id="0b78c-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="0b78c-136">السمات من نوع البيانات‬: حدد عدد الفترات الزمنية المضمنة في جزء **خيارات تصفية البيانات** وسياسة الترتيب التي سوف يتم التنظيم وفقًا لها.</span><span class="sxs-lookup"><span data-stu-id="0b78c-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="0b78c-137">حدد **حفظ** لتطبيق التغييرات التي أجريتها.</span><span class="sxs-lookup"><span data-stu-id="0b78c-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="0b78c-138">حدد **تشغيل** بُمجرد أن تكون مستعدًا لتطبيق إعداداتك.</span><span class="sxs-lookup"><span data-stu-id="0b78c-138">Select **Run** once you're ready to apply your settings.</span></span>
