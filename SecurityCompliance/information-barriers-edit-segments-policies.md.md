---
title: 编辑信息屏障策略
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
description: 了解如何编辑或删除信息障碍策略。
ms.openlocfilehash: c55ffac0984fe83fec1ef7b995d1589ea770bfef
ms.sourcegitcommit: a6f046f1529b0515f4f0e918a19ec83f4138b871
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2019
ms.locfileid: "35587071"
---
# <a name="edit-or-remove-information-barrier-policies"></a>编辑 (或删除) 信息屏障策略

[定义信息障碍策略](information-barriers-policies.md)后, 您可能需要对这些策略或用户区段进行更改, 作为[故障排除](information-barriers-troubleshooting.md)或定期维护的一部分。 将本文用作指南。

## <a name="what-do-you-want-to-do"></a>要执行什么操作？

|操作  |说明 |
|---------|---------|
|[编辑用户帐户属性](#edit-user-account-attributes)     |填写可用于定义段的 Azure Active Directory 中的属性。<br/>当用户不包含在应使用的分段中时编辑用户帐户属性, 以更改用户所在的分段, 或使用不同的属性定义分段。         |
|[编辑段](#edit-a-segment)     |当您想要更改分段定义的方式时编辑线段。 <br/>例如, 您可能已使用*部门*最初定义了分段, 现在想要使用另一个属性, 如*MemberOf*。         |
|[编辑策略](#edit-a-policy)     |当您想要更改策略的工作方式时, 请编辑信息障碍策略。<br/>例如, 您可能会决定只允许在某些网段之间进行通信, 而无需阻止两个网段之间的通信。         |
|[将策略设置为非活动状态](#set-a-policy-to-inactive-status)     |如果要对策略进行更改, 或不希望策略生效, 请将策略设置为非活动状态。         |
|[删除策略](#remove-a-policy)     |当不再需要特定策略时, 请删除信息障碍策略。         |
|[停止策略应用程序](#stop-a-policy-application)     |如果要停止应用信息屏障策略的过程, 请执行此操作。<br/>请注意, 停止策略应用程序不是即时的, 并且不会撤消已应用于用户的策略。         |
|[定义信息障碍策略](information-barriers-policies.md)     |如果不存在此类策略, 请定义信息屏障策略, 并且必须限制或限制特定用户组之间的通信。         |
|[信息障碍故障排除](information-barriers-troubleshooting.md)     |遇到信息障碍遇到意外问题时, 请参阅本文。         |

> [!IMPORTANT]
> 若要执行本文中所述的任务, 必须为您分配适当的角色, 如以下某项:<br/>-Microsoft 365 企业全局管理员<br/>-Office 365 全局管理员<br/>-合规性管理员<br/>-IB 合规性管理 (这是一个新角色!)<p>若要了解有关信息障碍的先决条件方面的详细信息, 请参阅[先决条件 (适用于信息屏障策略)](information-barriers-policies.md#prerequisites)。<p>请确保[连接到 Office 365 安全 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

## <a name="edit-user-account-attributes"></a>编辑用户帐户属性

使用此过程可编辑用于分段用户的属性。 

例如, 如果您使用的是部门属性, 并且一个或多个用户帐户当前没有为部门列出任何值, 则必须编辑这些用户帐户以包含部门信息。 

用户帐户属性用于定义段, 以便可以分配信息障碍策略。

1. 若要查看特定用户帐户的详细信息 (如属性值和分配的段), 请使用带有 Identity 参数的**InformationBarrierRecipientStatus** cmdlet。 

    |语法  |示例  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>   您可以使用任何唯一标识每个用户的值, 如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。 <p>   (也可以将此 cmdlet 用于单个用户: `Get-InformationBarrierRecipientStatus -Identity <value>`)      |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`  <p>   在此示例中, 我们引用 Office 365 中的两个用户帐户: *meganb* for *Megan*和*alexw* for *Alex*。         |

2. 为您的用户帐户配置文件确定要编辑的属性。 有关详细信息, 请参阅[信息障碍策略的属性](information-barriers-attributes.md)。 

3. 编辑一个或多个用户帐户, 以包含您在上一步中选择的属性的值。 为此, 请使用以下过程之一:

    - 若要编辑单个帐户, 请参阅[使用 Azure Active Directory 添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。

    - 若要编辑多个帐户 (或使用 PowerShell 编辑单个帐户), 请参阅[Configure user account properties With Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)。

## <a name="edit-a-segment"></a>编辑段

使用此过程可编辑用户区段的定义。 例如, 您可以更改段的名称, 或使用用于确定字段中所包含的用户的筛选器。

1. 若要查看所有现有段, 请使用**OrganizationSegment** cmdlet。
    
    语法`Get-OrganizationSegment`

    你将看到每个段的列表和详细信息, 如段类型、其 UserGroupFilter 值、创建日期或上次修改时间、GUID 等。

    > [!TIP]
    > 打印或保存段列表以便日后参考。 例如, 如果您想要编辑某一段, 则需要知道它的名称或标识值 (这与 Identity 参数一起使用)。

2. 若要编辑分段, 请使用**OrganizationSegment** Cmdlet 和**Identity**参数以及相关详细信息。 

    |语法  |示例  |
    |---------|---------|
    |`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`     |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p>在此示例中, 对于具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的段, 我们将部门名称更新为 "HRDept"。         |

为组织编辑完段后, 可以[定义](information-barriers-policies.md#part-2-define-information-barrier-policies)或[编辑](#edit-a-policy)信息障碍策略。

## <a name="edit-a-policy"></a>编辑策略

1. 若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。

    语法`Get-InformationBarrierPolicy`

    在结果列表中, 标识要更改的策略。 记下策略的 GUID 和名称。

2. 将**InformationBarrierPolicy** Cmdlet 与**Identity**参数一起使用, 并指定要进行的更改。

    示例: 假设定义了一个策略来阻止与*销售*和*市场营销*部门通信的*研究*分段。 该策略是使用以下 cmdlet 定义的:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`
    
    假设我们要对其进行更改, 以便*研究*部门中的人员只能与*HR*部门中的人员进行通信。 若要进行此更改, 我们使用以下 cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    在此示例中, 我们将 "SegmentsBlocked" 更改为 "SegmentsAllowed", 并指定*HR*段。

3. 完成策略的编辑后, 请确保应用所做的更改。 (请参阅[Apply 信息屏障策略](information-barriers-policies.md#part-3-apply-information-barrier-policies)。)

## <a name="set-a-policy-to-inactive-status"></a>将策略设置为非活动状态

1. 若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。

    语法`Get-InformationBarrierPolicy`

    在结果列表中, 标识要更改 (或删除) 的策略。 记下策略的 GUID 和名称。

2. 若要将策略的状态设置为 "非活动", 请使用带有 Identity 参数的**InformationBarrierPolicy** cmdlet, 将 State 参数设置为 "非活动"。

    |语法  |示例  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Inactive`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p>在此示例中, 我们将具有 GUID *43c37853-ea10-4b90-a23d-ab8c9377247*的信息屏障策略设置为非活动状态。         |

3. 若要应用所做的更改, 请使用**InformationBarrierPoliciesApplication** cmdlet。

    语法`Start-InformationBarrierPoliciesApplication`

    为您的组织应用更改的用户。 如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。 (一般原则是, 处理5000用户帐户需要大约一小时的时间。)

在这种情况下, 一个或多个信息障碍策略将设置为非活动状态。 在这里, 您可以执行以下任一操作:
- 将其保留为 (策略设置为非活动状态对用户没有影响)
- [编辑策略](#edit-a-policy) 
- [删除策略](#remove-a-policy)

## <a name="remove-a-policy"></a>删除策略

1. 若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。

    语法`Get-InformationBarrierPolicy`

    在结果列表中, 标识要删除的策略。 记下策略的 GUID 和名称。 请确保将策略设置为非活动状态。

2. 将**InformationBarrierPolicy** Cmdlet 与 Identity 参数一起使用。

    |语法  |示例  |
    |---------|---------|
    |`Remove-InformationBarrierPolicy -Identity GUID`     |`Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p>在此示例中, 我们将删除 GUID 为*43c37853-ea10-4b90-a23d-ab8c93772471*的策略。          |

    出现提示时, 请确认更改。

3. 对要删除的每个策略重复步骤1-2。

4. 删除完策略后, 应用所做的更改。 为此, 请使用**InformationBarrierPoliciesApplication** cmdlet。

    语法`Start-InformationBarrierPoliciesApplication`

    为您的组织应用更改的用户。 如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。

## <a name="stop-a-policy-application"></a>停止策略应用程序

如果在您开始应用信息屏障策略后, 您想要停止应用这些策略, 请使用以下过程。 请注意, 此过程将需要大约30-35 分钟才能开始。

1. 若要查看最新信息屏障策略应用程序的状态, 请使用**InformationBarrierPoliciesApplicationStatus** cmdlet。

    语法`Get-InformationBarrierPoliciesApplicationStatus`

    记下应用程序的 GUID。

2. 将**InformationBarrierPoliciesApplication** Cmdlet 与 Identity 参数一起使用。

    |语法  |示例  |
    |---------|---------|
    |`Stop-InformationBarrierPoliciesApplication -Identity GUID`     |`Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p>在此示例中, 我们将停止应用信息屏障策略。         |

## <a name="related-articles"></a>相关文章

[获取信息障碍概述](information-barriers.md)

[定义信息障碍策略](information-barriers-policies.md)

[了解有关 Microsoft 团队中的信息障碍的详细信息](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[信息屏障策略的属性](information-barriers-attributes.md)

[信息障碍故障排除](information-barriers-troubleshooting.md)
