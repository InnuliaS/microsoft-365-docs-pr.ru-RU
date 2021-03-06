---
title: Поиск контента в основном случае обнаружения электронных данных
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
description: Можно выполнить поиск содержимого, которое может быть релевантным для основного случая обнаружения электронных данных.
ms.openlocfilehash: d17a9d16643ec9077e02b5438597237b80f09af5
ms.sourcegitcommit: 6007dbe2cf758c683de399f94023122c678bcada
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/14/2020
ms.locfileid: "44224626"
---
# <a name="search-for-content-in-a-core-ediscovery-case"></a>Поиск контента в основном случае обнаружения электронных данных

После создания основного случая обнаружения электронных данных и посторонних людей в случае помещается в удержание вы можете создать и выполнить один или несколько операций поиска для контента, относящегося к этому случаю. Поиск, связанный с основным вариантом обнаружения электронных данных, отсутствует в списке на странице " **Поиск контента** " в центре соответствия требованиям Microsoft 365. Эти операции поиска перечислены на странице " **поиски** " основного случая едисковер, с которыми связаны операции поиска. Это также означает, что операции поиска, связанные с обращением, доступны только для элементов case.

Чтобы создать основной поиск обнаружения электронных данных, выполните указанные ниже действия.
  
1. Перейдите на страницу [https://compliance.microsoft.com](https://compliance.microsoft.com) и войдите, используя учетные данные для учетной записи пользователя, которой были назначены соответствующие разрешения на обнаружение электронных данных.

2. В левой области навигации центра соответствия требованиям Microsoft 365 щелкните **Показать все**, а затем щелкните **ядро > обнаружения электронных**данных.

3. На странице " **основные обнаружения электронных** данных" выберите случай, в котором необходимо создать сопоставленный Поиск, а затем щелкните **открыть обращение**.

4. На **домашней** странице для обращения перейдите на вкладку **поиски** .
  
5. На странице **Поиск** нажмите кнопку **создать поиск**.

6. На странице **Новый поиск** можно добавить ключевые слова и условия для создания поискового запроса. 

    ![Новый поиск](../media/0e9954e7-c0ea-4e05-820b-e4b81dc5f81d.png)
  
   а) Вы можете указать ключевые слова, свойства сообщений, такие как даты отправки и получения, или свойства документа, такие как имена файлов или Дата последнего изменения документа. Можно использовать более сложные запросы, использующие логические операторы, такие как **and**, **or**, **Not**и **NEAR**. Кроме того, возможен поиск конфиденциальной информации (например, номера социального страхования) в документах или поиск документов, доступ к которым получали внешние пользователи. Если оставить поле ключевое слово пустым, в результаты поиска будут включены все содержимое, расположенное в указанных расположениях контента.

   б) Можно щелкнуть флажок **Показать список ключевых слов** и ввести ключевое слово в каждой строке. В этом случае ключевые слова в каждой строке будут соединены оператором **or** в созданном запросе поиска. В список можно ввести не более 20 ключевых слов.

    ![Список ключевых слов](../media/29cceb5d-2817-4fc4-b91a-ced1c5824a17.png)
  
    Зачем использовать список ключевых слов? Вы можете получить статистические сведения о том, сколько элементов соответствует каждому ключевому слову. Это поможет быстро определить, какие ключевые слова наиболее (и наименее) эффективны. В строке можно также использовать ключевую фразу (в скобках). Дополнительные сведения о статистике поиска см. в статье [Просмотр статистики ключевых слов для результатов поиска контента](view-keyword-statistics-for-content-search.md).

    Для получения дополнительных сведений об использовании списка "Ключевые слова", ознакомьтесь со статьей [Создание поискового запроса](content-search.md#building-a-search-query).

   в. Вы можете щелкнуть **условия** и добавить условия в поисковый запрос, чтобы сузить поиск и получить более уточненный набор результатов. Каждое условие добавляет выражение к создаваемому поисковому запросу KQL, который запускается, когда вы начинаете поиск. Условие логически связано с запросом по ключевым словам, указанном в поле для ввода ключевых слов, с помощью оператора **AND**. Это означает, что элементы должны удовлетворять как запрос ключевых слов, так и все условия, включаемые в результаты. Таким образом условия помогают сузить область результатов поиска.

    Дополнительные сведения о создании поисковых запросов и использовании условий см. в статье [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).

7. В разделе **расположения: расположения на удержании**выберите расположения контента, которые требуется найти. Поиск можно выполнять в почтовых ящиках, сайтах и общедоступных папках.

    ![Расположения, расположения на удержании](../media/d56398aa-0b20-4500-8e26-494eab92a99f.png)
  
    - **Все расположения**. Выберите этот параметр для поиска всех расположений контента в Организации. При выборе этого параметра можно выбрать поиск во всех почтовых ящиках Exchange (включая почтовые ящики для всех групп Microsoft Teams, Yammer и Office 365), всех сайтов SharePoint и OneDrive для бизнеса (включающих сайты для всех групп Microsoft Teams, Yammer и Office 365) и всех общедоступных папок.
    
    - **Все расположения на удержании**. Выберите этот параметр, чтобы выполнить поиск по всем расположениям контента, включенных в удержание eDiscovery в случае обнаружения электронных данных. Если регистр содержит несколько удержаний, будет выполнен поиск расположений контента из всех удержаний. Кроме того, если расположение содержимого было размещено на удержании на основе запроса, при выполнении поиска контента, созданного на этом этапе, будет выполняться поиск только элементов, находящихся на удержании. Например, если пользователь поместился на удержание на основе запроса, в котором сохраняются элементы, отправленные или созданные до определенной даты, поиск будет выполнен только для этих элементов. Это достигается путем подключения запроса на удержание дел и поискового запроса к содержимому с помощью оператора **и** . Дополнительные сведения [см.](create-ediscovery-holds.md#search-locations-on-ediscovery-hold)
    
    - **Определенных расположениях**. Выберите этот параметр, чтобы выбрать почтовые ящики и сайты, в которых вы хотите выполнить поиск. При выборе этого параметра и нажатии кнопки **изменить**отображается список расположений. Можно выбрать поиск всех или всех пользователей, групп, групп или расположений сайтов. Кроме того, можно искать в общедоступных папках в Организации.
    
      ![Выбор определенных расположений](../media/97469b15-7be1-4aee-be27-f8343636152c.png)
  
     При выборе этого параметра и поиске содержимого, расположенного на удержании, любой запрос из регистра на основе запроса не будет применен к поисковому запросу. Другими словами, выполняется поиск по всему содержимому, а не только к содержимому, которое сохраняется с учетом регистра на основе запроса.

8. Выбрав расположения контента для поиска, нажмите кнопку Done ( **Готово** ), а затем **сохранить**.

9. На странице **Новый поиск** нажмите кнопку **сохранить & выполнить** , а затем введите имя для поиска. При поиске, связанном с основным вариантом обнаружения электронных данных, имена должны быть уникальными в пределах организации Office 365.

10. Нажмите кнопку **сохранить** , чтобы сохранить параметры поиска и начать поиск.

  После завершения поиска можно просмотреть его результаты. При необходимости нажмите кнопку **Обновить** на странице " **поиски** ", чтобы отобразить Поиск, созданный в списке.

11. Щелкните Поиск, чтобы отобразить всплывающую страницу, содержащую статистику поиска и выполнения других задач, таких как просмотр статистики поиска и экспорт результатов поиска.

## <a name="more-information-about-searching-content-locations"></a>Дополнительные сведения о поиске в расположениях контента

- Если нажать кнопку **выбрать пользователей, группы или Teams** , чтобы указать почтовые ящики для поиска, отображается пустое средство выбора почтовых ящиков. Это вызвано мерами по повышению скорости работы. Чтобы добавить получателей в этот список, щелкните **Выбор пользователей, групп или групп**, введите имя (не менее 3 символов) в поле поиска, установите флажок рядом с именем и нажмите кнопку **выбрать**.

- Можно добавить Неактивные почтовые ящики, Microsoft Teams, группы Yammer, группы Office 365 и группы рассылки в список почтовых ящиков, в которых выполняется поиск. Динамические группы рассылки не поддерживаются. Если вы добавляете Microsoft Teams, группы Yammer или группы Office 365, выполняется поиск группы или почтового ящика группы. не выполняется поиск почтовых ящиков членов группы.

- Чтобы добавить сайты, нажмите кнопку **выбрать сайты**, еще раз нажмите кнопку **выбрать сайты** , а затем введите URL-адрес для каждого сайта, который требуется найти. Вы также можете добавить URL-адрес сайта SharePoint для группы Майкрософт, группы Yammer или группы Office 365.
