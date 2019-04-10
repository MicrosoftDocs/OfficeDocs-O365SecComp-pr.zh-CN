---
title: 在高级电子数据展示中管理作业 (预览)
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
ms.openlocfilehash: e5f7c6d0f0932041ef92591afcb59ad836cae0e4
ms.sourcegitcommit: 19d27ff836ee7fa1f8a4e761e04d928f13f4bfd8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "31745284"
---
# <a name="manage-jobs-in-advanced-ediscovery-preview"></a>在高级电子数据展示中管理作业 (预览)

下面列出了高级电子数据展示 (预览) 中的 "**作业**" 选项卡上跟踪的作业 (通常为长时间运行的进程)。 这些作业是在使用和管理案例时由用户操作触发的。

| 作业类型            | 描述     |
| :----------------- | :----------     |
|将数据添加到工作集 | 用户将搜索结果添加到工作集。  有关详细信息, 请参阅[将搜索结果添加到工作集](add-data-to-working-set.md)。 |
|将数据添加到另一个工作集 | 用户在同一情况下将文档从一个工作集添加到不同的工作集。|
|将非 Office 365 数据添加到工作集 | 用户将非 Office 365 数据上载到工作集。 在此过程中, 还会对数据编制索引。 例如, 将本地文件服务器或客户端计算机上的文件上载到工作集。 有关详细信息, 请参阅[将非 Office 365 数据加载到工作集](load-non-office365-data.md)。| 
|将修正的数据添加到工作集 | 将修正带有处理错误的数据, 并将其重新加载回工作集。 有关详细信息, 请参阅[处理数据时的错误修正](error-remediation.md)。 | 
|比较负载集 | 用户查看工作集中不同加载集之间的差异。 加载集是将数据添加到工作集的实例。 例如, 如果将两个不同搜索的结果添加到同一工作集, 每个搜索将代表一个负载集。 有关详细信息, 请参阅[管理加载集](manage-load-sets.md)。 |
|将编辑文档转换为 PDF|在用户 annotates 工作集中的文档并修订该文档的一部分后, 他们可以选择将编辑文档转换为 PDF 文件。 这样可确保在导出文档以进行演示时不会显示编辑部分。 有关详细信息, 请参阅[在工作集中查看文档](annotating-and-redacting-documents.md)。 |
|估计搜索结果 | 在用户创建并运行新的搜索 (或重新运行现有搜索) 后, 搜索工具会在索引中搜索与搜索查询匹配的项目, 并准备一个估计, 其中包括搜索的所有项目的数量和总大小以及数据源的数量 searched。  有关详细信息, 请参阅为[事例收集数据](collecting-data-for-ediscovery.md)。 | 
|准备数据以供导出 | 用户从工作集中导出文档。 导出过程完成后, 可以将导出的数据下载到本地计算机。 有关详细信息, 请参阅[导出事例数据](exporting-data-ediscover20.md)。 | 
|为错误解决做准备 |当用户在事例的 "**处理**" 选项卡上的 "错误" 视图中选择文件并创建新的错误修正时, 该过程中的第一步是将具有处理错误的文件上传到 Microsoft 云中的 Azure 存储位置。 此作业跟踪上载过程的进度。 有关错误修正工作流的详细信息, 请参阅[处理数据时的错误修正](error-remediation.md)。 | 
|准备搜索预览 | 在用户创建并运行新的搜索 (或重新运行现有搜索) 后, 搜索工具准备可预览的项的示例子集 (与搜索查询匹配)。 预览搜索结果可帮助您确定搜索的有效性。  有关详细信息, 请参阅为[事例收集数据](collecting-data-for-ediscovery.md#view-search-results-and-statistics)。 | 
|对保管人数据重新编制索引 | 将管理员添加到事例时, 将通过名为 "*高级索引*" 的过程对保管人的选定数据源中的所有部分索引项目重新编制索引。 如果在事例的 "**处理**" 选项卡上单击 "索引视图" 中的 "**更新索引**", 也会触发此作业。 有关详细信息, 请参阅[高级索引的保管人数据](indexing-custodian-data.md)。
|运行分析 | 用户通过运行高级电子数据展示分析工具 (如近期重复检测、电子邮件线程分析和主题分析) 来分析工作集中的数据。 有关详细信息, 请参阅[分析工作集中的数据](analyzing-data-in-working-set.md)。 | 
|标记文档 | 当用户在工作集中审阅文档时, 当用户单击 "**标记" 面板**中的 "**开始标记作业**" 时, 将触发此作业。 用户可以在工作集中对文档进行标记, 然后在 "查看文档" 面板中批量选择这些文档, 从而启动此作业。 有关详细信息, 请参阅[标记文档在工作集中](tagging-documents.md)。 | 
|||
