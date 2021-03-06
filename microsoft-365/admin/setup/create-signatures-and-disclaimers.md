---
title: Создание подписей на уровне Организации и заявления об отказе
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2d75860f-c527-4352-a7f6-73eba54c0c72
description: Сведения о том, как добавить подпись электронной почты, юридическое заявление или раскрытие, во все сообщения электронной почты, которые вводят или выходят из Организации.
ms.openlocfilehash: d7e19c6e3f425f95429aefd769d2b8992fde141e
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779885"
---
# <a name="create-organization-wide-signatures-and-disclaimers"></a>Создание подписей на уровне Организации и заявления об отказе

 You can add an email signature, legal disclaimer, or disclosure statement to the email messages that enter or leave your organization. You can set it up to apply to all incoming and outgoing messages as shown below. Or you can apply it to certain messages like those containing specific words or text patterns.

 Посмотрите короткое видео о создании подписи электронной почты на уровне всей компании. <br><br>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf] 

Если этот видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

## <a name="create-a-signature-that-applies-to-all-messages"></a>Создание подписи,применяемой ко всем сообщениям

> [!TIP]
> Подписи на уровне Организации называются "заявления об отказе", независимо от того, что они включают. Например, это может быть подпись, а также адрес, юридическое заявление об отказе или другие необходимые сведения.
    
::: moniker range="o365-worldwide"

Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.

::: moniker-end

::: moniker range="o365-21vianet"

Перейдите в Центр администрирования <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn/adminportal</a>.

::: moniker-end

1. Выберите средство запуска приложений ![ и значок запуска приложений ](../../media/7502f4ec-3c9a-435d-a7b4-b9cda85189a7.png) , а затем выберите элемент **Администратор**.
   
    Не удается найти приложение, которое вы ищете? В средстве запуска приложений выберите **все приложения** , чтобы просмотреть алфавитный список доступных вам приложений. Отсюда можно искать конкретное приложение. 
    
2. Выберите пункт **центры администрирования**, а затем нажмите кнопку **Exchange**.
    
3. В разделе процесс обработки почты выберите **правила**.
    
4. Нажмите **+** значок (Добавить) и выберите **Применить заявления об отказе**.
    
5. Задайте имя правила.
    
6. В разделе **Применить это правило**выберите **[Применить ко всем сообщениям]**.
    
    > [!TIP]
    > [Узнайте больше](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#Scoping) о том, как настроить условия, чтобы заявление об отказе применялось не ко всем сообщениям. (Эта статья относится к Exchange Server, но она также применима к Microsoft 365.) 
  
7. В списке "Выполнить следующие действия..." оставьте выбранным пункт **Добавить в сообщение заявление об отказе**. 
    
8.  Нажмите **Ввод текста** и введите заявление об отказе. 
    
    > [!TIP]
    > [Узнайте больше](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/signatures#FormatDisclaimer) о форматировании заявлений об отказе. (Эта статья форматирования предназначена для Exchange Server, но она также применима к Microsoft 365.) 

9. Выберите **пункт выбрать один** и выберите параметр **переносить** как резервный. Затем нажмите кнопку **ОК**. Это означает, что если заявление об отказе невозможно добавить из-за шифрования или других настроек почты, оно переносится в конверт сообщения.
    
10. Leave **Audit this rule with severity level** selected. Then choose **Low**, **Medium**, or **High** to be used in the message log. 
    
11. Установите переключатель **Принудительно**, чтобы включить это правило немедленно, если его не нужно предварительно протестировать. 
    
12. Щелкните ссылку **Дополнительные параметры**, чтобы добавить дополнительные условия или исключения. 
    
13. Когда все будет готово, нажмите кнопку **Сохранить**. 
    
## <a name="limitations-of-organization-wide-signatures"></a>Ограничения подписей на уровне Организации

Вы не можете выполнять следующие действия с подписями Microsoft 365:
  
- Вставка подписи непосредственно под последним ответом или пересылкой сообщения
    
- Отображение подписей электронной почты на стороне сервера в папках "Отправленные" пользователей
    
- Внедрение изображений в подписи электронной почты
    
- Пропускать строки, содержащие переменные, которые не удалось обновить (например, из-за того, что значение не было предоставлено пользователю)
    
Чтобы получить эти и другие возможности, воспользуйтесь сторонним средством. Выполните поиск **по программному обеспечению для подписи электронной почты**в Интернете. У некоторых из этих поставщиков есть золотых партнеров Майкрософт, и их программное обеспечение предоставляет эти возможности. 
  
## <a name="more-resources"></a>Дополнительные ресурсы

- Сведения об использовании PowerShell [можно найти в статье заявление об отказе, подписи, нижние колонтитулы или заголовки в Microsoft 365](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/disclaimers-signatures-footers-or-headers) . 
    

