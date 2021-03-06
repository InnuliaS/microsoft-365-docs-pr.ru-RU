---
title: Использование общих запросов в расширенной охоте службы защиты от угроз (Майкрософт)
description: Быстро начинайте охоту на угрозы с помощью готовых и общих запросов. Делитесь своими запросами с людьми или со своей организацией.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, пользовательские обнаружения, схема, Кусто, репозиторий GitHub, мои запросы, общие запросы
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 38eb3c39c5473d0a729b12771b61e965dbc81931
ms.sourcegitcommit: 3b2fdf159d7dd962493a3838e3cf0cf429ee2bf2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "42929484"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Использование общих запросов в расширенной охоте

**Область применения:**
- Защита от угроз (Майкрософт)



Запросами [расширенной охоты](advanced-hunting-overview.md) можно делиться с пользователями одной организации. Вы также можете найти общедоступные запросы в GitHub. Эти запросы позволяют быстро реализовывать сценарии охоты на угрозы, не создавая запросы с нуля.

![Изображение общих запросов](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Сохранение и изменение запроса и предоставление к нему общего доступа
Вы можете сохранить новый или существующий запрос, чтобы он был доступен только вам, или поделиться им с пользователями своей организации. 

1. Создание или изменение запроса 

2. Нажмите разворачивающуюся кнопку **Сохранить запрос** и выберите параметр **Сохранить как**.
    
3. Введите имя запроса. 

   ![Изображение сохранения запроса](../../media/advanced-hunting-save-query.png)

4. Выберите папку, в которую нужно сохранить запрос.
    - **Общие запросы** — общие для всех пользователей вашей организации
    - **Мои запросы** — доступны только для вас
    
5. Нажмите кнопку **Сохранить**. 

## <a name="delete-or-rename-a-query"></a>Удаление или переименование запроса
1. Щелкните правой кнопкой мыши запрос, который нужно переименовать или удалить.

    ![Изображение удаления запроса](../../media/advanced_hunting_delete_rename.png)

2. Нажмите кнопку **Удалить** и подтвердите удаление. Или нажмите кнопку **Переименовать** и введите новое имя запроса.

## <a name="access-queries-in-the-github-repository"></a>Доступ к запросам в репозитории GitHub  
Исследователи безопасности Майкрософт часто делятся запросами расширенной охоты в [специальном общедоступном репозитории в GitHub](https://github.com/microsoft/MTP-AHQ). Этот репозиторий открыт для участия. Чтобы внести свой вклад, [бесплатно присоединяйтесь к GitHub](https://github.com/).

>[!tip]
>Исследователи безопасности Майкрософт также предоставляют запросы расширенной охоты, которые можно использовать для обнаружения действий и индикаторов, связанных с возникающими угрозами. Эти запросы предоставляются в рамках отчетов [аналитики угроз](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) в Центре безопасности в Microsoft Defender.

## <a name="related-topics"></a>См. также
- [Обзор расширенной охоты на угрозы](advanced-hunting-overview.md)
- [Сведения о языке запросов](advanced-hunting-query-language.md)
- [Работать с результатами запроса](advanced-hunting-query-results.md)
- [Поиск угроз на устройствах и в сообщениях электронной почты](advanced-hunting-query-emails-devices.md)
- [Сведения о схеме](advanced-hunting-schema-tables.md)
- [Рекомендации по применению запросов](advanced-hunting-best-practices.md)
