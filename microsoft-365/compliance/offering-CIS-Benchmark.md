---
title: Контрольные показатели Center for Internet Security (CIS)
description: Center for Internet Security (CIS) опубликовал ряд контрольных показателей для продуктов и служб Майкрософт.
keywords: Microsoft 365, соответствие требованиям, предложения
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 8e147e26072609a43d962b1d9fc7e71925510da4
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064698"
---
# <a name="center-for-internet-security-cis-benchmarks"></a>Контрольные показатели Center for Internet Security (CIS)

## <a name="about-cis-benchmarks"></a>О контрольных показателях CIS

[Center for Internet Security](https://www.cisecurity.org/) представляет собой некоммерческую организацию, чья миссия заключается в том, чтобы "выявлять, разрабатывать, утверждать, продвигать и поддерживать лучшие практические решения для киберзащиты". Он опирается на знания и опыт экспертов в области кибербезопасности и ИТ-специалистов из государственных организаций, деловых и научных кругов со всего мира. Для разработки стандартов и передовых методов, в том числе контрольных показателей CIS, средств управления и защищенных образов, они следуют консенсусной модели принятия решений.  
  
[Контрольные показатели CIS](https://www.cisecurity.org/cis-benchmarks/) представляют собой базовые показатели конфигурации и рекомендации для безопасной настройки системы. В каждой из рекомендаций содержатся ссылки на одну или несколько [точек управления CIS](https://www.cisecurity.org/controls/), которые были разработаны, чтобы помочь организациям улучшить свои возможности киберзащиты. Контрольные точки CIS соответствуют многим установленным стандартам и нормативным положениям, включая NIST Cybersecurity Framework (CSF) и NIST SP 800-53, серию стандартов ISO 27000, PCI DSS, HIPAA и другие.  
  
Каждый контрольный показатель проходит два этапа консенсусного анализа. Первый имеет место во время первоначальной разработки, когда эксперты собираются для обсуждения, создания и тестирования рабочих проектов, и продолжается до тех пор, пока они не достигнут консенсуса по контрольному показателю. На втором этапе, после публикации контрольного показателя, консенсусная группа рассматривает отзывы интернет-сообщества для включения в контрольную точку.  
  
В контрольных показателях CIS предусмотрены два уровня настроек безопасности:

- **Уровень 1** рекомендует основные базовые требования безопасности, которые могут быть настроены в любой системе и должны вызывать незначительное или нулевое прерывание обслуживания либо снижение функциональности.
- **Уровень 2** рекомендует параметры безопасности для сред, требующих повышенной безопасности, что может привести к некоторому снижению функциональности.

[CIS Hardened Images](https://www.cisecurity.org/blog/cis-hardened-images-now-in-microsoft-azure-marketplace/) представляют собой надежно настроенные образы виртуальных машин на основе контрольных показателей CIS, защищенных до профиля контрольных точек CIS уровня 1 или уровня 2. Усиление защиты – это процесс, который помогает обеспечить защиту от несанкционированного доступа, отказа в обслуживании и других киберугроз путем ограничения потенциальных слабых мест, вследствие которых системы становятся уязвимыми для кибератак.

## <a name="microsoft-and-the-cis-benchmarks"></a>Майкрософт и контрольные показатели CIS

Center for Internet Security (CIS) опубликовал контрольные точки производительности продуктов и служб Майкрософт, в том числе контрольные показатели для Microsoft Azure и ключевых компонентов Microsoft 365, контрольный показатель для Windows 10 и контрольный показатель для Windows Server 2016.  
  
Контрольные показатели CIS признаны во всем мире как стандарты безопасности для защиты ИТ-систем и данных от кибератак. Используемые тысячами предприятий, они предлагают конкретные рекомендации по созданию безопасной базовой конфигурации. Администраторы систем и приложений, специалисты по безопасности и другие специалисты, разрабатывающие решения с использованием продуктов и служб Майкрософт, могут использовать эти передовые методы для оценки и повышения безопасности своих приложений.  
  
Как и все контрольные показатели CIS, контрольные показатели для Майкрософт были созданы с использованием процесса консенсусного анализа, основанного на мнениях экспертов в данной области, имеющих разносторонний опыт в области разработки программного обеспечения, аудита и соответствия требованиям, исследований в области безопасности, операций, взаимодействия с государственными организациями и законодательства. Корпорация Майкрософт стала полноправным партнером в рамках таких усилий CIS. В частности, Office 365 был протестирован на соответствие перечисленным службам, и полученный в результате контрольный показатель для ключевых компонентов Microsoft 365 охватывает широкий спектр рекомендаций по настройке соответствующих политик безопасности в отношении учетных записей и проверки подлинности, управления данными, разрешений приложений, хранения и других областей политики безопасности.  
  
В дополнение к контрольным показателям для продуктов и служб Майкрософт, CIS также опубликовал [CIS Hardened Images, предназначенные для использования на виртуальных машинах Azure](https://www.cisecurity.org/blog/cis-hardened-images-now-in-microsoft-azure-marketplace/), настроенных для соответствия контрольным показателям CIS. В их число входят CIS Hardened Image для Microsoft Windows Server 2016, сертифицированный для запуска на Azure. Согласно информации CIS, "все защищенные образы CIS, доступные на [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/apps?search=center%20for%20internet%20security), сертифицированы для запуска на Azure. Они были предварительно протестированы на готовность и совместимость с общедоступным облаком Azure, облачной платформой Microsoft, размещенной поставщиками услуг через сеть Cloud OS Network, и развертываниями в локальном частном облаке Windows Server Hyper-V, управляемыми клиентами".

## <a name="microsoft-in-scope-cloud-services"></a>Облачные службы Майкрософт, к которым применима оценка

- [Azure и Azure для государственных организаций](https://aka.ms/AzureCompliance)
- [Office и Microsoft 365](https://aka.ms/o365-compliance-framework)
- SQL Server
- Windows 10
- Windows Server 2016

## <a name="audits-reports-and-certificates"></a>Аудит, отчеты и сертификаты

Получить [полный список контрольных показателей CIS](https://www.cisecurity.org/cis-benchmarks/) для продуктов и служб Майкрософт.

- [Контрольные показатели CIS для ключевых компонентов Azure](https://www.cisecurity.org/benchmark/azure/)
- [Контрольные показатели CIS для Microsoft 365](https://www.cisecurity.org/benchmark/microsoft_office/)
- [Контрольный показатель для Windows 10](https://www.cisecurity.org/benchmark/microsoft_windows_desktop/)
- [Контрольный показатель для Windows Server 2016](https://www.cisecurity.org/benchmark/microsoft_windows_server/)

## <a name="how-to-implement"></a>Методика реализации

- [Контрольный показатель CIS для Azure](https://azure.microsoft.com/mediahandler/files/resourcefiles/cis-microsoft-azure-foundations-security-benchmark/CIS_Microsoft_Azure_Foundations_Benchmark_v1.0.0.pdf): получите конкретные рекомендации по созданию безопасной базовой конфигурации для Azure.  
- [Схема обеспечения безопасности Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap): сведите к минимуму риск утечки данных или компрометации учетных записей, соблюдая эту схему.
- [Базовые показатели безопасности Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines): следуйте этим рекомендациям, чтобы эффективно использовать базовые показатели безопасности в вашей организации.
- [Сопроводительное руководство по контрольным точкам CIS Controls для облака](https://www.cisecurity.org/white-papers/cis-controls-cloud-companion-guide/): получите рекомендации по применению передовых методов безопасности в CIS Controls, версия 7 для облачных сред.

## <a name="frequently-asked-questions"></a>Вопросы и ответы

**Будут ли параметры контрольных показателей CIS обеспечивать безопасность моих приложений?**

Контрольные показатели CIS определяют базовый уровень безопасности для всех пользователей, в сферу охвата которых входят продукты и службы Майкрософт. Тем не менее, они должны рассматриваться не в качестве исчерпывающего списка всех возможных конфигураций и архитектур безопасности, а в качестве отправной точки. Каждая организация должна при этом оценивать свою конкретную ситуацию, рабочие нагрузки и соответствие требованиям и адаптировать свою среду соответствующим образом.

**Как часто обновляются контрольные показатели CIS?**

Выпуск пересмотренных контрольных показателей CIS изменяется в зависимости от разработавшего их сообщества ИТ-специалистов, а также от графика выпуска технологии, поддерживаемой контрольными точками. CIS распространяет ежемесячные отчеты, в которых объявляется о новых контрольных показателях и обновлениях для существующих контрольных показателей. Для их получения зарегистрируйтесь в [CIS Workbench](https://workbench.cisecurity.org/) (это бесплатно) и поставьте флажок в поле Receive newsletter (Получать бюллетень) в своем профиле.

**Кто внес вклад в разработку контрольных показателей CIS для Майкрософт?**

В CIS отмечает, что "контрольные показатели разрабатываются благодаря бескорыстным усилиям волонтеров-экспертов в данной области, поставщиков технологий, членов сообщества CIS Benchmark из государственных и частных организаций, а также команды разработчиков CIS Benchmark". В частности, вы найдете список участников Azure в разделе [Доступен контрольный показатель CIS для ключевых компонентов Microsoft Azure v1.0.0](https://www.cisecurity.org/blog/cis-microsoft-azure-foundations-benchmark-v1-0-0-now-available/).

## <a name="resources"></a>Ресурсы

- [Передовые методы CIS по безопасному использованию Microsoft 365](https://www.microsoft.com/security/blog/2019/01/10/best-practices-for-securely-using-microsoft-365-the-cis-microsoft-365-foundations-benchmark-now-available/)
- [Параметры политики безопасности Windows 10](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/security-policy-settings)
- [Безопасность Windows 10 Корпоративная](https://docs.microsoft.com/windows/security/index)
- [Соответствие требованиям в центре управления безопасностью Майкрософт](https://www.microsoft.com/trust-center/compliance/compliance-overview)
