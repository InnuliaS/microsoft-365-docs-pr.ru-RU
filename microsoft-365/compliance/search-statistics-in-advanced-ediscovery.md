---
title: Статистика поиска
f1.keywords:
- NOCSH
ms.author: markjjo
author: esclee
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
description: ''
ms.openlocfilehash: b7975f5d288348177cbb6edec8002b4ed49de327
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069876"
---
# <a name="search-statistics"></a>Статистика поиска

Одним из способов проверки результатов поиска является просмотр статистики по результатам, чтобы убедиться, что они соответствуют ожиданиям. После завершения поиска в всплывающем окне со сведениями поиска отображается статистика высокого уровня:
- Количество и количество элементов, получаемых при поиске
- Количество частично индексированных/неиндексированных элементов, найденных в расположениях поиска
- Количество искомых почтовых ящиков и расположений.
Чтобы просмотреть более подробную статистику, нажмите кнопку "Статистика" из всплывающего меню сведений о поиске.

## <a name="summary"></a>Сводка

В представлении сводки можно просматривать результаты поиска с разбивкой по типу расположения (например, Exchange). Для каждого типа расположения можно увидеть следующее:
- Количество местоположений, в которых были элементы, соответствующие условиям поиска
- Количество элементов из этих расположений, соответствующих условиям поиска
- Общий объем элементов, которые отвечают условиям поиска.

## <a name="top-locations"></a>Основные расположения

В представлении расположений сверху отображаются отдельные расположения с наиболее совпадениями. Для каждого расположения вы увидите следующее:
- Имя расположения (например, URL-адрес SharePoint)
- Тип расположения
- Количество элементов, которые отвечают условиям поиска
- Общий объем элементов, которые отвечают условиям поиска.

## <a name="queries"></a>Запросы

Если в запросе используются ключевые слова (к:с) или ключевые слова, можно увидеть разделение запроса в представлении запросы по типу расположения. Для каждого типа расположения вы увидите следующее:

- Часть: в этом столбце будет либо слово "Primary", либо "ключевое слово". "Primary" означает, что строка содержит статистику для всего запроса, а "ключевое слово" означает один из компонентов запроса.

- Запрос: фактический компонент запроса, на который ссылается строка. Если часть "основная", это будет весь запрос; Если часть — "ключевое слово", вы увидите один из компонентов запроса здесь.
  
  - При поиске всех почтовых ящиков (без указания ключевых слов) фактическим запросом является (Size >= 0), чтобы возвращались все элементы
  
  - При поиске на сайтах SharePoint Online и OneDrive для бизнеса добавляются два следующих компонента:
    
    - NOT IsExternalContent: 1 — исключение любого контента из локальной организации SharePoint
    
    - NOT Исоненотепаже: 1-исключает все файлы OneNote, так как они будут дублироваться любого документа, который соответствует поисковому запросу.

- Количество расположений, для которых были получены элементы, соответствующие условиям поиска.

- Количество элементов из этих расположений, соответствующих условиям поиска.

- Общий объем элементов, которые отвечают условиям поиска.
