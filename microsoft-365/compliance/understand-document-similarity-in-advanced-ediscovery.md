---
title: Принцип подобия документов в Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 09/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4d4cb381-4c9a-4165-a455-609d525c7a88
description: Проверьте, как значение подобия документа — минимальный уровень сходства для двух файлов, которые должны рассматриваться как почти повторяющиеся, работает в Advanced eDiscovery.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 939e9ad6cb193e2019fe84f1e0d3482eebac721c
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936644"
---
# <a name="understand-document-similarity-in-advanced-ediscovery-classic"></a>Принцип подобия документов в Advanced eDiscovery (классический)

> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
В Advanced eDiscovery сходство документов — это минимальный уровень сходства, необходимый для двух документов, которые должны рассматриваться как почти повторяющиеся.
  
> [!TIP]
> Для большинства бизнес-приложений рекомендуется использовать значение подобия 60%-75%. Для очень низкого качества оптического распознавания символов (OCR) можно применить меньшее значение подобия. 
  
> [!NOTE]
> После настройки и запуска в заданном случае значение сходства не может быть изменено. 
  
В наборе NEAR-дублировать (ND) могут находиться документы с уровнем сходства ниже порога подобия. Чтобы документ присоединился к набору ND, в наборе ND должен быть по крайней мере один документ с уровнем сходства, превышающим подобную степень. 
  
Например, предположим, что для параметра подобие задано значение 80%, а в документе F1 похож документ F2 на уровне 85%, а документ F2 напоминает документ F3 на уровне 90%. 
  
Тем не менее, в документе F1 может напоминаться документ F3 на уровне 70%, который ниже порогового значения. Тем не менее, в этом примере документы F1, F2 и F3 отображаются в наборе ND. Аналогично, при использовании значения подобия 80% могли быть созданы два набора: Екуисет – 1 и Екуисет – 2. Екуисет – 1 содержит документы E1 и E2. Екуисет – 2 содержит документы F1, F2 и F3. 
  
Уровни сходства иллюстрируются следующим образом:
  
![Схожесть документов](../media/3907ea7d-e28a-4027-8fc3-be090dd39144.gif)
  
Предположим, что теперь вставлен другой документ, x1. Сходство между x1 и E3 составляет 87%. Аналогично, сходство между x1 и F1 составляет 92%. В результате Екуисет – 1, Екуисет – 2 и x1 теперь объединены в один набор ND.
  
![Похожесть документов](../media/d140d347-33d5-475a-af04-594a0f2ab13d.gif)
  
> [!NOTE]
> Если для одного набора ND назначены два документа, они останутся в одном наборе ND, даже если в набор добавляются дополнительные документы, или же при объединении наборов. 
  
После объединения наборов сводный документ может измениться при добавлении новых документов в набор. 
  
## <a name="related-topics"></a>Связанные статьи

[Advanced eDiscovery (классическая версия)](office-365-advanced-ediscovery.md)
  
[Настройка параметров анализа](set-analyze-options-in-advanced-ediscovery.md)
  
[Настройка игнорируемого текста](set-ignore-text-in-advanced-ediscovery.md)
  
[Настройка дополнительных параметров анализа](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[Просмотр результатов анализа](view-analyze-results-in-advanced-ediscovery.md)

