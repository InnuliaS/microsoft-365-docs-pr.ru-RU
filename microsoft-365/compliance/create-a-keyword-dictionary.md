---
title: Создание словаря ключевых слов
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Узнайте, как создать словарь ключевых слов в центре безопасности Office 365 & соответствия требованиям.
ms.openlocfilehash: 38a92aaf7e72ab79243c547ff48fa156e26b6ee6
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818058"
---
# <a name="create-a-keyword-dictionary"></a>Создание словаря ключевых слов

Защита от потери данных (DLP) позволяет определять, отслеживать и защищать конфиденциальные данные. Для определения конфиденциальной информации иногда требуется поиск ключевых слов, особенно при определении общего контента (например, для общения с учетом здравоохранения) или неуместного или явного языка. Несмотря на то, что вы можете создавать списки ключевых слов в типах конфиденциальных данных, списки ключевых слов ограничены и требуют изменения XML для создания или изменения. Словари ключевых слов обеспечивают упрощенное управление ключевыми словами и на более крупном масштабе, поддерживающем до 100 000 терминов для каждого словаря.
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>Основные этапы создания словаря ключевых слов

The keywords for your dictionary could come from a variety of sources, most commonly from a file (such as a .csv or .txt list) imported in the service or by PowerShell cmdlet, from a list you enter directly in the PowerShell cmdlet, or from an existing dictionary. When you create a keyword dictionary, you follow the same core steps:
  
1. Используйте **Центр безопасности & соответствия требованиям** ( [https://protection.office.com](https://protection.office.com) ) или подключитесь **к &amp; PowerShell центра соответствия требованиям безопасности**.
    
2. **Определите или загрузите ключевые слова из предполагаемого источника**. Мастер и командлет принимают разделенный запятыми список ключевых слов для создания пользовательского словаря ключевых слов, поэтому этот шаг будет слегка отличаться в зависимости от того, откуда берутся ключевые слова. После загрузки они кодируются и преобразуются в байтовый массив, а затем импортируются.
    
3. **Создайте словарь**. Выберите имя и описание и создайте словарь.

## <a name="create-a-keyword-dictionary-using-the-security--compliance-center"></a>Создание словаря ключевых слов с помощью центра безопасности & соответствия требованиям

Используйте указанные ниже действия, чтобы создать и импортировать ключевые слова для пользовательского словаря:

1. Подключитесь к центру безопасности & соответствия требованиям ( [https://protection.office.com](https://protection.office.com) ).

2. Перейдите в раздел **Классификации > Типы конфиденциальной информации**.

3. Нажмите кнопку **Создать** и введите **имя** и **описание** для типа конфиденциальной информации, затем нажмите кнопку **Далее**.

4. Нажмите кнопку **Добавить элемент** и выберите вариант **Словарь (большие ключевые слова)** в раскрывающемся списке **Обнаруживать содержимое с указанными элементами**.

5. Выберите команду **Добавить словарь**.

6. В разделе управления поиском щелкните ссылку **Создать словари ключевых слов можно здесь**.

7. Введите **имя** для пользовательского словаря.

8. Нажмите кнопку **Импорт** и выберите параметр **Из текста** или **Из CSV** в зависимости от типа файла ключевых слов.

9. В диалоговом окне поиска файла выберите файл ключевых слов на локальном компьютере или в общей сетевой папке и нажмите кнопку **Открыть**.

10. Нажмите кнопку **Сохранить**, затем выберите пользовательский словарь из списка **Словари ключевых слов**.

11. Нажмите кнопку **Добавить**, а затем **Далее**.

12. Проверьте и выберите окончательные параметры типа конфиденциальной информации, затем нажмите кнопку **Готово**. 
    
## <a name="create-a-keyword-dictionary-from-a-file-using-powershell"></a>Создание словаря ключевых слов из файла с помощью PowerShell

Often when you need to create a large dictionary, it's to use keywords from a file or a list exported from some other source. In this case, you'll create a keyword dictionary containing a list of inappropriate language to screen in external email. You must first [connect to Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
  
1. Скопируйте ключевые слова в текстовый файл и убедитесь, что каждое ключевое слово находится на отдельной строке.
    
2. Save the text file with Unicode encoding. In Notepad \> **Save As** \> **Encoding** \> **Unicode**.
    
3. Считайте файл в переменную с помощью следующего командлета:
    
    ```powershell
    $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
    ```

4. Создайте словарь с помощью следующего командлета:
    
    ```powershell
    New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
    ```

## <a name="modifying-an-existing-keyword-dictionary"></a>Изменение имеющегося словаря ключевых слов

Иногда требуется изменить ключевые слова в одном из встроенных или своих собственных словарей. Сейчас обновить пользовательский словарь ключевых слов можно только с помощью PowerShell. 

Например, мы изменим некоторые термины в PowerShell, сохраняйте термины, которые вы можете изменить в редакторе, а затем обновляйте предыдущие термины на месте. 

Прежде всего получаем объект словаря:
  
```powershell
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

При печати `$dict` будут показаны различные переменные. Сами ключевые слова хранятся в объекте на внутреннем стороне, но `$dict.KeywordDictionary` содержат строковые представления, которые используются для изменения словаря. 

Перед изменением словаря необходимо снова превратить строку терминов в массив с помощью `.split(',')` метода. Затем вы удалите ненужные пробелы между ключевыми словами с `.trim()` методом, оставив только ключевые слова для работы. 
  
```powershell
$terms = $dict.KeywordDictionary.split(',').trim()
```

Now you'll remove some terms from the dictionary. Because the example dictionary has only a few keywords, you could just as easily skip to exporting the dictionary and editing it in Notepad, but dictionaries generally contain a large amount of text, so you'll first learn this way to edit them easily in PowerShell.
  
In the last step, you saved the keywords to an array. There are several ways to [remove items from an array](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-powershell-1.0/ee692802(v=technet.10)), but as a straightforward approach, you'll create an array of the terms you want to remove from the dictionary, and then copy only the dictionary terms to it that aren't in the list of terms to remove.
  
Run the command  `$terms` to show the current list of terms. The output of the command looks like this: 
  
`aarskog's syndrome`
`abandonment`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipoproteinemia`
`abiotrophy`
`ablatio`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`

Выполните следующую команду, чтобы указать удаляемые элементы:
  
```powershell
$termsToRemove = @('abandonment', 'ablatio')
```

Выполните следующую команду, чтобы фактически удалить термины из списка:
  
```powershell
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

Run the command  `$updatedTerms` to show the updated list of terms. The output of the command looks like this (the specified terms have been removed): 
  
`aarskog's syndrome`
`abasia`
`abderhalden-kaufmann-lignac`
`abdominalgia`
`abduction contracture`
`abetalipo proteinemia`
`abiotrophy`
`ablation`
`ablepharia`
`abocclusion`
`abolition`
`aborter`
`abortion`
`abortus`
`aboulomania`
`abrami's disease`
```

Now save the dictionary locally and add a few more terms. You could add the terms right here in PowerShell, but you'll still need to export the file locally to ensure it's saved with Unicode encoding and contains the BOM.
  
Save the dictionary locally by running the following:
  
```powershell
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

Now simply open the file, add your additional terms, and save with Unicode encoding (UTF-16). Now you'll upload the updated terms and update the dictionary in place.
  
```powershell
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

Now the dictionary has been updated in place. Note that the  `Identity` field takes the name of the dictionary. If you wanted to also change the name of your dictionary using the  `set-` cmdlet, you would just need to add the  `-Name` parameter to what's above with your new dictionary name. 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>Использование словарей ключевых слов в типах конфиденциальной информации и политиках защиты от потери данных

Словари ключевых слов можно использовать в качестве части требований к соответствию для настраиваемого типа конфиденциальной информации или как сам тип конфиденциальной информации. Для обоих требуется создать [настраиваемый тип конфиденциальной информации](create-a-custom-sensitive-information-type-in-scc-powershell.md). Следуйте инструкциям в связанной статье, чтобы создать тип конфиденциальной информации. Когда у вас есть XML, вам потребуется идентификатор GUID для словаря, чтобы его использовать.
  
```xml
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

Чтобы получить идентификатор словаря, выполните следующую команду и скопируйте значение свойства **Identity**: 
  
```powershell
Get-DlpKeywordDictionary -Name "Diseases"
```

Выходные данные команды выглядят так:
  
`RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255`
`Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f`
`Name              : Diseases`
`Description       : Names of diseases and injuries from ICD-10-CM lexicon`
`KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo` `proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,`
                    `abrami's disease, abramo`
`IsValid           : True`
`ObjectState       : Unchanged`


Paste the identity into your custom sensitive information type's XML and upload it. Now your dictionary will appear in your list of sensitive information types and you can use it right in your policy, specifying how many keywords are required to match.
  
```xml
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```
