---
title: تصدير بيانات Customer Insights إلى مضيفي SFTP
description: تعرف على كيفية تكوين الاتصال بمضيف SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: ar-SA
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643487"
---
# <a name="connector-for-sftp-preview"></a>موصل لـ SFTP (معاينة)

استخدم بيانات في تطبيقات الجهة الخارجية عن طريق تصديرها إلى مضيف إلى بروتوكول نقل الملفات الآمن (SFTP)‬.

## <a name="prerequisites"></a>المتطلبات الأساسية

- توفر مضيف FTP وبيانات الاعتماد المناظرة.

## <a name="connect-to-sftp"></a>الاتصال بـ SFTP

1. انتقل إلى **المسؤول** > **وجهات التصدير**.

1. ضمن **SFTP**، حدد **إعداد**.

1. في حقل **الاسم المعروض**، أدخل اسمًا للوجهة سهل التمييز.

1. قم بتوفير **اسم المستخدم** و **كلمة المرور** و **اسم المضيف** لحساب SFTP. مثال: إذا كان المجلد الجذر لخادم SFTP هو /root/folder، وأردت تصدير البيانات إلى /root/folder/ci_export_destination_folder، فسيكون المضيف sftp://<server_address>/ci_export_destination_folder".

1. حدد **تحقق** لاختبار الاتصال.

1. بعد نجاح التحقق، اختر إن كنت تريد تصدير بياناتك في حالة **مضغوطة** أو **غير مضغوطة‏‎**، وحدد **محدد الحقل** للملفات المصدّرة.

1. حدد **أوافق** لتأكيد **خصوصية البيانات والتوافق‬**.

1. حدد **التالي** لبدء تكوين التصدير.

## <a name="configure-the-connection"></a>تكوين الاتصال

1. حدد **سمات العميل** التي تريد تصديرها. يمكنك تصدير سمة واحدة أو سمات متعددة.

1. حدد **التالي**.

1. حدد الشرائح التي تريد تصديرها.

1. حدد **حفظ**.

## <a name="export-the-data"></a>تصدير البيانات

يمكنك [تصدير البيانات عند الطلب](export-destinations.md). سيعمل التصدير أيضًا مع كل [تحديث مجدول](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>خصوصية البيانات والتوافق

عند تمكين Dynamics 365 Customer Insights لإرسال البيانات عبر SFTP Technologies، تسمح أنت بنقل البيانات خارج حدود الامتثال في Dynamics 365 Customer Insights، بما في ذلك البيانات الحساسة على الأرجح مثل البيانات الشخصية. ستقوم شركة Microsoft بنقل هذه البيانات وفقًا لتعليماتك، ولكنك مسؤول عن ضمان قيام وجهة التصدير بتلبية أي التزامات تتعلق بالخصوصية أو الأمان قد تكون لديك. لمزيد من المعلومات، راجع [بيان خصوصية Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
بإمكان مسؤول Dynamics 365 Customer Insights إزالة وجهة التصدير هذه في أي وقت لإيقاف استخدام هذه الوظيفة.
