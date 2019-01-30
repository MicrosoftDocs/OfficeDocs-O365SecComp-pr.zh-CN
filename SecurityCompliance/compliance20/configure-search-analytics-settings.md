---
title: 配置搜索和分析设置
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: d9528a4bcfaa77f2e232b25d03eda46cce42ebb9
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607445"
---
# <a name="configure-search-and-analytics-settings"></a><span data-ttu-id="fcdd4-102">配置搜索和分析设置</span><span class="sxs-lookup"><span data-stu-id="fcdd4-102">Configure search and analytics settings</span></span>


## <a name="near-duplicates-and-email-threading"></a><span data-ttu-id="fcdd4-103">Near 重复项和电子邮件线程处理</span><span class="sxs-lookup"><span data-stu-id="fcdd4-103">Near duplicates and email threading</span></span>

<span data-ttu-id="fcdd4-104">在此部分中，您可以设置重复检测，靠近重复检测和电子邮件超线程的参数。</span><span class="sxs-lookup"><span data-stu-id="fcdd4-104">In this section, you can set parameters for duplicate detection, near duplicate detection, and email threading.</span></span>

- <span data-ttu-id="fcdd4-p101">启用/禁用： 包括重复检测，靠近重复检测和电子邮件线程分析流如果启用的一部分。因为它们彼此生成，您必须启用所有这些或禁用所有这些。</span><span class="sxs-lookup"><span data-stu-id="fcdd4-p101">Enable/disable: include duplicate detection, near duplicate detection, and email threading as part of analytics flow if enabled. Because they build on top of each other, you must enable all of them or disable all of them.</span></span>

- <span data-ttu-id="fcdd4-107">阈值： 如果两个文档的相似性级别是高于阈值，它们将处于近乎重复的设置相同。</span><span class="sxs-lookup"><span data-stu-id="fcdd4-107">Threshold: if the similarity level of two documents are above the threshold, they will be put in the same near duplicate set.</span></span>

- <span data-ttu-id="fcdd4-p102">默认情况下隐藏重复项： 如果在此设置，将在默认情况下设置工作应用筛选器以隐藏重复文档。中工作集有必要，可以手动删除筛选器。</span><span class="sxs-lookup"><span data-stu-id="fcdd4-p102">Hide duplicates by default: if this setting is on, a filter to hide duplicate documents will be applied in the working set by default. The filter can be removed manually in the working set if necessary.</span></span>

- <span data-ttu-id="fcdd4-p103">最小/最大单词数： 近乎重复项和电子邮件线程将上仅运行至少拥有的单词数最小和最多的最大单词数的文档。有关详细信息，请参阅[Near 重复检测](near-duplicates.md)和[电子邮件超线程](email-threading.md)。</span><span class="sxs-lookup"><span data-stu-id="fcdd4-p103">Minimum/maximum number of words: near duplicates and email threading will run only on documents that have at least the minimum number of words and at most the maximum number of words. For more information, see [Near duplicate detection](near-duplicates.md) and [Email threading](email-threading.md).</span></span>

## <a name="themes"></a><span data-ttu-id="fcdd4-112">主题</span><span class="sxs-lookup"><span data-stu-id="fcdd4-112">Themes</span></span>

<span data-ttu-id="fcdd4-113">在此部分中，您可以设置主题的参数。</span><span class="sxs-lookup"><span data-stu-id="fcdd4-113">In this section, you can set parameters for themes.</span></span>

- <span data-ttu-id="fcdd4-114">启用/禁用： 包括群集分析流如果启用的一部分的主题。</span><span class="sxs-lookup"><span data-stu-id="fcdd4-114">Enable/disable: include themes clustering as part of analytics flow if enabled.</span></span>
- <span data-ttu-id="fcdd4-p104">动态动态调整主题的最大数目： 在某些情况下，没有足够的文档生成所需的主题数。如果打开此设置，然后而不是强制主题，所需的最大数目在尝试系统调整主题的最大数目动态。</span><span class="sxs-lookup"><span data-stu-id="fcdd4-p104">Adjust maximum number of themes dynamically dynamically: in certain cases, there are not enough documents to produce the desired number of themes. If this setting is turned on, then rather than trying to force the desired maximum number of themes, the system adjusts maximum number of themes dynamically.</span></span>
- <span data-ttu-id="fcdd4-117">主题的最大数目： 所需的主题</span><span class="sxs-lookup"><span data-stu-id="fcdd4-117">Maximum number of themes: desired number of themes</span></span>
- <span data-ttu-id="fcdd4-118">在主题中包括号： 启用时，生成主题时，它将包括中的号码。</span><span class="sxs-lookup"><span data-stu-id="fcdd4-118">Include numbers in themes: When enabled, it will include numbers in when generating themes.</span></span>  

## <a name="optical-character-recognition-ocr"></a><span data-ttu-id="fcdd4-119">光学字符识别 (OCR)</span><span class="sxs-lookup"><span data-stu-id="fcdd4-119">Optical character recognition (OCR)</span></span>

<span data-ttu-id="fcdd4-120">启用此设置后，将运行 OCR 上 ingested 到工作集，以便他们可以是可搜索的图像。</span><span class="sxs-lookup"><span data-stu-id="fcdd4-120">When this setting is turned on, OCR will be run on images that are ingested into working sets so that they can be searchable.</span></span>

## <a name="ignore-text"></a><span data-ttu-id="fcdd4-121">忽略文本</span><span class="sxs-lookup"><span data-stu-id="fcdd4-121">Ignore text</span></span>

<span data-ttu-id="fcdd4-p105">有其中某些文本将降低分析，例如获取添加到特定电子邮件与电子邮件内容无关的长免责声明的质量的实例。如果您注意这种情况下，可以从中排除此文本分析通过指定的文本 （支持正则表达式） 和其中的文本应排除的模块。</span><span class="sxs-lookup"><span data-stu-id="fcdd4-p105">There are instances where certain texts will diminish the quality of analytics, such as lengthy disclaimers that get added to certain emails regardless of the content of the email. If you are aware of such cases, you can exclude this text from analytics by specifying the text (RegEx is supported) and which modules that text should be excluded for.</span></span>