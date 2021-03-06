---
title: Применение управления правами на доступ к данным (IRM) к списку или библиотеке
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- OSU150
- OSU160
- MET150
ms.assetid: 3bdb5c4e-94fc-4741-b02f-4e7cc3c54aa1
ms.collection:
- M365-security-compliance
- SPO_Content
description: С помощью управления правами на доступ к данным (IRM) можно управлять файлами, загруженными из списков или библиотек, и защищать их.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 11d12eda6f2cb8de5c94b6952a8a194b06471473
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818478"
---
# <a name="apply-information-rights-management-irm-to-a-list-or-library"></a>Применение управления правами на доступ к данным (IRM) к списку или библиотеке

С помощью управления правами на доступ к данным (IRM) можно управлять файлами, загруженными из списков или библиотек, и защищать их.
  
## <a name="administrator-preparations-before-applying-irm"></a>Подготовительные действия для администраторов перед применением IRM

- Служба управления правами Azure (Azure RMS) из Azure Information Protection, а также локальный эквивалент, служба управления правами Active Directory (AD RMS), поддерживают управление правами на доступ к данным для сайтов. Не требуются отдельные и дополнительные установки.
    
- Перед применением IRM к списку или библиотеке необходимо сначала включить его администратором сайта.
    
- Чтобы применить IRM к списку или библиотеке, необходимо иметь разрешения администратора для этого списка или библиотеки.
    
- Если вы используете SharePoint Online, то при загрузке больших файлов, защищенных с помощью IRM, могут возникать тайм-ауты пользователей. В этом случае примените защиту IRM с помощью программ Office и храните файлы большего размера в библиотеке SharePoint, не использующей IRM.
    
> [!NOTE]
> Если вы используете SharePoint Server 2013, администратор сервера должен установить предохранители на всех интерфейсных веб-серверах для каждого типа файлов, которые сотрудники организации хотят защитить, с помощью IRM. 
  
## <a name="apply-irm-to-a-list-or-library"></a>Применение управления правами на доступ к данным для списка или библиотеки
<a name="__toc256598179"> </a>

![Параметры управления правами на доступ к данным](../media/1b708102-9c90-42b0-b255-ef0e72d0be88.png)
  
1. Перейдите к списку или библиотеке, для которых необходимо настроить IRM.
    
2. На ленте перейдите на вкладку **Библиотека** , а затем щелкните **Параметры библиотеки**. (Если вы работаете в списке, перейдите на вкладку **список** , а затем выберите **Параметры списка**).
    
    ![Кнопки параметров библиотеки SharePoint на ленте](../media/cdf718fa-d792-40fc-8026-00c3b80b9e05.png)
  
3. В разделе **разрешения и управление**выберите **Управление правами**на доступ к данным. Если ссылка "Управление правами на доступ к данным" не отображается, для сайта может быть отключена служба управления правами на доступ к данным. Обратитесь к администратору сервера, чтобы проверить возможность включения IRM для сайта. Ссылка "Управление правами на доступ к данным" не отображается для библиотек рисунков.
    
4. На странице **параметров управления правами** на доступ к данным установите флажок **ограничить разрешения для документов этой библиотеки при загрузке** , чтобы применить ограниченное разрешение к документам, загруженным из этого списка или библиотеки. 
    
5. В поле **создать название политики разрешений** введите описательное имя политики, которую вы можете использовать позже, чтобы отличать эту политику от других политик. Например, вы можете ввести сведения о компании, если вы **придадите** ограниченные разрешения к списку или библиотеке, которые будут содержать конфиденциальные документы компании. 
    
6. В поле **Добавление описания политики разрешений** введите описание, которое будет отображаться для пользователей, использующих этот список или библиотеку, объясняющий, как они должны обрабатывать документы в этом списке или библиотеке. Например, вы можете ввести **обсудить содержимое этого документа только с другими сотрудниками** , если вы хотите ограничить доступ к информации в этих документах внутренним сотрудникам. 
    
7. Чтобы применить дополнительные ограничения к документам в этом списке или библиотеке, щелкните **Показать параметры**и выполните одно из следующих действий:
    
|**Для этого сделайте следующее:**|**Выполните указанные ниже действия.**|
|:-----|:-----|
|Разрешить пользователям печатать документы из этого списка или библиотеки  <br/> |Установите флажок **Разрешить пользователям печать** .  <br/> |
|Разрешить пользователям, у которых есть по крайней мере разрешение на просмотр элементов, запускать внедренный код или макросы в документе.  <br/> |Установите флажок **Разрешить читателям запускать сценарии и средство чтения с экрана для работы с загруженными документами** .  <br/> При выборе этого параметра пользователи могут запускать код для извлечения содержимого документа.           |
|Требовать, чтобы пользователи проверяют свои учетные данные через определенные промежутки времени.  <br/> Выберите этот параметр, если необходимо ограничить доступ к контенту за указанный период времени. При выборе этого параметра срок действия лицензий на выдачу для доступа к содержимому истечет через указанное число дней, и пользователям потребуется вернуться на сервер, чтобы проверить свои учетные данные и скачать новую копию.  <br/> |Установите флажок **Пользователи должны проверить свои учетные данные с использованием этого интервала (дней)** , а затем укажите количество дней, в течение которых документ должен быть доступен для просмотра.  <br/> |
| Запретить пользователям отправлять документы, не поддерживающие управление правами на доступ к данным, в этот список или библиотеку.  <br/>  Если выбран этот параметр, пользователи не смогут отправлять файлы следующих типов:  <br/>  Типы файлов, на которых не установлены соответствующие предохранители IRM на всех интерфейсных веб-серверах.  <br/>  Типы файлов, которые SharePoint Server 2010 не могут расшифровать.  <br/>  Типы файлов, защищенные службой управления правами на доступ к данным в другой программе  <br/> |Установите флажок **не разрешать пользователям отправлять документы, не поддерживающие управление правами на доступ к данным** .  <br/> |
|Удаление ограниченных разрешений из этого списка или библиотеки на определенную дату.  <br/> |Установите флажок **остановить запрет на доступ к библиотеке** , а затем выберите нужную дату.  <br/> |
|Управление интервалом, в течение которого кэшируются учетные данные для программы, лицензированной для открытия документа.  <br/> |В разделе **Настройка защиты групп и интервала учетных данных**введите интервал для кэширования учетных данных в днях.  <br/> |
|Разрешите защиту группы, чтобы пользователи могли делиться с членами одной и той же группы.  <br/> |Выберите параметр **Разрешить защиту группы**и введите имя группы для общего доступа.  <br/> |
   
8. После завершения выбора нужных параметров нажмите кнопку **ОК**.
  
## <a name="what-is-information-rights-management"></a>Что такое управление правами на доступ к данным?
<a name="__toc256598175"> </a>

Управление правами на доступ к данным (IRM) позволяет ограничить действия, которые пользователи могут выполнять с файлами, загруженными из списков или библиотек. IRM выполняет шифрование загруженных файлов и ограничивает набор пользователей и программ, которым разрешается расшифровывать эти файлы. IRM также может ограничить права пользователей, которым разрешается чтение файлов, запрещая им такие действия как печать копий файлов или копирование текста из них.
  
Вы можете использовать IRM для списков и библиотек, чтобы ограничить распространение конфиденциального содержимого. Например, если вы создаете библиотеку документов для обмена сведениями о предстоящих продуктах с выбранными торговыми представителями, вы можете использовать IRM, чтобы запретить этим пользователям предоставлять доступ к этому содержимому другим сотрудникам компании.
  
На сайте Управление правами на доступ к данным применяется ко всему списку или библиотеке, а не к отдельным файлам. Это упрощает обеспечение согласованного уровня защиты для всего набора документов или файлов. Таким образом, управление правами на доступ к данным может помочь организации применять корпоративные политики, которые управляют использованием и распространением конфиденциальных или конфиденциальных сведений.
  
> [!NOTE]
> Сведения на этой странице об управлении правами на доступ к данным заменяют все термины, которые ссылаются на "Управление правами на доступ к данным" в любых лицензионных соглашениях Microsoft SharePoint Server 2013 и SharePoint Server 2016. 
  
### <a name="how-irm-can-help-protect-content"></a>Как IRM помогает защитить контент
<a name="__toc256598176"> </a>

IRM помогает защитить ограниченное содержимое следующими способами:
  
- Предотвращает копирование, изменение, печать, отправку и вставку содержимого для несанкционированного доступа с помощью средства просмотра.
    
- Помогает предотвратить копирование контента с помощью средства "Печать" с помощью функции "Печать" в Microsoft Windows
    
- Помогает предотвратить просмотр контента средством просмотра, если оно отправляется по электронной почте после загрузки с сервера
    
- Ограничение доступа к содержимому через заданный период времени, после которого пользователи должны подтвердить свои учетные данные и скачать содержимое повторно
    
- Позволяет применять корпоративные политики, которые управляют использованием и распространением контента в Организации
    
### <a name="how-irm-cannot-help-protect-content"></a>Как IRM не помогает защитить контент
<a name="__toc256598177"> </a>

Службе управления правами на доступ к данным не удается защитить ограниченное содержимое от следующих компонентов:
  
- Стирание, хищение, захват и передача вредоносных программ, таких как троянские кони, средства ведения журнала нажатия клавиш и определенные типы шпионских программ
    
- Потеря или повреждение из-за действий компьютерных вирусов
    
- Копирование или повторное ввод контента вручную с экрана
    
- Цифровая фотография контента, отображаемого на экране
    
- Копирование с помощью программ записи с экрана стороннего производителя
    
- Копирование метаданных содержимого (значений столбцов) с помощью программ записи с экрана стороннего производителя или действия копирования и вставки
    
[Применение управления правами на доступ к данным к списку или библиотеке](https://support.office.com/article/6714cfe3-ef39-43b0-bb65-a887726bb63c)
  
## <a name="how-irm-works-for-lists-and-libraries"></a>Как IRM работает для списков и библиотек
<a name="__toc256598178"> </a>

Защита IRM применяется к файлам на уровне списка или библиотеки. Если для библиотеки включено управление правами на доступ к данным, управление правами применяется ко всем файлам в этой библиотеке. Если для списка включено управление правами на доступ к данным, управление правами применяется только к файлам, вложенным в элементы списка, а не к реальным элементам списка.
  
Когда пользователи загружают файлы в списке или библиотеке с поддержкой управления правами на доступ к данным, файлы шифруются таким образом, что они могут просматривать только авторизованные пользователи. Каждый файл, управляемый правами, также содержит лицензию на выдачу, которая накладывает ограничения для пользователей, просматривающих файл. К типичным ограничениям относятся предоставление доступа к файлу только для чтения, отключение копирования текста, запрет на сохранение локальной копии и запрет на печать файла пользователями. Клиентские программы, которые могут читать типы файлов, поддерживаемые IRM, используют лицензию на выдачу в управляемом правами файле, чтобы применить эти ограничения. Так как файл, управляемый правами, сохраняет свою защиту даже после загрузки с сервера.
  
Типы ограничений, применяемые к файлу при его загрузке из списка или библиотеки, основываются на разрешениях отдельных пользователей на сайте, содержащем файл. В следующей таблице показано, как разрешения для сайтов соответствуют разрешениям IRM.
  
|**Разрешения**|**Разрешения IRM**|
|:-----|:-----|
|Управление разрешениями, Управление веб-сайтом  <br/> |**Полный** доступ (как определено клиентской программой): это разрешение обычно позволяет пользователю читать, редактировать, копировать, сохранять и изменять разрешения для контента, управляемого правами.  <br/> |
|Изменение элементов, управление списками, Добавление и настройка страниц  <br/> |**Правка**, **копирование**и **Сохранение**: пользователь может напечатать файл, только если установлен флажок **Разрешить пользователям печатать документы** , на странице параметров управления правами на доступ к данным для списка или библиотеки.  <br/> |
|Просмотр элементов  <br/> |**Read**: пользователь может читать документ, но не может копировать или изменять его содержимое. Пользователь может выполнять печать только в том случае, если установлен флажок **Разрешить пользователям печатать документы** на странице параметров управления правами на доступ к данным для списка или библиотеки.  <br/> |
|Другое  <br/> |Никакие другие разрешения не соответствуют напрямую разрешениям IRM.  <br/> |
   
При включении управления правами на доступ к данным для списка или библиотеки в SharePoint Server 2013 можно защищать только типы файлов в этом списке или библиотеке, для которых установлен предохранитель на всех интерфейсных веб-серверах. Предохранитель — это программа, контролирующая шифрование и расшифровку файлов, управляемых правами, в определенном формате файлов. В SharePoint есть системы защиты для следующих типов файлов:
  
- Формы Microsoft Office InfoPath
    
- Форматы файлов 97-2003 для следующих программ Microsoft Office: Word, Excel и PowerPoint
    
- Форматы Office Open XML для следующих программ Microsoft Office: Word, Excel и PowerPoint
    
- Формат XML Paper Specification (XPS)
    
Если ваша организация планирует использовать IRM для защиты других типов файлов, кроме перечисленных выше, администратор сервера должен установить для этих дополнительных форматов средства защиты.
  

