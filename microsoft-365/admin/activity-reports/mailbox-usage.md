---
title: Отчеты Microsoft 365 в центре администрирования — использование почтовых ящиков
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: beffbe01-ce2d-4614-9ae5-7898868e2729
description: Узнайте, как получить отчет об использовании почтовых ящиков, чтобы узнать о действиях пользователей с почтовым ящиком пользователя.
ms.openlocfilehash: 15da09574b2273e119ba9cf2c132d2e9596e9a64
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387685"
---
# <a name="microsoft-365-reports-in-the-admin-center---mailbox-usage"></a>Отчеты Microsoft 365 в центре администрирования — использование почтовых ящиков

**Отчет об использовании почтовых ящиков** предоставляет сведения о пользователях с почтовым ящиком пользователя и уровнем активности на основе электронной почты, чтения, чтения, создания встречи, отправки собрания, принятия собрания, отклонить собрание и отменить действие собрания. В нем также представлены сведения о том, какой объем хранилища используется для почтового ящика каждого пользователя и сколько из них приближаются к квотам. 
  
> [!NOTE]
> Для просмотра отчетов необходимо быть глобальным администратором, глобальным читателям или читателями отчетов в Microsoft 365 или Exchange, SharePoint, Teams Service, Team Communications или Skype для бизнеса. 
 
## <a name="how-to-get-to-the-mailbox-usage-report"></a>Просмотр отчета об использовании почтового ящика

1. В центре администрирования перейдите в раздел **отчеты о** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">использование</a> страницы.

    
2. В раскрывающемся списке **выберите отчет** выберите **Exchange** \> **использование почтовых ящиков**Exchange.
  
## <a name="interpret-the-mailbox-usage-report"></a>Анализ отчета об использовании почтового ящика

Чтобы изучить **использование почтовых ящиков** в организации, просмотрите диаграммы **Почтовый ящик**, **Хранилище** и **Квота**. 
  
|||
|:-----|:-----|
|1.  <br/> |В отчете **Использование почтового ящика** можно отследить тенденции за последние 7, 30, 90 и 180 дней. Тем не менее, если выбрать определенный день в отчете, в таблице будут отображаться данные в течение 28 дней с текущей даты (не Дата создания отчета).  <br/> |
|2.  <br/> |Данные в каждом отчете обычно закрываются в течение последних 24 – 48 часов.  <br/> |
|3.  <br/> |На диаграмме "Почтовый ящик" показано общее количество почтовых ящиков пользователей в организации, а также число активных почтовых ящиков в каждый день отчетного периода. Почтовый ящик пользователя считается активным, если он имел сообщение отправить, прочитать, создать встречу, отправить собрание, принять собрание, отклонить собрание и отменить действие собрания.  <br/> |
|4.  <br/> |На диаграмме **Хранилище** показан объем хранилища, используемый в вашей организации. Диаграмма хранения не включает архивные почтовые ящики. Дополнительные сведения об автоматическом развертывании архивации приведены [в статье Обзор неограниченного архивирования в Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/unlimited-archiving).<br/> |
|5.  <br/> | Диаграмма **Квота** показывает количество почтовых ящиков пользователей для каждой категории квоты. Существует четыре категории:  <br/>  "Хорошо"  количество пользователей, для хранилища которых не превышена квота предупреждения.  <br/>  "Предупреждение"  количество пользователей, для хранилища которых превышена квота предупреждения, но не квота запрета отправки.  <br/>  "Невозможно отправлять"  количество пользователей, для хранилища которых превышена квота запрета отправки, но не квота запрета отправки и получения.  <br/>  "Невозможно отправлять и получать"  количество пользователей, для хранилища которых превышена квота запрета отправки и получения.  <br/> |
|6.  <br/> | На диаграмме **Почтовый ящик** ось Y представляет собой количество почтовых ящиков пользователей.  <br/>  На оси Y диаграммы **Хранилище** показан объем хранилища, занятый почтовыми ящиками пользователей в организации.  <br/>  На диаграмме **Квота** ось Y представляет собой количество почтовых ящиков пользователей для каждой квоты хранилища.  <br/>  На оси X диаграмм "Почтовый ящик" и "Хранилище" представлен диапазон дат, выбранный для отчета.  <br/>  Ось X диаграммы "Квота" отражает категорию квоты.  <br/> |
|7.  <br/> |Вы можете отфильтровать отображенные диаграммы, выбрав элемент в условных обозначениях.  <br/> |
|8.  <br/> | В таблице показана разбивка использования почтовых ящиков по пользователям. Вы можете добавить в нее дополнительные столбцы.  <br/> **Имя пользователя**  это адрес электронной почты пользователя.  <br/> **Отображаемое имя** это полное имя пользователя.  <br/> Статус **Удаленный** означает, что почтовый ящик сейчас удален, но был активен в течение какой-то части отчетного периода.  <br/> **Дата удаления**  это дата удаления почтового ящика.  <br/> **Дата создания**  это дата создания почтового ящика.  <br/> **Дата последнего действия**  это дата отправки или прочтения сообщения в почтовом ящике.  <br/> **Количество элементов**  это общее число элементов в почтовом ящике.  <br/> **Используемое хранилище (МБ)** объем занятого хранилища.  <br/> **Количество удаленных** элементов относится к общему количеству удаленных элементов в почтовом ящике. <br/> **Размер удаленного элемента (МБ)** — это общий размер всех удаленных элементов в почтовом ящике. <br/> **Квота предупреждения (МБ)**  ограничение, при котором владелец почтового ящика будет получать предупреждение о том, что квота хранилища скоро будет превышена.  <br/> **Квота запрета отправки (МБ)**  ограничение, при котором почтовый ящик больше не может отправлять сообщения.  <br/> **Квота запрета отправки и получения (МБ)**  ограничение, при котором почтовый ящик больше не может отправлять и получать сообщения.  <br/>  Если политики организации не позволяют просматривать отчеты, в которых есть личные сведения пользователей, можно изменить параметр конфиденциальности для всех отчетов. Ознакомьтесь со статьей **Скрыть сведения о пользователе в разделе Отчеты** в [отчетах об активности в центре администрирования Microsoft 365](activity-reports.md).  <br/> |
|9.  <br/> |Вы также можете экспортировать данные отчета в CSV-файл Excel, выбрав ссылку **Экспорт** .  <br/> |
|||
   

