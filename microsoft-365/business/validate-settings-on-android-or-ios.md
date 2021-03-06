---
title: Проверка параметров защиты приложений на устройствах с Android или iOS
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
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: f3433b6b-02f7-447f-9d62-306bf03638b0
description: Узнайте, как проверить параметры защиты приложений Microsoft 365 бизнес премиум на устройствах с Android или iOS.
ms.openlocfilehash: d4b8ec3ff3a15c25133b20d437249611530977a5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403377"
---
# <a name="validate-app-protection-settings-on-android-or-ios-devices"></a>Проверка параметров защиты приложений на устройствах с Android или iOS

Следуйте инструкциям, приведенным в следующих разделах, чтобы проверить параметры защиты приложений на устройствах с Android или iOS.
  
## <a name="android"></a>Android
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Проверка работы параметров защиты приложений на устройствах пользователя

[Настроив конфигурацию приложений для устройств с Android](app-protection-settings-for-android-and-ios.md) для защиты приложений, проверьте, работают ли выбранные параметры, с помощью инструкций ниже. 
  
Сначала убедитесь, что политика применяется к приложению, в котором вы собираетесь проверить его.
  
1. В [центре администрирования](https://portal.office.com)Microsoft 365 Business Premium перейдите в раздел **политики** \> **изменения политики**.
    
2. Выберите **Политика приложений для Android** для параметров, созданных при установке, или другую созданную политику и убедитесь, что она применяется для Outlook, например. 
    
    ![Shows all the apps for which this policy protects files.](../media/b3be3ddd-f683-4073-8d7a-9c639a636a2c.png)
  
### <a name="validate-require-a-pin-or-a-fingerprint-to-access-office-apps"></a>Проверка запроса ПИН-кода или отпечатка пальца для доступа к приложениям Office

На панели **Изменение политики** рядом с параметром **Управление доступом к документам Office** нажмите **Изменить**, разверните раздел **Контроль над доступом пользователей к файлам Office с мобильных устройств** и убедитесь, что **включен** параметр **Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office**.
  
![Убедитесь, что для параметра требовать ПИН-код или отпечаток для доступа к приложениям Office задано значение Вкл.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. На устройстве с Android пользователя откройте Outlook и войдите в систему, используя учетные данные пользователя Microsoft 365 Business Premium.
    
2. Кроме того, вам будет предложено ввести ПИН-код или использовать отпечаток пальца.
    
    ![Enter a PIN on your Android device to access Office apps.](../media/9e8ecfee-8122-4a3a-8918-eece80344310.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Проверка сброса ПИН-кода после нескольких неудачных попыток

В области **Политика изменения** нажмите кнопку **изменить** рядом с **элементом Управление доступом к документам Office**, разверните **Управление доступом пользователей к файлам Office на мобильных устройствах**и убедитесь, что **ПИН-код сбрасывается после количества неудачных попыток** , для которых задано количество неудачных попыток. По умолчанию это 5. 
  
1. На устройстве с Android пользователя откройте Outlook и войдите в систему, используя учетные данные пользователя Microsoft 365 Business Premium.
    
2. Введите неправильный ПИН-код указанное в политике количество раз. Вы увидите сообщение о том, что **достигнуто максимальное количество попыток ПИН-** кода, чтобы сбросить ПИН-код. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fca6fcb4-bb5c-477f-af5e-5dc937e8b835.png)
  
3. Нажмите кнопку **Сброс ПИН-кода**. Вам будет предложено войти в систему, используя учетные данные пользователя Microsoft 365 Бизнес Premium, а затем указать новый ПИН-код.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Проверка принудительного сохранения всех рабочих файлов в OneDrive для бизнеса

На панели **Изменение политики** рядом с параметром **Защита от потери или кражи устройств** нажмите **Изменить**, разверните раздел **Защита рабочих файлов при краже или потере устройств** и убедитесь, что **включен** параметр **Обеспечить принудительное сохранение всех рабочих файлов пользователей в OneDrive для бизнеса**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. На устройстве с Android пользователя откройте Outlook и войдите с помощью учетных данных пользователя Microsoft 365 Business Premium и введите ПИН-код по запросу.
    
2. Откройте сообщение электронной почты с вложением и коснитесь значка со стрелкой вниз рядом со сведениями о вложении.
    
    ![Tap the down arrow next to an attachment to try to save it.](../media/b22573bb-91ce-455f-84fa-8feb2846b117.png)
  
    В нижней части экрана вы увидите команду **сохранить на устройстве** . 
    
    ![Warning text that indicates cannot save a file locally to an Android.](../media/52ca3f3d-7ed0-4a52-9621-4872da6ea9c5.png)
  
    > [!NOTE]
    > Сохранение в OneDrive для бизнеса сейчас не включено для Android, поэтому вы можете только увидеть, что локальное сохранение заблокировано. 
  
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Проверка требования повторного входа при неактивности приложений Office в течение указанного времени

В области " **изменение политики** " выберите пункт **изменить** рядом с **элементом Управление доступом к документам Office**, разверните **Управление доступом пользователей к файлам Office на мобильных устройствах**и убедитесь, что пользователям требуется **повторно входить в систему после неактивности для приложений Office** в течение определенного количества минут. По умолчанию это 30 минут. 
  
1. На устройстве с Android пользователя откройте Outlook и войдите с помощью учетных данных пользователя Microsoft 365 Business Premium и введите ПИН-код по запросу.
    
2. Вы должны увидеть папку входящих сообщений в Outlook. Оставьте устройство с Android в неактивном состоянии в течение 30 минут (или другого количества времени, превышающего указанное в политике). Скорее всего, экран устройства погаснет.
    
3. Снова получите доступ к Outlook на устройстве с Android.
    
4. Вам будет предложено ввести ПИН-код, прежде чем вы сможете снова получить доступ к Outlook.
    
### <a name="validate-protect-work-files-with-encryption"></a>Проверка защиты рабочих файлов шифрованием

На панели **Изменение политики** рядом с параметром **Защита от потери или кражи устройств** нажмите **Изменить**, разверните раздел **Защита рабочих файлов при краже или потере устройств** и убедитесь, что параметр **Шифровать рабочие файлы**  **включен**, а параметр **Обеспечить принудительное сохранение всех рабочих файлов пользователей в OneDrive для бизнеса**  **выключен**.
  
1. На устройстве с Android пользователя откройте Outlook и войдите с помощью учетных данных пользователя Microsoft 365 Business Premium и введите ПИН-код по запросу.
    
2. Откройте сообщение электронной почты, которое содержит несколько вложенных файлов изображений.
    
3. Коснитесь значка со стрелкой вниз рядом с вложением, чтобы сохранить его.
    
    ![Tap the down arrow to save the figure file to the Android device.](../media/08a9e21e-4022-45d5-acff-59cface651e7.png)
  
4. Вам будет предложено разрешить приложению Outlook доступ к фотографиям, мультимедийным и прочим файлам на устройстве. Нажмите **Разрешить**.
    
5. Внизу экрана выберите команду **Сохранить на устройстве** и откройте приложение **Галерея**. 
    
6. Вы должны увидеть в списке зашифрованную фотографию (или несколько, если сохранили несколько вложенных файлов изображений). В списке изображений она может отображаться в виде серого квадрата, в центре которого изображен белый восклицательный знак внутри белой окружности.
    
    ![An encrypted image file in the Gallery app.](../media/25936414-bd7e-421d-824e-6e59b877722d.png)
  
## <a name="ios"></a>iOS
  
### <a name="check-that-the-app-protection-settings-are-working-on-user-devices"></a>Проверка работоспособности параметров защиты приложений на пользовательских устройствах

[Настроив конфигурацию приложений для устройств с iOS](app-protection-settings-for-android-and-ios.md) для защиты приложений, проверьте, работают ли выбранные параметры, с помощью инструкций ниже. 
  
Сначала убедитесь, что политика применяется к приложению, в котором вы собираетесь проверить его.
  
1. В [центре администрирования](https://portal.office.com)Microsoft 365 Business Premium перейдите в раздел **политики** \> **изменения политики**.
    
2. Выберите **Политика приложений для iOS** для параметров, созданных при установке, или другую созданную политику и убедитесь, что она применяется для Outlook, например. 
    
    ![Shows all the apps for which this policy protects files.](../media/842441b8-e7b1-4b86-9edd-d94d1f77b6f4.png)
  
### <a name="validate-require-a-pin-to-access-office-apps"></a>Проверка запроса ПИН-кода для доступа к приложениям Office

На панели **Изменение политики** рядом с параметром **Управление доступом к документам Office** нажмите **Изменить**, разверните раздел **Контроль над доступом пользователей к файлам Office с мобильных устройств** и убедитесь, что **включен** параметр **Запрашивать ПИН-код или отпечаток пальца для доступа к приложениям Office**.
  
![Убедитесь, что для параметра требовать ПИН-код или отпечаток для доступа к приложениям Office задано значение Вкл.](../media/f37eb5b2-7e26-49fb-9bd6-d955d196bacf.png)
  
1. На устройстве с iOS пользователя откройте Outlook и войдите в систему, используя учетные данные пользователя Microsoft 365 Business Premium.
    
2. Кроме того, вам будет предложено ввести ПИН-код или использовать отпечаток пальца.
    
    ![Enter a PIN on your IOS device to access Office apps.](../media/06fc5cf3-9f19-4090-b23c-14bb59805b7a.png)
  
### <a name="validate-reset-pin-after-number-of-failed-attempts"></a>Проверка сброса ПИН-кода после нескольких неудачных попыток

В области **Политика изменения** нажмите кнопку **изменить** рядом с **элементом Управление доступом к документам Office**, разверните **Управление доступом пользователей к файлам Office на мобильных устройствах**и убедитесь, что **ПИН-код сбрасывается после количества неудачных попыток** , для которых задано количество неудачных попыток. По умолчанию это 5. 
  
1. На устройстве с iOS пользователя откройте Outlook и войдите в систему, используя учетные данные пользователя Microsoft 365 Business Premium.
    
2. Введите неправильный ПИН-код указанное в политике количество раз. Вы увидите сообщение о том, что **достигнуто максимальное количество попыток ПИН-** кода, чтобы сбросить ПИН-код. 
    
    ![After too many incorrect PIN attempts, you need to reset your PIN.](../media/fab5c089-a4a5-4e8d-8c95-b8eed1dfa262.png)
  
3. Нажмите кнопку **ОК**. Вам будет предложено войти в систему, используя учетные данные пользователя Microsoft 365 Бизнес Premium, а затем указать новый ПИН-код.
    
### <a name="validate-force-users-to-save-all-work-files-to-onedrive-for-business"></a>Проверка принудительного сохранения всех рабочих файлов в OneDrive для бизнеса

На панели **Изменение политики** рядом с параметром **Защита от потери или кражи устройств** нажмите **Изменить**, разверните раздел **Защита рабочих файлов при краже или потере устройств** и убедитесь, что **включен** параметр **Обеспечить принудительное сохранение всех рабочих файлов пользователей в OneDrive для бизнеса**.
  
![Verify that Force users to save all work files to OneDrive for Business is set to On.](../media/7140fa1d-966d-481c-829f-330c06abb5a5.png)
  
1. На устройстве с iOS пользователя откройте Outlook и войдите в систему, используя учетные данные пользователя Microsoft 365 Business Premium, и введите ПИН-код по запросу.
    
2. Откройте сообщение электронной почты с вложением, откройте вложение и внизу экрана нажмите кнопку **Сохранить**. 
    
    ![Tap the Save option after you open an attachment to try to save it.](../media/b419b070-1530-4f14-86a8-8d89933a2b25.png)
  
3. У вас должен быть только один вариант  OneDrive для бизнеса. В противном случае нажмите кнопку **Добавить учетную запись** и выберите **OneDrive для бизнеса** в окне **Добавление учетной записи хранения** . Введите Microsoft 365 Business Premium конечного пользователя, чтобы войти в систему, когда будет предложено. 
    
    Нажмите **Сохранить** и выберите **OneDrive для бизнеса**.
    
### <a name="validate-require-user-to-sign-in-again-if-office-apps-have-been-idle-for-a-specified-time"></a>Проверка требования повторного входа при неактивности приложений Office в течение указанного времени

В области " **изменение политики** " выберите пункт **изменить** рядом с **элементом Управление доступом к документам Office**, разверните **Управление доступом пользователей к файлам Office на мобильных устройствах**и убедитесь, что пользователям требуется **повторно входить в систему после неактивности для приложений Office** в течение определенного количества минут. По умолчанию это 30 минут. 
  
1. На устройстве с iOS пользователя откройте Outlook и войдите в систему, используя учетные данные пользователя Microsoft 365 Business Premium, и введите ПИН-код по запросу.
    
2. Вы должны увидеть папку входящих сообщений в Outlook. Не трогайте устройство с iOS в течение 30 минут (или другого количества времени, превышающего указанное в политике). Скорее всего, экран устройства погаснет.
    
3. Снова получите доступ к Outlook на устройстве iOS.
    
4. Вам будет предложено ввести ПИН-код, прежде чем вы сможете снова получить доступ к Outlook.
    
### <a name="validate-protect-work-files-with-encryption"></a>Проверка защиты рабочих файлов шифрованием

На панели **Изменение политики** рядом с параметром **Защита от потери или кражи устройств** нажмите **Изменить**, разверните раздел **Защита рабочих файлов при краже или потере устройств** и убедитесь, что параметр **Шифровать рабочие файлы**  **включен**, а параметр **Обеспечить принудительное сохранение всех рабочих файлов пользователей в OneDrive для бизнеса**  **выключен**.
  
1. На устройстве с iOS пользователя откройте Outlook и войдите в систему, используя учетные данные пользователя Microsoft 365 Business Premium, и введите ПИН-код по запросу.
    
2. Откройте сообщение электронной почты, которое содержит несколько вложенных файлов изображений.
    
3. Нажмите вложение, а затем команду **Сохранить** под ним. 
    
4. На главном экране откройте приложение **Фотографии**. Вы должны увидеть в списке сохраненную и зашифрованную фотографию (или несколько, если сохранили несколько вложенных файлов изображений). 
    
---

