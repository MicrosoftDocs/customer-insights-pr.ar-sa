---
title: التعامل مع واجهات API
description: استخدام واجهات API وفهم القيود.
ms.date: 03/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 59161456914df84d7e72402ed1f5faf70a5119ba
ms.sourcegitcommit: a39e00a50ad3eda820fd756c5611081f0ca04662
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 04/09/2021
ms.locfileid: "5873646"
---
# <a name="work-with-customer-insights-apis"></a>التعامل مع واجهات API في Customer Insights

يوفر Dynamics 365 Customer Insights واجهات API لبناء تطبيقاتك الخاصة استنادًا إلى البيانات الموجودة في Customer Insights.

> [!IMPORTANT]
> يمكن العثور على تفاصيل واجهات API هذه في [مرجع واجهات API‏‎ في Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). وهي تتضمن معلومات إضافية حول العمليات والمعلمات والاستجابات.

ترشدك هذه المقالة للوصول إلى واجهات API في Customer Insights وإنشاء تسجيل تطبيق Azure ومساعدتك على الشروع في العمل مع مكتبات العملاء المتوفرة.

## <a name="get-started-trying-the-customer-insights-apis"></a>بدء تجربة واجهات API في Customer Insights

1. [سجل دخولك](https://home.ci.ai.dynamics.com) إلى Customer Insights. إذا لم يكن لديك اشتراك حتى الآن، فيمكنك [التسجيل للحصول على إصدار تجريبي من Customer Insights](https://aka.ms/tryci).

1. لتمكين واجهات API على بيئة Customer Insights، انتقل إلى **المسؤول** > **الأذونات**. ستحتاج إلى أذونات المسؤول للقيام بذلك.

1. انتقل إلى علامة تبويب **واجهات API** وحدد الزر **تمكين**.    
   يؤدي تمكين واجهات API إلى إنشاء مفتاح اشتراك أساسي وثانوي للمثيل الذي يتم استخدامه في طلبات API. يمكنك إعادة إنشاء المفاتيح بتحديد **إعادة إنشاء الأساسي** أو **إعادة إنشاء الثانوي** على **المسؤول** > **الأذونات** > **واجهات API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="تمكين واجهات API في Customer Insights":::

1. حدد **استكشاف واجهات API** [لتجربة واجهات API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. اختر عملية واجهة API وحدد **جرّبها**.

1. في الجزء الجانبي، قم بتعيين القيمة في القائمة المنسدلة **التفويض** إلى **ضمني**. يمكن الحصول على الرأس `Authorization` مع رمز مميز حامل. ستتم تعبئة مفتاح الاشتراك بشكل تلقائي.
  
1. بشكل اختياري، أضف كافة معلمات الاستعلام الضرورية.

1. قم بالتمرير لأسفل الجزء الجانبي وحدد **إرسال**.

ستظهر استجابة HTTP تحته.


   :::image type="content" source="media/try-apis.gif" alt-text="رسم Gif متحرك يوضح كيفية تحديد اختبار واجهات API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>إنشاء تسجيل تطبيق جديد في مدخل Azure

تساعدك هذه الخطوات على الشروع في العمل باستخدام واجهات API في Customer Insights في تطبيق Azure باستخدام الأذونات المفوضة. تأكد من إكمال [قسم الشروع في العمل](#get-started-trying-the-customer-insights-apis) أولاً.

1. سجل دخولك إلى [مدخل Azure](https://portal.azure.com) باستخدام الحساب الذي يمكنه الوصول إلى بيانات Customer Insights.

1. من اليمين، حدد **تسجيلات التطبيق**.

1. حدد **تسجيل جديد**، وقدم اسم تطبيق واختر نوع الحساب.
   بشكل اختياري، أضف عنوان URL لإعادة التوجيه. http://localhost يكفي لتطوير تطبيق على الكمبيوتر المحلي.

1. على تسجيل التطبيق الجديد، انتقل إلى **أذونات واجهة API**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="رسم GIF متحرك لتعيين إذن API في تسجيل التطبيق.":::

1. حدد **إضافة إذن**، وحدد **Customer Insights** في الجزء الجانبي.

1. في **نوع الإذن**، حدد **الأذونات المفوضة** وحدد إذن **user_impersonation**.

1. حدد **إضافة أذونات**. إذا كنت بحاجة إلى الوصول إلى واجهة API من دون قيام المستخدم بتسجيل الدخول، فراجع [أذونات التطبيق من خادم إلى خادم](#server-to-server-application-permissions).

1. حدد **منح موافقة المسؤول ل...** لإكمال تسجيل التطبيق.

يمكنك استخدام معرف التطبيق/العميل لتسجيل التطبيق هذا باستخدام مكتبة المصادقة من Microsoft (MSAL) للحصول علي رمز مميز حامل لإرساله مع طلبك إلى API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="رسم Gif متحرك لمنح موافقة المسؤول.":::

لمزيد من المعلومات حول MSAL، انظر [نظرة عامة على مكتبة المصادقة من Microsoft‏ (MSAL)](/azure/active-directory/develop/msal-overview).

لمزيد من المعلومات حول تسجيل التطبيق في Azure، انظر [تجربة تسجيل تطبيق Azure الجديد](/azure/active-directory/develop/app-registration-portal-training-guide).

للحصول على معلومات حول استخدام API لمكتبات العملاء، راجع [مكتبات عملاء Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>أذونات التطبيق من خادم إلى خادم

يوضح [قسم تسجيل التطبيق](#create-a-new-app-registration-in-the-azure-portal) كيفية تسجيل تطبيق يتطلب قيام مستخدم بتسجيل الدخول للمصادقة. تعرف على كيفية إنشاء تسجيل تطبيق لا يحتاج إلى تفاعل المستخدم ويمكن تشغيله على خادم.

1. في تسجيل التطبيق في مدخل Azure، انتقل إلى **أذونات واجهة API**.

1. حدد **إضافة إذن**، وحدد **Customer Insights** في الجزء الجانبي.

1. في **نوع الإذن**، حدد **أذونات التطبيق** وحدد إذن **CustomerInsights.Api.All**.

1. حدد **إضافة أذونات**.

1. لمنح المسؤول الموافقة على إذن التطبيق هذا، يتعين عليك إضافة كيان خدمة.

   1. ثبّت الوحدة النمطية Azure Active Directory(AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. اتصل بحساب AD: `Connect-AzureAD -TenantId <your tenant id>`. يمكنك العثور على معرف المستأجر على **نظرة عامة** > **Azure Active Directory**.
   1. قم بتشغيل الأمر التالي لإضافة كيان خدمة Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` تنتمي المعلمة إلى تطبيق Customer Insights API.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="عينة كيان الخدمة":::

1. عد إلى **أذونات واجهة API** لتسجيل تطبيقك.

1. حدد **منح موافقة المسؤول ل...** لإكمال تسجيل التطبيق.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="رسم Gif متحرك لمنح موافقة المسؤول.":::

1. في النهاية، يتعين علينا إضافة اسم تسجيل التطبيق كمستخدم في Customer Insights.    
   افتح Customer Insights، وانتقل إلى **المسؤول** > **الأذونات** وحدد **إضافة مستخدم**.

1. ابحث عن اسم تسجيل التطبيق، وحدده من نتائج البحث، وحدد **حفظ**.

## <a name="customer-insights-client-libraries"></a>مكتبات عملاء Customer Insights

يساعدك هذا القسم على بدء استخدام مكتبات العملاء المتوفرة لواجهات API في Customer Insights. يمكن العثور على كافة التعليمات البرمجية المصدر الخاصة بالمكتبات وعينات التطبيقات في [صفحة Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

تعرف على كيفية بدء استخدام مكتبات العميل C# من  NuGet.org. لمزيد من المعلومات حول حزمة NuGet، راجع [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). في الوقت الحالي، تستهدف هذه الحزمة إطارات عمل netstandard2.0 and netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>إضافة مكتبة العملاء C# إلى مشروع C#

1. في Visual Studio، افتح **NuGet Package Manager** لمشروعك.

1. ابحث عن **Microsoft.Dynamics.CustomerInsights.Api**.

1. حدد **تثبيت** لإضافة الحزمة إلى المشروع.
   أو بدلاً من ذلك، يمكنك تشغيل هذا الأمر في **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="إضافة حزمة NuGet إلى مشروع Visual Studio":::

#### <a name="use-the-c-client-library"></a>استخدام مكتبة العملاء C#

1. استخدم [مكتبة المصادقة من Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) للحصول على `AccessToken` باستخدام [تسجيل تطبيق Azure](#create-a-new-app-registration-in-the-azure-portal) موجود.

1. بعد المصادقة على رمز مميز بنجاح والحصول عليه، قم بإنشاء `HttpClient` جديد أو استخدام واحد موجود مع تعيين **"التخويل" DefaultRequestHeaders** الإضافي إلى **الحامل <access token>** وتعيين **Ocp-Apim-Subscription-Key** إلى [**مفتاح الاشتراك** من بيئة Customer Insights](#get-started-trying-the-customer-insights-apis).    
   أعد تعيين رأس **التفويض** عندما يكون مناسبًا. على سبيل المثال، عند انتهاء صلاحية الرمز المميز.

1. قم بتمرير `HttpClient` هذا إلى بناء عميل `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="عينة httpclient":::

1. يمكنك إجراء استدعاءات مع العميل "لأساليب التوسيع"، على سبيل المثال، `GetAllInstancesAsync`. إذا كان الوصول إلى `Microsoft.Rest.HttpOperationResponse` الأساسي مفضلاً، فاستخدم "أساليب رسالة http"، على سبيل المثال `GetAllInstancesWithHttpMessagesAsync`.

1. من المحتمل أن تكون الاستجابة من النوع `object` لأنه باستطاعة الأسلوب إرجاع أنواع متعددة (على سبيل المثال ، `IList<InstanceInfo>` و `ApiErrorResult`). للتحقق من نوع الإرجاع، يمكنك تحويل الكائنات بأمان إلى أنواع الاستجابة المحددة في [صفحة تفاصيل واجهة API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) لهذه العملية.    
   إذا كانت هناك حاجة إلى مزيد من المعلومات حول الطلب، فاستخدم **أساليب رسالة http** للوصول إلى كائن الاستجابة الأولي.

### <a name="nodejs-package"></a>حزمة NodeJS

استخدم مكتبات عميل NodeJS المتوفرة من خلال NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>حزمة Python

استخدم مكتبات عميل Python المتوفرة من خلال PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]