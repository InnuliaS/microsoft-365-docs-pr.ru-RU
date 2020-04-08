---
title: Вопросы и ответы по централизованному развертыванию
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
description: Ознакомьтесь с ответами на часто задаваемые вопросы о централизованном развертывании в центре администрирования Microsoft 365.
ms.openlocfilehash: d63158f70e3f905b0ee1acf994cbef207f1ab4f1
ms.sourcegitcommit: b1ec6ba779a94ddbaab11a272e40abe1d3064532
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2020
ms.locfileid: "43166497"
---
# <a name="centralized-deployment-faq"></a>Вопросы и ответы по централизованному развертыванию

Централизованное развертывание — рекомендуемый 365 способ развертывания надстроек Office (Word, Excel, PowerPoint и Outlook) для пользователей и групп в Организации при условии, что организация отвечает всем требованиям для использования централизованного развертывания, как описано в этой статье.   
  
## <a name="how-do-i-know-if-my-organization-is-set-up-for-centralized-deployment"></a>Как узнать, настроена ли Организация для централизованного развертывания?  

Для централизованного развертывания надстроек необходимо, чтобы пользователи выполняли Office 365 профессиональный плюс (а также вошли в Office с помощью учетных данных Организации) и иметь почтовые ящики Exchange Online. Каталог подписки должен находиться в службе Azure Active Directory или быть Федеративной для нее.  
 
Централизованное развертывание поддерживается только для почтовых ящиков Outlook Online. Он не поддерживает развертывание для локальных почтовых ящиков Exchange.
 
Можно использовать  [средство проверки совместимости централизованного развертывания Office 365](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker), чтобы определить, подходит ли ваша подписка. 
  
## <a name="how-do-you-target-add-in-user-assignments-with-centralized-deployment"></a>Как вы научитесь назначать пользователя надстройки при централизованном развертывании?  

Централизованное развертывание поддерживает назначения для отдельных пользователей, групп и всех пользователей в клиенте. Централизованное развертывание можно использовать для пользователей в группах или группах верхнего уровня без родительских групп, но не для пользователей в вложенных группах или группах с родительскими группами. Централизованное развертывание также является частью большинства групп Azure Active Directory, в том числе групп Office 365, списков рассылки и групп безопасности.  

Для упрощения управления лучше использовать назначения групп, а не индивидуальные назначения пользователей.
 
Более подробную информацию можно узнать в разделе [Назначение пользователей и групп](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#user-and-group-assignments).  
   
## <a name="how-long-does-it-take-for-add-ins-to-show-up-for-all-users"></a>Сколько времени занимает надстройки для отображения для всех пользователей?  

Для отображения надстройки для всех пользователей может потребоваться до 12 часов. Это может занять то же время для обновлений надстроек, изменения, внесенные после включения или отключения, или удаления надстроек. 
  
## <a name="as-an-administrator-how-do-i-manage-the-user-access-to-add-ins-for-my-organization"></a>Как администратор, как управлять доступом пользователей к надстройкам для моей организации?

Для упрощения развертывания надстроек для пользователей, групп или всей Организации мы рекомендуем администраторам использовать централизованное развертывание.

Более подробную информацию об управлении доступом пользователей можно узнать в статье </br>[Запретить загрузку надстроек, отключив магазин Office для всех клиентов (кроме Outlook)](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook) и </br>[Укажите администраторов и пользователей, которые могут устанавливать надстройки для Outlook и управлять ими](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins?redirectedfrom=MSDN).

## <a name="will-centralized-deployment-provide-admins-the-flexibility-to-choose-the-deployment-method-for-outlook-add-ins"></a>Централизованное развертывание позволяет администраторам выбрать способ развертывания надстроек Outlook?  

Да. Централизованное развертывание предоставляет администраторам гибкие возможности выбора одного из трех методов развертывания надстроек Outlook во время развертывания надстройки:

**FIXED (по умолчанию)**   надстройка автоматически развертывается для назначенных пользователей и не может удалить ее.  
 
**Доступен** Пользователи могут установить надстройку в Outlook, выбрав пункт Домашняя > получить другие надстройки > управляемые администратором.   
 
**Необязательное требование** Надстройка автоматически развертывается для назначенных пользователей, но может быть удалена.  
    
## <a name="can-admins-update-line-of-business-lob-add-ins"></a>Могут администраторы обновлять бизнес-надстройки?  

Да. Администраторы могут отправлять новый файл манифеста для поддержки изменений метаданных для специализированных надстроек, развернутых администратором. Надстройка обновится при следующем запуске приложений Office. Веб-приложение может изменяться в любое время.  
 
Более подробную информацию можно узнать [в статье надстройка для бизнеса](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#security-of-office-add-ins).  

## <a name="can-admins-turn-off-add-ins"></a>Могут администраторы отключить надстройки?  

Да. Администраторы могут включать и отключать надстройки, которые они развертывают, для всех пользователей в центре администрирования Майкрософт.

Дополнительную информацию можно узнать [в статье состояния надстроек](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#add-in-states).  

##  <a name="can-admins-delete-or-remove-add-ins"></a>Могут ли администраторы удалять или удалять надстройки?

Да. Администраторы могут удалять надстройки, развернутые для всех пользователей в центре администрирования Майкрософт.

Дополнительные сведения см. [в статье удаление надстройки](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins?view=o365-worldwide#delete-the-add-in). 
  
## <a name="can-admins-deploy-paid-add-ins-from-the-office-store-using-centralized-deployment"></a>Могут администраторы развертывать платные надстройки из магазина Office с помощью централизованного развертывания? 

Нет. В настоящее время вы не можете развернуть платные надстройки из магазина Office с помощью централизованного развертывания.  
 
Мы рекомендуем вам присвоить поставщику программного обеспечения для платной надстройки запрос файла манифеста или URL-адреса. После этого администратор клиента может развернуть надстройку в виде бизнес-надстройки с помощью централизованного развертывания.
    
## <a name="which-admin-role-do-i-need-to-manage-add-ins-for-my-organization"></a>Какую роль администратора требуется для управления надстройками в Организации?  

Для управления надстройками необходимо иметь роль глобального администратора. Если вы человек, который приобрели подписку на Microsoft 365 для бизнеса, вы являетесь глобальным администратором. 
 
Ваша подписка сопровождается набором ролей администратора, которые можно назначить другим пользователям в Организации. Каждая роль администратора соответствует распространенным бизнес-функциям и предоставляет пользователям в организации разрешения на выполнение определенных задач в центре администрирования Microsoft 365.  
 
Более подробную информацию можно узнать в статье [назначение ролей администратора](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-worldwide).  