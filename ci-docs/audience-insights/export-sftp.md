---
title: تصدير بيانات Customer Insights إلى مضيفي SFTP
description: تعرف على كيفية تكوين الاتصال بمضيف SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643487"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="59ee8-103">موصل لـ SFTP (معاينة)</span><span class="sxs-lookup"><span data-stu-id="59ee8-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="59ee8-104">استخدم بيانات في تطبيقات الجهة الخارجية عن طريق تصديرها إلى مضيف إلى بروتوكول نقل الملفات الآمن (SFTP)‬.</span><span class="sxs-lookup"><span data-stu-id="59ee8-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="59ee8-105">المتطلبات الأساسية</span><span class="sxs-lookup"><span data-stu-id="59ee8-105">Prerequisites</span></span>

- <span data-ttu-id="59ee8-106">توفر مضيف FTP وبيانات الاعتماد المناظرة.</span><span class="sxs-lookup"><span data-stu-id="59ee8-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="59ee8-107">الاتصال بـ SFTP</span><span class="sxs-lookup"><span data-stu-id="59ee8-107">Connect to SFTP</span></span>

1. <span data-ttu-id="59ee8-108">انتقل إلى **المسؤول** > **وجهات التصدير**.</span><span class="sxs-lookup"><span data-stu-id="59ee8-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="59ee8-109">ضمن **SFTP**، حدد **إعداد**.</span><span class="sxs-lookup"><span data-stu-id="59ee8-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="59ee8-110">في حقل **الاسم المعروض**، أدخل اسمًا للوجهة سهل التمييز.</span><span class="sxs-lookup"><span data-stu-id="59ee8-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="59ee8-111">قم بتوفير **اسم المستخدم** و **كلمة المرور** و **اسم المضيف** لحساب SFTP.</span><span class="sxs-lookup"><span data-stu-id="59ee8-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="59ee8-112">مثال: إذا كان المجلد الجذر لخادم SFTP هو /root/folder، وأردت تصدير البيانات إلى /root/folder/ci_export_destination_folder، فسيكون المضيف sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="59ee8-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="59ee8-113">حدد **تحقق** لاختبار الاتصال.</span><span class="sxs-lookup"><span data-stu-id="59ee8-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="59ee8-114">بعد نجاح التحقق، اختر إن كنت تريد تصدير بياناتك في حالة **مضغوطة** أو **غير مضغوطة‏‎**، وحدد **محدد الحقل** للملفات المصدّرة.</span><span class="sxs-lookup"><span data-stu-id="59ee8-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="59ee8-115">حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.</span><span class="sxs-lookup"><span data-stu-id="59ee8-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="59ee8-116">حدد **التالي** لبدء تكوين التصدير.</span><span class="sxs-lookup"><span data-stu-id="59ee8-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="59ee8-117">تكوين الاتصال</span><span class="sxs-lookup"><span data-stu-id="59ee8-117">Configure the connection</span></span>

1. <span data-ttu-id="59ee8-118">حدد **سمات العميل** التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="59ee8-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="59ee8-119">يمكنك تصدير سمة واحدة أو سمات متعددة.</span><span class="sxs-lookup"><span data-stu-id="59ee8-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="59ee8-120">حدد **التالي**.</span><span class="sxs-lookup"><span data-stu-id="59ee8-120">Select **Next**.</span></span>

1. <span data-ttu-id="59ee8-121">حدد الشرائح التي تريد تصديرها.</span><span class="sxs-lookup"><span data-stu-id="59ee8-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="59ee8-122">حدد **حفظ**.</span><span class="sxs-lookup"><span data-stu-id="59ee8-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="59ee8-123">تصدير البيانات</span><span class="sxs-lookup"><span data-stu-id="59ee8-123">Export the data</span></span>

<span data-ttu-id="59ee8-124">يمكنك [تصدير البيانات عند الطلب](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="59ee8-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="59ee8-125">سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="59ee8-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="59ee8-126">خصوصية البيانات والتوافق</span><span class="sxs-lookup"><span data-stu-id="59ee8-126">Data privacy and compliance</span></span>

<span data-ttu-id="59ee8-127">عند تمكين Dynamics 365 Customer Insights لإرسال البيانات عبر SFTP Technologies، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية.</span><span class="sxs-lookup"><span data-stu-id="59ee8-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="59ee8-128">ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام وجهة التصدير بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك.</span><span class="sxs-lookup"><span data-stu-id="59ee8-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="59ee8-129">لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="59ee8-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="59ee8-130">بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.</span><span class="sxs-lookup"><span data-stu-id="59ee8-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
