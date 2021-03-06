---
title: Отправка сообщений в корпорацию Майкрософт для анализа вручную
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: Администраторы и конечные пользователи могут узнать, как почтовые сообщения (хорошая почта, помеченная как плохая или плохая почта) в корпорацию Майкрософт для анализа.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d6973330c4504bd6478265205f60798b3b7c1875
ms.sourcegitcommit: 7a59d83a8660c2344ebdb92e0ea0171c9c2d9498
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44811042"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a>Отправка сообщений в корпорацию Майкрософт для анализа вручную

> [!NOTE]
> Если вы являетесь администратором в Организации с почтовыми ящиками Exchange Online, рекомендуем использовать портал отправки в центре безопасности & соответствия требованиям. Дополнительные сведения см. в [статье Использование отправки администратором для отправки подозреваемой спама, фишинга, URL-адресов и файлов в корпорацию Майкрософт](admin-submission.md).

Может быть непонятно, когда пользователи в вашей организации получают нежелательные сообщения или фишинговые сообщения в их папке "Входящие" или если они не получили легальное сообщение электронной почты, так как отмечено как нежелательное. Мы постоянно намерены настраивать фильтры нежелательной почты, чтобы они были более точными.

Вы и ваши пользователи могут помочь этому процессу, отправив ложные срабатывания (хорошее сообщение отмечено как плохое), ложные отрицательные отрицательные (недопустимые почты) и фишинговые сообщения в корпорацию Майкрософт для анализа.

> [!NOTE]
> Из-за большого объема получаемых данных мы не можем ответить на все запросы на анализ.

## <a name="submit-false-negatives-to-microsoft"></a>Передача ложных негативных результатов в корпорацию Майкрософт

> [!TIP]
> Вместо того чтобы сообщать о ложных отрицательных значениях, пользователи Outlook и Outlook в Интернете (прежнее название — Outlook Web App) могут использовать надстройку сообщения отчета для Microsoft Outlook. Сведения об установке и использовании этого средства приведены [в разделе Включение надстройки Report Message](enable-the-report-message-add-in.md).

Если вы получаете сообщение, прошедшее с помощью фильтрации нежелательной почты, которое должно быть определено как нежелательная почта или фишинг, вы можете отправить сообщение в Microsoft спама и Microsoft фишинга, если это необходимо. Аналитики просматривают сообщение и добавляют его к фильтрам на уровне службы, если он соответствует критериям классификации.

1. Создайте новое пустое сообщение электронной почты с одним из следующих получателей:

   - **Нежелательная почта**:`junk@office365.microsoft.com`

   - **Фишинг**:`phish@office365.microsoft.com`

2. Перетащите нежелательное или мошенническое сообщение в новое сообщение. Это приведет к сохранению нежелательного или фишингового сообщения в виде вложения в новом сообщении. Не копируйте и не вставляйте содержимое сообщения или пересылаете сообщение (вам нужно исходное сообщение, чтобы мы могли проверить заголовки сообщений).

   > [!NOTE]
   > <ul><li>В новое сообщение можно вложить несколько сообщений. Убедитесь, что все сообщения имеют один и тот же тип: фишинговые или нежелательные сообщения электронной почты.</li><li>Оставьте текст нового сообщения пустым.</li><li>Используйте формат MSG (формат Outlook) или EML (по умолчанию Outlook в Интернете) для вложенных сообщений.</li></ul>

3. Когда все будет готово, нажмите кнопку **Отправить**.

> [!TIP]
> Администраторы имеют несколько различных способов блокирования определенных сообщений, которые неопознаны как спам. Дополнительные сведения см. [в разделе Создание заблокированных списков отправителей в EOP](create-block-sender-lists-in-office-365.md).

## <a name="submit-false-positives-to-microsoft"></a>Передача ложных срабатываний в корпорацию Майкрософт

> [!TIP]
> Вместо использования следующих процедур для создания отчетов о ложных срабатываниях, пользователи в Outlook и Outlook в Интернете могут использовать надстройку сообщения отчета для Microsoft Outlook. Сведения об установке и использовании этого средства приведены [в разделе Включение надстройки Report Message](enable-the-report-message-add-in.md).

Если сообщение было ошибочно определено как спам, вы можете отправлять сообщение в группу анализа нежелательной почты Майкрософт. Аналитики оценивают сообщение и (в зависимости от результатов анализа) фильтры, которые могут быть настроены на уровне службы, чтобы разрешить сообщения.

1. Создание нового пустого сообщения электронной почты с `not_junk@office365.microsoft.com` получателем:

2. Перетащите неопознанное сообщение в новое сообщение. Это приведет к сохранению неопознанного сообщения в виде вложения в новом сообщении. Не копируйте и не вставляйте содержимое сообщения или пересылаете сообщение (вам нужно исходное сообщение, чтобы мы могли проверить заголовки сообщений).

   > [!NOTE]
   > <ul><li>В новое сообщение можно вложить несколько сообщений. Убедитесь, что все сообщения имеют один и тот же тип: сообщения фишинга или нежелательные сообщения электронной почты.</li><li>Оставьте текст нового сообщения пустым.</li><li>Используйте формат MSG (формат Outlook) или EML (по умолчанию Outlook в Интернете) для вложенных сообщений.</li></ul>

3. Когда все будет готово, нажмите кнопку **Отправить**.

> [!TIP]
> Администраторы имеют несколько различных способов, позволяющих определенным сообщениям пропускать фильтрацию нежелательной почты. Дополнительные сведения см. [в статье Создание списков надежных отправителей в EOP](create-safe-sender-lists-in-office-365.md).

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a>Создание правила обработки почтового ящика для получения копий сообщений, отправленных в корпорацию Майкрософт

Инструкции можно найти в статье [Использование правил для обработки почтового ящика для просмотра отчетов о пользователях в Майкрософт](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).
