---
title: 'طلبات حقوق صاحب البيانات (DSR) بموجب GDPR | Microsoft Docs '
description: الاستجابة لطلبات صاحب البيانات للحصول على قدرات رؤى الجمهور في Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350253"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>طلبات حقوق صاحب البيانات (DSR) بموجب GDPR

تم بدء العمل باللائحة العامة لحماية البيانات (هذه اللائحة) السارية منذ 25 مايو 2018. فهو يمنح حقوقا كبيرة للأفراد فيما يتعلق بياناتهم. ويتكاتف هذا المستخدم حول حماية حقوق الخصوصية للأفراد وتمكينها. يمكنك قراءة المزيد حول التزام Microsoft تجاه الأمان وتوافق البيانات في [مركز Microsoft Trust Center](https://www.microsoft.com/trust-center).

نحن ملتزمون بمساعدة عملائنا على استيفاء متطلبات القانون العام لحماية البيانات (GDPR). فهو يتضمن الحق في حذف وتصدير البيانات التي تتضمن معلومات شخصية مثل هويات المستخدمين ورقم الهاتف وعناوين البريد الإلكتروني. يمكن للمسؤولين تنفيذ طلبات المستخدمين بحذف بيانات شخصية أو تصديرها.

## <a name="audience-insights"></a>رؤى الجمهور

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>الاستجابة لطلبات الحذف من أصحاب البيانات (DSR) في GDPR للحصول على قدرات رؤى الجمهور في Dynamics 365 Customer Insights.

يعتبر "الحق في الإزالة" عن طريق إزالة البيانات الشخصية من بيانات عملاء المؤسسة هو الحماية الأساسية في القانون العام لحماية البيانات (GDPR). تتضمن إزالة البيانات الشخصية إزالة كافة البيانات الشخصية والسجلات التي أنشأها النظام باستثناء معلومات سجل التدقيق.

#### <a name="manage-data-subject-delete-requests"></a>إدارة طلبات حذف موضوع البيانات

تقدم رؤى الجمهور التجارب التالية داخل المنتج لحذف البيانات الشخصية لعميل أو مستخدم معين:

- **إدارة طلبات الحذف لبيانات العميل**: يتم استيعاب بيانات العميل في Customer Insights من مصادر البيانات الأصلية الخارجية لـCustomer Insights. يجب إجراء كافة طلبات حذف GDPR في مصدر البيانات الأصلي.
- **إدارة طلبات الحذف لبيانات مستخدم Customer Insights**: يتم إنشاء بيانات للمستخدمين بواسطة Customer Insights. يجب تنفيذ كافة طلبات حذف GDPR في Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>إدارة طلبات حذف بيانات العميل

يمكن لمسؤول Customer Insights اتباع هذه الخطوات لإزالة بيانات العملاء التي تم حذفها في مصدر البيانات:

1. قم بتسجيل الدخول إلى Dynamics 365 Customer Insights.
2. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.
3. بالنسبة لكل مصدر بيانات في القائمة التي تحتوي على بيانات العميل المحذوفة:
   1. حدد (...) ثم حدد **تحديث**.
   2. تحقق من حالة مصدر البيانات تحت **الحالة**. تعني علامة الاختيار أن التحديث تم بنجاح. يعني المثلث التحذيري حدوث خطأ ما. في حالة ظهور المثلث التحذيري، اتصل بـ D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![معالجة طلبات حذف GDPR لبيانات العملاء.](audience-insights/media/gdpr-data-sources.png "معالجة طلبات الحذف لبيانات العملاء")

##### <a name="manage-delete-requests-for-user-data"></a>إدارة طلبات الحذف لبيانات المستخدم

يُمكن لمسؤول Customer Insights اتباع هذه الخطوات لحذف بيانات مستخدم Customer Insights:

1. قم بتسجيل الدخول إلى Dynamics 365 Customer Insights.
2. في رؤى الجمهور، انتقل إلى **المسؤول‏‎** > **الأذونات**.
3. حدد خانة الاختيار للمستخدم الذي تُريد حذفه.
4. حدد **إزالة**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>الاستجابة لطلبات التصدير من أصحاب البيانات (DSR) في GDPR

كجزء من التزامنا تجاه الشريك معك في رحلتك إلى لتطبيق القانون العام لحماية البيانات (GDPR)، قمنا بوضع وثائق تساعدك على الاستعداد. توضح هذه الوثائق الخطوات التي يمكنك اتخاذها لدعم الامتثال لـ GDPR عند استخدام رؤى الجمهور.

#### <a name="manage-export-and-view-requests"></a>إدارة طلبات التصدير والعرض

يسمح حق نقل البيانات لأصحاب البيانات بطلب نسخة من بياناته الشخصية بتنسيق إلكتروني (تنسيق مصنف وشائع الاستخدام وقابل للقراءة بواسطة جهاز وقابل للتشغيل المتداخل") يمكن إرساله إلى متحكم آخر في البيانات.

##### <a name="export-customer-data-tenant-admin"></a>تصدير بيانات العميل (مسؤول المستأجر)

يُمكن أن يتبع مسؤول المستأجر هذه الخطوات لتصدير البيانات:

1. إرسال بريد إلكتروني إلى D365CI@microsoft.com لتحديد عنوان البريد الإلكتروني الخاص بالعميل في الطلب. سوف فريق Customer Insights بإرسال بريد إلكتروني إلى عنوان البريد الإلكتروني لمسؤول المستأجر المُسجل، للمطالبة بتأكيد تصدير البيانات.
2. قم بالإقرار بتأكيد تصدير البيانات للعميل المطلوب.
3. استلام البيانات المُصدرة من خلال عنوان البريد الإلكتروني لمسؤول المستأجر.

##### <a name="export-user-data-tenant-admin"></a>تصدير بيانات المستخدم (مسؤول المستأجر)

1. إرسال بريد إلكتروني إلى D365CI@microsoft.com لتحديد عنوان البريد الإلكتروني الخاص بالمستخدم في الطلب. سوف فريق Customer Insights بإرسال بريد إلكتروني إلى عنوان البريد الإلكتروني لمسؤول المستأجر المُسجل، للمطالبة بتأكيد تصدير البيانات.
2. قم بالإقرار بتأكيد تصدير البيانات للمستخدم المطلوب.
3. استلام البيانات المُصدرة من خلال عنوان البريد الإلكتروني لمسؤول المستأجر.

## <a name="consent-management-preview"></a>إدارة الموافقة (إصدار أولي)

لا تقوم إمكانية إدارة الموافقة بجمع بيانات المستخدم مباشرة. فهو يقوم فقط باستيراد بيانات الموافقة التي يتم تقديمها بواسطة المستخدمين في التطبيقات الأخرى، ثم يقوم بمعالجة تلك البيانات.

لإزالة بيانات الموافقة الخاصة لمستخدمين معينين، قم بإزالتها في مصادر البيانات التي تم حذفها إلى إمكانية إدارة الموافقة. وبعد تحديث مصدر البيانات، سيتم حذف البيانات التي تمت إزالتها في مركز الموافقة أيضا. التطبيقات التي تستخدم كيان الموافقة ستحذف البيانات التي تمت إزالتها من المصدر بعد [التحديث](audience-insights/system.md#refresh-processes). يوصى بتحديث مصادر البيانات بسرعة بعد الاستجابة لطلب موضوع بيانات لإزالة بيانات المستخدم من كافة العمليات والتطبيقات الأخرى.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]