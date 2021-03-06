---
title: Импорт контента, отличного от Microsoft 365, для расширенного анализа обнаружения электронных данных
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OEC150
- MET150
ms.assetid: 0ee60763-a30b-495b-8543-971c3384a801
description: Инструкции по импорту контента, не хранящегося в Microsoft 365, в большой двоичный объект Azure, чтобы его можно было проанализировать с помощью АЕД
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: fbb21f6bc3fdfd2a5251a9ec773a22351db5749e
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817598"
---
# <a name="import-non-microsoft-365-content-for-advanced-ediscovery-classic-analysis"></a>Импорт контента, отличного от Microsoft 365, для расширенного анализа обнаружения электронных данных (классический)

Не все документы, которые может потребоваться проанализировать с помощью расширенного обнаружения электронных данных, будут находиться в Microsoft 365. С помощью функции импорта содержимого, отличной от Microsoft 365, в Advanced eDiscovery вы можете отправлять документы, не входящие в состав Microsoft 365 (за исключением PST-файлов), в объект, связанный с хранилищем Azure, и анализировать их с помощью расширенного обнаружения электронных данных. В этой процедуре показано, как перенести документы, не относящиеся к Microsoft 365, в Расширенное обнаружение электронных данных для анализа.
  
> [!NOTE]
> Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
> [!NOTE]
> Вы можете приобрести расширенную подписку на надстройку хранилища данных eDiscovery для вашего контента, отличного от Майкрософт 365. Этот параметр доступен только для контента, который необходимо проанализировать с помощью расширенного обнаружения электронных данных. Выполните действия, описанные в статье [Покупка или изменение надстройки для Microsoft 365 для бизнеса](https://docs.microsoft.com/microsoft-365/commerce/buy-or-edit-an-add-on) , и приобретите расширенную надстройку для хранения электронных данных. 
  
## <a name="requirements-to-upload-non-office-365-content"></a>Требования к отправке контента, отличного от Office 365

Для использования функции отправки, отличной от Office 365, описанной в этой процедуре, необходимо следующее:
  
- Office 365 E3 с расширенной подпиской на надстройку с расширенным соответствием
    
- Все custodians, для которых содержимое, не относящееся к Office 365, должно быть отправлено в соответствии с дополнительными лицензиями на надстройку
    
- Существующее дело обнаружения электронных данных
    
- Все файлы для отправки собраны в папки, для которых в одной папке есть папка хранитель, а имя папки в этом формате *Alias@domainname* . *Alias@domainname* должны быть пользователями псевдонимов Office 365 и домена. Вы можете собрать все *Alias@domainname* папки в корневую папку. Корневая папка может содержать только папки *Alias@domainname* , в корневой папке не должно быть свободных файлов. 
    
- Учетная запись, которая является диспетчером обнаружения электронных данных или администратором обнаружения электронных данных
    
- [Средства Microsoft Azure Storage Tools](https://aka.ms/downloadazcopy) , установленные на компьютере, который имеет доступ к структуре папки контента, отличной от Office 365. 
    
## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Отправка контента, отличного от Office 365, в Расширенное обнаружение электронных данных


1. В качестве диспетчера обнаружения электронных данных или администратора eDiscovery откройте объект **обнаружения электронных**данных и откройте ситуацию, в которую будут отправлены данные, не относящиеся к Office 365. Если вам нужно создать обращение, ознакомьтесь со статьей [Управление вариантами обнаружения электронных &amp; данных в центре безопасности и соответствия требованиям](ediscovery-cases.md)
    
2. Нажмите кнопку **переключиться на расширенные функции обнаружения электронных** данных
    
3. В разделе **тип источника** выберите **данные, отличные от Office 365**.
    
4. Нажмите кнопку **добавить контейнер**. Назовите контейнер и добавьте описание.
    
5. Выберите только что добавленный контейнер из списка контейнер и скопируйте URL-адрес, который отображается в области сведений о контейнере, а затем закройте область.
    
6. Откройте командную строку от имени администратора и измените каталог на папку, в которой установлен AzCopy..
    
7. Создайте командную строку AzCopy, чтобы отправить файлы следующим образом:
    
    AzCopy/Source: " *полный путь к корневой папке на локальном компьютере* "/Дест: " *URL-адрес контейнера, но не включает?*  "/Дестсас:" *оставшаяся часть URL-адреса контейнера из поля "?" в конец* "/с. 
    
    Например, используйте следующие значения: 
    
  - Корневая папка — данные К:\коллектед 
    
  - URL-адрес контейнера- https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17?sv=2015-04-05&amp ; SR = c &amp; Si = NonOfficeData15% 7C0 &amp; SIG = Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA% 3D
    
    синтаксис командной строки AzCopy:
    
     `AzCopy /Source:"C:\CollectedData" /Dest:"https://zoomsabcprodeuss114.blob.core.windows.net/ingestion53d059efe5f74784afb308f66cdebf17" /DestSAS:"?sv=2015-04-05&amp;sr=c&amp;si=NonOfficeData15%7C0&amp;sig=Bk5INP8CUfv1y4CSJiJl3pJt3Ekvu8GS3P8NkOvoQxA%3D" /S`
    
    Для получения дополнительных сведений о синтаксисе Azcopy [перенесите данные с помощью Azcopy в Windows](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy) . 
    
    > [!IMPORTANT]
    > Для каждого пользователя должна быть только одна корневая папка, а имя папки должно быть в формате *Alias@domainname* . 
  
8. После завершения отправки папок переключитесь обратно на Advanced eDiscovery. Содержимое загруженных вами папок теперь готово для обработки в Advanced eDiscovery. Выберите контейнер и нажмите кнопку Process (обработать). Дополнительные сведения о расширенной обработке обнаружения электронных данных см. [запустите модуль Process и загрузите данные в Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md)
    
    > [!IMPORTANT]
    > После успешной обработки контейнера в Advanced eDiscovery вы больше не сможете добавлять новые материалы в хранилище SAS в Azure. Если вы собираете дополнительный контент и хотите добавить его в дело с расширенным анализом обнаружения электронных данных, необходимо создать новый контейнер данных, не относящийся к **Office 365** , и повторить эту процедуру. 
  
    > [!NOTE]
    > Если *не удается обработать контейнер из-за проблем с именованием папок* , а затем устранены проблемы, то все равно потребуется создать новый контейнер, а затем повторно подключиться и отправить его с помощью процедур, описанных в этой статье.
