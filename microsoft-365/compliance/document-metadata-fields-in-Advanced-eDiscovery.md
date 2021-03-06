---
title: Поля метаданных документа в Advanced eDiscovery
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
description: В этой статье определяются поля метаданных для документов в наборе проверки в случае Advanced eDiscovery в Microsoft 365.
ms.openlocfilehash: 19a8b4968ea4b1d82cd6a9e9278530e6c155ef3f
ms.sourcegitcommit: df6cc8c2eb2a65c7668f2953b0f7ec783a596d15
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/13/2020
ms.locfileid: "44726450"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Поля метаданных документа в Advanced eDiscovery

В приведенной ниже таблице перечислены поля метаданных для документов в наборе рецензий в случае расширенного обнаружения электронных данных. В таблице представлены следующие сведения:

- **Имя поля** и **имя отображаемого поля:** имя поля метаданных и имя поля, которое отображается при просмотре метаданных файла выбранного документа в наборе рецензирования. При просмотре метаданных файла для документа не включаются некоторые поля метаданных. Эти поля выделяются звездочкой (*).

- **Имя поля для поиска:** Имя свойства, которое можно искать при выполнении [запроса на проверку набора](review-set-search.md). Пустая ячейка означает, что вы не можете выполнять поиск этого поля в запросе на проверку набора.

- **Имя экспортированного поля:** Имя поля метаданных, которое включается при экспорте документов.  Пустая ячейка означает, что поле не включено в экспортированные метаданные.

- **Description:** Описание поля метаданных.

> [!NOTE]
> Поле **Ключевые слова** в разделе [Обзор Set Search](https://docs.microsoft.com/microsoft-365/compliance/review-set-search) использует язык запросов по ключевым словам (KQL). Поля, перечисленные в столбце **имя поля с возможностью поиска** , можно использовать в поле **Ключевые слова** в поиске набора проверки для формирования сложных запросов без использования построителя запросов. Дополнительную информацию о KQL можно узнать в статье [Справочник по синтаксису языка запросов по ключевым словам](https://go.microsoft.com/fwlink/?LinkId=269603).

|**Имя поля** и **имя отображаемого поля**|**Имя поля с возможностью поиска**|**Имя экспортируемого поля**|**Описание**|
|:-----|:-----|:-----|:-----|
|Код содержимого вложения|аттачментконтентид||Идентификатор содержимого вложения элемента.|
|Имена вложений|аттачментнамес|Attachment_Names|Список имен вложений.|
|Оценка прав клиента юриста|атторнэйклиентпривилежескоре||Юрист — Оценка контента модели прав клиентов.|
|Автор|Автор|Doc_authors|Автор из метаданных документа.|
|BCC|СК|Email_bcc|Поле "СК" для типов сообщений. Формат — **DisplayName \<SMTPAddress> **.|
|CC|Копия|Email_cc|Поле "копия" для типов сообщений. Формат — **DisplayName \<SMTPAddress> **.|
|Метки соответствия требованиям|комплианцелабелс|Compliance_labels|[Метки хранения](labels.md) применены к содержимому в Office 365.|
|Составной путь|компаундпас|Compound_path|Доступный для человека путь, который описывает источник элемента.|
|Справки|Контентная||Извлеченный текст элемента.|
|Текст беседы|Текст беседы||Текст беседы элемента.|
|Тема "Беседа"|Тема "Беседа"||Раздел "Беседа" элемента.|
|ИДЕНТИФИКАТОР беседы|ConversationId|Conversation_ID|Идентификатор беседы из сообщения.|
|Индекс беседы||Conversation_index|Индекс беседы из сообщения.|
|Время беседы в формате PDF|конверсатионпдфтиме||Дата создания PDF-версии беседы.|
|Время записи исправления беседы|конверсатионредактионбурнтиме||Дата создания PDF-версии беседы для чата.|
|Дата создания документа|CreatedTime|Doc_date_created|Создание даты из метаданных документа.|
|Custodian|Custodian|Custodian|Имя хранитель, с которым связан элемент.|
|Дата|Дата|Дата|Date — это вычисляемое поле, зависящее от типа файла.<br /><br />Электронная почта: Дата отправки<br />Вложения электронной почты: Дата последнего изменения документа; если она недоступна, Дата отправки родительского объекта<br />Внедренные документы: Дата последнего изменения документа; Если этот параметр недоступен, Дата последнего изменения родительского элемента<br />Документы SPO (включает современные вложения): Дата последнего изменения SharePoint; Если этот параметр недоступен, Дата последнего изменения документов<br />Документы, не относящиеся к Office 365: Дата последнего изменения<br />Собрания: Дата начала собрания<br />Голосовая почта: Дата отправки<br />Мгновенные сообщения: Дата отправки|
|Другие пути|дедупедкомпаундпас|Deduped_compound_path|Список составных путей документов, которые являются точными дубликатами (электронная почта: на основе контента, документов: на основе хеша).|
|Другие custodians|дедупедкустодианс|Deduped_custodians|Список custodians документов, которые являются точными дубликатами (для сообщений электронной почты на основе содержимого, в зависимости от хеша).|
|Другие идентификаторы файлов|дедупедфилеидс|Deduped_file_IDs|Список идентификаторов документов, которые являются точными дубликатами (для сообщений электронной почты на основе содержимого, в зависимости от хеша).|
|Комментарии к документам|доккомментс|Doc_comments|Комментарии из метаданных документа.|
|Организация документа||Doc_company|Организация из метаданных документа.|
|ДоЦиндекс *|||Индекс в семействе. **-1** или **0** означает, что это корневой каталог.|
|Ключевые слова документа||Doc_keywords|Ключевые слова из метаданных документа.|
|Автор изменений в документе||Doc_modified_by|Дата последнего изменения от метаданных документа.|
|Версия документа||Doc_revision|Редакция из метаданных документа.|
|Тема документа||Doc_subject|Тема из метаданных документа.|
|Шаблон документа||Doc_template|Шаблон из метаданных документа.|
|Тема "главный"|доминантсеме|Dominant_theme|Тема, рассчитанная для аналитики.|
|Повторяющееся подмножество||Duplicate_subset|Идентификатор группы для точных повторов.|
|Емаилактион *||Email_action|Значения: **None**, **Reply**или **Forward**; в соответствии со строкой темы сообщения.|
|Уведомление о доставке электронной почты||Email_delivery_receipt|Адрес электронной почты, указанный в заголовках Интернета для уведомления о доставке.|
|Importance|емаилимпортанце|Email_importance|Важность сообщения: **0** — мин; **1** — обычный; **2** — высокий|
|Емаиллевел *||Email_level|Указывает уровень сообщения в цепочке электронной почты, к которой он принадлежит; вложения наследуют значение родительского сообщения.|
|Идентификатор сообщения электронной почты||Email_message_ID|Идентификатор сообщения Интернета из сообщения.|
|Емаилреадрецеипт *||Email_read_receipt|Адрес электронной почты, указанный в заголовках Интернета для уведомления о прочтении.|
|Защита электронной почты|емаилсекурити|Email_security|Параметр безопасности сообщения: **0** — нет; **1** — подписан; **2** — зашифровано; **3** — зашифровано и подписано.|
|Чувствительность электронной почты|емаилсенситивити|email_sensitivity|Параметр учета сообщения: **0** — нет; **1** персональный; **2** — частный; **3** — компаниконфидентиал.|
|Набор электронной почты|Почтовые подпочты|Email_set|Идентификатор группы для всех сообщений в одном наборе электронной почты.|
|Емаилсреад *||Email_thread|Позиция сообщения в наборе электронной почты; состоит из идентификаторов узлов из корня к текущему сообщению и разделены точками (.).|
|Извлеченный тип контента||Extracted_content_type|Извлеченный тип контента в виде типа MIME; Например, **image/jpeg**|
|Екстрактедтекстленгс *||Extracted_text_length|Количество символов в извлеченном тексте.|
|Выдача очков с учетом соответствия продукта 1 *||Family_relevance_score_case_issue_1|Показатель релевантности для продукта с учетом случая 1 от релевантности.|
|Фамилидупликатесет *||Family_duplicate_set|Числовой идентификатор для семейств, которые являются точными дубликатами друг друга (одинаковым контентом и всеми вложениями).|
|ИДЕНТИФИКАТОР семейства|FamilyId|Family_ID|Идентификатор семейства объединяет все элементы; для электронной почты сюда входят сообщения и все вложения; для документов это включает документ и все внедренные элементы.|
|Размер семейства||Family_size|Число документов в семействе.|
|Ошибка оценки релевантности файлов 1 *||File_relevance_score_case_issue_1|Показатель релевантности файлов с учетом случая 1 от релевантности.|
|Класс File|филекласс|File_class|Для контента из SharePoint и OneDrive: **Document**; для контента из Exchange: **Электронная почта** или **вложение**.|
|Идентификатор файла|FileId|File_ID|Уникальный идентификатор документа в случае.|
|Дата создания файловой системы||File_system_date_created|Дата создания из файловой системы (применяется только к данным, не относящимся к Office 365).|
|Изменена дата файловой системы||File_system_date_modified|Дата изменения из файловой системы (применяется только к данным, не относящимся к Office 365).|
|Тип файла|FileType||Тип файла элемента в соответствии с расширением файла.|
|Имеет вложение|HasAttachment|Email_has_attachment|Указывает, содержит ли сообщение вложения.|
|Имеет юрист|хасатторнэй||**True** , когда по крайней мере один из участников обнаруживается в списке юрист; в противном случае — значение **false**.|
|Хастекст *||Has_text|Указывает, содержит ли элемент текст; возможные значения: **true** и **false**.|
|Неизменяемый идентификатор||Immutable_ID|Этот идентификатор используется для уникальной идентификации документа в наборе рецензирования. Это поле нельзя использовать в поиске набора проверки, и идентификатор невозможно использовать для доступа к документу в собственном расположении.|
|Инклюзивный тип|инклусиветипе|Inclusive_type|Инклюзивный тип, рассчитанный для аналитики: **0** — не включительно; **1** включительно; **2** – включительно минус; **3** — включающая копия.|
|В качестве ответа на идентификатор||In_reply_to_ID|В поле ответить на идентификатор из сообщения.|
|Является представителем|Торговый представитель|Is_representative|Один документ в каждом наборе точных дубликатов отмечается как представитель.|
|Класс элемента|ItemClass|Item_class|Класс элемента, предоставляемый Exchange Server; Например, **IPM. Note (Примечание** )|
|Дата последнего изменения|LastModifiedDate|Doc_date_modified|Дата последнего изменения из метаданных документа.|
|Идентификатор загрузки|лоадид|Load_ID|Идентификатор набора нагрузок, в который был добавлен элемент в набор рецензирования.|
|Location|Location|Location|Строка, указывающая тип расположения, из которого были получены документы.<br /><br />**Импортированные** данные, не относящиеся к Office 365<br />**Teams** — Microsoft Teams<br />Почтовые ящики **Exchange**<br />**SharePoint** — сайты SharePoint<br />**Onedrive** — учетные записи onedrive|
|Имя расположения|локатионнаме|Location_name|Строка, определяющая источник элемента. Для Exchange это будет SMTP-адрес почтового ящика; для SharePoint и OneDrive URL-адрес семейства веб-сайтов.|
|Помечен как представитель|маркасрепресентативе||Один документ из каждого набора точных дубликатов помечен как представители.|
|Отмечена как предваряющая ситуация с тегом 1 *||Marked_as_pre_tagged_Case_issue_1|Отмечена как предваряющая ситуация с учетом регистра 1 от релевантности.|
|Отмечена как Начальная ошибка случая 1 *||Marked_as_seed_Case_issue_1|Отмечена как Начальная ошибка случая 1 от релевантности.|
|Дата окончания собрания|митинженддате|Meeting_end_date|Дата окончания собрания для собраний.|
|Дата начала собрания|митингстартдате|Meeting_start_date|Дата начала собрания для собраний.|
|Вид сообщения|мессажекинд|Message_kind|Тип искомого сообщения. Возможные значения: ** <br /> <br /> Контакты <br /> Документация <br /> электронной почты <br /> екстерналдата <br /> факсы <br /> журналы обмена мгновенными сообщениями <br /> <br /> <br /> microsoftteams** (Возвращает элементы из чатов, собраний и звонков в Microsoft Teams) ** <br /> заметки о <br /> записях <br /> рссфидс <br /> tasks <br /> голосовой почты**| 
|Собственное расширение|нативикстенсион|Native_extension|Собственное расширение элемента.|
|Собственное имя файла|нативефиленаме|Native_file_name|Собственное имя файла элемента.|
|NativeMD5||Native_MD5|Хеш MD5 (128-разрядное значение хэша) файлового потока.|
|NativeSHA256||Native_SHA_256|Хэш SHA256 (256-разрядное значение хэша) файлового потока.|
|Сортировка по ND/ET: исключение вложений|ндетсортексклаттач|ND_ET_sort_excl_attach|Объединение набора почтовых потоков (ET) и набора NEAR-дублировать (ND). Это поле используется для эффективной сортировки во время проверки. Префикс **D** размещается до набора ND, а в качестве префикса **E** используется префикс et.|
|Сортировка по ND/ET: включение вложений|ндетсортинклаттач|ND_ET_sort_incl_attach|Объединение набора почтовых потоков (ET) и набора NEAR-дублировать (ND). Это поле используется для эффективной сортировки во время проверки. Префикс **D** размещается до набора ND, а в качестве префикса **E** используется префикс et. Каждый элемент электронной почты в наборе ET сопровождается соответствующими вложениями.|
|Выдача нормализованного показателя релевантности 1||Normalized_relevance_score_case_issue_1|Выдача нормализованного показателя релевантности 1 из релевантности.|
|Авторы O365||O365_authors|Автор из SharePoint.|
|O365, созданный пользователем||O365_created_by|Создано из SharePoint.|
|Создана Дата O365||O365_date_created|Дата создания из SharePoint.|
|Измененная дата O365||O365_date_modified|Дата последнего изменения из SharePoint.|
|Автор Office 365||O365_modified_by|Изменено из SharePoint.|
|Родительский идентификатор|ParentId|Parent_ID|Идентификатор родителя элемента.|
|ParentNode||Parent_node|Ближайшее предыдущее сообщение электронной почты в цепочке сообщений электронной почты.|
|Родительский путь|парентпас|Parent_path|Составной путь прямого родителя элемента.|
|Домены участников|партиЦипантдомаинс|Email_participant_domains|Список всех доменов участников сообщения.|
|Participants|Participants|Email_participants|Список всех участников сообщения; Например, "отправитель", "Кому", "копия" или "СК".|
|Идентификатор сведения|пивотид|Pivot_ID|ИДЕНТИФИКАТОР сводной таблицы.|
|Потенциально привилегированный|потентиаллипривилежед|Potentially_privileged|True, если модель обнаружения доверенных прав клиентов считает потенциально привилегированным документом|
|Состояние обработки|процессингстатус|Error_code|Состояние обработки после добавления элемента в набор рецензирования.|
|Прочесть процент с учетом регистра 1||Read_percent_Case_issue_1|Прочтите процентное соотношение с ситуациями 1 от релевантности.|
|Чтение процентилей|реадперцентиле||Чтение процентиля для документа на основе релевантности.|
|Количество получателей||Recipient_count|Количество получателей сообщения.|
|Домены получателей|реЦипиентдомаинс|Email_recipient_domains|Список всех доменов получателей сообщения.|
|Recipients|Recipients|Email_recipients|Список всех получателей сообщения ("Кому", "копия" и "СК").|
|Выдача релевантности для группы загрузки релевантности 1||Relevance_load_group_case_issue_1|Выдача релевантности для группы загрузки релевантности 1 от релевантности.|
|Описание состояния релевантности ситуация 1||Relevance_status_description_Case_issue_1|Описание состояния релевантности ситуация 1: релевантность.|
|Вопрос с вариантом тега релевантности 1||Relevance_tag_case_issue_1|Вопрос с вариантом тега релевантности 1 от релевантности.|
|Комментарий релевантности||Relevance_comment|Поле комментария из релевантности.|
|Показатель релевантности|RelevanceScore||Показатель релевантности документа на основе релевантности.|
|Тег релевантности|релеванцетаг||Показатель релевантности документа на основе релевантности.|
|ИДЕНТИФИКАТОР представителя|репресентативеид||Числовой идентификатор каждого набора точных дубликатов.|
|Sender|Sender|Email_sender|Поле Sender (от) для типов сообщений. Формат — **DisplayName \<SmtpAddress> **.|
|Отправитель или автор|сендераусор||Вычисляемое поле, состоящее из отправителя или автора элемента.|
|домен отправителя;|сендердомаин|Email_sender_domain|Домен отправителя.|
|Sent|Sent|Email_date_sent|Дата отправки сообщения.|
|Задать порядок: включительно|сетордеринклусивесфирст|Set_order_inclusives_first|Поле сортировки — электронная почта и вложения: Counter — хронологически; Documents: Pivot сначала обоцениваются по убыванию степени сходства.|
|симиларитиперцент||Similarity_percent|Указывает, как похожим документом является поворот вблизи от повторяющегося набора.|
|Исходный размер файла|Size|Native_size|Число байтов собственного элемента.|
|Subject|Subject|Email_subject|Тема сообщения.|
|Тема или название|субжекттитле||Вычисляемое поле, состоящее из темы или заголовка элемента.|
|С пометкой "ситуация 1"||Tagged_by_Case_issue_1|Пользователь, помечающий этот документ в соответствие с выпуском Case 1 по релевантности.|
|Теги|Теги|Теги|Теги, применяемые в наборе рецензирования.|
|Список "темы"|семеслист|Themes_list|Список "темы", рассчитанный для аналитики.|
|Title|Title|Doc_title|Заголовок из метаданных документа.|
|To|To|Email_to|Поле "Кому" для типов сообщений. Формат — **DisplayName \<SmtpAddress> **|
|Уникальный в наборе электронной почты|уникуеинемаилсет||**Значение false** , если в наборе электронной почты есть дубликат вложения.|
|Исправлено|васремедиатед|Was_Remediated|**True** , если элемент был исправлен; в противном случае — **значение false**.|
|Word count|WordCount|Word_count|Число слов в элементе.|
|||||

> [!NOTE]
> Дополнительные сведения о свойствах, которые можно найти для поиска при 365 поиске данных для расширенного случая обнаружения электронных данных, можно найти в статье [запросы и условия поиска для поиска контента](keyword-queries-and-search-conditions.md).
