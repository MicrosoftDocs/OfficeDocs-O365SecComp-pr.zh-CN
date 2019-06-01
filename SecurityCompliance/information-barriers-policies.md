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
# <a name="define-policies-for-information-barriers-preview"></a><span data-ttu-id="24031-103">定义信息障碍策略 (预览)</span><span class="sxs-lookup"><span data-stu-id="24031-103">Define policies for information barriers (Preview)</span></span>

<span data-ttu-id="24031-104">通过信息障碍, 您可以定义旨在防止某些用户段相互通信的策略, 或允许特定的分段仅与某些其他网段进行通信。</span><span class="sxs-lookup"><span data-stu-id="24031-104">With information barriers, you can define policies that are designed to prevent certain segments of users from communicating with each other, or allow specific segments to communicate only with certain other segments.</span></span> <span data-ttu-id="24031-105">信息屏障策略可帮助您的组织保持遵守相关的行业标准和法规, 并避免潜在的利益冲突。</span><span class="sxs-lookup"><span data-stu-id="24031-105">Information barrier policies can help your organization maintain compliance with relevant industry standards and regulations, and avoid potential conflicts of interest.</span></span> <span data-ttu-id="24031-106">若要了解详细信息, 请参阅[信息障碍 (预览)](information-barriers.md)。</span><span class="sxs-lookup"><span data-stu-id="24031-106">To learn more, see [Information barriers (Preview)](information-barriers.md).</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="24031-107">本文介绍如何规划、定义、实现和管理信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="24031-107">This article describes how to plan, define, implement, and manage information barrier policies.</span></span> <span data-ttu-id="24031-108">涉及几个步骤, 工作流划分为多个部分。</span><span class="sxs-lookup"><span data-stu-id="24031-108">Several steps are involved, and the work flow is divided into several parts.</span></span> <span data-ttu-id="24031-109">在开始定义 (或编辑) 信息屏障策略之前, 请务必阅读[先决条件](#prerequisites)和整个过程。</span><span class="sxs-lookup"><span data-stu-id="24031-109">Make sure to read through the [prerequisites](#prerequisites) and the entire process before you begin defining (or editing) information barrier policies.</span></span>

## <a name="concepts-of-information-barrier-policies"></a><span data-ttu-id="24031-110">信息屏障策略的概念</span><span class="sxs-lookup"><span data-stu-id="24031-110">Concepts of information barrier policies</span></span>

<span data-ttu-id="24031-111">在规划、定义和实施信息屏障策略之前, 请了解相关的基本概念。</span><span class="sxs-lookup"><span data-stu-id="24031-111">Before you plan, define, and implement information barrier policies, get to know the underlying concepts.</span></span> <span data-ttu-id="24031-112">通过信息障碍, 你将使用用户帐户属性、段、信息屏障策略和本文中所述的策略应用程序过程。</span><span class="sxs-lookup"><span data-stu-id="24031-112">With information barriers, you'll work with user account attributes, segments, information barrier policies, and a policy application process described in this article.</span></span> 

- <span data-ttu-id="24031-113">**用户帐户属性**是在 Azure Active Directory (或 Exchange Online) 中定义的。</span><span class="sxs-lookup"><span data-stu-id="24031-113">**User account attributes** are defined in Azure Active Directory (or Exchange Online).</span></span> <span data-ttu-id="24031-114">这些属性可以包括部门、职务、位置、团队名称等。</span><span class="sxs-lookup"><span data-stu-id="24031-114">These attributes can include department, job title, location, team name, etc.</span></span> 

- <span data-ttu-id="24031-115">**分段**在 Office 365 安全 & 合规性中心中使用选定的**用户帐户属性**(如部门、职务、位置、团队名称或任何[受支持的属性](information-barriers-attributes.md)) 进行定义。</span><span class="sxs-lookup"><span data-stu-id="24031-115">**Segments** are defined in the Office 365 Security & Compliance Center using a selected **user account attribute**, such as department, job title, location, team name, or any [supported attribute](information-barriers-attributes.md).</span></span> <span data-ttu-id="24031-116">定义段不会对用户产生影响;它只是设置要定义并应用的信息屏障策略的阶段。</span><span class="sxs-lookup"><span data-stu-id="24031-116">Defining segments does not effect users; it just sets the stage for information barrier policies to be defined and then applied.</span></span>

- <span data-ttu-id="24031-117">**信息屏障策略**定义并分配给各个**网段**。</span><span class="sxs-lookup"><span data-stu-id="24031-117">**Information barrier policies** are defined and assigned to individual **Segments**.</span></span> <span data-ttu-id="24031-118">并不是所有段都分配有策略。</span><span class="sxs-lookup"><span data-stu-id="24031-118">Not all segments will have a policy assigned.</span></span> <span data-ttu-id="24031-119">此外, 不能向任何一个字段分配多个策略。</span><span class="sxs-lookup"><span data-stu-id="24031-119">In addition, no single segment can be assigned more than one policy.</span></span> <span data-ttu-id="24031-120">定义策略时, 可以从以下两种策略中进行选择:</span><span class="sxs-lookup"><span data-stu-id="24031-120">When you define policies, you choose from two kinds of policies:</span></span>
    - <span data-ttu-id="24031-121">防止一个分段与另一个网段通信的策略</span><span class="sxs-lookup"><span data-stu-id="24031-121">Policies that prevent one segment from communicating with another segment</span></span>
    - <span data-ttu-id="24031-122">允许一段仅与某些其他段进行通信的策略</span><span class="sxs-lookup"><span data-stu-id="24031-122">Policies that allow one segment to communicate with only certain other segments</span></span>

    <span data-ttu-id="24031-123">理想情况下, 您将使用最少的策略数, 以确保您的组织符合法律和行业要求。</span><span class="sxs-lookup"><span data-stu-id="24031-123">Ideally, you'll use the minimum number of policies to ensure your organization is compliant with legal and industry requirements.</span></span>

- <span data-ttu-id="24031-124">**策略应用程序**在定义所有信息屏障策略之后完成, 并准备好在您的组织中应用它们。</span><span class="sxs-lookup"><span data-stu-id="24031-124">**Policy application** is done after all information barrier policies are defined, and you are ready to apply them in your organization.</span></span>

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="24031-125">工作流一览</span><span class="sxs-lookup"><span data-stu-id="24031-125">The work flow at a glance</span></span>

|<span data-ttu-id="24031-126">阶段</span><span class="sxs-lookup"><span data-stu-id="24031-126">Phase</span></span>    |<span data-ttu-id="24031-127">涉及的内容</span><span class="sxs-lookup"><span data-stu-id="24031-127">What's involved</span></span>  |
|---------|---------|
|[<span data-ttu-id="24031-128">确保满足先决条件</span><span class="sxs-lookup"><span data-stu-id="24031-128">Make sure prerequisites are met</span></span>](#prerequisites)     |<span data-ttu-id="24031-129">-确认你的订阅包括信息障碍</span><span class="sxs-lookup"><span data-stu-id="24031-129">- Confirm that your subscription includes information barriers</span></span><br/><span data-ttu-id="24031-130">-验证您是否具有定义/编辑段落和策略的必要权限</span><span class="sxs-lookup"><span data-stu-id="24031-130">- Verify that you have the necessary permissions to define/edit segments and policies</span></span><br/><span data-ttu-id="24031-131">-确保目录数据反映组织的结构</span><span class="sxs-lookup"><span data-stu-id="24031-131">- Make sure that your directory data reflects your organization's structure</span></span><br/><span data-ttu-id="24031-132">-确保在 Microsoft 团队中启用了范围内的目录搜索</span><span class="sxs-lookup"><span data-stu-id="24031-132">- Make sure that scoped directory search is enabled in Microsoft Teams</span></span><br/><span data-ttu-id="24031-133">-请确保审核日志记录已打开</span><span class="sxs-lookup"><span data-stu-id="24031-133">- Make sure audit logging is turned on</span></span><br/><span data-ttu-id="24031-134">-使用 PowerShell 执行本文中的任务 (提供示例 cmdlet)</span><span class="sxs-lookup"><span data-stu-id="24031-134">- Use PowerShell to perform the tasks in this article (example cmdlets are provided)</span></span><br/><span data-ttu-id="24031-135">-为 Microsoft 团队中的信息障碍提供管理员同意 (包括步骤)</span><span class="sxs-lookup"><span data-stu-id="24031-135">- Provide admin consent for information barriers in Microsoft Teams (steps are included)</span></span>          |
|[<span data-ttu-id="24031-136">第1部分: 分段组织中的所有用户</span><span class="sxs-lookup"><span data-stu-id="24031-136">Part 1: Segment all the users in your organization</span></span>](#part-1-segment-users)     |<span data-ttu-id="24031-137">-确定所需的策略</span><span class="sxs-lookup"><span data-stu-id="24031-137">- Determine what policies are needed</span></span><br/><span data-ttu-id="24031-138">-创建要定义的段的列表</span><span class="sxs-lookup"><span data-stu-id="24031-138">- Make a list of segments to define</span></span><br/><span data-ttu-id="24031-139">-确定要使用的属性</span><span class="sxs-lookup"><span data-stu-id="24031-139">- Identify which attributes to use</span></span><br/><span data-ttu-id="24031-140">-在策略筛选器方面定义段</span><span class="sxs-lookup"><span data-stu-id="24031-140">- Define segments in terms of policy filters</span></span>        |
|[<span data-ttu-id="24031-141">第2部分: 定义信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="24031-141">Part 2: Define information barrier policies</span></span>](#part-2-define-information-barrier-policies)     |<span data-ttu-id="24031-142">-定义你的策略 (尚不应用)</span><span class="sxs-lookup"><span data-stu-id="24031-142">- Define your policies (do not apply yet)</span></span><br/><span data-ttu-id="24031-143">-从两种类型 (阻止或允许) 中选择</span><span class="sxs-lookup"><span data-stu-id="24031-143">- Choose from two kinds (block or allow)</span></span> |
|[<span data-ttu-id="24031-144">第3部分: 应用信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="24031-144">Part 3: Apply information barrier policies</span></span>](#part-3-apply-information-barrier-policies)     |<span data-ttu-id="24031-145">-将策略设置为活动状态</span><span class="sxs-lookup"><span data-stu-id="24031-145">- Set policies to active status</span></span><br/><span data-ttu-id="24031-146">-运行策略应用程序</span><span class="sxs-lookup"><span data-stu-id="24031-146">- Run the policy application</span></span><br/><span data-ttu-id="24031-147">-验证策略状态</span><span class="sxs-lookup"><span data-stu-id="24031-147">- Verify policy status</span></span>         |
|<span data-ttu-id="24031-148">(根据需要)[编辑段或策略](#edit-a-segment-or-a-policy)</span><span class="sxs-lookup"><span data-stu-id="24031-148">(As needed) [Edit a segment or a policy](#edit-a-segment-or-a-policy)</span></span>     |<span data-ttu-id="24031-149">-编辑分段</span><span class="sxs-lookup"><span data-stu-id="24031-149">- Edit a segment</span></span><br/><span data-ttu-id="24031-150">-编辑或删除策略</span><span class="sxs-lookup"><span data-stu-id="24031-150">- Edit or remove a policy</span></span><br/><span data-ttu-id="24031-151">-运行策略应用程序</span><span class="sxs-lookup"><span data-stu-id="24031-151">- Run the policy application</span></span><br/><span data-ttu-id="24031-152">-验证策略状态</span><span class="sxs-lookup"><span data-stu-id="24031-152">- Verify policy status</span></span>         |
|<span data-ttu-id="24031-153">(根据需要)[故障排除](information-barriers-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="24031-153">(As needed) [Troubleshooting](information-barriers-troubleshooting.md)</span></span>|<span data-ttu-id="24031-154">-当策略未按预期工作时执行操作</span><span class="sxs-lookup"><span data-stu-id="24031-154">- Take action when policies are not working as expected</span></span>|

## <a name="prerequisites"></a><span data-ttu-id="24031-155">先决条件</span><span class="sxs-lookup"><span data-stu-id="24031-155">Prerequisites</span></span>

<span data-ttu-id="24031-156">**目前, 信息屏障功能位于私人预览版中**。</span><span class="sxs-lookup"><span data-stu-id="24031-156">**Currently, the information barrier feature is in private preview**.</span></span> <span data-ttu-id="24031-157">当这些功能普遍可用时, 它们将包含在订阅中, 例如:</span><span class="sxs-lookup"><span data-stu-id="24031-157">When these features are generally available, they'll be included in subscriptions, such as:</span></span>

- <span data-ttu-id="24031-158">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="24031-158">Microsoft 365 E5</span></span>
- <span data-ttu-id="24031-159">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="24031-159">Office 365 E5</span></span>
- <span data-ttu-id="24031-160">Office 365 高级合规版</span><span class="sxs-lookup"><span data-stu-id="24031-160">Office 365 Advanced Compliance</span></span>
- <span data-ttu-id="24031-161">Microsoft 365 E5 信息保护和合规性</span><span class="sxs-lookup"><span data-stu-id="24031-161">Microsoft 365 E5 Information Protection and Compliance</span></span>

<span data-ttu-id="24031-162">有关更多详细信息, 请参阅[合规性解决方案](https://products.office.com/business/security-and-compliance/compliance-solutions)。</span><span class="sxs-lookup"><span data-stu-id="24031-162">For more details, see [Compliance Solutions](https://products.office.com/business/security-and-compliance/compliance-solutions).</span></span>

### <a name="permissions"></a><span data-ttu-id="24031-163">权限</span><span class="sxs-lookup"><span data-stu-id="24031-163">Permissions</span></span>

<span data-ttu-id="24031-164">若要定义或编辑信息障碍策略,**必须为您分配适当的角色**, 如以下某项:</span><span class="sxs-lookup"><span data-stu-id="24031-164">To define or edit information barrier policies, **you must be assigned an appropriate role**, such as one of the following:</span></span>
- <span data-ttu-id="24031-165">Microsoft 365 企业全局管理员</span><span class="sxs-lookup"><span data-stu-id="24031-165">Microsoft 365 Enterprise Global Administrator</span></span>
- <span data-ttu-id="24031-166">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="24031-166">Office 365 Global Administrator</span></span>
- <span data-ttu-id="24031-167">合规性管理员</span><span class="sxs-lookup"><span data-stu-id="24031-167">Compliance Administrator</span></span>
- <span data-ttu-id="24031-168">IB 合规性管理 (这是一个新角色!)</span><span class="sxs-lookup"><span data-stu-id="24031-168">IB Compliance Management (this is a new role!)</span></span>

<span data-ttu-id="24031-169">若要了解有关角色和权限的详细信息, 请参阅[Office 365 Security & 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="24031-169">To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
       
### <a name="directory-data"></a><span data-ttu-id="24031-170">目录数据</span><span class="sxs-lookup"><span data-stu-id="24031-170">Directory data</span></span>

<span data-ttu-id="24031-171">**确保您的组织的结构已反映在目录数据中**。</span><span class="sxs-lookup"><span data-stu-id="24031-171">**Make sure that your organization's structure is reflected in directory data**.</span></span> <span data-ttu-id="24031-172">为此, 请确保在 Azure Active Directory (或 Exchange Online) 中正确填充了用户帐户属性, 如组成员身份、部门名称等。</span><span class="sxs-lookup"><span data-stu-id="24031-172">To do this, make sure that user account attributes, such as group membership, department name, etc. are populated correctly in Azure Active Directory (or Exchange Online).</span></span> <span data-ttu-id="24031-173">若要了解详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="24031-173">To learn more, see the following resources:</span></span>
- [<span data-ttu-id="24031-174">信息屏障策略的属性 (预览)</span><span class="sxs-lookup"><span data-stu-id="24031-174">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="24031-175">使用 Azure Active Directory 添加或更新用户的配置文件信息</span><span class="sxs-lookup"><span data-stu-id="24031-175">Add or update a user's profile information using Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
- [<span data-ttu-id="24031-176">使用 Office 365 PowerShell 配置用户帐户的属性</span><span class="sxs-lookup"><span data-stu-id="24031-176">Configure user account properties with Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

### <a name="scoped-directory-search"></a><span data-ttu-id="24031-177">作用域目录搜索</span><span class="sxs-lookup"><span data-stu-id="24031-177">Scoped directory search</span></span>

<span data-ttu-id="24031-178">在**定义组织的第一个信息屏障策略之前, 必须先[在 Microsoft 团队中启用范围目录搜索](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)**。</span><span class="sxs-lookup"><span data-stu-id="24031-178">**Before you define your organization's first information barrier policy, you must [enable scoped directory search in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)**.</span></span> <span data-ttu-id="24031-179">在设置或定义信息屏障策略之前, 请先等待至少24小时后, 再启用范围目录搜索。</span><span class="sxs-lookup"><span data-stu-id="24031-179">Wait at least 24 hours after enabling scoped directory search before you set up or define information barrier policies.</span></span>

### <a name="audit-logging"></a><span data-ttu-id="24031-180">审核日志记录</span><span class="sxs-lookup"><span data-stu-id="24031-180">Audit logging</span></span>

<span data-ttu-id="24031-181">为了查找策略应用程序的状态, 审核日志记录必须处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="24031-181">In order to look up the status of a policy application, audit logging must be turned on.</span></span> <span data-ttu-id="24031-182">我们建议您在开始定义段或策略之前执行此操作。</span><span class="sxs-lookup"><span data-stu-id="24031-182">We recommend doing this before you begin to define segments or policies.</span></span> <span data-ttu-id="24031-183">若要了解详细信息, 请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="24031-183">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

### <a name="powershell"></a><span data-ttu-id="24031-184">PowerShell</span><span class="sxs-lookup"><span data-stu-id="24031-184">PowerShell</span></span>

<span data-ttu-id="24031-185">**目前, 信息屏障策略在 Office 365 Security & 合规性中心 (使用 PowerShell cmdlet) 中进行定义和管理**。</span><span class="sxs-lookup"><span data-stu-id="24031-185">**Currently, information barrier policies are defined and managed in the Office 365 Security & Compliance Center using PowerShell cmdlets**.</span></span> <span data-ttu-id="24031-186">虽然本文中提供了几个方案和示例, 但您需要熟悉 PowerShell cmdlet 和参数。</span><span class="sxs-lookup"><span data-stu-id="24031-186">Although several scenarios and examples are provided in this article, you'll need to be familiar with PowerShell cmdlets and parameters.</span></span> 

<span data-ttu-id="24031-187">[连接到 Office 365 安全 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="24031-187">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

### <a name="provide-admin-consent-for-information-barriers-in-microsoft-teams"></a><span data-ttu-id="24031-188">为 Microsoft 团队中的信息障碍提供管理员同意</span><span class="sxs-lookup"><span data-stu-id="24031-188">Provide admin consent for information barriers in Microsoft Teams</span></span>

<span data-ttu-id="24031-189">使用以下过程可使信息障碍策略在 Microsoft 团队中按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="24031-189">Use the following procedure to enable information barrier policies to work as expected in Microsoft Teams.</span></span> 

<span data-ttu-id="24031-190">例如, 当您的策略已准备就绪时, 信息障碍可以从聊天会话中删除他们不应处于其中的人。</span><span class="sxs-lookup"><span data-stu-id="24031-190">For example, when your policies are in place, information barriers can remove people from chat sessions they are not supposed to be in.</span></span> <span data-ttu-id="24031-191">这有助于确保您的组织遵守策略和管理法规。</span><span class="sxs-lookup"><span data-stu-id="24031-191">This helps ensure your organization remains compliant with policies and regulations.</span></span> 

1. <span data-ttu-id="24031-192">运行以下 PowerShell cmdlet:</span><span class="sxs-lookup"><span data-stu-id="24031-192">Run the following PowerShell cmdlets:</span></span>

    ```
    Login-AzureRmAccount 
    $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
    $sp=Get-AzureRmADServicePrincipal -ServicePrincipalName $appId
    if ($sp -eq $null) { New-AzureRmADServicePrincipal -ApplicationId $appId }
    Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
    ```

2. <span data-ttu-id="24031-193">出现提示时, 使用您的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="24031-193">When prompted, sign in using your work or school account for Office 365.</span></span>

3. <span data-ttu-id="24031-194">在 "**请求的权限**" 对话框中, 检查信息, 然后选择 "**接受**"。</span><span class="sxs-lookup"><span data-stu-id="24031-194">In the **Permissions requested** dialog box, review the information, and then choose **Accept**.</span></span>

## <a name="part-1-segment-users"></a><span data-ttu-id="24031-195">第1部分: 分段用户</span><span class="sxs-lookup"><span data-stu-id="24031-195">Part 1: Segment users</span></span>

<span data-ttu-id="24031-196">在此阶段中, 您将确定所需的策略, 创建要定义的段的列表, 然后定义您的段落。</span><span class="sxs-lookup"><span data-stu-id="24031-196">During this phase, you determine what policies are needed, make a list of segments to define, and then define your segments.</span></span>

### <a name="determine-what-policies-are-needed"></a><span data-ttu-id="24031-197">确定所需的策略</span><span class="sxs-lookup"><span data-stu-id="24031-197">Determine what policies are needed</span></span>

<span data-ttu-id="24031-198">考虑法律和行业法规, 谁是组织中需要信息障碍策略的组？</span><span class="sxs-lookup"><span data-stu-id="24031-198">Considering legal and industry regulations, who are the groups within your organization who will need information barrier policies?</span></span> <span data-ttu-id="24031-199">创建列表。</span><span class="sxs-lookup"><span data-stu-id="24031-199">Make a list.</span></span> <span data-ttu-id="24031-200">是否有任何组应阻止其与另一个组进行通信？</span><span class="sxs-lookup"><span data-stu-id="24031-200">Are there any groups who should be prevented from communicating with another group?</span></span> <span data-ttu-id="24031-201">是否有任何组应允许只与一个或两个其他组进行通信？</span><span class="sxs-lookup"><span data-stu-id="24031-201">Are there any groups that should be allowed to communicate only with one or two other groups?</span></span> <span data-ttu-id="24031-202">考虑您需要的策略是否属于两个组中的一个:</span><span class="sxs-lookup"><span data-stu-id="24031-202">Think about the policies you need as belonging to one of two groups:</span></span>
- <span data-ttu-id="24031-203">阻止一个组与另一个组进行通信的**阻止策略**</span><span class="sxs-lookup"><span data-stu-id="24031-203">**Blocking policies** that prevent one group from communicating with another group</span></span>
- <span data-ttu-id="24031-204">**允许**特定组仅与特定的其他组进行通信的策略。</span><span class="sxs-lookup"><span data-stu-id="24031-204">**Allow policies** that allow certain groups to communicate with only certain other groups.</span></span>

<span data-ttu-id="24031-205">当您拥有组和策略的初始列表时, 请继续确定所需的段。</span><span class="sxs-lookup"><span data-stu-id="24031-205">When you have your initial list of groups and policies, proceed to identify the segments you'll need.</span></span>

<span data-ttu-id="24031-206">(请参阅本文中[的示例: Contoso 的部门和规划](#contosos-departments-and-plan)。)</span><span class="sxs-lookup"><span data-stu-id="24031-206">(See [Example: Contoso's departments and plan](#contosos-departments-and-plan) in this article.)</span></span>

### <a name="identify-segments"></a><span data-ttu-id="24031-207">标识段</span><span class="sxs-lookup"><span data-stu-id="24031-207">Identify segments</span></span>

<span data-ttu-id="24031-208">除了您的初始策略列表之外, 请为您的组织创建一个段落列表。</span><span class="sxs-lookup"><span data-stu-id="24031-208">In addition to your initial list of policies, make a list of segments for your organization.</span></span> <span data-ttu-id="24031-209">组织中的每个用户都应属于某个分段, 并且任何用户都不应属于两个或多个分段。</span><span class="sxs-lookup"><span data-stu-id="24031-209">Every user in your organization should belong to a segment, and no user should belong to two or more segments.</span></span> <span data-ttu-id="24031-210">每个段只能应用一个信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="24031-210">Each segment can have only one information barrier policy applied.</span></span> 

<span data-ttu-id="24031-211">确定您的组织的目录数据中将用来定义段落的属性。</span><span class="sxs-lookup"><span data-stu-id="24031-211">Determine which attributes in your organization's directory data you'll use to define segments.</span></span> <span data-ttu-id="24031-212">您可以使用 "*部门*"、" *MemberOf*" 或任何受支持的属性。</span><span class="sxs-lookup"><span data-stu-id="24031-212">You can use *Department*, *MemberOf*, or any of the supported attributes.</span></span> <span data-ttu-id="24031-213">请确保您为所有用户选择的属性中具有值。</span><span class="sxs-lookup"><span data-stu-id="24031-213">Make sure that you have values in the attribute you select for all users.</span></span> <span data-ttu-id="24031-214">若要查看受支持的属性的列表, 请参阅[信息障碍策略的属性 (预览)](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="24031-214">To see a list of supported attributes, refer to [Attributes for information barrier policies (Preview)](information-barriers-attributes.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24031-215">在**继续下一节之前, 请确保您的目录数据具有可用于定义段的属性的值**。</span><span class="sxs-lookup"><span data-stu-id="24031-215">**Before you proceed to the next section, make sure your directory data has values for attributes that you can use to define segments**.</span></span> <span data-ttu-id="24031-216">如果您的目录数据没有要使用的属性的值, 则必须更新所有用户帐户, 以便在继续进行信息障碍之前将该信息包括在内。</span><span class="sxs-lookup"><span data-stu-id="24031-216">If your directory data does not have values for the attributes you want to use, then all user accounts must be updated to include that information before you proceed with information barriers.</span></span> <span data-ttu-id="24031-217">若要获取有关此方面的帮助, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="24031-217">To get help with this, see the following resources:</span></span><br/><span data-ttu-id="24031-218">- [使用 Office 365 PowerShell 配置用户帐户属性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="24031-218">- [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)</span></span><br/><span data-ttu-id="24031-219">- [使用 Azure Active Directory 添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="24031-219">- [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span></span>

### <a name="define-segments-using-powershell"></a><span data-ttu-id="24031-220">使用 PowerShell 定义段</span><span class="sxs-lookup"><span data-stu-id="24031-220">Define segments using PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24031-221">**请确保您的段不重叠**。</span><span class="sxs-lookup"><span data-stu-id="24031-221">**Make sure that your segments do not overlap**.</span></span> <span data-ttu-id="24031-222">组织中的每个用户都应属于一个 (且只有一个) 分段。</span><span class="sxs-lookup"><span data-stu-id="24031-222">Each user in your organization should belong to one (and only one) segment.</span></span> <span data-ttu-id="24031-223">任何用户都不应属于两个或多个段。</span><span class="sxs-lookup"><span data-stu-id="24031-223">No user should belong to two or more segments.</span></span> <span data-ttu-id="24031-224">应为组织中的所有用户定义分段。</span><span class="sxs-lookup"><span data-stu-id="24031-224">Segments should be defined for all users in your organization.</span></span> <span data-ttu-id="24031-225">(请参阅本文中[的 Contoso 定义的部分](#contosos-defined-segments)。)</span><span class="sxs-lookup"><span data-stu-id="24031-225">(See [Example: Contoso's defined segments](#contosos-defined-segments) in this article.)</span></span>

1. <span data-ttu-id="24031-226">若要定义组织段, 请使用**OrganizationSegment** Cmdlet 和**UserGroupFilter**参数, 该参数对应于要使用的[属性](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="24031-226">To define an organizational segment, use the **New-OrganizationSegment** cmdlet with the **UserGroupFilter** parameter that corresponds to the [attribute](information-barriers-attributes.md) you want to use.</span></span> 

    <span data-ttu-id="24031-227">语法`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="24031-227">Syntax: `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

    <span data-ttu-id="24031-228">示例：`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`</span><span class="sxs-lookup"><span data-stu-id="24031-228">Example: `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`</span></span>

    <span data-ttu-id="24031-229">在此示例中, 使用*hr*("部门" 属性中的值) 定义名为*hr*的字段。</span><span class="sxs-lookup"><span data-stu-id="24031-229">In this example, a segment called *HR* is defined using *HR*, a value in the Department attribute.</span></span>

2. <span data-ttu-id="24031-230">对要定义的每个段重复步骤1。</span><span class="sxs-lookup"><span data-stu-id="24031-230">Repeat step 1 for each segment you want to define.</span></span>

    <span data-ttu-id="24031-231">在运行每个 cmdlet 之后, 您应该会看到有关新段的详细信息列表。</span><span class="sxs-lookup"><span data-stu-id="24031-231">After you run each cmdlet, you should see a list of details about the new segment.</span></span> <span data-ttu-id="24031-232">详细信息包括段的类型、创建者或最后修改的人, 等等。</span><span class="sxs-lookup"><span data-stu-id="24031-232">Details include the segment's type, who created or last modified it, and so on.</span></span> 

<span data-ttu-id="24031-233">定义了分段后, 请继续定义信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="24031-233">After you have defined your segments, proceed to define information barrier policies.</span></span>

## <a name="part-2-define-information-barrier-policies"></a><span data-ttu-id="24031-234">第2部分: 定义信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="24031-234">Part 2: Define information barrier policies</span></span>

<span data-ttu-id="24031-235">在您的用户区段列表和要定义的信息屏障策略中, 选择一个方案, 然后按照步骤操作。</span><span class="sxs-lookup"><span data-stu-id="24031-235">With your list of user segments and the information barrier policies you want to define, select a scenario, and then follow the steps.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="24031-236">请**确保在定义策略时, 不会向一个分段分配多个策略**。</span><span class="sxs-lookup"><span data-stu-id="24031-236">**Make sure that as you define policies, you do not assign more than one policy to a segment**.</span></span> <span data-ttu-id="24031-237">例如, 如果您为 " *sales*" 一段定义一个策略, 则不要为*sales*定义其他策略。</span><span class="sxs-lookup"><span data-stu-id="24031-237">For example, if you define one policy for a segment called *Sales*, do not define an additional policy for *Sales*.</span></span> 

<span data-ttu-id="24031-238">确定是否需要阻止某些网段之间的通信, 或将通信限制到某些段。</span><span class="sxs-lookup"><span data-stu-id="24031-238">Determine whether you need to prevent communications between certain segments, or limit communications to certain segments.</span></span> <span data-ttu-id="24031-239">在下面的方案中进行选择以定义策略。</span><span class="sxs-lookup"><span data-stu-id="24031-239">Choose between the scenarios below to define your policies.</span></span>

- [<span data-ttu-id="24031-240">方案 1: 阻止段之间的通信</span><span class="sxs-lookup"><span data-stu-id="24031-240">Scenario 1: Block communications between segments</span></span>](#scenario-1-block-communications-between-segments)
- [<span data-ttu-id="24031-241">方案 2: 允许段仅与一个其他段进行通信</span><span class="sxs-lookup"><span data-stu-id="24031-241">Scenario 2: Allow a segment to communicate only with one other segment</span></span>](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!NOTE]
> <span data-ttu-id="24031-242">在定义信息障碍策略时, 请确保将这些策略设置为非活动状态, 直到您准备好应用它们。</span><span class="sxs-lookup"><span data-stu-id="24031-242">As you define information barrier policies, make sure to set those policies to inactive status until you are ready to apply them.</span></span> <span data-ttu-id="24031-243">定义 (或编辑) 策略不会影响用户, 直到这些策略设置为 "活动状态", 然后应用。</span><span class="sxs-lookup"><span data-stu-id="24031-243">Defining (or editing) policies does not affect users until those policies are set to active status and then applied.</span></span>

<span data-ttu-id="24031-244">(请参阅本文中[的示例: Contoso 的信息屏障策略](#contosos-information-barrier-policies)。)</span><span class="sxs-lookup"><span data-stu-id="24031-244">(See [Example: Contoso's information barrier policies](#contosos-information-barrier-policies) in this article.)</span></span>

### <a name="scenario-1-block-communications-between-segments"></a><span data-ttu-id="24031-245">方案 1: 阻止段之间的通信</span><span class="sxs-lookup"><span data-stu-id="24031-245">Scenario 1: Block communications between segments</span></span>

<span data-ttu-id="24031-246">当您想要阻止多个段相互通信时, 可以定义两个策略: 每个方向一个。</span><span class="sxs-lookup"><span data-stu-id="24031-246">When you want to block segments from communicating with each other, you define two policies: one for each direction.</span></span> <span data-ttu-id="24031-247">每个策略仅阻止单向通信。</span><span class="sxs-lookup"><span data-stu-id="24031-247">Each policy blocks communication one way only.</span></span>

<span data-ttu-id="24031-248">例如, 假设您想要阻止段 A 和 Segment B 之间的通信。在这种情况下, 您可以定义一个策略, 阻止段 A 与段 B 通信, 然后定义另一个策略以防止段 B 与段 A 通信。</span><span class="sxs-lookup"><span data-stu-id="24031-248">For example, suppose you want to block communications between Segment A and Segment B. In this case, you define one policy preventing Segment A from communicating with Segment B, and then define a second policy to prevent Segment B from communicating with Segment A.</span></span>

1. <span data-ttu-id="24031-249">若要定义您的第一个阻止策略, 请将**InformationBarrierPolicy** Cmdlet 与**SegmentsBlocked**参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="24031-249">To define your first blocking policy, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsBlocked** parameter.</span></span> 

    <span data-ttu-id="24031-250">语法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsBlocked "segmentname"`</span><span class="sxs-lookup"><span data-stu-id="24031-250">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsBlocked "segmentname"`</span></span>

    <span data-ttu-id="24031-251">示例：`New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="24031-251">Example: `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`</span></span>

    <span data-ttu-id="24031-252">在此示例中, 我们定义了名为 "*销售*" 的部门的名为 "销售 *-研究*" 的策略。</span><span class="sxs-lookup"><span data-stu-id="24031-252">In this example, we defined a policy called *Sales-Research* for a segment called *Sales*.</span></span> <span data-ttu-id="24031-253">在活动和应用后, 此策略将阻止*销售*人员与名为 "*研究*" 的部门中的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="24031-253">When active and applied, this policy prevents people in *Sales* from communicating with people in a segment called *Research*.</span></span>

2. <span data-ttu-id="24031-254">若要定义您的第二个阻塞段, 请再次将**InformationBarrierPolicy** Cmdlet 与**SegmentsBlocked**参数一起使用, 这次将段反向。</span><span class="sxs-lookup"><span data-stu-id="24031-254">To define your second blocking segment, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsBlocked** parameter again, this time with the segments reversed.</span></span>

    <span data-ttu-id="24031-255">示例：`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="24031-255">Example: `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`</span></span>

    <span data-ttu-id="24031-256">在此示例中, 我们定义了一个名为 "*研究部*" 的策略, 以防止与 "销售" 通信的研究。</span><span class="sxs-lookup"><span data-stu-id="24031-256">In this example, we defined a policy called *Research-Sales* to prevent Research from communicating with Sales.</span></span>
 
2. <span data-ttu-id="24031-257">继续执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="24031-257">Proceed to one of the following:</span></span>

   - <span data-ttu-id="24031-258">(如果需要)[定义一个策略以允许某个分段仅与另一个网段进行通信](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)</span><span class="sxs-lookup"><span data-stu-id="24031-258">(If needed) [Define a policy to allow a segment to communicate only with one other segment](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)</span></span> 
   - <span data-ttu-id="24031-259">(在定义了所有策略之后)[应用信息屏障策略](#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="24031-259">(After all your policies are defined) [Apply information barrier policies](#part-3-apply-information-barrier-policies)</span></span>

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a><span data-ttu-id="24031-260">方案 2: 允许段仅与一个其他段进行通信</span><span class="sxs-lookup"><span data-stu-id="24031-260">Scenario 2: Allow a segment to communicate only with one other segment</span></span>

1. <span data-ttu-id="24031-261">若要允许一个分段仅与一个其他网段通信, 请使用**InformationBarrierPolicy** Cmdlet 和**SegmentsAllowed**参数。</span><span class="sxs-lookup"><span data-stu-id="24031-261">To allow one segment to communicate with only one other segment, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsAllowed** parameter.</span></span> 

    <span data-ttu-id="24031-262">语法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname"`</span><span class="sxs-lookup"><span data-stu-id="24031-262">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname"`</span></span>

    <span data-ttu-id="24031-263">示例：`New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="24031-263">Example: `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`</span></span>

    <span data-ttu-id="24031-264">在此示例中, 我们为 "*制造业*" 字段定义了称为 "制造业 *-HR* " 的策略。</span><span class="sxs-lookup"><span data-stu-id="24031-264">In this example, we defined a policy called *Manufacturing-HR* for a segment called *Manufacturing*.</span></span> <span data-ttu-id="24031-265">在活动和应用后, 此策略允许在*制造业*中的人员仅与称为*HR*的部门中的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="24031-265">When active and applied, this policy allows people in *Manufacturing* to communicate only with people in a segment called *HR*.</span></span> <span data-ttu-id="24031-266">(在这种情况下, 制造无法与不属于 HR 的用户进行通信。)</span><span class="sxs-lookup"><span data-stu-id="24031-266">(In this case, Manufacturing cannot communicate with users who are not part of HR.)</span></span>

    <span data-ttu-id="24031-267">**如果需要, 可以使用此 cmdlet 指定多个段, 如下面的两个示例中所示。**</span><span class="sxs-lookup"><span data-stu-id="24031-267">**If needed, you can specify multiple segments with this cmdlet, as shown in the following two examples.**</span></span>

    <span data-ttu-id="24031-268">语法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname, segmentname"`</span><span class="sxs-lookup"><span data-stu-id="24031-268">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segmentname" -SegmentsAllowed "segmentname, segmentname"`</span></span>

    <span data-ttu-id="24031-269">**示例 1: 定义一个策略以允许多个段仅与一个其他段进行通信**</span><span class="sxs-lookup"><span data-stu-id="24031-269">**Example 1: Define a policy to allow multiple segments to communicate with only one other segment**</span></span>

    `New-InformationBarrierPolicy -Name "ResearchManufacturing-HR" -AssignedSegment "Research, Manufacturing" -SegmentsAllowed "HR" -State Inactive`

    <span data-ttu-id="24031-270">在此示例中, 我们定义了一个策略, 允许*信息检索*和*制造*网段仅与*HR*进行通信。</span><span class="sxs-lookup"><span data-stu-id="24031-270">In this example, we defined a policy that allows the *Research* and *Manufacturing* segments to communicate only with *HR*.</span></span>

    <span data-ttu-id="24031-271">**示例 2: 定义一个策略以允许多个段仅与某些其他段进行通信**</span><span class="sxs-lookup"><span data-stu-id="24031-271">**Example 2: Define a policy to allow multiple segments to communicate with only certain other segments**</span></span>    

    `New-InformationBarrierPolicy -Name "SalesMarketing-HRManufacturing" -AssignedSegment "Sales, Marketing" -SegmentsAllowed "HR, Manufacturing" -State Inactive`

    <span data-ttu-id="24031-272">在此示例中, 我们定义了一个允许*销售*和*市场营销*部门仅与*HR*和*制造业*进行通信的策略。</span><span class="sxs-lookup"><span data-stu-id="24031-272">In this example, we defined a policy that allows the *Sales* and *Marketing* segments to communicate with only *HR* and *Manufacturing*.</span></span>

    <span data-ttu-id="24031-273">对于要定义的每个策略, 请重复此步骤, 以允许特定段仅与特定的其他特定段进行通信。</span><span class="sxs-lookup"><span data-stu-id="24031-273">Repeat this step for each policy you want to define to allow specific segments to communicate with only certain other specific segments.</span></span>

2. <span data-ttu-id="24031-274">继续执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="24031-274">Proceed to one of the following:</span></span>

   - <span data-ttu-id="24031-275">(如果需要)[定义策略以阻止网段之间的通信](#scenario-1-block-communications-between-segments)</span><span class="sxs-lookup"><span data-stu-id="24031-275">(If needed) [Define a policy to block communications between segments](#scenario-1-block-communications-between-segments)</span></span> 
   - <span data-ttu-id="24031-276">(在定义了所有策略之后)[应用信息屏障策略](#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="24031-276">(After all your policies are defined) [Apply information barrier policies](#part-3-apply-information-barrier-policies)</span></span>

## <a name="part-3-apply-information-barrier-policies"></a><span data-ttu-id="24031-277">第3部分: 应用信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="24031-277">Part 3: Apply information barrier policies</span></span>

<span data-ttu-id="24031-278">信息屏障策略在将其设置为 "活动状态" 之前不起作用, 然后应用这些策略。</span><span class="sxs-lookup"><span data-stu-id="24031-278">Information barrier policies are not in effect until you set them to active status, and then apply the policies.</span></span>

1. <span data-ttu-id="24031-279">使用**InformationBarrierPolicy** cmdlet 可以查看已定义的策略的列表。</span><span class="sxs-lookup"><span data-stu-id="24031-279">Use the **Get-InformationBarrierPolicy** cmdlet to see a list of policies that have been defined.</span></span> <span data-ttu-id="24031-280">记下每个策略的状态和标识 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="24031-280">Note the status and identity (GUID) of each policy.</span></span>

    <span data-ttu-id="24031-281">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="24031-281">Syntax: `Get-InformationBarrierPolicy`</span></span>

2. <span data-ttu-id="24031-282">若要将策略设置为活动状态, 请使用带有**Identity**参数的**InformationBarrierPolicy** Cmdlet, 并将**State**参数设置为 "**活动**"。</span><span class="sxs-lookup"><span data-stu-id="24031-282">To set a policy to active status, use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and the **State** parameter set to **Active**.</span></span> 

    <span data-ttu-id="24031-283">语法`Set-InformationBarrierPolicy -Identity GUID -State Active`</span><span class="sxs-lookup"><span data-stu-id="24031-283">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Active`</span></span>

    <span data-ttu-id="24031-284">示例：`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`</span><span class="sxs-lookup"><span data-stu-id="24031-284">Example: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`</span></span>
    
    <span data-ttu-id="24031-285">在此示例中, 我们将 GUID 为 " *43c37853-ea10-4b90-a23d-ab8c93772471* " 的信息屏障策略设置为 "活动" 状态。</span><span class="sxs-lookup"><span data-stu-id="24031-285">In this example, we set an information barrier policy that has the GUID *43c37853-ea10-4b90-a23d-ab8c93772471* to active status.</span></span>

    <span data-ttu-id="24031-286">根据需要对每个策略重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="24031-286">Repeat this step as appropriate for each policy.</span></span>

3. <span data-ttu-id="24031-287">完成将信息屏障策略设置为活动状态后, 请使用**InformationBarrierPoliciesApplication** Cmdlet 在 Office 365 安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="24031-287">When you have finished setting your information barrier policies to active status, use the **Start-InformationBarrierPoliciesApplication** cmdlet in the Office 365 Security & Compliance Center.</span></span>

    <span data-ttu-id="24031-288">语法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="24031-288">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="24031-289">大约半小时后, 策略将应用于您的组织的用户。</span><span class="sxs-lookup"><span data-stu-id="24031-289">After approximately a half hour, policies are applied, user by user, for your organization.</span></span> <span data-ttu-id="24031-290">如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="24031-290">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="24031-291">(一般原则是, 处理5000用户帐户需要大约一小时的时间。)</span><span class="sxs-lookup"><span data-stu-id="24031-291">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

## <a name="verify-status-of-user-accounts-segments-policies-or-policy-application"></a><span data-ttu-id="24031-292">验证用户帐户、段、策略或策略应用程序的状态</span><span class="sxs-lookup"><span data-stu-id="24031-292">Verify status of user accounts, segments, policies, or policy application</span></span>

<span data-ttu-id="24031-293">使用 PowerShell, 可以验证用户帐户、段、策略和策略应用程序的状态, 如下表中所列。</span><span class="sxs-lookup"><span data-stu-id="24031-293">Using PowerShell, you can verify status of user accounts, segments, policies, and policy application, as listed in the following table.</span></span>

|<span data-ttu-id="24031-294">若要验证此</span><span class="sxs-lookup"><span data-stu-id="24031-294">To verify this</span></span>  |<span data-ttu-id="24031-295">具体操作</span><span class="sxs-lookup"><span data-stu-id="24031-295">Do this</span></span>  |
|---------|---------|
|<span data-ttu-id="24031-296">用户帐户</span><span class="sxs-lookup"><span data-stu-id="24031-296">User accounts</span></span>     |<span data-ttu-id="24031-297">使用具有 Identity 参数的**InformationBarrierRecipientStatus** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24031-297">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> <p><span data-ttu-id="24031-298">语法`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span><span class="sxs-lookup"><span data-stu-id="24031-298">Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span></span> <p><span data-ttu-id="24031-299">您可以使用任何唯一标识每个用户的值, 如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="24031-299">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> <p><span data-ttu-id="24031-300">示例：`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span><span class="sxs-lookup"><span data-stu-id="24031-300">Example: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span></span> <p><span data-ttu-id="24031-301">在此示例中, 我们引用 Office 365 中的两个用户帐户: *meganb* for *Megan*和*alexw* for *Alex*。</span><span class="sxs-lookup"><span data-stu-id="24031-301">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> <p><span data-ttu-id="24031-302">(也可以将此 cmdlet 用于单个用户: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span><span class="sxs-lookup"><span data-stu-id="24031-302">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span> <p><span data-ttu-id="24031-303">此 cmdlet 返回有关用户的信息, 如属性值和应用的任何信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="24031-303">This cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>|
|<span data-ttu-id="24031-304">段</span><span class="sxs-lookup"><span data-stu-id="24031-304">Segments</span></span>     |<span data-ttu-id="24031-305">使用**OrganizationSegment** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24031-305">Use the **Get-OrganizationSegment** cmdlet.</span></span><p><span data-ttu-id="24031-306">语法`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="24031-306">Syntax: `Get-OrganizationSegment`</span></span> <p><span data-ttu-id="24031-307">这将显示为您的组织定义的所有网段的列表。</span><span class="sxs-lookup"><span data-stu-id="24031-307">This will display a list of all segments defined for your organization.</span></span>         |
|<span data-ttu-id="24031-308">信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="24031-308">Information barrier policies</span></span>     |<span data-ttu-id="24031-309">使用**InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24031-309">Use the **Get-InformationBarrierPolicy** cmdlet.</span></span> <p> <span data-ttu-id="24031-310">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="24031-310">Syntax: `Get-InformationBarrierPolicy`</span></span> <p><span data-ttu-id="24031-311">这将显示已定义的信息障碍策略的列表及其状态。</span><span class="sxs-lookup"><span data-stu-id="24031-311">This will display a list of information barrier policies that were defined, and their status.</span></span>       |
|<span data-ttu-id="24031-312">最新的信息屏障策略应用程序</span><span class="sxs-lookup"><span data-stu-id="24031-312">The most recent information barrier policy application</span></span>     | <span data-ttu-id="24031-313">使用**InformationBarrierPoliciesApplicationStatus** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24031-313">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span> <p><span data-ttu-id="24031-314">语法`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="24031-314">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span><p>    <span data-ttu-id="24031-315">这将显示有关策略应用程序是已完成、失败还是正在进行的信息。</span><span class="sxs-lookup"><span data-stu-id="24031-315">This will display information about whether policy application completed, failed, or is in progress.</span></span>       |
|<span data-ttu-id="24031-316">所有信息屏障策略应用程序</span><span class="sxs-lookup"><span data-stu-id="24031-316">All information barrier policy applications</span></span>|<span data-ttu-id="24031-317">改用`Get-InformationBarrierPoliciesApplicationStatus -All $true`</span><span class="sxs-lookup"><span data-stu-id="24031-317">Use `Get-InformationBarrierPoliciesApplicationStatus -All $true`</span></span><p><span data-ttu-id="24031-318">这将显示有关策略应用程序是已完成、失败还是正在进行的信息。</span><span class="sxs-lookup"><span data-stu-id="24031-318">This will display information about whether policy application completed, failed, or is in progress.</span></span>|

## <a name="stop-a-policy-application"></a><span data-ttu-id="24031-319">停止策略应用程序</span><span class="sxs-lookup"><span data-stu-id="24031-319">Stop a policy application</span></span>

<span data-ttu-id="24031-320">如果在您开始应用信息屏障策略后, 您想要停止应用这些策略, 请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="24031-320">If, after you have started applying information barrier policies, you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="24031-321">请注意, 此过程将需要大约30-35 分钟才能开始。</span><span class="sxs-lookup"><span data-stu-id="24031-321">Keep in mind that it will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="24031-322">若要查看最新信息屏障策略应用程序的状态, 请使用**InformationBarrierPoliciesApplicationStatus** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24031-322">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="24031-323">语法`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="24031-323">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="24031-324">记下应用程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="24031-324">Note the application's GUID.</span></span>

2. <span data-ttu-id="24031-325">将**InformationBarrierPoliciesApplication** Cmdlet 与 Identity 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="24031-325">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="24031-326">语法`Stop-InformationBarrierPoliciesApplication -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="24031-326">Syntax:  `Stop-InformationBarrierPoliciesApplication -Identity GUID`</span></span>

    <span data-ttu-id="24031-327">示例：`InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span><span class="sxs-lookup"><span data-stu-id="24031-327">Example: `InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span></span>

## <a name="edit-a-segment-or-a-policy"></a><span data-ttu-id="24031-328">编辑段或策略</span><span class="sxs-lookup"><span data-stu-id="24031-328">Edit a segment or a policy</span></span>

### <a name="edit-a-segment"></a><span data-ttu-id="24031-329">编辑段</span><span class="sxs-lookup"><span data-stu-id="24031-329">Edit a segment</span></span>

1. <span data-ttu-id="24031-330">若要查看所有现有段, 请使用**OrganizationSegment** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24031-330">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>
    
    <span data-ttu-id="24031-331">语法`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="24031-331">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="24031-332">你将看到每个段的列表和详细信息, 如段类型、其 UserGroupFilter 值、创建日期或上次修改时间、GUID 等。</span><span class="sxs-lookup"><span data-stu-id="24031-332">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="24031-333">打印或保存段列表以便日后参考。</span><span class="sxs-lookup"><span data-stu-id="24031-333">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="24031-334">例如, 如果您想要编辑某一段, 则需要知道它的名称或标识值 (这与 Identity 参数一起使用)。</span><span class="sxs-lookup"><span data-stu-id="24031-334">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="24031-335">若要编辑分段, 请使用**OrganizationSegment** Cmdlet 和**Identity**参数以及相关详细信息。</span><span class="sxs-lookup"><span data-stu-id="24031-335">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span> 

    <span data-ttu-id="24031-336">语法`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="24031-336">Syntax: `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

    <span data-ttu-id="24031-337">示例：`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span><span class="sxs-lookup"><span data-stu-id="24031-337">Example: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span></span>

    <span data-ttu-id="24031-338">在此示例中, 对于具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的段, 我们将部门名称更新为 "HRDept"。</span><span class="sxs-lookup"><span data-stu-id="24031-338">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span>

<span data-ttu-id="24031-339">为组织编辑完段后, 可以继续[定义](#part-2-define-information-barrier-policies)或[编辑](#edit-a-policy)信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="24031-339">When you have finished editing segments for your organization, you can proceed to [define](#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

### <a name="edit-a-policy"></a><span data-ttu-id="24031-340">编辑策略</span><span class="sxs-lookup"><span data-stu-id="24031-340">Edit a policy</span></span>

1. <span data-ttu-id="24031-341">若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24031-341">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="24031-342">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="24031-342">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="24031-343">在结果列表中, 标识要更改的策略。</span><span class="sxs-lookup"><span data-stu-id="24031-343">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="24031-344">记下策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="24031-344">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="24031-345">将**InformationBarrierPolicy** Cmdlet 与**Identity**参数一起使用, 并指定要进行的更改。</span><span class="sxs-lookup"><span data-stu-id="24031-345">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="24031-346">语法 (阻止段与其他段通信):</span><span class="sxs-lookup"><span data-stu-id="24031-346">Syntax (blocking segments from communicating with other segments):</span></span> 

    `Set-InformationBarrierPolicy -Identity GUID -SegmentsBlocked "segmentname, segmentname"` 

    <span data-ttu-id="24031-347">语法 (仅允许段与某些其他段进行通信):</span><span class="sxs-lookup"><span data-stu-id="24031-347">Syntax (enabling segments to communicate only with certain other segments):</span></span>
    
    ``Set-InformationBarrierPolicy -Identity GUID -SegmentsAllowed "segmentname, segmentname"``

    <span data-ttu-id="24031-348">示例: 假设定义了一个策略以阻止与销售和市场进行通信的研究。</span><span class="sxs-lookup"><span data-stu-id="24031-348">Example: Suppose a policy was defined to block Research from communicating with Sales and Marketing.</span></span> <span data-ttu-id="24031-349">该策略是使用以下 cmdlet 定义的:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales, Marketing"`</span><span class="sxs-lookup"><span data-stu-id="24031-349">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales, Marketing"`</span></span>
    
    <span data-ttu-id="24031-350">假设我们要对其进行更改, 以便信息检索中的人员只能与 HR 中的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="24031-350">Suppose we want to change it so that people in Research can only communicate with people in HR.</span></span> <span data-ttu-id="24031-351">若要进行此更改, 我们使用以下 cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="24031-351">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

3. <span data-ttu-id="24031-352">完成策略的编辑后, 请确保应用所做的更改。</span><span class="sxs-lookup"><span data-stu-id="24031-352">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="24031-353">(请参阅[Apply 信息屏障策略](#part-3-apply-information-barrier-policies)。)</span><span class="sxs-lookup"><span data-stu-id="24031-353">(See [Apply information barrier policies](#part-3-apply-information-barrier-policies).)</span></span>

### <a name="remove-a-policy"></a><span data-ttu-id="24031-354">删除策略</span><span class="sxs-lookup"><span data-stu-id="24031-354">Remove a policy</span></span>

1. <span data-ttu-id="24031-355">若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24031-355">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="24031-356">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="24031-356">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="24031-357">在结果列表中, 标识要删除的策略。</span><span class="sxs-lookup"><span data-stu-id="24031-357">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="24031-358">记下策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="24031-358">Note the policy's GUID and name.</span></span> <span data-ttu-id="24031-359">请确保将策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="24031-359">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="24031-360">将**InformationBarrierPolicy** Cmdlet 与 Identity 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="24031-360">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="24031-361">语法`Remove-InformationBarrierPolicy -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="24031-361">Syntax: `Remove-InformationBarrierPolicy -Identity GUID`</span></span>

    <span data-ttu-id="24031-362">示例: 假设我们要删除 GUID 为*43c37853-ea10-4b90-a23d-ab8c93772471*的策略。</span><span class="sxs-lookup"><span data-stu-id="24031-362">Example: Suppose we want to remove a policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span> <span data-ttu-id="24031-363">为此, 我们使用此 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="24031-363">To do this, we use this cmdlet:</span></span>
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    <span data-ttu-id="24031-364">出现提示时, 请确认更改。</span><span class="sxs-lookup"><span data-stu-id="24031-364">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="24031-365">对要删除的每个策略重复步骤1-2。</span><span class="sxs-lookup"><span data-stu-id="24031-365">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="24031-366">删除完策略后, 应用所做的更改。</span><span class="sxs-lookup"><span data-stu-id="24031-366">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="24031-367">为此, 请使用**InformationBarrierPoliciesApplication** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24031-367">To do this, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="24031-368">语法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="24031-368">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="24031-369">为您的组织应用更改的用户。</span><span class="sxs-lookup"><span data-stu-id="24031-369">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="24031-370">如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="24031-370">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

### <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="24031-371">将策略设置为非活动状态</span><span class="sxs-lookup"><span data-stu-id="24031-371">Set a policy to inactive status</span></span>

1. <span data-ttu-id="24031-372">若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24031-372">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="24031-373">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="24031-373">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="24031-374">在结果列表中, 标识要更改 (或删除) 的策略。</span><span class="sxs-lookup"><span data-stu-id="24031-374">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="24031-375">记下策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="24031-375">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="24031-376">若要将策略的状态设置为 "非活动", 请使用带有 Identity 参数的**InformationBarrierPolicy** cmdlet, 将 State 参数设置为 "非活动"。</span><span class="sxs-lookup"><span data-stu-id="24031-376">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    <span data-ttu-id="24031-377">语法`Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="24031-377">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span></span>

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    <span data-ttu-id="24031-378">在此示例中, 我们将具有 GUID *43c37853-ea10-4b90-a23d-ab8c9377247*的信息屏障策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="24031-378">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span>

3. <span data-ttu-id="24031-379">若要应用所做的更改, 请使用**InformationBarrierPoliciesApplication** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="24031-379">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="24031-380">语法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="24031-380">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="24031-381">为您的组织应用更改的用户。</span><span class="sxs-lookup"><span data-stu-id="24031-381">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="24031-382">如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="24031-382">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="24031-383">(一般原则是, 处理5000用户帐户需要大约一小时的时间。)</span><span class="sxs-lookup"><span data-stu-id="24031-383">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="24031-384">在这种情况下, 一个或多个信息障碍策略将设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="24031-384">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="24031-385">在这里, 您可以执行以下任一操作:</span><span class="sxs-lookup"><span data-stu-id="24031-385">From here, you can do any of the following:</span></span>
- <span data-ttu-id="24031-386">将其保持原样 (策略设置为非活动状态对用户没有影响)</span><span class="sxs-lookup"><span data-stu-id="24031-386">Leave it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="24031-387">编辑策略</span><span class="sxs-lookup"><span data-stu-id="24031-387">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="24031-388">删除策略</span><span class="sxs-lookup"><span data-stu-id="24031-388">Remove a policy</span></span>](#remove-a-policy)

## <a name="example-contosos-departments-segments-and-policies"></a><span data-ttu-id="24031-389">示例: Contoso 的部门、分段和策略</span><span class="sxs-lookup"><span data-stu-id="24031-389">Example: Contoso's departments, segments, and policies</span></span>

<span data-ttu-id="24031-390">若要了解组织如何采用定义段落和策略的方法, 请考虑以下示例。</span><span class="sxs-lookup"><span data-stu-id="24031-390">To see how an organization might approach defining segments and policies, consider the following example.</span></span>

### <a name="contosos-departments-and-plan"></a><span data-ttu-id="24031-391">Contoso 的部门和规划</span><span class="sxs-lookup"><span data-stu-id="24031-391">Contoso's departments and plan</span></span>

<span data-ttu-id="24031-392">Contoso 有五个部门: HR、销售、营销、研究和制造。</span><span class="sxs-lookup"><span data-stu-id="24031-392">Contoso has five departments: HR, Sales, Marketing, Research, and Manufacturing.</span></span> <span data-ttu-id="24031-393">为了保持与行业法规的兼容性, 某些部门中的人员不应与其他部门通信, 如下表所示:</span><span class="sxs-lookup"><span data-stu-id="24031-393">In order to remain compliant with industry regulations, people in some departments are not supposed to communicate with other departments, as listed in the following table:</span></span>

|<span data-ttu-id="24031-394">段落</span><span class="sxs-lookup"><span data-stu-id="24031-394">Segment</span></span>  |<span data-ttu-id="24031-395">可以与</span><span class="sxs-lookup"><span data-stu-id="24031-395">Can talk to</span></span>  |<span data-ttu-id="24031-396">无法对话</span><span class="sxs-lookup"><span data-stu-id="24031-396">Cannot talk to</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="24031-397">HR</span><span class="sxs-lookup"><span data-stu-id="24031-397">HR</span></span>     |<span data-ttu-id="24031-398">每个人</span><span class="sxs-lookup"><span data-stu-id="24031-398">Everyone</span></span>         |<span data-ttu-id="24031-399">(无限制)</span><span class="sxs-lookup"><span data-stu-id="24031-399">(no restrictions)</span></span>         |
|<span data-ttu-id="24031-400">销售</span><span class="sxs-lookup"><span data-stu-id="24031-400">Sales</span></span>     |<span data-ttu-id="24031-401">HR、营销、制造业</span><span class="sxs-lookup"><span data-stu-id="24031-401">HR, Marketing, Manufacturing</span></span>         |<span data-ttu-id="24031-402">信息检索</span><span class="sxs-lookup"><span data-stu-id="24031-402">Research</span></span>         |
|<span data-ttu-id="24031-403">营销</span><span class="sxs-lookup"><span data-stu-id="24031-403">Marketing</span></span>     |<span data-ttu-id="24031-404">每个人</span><span class="sxs-lookup"><span data-stu-id="24031-404">Everyone</span></span>         |<span data-ttu-id="24031-405">(无限制)</span><span class="sxs-lookup"><span data-stu-id="24031-405">(no restrictions)</span></span>         |
|<span data-ttu-id="24031-406">信息检索</span><span class="sxs-lookup"><span data-stu-id="24031-406">Research</span></span>     |<span data-ttu-id="24031-407">HR、营销、制造业</span><span class="sxs-lookup"><span data-stu-id="24031-407">HR, Marketing, Manufacturing</span></span>        |<span data-ttu-id="24031-408">销售</span><span class="sxs-lookup"><span data-stu-id="24031-408">Sales</span></span>     |
|<span data-ttu-id="24031-409">制造业</span><span class="sxs-lookup"><span data-stu-id="24031-409">Manufacturing</span></span> |<span data-ttu-id="24031-410">HR、营销</span><span class="sxs-lookup"><span data-stu-id="24031-410">HR, Marketing</span></span> |<span data-ttu-id="24031-411">除 HR 或营销之外的任何人</span><span class="sxs-lookup"><span data-stu-id="24031-411">Anyone other than HR or Marketing</span></span> |

<span data-ttu-id="24031-412">考虑到这一点, Contoso 的计划包括三个信息屏障策略:</span><span class="sxs-lookup"><span data-stu-id="24031-412">With this in mind, Contoso's plan includes three information barrier policies:</span></span>

1. <span data-ttu-id="24031-413">旨在防止销售人员与信息检索通信的策略 (和另一个策略, 以防止与销售通信的信息检索)</span><span class="sxs-lookup"><span data-stu-id="24031-413">A policy designed to prevent Sales from communicating with Research (and another policy to prevent Research from communicating with Sales)</span></span>
2. <span data-ttu-id="24031-414">旨在允许制造业仅与 HR 和营销进行通信的策略</span><span class="sxs-lookup"><span data-stu-id="24031-414">A policy designed to allow Manufacturing to communicate with HR and Marketing only</span></span> 

<span data-ttu-id="24031-415">不需要为 HR 或营销定义策略。</span><span class="sxs-lookup"><span data-stu-id="24031-415">It's not necessary to define policies for HR or Marketing.</span></span>

### <a name="contosos-defined-segments"></a><span data-ttu-id="24031-416">Contoso 定义的段</span><span class="sxs-lookup"><span data-stu-id="24031-416">Contoso's defined segments</span></span>

<span data-ttu-id="24031-417">Contoso 将使用 Azure Active Directory 中的 "部门" 属性来定义段, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="24031-417">Contoso will use the Department attribute in Azure Active Directory to define segments, as follows:</span></span>

|<span data-ttu-id="24031-418">部门</span><span class="sxs-lookup"><span data-stu-id="24031-418">Department</span></span>  |<span data-ttu-id="24031-419">段定义</span><span class="sxs-lookup"><span data-stu-id="24031-419">Segment Definition</span></span>  |
|---------|---------|
|<span data-ttu-id="24031-420">HR</span><span class="sxs-lookup"><span data-stu-id="24031-420">HR</span></span>     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|<span data-ttu-id="24031-421">销售</span><span class="sxs-lookup"><span data-stu-id="24031-421">Sales</span></span>     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|<span data-ttu-id="24031-422">营销</span><span class="sxs-lookup"><span data-stu-id="24031-422">Marketing</span></span>     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|<span data-ttu-id="24031-423">信息检索</span><span class="sxs-lookup"><span data-stu-id="24031-423">Research</span></span>     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|<span data-ttu-id="24031-424">制造业</span><span class="sxs-lookup"><span data-stu-id="24031-424">Manufacturing</span></span>     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

<span data-ttu-id="24031-425">定义段后, Contoso 将继续定义策略。</span><span class="sxs-lookup"><span data-stu-id="24031-425">With the segments defined, Contoso proceeds to define policies.</span></span> 

### <a name="contosos-information-barrier-policies"></a><span data-ttu-id="24031-426">Contoso 的信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="24031-426">Contoso's information barrier policies</span></span>

<span data-ttu-id="24031-427">Contoso 定义了三种策略, 如下表所述:</span><span class="sxs-lookup"><span data-stu-id="24031-427">Contoso defines three polices, as described in the following table:</span></span>

|<span data-ttu-id="24031-428">策略</span><span class="sxs-lookup"><span data-stu-id="24031-428">Policy</span></span>  |<span data-ttu-id="24031-429">策略定义</span><span class="sxs-lookup"><span data-stu-id="24031-429">Policy Definition</span></span>  |
|---------|---------|
|<span data-ttu-id="24031-430">策略 1: 防止销售与信息检索通信</span><span class="sxs-lookup"><span data-stu-id="24031-430">Policy 1: Prevent Sales from communicating with Research</span></span>     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> <span data-ttu-id="24031-431">在此示例中, 信息屏障策略称为 "*销售-研究*"。</span><span class="sxs-lookup"><span data-stu-id="24031-431">In this example, the information barrier policy is called *Sales-Research*.</span></span> <span data-ttu-id="24031-432">当此策略处于活动状态且已应用时, 它将有助于阻止销售部门中的用户与研究网段中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="24031-432">When this policy is active and applied, it will help prevent users who are in the Sales segment from communicating with users in the Research segment.</span></span> <span data-ttu-id="24031-433">这是单向策略;它不会阻止研究与销售通信。</span><span class="sxs-lookup"><span data-stu-id="24031-433">This is a one-way policy; it won't prevent Research from communicating with Sales.</span></span> <span data-ttu-id="24031-434">为此, 需要策略2。</span><span class="sxs-lookup"><span data-stu-id="24031-434">For that, Policy 2 is needed.</span></span>      |
|<span data-ttu-id="24031-435">策略 2: 防止与销售通信的研究</span><span class="sxs-lookup"><span data-stu-id="24031-435">Policy 2: Prevent Research from communicating with Sales</span></span>     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> <span data-ttu-id="24031-436">在此示例中, 信息屏障策略称为 "*研究-销售*"。</span><span class="sxs-lookup"><span data-stu-id="24031-436">In this example, the information barrier policy is called *Research-Sales*.</span></span> <span data-ttu-id="24031-437">当此策略处于活动状态且已应用时, 它将有助于防止在研究网段中的用户与销售部门中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="24031-437">When this policy is active and applied, it will help prevent users who are in the Research segment from communicating with users in the Sales segment.</span></span>       |
|<span data-ttu-id="24031-438">策略 3: 允许制造业仅与 HR 和营销进行通信</span><span class="sxs-lookup"><span data-stu-id="24031-438">Policy 3: Allow Manufacturing to communicate with HR and Marketing only</span></span>     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR, Marketing" -State Inactive` <p><span data-ttu-id="24031-439">在这种情况下, 信息屏障策略称为 "*制造业-HRMarketing*"。</span><span class="sxs-lookup"><span data-stu-id="24031-439">In this case, the information barrier policy is called *Manufacturing-HRMarketing*.</span></span> <span data-ttu-id="24031-440">当此策略处于活动状态且已应用时, 生产只能与 HR 和 Marketing 进行通信。</span><span class="sxs-lookup"><span data-stu-id="24031-440">When this policy is active and applied, Manufacturing can communicate only with HR and Marketing.</span></span> <span data-ttu-id="24031-441">请注意, 不限制 HR 和市场营销与其他段进行通信。</span><span class="sxs-lookup"><span data-stu-id="24031-441">Note that HR and Marketing are not restricted from communicating with other segments.</span></span> |

<span data-ttu-id="24031-442">通过定义的段和策略, Contoso 通过运行**InformationBarrierPoliciesApplication** cmdlet 来应用这些策略。</span><span class="sxs-lookup"><span data-stu-id="24031-442">With segments and policies defined, Contoso applies the policies by running the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span> 

<span data-ttu-id="24031-443">完成后, Contoso 就符合法律和行业要求。</span><span class="sxs-lookup"><span data-stu-id="24031-443">When that finishes, Contoso is compliant with legal and industry requirements.</span></span>

## <a name="related-articles"></a><span data-ttu-id="24031-444">相关文章</span><span class="sxs-lookup"><span data-stu-id="24031-444">Related articles</span></span>

[<span data-ttu-id="24031-445">获取信息障碍概述</span><span class="sxs-lookup"><span data-stu-id="24031-445">Get an overview of information barriers</span></span>](information-barriers.md)

[<span data-ttu-id="24031-446">了解有关 Microsoft 团队中的信息障碍的详细信息</span><span class="sxs-lookup"><span data-stu-id="24031-446">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[<span data-ttu-id="24031-447">信息屏障策略的属性 (预览)</span><span class="sxs-lookup"><span data-stu-id="24031-447">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)

[<span data-ttu-id="24031-448">解决信息障碍 (预览)</span><span class="sxs-lookup"><span data-stu-id="24031-448">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)
