---
title: إثراء ملفات تعريف الشركات بواسطة خدمات إثراء البيانات من طرف ثالث Leadspace‬
description: معلومات عامة حول خدمات إثراء البيانات من طرف ثالث Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668707"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>إثراء ملفات تعريف الشركات من خلال Leadspace (معاينة)

Leadspace هي شركة مختصة في علوم البيانات توفر نظامًا أساسيًا لبيانات العميل من عمل لعمل. وهي تمكن العملاء من خلال ملفات تعريف العملاء الموحدة للشركات من إثراء بياناتهم. يتضمن الإثراء سمات إضافية مثل حجم الشركة والموقع والصناعة والمزيد.

## <a name="prerequisites"></a>المتطلبات الأساسية

لتكوين Leadspace، يجب استيفاء المتطلبات الأساسية التالية:

- لديك ترخيص Leadspace نشط و"المفتاح الدائم" (يشار اليه باسم **الرمز المميز لـ Leadspace**). تواصل مباشرةً مع [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) للحصول على تفاصيل حول منتجاتهم.
- لديك أذونات [المسؤول](permissions.md#administrator).
- لديك [ملفات تعريف عملاء موحدة](customer-profiles.md) للشركات.

## <a name="configuration"></a>التكوين

1. في رؤى الجمهور، انتقل إلى **البيانات‏‎** > **الإثراء**.

1. حدد **إثراء بياناتي** على تجانب Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="لقطة شاشة للإطار المتجانب Leadspace.":::

1. حدد **الشروع في العمل**، ثم أدخل **الرمز المميز لـ Leadspace** (المفتاح الدائم). راجع وقدم موافقتك على **خصوصية البيانات والتوافق‬** من خلال تحديد خانة الاختيار **أوافق**. أكد الإدخالين عن طريق تحديد **اتصال بـ Leadspace‎**.

1. حدد **تعيين البيانات** وحدد الحقول من ملفات التعريف الموحدة التي سيتم استخدامها للبحث عن بيانات الشركة المطابقة من Leadspace. الحقل **اسم الشركة** مطلوب. للحصول على دقة مطابقه أعلى، يمكن إضافة الحقلين **موقع ويب للشركة** و **موقع الشركة**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="جزء تعيين حقول Leadspace.":::
   
1. حدد **تطبيق** لإكمال تعيين الحقول.

1. حدد **تشغيل** لإثراء ملفات تعريف الشركة. تتوقف الفترة التي يستغرقها الإثراء على عدد ملفات تعريف العملاء الموحدة.

## <a name="enrichment-results"></a>نتائج الإثراء

بعد تحديث الإثراء، يمكنك مراجعة بيانات الشركة التي تم إثراؤها حديثًا والموجودة ضمن [عمليات الإثراء الخاصة بي‬](enrichment-hub.md). يمكنك العثور على وقت آخر تحديث وعدد ملفات تعريف التي تم إثراؤها.

يمكنك الوصول إلى عرض مفصل لكل ملف تعريف تم إثراؤه من خلال تحديد **عرض البيانات التي تم إثراؤها**.

لمزيد من المعلومات، راجع [مؤشرات الأداء الأساسية API لـ Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>الخطوات التالية

قم بالبناء أعلى بيانات العملاء التي تم إثرائها. أنشئ [الشرائح](segments.md)، و[المقاييس](measures.md)، وقم كذلك [بتصدير البيانات](export-destinations.md) لتقديم تجارب مخصصة لعملائك.

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات إلى Leadspace، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام Leadspace بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة هذا الإثراء في أي وقت لإيقاف استخدام هذه الوظيفة.