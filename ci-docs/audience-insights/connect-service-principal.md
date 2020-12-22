---
title: الاتصال بحساب Azure Data Lake Storage Gen2 بواسطة كيان خدمة
description: استخدم كيان خدمة في Azure لنتائج رؤى الجمهور للاتصال بمستودع بياناتك الخاصة عند إرفاقها برؤى الجمهور.
ms.date: 11/24/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c2fae278d34fa02b9168ac70dfa8dd351653245e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644072"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="79e85-103">الاتصال بحساب Azure Data Lake Storage Gen2 بواسطة كيان خدمة Azure لرؤى الجمهور</span><span class="sxs-lookup"><span data-stu-id="79e85-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="79e85-104">يجب أن تكون دائمًا الأدوات المؤتمتة التي تستخدم خدمات Azure ذات أذونات مقيدة.</span><span class="sxs-lookup"><span data-stu-id="79e85-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="79e85-105">بدلاً من قيام التطبيقات بتسجيل الدخول كمستخدم له امتيازات كاملة، يقدم Azure كيانات الخدمة.</span><span class="sxs-lookup"><span data-stu-id="79e85-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="79e85-106">اقرأ لمعرفة كيفية توصيل رؤى الجمهور بواسطة حساب Azure Data Lake Storage Gen2 يستخدم كيان خدمة Azure بدلاً من مفاتيح حساب تخزين.</span><span class="sxs-lookup"><span data-stu-id="79e85-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="79e85-107">يمكنك استخدام كيان الخدمة من أجل [إضافة أو تحرير مجلد نموذج البيانات العامة كمصدر بيانات](connect-common-data-model.md) بشكل آمن أو [إنشاء بيئة جديدة أو تحديث بيئة موجودة](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="79e85-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

<span data-ttu-id="79e85-108">تحتاج إلى أذونات المسؤول لاشتراكك في Azure لإنشاء كيان الخدمة.</span><span class="sxs-lookup"><span data-stu-id="79e85-108">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="79e85-109">إنشاء كيان خدمة Azure لرؤى الجمهور‬</span><span class="sxs-lookup"><span data-stu-id="79e85-109">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="79e85-110">قبل إنشاء كيان خدمة جديد لرؤى الجمهور‬، تحقق مما إذا كان موجودًا بالفعل في مؤسستك.</span><span class="sxs-lookup"><span data-stu-id="79e85-110">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="79e85-111">البحث عن كيان خدمة موجود</span><span class="sxs-lookup"><span data-stu-id="79e85-111">Look for an existing service principal</span></span>

1. <span data-ttu-id="79e85-112">انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com) وسجل دخولك إلى مؤسستك.</span><span class="sxs-lookup"><span data-stu-id="79e85-112">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="79e85-113">حدد **Azure Active Directory** من خدمات Azure.</span><span class="sxs-lookup"><span data-stu-id="79e85-113">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="79e85-114">ضمن **إدارة**، حدد **تطبيقات المؤسسة**.</span><span class="sxs-lookup"><span data-stu-id="79e85-114">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="79e85-115">ابحث عن معرف تطبيق الطرف الأول لرؤى الجمهور `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` أو عن الاسم `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="79e85-115">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="79e85-116">إذا عثرت على سجل مطابق، فهذا يعني أن كيان الخدمة لرؤى الجمهور موجود.</span><span class="sxs-lookup"><span data-stu-id="79e85-116">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="79e85-117">لا حاجة إلى إنشائه من جديد.</span><span class="sxs-lookup"><span data-stu-id="79e85-117">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="لقطة شاشة تُظهر كيان الخدمة الحالي.":::
   
6. <span data-ttu-id="79e85-119">إذا لم يتم إرجاع أي نتائج، فيمكنك إنشاء كيان خدمة جديد.</span><span class="sxs-lookup"><span data-stu-id="79e85-119">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="79e85-120">إنشاء كيان خدمة جديد</span><span class="sxs-lookup"><span data-stu-id="79e85-120">Create a new service principal</span></span>

1. <span data-ttu-id="79e85-121">ثبّت الإصدار الأخير من **Azure Active Directory PowerShell for Graph**.</span><span class="sxs-lookup"><span data-stu-id="79e85-121">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="79e85-122">لمزيد من المعلومات، راجع [تثبيت Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="79e85-122">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="79e85-123">علي جهاز الكمبيوتر، حدد مفتاح Windows على لوحة المفاتيح وابحث عن **Windows PowerShell** و **تشغيل كمسؤول**.</span><span class="sxs-lookup"><span data-stu-id="79e85-123">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="79e85-124">في نافذة PowerShell التي تفتح، أدخل `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="79e85-124">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="79e85-125">أنشئ كيان الخدمة لرؤى الجمهور بواسطة الوحدة النمطية Azure AD PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79e85-125">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="79e85-126">في نافذة PowerShell، أدخل `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="79e85-126">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="79e85-127">استبدل "معرف المستأجر" بالمعرف الفعلي للمستأجر حيث تريد إنشاء كيان الخدمة.</span><span class="sxs-lookup"><span data-stu-id="79e85-127">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="79e85-128">معلمة اسم البيئة `AzureEnvironmentName` اختيارية.</span><span class="sxs-lookup"><span data-stu-id="79e85-128">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="79e85-129">أدخل `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="79e85-129">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="79e85-130">يقوم هذا الأمر بإنشاء كيان الخدمة لرؤى الجمهور على المستأجر المحدد.</span><span class="sxs-lookup"><span data-stu-id="79e85-130">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="79e85-131">منح أذونات لكيان الخدمة للوصول إلى حساب التخزين</span><span class="sxs-lookup"><span data-stu-id="79e85-131">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="79e85-132">انتقل إلى مدخل Azure لمنح أذونات لكيان الخدمة الخاص بحساب التخزين الذي ترغب في استخدامه في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="79e85-132">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="79e85-133">انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com) وسجل دخولك إلى مؤسستك.</span><span class="sxs-lookup"><span data-stu-id="79e85-133">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="79e85-134">افتح حساب التخزين الذي تريد أن يدخل إليه كيان الخدمة لرؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="79e85-134">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="79e85-135">حدد **التحكم بالوصول (IAM)** من جزء التنقل، وحدد **إضافة** > **إضافة‏‎ تعيين الدور**.</span><span class="sxs-lookup"><span data-stu-id="79e85-135">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="لقطة شاشة تُظهر مدخل Azure أثناء إضافة تعيين الدور.":::
   
1. <span data-ttu-id="79e85-137">في الجزء **إضافة تعيين الدور**، قم بتعيين الخصائص التالية:</span><span class="sxs-lookup"><span data-stu-id="79e85-137">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="79e85-138">الدور: *المساهم في بيانات مخزن البيانات الثنائية الكبيرة*</span><span class="sxs-lookup"><span data-stu-id="79e85-138">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="79e85-139">تعيين الوصول إلى: *المستخدم أو المجموعة أو كيان الخدمة*</span><span class="sxs-lookup"><span data-stu-id="79e85-139">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="79e85-140">حدد: *Dynamics 365 AI for Customer Insights* ([كيان الخدمة الذي قمت بإنشائه](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="79e85-140">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="79e85-141">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="79e85-141">Select **Save**.</span></span>

<span data-ttu-id="79e85-142">قد تستغرق فترة نشر التغييرات ما يصل إلى 15 دقيقة.</span><span class="sxs-lookup"><span data-stu-id="79e85-142">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="79e85-143">أدخل معرف مورد Azure أو تفاصيل اشتراك Azure في مرفق حساب التخزين في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="79e85-143">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="79e85-144">قم بإرفاق حساب Azure Data Lake Storage في رؤى الجمهور [لتخزين بيانات الإخراج](manage-environments.md) أو [لاستخدامه كمصدر بيانات](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="79e85-144">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="79e85-145">يتيح لك تحديد خيار Azure Data Lake الاختيار بين طريقة تستند إلى الموارد أو طريقة تستند إلى الاشتراكات.</span><span class="sxs-lookup"><span data-stu-id="79e85-145">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="79e85-146">اتبع الخطوات أدناه لتقديم المعلومات المطلوبة بالطريقة المحددة.</span><span class="sxs-lookup"><span data-stu-id="79e85-146">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resounce-based-storage-account-connection"></a><span data-ttu-id="79e85-147">‏‏اتصال حساب التخزين المستند إلى الموارد</span><span class="sxs-lookup"><span data-stu-id="79e85-147">Resounce-based storage account connection</span></span>

1. <span data-ttu-id="79e85-148">انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com)، ثم قم بتسجيل الدخول إلى اشتراكك وافتح حساب التخزين.</span><span class="sxs-lookup"><span data-stu-id="79e85-148">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="79e85-149">انتقل إلى **الإعدادات** > **خصائص** في جزء التنقل.</span><span class="sxs-lookup"><span data-stu-id="79e85-149">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="79e85-150">انسخ قيمة معرف مورد حساب التخزين.</span><span class="sxs-lookup"><span data-stu-id="79e85-150">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="انسخ معرف مورد حساب التخزين.":::

1. <span data-ttu-id="79e85-152">في رؤى الجمهور، أدخل معرف المورد في حقل المورد المعروض في شاشة اتصال حساب التخزين.</span><span class="sxs-lookup"><span data-stu-id="79e85-152">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="أدخل معلومات معرف مورد حساب التخزين.":::   
   
1. <span data-ttu-id="79e85-154">تابع تنفيذ الخطوات المتبقية في رؤى الجمهور لإرفاق حساب التخزين.</span><span class="sxs-lookup"><span data-stu-id="79e85-154">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="79e85-155">‏‏اتصال حساب التخزين المستند إلى الاشتراكات</span><span class="sxs-lookup"><span data-stu-id="79e85-155">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="79e85-156">انتقل إلى [مدخل مسؤول Azure](https://portal.azure.com)، ثم قم بتسجيل الدخول إلى اشتراكك وافتح حساب التخزين.</span><span class="sxs-lookup"><span data-stu-id="79e85-156">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="79e85-157">انتقل إلى **الإعدادات** > **خصائص** في جزء التنقل.</span><span class="sxs-lookup"><span data-stu-id="79e85-157">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="79e85-158">راجع **اشتراك** حساب التخزين بالإضافة إلى **مجموعة الموارد** و **الاسم** للتأكد من أنك تحدد القيم الصحيحة في رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="79e85-158">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="79e85-159">في رؤى الجمهور، اختر القيم أو الحقول المطابقة عند إرفاق حساب التخزين.</span><span class="sxs-lookup"><span data-stu-id="79e85-159">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>

   :::image type="content" source="media/ADLS-SP-SubscriptionConnection.png" alt-text="أدخل معلومات معرف مورد حساب التخزين.":::
   
1. <span data-ttu-id="79e85-161">تابع تنفيذ الخطوات المتبقية في رؤى الجمهور لإرفاق حساب التخزين.</span><span class="sxs-lookup"><span data-stu-id="79e85-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>
