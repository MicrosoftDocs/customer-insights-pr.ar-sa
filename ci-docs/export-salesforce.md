---
title: تصدير البيانات إلى Salesforce Marketing Cloud (إصدار أولي)
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197022"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>تصدير البيانات إلى Salesforce Marketing Cloud (إصدار أولي)

استخدم بيانات العملاء في Salesforce Marketing Cloud عن طريق تصديرها عبر موقع بروتوكول نقل الملفات الآمن (SFTP).

## <a name="prerequisites"></a>المتطلبات

- [مضيف SFTP لسحابة Salesforce Marketing](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) وبيانات اعتماد المسؤول المقابلة.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>إعداد الاتصال بـ Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Salesforce Marketing Cloud**.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إنه المسؤول بشكل افتراضي. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **اسم المستخدم** و **كلمة المرور** و **اسم المضيف** و **مجلد التصدير** لحساب SFTP.

1. حدد **تحقق** لاختبار الاتصال.

1. راجع [خصوصية البيانات والامتثال](connections.md#data-privacy-and-compliance) وحدد **أوافق**.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. انتقل إلى **البيانات** > **التصديرات**.

1. حدد **إضافة تصدير**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم SFTP. اتصل بالمسؤول إذا لم يكن هناك اتصال متوفر.

1. إدخال اسمًا للتصدير.

1. اختر ما إذا كنت ترغب في تصدير بياناتك **المضغوطة** أو **المفكوك ضغطها** و **محدد المجال** للملفات المصدرة.

1. حدد الكيانات، على سبيل المثال المقاطع، التي ترغب في تصديرها.

   > [!NOTE]
   > سيتم تقسيم كل كيان محدد إلى خمسة ملفات إخراج بحد أقصى عند التصدير.

1. حدد **حفظ.**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>استيراد بيانات Customer Insights من موقع SFTP إلى Salesforce Marketing Cloud

1. أنشئ [امتدادات البيانات في Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) لاستيراد ملف بيانات Customer Insights من موقع SFTP.

2. [استيراد البيانات من موقع SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) إلى ملحق بيانات Salesforce Marketing Cloud.

3. قم بإعداد التنفيذ التلقائي لاستيراد البيانات إلى ملحقات البيانات. تعرف على المزيد حول [عمليات الأتمتة الخاصة بإسقاط الملفات والتشغيل التلقائي المجدول](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   حدد [التنفيذ التلقائي لإسقاط الملف](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) أو [التنفيذ التلقائي المجدول](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

وفيما يلي مثال على [التنفيذ التلقائي باستخدام SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
