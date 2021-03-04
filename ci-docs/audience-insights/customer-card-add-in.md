---
title: تثبيت واستخدام الوظيفة الإضافية لبطاقة عميل
description: تثبيت وتكوين الوظيفة الإضافية لبطاقة عميل لـ Dynamics 365 Customer Insights
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268028"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="d1a53-103">الوظيفة الإضافية لبطاقة عميل (معاينة)</span><span class="sxs-lookup"><span data-stu-id="d1a53-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d1a53-104">احصل على طريقة عرض 360 درجة لعملائك مباشرةً في تطبيقات Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d1a53-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="d1a53-105">قم بعرض الإحصائيات السكانية والمعلومات والمخططات الزمنية للأنشطة باستخدام الوظيفة الإضافية لبطاقة العملاء.</span><span class="sxs-lookup"><span data-stu-id="d1a53-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d1a53-106">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="d1a53-106">Prerequisites</span></span>

- <span data-ttu-id="d1a53-107">تطبيق Dynamics 365 (مثل مركز المبيعات أو مركز خدمة العملاء)، والإصدار 9.0 وأحدث في حالة تمكين الواجهة الموحدة.</span><span class="sxs-lookup"><span data-stu-id="d1a53-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="d1a53-108">ملفات تعريف العملاء التي تم [استيعابها من تطبيق Dynamics 365 باستخدام Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="d1a53-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="d1a53-109">يجب إضافة مستخدمي الوظيفة الإضافية لبطاقات العميل [كمستخدمين](permissions.md) في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="d1a53-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="d1a53-110">[تكوين قدرات البحث والتصفية](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="d1a53-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="d1a53-111">التحكم في البيانات السكانية‬: تتوفر حقول البيانات السكانية‬ (مثل العمر أو الجنس) في ملف تعريف العميل الموحد.</span><span class="sxs-lookup"><span data-stu-id="d1a53-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="d1a53-112">عنصر تحكم الإثراء: يتطلب تطبيق [عمليات إثراء](enrichment-hub.md) نشطة على ملفات تعريف العملاء.</span><span class="sxs-lookup"><span data-stu-id="d1a53-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="d1a53-113">التحكم في الذكاء: يحتاج إلى بيانات يتم إنشاؤها باستخدام التعلم الآلي من Azure ([التوقعات](predictions.md) أو [النماذج المخصصة](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="d1a53-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="d1a53-114">التحكم في المقاييس: يتطلب [مقاييس مكوّنة](measures.md).</span><span class="sxs-lookup"><span data-stu-id="d1a53-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="d1a53-115">التحكم في المخطط الزمني: يتطلب [أنشطة مكوّنة](activities.md).</span><span class="sxs-lookup"><span data-stu-id="d1a53-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="d1a53-116">تثبيت الوظيفة الإضافية لبطاقة عميل</span><span class="sxs-lookup"><span data-stu-id="d1a53-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="d1a53-117">تعتبر الوظيفة الإضافية لبطاقات العملاء حلاً لتطبيقات customer engagement في Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d1a53-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="d1a53-118">لتثبيت الحل، انتقل إلى AppSource وابحث عن **بطاقة عميل Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="d1a53-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="d1a53-119">حدد [تشغيل الوظيفة الإضافية لبطاقة العميل AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) وحدد **احصل عليها الآن**.</span><span class="sxs-lookup"><span data-stu-id="d1a53-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="d1a53-120">قد تحتاج إلى تسجيل الدخول باستخدام بيانات المسؤول الخاصة بك لتطبيق Dynamics 365 لتثبيت الحل.</span><span class="sxs-lookup"><span data-stu-id="d1a53-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="d1a53-121">يمكن أن يستغرق تثبيت الحل للبيئة الخاصة بك بعض الوقت.</span><span class="sxs-lookup"><span data-stu-id="d1a53-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="d1a53-122">تكوين الوظيفة الإضافية لبطاقة العميل</span><span class="sxs-lookup"><span data-stu-id="d1a53-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="d1a53-123">بصفتك مسؤول، انتقل إلى قسم **الإعدادات** في Dynamics 365، ثم حدد **الحلول**.</span><span class="sxs-lookup"><span data-stu-id="d1a53-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="d1a53-124">حدد الارتباط **اسم العرض** لحل **Dynamics 365 Customer Insights الوظيفة الإضافية لبطاقة العميل (معاينة)**.</span><span class="sxs-lookup"><span data-stu-id="d1a53-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d1a53-125">![تحديد اسم العرض](media/select-display-name.png "تحديد اسم العرض")</span><span class="sxs-lookup"><span data-stu-id="d1a53-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="d1a53-126">حدد **تسجيل الدخول** وأدخل بيانات الاعتماد الخاصة بحساب المسؤول الذي تستخدمه لتكوين Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d1a53-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d1a53-127">تحقق من عدم قيام أداة حظر العناصر المنبثقة في المستعرض بحظر نافذة المصادقة عندما تقوم بتحديد زر **تسجيل الدخول**.</span><span class="sxs-lookup"><span data-stu-id="d1a53-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="d1a53-128">حدد التي البيئة تريد إحضار البيانات منها.</span><span class="sxs-lookup"><span data-stu-id="d1a53-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="d1a53-129">حدد تعيين الحقل للسجلات الموجودة في تطبيق Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d1a53-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="d1a53-130">للتعيين مع جهة اتصال، حدد الحقل الموجود في كيان العميل الذي يتطابق مع معرف كيان جهة الاتصال.</span><span class="sxs-lookup"><span data-stu-id="d1a53-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="d1a53-131">للتعيين مع حساب، حدد الحقل الموجود في كيان العميل الذي يتطابق مع معرف كيان الحساب.</span><span class="sxs-lookup"><span data-stu-id="d1a53-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="d1a53-132">![حقل مُعرف جهة الاتصال](media/contact-id-field.png "حقل مُعرف جهة الاتصال")</span><span class="sxs-lookup"><span data-stu-id="d1a53-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="d1a53-133">حدد **حفظ التكوين** لحفظ الإعدادات.</span><span class="sxs-lookup"><span data-stu-id="d1a53-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="d1a53-134">بعد ذلك، يجب عليك تعيين أدوار أمان في Dynamics 365 حتى يتمكن المستخدمون من تخصيص بطاقة العملاء ومراجعتها.</span><span class="sxs-lookup"><span data-stu-id="d1a53-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="d1a53-135">في Dynamics 365، انتقل إلى **الإعدادات** > **الأمان** > **المستخدمون**.</span><span class="sxs-lookup"><span data-stu-id="d1a53-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="d1a53-136">حدد المستخدمين لتحرير أدوار المستخدم وحدد **إدارة الأدوار**.</span><span class="sxs-lookup"><span data-stu-id="d1a53-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="d1a53-137">تعيين دور **مخصص بطاقة Customer Insights** بالنسبة للمستخدمين الذين سيقومون بتخصيص المحتوى المعروض على البطاقة للمؤسسة بالكامل.</span><span class="sxs-lookup"><span data-stu-id="d1a53-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="d1a53-138">إضافة عناصر تحكم بطاقة العميل إلى النماذج</span><span class="sxs-lookup"><span data-stu-id="d1a53-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="d1a53-139">لإضافة عناصر تحكم بطاقة العميل إلى نموذج جهة الاتصال الخاص بك، انتقل إلى **الإعدادات** > **تخصيصات** في Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="d1a53-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="d1a53-140">حدد **تخصيص النظام**.</span><span class="sxs-lookup"><span data-stu-id="d1a53-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="d1a53-141">استعرض إلى كيان **جهة الاتصال**، وقم بتوسيعه وحدد **النماذج**.</span><span class="sxs-lookup"><span data-stu-id="d1a53-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="d1a53-142">حدد جهة الاتصال التي ترغب في إضافة عناصر تحكم بطاقة العميل إليها.</span><span class="sxs-lookup"><span data-stu-id="d1a53-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="d1a53-143">![تحديد نموذج جهة اتصال](media/contact-active-forms.png "تحديد نموذج جهة اتصال")</span><span class="sxs-lookup"><span data-stu-id="d1a53-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="d1a53-144">لإضافة عنصر تحكم، في مُحرر النماذج، قم بسحب أي حقل من **مستكشف الحقول** إلى حيث تريد أن يظهر عنصر التحكم.</span><span class="sxs-lookup"><span data-stu-id="d1a53-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="d1a53-145">حدد الحقل الذي أضفته للتو، وحدد **تغيير الخصائص**.</span><span class="sxs-lookup"><span data-stu-id="d1a53-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="d1a53-146">انتقل إلى علامة تبويب **عناصر التحكم**، ثم حدد **إضافة عنصر تحكم**.</span><span class="sxs-lookup"><span data-stu-id="d1a53-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="d1a53-147">اختر أحد عناصر التحكم المخصصة المتوفرة وحدد **إضافة**.</span><span class="sxs-lookup"><span data-stu-id="d1a53-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="d1a53-148">في مربع حوار **خصائص الحقل** ، قم بمسح خانة اختيار **‏‫عرض التسمية على النموذج‬**. </span><span class="sxs-lookup"><span data-stu-id="d1a53-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="d1a53-149">حدد الخيار **الويب** لعنصر التحكم.</span><span class="sxs-lookup"><span data-stu-id="d1a53-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="d1a53-150">بالنسبة لعنصر التحكم الإثراء، حدد نوع الإثراء الذي ترغب في عرضه عن طريق تكوين الحقل **enrichmentType**.</span><span class="sxs-lookup"><span data-stu-id="d1a53-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="d1a53-151">أضف عنصر تحكم منفصل للإثراء لكل نوع من أنواع الإثراء‬.</span><span class="sxs-lookup"><span data-stu-id="d1a53-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="d1a53-152">حدد **حفظ** و **نشر** لنشر نموذج جهة الاتصال المحدثة.</span><span class="sxs-lookup"><span data-stu-id="d1a53-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="d1a53-153">الانتقال إلى نموذج جهة الاتصال المنشور.</span><span class="sxs-lookup"><span data-stu-id="d1a53-153">Go to the published contact form.</span></span> <span data-ttu-id="d1a53-154">ستشاهد عنصر التحكم المضاف حديثًا.</span><span class="sxs-lookup"><span data-stu-id="d1a53-154">You'll see the newly added control.</span></span> <span data-ttu-id="d1a53-155">قد تحتاج إلى تسجيل الدخول في المرة الأولى الذي تستخدمه فيها.</span><span class="sxs-lookup"><span data-stu-id="d1a53-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="d1a53-156">لتخصيص ما تريد عرضه في عنصر التحكم مخصص، قم بتحديد الزر تحرير في الزاوية العلوية اليُمنى.</span><span class="sxs-lookup"><span data-stu-id="d1a53-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="d1a53-157">ترقية الوظيفة الإضافية لبطاقة العميل</span><span class="sxs-lookup"><span data-stu-id="d1a53-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="d1a53-158">لا تتم ترقية الوظيفة الإضافية لبطاقة العميل بشكل تلقائي.</span><span class="sxs-lookup"><span data-stu-id="d1a53-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="d1a53-159">للترقية إلى الإصدار الأخير، اتبع هذا الإجراء في تطبيق Dynamics 365 المثبت عليه الوظيفة الإضافية.</span><span class="sxs-lookup"><span data-stu-id="d1a53-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="d1a53-160">في تطبيق Dynamics 365، انتقل إلى **الإعدادات** > **تخصيص** وحدد **الحلول**.</span><span class="sxs-lookup"><span data-stu-id="d1a53-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="d1a53-161">في جدول الوظائف الإضافية، ابحث عن **CustomerInsightsCustomerCard** وحدد الصف.</span><span class="sxs-lookup"><span data-stu-id="d1a53-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="d1a53-162">حدد **تطبيق ترقية الحل** في شريط الإجراءات.</span><span class="sxs-lookup"><span data-stu-id="d1a53-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="ترقية الحل في منطقة التخصيص في تطبيقات Dynamics 365":::

1. <span data-ttu-id="d1a53-164">بعد بدء عملية الترقية، سوف تشاهد مؤشر تحميل حتى تكتمل الترقية.</span><span class="sxs-lookup"><span data-stu-id="d1a53-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="d1a53-165">إذا لم يكن هناك إصدار جديد، فإن الترقية ستعرض رسالة خطأ.</span><span class="sxs-lookup"><span data-stu-id="d1a53-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]