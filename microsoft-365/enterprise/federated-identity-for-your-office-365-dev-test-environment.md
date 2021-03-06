---
title: Федеративная идентификация для среды тестирования Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: 65a6d687-a16a-4415-9fd5-011ba9c5fd80
description: Сводка. Сведения о настройке федеративной аутентификации для среды тестирования Microsoft 365.
ms.openlocfilehash: efe2e196b95feff2aab1577f8e5d3ee29b5e39ba
ms.sourcegitcommit: 330e9baf02b5bc220d61f777c2338814459626ec
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44385064"
---
# <a name="federated-identity-for-your-microsoft-365-test-environment"></a>Федеративная идентификация для среды тестирования Microsoft 365

*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 корпоративный и Office 365 корпоративный.*

Microsoft 365 supports federated identity. This means that instead of performing the validation of credentials itself, Microsoft 365 refers the connecting user to a federated authentication server that Microsoft 365 trusts. If the user's credentials are correct, the federated authentication server issues a security token that the client then sends to Microsoft 365 as proof of authentication. Federated identity allows for the offloading and scaling up of authentication for a Microsoft 365 subscription and advanced authentication and security scenarios.
  
В этой статье описано, как можно настроить федеративную аутентификацию для среды тестирования Microsoft 365 или Office 365, чтобы получить представленную ниже конфигурацию.

![Федеративная аутентификация для среды тестирования Microsoft 365](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase3.png)
  
Конфигурация состоит из следующих компонентов: 
  
- Пробная или рабочая подписка на Microsoft 365 E5 или Office 365 E5.
    
- A simplified organization intranet connected to the Internet, consisting of five virtual machines on a subnet of an Azure virtual network (DC1, APP1, CLIENT1, ADFS1, and PROXY1). Azure AD Connect runs on APP1 to synchronize the list of accounts in the Active Directory Domain Services domain to Office 365. PROXY1 receives the incoming authentication requests. ADFS1 validates credentials with DC1 and issues security tokens.
    
Настройка этой среды тестирования состоит из пяти указанных ниже этапов.
  
1. Создание тестовой среды с синхронизацией хэшей паролей для имитации корпоративной среды.
    
2. Создание сервера AD FS (ADFS1).
    
3. Создание веб-прокси-сервера (PROXY1).
    
4. Создание самозаверяющего сертификата и настройка ADFS1 и PROXY1.
    
5. Настройка федеративной идентификации для Microsoft 365.
    
> [!NOTE]
> Эту среду тестирования невозможно настроить, имея пробную подписку на Azure. 
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Этап 1. Настройка синхронизации хэша паролей для тестовой среды Microsoft 365

Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.
  
![Тестовая среда смоделированной организации с синхронизацией хэша паролей](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase1.png)
  
Конфигурация состоит из следующих компонентов: 
  
- Пробные или платные подписки на Microsoft 365 E5 или Office 365 E5.
- Упрощенная интрасеть организации, подключенная к Интернету и состоящая из виртуальных машин DC1, APP1 и CLIENT1 в подсети, входящей в виртуальную сеть Azure. Azure AD Connect работает на APP1 для периодической синхронизации домена AD DS TESTLAB с клиентом Azure AD, связанным с подписками Microsoft 365.

## <a name="phase-2-create-the-ad-fs-server"></a>Этап 2. Создание сервера AD FS

Сервер AD FS обеспечивает федеративную аутентификацию между Microsoft 365 и учетными записями в домене corp.contoso.com, размещенном на DC1.
  
Чтобы создать виртуальную машину Azure для ADFS1, укажите имя своей подписки, группы ресурсов и расположение Azure для базовой конфигурации, а затем выполните указанные ниже команды в командной строке Azure PowerShell на локальном компьютере.
  
```powershell
$subscrName="<your Azure subscription name>"
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
Connect-AzAccount
Select-AzSubscription -SubscriptionName $subscrName
$staticIP="10.0.0.100"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name ADFS1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic = New-AzNetworkInterface -Name ADFS1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName ADFS1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for ADFS1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName ADFS1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "ADFS-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

После этого на [портале Azure](https://portal.azure.com) подключитесь к виртуальной машине ADFS1, используя имя и пароль учетной записи локального администратора ADFS1. Затем откройте командную строку Windows PowerShell.
  
Чтобы проверить разрешение имен и сетевое подключение между ADFS1 и DC1, выполните команду **ping dc1.corp.contoso.com** и убедитесь, что поступило четыре ответа.
  
Далее присоедините виртуальную машину ADFS1 к домену CORP, выполнив указанные ниже команды в командной строке Windows PowerShell на ADFS1.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

Ниже показана итоговая конфигурация.
  
![Сервер AD FS добавлен в DirSync для среды тестирования Microsoft 365](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase2.png)
  
## <a name="phase-3-create-the-web-proxy-server"></a>Этап 3. Создание веб-прокси-сервера

PROXY1 обеспечивает передачу сообщений аутентификации через прокси-соединения между подключающимися пользователями и ADFS1.
  
Чтобы создать виртуальную машину Azure для PROXY1, укажите имя группы ресурсов, расположение Azure, а затем выполните указанные ниже команды в командной строке Azure PowerShell на локальном компьютере.
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
$vnetName="TlgBaseConfig-01-VNET"
# NOTE: If you built your simulated intranet with Azure PowerShell, comment the previous line with a "#" and remove the "#" from the next line.
#$vnetName="TestLab"
$staticIP="10.0.0.101"
$locName=(Get-AzResourceGroup -Name $rgName).Location
$vnet=Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgName
$pip = New-AzPublicIpAddress -Name PROXY1-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Static
$nic = New-AzNetworkInterface -Name PROXY1-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id -PrivateIpAddress $staticIP
$vm=New-AzVMConfig -VMName PROXY1 -VMSize Standard_D2_v2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for PROXY1."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName PROXY1 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name "PROXY1-OS" -DiskSizeInGB 128 -CreateOption FromImage -StorageAccountType "Standard_LRS"
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

> [!NOTE]
> Машине PROXY1 присваивается статический общедоступный IP-адрес, который не должен меняться при перезапуске виртуальной машины PROXY1, так как на него указывает созданная вами общедоступная запись DNS. 
  
Next, add a rule to the network security group for the CorpNet subnet to allow unsolicited inbound traffic from the Internet to PROXY1's private IP address and TCP port 443. Run these commands at the Azure PowerShell command prompt on your local computer.
  
```powershell
$rgName="<the resource group name of your Base Configuration>"
Get-AzNetworkSecurityGroup -Name CorpNet -ResourceGroupName $rgName | Add-AzNetworkSecurityRuleConfig -Name "HTTPS-to-PROXY1" -Description "Allow TCP 443 to PROXY1" -Access "Allow" -Protocol "Tcp" -Direction "Inbound" -Priority 101 -SourceAddressPrefix "Internet" -SourcePortRange "*" -DestinationAddressPrefix "10.0.0.101" -DestinationPortRange "443" | Set-AzNetworkSecurityGroup
```

После этого подключитесь к виртуальной машине PROXY1 на [портале Azure](https://portal.azure.com), используя имя и пароль учетной записи локального администратора PROXY1. Затем откройте командную строку Windows PowerShell на PROXY1.
  
Чтобы проверить разрешение имен и сетевое подключение между PROXY1 и DC1, выполните команду **ping dc1.corp.contoso.com** и убедитесь, что поступило четыре ответа.
  
Далее присоедините виртуальную машину PROXY1 к домену CORP, выполнив указанные ниже команды в командной строке Windows PowerShell на PROXY1.
  
```powershell
$cred=Get-Credential -UserName "CORP\User1" -Message "Type the User1 account password."
Add-Computer -DomainName corp.contoso.com -Credential $cred
Restart-Computer
```

Выведите на экран общедоступный IP-адрес PROXY1 с помощью этих команд Azure PowerShell на локальном компьютере:
  
```powershell
Write-Host (Get-AzPublicIpaddress -Name "PROXY1-PIP" -ResourceGroup $rgName).IPAddress
```

Next, work with your public DNS provider and create a new public DNS A record for **fs.testlab.**\<your DNS domain name> that resolves to the IP address displayed by the **Write-Host** command. The **fs.testlab.**\<your DNS domain name> is hereafter referred to as the  *federation service FQDN*.
  
После этого воспользуйтесь учетными данными CORP\\User1 на [портале Azure](https://portal.azure.com), чтобы подключиться к виртуальной машине DC1, а затем выполните следующие команды в командной строке Windows PowerShell, открытой от имени администратора:
  
```powershell
Add-DnsServerPrimaryZone -Name corp.contoso.com -ZoneFile corp.contoso.com.dns
Add-DnsServerResourceRecordA -Name "fs" -ZoneName corp.contoso.com -AllowUpdateAny -IPv4Address "10.0.0.100" -TimeToLive 01:00:00
```
Эти команды создают внутреннюю запись DNS A, чтобы виртуальные машины в виртуальной сети Azure могли превращать внутреннее полное доменное имя в частный IP-адрес ADFS1.
  
Ниже показана итоговая конфигурация.
  
![Прокси-сервер веб-приложений добавлен в DirSync для среды тестирования Microsoft 365](../media/federated-identity-for-your-office-365-dev-test-environment/federated-tlg-phase3.png)
  
## <a name="phase-4-create-a-self-signed-certificate-and-configure-adfs1-and-proxy1"></a>Этап 4. Создание самозаверяющего сертификата и настройка ADFS1 и PROXY1

На этом этапе создается самозаверяющий цифровой сертификат для полного доменного имени службы федерации и настраиваются ADFS1 и PROXY1 как ферма AD FS.
  
Сначала подключитесь к виртуальной машине DC1 на [портале Azure](https://portal.azure.com), используя учетные данные CORP\\User1, а затем откройте командную строку Windows PowerShell от имени администратора. 
  
После этого создайте на DC1 учетную запись службы AD FS с помощью этой команды в командной строке Windows PowerShell:
  
```powershell
New-ADUser -SamAccountName ADFS-Service -AccountPassword (read-host "Set user password" -assecurestring) -name "ADFS-Service" -enabled $true -PasswordNeverExpires $true -ChangePasswordAtLogon $false
```
Note that this command prompts you to supply the account password. Choose a strong password and record it in a secured location. You will need it for this phase and Phase 5.
  
Use the [Azure portal](https://portal.azure.com) to connect to the ADFS1 virtual machine using the CORP\\User1 credentials. Open an administrator-level Windows PowerShell command prompt on ADFS1, fill in your federation service FQDN, and then run these commands to create a self-signed certificate:
  
```powershell
$fedServiceFQDN="<federation service FQDN>"
New-SelfSignedCertificate -DnsName $fedServiceFQDN -CertStoreLocation "cert:\LocalMachine\My"
New-Item -path c:\Certs -type directory
New-SmbShare -name Certs -path c:\Certs -changeaccess CORP\User1
```

После этого выполните указанные ниже действия, чтобы сохранить новый самозаверяющий сертификат в виде файла.
  
1. Нажмите кнопку **Пуск**, введите **mmc.exe** и нажмите клавишу **ВВОД**.
    
2. Выберите **Файл > Добавить или удалить оснастку**.
    
3. В окне **Добавление или удаление оснасток** дважды щелкните пункт **Сертификаты** в списке доступных оснасток, выберите пункт **Учетная запись компьютера** и нажмите кнопку **Далее**.
    
4. В окне **Выбор компьютера** последовательно нажмите кнопки **Готово** и **ОК**.
    
5. В области дерева выберите **Сертификаты (локальный компьютер) > Личное > Сертификаты**.
    
6. Щелкните правой кнопкой мыши сертификат с FQDN службы федерации, выберите **Все задачи**, а затем нажмите **Экспорт**.
    
7. На странице **Добро пожаловать** нажмите кнопку **Далее**.
    
8. На странице **Экспортирование закрытого ключа** последовательно нажмите кнопки **Да** и **Далее**.
    
9. На странице **Формат экспортируемого файла** выберите **Экспортировать все расширенные свойства** и нажмите кнопку **Далее**.
    
10. На странице **Безопасность** выберите элемент **Пароль** и введите пароль в поля **Пароль** и **Подтвердите пароль**.
    
11. На странице **Имя экспортируемого файла** нажмите **Обзор**.
    
12. Перейдите в папку **C:\\Certs**, введите **SSL** в поле **Имя файла** и нажмите кнопку **Сохранить**.
    
13. На странице **Имя экспортируемого файла** нажмите кнопку **Далее**.
    
14. On the **Completing the Certificate Export Wizard** page, click **Finish**. When prompted, click **OK**.
    
После этого установите службу AD FS, выполнив следующую команду в командной строке Windows PowerShell на ADFS1:
  
```powershell
Install-WindowsFeature ADFS-Federation -IncludeManagementTools
```

Дождитесь завершения установки.
  
После этого выполните указанные ниже действия, чтобы настроить службу AD FS.
  
1. Нажмите кнопку **Пуск** и выберите значок **Диспетчер серверов**.
    
2. В области дерева диспетчера серверов выберите **AD FS**.
    
3. На панели инструментов вверху нажмите оранжевый символ предупреждения и выберите **Настроить службу федерации на этом сервере**.
    
4. На странице **Добро пожаловать** в мастере настройки служб федерации Active Directory нажмите кнопку **Далее**.
    
5. На странице **Подключение к AD DS** нажмите кнопку **Далее**.
    
6. На странице **Настройка свойств службы**:
    
  - Щелкните стрелку вниз и выберите **SSL-сертификат** с FQDN службы федерации.
    
  - В окне **Отображаемое имя службы федерации** введите название вымышленной организации.
    
  - Нажмите кнопку **Далее**.
    
7. На странице **Выбор учетной записи службы** нажмите **Выбрать** для параметра **Имя учетной записи**.
    
8. В поле **Выберите пользователя или учетную запись службы** введите **ADFS-Service**, затем последовательно нажмите кнопки **Проверить имена** и **ОК**.
    
9. В поле **Пароль учетной записи** введите пароль для учетной записи ADFS-Service и нажмите кнопку **Далее**.
    
10. На странице **Выбор базы данных конфигурации** нажмите кнопку **Далее**.
    
11. На странице **Просмотр параметров** нажмите кнопку **Далее**.
    
12. На странице **Предварительные проверки** нажмите **Настроить**.
    
13. На странице **Результаты** нажмите **Закрыть**.
    
14. Нажмите кнопку **Пуск**, щелкните значок питания, выберите **Перезагрузка** и нажмите кнопку **Продолжить**.
    
Откройте [портал Azure](https://portal.azure.com) и подключитесь к PROXY1, используя учетные данные CORP\\User1.
  
После этого выполните указанные ниже действия, чтобы установить самозаверяющий сертификат на **PROXY1 и APP1**.
  
1. Нажмите кнопку **Пуск**, введите **mmc.exe** и нажмите клавишу **ВВОД**.
    
2. Выберите **Файл > Добавить или удалить оснастку**.
    
3. В окне **Добавление или удаление оснасток** дважды щелкните пункт **Сертификаты** в списке доступных оснасток, выберите пункт **Учетная запись компьютера** и нажмите кнопку **Далее**.
    
4. В окне **Выбор компьютера** последовательно нажмите кнопки **Готово** и **ОК**.
    
5. В области дерева выберите **Сертификаты (локальный компьютер) > Личное > Сертификаты**.
    
6. Щелкните правой кнопкой пункт **Личное** и выберите **Все задачи** > **Импорт**.
    
7. На странице **Добро пожаловать** нажмите кнопку **Далее**.
    
8. На странице **Имя импортируемого файла** введите **\\\\adfs1\\certs\\ssl.pfx** и нажмите кнопку **Далее**.
    
9. На странице **Защита с помощью закрытого ключа** введите пароль сертификата в поле **Пароль** и нажмите кнопку **Далее**.
    
10. На странице **Хранилище сертификатов** нажмите кнопку **Далее**.
    
11. На странице **Завершение** нажмите кнопку **Готово**.
    
12. На странице **Хранилище сертификатов** нажмите кнопку **Далее**.
    
13. Нажмите кнопку **ОК**.
    
14. Выберите **Сертификаты** в области дерева.
    
15. Щелкните сертификат правой кнопкой мыши и выберите **Копировать**.
    
16. В области дерева выберите **Доверенные корневые центры сертификации > Сертификаты**.
    
17. Щелкните правой кнопкой мыши под списком установленных сертификатов и выберите **Вставить**.
    
Откройте командную строку администратора PowerShell и выполните следующую команду:
  
```powershell
Install-WindowsFeature Web-Application-Proxy -IncludeManagementTools
```

Дождитесь завершения установки.
  
Сделайте так, чтобы прокси-служба веб-приложения использовала ADFS1 в качестве сервера федерации:
  
1. Нажмите кнопку **Пуск** и выберите пункт **Диспетчер серверов**.
    
2. В области дерева выберите **Удаленный доступ**.
    
3. На панели инструментов вверху нажмите оранжевый символ предупреждения и выберите **Открытие мастера прокси веб-приложения**.
    
4. На странице **Добро пожаловать** в мастере настройки прокси веб-приложений нажмите кнопку **Далее**.
    
5. На странице **Сервер федерации**:
    
  - Введите FQDN службы федерации в поле **Имя службы федерации**.
    
  - Введите **CORP\\User1** в поле **Имя пользователя**.
    
  - Введите пароль для учетной записи User1 в поле **Пароль**.
    
  - Нажмите кнопку **Далее**.
    
6. На странице **Сертификат прокси-сервера AD FS** щелкните стрелку вниз, выберите сертификат с FQDN службы федерации и нажмите кнопку **Далее**.
    
7. На странице **Подтверждение** нажмите **Настроить**.
    
8. На странице **Результаты** нажмите **Закрыть**.

    
## <a name="phase-5-configure-microsoft-365-for-federated-identity"></a>Этап 5. Настройка федеративной идентификации для Microsoft 365

Используйте учетные данные CORP\\User1 на [портале Azure](https://portal.azure.com), чтобы подключиться к виртуальной машине APP1.
  
Выполните следующие действия, чтобы настроить федеративную проверку подлинности для Azure AD Connect и подписки Microsoft 365:
  
1. На рабочем столе дважды щелкните значок **Azure AD Connect**.
    
2. На странице **Вас приветствует Azure AD Connect** нажмите **Настроить**.
    
3. На странице **Дополнительные задачи** выберите **Смена имени пользователя для входа** и нажмите кнопку **Далее**.
    
4. На странице **Подключение к Azure AD** введите имя и пароль учетной записи глобального администратора и нажмите кнопку **Далее**.
    
5. На странице **Вход пользователя** выберите **Федерация с AD FS** и нажмите кнопку **Далее**.
    
6. На странице **Ферма AD FS** выберите **Использовать существующую ферму AD FS**, введите **ADFS1** в поле **Имя сервера** и нажмите кнопку **Далее**.
    
7. Введите учетные данные учетной записи CORP\\User1 и нажмите кнопку **ОК**.
    
8. На странице учетных записей **Администратор домена** введите **CORP\\User1** в поле **Имя пользователя** и пароль учетной записи в поле **Пароль**, затем нажмите кнопку **Далее**.
    
9. На странице **Учетная запись службы AD FS** введите **CORP\\ADFS-Service** в поле **Имя пользователя домена** и пароль учетной записи в поле **Пароль пользователя домена**, затем нажмите кнопку **Далее**.
    
10. На странице **Домен Azure AD** в поле **Домен**, выберите имя домена, созданного и добавленного в подписку на этапе 1, затем нажмите кнопку **Далее**.
    
11. На странице **Готово к настройке** нажмите кнопку **Настроить**.
    
12. На странице **Установка завершена** нажмите **Проверить**.
    
    Появятся сообщения о том, что конфигурации интрасети и Интернета проверены.
    
13. На странице **Установка завершена** нажмите **Выход**.
    
Действия для демонстрации работы федеративной аутентификации:
  
1. Откройте новый частный экземпляр браузера на локальном компьютере и перейдите по адресу [https://admin.microsoft.com](https://admin.microsoft.com).
    
2. В поле учетных данных для входа введите **user1@**\<the domain created in Phase 1>. 
    
    For example, if your test domain is **testlab.contoso.com**, you would type "user1@testlab.contoso.com". Press TAB or allow Microsoft 365 to automatically redirect you.
    
    You should now see a **Your connection is not private** page. You are seeing this because you installed a self-signed certificate on ADFS1 that your desktop computer cannot validate. In a production deployment of federated authentication, you would use a certificate from a trusted certification authority and your users would not see this page.
    
3. На странице **Подключение не является частным** нажмите **Дополнительно**, а затем нажмите **Перейти к \<your federation service FQDN>**.  
    
4. На странице с именем вымышленной организации войдите с помощью следующих учетных данных:
    
  - имя **CORP\\User1**;
    
  - пароль учетной записи User1.
    
    Откроется **Домашняя страница Microsoft Office**.
    
This procedure demonstrates that your trial subscription is federated with the AD DS corp.contoso.com domain hosted on DC1. Here are the basics of the authentication process:
  
1. Когда вы используете федеративный домен, созданный на этапе 1, в имени учетной записи для входа, Microsoft 365 перенаправляет ваш браузер на полное доменное имя службы федерации и PROXY1.
    
2. PROXY1 направляет локальный компьютер на страницу входа вымышленной организации.
    
3. Когда вы отправляете имя CORP\\User1 и пароль на PROXY1, сервер пересылает эти данные на ADFS1.
    
4. ADFS1 проверяет имя CORP\\User1 и пароль с помощью DC1 и отправляет на локальный компьютер токен безопасности.
    
5. Локальный компьютер отправляет маркер безопасности в Microsoft 365.
    
6. Microsoft 365 проверяет, действительно ли маркер безопасности создан в ADFS1, и разрешает доступ.
    
Your trial subscription is now configured with federated authentication. You can use this dev/test environment for advanced authentication scenarios.
  
## <a name="next-step"></a>Следующий шаг

Сведения о том, как выполнить в Azure развертывание федеративной проверки подлинности с высокой доступностью для рабочей среды Microsoft 365 или Office 365, см. в статье [Развертывание федеративной проверки подлинности с высокой доступностью для Microsoft 365 в Azure](https://docs.microsoft.com/office365/enterprise/deploy-high-availability-federated-authentication-for-office-365-in-azure).
  
