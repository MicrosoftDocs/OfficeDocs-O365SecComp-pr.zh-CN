---
title: 在 Office 365 中配置特权访问管理
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: 使用本主题可了解有关在 Office 365 中配置特权访问管理的详细信息
ms.openlocfilehash: af8058ff852bbf290084e42d1f4c72d6fcee0e27
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30221082"
---
# <a name="configuring-privileged-access-management-in-office-365"></a><span data-ttu-id="e5296-103">在 Office 365 中配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="e5296-103">Configuring privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e5296-104">本主题介绍了 Office 365 E5 和高级合规 sku 中目前仅提供的功能的部署和配置指南。</span><span class="sxs-lookup"><span data-stu-id="e5296-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="e5296-p101">本主题将指导您在 Office 365 组织中启用和配置特权访问管理。您可以使用 Microsoft 365 管理中心或 Exchange 管理 PowerShell 管理和使用特权访问。</span><span class="sxs-lookup"><span data-stu-id="e5296-p101">This topic will guide you through enabling and configuring privileged access management in your Office 365 organization. You can use either the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="e5296-107">启用和配置特权访问管理</span><span class="sxs-lookup"><span data-stu-id="e5296-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="e5296-108">按照以下步骤设置和使用 Office 365 组织中的特权访问:</span><span class="sxs-lookup"><span data-stu-id="e5296-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="e5296-109">步骤 1: 创建审批者的组</span><span class="sxs-lookup"><span data-stu-id="e5296-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="e5296-p102">在开始使用权限访问之前, 请确定谁将拥有对已提升和特权任务的传入请求的审批权限。作为审批者组的一部分的任何用户都将能够批准访问请求。这是通过在 Office 365 中创建启用邮件的安全组来启用的。</span><span class="sxs-lookup"><span data-stu-id="e5296-p102">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="e5296-113">步骤 2: 启用特权访问</span><span class="sxs-lookup"><span data-stu-id="e5296-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="e5296-114">需要在 Office 365 中显式打开具有默认审批者组的特权访问权限, 并包含要从特权访问管理访问控制中排除的一组系统帐户。</span><span class="sxs-lookup"><span data-stu-id="e5296-114">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="e5296-115">步骤 3: 创建访问策略</span><span class="sxs-lookup"><span data-stu-id="e5296-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="e5296-p103">通过创建审批策略, 可以定义各个任务范围内的特定审批要求。审批类型选项为 "**自动**" 或 "**手动**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-p103">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks. The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="e5296-118">步骤 4: 提交/批准权限访问请求</span><span class="sxs-lookup"><span data-stu-id="e5296-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="e5296-p104">启用后, 特权访问需要审批以执行任何定义了关联的审批策略的任务。需要执行审批策略中包含的任务的用户必须请求并授予访问审批权限, 以便拥有执行任务所需的权限。</span><span class="sxs-lookup"><span data-stu-id="e5296-p104">Once enabled, privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="e5296-p105">授予批准后, 请求用户可以执行预期的任务, 而特权访问将代表用户授权和执行任务。审批在请求的持续时间 (默认持续时间为4小时) 内保持有效, 在此期间, 请求者可以多次执行预期任务。将记录所有此类执行情况, 并提供安全和合规性审核。</span><span class="sxs-lookup"><span data-stu-id="e5296-p105">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on users’ behalf. The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times. All such executions are logged and made available for security and compliance auditing.</span></span> 

> [!NOTE]
> <span data-ttu-id="e5296-p106">如果要使用 Exchange 管理 PowerShell 启用和配置特权访问, 请按照[使用多重身份验证](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)连接到 exchange online powershell 与 Office 365 连接到 exchange online powershell 中的步骤操作。凭据.您无需为 Office 365 组织启用多重身份验证, 即可使用在连接到 Exchange Online PowerShell 时启用特权访问的步骤。使用多重身份验证进行连接将创建一个 OAuth 令牌, 该令牌由用于对您的请求进行签名的特权访问使用。</span><span class="sxs-lookup"><span data-stu-id="e5296-p106">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials. You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell. Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="e5296-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="e5296-127"></span></span>

## <a name="step-1---create-an-approvers-group"></a><span data-ttu-id="e5296-128">步骤 1-创建审批者的组</span><span class="sxs-lookup"><span data-stu-id="e5296-128">Step 1 - Create an approver's group</span></span>

1. <span data-ttu-id="e5296-129">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="e5296-129">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="e5296-130">在管理中心中, 转到 "**组** > " "**添加组**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="e5296-131">选择 "**已启用邮件的安全组**" 组类型, 然后填写新组的**名称**、**组电子邮件地址**和**说明**字段。</span><span class="sxs-lookup"><span data-stu-id="e5296-131">Select the **mail-enabled security group** group type and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="e5296-p107">保存组。可能需要几分钟的时间才能完全配置组并将其显示在 Office 365 管理中心中。</span><span class="sxs-lookup"><span data-stu-id="e5296-p107">Save the group. It may take a few minutes for the group to be fully configured and to appear in the Office 365 Admin Center.</span></span>

5. <span data-ttu-id="e5296-134">选择新的审批者组, 然后选择 "**编辑**" 将用户添加到组中。</span><span class="sxs-lookup"><span data-stu-id="e5296-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="e5296-135">保存组。</span><span class="sxs-lookup"><span data-stu-id="e5296-135">Save the group.</span></span>

<span data-ttu-id="e5296-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="e5296-136"></span></span>

## <a name="step-2---enable-privileged-access"></a><span data-ttu-id="e5296-137">步骤 2-启用特权访问</span><span class="sxs-lookup"><span data-stu-id="e5296-137">Step 2 - Enable privileged access</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="e5296-138">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="e5296-138">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="e5296-139">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="e5296-139">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="e5296-140">在管理中心中, 转到 "**设置" > Security & 隐私** > 权限**访问**。</span><span class="sxs-lookup"><span data-stu-id="e5296-140">In the Admin Center, go to **Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e5296-141">启用 "**需要批准以进行特权访问**控制"。</span><span class="sxs-lookup"><span data-stu-id="e5296-141">Enable the **Require approvals for privileged access** control.</span></span>

4. <span data-ttu-id="e5296-142">将您在步骤1中创建的审批者组分配为默认的 "**审批者" 组**。</span><span class="sxs-lookup"><span data-stu-id="e5296-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="e5296-143">**保存**并**关闭**。</span><span class="sxs-lookup"><span data-stu-id="e5296-143">**Save** and **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="e5296-144">使用 Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5296-144">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="e5296-145">在 Exchange Online PowerShell 中运行以下命令, 以启用特权访问并分配审批者的组:</span><span class="sxs-lookup"><span data-stu-id="e5296-145">Run the following command in Exchange Online PowerShell to enable privileged access and to assign the approver's group:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
<span data-ttu-id="e5296-146">示例：</span><span class="sxs-lookup"><span data-stu-id="e5296-146">Example:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="e5296-147">系统帐户功能可用于确保组织内的某些自动脚本可以正常工作, 而无需对特权访问进行依赖性, 但建议将此类排除条件设为例外, 并且应批准和审核这些排除条件保持.</span><span class="sxs-lookup"><span data-stu-id="e5296-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="e5296-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="e5296-148"></span></span>

## <a name="step-3---create-an-access-policy"></a><span data-ttu-id="e5296-149">步骤 3-创建访问策略</span><span class="sxs-lookup"><span data-stu-id="e5296-149">Step 3 - Create an access policy</span></span>

<span data-ttu-id="e5296-150">您可以为 Office 365 组织创建和配置最高30个权限访问策略。</span><span class="sxs-lookup"><span data-stu-id="e5296-150">You can create and configure up to 30 privileged access policies for your Office 365 organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="e5296-151">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="e5296-151">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="e5296-152">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="e5296-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="e5296-153">在管理中心中, 转到 "**设置** > **安全 & 隐私** > 权限**访问**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e5296-154">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="e5296-155">选择 "**配置策略**", 然后选择 "**添加策略**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-155">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="e5296-156">从下拉字段中, 为您的组织选择适当的值:</span><span class="sxs-lookup"><span data-stu-id="e5296-156">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="e5296-157">**策略类型**: 任务、角色或角色组</span><span class="sxs-lookup"><span data-stu-id="e5296-157">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="e5296-158">**策略作用域**: Exchange 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="e5296-158">**Policy scope**: Exchange or Office 365</span></span>

    <span data-ttu-id="e5296-159">**策略名称**: 从可用策略中进行选择</span><span class="sxs-lookup"><span data-stu-id="e5296-159">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="e5296-160">**审批类型**: 手动或自动</span><span class="sxs-lookup"><span data-stu-id="e5296-160">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="e5296-161">**审批组**: 选择在步骤1中创建的 "审批者" 组</span><span class="sxs-lookup"><span data-stu-id="e5296-161">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="e5296-p108">选择 "**创建**", 然后单击 "**关闭**"。为策略完全配置和启用可能需要几分钟时间。</span><span class="sxs-lookup"><span data-stu-id="e5296-p108">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="e5296-164">使用 Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5296-164">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="e5296-165">在 Exchange Online PowerShell 中运行以下命令, 以创建和定义审批策略:</span><span class="sxs-lookup"><span data-stu-id="e5296-165">Run the following command in Exchange Online PowerShell to create and define an approval policy:</span></span>

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
<span data-ttu-id="e5296-166">示例：</span><span class="sxs-lookup"><span data-stu-id="e5296-166">Example:</span></span>
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="e5296-167"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="e5296-167"></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="e5296-168">步骤 4: 提交/批准权限访问请求</span><span class="sxs-lookup"><span data-stu-id="e5296-168">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="e5296-169">请求提升授权以执行特权任务</span><span class="sxs-lookup"><span data-stu-id="e5296-169">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="e5296-p109">特权访问请求在提交请求后最长24小时有效。如果未批准或被拒绝, 请求将过期, 并且不会获得访问权限。</span><span class="sxs-lookup"><span data-stu-id="e5296-p109">Requests for privileged access are valid for up to 24 hours after the request is submitted. If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="e5296-172">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="e5296-172">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="e5296-173">使用您的凭据登录到[Microsoft 365 管理中心](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="e5296-173">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="e5296-174">在管理中心中, 转到 "**设置** > **安全 & 隐私** > 权限**访问**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-174">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e5296-175">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-175">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="e5296-p110">选择 "**新建请求**"。从下拉字段中, 为您的组织选择适当的值:</span><span class="sxs-lookup"><span data-stu-id="e5296-p110">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="e5296-178">**请求类型**: 任务、角色或角色组</span><span class="sxs-lookup"><span data-stu-id="e5296-178">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="e5296-179">**请求范围**: Exchange</span><span class="sxs-lookup"><span data-stu-id="e5296-179">**Request scope**: Exchange</span></span>

    <span data-ttu-id="e5296-180">**请求**: 从可用策略中选择</span><span class="sxs-lookup"><span data-stu-id="e5296-180">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="e5296-p111">**持续时间 (小时)**: 请求的访问的小时数。对于可以请求的小时数没有限制。</span><span class="sxs-lookup"><span data-stu-id="e5296-p111">**Duration (hours)**: Number of hours of requested access. There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="e5296-183">**注释**: 与您的访问请求相关的注释的文本字段</span><span class="sxs-lookup"><span data-stu-id="e5296-183">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="e5296-p112">依次选择 "**保存**" 和 "**关闭**"。您的请求将通过电子邮件发送给审批者的组。</span><span class="sxs-lookup"><span data-stu-id="e5296-p112">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="e5296-186">使用 Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5296-186">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="e5296-187">在 Exchange Online PowerShell 中运行以下命令, 以创建批准请求并将其提交给审批者的组:</span><span class="sxs-lookup"><span data-stu-id="e5296-187">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
<span data-ttu-id="e5296-188">示例：</span><span class="sxs-lookup"><span data-stu-id="e5296-188">Example:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="e5296-189">查看提升请求的状态</span><span class="sxs-lookup"><span data-stu-id="e5296-189">View status of elevation requests</span></span>
<span data-ttu-id="e5296-190">在创建审批请求后, 可以在管理中心或 Exchange Management PowerShell 中使用与请求 ID 关联的权限来查看提升请求状态。</span><span class="sxs-lookup"><span data-stu-id="e5296-190">After an approval request is created, elevation request status can be reviewed in the Admin Center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="e5296-191">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="e5296-191">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="e5296-192">使用您的凭据登录到[Microsoft 365 管理中心](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="e5296-192">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="e5296-193">在管理中心中, 转到 "**设置** > **安全 & 隐私** > 权限**访问**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-193">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e5296-194">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-194">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="e5296-195">选择 "**查看**" 以按**待定**、**批准**、**拒绝**或**客户密码箱**状态筛选提交的请求。</span><span class="sxs-lookup"><span data-stu-id="e5296-195">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="e5296-196">使用 Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5296-196">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="e5296-197">在 Exchange Online PowerShell 中运行以下命令, 以查看特定请求 ID 的审批请求状态:</span><span class="sxs-lookup"><span data-stu-id="e5296-197">Run the following command in Exchange Online PowerShell to view a approval request status for a specific request ID:</span></span>
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
<span data-ttu-id="e5296-198">示例：</span><span class="sxs-lookup"><span data-stu-id="e5296-198">Example:</span></span>
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="e5296-199">批准提升授权请求</span><span class="sxs-lookup"><span data-stu-id="e5296-199">Approving an elevation authorization request</span></span>
<span data-ttu-id="e5296-p113">在创建审批请求时, 相关审批者组的成员将收到电子邮件通知, 并且可以批准与请求 ID 关联的请求。请求批准或通过电子邮件拒绝的请求程序将收到通知。</span><span class="sxs-lookup"><span data-stu-id="e5296-p113">When an approval request is created, members of the relevant approver group will receive an email notification and can approve the request associated with the request ID. The requestor will be notified of the request approval or denial via email message.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="e5296-202">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="e5296-202">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="e5296-203">使用您的凭据登录到[Microsoft 365 管理中心](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="e5296-203">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="e5296-204">在管理中心中, 转到 "**设置** > **安全 & 隐私** > 权限**访问**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-204">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e5296-205">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-205">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="e5296-206">选择一个列出的请求以查看详细信息, 并对请求执行操作。</span><span class="sxs-lookup"><span data-stu-id="e5296-206">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="e5296-p114">选择 "**批准**" 以批准请求, 或选择 "**拒绝**" 以拒绝该请求。以前批准的请求可以通过选择 "**吊销**" 来撤销访问权限。</span><span class="sxs-lookup"><span data-stu-id="e5296-p114">Select **Approve** to approve the request or select **Deny** to deny the request. Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="e5296-209">使用 Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5296-209">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="e5296-210">在 Exchange Online PowerShell 中运行以下命令, 以批准提升授权请求:</span><span class="sxs-lookup"><span data-stu-id="e5296-210">Run the following command in Exchange Online PowerShell to approve an elevation authorization request:</span></span>

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
<span data-ttu-id="e5296-211">示例：</span><span class="sxs-lookup"><span data-stu-id="e5296-211">Example:</span></span>
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="e5296-212">在 Exchange Online PowerShell 中运行以下命令, 以拒绝提升授权请求:</span><span class="sxs-lookup"><span data-stu-id="e5296-212">Run the following command in Exchange Online PowerShell to deny an elevation authorization request:</span></span>

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
<span data-ttu-id="e5296-213">示例：</span><span class="sxs-lookup"><span data-stu-id="e5296-213">Example:</span></span>
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="e5296-214">删除 Office 365 中的特权访问策略</span><span class="sxs-lookup"><span data-stu-id="e5296-214">Delete a privileged access policy in Office 365</span></span>
<span data-ttu-id="e5296-215">如果您的组织不再需要某个特权访问策略, 则可以将其删除。</span><span class="sxs-lookup"><span data-stu-id="e5296-215">You can delete a privileged access policy if it is no longer needed in your organization.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="e5296-216">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="e5296-216">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="e5296-217">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="e5296-217">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="e5296-218">在管理中心中, 转到 "**设置** > **安全 & 隐私** > 权限**访问**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-218">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e5296-219">选择 "**管理访问策略和请求**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="e5296-220">选择 "**配置策略**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-220">Select **Configure policies**.</span></span>

5. <span data-ttu-id="e5296-221">选择要删除的策略, 然后选择 "**删除策略**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-221">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="e5296-222">选择 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-222">Select **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="e5296-223">使用 Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5296-223">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="e5296-224">在 Exchange Online Powershell 中运行以下命令以删除特权访问策略:</span><span class="sxs-lookup"><span data-stu-id="e5296-224">Run the following command in Exchange Online Powershell to delete a privileged access policy:</span></span>

```
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="e5296-225">禁用 Office 365 中的特权访问</span><span class="sxs-lookup"><span data-stu-id="e5296-225">Disable privileged access in Office 365</span></span>

<span data-ttu-id="e5296-p115">如果需要, 您可以为您的组织禁用特权访问管理。禁用特权访问不会删除任何关联的审批策略或审批者组。</span><span class="sxs-lookup"><span data-stu-id="e5296-p115">If needed, you can disable privileged access management for your organization. Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="e5296-228">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="e5296-228">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="e5296-229">使用组织中的管理员帐户的凭据登录[Microsoft 365 管理中心](https://portal.office.com)。</span><span class="sxs-lookup"><span data-stu-id="e5296-229">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="e5296-230">在管理中心中, 转到 "**设置** > **安全 & 隐私** > 权限**访问**"。</span><span class="sxs-lookup"><span data-stu-id="e5296-230">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="e5296-231">启用 "**需要批准以进行特权访问**控制"。</span><span class="sxs-lookup"><span data-stu-id="e5296-231">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="e5296-232">使用 Exchange 管理 PowerShell</span><span class="sxs-lookup"><span data-stu-id="e5296-232">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="e5296-233">在 Exchange Online Powershell 中运行以下命令, 以禁用特权访问:</span><span class="sxs-lookup"><span data-stu-id="e5296-233">Run the following command in Exchange Online Powershell to disable privileged access:</span></span>

```
Disable-ElevatedAccessControl
```