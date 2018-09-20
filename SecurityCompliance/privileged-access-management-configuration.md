---
title: Office 365 中配置的访问权限的管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Strat_O365_IP
ms.custom: Ent_Solutions
ms.assetid: ''
description: 使用本主题以详细了解如何在 Office 365 中配置访问权限的管理
ms.openlocfilehash: b2b6ab18687617c0da3425f4ee60cf81074f6f69
ms.sourcegitcommit: 15dfa0c83aa88816c18e30a44a49e36e733d952c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "24021395"
---
# <a name="configuring-privileged-access-management-in-office-365"></a>Office 365 中配置的访问权限的管理

> [!IMPORTANT]
> 本主题介绍了部署和配置指南仅当前 Office 365 E5 和高级合规性 Sku 中可用的功能。

本主题将指导您完成启用和配置 Office 365 组织中的访问权限的管理。您可以使用管理和使用的 Microsoft 365 Admin Center 或 Exchange Management PowerShell 特权访问。 

## <a name="enable-and-configure-privileged-access-management"></a>启用和配置访问权限的管理

请按照下列步骤设置和使用 Office 365 组织中的访问权限：

- [步骤 1： 创建审批者组](privileged-access-management-configuration.md#step1)

    在开始使用最小特权 access 之前，决定谁将具有审批授权的传入请求访问提升特权的任务。审批者的组的一部分的任何用户都将能够批准访问请求。这被启用的 Office 365 中创建启用邮件的安全组。

- [步骤 2： 启用访问权限](privileged-access-management-configuration.md#step2)

    需要显式打开 Office 365 中使用的默认审批者组和包括要排除的访问权限的管理访问控制从系统帐户的一组访问权限。

- [步骤 3： 创建访问策略](privileged-access-management-configuration.md#step3)

    创建审批策略允许您定义的范围限制在各项任务的特定审批要求。**自动**或**手动**了审批类型选项。

- [步骤 4： 提交/批准特权的访问请求](privileged-access-management-configuration.md#step4)

    启用之后，特权访问需要执行任何任务已定义的关联的审批策略审批。无需执行中包含的任务的用户的审批策略必须请求，并让执行任务所需的权限授予访问审核。

授予审批后，请求的用户可以执行预期的任务并特权的 access 将授权，并对代表用户执行任务。审批保持有效的请求持续时间 （默认持续时间是 4 个小时），在此期间请求者可以预期的任务多次执行。所有此类执行的记录，并使其可供安全性和合规性审核。 

> [!NOTE]
> 如果您想要使用 Exchange Management PowerShell 启用和配置访问权限，请按照[连接到 Exchange Online PowerShell 中使用多因素身份验证](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)连接到 Exchange Online PowerShell 中使用 Office 365 中的步骤凭据。不需要启用多重身份验证您的 Office 365 组织使用的步骤同时连接到 Exchange Online PowerShell 中启用访问权限。将与多因素身份验证连接创建由授权的访问权限，登录您的请求的 OAuth 令牌。

<a name="step1"> </a>

## <a name="step-1---create-an-approvers-group"></a>步骤 1-创建审批者组

1. 登录到[Microsoft 365 Admin Center](https://portal.office.com)使用您的组织中的管理帐户的凭据。

2. 在管理中心，转到**组** > **添加组**。

3. 选择**已启用邮件的安全组**的组类型，然后完成新建组的**名称**、**组电子邮件地址**和**说明**字段。

4. 保存组。可能需要几分钟，以便完全配置并显示在 Office 365 管理中心中的组。

5. 选择新的审批者组，然后选择**编辑**以将用户添加到组。

6. 保存组。

<a name="step2"> </a>

## <a name="step-2---enable-privileged-access"></a>步骤 2-启用访问权限

### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

1. 登录到[Microsoft 365 Admin Center](https://portal.office.com)使用您的组织中的管理帐户的凭据。

2. 在管理中心，转到**设置 > 安全和隐私** > **访问权限**。

3. 启用**需要批准的访问权限**控件。

4. 将作为**默认审批者组**的步骤 1 中创建审批者的组分配。

5. **保存**并**关闭**。

### <a name="using-exchange-management-powershell"></a>使用 Exchange Management PowerShell

若要启用访问权限，并将审批者的组分配 Exchange Online PowerShell 中运行以下命令：
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
示例：
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> 系统帐户由可用于确保组织内的特定自动化功能可以处理不依赖项的情况下访问权限，但建议的此类排除在极那些允许应核准和审核定期。

<a name="step3"> </a>

## <a name="step-3---create-an-access-policy"></a>步骤 3-创建访问策略

### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

1. 登录到[Microsoft 365 Admin Center](https://portal.office.com)使用您的组织中的管理帐户的凭据。

2. 在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。

3. 选择**管理访问策略和请求**。

4. 选择**配置策略**，然后选择**添加策略**。

5. 从下拉列表字段中，选择您的组织的相应值：
    
    **策略类型**： 任务、 角色或角色组

    **策略作用域**： Exchange 或 Office 365

    **策略名称**： 从可用的策略选择

    **审批类型**： 手动或自动

    **审核组**： 选择在步骤 1 中创建的审批者组

6. 选择**创建**，然后**关闭**。可能需要几分钟，要完全配置并启用的策略。

### <a name="using-exchange-management-powershell"></a>使用 Exchange Management PowerShell

运行以下命令在 Exchange Online PowerShell，可以创建并定义审批策略：

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
示例：
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<a name="step4"> </a>

## <a name="step-4-submitapprove-privileged-access-requests"></a>步骤 4： 提交/批准特权的访问请求

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a>请求提升授权执行特权的任务

#### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

1. 登录到[Microsoft 365 Admin Center](https://portal.office.com)使用您的凭据。

2. 在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。

3. 选择**管理访问策略和请求**。

4. 选择**新的请求**。从下拉列表字段中，选择您的组织的相应值：

    **请求类型**： 任务、 角色或角色组

    **请求作用域**： Exchange

    **请求**： 从可用的策略选择

    **持续时间 （小时）**： 请求的访问的小时数

    **注释**： 注释的文本字段与您的访问请求

5. 选择**保存**和**关闭**。您的请求将发送到通过电子邮件的审批者的组。

#### <a name="using-exchange-management-powershell"></a>使用 Exchange Management PowerShell

运行以下命令在 Exchange Online PowerShell 来创建和提交给审批者的组的审批请求：
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
示例：
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a>查看提升请求的状态
创建审批请求后，可以在管理中心检查提升请求状态或在 Exchange Management PowerShell 请求使用关联的 id。

#### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

1. 登录到[Microsoft 365 Admin Center](https://portal.office.com)使用您的凭据。

2. 在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。

3. 选择**管理访问策略和请求**。

4. 选择要筛选**挂起**、**批准**、**拒绝**或**客户密码箱**状态提交的请求的**视图**。

#### <a name="using-exchange-management-powershell"></a>使用 Exchange Management PowerShell

运行以下命令在 Exchange Online PowerShell，可以查看特定的请求 ID 审批请求状态：
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
示例：
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a>批准提升授权请求
当创建审批请求时，相关的审批者组的成员将收到的电子邮件通知和可以批准请求 ID 与关联的请求

#### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

1. 登录到[Microsoft 365 Admin Center](https://portal.office.com)使用您的凭据。

2. 在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。

3. 选择**管理访问策略和请求**。

4. 选择列出的请求，若要查看详细信息，以请求对其执行操作。

5. 选择**批准**批准请求或选择**拒绝**以拒绝该请求。以前批准的请求可以通过选择**取消**吊销的访问。

#### <a name="using-exchange-management-powershell"></a>使用 Exchange Management PowerShell

运行以下命令在 Exchange Online PowerShell 批准提升授权请求：

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
示例：
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

运行以下命令在 Exchange Online PowerShell 拒绝提升授权请求：

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
示例：
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="disable-privileged-access-in-office-365"></a>禁用 Office 365 中的特权的访问

如果需要您可以为组织禁用特权的访问管理。禁用权限访问不会删除任何关联的审批策略或审批者组。

### <a name="using-the-microsoft-365-admin-center"></a>使用 Microsoft 365 管理中心

1. 登录到[Microsoft 365 Admin Center](https://portal.office.com)使用您的组织中的管理帐户的凭据。

2. 在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。

3. 启用**需要批准的访问权限**控件。

### <a name="using-exchange-management-powershell"></a>使用 Exchange Management PowerShell

运行以下命令在 Exchange Online Powershell，可以禁用授权访问权限：

```
Disable-ElevatedAccessControl
```