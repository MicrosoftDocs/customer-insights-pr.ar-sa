---
title: تصدير بيانات Customer Insights إلى Adobe Campaign Standard
description: اعرف كيفية استخدام شرائح رؤى الجمهور في Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760265"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>استخدام شرائح Customer Insights في Adobe Campaign Standard (إصدار أولي)

بصفتك مستخدم رؤى الجمهور في Dynamics 365 Customer Insights، من المحتمل أن تكون قد أنشأت شرائح لزيادة مستوى فعالية حملاتك التسويقية من خلال استهداف شرائح جمهور ذات صلة. لاستخدام شريحة من رؤى الجمهور في Adobe Experience Platform وتطبيقات مثل Adobe Campaign Standard، يلزمك اتباع بعض الخطوات الملخصة في هذه المقالة.

:::image type="content" source="media/ACS-flow.png" alt-text="مخطط العملية للخطوات الملخصة في هذه المقالة.":::

## <a name="prerequisites"></a>المتطلبات الأساسية

-   ترخيص Dynamics 365 Customer Insights
-   ترخيص Adobe Campaign Standard
-   حساب Azure Blob Storage

## <a name="campaign-overview"></a>نظرة عامة حول الحملة

لتكوين فهم أفضل لكيفية استخدام شرائح من رؤى الجمهور في Adobe Experience Platform، سنلقي نظرة على عينة حملة وهمية.

لنفترض أن شركتك تقدم خدمة شهرية قائمة على اشتراك لعملائك في الولايات المتحدة. تريد تحديد العملاء الذين من المقرر تجديد اشتراكاتهم في الأيام الثمانية القادمة، ولكنهم لم يجددوا اشتراكهم بعد. للمحافظة على هؤلاء العملاء، تريد إرسال عرض ترويجي لهم عبر البريد الإلكتروني، باستخدام Adobe Campaign Standard.

في هذا المثال، نريد تشغيل حملة البريد الإلكتروني الترويجية مرة واحدة. لا تتناول هذه المقالة حالة استخدام تشغيل الحملة أكثر من مرة. ومع ذلك، يمكنك تكوين رؤى الجمهور وAdobe Campaign Standard بحيث يعملان لسيناريو حملة متكررة أيضًا.

## <a name="identify-your-target-audience"></a>تحديد الجمهور المستهدف

في السيناريو لدينا، نفترض أن عناوين البريد الإلكتروني الخاصة بالعملاء متوفرة في رؤى الجمهور‬، وأنه قد تم تحليل وتفضيلاتهم الترويجية لتحديد أعضاء الشريحة.

تسمى [الشريحة التي حددتها في رؤى الجمهور‬](segments.md) is called **ChurnProneCustomers**، وتريد إرسال العرض الترويجي إلى هؤلاء العملاء بالبريد الإلكتروني.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="لقطة شاشة لصفحة الشرائح باستخدام الشريحة ChurnProneCustomers التي تم إنشاؤها.":::

سيحتوي العرض الذي تريد إرسال بالبريد الإلكتروني على الاسم الأول واسم العائلة وتاريخ انتهاء اشتراك العميل. كما يعلم العملاء بالتخفيض الذي سيحصلون عليه في حالة قيامهم بتجديد اشتراكهم قبل انتهاء مدته.

## <a name="export-your-target-audience"></a>تصدير الجمهور المستهدف

### <a name="configure-a-connection"></a>تكوين اتصال

ومن خلال تحديد الجمهور المستهدف، يمكننا تكوين التصدير من رؤى الجمهور إلى حساب Azure Blob Storage.

1. من رؤى الجمهور، انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **حملة Adobe** لتكوين الاتصال أو حدد **إعداد** في تجانب **حملة Adobe**

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="الإطار المتجانب لتكوين Adobe Campaign Standard.":::

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. أدخل **اسم الحساب**، و **مفتاح الحساب**، و **الحاوية** لحساب تخزين Azure Blob حيث تريد تصدير الشريحة إليه.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="لقطة شاشة لتكوين حساب التخزين. "::: 

   - لمعرفة المزيد حول كيفية العثور على اسم حساب مخزن البيانات الثنائية الكبيرة الحجز لـ Azure ومفتاح الحساب، راجع [أداة إعدادات حساب التخزين في مدخل Azure](/azure/storage/common/storage-account-manage).

   - لمعرفة كيفية إنشاء حاوية، راجع [إنشاء حاوية](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. حدد **حفظ** لإكمال الاتصال.

### <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء عملية تصدير جديدة، حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم حملة Adobe. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. اختر الشريحة التي تريد تصديرها. في هذا المثال، هي **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="لقطة شاشة لواجهة مستخدم تحديد الشريحة مع تحديد الشريحة ChurnProneCustomers.":::

1. حدد **التالي**.

1. سنقوم الآن بتعيين حقول **المصدر** من شريحة رؤى الجمهور إلى أسماء حقول **الهدف** في مخطط ملف تعريف Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="تعيين الحقول لموصل Adobe Campaign Standard.":::

   إذا كنت ترغب في إضافة مزيد من السمات، فحدد **إضافة سمة**. بإمكان اسم الحقل الهدف أن يكون مختلفًا عن اسم الحقل المصدر بحيث يبقى باستطاعتك تعيين إخراج الشرائح من رؤى الجمهور إلى Adobe Campaign Standard إذا لم يكن لدى الحقول الاسم نفسه في النظامين.

   > [!NOTE]
   > يتم استخدام عنوان البريد الإلكتروني كحقل هوية، ولكن يمكنك استخدام أي معرف آخر من ملف تعريف عميل رؤى الجمهور لتعيين البيانات إلى Adobe Campaign Standard.

1. حدد **حفظ**.

بعد حفظ وجهة التصدير، تجدها في **البيانات** > **عمليات التصدير**.

يمكنك الآن [تصدير الشريحة عند الطلب](export-destinations.md#run-exports-on-demand). سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md).

> [!NOTE]
> تأكد من أن عدد السجلات في الشريحة المصدّرة هو ضمن الحد المسموح به في ترخيص Adobe Campaign Standard.

يتم تخزين البيانات المصدّرة في حاوية Azure Blob storage التي قمت بتكوينها أعلاه. يتم إنشاء مسار المجلد التالي بشكل تلقائي في حاويتك:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

مثال: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>تكوين Adobe Campaign Standard

تحتوي الشريحة، عند تصديرها من رؤى الجمهور، على الأعمدة التي حددتها أثناء تعريف وجهة التصدير في الخطوة السابقة. يمكن استخدام هذه البيانات في عملية [إنشاء ملفات تعريف في Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

لاستخدام الشريحة في Adobe Campaign Standard، يلزمنا توسيع مخطط ملف التعريف في Adobe Campaign Standard بحيث يتضمن حقلين إضافيين. اعرف كيفية [توسيع مورد ملف التعريف](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) باستخدام حقول جديدة في Adobe Campaign Standard.

في المثال الذي قدمناه، هذه الحقول هي *اسم الشريحة وتاريخ الشريحة (اختياري).*

سوف نستخدم هذه الحقول لتحديد ملفات التعريف في Adobe Campaign Standard التي نريد استهدافها لهذه الحملة.

إذا لم تكن هناك سجلات أخرى في Adobe Campaign Standard، غير تلك التي ستقوم باستيرادها، فيمكنك تخطي هذه الخطوة.

## <a name="import-data-into-adobe-campaign-standard"></a>استيراد البيانات إلى Adobe Campaign Standard

الآن وقد تم تنظيم كل شيء، نحتاج إلى استيراد بيانات الجمهور التي قمنا بإعدادها من رؤى الجمهور إلى Adobe Campaign Standard لإنشاء ملفات تعريف. اعرف [كيفية استيراد ملفات التعريفي في Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) باستخدام سير عمل.

تم تكوين سير عمل الاستيراد في الصورة أدناه كي يتم تشغيله كل 8 ساعات ويبحث عن شرائح الجمهور المصدّرة (ملف csv. في Azure Blob Storage). يستخرج سير العمل محتوى ملف csv. في ترتيب أعمدة محدد. تم بناء سير العمل هذا لتنفيذ معالجة أخطاء أساسية والتأكد من أن كل سجل يحتوي على عنوان بريد إلكتروني قبل ترحيل البيانات إلى Adobe Campaign Standard. كما يستخرج سير العمل اسم الشريحة من اسم الملف قبل تحديثها وإدراجها داخل بيانات ملف تعريف ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="لقطة شاشة لسير عمل عملية استيراد في واجهة مستخدم Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>استرداد الجمهور في Adobe Campaign Standard

بعد استيراد البيانات إلى Adobe Campaign Standard، [يمكنك إنشاء سير عمل](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) و [استعلام](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) العملاء استنادًا إلى *اسم الشريحة* و *تاريخ الشريحة* لتحديد ملفات التعريف التي تم تعريفها لعينة الحملة.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>إنشاء البريد الإلكتروني وإرساله باستخدام Adobe Campaign Standard

أنشئ محتوى البريد الإلكتروني، ثم [اختبر وأرسل](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) البريد الإلكتروني.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="عينة بريد إلكتروني مع عرض التجديد من Adobe Campaign Standard.":::
