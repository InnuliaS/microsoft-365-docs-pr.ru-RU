---
title: Требования к экспорту в США (год)
description: Облачные службы Майкрософт помогают клиентам подчиняться требованиям по экспорту в США (с учетом нормативов), которые соответствуют требованиям к их соответствию и контролируют риск экспорта.
keywords: Microsoft 365, соответствие требованиям, предложения
localization_priority: None
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
ms.openlocfilehash: 1adf0bab35c921dd416028747b0309e5ad5f3055
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601966"
---
# <a name="us-export-administration-regulations-ear"></a>Требования к экспорту в США (год)

## <a name="about-the-ear"></a>О.

Отдел США включает административные нормативные правила (год), используя [бюро отрасли и безопасности (BIS)](https://www.bis.doc.gov/). Самое большое — управление элементами управления при экспорте и повторной экспорте большинства коммерческих товаров, программного обеспечения и технологий, в том числе «двойных» элементов, которые можно использовать как для коммерческой, так и для воинского использования, а также для определенных элементов защиты.

Рекомендации BIS содержат сведения о том, что когда данные или программное обеспечение передаются в облако или передаются между узлами пользователей, клиент, не являющийся облачным поставщиком, является "экспортом", который несет ответственность за передачу, хранение и доступ к данным или программному обеспечению. соответствует год.

В [соответствии с параметрами BIS](https://www.bis.doc.gov/index.php/documents/regulation-docs/412-part-734-scope-of-the-export-administration-regulations/file) *Экспорт* относится к переносу защищенной технологии или технических данных во внешнее место или на его выпуск для внешнего лица в США (которое также называется *признанным экспортом*). Самое большое — управлять:

- Экспорт из США.
- Повторно экспортирует или переносит элементы источника US и определенные внешние элементы с более чем уменьшенной *частью контента* US.
- Передает или раскрытие информации для людей из других стран.

Элементы, к которым относится год, можно найти в списке управления Commerce (ККЛ), где каждому элементу назначен уникальный [номер классификации контроля экспорта (еккн)](https://www.bis.doc.gov/index.php/licensing/commerce-control-list-classification/export-control-classification-number-eccn). Элементы, не перечисленные в ККЛ, обозначены как EAR99, а большинство коммерческих продуктов EAR99 не требуют экспорта лицензии. Однако в зависимости от назначения, конечного пользователя или конечного использования элемента даже для элемента EAR99 может потребоваться лицензия на экспорт BIS.

[Последнее правило](https://www.federalregister.gov/documents/2016/06/03/2016-12734/revisions-to-definitions-in-the-export-administration-regulations), опубликованное в июне 2016, разъяснено, что правила лицензирования не будут применяться к передаче и хранению неклассифицированных технических данных и программного обеспечения, если они были зашифрованы с помощью проверенных криптографических модулей FIPS 140-2 и не были намеренно сохранены в стране или в Российской Федерации.

## <a name="microsoft-and-the-ear"></a>Корпорация Майкрософт и год

Для технологий, продуктов и служб Майкрософт действуют правила экспорта в США (год). Несмотря на то, что нет сертификации на соответствие требованиям для государственных, Microsoft Azure, государственных организаций Microsoft Azure и государственных учреждений Microsoft Office 365 (Гкчигх и DoD), вы можете получить важные функции и средства, которые помогут клиентам подчиняться политике "Управление экспортом". Управление рисками и соответствие требованиям их соответствия требованиям.

Отдел США, который применяет год, затратил положение клиентов, а не облачных поставщиков услуг, таких как Майкрософт, как экспортируемые данные своих собственных клиентов. В то время как большинство данных клиентов не считаются "технологиями" или "техническими данными" для сокращения элементов управления экспортом, облачные службы Microsoft в области структурированы так, чтобы помочь клиентам управлять и значительно снизить потенциальные риски, связанные с контролем экспорта. Как правило, Майкрософт, но не исключительно, рекомендует использовать облачные облачные службы для соответствующих клиентов. С помощью соответствующего планирования клиенты могут использовать следующие средства и собственные внутренние процедуры для обеспечения полной совместимости с элементами управления экспортом в Майкрософт.

- **Элементы управления в расположении данных**. Пользователи имеют возможность видеть, где хранятся данные, и получать доступ к надежным средствам, чтобы ограничить его хранение. Таким образом, они могут гарантировать, что их данные хранятся в США, а также свести к минимуму перенос контролируемых технологий или технических данных за пределами США. Кроме того, данные клиентов не хранятся в несоответствующем расположении, что согласуется с нестандартными запретами на случай, когда данные "преднамеренно сохранены": нет центра обработки данных Azure находится в одной из 25 групп D:5 или Российской Федерации.
- **Сквозное шифрование**. Благодаря преимуществам сквозного безопасного шифрования Harbor (бухты для физических расположений, указанных в этом случае облачные службы Майкрософт обеспечивают функции шифрования, позволяющие защититься от угроз управления экспортом. Кроме того, они предоставляют пользователям [широкий спектр возможностей для шифрования данных](https://aka.ms/Azure-Encryption-Overview) в транзитном месте и в REST, а также возможность выбора между параметрами шифрования.
- **Средства и протоколы для предотвращения несанкционированного экспорта**. Использование шифрования также помогает защититься от потенциально признанного экспортируемого (или повторного экспорта), так как даже если у пользователя, отличного от США, есть доступ к зашифрованным данным, ничего не отображается, если они не могут прочитать или прочитать данные, когда они зашифрованы; Таким образом, отсутствует "выпуск" контролируемых данных.

## <a name="microsoft-in-scope-cloud-services"></a>Облачные службы Майкрософт, к которым применима оценка

- [Azure и Azure для государственных организаций](https://aka.ms/AzureCompliance)
- [Office 365 для государственных учреждений (GCC-High и DoD)](https://aka.ms/Office-365-Export-Controls)
- Intune

## <a name="how-to-implement"></a>Методика реализации

Общие сведения об элементах управления экспортом и рекомендациях для клиентов, оценивающих свои обязательства в год.

- [Azure](https://aka.ms/Azure-Export-Controls)
- [Office 365](https://aka.ms/Office-365-Export-Controls)

## <a name="frequently-asked-questions"></a>Вопросы и ответы

**Что делать, чтобы соответствовать экспортным элементам управления при использовании облачных служб Майкрософт?**

В этом случае, когда данные передаются на облачный сервер, например в облако Майкрософт, клиент, который владеет данными, а не как поставщик облачных служб, считается экспортируемым. По этой причине владелец данных (то есть, клиент Майкрософт) должен тщательно оценить, как их использование в облаке Майкрософт может импликате экспортные элементы управления и определить, могут ли какие-либо данные использовать или хранить эти элементы управления. и если да, то какие элементы управления применяются. Узнайте больше о том, как службы [Azure](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers) и облачные службы [Office 365](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE1s5kI) могут помочь пользователям обеспечить полное соответствие требованиям для экспорта элементов управления Майкрософт.

**Используются технологии Майкрософт, продукты и службы Майкрософт, которые, в своюмся, задействуются на год?**

Большинство технологий, продуктов и служб Майкрософт:

- Не накладываются на год, поэтому они не включены в список управления Commerce и не имеют ЕККН;
- Это EAR99 или 5D992 массовый рынок, пригодных для самостоятельной классификации корпорацией Майкрософт и экспортируемые в неэмбаргоные страны без лицензии, так как не требуется лицензия (НЛР).

С другой стороны, некоторым продуктам Майкрософт был назначен ЕККН, который может не требовать лицензию. Ознакомьтесь с юридическими или юридическими Юрисконсульта, чтобы определить подходящий тип лицензии и соответствующие страны для целей экспорта.

**В чем разница между международным и международным трафиком в нормах подлокотников (ITAR)?**

Основные элементы управления для экспорта в США с большим количеством приложений — это год, который управляется министерством торговли США. Этот год применяется к элементам двойного использования, которые содержат как коммерческие, так и воинские приложения, а также элементы с полностью коммерческими приложениями.

В США также разделяются отдельные и более специализированные нормативные положения управления экспортом, такие как ITAR, которые управляют самыми важными элементами и технологиями. Управление с помощью штата США заключается в том, чтобы управлять экспортом, временным импортом, переэкспортом и передачей множества воинских, оборонных и аналитических элементов (также называемых "оборонными статьями"), в том числе соответствующими техническими данными.

## <a name="resources"></a>Ресурсы

- [Экспорт продуктов Майкрософт: обзор](https://www.microsoft.com/exporting/overview.aspx)
- [Экспорт продуктов Майкрософт: вопросы и ответы](https://www.microsoft.com/exporting/faq.aspx)
- [Экспорт продуктов Майкрософт: Поиск продукта](https://www.microsoft.com/exporting/exporting-information.aspx)
- [Экспорт ограничений на криптографию](https://docs.microsoft.com/windows/uwp/security/export-restrictions-on-cryptography)
- [Microsoft и FIPS 140-2](offering-fips-140-2.md)
- [Microsoft и ITAR](offering-itar.md)
- [Соответствие требованиям в центре управления безопасностью Майкрософт](https://www.microsoft.com/trust-center/compliance/compliance-overview)
