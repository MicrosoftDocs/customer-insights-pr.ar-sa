---
title: تعيين الكيانات لتوحيد البيانات
description: تعيين البيانات لإنشاء ملفات تعريف العملاء الموحدة.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: e98c7717f7707d43a9fd1fc6f6b0e9c49e4e7ee0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4404932"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="5be2b-103">تعيين الكيانات والسمات</span><span class="sxs-lookup"><span data-stu-id="5be2b-103">Map entities and attributes</span></span>

<span data-ttu-id="5be2b-104">**التعيين** هو المرحلة الأولى في عملية توحيد البيانات في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="5be2b-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="5be2b-105">يتكون التعيين من ثلاث مراحل.</span><span class="sxs-lookup"><span data-stu-id="5be2b-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="5be2b-106">*تحديد الكيان*: تحديد الكيانات القابلة للدمج التي تؤدي إلى مجموعة بيانات تحتوي على المزيد من المعلومات الكاملة حول عملائك.</span><span class="sxs-lookup"><span data-stu-id="5be2b-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="5be2b-107">*تحديد السمة*: بالنسبة لكل كيان، حدد الأعمدة التي ترغب في دمجها وتسويتها في مراحل *المطابقة* و *الدمج*.</span><span class="sxs-lookup"><span data-stu-id="5be2b-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="5be2b-108">تسمى هذه الأعمدة *سمات*.</span><span class="sxs-lookup"><span data-stu-id="5be2b-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="5be2b-109">*المفتاح الأساسي وتحديد النوع الدلالي*: لكل كيان، قم بتعريف سمة ترغب تحديدها كمفتاح أساسي لهذا الكيان، ولكل سمة، قم بتعريف نوع دلالي يصف هذه السمة.</span><span class="sxs-lookup"><span data-stu-id="5be2b-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="5be2b-110">لمزيد من المعلومات حول التدفق العام لتوحيد البيانات، راجع [توحيد](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="5be2b-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="5be2b-111">حدد الكيانات الأولى</span><span class="sxs-lookup"><span data-stu-id="5be2b-111">Select the first entities</span></span>

1. <span data-ttu-id="5be2b-112">في رؤى الجمهور، انتقل إلى **البيانات** > **توحيد** > **تعيين**.</span><span class="sxs-lookup"><span data-stu-id="5be2b-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="5be2b-113">ابدأ مرحلة التعيين عن طريق تحديد **تحديد كيانات**.</span><span class="sxs-lookup"><span data-stu-id="5be2b-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="5be2b-114">حدد الكيانات والسمات التي ترغب في استخدامها في مرحلتي *المطابقة* و *الدمج*.</span><span class="sxs-lookup"><span data-stu-id="5be2b-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="5be2b-115">يمكنك تحديد السمات المطلوبة بشكل فردي من أحد الكيانات أو تضمين كافة السمات من أحد الكيانات من خلال تحديد خانة الاختيار **تضمين جميع الحقول** على مستوى الكيان.</span><span class="sxs-lookup"><span data-stu-id="5be2b-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="5be2b-116">نوصي بتحديد كيانين على الاقل للاستفادة من عملية توحيد البيانات.</span><span class="sxs-lookup"><span data-stu-id="5be2b-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5be2b-117">![مثال إضافة الكيانات](media/data-manager-configure-map-add-entities-example.png "مثال إضافة الكيانات")</span><span class="sxs-lookup"><span data-stu-id="5be2b-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="5be2b-118">في هذا المثال، نضيف الكيانين **eCommerceContacts** و **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="5be2b-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="5be2b-119">ومن خلال اختيار هذين الكيانين، يمكنك اشتقاق الرؤى التي بناء عليها يكون عملاء الأعمال عبر الإنترنت أعضاء في برامج الولاء.</span><span class="sxs-lookup"><span data-stu-id="5be2b-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="5be2b-120">يمكنك البحث حسب الكلمات الأساسية عبر كل السمات والكيانات لتحديد السمات المطلوبة التي تريد تعيينها.</span><span class="sxs-lookup"><span data-stu-id="5be2b-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5be2b-121">![مثال حقول البحث](media/data-manager-configure-map-search-fields-example.png "مثال حقول البحث")</span><span class="sxs-lookup"><span data-stu-id="5be2b-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="5be2b-122">حدد **تطبيق** لتأكيد التحديدات.</span><span class="sxs-lookup"><span data-stu-id="5be2b-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="5be2b-123">حدد المفتاح الأساسي والنوع الدلالي للسمات</span><span class="sxs-lookup"><span data-stu-id="5be2b-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="5be2b-124">بعد تحديد الكيانات، تسرد الصفحة **تعيين** الكيانات المحددة لمراجعتك.</span><span class="sxs-lookup"><span data-stu-id="5be2b-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="5be2b-125">حدد المفتاح الأساسي لكيان وحدد النوع الدلالي لسمة في الكيان.</span><span class="sxs-lookup"><span data-stu-id="5be2b-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="5be2b-126">**المفتاح الأساسي**: حدد سمة واحدة كمفتاح أساسي لكل كيان من الكيانات الخاصة بك.</span><span class="sxs-lookup"><span data-stu-id="5be2b-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="5be2b-127">كي تكون سمة مفتاحًا أساسيًا صالحًا، يجب ألا تتضمن قيمًا مكررة أو قيمًا مفقودة أو قيمًا فارغة.</span><span class="sxs-lookup"><span data-stu-id="5be2b-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="5be2b-128">يتم دعم سمات نوع بيانات السلسلة والعدد الصحيح والمعرف الفريد العمومي (GUID) كمفاتيح أساسيه سيتم عرضها في حقل للاختيار من بينها.</span><span class="sxs-lookup"><span data-stu-id="5be2b-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="5be2b-129">**النوع الدلالي للسمة**: فئات السمات، مثل عنوان البريد الإلكتروني أو الاسم.</span><span class="sxs-lookup"><span data-stu-id="5be2b-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="5be2b-130">لاستخدام نماذج الذكاء الاصطناعي للتنبؤ الذكي للدلالات ، قم بتوفير الوقت وتحسين الدقة ، قم بتعيين **التعيين الذكي** إلى **تشغيل**.</span><span class="sxs-lookup"><span data-stu-id="5be2b-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="5be2b-131">يسلط التعيين الذكي الضوء على توصيات الدلالات المستندة إلى الذكاء الاصطناعي في حقل **النوع**.</span><span class="sxs-lookup"><span data-stu-id="5be2b-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="5be2b-132">إذا قمت بتعيينه إلى **إيقاف التشغيل**، ستظهر لك توصيات التعيين المنتظمة الخاصة بنا.</span><span class="sxs-lookup"><span data-stu-id="5be2b-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="5be2b-133">يمكنك تحديد أي نوع دلالي من قائمة الخيارات المتاحة وتجاوز التحديد المقترح.</span><span class="sxs-lookup"><span data-stu-id="5be2b-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5be2b-134">![نوع السمة والتنبؤ الدلالي](media/data-manager-configure-map-add-attributes-semantic-prediction.png "نوع السمة والتنبؤ الدلالي")</span><span class="sxs-lookup"><span data-stu-id="5be2b-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="5be2b-135">من المُمكن أيضًا إضافة نوع كيان دلالي.</span><span class="sxs-lookup"><span data-stu-id="5be2b-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="5be2b-136">حدد حقل النوع لسمة، ثم اكتب اسم نوع السمة الدلالي.</span><span class="sxs-lookup"><span data-stu-id="5be2b-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="5be2b-137">وبهذه الطريقة، يُمكنك أيضًا تغيير أنواع السمات التي تم تعريفها بواسطة النظام.</span><span class="sxs-lookup"><span data-stu-id="5be2b-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="5be2b-138">يتم تجميع كافة السمات التي يتم تعريف النوع الدلالي لها بشكل تلقائي في القسم **مراجعة الحقول المعينة**.</span><span class="sxs-lookup"><span data-stu-id="5be2b-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="5be2b-139">راجع هذه السمات وأنواعها الدلالية لأنه سيتم استخدامها لدمج كياناتك في خطوة الدمج لتوحيد البيانات.</span><span class="sxs-lookup"><span data-stu-id="5be2b-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="5be2b-140">يتم تجميع السمات التي لم يتم تعيينها تلقائيًا إلى نوع دلالي في القسم **تعريف البيانات في جميع الحقول غير المعينة**.</span><span class="sxs-lookup"><span data-stu-id="5be2b-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="5be2b-141">حدد حقل النوع الدلالي للسمات غير المعينة، أو ادخل اسم نوع السمة المخصص.</span><span class="sxs-lookup"><span data-stu-id="5be2b-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5be2b-142">![المفتاح الأساسي ونوع السمة](media/data-manager-configure-map-add-attributes.png "المفتاح الأساسي ونوع السمة")</span><span class="sxs-lookup"><span data-stu-id="5be2b-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="5be2b-143">يجب تعيين حقل واحد إلى النوع الدلالي Person.FullName لملء اسم العميل في بطاقة العميل.</span><span class="sxs-lookup"><span data-stu-id="5be2b-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="5be2b-144">وإلا، ستظهر بطاقة العميل بدون اسم.</span><span class="sxs-lookup"><span data-stu-id="5be2b-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="5be2b-145">إضافة السمات والكيانات وإزالتها</span><span class="sxs-lookup"><span data-stu-id="5be2b-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="5be2b-146">على **توحيد** > **تعيين**، حدد **تحرير الحقول**.</span><span class="sxs-lookup"><span data-stu-id="5be2b-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="5be2b-147">في الجزء **تحرير الحقول**، أضف أو أزل السمات والكيانات.</span><span class="sxs-lookup"><span data-stu-id="5be2b-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="5be2b-148">استخدم البحث أو التمرير للعثور على السمات والكيانات التي تهمك وتحديدها.</span><span class="sxs-lookup"><span data-stu-id="5be2b-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="5be2b-149">لا يمكنك إزالة سمة أو كيان إذا تمت مطابقته بالفعل.</span><span class="sxs-lookup"><span data-stu-id="5be2b-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5be2b-150">![إضافة أو إزالة السمات](media/configure-data-map-edit.png "إضافة أو إزالة السمات")</span><span class="sxs-lookup"><span data-stu-id="5be2b-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="5be2b-151">حدد **تطبيق**.</span><span class="sxs-lookup"><span data-stu-id="5be2b-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="5be2b-152">إضافة صور إلى ملفات التعريف</span><span class="sxs-lookup"><span data-stu-id="5be2b-152">Add images to profiles</span></span>

<span data-ttu-id="5be2b-153">إذا كان الكيان يحتوي على عناوين URL لصور أو شعارات ملفات التعريف المتوفرة بشكل عام، فيمكنك إضافتها إلى ملف تعريف العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="5be2b-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="5be2b-154">حدد الكيان وابحث عن الحقل الذي يحتوي على عنوان URL لصورة ملف التعريف.</span><span class="sxs-lookup"><span data-stu-id="5be2b-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="5be2b-155">في حقل إدخال **النوع**، أدخل القيمة التالية يدويًا.</span><span class="sxs-lookup"><span data-stu-id="5be2b-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="5be2b-156">بالنسبة لشخص: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="5be2b-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="5be2b-157">بالنسبة لمؤسسة: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="5be2b-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="5be2b-158">تابع خطوات التوحيد وتأكد من إضافة السمة التي تحتوي على عنوان URL للصورة أيضًا في [خطوة الدمج](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="5be2b-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="5be2b-159">تعيين السمات للمؤسسات</span><span class="sxs-lookup"><span data-stu-id="5be2b-159">Set attributes for organizations</span></span>

<span data-ttu-id="5be2b-160">بالنسبة للمؤسسات (مُعاينة)، يجب تعيين نوع السمة إلى "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="5be2b-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="5be2b-161">![المفتاح الأساسي ونوع السمة B2B](media/configure-data-map-edit-b2b.png "المفتاح الأساسي ونوع السمة B2B")</span><span class="sxs-lookup"><span data-stu-id="5be2b-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="5be2b-162">الخطوة التالية</span><span class="sxs-lookup"><span data-stu-id="5be2b-162">Next step</span></span>

<span data-ttu-id="5be2b-163">كجزء من عملية توحيد البيانات، انتقل إلى صفحة **مُطابقة**.</span><span class="sxs-lookup"><span data-stu-id="5be2b-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="5be2b-164">تفضل بزيارة [**مُطابقة**](match-entities.md) لمعرفة المزيد حول هذه المرحلة.</span><span class="sxs-lookup"><span data-stu-id="5be2b-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="5be2b-165">راجع الفيديو التالي: [بدء استخدام: إنشاء ملف تعريف عميل مُوحد](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="5be2b-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>
