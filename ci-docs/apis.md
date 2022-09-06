---
title: التعامل مع واجهات API في Customer Insights
description: استخدام واجهات API وفهم القيود.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387324"
---
# <a name="work-with-customer-insights-apis"></a>التعامل مع واجهات API في Customer Insights

يوفر Dynamics 365 Customer Insights واجهات برمجة تطبيقات لبناء التطبيقات الخاصة بك استنادا إلى بياناتك في Customer Insights.

> [!IMPORTANT]
> يمكن العثور على تفاصيل واجهات API هذه في [مرجع واجهات API‏‎ في Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). وهي تتضمن معلومات إضافية حول العمليات والمعلمات والاستجابات.

جرب واجهات API في Customer Insights، وأنشئ تسجيلًا لتطبيق Azure، وابدأ في مكتبات العملاء.

## <a name="get-started-trying-the-customer-insights-apis"></a>بدء تجربة واجهات API في Customer Insights

قم بتمكين واجهات API في Customer Insights وجربها. ويجب أن يقوم مسؤول Customer Insights بتمكين وصول API إلى Customer Insights. وبمجرد تمكين الوصول، يمكن لأي مستخدم استخدام API باستخدام مفتاح الاشتراك.

1. [سجل دخولك](https://home.ci.ai.dynamics.com) إلى Customer Insights. إذا لم يكن لديك اشتراك حتى الآن، فيمكنك [التسجيل للحصول على إصدار تجريبي من Customer Insights](https://aka.ms/tryci).

1. انتقل إلى **المسؤول** > **الأمن**، ثم حدد علامة التبويب **APIs‎**.

1. إذا لم يتم إعداد وصول API إلى البيئة، حدد **تمكين**.

   يؤدي تمكين واجهات API إلى إنشاء مفتاح اشتراك أساسي وثانوي للمثيل الذي يتم استخدامه في طلبات API. لإعادة إنشاء المفاتيح، حدد **إعادة إنشاء المفتاح الأساسي** أو **إعادة إنشاء المفتاح الثانوي** في علامة التبويب **واجهات برمجة التطبيقات**.

1. حدد [**استكشاف واجهات API الخاصة بنا**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) لتجربة واجهات API.

1. ابحث عن عملية API وحددها ثم حدد **جربها**.

   :::image type="content" source="media/try-api.png" alt-text="كيفية اختبار واجهات برمجة التطبيقات.":::

1. في الجزء الجانبي، قم بتعيين القيمة في القائمة المنسدلة **تفويض** إلى **ضمني**. تتم إضافة رأس `Authorization` باستخدام رمز مميز للحامل. سيتم تعبئة مفتاح الاشتراك تلقائياً.
  
1. بشكل اختياري، أضف كافة معلمات الاستعلام الضرورية.

1. قم بالتمرير لأسفل الجزء الجانبي وحدد **إرسال**.

   يتم عرض استجابة HTTP في الجزء السفلي.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>إنشاء تسجيل تطبيق جديد في مدخل Azure

قم بإنشاء [تسجيل تطبيق](/graph/auth-register-app-v2) لاستخدام واجهات APIs من Customer Insights في تطبيق Azure باستخدام الأذونات المفوضة.

1. أكمل [قسم بدء العمل](#get-started-trying-the-customer-insights-apis)".

1. سجل دخولك إلى [مدخل Azure](https://portal.azure.com) باستخدام الحساب الذي يمكنه الوصول إلى بيانات Customer Insights.

1. ابحث عن **تسجيلات التطبيق** ثم حددها.

1. حدد **تسجيل جديد**، وقدم اسم تطبيق واختر نوع الحساب.

   بشكل اختياري، أضف عنوان URL لإعادة التوجيه. http://localhost يكفي لتطوير تطبيق على الكمبيوتر المحلي.

1. حدد **تسجيل**.

1. على تسجيل التطبيق الجديد، انتقل إلى **أذونات واجهة API**.

1. حدد **إضافة إذن** وحدد **Dynamics 365 AI for Customer Insights** في الجزء الجانبي.

1. بالنسبة إلى **نوع الإذن**، حدد **الأذونات المفوضة**، ثم حدد إذن **انتحال شخصية المستخدم**.

1. حدد **إضافة أذونات**.

1. حدد **منح موافقة المسؤول ل...** لإكمال تسجيل التطبيق.

1. إذا كنت بحاجة إلى الوصول إلى واجهة API من دون قيام المستخدم بتسجيل الدخول، انتقل إلى [أذونات التطبيق من خادم إلى خادم](#server-to-server-application-permissions).

يمكنك استخدام معرف التطبيق/العميل لتسجيل هذا التطبيق باستخدام [مكتبة المصادقة من Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) للحصول علي رمز مميز حامل لإرساله مع طلبك إلى API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

للحصول على معلومات حول استخدام واجهات برمجة التطبيقات في مكتبات عملائنا، راجع [مكتبات عميل Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>أذونات التطبيق من خادم إلى خادم

يمكنك إنشاء تسجيل تطبيق لا يحتاج إلى تفاعل المستخدم ويمكن تشغيله على خادم.

1. في تسجيل التطبيق في مدخل Azure، انتقل إلى **أذونات واجهة API**.

1. حدد **إضافة إذن**.

1. حدد **واجهات برمجة التطبيقات (APIS) التي تستخدمها مؤسستي** واختر **الذكاء الاصطناعي في Dynamics 365 لـ Customer Insights** من القائمة.

1. بالنسبة إلى **نوع الإذن**، حدد **أذونات التطبيقات**، ثم حدد إذن **CustomerInsights.Api.All**.

1. حدد **إضافة أذونات**.

1. عد إلى **أذونات واجهة API** لتسجيل تطبيقك.

1. حدد **منح موافقة المسؤول ل...** لإكمال تسجيل التطبيق.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. قم بإضافة اسم تسجيل التطبيق كمستخدم في Customer Insights.

   1. افتح Customer Insights، وانتقل إلى **المسؤول‏‎** > **الأمان** وحدد **إضافة مستخدمين**.

   1. ابحث عن اسم تسجيل التطبيق، وحدده من نتائج البحث، وحدد **حفظ**.

## <a name="sample-queries"></a>نماذج الاستعلامات

بالنسبة لقائمة قصيرة من نماذج استعلامات OData للعمل مع واجهات API: [أمثلة على استعلامات OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>مكتبات عملاء Customer Insights

بدء استخدام مكتبات العملاء المتوفرة لواجهات API في Customer Insights. يمكن العثور على كافة التعليمات البرمجية المصدر الخاصة بالمكتبات وعينات التطبيقات في [صفحة Customer Insights GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

استخدم مكتبات العميل C# من NuGet.org. في الوقت الحالي، تستهدف هذه الحزمة إطارات عمل netstandard2.0 and netcoreapp2.0. لمزيد من المعلومات حول الحزمة NuGet، راجع [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>إضافة مكتبة العملاء C# إلى مشروع C#

1. في Visual Studio، افتح **NuGet Package Manager** لمشروعك.

1. ابحث عن **Microsoft.Dynamics.CustomerInsights.Api**.

1. حدد **تثبيت** لإضافة الحزمة إلى المشروع.

   أو بدلاً من ذلك، يمكنك تشغيل هذا الأمر في **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>استخدام مكتبة العملاء C#

1. استخدم [مكتبة المصادقة من Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) للحصول على `AccessToken` باستخدام [تسجيل تطبيق Azure](#create-a-new-app-registration-in-the-azure-portal) موجود.

1. بعد المصادقة بنجاح والحصول على رمز، قم ببناء رمز جديد أو استخدم `HttpClient` مع إعداد **DefaultRequestHeaders "Authorization** على **رمز وصول الحامل** وإعداد **Ocp-Apim-Subscription-Key** على [**مفتاح الاشتراك**](#get-started-trying-the-customer-insights-apis) من بيئة Customer Insights الخاصة بك.   

   أعد تعيين رأس **التخويل** عندما يكون مناسبًا. على سبيل المثال، عند انتهاء صلاحية الرمز المميز.

1. قم بتمرير `HttpClient` هذا إلى بناء عميل `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. يمكنك إجراء استدعاءات مع العميل "لأساليب التوسيع"، على سبيل المثال، `GetAllInstancesAsync`. إذا كان الوصول إلى `Microsoft.Rest.HttpOperationResponse` الأساسي مفضلاً، فاستخدم "طرق رسالة http"، على سبيل المثال `GetAllInstancesWithHttpMessagesAsync`.

1. من المحتمل أن تكون الاستجابة من النوع `object` لأنه باستطاعة الطريقة إرجاع أنواع متعددة (على سبيل المثال، `IList<InstanceInfo>` و `ApiErrorResult`). للتحقق من نوع الإرجاع، يمكنك استخدام الكائنات في أنواع الاستجابة المحددة في [صفحة تفاصيل واجهة API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) لهذه العملية.

   إذا كانت هناك حاجة إلى مزيد من المعلومات حول الطلب، فاستخدم **طرق رسالة http** للوصول إلى كائن الاستجابة الأولي.

### <a name="nodejs-package"></a>حزمة NodeJS

استخدم مكتبات عميل NodeJS المتوفرة من خلال NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>حزمة Python

استخدم مكتبات عميل Python المتوفرة من خلال PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
