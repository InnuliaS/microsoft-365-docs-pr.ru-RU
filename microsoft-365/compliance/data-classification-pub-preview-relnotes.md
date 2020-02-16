---
title: Заметки о выпуске предварительной версии классификации данных (предварительная версия)
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Заметки о выпуске общедоступной предварительной версии классификации данных.
ms.openlocfilehash: fecf643d12cf544c16570c173b15bb1e0dc043f0
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887345"
---
# <a name="data-classification-public-preview-release-notes-preview"></a>Заметки о выпуске общедоступной предварительной версии классификации данных (предварительная версия)

В этой общедоступной предварительной версии появилась новая функция, позволяющая начать сканирование конфиденциального содержимого и содержимого с метками *до* создания политик. Она называется **управлением изменениями нулевого состояния**. Такая возможность позволит вам определить влияние всех меток хранения и меток конфиденциальности в вашей среде и начать оценку требований политики защиты и управления.

Ознакомьтесь с заметками о выпуске для оптимальной работы с этой общедоступной предварительной версией. Мы будем работать над этими вопросами, пока не появится общедоступная версия (GA).

## <a name="permissions-for-accessing-content-explorer"></a>Разрешения на доступ к обозревателю содержимого

Доступ к обозревателю содержимого чрезвычайно ограничен, так как он позволяет прочитать содержимое отсканированных файлов. Для доступа к обозревателю содержимого необходимо быть участником групп ролей **Читатель списка в обозревателе содержимого** и **Читатель содержимого в обозревателе содержимого**. Ни одна учетная запись не имеет доступа к обозревателю содержимого по умолчанию. См. статью [Использование обозревателя содержимого классификации данных (предварительная версия)](data-classification-content-explorer.md#permissions) Глобальный администратор, администратор соответствия или администратор данных может назначить необходимую роль в группе **Читатель списка в обозревателе содержимого** и **Читатель содержимого в обозревателе содержимого**.

> [!TIP]
> Группы ролей **Читатель списка в обозревателе содержимого** и **Читатель содержимого в обозревателе содержимого** могут не отображаться на странице разрешений, в то время как элементы управления доступом на основе ролей (RBAC) развертываются во всем мире. Если они не отображаются на странице разрешений, необходимо создать настраиваемую группу ролей и назначить роль `data classification list viewer` и (или) `data classification content viewer` настраиваемой группе ролей.

## <a name="exchange-mailbox-count"></a>Количество почтовых ящиков Exchange

При детализации почтовых ящиков Exchange выводится небольшая подсказка. В ней сообщается, что общее число типов конфиденциальной информации, меток конфиденциальности и меток хранения, которое отображается, может не совпадать с количеством элементов, которые будут найдены в почтовом ящике. Это объясняется тем, что при детализации папки общее число рассчитывается в процессе классификации интерактивного представления содержимого.

## <a name="seeing-guids-instead-of-label-names"></a>Отображение GUID вместо имен меток

Клиенты с личной предварительной версией сталкивались с тем, что при удалении метки, которая уже была применена к содержимому, имена меток разрешались в 32-битный идентификатор GUID в обозревателе содержимого и в обозревателе действий. 

## <a name="rendering-of-encrypted-documents"></a>Отображение зашифрованных документов

Зашифрованные файлы SharePoint, Exchange и OneDrive не отображаются в обозревателе содержимого. Соображения конфиденциальности требуют баланса между необходимостью просматривать содержимое файла в обозревателе содержимого и необходимостью отображать содержимое в зашифрованном виде. Разрешения, предоставленные группами ролей **Читатель списка в обозревателе содержимого** и **Читатель содержимого в обозревателе содержимого**, позволяют увидеть представление списка файлов, метаданные файлов и ссылку для получения доступа к содержимому через веб-клиент.

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>Поддерживаемые символы в именах меток хранения в поиске SharePoint

Служба поиска SharePoint не поддерживает имена меток хранения с символами `-` или `_`. Например, не поддерживаются имена меток `Label-MIP` и `Label_MIP`. Служба поиска SharePoint поддерживает такие символы в именах меток конфиденциальности и типов конфиденциальной информации.

## <a name="see-also"></a>См. также

- [Начало работы с классификацией данных (предварительная версия)](data-classification-overview.md)
- [Просмотр действий с метками (предварительная версия)](data-classification-activity-explorer.md)
- [Просмотр содержимого с метками (предварительная версия)](data-classification-content-explorer.md)
- [Метки конфиденциальности](sensitivity-labels.md)
- [Метки хранения](labels.md)
- [Что позволяют искать типы конфиденциальной информации](what-the-sensitive-information-types-look-for.md)
