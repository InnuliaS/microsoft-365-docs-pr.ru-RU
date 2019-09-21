---
title: Проверка запроса веб-части "Поиск контента" на ошибки
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 88898874-e262-4c5c-b6d2-4e697497fc74
description: Перед выполнением поиска проверьте запрос ключевого слова на поиск содержимого на наличие ошибок и опечаток, таких как неподдерживаемые символы и логические операторы нижнего регистра. Если мы нашли сообщение об ошибке, мы предлагаем исправленный запрос.
ms.openlocfilehash: 9f9f59c4466102d678bc3a599aa208869bbd9d64
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37089846"
---
# <a name="check-your-content-search-query-for-errors"></a><span data-ttu-id="3fc9b-104">Проверка запроса веб-части "Поиск контента" на ошибки</span><span class="sxs-lookup"><span data-stu-id="3fc9b-104">Check your Content Search query for errors</span></span>

<span data-ttu-id="3fc9b-105">При создании или изменении поиска контента можно использовать Office 365, чтобы проверить запрос на наличие неподдерживаемых символов и логических операторов, которые могут быть не прописными.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-105">When you create or edit a Content Search, you can have Office 365 check your query for unsupported characters and Boolean operators that might not be capitalized.</span></span> <span data-ttu-id="3fc9b-106">Как это сделать?</span><span class="sxs-lookup"><span data-stu-id="3fc9b-106">How?</span></span> <span data-ttu-id="3fc9b-107">Просто нажмите кнопку **проверить запрос на наличие опечаток** на странице запрос поиска контента.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-107">Just click **Check query for typos** on the query page of a Content Search.</span></span> 
  
![Нажмите кнопку "проверить запрос на опечатки", чтобы проверить запрос поиска на наличие неподдерживаемых символов](media/e5314306-cfb2-481d-9b5c-13ce658156e7.png)
  
<span data-ttu-id="3fc9b-109">Ниже приведен список неподдерживаемых символов, которые мы проверяем.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-109">Here's a list of the unsupported characters that we check for.</span></span> <span data-ttu-id="3fc9b-110">Неподдерживаемые символы часто скрываются, и они, как правило, вызывают ошибку поиска или возвращают нежелательные результаты.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-110">Unsupported characters are often hidden, and they typically cause a search error or return unintended results.</span></span>
  
- <span data-ttu-id="3fc9b-111">**Парные** кавычки — разумные одинарные и двойные кавычки (также называемые фигурными кавычками) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-111">**Smart quotation marks** - Smart single and double quotation marks (also called curly quotes) aren't supported.</span></span> <span data-ttu-id="3fc9b-112">В поисковом запросе можно использовать только прямые кавычки.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-112">Only straight quotation marks can be used in a search query.</span></span> 
    
- <span data-ttu-id="3fc9b-113">Непечатаемые и непечатаемые **символы** — непечатаемые и непечатаемые символы не представляют собой записанный символ, например, буквенно-цифровой символ.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-113">**Non-printable and control characters** - Non-printable and control characters don't represent a written symbol, such as a alpha-numeric character.</span></span> <span data-ttu-id="3fc9b-114">К непечатаемым и управляющим символам относятся символы, которые форматируют текст или разделяют его на строки.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-114">Examples of non-printable and control characters include characters that format text or separate lines of text.</span></span> 
    
- <span data-ttu-id="3fc9b-115">**Метки слева направо и справа налево** — это управляющие символы, используемые для указания направления текста для языков с письмом слева направо (например, английский и испанский) и языков с письмом справа налево (например, арабского языка и иврита).</span><span class="sxs-lookup"><span data-stu-id="3fc9b-115">**Left-to-right and right-to-left marks** - These are control characters used to indicate text direction for left-to-right languages (such as English and Spanish) and right-to-left languages (such as Arabic and Hebrew).</span></span>
    
- <span data-ttu-id="3fc9b-116">**Логические операторы в нижнем регистре** — если вы используете логический оператор (например, **and**, **or**), а **не** в поисковом запросе, он должен быть задан в верхнем регистре.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-116">**Lowercase Boolean operators** - If you use a Boolean operator, such as **AND**, **OR**, and **NOT** in a search query, it must be uppercase.</span></span> <span data-ttu-id="3fc9b-117">Когда мы проверяем запрос на опечатки, синтаксис запроса часто указывает на то, что логический оператор используется, несмотря на то, что можно использовать операторы нижнего регистра; Пример: `(WordA or WordB) and (WordC or WordD)`.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-117">When we check a query for typos, the query syntax will often indicate that a Boolean operator is being used even though lowercase operators might be used; for example,  `(WordA or WordB) and (WordC or WordD)`.</span></span>
    
## <a name="what-happens-if-a-query-has-an-unsupported-character"></a><span data-ttu-id="3fc9b-118">Что произойдет, если запрос содержит неподдерживаемый символ?</span><span class="sxs-lookup"><span data-stu-id="3fc9b-118">What happens if a query has an unsupported character?</span></span>

<span data-ttu-id="3fc9b-119">Если в запросе найдены неподдерживаемые символы, отображается предупреждение с сообщением о том, что обнаружены неподдерживаемые символы, и предлагается альтернативный вариант.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-119">If unsupported characters are found in your query, a warning message is displayed that says unsupported characters that were found and a suggests an alternative.</span></span> <span data-ttu-id="3fc9b-120">Затем вы можете оставить исходный запрос или заменить его предложенным исправленным запросом.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-120">Then you then have the option keep the original query or replace it with the suggested revised query.</span></span> <span data-ttu-id="3fc9b-121">Ниже приведен пример сообщения с предупреждением, которое отображается после нажатия кнопки **проверить запрос на наличие опечаток** для поискового запроса на предыдущем снимке экрана.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-121">Here's an example of the warning message that's displayed after you click **Check query for typos** for the search query in the previous screenshot.</span></span> <span data-ttu-id="3fc9b-122">Обратите внимание, что исходный запрос содержит логические операторы и логические операторы для кавычек и строчных букв.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-122">Notice that the original query contains smart quotes and lowercase Boolean operators.</span></span> 
  
![Отображается предупреждающее сообщение с предлагаемой версией запроса](media/23214b30-8e52-412c-bd80-63fb1b3ed52d.png)
  
## <a name="how-to-prevent-unsupported-characters-in-your-search-queries"></a><span data-ttu-id="3fc9b-124">Как предотвратить неподдерживаемые символы в поисковых запросах</span><span class="sxs-lookup"><span data-stu-id="3fc9b-124">How to prevent unsupported characters in your search queries</span></span>

<span data-ttu-id="3fc9b-125">Неподдерживаемые символы обычно добавляются в запрос при копировании запроса или частей запроса из других приложений (таких как Microsoft Word или Microsoft Excel) и их копирования в поле ключевое слово на странице запрос поиска контента.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-125">Unsupported characters are typically added to a query when you copy the query or parts of the query from other applications (such as Microsoft Word or Microsoft Excel) and copy them to the keyword box on the query page of a Content Search.</span></span> <span data-ttu-id="3fc9b-126">Лучший способ избежать неподдерживаемых символов  просто ввести запрос в поле ключевых слов.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-126">The best way to prevent unsupported characters is to just type the query in the keyword box.</span></span> <span data-ttu-id="3fc9b-127">Кроме того, вы можете скопировать запрос из Word или Excel, а затем вставить его в файл в обычном текстовом редакторе, например "Блокноте".</span><span class="sxs-lookup"><span data-stu-id="3fc9b-127">Alternatively, you can copy a query from Word or Excel and then paste it to file in a plain text editor, such as Microsoft Notepad.</span></span> <span data-ttu-id="3fc9b-128">После этого сохраните текстовый файл и выберите **ANSI** в раскрывающемся списке **Кодировка**.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-128">Then save the text file and select **ANSI** in the **Encoding** drop-down list.</span></span> <span data-ttu-id="3fc9b-129">Так вы удалите все форматирование и неподдерживаемые символы.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-129">This will remove any formatting and unsupported characters.</span></span> <span data-ttu-id="3fc9b-130">Затем вы можете скопировать запрос из текстового файла и вставить его в поле запроса по ключевым словам.</span><span class="sxs-lookup"><span data-stu-id="3fc9b-130">Then you can copy and paste the query from the text file to the keyword query box.</span></span> 