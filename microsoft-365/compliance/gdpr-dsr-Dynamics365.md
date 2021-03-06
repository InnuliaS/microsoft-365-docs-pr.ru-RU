---
title: Запросы субъектов данных Dynamics 365, определенные GDPR и CCPA
description: Узнайте, как искать и обрабатывать личные данные и отвечать на запросы DSR и CCPA, сделанные клиентами Dynamics 365.
keywords: Microsoft 365, Microsoft 365 для образования, документация по Microsoft 365, GDPR, CCPA
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
hideEdit: true
ms.custom:
- seo-marvel-mar2020
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 04ecbd6e52a56ea83f3b2e2eaebd02de20cfbe52
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817668"
---
# <a name="dynamics-365-data-subject-requests-for-the-gdpr-and-ccpa"></a>Запросы субъектов данных Dynamics 365, определенные GDPR и CCPA

The European Union [General Data Protection Regulation (GDPR)](https://ec.europa.eu/justice/data-protection/reform/index_en.htm) gives rights to people (known in the regulation as *data subjects*) to manage the personal data that has been collected by an employer or other type of agency or organization (known as the *data controller* or just *controller*). Personal data is defined broadly under the GDPR as any data that relates to an identified or identifiable natural person. The GDPR gives data subjects specific rights to their personal data; these rights include obtaining copies of it, requesting changes to it, restricting the processing of it, deleting it, or receiving it in an electronic format so it can be moved to another controller. A formal request by a data subject to a controller to take an action on their personal data is called in this document a *Data Subject Rights Request* or DSR request.

Аналогичным образом, Калифорнийский закон о защите прав потребителей (CCPA) предоставляет права и обязанности в отношении конфиденциальности для калифорнийских потребителей, включая права, аналогичные правам субъектов данных GDPR, такие как право на удаление, доступ и получение (переносимость) их личной информации.  CCPA также предусматривает определенное раскрытие информации, защиту от дискриминации при избрании прав на осуществление и требования «отказаться / подписаться» для определенных передач данных, классифицированных как «продажи». Широкое определение продаж включает обмен данными для встречного удовлетворения. Дополнительные сведения о CCPA см. в статьях [Закон Калифорнии о конфиденциальности данных](offering-ccpa.md) и [Вопросы и ответы о законе Калифорнии о конфиденциальности данных](ccpa-faq.md).

В руководстве рассматривается использование продуктов, служб и средств администрирования Майкрософт, позволяющих управляющим находить персональные данные и выполнять с ними действия в ответ на запросы DSR. В частности, это включает инструкции по поиску персональных данных или персональной информации, которые находятся в облаке Майкрософт, получению к ним доступа и выполнению в отношении них действий. Вот краткий обзор процессов, описанных в этом руководстве:

- **Обнаружение.** Используйте средства поиска и обнаружения, чтобы легко находить клиентские данные, которые могут быть предметом запроса DSR. Собрав соответствующие документы, можно выполнить одно или несколько из описанных в следующих шагах действий DSR, чтобы ответить на запрос. Кроме того, можно определить, что запрос не соответствует рекомендациям вашей организации по ответу на запросы DSR.
- **Доступ.** Получение персональных данных, размещенных в облаке Майкрософт, и предоставление копии этих данных субъекту данных.
- **Уточнение.** Внесение изменений или выполнение других запрошенных действий с персональными данными (если это возможно).
- **Ограничение**. Ограничьте обработку персональных данных, по возможности удалив лицензии для различных веб-служб или отключив соответствующие службы. Вы можете следующее
- **Удаление.** Безвозвратное удаление персональных данных, хранящихся в облаке Майкрософт.
- **Экспорт и получение (переносимость).** Предоставление электронной копии персональных данных или личных сведений (в машиночитаемом формате) субъекту данных. В рамках CCPA персональные данные — это любая информация, относящаяся к идентифицированному или идентифицируемому лицу. Нет различия между личными, общественными или рабочими ролями человека. Определение термина "личные сведения" в общих чертах совпадает с определением термина "персональные данные" в GDPR. Кроме того, CCPA также распространяется на данные о семье и домашнем хозяйстве. Дополнительные сведения о CCPA см. в статьях [Закон Калифорнии о конфиденциальности данных](offering-ccpa.md) и [Вопросы и ответы о законе Калифорнии о конфиденциальности данных](ccpa-faq.md).

В каждом разделе этого руководства описываются технические процедуры, которые организация, управляющая данными, может выполнять в ответ на запрос DSR на персональные данные в облаке Майкрософт.

### <a name="gdpr-terminology"></a>Терминология GDPR

Ниже представлены определения терминов, относящихся к данному руководству.

- **Управляющий** — физическое или юридическое лицо, орган государственной власти, агентство или другое лицо, которое отдельно от других или вместе с ними определяет цели и средства обработки персональных данных. Если цели и средства такой обработки данных определены законом Союза или государства-участника, в этом законе может быть указан управляющий или определенные критерии для его назначения.
- **Персональные данные и субъект данных** — любая информация, связанная с идентифицированным или идентифицируемым физическим лицом ("субъектом данных"). Идентифицируемым физическим лицом считается человек, чью личность можно прямо или косвенно установить, в частности с помощью идентификатора, такого как имя, идентификационный номер, данные о местоположении, идентификатор в сети, либо с использованием одного или нескольких факторов, связанных с физическими, физиологическими, генетическими, умственными, экономическими, культурными или социальными характеристиками этого физического лица.
- **Обработчик** — физическое или юридическое лицо, орган государственной власти, агентство или другое лицо, которое обрабатывает персональные данные от лица управляющего.
- **Данные клиента** — все данные, включая текстовые, звуковые, видеофайлы или файлы изображений, а также программное обеспечение, которые предоставляются корпорации Майкрософт клиентом или от его имени через корпоративную службу. К данным клиента относятся (1) информация, позволяющая идентифицировать пользователей (например, их имена и контактные данные в Azure Active Directory), и контент клиента, отправляемый или создаваемый им в определенных службах (например, контент в учетной записи службы хранилища Azure либо базе данных Azure SQL или образ виртуальной машины Azure).
- **Системные журналы** — журналы и соответствующие данные, созданные корпорацией Майкрософт, которые помогают ей предоставлять пользователям корпоративные службы. Системные журналы в основном содержат псевдонимизированные данные, например уникальные идентификаторы. Как правило, это сгенерированное системой число, по которому невозможно установить личность конкретного человека, но можно предоставлять пользователям корпоративные службы. Системные журналы также могут содержать сведения, позволяющие идентифицировать конечных пользователей, например имя пользователя.

### <a name="how-this-guide-can-help-you-meet-your-controller-responsibilities"></a>Сведения о том, как с помощью данного руководства можно выполнить обязанности управляющего данными

Данное руководство разделено на две части и описывает использование продуктов, служб и средств администрирования Dynamics 365 для поиска данных в облаке Майкрософт и выполнения действий над ними в ответ на запросы субъектов данных, которые пользуются своими правами в рамках GDPR. Первая часть посвящена персональным данным, которые включены в данные клиента, а в следующей части рассматриваются остальные псевдонимизированные персональные данные, собранные из системного журнала.

- **Часть 1. Реагирование на запросы прав субъекта данных (DSR) для персональных данных, включенных в данные клиента.** В первой части этого руководства описывается, как получать доступ к персональным данным, обрабатываемым в составе данных клиента, которые вы предоставили веб-службе, а также как исправлять, ограничивать, удалять и экспортировать их из приложений Dynamics 365 (программное обеспечение как услуга).
- **Часть 2. Реагирование на запросы прав субъекта данных для псевдонимизированных данных.** Когда вы используете корпоративные службы Dynamics 365, Майкрософт генерирует некоторую информацию (в этом документе называется как *системные журналы*) для предоставления службы, которая ограничена объемом нагрузки использования конечными пользователями, для определения их действий в системе. Такие данные невозможно связать с конкретным субъектом данных без использования дополнительных сведений, некоторые из которых могут рассматриваться в качестве персональных данных, определяемых в GDPR. Во второй части данного руководства рассматривается доступ к системным журналам, а также их удаление и экспорт, выполняемые Dynamics 365.

### <a name="preparing-for-data-subject-rights-investigations"></a>Подготовка расследований, связанных с правами субъектов данных

Когда субъекты данных используют свои права и отправляют запросы, учитывайте указанные ниже моменты.

- Правильно определите человека и роль (например, сотрудник, клиент, исполнитель), используя информацию, которую субъект данных передал вам в рамках своего запроса. Этой информацией может быть имя, ИД сотрудника, номер клиента или другой идентификатор.
- Record the data and time of the request. (You have 30 days to complete the request.)
- Affirm that the request meets your organization's requirements for honoring or declining a data subject's request. For example, you must make sure that executing the request doesn't conflict with any other legal, financial, or regulatory obligations that you have, or infringe on the rights and freedoms of others.
- Убедитесь, что у вас есть информация, связанная с запросом.

## <a name="part-1-responding-to-data-subject-rights-requests-for-personal-data-included-in-customer-data"></a>Часть 1. Реагирование на запросы, связанные с правами субъектов данных, в отношении персональных данных, входящих в состав данных клиентов

Ниже вы найдете информацию, которая поможет вам подготовиться к DSR-запросам персональных данных, включенных в обрабатываемые в Dynamics 365 данные клиента, и отвечать на них. Важно отметить, что персональные данные могут присутствовать в других категориях данных, обрабатываемых корпорацией Майкрософт во время обслуживания подписки на веб-службы, например данные администратора или данные поддержки, определенные в Заявлении о конфиденциальности корпорации Майкрософт. Этот документ представлен в сжатом виде, чтобы помочь вам находить DSR-запросы, затрагивающие персональные данные, включенные в данные клиента, которые вы предоставили в Dynamics 365, и управлять ими.

Dynamics 365 — это веб-служба, которая предоставляется по модели SaaS и обеспечивает широкие возможности для обработки данных. Они могут отличаться в зависимости от происхождения, цели и других специфических атрибутов, таких как данные о продажах, транзакции, финансовые показатели, информация о персонале и т. д. В свете этого разнообразия Dynamics 365 также предлагает различные формы, поля, схемы, конечные точки и логику для обработки данных клиента, которые позволяют удовлетворить DSR-запросы в каждом приложении. Если реагировать на запросы DSR в приложениях Dynamics 365 можно несколькими способами, мы отметим их в данном руководстве, указав технические описания, предлагаемые каждым приложением.

### <a name="dynamics-365"></a>Dynamics 365

#### <a name="finding-customer-data"></a>Поиск данных клиентов

Чтобы отреагировать на запрос по правам субъекта данных, сначала нужно найти и идентифицировать данные клиента, которые относятся к этому запросу.

Правильная классификация данных клиента — основа работы с персональными данными в бизнес-приложениях Dynamics 365 Customer Engagement. Dynamics 365 for Customer Engagement позволяет создавать расширения приложений на основе классификации данных. Правильная классификация позволяет идентифицировать сведения как персональные данные, благодаря чему их можно находить и извлекать, реагируя на запросы от субъекта данных. Она также помогает обеспечивать соответствие требованиям законодательства и нормативных органов относительно сбора персональных данных и управления ими.

Майкрософт предоставляет возможности для реагирования на запросы по правам субъекта данных и последующего получения доступа к данным клиента. Однако вы несете ответственность за надлежащее размещение и классификацию персональных данных.

***Dynamics 365 for Customer Engagement*** предоставляет несколько методов поиска персональных данных среди записей, например расширенный поиск и поиск по записям. Эти функции позволяют идентифицировать (находить) персональные данные.

- [Расширенный поиск](https://docs.microsoft.com/dynamics365/customer-engagement/basics/save-advanced-find-search).
- [Поиск по записям](https://docs.microsoft.com/dynamics365/customer-engagement/basics/search-records).

В Dynamics 365 for Marketing вы также можете выполнять следующие действия:

1. [Создавать отчеты Power BI](https://docs.microsoft.com/power-bi/service-connect-to-microsoft-dynamics-crm) для фильтрации и идентификации данных клиента.
2. Использовать аналитические представления для контактов и объектов проведения маркетингового мероприятия, чтобы определять дополнительные точки данных, которые могут содержать данные клиента.

***Dynamics 365 Customer Service Insights*** представляет список ресурсов, помогающих [находить данные клиента](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-discovery), чтобы отвечать на запросы GDPR от клиентов. 

***Dynamics 365 for Finance and Operations*** позволяет искать данные клиента несколькими способами. Как администратор клиента вы можете выполнить для этого следующие действия:

- Упорядочить данные клиента для быстрого обнаружения персональных данных. Чтобы сделать это, см. статью о том, [как классифицировать перечень данных](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#detailed-inventory).
- Использовать [отчет о результатах поиска человека](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report), чтобы найти и собрать персональные данные.
- [Расширить отчет о результатах поиска человека](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report), создав новый объект или расширив уже существующий.
- Использовать функции поиска и фильтрации, чтобы найти данные определенного человека и экспортировать их с помощью функций экспорта в Microsoft Office Export или распечатать эту информацию в PDF-файл с помощью расширений браузера.
- Создать настраиваемую форму, которая находит и экспортирует персональные данные.
- Создать внешний портал или веб-сайт, позволяющий клиенту, прошедшему проверку подлинности, получить доступ к своим персональным данным.

***Dynamics 365 Business Central*** позволяет искать данные клиента несколькими способами. Дополнительные сведения см. в статье [Поиск, фильтрация и сортировка данных](https://docs.microsoft.com/dynamics365/business-central/ui-enter-criteria-filters).

***Dynamics 365 for Talent*** предоставляет функции расширенного поиска и фильтрации для обнаружения определенных персональных данных и функции Microsoft Office Export для экспорта или печати этой информации в PDF-файл с помощью расширений браузера.

- Используйте [отчет о результатах поиска человека](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#the-person-search-report), чтобы найти и собрать данные клиента.
- [Расширьте отчет о результатах поиска человека](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report), создав новый объект или расширив уже существующий.

### <a name="providing-a-copy-of-customer-data"></a>Предоставление копии данных клиента

Данные клиента в ***Dynamics 365 for Customer Engagement*** можно экспортировать, используя широкие возможности экспорта объектов. Данные клиента можно экспортировать в статический файл Excel для облегчения запроса на перенос данных. Затем в Excel вы можете изменить персональные данные, чтобы включить их в запрос на перенос, и сохранить в распространенном машиночитаемом формате типа CSV или XML. Пакет Dynamics 365 для записей средства Customer Engagement также можно экспортировать с помощью [Common Data Service Web API](https://docs.microsoft.com/powerapps/developer/common-data-service/webapi/overview).

Additionally, for Dynamics 365 for Marketing a [dedicated API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) is provided that allows customer to build extensions that retrieve additional records of captured customer interactions that may contain personal data. The API loads all the relevant information from the back-end system and assembles it into a single, portable document.

***Dynamics 365 Customer Service Insights*** позволяет [предоставлять копию данных клиента](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export) с помощью экспорта данных.

Данные клиента в ***Dynamics 365 for Finance and Operations*** можно экспортировать, используя широкие возможности экспорта объектов. Администратор клиента может использовать [*объекты для управления данными и интеграции*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), создавать новые или расширять существующие, чтобы экспортировать персональные данные в Excel или другие распространенные форматы через [*задания импорта и экспорта данных*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job).  Кроме того, для упрощения запроса на перенос данных многие списки можно экспортировать в статический файл Excel. Экспортированные в Excel данные клиента можно изменить, чтобы персональные данные были включены в запрос на перенос, а затем сохранить файл в распространенном машиночитаемом формате типа CSV или XML. Вы также можете использовать *отчет о результатах поиска человека*, чтобы предоставить субъекту данных те данные, которые вы классифицировали как персональные.

В ***Dynamics 365 Business Central*** можно использовать две функции, чтобы предоставить субъекту данных копию данных клиента:

Вы можете экспортировать данные клиента в файл Excel, затем отредактировать их в Excel, чтобы включить их в запрос на перенос, и сохранить файл в распространенном машиночитаемом формате типа CSV или XML. Подробные сведения см. в статье [Экспорт бизнес-данных в Excel.](https://docs.microsoft.com/dynamics365/business-central/about-export-data)

В ***Dynamics 365 for Talent*** можно [расширить отчет о результатах поиска человека](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-extend-person-search-report), чтобы собрать информацию для подтверждения запроса на копирование персональных данных субъекта.

### <a name="rectifying-customer-data"></a>Уточнение данных клиентов

В ***Dynamics 365 for Customer Engagement*** доступны указанные ниже методы исправления или удаления неточных или неполных данных клиента.

- Поиск данных клиента с помощью функций, упомянутых в разделе "Поиск данных клиента", и непосредственное изменение данных в формах Customer Engagement. Изменять можно как одну, так и несколько строк сразу.
- Операция массового редактирования нескольких записей в Customer Engagement. Вы можете использовать надстройку Microsoft Office, чтобы экспортировать данные в Microsoft Excel, внести изменения, а затем импортировать обновленные данные из Excel в Dynamics 365 for Customer Engagement.

Кроме того, для Dynamics 365 for Marketing вы также можете:

- Обновить целевую страницу update-my-data (обновить-мои-данные), напрямую изменив одну или несколько строк.
- Prepare a [subscription centers](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-subscription-center) page that has as many editable contact fields that can be included. This enables an end user to update their own information as much as possible.

***Dynamics 365 Customer Service Insights*** также предоставляет возможности, позволяющие организациям [уточнять или изменять данные клиента](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-summary).

В ***Dynamics 365 for Finance and Operations*** вы также можете использовать [*средства настройки*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page), но решение и исполнение находятся в сфере вашей ответственности.

В ***Dynamics 365 Business Central*** исправить неточные или неполные данные клиента можно двумя способами.

To quickly bulk-edit multiple Business Central records, you can export lists to Excel using the [Business Central Excel Add-in](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) to correct multiple records, and then publish the modified data from Excel in Business Central. For details, see [Exporting your Business Data to Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).

Вы можете изменить данные клиента, хранимые в любом поле, например информацию о клиенте в карточке клиента, вручную изменив элемент данных, содержащий целевые персональные данные. Подробные сведения см. в статье [Ввод данных](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).

#### <a name="brief-note-about-modifying-entries-in-business-transactions"></a>Краткое примечание об изменении записей в бизнес-транзакциях

Transactional records, such as general, customer, and tax ledger entries, are essential to the integrity of an enterprise resource planning system. Personal data that is part of a financial or other transaction is kept "as is" for compliance with financial laws (for example, tax laws), prevention of fraud (such as security audit trail), or compliance with industry certifications. Therefore, Dynamics 365 for Finance and Operations and Dynamics 365 Business Central restrict modifying data in such records.

If you store personal data in business transaction records, the only way to correct, delete, or restrict processing of personal data to honor a data subject's request is to use the Dynamics 365 Business Central [customization capabilities](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/index). Th[](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/gdpr-guide#reasons-why-certain-personal-data-may-not-be-modified-or-deleted)e decision to honor a modification data subject request and implementation thereof is your responsibility.

### <a name="restricting-the-processing-of-customer-data"></a>Запрет на обработку данных клиентов

Если вы получили от субъекта данных запрос на ограничение обработки данных клиента, вы можете просто извлечь необходимые данные из веб-службы и хранить их в отдельном контейнере (т. е. в локальном хранилище или в отдельной веб-службе, которая имеет возможность изолирования данных), обособленно от функций обработки, предлагаемых любым облачным приложением.

***Dynamics 365 Business Central*** предлагает альтернативный механизм, такой как блокировка обработки данных, где пользователи могут заблокировать определенную запись с данными субъекта. Подробные сведения см. в разделе [Ограничение обработки данных для субъекта данных](https://docs.microsoft.com/dynamics365/business-central/admin-responding-to-requests-about-personal-data#restrict-data-processing-for-a-data-subject). Если запись помечена как заблокированная, Dynamics 365 Business Central остановит обработку данных клиента этого субъекта данных. Вы не сможете создавать новые транзакции, использующие заблокированную запись; например, вам не удастся создать новый счет для клиента, если клиент или продавец заблокированы.

### <a name="deleting-customer-data"></a>Удаление данных клиентов

Если субъект данных запрашивает удаление своих данных клиента, это можно сделать несколькими указанными ниже способами.

- Чтобы выполнить операцию массового редактирования нескольких записей в Dynamics 365, вы можете использовать надстройку Microsoft Office для экспорта данных в Microsoft Excel, внести изменения, а затем импортировать обновленные данные из Excel обратно в веб-службу.
- Вы можете удалить данные клиента, хранящиеся в любом поле, определив местоположение удаляемых данных, а затем вручную удалив элемент, содержащий целевые данные клиента, например, как при использовании необратимого удаления для записи контакта, представляющей субъект данных, и остальных записей, содержащих персональные данные.

Кроме того, для Dynamics 365 Marketing удаление контакта гарантирует, что вместе с персональной информацией будут удалены данные о взаимодействии. Для любых настраиваемых полей или объектов вы должны настроить свою систему таким образом, чтобы она удаляла все данные клиента из связанных записей и/или связи с ними из записи контакта. Подробные сведения см. в статье [Руководство разработчика (маркетинг)](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/marketing-developer-guide).

***Dynamics 365 Customer Service Insights*** также предоставляет организациям возможности [удаления данных клиента](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-delete).

Кроме того, в ***Dynamics 365 for Finance and Operations*** для удаления или изменения данных клиента можно использовать [*средства настройки*](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/dev-tools/developer-home-page).

Когда субъект данных просит удалить свои персональные данные, которые оказались включены в ваши данные клиента в ***Dynamics 365 Business Central***, отреагировать на этот запрос можно несколькими способами:

- To quickly bulk-edit multiple Business Central records, you can export data to Excel using the [Business Central Excel Add-in](https://docs.microsoft.com/dynamics365/business-central/finance-analyze-excel#the--excel-add-in) to delete multiple records, and then publish these changes from Excel back in Business Central. For details, see [Exporting your Business Data to Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).
- Вы можете удалить данные клиента, хранящиеся в каком-либо поле, вручную удалив элемент данных, содержащий целевые данные клиента. Подробные сведения см. в статье [Ввод данных](https://docs.microsoft.com/dynamics365/business-central/ui-enter-data).
- Вы можете напрямую удалить данные клиента, например, удалив контакт, а затем запустив пакетное задание "Удалить отмененные записи журнала взаимодействия", чтобы удалить взаимодействия для этого контакта.
- Вы можете [удалить документы](https://docs.microsoft.com/dynamics365/business-central/admin-manage-documents), содержащие данные клиента, например напоминания и опубликованные продажи, а также счета покупок.

Besides bulk or individual deletion of discrete records, please note that only terminated workers can be fully deleted from ***Dynamics 365 for Talent***. [Follow these steps to delete terminated workers](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/gdpr/respond-dsr-request-talent#additional-notes-that-apply-to-requests-for-personal-data).

### <a name="exporting-customer-data"></a>Экспорт данных клиентов

Чтобы ответить на запрос переноса данных, данные клиента в ***Dynamics 365 for Customer Engagement*** можно экспортировать, используя широкие возможности экспорта объектов. Данные клиента можно экспортировать в статический файл Excel для облегчения запроса на перенос данных. Затем в Excel вы можете изменить персональные данные, чтобы включить их в запрос на перенос, и сохранить в распространенном машиночитаемом формате типа CSV или XML.

Additionally, for Dynamics 365 for Marketing a [dedicated API](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/developer/retrieve-interactions-contact) is provided that allows customer to build extensions that retrieve additional records of captured customer interactions that may contain personal data. The API loads all the relevant information from the back-end system and assembles it into a single, portable document.

Для ***Dynamics 365 Customer Service Insights*** вы [экспортируете данные клиента](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/gdpr-export) с помощью портала управления Azure.

***Dynamics 365 for Finance and Operations*** позволяет использовать [объекты для управления данными и интеграции](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-management-integration-data-entity), создавать новые или расширять существующие для экспорта персональных данных в Excel или другие распространенные форматы с помощью [заданий импорта и экспорта данных](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/data-entities/data-import-export-job).  Кроме того, для упрощения запроса на перенос данных многие списки можно экспортировать в статический файл Excel. Экспортированные в Excel таким образом данные клиента можно изменить, чтобы включить персональные данные в запрос на перенос, а затем сохранить файл в распространенном машиночитаемом формате типа CSV или XML.

Dynamics 365 for Finance and Operations и ***Dynamics 365 for Talent*** предлагают отчет о результатах поиска человека, чтобы предоставить субъекту данных те данные, которые вы классифицировали как персональные. 

***Dynamics 365 Business Central*** предлагает следующие возможности:

- Вы можете экспортировать данные клиента в файл Excel, затем отредактировать их в Excel, чтобы включить их в запрос на перенос, и сохранить файл в распространенном машиночитаемом формате типа CSV или XML. Подробные сведения см. в статье [Экспорт бизнес-данных в Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).
- Вы можете экспортировать данные клиента в файл Excel, затем отредактировать их в Excel, чтобы включить их в запрос на перенос, и сохранить файл в распространенном машиночитаемом формате типа CSV или XML. Подробные сведения см. в статье [Экспорт бизнес-данных в Excel](https://docs.microsoft.com/dynamics365/business-central/about-export-data).


## <a name="part-2-responding-to-dsrs-for-system-generated-logs"></a>Часть 2. Реагирование на запросы субъектов данных в части журналов, созданных системой

Microsoft also provides you with the ability to access, export, and delete system-generated logs that may be deemed personal under the GDPR's broad definition of "personal data." Examples of system-generated logs that may be deemed personal under GDPR include:

- Данные об использовании продуктов и служб, например журналы о действиях пользователей
- Данные запросов и поисковых запросов пользователей
- Данные, созданные продуктами и службами на основе сведений о работе системы и взаимодействии с пользователями и другими системами

Note that the ability to restrict or rectify data in system-generated logs is not supported. Data in system-generated logs constitutes factual actions conducted within the Microsoft cloud and diagnostic data, and modifications to such data would compromise the historical record of actions and increase fraud and security risks.

### <a name="accessing-and-exporting-system-generated-logs"></a>Получение доступа к журналам, создаваемым системой, и их экспорт

Admins can access system-generated logs associated with a particular user's use of Dynamics 365 services and applications. To access and export system-generated logs:

1. Перейдите на портал [Microsoft Service Trust Portal](https://servicetrust.microsoft.com/) и войдите в систему, используя учетные данные глобального администратора Dynamics 365.
2. В раскрывающемся списке **Конфиденциальность** в верхней части страницы щелкните **Запрос субъекта данных**.
3. На странице **Запрос субъекта данных**, в разделе **Системные журналы**, щелкните **Экспорт журнала данных**.
    > [!NOTE]
    > The **Data Log Export** is displayed. Note that a list of export data requests submitted by your organization is displayed.
4. Чтобы создать запрос для пользователя, щелкните **Создать запрос на экспорт данных**.

After you create a new request, it will be listed on the **Data Log Export** page where you can track its status. After a request is complete, you can click a link to access the system-generated logs, which will be exported to your organization's Azure storage location within 30 days of creating the request. The data will be saved in common, machine-readable file formats such as JSON or XML. If you don't have an Azure account and Azure storage location, you'll need to create an Azure account and/or Azure storage location for your organization so that the Data Log Export tool can export the system-generated logs.

Azure поддерживает их, позволяя вашей организации экспортировать данные в основном формате JSON в указанный вами контейнер службы хранилища Azure. См. раздел ["Хранилище BLOB-объектов" статьи "Общие сведения о службе хранилища Microsoft Azure"](https://docs.microsoft.com/azure/storage/common/storage-introduction#blob-storage). Полученные данные не будут включать данные, которые могут поставить под угрозу безопасность и стабильность службы.

> [!IMPORTANT]
> Чтобы экспортировать данные пользователя из клиента, необходимо быть администратором этого клиента.

В таблице ниже приведены сведение о доступе к системным журналам и их экспорте.

| | |
|:----|:---|
| | |
|**Сколько времени нужно средству экспорта журнала данных для выполнения запроса?**| This can depend on several factors. In most cases it should complete in one or two days, but it can take up to 30 days. |
|**Какой формат имеют выходные данные?**| Выходные данные — структурированные машиночитаемые файлы в формате XML, CSV или JSON. |
|**Какие данные возвращает средство экспорта журнала данных?**| Средство экспорта журналов данных возвращает системные журналы, хранящиеся в службах Майкрософт. Экспортируемые данные извлекаются из различных служб Майкрософт, включая Office 365, Azure и Dynamics. |
|***Кто имеет доступ к средству экспорта журнала данных для отправки запросов на доступ к системным журналам?**| Глобальные администраторы Dynamics 365 получат доступ к служебной программе GDPR Log Manager. |
|**Каков порядок возвращения данных пользователю?**| Данные экспортируются в место хранения вашей организации в Azure. Администраторы организации определяют порядок отображения или возврата данных пользователям. |
|**Как выглядят данные в системных журналах?**| Пример записи из системного журнала в формате JSON: <br><br> "DateTime": "2017-04-28T12:09:29-07:00", <br> "AppName": "SharePoint", <br> "Action": "OpenFile", <br> "IP": "154.192.13.131", <br> "DevicePlatform": "Windows 1.0.1607" |

### <a name="deleting-system-generated-logs"></a>Удаление системных журналов

Чтобы удалить сгенерированные системой журналы, полученные с помощью запроса на доступ, необходимо удалить пользователя из службы и окончательно удалить его учетную запись Azure Active Directory. Инструкции по окончательному удалению пользователя приведены в разделе [Шаг 5: Удалить](gdpr-dsr-azure.md#step-5-delete) в теме Запросы субъектов данных Azure. Важно отметить, что окончательное удаление учетной записи пользователя необратимо после его инициирования. При окончательном удалении учетной записи пользователя данные пользователя удаляются из системных журналов (кроме данных, которые могут скомпрометировать безопасность или надежность службы) почти для всех служб Dynamics 365 в течение 30 дней.

## <a name="learn-more"></a>Подробнее

- [Центр управления безопасностью (Майкрософт)](https://www.microsoft.com/trust-center/privacy/gdpr-overview)
