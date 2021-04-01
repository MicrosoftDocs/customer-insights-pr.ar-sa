---
title: العلاقات بين الكيانات ومسارات الكيانات
description: إنشاء العلاقات بين الكيانات من مصادر بيانات متعددة وإدارتها.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595196"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="307d6-103">العلاقات بين الكيانات</span><span class="sxs-lookup"><span data-stu-id="307d6-103">Relationships between entities</span></span>

<span data-ttu-id="307d6-104">تساعدك العلاقات على توصيل الكيانات وإنشاء رسم بياني لبياناتك عندما تشارك الكيانات معرف مشترك (مفتاح خارجي) يمكن الإشارة إليه من كيان واحد لآخر.</span><span class="sxs-lookup"><span data-stu-id="307d6-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="307d6-105">تمكنك الكيانات المتصلة من تعريف المقاطع والمقاييس استنادًا إلى مصادر البيانات المتعددة.</span><span class="sxs-lookup"><span data-stu-id="307d6-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="307d6-106">هناك نوعان من العلاقات:</span><span class="sxs-lookup"><span data-stu-id="307d6-106">There are two types of relationships.</span></span> <span data-ttu-id="307d6-107">علاقات النظام غير القابلة للتحرير، والتي يتم إنشاؤها تلقائيًا/، والعلاقات المخصصة التي تم إنشاؤها وتكوينها بواسطة المستخدمين.</span><span class="sxs-lookup"><span data-stu-id="307d6-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="307d6-108">أثناء عمليات المطابقة والدمج، يتم إنشاء علاقات النظام في الخلفية بناءً على التطابق الذكي.</span><span class="sxs-lookup"><span data-stu-id="307d6-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="307d6-109">تساعد هذه العلاقات في ربط سجلات ملفات تعريف العملاء بسجلات الكيانات المقابلة الأخرى.</span><span class="sxs-lookup"><span data-stu-id="307d6-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="307d6-110">يوضح المخطط التالي إنشاء ثلاث علاقات نظام عند مطابقة كيان العميل مع الكيانات الإضافية لإنتاج كيان ملف تعريف العميل النهائي.</span><span class="sxs-lookup"><span data-stu-id="307d6-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="307d6-111">![إنشاء علاقة](media/relationships-entities-merge.png "إنشاء علاقة")</span><span class="sxs-lookup"><span data-stu-id="307d6-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="307d6-112">تم إنشاء ***العلاقة* CustomerToContact** بين كيان العميل وكيان جهة الاتصال.</span><span class="sxs-lookup"><span data-stu-id="307d6-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="307d6-113">يعمل كيان العميل على ربط حقل المفتاح الأساسي **Contact_contactId** بحقل المفتاح الأساسي لكيان جهة الاتصال **contactId**.</span><span class="sxs-lookup"><span data-stu-id="307d6-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="307d6-114">تم إنشاء ***العلاقة* CustomerToAccount** بين كيان العميل وكيان الحساب.</span><span class="sxs-lookup"><span data-stu-id="307d6-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="307d6-115">يعمل كيان العميل على ربط حقل المفتاح الأساسي **Account_contactId** بحقل المفتاح الأساسي لكيان الحساب **contactId**.</span><span class="sxs-lookup"><span data-stu-id="307d6-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="307d6-116">تم إنشاء ***العلاقة* CustomerToWebAccount** بين كيان العميل وكيان حساب الويب.</span><span class="sxs-lookup"><span data-stu-id="307d6-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="307d6-117">يعمل كيان العميل على ربط حقل المفتاح الأساسي **WebAccount_webaccountId** بحقل المفتاح الأساسي لكيان الحساب **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="307d6-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="307d6-118">إنشاء علاقة</span><span class="sxs-lookup"><span data-stu-id="307d6-118">Create a relationship</span></span>

<span data-ttu-id="307d6-119">قم بتعريف العلاقات المخصصة في الصفحة **العلاقات**.</span><span class="sxs-lookup"><span data-stu-id="307d6-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="307d6-120">تتكون كل علاقة من كيان مصدر (الكيان الذي يحتوي على المفتاح الخارجي) وكيان هدف (الكيان الذي يشير إليه المفتاح الخارجي للكيان المصدر).</span><span class="sxs-lookup"><span data-stu-id="307d6-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="307d6-121">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **العلاقات**.</span><span class="sxs-lookup"><span data-stu-id="307d6-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="307d6-122">حدد **علاقة جديدة**.</span><span class="sxs-lookup"><span data-stu-id="307d6-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="307d6-123">في الجزء **إضافة علاقة**، أدخل المعلومات التالية:</span><span class="sxs-lookup"><span data-stu-id="307d6-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="307d6-124">![إدخال تفاصيل العلاقة](media/relationships-add.png "إدخال تفاصيل العلاقة")</span><span class="sxs-lookup"><span data-stu-id="307d6-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="307d6-125">**اسم العلاقة**: الاسم الذي يعكس غرض العلاقة (على سبيل المثال، **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="307d6-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="307d6-126">**الوصف**: وصف العلاقة.</span><span class="sxs-lookup"><span data-stu-id="307d6-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="307d6-127">**الكيان المصدر**: حدد الكيان الذي يتم استخدامه كمصدر في العلاقة (على سبيل المثال، WebLog).</span><span class="sxs-lookup"><span data-stu-id="307d6-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="307d6-128">**العلاقة الأساسية**: حدد العلاقة الأساسية لسجلات الكيان المصدر.</span><span class="sxs-lookup"><span data-stu-id="307d6-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="307d6-129">على سبيل المثال، "متعدد" تعني أن سجلات Weblog المتعددة مرتبطة بـ WebAccount واحد.</span><span class="sxs-lookup"><span data-stu-id="307d6-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="307d6-130">**حقل مفتاح المصدر**: يمثل هذا حقل المفتاح الخارجي في الكيان المصدر.</span><span class="sxs-lookup"><span data-stu-id="307d6-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="307d6-131">على سبيل المثال، يحتوي WebLog على حقل المفتاح الخارجي **accountId**.</span><span class="sxs-lookup"><span data-stu-id="307d6-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="307d6-132">**الكيان الهدف**: حدد الكيان الذي يتم استخدامه كهدف في العلاقة (على سبيل المثال، WebAccount).</span><span class="sxs-lookup"><span data-stu-id="307d6-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="307d6-133">**علاقة الهدف الأساسية**: حدد العلاقة الأساسية لسجلات الكيان الهدف.</span><span class="sxs-lookup"><span data-stu-id="307d6-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="307d6-134">على سبيل المثال، "واحد" تعني أن سجلات Weblog المتعددة مرتبطة بـ WebAccount واحد.</span><span class="sxs-lookup"><span data-stu-id="307d6-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="307d6-135">**حقل الهدف الأساسي**: يمثل هذا الحقل الحقل الأساسي للكيان الهدف.</span><span class="sxs-lookup"><span data-stu-id="307d6-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="307d6-136">على سبيل المثال، يحتوي WebAccount على الحقل الأساسي **accountId**.</span><span class="sxs-lookup"><span data-stu-id="307d6-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="307d6-137">لا يتم دعم سوى العلاقات متعدد إلى واحد وواحد إلى واحد فقط.</span><span class="sxs-lookup"><span data-stu-id="307d6-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="307d6-138">يمكن إنشاء العلاقات متعدد إلى متعدد باستخدام العلاقتين متعدد إلى واحد وكيان ارتباط (كيان يستخدم لتوصيل الكيان المصدر والكيان الهدف).</span><span class="sxs-lookup"><span data-stu-id="307d6-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="307d6-139">حذف علاقة</span><span class="sxs-lookup"><span data-stu-id="307d6-139">Delete a relationship</span></span>

1. <span data-ttu-id="307d6-140">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **العلاقات**.</span><span class="sxs-lookup"><span data-stu-id="307d6-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="307d6-141">حدد خانات الاختيار للعلاقات التي تريد حذفها.</span><span class="sxs-lookup"><span data-stu-id="307d6-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="307d6-142">حدد **حذف** في أعلى الجدول **العلاقات**.</span><span class="sxs-lookup"><span data-stu-id="307d6-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="307d6-143">قم بتأكيد الحذف.</span><span class="sxs-lookup"><span data-stu-id="307d6-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="307d6-144">الخطوة التالية</span><span class="sxs-lookup"><span data-stu-id="307d6-144">Next step</span></span>

<span data-ttu-id="307d6-145">يتم استخدام العلاقات النظام والمخصصة لإنشاء المقاطع التي تستند إلى مصادر البيانات المتعددة التي لم تعد معزولة.</span><span class="sxs-lookup"><span data-stu-id="307d6-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="307d6-146">للمزيد من المعلومات، راجع [الشرائح](segments.md).</span><span class="sxs-lookup"><span data-stu-id="307d6-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]