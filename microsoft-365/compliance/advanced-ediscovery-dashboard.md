---
title: Расширенная панель мониторинга обнаружения электронных данных для наборов проверок
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 127e2c9a04977bf6e902a1ce669fa9e4248e3ef2
ms.sourcegitcommit: 2913fd74ad5086c7cac6388447285be9aa5a8e44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2020
ms.locfileid: "41662269"
---
# <a name="advanced-ediscovery-dashboard-for-review-sets-preview"></a>Расширенная панель мониторинга обнаружения электронных данных для наборов проверок (Предварительная версия)

В некоторых случаях для расширенного обнаружения электронных данных может потребоваться проверить большой объем документов и сообщений электронной почты. Прежде чем начать процесс проверки, можно быстро проанализировать собрании, чтобы определить тенденции или ключевую статистику, которая поможет вам разработать стратегию рецензирования. Для этого вы можете использовать расширенную панель мониторинга обнаружения электронных данных для наборов проверок, чтобы быстро проанализировать собрании.

## <a name="step-1-create-a-widget-on-the-review-set-dashboard"></a>Шаг 1: создание мини-приложения на панели мониторинга "набор проверки"

1. В центре безопасности & соответствия требованиям перейдите на **Обнаружение электронных данных > Advanced eDiscovery** для отображения списка дел в Организации.
  
2. Выберите существующее обращение.
  
3. Перейдите на вкладку **Рецензирование** и выберите набор рецензирования.
  
4. В раскрывающемся списке **отдельные результаты** выберите **представление профиля поиска**. 

   ![дашбордпивот](media/dashboardpivot.png)

   Отображается страница **представления профиля поиска** ; При первом отображении этой страницы отображаются три стандартных мини-пользователя.

   ![Информационная панель](media/dashboardonly.png)
  
5. Щелкните **новое мини** -приложение, а затем выберите один из следующих элементов:

   ![Раскрывающийся список "создать мини-приложение"](media/NewWidgetDropdownBox.png)

   - **Выберите из библиотеки:** Отображает библиотеку Widgets по умолчанию. Щелкните мини-приложение и нажмите кнопку **Добавить** , чтобы добавить его в элементы widget на странице **представления профиля поиска** .
  
   - **Создание настраиваемого мини** -приложения: Отображает раскрывающуюся страницу, которую можно использовать для настройки настраиваемого мини-приложения. 

6. Чтобы создать настраиваемое мини-приложение, выполните следующие действия на всплывающей странице **Добавление мини** -приложения:

   ![Создать мини-приложение](media/addwidget.png)

    а) Введите имя мини-приложения, которое отображается в строке заголовка мини-приложения. Имя мини-приложения является обязательным, но оно полезно для определения данных мини-приложения.

    б) Выберите свойство в выпадающем списке **Выбор сводной таблицы** , который будет использоваться для данных мини-приложения. Элементы в этом списке являются свойствами для поиска элементов в наборе рецензирования. Описание этих свойств приведено [в статье Document Metadata Fields in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md). Параметры сведения для мини-приложения перечислены в столбце **имя поля для поиска** в этой статье.

    в. Выберите тип диаграммы, чтобы отобразить данные из выбранного свойства сведения.

  6. Нажмите кнопку **Добавить** , чтобы создать настраиваемое мини-приложение и отобразить его на странице **представления профиля поиска** .

## <a name="step-2-create-a-review-set-search-query"></a>Шаг 2: Создание запроса на поиск набора проверки

1. Нажмите кнопку **..** . в строке заголовка мини-приложения, а затем выберите команду **применить условие**.

   ![Информационная панель](media/searchprofilehome.png)

2. Чтобы создать фильтр, на всплывающей странице щелкните элемент в разделе Widget или widget Chart (мини-приложение).

   ![креатефилтер](media/applyconditionfilter.png)

3. Повторите шаги 1-2 для других графических подэлементов. 

4. Когда все будет готово, нажмите **Сохранить как запрос** , чтобы сохранить условия в качестве нового поискового запроса для набора проверки.

   ![Query](media/savequery.png)

5. Закройте **представление профиля поиска** , чтобы вернуться к представлению результатов поиска.

   Если вы создали визуальные фильтры, результирующий запрос применяется к отображаемым результатам поиска, а запрос поиска, сохраненный на шаге 4, отображается в разделе **сохраненные запросы**. Дополнительные сведения о запросах Set см. [в статье запрос данных в наборе рецензирования](review-set-search.md).