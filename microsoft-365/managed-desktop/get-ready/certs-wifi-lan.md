---
title: Подготовка сертификатов и сетевых профилей для компьютеров, управляемых Майкрософт
description: certs/Wi/LAN
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0c3edda92e28b45b7f7b48c1d5002014f71116f6
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596576"
---
# <a name="prepare-certificates-and-network-profiles-for-microsoft-managed-desktop"></a>Подготовка сертификатов и сетевых профилей для компьютеров, управляемых Майкрософт  
 
Проверка подлинности на основе сертификатов является распространенным требованием для клиентов, использующих Рабочий стол, управляемый Майкрософт. Для подключения к VPN-решениям или для доступа к внутренним ресурсам в организации могут потребоваться сертификаты для доступа к сетям Wi-Fi или LAN.   
 
Так как настольные устройства, управляемые Майкрософт, присоединяются к Azure Active Directory (Azure AD) и управляются с помощью Microsoft Intune, необходимо развернуть такие сертификаты с помощью протокола SCEP или инфраструктуры сертификатов PKCS, которая интегрирована с Intune.    
 
## <a name="certificate-requirements"></a>Требования к сертификатам 
 
Корневые сертификаты необходимы для развертывания сертификатов с помощью инфраструктуры SCEP или PKCS. Для других приложений и служб в Организации может потребоваться развертывание корневых сертификатов на настольных устройствах, управляемых Майкрософт.    
 
Прежде чем развертывать сертификаты SCEP или PKCS на настольном компьютере, управляемом Майкрософт, необходимо собрать требования для каждой службы, для которой требуется сертификат пользователя или устройства в Организации. Чтобы упростить это, вы можете использовать один из следующих шаблонов планирования:  
 
- [Шаблон сертификата PKCS](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/PKCS-certificate-template.xlsx) 
- [Шаблон сертификата SCEP](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/SCEP-certificate-template.xlsx)

>[!NOTE]
>В настоящее время только профили сертификатов SCEP поддерживаются для развертывания профилей Wi/Fi на настольном компьютере, управляемом Майкрософт, при использовании типа EAP. Профили сертификатов PKCS не поддерживаются. Обратитесь к разделу [Добавление параметров Wi/Fi для устройств с Windows 10 в Intune](https://docs.microsoft.com/intune/wi-fi-settings-windows) для получения справки.

  
## <a name="wi-fi-connectivity-requirements"></a>Требования к подключению Wi – Fi

Чтобы разрешить автоматическое предоставление устройства с требуемой конфигурацией Wi/Fi для корпоративной сети, может потребоваться профиль конфигурации Wi/Fi. Вы можете настроить управление настольным компьютером Майкрософт, чтобы развернуть эти профили на устройствах. Если для обеспечения безопасности сети требуется, чтобы устройства были частью локального домена, вам также может потребоваться оценить сетевую инфраструктуру сети Wi-Fi, чтобы убедиться, что она совместима с настольными компьютерами, управляемыми Майкрософт (только для настольных компьютеров, управляемых корпорацией Майкрософт). 
 
Перед развертыванием конфигурации Wi/Fi на настольных устройствах, управляемых Майкрософт, вам потребуется собрать требования Организации для каждой сети Wi/Fi. Чтобы упростить это, вы можете использовать этот [шаблон профиля Wi-Fi](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/managed-desktop/get-ready/downloads/WiFi-profile-template.xlsx).
 
 
## <a name="wired-connectivity-requirements-and-8021x-authentication"></a>Требования к проводным подключениям и проверка подлинности 802.1 x 
 
Если вы используете проверку подлинности 802.1 x для безопасного доступа к локальной сети (ЛВС), вам потребуется отправить необходимые сведения о конфигурации на настольных устройствах, управляемых Майкрософт. Настольные устройства, управляемые Майкрософт под управлением Windows 10, версии 1809 или более поздней, поддерживают развертывание конфигурации 802.1 x с помощью поставщика службы настройки Виреднетворк (CSP). Для получения дополнительных сведений обратитесь к документации по [поставщику виреднетворк CSP](https://docs.microsoft.com/windows/client-management/mdm/wirednetwork-csp) . 
 
Перед развертыванием профиля конфигурации проводной сети на настольных устройствах, управляемых Майкрософт, соберите требования Организации к корпоративной сети проводной сети. Для этого выполните указанные ниже действия. 
 
 
1. Войдите на устройство, на котором установлен ваш существующий профиль 802.1 x, подключенный к сети локальной сети.  
2. Откройте командную строку с административными учетными данными. 
3. Найдите имя интерфейса локальной сети, выполнив **netsh interface show interface**. 
4. Экспортируйте XML профиля локальной сети, выполнив **команду Netsh LAN Export Profile Folder =.  Interface = "interface_name"**. 
5. Если необходимо протестировать экспортированный профиль на компьютере, управляемом Майкрософт, запустите **Netsh LAN Add Profile filename = "PATH_AND_FILENAME. XML" Interface = "interface_name"**. 
 
 
## <a name="deploy-certificate-infrastructure"></a>Развертывание инфраструктуры сертификатов  
 
Если у вас уже есть инфраструктура SCEP или PKCS с Intune, которая соответствует вашим требованиям, вы также можете использовать ее для настольного компьютера, управляемого корпорацией Майкрософт. Если не существует инфраструктуры SCEP или PKCS, необходимо подготовить ее.  
 
Дополнительную информацию можно узнать [в статье Настройка профиля сертификата для устройств в Microsoft Intune](https://docs.microsoft.com/intune/certificates-configure). 
 
 
 
## <a name="deploy-a-lan-profile"></a>Развертывание профиля локальной сети 
 
После экспорта профиля локальной сети можно подготовить политику для настольного компьютера, управляемого Майкрософт, выполнив указанные ниже действия.   
 
1. Создайте настраиваемый профиль в Microsoft Intune для профиля локальной сети, используя следующие параметры (см. раздел [Использование пользовательских параметров для устройств с Windows 10 в Intune](https://docs.microsoft.com/intune/custom-settings-windows-10)). В разделе **Настраиваемые параметры OMA – URI**нажмите кнопку **Добавить**, а затем введите следующие значения: 
    - Name: *современный рабочем месте — профиль локальной сети Windows 10* 
    - Описание: введите описание параметра и другие важные сведения. 
    - OMA-URI (с учетом регистра): ввод *./девице/вендор/мсфт/виреднетворк/ланксмл*
    - Тип данных: SELECT **String (XML-файл)**. 
    - Настраиваемый XML: Отправьте экспортированный XML-файл.
2. Отправьте запрос в службу поддержки, управляемый корпорацией Майкрософт, с помощью портала администрирования рабочих столов Майкрософт, чтобы просмотреть и развернуть профиль конфигурации на "современные рабочие устройства – тестирование". Системные ИТ-операции, управляемые Майкрософт, помогут вам узнать, когда запрос будет выполнен через запрос поддержки на портале администрирования.
 
## <a name="deploy-certificates-and-wi-fivpn-profile"></a>Развертывание сертификатов и профиля Wi-Fi/VPN 
 
 
Чтобы развернуть сертификаты и профили, выполните указанные ниже действия.

1. Создайте профиль для каждого корневого и промежуточного сертификатов (см. раздел [Создание доверенных профилей сертификатов](https://docs.microsoft.com/intune/protect/certificates-configure#step-3-create-trusted-certificate-profiles)). Каждый из этих профилей должен иметь описание, включающее дату истечения срока действия в формате дд/мм/гггг. **Профили сертификатов без даты истечения срока действия не будут развернуты.**
2. Создайте профиль для каждого сертификата SCEP или PKCS (см. [Создание профиля сертификата SCEP](https://docs.microsoft.com/intune/protect/certificates-scep-configure#create-a-scep-certificate-profile) или [Создание профиля сертификата PKCS](https://docs.microsoft.com/intune/protect/certficates-pfx-configure#create-a-pkcs-certificate-profile)) каждый из этих профилей должен иметь описание, включающее дату истечения срока действия в формате дд/мм/гггг. **Профили сертификатов без даты истечения срока действия не будут развернуты.**
3. Создайте профиль для каждой корпоративной сети Wi-Fi (см. [Параметры Wi-Fi для Windows 10 и более поздних версий](https://docs.microsoft.com/intune/wi-fi-settings-windows)).
4. Создайте профиль для каждой корпоративной виртуальной частной сети ( [в разделе Параметры устройств Windows 10 и Windows holographic можно добавить VPN-подключения с помощью Intune](https://docs.microsoft.com/intune/vpn-settings-windows-10)).
5. Отправьте запрос в службу поддержки под названием "развертывание сертификата" или "развертывание профилей Wi-Fi" на компьютер, управляемый корпорацией Майкрософт, с помощью портала администрирования рабочих столов Майкрософт, чтобы просмотреть и развернуть профиль конфигурации на "современные рабочие устройства – тестирование". Системные операции, управляемые Майкрософт для настольных систем, помогут вам узнать, когда запрос будет выполнен через запрос поддержки на портале администрирования. 
 
 
