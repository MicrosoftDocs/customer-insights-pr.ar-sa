---
title: التعامل مع واجهات API
description: استخدام واجهات API وفهم القيود.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689114"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="0e430-103">التعامل مع واجهات API في Customer Insights</span><span class="sxs-lookup"><span data-stu-id="0e430-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="0e430-104">يوفر Dynamics 365 Customer Insights واجهات API لبناء تطبيقاتك الخاصة استنادًا إلى البيانات الموجودة في Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0e430-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0e430-105">يمكن العثور على تفاصيل واجهات API هذه في [مرجع واجهات API‏‎ في Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="0e430-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="0e430-106">وهي تتضمن معلومات إضافية حول العمليات والمعلمات والاستجابات.</span><span class="sxs-lookup"><span data-stu-id="0e430-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="0e430-107">ترشدك هذه المقالة للوصول إلى واجهات API في Customer Insights وإنشاء تسجيل تطبيق Azure ومساعدتك على الشروع في العمل مع مكتبات العملاء المتوفرة.</span><span class="sxs-lookup"><span data-stu-id="0e430-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="0e430-108">بدء تجربة واجهات API في Customer Insights</span><span class="sxs-lookup"><span data-stu-id="0e430-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="0e430-109">[سجل دخولك](https://home.ci.ai.dynamics.com) إلى Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0e430-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="0e430-110">إذا لم يكن لديك اشتراك حتى الآن، فيمكنك [التسجيل للحصول على إصدار تجريبي من Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="0e430-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="0e430-111">لتمكين واجهات API على بيئة Customer Insights، انتقل إلى **المسؤول** > **الأذونات**.</span><span class="sxs-lookup"><span data-stu-id="0e430-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="0e430-112">ستحتاج إلى أذونات المسؤول للقيام بذلك.</span><span class="sxs-lookup"><span data-stu-id="0e430-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="0e430-113">انتقل إلى علامة تبويب **واجهات API** وحدد الزر **تمكين**.</span><span class="sxs-lookup"><span data-stu-id="0e430-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="0e430-114">يؤدي تمكين واجهات API إلى إنشاء مفتاح اشتراك أساسي وثانوي للمثيل الذي يتم استخدامه في طلبات API.</span><span class="sxs-lookup"><span data-stu-id="0e430-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="0e430-115">يمكنك إعادة إنشاء المفاتيح بتحديد **إعادة إنشاء الأساسي** أو **إعادة إنشاء الثانوي** على **المسؤول** > **الأذونات** > **واجهات API**.</span><span class="sxs-lookup"><span data-stu-id="0e430-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="تمكين واجهات API في Customer Insights":::

1. <span data-ttu-id="0e430-117">حدد **استكشاف واجهات API** لتجربة واجهات API.</span><span class="sxs-lookup"><span data-stu-id="0e430-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="0e430-118">اختر عملية واجهة API وحدد **جرّبها**.</span><span class="sxs-lookup"><span data-stu-id="0e430-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="0e430-119">في الجزء الجانبي، قم بتعيين القيمة في القائمة المنسدلة **التفويض** إلى **ضمني**.</span><span class="sxs-lookup"><span data-stu-id="0e430-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="0e430-120">يمكن الحصول على الرأس `Authorization` مع رمز مميز حامل.</span><span class="sxs-lookup"><span data-stu-id="0e430-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="0e430-121">ستتم تعبئة مفتاح الاشتراك بشكل تلقائي.</span><span class="sxs-lookup"><span data-stu-id="0e430-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="0e430-122">بشكل اختياري، أضف كافة معلمات الاستعلام الضرورية.</span><span class="sxs-lookup"><span data-stu-id="0e430-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="0e430-123">قم بالتمرير لأسفل الجزء الجانبي وحدد **إرسال**.</span><span class="sxs-lookup"><span data-stu-id="0e430-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="0e430-124">ستظهر استجابة HTTP تحته.</span><span class="sxs-lookup"><span data-stu-id="0e430-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="0e430-125">إنشاء تسجيل تطبيق جديد في مدخل Azure</span><span class="sxs-lookup"><span data-stu-id="0e430-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="0e430-126">تساعدك هذه الخطوات على الشروع في العمل باستخدام واجهات API في Customer Insights في تطبيق Azure باستخدام الأذونات المفوضة.</span><span class="sxs-lookup"><span data-stu-id="0e430-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="0e430-127">تأكد من إكمال [قسم الشروع في العمل](#get-started-trying-the-customer-insights-apis) أولاً.</span><span class="sxs-lookup"><span data-stu-id="0e430-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="0e430-128">سجل دخولك إلى [مدخل Azure](https://portal.azure.com) باستخدام الحساب الذي يمكنه الوصول إلى بيانات Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0e430-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="0e430-129">من اليمين، حدد **تسجيلات التطبيق**.</span><span class="sxs-lookup"><span data-stu-id="0e430-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="0e430-130">حدد **تسجيل جديد**، وقدم اسم تطبيق واختر نوع الحساب.</span><span class="sxs-lookup"><span data-stu-id="0e430-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="0e430-131">بشكل اختياري، أضف عنوان URL لإعادة التوجيه.</span><span class="sxs-lookup"><span data-stu-id="0e430-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="0e430-132">http://localhost يكفي لتطوير تطبيق على الكمبيوتر المحلي.</span><span class="sxs-lookup"><span data-stu-id="0e430-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="0e430-133">على تسجيل التطبيق الجديد، انتقل إلى **أذونات واجهة API**.</span><span class="sxs-lookup"><span data-stu-id="0e430-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="0e430-134">حدد **إضافة إذن**، وحدد **Customer Insights** في الجزء الجانبي.</span><span class="sxs-lookup"><span data-stu-id="0e430-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="0e430-135">في **نوع الإذن**، حدد **الأذونات المفوضة** وحدد إذن **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="0e430-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="0e430-136">حدد **إضافة أذونات**.</span><span class="sxs-lookup"><span data-stu-id="0e430-136">Select **Add permissions**.</span></span> <span data-ttu-id="0e430-137">إذا كنت بحاجة إلى الوصول إلى واجهة API من دون قيام المستخدم بتسجيل الدخول، فراجع [أذونات التطبيق من خادم إلى خادم](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="0e430-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="0e430-138">حدد **منح موافقة المسؤول ل...** لإكمال تسجيل التطبيق.</span><span class="sxs-lookup"><span data-stu-id="0e430-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="0e430-139">يمكنك استخدام معرف التطبيق/العميل لتسجيل التطبيق هذا باستخدام مكتبة المصادقة من Microsoft (MSAL) للحصول علي رمز مميز حامل لإرساله مع طلبك إلى API.</span><span class="sxs-lookup"><span data-stu-id="0e430-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="0e430-140">لمزيد من المعلومات حول MSAL، انظر [نظرة عامة على مكتبة المصادقة من Microsoft‏ (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="0e430-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="0e430-141">لمزيد من المعلومات حول تسجيل التطبيق في Azure، انظر [تجربة تسجيل تطبيق Azure الجديد](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="0e430-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="0e430-142">للحصول على معلومات حول استخدام API لمكتبات العملاء، راجع [مكتبات عملاء Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="0e430-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="0e430-143">أذونات التطبيق من خادم إلى خادم</span><span class="sxs-lookup"><span data-stu-id="0e430-143">Server-to-server application permissions</span></span>

<span data-ttu-id="0e430-144">يوضح [قسم تسجيل التطبيق](#create-a-new-app-registration-in-the-azure-portal) كيفية تسجيل تطبيق يتطلب قيام مستخدم بتسجيل الدخول للمصادقة.</span><span class="sxs-lookup"><span data-stu-id="0e430-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="0e430-145">تعرف على كيفية إنشاء تسجيل تطبيق لا يحتاج إلى تفاعل المستخدم ويمكن تشغيله على خادم.</span><span class="sxs-lookup"><span data-stu-id="0e430-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="0e430-146">في تسجيل التطبيق في مدخل Azure، انتقل إلى **أذونات واجهة API**.</span><span class="sxs-lookup"><span data-stu-id="0e430-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="0e430-147">حدد **إضافة إذن**، وحدد **Customer Insights** في الجزء الجانبي.</span><span class="sxs-lookup"><span data-stu-id="0e430-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="0e430-148">في **نوع الإذن**، حدد **أذونات التطبيق** وحدد إذن **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="0e430-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="0e430-149">حدد **إضافة أذونات**.</span><span class="sxs-lookup"><span data-stu-id="0e430-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="0e430-150">لمنح المسؤول الموافقة على إذن التطبيق هذا، يتعين عليك إضافة كيان خدمة.</span><span class="sxs-lookup"><span data-stu-id="0e430-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="0e430-151">ثبّت الوحدة النمطية Azure Active Directory(AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="0e430-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="0e430-152">اتصل بحساب AD: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="0e430-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="0e430-153">يمكنك العثور على معرف المستأجر على **نظرة عامة** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0e430-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="0e430-154">قم بتشغيل الأمر التالي لإضافة كيان خدمة Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` تنتمي المعلمة إلى تطبيق Customer Insights API.</span><span class="sxs-lookup"><span data-stu-id="0e430-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="عينة كيان الخدمة":::

1. <span data-ttu-id="0e430-156">عد إلى **أذونات واجهة API** لتسجيل تطبيقك.</span><span class="sxs-lookup"><span data-stu-id="0e430-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="0e430-157">حدد **منح موافقة المسؤول ل...** لإكمال تسجيل التطبيق.</span><span class="sxs-lookup"><span data-stu-id="0e430-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="0e430-158">في النهاية، يتعين علينا إضافة اسم تسجيل التطبيق كمستخدم في Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0e430-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="0e430-159">افتح Customer Insights، وانتقل إلى **المسؤول** > **الأذونات** وحدد **إضافة مستخدم**.</span><span class="sxs-lookup"><span data-stu-id="0e430-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="0e430-160">ابحث عن اسم تسجيل التطبيق، وحدده من نتائج البحث، وحدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="0e430-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="0e430-161">مكتبات عملاء Customer Insights</span><span class="sxs-lookup"><span data-stu-id="0e430-161">Customer Insights client libraries</span></span>

<span data-ttu-id="0e430-162">يساعدك هذا القسم على بدء استخدام مكتبات العملاء المتوفرة لواجهات API في Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0e430-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="0e430-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="0e430-163">C# NuGet</span></span>

<span data-ttu-id="0e430-164">تعرف على كيفية بدء استخدام مكتبات العميل C# من  NuGet.org. لمزيد من المعلومات حول حزمة NuGet، راجع [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="0e430-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="0e430-165">في الوقت الحالي، تستهدف هذه الحزمة إطارات عمل netstandard2.0 and netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="0e430-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="0e430-166">إضافة مكتبة العملاء C# إلى مشروع C#</span><span class="sxs-lookup"><span data-stu-id="0e430-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="0e430-167">في Visual Studio، افتح **NuGet Package Manager** لمشروعك.</span><span class="sxs-lookup"><span data-stu-id="0e430-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="0e430-168">ابحث عن **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="0e430-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="0e430-169">حدد **تثبيت** لإضافة الحزمة إلى المشروع.</span><span class="sxs-lookup"><span data-stu-id="0e430-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="0e430-170">أو بدلاً من ذلك، يمكنك تشغيل هذا الأمر في **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="0e430-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="إضافة حزمة NuGet إلى مشروع Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="0e430-172">استخدام مكتبة العملاء C#</span><span class="sxs-lookup"><span data-stu-id="0e430-172">Use the C# client library</span></span>

1. <span data-ttu-id="0e430-173">استخدم [مكتبة المصادقة من Microsoft (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) للحصول على `AccessToken` باستخدام [تسجيل تطبيق Azure](#create-a-new-app-registration-in-the-azure-portal) موجود.</span><span class="sxs-lookup"><span data-stu-id="0e430-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="0e430-174">بعد المصادقة على رمز مميز بنجاح والحصول عليه، قم بإنشاء `HttpClient` جديد أو استخدام واحد موجود مع تعيين **"التخويل" DefaultRequestHeaders** الإضافي إلى **الحامل <access token>** وتعيين **Ocp-Apim-Subscription-Key** إلى [**مفتاح الاشتراك** من بيئة Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="0e430-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="0e430-175">أعد تعيين رأس **التفويض** عندما يكون مناسبًا.</span><span class="sxs-lookup"><span data-stu-id="0e430-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="0e430-176">على سبيل المثال، عند انتهاء صلاحية الرمز المميز.</span><span class="sxs-lookup"><span data-stu-id="0e430-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="0e430-177">قم بتمرير `HttpClient` هذا إلى بناء عميل `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="0e430-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="عينة httpclient":::

1. <span data-ttu-id="0e430-179">يمكنك إجراء استدعاءات مع العميل "لأساليب التوسيع"، على سبيل المثال، `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="0e430-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="0e430-180">إذا كان الوصول إلى `Microsoft.Rest.HttpOperationResponse` الأساسي مفضلاً، فاستخدم "أساليب رسالة http"، على سبيل المثال `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="0e430-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="0e430-181">من المحتمل أن تكون الاستجابة من النوع `object` لأنه باستطاعة الأسلوب إرجاع أنواع متعددة (على سبيل المثال ، `IList<InstanceInfo>` و `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="0e430-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="0e430-182">للتحقق من نوع الإرجاع، يمكنك تحويل الكائنات بأمان إلى أنواع الاستجابة المحددة في [صفحة تفاصيل واجهة API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) لهذه العملية.</span><span class="sxs-lookup"><span data-stu-id="0e430-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="0e430-183">إذا كانت هناك حاجة إلى مزيد من المعلومات حول الطلب، فاستخدم **أساليب رسالة http** للوصول إلى كائن الاستجابة الأولي.</span><span class="sxs-lookup"><span data-stu-id="0e430-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>
