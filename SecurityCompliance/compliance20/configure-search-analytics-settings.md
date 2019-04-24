---
title: 配置搜索和分析设置
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 0f5a98a7ba7a62e3b77794b38e444006a340cb49
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32243185"
---
# <a name="configure-search-and-analytics-settings"></a>配置搜索和分析设置

## <a name="near-duplicates-and-email-threading"></a>临近重复项和电子邮件线程

在此部分中, 您可以设置重复检测、接近重复检测和电子邮件线程的参数。

- 启用/禁用: 包括重复检测、接近重复检测和电子邮件线程 (如果已启用) 作为分析流的一部分。 由于它们是相互依赖的, 因此必须全部启用或禁用所有这些版本。

- 阈值: 如果两个文档的相似性级别高于阈值, 则它们将放在相同的临近重复集内。

- 默认情况下隐藏重复项: 如果启用此设置, 则默认情况下将在工作集中应用用于隐藏重复文档的筛选器。 如果需要, 可以在工作集中手动删除筛选器。

- 最小/最大单词数: 临近重复项和电子邮件线程处理将仅在至少包含最少单词数和最大单词数的文档中运行。
有关详细信息, 请参阅[接近重复检测](near-duplicates.md)和[电子邮件线程](email-threading.md)。

## <a name="themes"></a>主题

在本节中, 您可以设置主题的参数。

- 启用/禁用: 将主题群集包含为分析流 (如果已启用) 的一部分。
- 动态动态调整主题的最大数量: 在某些情况下, 没有足够的文档来生成所需数量的主题。 如果启用此设置, 则不是尝试强制实施所需的最大主题数, 系统会动态调整最大主题数。
- 主题的最大数量: 所需的主题数量
- 主题中包含数字: 如果启用此选项, 它将在生成主题时包含数字。  

## <a name="optical-character-recognition-ocr"></a>光学字符识别 (OCR)

启用此设置后, OCR 将在引入工作集的图像上运行, 以便可以对其进行搜索。

## <a name="ignore-text"></a>忽略文本

有些情况下, 某些文本会降低分析质量, 例如, 如果不考虑电子邮件的内容, 则添加到特定电子邮件的冗长免责声明。 如果您知道这种情况, 可以通过指定文本 (RegEx 受支持) 以及应排除文本的模块来从分析中排除此文本。