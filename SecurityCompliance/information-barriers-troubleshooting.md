---
title: 信息障碍故障排除
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 05/31/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用本文作为对信息障碍进行故障排除的指导。
ms.openlocfilehash: b37585469ec8bb299b7976f8a330f4c6b29e3f95
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668277"
---
# <a name="troubleshooting-information-barriers-preview"></a>解决信息障碍 (预览)

信息障碍可帮助您的组织遵守法律要求和行业法规。 例如, 通过信息障碍, 可以限制特定用户组之间的通信, 以避免利益冲突或其他问题。 若要了解详细信息, 请参阅[信息障碍 (预览)](information-barriers.md)。

本文提供的指导可用于获取问题的答案或解决因信息障碍而可能遇到的问题。  

## <a name="before-you-begin"></a>开始之前 .。。

若要执行本文中所述的任务, 必须为您分配适当的角色, 如以下某项:
- Microsoft 365 企业全局管理员
- Office 365 全局管理员
- 合规性管理员
- IB 合规性管理 (这是一个新角色!)

若要了解有关角色和权限的详细信息, 请参阅[Office 365 Security & 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

若要了解有关信息障碍的先决条件方面的详细信息, 请参阅[先决条件 (适用于信息屏障策略)](information-barriers-policies.md#prerequisites)。

此外, 请确保[连接到 Office 365 安全 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

## <a name="issue-people-are-unexpectedly-blocked-from-communicating-in-microsoft-teams"></a>问题: 意外阻止用户在 Microsoft 团队中进行通信 

在这种情况下, 人们会报告在 Microsoft 团队中进行通信时遇到的意外问题。 示例：
- 用户无法在 Microsoft 团队中找到其他用户或与之通信。
- 用户无法在 Microsoft 团队中查看或选择其他用户。
- 用户可以查看, 但不能向 Microsoft 团队中的其他用户发送邮件。

### <a name="what-to-do"></a>需执行的操作

1. 确定用户是否受信息屏障策略的影响。 为此, 请使用**InformationBarrierRecipientStatus** Cmdlet 和 Identity 参数。 

    语法为`Get-InformationBarrierRecipientStatus -Identity`

    您可以使用任何标识值来唯一标识每个收件人, 如名称、别名、可分辨名称 (DN)、规范 DN、电子邮件地址或 GUID。

    示例：`Get-InformationBarrierRecipientStatus -Identity meganb`

    在此示例中, 我们使用 Identity 参数的别名 (*meganb*)。 此 cmdlet 将返回指示用户是否受信息屏障策略影响的信息。 (查找 * ExoPolicyId: \<GUID>。)

    如果用户未包含在信息屏障策略中, 请联系支持人员。 否则，继续执行下一步。

2. 了解信息屏障策略中包括的段落。 若要执行此操作, `Get-InformationBarrierPolicy`请将 Cmdlet 与 Identity 参数结合使用。 使用在上一步中收到的策略 GUID (ExoPolicyId) 等详细信息作为标识值。

    示例：`Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f`

    在此示例中, 我们将获取有关具有 ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*的信息屏障策略的详细信息。
    
    运行 cmdlet 后, 在 "结果" 中, 查找 " **AssignedSegment**"、" **SegmentsAllowed**" 和 " **SegmentsBlocked** " 值。

    示例: 运行`Get-InformationBarrierPolicy` cmdlet 后, 我们在结果列表中看到以下内容:

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    在这种情况下, 我们可以看到信息障碍策略会影响销售和研究领域中的人员。 在这种情况下, 将阻止 Sales 中的人员与 "调查" 中的人员进行通信。 如果看上去正确, 则信息障碍按预期工作。 如果不是, 请继续执行下一步。

4. 请确保正确定义了段。 为此, 请使用`Get-OrganizationSegment` cmdlet, 并查看结果列表。 

    若要查看特定段的详细信息, 请`Get-OrganizationSegment`将 Cmdlet 与 Identity 参数一起使用。 

    示例：`Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd`

    在此示例中, 我们将获取有关具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的段的信息。

    查看段的详细信息。 如有必要, 请[编辑段](information-barriers-policies.md#edit-a-segment), 然后重新使用`Start-InformationBarrierPoliciesApplication` cmdlet。

    如果您仍遇到信息障碍策略问题, 请联系支持人员。
    
## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>问题: 信息障碍应用程序进程花费的时间太长

运行**InformationBarrierPoliciesApplication** cmdlet 后, 该过程将花费很长时间才能完成。

### <a name="what-to-do"></a>需执行的操作

1. 请注意, 在运行策略应用程序 cmdlet 时, 将为组织中的所有帐户应用 (或删除) 用户的信息屏障策略。 如果有很多用户, 需要一段时间才能处理。 (一般原则是, 处理5000用户帐户需要大约一小时的时间。) 

2. 使用**InformationBarrierPoliciesApplicationStatus** cmdlet 验证状态。

    语法`Get-InformationBarrierPoliciesApplicationStatus`

    若要显示所有信息屏障策略应用程序的状态, 请使用`Get-InformationBarrierPoliciesApplicationStatus -All $true`

    这将显示有关策略应用程序是已完成、失败还是正在进行中的信息。。

3. 根据步骤2的结果, 执行以下步骤之一:

    - 如果应用程序尚未启动, 并且由于已运行**InformationBarrierPoliciesApplication** cmdlet, 则已超过45分钟, 请查看您的审核日志以查看策略定义中是否存在任何错误, 或其他原因。应用程序尚未启动。

    - 如果应用程序失败, 请查看您的段落和策略。 如有必要, 请[编辑分段](information-barriers-policies.md#edit-a-segment)和/或[编辑策略](information-barriers-policies.md#edit-a-policy), 然后再次运行**InformationBarrierPoliciesApplication** cmdlet。

    - 如果仍在运行应用程序, 请等待更多的时间完成。 如果已过几天, 请联系支持人员。

## <a name="related-topics"></a>相关主题

[为 Microsoft 团队中的信息障碍定义策略 (预览)](information-barriers-policies.md)

[信息障碍 (预览)](information-barriers.md)



