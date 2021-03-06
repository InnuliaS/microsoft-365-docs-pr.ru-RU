---
title: Настройка коллекции виртуальных сертификатов — Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: Администраторы могут узнать, как создать коллекцию виртуальных сертификатов, которая будет использоваться для проверки сертификатов S/MIME в Exchange Online.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c8833cb50150eefea6bb786f8694fad42b52a752
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617190"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a>Настройка коллекции виртуальных сертификатов в Exchange Online для проверки S/MIME

В качестве администратора вам потребуется настроить виртуальную коллекцию сертификатов в Exchange Online, которая будет использоваться для проверки сертификатов S/MIME. Эта коллекция виртуальных сертификатов настроена как хранилище сертификатов с расширением имени файла SST. SST-файл содержит все корневые и промежуточные сертификаты, которые используются при проверке сертификата S/MIME.

## <a name="create-and-save-an-sst"></a>Создание и сохранение SST-файла

Вы можете создать SST файл хранилища сертификатов, экспортировав сертификаты с доверенного компьютера, используя командлет **Export/Certificate** в Windows PowerShell, и указав _тип_ значения SST. Инструкции можно найти в разделе [Export/Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).

Когда у вас будет файл хранилища сертификатов SST, используйте следующий синтаксис в Exchange Online PowerShell, чтобы сохранить содержимое SST-файла в виртуальном хранилище сертификатов Exchange Online. Сведения о том, как подключиться к Exchange Online PowerShell, см. в статье [Подключение к Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

В этом примере импортируется SST файл с параметром Documents\exported Rules Certificate Store. SST. SST.

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

Подробные сведения о синтаксисе и параметрах можно найти в статье [Set – SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).

## <a name="ensuring-a-certificate-is-valid"></a>Проверка действительности сертификата

В Exchange Online для проверки сертификата используется только SST.

## <a name="more-information"></a>Дополнительная информация

[S/MIME для подписи и шифрования сообщений](s-mime-for-message-signing-and-encryption.md)

[Get — SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
