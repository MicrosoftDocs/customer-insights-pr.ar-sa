---
title: قم بتصدير مقاطع Customer Insights إلى Adobe Campaign Standard (إصدار أولي).
description: تعرف على كيفية استخدام مقاطع Customer Insights في Adobe Campaign Standard.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 834880cac9c5023157983081ff2513d9b051491f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195504"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>قم بتصدير مقاطع Customer Insights إلى Adobe Campaign Standard (إصدار أولي).

قم بتصدير المقاطع التي تستهدف الجمهور ذي الصلة لـ Adobe Campaign Standard.

:::image type="content" source="media/ACS-flow.png" alt-text="مخطط العملية للخطوات الملخصة في هذه المقالة.":::

## <a name="prerequisites"></a>المتطلبات

- ترخيص Adobe ‏Campaign Standard.
- اسم [حساب مساحة تخزين Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) ومفتاح الحساب. للعثور على الاسم والمفتاح، راجع [إدارة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).
- [حاوية مساحة تخزين Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>نظرة عامة على الحملة

لفهم كيفية استخدام مقاطع من Customer Insights في Adobe Experience Platform بشكل أفضل، دعنا نلقي نظرة على عينة وهمية لحملة.

لنفترض أن شركتك تقدم خدمة شهرية قائمة على اشتراك لعملائك في الولايات المتحدة. تريد تحديد العملاء الذين من المقرر تجديد اشتراكاتهم في الأيام الثمانية القادمة، ولكنهم لم يجددوا اشتراكهم بعد. للمحافظة على هؤلاء العملاء، ترغب في إرسال عرض ترويجي لهم عبر البريد الإلكتروني، باستخدام Adobe Campaign Standard.

في هذا المثال، نريد تشغيل حملة البريد الإلكتروني الترويجية مرة واحدة. لا تتناول هذه المقالة حالة استخدام تشغيل الحملة أكثر من مرة. ومع ذلك، يمكن تكوين Customer Insights وAdobe Campaign Standard للعمل على سيناريو حملة متكررة أيضًا.

## <a name="identify-your-target-audience"></a>تحديد الجمهور المستهدف

في السيناريو الخاص بنا، نفترض أن عناوين البريد الإلكتروني للعملاء متوفرة في Customer Insights وتم تحليل تفضيلاتهم الترويجية لتحديد أعضاء المقطع.

ويسمى [المقطع الذي حددته في Customer Insights](segments.md)باسم **ChurnProneCustomers** وأنت تخطط لإرسال الترويج عبر البريد الإلكتروني لهؤلاء العملاء.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="لقطة شاشة لصفحة المقاطع باستخدام المقطع ChurnProneCustomers التي تم إنشاؤها.":::

سيحتوي العرض الذي تريد إرسال بالبريد الإلكتروني على الاسم الأول واسم العائلة وتاريخ انتهاء اشتراك العميل. كما يعلم العملاء بالتخفيض الذي سيحصلون عليه في حالة قيامهم بتجديد اشتراكهم قبل انتهاء مدته.

## <a name="export-your-target-audience"></a>تصدير الجمهور المستهدف

### <a name="set-up-connection-to-adobe-campaign"></a>إعداد الاتصال بـ Adobe ‏Campaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Adobe ‏Campaign**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **اسم الحساب**، و **مفتاح الحساب**، و **الحساب** لحسابك في حساب مساحة تخزين Blob storage الخاصة بك.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="لقطة شاشة لتكوين حساب التخزين. ":::

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **حفظ** لإكمال الاتصال.

### <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في الحقل **اتصال للتصدير**، اختر اتصالا من قسم Adobe Campaign. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. اختر المقطع التي تريد تصديرها. في هذا المثال، هي **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="لقطة شاشة لواجهة مستخدم تحديد المقطع مع تحديد المقطع ChurnProneCustomers.":::

1. حدد **التالي**.

1. قم بتعيين حقول **المصدر** من مقطع Customer Insights إلى أسماء الحقول **الهدف** في مخطط ملف تعريف Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="تعيين الحقول لموصل Adobe Campaign Standard.":::

   إذا كنت ترغب في إضافة مزيد من السمات، فحدد **إضافة سمة**. يمكن أن يكون اسم الهدف مختلفًا عن اسم الحقل المصدر، لذا لا يزال بإمكانك تعيين إخراج المقطع من Customer Insights إلى Adobe Campaign Standard إذا لم يكن للحقول نفس الاسم في النظامين.

   > [!NOTE]
   > يتم استخدام عنوان البريد الإلكتروني كحقل هوية ولكن يمكنك استخدام أي معرف آخر من ملف تعريف العميل لتعيين البيانات إلى Adobe Campaign Standard.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> تأكد من أن عدد السجلات في المقطع التي تم تصديرها يقع ضمن الحد المسموح به في ترخيص Adobe Campaign Standard.

يتم تخزين البيانات المصدّرة في حاوية Azure Blob storage التي قمت بتكوينها أعلاه. يتم إنشاء مسار المجلد التالي تلقائيًا في حاويتك: *%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

مثال: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>تكوين Adobe Campaign Standard

تحتوي المقاطع التي تم تصديرها على الأعمدة التي حددتها أثناء تكوين التصدير. يمكن استخدام هذه البيانات من أجل [إنشاء ملفات تعريف في Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

لاستخدام المقطع في Adobe ‏Campaign Standard‏، [قم بتوسيع مخطط ملف التعريف](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) في Adobe Campaign Standard بحيث يتضمن حقلين إضافيين.

في المثال الذي قدمناه، هذه الحقول هي اسم المقطع وتاريخ المقطع. سوف نستخدم هذه الحقول لتحديد ملفات التعريف في Adobe Campaign Standard التي نريد استهدافها في هذه الحملة.

في حال عدم وجود أي سجلات أخرى في Adobe Campaign Standard، غير تلك التي تريد استيرادها، فقم بتخطي هذه الخطوة.

## <a name="import-data-into-adobe-campaign-standard"></a>استيراد البيانات إلى Adobe Campaign Standard

استورد بيانات الجمهور المعدة من Customer Insights إلى Adobe Campaign Standard [لإنشاء ملفات التعريف باستخدام سير عمل](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences).

تم تكوين سير عمل الاستيراد في الصورة أدناه للتشغيل كل ثماني ساعات والبحث عن مقاطع Customer Insights المصدرة (ملف .csv في مساحة تخزين Azure Blob). يستخرج سير العمل محتوى ملف csv. في ترتيب أعمدة محدد. تم بناء سير العمل هذا لإجراء معالجة أساسية للأخطاء والتأكد من وجود عنوان بريد إلكتروني لكل سجل الأساسية والتأكد من أن كل سجل يحتوي على عنوان بريد إلكتروني قبل استخدام البيانات في Adobe Campaign Standard. يستخرج سير العمل أيضًا اسم المقطع من اسم الملف قبل تحويله إلى بيانات ملف تعريف Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="لقطة شاشة لسير عمل عملية استيراد في واجهة مستخدم Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>استرداد الجمهور في Adobe Campaign Standard

بعد استيراد البيانات إلى Adobe ‏Campaign Standard، [أنشئ سير عمل](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) و[استعلامًا](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) للعملاء استنادًا إلى اسم المقطع وتاريخ المقطع لتحديد الملفات الشخصية التي تم تحديدها لحملتنا النموذجية.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>إنشاء البريد الإلكتروني وإرساله باستخدام Adobe Campaign Standard

أنشئ محتوى البريد الإلكتروني، ثم [اختبر وأرسل](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) البريد الإلكتروني.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="عينة بريد إلكتروني مع عرض تجديد من Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
