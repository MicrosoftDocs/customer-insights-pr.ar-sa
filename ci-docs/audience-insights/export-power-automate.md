---
title: موصل Power Automate  | Microsoft Docs
description: إنشاء عمليات سير العمل في Microsoft Power Automate من Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/03/2020
ms.locfileid: "4404895"
---
# <a name="power-automate-connector-preview"></a>موصل Power Automate (معاينة)

قم بتشغيل أحداث معينة لكي تحدث تلقائيًا عند تغيير بياناتك وأدر مزيدًا من عمليات سير المهام المعقدة مباشرةً في [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Power Automate المشغلات

يمكنك استخدام العديد من المشغلات التي تتيح لك إنشاء سير عمل لتنفيذ المهام المتكررة تلقائيا، مثل الإعلامات أو الإجراءات الأكثر تقدمًا. 

- التشغيل عند فشل تحديث مصدر البيانات. 
- التشغيل عند نجاح تحديث مصدر البيانات.
- التشغيل عند تخطي الحد في شريحة. يقتصر التشغيل على تجاوز الحد.
- التشغيل عند تخطي الحد في إجراء أعمال. يقتصر التشغيل على تجاوز الحد.
- التشغيل عند اكتمال عملية تحديث كاملة (مصادر البيانات والشرائح والمقاييس,...).
- تشغيل عند اكتمال تحديث عملية التوحيد (التعيين، المطابقة، الدمج).

[تكوين المشغلات في Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>إجراءات Power Automate
يوفر موصل Power Automate إجراءات أخرى بخلاف المشغلات المتوفرة. لمزيد من المعلومات، راجع [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>إنشاء سير مهام Power Automate في رؤى الجمهور

1. في رؤى الجمهور، انتقل إلى **المسؤول‏‎** > **النظام**.

1. في الصفحة **النظام**، حدد علامة التبويب **الحالة**.

1. في القسم **مصادر البيانات**، قم بتحديد **عمليات سير المهام** وحدد **إنشاء عملية سير المهام** من القائمة المنسدلة.
   > [!div class="mx-imgBorder"]
   > موصل ![Power Automate يوضح إنشاء إجراء سير العمل](media/power-automate-connector-create-flow.png "موصل Power Automate يوضح إنشاء إجراء سير العمل")

1. في Power Automate، حدد أحد المشغلات المتوفرة لإنشاء عملية سير المهام المفضلة لديك. إذا كنت تقوم بإنشاء التدفق الأول، ستحتاج المصادقة مع الموصل Power Automate أولاً.
