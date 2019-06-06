---
title: 定义信息屏障策略
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
description: 了解如何在 Microsoft 团队中定义信息障碍策略。
ms.openlocfilehash: 3ec9d89f22456f00104135013ee6009e8e4824df
ms.sourcegitcommit: 4fedeb06a6e7796096fc6279cfb091c7b89d484d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "34668278"
---
# <a name="define-policies-for-information-barriers-preview"></a>定义信息障碍策略 (预览)

通过信息障碍, 您可以定义旨在防止某些用户段相互通信的策略, 或允许特定的分段仅与某些其他网段进行通信。 信息屏障策略可帮助您的组织保持遵守相关的行业标准和法规, 并避免潜在的利益冲突。 若要了解详细信息, 请参阅[信息障碍 (预览)](information-barriers.md)。 

> [!IMPORTANT]
> 本文介绍如何规划、定义、实现和管理信息屏障策略。 涉及几个步骤, 工作流划分为多个部分。 在开始定义 (或编辑) 信息屏障策略之前, 请务必阅读[先决条件](#prerequisites)和整个过程。

## <a name="concepts-of-information-barrier-policies"></a>信息屏障策略的概念

在规划、定义和实施信息屏障策略之前, 请了解相关的基本概念。 通过信息障碍, 你将使用用户帐户属性、段、信息屏障策略和本文中所述的策略应用程序过程。 

- **用户帐户属性**是在 Azure Active Directory (或 Exchange Online) 中定义的。 这些属性可以包括部门、职务、位置、团队名称等。 

- **分段**在 Office 365 安全 & 合规性中心中使用选定的**用户帐户属性**(如部门、职务、位置、团队名称或任何[受支持的属性](information-barriers-attributes.md)) 进行定义。 定义段不会对用户产生影响;它只是设置要定义并应用的信息屏障策略的阶段。

- **信息屏障策略**定义并分配给各个**网段**。 并不是所有段都分配有策略。 此外, 不能向任何一个字段分配多个策略。 定义策略时, 可以从以下两种策略中进行选择:
    - 防止一个分段与另一个网段通信的策略
    - 允许一段仅与某些其他段进行通信的策略

    理想情况下, 您将使用最少的策略数, 以确保您的组织符合法律和行业要求。

- **策略应用程序**在定义所有信息屏障策略之后完成, 并准备好在您的组织中应用它们。

## <a name="the-work-flow-at-a-glance"></a>工作流一览

|阶段    |涉及的内容  |
|---------|---------|
|[确保满足先决条件](#prerequisites)     |-确认你的订阅包括信息障碍<br/>-验证您是否具有定义/编辑段落和策略的必要权限<br/>-确保目录数据反映组织的结构<br/>-确保在 Microsoft 团队中启用了范围内的目录搜索<br/>-请确保审核日志记录已打开<br/>-使用 PowerShell 执行本文中的任务 (提供示例 cmdlet)<br/>-为 Microsoft 团队中的信息障碍提供管理员同意 (包括步骤)          |
|[第1部分: 分段组织中的所有用户](#part-1-segment-users)     |-确定所需的策略<br/>-创建要定义的段的列表<br/>-确定要使用的属性<br/>-在策略筛选器方面定义段        |
|[第2部分: 定义信息屏障策略](#part-2-define-information-barrier-policies)     |-定义你的策略 (尚不应用)<br/>-从两种类型 (阻止或允许) 中选择 |
|[第3部分: 应用信息屏障策略](#part-3-apply-information-barrier-policies)     |-将策略设置为活动状态<br/>-运行策略应用程序<br/>-验证策略状态         |
|(根据需要)[编辑段或策略](#edit-a-segment-or-a-policy)     |-编辑分段<br/>-编辑或删除策略<br/>-运行策略应用程序<br/>-验证策略状态         |
|(根据需要)[故障排除](information-barriers-troubleshooting.md)|-当策略未按预期工作时执行操作|

## <a name="prerequisites"></a>先决条件

**目前, 信息屏障功能位于私人预览版中**。 当这些功能普遍可用时, 它们将包含在订阅中, 例如:

- Microsoft 365 E5
- Office 365 E5
- Office 365 高级合规版
- Microsoft 365 E5 信息保护和合规性

有关更多详细信息, 请参阅[合规性解决方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。

### <a name="permissions"></a>权限

若要定义或编辑信息障碍策略,**必须为您分配适当的角色**, 如以下某项:
- Microsoft 365 企业全局管理员
- Office 365 全局管理员
- 合规性管理员
- IB 合规性管理 (这是一个新角色!)

若要了解有关角色和权限的详细信息, 请参阅[Office 365 Security & 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。
       
### <a name="directory-data"></a>目录数据

**确保您的组织的结构已反映在目录数据中**。 为此, 请确保在 Azure Active Directory (或 Exchange Online) 中正确填充了用户帐户属性, 如组成员身份、部门名称等。 若要了解详细信息, 请参阅以下资源:
- [信息屏障策略的属性 (预览)](information-barriers-attributes.md)
- [使用 Azure Active Directory 添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
- [使用 Office 365 PowerShell 配置用户帐户的属性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

### <a name="scoped-directory-search"></a>作用域目录搜索

在**定义组织的第一个信息屏障策略之前, 必须先[在 Microsoft 团队中启用范围目录搜索](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)**。 在设置或定义信息屏障策略之前, 请先等待至少24小时后, 再启用范围目录搜索。

### <a name="audit-logging"></a>审核日志记录

为了查找策略应用程序的状态, 审核日志记录必须处于打开状态。 我们建议您在开始定义段或策略之前执行此操作。 若要了解详细信息, 请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。

### <a name="powershell"></a>PowerShell

**目前, 信息屏障策略在 Office 365 Security & 合规性中心 (使用 PowerShell cmdlet) 中进行定义和管理**。 虽然本文中提供了几个方案和示例, 但您需要熟悉 PowerShell cmdlet 和参数。 

[连接到 Office 365 安全 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。

### <a name="provide-admin-consent-for-information-barriers-in-microsoft-teams"></a>为 Microsoft 团队中的信息障碍提供管理员同意

使用以下过程可使信息障碍策略在 Microsoft 团队中按预期方式工作。 

例如, 当您的策略已准备就绪时, 信息障碍可以从聊天会话中删除他们不应处于其中的人。 这有助于确保您的组织遵守策略和管理法规。 

1. 运行以下 PowerShell cmdlet:

    ```
    Login-AzureRmAccount 
    $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
    $sp=Get-AzureRmADServicePrincipal -ServicePrincipalName $appId
    if ($sp -eq $null) { New-AzureRmADServicePrincipal -ApplicationId $appId }
    Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
    ```

2. 出现提示时, 使用您的工作或学校帐户登录 Office 365。

3. 在 "**请求的权限**" 对话框中, 检查信息, 然后选择 "**接受**"。

## <a name="part-1-segment-users"></a>第1部分: 分段用户

在此阶段中, 您将确定所需的策略, 创建要定义的段的列表, 然后定义您的段落。

### <a name="determine-what-policies-are-needed"></a>确定所需的策略

考虑法律和行业法规, 谁是组织中需要信息障碍策略的组？ 创建列表。 是否有任何组应阻止其与另一个组进行通信？ 是否有任何组应允许只与一个或两个其他组进行通信？ 考虑您需要的策略是否属于两个组中的一个:
- 阻止一个组与另一个组进行通信的**阻止策略**
- **允许**特定组仅与特定的其他组进行通信的策略。

当您拥有组和策略的初始列表时, 请继续确定所需的段。

(请参阅本文中[的示例: Contoso 的部门和规划](#contosos-departments-and-plan)。)

### <a name="identify-segments"></a>标识段

除了您的初始策略列表之外, 请为您的组织创建一个段落列表。 组织中的每个用户都应属于某个分段, 并且任何用户都不应属于两个或多个分段。 每个段只能应用一个信息障碍策略。 

确定您的组织的目录数据中将用来定义段落的属性。 您可以使用 "*部门*"、" *MemberOf*" 或任何受支持的属性。 请确保您为所有用户选择的属性中具有值。 若要查看受支持的属性的列表, 请参阅[信息障碍策略的属性 (预览)](information-barriers-attributes.md)。

> [!IMPORTANT]
> 在**继续下一节之前, 请确保您的目录数据具有可用于定义段的属性的值**。 如果您的目录数据没有要使用的属性的值, 则必须更新所有用户帐户, 以便在继续进行信息障碍之前将该信息包括在内。 若要获取有关此方面的帮助, 请参阅以下资源:<br/>- [使用 Office 365 PowerShell 配置用户帐户属性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)<br/>- [使用 Azure Active Directory 添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>使用 PowerShell 定义段

> [!IMPORTANT]
> **请确保您的段不重叠**。 组织中的每个用户都应属于一个 (且只有一个) 分段。 任何用户都不应属于两个或多个段。 应为组织中的所有用户定义分段。 (请参阅本文中[的 Contoso 定义的部分](#contosos-defined-segments)。)

1. 若要定义组织段, 请使用**OrganizationSegment** Cmdlet 和**UserGroupFilter**参数, 该参数对应于要使用的[属性](information-barriers-attributes.md)。 

    语法`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`

    示例：`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`

    在此示例中, 使用*hr*("部门" 属性中的值) 定义名为*hr*的字段。

2. 对要定义的每个段重复步骤1。

    在运行每个 cmdlet 之后, 您应该会看到有关新段的详细信息列表。 详细信息包括段的类型、创建者或最后修改的人, 等等。 

定义了分段后, 请继续定义信息屏障策略。

## <a name="part-2-define-information-barrier-policies"></a>第2部分: 定义信息屏障策略

在您的用户区段列表和要定义的信息屏障策略中, 选择一个方案, 然后按照步骤操作。 

> [!IMPORTANT]
> 请**确保在定义策略时, 不会向一个分段分配多个策略**。 例如, 如果您为 " *sales*" 一段定义一个策略, 则不要为*sales*定义其他策略。 

确定是否需要阻止某些网段之间的通信, 或将通信限制到某些段。 在下面的方案中进行选择以定义策略。

- [方案 1: 阻止段之间的通信](#scenario-1-block-communications-between-segments)
- [方案 2: 允许段仅与一个其他段进行通信](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!NOTE]
> 在定义信息障碍策略时, 请确保将这些策略设置为非活动状态, 直到您准备好应用它们。 定义 (或编辑) 策略不会影响用户, 直到这些策略设置为 "活动状态", 然后应用。

(请参阅本文中[的示例: Contoso 的信息屏障策略](#contosos-information-barrier-policies)。)

### <a name="scenario-1-block-communications-between-segments"></a>方案 1: 阻止段之间的通信

当您想要阻止多个段相互通信时, 可以定义两个策略: 每个方向一个。 每个策略仅阻止单向通信。

例如, 假设您想要阻止段 A 和 Segment B 之间的通信。在这种情况下, 您可以定义一个策略, 阻止段 A 与段 B 通信, 然后定义另一个策略以防止段 B 与段 A 通信。

1. 若要定义您的第一个阻止策略, 请将**InformationBarrierPolicy** Cmdlet 与**SegmentsBlocked**参数一起使用。 

    语法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsBlocked "segmentname"`

    示例：`New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`

    在此示例中, 我们定义了名为 "*销售*" 的部门的名为 "销售 *-研究*" 的策略。 在活动和应用后, 此策略将阻止*销售*人员与名为 "*研究*" 的部门中的人员进行通信。

2. 若要定义您的第二个阻塞段, 请再次将**InformationBarrierPolicy** Cmdlet 与**SegmentsBlocked**参数一起使用, 这次将段反向。

    示例：`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`

    在此示例中, 我们定义了一个名为 "*研究部*" 的策略, 以防止与 "销售" 通信的研究。
 
2. 继续执行下列操作之一:

   - (如果需要)[定义一个策略以允许某个分段仅与另一个网段进行通信](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (在定义了所有策略之后)[应用信息屏障策略](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>方案 2: 允许段仅与一个其他段进行通信

1. 若要允许一个分段仅与一个其他网段通信, 请使用**InformationBarrierPolicy** Cmdlet 和**SegmentsAllowed**参数。 

    语法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname"`

    示例：`New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`

    在此示例中, 我们为 "*制造业*" 字段定义了称为 "制造业 *-HR* " 的策略。 在活动和应用后, 此策略允许在*制造业*中的人员仅与称为*HR*的部门中的人员进行通信。 (在这种情况下, 制造无法与不属于 HR 的用户进行通信。)

    **如果需要, 可以使用此 cmdlet 指定多个段, 如下面的两个示例中所示。**

    语法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname, segmentname"`

    **示例 1: 定义一个策略以允许多个段仅与一个其他段进行通信**

    `New-InformationBarrierPolicy -Name "ResearchManufacturing-HR" -AssignedSegment "Research, Manufacturing" -SegmentsAllowed "HR" -State Inactive`

    在此示例中, 我们定义了一个策略, 允许*信息检索*和*制造*网段仅与*HR*进行通信。

    **示例 2: 定义一个策略以允许多个段仅与某些其他段进行通信**    

    `New-InformationBarrierPolicy -Name "SalesMarketing-HRManufacturing" -AssignedSegment "Sales, Marketing" -SegmentsAllowed "HR, Manufacturing" -State Inactive`

    在此示例中, 我们定义了一个允许*销售*和*市场营销*部门仅与*HR*和*制造业*进行通信的策略。

    对于要定义的每个策略, 请重复此步骤, 以允许特定段仅与特定的其他特定段进行通信。

2. 继续执行下列操作之一:

   - (如果需要)[定义策略以阻止网段之间的通信](#scenario-1-block-communications-between-segments) 
   - (在定义了所有策略之后)[应用信息屏障策略](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>第3部分: 应用信息屏障策略

信息屏障策略在将其设置为 "活动状态" 之前不起作用, 然后应用这些策略。

1. 使用**InformationBarrierPolicy** cmdlet 可以查看已定义的策略的列表。 记下每个策略的状态和标识 (GUID)。

    语法`Get-InformationBarrierPolicy`

2. 若要将策略设置为活动状态, 请使用带有**Identity**参数的**InformationBarrierPolicy** Cmdlet, 并将**State**参数设置为 "**活动**"。 

    语法`Set-InformationBarrierPolicy -Identity GUID -State Active`

    示例：`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`
    
    在此示例中, 我们将 GUID 为 " *43c37853-ea10-4b90-a23d-ab8c93772471* " 的信息屏障策略设置为 "活动" 状态。

    根据需要对每个策略重复此步骤。

3. 完成将信息屏障策略设置为活动状态后, 请使用**InformationBarrierPoliciesApplication** Cmdlet 在 Office 365 安全 & 合规性中心。

    语法`Start-InformationBarrierPoliciesApplication`

    大约半小时后, 策略将应用于您的组织的用户。 如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。 (一般原则是, 处理5000用户帐户需要大约一小时的时间。)

## <a name="verify-status-of-user-accounts-segments-policies-or-policy-application"></a>验证用户帐户、段、策略或策略应用程序的状态

使用 PowerShell, 可以验证用户帐户、段、策略和策略应用程序的状态, 如下表中所列。

|若要验证此  |具体操作  |
|---------|---------|
|用户帐户     |使用具有 Identity 参数的**InformationBarrierRecipientStatus** cmdlet。 <p>语法`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>您可以使用任何唯一标识每个用户的值, 如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。 <p>示例：`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>在此示例中, 我们引用 Office 365 中的两个用户帐户: *meganb* for *Megan*和*alexw* for *Alex*。 <p>(也可以将此 cmdlet 用于单个用户: `Get-InformationBarrierRecipientStatus -Identity <value>`) <p>此 cmdlet 返回有关用户的信息, 如属性值和应用的任何信息障碍策略。|
|段     |使用**OrganizationSegment** cmdlet。<p>语法`Get-OrganizationSegment` <p>这将显示为您的组织定义的所有网段的列表。         |
|信息屏障策略     |使用**InformationBarrierPolicy** cmdlet。 <p> 语法`Get-InformationBarrierPolicy` <p>这将显示已定义的信息障碍策略的列表及其状态。       |
|最新的信息屏障策略应用程序     | 使用**InformationBarrierPoliciesApplicationStatus** cmdlet。 <p>语法`Get-InformationBarrierPoliciesApplicationStatus`<p>    这将显示有关策略应用程序是已完成、失败还是正在进行的信息。       |
|所有信息屏障策略应用程序|改用`Get-InformationBarrierPoliciesApplicationStatus -All $true`<p>这将显示有关策略应用程序是已完成、失败还是正在进行的信息。|

## <a name="stop-a-policy-application"></a>停止策略应用程序

如果在您开始应用信息屏障策略后, 您想要停止应用这些策略, 请使用以下过程。 请注意, 此过程将需要大约30-35 分钟才能开始。

1. 若要查看最新信息屏障策略应用程序的状态, 请使用**InformationBarrierPoliciesApplicationStatus** cmdlet。

    语法`Get-InformationBarrierPoliciesApplicationStatus`

    记下应用程序的 GUID。

2. 将**InformationBarrierPoliciesApplication** Cmdlet 与 Identity 参数一起使用。

    语法`Stop-InformationBarrierPoliciesApplication -Identity GUID`

    示例：`InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`

## <a name="edit-a-segment-or-a-policy"></a>编辑段或策略

### <a name="edit-a-segment"></a>编辑段

1. 若要查看所有现有段, 请使用**OrganizationSegment** cmdlet。
    
    语法`Get-OrganizationSegment`

    你将看到每个段的列表和详细信息, 如段类型、其 UserGroupFilter 值、创建日期或上次修改时间、GUID 等。

    > [!TIP]
    > 打印或保存段列表以便日后参考。 例如, 如果您想要编辑某一段, 则需要知道它的名称或标识值 (这与 Identity 参数一起使用)。

2. 若要编辑分段, 请使用**OrganizationSegment** Cmdlet 和**Identity**参数以及相关详细信息。 

    语法`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`

    示例：`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`

    在此示例中, 对于具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的段, 我们将部门名称更新为 "HRDept"。

为组织编辑完段后, 可以继续[定义](#part-2-define-information-barrier-policies)或[编辑](#edit-a-policy)信息屏障策略。

### <a name="edit-a-policy"></a>编辑策略

1. 若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。

    语法`Get-InformationBarrierPolicy`

    在结果列表中, 标识要更改的策略。 记下策略的 GUID 和名称。

2. 将**InformationBarrierPolicy** Cmdlet 与**Identity**参数一起使用, 并指定要进行的更改。

    语法 (阻止段与其他段通信): 

    `Set-InformationBarrierPolicy -Identity GUID -SegmentsBlocked "segmentname, segmentname"` 

    语法 (仅允许段与某些其他段进行通信):
    
    ``Set-InformationBarrierPolicy -Identity GUID -SegmentsAllowed "segmentname, segmentname"``

    示例: 假设定义了一个策略以阻止与销售和市场进行通信的研究。 该策略是使用以下 cmdlet 定义的:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales, Marketing"`
    
    假设我们要对其进行更改, 以便信息检索中的人员只能与 HR 中的人员进行通信。 若要进行此更改, 我们使用以下 cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

3. 完成策略的编辑后, 请确保应用所做的更改。 (请参阅[Apply 信息屏障策略](#part-3-apply-information-barrier-policies)。)

### <a name="remove-a-policy"></a>删除策略

1. 若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。

    语法`Get-InformationBarrierPolicy`

    在结果列表中, 标识要删除的策略。 记下策略的 GUID 和名称。 请确保将策略设置为非活动状态。

2. 将**InformationBarrierPolicy** Cmdlet 与 Identity 参数一起使用。

    语法`Remove-InformationBarrierPolicy -Identity GUID`

    示例: 假设我们要删除 GUID 为*43c37853-ea10-4b90-a23d-ab8c93772471*的策略。 为此, 我们使用此 cmdlet:
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    出现提示时, 请确认更改。

3. 对要删除的每个策略重复步骤1-2。

4. 删除完策略后, 应用所做的更改。 为此, 请使用**InformationBarrierPoliciesApplication** cmdlet。

    语法`Start-InformationBarrierPoliciesApplication`

    为您的组织应用更改的用户。 如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。

### <a name="set-a-policy-to-inactive-status"></a>将策略设置为非活动状态

1. 若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。

    语法`Get-InformationBarrierPolicy`

    在结果列表中, 标识要更改 (或删除) 的策略。 记下策略的 GUID 和名称。

2. 若要将策略的状态设置为 "非活动", 请使用带有 Identity 参数的**InformationBarrierPolicy** cmdlet, 将 State 参数设置为 "非活动"。

    语法`Set-InformationBarrierPolicy -Identity GUID -State Inactive`

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    在此示例中, 我们将具有 GUID *43c37853-ea10-4b90-a23d-ab8c9377247*的信息屏障策略设置为非活动状态。

3. 若要应用所做的更改, 请使用**InformationBarrierPoliciesApplication** cmdlet。

    语法`Start-InformationBarrierPoliciesApplication`

    为您的组织应用更改的用户。 如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。 (一般原则是, 处理5000用户帐户需要大约一小时的时间。)

在这种情况下, 一个或多个信息障碍策略将设置为非活动状态。 在这里, 您可以执行以下任一操作:
- 将其保持原样 (策略设置为非活动状态对用户没有影响)
- [编辑策略](#edit-a-policy) 
- [删除策略](#remove-a-policy)

## <a name="example-contosos-departments-segments-and-policies"></a>示例: Contoso 的部门、分段和策略

若要了解组织如何采用定义段落和策略的方法, 请考虑以下示例。

### <a name="contosos-departments-and-plan"></a>Contoso 的部门和规划

Contoso 有五个部门: HR、销售、营销、研究和制造。 为了保持与行业法规的兼容性, 某些部门中的人员不应与其他部门通信, 如下表所示:

|段落  |可以与  |无法对话  |
|---------|---------|---------|
|HR     |每个人         |(无限制)         |
|销售     |HR、营销、制造业         |信息检索         |
|营销     |每个人         |(无限制)         |
|信息检索     |HR、营销、制造业        |销售     |
|制造业 |HR、营销 |除 HR 或营销之外的任何人 |

考虑到这一点, Contoso 的计划包括三个信息屏障策略:

1. 旨在防止销售人员与信息检索通信的策略 (和另一个策略, 以防止与销售通信的信息检索)
2. 旨在允许制造业仅与 HR 和营销进行通信的策略 

不需要为 HR 或营销定义策略。

### <a name="contosos-defined-segments"></a>Contoso 定义的段

Contoso 将使用 Azure Active Directory 中的 "部门" 属性来定义段, 如下所示:

|部门  |段定义  |
|---------|---------|
|HR     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|销售     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|营销     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|信息检索     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|制造业     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

定义段后, Contoso 将继续定义策略。 

### <a name="contosos-information-barrier-policies"></a>Contoso 的信息屏障策略

Contoso 定义了三种策略, 如下表所述:

|策略  |策略定义  |
|---------|---------|
|策略 1: 防止销售与信息检索通信     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> 在此示例中, 信息屏障策略称为 "*销售-研究*"。 当此策略处于活动状态且已应用时, 它将有助于阻止销售部门中的用户与研究网段中的用户进行通信。 这是单向策略;它不会阻止研究与销售通信。 为此, 需要策略2。      |
|策略 2: 防止与销售通信的研究     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> 在此示例中, 信息屏障策略称为 "*研究-销售*"。 当此策略处于活动状态且已应用时, 它将有助于防止在研究网段中的用户与销售部门中的用户进行通信。       |
|策略 3: 允许制造业仅与 HR 和营销进行通信     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR, Marketing" -State Inactive` <p>在这种情况下, 信息屏障策略称为 "*制造业-HRMarketing*"。 当此策略处于活动状态且已应用时, 生产只能与 HR 和 Marketing 进行通信。 请注意, 不限制 HR 和市场营销与其他段进行通信。 |

通过定义的段和策略, Contoso 通过运行**InformationBarrierPoliciesApplication** cmdlet 来应用这些策略。 

完成后, Contoso 就符合法律和行业要求。

## <a name="related-articles"></a>相关文章

[获取信息障碍概述](information-barriers.md)

[了解有关 Microsoft 团队中的信息障碍的详细信息](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[信息屏障策略的属性 (预览)](information-barriers-attributes.md)

[解决信息障碍 (预览)](information-barriers-troubleshooting.md)