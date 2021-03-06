---
title: Подготовка пробной лабораторной среды Майкрософт по защите от угроз
description: Подготовка подписывания заинтересованного лица, временных шкал, вопросов среды и порядка внедрения при настройке испытательной лабораторной среды Майкрософт по защите от угроз
keywords: Пробная версия для пробной подготовки, развертывание, подготовка, заинтересованные лица, временная шкала, среда, конечная точка, сервер, управление, принятие
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: da0fd99aaa533c6e4f65b5b279adcd9a4b648c9c
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049631"
---
# <a name="prepare-your-microsoft-threat-protection-trial-lab-environment"></a>Подготовка пробной лабораторной среды Майкрософт по защите от угроз

**Область применения:**
- Защита от угроз (Майкрософт)

Создание пробной лабораторной среды Майкрософт для защиты от угроз и развертывание выполняется в три этапа:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Подготовка пробной лабораторной среды Майкрософт по защите от угроз" />
      <br/>Этап 1: подготовка</a><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Настройка пробной лабораторной среды Майкрософт для защиты от угроз" />
      <br/>Этап 2: Настройка</a><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft Threat Protection pillar" title="Настройка каждого из принципов защиты от угроз Майкрософт и встроенных конечных точек" />
      <br/>Этап 3: Настройка встроенного &</a><br>
</td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
  </tr>
</table>

В настоящее время вы находитесь на этапе подготовки.


Подготовка — это ключ к любому успешному развертыванию. В этом разделе вы узнаете, что нужно учесть при подготовке к созданию пробной лабораторной среды для развертывания Microsoft Threat protection.

## <a name="prerequisites"></a>Необходимые компоненты
Сведения о лицензировании, требованиях к оборудованию и программному обеспечению, а также другие параметры конфигурации для подготовки и использования защиты от угроз Майкрософт. Ознакомьтесь с минимальными требованиями для [защиты от угроз Майкрософт](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites?view=o365-worldwide), [Microsoft Defender atp](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), [Microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Заинтересованные стороны и подпись
Следующий раздел служит для определения всех заинтересованных лиц, вовлеченных в проект, которые могут потребоваться для выхода, проверки или информирования, даже для оценки или пробного использования.

>[!NOTE]
>Не все организации могут иметь такие роли в организации безопасности. В таком случае обратитесь к специалистам по ознакомлению и утверждению аккаунтабилитиес.

Добавьте заинтересованных лиц в приведенную ниже таблицу в соответствии с требованиями Организации.

-   Таким образом, для этого проекта следует выполнить вход.

-   R = просмотр этого проекта и предоставление входных данных

-   I = информирование о проекте

| Имя                 | Role                                                                                                                                                                                                          | Action |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Введите имя и адрес электронной почты | **Генеральный директор по безопасности информационных технологий (Цисо)** *— руководитель, который выступает в качестве спонсора в Организации для развертывания нового решения.*                                                  | МОГЛИ     |
| Введите имя и адрес электронной почты | **Head of кибератак оборонного центра (кдок)** в *группе кдок, ответственной за определение того, как это изменение выровнено с процессами в группе "операции безопасности клиентов".*       | МОГЛИ     |
| Введите имя и адрес электронной почты | **Архитектор по безопасности** *— это представитель группы безопасности, ответственный за определение того, как это изменение согласуется с основной архитектурой безопасности в Организации.*                         | R      |
| Введите имя и адрес электронной почты | **Архитектор рабочего места** *— представитель ИТ-отдела, ответственный за определение того, как это изменение выровнено с основной архитектурой рабочего места в Организации.*                             | R      |
| Введите имя и адрес электронной почты | **Аналитика безопасности** *— это представитель группы кдок, который может предоставлять входные данные о возможностях обнаружения, взаимодействии с пользователем и общей целесообразности этого изменения с точки зрения безопасности.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Подготовка Azure Active Directory
Пропустите этот шаг, если вы уже включили синхронизацию между Active Directory и Azure Active Directory в локальной среде. Изучите существующую документацию по рекомендациям из Azure Active Directory. Следующие действия оптимизированы для оценки защиты от угроз Майкрософт.

1. Перейдите на портал [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > **Azure AD Connect**. 
![Изображение страницы портала Azure Active Directory](../../media/mtp-eval-1.png) <br> 

2. Щелкните **скачать** из **Microsoft Azure Active Directory Connect** и перенесите его на контроллер домена.
![Изображение страницы скачивания Azure Active директору Connect](../../media/mtp-eval-2.png) <br>

3. На контроллере домена следуйте указаниям мастера подключения Azure Active Directory. Ознакомьтесь с условиями лицензионного соглашения и заявлением о конфиденциальности и установите флажок, если вы согласны. Нажмите кнопку **Продолжить**.
![Изображение страницы приветствия Azure AD Connect](../../media/mtp-eval-3.png) <br>

4. Перейдите в раздел **Экспресс — параметры**.
![Изображение страницы "Экспресс-параметры"](../../media/mtp-eval-4.png) <br>

5. Введите свои учетные данные глобального администратора. Нажмите кнопку **Далее**.
![Изображение страницы "подключение к Azure AD", на которой необходимо ввести учетные данные глобального администратора](../../media/mtp-eval-5.png) <br>

6. Введите учетные данные администратора доменных служб Active Directory. Нажмите кнопку **Далее**.
![Изображение страницы "подключение к доменным СЛУЖБам Active Directory", на которой необходимо ввести учетные данные](../../media/mtp-eval-6.png) <br>

7. Нажмите кнопку **установить** , чтобы подтвердить настройку.
![Изображение страницы "подтверждение конфигурации"](../../media/mtp-eval-7.png) <br>

8. Поздравляем, вы успешно настроили Azure Active Directory Connect.
![Изображение успешной настройки страницы подключения Azure Active Directory](../../media/mtp-eval-8.png) <br>

Теперь вы можете [Добавить пользователей и группы в Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) и [настроить политику SAM – R](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc).  


## <a name="configuration-order"></a>Порядок настройки
В таблице ниже показано, как настроить компоненты защиты от угроз Майкрософт для развертывания пробной лабораторной среды.

| Компонент                               | Описание                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Ранг заказа конфигурации |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| Office 365 Advanced Threat Protection| Office 365 ATP защищает вашу организацию от вредоносных угроз, исносящихся к сообщениям электронной почты, ссылкам (URL-адресам) и средствам для совместной работы. <br> [Подробнее.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)                                                                                                                                                                                                                                             | 1,1                   |
|Расширенная защита от угроз Azure|Azure ATP использует сигналы Active Directory для определения, обнаружения и исследования сложных угроз, скомпрометированных удостоверений и действий, которые вы направляете в Организации. <br> [Подробнее](https://docs.microsoft.com/azure-advanced-threat-protection/).| 2 |
|Microsoft Cloud App Security| Microsoft Cloud App Security — это брокер безопасности облачного доступа (КАСБ), работающий в нескольких облаках. Он обеспечивает широкие возможности просмотра и управления путешествием данных, а также интеллектуальную аналитику для выявления и борьбы киберугрозами среди всех облачных служб. <br> [Подробнее](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |4                   |
|Advanced Threat Protection в Microsoft Defender | Функции обнаружения угроз и реагирования на них для конечных точек в ATP в Microsoft Defender обеспечивают обнаружение расширенных атак, работают в режиме практически реального времени, а результаты, предоставляемые такими функциями, можно использовать в качестве основания для выполнения тех или иных действий. Аналитики систем безопасности могут эффективно определять приоритеты предупреждений, получать полную картину всех возможных брешей в системе безопасности, а также предпринимать действия по реагированию для устранения угроз. <br> [Подробнее.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Следующий этап
|||
|:-------|:-----|
|![Этап 2: Настройка](../../media/setup.png) <br>[Этап 2: Настройка](setup-mtpeval.md) | Настройка пробной лабораторной среды Майкрософт для защиты от угроз

