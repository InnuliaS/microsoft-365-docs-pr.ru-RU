---
title: Закрытие, повторное открытие и удаление основных вариантов обнаружения электронных данных
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: В этой статье описывается, как управлять основными случаями обнаружения электронных данных. Это включает в себя закрытие случая, повторное открытие закрытого дела и удаление обращения.
ms.openlocfilehash: 17b243a7207fd6927188b42e585101ff1d258b76
ms.sourcegitcommit: 5c96d06496d40d2523edbea336f7355c3c77cc80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "44412798"
---
# <a name="close-reopen-and-delete-a-core-ediscovery-case"></a>Закрытие, повторное открытие и удаление основного случая обнаружения электронных данных

В этой статье описывается, как закрыть, повторно открыть и удалить основные случаи обнаружения электронных данных в Microsoft 365.

## <a name="close-a-case"></a>Закрытие обращения

При наличии судебного разбирательства или расследования, поддерживаемого основным вариантом обнаружения электронных данных, можно закрыть обращение. Вот что происходит при закрытии дела:
  
- Если обращение содержит какие – либо расположения контента при удержании электронных данных, эти удержания будут отключены. После выключения удержания к расположениям, которые были заблокированы, применяется 30-дневный льготный период (называемый *задержками задержки*). Это помогает предотвратить немедленный доступ к контенту и предоставляет администраторам возможность поиска и восстановления контента, прежде чем он может быть окончательно удален после истечения периода задержки. Для получения дополнительных сведений ознакомьтесь с разделом [Удаление расположений содержимого из удержания обнаружения электронных данных](create-ediscovery-holds.md#removing-content-locations-from-an-ediscovery-hold).

- При закрытии обращения отключаются только удержания, связанные с этим обращением. Если другие удержания размещаются в местоположении контента (например, хранение для судебного разбирательства, политика хранения или удержание из другого основного случая обнаружения электронных данных), эти удержания по-прежнему будут поддерживаться.

- В этом случае все еще отображается на основной странице обнаружения электронных данных в центре соответствия требованиям Microsoft 365. Сохраняются сведения, удержания, Поиск и элементы закрытого обращения.

- Вы можете изменить обращение после его закрытия. Например, вы можете добавлять и удалять участников, создавать поисковые запросы и экспортировать результаты поиска. Основное различие между активными и закрытыми случаями заключается в том, что удержания электронных данных при закрытии обращения отключены.

Чтобы закрыть ситуацию, выполните следующие действия:
  
1. В центре соответствия требованиям Microsoft 365 щелкните ядро **обнаружения электронных**данных,  >  **Core** чтобы отобразить список основных вариантов обнаружения электронных данных в Организации.

2. Щелкните имя обращения, которое нужно закрыть.

    Отображается раскрывающаяся страница **Управление этим обращением** .

3. В разделе **Управление состоянием обращения**нажмите кнопку **Закрыть регистр**.

    Отображается предупреждение о том, что удержания, связанные с обращением, будут отключены.

4. Нажмите кнопку **Да** , чтобы закрыть обращение.

    Состояние на всплывающей странице " **Управление этим обращением** " изменяется с " **активно** " на " **закрытие**".

5. Закройте страницу **Управление этим обращением** .

6. На странице **основные обнаружения электронных** данных нажмите кнопку **Обновить** , чтобы обновить состояние закрытого дела. Завершение процесса закрытия может занимать до 60 минут.

    По завершении процесса состояние обращения изменяется на " **закрыто** " на **основной странице обнаружения электронных** данных. Щелкните имя этого случая еще раз, чтобы отобразить раскрывающуюся страницу **Управление этим обращением** , которая содержит сведения о том, когда обращение было закрыто и кто его закрыл.

## <a name="reopen-a-closed-case"></a>Повторное открытие закрытого дела

При повторном открытии такого случая все удержания электронных данных, которые были на месте, когда обращение было закрыто, не будут автоматически возобновлены. После повторного открытия обращения необходимо перейти на страницу **удержания** и включить предыдущие удержания. Чтобы включить удержание, выберите его, чтобы отобразить раскрывающуюся страницу, а затем установите для параметра **Status** значение **вкл**.
  
1. В центре соответствия требованиям Microsoft 365 щелкните ядро **обнаружения электронных**данных,  >  **Core** чтобы отобразить список основных вариантов обнаружения электронных данных в Организации.

2. Щелкните имя обращения, которое необходимо повторно открыть.

    Отображается раскрывающаяся страница **Управление этим обращением** . 

3. В разделе **Управление состоянием обращения**нажмите кнопку **повторно открыть регистр**.

    Отображается предупреждение о том, что удержания, связанные с обращением, когда оно было закрыто, не будут включены автоматически.

4. Нажмите кнопку **Да** , чтобы снова открыть обращение.

    Состояние всплывающей страницы " **Управление этим обращением** " меняется с " **закрыто** " на " **активно**".

5. Закройте страницу **Управление этим обращением** . 

6. На странице **основные обнаружения электронных** данных нажмите кнопку **Обновить** , чтобы обновить состояние повторно открытого случая. Для завершения процесса повторного открытия может потребоваться до 60 минут. 

    По завершении процесса состояние обращения изменяется на " **активно** " на **основной странице обнаружения электронных** данных. 
  
## <a name="delete-a-case"></a>Удаление обращения

Вы также можете удалять активные и закрытые базовые случаи обнаружения электронных данных. При удалении случая все операции поиска и экспорта в случае удаляются, а обращение удаляется из списка обращений на **основной странице обнаружения электронных** данных в центре соответствия требованиям Microsoft 365. Невозможно повторно открыть удаленное обращение.

Прежде чем можно будет удалить обращение (независимо от того, является ли оно активным или закрытым), необходимо сначала удалить *все* удержания электронных данных, связанные с этим обращением. Включает в себя удаление удержаний со статусом " **отключено**". 

Чтобы удалить удержание обнаружения электронных данных, выполните указанные ниже действия.

1. Перейдите на вкладку **удержания** в том случае, которое нужно удалить.

2. Щелкните удержание, которое нужно удалить.

3. На всплывающей странице нажмите кнопку **Удалить удержание**.

Чтобы удалить обращение:

1. В центре соответствия требованиям Microsoft 365 щелкните ядро **обнаружения электронных**данных,  >  **Core** чтобы отобразить список основных вариантов обнаружения электронных данных в Организации.

2. Щелкните имя случая, который требуется удалить.

3. В разделе **Управление состоянием дел** на всплывающей странице щелкните **Удалить обращение**.

Если попытка удалить все еще содержит обнаружение электронных данных, появится сообщение об ошибке. Необходимо удалить все удержания, связанные с обращением, а затем попробовать еще раз, чтобы удалить обращение.
