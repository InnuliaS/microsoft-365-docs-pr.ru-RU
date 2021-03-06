---
title: Многофакторная проверка подлинности Microsoft 365 Enterprise тестовая среда
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
description: Настройка многофакторной проверки подлинности с помощью текстовых сообщений, отправленных на смарт-телефон в тестовой среде Microsoft 365 Enterprise.
ms.openlocfilehash: e26fb7470e01397266f5f424ee45941a79a2940c
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819380"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Многофакторная проверка подлинности для тестовой среды Microsoft 365 корпоративный

*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 корпоративный и Office 365 корпоративный.*

Для дополнительного уровня безопасности при входе в Microsoft 365 или любой другой службы или приложения, использующего клиент Azure AD для вашей подписки, вы можете включить многофакторную проверку подлинности Azure, которая требует больше имени пользователя и пароля, чтобы проверить учетную запись. 

При использовании многофакторной проверки подлинности пользователям необходимо подтвердить телефонный звонок, ввести код проверки, отправленный в текстовом сообщении, или проверить проверку подлинности с помощью приложения на смарт-телефонах после правильного ввода паролей. Только после этого он сможет войти в свою учетную запись. 
  
В этой статье описывается, как включить и протестировать проверку подлинности на основе текстовых сообщений для конкретной учетной записи пользователя.
  
Настройка многофакторной проверки подлинности для учетной записи в тестовой среде Microsoft 365 Enterprise состоит из двух этапов:
  
1. Создайте среду тестирования Microsoft 365 корпоративный.
    
2. Включение и проверка многофакторной проверки подлинности для учетной записи User 2.

3. Включение и тестирование многофакторной проверки подлинности с помощью политики условного доступа (необязательно).

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Перейдите к разделу [Test Lab Guide](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) для визуальной карты со всеми статьями руководства по лаборатории тестирования Microsoft 365 корпоративный.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Этап 1. Создание собственной тестовой среды Microsoft 365 корпоративный

Если вы только хотите протестировать многофакторную проверку подлинности в упрощенном виде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Если вы хотите протестировать многофакторную проверку подлинности на имитируемом предприятии, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Для тестирования многофакторной проверки подлинности не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов для леса доменных служб Active Directory (AD DS). Она показана здесь лишь для того, чтобы вы могли проверить многофакторную проверку подлинности и поэкспериментировать с этим компонентом в типичной для организаций среде. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Этап 2. Включение и проверка многофакторной проверки подлинности для учетной записи User 2

Чтобы включить многофакторную проверку подлинности для учетной записи User 2, сделайте следующее:
  
1. Откройте отдельный частный экземпляр браузера, перейдите в центр администрирования Microsoft 365 ( [https://portal.microsoft.com](https://portal.microsoft.com) ), а затем войдите с помощью учетной записи глобального администратора.
    
2. На панели навигации слева выберите элементы **Пользователи > Активные пользователи**.
    
3. В области активные пользователи выберите **многофакторную проверку подлинности**.
    
4. В списке выберите учетную запись **пользователя 2** .
    
5. В разделе **пользователь 2** в разделе **быстрые действия**нажмите кнопку **включить**.
    
6. В диалоговом окне **Сведения о включении многофакторной проверки подлинности** нажмите **Включить проверку Multi-Factor Auth**.
    
7. В диалоговом окне **успешное обновление** нажмите кнопку **Закрыть**.
    
8. На вкладке **центра администрирования Microsoft 365** щелкните значок учетной записи пользователя в правом верхнем углу, а затем нажмите **выйти**.
    
9. Закройте окно браузера.
   
Чтобы настроить отправку текстового сообщения для проверки учетной записи User 2 и проверить ее, сделайте следующее:
  
1. Откройте новый частный экземпляр браузера.
    
2. Перейдите на портал Office 365 ( [https://portal.office.com](https://portal.office.com) ) и войдите в систему, используя имя и пароль учетной записи пользователя 2.
    
3. После входа вам будет предложено настроить учетную запись для получения дополнительных сведений. Нажмите кнопку **Далее**.
    
4. На странице **Дополнительная проверка безопасности**: 
    
   - Выберите свою страну или регион.
    
   - Введите номер телефона, на который будут отправляться текстовые сообщения.
    
   - В поле **метод**нажмите кнопку **отправить код по текстовому сообщению**.
    
5. Нажмите кнопку **Далее**.
    
6. Введите код проверки из текстового сообщения, полученного на смартфон, и нажмите **Проверить**.
    
7. На странице **Шаг 3: сохраните существующие приложения** нажмите кнопку **Готово**.
    
8. If this is the first time you signed in with the User 2 account, you are prompted to change the password. Type the original password and a new password twice, and then click **Update password and sign in**. Record the new password in a secure location.
    
    Вы должны увидеть портал Office для пользователя 2 на вкладке **Microsoft Office Главная** в браузере.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Этап 3: Включение и тестирование многофакторной проверки подлинности с помощью политики условного доступа

*Этот этап можно использовать только для тестовой среды Microsoft 365 Enterprise.*

На этом этапе включается многофакторная проверка подлинности для учетной записи пользователя 3 с использованием политики группы и условного доступа.

Затем создайте новую группу с именем Мфаусерс и добавьте к ней учетную запись пользователя 3.

1. На вкладке **центра администрирования Microsoft 365** щелкните **группы** в левой области навигации, а затем щелкните **группы**.
2. Нажмите кнопку **Добавить группу**.
3. В области **Выбор типа группы** выберите **Безопасность**, а затем нажмите кнопку **Далее**.
4. В области **Настройка основных принципов** нажмите кнопку **создать группу**, а затем нажмите кнопку **Закрыть**.
5. В области **Проверка и Добавление группы** введите **мфаусерс**, а затем нажмите кнопку **Далее**.
6. В списке групп выберите группу **мфаусерс** .
7. В области **мфаусерс** щелкните **элементы**, а затем щелкните **Просмотр всех элементов и управление ими**.
8. В области **мфаусерс** нажмите кнопку **Добавить участников**, выберите учетную запись **пользователя 3** , а затем нажмите кнопку **сохранить > закрыть > закрыть**.

Затем создайте политику условного доступа, которая будет требовать многофакторную проверку подлинности для членов группы Мфаусерс.

1. На новой вкладке браузера перейдите в раздел [https://portal.azure.com](https://portal.azure.com) .
2. Щелкните элемент **Azure Active Directory > безопасность > условный доступ**.
3. В области **Условный доступ – политики** щелкните **создать политику**.
4. В области **создать** введите **MFA для учетных записей пользователей** в **поле имя**.
5. В разделе **назначения** выберите **Пользователи и группы**.
6. На вкладке **включить** в области **Пользователи и группы** щелкните **Выбор пользователей и групп > пользователи и группы > выбрать**.
7. В области **Выбор** выберите группу **мфаусерс** и нажмите кнопку **выбрать > готово**.
8. В разделе **элементы управления доступом** в области **создать** нажмите кнопку **предоставить**.
9. В области **предоставление** выберите пункт **требовать многофакторную проверку подлинности**, а затем нажмите кнопку **выбрать**.
10. В области **создать** выберите пункт **включить политику**, а **затем нажмите кнопку** **создать**.
11. Закройте вкладки **портал Azure** и **центр администрирования Microsoft 365** .

Чтобы проверить эту политику, выйдите из учетной записи пользователя 3 и войдите в нее. Вам будет предложено настроить MFA. В этом примере показано, что применяется политика Мфаусерс.

Чтобы получить сведения и ссылки для развертывания многофакторной проверки подлинности в рабочей среде, просмотрите этап " [Настройка многофакторной проверки подлинности](identity-secure-user-sign-ins.md#identity-mfa) " на этапе идентификации.
    
## <a name="next-step"></a>Следующий шаг

Ознакомьтесь с дополнительными функциями и возможностями [идентификации](m365-enterprise-test-lab-guides.md#identity) в тестовой среде.

## <a name="see-also"></a>См. также

[Шаг 2. Идентификация](identity-infrastructure.md)

[Руководства по лаборатории тестирования для Microsoft 365 корпоративный](m365-enterprise-test-lab-guides.md)

[Развертывание Microsoft 365 корпоративный](deploy-microsoft-365-enterprise.md)

[Документация по Microsoft 365 корпоративный](https://docs.microsoft.com/microsoft-365-enterprise/)
