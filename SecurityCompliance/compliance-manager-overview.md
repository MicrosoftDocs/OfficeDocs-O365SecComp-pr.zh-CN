---
title: Microsoft 合规性管理器概述
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 合规性管理器是 Microsoft 服务信任门户中基于工作流的免费风险评估工具。 合规性管理器使你能够跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。
ms.openlocfilehash: e7c8afd3a9b2e0514e0df7df0f10871b0a7ca329
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155284"
---
# <a name="microsoft-compliance-manager-preview"></a>Microsoft 合规性管理器 (预览)

> [!IMPORTANT]
> 由世纪互联运营的 Office 365、Office 365 Germany、Office 365 U.S. Government Community High (GCC High) 或 Office 365 Department of Defense 不提供合规性管理器。

[Microsoft 合规性管理器 (预览版)](https://servicetrust.microsoft.com/ComplianceManager)是一个基于工作流的免费风险评估工具, 可让您跟踪、分配和验证与 Microsoft 云服务相关的法规遵从性活动。 您的 Microsoft 365、Office 365 或 Azure Active Directory 订阅的一部分, 合规性管理器可帮助您管理 Microsoft 云服务的共享职责模型中的法规遵从性。 合规性管理器提供了一个集中的仪表板, 用于查看 Microsoft service 评估的标准、法规和控制实施详细信息和测试结果。 它还包括允许您管理特定于您的组织的自定义控件实现和合规性跟踪的工具。

使用合规性管理器, 您的组织可以:
  
- 结合了 Microsoft 为审计员和管理机构提供的详细合规性信息, 以及有关适用于您的组织的标准和规章的合规性自我评估的云服务。 其中包括国际标准化组织 (ISO)、美国国家标准和技术协会 (NIST)、健康保险便携性和责任法案 (HIPAA) 中列出的标准和法规 (常规数据)保护规章 (GDPR) 和其他许多。
- 使您能够分配、跟踪和记录符合性和与评估相关的活动, 这些活动可帮助您的组织跨团队障碍实现合规性目标。
- 提供符合性分数以帮助您跟踪进度并设置审核控件的优先级, 以帮助减少组织对风险的暴露程度。
- 为您提供一个安全存储库, 以便上载和管理与合规性活动相关的证据和其他项目。
- 生成详尽的 Microsoft Excel 报告, 这些报告记录由 Microsoft 和您的组织为审计员、管理机构和其他合规性审阅者执行的合规性活动。

> [!NOTE]
> 合规性管理器中提供的客户操作是建议;在实现之前, 你的组织可以评估这些建议在其各自的法规环境中的有效性。 在合规性管理器中找到的建议不应解释为合规性保证。

## <a name="compliance-manager-relationships"></a>合规性管理器关系

合规性管理器使用多个组件可帮助你实现合规性管理活动。 这些组件协同工作, 为审计员提供完整的管理工作流和无障碍的合规性报告。

图中显示了合规性管理器的主要组件之间的关系:

![合规性管理器版本3中的关系](media/compliance-manager-relationships.png)

## <a name="groups"></a>组

[组](https://docs.microsoft.com/office365/securitycompliance/working-with-compliance-manager#groups)是允许您组织评估的容器, 并在评估之间共享具有相同或相关的客户托管控件的常见信息和工作流任务。 当同一个组中的两个不同评估共享客户托管控件时, 该控件的实现详细信息、测试和状态的完成将自动同步到组中任何其他评估中的相同控件。 这将为组中的每个控件统一分配的操作项, 并减少重复工作。 您还可以选择使用组进行组织。 按年、区域、合规性标准或其他分组进行评估, 以帮助组织合规性工作。

## <a name="assessments"></a>评估

[评估](https://docs.microsoft.com/office365/securitycompliance/working-with-compliance-manager#assessments)是容器, 允许您根据在 Microsoft 和组织之间共享的职责来组织控制, 以评估云服务安全性和合规性风险。 评估可帮助您实施由合规性标准和适用的数据保护标准、法规或法律指定的数据保护安全措施。 它们可帮助您针对选定 Microsoft 云服务的所选行业标准来辨别您的数据保护和合规性状况。 评估通过在与证书标准对应的评估中包含的控制实施完成。

默认情况下, 合规性管理器将为您的组织创建以下评估:

- Office 365 ISO 27001
- Office 365 NIST 800-53
- Office 365 GDPR

评估包括以下几个组件:
  
- **范围内的服务**: 每个评估适用于一组特定的 Microsoft 服务。
- **Microsoft 托管控件**: 对于每个云服务, microsoft 实施并管理一组适用标准和管理法规的合规性控制。
- **客户管理的控件**: 这是您对每个控件执行操作时由您的组织实现的控件的集合。
- **评估分数**: 评估中客户管理的控件的总可能分数的百分比。 这可帮助您跟踪分配给每个控件的操作的实现。

## <a name="controls"></a>控件

[控件](https://docs.microsoft.com/office365/securitycompliance/working-with-compliance-manager#controls-and-actions)是合规性管理器中的合规性流程容器, 用于定义管理合规性活动的方式。 这些控制措施被组织为与相应证书或法规的评估结构一致的控制系列。

- **控件 ID**: 所选控件在相应的证书或法规中的名称。
- **控件标题**: 来自相应的证书或法规的控件 ID 的标题。
- **文章 ID**: 此字段仅用于 GDPR 评估, 并指定相应的 GDPR 文章编号。
- **说明**: 来自相应证书或法规的控制文本。 由于版权限制, 针对 ISO 标准列出了相关信息的链接。

![合规性管理器版本3中的控件](media/compliance-manager-controls.png)

合规性管理器、 **Microsoft 托管控件**、**客户托管控件**和**共享管理控件**中有三种类型的控件

### <a name="microsoft-managed-controls"></a>Microsoft 托管控件

对于每个云服务, Microsoft 实施并管理一组控件作为 Microsoft 符合各种标准和法规的一部分。 每个控件都提供了有关 Microsoft 如何实现控件的详细信息, 以及 Microsoft 和/或独立第三方审计员对该实施进行测试和验证的方式和时间的详细信息。

### <a name="customer-managed-controls"></a>客户管理的控件

这是由您的组织管理的控件的集合。 您的组织负责客户托管的控制实施, 作为给定标准或法规的合规性流程的一部分。 将客户管理的控件组织为相应的证书或法规的控制系列。 使用客户托管的控件来实施 Microsoft 建议的建议操作, 作为合规性活动的一部分。 您的组织可以使用每个客户托管控件中的规范性指南和建议的客户操作来管理该控件的实施和评估过程。

评估中的客户管理的控件还具有内置工作流管理功能, 可用于管理和跟踪评估完成的进展情况。 使用此工作流功能, 可以执行以下操作:

- 为每个控件分配操作项
- 跟踪分配的交办事项
- 上载控件实现的证据
- 记录控件的测试和验证
- 将操作项标记为已实现和已测试

例如, 贵组织中的合规性监察官将操作项分配给 IT 管理员, 并具有执行建议操作所需的责任和必要权限。 IT 管理员上载实施任务的证据 (配置或策略设置的屏幕截图), 并在完成后将措施项分配回合规专员。 合规性监察官评估收集的证据, 测试控件的实现, 并在合规性管理器中记录实施日期和测试结果。

### <a name="shared-management-controls"></a>共享管理控件

共享控件指的是 Microsoft 和客户共同承担实施责任的任何控制。 例如, 与人员屏蔽、帐户和密码管理以及加密相关的控件都需要由 Microsoft 和客户执行操作。

## <a name="action-items"></a>拟办事项

[操作项](https://docs.microsoft.com/office365/securitycompliance/working-with-compliance-manager#controls-and-actions)以内置工作流管理功能的一部分的形式包含在客户托管的控件中, 可用于管理和跟踪评估完成的进展情况。

组织中的人员可以使用合规性管理器从其分配的所有评估中查看客户托管的控件。 当用户登录合规性管理器并打开 "**交办事项**" 仪表板时, 将显示分配给它们的操作项的列表。 根据为用户分配的合规性管理器角色, 他们可以提供实施或测试详细信息、更新状态或分配操作项。

证书控制通常由一个人实施, 并由另一个人测试。 例如, 在最初分配给一个人实现实施的操作项目完成后, 会将措施项分配给下一个要测试和上载证据的人员。 对控制分配具有足够权限的任何用户都可以分配和重新分配操作项目。 这样可以集中管理控制分配以及 implementors 和测试人员之间的操作项目的分散路由。

## <a name="permissions"></a>权限

合规性管理器使用基于角色的访问控制[权限模型](https://docs.microsoft.com/office365/securitycompliance/working-with-compliance-manager#permissions)。 默认情况下, 使用 Azure Active Directory (Azure AD) 帐户的组织中的所有人都具有完全访问权限, 并且可以在合规性管理器中执行任何操作。 在组织实施了基于角色的访问控制后, 任何未分配到已定义合规性管理器角色的用户都将被分配来宾访问权限。 Microsoft 服务人员不具有对您输入或上载的任何数据的访问权限。

若要更改默认权限并实现完全基于角色的访问控制模型, 必须至少将一个用户添加到每个合规性管理器角色。 将用户添加到角色后, 执行分配给该角色的操作的权限将从对所有用户可用的默认权限集删除。 只有使用该角色设置的用户才能访问合规性管理器并执行该角色允许的操作。

例如, 如果将用户添加到管理评估的角色中, 则只有该角色的成员可以管理评估。 如果不将用户添加到允许用户读取评估中的数据的角色, 则组织中的所有用户都可以访问合规性管理器并读取任何评估中的数据。
  
## <a name="manage-evidence"></a>管理证据

合规性管理器可以存储实施任务的证据, 以执行客户托管控件的测试和验证。 证据包括文档、电子表格、屏幕截图、图像、脚本、脚本输出文件和其他文件。 合规性管理器还会自动接收遥测并为与安全得分集成的措施项创建证据记录。 作为证据上传到合规性管理器中的任何数据均存储在 Microsoft 云存储站点上的美国。 此数据在位于东南亚和西欧的 Azure 区域之间复制。

## <a name="templates"></a>模板

合规性管理器为评估提供预先配置的[模板](https://docs.microsoft.com/office365/securitycompliance/working-with-compliance-manager#templates), 并允许您为客户托管的控件创建自定义模板, 以满足您的合规性需求。 新模板是通过导入 Excel 文件中的控件信息来创建的, 也可以通过现有模板的副本创建模板。

合规性管理器附带的预配置模板为:
 
- [ISO 27001:2013](https://www.iso.org/obp/ui/#iso:std:iso-iec:27001:ed-2:v1:en)
- [ISO 27018:2019](https://www.iso.org/obp/ui/#iso:std:iso-iec:27018:ed-2:v1:en)
- [NIST 800-53](https://csrc.nist.gov/publications/detail/sp/800-53/rev-4/final)
- [NIST 800-171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)
- [NIST Cybersecurity Framework (CSF)](https://www.nist.gov/cyberframework)
- [云安全联盟 (CSA) 云控制矩阵 (CCM) 3.0。1](https://cloudsecurityalliance.org/working-groups/cloud-controls-matrix/#_overview)
- [联邦金融机构检查委员会 (FFIEC) 信息安全手册](https://ithandbook.ffiec.gov/it-booklets/information-security.aspx) 
- [HIPAA](https://www.hhs.gov/hipaa/for-professionals/index.html) / 高[科技](https://www.hhs.gov/hipaa/for-professionals/special-topics/hitech-act-enforcement-interim-final-rule/index.html)
- [FedRAMP 中等](https://www.fedramp.gov/documents/)
- [欧洲联合 GDPR](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=CELEX:32016R0679&from=EN)

## <a name="compliance-score"></a>合规性分数

[合规性分数](compliance-score-methodology.md)是合规性管理器的核心组件, 可帮助您的组织了解和管理合规性。 与[Microsoft 安全分数](microsoft-secure-score.md)一样, 合规性分数是基于行为的计分系统, 用于实现与组织中的数据保护、隐私和安全性相关的活动。 评估的合规性分数是符合给定标准或法规的表达式。 数值分数越高, 评估的合规性状况越好。 了解合规性评分方法对于确定必需的客户托管控制操作的优先级至关重要。
  
> [!IMPORTANT]
> 合规性分数并不是组织遵守任何特定标准或法规情况的绝对度量。它表示执行控制措施的程度，这些控制措施可降低个人数据和个人隐私面临的风险。任何服务都无法保证遵守标准或法规，不得以任何方式将合规性分数解读为保证。

## <a name="secure-score-integration"></a>安全分数集成

合规性管理器与[Microsoft 安全分数](microsoft-secure-score.md)集成, 以自动对同步交办事项的合规性分数应用安全分数积分。 可以对单个操作项进行配置, 并在各项之间进行连续更新。

例如, 您对在组织中激活 Azure 权限管理 (也适用于与合规性相关的措施项) 进行安全相关的要求。 当 Azure 权限管理激活并由安全得分处理时, 合规性管理器将接收更新通知, 并通过完成信用自动更新措施项的分数。

## <a name="ready-to-get-started"></a>准备好开始了吗？

开始[使用合规性管理器](working-with-compliance-manager.md)来管理组织的法规遵从性活动。

## <a name="resources"></a>资源

- [交互式指南: 使用合规性管理器评估和增强数据保护控制](https://content.cloudguides.com/guides/Compliance%20Manager)
- [Microsoft 安全、隐私和合规性技术社区](https://techcommunity.microsoft.com/t5/Security-Privacy-Compliance/ct-p/SecurityPrivacyCompliance)
