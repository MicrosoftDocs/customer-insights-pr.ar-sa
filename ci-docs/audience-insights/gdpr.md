---
title: 'طلبات حقوق صاحب البيانات (DSR) بموجب GDPR | Microsoft Docs '
description: الاستجابة لطلبات صاحب البيانات للحصول على قدرات رؤى الجمهور في Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4404926"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="80300-103">طلبات حقوق صاحب البيانات (DSR) بموجب GDPR</span><span class="sxs-lookup"><span data-stu-id="80300-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="80300-104">الاستجابة لطلبات الحذف من أصحاب البيانات (DSR) في GDPR للحصول على قدرات رؤى الجمهور في Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="80300-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="80300-105">يعتبر "الحق في الإزالة" عن طريق إزالة البيانات الشخصية من بيانات عملاء المؤسسة هو الحماية الأساسية في القانون العام لحماية البيانات (GDPR).</span><span class="sxs-lookup"><span data-stu-id="80300-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="80300-106">تتضمن إزالة البيانات الشخصية إزالة كافة البيانات الشخصية والسجلات التي أنشأها النظام باستثناء معلومات سجل التدقيق.</span><span class="sxs-lookup"><span data-stu-id="80300-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="80300-107">إدارة طلبات حذف موضوع البيانات</span><span class="sxs-lookup"><span data-stu-id="80300-107">Manage data subject delete requests</span></span>

<span data-ttu-id="80300-108">تقدم رؤى الجمهور التجارب التالية داخل المنتج لحذف البيانات الشخصية لعميل أو مستخدم معين:</span><span class="sxs-lookup"><span data-stu-id="80300-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="80300-109">**إدارة طلبات الحذف لبيانات العميل**: يتم استيعاب بيانات العميل في Customer Insights من مصادر البيانات الأصلية الخارجية لـCustomer Insights.</span><span class="sxs-lookup"><span data-stu-id="80300-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="80300-110">يجب إجراء كافة طلبات حذف GDPR في مصدر البيانات الأصلي.</span><span class="sxs-lookup"><span data-stu-id="80300-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="80300-111">**إدارة طلبات الحذف لبيانات مستخدم Customer Insights**: يتم إنشاء بيانات للمستخدمين بواسطة Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="80300-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="80300-112">يجب تنفيذ كافة طلبات حذف GDPR في Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="80300-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="80300-113">إدارة طلبات الحذف لبيانات العملاء</span><span class="sxs-lookup"><span data-stu-id="80300-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="80300-114">يمكن لمسؤول Customer Insights اتباع هذه الخطوات لإزالة بيانات العملاء التي تم حذفها في مصدر البيانات:</span><span class="sxs-lookup"><span data-stu-id="80300-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="80300-115">قم بتسجيل الدخول إلى Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="80300-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="80300-116">في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.</span><span class="sxs-lookup"><span data-stu-id="80300-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="80300-117">بالنسبة لكل مصدر بيانات في القائمة التي تحتوي على بيانات العميل المحذوفة:</span><span class="sxs-lookup"><span data-stu-id="80300-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="80300-118">حدد (...) ثم حدد **تحديث**.</span><span class="sxs-lookup"><span data-stu-id="80300-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="80300-119">تحقق من حالة مصدر البيانات تحت **الحالة**.</span><span class="sxs-lookup"><span data-stu-id="80300-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="80300-120">تعني علامة الاختيار أن التحديث تم بنجاح.</span><span class="sxs-lookup"><span data-stu-id="80300-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="80300-121">يعني المثلث التحذيري حدوث خطأ ما.</span><span class="sxs-lookup"><span data-stu-id="80300-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="80300-122">في حالة ظهور المثلث التحذيري، اتصل بـ D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="80300-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="80300-123">![معالجة طلبات الحذف لبيانات العملاء](media/gdpr-data-sources.png "معالجة طلبات الحذف لبيانات العملاء")</span><span class="sxs-lookup"><span data-stu-id="80300-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="80300-124">إدارة طلبات الحذف لبيانات المستخدم</span><span class="sxs-lookup"><span data-stu-id="80300-124">Manage delete requests for user data</span></span>

<span data-ttu-id="80300-125">يُمكن لمسؤول Customer Insights اتباع هذه الخطوات لحذف بيانات مستخدم Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="80300-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="80300-126">قم بتسجيل الدخول إلى Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="80300-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="80300-127">في رؤى الجمهور، انتقل إلى **المسؤول‏‎** > **الأذونات**.</span><span class="sxs-lookup"><span data-stu-id="80300-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="80300-128">حدد خانة الاختيار للمستخدم الذي تُريد حذفه.</span><span class="sxs-lookup"><span data-stu-id="80300-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="80300-129">حدد **إزالة**.</span><span class="sxs-lookup"><span data-stu-id="80300-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="80300-130">![التعامل مع طلبات الحذف من GDPR لبيانات المستخدم](media/gdpr-permissions.png "التعامل مع طلبات الحذف من GDPR لبيانات المستخدم")</span><span class="sxs-lookup"><span data-stu-id="80300-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="80300-131">الاستجابة لطلبات التصدير من أصحاب البيانات (DSR) في GDPR</span><span class="sxs-lookup"><span data-stu-id="80300-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="80300-132">كجزء من التزامنا تجاه الشريك معك في رحلتك إلى لتطبيق القانون العام لحماية البيانات (GDPR)، قمنا بوضع وثائق تساعدك على الاستعداد.</span><span class="sxs-lookup"><span data-stu-id="80300-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="80300-133">توضح هذه الوثائق الخطوات التي يمكنك اتخاذها لدعم الامتثال لـ GDPR عند استخدام رؤى الجمهور.</span><span class="sxs-lookup"><span data-stu-id="80300-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="80300-134">إدارة طلبات التصدير والعرض</span><span class="sxs-lookup"><span data-stu-id="80300-134">Manage export and view requests</span></span>

<span data-ttu-id="80300-135">يسمح حق نقل البيانات لأصحاب البيانات بطلب نسخة من بياناته الشخصية بتنسيق إلكتروني (تنسيق مصنف وشائع الاستخدام وقابل للقراءة بواسطة جهاز وقابل للتشغيل المتداخل") يمكن إرساله إلى متحكم آخر في البيانات.</span><span class="sxs-lookup"><span data-stu-id="80300-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="80300-136">تصدير بيانات العميل (مسؤول المستأجر)</span><span class="sxs-lookup"><span data-stu-id="80300-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="80300-137">يُمكن أن يتبع مسؤول المستأجر هذه الخطوات لتصدير البيانات:</span><span class="sxs-lookup"><span data-stu-id="80300-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="80300-138">إرسال بريد إلكتروني إلى D365CI@microsoft.com لتحديد عنوان البريد الإلكتروني الخاص بالعميل في الطلب.</span><span class="sxs-lookup"><span data-stu-id="80300-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="80300-139">سوف فريق Customer Insights بإرسال بريد إلكتروني إلى عنوان البريد الإلكتروني لمسؤول المستأجر المُسجل، للمطالبة بتأكيد تصدير البيانات.</span><span class="sxs-lookup"><span data-stu-id="80300-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="80300-140">قم بالإقرار بتأكيد تصدير البيانات للعميل المطلوب.</span><span class="sxs-lookup"><span data-stu-id="80300-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="80300-141">استلام البيانات المُصدرة من خلال عنوان البريد الإلكتروني لمسؤول المستأجر.</span><span class="sxs-lookup"><span data-stu-id="80300-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="80300-142">تصدير بيانات المستخدم (مسؤول المستأجر)</span><span class="sxs-lookup"><span data-stu-id="80300-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="80300-143">إرسال بريد إلكتروني إلى D365CI@microsoft.com لتحديد عنوان البريد الإلكتروني الخاص بالمستخدم في الطلب.</span><span class="sxs-lookup"><span data-stu-id="80300-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="80300-144">سوف فريق Customer Insights بإرسال بريد إلكتروني إلى عنوان البريد الإلكتروني لمسؤول المستأجر المُسجل، للمطالبة بتأكيد تصدير البيانات.</span><span class="sxs-lookup"><span data-stu-id="80300-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="80300-145">قم بالإقرار بتأكيد تصدير البيانات للمستخدم المطلوب.</span><span class="sxs-lookup"><span data-stu-id="80300-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="80300-146">استلام البيانات المُصدرة من خلال عنوان البريد الإلكتروني لمسؤول المستأجر.</span><span class="sxs-lookup"><span data-stu-id="80300-146">Receive the exported data through the tenant admin email address.</span></span>
