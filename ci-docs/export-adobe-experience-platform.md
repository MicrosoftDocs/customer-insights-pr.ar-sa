---
title: التصدير إلى Adobe Experience Platform (إصدار أولي)
description: تعرف على كيفية استخدام مقاطع Customer Insights في Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195274"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>التصدير إلى Adobe Experience Platform (إصدار أولي)

قم بتصدير المقاطع التي تستهدف الجمهور ذي الصلة لـ Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="مخطط العملية للخطوات الملخصة في هذه المقالة.":::

## <a name="prerequisites"></a>المتطلبات

- ترخيص Adobe Experience Platform.
- ترخيص Adobe ‏Campaign Standard.
- اسم [حساب مساحة تخزين Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) ومفتاح الحساب. للعثور على الاسم والمفتاح، راجع [إدارة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).
- [حاوية مساحة تخزين Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>نظرة عامة حول الحملة

لفهم كيفية استخدام مقاطع من Customer Insights في Adobe Experience Platform بشكل أفضل، دعنا نلقي نظرة على عينة وهمية لحملة.

لنفترض أن شركتك تقدم خدمة شهرية قائمة على اشتراك لعملائك في الولايات المتحدة. تريد تحديد العملاء الذين من المقرر تجديد اشتراكاتهم في الأيام الثمانية القادمة، ولكنهم لم يجددوا اشتراكهم بعد. للمحافظة على هؤلاء العملاء، ترغب في إرسال عرض ترويجي لهم عبر البريد الإلكتروني، باستخدام Adobe Experience Platform.

في هذا المثال، نريد تشغيل حملة البريد الإلكتروني الترويجية مرة واحدة. لا تتناول هذه المقالة حالة استخدام تشغيل الحملة أكثر من مرة.

## <a name="identify-your-target-audience"></a>تحديد الجمهور المستهدف

في السيناريو الخاص بنا، نفترض أن عناوين البريد الإلكتروني للعملاء متوفرة في Customer Insights وتم تحليل تفضيلاتهم الترويجية لتحديد أعضاء المقطع.

ويسمى [المقطع الذي حددته في Customer Insights](segments.md)باسم **ChurnProneCustomers** وأنت تخطط لإرسال الترويج عبر البريد الإلكتروني لهؤلاء العملاء.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="لقطة شاشة لصفحة المقاطع باستخدام المقطع ChurnProneCustomers التي تم إنشاؤها.":::

سيحتوي العرض الذي تريد إرسال بالبريد الإلكتروني على الاسم الأول واسم العائلة وتاريخ انتهاء اشتراك العميل. كما يعلم العملاء بالتخفيض الذي سيحصلون عليه في حالة قيامهم بتجديد اشتراكهم قبل انتهاء مدته.

## <a name="export-your-target-audience"></a>تصدير الجمهور المستهدف

سنقوم بتكوين التصدير من Customer Insights إلى حساب تخزين Azure Blob.

### <a name="set-up-connection-to-azure-blob-storage"></a>إعداد الاتصال بـ Azure Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Azure Blob Storage**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **اسم الحساب**، و **مفتاح الحساب**، و **الحاوية** لحساب تخزين Blob storage حيث تريد تصدير المقطع إليه.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="لقطة شاشة لتكوين حساب التخزين. ":::

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **حفظ** لإكمال الاتصال.

### <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم مساحة تخزين Azure Blob Storage, اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. اختر المقطع التي تريد تصديرها. في هذا المثال، هي **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="لقطة شاشة لواجهة مستخدم تحديد المقطع مع تحديد المقطع ChurnProneCustomers.":::

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> تأكد من أن عدد السجلات في المقطع التي تم تصديرها يقع ضمن الحد المسموح به في ترخيص Adobe Campaign Standard.

يتم تخزين البيانات التي تم تصديرها في حاوية Azure Blob Storage التي قمت بتكوينها. يتم إنشاء مسارات المجلدات التالية بشكل تلقائي في حاويتك:

- بالنسبة للكيانات المصدر والكيانات التي تم إنشاؤها بواسطة النظام:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  مثال: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- يقيم الملف *model.json* للكيانات المصدّرة على مستوى *%ExportDestinationName%*.

  مثال: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>تعريف نموذج بيانات التجربة (XDM) في Adobe Experience Platform

قبل استخدام البيانات التي تم تصديرها من Customer Insights داخل Adobe Experience Platform، حدد مخطط نموذج بيانات التجربة و[تكوين البيانات لملف تعريف العميل في الوقت الفعلي](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

تعرف على [XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) وافهم [أساسيات تركيب المخطط](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>استيراد البيانات في Adobe Experience Platform

استورد بيانات الجمهور المعدة من Customer Insights إلى Adobe Experience Platform.

1. [أنشئ اتصال مصدر Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [قم بتكوين تدفق البيانات](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) لاتصال دفعة تخزين سحابي لاستيراد إخراج المقطع من Customer Insights إلى Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>إنشاء جمهور في Adobe Campaign Standard

لإرسال البريد الإلكتروني لهذه الحملة، سوف نستخدم Adobe Campaign Standard.

1. [قم بإنشاء جمهور](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) في Adobe ‏Campaign Standard باستخدام البيانات الواردة في Adobe Experience Platform.

1. [استخدام منشئ المقاطع](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) في Adobe Campaign Standard لتعريف جمهور بالاستناد إلى البيانات الموجودة في Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>إنشاء البريد الإلكتروني وإرساله باستخدام Adobe Campaign Standard

أنشئ محتوى البريد الإلكتروني، ثم [اختبر وأرسل](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) البريد الإلكتروني.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="عينة بريد إلكتروني مع عرض تجديد من Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
