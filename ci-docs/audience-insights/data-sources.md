---
title: استخدام مصادر بيانات لاستيعاب البيانات
description: تعرف على كيفية استيراد البيانات من مصادر متعددة.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: e7bcf82c4fe3625ef791ec2b0a7651be0356a006
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354033"
---
# <a name="data-sources-overview"></a>نظرة عامة مصادر البيانات



تتصل قدرة رؤى الجمهور في Dynamics 365 Customer Insights بالبيانات من مجموعة واسعة من المصادر. غالبًا ما يشار إلى الاتصال بمصدر البيانات على أنه عملية *استيعاب بيانات*. بعد استيعاب البيانات، يمكنك [توحيدها](data-unification.md) واتخاذ إجراءات بشأنها.

## <a name="add-a-data-source"></a>إضافة مصدر بيانات

راجع المقالات المفصلة المتعلقة بكيفية إضافة قائمة مصدر بيانات، حسب الخيار الذي تختاره.

يمكنك إضافة عناصر البيانات التالية:

- [من خلال عشرات الموصلات من Power Query](connect-power-query.md)
- [من مجلد نموذج البيانات العامة](connect-common-data-model.md)
- [من مخزن Microsoft Dataverse الخاص بك](connect-dataverse-managed-lake.md)
- [من خلال قاعدة بيانات Azure Synapse Analytics ](connect-synapse.md)

> [!NOTE]
> إذا كنت تستخدم الإصدار التجريبي، فإن قسم طرق الاستيراد يتضمن خيار **مكتبة بيانات Customer Insights**. اختر هذا الخيار لتحديد عينة مجموعة بيانات متوفرة لصناعات متنوعة. لمزيد من المعلومات، راجع [Dynamics 365 Customer Insights إصدار تجريبي](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>إضافة البيانات من مصادر البيانات المحلية

يتم دعم استيعاب البيانات من مصادر البيانات المحلية في Audience Insights استنادًا إلى تدفقات بيانات Microsoft Power Platform. يمكنك تمكين تدفقات البيانات في Customer Insights من خلال [توفير عنوان URL لبيئة Microsoft Dataverse](create-environment.md) عند إعداد البيئة.

تستخدم مصادر البيانات التي يتم إنشاؤها بعد ربط بيئة Dataverse مع Customer Insights تدفقات بيانات [Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) بشكل افتراضي. تدعم تدفقات البيانات الاتصال المحلي باستخدام بوابة البيانات. يمكنك إزالة وإعادة إنشاء مصادر البيانات التي كانت موجودة قبل اقتران بيئة Dataverse[باستخدام بوابات البيانات الداخلية](/data-integration/gateway/service-gateway-app).

ستظهر بوابات البيانات من بيئة Power BI أو Power Apps موجودة ويمكنك إعادة استخدامها في Customer Insights. تعرض صفحة مصادر البيانات ارتباطات للوصول إلى بيئةMicrosoft Power Platform ، حيث يمكنك عرض محلي بوابات البيانات المحلية وتكوينها.

## <a name="review-ingested-data"></a>مراجعة البيانات المستوعبة

سترى اسم كل مصدر بيانات تم إدخاله وحالته وآخر مرة تم فيها تحديث البيانات لهذا المصدر. يمكنك فرز قائمة مصادر البيانات حسب كل عمود.

> [!div class="mx-imgBorder"]
> ![مصدر بيانات تمت إضافته.](media/configure-data-datasource-added.png "مصدر بيانات تمت إضافته")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

قد يستغرق تحميل البيانات وقتا. بعد الانتهاء من التحديث بنجاح، يُمكنك مراجعة البيانات المستوعبة من صفحة **الكيانات**. للمزيد من المعلومات، راجع [التفاصيل](entities.md).

## <a name="refresh-a-data-source"></a>تحديث مصدر البيانات

يمكن تحديث مصادر البيانات حسب جدول تلقائي أو يمكن تحديثها يدويًا عند الطلب. 

انتقل إلى **المسؤول** > **النظام** > [**الجدول**](system.md#schedule-tab) لتكوين عمليات تحديث مجدولة لجميع مصادر البيانات التي تم استيعابها.

لتحديث مصدر البيانات حسب الطلب، اتبع الخطوات التالية:

1. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.

2. حدد الخصاص العمودي بجوار القائمة مصدر البيانات ترغب في تحديثها وحدد **تحديث** من القائمة المنسدلة.

3. تم تشغيل مصدر البيانات الآن للحصول على تحديث يدوي. سيؤدي تحديث مصدر البيانات إلى تحديث كل من مخطط الكيان والبيانات لجميع الكيانات المحددة في مصدر البيانات.

4. حدد **إيقاف التحديث** إذا كنت تريد إلغاء تحديث موجود وسيعود مصدر البيانات إلى حالة التحديث الأخيرة.

## <a name="delete-a-data-source"></a>حذف مصدر البيانات

1. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **مصادر البيانات**.

2. حدد الخصاص العمودي بجوار القائمة مصدر البيانات ترغب في إزالتها وحدد **حذف** من القائمة المنسدلة.

3. قم بتأكيد الحذف.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
