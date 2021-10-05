---
title: إنشاء ارتباط بين رؤى الجمهور ورؤى المشاركة
description: أنشئ ارتباطًا نشطًا بين رؤى الجمهور ورؤى المشاركة لتمكين المشاركة ثنائية الاتجاه للبيانات.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8d93a49a29c29103e189a6d4a42294c18dc28abd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 09/27/2021
ms.locfileid: "7559002"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>إنشاء ارتباط بين رؤى الجمهور ورؤى المشاركة

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

يقوم التكامل بين رؤى الجمهور ورؤى المشاركة بربط البيئات من الإمكانيتين، ويمكّن مشاركة البيانات بطريقة ثنائية الاتجاه بينهما.

استخدم الشرائح وملفات التعريف الموحدة من رؤى الجمهور للحصول على المزيد من خيارات التحليلات في رؤى المشاركة. صدّر الأحداث ذات قيمة أعمال عالية من رؤى المشاركة. استخدم هذه الأحداث لإضافة بيانات إلى ملفات التعريف الموحدة في رؤى الجمهور.

## <a name="prerequisites"></a>المتطلبات الأساسية

- يجب تخزين ملفات تعريف رؤى الجمهور في حساب Azure Data Lake Storage تملكه أو في مستودع بيانات مدار في [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash;. 
- يجب أن تحتوي بيئة رؤى الجمهور على بيئة Dataverse مرتبطة. وإذا كانت هذه البيئة تستخدم أيضًا Dataverse لتخزين البيانات، فتأكد من تحديد خيار **تمكين مشاركة البيانات** في رؤى الجمهور. لمزيد من المعلومات، راجع [إنشاء وتكوين بيئة مدفوعة في رؤى الجمهور](../audience-insights/get-started-paid.md).
- تحتاج إلى أذونات المسؤول لبيئات كل من رؤى المشاركة ورؤى الجمهور.
- يجب أن تكون البيئات المرتبطة في نفس المنطقة الجغرافية.

> [!NOTE]
> - إذا كان اشتراكك في رؤى الجمهور عبارة عن إصدار تجريبي يستخدم مستودع بيانات يُدار داخليًا بواسطة رؤى الجمهور، فاتصل بـ [pirequest@microsoft.com](mailto:pirequest@microsoft.com) للحصول على المساعدة. 
> - إذا كانت بيئة رؤى الجمهور تستخدم Azure Data Lake Storage الخاصة بك لتخزين البيانات، فعليك إضافة كيان خدمة من Azure لرؤى المشاركة إلى حساب التخزين الخاص بك. للاطلاع على التفاصيل، انتقل إلى [الاتصال بحساب Azure Data Lake Storage باستخدام كيان خدمة من Azure لرؤى الجمهور](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>إنشاء ارتباط بيئة

يمكنك إنشاء ارتباط بيئة من خلال تحديث إعدادات **المسؤول** > **البيئة** في رؤى المشاركة.

**لإنشاء ارتباط نشط بين رؤى الجمهور ورؤى المشاركة**

1. من صفحة **مسؤول البيئة**، حدد علامة التبويب **ربط البيئات**.

    :::image type="content" source="media/integrate1.png" alt-text="إعداد بيئة.":::

1. حدد **إعداد البيئات** في الزاوية العلوية اليسرى من أسفل الشاشة.

     :::image type="content" source="media/integrate2.png" alt-text="تحديد بيئة رؤى الجمهور.":::

1. حدد بيئة رؤى الجمهور، ثم حدد ***التالي** للانتهاء. الآن، يمكنك تحديد ميزات اختيارية للبيئات المرتبطة.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>تمكين سمات وشرائح ملفات التعريف الموحدة لرؤى الجمهور

بعد ربط البيئات، يمكنك تحديد ميزات اختيارية للبيئات المرتبطة. تمكّث هذه الميزات سمات وشرائح ملفات التعريف الموحدة من رؤى الجمهور للتحليل التفاعلي على بيانات العملاء.

> [!IMPORTANT]
> كي تظهر شرائح رؤى الجمهور في رؤى المشاركة، يجب عليك أولاً [تشغيل عمليات الدمج والعمليات النهائية](../audience-insights/merge-entities.md). تعد العمليات النهائية مهمة لأنها تنشئ جدولاُ فريدًا يعمل على تحضير شرائح رؤى الجمهور لمشاركتها مع رؤى المشاركة. (في حالة جدولة عملية للنظام، فستتضمن تلقائيًا عمليات نهائية.)

**لتحليل بيانات الويب في رؤى المشاركة**

1. في صفحة **مسؤول البيئة**، شغّل مفتاح التبديل **مشاركة البيانات من رؤى الجمهور مع رؤى المشاركة**، ثم حدد **التالي**.

    :::image type="content" source="media/integrate4.png" alt-text="تحديد الميزات.":::

1. حدد سمات ملفات التعريف الموحدة التي ستصبح أبعادًا في رؤى المشاركة. (لا تُعد جميع السمات أبعادًا مفيدة. على سبيل المثال، من غير المرجح أن تحتاج إلى **الاسم الأول** أو **اسم العائلة** كسمة لتحليل أحداث الويب.)

    :::image type="content" source="media/integrate5.png" alt-text="تنظيم الأبعاد.":::

   >[!NOTE]
   > تتم تصفية جميع سمات ملفات تعريف رؤى الجمهور التي تمثل المعرفات (مثل **المعرف** و **المعرف البديل**) من السمات المتوفرة وتتحول إلى أبعاد في رؤى المشاركة.

1. عندما تنتهي من تحديد السمات، حدد **التالي**.
1. قم بإضافة المستخدمين الذين يمكنهم عرض شرائح وأبعاد ملفات تعريف رؤى الجمهور في رؤى المشاركة.

    :::image type="content" source="media/integrate6.png" alt-text="إدارة الوصول إلى بيانات العملاء.":::

   > [!IMPORTANT]
   > إذا لم تقم بإضافة مستخدمين بشكل واضح في هذه الخطوة، فسيتم إخفاء البيانات عن المستخدمين في رؤى المشاركة.
   > كي تظهر شرائح رؤى الجمهور في رؤى المشاركة، يجب عليك أولاً [تشغيل عمليات الدمج والعمليات النهائية](../audience-insights/merge-entities.md). تعد العمليات النهائية مهمة لأنها تنشئ جدولاُ فريدًا يعمل على تحضير شرائح رؤى الجمهور لمشاركتها مع رؤى المشاركة. (في حالة جدولة عملية للنظام، فستتضمن تلقائيًا عمليات نهائية.)

1. راجع تحديدك، ثم حدد **إنهاء**.

    :::image type="content" source="media/integrate7.png" alt-text="مراجعة إعدادات بيانات العملاء.":::

## <a name="export-refined-events-to-audience-insights"></a>تصدير الأحداث المكررة إلى رؤى الجمهور

بعد إنشاء ارتباط بين البيئات، يمكنك تصدير الأحداث المكررة من رؤى المشاركة إلى رؤى الجمهور واستيعابها كمصدر بيانات جديد. 

لمزيد من المعلومات، انتقل إلى [دمج بيانات الويب من رؤى المشاركة مع رؤى الجمهور.](../audience-insights/integrate-engagement-insights.md)

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
