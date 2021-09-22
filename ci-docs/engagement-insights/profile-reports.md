---
title: تمكين تقارير ملفات التعريف الخارجية
description: كيفية إنشاء تقارير ملفات تعريف جديدة تم تجميعها حسب الحالات المشخصة وال عمرها والمنطقة أو منطقة الأصل.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 3aa9599fc780098a2f7f31f0210d76ed2ef27ece774dd6212b5cb2a599ad537e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033936"
---
# <a name="out-of-box-profile-reports"></a>تقارير ملفات التعريف الخارجية

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

التقرير هو مجموعة من مرئيات البيانات التي تساعدك على قياس وفهم سلوك المستخدم. من خلال الاتصال برؤى الجمهور Customer Insights، يمكن أن تظهر رؤى الارتباط تقريرا بمعلومات حول ملفات تعريف العملاء الموحدة. يتضمن هذا التقرير عدد ملفات التعريف التي لديك، التي تم تجميعها حسب الحالات المشخصة، والعمر، والموقع الجغرافي.

## <a name="prerequisites"></a>المتطلبات الأساسية

يجب الجمهور بيئة المعلومات المتعمقة تخزين البيانات في حساب مدار من قبل عميل Azure Data Lake Storage.

إذا كنت تستخدم إصدارا تجريبيا من رؤى الجماهير أو بيئة في بيانات data lake المدارة لـ Customer Insights، [اتصل بنا](https://go.microsoft.com/fwlink/?linkid=2145734) للحصول على المساعدة.  


## <a name="enable-the-customer-profile-report"></a>تمكين تقرير ملف تعريف العميل

يجب على مسؤول البيئة [إنشاء اتصال الجمهور الرؤى](configure-connections.md).

بعد تحديد تفاصيل الاتصال، يمكن للمسؤول منح حق الوصول إلى أشخاص آخرين في المؤسسة لمشاهدة التقرير. فقط مسؤول البيئة الذي يقوم تلقائيًا بإعداد الاتصال لديه حق الوصول إلى تقرير ملف تعريف العميل تلقائيا. 

بعد إكمال الاتصال، ستكون ميزة **ملفات التعريف** متوفرة في جزء التنقل الأيسر. 

- انتقل إلى **اكتشاف** > **ملفات التعريف** للاطلاع على تقرير.

يحتوي تقرير **ملفات التعريف** على مرئيات حول المهيأ والعمر والموقع الجغرافي لملفات تعريف العملاء المتصلين.

:::image type="content" source="media/customer-profiles.png" alt-text="تقرير ملف تعريف العميل.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]