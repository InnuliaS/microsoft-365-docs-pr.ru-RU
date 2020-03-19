---
title: Обновления оценки соответствия требованиям корпорации Майкрософт
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Сведения о будущих обновлениях для оценки соответствия требованиям Майкрософт (Предварительная версия) — функция в центре соответствия требованиям M365, помогающая упростить и автоматизировать оценку риска.
ms.openlocfilehash: c46b70d0762a805e4ecfc83b70173c56d21a3933
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857780"
---
# <a name="microsoft-compliance-score-preview-updates"></a>Обновления оценки соответствия требованиям Майкрософт (Предварительная версия)

 В этой статье приводятся сведения о будущих обновлениях для [оценки соответствия требованиям Майкрософт](compliance-score.md) и [диспетчере соответствия требованиям Майкрософт](compliance-manager-overview.md). Узнайте больше о [связи](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager).

## <a name="improved-template-creation-and-update-processes"></a>Улучшенные процессы создания и обновления шаблонов

Мы упростили процесс импорта, экспорта и изменения шаблонов для оценки. Новый интерфейс упрощает выполнение собственных оценок для оценки соответствия требованиям и обновления.

### <a name="the-current-process"></a>Текущий процесс

Существует два способа создания шаблона в диспетчере соответствия требованиям. Вы можете скопировать существующий шаблон или импортировать данные шаблона из таблицы Excel в новый шаблон. На странице **Templates (шаблоны** ) выберите **+ Add Template (добавить шаблон** ), чтобы создать новый шаблон, указав имя, выбрав измерения и отправив файл Excel с определенным форматом и схемой. Кроме того, можно установить флажок **Копировать из существующего шаблона** , выбрать шаблон для копирования и проверить размеры, как показано на рисунке ниже. Для настройки шаблона требуется [многоэтапный процесс](working-with-compliance-manager.md#templates) , который начинается с выбора параметра **Добавить настраиваемый элемент управления** после создания шаблона.

![Оценка соответствия требованиям — панель мониторинга](../media/compliance-score-template-update-old.png "Текущий процесс копирования шаблона")

### <a name="whats-changing"></a>Изменения

Мы облегчаем создание новых шаблонов. В процессе одноэтапного **расширения** можно добавить электронную таблицу с действиями и элементами управления в существующий шаблон Microsoft, чтобы создать собственную пользовательскую версию. В раскрывающейся области **шаблона** установите флажок **создать расширение в глобальном шаблоне** , как показано на рисунке ниже. Затем вы добавляете настройки с использованием нового формата Excel, который менее сложен, чем текущий. Этот новый процесс заменяет текущую **копию из существующего шаблона** и добавляет функции **пользовательских элементов управления** .

При каждом обновлении исходной оценки с помощью процесса управления версиями, приведенного ниже, ваша настраиваемая оценка будет наследовать эти обновления и сохранять пользовательские элементы управления.

Кроме того, мы упростили изменение существующих шаблонов. Вы можете экспортировать шаблон, внести изменения в ту же книгу, а затем импортировать его с сохранением изменений.

![Оценка соответствия требованиям — панель мониторинга](../media/compliance-score-template-update-new.png "Новый процесс создания шаблона")

## <a name="versioning-notice-and-control"></a>Уведомление об управлении версиями и управление

Ваша организация будет получать обновленные оценки в следующем выпуске оценки соответствия требованиям и диспетчере соответствия требованиям для согласования с обновлениями сертификации и нормативными сведениями.

Перемотка вперед, когда обновление будет доступно для шаблона оценки или действия по улучшению, отображается значок оповещения о том, что обновление готово. Если щелкнуть этот значок, всплывающее окно поясняет обновление и выдает запрос на принятие. Ниже приведен пример оповещения о версии для оценки.

![Оценка соответствия требованиям управления версиями](../media/compliance-score-assessment-version.png "Оповещение об обновлении версии оценки")

При выборе значка оповещения раскрывается раскрывающаяся панель, в которой объясняется обновление и предлагается принять его:

![Оценка соответствия требованиям — всплывающее меню управления версиями](../media/compliance-score-assessment-version-accept.png "Область подтверждения обновления оценки")

## <a name="common-actions-will-synch-status-across-groups"></a>Общие действия будут синхронизировать состояние для разных групп

Если в Организации имеется несколько групп оценок, поведение **технических** действий (то есть действий, влияющих на всю организацию) изменится. Все повторяющиеся действия в группах будут объединены в одно действие. Это единственное действие будет содержать все отправленные заметки и доказательства из дублирующихся версий. В этом случае технические действия будут вести себя так, как если бы они принадлежали к одной группе. Все изменения, внесенные в действие в одной группе или оценке, теперь будут отображаться во всех экземплярах.  **Состояние реализации**, **Реализация dat**, **Состояние тестирования**и **Дата** тестирования будут отражать последние обновления.

## <a name="language-support"></a>Поддержка языка

Оценка соответствия теперь будет доступна на следующих языках в дополнение к английским: Китайский (упрощенное письмо), китайский (традиционное письмо), французский, немецкий, итальянский, японский, корейский, португальский (Бразилия), русский и испанский.