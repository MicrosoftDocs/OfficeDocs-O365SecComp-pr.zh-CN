---
title: Office 365 数据永久性
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 定义并解释数据永久性或必须可发现且无法销毁或更改的数据。
ms.openlocfilehash: d3f02a088ede557a1e7308182b2ec6e378cd418e
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004149"
---
# <a name="immutability-in-office-365"></a>Office 365 中的永久性
对于某些组织, 法规遵从性、内部治理要求或诉讼风险要求将电子邮件和相关数据保留在可检测到的表单中。 系统中的所有数据都必须是可检测到的, 且不能销毁或更改任何内容。 本行业标准术语是 "不可变性" 的。 

实现永久性的传统方法通常通过将电子邮件移动到单独的只读存储位置来工作。 虽然此类系统提供了保留邮箱项以供发现的目的, 但它们通常会通过从建议的日常工作流中删除保留的项目来显著地影响用户体验。 对于 IT 专业人员, 这种不需要的方法需要对单独的服务器和存储基础结构进行部署和日常维护。 发现本身是使用邮件系统外部的工具执行的, 并提供了相关的部署和维护成本。

通过在 office 365 中配置存档的就地保留和保留策略功能以及 office 365 套件中的服务 (如 Exchange online、SharePoint online、OneDrive for business 和 Skype for business),Office 365 中的存档可以保留和保留多个传入、内部和传出数据的类, 包括:
- 入站和出站电子邮件通信
- 包含在电子邮件表单或共享联机文档中的书籍和记录
- 会议请求
- 早
- 即时消息
- 联机会议期间共享的文档
- Voicemails

此外, Microsoft 还开发了附加功能, 通过与第三方数据捕获和管理解决方案集成, 允许从其他来源[存档数据](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc)。 导入第三方数据后, 可以将 Office 365 合规性功能应用于数据, 包括诉讼保留、就地电子数据展示和保留、合规性搜索、就地存档、审核和保留策略。 例如，当将邮箱置于诉讼保留时，将保留第三方数据。 您可以通过使用就地电子数据展示或合规性搜索来搜索第三方数据。 或者，您可以将存档和保留策略应用于第三方数据，就像可以应用于 Microsoft 数据那样。 简言之, 在 Office 365 中存档第三方数据可帮助您的组织遵守政府和法规策略。

Office 365 中的存档提供有价证券和 Exchange 委员会 (SEC) 规则17a-4 合规性存储, 并保留使用就地保留策略和保留策略以不可改写、不可擦除的格式收集的所有数据的永久文件, 包括保留锁定。 具体来说：
- 使用上面所述的保留策略存储的所有记录都保留在 purview 的专用存储区域中, 而不是普通用户的。 此外, 只有授权用户可以访问和搜索这些记录, 但不能更改或清除它们。
- 每个项目的元数据包括用于计算保留期的时间戳。 在收到或创建新项目且无法随后修改或删除元数据时, 应用时间戳。
- Office 365 中的存档允许用户将不同的保留策略和保留操作组合在一起, 以创建精确的保留策略, 以定义要并永久保留的项目的类型或位置以及此类保留的持续时间。
- 保留锁定功能允许用户选择是否要使策略成为限制性策略。 限制性策略禁止任何人能够删除、禁用或对保留策略进行任何更改。 这意味着一旦启用保留锁定, 则它将无法禁用, 并且在此过程中, 保留策略所收集的来自现有保管人的任何数据可能会被覆盖、修改、删除或删除 (在保留期。 此外, 保留锁设置的保留期可能不会缩短或减少。 但是, 如果法律要求继续保留所存储的数据, 则可能会延长此时间, 如上文所述。 保留锁定可确保任何人 (甚至不是管理员或具有特定控制访问权限的管理员) 都可能会更改设置或覆盖或擦除已存储的数据, 从而使 Office 365 中的存档与 SEC 2003 版本中提出的指导相结合规则17a-4。

向客户更好地了解如何利用 Office 365 来满足其法规义务 (尤其是与规则17a-4 要求相关), 我们发布了一个[白皮书](https://go.microsoft.com/fwlink/?linkid=830440), 其中包含 Exchange online 存档、SharePoint online、OneDrive商业版和 Skype for business。 该白皮书还提供了对 office 365 存档功能和功能的深入分析, 以根据 SEC Rule 17a-4 中的每个要求, 向管控客户演示 office 365 存档如何使他们能够满足这些要求满足.