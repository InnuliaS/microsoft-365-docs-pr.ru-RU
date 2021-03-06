---
title: Управление custodians в расширенном случае обнаружения электронных данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте, как просмотреть сведения, изменить и массово изменить список custodians в расширенном случае обнаружения электронных данных.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95b7a7dbec5656a1ac0692ed465eb5a99d7ca11a
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024809"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a>Управление custodians в расширенном случае обнаружения электронных данных

Страница custodians на вкладке **источники** в расширенном случае обнаружения электронных данных содержит список всех custodians, которые были добавлены в обращение. Когда вы добавите custodians в дело, сведения о каждом из них автоматически собираются из Azure Active Directory и доступны для просмотра в Advanced eDiscovery.

![Управление custodians](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a>Просмотр сведений о хранитель

Чтобы просмотреть сведения о хранитель, щелкните хранитель в списке на вкладке **custodians** . Откроется всплывающая страница со следующими сведениями о хранитель:

- Контактные данные

  - **Display Name** — имя, отображаемое в адресной книге для хранитель. Обычно это сочетание имени, инициала и фамилии хранитель.
  
   - **Mail/SMTP** — основной SMTP-адрес для хранитель, например brianj@contoso.onmicrosoft.com. Кроме того, приводятся имя участника-пользователя хранитель (UPN).

  - **Title** — название задания хранитель.

  - **Department** — имя отдела, в котором работает хранитель.

  - **Руководитель** — менеджер хранитель. Указанный руководитель получит все сообщения о эскалации для этого хранитель.
  
- Сведения о расположении

  - **City** — город, в котором располагается хранитель.

  - **State** — область или край в адресе хранитель.

  - **Страна** или регион — страна или регион, где находится хранитель.

  - **Office** — расположение комнаты бизнеса в хранитель.

- Сведения о делах

  - **Состояние удержания** — указывает, был ли хранитель включен в удержание. 

  - **Состояние связи**: указывает, было ли хранитель было создано уведомление об удержании. Если хранитель было создано уведомление, это значение этого свойства **публикуется**. Если хранитель не выдал уведомление, состояние **отменяется**. 

  - **Status (состояние** ) — состояние хранитель в случае. Состояние **Active** указывает на то, что хранитель является частью дела. Если хранитель выпускается из случая, состояние изменится на " **выпущен**". 

- Источники данных и сведения об индексировании

    - **Источники данных** — отображает количество и тип источников данных (почтовые ящики, сайты и команды), которые связаны с хранитель и являются частью этого случая.

    - **Обновлять время индексирования** — указывает время и дату последнего запуска задания расширенного индексирования. Это свойство также указывает, когда в данный момент выполняется расширенный процесс индексирования.


## <a name="edit-a-custodian"></a>Изменение хранитель

По мере последовательного выполнения можно обнаружить, что могут быть дополнительные источники данных, относящиеся к определенному хранитель & вашем случае. В других сценариях может потребоваться удалить некоторые источники данных, которые были проверены и были признаны несвязанными.

Обновление источников данных, связанных с хранитель:

1. Перейдите на **Обнаружение электронных данных > Advanced eDiscovery** и откройте обращение.
  
2. Перейдите на вкладку **источники** .
  
3. На странице **custodians** выберите хранитель в списке и нажмите кнопку **изменить** на всплывающей странице.

    ![Изменение источников данных](../media/EditCustodianDataSource.PNG)
  
4. Нажмите кнопку **Выбор источников данных** , чтобы изменить параметры почтового ящика Exchange и учетной записи OneDrive хранитель, и выберите пункт **выбрать источники данных**.
  
5. Перейдите на вкладку **выберите Дополнительные источники данных** , чтобы добавить или удалить Teams, SharePoint или почтовые ящики Exchange, связанные с хранитель. 

    Для получения дополнительных сведений об источниках данных, связанных с хранитель, обратитесь к разделу "шаг 3: связывание дополнительных источников данных с хранитель" в разделе [Add custodians to Case](add-custodians-to-case.md#step-3-associate-additional-data-sources-to-a-custodian). 
  
6. Нажмите кнопку **поместить кустодиал удержания** , чтобы включить или отключить удержание для хранитель.

## <a name="re-index-custodian-data"></a>Повторное индексирование данных хранитель

В большинстве рабочих процессов обнаружения электронных данных для юридического расследования подмножество данных хранитель ищется после добавления хранитель в юридическое обращение. Из-за очень большого размера файлов или возможных повреждений данных некоторые элементы в источниках данных, связанных с хранитель, могут быть частично индексированы. С помощью [расширенной функции индексирования](indexing-custodian-data.md) расширенного обнаружения электронных данных большинство частично индексированных элементов можно автоматически исправить путем повторного индексирования этих элементов по запросу.

Когда хранитель добавляется к случаю, данные, расположенные в источниках данных, связанных с хранитель, автоматически переиндексируются автоматически (с помощью расширенного процесса индексирования). Это означает, что вы можете оставить данные на месте, а не загружать и исправлять их, а затем искать их в автономном режиме. Однако во время жизненного цикла для юридического случая новые источники данных могут быть связаны с хранитель. В этом случае вы можете повторно индексировать данные хранитель, повторно выполнив расширенный процесс индексирования, чтобы исправить все элементы с частичным индексированием и обновить индекс для данных хранитель.

Чтобы запустить процесс повторного индексирования для частично индексированных элементов:

1. Перейдите на **Обнаружение электронных данных > Advanced eDiscovery** и откройте обращение.

2. Перейдите на вкладку **источники** .

3. На странице **custodians** выберите хранитель, данные которого необходимо переиндексировать.

4. На всплывающей странице щелкните **обновить индекс**.

   Отображается диалоговое окно с сообщением о том, что было создано задание индексирования.

Повторное индексирование данных хранитель — это длительный процесс; соответствующее созданное задание называется **повторная индексация данных хранитель**. Отслеживать ход выполнения можно на вкладке " **задания** " или на вкладке " **custodians** ", отслеживая состояние в столбце " **состояние задания индексирования** ".

Дополнительные сведения см. в указанных ниже статьях.

- [Работа с ошибками обработки](processing-data-for-case.md)

- [Управление заданиями](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a>Выпуск хранитель из обращения

Хранитель размещается в ситуациях, когда обращение закрывается, хранитель больше не считается обязательством по сохранению содержимого для случая или когда хранитель считается нерелевантным для случая. 

Если вы выпустите хранитель после публикации уведомления об удержании, в Хранитель будет отправлено уведомление о выпуске. Кроме того, удаляются все удержания, размещенные в источниках данных, связанных с хранитель. Если хранитель размещается на *удержании в автоматическом режиме*, где они не получали уведомления о юридическом удержании, уведомление о выпуске не будет отправлено, но все удержания, размещенные на источниках данных, связанных с этим хранитель, удаляются.

Чтобы освободить хранитель, выполните указанные ниже действия. 

1. Перейдите на **Обнаружение электронных данных > Advanced eDiscovery** и откройте обращение.

2. Перейдите на вкладку **источники** .

3. На странице **custodians** , а затем выберите хранитель, который выпускается из этого случая.

4. На всплывающей странице нажмите кнопку **Release хранитель**.

   Будет выведена страница с предупреждением о том, что если удержание помещается в источник данных, связанный с хранитель, то удержание будет удалено и все остальные удержания, связанные с другими дополнительными случаями обнаружения электронных данных, будут по-прежнему применяться. Включает другие типы сохранения и хранения (например, политика хранения Microsoft 365).

5. Нажмите кнопку **Да** , чтобы подтвердить, что вы хотите освободить хранитель. 

    Для этого пользователя на вкладке **custodians** задано значение " **Пуск** ", а **состояние удержания** для всплывающей страницы изменяется на " **false**". 

> [!NOTE]
> Хранитель может быть одновременно задействована в нескольких юридических случаях. При отпускании хранитель из случая удержания и уведомления на другие вопросы не затрагиваются.

## <a name="bulk-edit-custodians"></a>Массовое изменение custodians

Можно использовать пакетный редактор для одновременного редактирования нескольких custodians. Для этого достаточно выбрать два или более custodians на вкладке **custodians** , чтобы отобразить Пакетный редактор, а затем выбрать одну из задач.

![Всплывающая страница для изменения параметров нескольких custodians](../media/AeDBulkEditCustodians.png)
