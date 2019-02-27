---
title: Microsoft 365 中的数据调查 (预览) 发布说明
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 本文介绍了 Microsoft 365 中高级电子数据展示 (预览) 的新版本。
ms.openlocfilehash: 900031815ef1a2bbbd770c22db958659d8a0ef99
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30297025"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a>Microsoft 365 中的数据调查 (预览) 发布说明

您可以使用 Microsoft 365 中的新数据调查 (预览版) 工具对数据相关事件进行会审、调查和补救, 如数据外泄事件或内部调查。数据调查的公共预览为您提供了对即将推出的功能和更新的早期访问权限。若要尽早访问最新功能, 请在 "Office 365 安全 & 合规中心" 中创建一个新的数据调查 (预览版) 调查。若要了解如何操作, 请参阅[在 Microsoft 365 中管理数据外泄事件](manage-data-spillage-incidents.md)。

## <a name="whats-new"></a>新增功能 

- **调查**-您可以通过创建调查来对搜索和事件进行分组。通过添加或删除成员来管理可访问调查的人员。 您还可以选择并标记您喜爱的调查。使用新仪表板跟踪和监控调查中和跨调查的活动。完成调查后, 可以关闭或删除它。

- **感兴趣的人**–当您将用户添加到调查中的人时, 您可以查看他们的邮箱、OneDrive for business 帐户和 Microsoft 团队网站。您可以使用它们来限定调查内容搜索的范围。若要进一步调查感兴趣的人员, 您还可以查看与 Office 365 和其他 Microsoft 服务中的活动相关的审核记录。

- **搜索**–使用各种搜索条件创建组织范围的搜索。如果您知道要搜索的用户或网站, 可以通过将这些用户添加为感兴趣的人员或在 "搜索创建向导" 中指定网站位置来执行此操作。 

- **事件**–创建新的事件并添加要查看的搜索结果。您可以查看各个文档、批注以留下调查说明, 以及导出结果以移到不同的环境。 

- **审阅**–使用本机、文本和近本机视图查看添加到事件中的文档。您还可以将分析应用于文档以按重复项、电子邮件线索和主题对项目进行分组, 这有助于协助您复查事件。 

- **密文、标记和批注**–在审阅文档时设置密文、应用标记和批注。
  
- **深层索引**–如果有任何部分已编制索引的项目, 它们将按需重新编制索引, 以便所有数据都可供搜索。

- **错误修正**–修正或下载处理错误。这包括对大型文件类型的补救性支持、受密码保护的文件以及与索引错误相关的其他问题。 

- **作业**–跟踪长时间运行的进程的状态。

- **硬删除邮箱项目**-在紧急情况下, 可能需要永久删除错放的项目。为此, 您可以在安全 & 合规中心 PowerShell 中运行**new-compliancesearchaction-PurgeType HardDelete**命令, 以从邮箱中永久删除项目。有关详细信息, 请参阅[new-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction)。
