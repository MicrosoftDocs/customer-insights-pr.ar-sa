---
title: تصدير بيانات Customer Insights إلى Salesforce Marketing Cloud
description: تعرف على كيفية تهيئة الاتصال والتصدير إلى Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314567"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a>تصدير الشرائح والبيانات الأخرى إلى Salesforce Marketing Cloud (معاينة)

استخدم بيانات العملاء في Salesforce Marketing Cloud عن طريق تصديرها عبر موقع بروتوكول نقل الملفات الآمن (SFTP).

## <a name="prerequisites-for-connection"></a>المتطلبات الأساسية للاتصال

- توفر مضيف SFTP وبيانات اعتماد المسؤول المقابلة. [كيفية إعداد مواقع SFTP لـ Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a>القيود المعروفة

- يعتمد وقت تشغيل أي تصدير على أداء النظام. نوصي بمركزين لوحدة المعالجة المركزية وذاكرة بسعة غيغابايت واحد كحدٍ أدنى لتكوين الخادم. 
- قد يستغرق تصدير الكيانات التي يصل حجم ملفات تعريف العملاء لها 100 مليون ملف تعريف 90 دقيقة عند استخدام الحد الأدنى من التكوين الموصى به. 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>إعداد الاتصال بـ Salesforce Marketing Cloud

1. انتقل إلى **المسؤول** > **الاتصالات**.

1. حدد **إضافة اتصال** واختر **Salesforce Marketing Cloud** لتكوين الاتصال.

1. اعط اتصالك اسمًا يمكن التعرف عليه في حقل **الاسم المعروض**. يصف الاسم ونوع الاتصال هذا الاتصال. ننصح باختيار اسم يوضح الغرض والهدف من الاتصال.

1. اختر الشخص الذي يمكنه استخدام هذا الاتصال. إذا لم تتخذ أي إجراء، فإن الإعداد الافتراضي سيكونالمسؤولين. لمزيد من المعلومات، راجع [السماح للمساهمين باستخدام اتصال للتصديرات](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. أدخل **اسم المستخدم** و **كلمة المرور** و **اسم المضيف** و **مجلد التصدير** لحساب SFTP.

1. حدد **تحقق** لاختبار الاتصال.

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **حفظ** لإكمال الاتصال.

## <a name="configure-an-export"></a>تكوين تصدير

يمكنك تكوين هذا التصدير إذا كان لديك حق الوصول إلى اتصال من هذا النوع. لمزيد من المعلومات، راجع [الأذونات اللازمة لتكوين تصدير](export-destinations.md#set-up-a-new-export).

1. انتقل إلى **البيانات** > **التصديرات**.

1. لإنشاء اتصال جديد، حدد **إضافة وجهة**.

1. في حقل **الاتصال للتصدير**، اختر اتصالاً من قسم SFTP. إذا لم تشاهد اسم المقطع هذا، لن تكون هناك اتصالات من هذا النوع متوفرة لك.

1. اختر ما إذا كنت ترغب في تصدير بياناتك **المضغوطة** أو **المفكوك ضغطها** و **محدد المجال** للملفات المصدرة.

1. حدد الكيانات، على سبيل المثال الشرائح، التي ترغب في تصديرها.

   > [!NOTE]
   > سيتم تقسيم كل كيان محدد إلى ما يصل إلى خمسة ملفات إخراج عند تصديرها. 

1. حدد **حفظ**.

لا تعمل عملية التصدير التي يتم حفظها على التصدير في الحال.

يتم تشغيل عملية التصدير مع كل [تحديث مجدول](system.md#schedule-tab). يمكنك أيضًا [تصدير البيانات عند الطلب](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>استيراد بيانات Customer Insights من موقع SFTP إلى Salesforce Marketing Cloud

1. أنشئ [امتدادات البيانات في Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) لاستيراد ملف بيانات Customer Insights من موقع SFTP.

2. [استيراد البيانات من موقع SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) إلى ملحق بيانات Salesforce Marketing Cloud. 

3. قم بإعداد التنفيذ التلقائي لاستيراد البيانات إلى ملحقات البيانات. تعرف على المزيد حول [عمليات الأتمتة الخاصة بإسقاط الملفات والتشغيل التلقائي المجدول](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   حدد [التنفيذ التلقائي لإسقاط الملف](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) أو [التنفيذ التلقائي المجدول](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

وفيما يلي مثال على [التنفيذ التلقائي باستخدام SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات عبر SFTP Technologies، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام وجهة التصدير بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.

[!INCLUDE[footer-include](../includes/footer-banner.md)]