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
# <a name="configure-search-and-analytics-settings"></a>配置搜索和分析设置


## <a name="near-duplicates-and-email-threading"></a>Near 重复项和电子邮件线程处理

在此部分中，您可以设置重复检测，靠近重复检测和电子邮件超线程的参数。

- 启用/禁用： 包括重复检测，靠近重复检测和电子邮件线程分析流如果启用的一部分。因为它们彼此生成，您必须启用所有这些或禁用所有这些。

- 阈值： 如果两个文档的相似性级别是高于阈值，它们将处于近乎重复的设置相同。

- 默认情况下隐藏重复项： 如果在此设置，将在默认情况下设置工作应用筛选器以隐藏重复文档。中工作集有必要，可以手动删除筛选器。

- 最小/最大单词数： 近乎重复项和电子邮件线程将上仅运行至少拥有的单词数最小和最多的最大单词数的文档。有关详细信息，请参阅[Near 重复检测](near-duplicates.md)和[电子邮件超线程](email-threading.md)。

## <a name="themes"></a>主题

在此部分中，您可以设置主题的参数。

- 启用/禁用： 包括群集分析流如果启用的一部分的主题。
- 动态动态调整主题的最大数目： 在某些情况下，没有足够的文档生成所需的主题数。如果打开此设置，然后而不是强制主题，所需的最大数目在尝试系统调整主题的最大数目动态。
- 主题的最大数目： 所需的主题
- 在主题中包括号： 启用时，生成主题时，它将包括中的号码。  

## <a name="optical-character-recognition-ocr"></a>光学字符识别 (OCR)

启用此设置后，将运行 OCR 上 ingested 到工作集，以便他们可以是可搜索的图像。

## <a name="ignore-text"></a>忽略文本

有其中某些文本将降低分析，例如获取添加到特定电子邮件与电子邮件内容无关的长免责声明的质量的实例。如果您注意这种情况下，可以从中排除此文本分析通过指定的文本 （支持正则表达式） 和其中的文本应排除的模块。