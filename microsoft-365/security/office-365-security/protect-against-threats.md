---
title: Защита от угроз
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Администраторы могут узнать о защите от угроз в Microsoft 365 и настроить способ ее использования в Организации.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 54500500095392ebfc3d93080701fa4715fc8448
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617400"
---
# <a name="protect-against-threats"></a>Защита от угроз

Microsoft 365 включает различные функции защиты от угроз. Вот краткое руководство, которое можно использовать в качестве контрольного списка, чтобы убедиться в том, что функции защиты от угроз настроены для Организации. Если вы не знакомы с функциями защиты от угроз в Office 365, или вы только не знаете, с чего начать, используйте следующие рекомендации в качестве отправной точки.

> [!IMPORTANT]
> **Начальные Рекомендуемые параметры включены для каждого типа политики, но многие варианты доступны, и вы можете настроить параметры в соответствии с потребностями конкретной организации**. Разрешите около 30 минут, чтобы политики или изменения работали с центром обработки данных.

## <a name="requirements"></a>Requirements

### <a name="subscriptions"></a>Подписки

Функции защиты от угроз включены во все подписки Microsoft 365; Однако некоторые подписки включают более сложные функции. В следующей таблице перечислены функции защиты, включенные в эту статью, с минимальными требованиями к подписке.<br/>

|||
|---|---|
|**Тип защиты**|**Требование к подписке**|
|Защита от вредоносных программ|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (EOP)|
|Защита от вредоносных URL-адресов и файлов в электронной почте и документах Office|[Office 365 Advanced Threat protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP)|
|Защита от фишинга|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Расширенная защита от фишинга|[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Защита от нежелательной почты|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Автоматическая очистка нулевого времени (для электронной почты)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Ведение журнала аудита (используется в целях создания отчетов)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a>Роли и разрешения

Необходимо назначить соответствующую роль для настройки политик в [центре безопасности & соответствия требованиям](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). В таблице приведено несколько примеров.

|Роль или группа ролей|Дополнительные сведения|
|---------|---------|
|Глобальный администратор|[О ролях администратора Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Администратор безопасности|[Разрешения роли администратора в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Управление организациями в Exchange Online|[Разрешения в Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>и<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Чтобы узнать больше, ознакомьтесь [с разрешениями в центре безопасности и &amp; соответствия требованиям](permissions-in-the-security-and-compliance-center.md).

## <a name="part-1---anti-malware-protection"></a>Часть 1 — Защита от вредоносных программ

[Защита от вредоносных программ](anti-malware-protection.md) доступна в подписках, включающих [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. В [центре безопасности & соответствия требованиям](https://protection.office.com)выберите политику **управления угрозами**для  >  **Policy**  >  **защиты от вредоносных программ**.

2. Дважды щелкните политику **по умолчанию** , а затем выберите **Параметры**.

3. Укажите следующие параметры:

    - В разделе **ответ на обнаружение вредоносных программ** оставьте значение по умолчанию ( **нет**).

    - В разделе **фильтр типов вложений** выберите **включено**.

4. Нажмите кнопку **Сохранить**.

Дополнительные сведения о параметрах политики защиты от вредоносных программ приведены в разделе [Настройка политик защиты от вредоносных](configure-anti-malware-policies.md)программ.

## <a name="part-2---protection-from-malicious-urls-and-files"></a>Часть 2 — Защита от вредоносных URL-адресов и файлов

Защита от использования вредоносных URL-адресов и файлов доступна в подписках, включающих [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP), и настраивается с помощью политик [безопасных вложений](atp-safe-attachments.md) ATP и " [безопасные ссылки ATP](atp-safe-links.md) ".

### <a name="atp-safe-attachments-policies"></a>Политики безопасных вложений ATP

Для настройки [безопасных вложений ATP](atp-safe-attachments.md)необходимо определить по крайней мере одну политику безопасных вложений ATP.

1. В [центре безопасности & соответствия требованиям](https://protection.office.com)выберите политика **управления угрозами**  >  **Policy**  >  **безопасные вложения ATP**.

2. Выберите параметр **включить ATP для SharePoint, OneDrive и Microsoft Teams**.

3. В разделе **защита вложений электронной почты** щелкните знак "плюс" ( **+** ).

4. Укажите следующие параметры:

   - В поле **имя** введите `Block malware` .

   - В разделе ответ выберите пункт **блокировать**.

   - В разделе **Перенаправление вложения** выберите параметр **включить перенаправление**, а затем укажите адрес электронной почты администратора безопасности Организации или оператора, который будет просматривать обнаруженные файлы.

   - В разделе **применено** выберите **домен получателя**. Затем выберите свой домен, нажмите кнопку **Добавить**, а затем нажмите кнопку **ОК**.

5. Нажмите кнопку **Сохранить**.

6. (**Рекомендуемое дополнительное действие**) Как глобальный администратор или администратор SharePoint Online выполните командлет **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** с параметром **дисалловинфектедфиледовнлоад** , для которого задано *значение true* для среды Microsoft 365. (Это предотвращает открытие, перемещение, копирование или совместное использование файлов, обнаруженных как вредоносные.)

Дополнительные сведения: [Настройка политик безопасных вложений office 365 ATP](set-up-atp-safe-attachments-policies.md) и [Включение Office 365 ATP для SharePoint, OneDrive и Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

### <a name="atp-safe-links-policies"></a>Политики безопасных ссылок ATP

Чтобы настроить [безопасные ссылки ATP](atp-safe-links.md), просмотрите и измените политику по умолчанию и добавьте политику для определенных пользователей.

1. В [центре безопасности & соответствия требованиям](https://protection.office.com)выберите политику **управления угрозой**  >  **Policy**  >  **безопасные ссылки ATP**.

2. Дважды щелкните политику **по умолчанию** .

3. В разделе **использовать безопасные ссылки в** выберите параметр **Microsoft 365 для корпоративных приложений, Office для iOS и Android**, а затем нажмите кнопку **сохранить**.

4. В разделе **политики, которые применяются к определенным получателям** щелкните знак "плюс" ( **+** ).

5. Укажите следующие параметры:

   - В поле **имя** введите имя, например `Safe Links` .

   - В разделе **Выбор действия** выберите **включить**.

   - Выберите следующие параметры:

     - **Использование безопасных вложений для сканирования загружаемого контента**

     - **Применение безопасных ссылок к сообщениям электронной почты, отправленным в Организации**

     - **Не разрешать пользователям щелкать ссылки с исходным URL-адресом.**

   - В разделе **применено** выберите **домен получателя**. Затем выберите свой домен, нажмите кнопку **Добавить**, а затем нажмите кнопку **ОК**.

6. Нажмите кнопку **Сохранить**.

Дополнительные сведения см. в статье [Настройка политик безопасных ссылок ATP в Office 365](set-up-atp-safe-links-policies.md).

## <a name="part-3---anti-phishing-protection"></a>Часть 3 — Защита от фишинга

[Защита от фишинга]

[Защита от фишинга](anti-phishing-protection.md) доступна в подписках, включающих [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Расширенная защита от фишинга доступна в [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

В следующей процедуре описывается настройка антифишинговой политики ATP. Эти действия похожи на настройку антифишинговой политики (без ATP).

1. В [центре безопасности & соответствия требованиям](https://protection.office.com)выберите политику **управления угрозами**для  >  **Policy**  >  **защиты от фишинга ATP**.

2. Щелкните **Политика по умолчанию**.

3. В разделе **олицетворение** нажмите кнопку **изменить**, а затем укажите следующие параметры:

   - На вкладке **Добавление пользователей для защиты** включите защиту. Затем добавьте пользователей, например, участников вашей организации, Генерального директора, финансового директора и других старших руководителей. (Вы можете ввести отдельный адрес электронной почты или щелкнуть для отображения списка.)

   - На вкладке **Добавление доменов для защиты** включите **Автоматическое включение доменов, которыми я владеют**. Если у вас есть пользовательские домены, добавьте их также.

   - На вкладке **действия** выберите пункт **карантин сообщения** для параметров **олицетворенного пользователя** и **олицетворенного домена** . Кроме того, включите советы по безопасности олицетворения.

   - На вкладке **аналитика почтовых ящиков** убедитесь, что включена функция интеллектуального анализа почтовых ящиков. Кроме того, включите защиту от олицетворения на основе логики почтовых ящиков. В разделе **Если сообщение отправляется в списке олицетворенного пользователя** , выберите пункт **помещать сообщение в карантин**.

   - На вкладке **Добавление надежных отправителей и доменов** укажите все доверенные отправители или домены, которые вы хотите добавить.

   - На вкладке **Проверка параметров** после просмотра параметров нажмите кнопку **сохранить**.

4. В разделе **подделка** нажмите кнопку **изменить**, а затем укажите следующие параметры:

   - На вкладке **Параметры фильтра подделки** убедитесь, что включена защита от спуфинга.

   - На вкладке **действия** выберите пункт **помещать сообщение в карантин**.

   - На вкладке **Проверка параметров** после просмотра параметров нажмите кнопку **сохранить**. (Если изменения не были внесены, нажмите кнопку **Отмена**.)

5. Закройте страницу параметров политики по умолчанию.

Чтобы узнать больше о параметрах политики защиты от фишинга, ознакомьтесь со статьей [Настройка политик защиты от фишинга ATP](configure-atp-anti-phishing-policies.md).

## <a name="part-4---anti-spam-protection"></a>Часть 4: защита от нежелательной почты

[Защита от нежелательной почты](anti-spam-protection.md) доступна в подписках, включающих [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. В [центре безопасности & соответствия требованиям](https://protection.office.com)выберите политика **управления угрозами**  >  **Policy**  >  **защиты от нежелательной почты**.

2. На вкладке **Настройка** включите **пользовательские параметры** .

3. Разверните узел **Политика фильтрации нежелательной почты по умолчанию**, щелкните **изменить политику**, а затем укажите следующие параметры:

   - В разделе **Нежелательная почта и групповые действия** установите для порогового значения 5 или 6.

   - В разделе **разрешить списки** просмотрите (и при необходимости измените) разрешенных отправителей и доменов.

4. Нажмите кнопку **Сохранить**.

Дополнительные сведения о параметрах политики защиты от нежелательной почты приведены [в разделе Настройка политик защиты от нежелательной почты в EOP](configure-your-spam-filter-policies.md).

## <a name="part-5---additional-settings-to-configure"></a>Часть 5 — Дополнительные параметры для настройки

В дополнение к настройке защиты от вредоносных программ, вредоносных URL-адресов и файлов, фишинговых и нежелательных сообщений рекомендуется настраивать параметры ведения журнала в автоматическом и автоматическом времени.

### <a name="zero-hour-auto-purge-for-email"></a>Автоматическая очистка электронной почты с нулевым часовым значением

[Автоматическая очистка](zero-hour-auto-purge.md) (ZAP) с нулевым часовым циклом доступна в подписках, включающих [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Эта защита включается по умолчанию; Однако для вступления в последствия защиты должны выполняться следующие условия:

- Для действий нежелательной почты настраивается **Перемещение сообщения в папку нежелательной почты** в [политиках защиты от нежелательной почты](anti-spam-protection.md).

- Пользователи сохраняли свои [Параметры нежелательной почты](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)по умолчанию и не отключили защиту от нежелательной почты.

Для получения дополнительных сведений о [нежелательной почте и вредоносном программном обеспечении автоматическая очистка без защиты от нежелательной почты](zero-hour-auto-purge.md).

### <a name="audit-logging-for-reporting-and-investigation"></a>Ведение журнала аудита для создания отчетов и исследования

Ведение журнала аудита доступно в подписках, включающих [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Для просмотра данных в отчетах защиты от угроз, таких как [панель мониторинга безопасности](security-dashboard.md), [отчеты о безопасности электронной почты](view-email-security-reports.md)и [проводник](threat-explorer.md), для Организации необходимо включить ведение журнала аудита. Дополнительные сведения см. [в разделе Включение поиска в журнале аудита](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="post-setup-tasks"></a>Задачи, выполняемые после установки

После того как вы настроили функции защиты от угроз, следите за тем, как работают эти функции, изучите и измените свои политики, а также следите за новыми функциями и обновлениями служб.

|||
|---|---|
|**Действия**|**Дополнительные ресурсы**|
|Узнайте, как функции защиты от угроз работают в вашей организации, просмотрев отчеты|[Панель мониторинга безопасности](security-dashboard.md)<br/>[Отчеты по безопасности электронной почты](view-email-security-reports.md)<br/>[Отчеты для Office 365 ATP](view-reports-for-atp.md)<br/>[Обозреватель угроз](threat-explorer.md)|
|При необходимости периодически проверяйте и изменяйте политики защиты от угроз.|[Оценка безопасности](../mtp/microsoft-secure-score.md)<br/>[Интеллектуальные отчеты и аналитика](reports-and-insights-in-security-and-compliance.md)<br/>[Исследование угроз и функции ответа Microsoft 365](keep-users-safe-with-office-365-ti.md)|
|Просмотр новых компонентов и обновлений служб|[Варианты стандартных и целевых выпусков](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Центр сообщений](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[План выпуска Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Описания служб](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
