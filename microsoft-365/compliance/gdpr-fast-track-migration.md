---
title: GDPR
description: 'Технические рекомендации Майкрософт: НАБОР ИНСТРУМЕНТОВ МИГРАЦИИ С ПОМОЩЬЮ FASTTRACK ДЛЯ ОТПРАВКИ ЗАПРОСОВ НА УДАЛЕНИЕ'
keywords: Миграция с помощью FastTrack, Microsoft 365 для образования, документация по Microsoft 365, GDPR
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: mohitku
author: MohitKumar
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 7e4f7fb72d6fb2b84c85ecb55301fc2024630f58
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632490"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a>Набор инструментов миграции с помощью FastTrack для отправки запросов на удаление

## <a name="toolset-purpose"></a>Назначение набора инструментов

Если вы клиент, участвующий в миграции с помощью FastTrack, удаление учетной записи пользователя не приведет к удалению копии данных, хранящейся у специалистов Microsoft FastTrack. Эти данные хранятся исключительно для целей завершения миграции. Если в процессе миграции вам потребуется, чтобы специалисты Microsoft FastTrack удалили имеющуюся у них копию данных, отправьте соответствующий запрос с помощью этого набора инструментов. В обычных обстоятельствах Microsoft FastTrack удаляет все копии данных по завершении миграции организации.

### <a name="supported-platforms"></a>Поддерживаемые платформы
Корпорация Майкрософт поддерживает первоначальный выпуск этого набора инструментов для платформы Windows и консоли PowerShell. Кроме того, этот набор инструментов поддерживает указанные ниже известные платформы.
 
***Таблица 1. Платформы, поддерживаемые набором инструментов***
 
<!--start table here HEADER -->
 
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
| |**Windows 7**|**Windows 8**|**Windows 10**|**Windows Server 2012**|**Windows Server 2016**|
|PS 5.0|Не<br/>Поддерживается|Поддерживается|Поддерживается|Поддерживается|Поддерживается|
|PS 5.1|Не<br/>Поддерживается|Поддерживается|Поддерживается|Поддерживается|Поддерживается|
|||
 
<!-- end of table -->

### <a name="obtaining-the-toolset"></a>Получение набора инструментов

Этот набор инструментов доступен в коллекции PowerShell в консольном приложении PowerShell. Чтобы найти и загрузить этот модуль командлета, сначала откройте PowerShell в режиме администратора, чтобы получить соответствующие разрешения для установки модуля. Если ранее вы не использовали PowerShell, в поле поиска на панели задач Windows введите PowerShell. Чтобы запустить Windows PowerShell, щелкните консольное приложение правой кнопкой мыши, выберите **Запуск от имени администратора** и нажмите кнопку **Да**.

![PowerShell: запуск от имени администратора](../media/fasttrack-powershell_image.png)

![PowerShell: предоставление разрешения на внесение изменений приложению](../media/fasttrack-run-powershell_image.png)

Теперь, когда вы открыли консоль, вам потребуется настроить разрешения для выполнения скрипта. Чтобы разрешить выполнение скрипта, введите следующую команду: Set-ExecutionPolicy — ExecutionPolicy: Bypass — Scope: Process

Вам будет предложено подтвердить это действие, так как администратор может изменять область по своему усмотрению.

***Настройка политики выполнения***

![Изменение политики выполнения в PowerShell](../media/powershell-set-execution-policy_image.png)

Теперь, когда для консоли настроено разрешение на выполнение скрипта, установите необходимый модуль, выполнив следующую команду:

>`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery
>        
>               -WarningAction: SilentlyContinue `
>               -Force’

### <a name="prerequisites-for-module"></a>Компоненты, необходимые для работы модуля
Для успешной работы этого модуля вам может потребоваться установить зависимые модули (если они еще не установлены). Возможно, вам придется перезапустить PowerShell.  

Чтобы отправить запрос субъекта данных, вам сначала потребуется выполнить вход, используя свои учетные данные Office 365. Введя соответствующие учетные данные, вы подтвердите свой статус глобального администратора и сможете собирать информацию о клиенте. 

**Login-FastTrackAccount -ApiKey: \<ключ API, предоставленный FastTrack MVM\>**

После успешного входа в систему учетные данные и ключ будут сохранены для использования с модулями FastTrack до конца текущего сеанса PowerShell.

Если вам необходимо подключиться к облачной среде, отличной от коммерческой, нужно добавить к команде *Log in* параметр *-Environment* с указанием одной из допустимых сред:
- AzureCloud
- AzureChinaCloud
- AzureGermanCloud
- AzureUSGovernmentCloud

**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <облачная среда\>**

Чтобы отправить запрос субъекта данных, выполните следующую команду: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: ЭлектронныйАдресСубъектаДанных@МояКомпания.com

При успешном выполнении командлета он возвратит объект идентификатора транзакции. Сохраните этот идентификатор транзакции.


#### <a name="checking-the-status-of-a-request-transaction"></a>Проверка состояния транзакции запроса

Запустите следующую функцию, используя ранее полученный идентификатор транзакции: Get-FastTrackGdprDsrRequest -TransactionID: "ИдентификаторВашейТранзакции"

#### <a name="transaction-status-codes"></a>Коды состояния транзакции
<!--start table here no header -->

|||
|:-----|:-----|:-----|
|**Транзакция** |**Состояние**|
|**Создана** |Запрос создан|
|**Не удалось выполнить**|Не удалось создать запрос. Отправьте запрос еще раз или обратитесь в службу поддержки|
|**Выполнена**|Запрос был выполнен и очищен|
|||

<!-- end of table -->

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->


## <a name="learn-more"></a>Дополнительные сведения
[Центр управления безопасностью (Майкрософт)](https://www.microsoft.com/trust-center/privacy/gdpr-overview
)
