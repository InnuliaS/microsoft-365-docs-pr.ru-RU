---
title: Отчеты в Центре безопасности и соответствия требованиям
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
f1_keywords:
- ms.o365.cc.AuditingHelp
ms.service: O365-seccomp
search.appverid:
- MET150
localization_priority: Normal
ms.assetid: 7acd33ce-1ec8-49fb-b625-43bac7b58c5a
description: Используйте центр безопасности & соответствия требованиям для получения различных отчетов для вашей организации SharePoint Online и Exchange Online, а также отчетов Azure Active Directory.
ms.openlocfilehash: 8762c1bbb23d2b9f3840076f0ffa465cf7ab264b
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936182"
---
# <a name="reports-in-the-security--compliance-center"></a>Отчеты в Центре безопасности и соответствия требованиям

Вы можете использовать страницу " **Просмотр отчетов** " центра безопасности & соответствия требованиям для быстрого доступа к отчетам аудита для организаций SharePoint Online и Exchange Online. Вы также можете получать доступ к отчетам по входу в Azure Active Directory (AD), отчетам об активности пользователей и журналу аудита Azure AD на странице " **Просмотр отчетов** ". Это связано с тем, что ваша платная подписка на Microsoft 365 включает бесплатную подписку на Microsoft Azure. При первом обращении к этим отчетам Azure потребуется выполнить однократную регистрацию. 
  
> [!TIP]
> Чтобы просмотреть дополнительные отчеты о действиях в Организации, просмотрите [отчеты об активности в центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/activity-reports/activity-reports). 
  
 **Перед началом работы**
  
Для просмотра отчетов в центре безопасности & соответствия требованиям необходимы следующие разрешения.
  
- Для просмотра отчетов в центре администрирования безопасности & необходимо назначить роль читателя безопасности в центре администрирования Exchange. По умолчанию эта роль назначается группам ролей "Управление организацией" и "читатель безопасности" в центре администрирования Exchange.
    
- Вы должны быть назначены роли управления поддержкой защиты от потери данных, предназначенной только для просмотра, в центре безопасности & соответствия требованиям для просмотра отчетов о защите от потери данных в центре соответствия требованиям &. По умолчанию эта роль назначается группам ролей "Администратор соответствия требованиям", "Управление организацией", "администратор безопасности" и "читатель безопасности" в центре безопасности & соответствия требованиям.

- Кроме того, для просмотра отчетов о защите от потери данных в центре администрирования Exchange необходимо назначить роль получателей только для просмотра в центре администрирования Exchange. По умолчанию эта роль назначается группам ролей "Управление соответствием", "Управление организацией" и "только просмотр" в центре администрирования Exchange.
  
 **Чтобы открыть страницу "Просмотр отчетов" в центре безопасности & соответствия требованиям:**
  
1. Перейдите по ссылке [https://protection.office.com/#/viewreports](https://protection.office.com/#/viewreports).
    
2. Войдите в систему, используя учетные данные для учетной записи пользователя в Организации.
    
На странице " **Просмотр отчетов** " можно просматривать отчеты следующих типов: 
  
- [Отчеты аудита](#auditing-reports)
- [Отчет по супервизорной проверке](#supervisory-review-report)
- [Отчеты службы защиты от потери данных](#data-loss-prevention-reports)
    
## <a name="auditing-reports"></a>Отчеты аудита

В следующей таблице описываются отчеты в разделе " **Аудит** " на странице " **Просмотр отчетов** " центра безопасности & соответствия требованиям. 
  
|**Отчет**|**Описание**|
|:-----|:-----|
|**отчет по журналу аудита** <br/> |В журнале аудита можно выполнить поиск действий пользователей и администраторов в Организации. Отчет содержит записи действий пользователей и администраторов в Exchange Online, SharePoint Online, OneDrive для бизнеса и Azure Active Directory, который является службой каталогов для Office 365. Дополнительные сведения можно найти в статье [Поиск в журнале аудита в Office 365](search-the-audit-log-in-security-and-compliance.md).  <br/> |
|**Отчеты Azure AD** <br/> |Чтобы найти необычные или подозрительные действия при входе в Организации, вы можете использовать отчеты о входе и активности в Microsoft Azure. Вы также можете просматривать события в журнале аудита Azure AD. Чтобы просмотреть отчеты в Azure, просто щелкните **Просмотр отчетов Azure AD**. Дополнительные сведения см. в указанных ниже статьях. <br/><br/>[Используйте свою бесплатную подписку на Azure Active Directory в Office 365](use-your-free-azure-ad-subscription-in-office-365.md). <br/> [Просмотр отчетов о доступе и использовании](https://go.microsoft.com/fwlink/p/?LinkId=506902).  <br/> |
|**Отчеты об аудите Exchange** <br/> | С помощью функции аудита в Microsoft 365 можно отслеживать изменения, внесенные в конфигурацию Exchange Online администраторами вашей организации. Также регистрируются изменения, вносимые в организацию Exchange Online администратором центра обработки данных или полномочным администратором. Для Exchange Online ведение журнала аудита действий администратора включено по умолчанию, поэтому нет необходимости выполнять какие-либо действия для его включения. В Exchange Online также предусмотрено ведение журнала аудита почтовых ящиков, позволяющее отслеживать доступ к почтовым ящикам не только владельцу почтового ящика. Чтобы отслеживать доступ к почтовым ящикам со стороны пользователей, не являющихся их владельцами, необходимо включить функцию ведения журнала аудита для соответствующих почтовых ящиков.  <br/>  Вы можете запускать отчеты аудита для просмотра записей журналов аудита почтовых ящиков и действий администраторов. Кроме того, вы можете экспортировать журналы аудита почтовых ящиков и действий администраторов, которые в течение 24 часов будут отправлены вам в виде XML-файла, вложенного в письмо. <br/><br/>Дополнительные сведения об экспорте журналов аудита см. в указанных ниже статьях.  <br/><br/> [Экспорт журналов аудита почтовых ящиков](https://go.microsoft.com/fwlink/p/?LinkID=404104) <br/> [Просмотр и экспорт журнала аудита действий администратора центра обработки данных](https://go.microsoft.com/fwlink/p/?LinkId=404109) <br/> [Поиск изменений группы ролей или журналов аудита действий администраторов](https://go.microsoft.com/fwlink/p/?LinkId=404105) <br/>   [Отчеты аудита Exchange](https://go.microsoft.com/fwlink/p/?LinkID=395232).  <br/> |
   
## <a name="supervisory-review-report"></a>Отчет по супервизорной проверке

С помощью отчета супервизорной проверки можно просмотреть состояние всех политик надзорной проверки в Организации. Дополнительные сведения можно найти [в статье Настройка политик надзорной проверки для Организации](configure-supervision-policies.md).
  
## <a name="data-loss-prevention-reports"></a>Отчеты защиты от потери данных

В отчетах по предотвращению потери данных (DLP) содержатся сведения о политиках и правилах защиты от потери данных, которые были применены к контенту, содержащему конфиденциальные данные в Организации. Кроме того, вы можете настроить отчет так, чтобы в нем отображались сведения о действиях политики защиты от потери данных, основанные на заданных вами политике и правилах защиты от потери данных. Дополнительные сведения см. [в статье Просмотр отчета об предотвращении потери данных](view-the-dlp-reports.md).
