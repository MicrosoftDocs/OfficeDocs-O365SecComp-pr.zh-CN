---
title: Microsoft 365 中的数据调查 （预览） 发行说明
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
description: 本文介绍了高级电子数据展示 （预览） Microsoft 365 中的新版本。
ms.openlocfilehash: 90bcbd4cae1e410e1544352a776ba4cbbedfa429
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695058"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a>Microsoft 365 中的数据调查 （预览） 发行说明

您可以使用新的数据调查 （预览） 工具在 Microsoft 365 会审、 调查和修正数据中相关的事件，如数据泄漏事件或内部调查。公共数据预览调查为您提供了到即将到来的功能和更新的及早访问。若要获取的最新功能的及早访问，请在 Office 365 安全性 & 合规性中心中创建数据调查 (Preview) 中的新调查。若要了解如何，请参阅[Manage Microsoft 365 中的数据泄漏事件](manage-data-spillage-incidents.md)。

## <a name="whats-new"></a>新增功能 

- **调查**-您可以通过创建调查组搜索和事件。管理谁可以访问调查通过添加或删除成员。 您还可以选择并标记您喜欢的调查。跟踪和监视活动内部以及跨使用新的仪表板调查。完成调查后，您可以关闭或将其删除。

- **人员感兴趣的**– 当您将用户添加到调查的值得关注的人一样，您可以看到他们的邮箱，OneDrive for Business 帐户和 Microsoft 团队网站。您可以使用它们来限制在调查的内容搜索范围。若要进一步调查值得关注的人员，您还可以查看审核与 Office 365 和其他 Microsoft 服务中其活动相关的记录。

- **搜索**– 创建组织范围内搜索使用各种搜索条件。如果您知道用户或您要搜索的网站，您可以这样通过将这些用户添加为利息或搜索创建向导中指定的网站位置的人员。 

- **事件**– 创建一个新的事件，并添加您想要查看的搜索结果。您可以查看单个文档、 批注以留言调查和导出结果将移动到不同的环境。 

- **查看**– 使用本机、 文本和近本机视图以查看添加到事件的文档。您可以通过重复项、 电子邮件线程和主题，帮助您进行审阅事件的可帮助向对项目进行分组的文档应用分析。 

- **Redact，标记，并批注**– 标记密文文本、 应用标记，并在您阅读文档进行注释。
  
- **深入索引**– 如果有任何部分索引的项，它们将按需重新编制索引，以便所有数据都将可供搜索。

- **错误修复**– 修正或下载处理错误。这包括修正支持较大的文件类型、 受密码保护的文件和其他与索引错误相关的问题。 

- **作业**– 跟踪状态的长期运行的过程。

- **硬盘删除邮箱项目**-在紧急情况下，您可能需要永久删除错放的项目。若要执行此操作，您可以运行**新建 ComplianceSearchAction-清除-PurgeType HardDelete**命令中安全 & 合规性中心 PowerShell，可以从邮箱中永久删除项目。有关详细信息，请参阅[新建 ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction)。
