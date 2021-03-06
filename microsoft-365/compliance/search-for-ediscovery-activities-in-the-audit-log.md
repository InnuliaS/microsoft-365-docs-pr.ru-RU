---
title: Поиск действий по обнаружению электронных данных в журнале аудита
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: Узнайте, какие события заносятся в журнал, когда пользователи, которым назначены разрешения eDiscovery, выполняют поиск контента и основные задачи обнаружения электронных данных в центре безопасности & соответствия требованиям.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 671fdebd75dfdaaf09deebf320b9fe4cfab0ca1c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818878"
---
# <a name="search-for-ediscovery-activities-in-the-audit-log"></a>Поиск действий по обнаружению электронных данных в журнале аудита

Операции поиска контента и обнаружения электронных данных (для базовых электронных данных и расширенных средств обнаружения электронных данных), выполняемые в центре безопасности & соответствия требованиям или запуска соответствующих командлетов PowerShell, записываются в журнал аудита. События записываются в журнал, когда Администраторы или менеджеры eDiscovery (или разрешения обнаружения электронных данных) выполняют следующие задачи поиска контента и обнаружения электронных данных в центре безопасности & соответствия требованиям:
  
- Создание и управление основными и расширенными случаями обнаружения электронных данных

- создание, запуск и редактирование операций поиска контента;

- выполнение действий поиска контента, таких как предварительный просмотр, экспорт и удаление результатов поиска;

- Управление custodians и обзор наборов в Advanced eDiscovery

- настройка фильтрации разрешений для поиска контента;

- управление ролью администратора обнаружения электронных данных.

> [!IMPORTANT]
> Действия, описанные в этой статье, относятся только к результату выполнения задач обнаружения электронных данных с помощью центра безопасности & соответствия требованиям. задачи обнаружения электронных данных, которые выполнялись с помощью средства обнаружения электронных данных на месте в Exchange Online или центра обнаружения электронных данных в SharePoint Online, не включаются. 
  
Дополнительные сведения о поиске в журнале аудита, необходимых разрешениях и экспорте результатов поиска можно найти в статье [Поиск в журнале аудита в центре безопасности & соответствия требованиям](search-the-audit-log-in-security-and-compliance.md).
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>Поиск и Просмотр действий обнаружения электронных данных

В настоящее время для просмотра действий обнаружения электронных данных в журнале аудита необходимо выполнить несколько определенных действий. Ниже приведено описание процедуры.
  
1. Перейдите по ссылке [https://protection.office.com](https://protection.office.com).

2. Выполните вход с помощью рабочей или учебной учетной записи.

3. В области слева щелкните **Поиск**, а затем щелкните Поиск в **журнале аудита**.

4. В раскрывающемся списке **действия** в разделе **действия обнаружения электронных** данных или **Расширенные действия eDiscovery**выберите одно или несколько действий для поиска.

    > [!NOTE]
    > Раскрывающийся список " **действия** " также включает группу действий, именуемых **действиями командлетов обнаружения электронных** данных, которые будут возвращать записи из журнала аудита командлетов.
  
5. Выберите диапазон дат и времени для отображения событий обнаружения электронных данных, произошедших в течение этого периода. 

6. В поле **Пользователи** выберите одного или нескольких пользователей, для которых отобразятся результаты поиска. Оставьте это поле пустым, чтобы вернуть записи для всех пользователей.

7. Чтобы выполнить поиск по указанным условиям, нажмите кнопку **Поиск**. 

8. После отображения результатов поиска можно нажать кнопку **фильтровать результаты** , чтобы отфильтровать или отсортировать полученные записи об активности. К сожалению, вы не можете использовать фильтрацию для явного исключения определенных действий. 

9. Чтобы просмотреть сведения о действии, щелкните запись Activity (действие) в списке результатов поиска. 

    Отображается страница выпадающего **сведений** , содержащая подробные свойства из записи события. Чтобы отобразить дополнительные сведения, нажмите кнопку **Дополнительные сведения**. Описание этих свойств приведено в разделе [подробные свойства для действий обнаружения электронных](#detailed-properties-for-ediscovery-activities) данных.

10. При необходимости вы можете экспортировать результаты поиска журнала аудита в CSV-файл, а затем с помощью функции Power Query в Excel отформатировать и отфильтровать эти записи. Дополнительные сведения см. в статье [Экспорт, настройка и просмотр записей журнала аудита](export-view-audit-log-records.md).

## <a name="ediscovery-activities"></a>Действия, связанные с обнаружением электронных данных

В следующей таблице описаны действия поиска и обнаружения контента, регистрируемые в журнале, когда администратор или диспетчер eDiscovery выполняет действия, связанные с eDiscovery, с помощью центра безопасности & соответствия требованиям или запуска соответствующего командлета в оболочке безопасности & центра соответствия требованиям. Кроме того, обратите внимание, что при поиске действий в этом списке будут возвращаться некоторые действия, выполненные в Advanced.
  
> [!NOTE]
> Действия обнаружения электронных данных, описанные в этом разделе, содержат похожие сведения о действиях командлетов обнаружения электронных данных, описанных в следующем разделе. Мы рекомендуем использовать действия обнаружения электронных данных, описанные в этом разделе, так как они будут отображаться в результатах поиска журнала аудита в течение 30 минут. Действия командлетов обнаружения электронных данных, которые будут отображаться в результатах поиска журнала аудита, занимают до 24 часов. 
  
|**Понятное имя**|**Операция**|**Соответствующий командлет**|**Описание**|
|:-----|:-----|:-----|:-----|
|Добавлен элемент для случая обнаружения электронных данных  <br/> |касемембераддед  <br/> |Add — Комплианцекасемембер  <br/> |Пользователь добавлен в качестве участника дела eDiscovery. В качестве участника сценария пользователь может выполнять различные задачи, связанные с учетом регистра, в зависимости от того, назначены ли им необходимые разрешения.  <br/> |
|Изменение поиска контента  <br/> |сеарчупдатед  <br/> |Set-ComplianceSearch  <br/> |Изменен существующий поиск контента. Изменения могут включать добавление или Удаление расположений контента или изменение поискового запроса.  <br/> |
|Изменение членства администратора обнаружения электронных данных  <br/> |касеадминупдатед  <br/> |Update — Едисковерикасеадмин  <br/> |Изменен список администраторов обнаружения электронных данных в Организации. Это действие регистрируется, когда список администраторов обнаружения электронных данных заменяется группой новых пользователей. Если добавляется или удаляется один пользователь, операция Касеадминаддед записывается в журнал.  <br/> |
|Измененное дело обнаружения электронных данных  <br/> |касеупдатед  <br/> |Set — ComplianceCase  <br/> |Изменено место обнаружения электронных данных. Изменения включают Закрытие открытого обращения или повторное открытие закрытого дела.  <br/> |
|Измененное членство в делах обнаружения электронных данных  <br/> |касемемберупдатед  <br/> |Update — Комплианцекасемембер  <br/> |Изменен список членов для случая обнаружения электронных данных. Это действие регистрируется, когда все члены заменяются группой новых пользователей. Если добавляется или удаляется один участник, операция Касемембераддед или Касемемберремовед записывается в журнал.  <br/> |
|Измененный фильтр разрешений поиска  <br/> |сеарчпермиссионупдатед  <br/> |Set — ComplianceSecurityFilter  <br/> |Изменен фильтр разрешений на поиск.  <br/> |
|Измененный поисковый запрос для хранения дел обнаружения электронных данных  <br/> |холдупдатед  <br/> |Set — Caseholdrule позволяет  <br/> |Было изменено удержание на основе запроса, связанное с вариантом обнаружения электронных данных. Возможные изменения включают изменение запроса или диапазона дат для удержания на основе запроса.  <br/> |
|Загруженный элемент предварительного просмотра поиска контента  <br/> |превиевитемдовнлоадед  <br/> |Недоступно  <br/> |Пользователь загрузил элемент на локальный компьютер (щелкнув ссылку **загрузить исходный элемент** ) при просмотре результатов поиска.  <br/> |
|Элемент предварительный просмотр поиска контента в списке  <br/> |превиевитемлистед  <br/> |Недоступно  <br/> |Пользователь настроил **Предварительный просмотр результатов поиска** для отображения страницы "Просмотр результатов поиска", в которой перечислены до 1000 элементов из результатов поиска контента.  <br/> |
|Просмотренный элемент предварительного просмотра поиска контента  <br/> |превиевитемрендеред  <br/> |Недоступно  <br/> |Диспетчер обнаружения электронных данных просматривает элемент, щелкая его при предварительном просмотре результатов поиска.  <br/> |
|Создан поиск контента  <br/> |сеарчкреатед  <br/> |New-ComplianceSearch  <br/> |Создан новый поиск контента.  <br/> |
|Администратор обнаружения электронных данных создан  <br/> |касеадминаддед  <br/> |Add — Едисковерикасеадмин  <br/> |Пользователь добавлен в качестве администратора обнаружения электронных данных в Организации.  <br/> |
|Созданное дело обнаружения электронных данных  <br/> |касеаддед  <br/> |New — ComplianceCase  <br/> |Создана ситуация обнаружения электронных данных. При создании обращения ему необходимо присвоить имя. Другие задачи, связанные с делами, такие как добавление элементов, создание удержаний и создание операций поиска контента, связанных с этим случаем, в журнал записываются дополнительные события.  <br/> |
|Создан фильтр разрешений поиска  <br/> |сеарчпермиссионкреатед  <br/> |New — ComplianceSecurityFilter  <br/> |Создан фильтр разрешений поиска.  <br/> |
|Создан поисковый запрос для хранения дел обнаружения электронных данных  <br/> |холдкреатед  <br/> |New — Caseholdrule позволяет  <br/> |Было создано удержание на основе запроса, связанное с вариантом обнаружения электронных данных.  <br/> |
|Поиск по удаленному содержимому  <br/> |сеарчремовед  <br/> |Remove-ComplianceSearch  <br/> |Был удален существующий поиск контента.  <br/> |
|Удаленный администратор обнаружения электронных данных  <br/> |касеадминремовед  <br/> |Remove — Едисковерикасеадмин  <br/> |Администратор обнаружения электронных данных был удален из вашей организации.  <br/> |
|Удаленное дело обнаружения электронных данных  <br/> |касеремовед  <br/> |Remove — ComplianceCase  <br/> |Удалено дело обнаружения электронных данных. Все удержания, связанные с делами, необходимо удалить, прежде чем можно будет удалить обращение.  <br/> |
|Фильтр "разрешения поиска удален"  <br/> |сеарчпермиссионремовед  <br/> |Remove — ComplianceSecurityFilter  <br/> |Удален фильтр разрешений на поиск.  <br/> |
|Удален поисковый запрос для хранения дел обнаружения электронных данных  <br/> |холдремовед  <br/> |Remove — Caseholdrule позволяет  <br/> |Удалено удержание на основе запроса, связанное с вариантом обнаружения электронных данных. Удаление запроса из удержания часто приводит к результату удаления удержания. При удалении запроса на удержание или удержание отправляются расположенные на удержании расположения контента.  <br/> |
|Скачанный экспорт поиска контента  <br/> |сеарчекспортдовнлоадед  <br/> |Недоступно  <br/> |Пользователь загрузил результаты поиска контента на локальный компьютер. **Начат экспорт действий по поиску контента** , прежде чем можно будет скачать результаты поиска.  <br/> |
|Предварительный просмотр результатов поиска контента  <br/> |сеарчпревиевед  <br/> |Недоступно  <br/> |Пользователь просматривает результаты поиска контента.  <br/> |
|Очищенные результаты поиска контента  <br/> |сеарчресултспуржед  <br/> |New — ComplianceSearchAction  <br/> |Пользователь отComplianceSearchAction результаты поиска контента, выполнив команду **New – – unуничтожать** .  <br/> |
|Удаленный анализ поиска контента  <br/> |ремоведсеарчресултссенттозум  <br/> |Remove — ComplianceSearchAction  <br/> |Удалено действие подготовки к поиску контента (для подготовки результатов поиска для расширенного обнаружения электронных данных). Если для подготовительных действий было задано менее двух недель, результаты поиска, подготовленные для расширенного обнаружения электронных данных, были удалены из области хранилища Microsoft Azure. Если действие подготовки старше 2 недель, то это событие указывает на то, что было удалено только соответствующее действие подготовки.  <br/> |
|Удален экспорт поиска контента  <br/> |ремоведсеарчекспортед  <br/> |Remove — ComplianceSearchAction  <br/> |Удалено действие экспорта поиска контента. Если действие экспорта было менее двух недель, результаты поиска, отправленные в область хранилища Microsoft Azure, были удалены. Если действие экспорта старше 2 недель, то это событие указывает на то, что было удалено только соответствующее действие экспорта.  <br/> |
|Элемент из случая обнаружения электронных данных удален  <br/> |касемемберремовед  <br/> |Remove — Комплианцекасемембер  <br/> |Пользователь был удален в качестве участника дела eDiscovery.  <br/> |
|Удалены предварительные результаты поиска контента  <br/> |ремоведсеарчпревиевед  <br/> |Remove — ComplianceSearchAction  <br/> |Было удалено действие предварительный просмотр поиска контента.  <br/> |
|Удалено действие по очистке, выполняемое при поиске контента  <br/> |ремоведсеарчресултспуржед  <br/> |Remove — ComplianceSearchAction  <br/> |Удалено действие по очистке поиска контента.  <br/> |
|Удален отчет о поиске  <br/> |сеарчрепортремовед  <br/> |Remove — ComplianceSearchAction  <br/> |Удалено действие с отчетом по экспорту контента для поиска контента.  <br/> |
|Начат анализ поиска контента  <br/> |сеарчресултссенттозум  <br/> |New — ComplianceSearchAction  <br/> |Результаты поиска контента были подготовлены для анализа в Advanced eDiscovery.  <br/> |
|Начат поиск контента  <br/> |сеарчстартед  <br/> |Start-ComplianceSearch  <br/> |Начат поиск контента. При создании или изменении поиска контента с помощью графического интерфейса центра & безопасности центра соответствия требованиям, поиск автоматически запускается. При создании или изменении поиска с помощью командлета **New – ComplianceSearch** или **Set – ComplianceSearch** необходимо запустить командлет **Start – ComplianceSearch** , чтобы начать поиск.  <br/> |
|Начат экспорт поиска контента  <br/> |сеарчекспортед  <br/> |New — ComplianceSearchAction  <br/> |Пользователь экспортировал результаты поиска контента.  <br/> |
|Начат экспорт отчета  <br/> |сеарчрепорт  <br/> |New — ComplianceSearchAction  <br/> |Пользователь экспортировал отчет о поиске контента.  <br/> |
|Остановлен поиск контента  <br/> |сеарчстоппед  <br/> |Stop-ComplianceSearch  <br/> |Пользователь остановил поиск контента.  <br/> |
|(нет)|касевиевед|Get — ComplianceCase|Пользователь просматривал список обращений на странице **обнаружения электронных** данных в центре безопасности и соответствия требованиям или выполнив командлет.|
|(нет)|сеарчвиевед|Get-ComplianceSearch|Пользователь просматривал список на поиск контента (указанный на вкладке **поиски** ) в центре безопасности и соответствия требованиям или путем запуска командлета. Это действие также заносится в журнал, когда пользователь просматривает список операций поиска контента, связанных с вариантом обнаружения электронных данных (при щелчке вкладки **Поиск** ) или при выполнении команды **Get-ComplianceSearch-Case** .|
|(нет)|виеведсеарчекспортед|Get – ComplianceSearchAction — Export|Пользователь просматривал список заданий экспорта поиска контента (указанный на вкладке **экспорты** ) в центре безопасности и соответствия требованиям или путем запуска командлета. Это действие также регистрируется, когда пользователь просматривает список заданий экспорта в случае обнаружения электронных данных (указан на вкладке " **Экспорт** ") или с помощью команды **Get-ComplianceSearchAction-Case-Export** .|
|(нет)|виеведсеарчпревиевед|Get – ComplianceSearchAction — Предварительная версия|Пользователь предварительно просматривает результаты поиска контента в центре безопасности и соответствия требованиям или с помощью командлета.|
|||||
  
## <a name="advanced-ediscovery-activities"></a>Действия, связанные с Advanced eDiscovery

В следующей таблице описаны расширенные операции обнаружения электронных данных, регистрируемые в журнале аудита. Эти действия (в дополнение к соответствующим действиям обнаружения электронных данных) можно использовать для отслеживания хода активности в расширенном случае обнаружения электронных данных.

|**Понятное имя**|**Операция**|**Описание**|
|:-----|:-----|:-----|
|Добавлены данные в другой набор для проверки|AddWorkingSetQueryToWorkingSet|Пользователь добавил документы из одного набора для проверки в другой.|
|Добавлены данные в набор для проверки|AddQueryToWorkingSet|Пользователь добавил результаты поиска из средства поиска контента, связанные с делом Advanced eDiscovery, в набор для проверки.|
|Добавлены данные Microsoft 365 для просмотра.|AddNonOffice365DataToWorkingSet|Пользователь добавил данные Microsoft 365 в набор обзоров.|
|Добавлены исправленные документы в набор для проверки|AddRemediatedData|Пользователь отправляет документы с ошибками индексирования, исправленными для набора проверки.|
|Проанализированы данные в наборе для проверки|RunAlgo|Пользователь провел анализ документов в наборе для проверки.|
|К документу в наборе для проверки добавлены заметки|AnnotateDocument|Пользователь добавил заметки к документу в наборе для проверки. Добавление заметок включает правку содержимого в документе.|
|Сравнены загруженные наборы|LoadComparisonJob|Пользователь сравнил два разных загруженных набора в наборе для проверки. Загруженный набор — это добавление в набор для проверки данных из средства поиска контента, связанных с делом.|
|Преобразованы документы со сделанными купюрами в PDF|BurnJob|Пользователь преобразует все документы с купюрами в наборе для проверки в PDF-файлы.|
|Создан набор для проверки|CreateWorkingSet|Пользователь создал набор для проверки.|
|Создан поиск в наборе для проверки|CreateWorkingSetSearch|Пользователь создал поисковый запрос, выполняющий поиск документов в наборе для проверки.|
|Создан тег|CreateTag|Пользователь создал группу тегов в наборе для проверки. Группа тегов может содержать один или несколько дочерних тегов. Эти теги затем используются для пометки документов в наборе для проверки.|
|Удален поиск в наборе для проверки|DeleteWorkingSetSearch|Пользователь удалил поисковый запрос в наборе для проверки.|
|Удален тег|DeleteTag|Пользователь удалил тег или группу тегов в наборе для проверки.|
|Скачан документ|DownloadDocument|Пользователь скачал документ из набора для проверки.|
|Изменен тег|UpdateTag|Пользователь изменил тег в наборе для проверки.|
|Экспортированы документы из набора для проверки|ExportJob|Пользователь экспортировал документы из набора для проверки.|
|Изменены параметры дела|UpdateCaseSettings|Пользователь изменил параметры дела. Параметры дела включают сведения о деле, разрешения на доступ и параметры, управляющие поведением поиска и анализа.|
|Изменен поиск в наборе для проверки|UpdateWorkingSetSearch|Пользователь изменил поисковый запрос в наборе для проверки.|
|Предварительно просмотрен поиск в наборе для проверки|PreviewWorkingSetSearch|Пользователь предварительно просмотрел результаты поискового запроса в наборе для проверки.|
|Исправлены документы с ошибками|ErrorRemediationJob|Пользователь исправляет файлы, содержащие ошибки индексирования.|
|Документ помечен тегом|TagFiles|Пользователь пометил тегом документ в наборе для проверки.|
|Результаты запроса помечены тегом|TagJob|Пользователь помечает все документы, удовлетворяющие условиям поискового запроса в наборе для проверки.|
|Просмотрен документ в наборе для проверки|ViewDocument|Пользователь просмотрел документ в наборе для проверки.|
|||

## <a name="ediscovery-cmdlet-activities"></a>действия командлетов обнаружения электронных данных

В следующей таблице перечислены записи журнала аудита командлетов, которые записываются в журнал, когда администратор или пользователь выполняет действия, связанные с обнаружением электронных данных, с помощью центра безопасности & соответствия требованиям или запуска соответствующего командлета в удаленной оболочке PowerShell, подключенного к центру безопасности & соответствия требованиям вашей организации. Подробные сведения в записи журнала аудита различаются для действий командлетов, перечисленных в этой таблице, и действий обнаружения электронных данных, описанных в предыдущем разделе.
  
Как отмечалось выше, действия командлетов обнаружения электронных данных в результатах поиска в журнале аудита занимают до 24 часов.
  
> [!TIP]
> Командлеты в столбце " **Операция** " в следующей таблице связаны с соответствующим разделом справки по командлетам на сайте TechNet. Перейдите к разделу Справка по командлетам, чтобы получить описание доступных параметров для каждого командлета. Параметр и значение параметра, которые использовались с командлетом, включаются в запись журнала аудита для каждого действия командлетов обнаружения электронных данных, регистрируемого в журнале. 
  
|**Понятное имя**|**Операция (командлет)**|**Описание**|
|:-----|:-----|:-----|
|Создание удержания в случае обнаружения электронных данных  <br/> |[New — Caseholdpolicy позволяет](https://go.microsoft.com/fwlink/p/?LinkId=823813) <br/> |Для случая обнаружения электронных данных было создано удержание. Удержание можно создать с указанием источника контента или без него. Если источники контента указаны, они будут идентифицированы в записи журнала аудита.  <br/> |
|Удалено удержание из случая обнаружения электронных данных  <br/> |[Remove — Caseholdpolicy позволяет](https://go.microsoft.com/fwlink/p/?LinkId=823814) <br/> |Было удалено удержание, связанное с вариантом обнаружения электронных данных. При удалении удержания из удержания освобождаются все расположения контента. Удаление удержания также приведет к удалению правил удержания для удержания, связанных с удержанием (см. **Remove-caseholdrule позволяет** ниже).  <br/> |
|Изменено удержание в случае обнаружения электронных данных  <br/> |[Set — Caseholdpolicy позволяет](https://go.microsoft.com/fwlink/p/?LinkId=823815) <br/> |Было изменено удержание, связанное с обнаружением электронных данных. Возможные изменения включают добавление или Удаление расположений контента или отключение удержания (отключение).  <br/> |
|Создан поисковый запрос для хранения дел обнаружения электронных данных  <br/> |[New — Caseholdrule позволяет](https://go.microsoft.com/fwlink/p/?LinkId=823816) <br/> |Было создано удержание на основе запроса, связанное с вариантом обнаружения электронных данных.  <br/> |
|Удален поисковый запрос для хранения дел обнаружения электронных данных  <br/> |[Remove — Caseholdrule позволяет](https://go.microsoft.com/fwlink/p/?LinkId=823820) <br/> |Удалено удержание на основе запроса, связанное с вариантом обнаружения электронных данных. Удаление запроса из удержания часто приводит к результату удаления удержания. При удалении запроса на удержание или удержание отправляются расположенные на удержании расположения контента.  <br/> |
|Измененный поисковый запрос для хранения дел обнаружения электронных данных  <br/> |[Set — Caseholdrule позволяет](https://go.microsoft.com/fwlink/p/?LinkId=823819) <br/> |Было изменено удержание на основе запроса, связанное с вариантом обнаружения электронных данных. Возможные изменения включают изменение запроса или диапазона дат для удержания на основе запроса.  <br/> |
|Созданное дело обнаружения электронных данных  <br/> |[New — ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823842) <br/> |Создана ситуация обнаружения электронных данных. При создании обращения ему необходимо присвоить имя. Другие задачи, связанные с делами, такие как добавление элементов, создание удержаний и создание операций поиска контента, связанных с этим случаем, в журнал записываются дополнительные события.  <br/> |
|Удаленное дело обнаружения электронных данных  <br/> |[Remove — ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823844) <br/> |Удалено дело обнаружения электронных данных. Все удержания, связанные с делами, необходимо удалить, прежде чем можно будет удалить обращение.  <br/> |
|Измененное дело обнаружения электронных данных  <br/> |[Set — ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823846) <br/> |Изменено место обнаружения электронных данных. Изменения включают Закрытие открытого обращения или повторное открытие закрытого дела.  <br/> |
|Добавлен элемент для случая обнаружения электронных данных  <br/> |[Add — Комплианцекасемембер](https://go.microsoft.com/fwlink/p/?LinkId=823848) <br/> |Пользователь добавлен в качестве участника дела eDiscovery. В качестве участника сценария пользователь может выполнять различные задачи, связанные с учетом регистра, в зависимости от того, назначены ли им необходимые разрешения.  <br/> |
|Элемент из случая обнаружения электронных данных удален  <br/> |[Remove — Комплианцекасемембер](https://go.microsoft.com/fwlink/p/?LinkId=823849) <br/> |Пользователь был удален в качестве участника дела eDiscovery.  <br/> |
|Измененное членство в делах обнаружения электронных данных  <br/> |[Update — Комплианцекасемембер](https://go.microsoft.com/fwlink/p/?LinkId=823850) <br/> |Изменен список членов для случая обнаружения электронных данных. Это действие регистрируется, когда все члены заменяются группой новых пользователей. При добавлении или удалении одного члена в журнал записывается операция **Add-комплианцекасемембер** или **Remove-комплианцекасемембер** .  <br/> |
|Создан поиск контента  <br/> |[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935) <br/> |Создан новый поиск контента.  <br/> |
|Поиск по удаленному содержимому  <br/> |[Remove-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517936) <br/> |Был удален существующий поиск контента.  <br/> |
|Изменение поиска контента  <br/> |[Set-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517937) <br/> |Изменен существующий поиск контента. Изменения могут включать в себя добавление или Удаление расположений контента, в которых выполняется поиск и редактирование поискового запроса.  <br/> |
|Начат поиск контента  <br/> |[Start-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517938) <br/> |Начат поиск контента. При создании или изменении поиска контента с помощью графического интерфейса центра & безопасности центра соответствия требованиям, поиск автоматически запускается. При создании или изменении поиска с помощью командлета **New – ComplianceSearch** или **Set – ComplianceSearch** необходимо запустить командлет **Start – ComplianceSearch** , чтобы начать поиск.  <br/> |
|Остановлен поиск контента  <br/> |[Stop-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517939) <br/> |Запущенный поиск контента был остановлен.  <br/> |
|Созданное действие поиска контента  <br/> |[New — ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=527971) <br/> |Создано действие поиска контента. Действия по поиску контента включают предварительный просмотр результатов поиска, экспорт результатов поиска, подготовку результатов поиска для анализа в Advanced eDiscovery и окончательное удаление элементов, которые отвечают условиям поиска контента.  <br/> |
|Действие по удалению поиска контента  <br/> |[Remove — ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=824027) <br/> |Было удалено действие поиска контента.  <br/> |
|Создан фильтр разрешений поиска  <br/> |[New — ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617542) <br/> |Создан фильтр разрешений поиска.  <br/> |
|Фильтр "разрешения поиска удален"  <br/> |[Remove — ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617543) <br/> |Удален фильтр разрешений на поиск.  <br/> |
|Измененный фильтр разрешений поиска  <br/> |[Set — ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617544) <br/> |Изменен фильтр разрешений на поиск.  <br/> |
|Администратор обнаружения электронных данных создан  <br/> |[Add — Едисковерикасеадмин](https://go.microsoft.com/fwlink/p/?LinkId=798217) <br/> |Пользователь добавлен в качестве администратора обнаружения электронных данных в Организации.  <br/> |
|Удаленный администратор обнаружения электронных данных  <br/> |[Remove — Едисковерикасеадмин](https://go.microsoft.com/fwlink/p/?LinkId=823945) <br/> |Администратор обнаружения электронных данных был удален из вашей организации.  <br/> |
|Изменение членства администратора обнаружения электронных данных  <br/> |[Update — Едисковерикасеадмин](https://go.microsoft.com/fwlink/p/?LinkId=823946) <br/> |Изменен список администраторов обнаружения электронных данных в Организации. Это действие регистрируется, когда список администраторов обнаружения электронных данных заменяется группой новых пользователей. Если добавляется или удаляется один пользователь, операция **Add-едисковерикасеадмин** или **Remove-едисковерикасеадмин** записывается в журнал.  <br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>Подробные свойства для действий обнаружения электронных данных

В следующей таблице описываются свойства, которые включаются при нажатии кнопки **Дополнительные сведения** на странице **сведений** о действиях eDiscovery, перечисленных в результатах поиска. Эти свойства также включаются в CSV-файл при экспорте результатов поиска в журнале аудита. Запись журнала аудита для действия eDiscovery не включает все подробные свойства, перечисленные ниже. 
  
> [!TIP]
> При экспорте результатов поиска CSV-файл содержит столбец **detail**, который содержит подробные свойства, описанные в следующей таблице, в многозначном свойстве. Вы можете использовать функцию Power Query в Excel, чтобы разделить этот столбец на несколько столбцов, чтобы каждое свойство было иметь собственный столбец. Это позволит сортировать и фильтровать по одному или нескольким из этих свойств. Дополнительные сведения можно найти в разделе "Экспорт результатов поиска в файл" в разделе [Поиск в журнале аудита](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file). 
  
|**Свойство**|**Описание**|
|:-----|:-----|
|Ситуация  <br/> |Идентификатор GUID случая обнаружения электронных данных, который был создан, изменен или удален.  <br/> |
|ClientApplication  <br/> |действия командлетов обнаружения электронных данных имеют значение **EMC** для этого свойства. Это указывает на то, что действие выполнялось с помощью графического интерфейса центра & Security или запуска командлета в PowerShell.  <br/> |
|ClientIP  <br/> |IP-адрес устройства, которое использовалось при регистрации действия в журнале. IP-адрес отображается в формате адреса IPv4 или IPv6.  <br/> |
|ClientRequestId  <br/> | Для действий обнаружения электронных данных это свойство, как правило, пустое.  <br/> |
|CmdletVersion  <br/> |Номер сборки для версии центра безопасности & соответствия требованиям в Организации.  <br/> |
|CreationTime  <br/> |Дата и время выполнения действия обнаружения электронных данных в формате UTC.  <br/> |
|EffectiveOrganization  <br/> |Имя организации Microsoft 365.  <br/> |
|ексчанжелокатионс  <br/> |Почтовые ящики Exchange Online, включенные в поиск контента или помещаемые на хранение в случае обнаружения электронных данных.  <br/> |
|Исключения  <br/> |Адреса почтового ящика или сайта, которые исключены из поиска контента или удержания в футляре eDiscovery.  <br/> |
|ExtendedProperties  <br/> |Дополнительные свойства из поиска контента, действия поиска контента или удержания в случае обнаружения электронных данных, например GUID объекта и соответствующие параметры командлета и командлета, которые использовались при выполнении действия.  <br/> |
|Id  <br/> |Идентификатор записи отчета. ИДЕНТИФИКАТОР однозначно определяет запись в журнале аудита.  <br/> |
|нонпиипараметерс  <br/> |Список параметров (без значений), которые использовались с командлетом, указанным в свойстве Operation. Параметры, указанные в этом свойстве, совпадают с параметрами, указанными в свойстве Parameters.  <br/> |
|ObjectId  <br/> |GUID или имя объекта (например, поиск контента или место обнаружения электронных данных), которое было создано, изменено или удалено с помощью действия, указанного в свойстве Operation. Этот объект также определяется в столбце элемент в результатах поиска журнала аудита.  <br/> |
|ObjectType  <br/> |Тип объекта обнаружения электронных данных, созданного, удаленного или измененного пользователем; Например, действие поиска контента (Предварительная версия, экспорт или очистка), вариант eDiscovery или поиск контента.  <br/> |
|Операция  <br/> |Имя операции, соответствующее выполняемой операции обнаружения электронных данных.  <br/> |
|OrganizationId  <br/> |GUID вашей организации Microsoft 365.  <br/> |
|Параметры  <br/> |Имя и значение параметров, которые использовались с соответствующим командлетом.  <br/> |
|публикфолдерлокатионс  <br/> |Расположения общедоступных папок в Exchange Online, включенные в поиск контента или помещаемые на хранение в футляре eDiscovery.  <br/> |
|Query  <br/> |Запрос поиска, связанный с действием, например поиск контента или удержание на основе запроса.  <br/> |
|RecordType  <br/> |Тип операции, указанный в записи. Значение **18** указывает на событие, связанное с действием, указанным в разделе [действия командлетов обнаружения электронных](#ediscovery-cmdlet-activities) данных. Значение **24** указывает на событие, связанное с действием, указанным в разделе [Поиск и Просмотр действий обнаружения электронных](#how-to-search-for-and-view-ediscovery-activities) данных.  <br/> |
|ResultStatus  <br/> |Указывает, успешно ли выполнено действие (указанное в свойстве Operation).  <br/> |
|секуритикомплианцецентеревенттипе  <br/> |Указывает на то, что действие было событием центра безопасности & соответствия требованиям. Для этого свойства все действия обнаружения электронных данных будут иметь значение **0** .  <br/> |
|шарепоинтлокатионс  <br/> |Сайты SharePoint Online, включенные в поиск контента или помещаемые на хранение в случае обнаружения электронных данных.  <br/> |
|StartTime  <br/> |Дата и время начала операции обнаружения электронных данных в формате UTC.  <br/> |
|UserId  <br/> |Пользователь, который выполнил действие (указанное в свойстве Operation), которое привело к записи в журнал. Записи обнаружения электронных данных, выполняемые системными учетными записями (например, NT AUTHORITY\SYSTEM), также включаются в журнал аудита.  <br/> |
|UserKey  <br/> |Альтернативный идентификатор пользователя, указываемый в свойстве UserId. Для действий обнаружения электронных данных значение этого свойства, как правило, совпадает со свойством UserId.  <br/> |
|UserServicePlan  <br/> |Подписка, используемая вашей организацией. Для действий обнаружения электронных данных это свойство, как правило, пустое.  <br/> |
|UserType  <br/> |Тип пользователя, который выполнил операцию. Следующие значения указывают тип пользователя.  <br/> 0 обычный пользователь. 2 Администратор в Организации. 3 администратор центра данных Майкрософт или системная учетная запись центра обработки данных. 4 Системная учетная запись. 5 приложение. 6 участник службы. |
|Версия  <br/> |Указывает номер версии действия (определяемого свойством Operation), который записывается в журнал.  <br/> |
|Workload  <br/> |Сесервице, где возникло действие. Для действий обнаружения электронных данных значение равно **секуритикомплианцецентер**.  <br/> |