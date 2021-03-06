---
title: Добавление тегов к документам в наборе для проверки
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
description: Маркировка документов в наборе рецензирования помогает удалить ненужные материалы и определить релевантный контент в расширенном случае обнаружения электронных данных.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 445bf9a0ee5959c4972920a74e7bd1596d9edca1
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034553"
---
# <a name="tag-documents-in-a-review-set"></a>Добавление тегов к документам в наборе для проверки

Организация контента в наборе проверки важна для выполнения различных рабочих процессов в процессе обнаружения электронных данных. Это включает:

- Отбор ненужного контента

- Определение релевантного содержимого
 
- Определение контента, который должен быть проверен экспертом или юристом

Когда эксперты, юристы или другие пользователи просматривают контент в наборе рецензирования, их мнения, связанные с содержимым, могут быть захвачены с помощью тегов. Например, если предполагалось исключать ненужное содержимое, пользователь может отмечать документы тегами, например "не отвечает". После рассмотрения и пометки контента можно создать поисковый набор для исключения любого содержимого, помеченного как "не отвечает", что исключает это содержимое из следующих действий в рабочем процессе обнаружения электронных данных. Область тегов можно изменить для каждого случая, чтобы теги могли поддерживать рабочий процесс, предназначенный для рецензирования.

## <a name="tag-types"></a>Типы тегов

Расширенное обнаружение электронных данных предоставляет два типа тегов:

- **Один тег выбора** — запрещает пользователям выбирать один тег в группе. Это может быть удобно, чтобы пользователи не могли выбирать конфликтующие теги, такие как "реагирующий" и "не отвечает". Они будут отображаться в виде переключателей.

- **Несколько тегов выбора** — позволяет пользователям выбирать несколько тегов в группе. Они будут отображаться в качестве флажков.

## <a name="tag-structure"></a>Структура тегов

В дополнение к типам тегов, структура того, как теги организованы в палитре тегов, может использоваться для упрощения интуитивной маркировки документов. Теги группируются по разделам. Обзор Set Search поддерживает поиск по разделу "возможность поиска по тегам и тегу". Это означает, что вы можете создать поисковый набор для получения документов, помеченных тегом в разделе.

![Разделы с тегами в панели тегов](../media/Tagtypes.png)

Теги можно упорядочить, дополнив их вложение в раздел. Например, если предполагается определить и пометить привилегированный контент, можно использовать вложение, чтобы сделать так, чтобы пользователь мог пометить документ как "Привилегированный" и выбрать тип привилегий, проверив соответствующий вложенный тег.

![Вложенные теги в разделе тегов](../media/Nestingtags.png)

## <a name="applying-tags"></a>Применение тегов

Существует несколько способов применения тега к контенту.

### <a name="tagging-a-single-document"></a>Добавление тегов для одного документа

При просмотре документа в наборе рецензирования можно отобразить теги, которые может использовать проверка, щелкнув **панель маркировки**.

![Щелкните панель тегов, чтобы отобразить панель тегов](../media/Singledoctag.png)

Это позволит применить теги к документу, отображаемому в средстве просмотра.

### <a name="bulk-tagging"></a>Массовая маркировка

Массовое расстановку тегов можно выполнить, выбрав несколько файлов в сетке результатов, а затем используя теги на **панели маркировки** , как при разметке отдельных документов. Массовое снятие тегов можно выполнить, выбирая Теги дважды; При первом щелчке будет применен тег, а во втором выделенном фрагменте этот тег будет очищен для всех выбранных файлов.

![Снимок экрана с автоматическим созданием описания сотового телефона](../media/Bulktag.png)

> [!NOTE]
> При массовом разметке на панели маркировки отображается количество файлов, помеченных для каждого тега в панели.

### <a name="tagging-in-other-review-panels"></a>Добавление тегов в другие панели рецензирования

При просмотре документов можно использовать другие панели рецензирования для просмотра других характеристик документов в таблице результатов. Это включает проверку других связанных документов, почтовых потоков, ближайших дубликатов и хэш-дубликатов. Например, если вы просматриваете связанные документы (с помощью панели рецензирования **семейства документов** ), вы можете значительно сократить время проверки путем массового разметки связанных документов. Например, если сообщение электронной почты имеет несколько вложений и вы хотите обеспечить единообразное пометку всех семейств.

Например, вот как можно отобразить **панель расстановки тегов** при использовании панели "Обзор **семейства документов** ":

1. Откройте панель рецензирование для выбранного документа (например, при отображении списка связанных материалов в панели "Проверка **семейства документов** " щелкните элемент **теги документы** под панелью рецензирование семейства документов.

   Панель тегирования отображается в виде всплывающего окна.

2. Выберите один или несколько тегов, которые необходимо применить к выбранному документу. 

3. Чтобы отметить все документы, выберите все документы в области **семейство документов** , щелкните Теги **документы**, а затем выберите Теги, которые применяются ко всему семейству документов.

![Снимок экрана с автоматически созданным описанием записи социальных медиа](../media/Relatedtag.png)
