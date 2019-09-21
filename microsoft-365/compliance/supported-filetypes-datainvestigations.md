---
title: Поддерживаемые типы файлов при расследовании данных (Предварительная версия)
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
ms.openlocfilehash: 60e4baf2df94793b532fb4035a34ca3c7a5cd332
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/20/2019
ms.locfileid: "37090705"
---
# <a name="supported-file-types-in-data-investigations-preview"></a><span data-ttu-id="f11ce-102">Поддерживаемые типы файлов при расследовании данных (Предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="f11ce-102">Supported file types in Data Investigations (Preview)</span></span>

<span data-ttu-id="f11ce-103">Расследования данных (Предварительная версия) поддерживает многие типы файлов несколькими различными способами, которые описаны в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f11ce-103">Data Investigations (Preview) supports many file types in several different ways, which are described in the following table.</span></span> <span data-ttu-id="f11ce-104">Этот список не завершен, и мы добавим новые типы файлов, когда мы продолжим проверочное тестирование.</span><span class="sxs-lookup"><span data-stu-id="f11ce-104">This list isn't finalized, and we'll add new file types as we continue our validation testing.</span></span> <span data-ttu-id="f11ce-105">В таблице также указано, можно ли просматривать типы файлов в доступных средствах просмотра, когда вы просматриваете доказательства.</span><span class="sxs-lookup"><span data-stu-id="f11ce-105">The table also indicates if a file type can be viewed in the available viewers when you're reviewing evidence.</span></span>

| <span data-ttu-id="f11ce-106">Тип MIME</span><span class="sxs-lookup"><span data-stu-id="f11ce-106">Mime type</span></span> | <span data-ttu-id="f11ce-107">Класс File</span><span class="sxs-lookup"><span data-stu-id="f11ce-107">File class</span></span> | <span data-ttu-id="f11ce-108">Встроенное средство просмотра</span><span class="sxs-lookup"><span data-stu-id="f11ce-108">Native viewer</span></span> | <span data-ttu-id="f11ce-109">Средство просмотра текста</span><span class="sxs-lookup"><span data-stu-id="f11ce-109">Text viewer</span></span> | <span data-ttu-id="f11ce-110">Средство просмотра примечаний</span><span class="sxs-lookup"><span data-stu-id="f11ce-110">Annotate viewer</span></span> | <span data-ttu-id="f11ce-111">Извлечение контейнера</span><span class="sxs-lookup"><span data-stu-id="f11ce-111">Container extraction</span></span> | <span data-ttu-id="f11ce-112">Расширения</span><span class="sxs-lookup"><span data-stu-id="f11ce-112">Extensions</span></span> |
| :- | :- | :- | :- | :- | :- | :- |
| <span data-ttu-id="f11ce-113">application/msword</span><span class="sxs-lookup"><span data-stu-id="f11ce-113">application/msword</span></span> | <span data-ttu-id="f11ce-114">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-114">Document</span></span> | <span data-ttu-id="f11ce-115">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-115">Yes</span></span> | <span data-ttu-id="f11ce-116">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-116">Yes</span></span> | <span data-ttu-id="f11ce-117">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-117">Yes</span></span> | <span data-ttu-id="f11ce-118">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-118">No</span></span> | <span data-ttu-id="f11ce-119">. doc;. dat</span><span class="sxs-lookup"><span data-stu-id="f11ce-119">.doc; .dat</span></span> |
| <span data-ttu-id="f11ce-120">application/pdf</span><span class="sxs-lookup"><span data-stu-id="f11ce-120">application/pdf</span></span> | <span data-ttu-id="f11ce-121">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-121">Document</span></span> | <span data-ttu-id="f11ce-122">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-122">Yes</span></span> | <span data-ttu-id="f11ce-123">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-123">Yes</span></span> | <span data-ttu-id="f11ce-124">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-124">Yes</span></span> | <span data-ttu-id="f11ce-125">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-125">No</span></span> | <span data-ttu-id="f11ce-126">PDF</span><span class="sxs-lookup"><span data-stu-id="f11ce-126">.pdf</span></span> |
| <span data-ttu-id="f11ce-127">приложение/RTF</span><span class="sxs-lookup"><span data-stu-id="f11ce-127">application/rtf</span></span> | <span data-ttu-id="f11ce-128">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-128">Document</span></span> | <span data-ttu-id="f11ce-129">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-129">Yes</span></span> | <span data-ttu-id="f11ce-130">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-130">Yes</span></span> | <span data-ttu-id="f11ce-131">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-131">Yes</span></span> | <span data-ttu-id="f11ce-132">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-132">No</span></span> | <span data-ttu-id="f11ce-133">RTF;. гостей</span><span class="sxs-lookup"><span data-stu-id="f11ce-133">.rtf;.doc</span></span> |
| <span data-ttu-id="f11ce-134">Application/ВНД. МС-ексцел</span><span class="sxs-lookup"><span data-stu-id="f11ce-134">application/vnd.ms-excel</span></span> | <span data-ttu-id="f11ce-135">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-135">Document</span></span> | <span data-ttu-id="f11ce-136">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-136">Yes</span></span> | <span data-ttu-id="f11ce-137">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-137">Yes</span></span> | <span data-ttu-id="f11ce-138">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-138">Yes</span></span> | <span data-ttu-id="f11ce-139">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-139">No</span></span> | <span data-ttu-id="f11ce-140">XLS; dat</span><span class="sxs-lookup"><span data-stu-id="f11ce-140">.xls; .dat</span></span> |
| <span data-ttu-id="f11ce-141">Application/ВНД. МС-ексцел. sheet. binary. макроенаблед. 12</span><span class="sxs-lookup"><span data-stu-id="f11ce-141">application/vnd.ms-excel.sheet.binary.macroenabled.12</span></span> | <span data-ttu-id="f11ce-142">Производительность и формат открытого документа</span><span class="sxs-lookup"><span data-stu-id="f11ce-142">Productivity / Open Document Format</span></span> | <span data-ttu-id="f11ce-143">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-143">Yes</span></span> | <span data-ttu-id="f11ce-144">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-144">Yes</span></span> | <span data-ttu-id="f11ce-145">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-145">No</span></span> | <span data-ttu-id="f11ce-146">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-146">No</span></span> | <span data-ttu-id="f11ce-147">. xlsb</span><span class="sxs-lookup"><span data-stu-id="f11ce-147">.xlsb</span></span> |
| <span data-ttu-id="f11ce-148">Application/ВНД. МС-ексцел. sheet. макроенаблед. 12</span><span class="sxs-lookup"><span data-stu-id="f11ce-148">application/vnd.ms-excel.sheet.macroenabled.12</span></span> | <span data-ttu-id="f11ce-149">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-149">Document</span></span> | <span data-ttu-id="f11ce-150">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-150">Yes</span></span> | <span data-ttu-id="f11ce-151">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-151">Yes</span></span> | <span data-ttu-id="f11ce-152">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-152">Yes</span></span> | <span data-ttu-id="f11ce-153">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-153">No</span></span> | <span data-ttu-id="f11ce-154">. xlsm</span><span class="sxs-lookup"><span data-stu-id="f11ce-154">.xlsm</span></span> |
| <span data-ttu-id="f11ce-155">Application/ВНД. МС-ексцел. Template. макроенаблед. 12</span><span class="sxs-lookup"><span data-stu-id="f11ce-155">application/vnd.ms-excel.template.macroenabled.12</span></span> | <span data-ttu-id="f11ce-156">Производительность и формат открытого документа</span><span class="sxs-lookup"><span data-stu-id="f11ce-156">Productivity / Open Document Format</span></span> | <span data-ttu-id="f11ce-157">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-157">No</span></span> | <span data-ttu-id="f11ce-158">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-158">Yes</span></span> | <span data-ttu-id="f11ce-159">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-159">No</span></span> | <span data-ttu-id="f11ce-160">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-160">No</span></span> | <span data-ttu-id="f11ce-161">. xltm</span><span class="sxs-lookup"><span data-stu-id="f11ce-161">.xltm</span></span> |
| <span data-ttu-id="f11ce-162">Application/ВНД. МС-Аутлук</span><span class="sxs-lookup"><span data-stu-id="f11ce-162">application/vnd.ms-outlook</span></span> | <span data-ttu-id="f11ce-163">Производительность труда</span><span class="sxs-lookup"><span data-stu-id="f11ce-163">Productivity</span></span> | <span data-ttu-id="f11ce-164">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-164">No</span></span> | <span data-ttu-id="f11ce-165">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-165">No</span></span> | <span data-ttu-id="f11ce-166">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-166">No</span></span> | <span data-ttu-id="f11ce-167">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-167">No</span></span> | <span data-ttu-id="f11ce-168">. MSG</span><span class="sxs-lookup"><span data-stu-id="f11ce-168">.msg</span></span> |
| <span data-ttu-id="f11ce-169">Application/ВНД. МС-Аутлук-ПСТ</span><span class="sxs-lookup"><span data-stu-id="f11ce-169">application/vnd.ms-outlook-pst</span></span> | <span data-ttu-id="f11ce-170">Производительность и совместная работа</span><span class="sxs-lookup"><span data-stu-id="f11ce-170">Productivity / Collaboration</span></span> | <span data-ttu-id="f11ce-171">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-171">No</span></span> | <span data-ttu-id="f11ce-172">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-172">No</span></span> | <span data-ttu-id="f11ce-173">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-173">No</span></span> | <span data-ttu-id="f11ce-174">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-174">Yes</span></span> | <span data-ttu-id="f11ce-175">PST-файл</span><span class="sxs-lookup"><span data-stu-id="f11ce-175">.pst</span></span> |
| <span data-ttu-id="f11ce-176">Application/ВНД. МС-поверпоинт</span><span class="sxs-lookup"><span data-stu-id="f11ce-176">application/vnd.ms-powerpoint</span></span> | <span data-ttu-id="f11ce-177">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-177">Document</span></span> | <span data-ttu-id="f11ce-178">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-178">Yes</span></span> | <span data-ttu-id="f11ce-179">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-179">Yes</span></span> | <span data-ttu-id="f11ce-180">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-180">Yes</span></span> | <span data-ttu-id="f11ce-181">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-181">No</span></span> | <span data-ttu-id="f11ce-182">PPT; PPS;. Pot</span><span class="sxs-lookup"><span data-stu-id="f11ce-182">.ppt; .pps;.pot</span></span> |
| <span data-ttu-id="f11ce-183">Application/ВНД. МС-Ворд. Document. макроенаблед. 12</span><span class="sxs-lookup"><span data-stu-id="f11ce-183">application/vnd.ms-word.document.macroenabled.12</span></span> | <span data-ttu-id="f11ce-184">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-184">Document</span></span> | <span data-ttu-id="f11ce-185">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-185">Yes</span></span> | <span data-ttu-id="f11ce-186">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-186">Yes</span></span> | <span data-ttu-id="f11ce-187">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-187">Yes</span></span> | <span data-ttu-id="f11ce-188">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-188">No</span></span> | <span data-ttu-id="f11ce-189">DOCM</span><span class="sxs-lookup"><span data-stu-id="f11ce-189">.docm</span></span> |
| <span data-ttu-id="f11ce-190">Application/ВНД. МС-Ворд. Template. макроенаблед. 12</span><span class="sxs-lookup"><span data-stu-id="f11ce-190">application/vnd.ms-word.template.macroenabled.12</span></span> | <span data-ttu-id="f11ce-191">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-191">Document</span></span> | <span data-ttu-id="f11ce-192">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-192">Yes</span></span> | <span data-ttu-id="f11ce-193">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-193">Yes</span></span> | <span data-ttu-id="f11ce-194">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-194">Yes</span></span> | <span data-ttu-id="f11ce-195">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-195">No</span></span> | <span data-ttu-id="f11ce-196">. dotm</span><span class="sxs-lookup"><span data-stu-id="f11ce-196">.dotm</span></span> |
| <span data-ttu-id="f11ce-197">Application/ВНД. Oasis. OpenDocument. Text</span><span class="sxs-lookup"><span data-stu-id="f11ce-197">application/vnd.oasis.opendocument.text</span></span> | <span data-ttu-id="f11ce-198">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-198">Document</span></span> | <span data-ttu-id="f11ce-199">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-199">Yes</span></span> | <span data-ttu-id="f11ce-200">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-200">Yes</span></span> | <span data-ttu-id="f11ce-201">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-201">Yes</span></span> | <span data-ttu-id="f11ce-202">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-202">No</span></span> | <span data-ttu-id="f11ce-203">Detection</span><span class="sxs-lookup"><span data-stu-id="f11ce-203">.odt;</span></span>  |
| <span data-ttu-id="f11ce-204">application/vnd.openxmlformats-officedocument.presentationml.presentation</span><span class="sxs-lookup"><span data-stu-id="f11ce-204">application/vnd.openxmlformats-officedocument.presentationml.presentation</span></span> | <span data-ttu-id="f11ce-205">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-205">Document</span></span> | <span data-ttu-id="f11ce-206">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-206">Yes</span></span> | <span data-ttu-id="f11ce-207">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-207">Yes</span></span> | <span data-ttu-id="f11ce-208">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-208">Yes</span></span> | <span data-ttu-id="f11ce-209">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-209">No</span></span> | <span data-ttu-id="f11ce-210">PPTX</span><span class="sxs-lookup"><span data-stu-id="f11ce-210">.pptx</span></span> |
| <span data-ttu-id="f11ce-211">Application/ВНД. опенксмлформатс-оффицедокумент. PresentationML. показ слайдов</span><span class="sxs-lookup"><span data-stu-id="f11ce-211">application/vnd.openxmlformats-officedocument.presentationml.slideshow</span></span> | <span data-ttu-id="f11ce-212">Производительность и формат открытого документа</span><span class="sxs-lookup"><span data-stu-id="f11ce-212">Productivity / Open Document Format</span></span> | <span data-ttu-id="f11ce-213">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-213">Yes</span></span> | <span data-ttu-id="f11ce-214">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-214">Yes</span></span> | <span data-ttu-id="f11ce-215">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-215">Yes</span></span> | <span data-ttu-id="f11ce-216">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-216">No</span></span> | <span data-ttu-id="f11ce-217">. ppsx</span><span class="sxs-lookup"><span data-stu-id="f11ce-217">.ppsx</span></span> |
| <span data-ttu-id="f11ce-218">Application/ВНД. опенксмлформатс-оффицедокумент. PresentationML. Template</span><span class="sxs-lookup"><span data-stu-id="f11ce-218">application/vnd.openxmlformats-officedocument.presentationml.template</span></span> | <span data-ttu-id="f11ce-219">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-219">Document</span></span> | <span data-ttu-id="f11ce-220">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-220">Yes</span></span> | <span data-ttu-id="f11ce-221">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-221">Yes</span></span> | <span data-ttu-id="f11ce-222">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-222">Yes</span></span> | <span data-ttu-id="f11ce-223">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-223">No</span></span> | <span data-ttu-id="f11ce-224">. potx</span><span class="sxs-lookup"><span data-stu-id="f11ce-224">.potx</span></span> |
| <span data-ttu-id="f11ce-225">application/vnd.openxmlformats-officedocument.spreadsheetml.sheet</span><span class="sxs-lookup"><span data-stu-id="f11ce-225">application/vnd.openxmlformats-officedocument.spreadsheetml.sheet</span></span> | <span data-ttu-id="f11ce-226">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-226">Document</span></span> | <span data-ttu-id="f11ce-227">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-227">Yes</span></span> | <span data-ttu-id="f11ce-228">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-228">Yes</span></span> | <span data-ttu-id="f11ce-229">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-229">Yes</span></span> | <span data-ttu-id="f11ce-230">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-230">No</span></span> | <span data-ttu-id="f11ce-231">XLSX</span><span class="sxs-lookup"><span data-stu-id="f11ce-231">.xlsx</span></span> |
| <span data-ttu-id="f11ce-232">Application/ВНД. опенксмлформатс-оффицедокумент. SpreadsheetML. Template</span><span class="sxs-lookup"><span data-stu-id="f11ce-232">application/vnd.openxmlformats-officedocument.spreadsheetml.template</span></span> | <span data-ttu-id="f11ce-233">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-233">Document</span></span> | <span data-ttu-id="f11ce-234">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-234">Yes</span></span> | <span data-ttu-id="f11ce-235">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-235">Yes</span></span> | <span data-ttu-id="f11ce-236">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-236">Yes</span></span> | <span data-ttu-id="f11ce-237">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-237">No</span></span> | <span data-ttu-id="f11ce-238">. xltx</span><span class="sxs-lookup"><span data-stu-id="f11ce-238">.xltx</span></span> |
| <span data-ttu-id="f11ce-239">application/vnd.openxmlformats-officedocument.wordprocessingml.document</span><span class="sxs-lookup"><span data-stu-id="f11ce-239">application/vnd.openxmlformats-officedocument.wordprocessingml.document</span></span> | <span data-ttu-id="f11ce-240">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-240">Document</span></span> | <span data-ttu-id="f11ce-241">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-241">Yes</span></span> | <span data-ttu-id="f11ce-242">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-242">Yes</span></span> | <span data-ttu-id="f11ce-243">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-243">Yes</span></span> | <span data-ttu-id="f11ce-244">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-244">No</span></span> | <span data-ttu-id="f11ce-245">DOCX</span><span class="sxs-lookup"><span data-stu-id="f11ce-245">.docx</span></span> |
| <span data-ttu-id="f11ce-246">Application/ВНД. опенксмлформатс-оффицедокумент. WordprocessingML. Template</span><span class="sxs-lookup"><span data-stu-id="f11ce-246">application/vnd.openxmlformats-officedocument.wordprocessingml.template</span></span> | <span data-ttu-id="f11ce-247">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-247">Document</span></span> | <span data-ttu-id="f11ce-248">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-248">Yes</span></span> | <span data-ttu-id="f11ce-249">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-249">Yes</span></span> | <span data-ttu-id="f11ce-250">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-250">Yes</span></span> | <span data-ttu-id="f11ce-251">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-251">No</span></span> | <span data-ttu-id="f11ce-252">. dotx</span><span class="sxs-lookup"><span data-stu-id="f11ce-252">.dotx</span></span> |
| <span data-ttu-id="f11ce-253">Application/ВНД. Visio</span><span class="sxs-lookup"><span data-stu-id="f11ce-253">application/vnd.visio</span></span> | <span data-ttu-id="f11ce-254">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-254">Document</span></span> | <span data-ttu-id="f11ce-255">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-255">Yes</span></span> | <span data-ttu-id="f11ce-256">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-256">Yes</span></span> | <span data-ttu-id="f11ce-257">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-257">Yes</span></span> | <span data-ttu-id="f11ce-258">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-258">No</span></span> | <span data-ttu-id="f11ce-259">. VSD</span><span class="sxs-lookup"><span data-stu-id="f11ce-259">.vsd</span></span> |
| <span data-ttu-id="f11ce-260">приложение/x-7z-сжатый</span><span class="sxs-lookup"><span data-stu-id="f11ce-260">application/x-7z-compressed</span></span> | <span data-ttu-id="f11ce-261">Архив/контейнер</span><span class="sxs-lookup"><span data-stu-id="f11ce-261">Archive / Container</span></span> | <span data-ttu-id="f11ce-262">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-262">No</span></span> | <span data-ttu-id="f11ce-263">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-263">No</span></span> | <span data-ttu-id="f11ce-264">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-264">No</span></span> | <span data-ttu-id="f11ce-265">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-265">Yes</span></span> | <span data-ttu-id="f11ce-266">.7z</span><span class="sxs-lookup"><span data-stu-id="f11ce-266">.7z</span></span> |
| <span data-ttu-id="f11ce-267">приложение/XHTML + XML</span><span class="sxs-lookup"><span data-stu-id="f11ce-267">application/xhtml+xml</span></span> | <span data-ttu-id="f11ce-268">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-268">Document</span></span> | <span data-ttu-id="f11ce-269">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-269">Yes</span></span> | <span data-ttu-id="f11ce-270">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-270">Yes</span></span> | <span data-ttu-id="f11ce-271">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-271">Yes</span></span> | <span data-ttu-id="f11ce-272">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-272">No</span></span> | <span data-ttu-id="f11ce-273">. XHTML</span><span class="sxs-lookup"><span data-stu-id="f11ce-273">.xhtml</span></span> |
| <span data-ttu-id="f11ce-274">Application/XML</span><span class="sxs-lookup"><span data-stu-id="f11ce-274">application/xml</span></span> | <span data-ttu-id="f11ce-275">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-275">Document</span></span> | <span data-ttu-id="f11ce-276">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-276">Yes</span></span> | <span data-ttu-id="f11ce-277">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-277">Yes</span></span> | <span data-ttu-id="f11ce-278">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-278">Yes</span></span> | <span data-ttu-id="f11ce-279">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-279">No</span></span> | <span data-ttu-id="f11ce-280">. XML</span><span class="sxs-lookup"><span data-stu-id="f11ce-280">.xml</span></span> |
| <span data-ttu-id="f11ce-281">приложение/x-Msaccess</span><span class="sxs-lookup"><span data-stu-id="f11ce-281">application/x-msaccess</span></span> | <span data-ttu-id="f11ce-282">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-282">Document</span></span> | <span data-ttu-id="f11ce-283">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-283">Yes</span></span> | <span data-ttu-id="f11ce-284">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-284">Yes</span></span> | <span data-ttu-id="f11ce-285">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-285">Yes</span></span> | <span data-ttu-id="f11ce-286">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-286">No</span></span> | <span data-ttu-id="f11ce-287">. mdb</span><span class="sxs-lookup"><span data-stu-id="f11ce-287">.mdb</span></span> |
| <span data-ttu-id="f11ce-288">Application/x-мспублишер</span><span class="sxs-lookup"><span data-stu-id="f11ce-288">application/x-mspublisher</span></span> | <span data-ttu-id="f11ce-289">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-289">Document</span></span> | <span data-ttu-id="f11ce-290">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-290">Yes</span></span> | <span data-ttu-id="f11ce-291">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-291">Yes</span></span> | <span data-ttu-id="f11ce-292">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-292">Yes</span></span> | <span data-ttu-id="f11ce-293">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-293">No</span></span> | <span data-ttu-id="f11ce-294">. pub</span><span class="sxs-lookup"><span data-stu-id="f11ce-294">.pub</span></span> |
| <span data-ttu-id="f11ce-295">приложение/x-сжатый архив RAR</span><span class="sxs-lookup"><span data-stu-id="f11ce-295">application/x-rar-compressed</span></span> | <span data-ttu-id="f11ce-296">Архив/контейнер</span><span class="sxs-lookup"><span data-stu-id="f11ce-296">Archive / Container</span></span> | <span data-ttu-id="f11ce-297">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-297">No</span></span> | <span data-ttu-id="f11ce-298">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-298">No</span></span> | <span data-ttu-id="f11ce-299">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-299">No</span></span> | <span data-ttu-id="f11ce-300">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-300">Yes</span></span> | <span data-ttu-id="f11ce-301">. rar</span><span class="sxs-lookup"><span data-stu-id="f11ce-301">.rar</span></span> |
| <span data-ttu-id="f11ce-302">приложение/ZIP-индекс</span><span class="sxs-lookup"><span data-stu-id="f11ce-302">application/zip</span></span> | <span data-ttu-id="f11ce-303">Архив/контейнер</span><span class="sxs-lookup"><span data-stu-id="f11ce-303">Archive / Container</span></span> | <span data-ttu-id="f11ce-304">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-304">No</span></span> | <span data-ttu-id="f11ce-305">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-305">No</span></span> | <span data-ttu-id="f11ce-306">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-306">No</span></span> | <span data-ttu-id="f11ce-307">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-307">Yes</span></span> | <span data-ttu-id="f11ce-308">ZIP-</span><span class="sxs-lookup"><span data-stu-id="f11ce-308">.zip</span></span> |
| <span data-ttu-id="f11ce-309">Image/BMP</span><span class="sxs-lookup"><span data-stu-id="f11ce-309">image/bmp</span></span> | <span data-ttu-id="f11ce-310">Изображение</span><span class="sxs-lookup"><span data-stu-id="f11ce-310">Image</span></span> | <span data-ttu-id="f11ce-311">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-311">Yes</span></span> | <span data-ttu-id="f11ce-312">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-312">Yes</span></span> | <span data-ttu-id="f11ce-313">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-313">Yes</span></span> | <span data-ttu-id="f11ce-314">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-314">No</span></span> | <span data-ttu-id="f11ce-315">BMP</span><span class="sxs-lookup"><span data-stu-id="f11ce-315">.bmp</span></span> |
| <span data-ttu-id="f11ce-316">Image/EMF</span><span class="sxs-lookup"><span data-stu-id="f11ce-316">image/emf</span></span> | <span data-ttu-id="f11ce-317">Изображение</span><span class="sxs-lookup"><span data-stu-id="f11ce-317">Image</span></span> | <span data-ttu-id="f11ce-318">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-318">Yes</span></span> | <span data-ttu-id="f11ce-319">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-319">Yes</span></span> | <span data-ttu-id="f11ce-320">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-320">Yes</span></span> | <span data-ttu-id="f11ce-321">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-321">No</span></span> | <span data-ttu-id="f11ce-322">EMF</span><span class="sxs-lookup"><span data-stu-id="f11ce-322">.emf</span></span> |
| <span data-ttu-id="f11ce-323">image/gif</span><span class="sxs-lookup"><span data-stu-id="f11ce-323">image/gif</span></span> | <span data-ttu-id="f11ce-324">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-324">Document</span></span> | <span data-ttu-id="f11ce-325">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-325">Yes</span></span> | <span data-ttu-id="f11ce-326">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-326">Yes</span></span> | <span data-ttu-id="f11ce-327">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-327">Yes</span></span> | <span data-ttu-id="f11ce-328">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-328">No</span></span> | <span data-ttu-id="f11ce-329">GIF</span><span class="sxs-lookup"><span data-stu-id="f11ce-329">.gif</span></span> |
| <span data-ttu-id="f11ce-330">image/jpeg</span><span class="sxs-lookup"><span data-stu-id="f11ce-330">image/jpeg</span></span> | <span data-ttu-id="f11ce-331">Изображение</span><span class="sxs-lookup"><span data-stu-id="f11ce-331">Image</span></span> | <span data-ttu-id="f11ce-332">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-332">Yes</span></span> | <span data-ttu-id="f11ce-333">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-333">Yes</span></span> | <span data-ttu-id="f11ce-334">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-334">Yes</span></span> | <span data-ttu-id="f11ce-335">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-335">No</span></span> | <span data-ttu-id="f11ce-336">JPG;. JPEG;. dat;. жпгт</span><span class="sxs-lookup"><span data-stu-id="f11ce-336">.jpg; .jpeg; .dat;.jpgt</span></span> |
| <span data-ttu-id="f11ce-337">image/png</span><span class="sxs-lookup"><span data-stu-id="f11ce-337">image/png</span></span> | <span data-ttu-id="f11ce-338">Изображение</span><span class="sxs-lookup"><span data-stu-id="f11ce-338">Image</span></span> | <span data-ttu-id="f11ce-339">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-339">Yes</span></span> | <span data-ttu-id="f11ce-340">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-340">Yes</span></span> | <span data-ttu-id="f11ce-341">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-341">Yes</span></span> | <span data-ttu-id="f11ce-342">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-342">No</span></span> | <span data-ttu-id="f11ce-343">PNG</span><span class="sxs-lookup"><span data-stu-id="f11ce-343">.png</span></span> |
| <span data-ttu-id="f11ce-344">Image/TIFF</span><span class="sxs-lookup"><span data-stu-id="f11ce-344">image/tiff</span></span> | <span data-ttu-id="f11ce-345">Изображение</span><span class="sxs-lookup"><span data-stu-id="f11ce-345">Image</span></span> | <span data-ttu-id="f11ce-346">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-346">Yes</span></span> | <span data-ttu-id="f11ce-347">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-347">Yes</span></span> | <span data-ttu-id="f11ce-348">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-348">Yes</span></span> | <span data-ttu-id="f11ce-349">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-349">No</span></span> | <span data-ttu-id="f11ce-350">TIF</span><span class="sxs-lookup"><span data-stu-id="f11ce-350">.tif</span></span> |
| <span data-ttu-id="f11ce-351">Image/ВНД. DWG</span><span class="sxs-lookup"><span data-stu-id="f11ce-351">image/vnd.dwg</span></span> | <span data-ttu-id="f11ce-352">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-352">Document</span></span> | <span data-ttu-id="f11ce-353">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-353">Yes</span></span> | <span data-ttu-id="f11ce-354">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-354">Yes</span></span> | <span data-ttu-id="f11ce-355">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-355">Yes</span></span> | <span data-ttu-id="f11ce-356">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-356">No</span></span> | <span data-ttu-id="f11ce-357">. DWG;. DXF</span><span class="sxs-lookup"><span data-stu-id="f11ce-357">.dwg;.dxf;</span></span> |
| <span data-ttu-id="f11ce-358">Image/WMF</span><span class="sxs-lookup"><span data-stu-id="f11ce-358">image/wmf</span></span> | <span data-ttu-id="f11ce-359">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-359">Document</span></span> | <span data-ttu-id="f11ce-360">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-360">Yes</span></span> | <span data-ttu-id="f11ce-361">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-361">Yes</span></span> | <span data-ttu-id="f11ce-362">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-362">Yes</span></span> | <span data-ttu-id="f11ce-363">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-363">No</span></span> | <span data-ttu-id="f11ce-364">. WMF</span><span class="sxs-lookup"><span data-stu-id="f11ce-364">.wmf</span></span> |
| <span data-ttu-id="f11ce-365">message/rfc822</span><span class="sxs-lookup"><span data-stu-id="f11ce-365">message/rfc822</span></span> | <span data-ttu-id="f11ce-366">Производительность и совместная работа</span><span class="sxs-lookup"><span data-stu-id="f11ce-366">Productivity / Collaboration</span></span> | <span data-ttu-id="f11ce-367">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-367">No</span></span> | <span data-ttu-id="f11ce-368">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-368">No</span></span> | <span data-ttu-id="f11ce-369">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-369">No</span></span> | <span data-ttu-id="f11ce-370">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-370">No</span></span> | <span data-ttu-id="f11ce-371">EML</span><span class="sxs-lookup"><span data-stu-id="f11ce-371">.eml</span></span> |
| <span data-ttu-id="f11ce-372">Text/CSV</span><span class="sxs-lookup"><span data-stu-id="f11ce-372">text/csv</span></span> | <span data-ttu-id="f11ce-373">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-373">Document</span></span> | <span data-ttu-id="f11ce-374">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-374">Yes</span></span> | <span data-ttu-id="f11ce-375">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-375">Yes</span></span> | <span data-ttu-id="f11ce-376">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-376">Yes</span></span> | <span data-ttu-id="f11ce-377">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-377">No</span></span> | <span data-ttu-id="f11ce-378">CSV-файл</span><span class="sxs-lookup"><span data-stu-id="f11ce-378">.csv</span></span> |
| <span data-ttu-id="f11ce-379">Text/HTML</span><span class="sxs-lookup"><span data-stu-id="f11ce-379">text/html</span></span> | <span data-ttu-id="f11ce-380">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-380">Document</span></span> | <span data-ttu-id="f11ce-381">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-381">Yes</span></span> | <span data-ttu-id="f11ce-382">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-382">Yes</span></span> | <span data-ttu-id="f11ce-383">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-383">Yes</span></span> | <span data-ttu-id="f11ce-384">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-384">No</span></span> | <span data-ttu-id="f11ce-385">. HTML;. shtml; htm</span><span class="sxs-lookup"><span data-stu-id="f11ce-385">.html;.shtml; .htm</span></span> |
| <span data-ttu-id="f11ce-386">text/plain</span><span class="sxs-lookup"><span data-stu-id="f11ce-386">text/plain</span></span> | <span data-ttu-id="f11ce-387">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-387">Document</span></span> | <span data-ttu-id="f11ce-388">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-388">Yes</span></span> | <span data-ttu-id="f11ce-389">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-389">Yes</span></span> | <span data-ttu-id="f11ce-390">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-390">Yes</span></span> | <span data-ttu-id="f11ce-391">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-391">No</span></span> | <span data-ttu-id="f11ce-392">. txt;. CSS;. Con;. pl;. csv;. dat</span><span class="sxs-lookup"><span data-stu-id="f11ce-392">.txt; .css;.con; .pl; .csv; .dat</span></span> |
| <span data-ttu-id="f11ce-393">текст/vCard-Contact</span><span class="sxs-lookup"><span data-stu-id="f11ce-393">text/vcard-contact</span></span> | <span data-ttu-id="f11ce-394">Document</span><span class="sxs-lookup"><span data-stu-id="f11ce-394">Document</span></span> | <span data-ttu-id="f11ce-395">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-395">Yes</span></span> | <span data-ttu-id="f11ce-396">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-396">Yes</span></span> | <span data-ttu-id="f11ce-397">Да</span><span class="sxs-lookup"><span data-stu-id="f11ce-397">Yes</span></span> | <span data-ttu-id="f11ce-398">Нет</span><span class="sxs-lookup"><span data-stu-id="f11ce-398">No</span></span> | <span data-ttu-id="f11ce-399">. vcf</span><span class="sxs-lookup"><span data-stu-id="f11ce-399">.vcf</span></span> |
||||||||