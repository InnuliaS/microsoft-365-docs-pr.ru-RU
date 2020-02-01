---
title: Оповещения об управлении рисками для участников
description: Сведения об оповещениях об управлении рисками в Microsoft 365
keywords: Microsoft 365, риск для участников, управление рисками, соответствие требованиям
localization_priority: Normal
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: m365-security-compliance
ms.openlocfilehash: 80c5bb701c7805f673280d24903935c2951046b7
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41590800"
---
# <a name="insider-risk-management-alerts-preview"></a>Оповещения об управлении рисками для участников (Предварительная версия)

Оповещения об управлении рисками для участников программы оценки автоматически создаются индикаторами риска, определенными в политиках управления рисками для участников программы. Эти оповещения предоставляют аналитикам и обучению соответствия требованиям к текущему состоянию риска и позволяют Организации проанализировать и принять меры по обнаруженным угрозам.

## <a name="alert-dashboard"></a>Панель мониторинга оповещений

**Панель мониторинга оповещений о** рисках для участников программы предварительной оценки позволяет просматривать оповещения, созданные политиками оценки риска, и выполнять действия над ними. Каждый графический элемент отчета отображает сведения за последние 30 дней.

- **Оповещения для проверки**: отображается общее число оповещений, требующих рассмотрения и рассмотрения, включая разбивку по уровню серьезности оповещений.
- **Открыть оповещения за последние 30 дней**: общее количество оповещений, созданных политикой за последние 30 дней, отсортированных по высококачественному, среднему и низкому уровню серьезности оповещений.
- **Среднее время на устранение оповещений**: сводка по полезной статистике оповещений:
    - Среднее время разрешения оповещений о высокой серьезности, указанных в часах, днях или месяцах.
    - Среднее время, в течение которого отменяются оповещения среднего уровня серьезности, которые перечислены в часах, днях или месяцах.
    - Среднее время разрешения оповещений с низкой степенью серьезности, указанных в часах, днях или месяцах.

![Панель мониторинга оповещений об управлении рисками](media/insider-risk-alerts-dashboard.png)

## <a name="alert-status-and-severity"></a>Состояние оповещения и степень серьезности

Вы можете рассмотреть оповещения в одном из следующих состояний:

- **Подтверждено**: оповещение подтверждено и назначено новому или существующему случаю.
- **Закрыто**: оповещение было закрыто как неблагоприятное в процессе рассмотрения.
- **Требуется проверка**: новое оповещение, в котором действия по рассмотрению еще не выполнены.
- **Разрешено**: оповещение, которое является частью закрытого и разрешенного обращения.

Показатели риска для оповещений автоматически рассчитываются по нескольким атрибутам действий с рисками. Эти атрибуты включают тип действия риска, число и частоту вхождения действия, историю действий пользователя о рисках и Добавление рисков для действий, которые могут увеличить серьезность действия. В показателе риска для оповещений задается программное назначение уровня серьезности риска для каждого оповещения и не может быть изменено. Если оповещения остаются нерассмотренными, а действия по рискам продолжают начисляться на оповещение, степень серьезности риска может увеличиться. Аналитики и изучает риски могут использовать серьезность риска для оповещений в соответствии с политиками и стандартами риска в Организации.

Уровни серьезности рисков оповещений:

- **Высокая степень серьезности**: действия и индикаторы для оповещения создают важный риск. Связанные с рисками действия — это серьезные, повторяющиеся и соотношения, которые сильно отличаются от других существенных факторов риска.
- **Средняя серьезность**: действия и индикаторы для оповещения создают умеренный риск. Связанные с рисками действия являются умеренными, частыми и имеют некоторую корреляцию от других факторов риска.
- **Низкую серьезность**: действия и индикаторы для оповещения представляют собой незначительный риск. Связанные с рисками действия являются незначительными, более редкими и не связаны с другими существенными факторами риска.

## <a name="filter-alerts"></a>Фильтрация оповещений

В зависимости от числа и типа активных политик управления рисками для оценки в Организации, просмотр большой очереди оповещений может быть непростым. Использование фильтров оповещений помогает аналитикам и исследованиям сортировать оповещения по нескольким атрибутам. Чтобы отфильтровать оповещения на панели мониторинга оповещения, выберите элемент управления **фильтра** . Вы можете отфильтровать предупреждения по одному или нескольким атрибутам:

- **Состояние**: выберите одно или несколько значений состояния, чтобы отфильтровать список оповещений. Параметры *подтверждены* *, отменяются,* *требуют проверки*и *разрешаются*.
- **Severity**: выберите один или несколько уровней серьезности угроз оповещений, чтобы отфильтровать список оповещений. Возможные значения: *Высокая*, *Средняя*и *Минимальная*.
- **Время обнаружения**: выберите начальную и конечную даты создания оповещения.
- **Политика**: выберите одну или несколько политик, чтобы отфильтровать оповещения, созданные выбранными политиками.

## <a name="search-alerts"></a>Оповещения о поиске

Чтобы выполнить поиск по имени оповещения для определенного слова, выберите элемент управления **поиском** и введите слово для поиска. В результатах поиска отображается любое оповещение о политике, содержащее слово, определенное в поиске.

## <a name="triage-alerts"></a>Оповещения о рассмотрении

Чтобы прорассматривать оповещение о риске для участников программы предварительной оценки, выполните указанные ниже действия.

1. В [центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com)перейдите к разделу **Управление рисками для оценки** и перейдите на вкладку **оповещения** .
2. На **панели мониторинга оповещения**выберите оповещение, которое нужно рассмотреть.
3. В **области сведений оповещения**можно просмотреть следующие вкладки и рассмотреть предупреждение:
    - **Обзор**: Эта вкладка содержит общие сведения об оповещении и позволяет подтвердить оповещение и создать новое обращение, а также позволяет отклонить оповещение.
        - **Состояние**: состояние оповещения
        - **Время обнаружения**: время с момента создания оповещения.
        - **Соответствия политике**: перечислены политики, созданные оповещением. Каждая политика представлена в виде ссылки на сведения о политике.
        - **Степень серьезности**: уровень серьезности риска для оповещений, в том числе *высокий*, *средний*или *маленький*. Уровень серьезности может увеличиваться или уменьшаться со временем, если оповещение не рассмотрено.
        - **Case**: при подтверждении отображается регистр, созданный из оповещения. Для новых оповещений поле case имеет значение *None (нет* ).
    - **Действия пользователя**: на этой вкладке отображается журнал действий для пользователя, связанного с оповещением. Этот журнал включает другие оповещения и действия, связанные с индикаторами риска, определенными в шаблоне, назначенном политике для этого оповещения. Этот журнал позволяет аналитикам и обучениям проанализировать прошедшее опасное поведение сотрудника в рамках процесса рассмотрения.
    - **Профиль пользователя**: на этой вкладке отображаются общие сведения о сотруднике, назначенном оповещению.
    - **Подтвердить и создать регистр**: отображается на всех вкладках нажмите эту кнопку, чтобы подтвердить и создать новое обращение. При этом состояние оповещения автоматически изменится на " *подтверждено*".
    - **Отклонить**: отображается на всех вкладках нажмите эту кнопку, чтобы закрыть оповещение. Состояние оповещения изменится на " *разрешено*".

## <a name="create-a-case-for-an-alert"></a>Создание обращения для оповещения

После рассмотрения и рассмотрения оповещения можно создать новое обращение для дальнейшего изучения действия риска. Чтобы создать обращение для оповещения, выполните следующие действия:

1. В [центре соответствия требованиям Microsoft 365](https://compliance.microsoft.com)перейдите к разделу **Управление рисками для оценки** и перейдите на вкладку **оповещения** .
2. На **панели мониторинга оповещения**выберите оповещение, которое требуется подтвердить, и создайте для него новое обращение.
3. В **области сведения оповещения**выберите пункт **подтвердить и создать обращение**.
4. В диалоговом окне " **Подтверждение оповещения и создание инцидента оценки риска** " введите имя для обращения, выберите пункт Пользователи для добавления в качестве авторов и добавьте комментарии в качестве соответствующих. Комментарии автоматически добавляются к регистру в качестве заметок о случае.
5. Выберите **создать обращение** , чтобы создать новое обращение, или кнопку **Отмена** , чтобы закрыть диалоговое окно без создания дела.