---
title: Настройка политик безопасных вложений Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: Узнайте, как определить политики безопасных вложений, чтобы защитить организацию от вредоносных файлов в электронной почте.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 581c45c9c5b606b3b4b0ba91bd96740bc838629d
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617234"
---
# <a name="set-up-office-365-atp-safe-attachments-policies"></a>Настройка политик безопасных вложений Office 365 ATP

> [!IMPORTANT]
> Эта статья предназначена для бизнес-клиентов, у которых есть [Office 365 Advanced Threat Protection](office-365-atp.md). Если вы являетесь домашним пользователем, который ищет сведения об безопасных вложениях в Outlook, ознакомьтесь со статьей [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Пользователи регулярно отправляют, получают и совместно используют вложения, такие как документы, презентации, электронные таблицы и многое другое. Не всегда просто определить, является ли вложение безопасным или вредоносным, просто взглянув на сообщение электронной почты. Последнее, что вы хотите сделать, — это вредоносное вложение, которое поможет вреакинг в Организации. К счастью, [Office 365 Advanced Threat protection](office-365-atp.md) (ATP) может помочь. Политики [безопасных вложений ATP](atp-safe-attachments.md) можно настроить, чтобы обеспечить защиту Организации от атак небезопасных вложений электронной почты.

## <a name="what-to-do"></a>Действия

1. Проверка необходимых компонентов

2. Настройка политики безопасных вложений ATP

3. Сведения о параметрах политики безопасных вложенных файлов ATP

## <a name="step-1-review-the-prerequisites"></a>Шаг 1: Проверка необходимых компонентов

- Убедитесь, что в вашей организации используется [Advanced Threat Protection в Office 365](office-365-atp.md).

- Убедитесь, что у вас есть необходимые разрешения. Для определения (или изменения) политик ATP должна быть назначена роль управления организацией Exchange Online (по умолчанию эта роль назначается глобальному администратору) или как для Exchange Online санацией, так и для ролей администратора безопасности. Более подробную информацию можно найти в следующей таблице.

  |Role|Где/как назначено|
  |---------|---------|
  |Глобальный администратор |Сотрудник, который подписывается на приобретение Microsoft 365, по умолчанию является глобальным администратором. (Чтобы узнать больше, ознакомьтесь со статьей [о ролях администратора майкрософт 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .)|
  |Администратор безопасности |Центр администрирования Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
  |Управление организацией Exchange Online, управление Exchange Online санацией |Центр администрирования Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>или <br>  Командлеты PowerShell (см. [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|
  |

  Дополнительные сведения о ролях и разрешениях приведены [в разделе разрешения в &amp; центре безопасности и соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

- [Сведения о параметрах политики безопасных вложенных файлов ATP](#step-3-learn-about-atp-safe-attachments-policy-options) (в этой статье). Некоторые параметры, такие как параметры монитора или замены, могут привести к незначительной задержке электронной почты при сканировании вложений. Чтобы избежать задержки в сообщениях, рассмотрите возможность использования [динамической доставки и предварительного просмотра](dynamic-delivery-and-previewing.md).

- Дождитесь распространения новой или обновленной политики на все центры обработки данных Microsoft 365 до 30 минут.

## <a name="step-2-set-up-or-edit-an-atp-safe-attachments-policy"></a>Шаг 2: Настройка (или изменение) политики безопасных вложений ATP

1. Перейдите к [https://protection.office.com](https://protection.office.com) рабочей или учебной учетной записи и войдите в нее.

2. В центре безопасности &amp; и соответствия требованиям в области навигации слева в разделе **Управление угрозами**выберите пункт **Policy** \> **безопасные вложения**политики.

3. Если вы видите раздел **Включение ATP для SharePoint, OneDrive и Microsoft Teams**, рекомендуем выбрать этот параметр. Это приведет к включению [Advanced Threat Protection в Office 365 для SharePoint, OneDrive и Microsoft Teams](atp-for-spo-odb-and-teams.md) для своей среды Майкрософт 365.

4. Нажмите кнопку **создать** (Новая кнопка напоминает знак плюса ( **+** )), чтобы приступить к созданию политики.

5. Укажите имя, описание и параметры политики.<br/><br/>**Пример:** Чтобы настроить политику "без задержки", которая сразу же предоставляет сообщения всех пользователей и затем повторно присоединяет вложения после сканирования, можно указать следующие параметры:

   - В поле **имя** введите нет задержек.

   - В поле **Описание** введите описание, например, доставляет сообщения немедленно и повторно присоединяет вложения после сканирования.

   - В разделе ответ выберите параметр **Динамическая доставка** . ([Узнайте больше о динамической доставке и предварительном просмотре с безопасными вложениями ATP](dynamic-delivery-and-previewing.md).)

   - В разделе **Перенаправление вложения** выберите параметр Включить перенаправление и введите адрес электронной почты глобального администратора, администратора безопасности или аналитика безопасности, которые будут изучать вредоносные вложения.

   - В разделе **применено** выберите **домен получателя**, а затем выберите свой домен. Нажмите кнопку **Добавить**, а затем нажмите кнопку **ОК**.

6. Нажмите кнопку **Сохранить**.

Рекомендуется настроить несколько политик безопасных вложений ATP для вашей организации. Эти политики будут применены в том порядке, в котором они перечислены на странице **безопасных вложений ATP** . После того как политика будет определена или изменена, предоставьте для них не менее 30 минут, чтобы политики вступили в силу во всех центрах обработки данных Майкрософт.

## <a name="step-3-learn-about-atp-safe-attachments-policy-options"></a>Шаг 3: сведения о параметрах политики безопасных вложений ATP

При настройке политик безопасных вложений ATP можно выбрать один из нескольких вариантов, в том числе мониторинг, блокировка, замена, динамическая Доставка и т. д. На случай, если вы не хотите узнать, что делает эти варианты, приведенная ниже таблица суммирует все результаты.

||||
|---|---|---|
|**Вариант**|**Effect**|**Используйте, когда нужно:**|
|**Выкл.**|Не сканирует вложения для вредоносных программ  <br/> Не задерживается доставки сообщений|Отключение сканирования для сканеров, факсов или промежуточных узлов, которые будут отправлять только известные, хорошие вложения  <br/> Предотвращение ненужных задержек при маршрутизации внутренних сообщений маршрутизации.  <br/> **Мы не рекомендуем использовать этот вариант для большинства пользователей. Этот параметр следует использовать только для отключения сканирования безопасных вложений ATP для небольшой группы доверенных отправителей.**|
|**Монитор**|Доставляет сообщения с вложениями и отслеживает, что происходит с обнаруженной вредоносной программой|Просмотр места обнаружения вредоносных программ в Организации|
|**Блок**|Предотвращает выполнение сообщений с обнаруженными вредоносными вложениями  <br/> Отправляет сообщения с обнаруженной вредоносной программой [в карантин в Office 365](manage-quarantined-messages-and-files.md) , где администратор безопасности или аналитик может просматривать и освобождать (или удалять) эти сообщения.  <br/> Автоматическое блокирование будущих сообщений и вложений|Защита Организации от повторяющихся атак, использующих те же вредоносные приложения|
|**Replace**|Удаляет обнаруженные вредоносные вложения  <br/> Уведомляет получателей об удалении вложений  <br/> Отправляет сообщения с обнаруженной вредоносной программой [в карантин в Office 365](manage-quarantined-messages-and-files.md) , где администратор безопасности или аналитик может просматривать и освобождать (или удалять) эти сообщения.|Повышение видимости для получателей, которые были удалены из-за обнаруженных вредоносных программ|
|**Динамическая Доставка**|Немедленное Досрочное предоставление сообщений  <br/> Заменяет вложения с помощью файла заполнителя до завершения сканирования, а затем повторно присоединяет вложения, если вредоносные программы не обнаружены  <br/> Включает возможности предварительного просмотра вложений для большинства файлов PDF и Office во время сканирования  <br/> Отправляет сообщения с обнаруженной вредоносной программой в карантин, где администратор безопасности или аналитик может просматривать и освобождать (или удалять) эти сообщения.  <br/> [Сведения о динамической доставке и предварительном просмотре с безопасными вложениями ATP](dynamic-delivery-and-previewing.md) <br/> |Предотвращение задержки сообщений при защите получателей от вредоносных файлов  <br/> Разрешение получателям предварительный просмотр вложений в безопасном режиме при сканировании|
|**Разрешить перенаправление**|Применяется при выборе параметра "монитор", "блокировать" или "заменить"  <br/> Отправляет вложения на указанный адрес электронной почты, на который могут изучены Администраторы или аналитики безопасности|Включение администраторов и аналитик безопасности для исследования подозрительных вложений|
|**Применить вышеуказанный вариант, если время ожидания для сканирования вредоносных программ истекает или возникнет ошибка**|Применяет действие, настроенное для небезопасных вложений, к вложениям, которые не удается просканировать (из-за истечения времени ожидания или ошибки).|
|

## <a name="next-steps"></a>Дальнейшие действия

После выполнения политик безопасных вложений ATP вы можете узнать, как работает ATP для вашей организации, просмотрев отчеты. Чтобы узнать больше, ознакомьтесь со следующими материалами:

- [Просмотр отчетов для Office 365 Advanced Threat protection](view-reports-for-atp.md)

- [Использование обозревателя в Центре безопасности и соответствия требованиям](threat-explorer.md)

Оставайтесь в курсе новых функций, поступающих в ATP. Посетите [план Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=O365) и Узнайте о [новых возможностях, которые добавляются в ATP](office-365-atp.md#new-features-in-office-365-atp).
