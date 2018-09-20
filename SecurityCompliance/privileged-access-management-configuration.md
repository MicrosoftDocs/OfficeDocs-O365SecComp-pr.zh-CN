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
ms.openlocfilehash: 6494505554a02f005df8f45839c9575094acbf1a
ms.sourcegitcommit: d31904e81f81d0fba75309a2bc8bbfb05565a0b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2018
ms.locfileid: "24055247"
---
# <a name="configuring-privileged-access-management-in-office-365"></a><span data-ttu-id="026df-103">Office 365 中配置的访问权限的管理</span><span class="sxs-lookup"><span data-stu-id="026df-103">Configuring privileged access management in Office 365</span></span>

> [!IMPORTANT]
> <span data-ttu-id="026df-104">本主题介绍了部署和配置指南仅当前 Office 365 E5 和高级合规性 Sku 中可用的功能。</span><span class="sxs-lookup"><span data-stu-id="026df-104">This topic covers deployment and configuration guidance for features only currently available in Office 365 E5 and Advanced Compliance SKUs.</span></span>

<span data-ttu-id="026df-p101">本主题将指导您完成启用和配置 Office 365 组织中的访问权限的管理。您可以使用管理和使用的 Microsoft 365 Admin Center 或 Exchange Management PowerShell 特权访问。</span><span class="sxs-lookup"><span data-stu-id="026df-p101">This topic will guide you through enabling and configuring privileged access management in your Office 365 organization. You can use either the the Microsoft 365 Admin Center or Exchange Management PowerShell to manage and use privileged access.</span></span> 

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="026df-107">启用和配置访问权限的管理</span><span class="sxs-lookup"><span data-stu-id="026df-107">Enable and configure privileged access management</span></span>

<span data-ttu-id="026df-108">请按照下列步骤设置和使用 Office 365 组织中的访问权限：</span><span class="sxs-lookup"><span data-stu-id="026df-108">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="026df-109">步骤 1： 创建审批者组</span><span class="sxs-lookup"><span data-stu-id="026df-109">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="026df-p102">在开始使用最小特权 access 之前，决定谁将具有审批授权的传入请求访问提升特权的任务。审批者的组的一部分的任何用户都将能够批准访问请求。这被启用的 Office 365 中创建启用邮件的安全组。</span><span class="sxs-lookup"><span data-stu-id="026df-p102">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="026df-113">步骤 2： 启用访问权限</span><span class="sxs-lookup"><span data-stu-id="026df-113">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="026df-114">需要显式打开 Office 365 中使用的默认审批者组和包括要排除的访问权限的管理访问控制从系统帐户的一组访问权限。</span><span class="sxs-lookup"><span data-stu-id="026df-114">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="026df-115">步骤 3： 创建访问策略</span><span class="sxs-lookup"><span data-stu-id="026df-115">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="026df-p103">创建审批策略允许您定义的范围限制在各项任务的特定审批要求。**自动**或**手动**了审批类型选项。</span><span class="sxs-lookup"><span data-stu-id="026df-p103">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks. The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="026df-118">步骤 4： 提交/批准特权的访问请求</span><span class="sxs-lookup"><span data-stu-id="026df-118">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="026df-p104">启用之后，特权访问需要执行任何任务已定义的关联的审批策略审批。无需执行中包含的任务的用户的审批策略必须请求，并让执行任务所需的权限授予访问审核。</span><span class="sxs-lookup"><span data-stu-id="026df-p104">Once enabled, privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="026df-p105">授予审批后，请求的用户可以执行预期的任务并特权的 access 将授权，并对代表用户执行任务。审批保持有效的请求持续时间 （默认持续时间是 4 个小时），在此期间请求者可以预期的任务多次执行。所有此类执行的记录，并使其可供安全性和合规性审核。</span><span class="sxs-lookup"><span data-stu-id="026df-p105">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on users’ behalf. The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times. All such executions are logged and made available for security and compliance auditing.</span></span> 

> [!NOTE]
> <span data-ttu-id="026df-p106">如果您想要使用 Exchange Management PowerShell 启用和配置访问权限，请按照[连接到 Exchange Online PowerShell 中使用多因素身份验证](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps)连接到 Exchange Online PowerShell 中使用 Office 365 中的步骤凭据。不需要启用多重身份验证您的 Office 365 组织使用的步骤同时连接到 Exchange Online PowerShell 中启用访问权限。将与多因素身份验证连接创建由授权的访问权限，登录您的请求的 OAuth 令牌。</span><span class="sxs-lookup"><span data-stu-id="026df-p106">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials. You do not need to enable multi-factor authentication for your Office 365 organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell. Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="026df-127"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="026df-127"></span></span>

## <a name="step-1---create-an-approvers-group"></a><span data-ttu-id="026df-128">步骤 1-创建审批者组</span><span class="sxs-lookup"><span data-stu-id="026df-128">Step 1 - Create an approver's group</span></span>

1. <span data-ttu-id="026df-129">登录到[Microsoft 365 Admin Center](https://portal.office.com)使用您的组织中的管理帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="026df-129">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="026df-130">在管理中心，转到**组** > **添加组**。</span><span class="sxs-lookup"><span data-stu-id="026df-130">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="026df-131">选择**已启用邮件的安全组**的组类型，然后完成新建组的**名称**、**组电子邮件地址**和**说明**字段。</span><span class="sxs-lookup"><span data-stu-id="026df-131">Select the **mail-enabled security group** group type and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="026df-p107">保存组。可能需要几分钟，以便完全配置并显示在 Office 365 管理中心中的组。</span><span class="sxs-lookup"><span data-stu-id="026df-p107">Save the group. It may take a few minutes for the group to be fully configured and to appear in the Office 365 Admin Center.</span></span>

5. <span data-ttu-id="026df-134">选择新的审批者组，然后选择**编辑**以将用户添加到组。</span><span class="sxs-lookup"><span data-stu-id="026df-134">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="026df-135">保存组。</span><span class="sxs-lookup"><span data-stu-id="026df-135">Save the group.</span></span>

<span data-ttu-id="026df-136"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="026df-136"></span></span>

## <a name="step-2---enable-privileged-access"></a><span data-ttu-id="026df-137">步骤 2-启用访问权限</span><span class="sxs-lookup"><span data-stu-id="026df-137">Step 2 - Enable privileged access</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="026df-138">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="026df-138">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="026df-139">登录到[Microsoft 365 Admin Center](https://portal.office.com)使用您的组织中的管理帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="026df-139">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="026df-140">在管理中心，转到**设置 > 安全和隐私** > **访问权限**。</span><span class="sxs-lookup"><span data-stu-id="026df-140">In the Admin Center, go to **Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="026df-141">启用**需要批准的访问权限**控件。</span><span class="sxs-lookup"><span data-stu-id="026df-141">Enable the **Require approvals for privileged access** control.</span></span>

4. <span data-ttu-id="026df-142">将作为**默认审批者组**的步骤 1 中创建审批者的组分配。</span><span class="sxs-lookup"><span data-stu-id="026df-142">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="026df-143">**保存**并**关闭**。</span><span class="sxs-lookup"><span data-stu-id="026df-143">**Save** and **Close**.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="026df-144">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="026df-144">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="026df-145">若要启用访问权限，并将审批者的组分配 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="026df-145">Run the following command in Exchange Online PowerShell to enable privileged access and to assign the approver's group:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```
<span data-ttu-id="026df-146">示例：</span><span class="sxs-lookup"><span data-stu-id="026df-146">Example:</span></span>
```
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="026df-147">系统帐户由可用于确保组织内的特定自动化功能可以处理不依赖项的情况下访问权限，但建议的此类排除在极那些允许应核准和审核定期。</span><span class="sxs-lookup"><span data-stu-id="026df-147">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="026df-148"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="026df-148"></span></span>

## <a name="step-3---create-an-access-policy"></a><span data-ttu-id="026df-149">步骤 3-创建访问策略</span><span class="sxs-lookup"><span data-stu-id="026df-149">Step 3 - Create an access policy</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="026df-150">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="026df-150">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="026df-151">登录到[Microsoft 365 Admin Center](https://portal.office.com)使用您的组织中的管理帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="026df-151">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="026df-152">在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。</span><span class="sxs-lookup"><span data-stu-id="026df-152">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="026df-153">选择**管理访问策略和请求**。</span><span class="sxs-lookup"><span data-stu-id="026df-153">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="026df-154">选择**配置策略**，然后选择**添加策略**。</span><span class="sxs-lookup"><span data-stu-id="026df-154">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="026df-155">从下拉列表字段中，选择您的组织的相应值：</span><span class="sxs-lookup"><span data-stu-id="026df-155">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="026df-156">**策略类型**： 任务、 角色或角色组</span><span class="sxs-lookup"><span data-stu-id="026df-156">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="026df-157">**策略作用域**： Exchange 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="026df-157">**Policy scope**: Exchange or Office 365</span></span>

    <span data-ttu-id="026df-158">**策略名称**： 从可用的策略选择</span><span class="sxs-lookup"><span data-stu-id="026df-158">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="026df-159">**审批类型**： 手动或自动</span><span class="sxs-lookup"><span data-stu-id="026df-159">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="026df-160">**审核组**： 选择在步骤 1 中创建的审批者组</span><span class="sxs-lookup"><span data-stu-id="026df-160">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="026df-p108">选择**创建**，然后**关闭**。可能需要几分钟，要完全配置并启用的策略。</span><span class="sxs-lookup"><span data-stu-id="026df-p108">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="026df-163">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="026df-163">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="026df-164">运行以下命令在 Exchange Online PowerShell，可以创建并定义审批策略：</span><span class="sxs-lookup"><span data-stu-id="026df-164">Run the following command in Exchange Online PowerShell to create and define an approval policy:</span></span>

```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```
<span data-ttu-id="026df-165">示例：</span><span class="sxs-lookup"><span data-stu-id="026df-165">Example:</span></span>
```
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="026df-166"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="026df-166"></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="026df-167">步骤 4： 提交/批准特权的访问请求</span><span class="sxs-lookup"><span data-stu-id="026df-167">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="026df-168">请求提升授权执行特权的任务</span><span class="sxs-lookup"><span data-stu-id="026df-168">Requesting elevation authorization to execute privileged tasks</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="026df-169">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="026df-169">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="026df-170">登录到[Microsoft 365 Admin Center](https://portal.office.com)使用您的凭据。</span><span class="sxs-lookup"><span data-stu-id="026df-170">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="026df-171">在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。</span><span class="sxs-lookup"><span data-stu-id="026df-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="026df-172">选择**管理访问策略和请求**。</span><span class="sxs-lookup"><span data-stu-id="026df-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="026df-p109">选择**新的请求**。从下拉列表字段中，选择您的组织的相应值：</span><span class="sxs-lookup"><span data-stu-id="026df-p109">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="026df-175">**请求类型**： 任务、 角色或角色组</span><span class="sxs-lookup"><span data-stu-id="026df-175">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="026df-176">**请求作用域**： Exchange</span><span class="sxs-lookup"><span data-stu-id="026df-176">**Request scope**: Exchange</span></span>

    <span data-ttu-id="026df-177">**请求**： 从可用的策略选择</span><span class="sxs-lookup"><span data-stu-id="026df-177">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="026df-178">**持续时间 （小时）**： 请求的访问的小时数</span><span class="sxs-lookup"><span data-stu-id="026df-178">**Duration (hours)**: Number of hours of requested access</span></span>

    <span data-ttu-id="026df-179">**注释**： 注释的文本字段与您的访问请求</span><span class="sxs-lookup"><span data-stu-id="026df-179">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="026df-p110">选择**保存**和**关闭**。您的请求将发送到通过电子邮件的审批者的组。</span><span class="sxs-lookup"><span data-stu-id="026df-p110">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="026df-182">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="026df-182">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="026df-183">运行以下命令在 Exchange Online PowerShell 来创建和提交给审批者的组的审批请求：</span><span class="sxs-lookup"><span data-stu-id="026df-183">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```
<span data-ttu-id="026df-184">示例：</span><span class="sxs-lookup"><span data-stu-id="026df-184">Example:</span></span>
```
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```
### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="026df-185">查看提升请求的状态</span><span class="sxs-lookup"><span data-stu-id="026df-185">View status of elevation requests</span></span>
<span data-ttu-id="026df-186">创建审批请求后，可以在管理中心检查提升请求状态或在 Exchange Management PowerShell 请求使用关联的 id。</span><span class="sxs-lookup"><span data-stu-id="026df-186">After an approval request is created, elevation request status can be reviewed in the Admin Center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="026df-187">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="026df-187">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="026df-188">登录到[Microsoft 365 Admin Center](https://portal.office.com)使用您的凭据。</span><span class="sxs-lookup"><span data-stu-id="026df-188">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="026df-189">在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。</span><span class="sxs-lookup"><span data-stu-id="026df-189">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="026df-190">选择**管理访问策略和请求**。</span><span class="sxs-lookup"><span data-stu-id="026df-190">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="026df-191">选择要筛选**挂起**、**批准**、**拒绝**或**客户密码箱**状态提交的请求的**视图**。</span><span class="sxs-lookup"><span data-stu-id="026df-191">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="026df-192">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="026df-192">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="026df-193">运行以下命令在 Exchange Online PowerShell，可以查看特定的请求 ID 审批请求状态：</span><span class="sxs-lookup"><span data-stu-id="026df-193">Run the following command in Exchange Online PowerShell to view a approval request status for a specific request ID:</span></span>
```
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```
<span data-ttu-id="026df-194">示例：</span><span class="sxs-lookup"><span data-stu-id="026df-194">Example:</span></span>
```
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="026df-195">批准提升授权请求</span><span class="sxs-lookup"><span data-stu-id="026df-195">Approving an elevation authorization request</span></span>
<span data-ttu-id="026df-p111">当创建审批请求时，相关的审批者组的成员将收到的电子邮件通知和可以批准请求 ID 与关联的请求请求者将请求批准或拒绝通过电子邮件通知。</span><span class="sxs-lookup"><span data-stu-id="026df-p111">When an approval request is created, members of the relevant approver group will receive an email notification and can approve the request associated with the request ID. The requestor will be notified of the request approval or denial via email message.</span></span>

#### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="026df-198">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="026df-198">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="026df-199">登录到[Microsoft 365 Admin Center](https://portal.office.com)使用您的凭据。</span><span class="sxs-lookup"><span data-stu-id="026df-199">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using your credentials.</span></span>

2. <span data-ttu-id="026df-200">在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。</span><span class="sxs-lookup"><span data-stu-id="026df-200">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="026df-201">选择**管理访问策略和请求**。</span><span class="sxs-lookup"><span data-stu-id="026df-201">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="026df-202">选择列出的请求，若要查看详细信息，以请求对其执行操作。</span><span class="sxs-lookup"><span data-stu-id="026df-202">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="026df-p112">选择**批准**批准请求或选择**拒绝**以拒绝该请求。以前批准的请求可以通过选择**取消**吊销的访问。</span><span class="sxs-lookup"><span data-stu-id="026df-p112">Select **Approve** to approve the request or select **Deny** to deny the request. Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="using-exchange-management-powershell"></a><span data-ttu-id="026df-205">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="026df-205">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="026df-206">运行以下命令在 Exchange Online PowerShell 批准提升授权请求：</span><span class="sxs-lookup"><span data-stu-id="026df-206">Run the following command in Exchange Online PowerShell to approve an elevation authorization request:</span></span>

```
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```
<span data-ttu-id="026df-207">示例：</span><span class="sxs-lookup"><span data-stu-id="026df-207">Example:</span></span>
```
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="026df-208">运行以下命令在 Exchange Online PowerShell 拒绝提升授权请求：</span><span class="sxs-lookup"><span data-stu-id="026df-208">Run the following command in Exchange Online PowerShell to deny an elevation authorization request:</span></span>

```
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```
<span data-ttu-id="026df-209">示例：</span><span class="sxs-lookup"><span data-stu-id="026df-209">Example:</span></span>
```
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="026df-210">禁用 Office 365 中的特权的访问</span><span class="sxs-lookup"><span data-stu-id="026df-210">Disable privileged access in Office 365</span></span>

<span data-ttu-id="026df-p113">如果需要您可以为组织禁用特权的访问管理。禁用权限访问不会删除任何关联的审批策略或审批者组。</span><span class="sxs-lookup"><span data-stu-id="026df-p113">If needed, you can disable privileged access management for your organization. Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="026df-213">使用 Microsoft 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="026df-213">Using the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="026df-214">登录到[Microsoft 365 Admin Center](https://portal.office.com)使用您的组织中的管理帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="026df-214">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="026df-215">在管理中心，转到**设置** > **安全性和隐私** > **访问权限**。</span><span class="sxs-lookup"><span data-stu-id="026df-215">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="026df-216">启用**需要批准的访问权限**控件。</span><span class="sxs-lookup"><span data-stu-id="026df-216">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="using-exchange-management-powershell"></a><span data-ttu-id="026df-217">使用 Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="026df-217">Using Exchange Management PowerShell</span></span>

<span data-ttu-id="026df-218">运行以下命令在 Exchange Online Powershell，可以禁用授权访问权限：</span><span class="sxs-lookup"><span data-stu-id="026df-218">Run the following command in Exchange Online Powershell to disable privileged access:</span></span>

```
Disable-ElevatedAccessControl
```