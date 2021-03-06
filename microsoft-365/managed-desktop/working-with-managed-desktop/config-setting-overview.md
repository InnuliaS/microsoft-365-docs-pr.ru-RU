---
title: Настраиваемые параметры для настольных компьютеров, управляемых Майкрософт
description: Сведения о настраиваемых параметрах с помощью управляемого рабочего стола Майкрософт
keywords: Настольные компьютеры, управляемые корпорацией Майкрософт, Microsoft 365, служба, документация, параметры, настраиваемые параметры
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: d8ebe4519d169db5500c55a3337836ca2d0986c0
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390726"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>Настраиваемые параметры — Рабочий стол, управляемый корпорацией Майкрософт

Настольные компьютеры, управляемые корпорацией Майкрософт, развертывают параметры и политики, применяемые ко всем устройствам, управляемым настольным компьютером Майкрософт. Дополнительные сведения см. [](../service-description/device-policies.md)

Настраиваемые параметры на рабочем столе, управляемом Майкрософт, позволяют ИТ-администраторам настраивать и развертывать параметры, которые уникальны в соответствии с потребностями Организации и бизнеса. Эти параметры задаются в дополнение к параметрам конфигурации устройств и политикам, управляемым настольным компьютером, управляемым Майкрософт.  

Настраиваемые изменения параметров вносятся в облако и применяются к управляемым устройствам, управляемым Майкрософт, в определенных группах развертывания. Этот процесс аналогичен тому, как управляемый Рабочий стол управляет изменениями параметров конфигуруатион и политик, определенных и управляемых службой. С помощью того же процесса, который использует Microsoft Managed Desktop для развертывания изменений, вы продолжаете перемещать организацию вперед, используя современные методики управления ИТ.

## <a name="when-to-use-configurable-settings"></a>Когда следует использовать настраиваемые параметры?

Для использования настраиваемых параметров необходимо несколько раз. 

**Процесс** входящей миграции — для настольных компьютеров, управляемых Майкрософт, рекомендуется настраивать настраиваемые параметры при подключении к службам настольных компьютеров Майкрософт или при подключении большого числа устройств (20 или более). Настройка категорий настраивается на портале администрирования настольных компьютеров Майкрософт. После включения и получения доступа к порталу администрирования можно выбрать категории, которые необходимо настроить для Организации, внести изменения, поэтапно развернуть и развернуть изменения.

**Ведение параметров** — регулярно проверяйте параметры и внесите необходимые изменения. Для поддержки изменений в вашей организации может потребоваться внести изменения.   

## <a name="setting-categories"></a>Настройка категорий

Настраиваемые категории параметров, которые можно настраивать:
- [Фоновый рисунок рабочего стола](config-setting-ref.md#desktop-background-picture) — Настройка фонового рисунка рабочего стола для устройств, управляемых Майкрософт. 
- [Начальная страница браузера](config-setting-ref.md#browser-start-pages) — Добавление начальных страниц для использования с Microsoft Edge. Просмотр начальной страницы браузера
- [Список сайтов в режиме предприятия](config-setting-ref.md#enterprise-mode-site-list-location) — Добавление сайтов и режим совместимости. Сайты в списке будут запущены в Internet Explorer. 
- [Надежные сайты](config-setting-ref.md#trusted-sites) — Добавление доверенных сайтов и настройка зон безопасности для каждого сайта. 
- [Исключения прокси-сайта](config-setting-ref.md#proxy) — Настройка номера и номера порта прокси-сервера, а затем Добавление исключений прокси-сайтов.

Каждая категория параметров может настраиваться и развертываться самостоятельно. Вы можете одновременно развертывать изменения нескольких категорий параметров, но в категорию параметров можно развертывать только одно изменение.

Пример:
- Вы можете развернуть изменения фонового рисунка рабочего стола и доверенных сайтов, каждый из которых будет развернут в любое время. 
- Вы не можете развертывать два развертывания одновременно для начальных страниц браузера. При последнем развертывании будут остановлены все еще не выполняемые развертывания.

## <a name="configurable-setting-process"></a>Настраиваемый процесс настройки

При использовании настраиваемых параметров в Организации с помощью управляемых рабочих столов Майкрософт рекомендуется выполнить следующие действия:

**Шаг 1 — Планирование** — сведения о настраиваемых параметрах и выборе категорий, которые необходимо настроить для Организации. Создайте временную шкалу для предполагаемого развертывания изменений каждой группы. Планируйте обмен данными с пользователями, которые соответствуют внутренним процессам управления изменениями. Например, если вы добавляете начальную страницу браузера, сообщите пользователям о том, что после развертывания будет создан новый набор начальных страниц в браузере.  

**Шаг 2 — Настройка и развертывание Stage** — внесение изменений в настраиваемые параметры на портале администрирования настольных компьютеров Майкрософт. Разместите изменения, чтобы они были готовы к развертыванию. Не забудьте сообщить пользователям об изменениях и изменить их взаимодействие с устройствами.   

Изменения настраиваются и изменяются на портале администрирования рабочих столов, управляемом Майкрософт. Дополнительную информацию можно узнать в статье [Настройка настраиваемых параметров](config-setting-ref.md). 

**Шаг 3: уведомление об изменениях** Сообщите сведения о предстоящих изменениях для пользователей. Для каждого развертывания выполните обмен данными, который является частью процессов управления изменениями. Необходимо четко сообщать любые изменения, которые влияют на то, как работает пользователь, или о том, как они будут отображаться на своих устройствах.

**Шаг 4: развертывание изменений** — развертывание изменений, начиная с тестовой группы. Тестовая группа позволяет проверять и устранять любые проблемы в группе с меньшим количеством устройств, прежде чем развертывать изменения в крупных группах устройств. При возникновении проблем вы можете отменить изменения, изменить параметр и поэтапно создать новое развертывание. Для настольных компьютеров, управляемых Майкрософт, рекомендуется следовать структурированному подходу и развертывать в группах в следующем порядке: Test, First, Fast, а затем широком.   

Все настраиваемые параметры управляются с помощью портала администрирования рабочих столов, управляемого Майкрософт. Более подробную информацию можно найти в разделе [deploy Changes](config-setting-deploy.md). 

**Шаг 5-отслеживание изменений** — отслеживание изменений состояния развертывания. Для каждого параметра можно выполнить следующие действия:
- **Отслеживание хода выполнения** — отслеживание состояния после развертывания изменения. Состояние изменится на " **выполняется**", а затем " **завершено**" или " **сбой**". Если при развертывании произойдет сбой, запрос в службу поддержки автоматически откроется для управляемых операций на рабочем столе Майкрософт для изучения этой проблемы.  
- **Развернутая версия** — каждое развернутое изменение имеет номер версии.
- **Вернуть изменения** — отмена отмены изменений приводит к прекращению текущего развертывания и возврат всех групп к последним изменениям, которые были развернуты для всех групп. Выполняется откат к последнему значению параметра "последнее удачное".
- **Проверка изменений** — после завершения развертывания убедитесь, что изменения применены должным образом.  

Если при развертывании возникла ошибка, или вы не можете отменить изменения, [откройте запрос в службу поддержки](admin-support.md) с управляемыми рабочими операциями, управляемыми корпорацией Майкрософт. 

Дополнительные сведения см в разделе [deploy and Track Settings Settings](config-setting-deploy.md).

## <a name="additional-resources"></a>Дополнительные ресурсы
- [Справочные сведения о настраиваемых параметрах](config-setting-ref.md) 
- [Развертывание настраиваемых параметров](config-setting-deploy.md) 
