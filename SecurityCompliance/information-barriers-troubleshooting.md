---
title: 信息障碍故障排除
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 使用本文作为对信息障碍进行故障排除的指导。
ms.openlocfilehash: 251fc1775318e2ed7cbda9a56e2c82db527082f6
ms.sourcegitcommit: a6f046f1529b0515f4f0e918a19ec83f4138b871
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2019
ms.locfileid: "35587051"
---
# <a name="troubleshooting-information-barriers"></a>信息障碍故障排除

[信息障碍](information-barriers.md)可帮助您的组织遵守法律要求和行业法规。 例如, 通过信息障碍, 可以限制特定用户组之间的通信, 以避免利益冲突或其他问题。 (若要了解有关如何设置信息屏障的详细信息, 请参阅[定义信息障碍策略](information-barriers-policies.md)。)

如果用户在发生信息障碍后遇到意外问题, 则可以采取一些步骤来解决这些问题。 将本文用作指南。

> [!IMPORTANT]
> 若要执行本文中所述的任务, 必须为您分配适当的角色, 如以下某项:<br/>-Microsoft 365 企业全局管理员<br/>-Office 365 全局管理员<br/>-合规性管理员<br/>-IB 合规性管理 (这是一个新角色!)<p>若要了解有关信息障碍的先决条件方面的详细信息, 请参阅[先决条件 (适用于信息屏障策略)](information-barriers-policies.md#prerequisites)。<p>请确保[连接到 Office 365 安全 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>问题: 意外阻止用户与 Microsoft 团队中的其他人通信 

在这种情况下, 用户将报告与 Microsoft 团队中的其他人通信的意外问题。 示例：
- 用户在 Microsoft 团队中搜索, 但找不到另一个用户。
- 用户可以在 Microsoft 团队中查找其他用户, 但不能选择。
- 用户可以查看其他用户, 但不能向 Microsoft 团队中的其他用户发送邮件。

### <a name="what-to-do"></a>需执行的操作

确定用户是否受信息屏障策略的影响。 根据策略的配置方式, 信息障碍可能按预期工作。 或者, 您可能必须优化组织的策略。

1. 将**InformationBarrierRecipientStatus** Cmdlet 与 Identity 参数一起使用。 

    |语法  |示例  |
    |---------|---------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p>您可以使用任何标识值来唯一标识每个收件人, 如名称、别名、可分辨名称 (DN)、规范 DN、电子邮件地址或 GUID。     |`Get-InformationBarrierRecipientStatus -Identity meganb` <p>在此示例中, 我们使用 Identity 参数的别名 (*meganb*)。 此 cmdlet 将返回指示用户是否受信息屏障策略影响的信息。 (查找 * ExoPolicyId: \<GUID>。)         |

    **如果用户未包含在信息屏障策略中, 请联系支持人员**。 否则，继续执行下一步。

2. 了解信息屏障策略中包括的段落。 若要执行此操作, `Get-InformationBarrierPolicy`请将 Cmdlet 与 Identity 参数结合使用。 

    |语法  |示例  |
    |---------|---------|
    |`Get-InformationBarrierPolicy` <p>使用在上一步中收到的策略 GUID (ExoPolicyId) 等详细信息作为标识值。     | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p>在此示例中, 我们将获取有关具有 ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*的信息屏障策略的详细信息。         |

    运行 cmdlet 后, 在 "结果" 中, 查找 " **AssignedSegment**"、" **SegmentsAllowed**" 和 " **SegmentsBlocked** " 值。

    例如, 运行`Get-InformationBarrierPolicy` cmdlet 后, 我们在结果列表中看到以下内容:

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    在这种情况下, 我们可以看到信息障碍策略会影响销售和研究领域中的人员。 在这种情况下, 将阻止 Sales 中的人员与 "调查" 中的人员进行通信。 
    
    如果看上去正确, 则信息障碍按预期工作。 如果不是, 请继续执行下一步。

4. 请确保正确定义了段。 为此, 请使用`Get-OrganizationSegment` cmdlet, 并查看结果列表。 

    |语法  |示例  |
    |---------|---------|
    |`Get-OrganizationSegment`<p>将此 cmdlet 与 Identity 参数一起使用。     |`Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p>在此示例中, 我们将获取有关具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的段的信息。         |

    查看段的详细信息。 如有必要, 请[编辑段](information-barriers-edit-segments-policies.md.md#edit-a-segment), 然后重新使用`Start-InformationBarrierPoliciesApplication` cmdlet。

    **如果您仍遇到信息障碍策略问题, 请联系支持人员**。

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>问题: 允许在 Microsoft 团队中阻止的用户之间进行通信

在这种情况下, 尽管信息障碍已定义、活动和应用, 但应阻止相互通信的人员能够在 Microsoft 团队中相互聊天和呼叫。

### <a name="what-to-do"></a>需执行的操作

验证相关用户是否包含在信息屏障策略中。 

1. 使用具有 Identity 参数的**InformationBarrierRecipientStatus** cmdlet。

    |语法  |示例  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>您可以使用任何唯一标识每个用户的值, 如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>在此示例中, 我们引用 Office 365 中的两个用户帐户: *meganb* for *Megan*和*alexw* for *Alex*。          |

    
    > [!TIP]
    > 您还可以将此 cmdlet 用于单个用户:`Get-InformationBarrierRecipientStatus -Identity <value>`
    
2. 查看发现。 **InformationBarrierRecipientStatus** cmdlet 返回有关用户的信息, 如属性值和应用的任何信息障碍策略。 

    查看结果, 然后执行下一步, 如下表所述:
    
    |结果  |下一步操作  |
    |---------|---------|
    |未列出所选用户的任何段     |执行下列操作之一：<br/>-通过在 Azure Active Directory 中编辑用户配置文件, 将用户分配到现有分段。 (请参阅[Configure user account properties With Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)。)<br/>-使用[受支持的信息障碍属性](information-barriers-attributes.md)定义段。 然后,[定义新策略](information-barriers-policies.md#part-2-define-information-barrier-policies)或[编辑现有策略](information-barriers-edit-segments-policies.md.md#edit-a-policy)以包含该分段。  |
    |列出了分段, 但没有为这些分段分配信息障碍策略     |执行下列操作之一：<br/>- 为问题的每个段[定义新的信息障碍策略](information-barriers-policies.md#part-2-define-information-barrier-policies)<br/>- [编辑现有的信息屏障策略](information-barriers-edit-segments-policies.md.md#edit-a-policy)以将其分配给正确的段         |
    |列出了分段, 每个段都包含在信息屏障策略中     |-运行`Get-InformationBarrierPolicy` cmdlet 以验证信息屏障策略是否处于活动状态<br/>-运行`Get-InformationBarrierPoliciesApplicationStatus` cmdlet 以确认应用了策略<br/>-运行`Start-InformationBarrierPoliciesApplication` cmdlet 以应用所有活动信息屏障策略          |
    

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>问题: 我需要从信息屏障策略中删除一个用户

在这种情况下, 信息屏障策略生效, 并且意外阻止了一个或多个用户与 Microsoft 团队中的其他用户通信。 您可以从信息屏障策略中删除一个或多个单个用户, 而无需完全删除信息障碍策略。 

### <a name="what-to-do"></a>需执行的操作

信息屏障策略被分配给用户的各个部分。 分段是通过使用[用户帐户配置文件中](information-barriers-attributes.md)的某些属性来定义的。 如果必须从单个用户中删除策略, 请考虑在 Azure Active Directory 中编辑该用户的配置文件, 以使该用户不再包含在受信息障碍影响的段中。

1. 使用具有 Identity 参数的**InformationBarrierRecipientStatus** cmdlet。 此 cmdlet 返回有关用户的信息, 如属性值和应用的任何信息障碍策略。

    |语法  |示例  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`<p>您可以使用任何唯一标识每个用户的值, 如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>在此示例中, 我们引用 Office 365 中的两个用户帐户: *meganb* for *Megan*和*alexw* for *Alex*。          |
    |`Get-InformationBarrierRecipientStatus -Identity <value>` <p>您可以使用任何能够唯一标识用户的值, 如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p>在此示例中, 我们引用 Office 365: *jeanp*中的单个帐户。 |

2. 查看结果以查看是否分配了信息屏障策略, 以及用户属于哪些网段。 

3. 若要从受信息障碍影响的段中删除用户, 请[在 Azure Active Directory 中更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。

4. 大约等待30分钟, FwdSync 才会发生。 或者, 运行`Start-InformationBarrierPoliciesApplication` cmdlet 以应用所有活动的信息屏障策略。

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>问题: 信息障碍应用程序进程花费的时间太长

运行**InformationBarrierPoliciesApplication** cmdlet 后, 该过程将花费很长时间才能完成。

### <a name="what-to-do"></a>需执行的操作

请注意, 在运行策略应用程序 cmdlet 时, 将为组织中的所有帐户应用 (或删除) 用户的信息屏障策略。 如果有很多用户, 需要一段时间才能处理。 (一般原则是, 处理5000用户帐户需要大约一小时的时间。)

1. 使用**InformationBarrierPoliciesApplicationStatus** cmdlet 验证最近策略应用程序的状态。

    |查看最新的策略应用程序  |查看所有策略应用程序的状态  |
    |---------|---------|
    |`Get-InformationBarrierPoliciesApplicationStatus`     |`Get-InformationBarrierPoliciesApplicationStatus -All $true`         |


    这将显示有关策略应用程序是已完成、失败还是正在进行的信息。

2. 根据上一步的结果, 执行下列步骤之一:
  
    |状态  |后续步骤  |
    |---------|---------|
    |**未启动**     |如果自运行**InformationBarrierPoliciesApplication** cmdlet 后, 它已超过45分钟, 请查看您的审核日志, 以确定策略定义中是否存在任何错误, 或者应用程序尚未启动的其他原因。 |
    |**失败**     |如果应用程序失败, 请查看您的审核日志。 此外, 还应查看你的段落和策略。 是否有任何用户分配到多个段？ 是否为任何段分配了多个 poliicy？ 如有必要, 请[编辑分段](information-barriers-edit-segments-policies.md.md#edit-a-segment)和/或[编辑策略](information-barriers-edit-segments-policies.md.md#edit-a-policy), 然后再次运行**InformationBarrierPoliciesApplication** cmdlet。  |
    |**进行中**     |如果仍在运行应用程序, 请等待更多的时间完成。 如果是几天, 请收集你的审核日志, 然后与支持人员联系。 |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>问题: 根本不应用信息屏障策略

在这种情况下, 您已定义了分段, 定义了信息屏障策略, 并试图应用这些策略。 但是, 在运行`Get-InformationBarrierPoliciesApplicationStatus` cmdlet 时, 可以看到策略应用程序已失败。

### <a name="what-to-do"></a>需执行的操作

请确保您的组织没有适当的[Exchange 通讯簿策略](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies)。 此类策略将阻止应用信息障碍策略。

1. 连接到 [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。 

2. 运行[AddressBookPolicy](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/get-addressbookpolicy?view=exchange-ps) cmdlet, 并查看结果。

    |结果  |后续步骤  |
    |---------|---------|
    |Exchange 通讯簿策略列出     |[删除通讯簿策略](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy)         |
    |不存在通讯簿策略 |查看您的审核日志以找出策略应用程序失败的原因 |

3. [查看用户帐户、段、策略或策略应用程序的状态](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)。

## <a name="related-topics"></a>相关主题

[在 Microsoft 团队中定义信息障碍策略](information-barriers-policies.md)

[信息障碍](information-barriers.md)



