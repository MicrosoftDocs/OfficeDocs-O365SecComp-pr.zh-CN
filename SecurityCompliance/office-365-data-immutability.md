---
title: Office 365 数据域永久性
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 定义并解释了域永久性数据或必须能够发现的数据，无法销毁或更改。
ms.openlocfilehash: 3a9e897734c1805e25a2e2dd5e0c5f8a3e3de3fd
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525678"
---
# <a name="immutability-in-office-365"></a>Office 365 中的永久性
对于某些组织、 法规遵从性、 内部控制要求或诉讼风险要求保留电子邮件和关联的数据可供搜索的窗体中。系统中的所有数据都必须能够发现，并且可以销毁或更改任何它。为此的行业标准术语是"域永久性。" 

传统方法的实现域永久性通常已经通过电子邮件移动到单独的只读的存储位置。尽管这样的系统实现保留邮箱项目的发现的目的，它们通常影响的用户体验重要方式保留从习惯日常工作流项目中删除。面向 IT 专业人员域永久性此方法需要的部署和正在进行维护单独的服务器和存储基础结构。发现本身执行与外部邮件系统，与相关联的部署和维护成本的工具。

通过就地保留和存档和与 Office 365 套件，例如 Exchange Online、 SharePoint Online、 OneDrive for Business 和 Skype for Business 中的服务一起使用 Office 365 中的保留策略功能的配置Office 365 中的存档可以保留并保留许多类的传入和传出的内部数据包括：
- 入站和出站电子邮件通信
- 书籍和包含在电子邮件窗体或共享的联机文档中的记录
- 会议请求
- 传真
- 即时消息
- 联机会议期间共享的文档
- 语音邮件

此外，Microsoft 具有开发加载项功能，以便通过集成的其他源中[数据的存档](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc)与第三方数据捕获和管理解决方案。导入第三方数据后，您可以应用于 Office 365 合规性功能的数据，包括诉讼保留、 就地电子数据展示和保留、 合规性搜索、 就地存档、 审核和保留策略。例如，当邮箱置于诉讼保留，将保留第三方的数据。您可以通过使用就地电子数据展示或合规性搜索中搜索第三方数据。或可应用存档和保留策略与第三方数据像可用于 Microsoft 数据。简而言之，存档 Office 365 中的第三方数据可帮助组织保持符合政府和法规的策略。

Office 365 中归档提供证券交易委员会 （秒） 规则 17a 4 符合存储，并保留的所有数据的永久文件收集非改写、 非擦除格式使用就地保留策略和保留策略包括保留锁。特别是：
- 超出范围以外的普通的用户的专用的存储区中的保留存储使用上述的保留策略的所有记录。此外，仅限授权的用户可以访问和搜索这些记录，但不能改变或清除它们。
- 每个项目的元数据包括保留持续时间的计算中使用的时间戳。收到新项目时，将应用时间戳或创建和无法随后修改或删除从元数据。
- Office 365 中的存档允许用户将不同的保留策略和保留操作创建精细的保留策略，以定义要永久保留的类型或项目的位置和此类保留的持续时间。
- 保留锁定功能允许用户选择是否要使限制策略的策略。严格策略阻止任何人能够删除、 禁用或更改的保留策略。这意味着一旦启用保留锁，不能禁用它，而且没有机制将存在下的任何数据从现有的管理员已收集的保留策略就地可能会被覆盖，修改，擦除或删除期间保留期。此外，不是缩短或减小保留期设置保留锁。它，但是，可能加长，对于继续保留所述的存储数据的上述法律要求。保留锁确保没有人，甚至不管理员或具有某些控制他人的访问，可能更改的设置或覆盖或清除已存储的数据将存档在 Office 365 中嵌入到规定 2003年秒发行版中的指南规则 17a-4。

向客户更好地了解如何利用 Office 365 以满足其法规义务，特别是相对于规则 17a-4 要求，我们已发布介绍 Exchange Online Archiving，SharePoint Online 的 OneDrive[白皮书 （英文）](https://go.microsoft.com/fwlink/?linkid=830440)for Business 和 Skype 的业务。该白皮书还提供了 Office 365 存档功能并针对每个 SEC Rule 17a-4 下的所有要求的功能的深入分析，并向监管客户演示 Office 365 存档如何使用户能够满足这些要求。