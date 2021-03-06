---
title: Просмотр отчетов о движении по почте в центре безопасности & соответствия требованиям
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Узнайте, как найти и использовать отчеты безопасности почтовых систем для вашей организации. Отчеты о движении по почте доступны в центре безопасности & соответствия требованиям.
ms.custom: ''
ms.openlocfilehash: 70c96bb4f43edb80f98fdc98aa173fed9e54e7d7
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937259"
---
# <a name="view-mail-flow-reports-in-the-security--compliance-center"></a>Просмотр отчетов о движении по почте в центре безопасности & соответствия требованиям

В дополнение к сведениям о [почтовых сообщениях](mail-flow-insights-v2.md) , которые доступны в центре безопасности & соответствия требованиям, доступны разнообразные отчеты о движении почты, которые помогут вам отслеживать свою организацию Microsoft 365. Если у вас есть [необходимые разрешения](#what-permissions-are-needed-to-view-these-reports), вы можете просмотреть эти отчеты в центре безопасности & соответствия требованиям, <https://office.protection.com> перейдя на **Reports** \> **панель мониторинга**отчетов. Чтобы перейти непосредственно к панели мониторинга отчетов, откройте ее <https://office.protection.office.com/insightdashboard> .

![Панель мониторинга отчетов в центре безопасности & соответствия требованиям](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>Отчет о соединителях

В **отчете о соединителе** отображаются действия потока обработки почты для [входящих и исходящих соединителей](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) , настроенных для Организации.

Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), откройте **Reports** \> **панель мониторинга "отчеты"** и выберите пункт " **отчет о соединителе**". Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=ConnectorReport> .

![Мини-приложение "отчет о соединителе" на панели мониторинга отчетов](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>Представление отчета для соединителя

В представлении отчета доступны следующие диаграммы:

- **Просмотр данных по: почтовые потоки**: на этой диаграмме показано количество входящих и исходящих сообщений, упорядоченных по следующим адресам:

  - **Total**
  - **Из Интернета без соединителя**
  - **В Интернет без соединителя**
  - Указанный соединитель, который вы настроили.
  
  Чтобы изолировать данные на диаграмме, используйте параметр **Показать данные для** управления, чтобы выбрать один из этих параметров или **весь процесс обработки почты**.

  ![Просмотр данных с помощью почтовых ящиков в отчете о соединителях](../../media/connector-report-view-data-by-mail-flow.png)

- **Просмотр данных по: использование TLS**: на этой диаграмме показан процент использования протокола TLS для потока обработки почты.

  Чтобы изолировать данные на диаграмме, используйте элемент управления **Показать данные для** выбора одного из следующих параметров:

  - **Весь процесс обработки почты**
  - **Из Интернета без соединителя**
  - **В Интернет без соединителя**
  - Указанный соединитель, который вы настроили.

  ![Просмотр данных по использованию TLS в отчете о соединителях](../../media/connector-report-view-data-by-tls-usage.png)

Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным**датами.

### <a name="details-table-view-for-the-connector-report"></a>Представление таблицы сведений о соединителе

Если в представлении отчета выбрать **Таблица Просмотр сведений** , отображаются следующие сведения:

- **Date**
- **Направление и имя соединителя**
- **Тип соединителя**
- **Принудительное TLS?**: значение **true** или **false**.
- **Без TLS** (%)
- **TLS 1,0** (%)
- **TLS 1,1** (%)
- **TLS 1,2** (%)
- **Volume**: количество сообщений.

Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.

Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.

## <a name="exchange-transport-rule-report"></a>Отчет о правилах транспорта Exchange

В **отчете о правиле транспорта Exchange** показано, как правила обработки почты (также называемые правилами транспорта) применяются к входящим и исходящим сообщениям в Организации.

Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **правило транспорта Exchange**. Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=ETRRuleReport> .

![Мини-приложение правил транспорта Exchange в панели мониторинга отчетов](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Представление отчета для отчета о правиле транспорта Exchange

В представлении отчета доступны следующие диаграммы:

- **Просмотр данных по: правила** \> транспорта Exchange **Разбить на: направление**: на этой диаграмме показано количество **входящих** и **исходящих** сообщений, на которые повлияли правила транспорта.

- **Просмотр данных по: правила** \> транспорта Exchange **Разбить на: степень серьезности**: на этой диаграмме показано количество сообщений с **высокой степенью серьезности** и **средней**серьезности, а также сообщения о **низком уровне** серьезности. Уровень серьезности задается как действие в правиле (**аудит этого правила со степенью серьезности** или _сетаудитсеверити_). Дополнительные сведения см. [в разделе действие правил обработки почты в Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Просмотр данных по: правила транспорта Exchange для защиты от потери данных** \> **Разбить на: направление**: на этой диаграмме показано количество **входящих** и **исходящих** сообщений, на которые повлияли правила транспорта защиты от потери данных (DLP). Вы можете уточнить диаграмму, выбрав следующие параметры:

  - **Показать данные для: все правила транспорта DLP**
  - **Показать данные для: скомпрометированных пользователей**
  - **Показать данные для: обнаружен маленький объем контента в США Патриотический ACT**

- **Просмотр данных по: правила транспорта Exchange для защиты от потери данных** \> **Разбить на: направление**: в этом представлении отображается количество **высоких** и **средних**уровней серьезности, а также сообщения о **низком** уровне, на которые влияют правила транспорта DLP. Вы можете уточнить диаграмму, выбрав следующие параметры:

  - **Показать данные для: все правила транспорта DLP**
  - **Показать данные для: скомпрометированных пользователей**
  - **Показать данные для: обнаружен маленький объем контента в США Патриотический ACT**

Если в представлении отчета щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров::

- **Дата начала** и **Дата окончания**
- Значения направления
- Значения серьезности

![Представление отчета в отчете о правиле транспорта Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Представление таблицы сведений для отчета о правилах транспорта Exchange

Если щелкнуть **Таблица Просмотр сведений**, отображаемая информация зависит от диаграммы, которую Вы искали:

- **Просмотр данных по: правила транспорта Exchange**:

  - **Date**
  - **Правило транспорта**
  - **Тема**
  - **Адрес отправителя**
  - **Адрес получателя**
  - **Серьезность**
  - **Направление**

- **Просмотр данных по: правила транспорта Exchange для защиты от потери данных**:

  - **Date**
  - **Политика защиты от потери данных**
  - **Правило транспорта**
  - **Тема**
  - **Адрес отправителя**
  - **Адрес получателя**
  - **Серьезность**
  - **Направление**

Если в представлении Таблица сведений щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров:

- **Дата начала** и **Дата окончания**
- Значения направления
- Значения серьезности

Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.

## <a name="forwarding-report"></a>Отчет о переадресации

**Отчет о переадресации** показывает автоматически перенаправляемые сообщения вашей организации на внешние домены из почтовых ящиков Exchange Online. Пересылаемые сообщения могут представлять угрозу безопасности или соответствия требованиям и могут указывать на скомпрометированную учетную запись.

Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **Пересылка отчета**. Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=MailFlowForwarding> .

![Мини-приложение "пересылка отчетов" на панели мониторинга отчетов](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>Представление отчета для отчета о перенаправлении

В представлении отчета доступны следующие диаграммы:

- **Показать данные для: методы пересылки**: показаны следующие методы:

  - **Правило транспорта**: также называется " [правила для поток обработки почты](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)".
  - **Правило почтовых ящиков**: также называются [правилами для папки "Входящие"](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).

  ![Способы пересылки в отчете о перенаправлении](../../media/forwarding-report-forwarding-methods.png)

- **Показать данные для: пересылка доменов**: в этом представлении отображаются домены получателей, которые являются конечными объектами для переадресации.

  ![Просмотр пересылаемых доменов в отчете о перенаправлении](../../media/forwarding-report-forwarding-domains.png)

- **Показать данные для: серверы пересылки**: отображаются следующие серверы пересылки:

  - **Правило транспорта**
  - Почтовый ящик, который содержит правило пересылки папки "Входящие".

  ![Представление пересылки в отчете о перенаправлении](../../media/forwarding-report-forwarders.png)

Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным**датами.

### <a name="details-table-view-for-the-forwarding-report"></a>Представление таблицы сведений для отчета о перенаправлении

Если в представлении отчета выбрать **Таблица Просмотр сведений** , отображаются следующие сведения:

- **Серверы пересылки**: **правило транспорта** или почтовый ящик, который содержит правило пересылки папки "Входящие".
- **Тип перенаправления**: **правило почтового ящика** значения или **правило транспорта**.
- **Имя получателя**
- **домен получателя;**
- **Details**: это значение GUID почтового процесса или значение рулеидентити правила для папки "Входящие".
- **Count**
- **Дата первой пересылки**

Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.

Чтобы вернуться к представлению отчетов, нажмите кнопку **Просмотреть отчет**.

## <a name="mailflow-status-report"></a>Отчет о состоянии Mailflow

**Отчет о состоянии Mailflow** похож на отчет о [отправленных и полученных сообщениях электронной почты](#sent-and-received-email-report)с дополнительными сведениями об электронной почте, разрешенной или заблокированной для пограничного сервера. Это единственный отчет, содержащий сведения о защите от краев, а также показывает, сколько электронной почты блокируется до того, как она будет разрешена для оценки службой Exchange Online Protection (EOP).

Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **отчет о состоянии Mailflow**. Чтобы перейти непосредственно к **отчету о состоянии почтового процесса**, откройте <https://protection.office.com/mailflowStatusReport> .

![Мини-приложение "отчет о состоянии Mailflow" на панели мониторинга отчетов](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>Тип представления для отчета о состоянии Mailflow

При открытии отчета по умолчанию выбирается вкладка **тип** . По умолчанию это представление содержит диаграмму и таблицу данных, настроенную со следующими фильтрами:

- **Дата**: последние 7 дней.
- **Направление**:

  - **Получение**
  - **Прав**
  - **Внутренняя** (подсчитывается отдельно от **входящих** и **исходящих**)

- **Тип**:

  - **Хорошая почта**
  - **Вредоносная программа**
  - **Спам**
  - **Защита пограничной системы**
  - **Сообщения правил**
  - **Фишинговое письмо**

Диаграмма организована по значениям **типов** .

Вы можете изменить эти фильтры, нажав кнопку **Фильтр** или выбрав значение в условных обозначениях диаграммы.

Таблица данных содержит следующие сведения:

- **Направление**
- **Тип**
- **24 часа**
- **за 3 дня;**
- **7 дней**
- **15 дней**
- **30 дней**

Если щелкнуть **выбрать категорию для получения дополнительных сведений**, можно выбрать следующие значения:

- **Фишинг-сообщение**: этот выбор переходит к [отчету о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report).
- **Вредоносные программы в электронной почте**: этот выбор переходит к [отчету о состоянии защиты от угроз](view-email-security-reports.md#threat-protection-status-report).
- **Обнаружения нежелательной почты**: при выборе этого параметра откроется [отчет об обнаружении нежелательной почты](view-email-security-reports.md#spam-detections-report).
- **Нежелательная почта с пограничным**сервером: при выборе этого параметра откроется [отчет об обнаружении нежелательной почты](view-email-security-reports.md#spam-detections-report).

**Export**:

Для подробного представления можно экспортировать данные только один день. Таким образом, если вы хотите экспортировать данные в течение 7 дней, необходимо выполнить 7 различных действий экспорта.

Каждый экспортированный CSV-файл может иметь не более 150 000 строк. Если данные за этот день содержат более 150 000 строк, будет создано несколько CSV-файлов.

![Введите View в отчете о состоянии Mailflow ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>Представление "направление" для отчета о состоянии Mailflow

При нажатии вкладки **направление** используются те же фильтры по умолчанию из представления **тип** .

Диаграмма организована по значениям **направления** .

Вы можете изменить эти фильтры, нажав кнопку **Фильтр** или выбрав значение в условных обозначениях диаграммы. Используются те же фильтры из представления **типа** .

Таблица данных содержит одну и ту же информацию из представления **типа** .

**Для получения дополнительных сведений выберите категорию** , которая совпадает с представлением " **тип** ".

**Export**:

Для подробного представления можно экспортировать данные только один день. Таким образом, если вы хотите экспортировать данные в течение 7 дней, необходимо выполнить 7 различных действий экспорта.

Каждый экспортированный CSV-файл может иметь не более 150 000 строк. Если данные за этот день содержат более 150 000 строк, будет создано несколько CSV-файлов.

![Представление "направление" в отчете о состоянии Mailflow ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a>Отчет о отправленных и полученных сообщениях электронной почты

Отчет о **отправленных и полученных сообщениях** — это интеллектуальный отчет, в котором отображаются сведения о входящих и исходящих сообщениях электронной почты, в том числе об обнаружении нежелательной почты, вредоносных программах и сообщениях электронной почты, определенных Разница между этим отчетом и [отчетом о состоянии Mailflow](#mailflow-status-report) : этот отчет не содержит данные о сообщениях, заблокированных службой защиты от краев.

Сводное представление и подробное представление отчета допускают 90 дней фильтрации.

Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), откройте **Reports** \> **панель мониторинга "отчеты"** и выберите **Отправленные и полученные сообщения электронной почты**. Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .

![Мини-приложение "Отправленные и полученные сообщения электронной почты" в панели мониторинга отчетов](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>Представление отчета для отчета о отправленных и полученных сообщениях электронной почты

В представлении отчета доступны следующие диаграммы:

- **Разбить на: тип**: на диаграмме отображаются все доступные категории:

  - **Total**
  - **Хорошая почта**
  - **Вредоносные программы (защита от вредоносных программ)** (EOP)
  - **Обнаружения нежелательной почты**
  - **Сообщения правил**
  - **Расширенная вредоносная программа** (Office 365 ATP)

  Когда вы наводите указатель мыши на день (точка данных) на диаграмме, вы можете просмотреть сведения об этом дне.

  ![Введите View в отчет о отправленных и полученных сообщениях электронной почты](../../media/sent-and-received-email-report-type-view.png)

- **Разбейте на: направление**: на диаграмме показаны **Общие**, **Входящие**и **Исходящие** данные. Когда вы наводите указатель мыши на день (точка данных) на диаграмме, вы можете просмотреть сведения об этом дне.

  ![Представление "направление" в отчете о отправленных и полученных сообщениях](../../media/sent-and-received-email-report-direction-view.png)

- **Детализация по** \> **Вредоносные программы (защита от вредоносных программ)**: этот вариант позволяет вернуться к [определению вредоносных программ в отчете по электронной почте](view-email-security-reports.md#malware-detection-in-email-report).

- **Детализация по** \> **Обнаружения нежелательной почты)**: при выборе этого параметра откроется [отчет об обнаружении нежелательной почты](view-email-security-reports.md#spam-detections-report).

Если в представлении отчета щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров:

- **Дата начала** и **Дата окончания**
- Значения направления
- Значения типов

Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>Представление таблицы сведений для отчета о отправленных и полученных сообщениях электронной почты

Если вы нажимайте кнопку **Просмотреть таблицу сведений** в разделе " **разделить вниз: направление** или" **разбивка на:** представление "направление", отображаются следующие сведения:

- **Дата (UTC)**
- **Тип**
- **Направление**
- **Количество сообщений**

Если в представлении Таблица сведений щелкнуть **фильтры** , вы можете изменить результаты с помощью следующих фильтров:

- **Дата начала** и **Дата окончания**
- Значения направления
- Значения типов

Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.

## <a name="top-senders-and-recipients-report"></a>Отчет по основным отправителям и получателям

Отчет по **основным отправителям и получателям** — это круговая диаграмма, в которой показаны лучшие отправители и получатели сообщений электронной почты.

Чтобы просмотреть отчет, откройте [Центр безопасности & соответствия требованиям](https://protection.office.com), перейдите в **Reports** \> **панель мониторинга** отчетов и выберите **наиболее отправители и получатели**. Чтобы перейти непосредственно к отчету, откройте его <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .

![Мини-приложение "лучшие отправители и получатели" в панели мониторинга отчетов](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>Представление отчета для отчета по верхним отправителям и получателям

В представлении отчета доступны следующие диаграммы:

- **Отображение данных для сообщений, \> отправляемых в первые почтовые сообщения**
- **Отображение данных для \> наиболее популярных получателей почты**
- **Отображение данных для \> самых популярных нежелательных получателей**
- **Показать данные для \> Первые получатели вредоносных программ** (EOP)
- **Показать данные для \> Первые получатели вредоносных программ (ATP)** (Office 365 ATP)

Структура круговой диаграммы изменяется в зависимости от выбранных вариантов.

При наведении указателя на сектор на круговой диаграмме можно увидеть количество отправленных или полученных сообщений.

Если в представлении отчета щелкнуть **фильтры** , можно указать диапазон дат с **начальным** и **конечным**датами.

![Круговая диаграмма в представлении отчета в отчете по верхним отправителям и получателям](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>Представление таблицы "сведения" для отчета по верхним отправителям и получателям

Если щелкнуть **Таблица Просмотр сведений**, отображаемая информация зависит от диаграммы, которую Вы искали:

- **Отображение данных для сообщений, \> отправляемых в первые почтовые сообщения**

  - **Сообщения верхнего уровня**
  - **Count**

- **Отображение данных для \> наиболее популярных получателей почты**

  - **Самые популярные Получатели почты**
  - **Count**

- **Отображение данных для \> самых популярных нежелательных получателей**

  - **Самые распространенные получатели нежелательной почты**
  - **Count**

- **Показать данные для \> Первые получатели вредоносных программ** (EOP)

  - **Самые популярные получатели вредоносных программ**
  - **Count**

- **Показать данные для \> Первые получатели вредоносных программ (ATP)** (Office 365 ATP)

  - **Первые получатели вредоносных программ (ATP)**
  - **Count**

Если в представлении Таблица сведений щелкнуть **фильтры** , можно указать диапазон дат с датой **начала** и **датой окончания**.

Чтобы вернуться к представлению отчета, нажмите кнопку **Просмотреть отчет**.

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Какие разрешения необходимы для просмотра отчетов?

Для просмотра и использования отчетов необходимо быть членом указанной группы ролей в центре безопасности & соответствия требованиям **и** в Exchange Online.

- В центре безопасности & соответствия требованиям необходимо быть участником одной из следующих групп ролей:

  — Управление организацией

  -Администратор безопасности (это также можно сделать в [центре администрирования Azure Active Directory](https://aad.portal.azure.com) — средство чтения безопасности

  Дополнительные сведения см. в статье [Разрешения в Центре безопасности и соответствия требованиям](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

- В Exchange Online необходимо быть участником одной из следующих групп ролей:

  — Управление организацией

  — Управление организацией только с просмотром

  — Получатели только для просмотра

  — Управление соответствием требованиям

Дополнительные сведения см в разделе [разрешения в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) и [Управление группами ролей в Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

## <a name="related-topics"></a>Связанные статьи

[Интеллектуальные отчеты и аналитика в Центре безопасности и соответствия требованиям](reports-and-insights-in-security-and-compliance.md)

[Просмотр отчетов о безопасности почты в Центре безопасности и соответствия требованиям](view-email-security-reports.md)
