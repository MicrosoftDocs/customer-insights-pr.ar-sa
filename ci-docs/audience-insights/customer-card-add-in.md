---
title: الوظيفة الإضافية لبطاقة العميل في تطبيقات Dynamics 365
description: إظهار البيانات من معلومات الجمهور في تطبيقات Dynamics 365 باستخدام هذه الوظيفة الإضافية.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059572"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="d9c30-103">الوظيفة الإضافية لبطاقة عميل (معاينة)</span><span class="sxs-lookup"><span data-stu-id="d9c30-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d9c30-104">احصل على طريقة عرض 360 درجة لعملائك مباشرةً في تطبيقات Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d9c30-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="d9c30-105">مع تثبيت الوظيفة الإضافية لبطاقة العميل في تطبيق Dynamics 365 المدعم، يمكنك اختيار عرض البيانات السكانية والرؤى والمخططات الزمنية للنشاط.</span><span class="sxs-lookup"><span data-stu-id="d9c30-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="d9c30-106">سوف تسترد الوظيفة الإضافية البيانات من Customer Insights دون التأثير على البيانات في تطبيق Dynamics 365 المتصل.</span><span class="sxs-lookup"><span data-stu-id="d9c30-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d9c30-107">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="d9c30-107">Prerequisites</span></span>

- <span data-ttu-id="d9c30-108">تعمل هذه الوظيفة الإضافية فقط مع تطبيقات Dynamics 365 التي تعتمد على نموذج، مثل Sales أو Customer Service الإصدار 9.0 وما يليه.</span><span class="sxs-lookup"><span data-stu-id="d9c30-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="d9c30-109">لكي يتم تعيين بيانات Dynamics 365 إلى ملفات تعريف العملاء لمعلومات الجمهور يلزم [استيعابها من تطبيق Dynamics 365 باستخدام موصل Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="d9c30-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="d9c30-110">كافة مستخدمي Dynamics 365 من الوظيفة الإضافية لبطاقة العميل يجب [إضافتهم كمستخدمين](permissions.md) في معلومات الجمهور لرؤية البيانات.</span><span class="sxs-lookup"><span data-stu-id="d9c30-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="d9c30-111">[إمكانيات البحث والتصفية المكونة](search-filter-index.md) في معلومات الجمهور تكون مطلوبة للبحث عن البيانات للعمل.</span><span class="sxs-lookup"><span data-stu-id="d9c30-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="d9c30-112">يعتمد كل عنصر تحكم من الوظيفة الإضافية على بيانات محددة في معلومات الجمهور:</span><span class="sxs-lookup"><span data-stu-id="d9c30-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="d9c30-113">التحكم في المقاييس: يتطلب [مقاييس مكوّنة](measures.md).</span><span class="sxs-lookup"><span data-stu-id="d9c30-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="d9c30-114">تحكم الذكاء: يتطلب بيانات تم إنشاؤها باستخدام [التنبؤات](predictions.md) أو [النماذج المخصصة](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="d9c30-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="d9c30-115">التحكم في البيانات السكانية‬: تتوفر حقول البيانات السكانية‬ (مثل العمر أو الجنس) في ملف تعريف العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="d9c30-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="d9c30-116">عنصر تحكم الإثراء: يتطلب تطبيق [عمليات إثراء](enrichment-hub.md) نشطة على ملفات تعريف العملاء.</span><span class="sxs-lookup"><span data-stu-id="d9c30-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="d9c30-117">التحكم في المخطط الزمني: يتطلب [أنشطة مكوّنة](activities.md).</span><span class="sxs-lookup"><span data-stu-id="d9c30-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="d9c30-118">تثبيت الوظيفة الإضافية لبطاقة عميل</span><span class="sxs-lookup"><span data-stu-id="d9c30-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="d9c30-119">تعتبر الوظيفة الإضافية لبطاقات العملاء حلاً لتطبيقات customer engagement في Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d9c30-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="d9c30-120">لتثبيت الحل، انتقل إلى AppSource وابحث عن **بطاقة عميل Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="d9c30-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="d9c30-121">حدد [تشغيل الوظيفة الإضافية لبطاقة العميل AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) وحدد **احصل عليها الآن**.</span><span class="sxs-lookup"><span data-stu-id="d9c30-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="d9c30-122">قد تحتاج إلى تسجيل الدخول باستخدام بيانات المسؤول الخاصة بك لتطبيق Dynamics 365 لتثبيت الحل.</span><span class="sxs-lookup"><span data-stu-id="d9c30-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="d9c30-123">يمكن أن يستغرق تثبيت الحل للبيئة الخاصة بك بعض الوقت.</span><span class="sxs-lookup"><span data-stu-id="d9c30-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="d9c30-124">تكوين الوظيفة الإضافية لبطاقة العميل</span><span class="sxs-lookup"><span data-stu-id="d9c30-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="d9c30-125">بصفتك مسؤول، انتقل إلى قسم **الإعدادات** في Dynamics 365، ثم حدد **الحلول**.</span><span class="sxs-lookup"><span data-stu-id="d9c30-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="d9c30-126">حدد الارتباط **اسم العرض** لحل **Dynamics 365 Customer Insights الوظيفة الإضافية لبطاقة العميل (معاينة)**.</span><span class="sxs-lookup"><span data-stu-id="d9c30-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d9c30-127">![تحديد اسم العرض](media/select-display-name.png "تحديد اسم العرض")</span><span class="sxs-lookup"><span data-stu-id="d9c30-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="d9c30-128">حدد **تسجيل الدخول** وأدخل بيانات الاعتماد الخاصة بحساب المسؤول الذي تستخدمه لتكوين Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d9c30-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d9c30-129">تحقق من عدم قيام أداة حظر العناصر المنبثقة في المستعرض بحظر نافذة المصادقة عندما تقوم بتحديد زر **تسجيل الدخول**.</span><span class="sxs-lookup"><span data-stu-id="d9c30-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="d9c30-130">حدد بيئة Customer Insights التي تريد إحضار البيانات منها.</span><span class="sxs-lookup"><span data-stu-id="d9c30-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="d9c30-131">قم بتعريف تعيين الحقل للسجلات في تطبيق Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d9c30-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="d9c30-132">تبعًا لبياناتك في Customer Insights يمكنك اختيار تعيين الخيارات التالية:</span><span class="sxs-lookup"><span data-stu-id="d9c30-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="d9c30-133">للتعيين مع جهة اتصال، حدد الحقل الموجود في كيان العميل الذي يتطابق مع معرف كيان جهة الاتصال.</span><span class="sxs-lookup"><span data-stu-id="d9c30-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="d9c30-134">للتعيين مع حساب، حدد الحقل الموجود في كيان العميل الذي يتطابق مع معرف كيان الحساب.</span><span class="sxs-lookup"><span data-stu-id="d9c30-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d9c30-135">![حقل مُعرف جهة الاتصال](media/contact-id-field.png "حقل مُعرف جهة الاتصال")</span><span class="sxs-lookup"><span data-stu-id="d9c30-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="d9c30-136">حدد **حفظ التكوين** لحفظ الإعدادات.</span><span class="sxs-lookup"><span data-stu-id="d9c30-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="d9c30-137">بعد ذلك، يجب عليك تعيين أدوار أمان في Dynamics 365 حتى يتمكن المستخدمون من تخصيص بطاقة العملاء ومراجعتها.</span><span class="sxs-lookup"><span data-stu-id="d9c30-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="d9c30-138">في Dynamics 365، انتقل إلى **الإعدادات** > **الأمان** > **المستخدمون**.</span><span class="sxs-lookup"><span data-stu-id="d9c30-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="d9c30-139">حدد المستخدمين لتحرير أدوار المستخدم وحدد **إدارة الأدوار**.</span><span class="sxs-lookup"><span data-stu-id="d9c30-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="d9c30-140">تعيين دور **مخصص بطاقة Customer Insights** بالنسبة للمستخدمين الذين سيقومون بتخصيص المحتوى المعروض على البطاقة للمؤسسة بالكامل.</span><span class="sxs-lookup"><span data-stu-id="d9c30-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="d9c30-141">إضافة عناصر تحكم بطاقة العميل إلى النماذج</span><span class="sxs-lookup"><span data-stu-id="d9c30-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="d9c30-142">لإضافة عناصر تحكم بطاقة العميل إلى نموذج جهة الاتصال الخاص بك، انتقل إلى **الإعدادات** > **تخصيصات** في Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d9c30-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="d9c30-143">حدد **تخصيص النظام**.</span><span class="sxs-lookup"><span data-stu-id="d9c30-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="d9c30-144">استعرض إلى كيان **جهة الاتصال**، وقم بتوسيعه وحدد **النماذج**.</span><span class="sxs-lookup"><span data-stu-id="d9c30-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="d9c30-145">حدد جهة الاتصال التي ترغب في إضافة عناصر تحكم بطاقة العميل إليها.</span><span class="sxs-lookup"><span data-stu-id="d9c30-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d9c30-146">![تحديد نموذج جهة اتصال](media/contact-active-forms.png "تحديد نموذج جهة اتصال")</span><span class="sxs-lookup"><span data-stu-id="d9c30-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="d9c30-147">لإضافة عنصر تحكم، في مُحرر النماذج، قم بسحب أي حقل من **مستكشف الحقول** إلى حيث تريد أن يظهر عنصر التحكم.</span><span class="sxs-lookup"><span data-stu-id="d9c30-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="d9c30-148">حدد الحقل الذي أضفته للتو، وحدد **تغيير الخصائص**.</span><span class="sxs-lookup"><span data-stu-id="d9c30-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="d9c30-149">انتقل إلى علامة تبويب **عناصر التحكم**، ثم حدد **إضافة عنصر تحكم**.</span><span class="sxs-lookup"><span data-stu-id="d9c30-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="d9c30-150">اختر أحد عناصر التحكم المخصصة المتوفرة وحدد **إضافة**.</span><span class="sxs-lookup"><span data-stu-id="d9c30-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="d9c30-151">في مربع حوار **خصائص الحقل** ، قم بمسح خانة اختيار **‏‫عرض التسمية على النموذج‬**. </span><span class="sxs-lookup"><span data-stu-id="d9c30-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="d9c30-152">حدد الخيار **الويب** لعنصر التحكم.</span><span class="sxs-lookup"><span data-stu-id="d9c30-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="d9c30-153">بالنسبة لعنصر التحكم الإثراء، حدد نوع الإثراء الذي ترغب في عرضه عن طريق تكوين الحقل **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="d9c30-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="d9c30-154">أضف عنصر تحكم منفصل للإثراء لكل نوع من أنواع الإثراء‬.</span><span class="sxs-lookup"><span data-stu-id="d9c30-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="d9c30-155">حدد **حفظ** و **نشر** لنشر نموذج جهة الاتصال المحدثة.</span><span class="sxs-lookup"><span data-stu-id="d9c30-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="d9c30-156">الانتقال إلى نموذج جهة الاتصال المنشور.</span><span class="sxs-lookup"><span data-stu-id="d9c30-156">Go to the published contact form.</span></span> <span data-ttu-id="d9c30-157">ستشاهد عنصر التحكم المضاف حديثًا.</span><span class="sxs-lookup"><span data-stu-id="d9c30-157">You'll see the newly added control.</span></span> <span data-ttu-id="d9c30-158">قد تحتاج إلى تسجيل الدخول في المرة الأولى الذي تستخدمه فيها.</span><span class="sxs-lookup"><span data-stu-id="d9c30-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="d9c30-159">لتخصيص ما تريد عرضه في عنصر التحكم مخصص، قم بتحديد الزر تحرير في الزاوية العلوية اليُمنى.</span><span class="sxs-lookup"><span data-stu-id="d9c30-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="d9c30-160">ترقية الوظيفة الإضافية لبطاقة العميل</span><span class="sxs-lookup"><span data-stu-id="d9c30-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="d9c30-161">لا تتم ترقية الوظيفة الإضافية لبطاقة العميل بشكل تلقائي.</span><span class="sxs-lookup"><span data-stu-id="d9c30-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="d9c30-162">للترقية إلى الإصدار الأخير، اتبع هذا الإجراء في تطبيق Dynamics 365 المثبت عليه الوظيفة الإضافية.</span><span class="sxs-lookup"><span data-stu-id="d9c30-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="d9c30-163">في تطبيق Dynamics 365، انتقل إلى **الإعدادات** > **تخصيص** وحدد **الحلول**.</span><span class="sxs-lookup"><span data-stu-id="d9c30-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="d9c30-164">في جدول الوظائف الإضافية، ابحث عن **CustomerInsightsCustomerCard** وحدد الصف.</span><span class="sxs-lookup"><span data-stu-id="d9c30-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="d9c30-165">حدد **تطبيق ترقية الحل** في شريط الإجراءات.</span><span class="sxs-lookup"><span data-stu-id="d9c30-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="ترقية الحل في منطقة التخصيص في تطبيقات Dynamics 365":::

1. <span data-ttu-id="d9c30-167">بعد بدء عملية الترقية، سوف تشاهد مؤشر تحميل حتى تكتمل الترقية.</span><span class="sxs-lookup"><span data-stu-id="d9c30-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="d9c30-168">إذا لم يكن هناك إصدار جديد، فإن الترقية ستعرض رسالة خطأ.</span><span class="sxs-lookup"><span data-stu-id="d9c30-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
