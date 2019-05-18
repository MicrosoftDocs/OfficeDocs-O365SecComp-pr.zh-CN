---
title: 搜索统计信息
ms.author: markjjo
author: esclee
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
ms.openlocfilehash: fe4d1c92230bcc4e6e1136eeb43c99cc6d8297ca
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151404"
---
# <a name="search-statistics"></a>搜索统计信息

验证搜索结果的一种方法是查看结果周围的统计信息, 以确保它们符合您的预期。 搜索完成后, "搜索详细信息" 浮出控件上将显示高级别统计信息:
- 搜索检索到的项目数和数量
- 在搜索位置中找到的部分已编制索引/未编制索引的项目的编号和数量
- 搜索的邮箱和位置的数量。
若要查看更详细的统计信息, 请单击 "搜索详细信息" 浮出控件中的 "统计信息"。

## <a name="summary"></a>Summary

在摘要视图中, 你可以看到按位置类型 (如 Exchange) 细分的搜索结果。 对于每个位置类型, 您可以查看以下内容:
- 包含符合搜索条件的项目的位置数
- 来自符合搜索条件的这些位置的项目数
- 符合搜索条件的项的总数量。

## <a name="top-locations"></a>顶部位置

在 "顶端位置" 视图中, 可以看到具有最匹配项的各个位置。 对于每个位置, 您将看到:
- 位置名称 (例如, SharePoint URL)
- 位置类型
- 匹配搜索条件的项目数
- 符合搜索条件的项的总数量。

## <a name="queries"></a>Queries

如果您已在查询中使用 (c:s) 关键字或关键字行, 则可以在 "每个位置的查询视图" 类型中查看查询细目。 对于每个位置类型, 您将看到:

- 部分: 此列将包含 "Primary" 或 "关键字" 一词。 "Primary" 表示该行显示整个查询的统计信息, 而 "关键字" 表示查询组件之一。

- 查询: 行所引用的实际查询组件。 如果 Part 为 "Primary", 则为整个查询;如果 Part 为 "关键字", 你将在此处看到一个查询组件。
  
  - 当您搜索所有 contentin 邮箱 (未指定任何关键字) 时, 实际查询是 (size > = 0), 以便返回所有项目
  
  - 当您搜索 SharePoint Online 和 OneDrive for Business 网站时, 将添加以下两个组件:
    
    - NOT IsExternalContent: 1-排除本地 SharePoint 组织中的任何内容
    
    - NOT isOneNotePage: 1-排除所有 OneNote 文件, 因为这些文件是与搜索查询相匹配的任何文档的重复项。

- 包含符合搜索条件的项目的位置的数量。

- 来自这些位置的符合搜索条件的项目数。

- 符合搜索条件的项的总数量。