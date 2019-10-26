---
title: Развертывание Windows 10 Корпоративная для существующих устройств в качестве обновления на месте
description: Предоставляет рекомендации по настройке и развертыванию образа Windows 10 Корпоративная с помощью System Center Configuration Manager в качестве обновления на месте.
keywords: Microsoft 365, Microsoft 365 корпоративный, документация по Microsoft 365, Windows 10 Корпоративная, развертывание, обновление на месте, Диспетчер конфигураций, Диспетчер конфигураций System Center
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 69edcd65ada007ead9e0c0d628b96f6390e34696
ms.sourcegitcommit: 64a21c59d31a283ccbe87d16f0a174998e3aeba8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2019
ms.locfileid: "37733466"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a>Шаг 2: развертывание Windows 10 Корпоративная для существующих устройств в качестве обновления на месте

*Эта статья относится как к корпоративным, так и к версиям Microsoft 365 для Microsoft*

![Этап 3. Windows 10 Корпоративная](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Самый простой путь обновления компьютеров под управлением Windows 7 или Windows 8,1 до Windows 10 заключается в обновлении на месте. Для полной автоматизации процесса можно использовать последовательность задач System Center Configuration Manager (Configuration Manager). 

Если у вас есть компьютеры под управлением Windows 7 или Windows 8,1, рекомендуем этот путь, если ваша организация развертывает Windows 10. При этом будет использоваться программа установки Windows (Setup. exe) для выполнения обновления на месте, которое автоматически сохраняет все данные, параметры, приложения и драйверы из существующей версии операционной системы. Это требует наименьшей ИТ-силы, так как нет необходимости в сложной инфраструктуре развертывания.

Выполните следующие действия, чтобы настроить и развернуть образ Windows 10 Корпоративная с помощью Configuration Manager в качестве обновления на месте.

## <a name="the-windows-10-deployment-with-system-center-configuration-manager-poster"></a>Развертывание Windows 10 с плакатом System Center Configuration Manager

Афиша диспетчера конфигураций — одна страница в альбомном режиме (17x11). Щелкните изображение ниже, чтобы просмотреть документ PDF в браузере. 

[![Развертывание Windows 10 с плакатом Configuration Manager](./media/windows10-deploy-inplaceupgrade/windows10-deployment-config-manager.png)](https://opdhsblobprod04.blob.core.windows.net/contents/d0d41f25ce48460387a79ace64acad6b/810b475c713ebb3ad65d13746940ef91?sv=2015-04-05&sr=b&sig=tKD38RgLAoOCAWJ5ppEbLevBAHk7KHtWrXldy2Jl6mY%3D&st=2019-10-24T22%3A16%3A08Z&se=2019-10-25T22%3A26%3A08Z&sp=r)

<!--

You can also download this poster in [PDF](https://github.com/MicrosoftDocs/windows-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.pdf) or [Visio](https://github.com/MicrosoftDocs/windows-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.vsdx) format.
-->

## <a name="part-1-verify-readiness-to-upgrade-windows"></a>Часть 1: Проверка готовности к обновлению Windows

Для начала используйте функцию готовности к обновлению Windows Analytics, чтобы предоставить эффективные сведения и рекомендации о компьютерах, приложениях и драйверах в Организации, без дополнительных затрат и без дополнительных требований к инфраструктуре. Эта новая служба предоставляет вам возможности по обновлению и обновлению функций с помощью рабочих процессов, основанных на рекомендуемых рекомендациях корпорации Майкрософт. Актуальные данные инвентаризации позволяют сбалансировать затраты и риски в проектах обновления.

Ознакомьтесь с разработкой [обновлений Windows, готовой к обновлению](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness) , для получения дополнительных сведений, начала работы, использования и устранения неполадок готовности к обновлению.

Далее следуйте указаниям по использованию диспетчера конфигураций System Center (Текущая ветвь) для обновления операционной системы Windows 7 или более поздней до Windows 10. Как и в случае с развертыванием с высоким уровнем риска, мы рекомендуем создать резервную копию пользовательских данных перед тем, как продолжить. Облачное хранилище OneDrive готово к использованию лицензированным пользователям Microsoft 365 и может использоваться для безопасного хранения файлов. Дополнительные сведения можно найти в [кратком руководстве по началу OneDrive](https://aka.ms/ODfBquickstartguide). Для доступа к этой странице необходимо войти в систему как администратор клиента или глобальный администратор в клиенте Office 365 или Microsoft 365.

Список версий Configuration Manager и соответствующих поддерживаемых версий клиентов Windows 10 можно найти в статье [Поддержка Windows 10 для System Center Configuration Manager](https://aka.ms/supportforwin10sccm).

**Проверка готовности к обновлению Windows**

Прежде чем приступать к развертыванию Windows 10, изучите указанные ниже требования.

- В **выпусках Windows, подходящих для обновления** , на ваших устройствах должны быть установлены выпуски Windows 7 или Windows 8,1, которые можно использовать для обновления до Windows 10 Корпоративная. Список поддерживаемых выпусков приведен в статье [варианты обновления Windows 10](https://aka.ms/win10upgradepaths). 
- **Поддерживаемые устройства** — большинство компьютеров, совместимых с Windows 8,1, будут совместимы с Windows 10. Для правильной работы устройств может потребоваться установить обновленные драйверы в Windows 10. Более подробную информацию вы найдете в статье [спецификации Windows 10](https://aka.ms/windows10specifications) .
- **Подготовка к развертыванию** прежде чем приступить к настройке развертывания, убедитесь, что у вас есть следующее:
    - Установочный носитель Windows 10 — установочный носитель должен находиться на отдельном диске с уже установленным ISO-образом. Вы можете получить ISO-файл из центра [загрузки для подписчиков MSDN](https://aka.ms/msdn-subscriber-downloads) или из [центра обслуживания корпоративного лицензирования](https://aka.ms/mvlsc).
    - Резервные копии пользовательских данных, хотя пользовательские данные будут перенесены при обновлении, рекомендуется настроить сценарий резервного копирования. Например, экспортируйте все пользовательские данные в учетную запись OneDrive, с помощью BitLocker на зашифрованное USB-устройство флэш-памяти или сетевой файловый сервер. Более подробную информацию можно узнать [в статье резервное копирование или передача данных в Windows](https://aka.ms/backuptransferdatawindows).
- **Подготовка среды** . для подготовки к развертыванию операционной системы вы будете использовать существующую структуру сервера Configuration Manager. В среде Configuration Manager в дополнение к базовой настройке необходимо внести следующие конфигурации:
    1. [Расширьте схему Active Directory](https://aka.ms/extendadschema) и [создайте контейнер управления системой](https://aka.ms/createsysmancontainer).
    2. Включение обнаружения лесов Active Directory и обнаружения системы Active Directory. Дополнительные сведения см. в разделе [Configure Discovery Methods for System Center Configuration Manager](https://aka.ms/configurediscoverymethods).
    3. Создание границ диапазонов IP-адресов и группы границ для контента и назначения сайта. Дополнительную информацию можно узнать в статье [Определение границ сайтов и групп границ для System Center Configuration Manager](https://aka.ms/definesiteboundaries).
    4. Добавление и Настройка роли точки служб отчетов Configuration Manager. Дополнительные сведения см в разделе [Настройка отчетов в Configuration Manager](https://aka.ms/configurereporting).
    5. Создайте структуру папок файловой системы для пакетов.
    6. Создайте структуру папок консоли Configuration Manager для пакетов.
    7. Установите обновления System Center Configuration Manager (текущей ветви) и все дополнительные необходимые компоненты для Windows 10.

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a>Часть 2: Добавление образа Windows 10 OS с помощью диспетчера конфигураций
Теперь вам потребуется создать пакет обновления операционной системы, содержащий полный установочный носитель с Windows 10. Выполните следующие действия, чтобы создать пакет обновления для Windows 10 Корпоративная x64 с помощью Configuration Manager.

**Добавление образа Windows 10 OS с помощью диспетчера конфигураций**

1. С помощью консоли диспетчера конфигураций в рабочей области " **Библиотека программного обеспечения** " щелкните правой кнопкой мыши узел **пакеты обновления операционной системы** , а затем выберите команду **Добавить пакет обновления операционной системы**.
2. На странице **источник данных** укажите UNC-путь к носителю Windows 10 Корпоративная, а затем нажмите кнопку **Далее**.
3. На странице " **Общие** " укажите **Windows 10 корпоративное обновление x64**, а затем нажмите кнопку **Далее**. 
4. На странице **Сводка** нажмите кнопку **Далее**, а затем нажмите кнопку **Закрыть**. 
5. Щелкните правой кнопкой мыши созданный пакет **обновления Windows 10 Корпоративная x64** , а затем выберите пункт **распространение контента**. 
6. Выберите точку распространения.

## <a name="part-3-configure-deployment-settings"></a>Часть 3: Настройка параметров развертывания
На этом этапе вы настроите последовательность задач обновления, содержащую параметры обновления до Windows 10. Затем определите устройства для обновления, а затем разверните последовательность задач для этих устройств.

### <a name="create-a-task-sequence"></a>Создание последовательности задач
Чтобы создать последовательность задач обновления, выполните следующие действия:
  
1. В рабочей области " **Библиотека программного обеспечения** " консоли диспетчера конфигураций разверните узел **операционные системы**. 
2. Щелкните узел " **последовательности задач** " правой кнопкой мыши и выберите команду **создать последовательность задач**.
3. На странице **Создание новой последовательности задач** выберите **обновление операционной системы из пакета обновления**, а затем нажмите кнопку **Далее**.
4. На странице **сведения о последовательности задач** укажите **Обновление Windows 10 Корпоративная с архитектурой x64**, а затем нажмите кнопку **Далее**.
5. На странице **обновление операционной системы Windows** нажмите кнопку **Обзор** и выберите **пакет обновления операционной системы для Windows 10 Корпоративная, обновление операционной системы x64**, нажмите кнопку **ОК**, а затем нажмите кнопку **Далее**.
6. Перейдите к оставшимся страницам мастера и нажмите кнопку **Закрыть**.

### <a name="create-a-device-collection"></a>Создание коллекции устройств
После создания последовательности задач обновления необходимо создать коллекцию, содержащую устройства, которые будут обновлены.

> [!NOTE]
> Используйте следующие параметры для тестирования развертывания на отдельном устройстве. Вы можете использовать различные правила членства, чтобы включить группы устройств, которые будут готовы к работе. Для получения дополнительных сведений ознакомьтесь [со статьей создание коллекций в System Center Configuration Manager](https://aka.ms/sccm-create-collections).

1. В консоли диспетчера конфигураций в рабочей области " **ресурсы и соответствие требованиям** " щелкните правой кнопкой мыши пункт **коллекции устройств**и выберите команду **создать коллекцию устройств**. 
2. В мастере создания коллекции устройств на странице **Общие** введите следующие параметры, а затем нажмите кнопку **Далее**.
    - Name: обновление Windows 10 Корпоративная с архитектурой x64
    - Ограничение коллекции: все системы
3. На странице " **правила членства** " выберите **Добавить** > **правило** правила для запуска мастера создания правила прямого членства.
4. На странице **приветствия** мастера создания правила прямого членства нажмите кнопку **Далее**.
5. На странице " **Поиск ресурсов** " введите следующие параметры, заменив текст **значения** заполнителя на имя обновляемого устройства: 
    - Класс ресурса: системный ресурс
    - Имя атрибута: Name
    - Значение: *PC0003*
6. На странице **Выбор ресурсов** выберите устройство и нажмите кнопку **Далее**.
7. Заполните мастер создания правила прямого членства и мастер создания коллекции устройств.  
8. Просмотрите семейство Windows 10 Корпоративная с обновлением x64. Не продолжайте, пока не увидите компьютеры, добавленные в коллекцию.

### <a name="create-an-operating-system-deployment"></a>Создание развертывания операционной системы
Выполните следующие действия, чтобы создать развертывание для последовательности задач.

1. В рабочей области " **Библиотека программного обеспечения** " консоли диспетчера конфигураций щелкните правой кнопкой мыши последовательность задач, созданную на предыдущем шаге, а затем выберите команду **развернуть**.
2. На странице " **Общие** " выберите семейство **Windows 10 Корпоративная для обновления x64** , а затем нажмите кнопку **Далее**.
3. На странице **содержимое** нажмите кнопку **Далее**.
4. На странице **Параметры развертывания** выберите следующие параметры, а затем нажмите кнопку **Далее**.

    > [!NOTE]
    > Для данного тестового развертывания вы настроили назначение как **Доступные**, которое требует вмешательства пользователя для запуска развертывания. В рабочей среде можно автоматизировать развертывание с использованием необходимой цели, которая включает в себя настройку дополнительных параметров, таких как планирование при запуске развертывания. 

    - Действие: install
    - Цель: доступна

5. На странице **планирования** примите параметры по умолчанию, а затем нажмите кнопку **Далее**.
6. На странице **взаимодействие с пользователем** примите параметры по умолчанию, а затем нажмите кнопку **Далее**.
7. На странице **оповещения** примите параметры по умолчанию, а затем нажмите кнопку **Далее**.
8. На странице **Сводка** нажмите кнопку **Далее**, а затем нажмите кнопку **Закрыть**.

## <a name="part-4-start-the-windows-10-upgrade-task-sequence"></a>Часть 4: запуск последовательности задач обновления Windows 10
Выполните следующие действия, чтобы запустить последовательность задач обновления Windows 10 на устройстве, которое вы обновляете.
 
1. Войдите на компьютер с Windows и запустите **центр программного обеспечения**.
2. Выберите последовательность задач, созданную на предыдущем шаге, а затем нажмите кнопку **установить**.
3. После начала последовательности задач она автоматически инициирует процесс обновления на месте, вызывая программу установки Windows (Setup. exe) с необходимыми параметрами командной строки для выполнения автоматического обновления, сохраняющего все данные, параметры, приложения и версий.
4. После успешного завершения последовательности задач компьютер будет полностью обновлен до Windows 10.

Если у вас возникли проблемы при использовании Windows 10 в корпоративной среде, вы можете обратиться к наиболее [распространенным решениям по поддержке корпорации Майкрософт](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). Эти ресурсы включают статьи базы знаний, обновления и статьи библиотеки.

При развертывании обновлений в Организации используйте возможность обновления соответствия требованиям Windows Analytics, чтобы обеспечить целостное представление о соответствии обновления ОС, процессе развертывания обновления и устранение неполадок при неисправности для устройств с Windows 10. Эта новая служба использует диагностические данные, в том числе сведения о ходе установки, конфигурации центра обновления Windows и другие сведения, которые обеспечивают такие сведения, без дополнительных затрат и без дополнительных требований к инфраструктуре. Независимо от того, используется ли центр обновления Windows для бизнеса или другие средства управления, вы можете быть уверены, что ваши устройства обновлены правильно.

Просмотрите раздел [мониторинг обновлений Windows и антивирусной программы "Защитник Windows"](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor) , чтобы узнать больше об этом, приступите к работе и используйте обновление соответствия требованиям.

Прежде чем перейти к следующему шагу, проверьте [условия](windows10-exit-criteria.md#crit-windows10-step2), при выполнении которых можно считать данный шаг завершенным.

## <a name="next-step"></a>Следующий шаг

|||
|:-------|:-----|
|![Шаг 3](./media/stepnumbers/Step3.png)| [Развертывание Windows 10 Корпоративная для новых устройств с помощью Windows автопилот](windows10-deploy-autopilot.md) |



<!--

| Phases | Description |
|:--- |:--- |
| [Phase 1: Consideration phase](#phase-1-consideration-phase) | TBD |
| [Phase 2: Testing phase](#phase-2-testing-phase) | TBD |
| [Phase 3: Deployment phase](#phase-3-deployment-phase) | TBD |

## Phase 1: Consideration phase
Before upgrading an OS in an enterprise environment, take the following technical aspects into account:
* [Infrastructure](#step-1-infrastructure)
* [Apps](#step-2-apps)
* [Governance and business processes](#step-3-governance-and-business-processes)

This guide is meant only to provide Microsoft's best recommendations around these assumptions by providing links to existing documentation.

### Step 1: Infrastructure
Consider your organization's collection of hardware, software, policies, networks, and other related technologies as part of the deployment process.

For in-place upgrade with Configuration Manager, these are the infrastructure you need to take into account:

#### Group Policy
Windows 10 introduces many new features and removes and changes many others in Windows 7 and 8.1, including new Group Policy settings which you need to test and implement as part of a Windows 10 migration. Use the examples from the following resources to assess current group policies for Windows, including Group Policy Objects in the Active Directory structure:
* [Manage Windows 10 with administrative templates](https://go.microsoft.com/fwlink/?linkid=860226) - Get step-by-step info on how to manage Windows 10 with administrative templates
* [Group Policy settings that apply to Windows 10](https://docs.microsoft.com/windows/client-management/group-policies-for-enterprise-and-education-editions) - Find out which Group Policy settings apply only to Windows 10 Enterprise

> [!NOTE]
> If you are considering moving to modern management by using MDM instead of Group Policy to manage device configurations, you can start by using the [MDM Migration Analysis Tool (MMAT)](https://github.com/WindowsDeviceManagement/MMAT) to determine what Group Policies are set on the device and report the corresponding settings, if available.

#### Data management
Although in-place upgrades shouldn’t affect user data and apps, a best practice is to configure a backup scenario and back up user data. For example, export all user data to a OneDrive for Business account, BitLocker To Go-encrypted USB flash drive, or network file server. For more details, see:
* [How to back up or transfer your data on a Windows-based computer](https://go.microsoft.com/fwlink/?linkid=860230) - Get step-by-step info on how to manually back up your personal files and settings.
* [Redirect known folders to OneDrive for Business](https://go.microsoft.com/fwlink/?linkid=846620) - Learn how to set a policy at the domain level to make sure users all sync to the same folder when they install the OneDrive sync client and how you can set additional policies to redirect the Documents folder to that sync location.

#### System Center Configuration Manager
This guide assumes you are following Microsoft recommendations and have one of the following versions of System Center Configuration Manager 2012 onward:
* System Center 2012 Configuration Manager with SP2
* System Center 2012, 2012 R2 Configuration Manager with SP1, Current Branch, 1706
    * [Run an in-place upgrade to the latest Configuration Manager](https://go.microsoft.com/fwlink/?linkid=839406)
    * [Updates for Configuration Manager](https://go.microsoft.com/fwlink/?linkid=620343)
* Core Configuration Manager configuration:
    * CONFIGURATION MANAGER accounts
    * Active Directory permissions
    * Source folder structure
    * Active Directory schema
* Configure the following [necessary Configuration Manager components for Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860245):
    * **State migration point** - Stores user state migration data during computer replace scenarios
    * **Distribution point** - Stores all packages in Configuration Manager
    * **Software update point** - Updates an OS as part of the deployment process
    * **Reporting services point** - Monitors the OS deployment process
    * **Boot images** - Are Windows Preinstallation Environment (PE) images used by Configuration Manager to start deployments
    * **OS images** - Denotes the production deployment image (mounted OS)
    * **OS installers** - Creates reference images using Microsoft Deployment Toolkit (MDT) Light Touch
    * **Drivers** - Denotes a repository of managed device drivers
    * **Task Sequence** - Is delivered automatically to the client as a policy

#### Network bandwidth
This guide assumes you have enough network bandwidth to support the deployment of Windows 10 Enterprise and Office 365 ProPlus as a unit. As a bundle, network bandwidth is a significant factor.

#### Client machines and in-place upgrade scenario
* Disk encryption - Third-party disk encryption isn't supported in an in-place upgrade scenario.
* User profiles - Only the standard user profile type is supported.
* Legacy BIOS to Unified Extensible Firmware Interface (UEFI) booting - Changing from legacy BIOS to UEFI booting isn't supported.
* Dual-boot - This scenario is not covered in the guide. If you have the FastTrack Benefit, it only covers devices running a single OS.
* Virtual desktop infrastructure (VDI) environments - This scenario is not covered in the guide. If you have the FastTrack Benefit, it doesn't cover configuration or deployment on VDI environments.
* x64 and x86 - Changing from a 32-bit OS to a 64-bit isn't supported. For more info, see [Windows 10 deployment scenario > In-place upgrade](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios#in-place-upgrade).

### Step 2: Apps

#### Security
Security clients (like antivirus, anti-malware, and anti-spam) are typically found on all PCs within an organization. Because these programs hook into the deeper levels of the OS, you may need to perform a compatibility assessment before starting any Windows 10 migrations. You may need to upgrade, reconfigure, or even replace Some software. Not performing this assessment can lead to:
* Native app compatibility checks failing and preventing an in-place upgrade from starting.
* Broken functionality in the security software.
* Instability after upgrading to Windows 10 (like crashing and reduced performance)

**Antivirus**

Assess current antivirus software. Windows 10 comes with Windows Defender Antivirus to protect devices from malware, viruses, and security threats. We recommend Windows Defender Antivirus. To enable Windows Defender Antivirus, see [Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus) and [Protect devices with Windows Defender Antivirus](https://go.microsoft.com/fwlink/?linkid=860254).

To learn about antivirus solutions from other providers, see [Consumer antivirus software providers for Windows](https://go.microsoft.com/fwlink/?linkid=67345).

#### App readiness
Each Windows 10 release provides improved app compatibility. However, some apps may not be compatible. Depending on the app, you may need to only do a simple upgrade or configuration update before upgrading to Windows 10. In other circumstances, you may need to remove an app entirely.

Be sure to assess business critical apps and understand the impact of upgrading to the next OS. Prioritize the workloads that impact the least number of people during deployment. 

See the following Upgrade Readiness resources to help with app inventory, driver compatibility issues, and usage information:
* [Manage Windows Upgrades with Upgrade Readiness](https://go.microsoft.com/fwlink/?linkid=860255) - Learn about the tools to help you plan and manage the upgrade process end to end, which allow you to adopt new Windows releases more quickly.
* [Configure Windows diagnostic data](https://go.microsoft.com/fwlink/?linkid=859970) - Find out about the importance of Windows diagnostic data and how Microsoft protects that data.

> [!NOTE]
> Upgrade Readiness may not be able to assess compatibility for custom and line-of-business (LOB) apps in an organization.

#### Language packs
In-place upgrades have have limitations when it comes to language packs. The language stays consistent throughout the upgrade. Verify the language version and make sure it stays consistent. For example, Windows 7 with English as the default won’t change when upgraded to Windows 10. For more info, see:
* [Default language pack on your OS](https://go.microsoft.com/fwlink/?linkid=860282)
* [Finding language packs on each Windows 10 deployment](https://go.microsoft.com/fwlink/?linkid=860283)

For a Microsoft 365 powered device, you'll also need to download Office 365 ProPlus language packs that applies to the client. These come in 32-bit (x86) or 64-bit (x64). A specific language must be installed as the default. You can install other languages later. For more info, see:
* [Choose between 64-bit or 32-bit version of Office](https://go.microsoft.com/fwlink/?linkid=862361) - Helps you decide which version of Office is right for you.
* [Language accessory pack for Office](https://go.microsoft.com/fwlink/?linkid=860280) - Follow the steps to install the language accessory pack for Office.
* [Add an additional language pack](https://go.microsoft.com/fwlink/?linkid=860281) - Get step-by-step info on adding a language or setting language preferences in Office.

### Step 3: Governance and business processes

#### Windows as a service
Windows 10 introduced the concept of Windows as a service. This greatly changes the frequency and style of updates to Windows. Instead of new versions being released every 3-5 years, a more incremental model is used where two smaller updates (Feature Updates) are released yearly. For more info, see:
* [Windows as a service on the Windows IT Pro Center](https://www.microsoft.com/itpro/windows-10/windows-as-a-service)
* [Overview of Windows as a service](https://go.microsoft.com/fwlink/?linkid=860288)
* [Update Windows 10 in the enterprise](https://go.microsoft.com/fwlink/?linkid=860285)

#### Pilot users and deployment rings
Be sure to have a pilot group of users selected from different parts of the business. If you have Microsoft 365 powered devices, Windows 10 and Office 365 ProPlus users should be in these deployment rings. This affects future Windows updates as well (including features and quality). You need to create and edit device collections by deployment rings to help minimize the effect on network bandwidth and simplify future updates. 

For the group of pilot users, create a device collection on Configuration Manager. The list of devices should correspond to the list of the first users upgraded to Windows 10. 

**Windows 10 deployment rings**

There are three servicing channels for OS deployment rings:
* Windows Insider Program - Provides organizations with the opportunity to test and provide feedback on features that are shipped in the next feature update.
* Semi-Annual Channel - Provides new functionality with twice-per-year feature update releases. Organizations can choose when to deploy updates from the Semi-Annual Channel.
* Long-Term Servicing Channel (LTSC) - Used for specialized devices and receives new feature releases about every three years.

For more info, see:
* [Windows Insider Program, Semi-Annual Channel, and Long-Term Servicing Channel](https://go.microsoft.com/fwlink/?linkid=860293)
* [Build deployment rings for Windows 10 updates](https://go.microsoft.com/fwlink/?linkid=860294)
* [Manage software updates using Intune in Azure Portal](https://docs.microsoft.com/intune/windows-update-for-business-configure)

**Office 365 ProPlus**

For Microsoft 365 powered devices, you must also be able to support the six-month update channel for both IT and business users. One way to do so is to have three groups:
* Current Channel
* Deferred Channel
* First-release for Deferred Channel

Each group has different configuration files, as users from the Current Channel are used as a pilot to test earlier updates. For more info, see:
* [Update process for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860299)
* [Manage updates to Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860300)
* [Configure update settings for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860301)
* [Update channels for Office 365 ProPlus](https://go.microsoft.com/fwlink/?linkid=860302)
* [Version and build numbers of update channel releases](https://go.microsoft.com/fwlink/?linkid=860304)

For more info, see [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md).

## Phase 2: Testing phase
Once you've completed the scenarios and requirements in [Step 1: Consideration phase](#step-1-consideration-phase), you can move to this stage.
* [Networking](#step-1-networking)
* [Identity](#step-2-identity)
* [Client readiness](#step-3-client-readiness)
* [System Center Configuration Manager](#step-4-system-center-configuration-manager)
* [Diagnostic data](#step-5-diagnostic-data)

### Step 1: Networking
Ports to the client need to be opened for Office 365 ProPlus (for a Microsoft 365 powered device) and Configuration Manager. For more details about setting up your Microsoft 365 Enterprise networking infrastructure, see [Phase 1: Networking](networking-infrastructure.md).

When setting up your networking infrastructure as part your in-place upgrade, make sure you complete these steps:
1. Read the best practices for [network planning and improving migration performance for Office 365](http://go.microsoft.com/fwlink/?LinkId=733655).
2. [Plan for network devices that connect to Office 365 services](http://go.microsoft.com/fwlink/?LinkId=733652).
3. [Review network impact of directory synchronization](http://go.microsoft.com/fwlink/?LinkId=733652).
4. Calculate the number of clients to use per IP address and understand [Network Address Translation (NAT) support with Office 365](http://go.microsoft.com/fwlink/?LinkId=733653) and how it impacts the number of users and client devices you can serve with a single IP address.
5. If your organization restricts computers on your network from connecting to the Internet, you'll need to understand the [endpoints (fully qualified domain names (FQDNs), ports, URLs, IPv4, and IPv6 address ranges)](http://go.microsoft.com/fwlink/?LinkID=280129) that you should include in your outbound allow lists to ensure your computers can successfully use Office 365 services.
6. [Create domain name system records for Office 365 at any Domain Name System hosting provider](http://go.microsoft.com/fwlink/?LinkId=733656).
7. [Reduce mail exchange (MX) DNS record time to live (TTL) value](http://go.microsoft.com/fwlink/?LinkId=733656).

### Step 2: Identity
Intelligent security for Microsoft 365 Enterprise, in which the right users have access to the right resources with an appropriate level of access, begins with identity management. For more details about setting up your Microsoft 365 Enterprise identity infrastructure, see [Phase 2: Identity](identity-infrastructure.md).

When setting up your identity infrastructure as part of your in-place upgrade, make sure you complete these tasks:
1. [Add a domain and users to Office 365](http://go.microsoft.com/fwlink/?LinkID=526338).
2. [Install and run the Office 365 IdFix tool](http://go.microsoft.com/fwlink/?LinkId=733662), which scans your on-premises Active Directory environment and identifies problems that might impact directory synchronization and slow your migration to Office 365.
3. Configure Active Directory for directory synchronization with Office 365 and [integrate on-premises directories with Azure AD](http://go.microsoft.com/fwlink/?LinkId=733661).
4. [Prepare to provision users through directory synchronization to Office 365](http://go.microsoft.com/fwlink/?LinkId=733659).
5. Know the [prerequisites for Azure AD Connect](http://go.microsoft.com/fwlink/?LinkId=733663), then install and run the Azure AD Connect tool to synchronize your on-premises Active Directory to the Azure AD service used by Office 365.
6. Determine custom installation of Azure AD Connect (full version of SQL Server for directory synchronization, if required).
7. [Integrate your on-premises identities with Azure AD](http://go.microsoft.com/fwlink/?LinkID=733485).
8. [Sync a list of required attributes with AD Connect](https://go.microsoft.com/fwlink/?linkid=860363) to get all the features in Office 365 and Windows 10.
9. Activate Windows 10 Enterprise licenses, which are checked based on Azure AD credentials.

    This provides a systematic way to assign licenses to end users and groups in your organization. For more info, see [Windows 10 Subscription Activation](https://go.microsoft.com/fwlink/?linkid=860365) and [Deploy Windows 10 licenses](https://go.microsoft.com/fwlink/?linkid=860367).

### Step 3: Client readiness

#### System requirements for Office 365
Confirm that Windows 10 works with Office 365. Be sure you're using the latest OS version and browsers with Office 365 and have updated them with the latest service packs. For more info on Office requirements, see [System requirements for Office](http://go.microsoft.com/fwlink/?LinkID=394412).

### Step 4: System Center Configuration Manager
See [System Center Configuration Manager](#system-center-configuration-manager).

### Step 5: Diagnostic data
Microsoft uses diagnostic data to help keep Windows devices secure by identifying malware trends and other threats and to help us improve the quality of Windows and Microsoft services. You must ensure that the diagnostics service is enabled at a minimum level of Basic on all endpoints in your organization. **By default, this service is enabled and set to the Enhanced level.** However, it’s good practice to check and ensure that they are receiving sensor data. Setting levels through policies overrides device-level settings. 

**Windows 10 operating system diagnostic data levels**

You can configure your operating system diagnostic data settings using the management tools you’re already using, such as Group Policy, MDM, or Windows Provisioning. You can also manually change your settings using Registry Editor. Setting your diagnostic data levels through a management policy overrides any device level settings.

Use the appropriate value in the table below when you configure the management policy.

| Level | Data gathered | Value |
|:--- |:--- |:--- |
| Security | Security data only. | 0 |
| Basic | Security data, and basic system and quality data. | 1 |
| Enhanced | Security data, basic system and quality data, and enhanced insights and advanced reliability data. | 2 |
| Full | Security data, basic system and quality data, enhanced insights and advanced reliability data, and full diagnostics data. | 3 |

You can enable diagnostics data through these methods:
* Microsoft Intune - If you plan to use Intune to manage your devices, you can create a configuration policy to enable diagnostic data by configuring the <a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a> system policy. For more info on setting up configuration policies, see [Manage settings and features on your devices with Microsoft Intune policies](https://aka.ms/intuneconfigpolicies).
* Registry Editor - You can use the Registry Editor to manually enable diagnostic data on each device in your organization, or write a script to edit the registry. If a management policy already exists, such as Group Policy or MDM, it will override this registry setting.
* Group Policy - If you do not plan to enroll devices in Intune, you can use a Group Policy object to set your organization’s diagnostic data level.
* Command prompt - You can set Windows 10 diagnostics data and service to automatically start with the command prompt. This method is best if you are testing the service on only a few devices. Enabling the service to start automatically with this command will not configure the diagnostic data level. If you have not configured a diagnostic data level using management tools, the service will operate with the default Enhanced level.

See [Configure Windows diagnostic data in your organization](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization) to learn more about Windows diagnostic data and how you can enable it based on the method that you choose.

## Phase 3: Deployment phase
When ready, complete these:
* [In-place upgrade to Windows 10 Enterprise](#31-in-place-upgrade-to-windows-10-enterprise)
* [Windows Defender Antivirus](#32-windows-defender-antivirus)

### Step 1: In-place upgrade to Windows 10 Enterprise
1. Integrate System Center Configuration Manager with Microsoft Deployment Tool.

    Be sure to use the Microsoft Deployment Toolkit (MDT) in conjunction with Configuration Manager when deploying an updated version of Windows 10. MDT brings Zero Touch Installation and Light Touch Installation enhancements to help with deployments at no cost to the customer. For more info, see:
    * [Download the latest MDT](https://go.microsoft.com/fwlink/?linkid=860465)
    * [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://go.microsoft.com/fwlink/?linkid=860466)

2. Prepare for zero touch installation.

    As part of zero touch installation, you are responsible for preparing the following:
    * Configuration Manager service accounts
    * Active Directory permissions
    * Source folder structure

    Then, [integrate Configuration Manager with MDT](https://go.microsoft.com/fwlink/?linkid=860035).

3. Create a custom Windows Preinstallation Environment boot image.

    Windows Preinstallation Environment (PE) is a pre-installation environment required for OS deployments. It’s used to prepare a client machine for Windows installation, to copy disk images from a network file server, and to initiate Windows Setup. It’s used for Windows 10 Enterprise editions. For more info, see:
    * [Overview of Windows PE](https://go.microsoft.com/fwlink/?linkid=860468)
    * [Windows PE features, hardware requirements, and limitations](https://go.microsoft.com/fwlink/?linkid=860469)
    * [Create a custom Windows PE boot image with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860470)

4. Add a Windows 10 OS upgrade image.

    You need to create a Windows 10 reference image with MDT (as needed). Reference images are the foundation of what each of the client machine’s OS looks like. The image should be in a separate folder located with the already-mounted ISO file. The task sequence looks for and then runs “setup.exe”. 

    Follow the steps to create and add a Windows 10 OS upgrade image on Configuration Manager:
    * [Create a Windows 10 reference image](https://go.microsoft.com/fwlink/?linkid=860500)
    * [Add a Windows 10 OS image using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860501)

5. Create an app to deploy with Windows 10.

    For a Microsoft 365 powered device, you can deploy Office 365 ProPlus with Windows 10 Enterprise using Configuration Manager. You can also add other apps as needed.

    To deploy Office 365 ProPlus, follow the steps in [Phase 4: Office 365 ProPlus infrastructure for Microsoft 365 Enterprise](office365proplus-infrastructure.md). During this phase, make sure you complete these steps:
    
    1. Download the Office 2016 Deployment Tool (ODT) in conjunction with Configuration Manager to help with Office 365 ProPlus deployments. 
    2. Edit the configuration XML file to fit specific deployment needs (like version, language, and product element). 
    
    You can then create apps with Configuration Manager. For more info, see:
    * [Configuration options for ODT](https://go.microsoft.com/fwlink/?linkid=860504)
    * [Create apps in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=761079)
    * [Deploy Office 365 ProPlus with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860506)

6. Add drivers to a Windows 10 deployment using Windows PE.

    Network drivers need to be created for both Windows PE and Windows 10 to connect deployment shares and storage drivers with local storage on a client computer. Use Configuration Manager to create these drivers required for deployment. For more info, see [Add drivers to a Windows 10 deployment with Windows PE using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860036).

7. Create a task sequence.

    A task sequence (a collection of commands) is required for MDT Lite Touch Installation (LTI). You need to create and then edit the task sequence for optimal deployment experience. One of the configurations enable support for Unified Extensible Firmware Interface (UEFI). The UEFI environment is a minimal boot OS where devices are booted and the Windows 10 OS runs. For more info, see:
    * [Overview of Windows Boot Manager](https://go.microsoft.com/fwlink/?linkid=860696)
    * [Create the task sequence in Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697)

8. Finalize the OS configuration for Windows 10 deployment.

    **To finalize the OS configuration**

    1. Enable MDT monitoring
    2. Create and share the Logs folder
    3. Configure the rules
    4. Distribute content to the distribution point (a server running Configuration Manager)
    5. Create a deployment for the task sequence

   For more info, see [Finalize OS configuration with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

9. Deploy the Windows 10 Enterprise image to a UEFI machine.

    For more info, see [Deploy Windows 10 using Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860697).

10. Monitor the Windows 10 deployment.

    Use Configuration Manager and MDT to monitor your deployment. Deployment Workbench enables access to the computer remotely using the Diagnostics and Recovery Toolset (DaRT) (optional). Deployments can be monitored in Configuration Manager. For more info, see [Monitor the Windows 10 deployment with Configuration Manager](https://go.microsoft.com/fwlink/?linkid=860705).

### Step 2: Windows Defender Antivirus
See [Enable Windows 10 Enterprise security features > Windows Defender Antivirus](windows10-enable-security-features.md#windows-defender-antivirus)

-->
