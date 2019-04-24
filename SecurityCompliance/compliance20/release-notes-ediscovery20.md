---
title: 高级电子数据展示的发行说明 (预览)
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
description: 本文包含适用于高级电子数据展示的发行说明 (预览)。
ms.openlocfilehash: 32a02c16fd30e740fcc6e1c99b46775b97590a28
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32240937"
---
# <a name="release-notes-for-advanced-ediscovery-preview"></a>高级电子数据展示的发行说明 (预览)

高级电子数据展示的公共预览计划是提前获取即将推出的功能和更新的方法。 若要尽早访问最新功能, 只需在 Office 365 安全 & 合规中心中创建和使用高级电子数据展示 (预览版) 事例即可。 请参阅[创建新事例](create-new-ediscovery-case.md)。

## <a name="known-issues"></a>已知问题

**Microsoft Forms**

- 在将高级电子数据展示 (预览) 中的搜索工具用于搜索保管人邮箱时, 与在2019年1月31日之前创建的表单对应的数据将不可搜索。 在此日期之后创建的表单可供搜索。

- 用户创建的表单仍可以接收响应, 即使创建该表单的用户被删除也是如此。 但是, 当使用高级电子数据展示 (预览) 中的搜索工具搜索保管人邮箱时, 这些响应的相应数据 (在保管人邮箱删除之后发生) 将不可搜索。
 
**Microsoft Sway**

- 如果用户在为该 sway 的所有者删除用户帐户之前编辑 sway, 则在使用高级电子数据展示 (预览) 中的搜索工具搜索保管人邮箱时, 这些更改可能无法搜索。 sway 会在收到已删除帐户的信号时立即阻止对该 sway 的更改。 但是, 在收到此信号之前, 可以编辑 sway 的可能性很小。

## <a name="issues-fixed-in-this-release"></a>此版本中修复的问题

- DCR: 未编制索引的项目和孤立项目的异常处理
- DCR: 保留通知
- DCR: 电子数据展示中的保管人

## <a name="whats-new"></a>新增功能

- **安全 & 合规性中心中重新设计的导航**-高级电子数据展示 (预览) 具有新的外观和感觉。 使用高级电子数据展示 (预览) 来管理更多的事例工作流。

- **案例管理**–还提供了对新事例类型的其他支持。 您还可以选择并保存最近和喜欢的案例。 使用新仪表板跟踪和监控各个事例中的活动。

- **保管人管理**–在某个情况下将用户添加和删除为数据保管人。

- **Exchange、onedrive 和团队集成**–自动将用户的当前邮箱、OneDrive for business 帐户和 Microsoft 团队网站添加到一个案例。 

- **保管人通信**–代表你的组织发送和管理法律封存通知。

- **保管人门户**–用于保管人的新门户, 可访问他们的活动保留通知。

- **深度索引**–根据需要重新对部分索引项进行爬网。

- **错误修正**–修正或下载处理错误;这包括对大型文件类型、受密码保护的文件等的补救性支持。 

- **搜索改进**-通过确定保管人和/或位置来创建搜索。

- **工作集**–管理、跟踪和审核一组静态文档。

- **审阅**–使用本机、文本和近本机视图查看添加到工作集的文档。

- **密文、标记和批注**–在审阅文档时设置密文、应用标记和批注。
  
- **分析-已通过分析-** 利用电子数据展示分析在工作集中查找、搜索和挑选结果。

- **作业**–跟踪长时间运行的进程的状态。

- **新的审核活动**–跟踪并查看高级电子数据展示的新审核活动。
