---
title: Обзор бесед в Advanced eDiscovery
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
description: Узнайте, как использовать функцию реконструкции беседы в Advanced eDiscovery для реорганизации, просмотра и экспорта связанных обсуждений.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 45cf4bdbf0956ee28e75878b7db5ec84b81c7230
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035497"
---
# <a name="review-conversations-in-advanced-ediscovery"></a>Обзор бесед в Advanced eDiscovery 

Обмен мгновенными сообщениями это удобный способ задать вопросы, обмениваться идеями или быстро общаться по большим группам. Как платформы обмена мгновенными сообщениями, такие как Microsoft Teams, становятся основой для совместной работы в корпоративной среде, организациям необходимо оценить, как их рабочие процессы обнаружения электронных данных посвящены новым формам общения 

Функция реконструкции беседы в Advanced eDiscovery предназначена для идентификации контекстного содержимого и создания отдельных представлений бесед. Эта возможность позволяет эффективно и быстро просматривать полные беседы по обмену мгновенными сообщениями (также называемые *цепочки*обсуждений), которые создаются на таких платформах, как Microsoft Teams.

С помощью функции реконструкции бесед можно создавать, просматривать и экспортировать цепочки обсуждений с помощью встроенных возможностей. Используйте расширенную реконструкции беседы обнаружения электронных данных, чтобы:

- Сохранять уникальные метаданные уровня сообщения для всех сообщений в беседе.

- Сбор контекстных сообщений для результатов поиска.

- Просмотр, комментирование и редактирование потоков обсуждений.

- Экспорт отдельных сообщений или цепочки обсуждений

## <a name="terminology"></a>Терминология

Ниже приведено несколько определений, которые помогут начать работу с реконструкции бесед.

- **Сообщения:** Представляет наименьшую единицу беседы. Сообщения могут отличаться в зависимости от размера, структуры и метаданных. 

- **Беседа:** Представляет группу из одного или нескольких сообщений. В разных приложениях беседы могут быть представлены различными способами. В некоторых приложениях существует явное действие, которое вызывается при ответе на существующее сообщение. Беседы формируются в явном виде в результате этого действия пользователя. Например, ниже приведен снимок экрана беседы с каналом в Microsoft Teams.

   ![Беседа с каналом Microsoft Teams](../media/threadedchat.png)

   В других приложениях (например, в 1xN сообщениях чата в Teams) не существует формальной цепочки ответа, а сообщения отображаются как "плоское Ривер сообщений" в одном потоке. В этих типах приложений беседы выводятся из группы сообщений, происходящих в течение определенного времени. Это "мягкое" Группирование сообщений (в отличие от цепочки ответа) представляет собой обсуждение с определенной темой. 

## <a name="step-1-run-a-search"></a>Шаг 1: выполнение поиска

После определения соответствующих custodians и расположений содержимого можно создать поиск для поиска потенциально релевантного контента. На вкладке **поиски** в расширенном случае обнаружения электронных данных можно создать поиск, нажав кнопку **Новый поиск** и следуя инструкциям мастера. Сведения о том, как создавать поисковый запрос, создавать поисковый запрос и просматривать результаты поиска, можно узнать [в статье сбор данных для обращения](create-search-to-collect-data.md).

## <a name="step-2-create-a-conversation-review-set"></a>Шаг 2: создание набора проверки беседы

В наборе рецензирования можно искать, помечать, аннотировать и изменять документы, сообщения электронной почты и беседы в чате. В Advanced eDiscovery вы можете настроить проверку бесед, используя отдельные сообщения или цепочки обсуждений. Это определяется типом набора проверки, который добавляет результаты поиска, созданного на шаге 1, в. Существует два вида наборов проверки: 
  
  - **Стандартные наборы проверки:** Сообщения в беседах обрабатываются и отображаются как отдельные элементы. 
  
  -  **Наборы проверки беседы:** Сообщения в беседах обрабатываются по отдельности, но отображаются в представлении беседы. В наборе проверки бесед можно закомментировать, пометить и исправить сообщения в связанном представлении беседы. 

Дополнительные сведения о том, как просматривать контент в наборе рецензирования и управлять им, можно найти в разделе [Управление наборами проверки](managing-review-sets.md). 

## <a name="step-3-enable-conversation-retrieval-options"></a>Шаг 3: включение параметров получения беседы

После просмотра и завершения запроса поиска можно добавить результаты поиска в набор проверки. При добавлении результатов поиска в набор проверки исходные данные копируются в область хранилища Azure, чтобы упростить процесс просмотра и анализа. Дополнительные сведения о добавлении результатов поиска в набор рецензирования можно найти в статье [Добавление результатов поиска в набор рецензирования](add-data-to-review-set.md). 

Когда вы добавляете данные из бесед в набор проверки, вы можете использовать параметры извлечения беседы для расширения поиска и включения контекстных сообщений. После настройки параметров извлечения беседы могут происходить следующие действия:

  ![Получение беседы](../media/messagesandconversations.png)
  
1. При использовании ключевого слова и запроса с диапазоном дат в *сообщении 3*будет возвращено совпадение поиска. Это сообщение было частью большой беседы, которое проиллюстрировано *CRC1*. 
  
2. Когда вы добавляете данные в набор проверки и включаете параметры получения беседы, Расширенное обнаружение электронных данных перейдет назад и соберет другие элементы в *CRC1*. 
  
3. После добавления элементов в набор проверки можно просмотреть все отдельные сообщения из *CRC1*. 

Чтобы включить извлечение бесед:
  
1. На вкладке **поиски** в расширенном случае обнаружения электронных данных выберите Поиск, а затем нажмите кнопку **Добавить, чтобы просмотреть набор** на всплывающей странице.
  
2. Выберите существующий набор рецензирования или создайте набор рецензирования. Вы можете настроить параметры извлечения при добавлении результатов поиска в стандартный или в набор проверки беседы.
  
3. В разделе **Параметры коллекции**настройте параметры извлечения бесед для источников контента, которые необходимо расширить в поиске, а затем нажмите кнопку **Добавить** , чтобы запустить процесс.  
  
4. После завершения задания **Add to Review Set** на вкладке **задания** можно начать просмотр бесед.

## <a name="step-4-review-and-export-conversations-in-a-review-set"></a>Шаг 4: Просмотр и экспорт бесед в наборе рецензирования

После того как содержимое было обработано и Добавлено в набор рецензирования, можно начать просмотр данных в наборе проверки. Возможности рецензирования различаются в зависимости от того, было ли содержимое добавлено в стандартный набор проверки или в набор проверки беседы. 

### <a name="reviewing-conversations-in-a-standard-review-set"></a>Просмотр бесед в стандартном наборе рецензирования

В стандартном наборе проверки сообщения обрабатываются и отображаются как отдельные элементы, аналогично тому, как они хранятся в папке почтового ящика. В этом рабочем процессе каждое сообщение обрабатывается как отдельный элемент. В результате этого сводные данные и параметры экспорта недоступны в стандартном наборе проверки. 

  ![Стандартный набор проверки](../media/standardrs.PNG)

### <a name="reviewing-conversations-in-a-conversation-review-set"></a>Просмотр бесед в наборе проверки беседы

В наборе проверки беседы отдельные сообщения объединяются в цепочки и представляются как беседы. Это позволяет просматривать и экспортировать контекстные беседы. 

  ![Набор проверки беседы](../media/ConversationRSOptions.PNG)

В следующих разделах описывается просмотр и экспорт бесед в наборе проверки беседы.

#### <a name="reviewing-conversations"></a>Рецензирование бесед

В наборе проверки беседы можно использовать следующие параметры для упрощения процесса проверки.

- **Группировка по беседам:** Группирует сообщения в одном сеансе, чтобы упростить и ускорить процесс проверки. 

- **Представление сводки:** Отображает цепочку обсуждений. В этом представлении вы можете видеть все беседы, а также получать доступ к метаданным для каждого отдельного сообщения.  
  
   - Просмотр метаданных для отдельных сообщений
   
   - Загрузка отдельных сообщений

- **Представление текста:** Предоставляет извлеченный текст для всей беседы. 

- **Представление "Примечания":** Позволяет разметку обсуждения в потоковом представлении. Все сообщения в беседе используют один и тот же документ с аннотациями.

- **Маркировка:** При просмотре бесед в наборе рецензирования можно просматривать и применять теги, щелкая **панель маркировки** в панели "код".

- **Повторное выполнение преобразования беседы:** При добавлении сообщений в набор проверки беседы автоматически запускается задание преобразования, чтобы создать потоковые представления сводки и примечаний. Если не удается выполнить задачу реконструкции беседы, можно повторно запустить это задание, нажав кнопку **действие > создать документы PDF для беседы** в наборе рецензирования.

#### <a name="exporting-conversations"></a>Экспорт бесед

В наборе проверки беседы можно задать следующие параметры для экспорта бесед:

![Экспорт](../media/export.png)

а. Параметры метаданных

   - **Загрузка файла:** Метаданные включены для каждого отдельного сообщения, электронной почты и документа. Для каждого сообщения в беседе существует одна строка. 

   - **Теги:** Теги из процесса проверки включены в файл метаданных. Сообщения в беседе используют одни и те же теги. 

б. Параметры беседы
  
   - **Файлы беседы:** При экспорте файлов бесед представление с заметками преобразуется в PDF-файл и загружается в папку экспорта. Сообщения в одном файле беседы указывает на PDF-версию того же файла беседы.  
  
   - **Отдельные сообщения чата:** При экспорте отдельных сообщений каждое уникальное сообщение в беседе экспортируется как автономный элемент. Файл экспортируется в том же формате, в котором он был сохранен, как в почтовом ящике. Для конкретной беседы вы получаете несколько файлов. MSG. 

     >[!NOTE]
     > Если вы применили заметки к файлу беседы, эти заметки не будут передаваться в отдельные сообщения. 

в. Другие варианты

   - **Создание текстовых файлов для всего экспортированного контента:** Создает текстовый файл для каждого диалога, экспортированного из набора рецензирования. 

   - **Замените экспортированный контент на отредактировал PDF:** Если в процессе проверки создаются файлы беседы отредактировал, эти файлы доступны во время экспорта. Вы можете выбрать, следует ли экспортировать только собственные файлы (не выбрав этот параметр) или заменить собственные файлы версиями отредактировал (выбрав этот параметр), которые будут экспортированы в виде PDF-файлов.

## <a name="more-information"></a>Дополнительные сведения

Чтобы узнать больше о том, как просматривать данные о делах в Advanced eDiscovery, ознакомьтесь со следующими статьями:

- [Просмотр данных обращений](view-documents-in-review-set.md)

- [Анализ данных дела](analyzing-data-in-review-set.md)

- [Экспорт данных дела](exporting-data-ediscover20.md)
