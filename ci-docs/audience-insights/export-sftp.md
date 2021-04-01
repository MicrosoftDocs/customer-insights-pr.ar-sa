---
title: تصدير بيانات Customer Insights إلى مضيفي SFTP
description: تعرف على كيفية تكوين الاتصال بمضيف SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598369"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="c3964-103">موصل لـ SFTP (معاينة)</span><span class="sxs-lookup"><span data-stu-id="c3964-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="c3964-104">استخدم بيانات في تطبيقات الجهة الخارجية عن طريق تصديرها إلى مضيف إلى بروتوكول نقل الملفات الآمن (SFTP)‬.</span><span class="sxs-lookup"><span data-stu-id="c3964-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c3964-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="c3964-105">Prerequisites</span></span>

- <span data-ttu-id="c3964-106">توفر مضيف SFTP وبيانات الاعتماد المقابلة.</span><span class="sxs-lookup"><span data-stu-id="c3964-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="c3964-107">الاتصال بـ SFTP</span><span class="sxs-lookup"><span data-stu-id="c3964-107">Connect to SFTP</span></span>

1. <span data-ttu-id="c3964-108">انتقل إلى **المسؤول** > **وجهات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="c3964-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c3964-109">ضمن **SFTP**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="c3964-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="c3964-110">في حقل **الاسم المعروض**، أدخل اسمًا للوجهة سهل التمييز.</span><span class="sxs-lookup"><span data-stu-id="c3964-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="c3964-111">أدخل **اسم المستخدم** و **كلمة المرور** و **اسم المضيف** و **مجلد التصدير** لحساب SFTP.</span><span class="sxs-lookup"><span data-stu-id="c3964-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="c3964-112">حدد **تحقق** لاختبار الاتصال.</span><span class="sxs-lookup"><span data-stu-id="c3964-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="c3964-113">بعد التحقق بنجاح، اختر ما إذا كنت ترغب في تصدير بياناتك وهي **مضغوطة** أو **غير مضغوطة‏‎**، وحدد **محدد الحقل** للملفات المصدّرة.</span><span class="sxs-lookup"><span data-stu-id="c3964-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="c3964-114">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="c3964-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="c3964-115">حدد **التالي** لبدء تكوين التصدير.</span><span class="sxs-lookup"><span data-stu-id="c3964-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="c3964-116">تكوين التصدير</span><span class="sxs-lookup"><span data-stu-id="c3964-116">Configure the export</span></span>

1. <span data-ttu-id="c3964-117">حدد الكيانات، على سبيل المثال الشرائح، التي ترغب في تصديرها.</span><span class="sxs-lookup"><span data-stu-id="c3964-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c3964-118">سيكون كل كيان محدد عبارة عن خمسة ملفات إخراج كحدٍ أقصى عند تصديره.</span><span class="sxs-lookup"><span data-stu-id="c3964-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="c3964-119">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="c3964-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="c3964-120">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="c3964-120">Export the data</span></span>

<span data-ttu-id="c3964-121">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="c3964-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="c3964-122">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c3964-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="c3964-123">القيود المعروفة</span><span class="sxs-lookup"><span data-stu-id="c3964-123">Known limitations</span></span>

- <span data-ttu-id="c3964-124">يعتمد وقت تشغيل أي تصدير على أداء النظام.</span><span class="sxs-lookup"><span data-stu-id="c3964-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="c3964-125">نوصي بمركزين لوحدة المعالجة المركزية وذاكرة بسعة غيغابايت واحد كحدٍ أدنى لتكوين الخادم.</span><span class="sxs-lookup"><span data-stu-id="c3964-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="c3964-126">قد يستغرق تصدير الكيانات مع 100 مليون من ملفات تعريف العملاء 90 دقيقة عند استخدام الحد الأدنى من التكوين الموصى به من مركزين لوحدة المعالجة المركزية وذاكرة بسعة غيغابايت واحد.</span><span class="sxs-lookup"><span data-stu-id="c3964-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="c3964-127">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="c3964-127">Data privacy and compliance</span></span>

<span data-ttu-id="c3964-128">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات عبر SFTP Technologies، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="c3964-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="c3964-129">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام وجهة التصدير بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="c3964-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="c3964-130">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="c3964-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="c3964-131">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="c3964-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]