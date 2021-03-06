---
title: Исправление вредоносного сообщения электронной почты, которое было доставлено в Office 365
author: msfttracyp
ms.author: tracyp
manager: ''
ms.topic: article
ms.service: Microsoft Threat Protection
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Исправление угроз
appliesto:
- Microsoft Threat Protection
ms.openlocfilehash: 6c1a07c6de55022797f284eb471d8ad054cd325e
ms.sourcegitcommit: a5ed189fa789975f8c3ed39db1d52f2ef7d671aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2020
ms.locfileid: "45101704"
---
# <a name="remediate-malicious-email-that-was-delivered-in-office-365"></a>Исправление вредоносного сообщения электронной почты, которое было доставлено в Office 365

Устранение неполадок означает выполнение действия проскрибед по отношению к угрозе. Вредоносные сообщения, отправленные в организацию, могут быть очищены системой с помощью ZAP (Автоочистка с нулевым временем) или группами безопасности путем действий по исправлению, таких как перемещение в папку "Входящие", перемещение в папку "Удаленные", "обратимое удаление" или "жесткое удаление". Office Advanced Threat protection (Office ATP) P2/водофункции предоставляет возможности по обеспечению безопасности Teams для устранения угроз по электронной почте и совместной работе с помощью функции автоматического исследования.

> [!NOTE]
> Чтобы отделы безопасности могли исправлять сообщения электронной почты, им необходимо назначить роли поиска и очистки. Назначение ролей выполняется с помощью разрешений в центре безопасности и соответствия требованиям. 

## <a name="what-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

Для выполнения определенных действий, таких как просмотр заголовков сообщений или загрузка содержимого сообщения электронной почты, необходимо создать новую роль с *предварительным просмотром* , добавленную в другую подходящую группу ролей. В следующей таблице даны пояснения к обязательным ролям и разрешениям.

|Действие  |Группа ролей |Нужна роль предварительного просмотра?  |
|---------|---------|---------|
|Использование обозревателя угроз (и обнаружения в реальном времени) для анализа угроз     |Глобальный администратор <br> Администратор безопасности <br> Читатель сведений о безопасности     | Нет   |
|Использование обозревателя угроз (и обнаружения в режиме реального времени) для просмотра заголовков сообщений электронной почты, а также предварительного просмотра и скачивания почтовых сообщений, помещенных в карантин    |Глобальный администратор <br> Администратор безопасности <br>Читатель сведений о безопасности   |       Нет  |
|Использование обозревателя угроз для просмотра заголовков и загрузки сообщений электронной почты, доставляемых в почтовые ящики     |Глобальный администратор <br>Администратор безопасности <br> Читатель сведений о безопасности <br> Preview   |   Да      |

> [!NOTE]
> *Предварительная версия* — это роль, а не группа ролей; роль предварительного просмотра необходимо добавить в существующую группу ролей для Office 365. Роли глобального администратора назначается центр администрирования Microsoft 365 ( [https://admin.microsoft.com](https://admin.microsoft.com) ), а роли администратора безопасности и средства чтения безопасности назначаются в центре безопасности & соответствия требованиям ( [https://protection.office.com](https://protection.office.com) ). Дополнительные сведения о ролях и разрешениях приведены [в разделе разрешения в центре безопасности & соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> Администраторы могут выполнять необходимые действия с сообщениями электронной почты, но чтобы получать их, они должны иметь роль "Поиск и очистка", назначенную им с помощью центра безопасности и соответствия требованиям > разрешений.

## <a name="manual-and-automated-remediation"></a>Ручное и автоматическое исправление

Поиск угроз вручную осуществляется в том случае, если специалисты по безопасности выявляют **угрозы вручную,** используя возможности поиска и фильтрации в обозревателе угроз. Ручное исправление сообщений электронной почты может быть запущено через любое представление электронной почты (вредоносные программы, фишинг или всю электронную почту) после обнаружения набора электронных сообщений, которые необходимо исправить.

[Поиск вручную в обозревателе угроз Office 365 по дате.](../../media/tp-RemediationArticle1.png)

Выбор электронной почты можно выполнить несколькими способами с помощью обозревателя угроз: 

1. Выбор электронных сообщений вручную: это означает, что Teams могут использовать фильтры в соответствующих представлениях и выбирать несколько сообщений в обозревателе угроз, которые необходимо исправить. Верхний предел выбора электронных сообщений — 100 (100). Операции безопасности Teams не может выбрать более сотни сообщений электронной почты вручную. 

2. Выбор запроса: операции с безопасностью Teams могут выбрать весь запрос с помощью кнопки Top "выделить все". Один и тот же запрос отображается в разделе сведения об отправке почты в центре уведомлений. 

3. Выбор запроса с исключением: возможны случаи, когда Teams решает исправить сообщения электронной почты, выбирая весь запрос и исключая из него несколько сообщений, вручную. Для этого администратор может воспользоваться флажком "выделить все" и прокрутить вниз, чтобы исключить несколько сообщений электронной почты вручную. В этом случае максимальное число сообщений электронной почты, которое может храниться в запросе, составляет 1000 (1 000), а максимальное число исключений — 100 (100).

После выбора в обозревателе угроз электронной почты, создание исправления может начаться с непосредственных действий или с помощью постановки в очередь сообщений электронной почты для действия. 

1. Прямое утверждение: при выполнении таких действий, как "переместить в папку" Входящие "," переместить в папку "Нежелательная почта", "переход к удаленным элементам", "обратимое удаление", "обратимое удаление", для сотрудников безопасности с соответствующими разрешениями и дальнейшие действия, выполняемые после создания исправления, процесс исправления начинает выполнение выбранного действия. Во временном всплывающем окне отображается выполняемое исправление. 

2. Два шага утверждения: действие "добавить в исправление" может быть выполнено администратором, у которого нет соответствующих разрешений или которым требуется больше ждать выполнения действия. В этом случае действие по исправлению не выполняется напрямую. Вместо этого сообщения добавляются в контейнер исправлений, который необходимо утвердить для выполнения. Сообщение электронной почты не будет исправлено до тех пор, пока исправление не будет утверждено. После утверждения исправления будут предприняты действия с электронной почтой. 

Действия **автоматического исследования и реагирования (AIR)** инициируются оповещениями или группами безопасности в обозревателе угроз. Они могут включать некоторые рекомендованные исправления, которые должны быть утверждены группами безопасности. Эти действия по исправлению содержатся на вкладке действия в автоматическом расследовании.  

[Почта с вредоносной программой — это страница Заппед, на которой показано время выполнения ZAP.](../../media/tp-RemediationArticle3.png)

Все исправления (прямые утверждения или два этапа утверждения), созданные с помощью обозревателя угроз, и действия, выполняемые из автоматизированного расследования, появятся в центре уведомлений, доступ к которому можно получить с помощью левой панели навигации в разделе * Проверка * > **центре уведомлений**.

[Центр уведомлений со списком угроз по дате и степени серьезности.](../../media/tp-RemediationArticle4.png)

В центре уведомлений отображаются все действия по исправлению за прошедшие 30 дней. Действия, выполняемые с помощью Explorer, отображаются с тем же именем, что и в Teams Operations в ходе создания исправления. Действия, выполняемые при автоматическом расследовании, отображаются с заголовками, которые начинаются с соответствующего оповещения, например "ZAP-Cluster Cluster...".

Каждый элемент исправления можно открыть для просмотра сведений о нем. При открытии элемента исправления отображаются основные сведения об исправлении, имя исправления, Дата создания, описание, серьезность угрозы и состояние. Кроме того, показаны две вкладки. 

1. **Вкладка "Отправка почты"**: это количество сообщений электронной почты, отправленных через обозреватель угроз или автоматических расследований, которые необходимо исправить. К этим сообщениям могут относиться следующие сообщения: 

[Центр уведомлений с угрозами, которые не подвержены действиям и не подвержены действиям.](../../media/tp-RemediationArticle5.png)

**Действие**: сообщения электронной почты из следующих расположений в облачных почтовых ящиках могут быть обработаны и перемещены, т. е. любые сообщения в категории ремедиабле можно перемещать из одного расположения в другое. 
  - Inbox; 
  - Нежелательное  
  - Удалена папка 
  - Обратимо удаленная папка 

[!NOTE]
> В настоящее время только конечный пользователь, имеющий доступ к почтовому ящику, может восстановить элементы из папки с обратимым удалением.

Не поддаются **действиям**: сообщения электронной почты из следующих расположений не могут обрабатываться или перемещаться как часть действий электронной почты, т. е. сообщения в категории, не относящиеся к ремедиабле, не могут быть перемещены в категорию, отличной от ремедиабле, и в ремедиабле. Расположения, отличные от ремедиабле: 

  - Карантин 
  - Окончательная удаленная папка
  - Локальная/внешняя 
  - Отправленные и отклоненные подозрительные сообщения классифицируются как ремедиабле или не ремедиабле. В большинстве случаев сообщения ремедиабле и не ремедиабле должны добавляться к общему количеству отправленных сообщений. Однако могут возникнуть редкие случаи, в которых отправляемые сообщения могут не доставляться до суммы элементов ремедиабле и не ремедиабле, а также могут быть выше или ниже, чем общее количество отправленных сообщений. Это может произойти из-за задержки системы, таймаутов или просроченных сообщений. Срок хранения сообщений зависит от срока хранения в Организации. 

Если вы не устранение старые сообщения после срока хранения в проводнике вашей организации, если вы видите несоответствия в числах, рекомендуется перезапустить устранение элементы. В случае задержки системы обновления исправлений обычно обновляются в течение нескольких часов. 

Если срок хранения в Организации для электронной почты в Explorer составляет 30 дней, а устранение отправляются через 29-30 дней назад, счетчики отправки почты могут не всегда добавляться, так как сообщения могут начаться за период хранения. 

Если в течение какого-либо состояния исправления в течение какого-то времени застряла, это может быть вызвано задержками системы. Исправление может занять несколько часов. Возможна ситуация, когда количество отправленных сообщений не является частью запроса при запуске исправления из-за задержки системы. В таких случаях рекомендуется повторить попытку устранение.  

Для достижения лучших результатов исправление должно выполняться в небольших пакетах вокруг 50k или меньшего числа сообщений электронной почты.  

Все сообщения электронной почты, отправляемые по электронной почте, ремедиабле только те, которые будут обрабатываться при исправлении. Сообщения электронной почты, не относящиеся к ремедиабле, не могут быть исправлены системой электронной почты Office 365, так как они не хранятся в облачных почтовых ящиках. 

Для сообщений, обнаруженных в карантине, администраторы могут переходить в карантин, чтобы выполнять действия с этими сообщениями, если это необходимо, но сообщения электронной почты истечет из карантина, если они не были очищены вручную. Почтовые сообщения, помещенные в карантин с помощью вредоносного контента, недоступны для конечных пользователей, поэтому персоналу безопасности не нужно предпринимать какие-либо действия, чтобы избавиться от угроз в карантине. Если сообщения хранятся на локальном или внешнем уровне, можно связаться с конечным пользователем, чтобы устранить подозрительные сообщения электронной почты или использовать отдельные средства сервера или средства безопасности для удаления. Эти сообщения можно определить путем применения места доставки = локальный/внешний фильтр в обозревателе угроз. Для неудачных или пропущенных сообщений электронной почты или сообщений, недоступных конечному пользователю, не должно быть электронной почты для устранения, так как они не достигают почтового ящика. 

Так как отправка отображается в центре уведомлений. Исправление может содержать несколько отправок. Если несколько действий утверждены за одно автоматическое исследование, каждое действие электронной почты или кластера электронной почты будет отображаться в том же исправлении, что и в другой отправке.

[Раскрывающаяся панель кластера электронной почты ZAP.](../../media/tp-RemediationArticle6.png)

При нажатии элемента отправки почты отображаются сведения об этих исправлениях, таких как запрос (при условии, что оно запускается с помощью автоматизированного расследования или проводника по угрозам, выбирая запрос), время начала и время окончания исправления. Кроме того, отображается список сообщений, отправленных для исправления. По мере того как сообщения выходят за срок хранения в проводнике, сообщения исчезнут из этого списка. В этом списке также показаны отдельные сообщения из списка ремедиабле.

2. **Вкладка журналы действий**: на этой вкладке показан результат исправления сообщений, в том числе сведения об утвержденных датах, утверждающем (администраторе, который утвердил действие), действии, состоянии и счетчиках.  

Status — общее состояние исправления. Состояние может принимать следующие значения: 

  - **Начато**: при срабатывании исправления. 
  - **Помещен в очередь**: при исправлении сообщений в очереди. 
  - **В ходе выполнения**: при снижении риска. 
  - **Завершено**: при успешном снижении по всем ремедиабле сообщениям электронной почты или при наличии некоторых сбоев. 
  - **Сбой**: при отсутствии исправлений. 

Как только сообщения ремедиабле могут быть обработаны, очистка каждой почты считается успешной или неудачной. Из общей ремедиабле электронной почты мы предоставляем успешные и неудачные меры. 

  - **Успех**: при выполнении желаемого действия с электронной почтой ремедиабле и совпадение с намерением администрирования. Например: администратор хочет удалить сообщения электронной почты из почтовых ящиков, чтобы они могли удалить электронную почту с возможностью их обратимого удаления. Если после выполнения действия сообщение электронной почты ремедиабле не найдено в исходной папке, состояние будет отображаться как успешное.  

  - **Сбой**: при неудачном выполнении желаемого действия с ремедиабле электронной почтой. Например: администратор хочет удалить сообщения электронной почты из почтовых ящиков, поэтому он выполняет действие обратимого удаления сообщений электронной почты. Если электронная почта ремедиабле по-прежнему находится в почтовом ящике, в поле Состояние отображается значение ошибка. 

При выборе любого элемента в журнале действий отображается подробная информация об исправлении. В случае успешного выполнения элементов, если сведения говорят, успешно или не найдены в почтовом ящике, это означает, что элемент уже удален из почтового ящика. Иногда возникают ошибки, возникающие из-за системной ошибки во время исправления, и в таких случаях рекомендуется повторно попытаться выполнить исправление.  

Исправление это мощный инструмент для устранения угроз и устранения подозрительных сообщений, сообщений электронной почты. Это помогает обеспечить надежную и безопасную организацию.  

## <a name="more-info"></a>Дополнительные сведения

Просмотр [вредоносных сообщений электронной почты](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

