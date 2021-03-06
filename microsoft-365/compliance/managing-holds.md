---
title: Управление удержаниями в Advanced eDiscovery
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
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Сведения о том, как разместить удержания в custodians и их источниках данных, чтобы сохранить релевантный контент для вашего расширенного случая обнаружения электронных данных.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f56d12b6d69e56e85f0e7ad37fbf65746a1cff23
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024739"
---
# <a name="manage-holds-in-advanced-ediscovery"></a>Управление удержаниями в Advanced eDiscovery

Вы можете использовать расширенное дело eDiscovery для создания удержаний, чтобы сохранить содержимое, которое может быть релевантным для вашего случая. С помощью расширенных возможностей удержания обнаружения электронных данных можно размещать удержания в custodians и их источниках данных. Кроме того, для почтовых ящиков и сайтов OneDrive для бизнеса можно поместить не кустодиал удержание. Вы также можете поместить удержание на сайт группового почтового ящика, сайта SharePoint и сайта OneDrive для бизнеса для группы Microsoft 365. Аналогичным образом можно поместить удержание на почтовый ящик и сайт, связанные с Microsoft Teams. При помещении расположений контента в удержание содержимое сохраняется до тех пор, пока не будет освобождено хранитель, не будет удалено определенное расположение данных или полностью удалена политика удержания.

## <a name="manage-custodian-based-holds"></a>Управление удержаниями на основе хранитель

В некоторых случаях вы можете использовать набор custodians, который вы определили, и решили сохранить их данные в этом случае. При использовании расширенного обнаружения электронных данных, когда эти custodians помещаются на удержание, пользователь и их выбранные источники автоматически добавляются в политику сохранения хранитель.

Чтобы просмотреть политику хранения хранитель, выполните указанные ниже действия.

1. В центре соответствия требованиям Microsoft 365 щелкните **> обнаружения электронных** данных, чтобы отобразить список обращений в Организации.

2. Перейдите на вкладку **источники** , чтобы добавить custodians в вашем случае. Чтобы узнать, как добавлять и размещать custodians в расширенном случае обнаружения электронных данных, ознакомьтесь с [разделом Добавление custodians в дело](add-custodians-to-case.md). Если вы уже добавили custodians и поместили их в удержание, перейдите к шагу 3.

3. Перейдите на вкладку **удержания** и нажмите кнопку **кустодианхолд \<HoldId> **.

4. На всплывающей странице можно просмотреть статистику для политики. Вы также можете выполнять такие действия, как применение запроса к удержанию на основе хранитель. Для получения дополнительных сведений о создании запроса на удержание и использовании условий просмотрите [запросы ключевых слов и условия поиска контента](keyword-queries-and-search-conditions.md).

## <a name="manage-non-custodial-holds"></a>Управление удержаниями, отличными от кустодиал

При создании удержания вы можете использовать следующие параметры для определения области контента, который хранится в указанных расположениях контента:

- Вы создаете бесконечное удержание, в котором все содержимое размещается на удержании. Кроме того, вы можете создать удержание на основе запроса, в котором на удержание помещается только содержимое, соответствующее поисковому запросу.
  
- Вы можете указать диапазон дат, в течение которого будет храниться только содержимое, которое было отправлено, получено или создано в пределах этого диапазона дат. Кроме того, вы можете хранить все содержимое независимо от того, когда оно было отправлено, получено или создано.

Чтобы создать кустодиал удержание для расширенного случая обнаружения электронных данных, выполните указанные ниже действия.

1. В центре соответствия требованиям Microsoft 365 щелкните **> обнаружения электронных** данных, чтобы отобразить список обращений в Организации.
  
2. Нажмите кнопку **Открыть** рядом с тем случае, в котором нужно создать удержания.
  
3. На домашней странице для обращения перейдите на вкладку **удержания** .
  
4. На вкладке **удержания** нажмите кнопку **создать**.
  
5. На странице **имя хранения** укажите имя для удержания. Имя удержания должно быть уникальным в пределах организации.
 
6. Необязательно В поле **Описание** добавьте описание удержания.
  
7. Нажмите кнопку **Далее**.
  
8. Выберите расположения контента, которые необходимо разместить на удержании. Вы можете размещать почтовые ящики, сайты и общедоступные папки на удержании.

   1. **Электронная почта Exchange** : выберите пункт **Выбор пользователей, групп или команд** и снова нажмите кнопку **выбрать пользователей, группы или Teams** , чтобы указать почтовые ящики, которые необходимо разместить на удержании. Используйте поле поиска для поиска почтовых ящиков пользователей и групп рассылки (чтобы заблокировать почтовые ящики участников группы), чтобы разместить их на удержании. Вы также можете разместить удержание на связанном почтовом ящике для группы Microsoft 365 или группы Майкрософт. Установите флажок Пользователь, группа, группа, нажмите кнопку **выбрать**, а затем нажмите кнопку **Готово**.
 
      > [!NOTE]
      > При нажатии кнопки **выбрать пользователей, группы или Teams** для указания почтовых ящиков, которые будут храниться, отображается пустое средство выбора почтовых ящиков. Это вызвано мерами по повышению скорости работы. Чтобы добавить пользователей в этот список, введите в поле поиска имя (не менее 3 символов).

   1. **Сайты SharePoint** — нажмите кнопку **выбрать сайты** , а затем нажмите кнопку **выбрать сайты** еще раз, чтобы указать сайты SharePoint и OneDrive для бизнеса, которые необходимо разместить на удержании. Укажите URL-адрес каждого сайта, который вы хотите поставить на удержание. Вы также можете добавить URL-адрес сайта SharePoint для группы Microsoft 365 или группы Майкрософт. Нажмите кнопку **выбрать**, а затем кнопку **Готово**.
    
      Советы по размещению групп Microsoft 365 и Microsoft Teams на удержании можно найти в разделе **вопросы и ответы** .

      > [!NOTE]
      > URL-адрес учетной записи OneDrive пользователя содержит имя участника-пользователя (например, `https://alpinehouse-my.sharepoint.com/personal/sarad_alpinehouse_onmicrosoft_com` ). В редких случаях изменение имени участника-пользователя в OneDrive также изменится на включение нового имени участника-пользователя. Если учетная запись пользователя OneDrive входит в состав некустодиалного удержания и изменено имя участника-пользователя, необходимо обновить удержание и указать новый URL-адрес OneDrive. Дополнительные сведения см. в разделе [Как изменения UPN влияют на URL-адрес OneDrive](https://docs.microsoft.com/onedrive/upn-changes).

   1. **Общедоступные папки Exchange** — переместите переключатель в положение все, чтобы поместить все общедоступные папки в организации Exchange Online на удержание. Обратите внимание, что вы не можете выбрать определенные общедоступные папки, которые будут храниться. Если вы не хотите хранить данные в общедоступных папках, оставьте переключатель переключатель в **положение нет** .

9. Когда вы закончите Добавление расположений содержимого в удержание, нажмите кнопку **Далее**.
  
10. Чтобы создать удержание на основе запроса с условиями, выполните приведенные ниже условия. В противном случае просто нажмите кнопку **Далее**.
    
    - В поле **Ключевые слова**введите поисковый запрос в поле, чтобы на удержание поместилось только содержимое, соответствующее условиям поиска. Можно указать ключевые слова, свойства сообщений или свойства документа, например имена файлов. Кроме того, можно использовать более сложные запросы, которые используют логический оператор, например AND, OR и NOT. Если оставить поле ключевое слово пустым, то весь контент, расположенный в указанных расположениях контента, будет помещен на удержание.

    - Нажмите кнопку **Добавить** условия, чтобы добавить одно или несколько условий, чтобы сузить поисковый запрос для удержания. Каждое условие добавляет в запрос поиска KQL предложение, созданное и выполняемое при создании удержания. Например, вы можете указать диапазон дат, чтобы документы электронной почты или документы сайта, созданные в пределах даты, помещаются на удержание. Условие логически соединяется с запросом по ключевому слову (указанному в соответствующем поле) оператором AND. Это означает, что элементы должны удовлетворять как запрос ключевых слов, так и условие, которое должно быть включено в удержание.

     Для получения дополнительных сведений о создании поискового запроса и использовании условий просмотрите [запросы ключевых слов и условия поиска контента](https://docs.microsoft.com/office365/SecurityCompliance/keyword-queries-and-search-conditions).

11. После того как вы настраиваете удержание на основе запроса, нажмите кнопку **Далее**.

12. Проверьте параметры и нажмите кнопку **создать удержание**.

## <a name="view-hold-statistics"></a>Просмотр статистики хранения

Через некоторое время сведения о новом удержании отображаются в области сведений на вкладке **удержания** для выбранного удержания. Эта информация включает в себя количество почтовых ящиков и сайтов на удержании и статистику по содержимому, которое было включено в удержание, например общее число и размер элементов, включенных в удержание, а также время последнего расчета статистики удержания. Эти статистические данные помогают определить, какой объем содержимого, связанного с вариантом обнаружения электронных данных, было занято.

Имейте в виду следующие моменты, касающиеся сбора статистики хранения:

- Общее количество элементов на удержании указывает количество элементов из всех источников контента, размещаемых на удержании. Если вы создали удержание на основе запроса, эта статистика указывает количество элементов, которые совпадают с запросом.
  
- Количество элементов на удержании также включает неиндексированные элементы, найденные в расположениях содержимого. Обратите внимание, что если вы создаете удержание на основе запроса, все неиндексированные элементы в расположениях содержимого размещаются на удержании. Сюда входят неиндексированные элементы, которые не соответствуют критериям поиска для хранения на основе запроса и неиндексированных элементов, которые могут находиться за пределами диапазона дат. Это отличается от того, что происходит при выполнении поиска контента, если неиндексированные элементы, которые не отвечают поисковому запросу или исключены с помощью условия диапазона дат, не включаются в результаты поиска. Для получения дополнительных сведений о неиндексированных элементах просмотрите раздел " [частично индексированные элементы" в разделе Поиск контента в Office 365](partially-indexed-items-in-content-search.md). 

- Вы можете получить последнюю статистику хранения, нажав кнопку Обновить статистику, чтобы повторно выполнить оценку поиска, которая вычисляет текущее количество элементов на удержании.

- При необходимости нажмите кнопку Обновить на панели инструментов, чтобы обновить статистику удержания в области сведений.

- Обычно количество элементов на удержании увеличивается, так как пользователи, чьи почтовые ящики или сайты на удержании обычно отправляют и получают новые сообщения электронной почты, а также для создания документов SharePoint и OneDrive для бизнеса.

- Если сайт SharePoint или учетная запись OneDrive перемещаются в другой регион в среде с поддержкой нескольких регионов, статистика для этого сайта не будет включаться в статистику удержания. Однако контент сайта по-прежнему останется на удержании. Кроме того, если сайт перемещен в другой регион, URL-адрес, который отображается в удержании, не будет обновлен. Необходимо изменить удержание и обновить URL-адрес.

## <a name="place-a-hold-on-microsoft-teams-and-office-365-groups"></a>Помещение удержания в группы Microsoft Teams и Office 365

Microsoft Teams построен на базе группы Office 365. Таким образом, помещение на удержание на Advanced eDiscovery очень похоже. 

- **Как сопоставить дополнительные группы Microsoft 365 или сайт Microsoft Teams с хранитель? Как насчет размещения Кустодиал в группах Microsoft 365 и Microsoft Teams?** Microsoft Teams построен на основе групп Microsoft 365. Таким образом, помещение их на удержание в случае обнаружения электронных данных очень похоже. При помещении групп Microsoft 365 и Microsoft Teams в удержание учитывайте следующие моменты.
  - Чтобы поместить контент, размещенный в группах Microsoft 365 и Microsoft Teams, на удержании, необходимо указать почтовый ящик и сайт SharePoint, связанный с группой или командой.
  
  - Выполните командлет **Get-UnifiedGroup** в Exchange Online, чтобы просмотреть свойства группы Microsoft 365 или Microsoft Team. Это хороший способ получения URL-адреса для сайта, связанного с группой Microsoft 365 или группой Майкрософт. Например, следующая команда отображает выбранные свойства для группы Microsoft 365 с именем "Senior Leadership Team":


    ```console
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > Чтобы запустить командлет Get-UnifiedGroup, в Exchange Online вам должна быть назначена роль "получатели только для чтения" или вы должны входить в группу пользователей, которым она назначена.

 - При поиске в почтовом ящике пользователя не будет выполняться поиск всех групп Microsoft 365 или групп, участником которых является пользователь. Аналогично, когда вы помещаете группу Microsoft 365 или удержание группы Майкрософт, на удержание помещаются только почтовый ящик группы и сайт группы. почтовые ящики и сайты OneDrive для бизнеса участников группы не отправляются, пока вы не добавите их в качестве custodians или не поместили их источники данных. Таким образом, если вы хотите поместить группу Microsoft 365 или Microsoft Team для определенных хранитель, рассмотрите возможность сопоставления сайта группы и почтового ящика группы с Хранитель (см. Управление custodians в Advanced eDiscovery). Если группа Microsoft 365 или группа Майкрософт не соотнесена ни к одной хранитель, рассмотрите возможность добавления источника в кустодиал удержание. 
 
 - Чтобы получить список членов группы Microsoft 365 или группы Майкрософт, можно просмотреть свойства на странице "домашние > группы" в центре администрирования Microsoft 365. Или можно выполнить следующую команду в Exchange Online PowerShell:

   ```powershell
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > Чтобы запустить командлет **Get-UnifiedGroupLinks**, в Exchange Online вам должна быть назначена роль "получатели только для чтения" или вы должны входить в группу пользователей, которым она назначена.

- Каналы, входящие в канал Microsoft Teams, хранятся в почтовом ящике, связанном с командой. Файлы, которыми обмениваются участники команды, также сохраняются на сайте команды SharePoint. Поэтому для сохранения бесед и файлов в канале необходимо поместить почтовый ящик группы Майкрософт и сайт SharePoint на удержание.
  
- Кроме того, беседы, являющиеся частью списка чата в Microsoft Teams, хранятся в почтовом ящике пользователя, который участвует в чате.  Файлы, которые пользователь предоставляет в беседах беседы, хранятся на сайте OneDrive для бизнеса пользователя, который совместно использует файл. Таким образом, для сохранения бесед и файлов в списке чата необходимо поместить почтовые ящики пользователей и сайты OneDrive для бизнеса на удержание. 
  
- Каждая команда Майкрософт или канал группы содержит вики-сайт для заметок и совместной работы. Содержимое вики-сайта автоматически сохраняется в файле формата MHT. Этот файл хранится в библиотеке документов Teams Wiki Data на сайте команды в SharePoint. Вы можете поместить контент на вики-сайт на удержании, поместив на удержание сайт группы SharePoint.

  > [!NOTE]
  > Возможность сохранения контента вики-сайта для группы или канала группы Майкрософт (при помещении сайта SharePoint для группы в удержание) выпущен 22 июня 2017 г. Если сайт группы находится на удержании, контент Wiki будет храниться в этот день. Тем не менее, если сайт группы находится на удержании, а вики-контент был удален до 22 июня 2017, контент wiki не был сохранен.
