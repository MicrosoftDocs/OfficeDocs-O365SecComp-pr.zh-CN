---
title: 搜索统计信息
ms.author: markjjo
author: esclee
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
ms.openlocfilehash: c5b7caff3550d42d84408d6b4e966655b8341123
ms.sourcegitcommit: ee28ee2b2bdfd049333c2f495d7f7780d13af4a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2019
ms.locfileid: "29607474"
---
# <a name="search-statistics"></a>搜索统计信息
您可以验证搜索结果的一种方法是查看您的结果，以确保它们与您的期望对齐周围的统计信息。在搜索完成后，高级统计信息将显示在搜索的详细信息弹出：
- 号码和搜索检索的项目量
- 号码和量部分编制索引/未编制索引的搜索位置中找到的项目
- 搜索邮箱和位置的数量。才能查看更多详细统计信息，请单击"统计"从搜索的详细信息弹出。

## <a name="summary"></a>摘要
在摘要视图中，您可以看到按位置类型 (例如 Exchange) 划分的搜索结果。对于每个位置类型，您可以看到：
- 有搜索条件匹配的项的位置数
- 从这些位置的搜索条件匹配的项目数
- 总搜索条件匹配的项目量。

## <a name="top-locations"></a>顶部的位置
在顶部的位置视图中，您将看到与最匹配的各个位置。对于每个位置，您将看到：
- 位置名称 (例如 SharePoint URL)
- 位置类型
- 匹配搜索条件的项目数
- 总搜索条件匹配的项目量。

## <a name="queries"></a>查询
如果您使用了 (c:s) 关键字或关键字行在查询中，您可以看到每个位置类型的查询视图中的查询的细分。对于每个位置类型，您将看到：
- 部件： 此列会单词"主"或"关键字"。"主要"表示行提供统计信息，介绍整个查询，而"关键字"表示查询组件之一。
- 查询： 行引用的实际查询组件。如果"主"部分，这将是整个查询。如果"关键字"部分，您将看到下面的查询组件之一。
  - 在搜索内容的所有邮箱 （通过不指定任何关键字） 时，是实际的查询 (大小 > = 0)，以便返回所有项
  - 在 SharePoint Online 和 OneDrive 搜索业务网站时，会添加两个以下组件：
    - 不 IsExternalContent:1-从内部部署 SharePoint 组织排除任何内容
    - 不 isOneNotePage: 1-排除所有 OneNote 文件，因为这些都是相匹配的搜索查询的任何文档的重复项。
- 有搜索条件匹配的项的位置数
- 从这些位置的搜索条件匹配的项目数
- 搜索条件匹配的项目的总 volumne。

## <a name="refiners"></a>精简程序
Exchange 邮箱中，优化器视图为您提供了 ItemClass、 发件人和收件人的其他损害。对于每个位置和优化器值，您可以看到多少个文档已返回在搜索。