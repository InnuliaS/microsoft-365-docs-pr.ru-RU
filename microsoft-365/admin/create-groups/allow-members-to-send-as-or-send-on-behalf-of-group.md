---
title: Разрешение пользователям отправлять сообщения от имени группы или отправлять от него
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Сведения о том, как разрешить участникам отправлять электронную почту как группу Microsoft 365 или отправлять электронную почту от имени группы Майкрософт 365.
ms.openlocfilehash: 090a5e177ed843c035155cd735e0b7b9560e5631
ms.sourcegitcommit: bd5a08785b5ec320b04b02f8776e28bce5fb448f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/23/2020
ms.locfileid: "44844672"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Разрешение пользователям отправлять сообщения от имени группы или отправлять от него

Член группы Microsoft 365, которому предоставлены разрешения " **Отправить как** " или " **Отправить от имени** ", может отправлять сообщения электронной почты в виде группы или от имени группы. В этом разделе объясняется, как администратор может настроить эти разрешения.
  
Например, если Меган Бовен входит в **учебную** группу Microsoft 365 и имеет разрешения " **Отправить как** " для группы, то, если она отправляет сообщение электронной почты в качестве группы, она будет выглядеть так, как **учебная** группа отправила сообщение электронной почты. 
  
Разрешение " **Отправить от имени** " позволяет пользователю отправлять электронную почту от имени группы Microsoft 365. Например, если Алекс Вилбер является частью группы **маркетинга** Microsoft 365 и имеет разрешения **на отправку от имени** и отправляет сообщение электронной почты в качестве группы, сообщение будет выглядеть так, как было отправлено **Вилбер от имени маркетингового отдела**.

> [!IMPORTANT]
> Вы можете настроить " **Отправить как** " или " **Отправить от имени** " для определенного пользователя, но не для обоих. Если вы настроили оба значения, то по умолчанию будет **отправляться как**.

> [!TIP]
> Чтобы узнать, как использовать Outlook и Outlook в Интернете для отправки электронной почты из группы, обратитесь к разделу [Отправка сообщений от имени или от имени группы майкрософт 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) .
    
## <a name="allow-members-to-send-email-as-a-group"></a>Разрешение участникам отправлять электронную почту как группу

В этом разделе объясняется, как разрешить пользователям отправлять электронную почту как группу в [центре администрирования Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) в Exchange Online.
  
1. В <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">центре администрирования Exchange</a>перейдите в раздел группы **получателей** \> **Groups**.
    
2. Выберите команду **изменить** ![ значок редактирования группы для ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) группы, которую нужно разрешить пользователям отправлять.   
    
3. Выберите пункт **Делегирование группы**.
    
4. В разделе **Отправить как** выберите **+** знак, чтобы добавить пользователей, которых нужно отправить в качестве группы. 
    
    ![Нажмите значок "плюс", чтобы добавить пользователей, которых нужно отправить в качестве группы Microsoft 365.](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Введите имя, чтобы найти пользователя, или выберите его из списка. Нажмите кнопку **ОК** и **Сохраните**.
    
    ![Введите текст для поиска или выберите пользователя из списка.](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Разрешение участникам отправлять электронную почту от имени группы

В этом разделе объясняется, как разрешить пользователям отправлять электронную почту от имени группы в центре администрирования Exchange в Exchange Online.
  
1. В <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">центре администрирования Exchange</a>перейдите в раздел группы **получателей** \> **Groups**.
    
2. Выберите команду **изменить** ![ значок редактирования группы для ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) группы, которую нужно разрешить пользователям отправлять. 
    
3. Выберите пункт **Делегирование группы**.
    
4. В разделе Отправить от имени выберите **+** знак, чтобы добавить пользователей, которых нужно отправить в качестве группы. 
    
    ![Нажмите значок "плюс", чтобы добавить пользователей, которых нужно отправить в качестве группы Microsoft 365.](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Введите имя, чтобы найти пользователя, или выберите его из списка. Нажмите кнопку **ОК** и **Сохраните**.
    
    ![Введите текст для поиска или выберите пользователя из списка.](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
    
> [!NOTE]
> Чтобы изменения вступили в силу, может потребоваться до двух часов.

## <a name="related-articles"></a>Статьи по теме

[Дополнительные сведения о группах Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add — RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set — UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
