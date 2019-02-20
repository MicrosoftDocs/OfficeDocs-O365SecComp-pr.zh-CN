---
title: 在 Office 365 中配置特权访问管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: 使用本主题可了解有关在 Office 365 中配置特权访问管理的详细信息
ms.openlocfilehash: 63780da59afb245b35916a1e7a5b2eb780d535a8
ms.sourcegitcommit: c94cb88a9ce5bcc2d3c558f0fcc648519cc264a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "30090914"
---
# <a name="configuring-privileged-access-management-in-office-365"></a>在 Office 365 中配置特权访问管理

> [!IMPORTANT]
> 本主题介绍了 Office 365 E5 和高级合规 sku 中目前仅提供的功能的部署和配置指南。

本主题将指导您在 Office 365 组织中启用和配置特权访问管理。您可以使用 Microsoft 365 管理中心或 Exchange 管理 PowerShell 管理和使用特权访问。 

## <a name="enable-and-configure-privileged-access-management"></a>启用和配置特权访问管理

按照以下步骤设置和使用 Office 365 组织中的特权访问:

- [步骤 1: 创建审批者的组](privileged-access-management-configuration.md#step1)

    在开始使用权限访问之前, 请确定谁将拥有对已提升和特权任务的传入请求的审批权限。作为审批者组的一部分的任何用户都将能够批准访问请求。这是通过在 Office 365 中创建启用邮件的安全组来启用的。

- [步骤 2: 启用特权访问](privileged-access-management-configuration.md#step2)

    需要在 Office 365 中显式打开具有默认审批者组的特权访问权限, 并包含要从特权访问管理访问控制中排除的一组系统帐户。

- [步骤 3: 创建访问策略](privileged-access-management-configuration.md#step3)

    通过创建审批策略, 可以定义各个任务范围内的特定审批要求。审批类型选项为 "**自动**" 或 "**手动**"。

- [步骤 4: 提交/批准权限访问请求](privileged-access-management-configuration.md#step4)

    启用后, 特权访问需要审批以执行任何定义了关联的审批策略的任务。需要执行审批策略中包含的任务的用户必须请求并授予访问审批权限, 以便拥有执行任务所需的权限。

授予批准后, 请求用户可以执行预期的任务, 而特权访问将代表用户授权和执行任务。审批在请求的持续时间 (默认持续时间为4小时) 内保持有效, 在此期间, 请求者可以多次执行预期任务。将记录所有此类执行情况, 并提供安全和合规性审核。 

> [!NOTE]
> 如果要使用 Exchange 管理 PowerShell 启用和配置特权访问, 请按照[使用多重身份验证](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)连接到 exchange online powershell 与 Office 365 连接到 exchange online powershell 中的步骤操作。凭据.您无需为 Office 365 组织启用多重身份验证, 即可使用在连接到 Exchange Online PowerShell 时启用特权访问的步骤。使用多重身份验证进行连接将创建一个 OAuth 令牌, 该令牌由用于对您的请求进行签名的特权访问使用。

<a name="step1"> </a>

## <a name="step-1---create-an-approvers-group"></a>步骤 1-创建审批者的组

1. 使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://portal.office.com)。

2. 在管理中心中, 转到 "**组** > " "**添加组**"。

3. 选择 "**已启用邮件的安全组**" 组类型, 然后填写新组的**名称**、**组电子邮件地址**和**说明**字段。

4. 保存组。可能需要几分钟的时间才能完全配置组并将其显示在 Office 365 管理中心中。

5. 选择新的审批者组, 然后选择 "**编辑**" 将用户添加到组中。

6. 保存组。

<a name="step2"> </a>

## <a name="step-2---enable-privileged-access"></a>步骤 2-启用特权访问

### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

1. 使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://portal.office.com)。

2. 在管理中心中, 转到 "**设置" > Security & 隐私** > 权限**访问**。

3. 启用 "**需要批准以进行特权访问**控制"。

4. 将您在步骤1中创建的审批者组分配为默认的 "**审批者" 组**。

5. **保存**并**关闭**。

### <a name="using-exchange-management-powershell"></a>使用 Exchange 管理 PowerShell

在 Exchange Online PowerShell 中运行以下命令, 以启用特权访问并分配审批者的组:
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
示例：
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> 系统帐户功能可用于确保组织内的某些自动脚本可以正常工作, 而无需对特权访问进行依赖性, 但建议将此类排除条件设为例外, 并且应批准和审核这些排除条件保持.

<a name="step3"> </a>

## <a name="step-3---create-an-access-policy"></a>步骤 3-创建访问策略

您可以为 Office 365 组织创建和配置最高30个权限访问策略。

### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

1. 使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://portal.office.com)。

2. 在管理中心中, 转到 "**设置** > **安全 & 隐私** > 权限**访问**"。

3. 选择 "**管理访问策略和请求**"。

4. 选择 "**配置策略**", 然后选择 "**添加策略**"。

5. 从下拉字段中, 为您的组织选择适当的值:
    
    **策略类型**: 任务、角色或角色组

    **策略作用域**: Exchange 或 Office 365

    **策略名称**: 从可用策略中进行选择

    **审批类型**: 手动或自动

    **审批组**: 选择在步骤1中创建的 "审批者" 组

6. 选择 "**创建**", 然后单击 "**关闭**"。为策略完全配置和启用可能需要几分钟时间。

### <a name="using-exchange-management-powershell"></a>使用 Exchange 管理 PowerShell

在 Exchange Online PowerShell 中运行以下命令, 以创建和定义审批策略:

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
示例：
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>步骤 4: 提交/批准权限访问请求

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>请求提升授权以执行特权任务

特权访问请求在提交请求后最长24小时有效。如果未批准或被拒绝, 请求将过期, 并且不会获得访问权限。

#### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

1. 使用您的凭据登录到[Microsoft 365 管理中心](https://portal.office.com)。

2. 在管理中心中, 转到 "**设置** > **安全 & 隐私** > 权限**访问**"。

3. 选择 "**管理访问策略和请求**"。

4. 选择 "**新建请求**"。从下拉字段中, 为您的组织选择适当的值:

    **请求类型**: 任务、角色或角色组

    **请求范围**: Exchange

    **请求**: 从可用策略中选择

    **持续时间 (小时)**: 请求的访问的小时数。对于可以请求的小时数没有限制。

    **注释**: 与您的访问请求相关的注释的文本字段

5. 依次选择 "**保存**" 和 "**关闭**"。您的请求将通过电子邮件发送给审批者的组。

#### <a name="using-exchange-management-powershell"></a>使用 Exchange 管理 PowerShell

在 Exchange Online PowerShell 中运行以下命令, 以创建批准请求并将其提交给审批者的组:
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
示例：
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a>查看提升请求的状态
在创建审批请求后, 可以在管理中心或 Exchange Management PowerShell 中使用与请求 ID 关联的权限来查看提升请求状态。

#### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

1. 使用您的凭据登录到[Microsoft 365 管理中心](https://portal.office.com)。

2. 在管理中心中, 转到 "**设置** > **安全 & 隐私** > 权限**访问**"。

3. 选择 "**管理访问策略和请求**"。

4. 选择 "**查看**" 以按**待定**、**批准**、**拒绝**或**客户密码箱**状态筛选提交的请求。

#### <a name="using-exchange-management-powershell"></a>使用 Exchange 管理 PowerShell

在 Exchange Online PowerShell 中运行以下命令, 以查看特定请求 ID 的审批请求状态:
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
示例：
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>批准提升授权请求
在创建审批请求时, 相关审批者组的成员将收到电子邮件通知, 并且可以批准与请求 ID 关联的请求。请求批准或通过电子邮件拒绝的请求程序将收到通知。

#### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

1. 使用您的凭据登录到[Microsoft 365 管理中心](https://portal.office.com)。

2. 在管理中心中, 转到 "**设置** > **安全 & 隐私** > 权限**访问**"。

3. 选择 "**管理访问策略和请求**"。

4. 选择一个列出的请求以查看详细信息, 并对请求执行操作。

5. 选择 "**批准**" 以批准请求, 或选择 "**拒绝**" 以拒绝该请求。以前批准的请求可以通过选择 "**吊销**" 来撤销访问权限。

#### <a name="using-exchange-management-powershell"></a>使用 Exchange 管理 PowerShell

在 Exchange Online PowerShell 中运行以下命令, 以批准提升授权请求:

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
示例：
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

在 Exchange Online PowerShell 中运行以下命令, 以拒绝提升授权请求:

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
示例：
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a>删除 Office 365 中的特权访问策略
如果您的组织不再需要某个特权访问策略, 则可以将其删除。

### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

1. 使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://portal.office.com)。

2. 在管理中心中, 转到 "**设置** > **安全 & 隐私** > 权限**访问**"。

3. 选择 "**管理访问策略和请求**"。

4. 选择 "**配置策略**"。

5. 选择要删除的策略, 然后选择 "**删除策略**"。

6. 选择 "**关闭**"。

### <a name="using-exchange-management-powershell"></a>使用 Exchange 管理 PowerShell

在 Exchange Online Powershell 中运行以下命令以删除特权访问策略:

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a>禁用 Office 365 中的特权访问

如果需要, 您可以为您的组织禁用特权访问管理。禁用特权访问不会删除任何关联的审批策略或审批者组。

### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

1. 使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://portal.office.com)。

2. 在管理中心中, 转到 "**设置** > **安全 & 隐私** > 权限**访问**"。

3. 启用 "**需要批准以进行特权访问**控制"。

### <a name="using-exchange-management-powershell"></a>使用 Exchange 管理 PowerShell

在 Exchange Online Powershell 中运行以下命令, 以禁用特权访问:

```
Disable-ElevatedAccessControl
```