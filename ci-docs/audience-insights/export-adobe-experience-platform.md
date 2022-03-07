---
title: تصدير بيانات Customer Insights إلى Adobe Experience Platform
description: تعرف على كيفية استخدام شرائح رؤى الجمهور في Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9010af3c42823ce0dd8685bf71c109aef8d3f635
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227696"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>استخدام شرائح Customer Insights في Adobe Experience Platform (إصدار أولي)

كمستخدم لمعلومات الجمهور في Dynamics 365 Customer Insights، ربما قمت بإنشاء شرائح لجعل حملات التسويق أكثر فعالية من خلال استهداف الجماهير ذات الصلة. لاستخدام شريحة من رؤى الجمهور في Adobe Experience Platform وتطبيقات مثل Adobe Campaign Standard، عليك اتباع بعض الخطوات التي تم توضيحها في هذا المقال.

:::image type="content" source="media/AEP-flow.png" alt-text="مخطط العملية للخطوات الملخصة في هذه المقالة.":::

## <a name="prerequisites"></a>المتطلبات الأساسية

-   ترخيص Dynamics 365 Customer Insights
-   ترخيص Adobe Experience Platform
-   ترخيص Adobe Campaign Standard
-   حساب Azure Blob Storage

## <a name="campaign-overview"></a>نظرة عامة حول الحملة

لتكوين فهم أفضل لكيفية استخدام شرائح من رؤى الجمهور في Adobe Experience Platform، سنلقي نظرة على عينة حملة وهمية.

لنفترض أن شركتك تقدم خدمة شهرية قائمة على اشتراك لعملائك في الولايات المتحدة. تريد تحديد العملاء الذين من المقرر تجديد اشتراكاتهم في الأيام الثمانية القادمة، ولكنهم لم يجددوا اشتراكهم بعد. للمحافظة على هؤلاء العملاء، ترغب في إرسال عرض ترويجي لهم عبر البريد الإلكتروني، باستخدام Adobe Experience Platform.

في هذا المثال، نريد تشغيل حملة البريد الإلكتروني الترويجية مرة واحدة. لا تتناول هذه المقالة حالة استخدام تشغيل الحملة أكثر من مرة.

## <a name="identify-your-target-audience"></a>تحديد الجمهور المستهدف

في السيناريو لدينا، نفترض أن عناوين البريد الإلكتروني الخاصة بالعملاء متوفرة في رؤى الجمهور‬، وأنه قد تم تحليل وتفضيلاتهم الترويجية لتحديد أعضاء الشريحة.

تسمى [الشريحة التي حددتها في رؤى الجمهور‬](segments.md) is called **ChurnProneCustomers**، وتريد إرسال العرض الترويجي إلى هؤلاء العملاء بالبريد الإلكتروني.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="لقطة شاشة لصفحة الشرائح باستخدام الشريحة ChurnProneCustomers التي تم إنشاؤها.":::

سيحتوي العرض الذي تريد إرسال بالبريد الإلكتروني على الاسم الأول واسم العائلة وتاريخ انتهاء اشتراك العميل. كما يعلم العملاء بالتخفيض الذي سيحصلون عليه في حالة قيامهم بتجديد اشتراكهم قبل انتهاء مدته.

## <a name="export-your-target-audience"></a>تصدير الجمهور المستهدف

ومن خلال تحديد الجمهور المستهدف، يمكننا تكوين التصدير من رؤى الجمهور إلى حساب Azure Blob Storage.

### <a name="configure-a-connection"></a>تكوين اتصال

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **مساحة تخزين Azure Blob** أو حدد **إعداد** في تجانب **مساحة تخزين Azure Blob** لتكوين الاتصال.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="الإطار المتجانب لتكوين Azure Blob Storage."::: 

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **اسم الحساب**، و **مفتاح الحساب**، و **الحاوية** لحساب تخزين Blob storage حيث تريد تصدير الشريحة إليه.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="لقطة شاشة لتكوين حساب التخزين. "::: 
   
    - لمعرفة المزيد حول كيفية العثور على اسم حساب مساحة تخزين اسم حساب تخزين Blob storage ومفتاح الحساب، راجع [إدارة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).
    - لمعرفة كيفية إنشاء حاوية، راجع [إنشاء حاوية](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. حدد **حفظ** لإكمال الاتصال. 

### <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء عملية تصدير جديدة، حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم مساحة تخزين Azure Blob Storage, إذا لم تشاهد اسم المقطع هذا، فلا توجد اتصالات من هذا النوع متوفرة لك.

1. اختر الشريحة التي تريد تصديرها. في هذا المثال، هي **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="لقطة شاشة لواجهة مستخدم تحديد الشريحة مع تحديد الشريحة ChurnProneCustomers.":::

1. حدد **حفظ**.

بعد حفظ وجهة التصدير، تجدها في **البيانات** > **عمليات التصدير**.

يمكنك الآن [تصدير الشريحة عند الطلب](export-destinations.md#run-exports-on-demand). سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md).

> [!NOTE]
> تأكد من أن عدد السجلات في الشريحة التي تم تصديرها يقع ضمن الحد المسموح به في ترخيص Adobe Campaign Standard.

يتم تخزين البيانات المصدّرة في حاوية Azure Blob storage التي قمت بتكوينها أعلاه. يتم إنشاء مسار المجلد التالي بشكل تلقائي في حاويتك:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

مثال: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

يقيم الملف *model.json* للكيانات المصدّرة على مستوى *%ExportDestinationName%*.

مثال: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>تعريف نموذج بيانات التجربة (XDM) في Adobe Experience Platform

قبل استخدام البيانات التي تم تصديرها من رؤى الجمهور داخل Adobe Experience Platform، علينا تحديد مخطط نموذج بيانات التجربة و[تكوين البيانات لملف تعريف العميل في الوقت الحقيقي](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

تعرف على [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) وافهم [أساسيات تركيب المخطط](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>استيراد البيانات في Adobe Experience Platform

الآن وقد تم إعداد كل شيء، نريد استيراد بيانات الجمهور التي قمنا بتحضيرها من رؤى الجمهور إلى Adobe Experience Platform.

أولاً، [أنشئ اتصال مصدر Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

عد تعريف الاتصال المصدر، يمكنك [تكوين تدفق بيانات](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) لاتصال دفعي بمساحة التخزين في السحابة لاستيراد إخراج الشرائح من رؤى الجمهور إلى Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>إنشاء جمهور في Adobe Campaign Standard

لإرسال البريد الإلكتروني لهذه الحملة، سوف نستخدم Adobe Campaign Standard. بعد استيراد البيانات إلى Adobe Experience Platform، علينا [إنشاء جمهور](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) في Adobe Campaign Standard باستخدام البيانات في Adobe Experience Platform.


تعرف على كيفية [استخدام منشئ الشرائح](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) في Adobe Campaign Standard لتعريف جمهور بالاستناد إلى البيانات الموجودة في Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>إنشاء البريد الإلكتروني وإرساله باستخدام Adobe Campaign Standard

أنشئ محتوى البريد الإلكتروني، ثم [اختبر وأرسل](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) البريد الإلكتروني.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="عينة بريد إلكتروني مع عرض تجديد من Adobe Campaign Standard.":::
