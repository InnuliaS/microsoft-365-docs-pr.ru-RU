---
title: Устранение неполадок аналитики использования Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Узнайте, как устранять проблемы с приложением шаблона аналитики использования Microsoft 365.
ms.openlocfilehash: 4696dd0c5140cdc110781c226819fc64a90fae1b
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402038"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a>Устранение неполадок аналитики использования Microsoft 365

Просмотрите приведенный ниже список сообщений об ошибках, чтобы получить справку по наиболее распространенным проблемам с аналитикой использования Microsoft 365.
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a>We are unable to process your request. Сначала необходимо подписаться на эти данные из центра администрирования Microsoft 365.

 **Код ошибки:** 422 
  
 **Где отображается следующее сообщение:** В Power BI при подключении к приложению шаблона аналитики использования Microsoft 365 или при непосредственном вызове API-интерфейсов отчетов Microsoft 365. 
  
 **Причина:** Перед подключением к приложению необходимо подписаться на данные из центра администрирования Microsoft 365. Если это действие не выполняется, вы не сможете подключиться к приложению шаблона, даже если вы задаете идентификатор клиента Microsoft 365. 
  
 **Чтобы устранить эту ошибку, выполните указанные ниже действия.** Чтобы подписаться на данные, перейдите в центр администрирования, чтобы получить сведения \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">об использовании</a> и найти плитку аналитики использования Microsoft 365 на главной странице панели мониторинга. Нажмите кнопку " **получить Начало работы** ", а затем в открывшейся области **отчетов** , **чтобы сделать данные доступными для аналитики использования Microsoft 365 для Power BI** , на и **сохранить**.
  
## <a name="we-are-processing-your-data"></a>We are processing your data

 **Где отображается следующее сообщение:** На плитке **аналитика использования microsoft 365** на панели мониторинга **использования** в центре администрирования Майкрософт 365. 
  
 **Причина:** Когда вы выдаете запрос [на просмотр данных в приложении шаблона](enable-usage-analytics.md) из центра администрирования Microsoft 365, система Microsoft 365 начинает создавать данные предыстории использования в Организации. В зависимости от размера клиента это действие может занять от 2 до 48 часов. 
  
 **Чтобы устранить эту проблему, выполните указанные ниже действия.** Подождите, но если сообщение не будет изменено, **оно будет готово** через 3 дня, обратитесь в службу [поддержки Microsoft 365 для бизнеса](../contact-support-for-business-products.md).
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a>We are unable to process your request at this time. We are still preparing the data for your organization

 **Код ошибки**: 423 
  
 **Где отображается следующее сообщение:** В Power BI при подключении к приложению шаблона аналитики использования Microsoft 365 или при непосредственном вызове API-интерфейсов отчетов Microsoft 365. 
  
 **Причина:** Когда вы выдаете запрос [на просмотр данных в приложении шаблона](enable-usage-analytics.md) из центра администрирования, система Microsoft 365 начинает создавать исторические данные об использовании в Организации. В зависимости от размера клиента это действие может занять от 2 до 48 часов. 
  
 **Чтобы устранить эту проблему, выполните указанные ниже действия.** Подождите, но если сообщение не **переводится на свои данные** в течение еще 3 дней с момента запуска, обратитесь в службу [поддержки Microsoft 365 для бизнеса](../contact-support-for-business-products.md).
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a>The tenant ID you provided is not in the correct format

 **Код ошибки**: 400 
  
 **Где отображается следующее сообщение:** В Power BI при подключении к приложению шаблона аналитики использования Microsoft 365 или при непосредственном вызове API-интерфейсов отчетов Microsoft 365. 
  
 **Причина**: идентификатор клиента  это GUID, который нужно вводить в формате xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. Если вы укажете любую другую строку в поле ввода клиента, возникнет эта ошибка. 
  
 **Чтобы устранить эту ошибку, выполните указанные ниже действия.** В центре администрирования отправляются \> **отчеты** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">об использовании</a> и поиске плитки аналитики использования Microsoft 365 на главной странице панели мониторинга. The tenant id is listed on the tile. Вы можете скопировать его отсюда и вставить в диалоговое окно для подключения к приложению шаблона. 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a>The tenant ID you provided is not recognized by our system

 **Код ошибки**: 404 
  
 **Где отображается следующее сообщение:** В Power BI при подключении к приложению шаблона аналитики использования Microsoft 365 или при непосредственном вызове API-интерфейсов отчетов Microsoft 365. 
  
 **Причина**: указанный вами идентификатор клиента не существует или является недействительным. 
  
 **Чтобы устранить эту ошибку, выполните указанные ниже действия.** В центре администрирования отправляются \> **отчеты** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">об использовании</a> и поиске плитки аналитики использования Microsoft 365 на главной странице панели мониторинга. The tenant id is listed on the tile. Вы можете скопировать его отсюда и вставить в диалоговое окно для подключения к приложению шаблона. 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a>Please re-enter your credentials to sign in to Power BI again

Код ошибки: 302
  
 **Где отображается следующее сообщение:** В Power BI при подключении к приложению шаблона аналитики использования Microsoft 365 или при непосредственном вызове API-интерфейсов отчетов Microsoft 365. 
  
 **Причина:** код авторизации не сработал; возможно, вам потребуется повторно ввести учетные данные. 
  
 **Как исправить ошибку**: выйдите из Power BI, а затем войдите еще раз. 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a>You do not have the right authorization to access to this data. To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins

 **Код ошибки**: 403 
  
 **Где отображается следующее сообщение:** В Power BI при подключении к приложению шаблона аналитики использования Microsoft 365 или при непосредственном вызове API-интерфейсов отчетов Microsoft 365. 
  
 **Причина:** Не удалось выполнить проверку подлинности, так как пользователь, который пытался подключиться к приложению-шаблону, не имеет правого уровня авторизации для доступа к этим данным. 
  
 **Чтобы устранить эту ошибку, выполните указанные ниже действия.** Предоставьте учетные данные пользователя, который является **глобальным администратором**, администратором **Exchange**, администратором **Skype для бизнеса**, администратором **SharePoint**, **глобальным читателям** или **читателями отчетов** для подключения к приложению-шаблону. Более подробную информацию можно узнать в статье [сведения о ролях администратора](../add-users/about-admin-roles.md) . 
  
## <a name="refresh-failed"></a>Refresh failed

 **Где выводится это сообщение:** в сообщениях электронной почты от Power BI или в сообщениях о сбоях в журнале обновления. 
  
 **Причина:** Иногда учетные данные пользователя, который подключился к приложению шаблона, сбрасываются и не обновляются в параметрах подключения приложения шаблона, в результате чего пользователь видит ошибки обновления. 
  
 **Чтобы устранить эту ошибку, выполните указанные ниже действия.** В Power BI Найдите набор данных, соответствующий приложению шаблона аналитики использования Microsoft 365, выберите пункт **расписание обновления** и укажите учетные данные администратора. 
  
Если это не поможет, очистите кэш и повторно создайте приложение шаблона.
  
  
