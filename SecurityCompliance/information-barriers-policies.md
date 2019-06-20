---
title: 定义信息屏障策略
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 06/19/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: 了解如何在 Microsoft 团队中定义信息障碍策略。
ms.openlocfilehash: fb162e380fa467cf3e832bd7bbdafcde136b1db6
ms.sourcegitcommit: 087cf1a022b13c46e207270d6837f09a9752c972
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2019
ms.locfileid: "35083860"
---
# <a name="define-policies-for-information-barriers-preview"></a><span data-ttu-id="95240-103">定义信息障碍策略 (预览)</span><span class="sxs-lookup"><span data-stu-id="95240-103">Define policies for information barriers (Preview)</span></span>

## <a name="overview"></a><span data-ttu-id="95240-104">概述</span><span class="sxs-lookup"><span data-stu-id="95240-104">Overview</span></span>

<span data-ttu-id="95240-105">通过信息障碍, 您可以定义旨在防止某些用户段相互通信的策略, 或允许特定的分段仅与某些其他网段进行通信。</span><span class="sxs-lookup"><span data-stu-id="95240-105">With information barriers, you can define policies that are designed to prevent certain segments of users from communicating with each other, or allow specific segments to communicate only with certain other segments.</span></span> <span data-ttu-id="95240-106">信息屏障策略可帮助您的组织保持遵守相关的行业标准和法规, 并避免潜在的利益冲突。</span><span class="sxs-lookup"><span data-stu-id="95240-106">Information barrier policies can help your organization maintain compliance with relevant industry standards and regulations, and avoid potential conflicts of interest.</span></span> <span data-ttu-id="95240-107">若要了解详细信息, 请参阅[信息障碍 (预览)](information-barriers.md)。</span><span class="sxs-lookup"><span data-stu-id="95240-107">To learn more, see [Information barriers (Preview)](information-barriers.md).</span></span> 

<span data-ttu-id="95240-108">本文介绍如何规划、定义、实现和管理信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="95240-108">This article describes how to plan, define, implement, and manage information barrier policies.</span></span> <span data-ttu-id="95240-109">涉及几个步骤, 工作流划分为多个部分。</span><span class="sxs-lookup"><span data-stu-id="95240-109">Several steps are involved, and the work flow is divided into several parts.</span></span> <span data-ttu-id="95240-110">在开始定义 (或编辑) 信息屏障策略之前, 请务必阅读[先决条件](#prerequisites)和整个过程。</span><span class="sxs-lookup"><span data-stu-id="95240-110">Make sure to read through the [prerequisites](#prerequisites) and the entire process before you begin defining (or editing) information barrier policies.</span></span>

> [!TIP]
> <span data-ttu-id="95240-111">本文包含一个[示例方案](#example-contosos-departments-segments-and-policies)和一个[可下载的 Excel 工作簿](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx), 可帮助您规划和定义信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="95240-111">This article includes an [example scenario](#example-contosos-departments-segments-and-policies) and a [downloadable Excel workbook](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) to help you plan and define your information barrier policies.</span></span>

## <a name="concepts-of-information-barrier-policies"></a><span data-ttu-id="95240-112">信息屏障策略的概念</span><span class="sxs-lookup"><span data-stu-id="95240-112">Concepts of information barrier policies</span></span>

<span data-ttu-id="95240-113">了解信息屏障策略的基本概念很有帮助:</span><span class="sxs-lookup"><span data-stu-id="95240-113">It's helpful to know the underlying concepts of information barrier policies:</span></span>

- <span data-ttu-id="95240-114">**用户帐户属性**是在 Azure Active Directory (或 Exchange Online) 中定义的。</span><span class="sxs-lookup"><span data-stu-id="95240-114">**User account attributes** are defined in Azure Active Directory (or Exchange Online).</span></span> <span data-ttu-id="95240-115">这些属性可以包括部门、职务、位置、团队名称和其他作业配置文件详细信息。</span><span class="sxs-lookup"><span data-stu-id="95240-115">These attributes can include department, job title, location, team name, and other job profile details.</span></span> 

- <span data-ttu-id="95240-116">**分段**是在 Office 365 安全 & 合规性中心中使用选定的**用户帐户属性**定义的用户集。</span><span class="sxs-lookup"><span data-stu-id="95240-116">**Segments** are sets of users that are defined in the Office 365 Security & Compliance Center using a selected **user account attribute**.</span></span> <span data-ttu-id="95240-117">(请参阅[支持的属性列表](information-barriers-attributes.md)。)</span><span class="sxs-lookup"><span data-stu-id="95240-117">(See the [list of supported attributes](information-barriers-attributes.md).)</span></span> 

- <span data-ttu-id="95240-118">**信息屏障策略**决定了通信限制或限制。</span><span class="sxs-lookup"><span data-stu-id="95240-118">**Information barrier policies** determine communication limits or restrictions.</span></span> <span data-ttu-id="95240-119">在定义信息障碍策略时, 可以从以下两种策略中进行选择:</span><span class="sxs-lookup"><span data-stu-id="95240-119">When you define information barrier policies, you choose from two kinds of policies:</span></span>
    - <span data-ttu-id="95240-120">"块" 策略防止一个分段与另一个网段通信。</span><span class="sxs-lookup"><span data-stu-id="95240-120">"Block" policies prevent one segment from communicating with another segment.</span></span>
    - <span data-ttu-id="95240-121">"允许" 策略允许一段仅与某些其他段进行通信。</span><span class="sxs-lookup"><span data-stu-id="95240-121">"Allow" policies allow one segment to communicate with only certain other segments.</span></span>

- <span data-ttu-id="95240-122">**策略应用程序**在定义所有信息屏障策略之后完成, 并准备好在您的组织中应用它们。</span><span class="sxs-lookup"><span data-stu-id="95240-122">**Policy application** is done after all information barrier policies are defined, and you are ready to apply them in your organization.</span></span>

## <a name="the-work-flow-at-a-glance"></a><span data-ttu-id="95240-123">工作流一览</span><span class="sxs-lookup"><span data-stu-id="95240-123">The work flow at a glance</span></span>

|<span data-ttu-id="95240-124">阶段</span><span class="sxs-lookup"><span data-stu-id="95240-124">Phase</span></span>    |<span data-ttu-id="95240-125">涉及的内容</span><span class="sxs-lookup"><span data-stu-id="95240-125">What's involved</span></span>  |
|---------|---------|
|[<span data-ttu-id="95240-126">确保满足先决条件</span><span class="sxs-lookup"><span data-stu-id="95240-126">Make sure prerequisites are met</span></span>](#prerequisites)     |<span data-ttu-id="95240-127">-验证您是否具有[所需的许可证和权限](information-barriers.md#required-licenses-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="95240-127">- Verify that you have the [required licenses and permissions](information-barriers.md#required-licenses-and-permissions)</span></span><br/><span data-ttu-id="95240-128">-验证您的目录是否包含分段用户的数据</span><span class="sxs-lookup"><span data-stu-id="95240-128">- Verify that your directory includes data for segmenting users</span></span><br/><span data-ttu-id="95240-129">-为 Microsoft 团队启用范围目录搜索</span><span class="sxs-lookup"><span data-stu-id="95240-129">- Enable scoped directory search for Microsoft Teams</span></span><br/><span data-ttu-id="95240-130">-请确保审核日志记录已打开</span><span class="sxs-lookup"><span data-stu-id="95240-130">- Make sure audit logging is turned on</span></span><br/><span data-ttu-id="95240-131">-Use PowerShell (提供示例)</span><span class="sxs-lookup"><span data-stu-id="95240-131">- Use PowerShell (examples are provided)</span></span><br/><span data-ttu-id="95240-132">-为 Microsoft 团队提供管理员同意 (包括步骤)</span><span class="sxs-lookup"><span data-stu-id="95240-132">- Provide admin consent for Microsoft Teams (steps are included)</span></span>          |
|[<span data-ttu-id="95240-133">第1部分: 组织中的用户区段</span><span class="sxs-lookup"><span data-stu-id="95240-133">Part 1: Segment users in your organization</span></span>](#part-1-segment-users)     |<span data-ttu-id="95240-134">-确定所需的策略</span><span class="sxs-lookup"><span data-stu-id="95240-134">- Determine what policies are needed</span></span><br/><span data-ttu-id="95240-135">-创建要定义的段的列表</span><span class="sxs-lookup"><span data-stu-id="95240-135">- Make a list of segments to define</span></span><br/><span data-ttu-id="95240-136">-确定要使用的属性</span><span class="sxs-lookup"><span data-stu-id="95240-136">- Identify which attributes to use</span></span><br/><span data-ttu-id="95240-137">-在策略筛选器方面定义段</span><span class="sxs-lookup"><span data-stu-id="95240-137">- Define segments in terms of policy filters</span></span>        |
|[<span data-ttu-id="95240-138">第2部分: 定义信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="95240-138">Part 2: Define information barrier policies</span></span>](#part-2-define-information-barrier-policies)     |<span data-ttu-id="95240-139">-定义你的策略 (尚不应用)</span><span class="sxs-lookup"><span data-stu-id="95240-139">- Define your policies (do not apply yet)</span></span><br/><span data-ttu-id="95240-140">-从两种类型 (阻止或允许) 中选择</span><span class="sxs-lookup"><span data-stu-id="95240-140">- Choose from two kinds (block or allow)</span></span> |
|[<span data-ttu-id="95240-141">第3部分: 应用信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="95240-141">Part 3: Apply information barrier policies</span></span>](#part-3-apply-information-barrier-policies)     |<span data-ttu-id="95240-142">-将策略设置为活动状态</span><span class="sxs-lookup"><span data-stu-id="95240-142">- Set policies to active status</span></span><br/><span data-ttu-id="95240-143">-运行策略应用程序</span><span class="sxs-lookup"><span data-stu-id="95240-143">- Run the policy application</span></span><br/><span data-ttu-id="95240-144">-查看策略状态</span><span class="sxs-lookup"><span data-stu-id="95240-144">- View policy status</span></span>         |
|<span data-ttu-id="95240-145">(根据需要)[编辑段或策略](#edit-a-segment-or-a-policy)</span><span class="sxs-lookup"><span data-stu-id="95240-145">(As needed) [Edit a segment or a policy](#edit-a-segment-or-a-policy)</span></span>     |<span data-ttu-id="95240-146">-编辑分段</span><span class="sxs-lookup"><span data-stu-id="95240-146">- Edit a segment</span></span><br/><span data-ttu-id="95240-147">-编辑或删除策略</span><span class="sxs-lookup"><span data-stu-id="95240-147">- Edit or remove a policy</span></span><br/><span data-ttu-id="95240-148">-运行策略应用程序</span><span class="sxs-lookup"><span data-stu-id="95240-148">- Run the policy application</span></span><br/><span data-ttu-id="95240-149">-查看策略状态</span><span class="sxs-lookup"><span data-stu-id="95240-149">- View policy status</span></span>         |
|<span data-ttu-id="95240-150">(根据需要)[故障排除](information-barriers-troubleshooting.md)</span><span class="sxs-lookup"><span data-stu-id="95240-150">(As needed) [Troubleshooting](information-barriers-troubleshooting.md)</span></span>|<span data-ttu-id="95240-151">-当事情未按预期工作时执行操作</span><span class="sxs-lookup"><span data-stu-id="95240-151">- Take action when things are not working as expected</span></span>|

## <a name="prerequisites"></a><span data-ttu-id="95240-152">先决条件</span><span class="sxs-lookup"><span data-stu-id="95240-152">Prerequisites</span></span>

<span data-ttu-id="95240-153">除了[所需的许可证和权限](information-barriers.md#required-licenses-and-permissions)之外, 请确保满足以下要求:</span><span class="sxs-lookup"><span data-stu-id="95240-153">In addition to the [required licenses and permissions](information-barriers.md#required-licenses-and-permissions), make sure that the following requirements are met:</span></span> 
     
- <span data-ttu-id="95240-154">**目录数据**。</span><span class="sxs-lookup"><span data-stu-id="95240-154">**Directory data**.</span></span> <span data-ttu-id="95240-155">确保您的组织的结构已反映在目录数据中。</span><span class="sxs-lookup"><span data-stu-id="95240-155">Make sure that your organization's structure is reflected in directory data.</span></span> <span data-ttu-id="95240-156">为此, 请确保在 Azure Active Directory (或 Exchange Online) 中正确填充了用户帐户属性, 如组成员身份、部门名称等。</span><span class="sxs-lookup"><span data-stu-id="95240-156">To do this, make sure that user account attributes, such as group membership, department name, etc. are populated correctly in Azure Active Directory (or Exchange Online).</span></span> <span data-ttu-id="95240-157">若要了解详细信息, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="95240-157">To learn more, see the following resources:</span></span>
  - [<span data-ttu-id="95240-158">信息屏障策略的属性 (预览)</span><span class="sxs-lookup"><span data-stu-id="95240-158">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)
  - [<span data-ttu-id="95240-159">使用 Azure Active Directory 添加或更新用户的配置文件信息</span><span class="sxs-lookup"><span data-stu-id="95240-159">Add or update a user's profile information using Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [<span data-ttu-id="95240-160">使用 Office 365 PowerShell 配置用户帐户的属性</span><span class="sxs-lookup"><span data-stu-id="95240-160">Configure user account properties with Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)

- <span data-ttu-id="95240-161">**作用域的目录搜索**。</span><span class="sxs-lookup"><span data-stu-id="95240-161">**Scoped directory search**.</span></span> <span data-ttu-id="95240-162">在定义组织的第一个信息屏障策略之前, 必须先[在 Microsoft 团队中启用范围目录搜索](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search)。</span><span class="sxs-lookup"><span data-stu-id="95240-162">Before you define your organization's first information barrier policy, you must [enable scoped directory search in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search).</span></span> <span data-ttu-id="95240-163">在设置或定义信息屏障策略之前, 请先等待至少24小时后, 再启用范围目录搜索。</span><span class="sxs-lookup"><span data-stu-id="95240-163">Wait at least 24 hours after enabling scoped directory search before you set up or define information barrier policies.</span></span>

- <span data-ttu-id="95240-164">**审核日志记录**。</span><span class="sxs-lookup"><span data-stu-id="95240-164">**Audit logging**.</span></span> <span data-ttu-id="95240-165">为了查找策略应用程序的状态, 审核日志记录必须处于打开状态。</span><span class="sxs-lookup"><span data-stu-id="95240-165">In order to look up the status of a policy application, audit logging must be turned on.</span></span> <span data-ttu-id="95240-166">我们建议您在开始定义段或策略之前执行此操作。</span><span class="sxs-lookup"><span data-stu-id="95240-166">We recommend doing this before you begin to define segments or policies.</span></span> <span data-ttu-id="95240-167">若要了解详细信息, 请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="95240-167">To learn more, see [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="95240-168">**PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="95240-168">**PowerShell**.</span></span> <span data-ttu-id="95240-169">目前, 信息屏障策略在 Office 365 Security & 合规性中心 (使用 PowerShell cmdlet) 中进行定义和管理。</span><span class="sxs-lookup"><span data-stu-id="95240-169">Currently, information barrier policies are defined and managed in the Office 365 Security & Compliance Center using PowerShell cmdlets.</span></span> <span data-ttu-id="95240-170">虽然本文中提供了几个示例, 但您需要熟悉 PowerShell cmdlet 和参数。</span><span class="sxs-lookup"><span data-stu-id="95240-170">Although several examples are provided in this article, you'll need to be familiar with PowerShell cmdlets and parameters.</span></span> <span data-ttu-id="95240-171">[连接到 Office 365 安全 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps)。</span><span class="sxs-lookup"><span data-stu-id="95240-171">[Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).</span></span>

- <span data-ttu-id="95240-172">**Microsoft 团队中的信息障碍的管理员同意**。</span><span class="sxs-lookup"><span data-stu-id="95240-172">**Admin consent for information barriers in Microsoft Teams**.</span></span> <span data-ttu-id="95240-173">如果你的策略已准备就绪, 则信息障碍可以从聊天会话中删除那些不应处于其中的人。</span><span class="sxs-lookup"><span data-stu-id="95240-173">When your policies are in place, information barriers can remove people from chat sessions they are not supposed to be in.</span></span> <span data-ttu-id="95240-174">这有助于确保您的组织遵守策略和管理法规。</span><span class="sxs-lookup"><span data-stu-id="95240-174">This helps ensure your organization remains compliant with policies and regulations.</span></span> <span data-ttu-id="95240-175">使用以下过程可使信息障碍策略在 Microsoft 团队中按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="95240-175">Use the following procedure to enable information barrier policies to work as expected in Microsoft Teams.</span></span> 

   1. <span data-ttu-id="95240-176">运行以下 PowerShell cmdlet:</span><span class="sxs-lookup"><span data-stu-id="95240-176">Run the following PowerShell cmdlets:</span></span>

      ```
      Login-AzureRmAccount 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzureRmADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzureRmADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. <span data-ttu-id="95240-177">出现提示时, 使用您的工作或学校帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="95240-177">When prompted, sign in using your work or school account for Office 365.</span></span>

   3. <span data-ttu-id="95240-178">在 "**请求的权限**" 对话框中, 检查信息, 然后选择 "**接受**"。</span><span class="sxs-lookup"><span data-stu-id="95240-178">In the **Permissions requested** dialog box, review the information, and then choose **Accept**.</span></span>

<span data-ttu-id="95240-179">满足所有先决条件后, 请继续执行下一节。</span><span class="sxs-lookup"><span data-stu-id="95240-179">When all the prerequisites are met, proceed to the next section.</span></span>

> [!TIP]
> <span data-ttu-id="95240-180">为了帮助你准备计划, 本文中包含了一个示例方案。</span><span class="sxs-lookup"><span data-stu-id="95240-180">To help you prepare your plan, an example scenario is included in this article.</span></span> <span data-ttu-id="95240-181">[请参阅 Contoso 的部门、领域和策略](#example-contosos-departments-segments-and-policies)。</span><span class="sxs-lookup"><span data-stu-id="95240-181">[See Contoso's departments, segments, and policies](#example-contosos-departments-segments-and-policies).</span></span><p><span data-ttu-id="95240-182">此外, 还提供了一个可下载的 Excel 工作簿, 可帮助您规划和定义您的区段和策略 (并创建 PowerShell cmdlet)。</span><span class="sxs-lookup"><span data-stu-id="95240-182">In addition, a downloadable Excel workbook is available to help you plan and define your segments and policies (and create your PowerShell cmdlets).</span></span> <span data-ttu-id="95240-183">[获取工作簿](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)。</span><span class="sxs-lookup"><span data-stu-id="95240-183">[Get the workbook](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx).</span></span> 

## <a name="part-1-segment-users"></a><span data-ttu-id="95240-184">第1部分: 分段用户</span><span class="sxs-lookup"><span data-stu-id="95240-184">Part 1: Segment users</span></span>

<span data-ttu-id="95240-185">在此阶段中, 您将确定需要哪些信息障碍策略, 创建要定义的段的列表, 然后定义您的段落。</span><span class="sxs-lookup"><span data-stu-id="95240-185">During this phase, you determine what information barrier policies are needed, make a list of segments to define, and then define your segments.</span></span>

### <a name="determine-what-policies-are-needed"></a><span data-ttu-id="95240-186">确定所需的策略</span><span class="sxs-lookup"><span data-stu-id="95240-186">Determine what policies are needed</span></span>

<span data-ttu-id="95240-187">考虑法律和行业法规, 谁是组织中需要信息障碍策略的组？</span><span class="sxs-lookup"><span data-stu-id="95240-187">Considering legal and industry regulations, who are the groups within your organization who will need information barrier policies?</span></span> <span data-ttu-id="95240-188">创建列表。</span><span class="sxs-lookup"><span data-stu-id="95240-188">Make a list.</span></span> <span data-ttu-id="95240-189">是否有任何组应阻止其与另一个组进行通信？</span><span class="sxs-lookup"><span data-stu-id="95240-189">Are there any groups who should be prevented from communicating with another group?</span></span> <span data-ttu-id="95240-190">是否有任何组应允许只与一个或两个其他组进行通信？</span><span class="sxs-lookup"><span data-stu-id="95240-190">Are there any groups that should be allowed to communicate only with one or two other groups?</span></span> <span data-ttu-id="95240-191">考虑您需要的策略是否属于两个组中的一个:</span><span class="sxs-lookup"><span data-stu-id="95240-191">Think about the policies you need as belonging to one of two groups:</span></span>
- <span data-ttu-id="95240-192">"阻止" 策略阻止一个组与另一个组进行通信。</span><span class="sxs-lookup"><span data-stu-id="95240-192">"Block" policies prevent one group from communicating with another group.</span></span>
- <span data-ttu-id="95240-193">"允许" 策略允许组仅与特定的其他特定组进行通信。</span><span class="sxs-lookup"><span data-stu-id="95240-193">"Allow" policies allow a group to communicate with only certain other, specific groups.</span></span>

<span data-ttu-id="95240-194">当您拥有组和策略的初始列表时, 请继续确定所需的段。</span><span class="sxs-lookup"><span data-stu-id="95240-194">When you have your initial list of groups and policies, proceed to identify the segments you'll need.</span></span> 

### <a name="identify-segments"></a><span data-ttu-id="95240-195">标识段</span><span class="sxs-lookup"><span data-stu-id="95240-195">Identify segments</span></span>

<span data-ttu-id="95240-196">除了您的初始策略列表之外, 请为您的组织创建一个段落列表。</span><span class="sxs-lookup"><span data-stu-id="95240-196">In addition to your initial list of policies, make a list of segments for your organization.</span></span> <span data-ttu-id="95240-197">将包含在信息屏障策略中的用户应属于某个网段, 并且任何用户都不应属于两个或多个网段。</span><span class="sxs-lookup"><span data-stu-id="95240-197">Users who will be included in information barrier policies should belong to a segment, and no user should belong to two or more segments.</span></span> <span data-ttu-id="95240-198">每个段只能应用一个信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="95240-198">Each segment can have only one information barrier policy applied.</span></span> 

<span data-ttu-id="95240-199">确定您的组织的目录数据中将用来定义段落的属性。</span><span class="sxs-lookup"><span data-stu-id="95240-199">Determine which attributes in your organization's directory data you'll use to define segments.</span></span> <span data-ttu-id="95240-200">您可以使用 "*部门*"、" *MemberOf*" 或任何受支持的属性。</span><span class="sxs-lookup"><span data-stu-id="95240-200">You can use *Department*, *MemberOf*, or any of the supported attributes.</span></span> <span data-ttu-id="95240-201">请确保您为用户选择的属性中具有值。</span><span class="sxs-lookup"><span data-stu-id="95240-201">Make sure that you have values in the attribute you select for users.</span></span> <span data-ttu-id="95240-202">[查看受支持的信息障碍属性的列表 (预览)](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="95240-202">[See the list of supported attributes for information barriers (Preview)](information-barriers-attributes.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="95240-203">在**继续下一节之前, 请确保您的目录数据具有可用于定义段的属性的值**。</span><span class="sxs-lookup"><span data-stu-id="95240-203">**Before you proceed to the next section, make sure your directory data has values for attributes that you can use to define segments**.</span></span> <span data-ttu-id="95240-204">如果您的目录数据没有要使用的属性的值, 则必须更新用户帐户以包含该信息, 然后再继续进行信息屏障。</span><span class="sxs-lookup"><span data-stu-id="95240-204">If your directory data does not have values for the attributes you want to use, then the user accounts must be updated to include that information before you proceed with information barriers.</span></span> <span data-ttu-id="95240-205">若要获取有关此方面的帮助, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="95240-205">To get help with this, see the following resources:</span></span><br/><span data-ttu-id="95240-206">- [使用 Office 365 PowerShell 配置用户帐户属性](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="95240-206">- [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell)</span></span><br/><span data-ttu-id="95240-207">- [使用 Azure Active Directory 添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="95240-207">- [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)</span></span>

### <a name="define-segments-using-powershell"></a><span data-ttu-id="95240-208">使用 PowerShell 定义段</span><span class="sxs-lookup"><span data-stu-id="95240-208">Define segments using PowerShell</span></span>

<span data-ttu-id="95240-209">定义段不会对用户产生影响;它只是设置要定义并应用的信息屏障策略的阶段。</span><span class="sxs-lookup"><span data-stu-id="95240-209">Defining segments does not effect users; it just sets the stage for information barrier policies to be defined and then applied.</span></span>

<span data-ttu-id="95240-210">若要定义组织段, 请使用**OrganizationSegment** Cmdlet 和**UserGroupFilter**参数, 该参数对应于要使用的[属性](information-barriers-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="95240-210">To define an organizational segment, use the **New-OrganizationSegment** cmdlet with the **UserGroupFilter** parameter that corresponds to the [attribute](information-barriers-attributes.md) you want to use.</span></span>

<span data-ttu-id="95240-211">语法`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="95240-211">Syntax: `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

<span data-ttu-id="95240-212">示例：`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`</span><span class="sxs-lookup"><span data-stu-id="95240-212">Example: `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`</span></span>

<span data-ttu-id="95240-213">在此示例中, 使用*hr*("*部门*" 属性中的值) 定义名为*hr*的字段。</span><span class="sxs-lookup"><span data-stu-id="95240-213">In this example, a segment called *HR* is defined using *HR*, a value in the *Department* attribute.</span></span> <span data-ttu-id="95240-214">Cmdlet 的 "-eq" 部分指的是 "等于"。</span><span class="sxs-lookup"><span data-stu-id="95240-214">The "-eq" portion of the cmdlet refers to "equals."</span></span>

<span data-ttu-id="95240-215">对要定义的每个段重复此过程。</span><span class="sxs-lookup"><span data-stu-id="95240-215">Repeat this process for each segment you want to define.</span></span>

<span data-ttu-id="95240-216">在运行每个 cmdlet 之后, 您应该会看到有关新段的详细信息列表。</span><span class="sxs-lookup"><span data-stu-id="95240-216">After you run each cmdlet, you should see a list of details about the new segment.</span></span> <span data-ttu-id="95240-217">详细信息包括段的类型、创建者或最后修改的人, 等等。</span><span class="sxs-lookup"><span data-stu-id="95240-217">Details include the segment's type, who created or last modified it, and so on.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="95240-218">**请确保您的段不重叠**。</span><span class="sxs-lookup"><span data-stu-id="95240-218">**Make sure that your segments do not overlap**.</span></span> <span data-ttu-id="95240-219">将受到信息障碍影响的每个用户应属于一个 (且仅有一个) 网段。</span><span class="sxs-lookup"><span data-stu-id="95240-219">Each user who will be affected by information barriers should belong to one (and only one) segment.</span></span> <span data-ttu-id="95240-220">任何用户都不应属于两个或多个段。</span><span class="sxs-lookup"><span data-stu-id="95240-220">No user should belong to two or more segments.</span></span> <span data-ttu-id="95240-221">(请参阅本文中[的 Contoso 定义的部分](#contosos-defined-segments)。)</span><span class="sxs-lookup"><span data-stu-id="95240-221">(See [Example: Contoso's defined segments](#contosos-defined-segments) in this article.)</span></span>

<span data-ttu-id="95240-222">定义了分段后, 请继续定义信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="95240-222">After you have defined your segments, proceed to define information barrier policies.</span></span>

### <a name="using-equals-and-not-equals-in-segment-definitions"></a><span data-ttu-id="95240-223">在段定义中使用 "等于" 和 "不等于"</span><span class="sxs-lookup"><span data-stu-id="95240-223">Using "equals" and "not equals" in segment definitions</span></span>

<span data-ttu-id="95240-224">在上面显示的第一个示例中, 我们定义了包含逻辑的片段, 即 "*部门" 等于 "HR*"。</span><span class="sxs-lookup"><span data-stu-id="95240-224">In the first example shown above, we defined a segment that includes the logic, *Department equals HR*.</span></span> <span data-ttu-id="95240-225">您还可以使用 "not 等于" 参数定义段, 如以下示例所示:</span><span class="sxs-lookup"><span data-stu-id="95240-225">You can also define segments using a "not equals" parameter, as shown in the following example:</span></span>

<span data-ttu-id="95240-226">语法`New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -ne 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="95240-226">Syntax: `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -ne 'attributevalue'"`</span></span>

<span data-ttu-id="95240-227">示例：`New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"`</span><span class="sxs-lookup"><span data-stu-id="95240-227">Example: `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"`</span></span>

<span data-ttu-id="95240-228">在此示例中, 我们定义了一个名为 NotSales 的字段, 其中包括不在销售中的所有人。</span><span class="sxs-lookup"><span data-stu-id="95240-228">In this example, we defined a segment called NotSales that includes everyone who is not in Sales.</span></span> <span data-ttu-id="95240-229">Cmdlet 的 "-ne" 部分引用 "不等于"。</span><span class="sxs-lookup"><span data-stu-id="95240-229">The "-ne" portion of the cmdlet refers to "not equals."</span></span>

<span data-ttu-id="95240-230">此外, 还可以使用 "等于" 和 "不等于" 参数定义一个段。</span><span class="sxs-lookup"><span data-stu-id="95240-230">In addition, you can define a segment using both "equals" and "not equals" parameters.</span></span>

<span data-ttu-id="95240-231">示例：`New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" and "Position -ne 'Temporary'"`</span><span class="sxs-lookup"><span data-stu-id="95240-231">Example: `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" and "Position -ne 'Temporary'"`</span></span>

<span data-ttu-id="95240-232">在此示例中, 我们定义了一个名为 " *LocalFTE* " 的字段, 其中包括本地定位且其位置未列为*临时*的用户。</span><span class="sxs-lookup"><span data-stu-id="95240-232">In this example, we defined a segment called *LocalFTE* that includes people who are locally located and whose positions are not listed as *Temporary*.</span></span>

## <a name="part-2-define-information-barrier-policies"></a><span data-ttu-id="95240-233">第2部分: 定义信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="95240-233">Part 2: Define information barrier policies</span></span>

<span data-ttu-id="95240-234">确定是否需要阻止某些网段之间的通信, 或将通信限制到某些段。</span><span class="sxs-lookup"><span data-stu-id="95240-234">Determine whether you need to prevent communications between certain segments, or limit communications to certain segments.</span></span> <span data-ttu-id="95240-235">理想情况下, 您将使用最少的策略数, 以确保您的组织符合法律和行业要求。</span><span class="sxs-lookup"><span data-stu-id="95240-235">Ideally, you'll use the minimum number of policies to ensure your organization is compliant with legal and industry requirements.</span></span>

<span data-ttu-id="95240-236">在您的用户区段列表和要定义的信息屏障策略中, 选择一个方案, 然后按照步骤操作。</span><span class="sxs-lookup"><span data-stu-id="95240-236">With your list of user segments and the information barrier policies you want to define, select a scenario, and then follow the steps.</span></span> 

- [<span data-ttu-id="95240-237">方案 1: 阻止段之间的通信</span><span class="sxs-lookup"><span data-stu-id="95240-237">Scenario 1: Block communications between segments</span></span>](#scenario-1-block-communications-between-segments)
- [<span data-ttu-id="95240-238">方案 2: 允许段仅与一个其他段进行通信</span><span class="sxs-lookup"><span data-stu-id="95240-238">Scenario 2: Allow a segment to communicate only with one other segment</span></span>](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> <span data-ttu-id="95240-239">请**确保在定义策略时, 不会向一个分段分配多个策略**。</span><span class="sxs-lookup"><span data-stu-id="95240-239">**Make sure that as you define policies, you do not assign more than one policy to a segment**.</span></span> <span data-ttu-id="95240-240">例如, 如果您为 " *sales*" 一段定义一个策略, 则不要为*sales*定义其他策略。</span><span class="sxs-lookup"><span data-stu-id="95240-240">For example, if you define one policy for a segment called *Sales*, do not define an additional policy for *Sales*.</span></span><p><span data-ttu-id="95240-241">此外, 在定义信息屏障策略时, 请确保将这些策略设置为非活动状态, 直到您准备好应用它们为止。</span><span class="sxs-lookup"><span data-stu-id="95240-241">In addition, as you define information barrier policies, make sure to set those policies to inactive status until you are ready to apply them.</span></span> <span data-ttu-id="95240-242">定义 (或编辑) 策略不会影响用户, 直到这些策略设置为 "活动状态", 然后应用。</span><span class="sxs-lookup"><span data-stu-id="95240-242">Defining (or editing) policies does not affect users until those policies are set to active status and then applied.</span></span>

<span data-ttu-id="95240-243">(请参阅本文中[的示例: Contoso 的信息屏障策略](#contosos-information-barrier-policies)。)</span><span class="sxs-lookup"><span data-stu-id="95240-243">(See [Example: Contoso's information barrier policies](#contosos-information-barrier-policies) in this article.)</span></span>

### <a name="scenario-1-block-communications-between-segments"></a><span data-ttu-id="95240-244">方案 1: 阻止段之间的通信</span><span class="sxs-lookup"><span data-stu-id="95240-244">Scenario 1: Block communications between segments</span></span>

<span data-ttu-id="95240-245">当您想要阻止多个段相互通信时, 可以定义两个策略: 每个方向一个。</span><span class="sxs-lookup"><span data-stu-id="95240-245">When you want to block segments from communicating with each other, you define two policies: one for each direction.</span></span> <span data-ttu-id="95240-246">每个策略仅阻止单向通信。</span><span class="sxs-lookup"><span data-stu-id="95240-246">Each policy blocks communication one way only.</span></span>

<span data-ttu-id="95240-247">例如, 假设您想要阻止段 A 和 Segment B 之间的通信。在这种情况下, 您可以定义一个策略, 阻止段 A 与段 B 通信, 然后定义另一个策略以防止段 B 与段 A 通信。</span><span class="sxs-lookup"><span data-stu-id="95240-247">For example, suppose you want to block communications between Segment A and Segment B. In this case, you define one policy preventing Segment A from communicating with Segment B, and then define a second policy to prevent Segment B from communicating with Segment A.</span></span>

1. <span data-ttu-id="95240-248">若要定义您的第一个阻止策略, 请将**InformationBarrierPolicy** Cmdlet 与**SegmentsBlocked**参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="95240-248">To define your first blocking policy, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsBlocked** parameter.</span></span> 

    <span data-ttu-id="95240-249">语法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"`</span><span class="sxs-lookup"><span data-stu-id="95240-249">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"`</span></span>

    <span data-ttu-id="95240-250">示例：`New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="95240-250">Example: `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive`</span></span>

    <span data-ttu-id="95240-251">在此示例中, 我们定义了名为 "*销售*" 的部门的名为 "销售 *-研究*" 的策略。</span><span class="sxs-lookup"><span data-stu-id="95240-251">In this example, we defined a policy called *Sales-Research* for a segment called *Sales*.</span></span> <span data-ttu-id="95240-252">在活动和应用后, 此策略将阻止*销售*人员与名为 "*研究*" 的部门中的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="95240-252">When active and applied, this policy prevents people in *Sales* from communicating with people in a segment called *Research*.</span></span>

2. <span data-ttu-id="95240-253">若要定义您的第二个阻塞段, 请再次将**InformationBarrierPolicy** Cmdlet 与**SegmentsBlocked**参数一起使用, 这次将段反向。</span><span class="sxs-lookup"><span data-stu-id="95240-253">To define your second blocking segment, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsBlocked** parameter again, this time with the segments reversed.</span></span>

    <span data-ttu-id="95240-254">示例：`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="95240-254">Example: `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive`</span></span>

    <span data-ttu-id="95240-255">在此示例中, 我们定义了一个名为 "*研究部*" 的策略, 以防止与 "*销售*" 通信的*研究*。</span><span class="sxs-lookup"><span data-stu-id="95240-255">In this example, we defined a policy called *Research-Sales* to prevent *Research* from communicating with *Sales*.</span></span>
 
2. <span data-ttu-id="95240-256">继续执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="95240-256">Proceed to one of the following:</span></span>

   - <span data-ttu-id="95240-257">(如果需要)[定义一个策略以允许某个分段仅与另一个网段进行通信](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)</span><span class="sxs-lookup"><span data-stu-id="95240-257">(If needed) [Define a policy to allow a segment to communicate only with one other segment](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)</span></span> 
   - <span data-ttu-id="95240-258">(在定义了所有策略之后)[应用信息屏障策略](#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="95240-258">(After all your policies are defined) [Apply information barrier policies](#part-3-apply-information-barrier-policies)</span></span>

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a><span data-ttu-id="95240-259">方案 2: 允许段仅与一个其他段进行通信</span><span class="sxs-lookup"><span data-stu-id="95240-259">Scenario 2: Allow a segment to communicate only with one other segment</span></span>

1. <span data-ttu-id="95240-260">若要允许一个分段仅与一个其他网段通信, 请使用**InformationBarrierPolicy** Cmdlet 和**SegmentsAllowed**参数。</span><span class="sxs-lookup"><span data-stu-id="95240-260">To allow one segment to communicate with only one other segment, use the **New-InformationBarrierPolicy** cmdlet with the **SegmentsAllowed** parameter.</span></span> 

    <span data-ttu-id="95240-261">语法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name"`</span><span class="sxs-lookup"><span data-stu-id="95240-261">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name"`</span></span>

    <span data-ttu-id="95240-262">示例：`New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="95240-262">Example: `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR" -State Inactive`</span></span>

    <span data-ttu-id="95240-263">在此示例中, 我们为 "*制造业*" 字段定义了称为 "制造业 *-HR* " 的策略。</span><span class="sxs-lookup"><span data-stu-id="95240-263">In this example, we defined a policy called *Manufacturing-HR* for a segment called *Manufacturing*.</span></span> <span data-ttu-id="95240-264">在活动和应用后, 此策略允许在*制造业*中的人员仅与称为*HR*的部门中的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="95240-264">When active and applied, this policy allows people in *Manufacturing* to communicate only with people in a segment called *HR*.</span></span> <span data-ttu-id="95240-265">(在这种情况下,*制造*无法与不属于*HR*的用户进行通信。)</span><span class="sxs-lookup"><span data-stu-id="95240-265">(In this case, *Manufacturing* cannot communicate with users who are not part of *HR*.)</span></span>

    <span data-ttu-id="95240-266">**如果需要, 可以使用此 cmdlet 指定多个段, 如下面的示例所示。**</span><span class="sxs-lookup"><span data-stu-id="95240-266">**If needed, you can specify multiple segments with this cmdlet, as shown in the following example.**</span></span>

    <span data-ttu-id="95240-267">语法`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name"`</span><span class="sxs-lookup"><span data-stu-id="95240-267">Syntax: `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name"`</span></span>

    <span data-ttu-id="95240-268">**示例 2: 定义一个策略以允许段仅与其他两个段进行通信**</span><span class="sxs-lookup"><span data-stu-id="95240-268">**Example 2: Define a policy to allow a segment to communicate with only two other segments**</span></span>    

    `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing" -State Inactive`

    <span data-ttu-id="95240-269">在此示例中, 我们定义了允许*研究*分段仅与*HR*和*制造业*通信的策略。</span><span class="sxs-lookup"><span data-stu-id="95240-269">In this example, we defined a policy that allows the *Research* segment to communicate with only *HR* and *Manufacturing*.</span></span>

    <span data-ttu-id="95240-270">对于要定义的每个策略, 请重复此步骤, 以允许特定段仅与特定的其他特定段进行通信。</span><span class="sxs-lookup"><span data-stu-id="95240-270">Repeat this step for each policy you want to define to allow specific segments to communicate with only certain other specific segments.</span></span>

2. <span data-ttu-id="95240-271">继续执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="95240-271">Proceed to one of the following:</span></span>

   - <span data-ttu-id="95240-272">(如果需要)[定义策略以阻止网段之间的通信](#scenario-1-block-communications-between-segments)</span><span class="sxs-lookup"><span data-stu-id="95240-272">(If needed) [Define a policy to block communications between segments](#scenario-1-block-communications-between-segments)</span></span> 
   - <span data-ttu-id="95240-273">(在定义了所有策略之后)[应用信息屏障策略](#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="95240-273">(After all your policies are defined) [Apply information barrier policies](#part-3-apply-information-barrier-policies)</span></span>

## <a name="part-3-apply-information-barrier-policies"></a><span data-ttu-id="95240-274">第3部分: 应用信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="95240-274">Part 3: Apply information barrier policies</span></span>

<span data-ttu-id="95240-275">信息屏障策略在将其设置为 "活动状态" 之前不起作用, 然后应用这些策略。</span><span class="sxs-lookup"><span data-stu-id="95240-275">Information barrier policies are not in effect until you set them to active status, and then apply the policies.</span></span>

1. <span data-ttu-id="95240-276">使用**InformationBarrierPolicy** cmdlet 可以查看已定义的策略的列表。</span><span class="sxs-lookup"><span data-stu-id="95240-276">Use the **Get-InformationBarrierPolicy** cmdlet to see a list of policies that have been defined.</span></span> <span data-ttu-id="95240-277">记下每个策略的状态和标识 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="95240-277">Note the status and identity (GUID) of each policy.</span></span>

    <span data-ttu-id="95240-278">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="95240-278">Syntax: `Get-InformationBarrierPolicy`</span></span>

2. <span data-ttu-id="95240-279">若要将策略设置为活动状态, 请使用带有**Identity**参数的**InformationBarrierPolicy** Cmdlet, 并将**State**参数设置为 "**活动**"。</span><span class="sxs-lookup"><span data-stu-id="95240-279">To set a policy to active status, use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and the **State** parameter set to **Active**.</span></span> 

    <span data-ttu-id="95240-280">语法`Set-InformationBarrierPolicy -Identity GUID -State Active`</span><span class="sxs-lookup"><span data-stu-id="95240-280">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Active`</span></span>

    <span data-ttu-id="95240-281">示例：`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`</span><span class="sxs-lookup"><span data-stu-id="95240-281">Example: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active`</span></span>
    
    <span data-ttu-id="95240-282">在此示例中, 我们将 GUID 为 " *43c37853-ea10-4b90-a23d-ab8c93772471* " 的信息屏障策略设置为 "活动" 状态。</span><span class="sxs-lookup"><span data-stu-id="95240-282">In this example, we set an information barrier policy that has the GUID *43c37853-ea10-4b90-a23d-ab8c93772471* to active status.</span></span>

    <span data-ttu-id="95240-283">根据需要对每个策略重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="95240-283">Repeat this step as appropriate for each policy.</span></span>

3. <span data-ttu-id="95240-284">完成将信息屏障策略设置为活动状态后, 请使用**InformationBarrierPoliciesApplication** Cmdlet 在 Office 365 安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="95240-284">When you have finished setting your information barrier policies to active status, use the **Start-InformationBarrierPoliciesApplication** cmdlet in the Office 365 Security & Compliance Center.</span></span>

    <span data-ttu-id="95240-285">语法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="95240-285">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="95240-286">大约半小时后, 策略将应用于您的组织的用户。</span><span class="sxs-lookup"><span data-stu-id="95240-286">After approximately a half hour, policies are applied, user by user, for your organization.</span></span> <span data-ttu-id="95240-287">如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="95240-287">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="95240-288">(一般原则是, 处理5000用户帐户需要大约一小时的时间。)</span><span class="sxs-lookup"><span data-stu-id="95240-288">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a><span data-ttu-id="95240-289">查看用户帐户、段、策略或策略应用程序的状态</span><span class="sxs-lookup"><span data-stu-id="95240-289">View status of user accounts, segments, policies, or policy application</span></span>

<span data-ttu-id="95240-290">使用 PowerShell, 可以查看用户帐户、分段、策略和策略应用程序的状态, 如下表所示。</span><span class="sxs-lookup"><span data-stu-id="95240-290">With PowerShell, you can view status of user accounts, segments, policies, and policy application, as listed in the following table.</span></span>

|<span data-ttu-id="95240-291">若要查看此</span><span class="sxs-lookup"><span data-stu-id="95240-291">To view this</span></span>  |<span data-ttu-id="95240-292">具体操作</span><span class="sxs-lookup"><span data-stu-id="95240-292">Do this</span></span>  |
|---------|---------|
|<span data-ttu-id="95240-293">用户帐户</span><span class="sxs-lookup"><span data-stu-id="95240-293">User accounts</span></span>     |<span data-ttu-id="95240-294">使用具有 Identity 参数的**InformationBarrierRecipientStatus** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95240-294">Use the **Get-InformationBarrierRecipientStatus** cmdlet with Identity parameters.</span></span> <p><span data-ttu-id="95240-295">语法`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span><span class="sxs-lookup"><span data-stu-id="95240-295">Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`</span></span> <p><span data-ttu-id="95240-296">您可以使用任何唯一标识每个用户的值, 如名称、别名、可分辨名称、规范域名、电子邮件地址或 GUID。</span><span class="sxs-lookup"><span data-stu-id="95240-296">You can use any value that uniquely identifies each user, such as name, alias, distinguished name, canonical domain name, email address, or GUID.</span></span> <p><span data-ttu-id="95240-297">示例：`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span><span class="sxs-lookup"><span data-stu-id="95240-297">Example: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`</span></span> <p><span data-ttu-id="95240-298">在此示例中, 我们引用 Office 365 中的两个用户帐户: *meganb* for *Megan*和*alexw* for *Alex*。</span><span class="sxs-lookup"><span data-stu-id="95240-298">In this example, we refer to two user accounts in Office 365: *meganb* for *Megan*, and *alexw* for *Alex*.</span></span> <p><span data-ttu-id="95240-299">(也可以将此 cmdlet 用于单个用户: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span><span class="sxs-lookup"><span data-stu-id="95240-299">(You can also use this cmdlet for a single user: `Get-InformationBarrierRecipientStatus -Identity <value>`)</span></span> <p><span data-ttu-id="95240-300">此 cmdlet 返回有关用户的信息, 如属性值和应用的任何信息障碍策略。</span><span class="sxs-lookup"><span data-stu-id="95240-300">This cmdlet returns information about users, such as attribute values and any information barrier policies that are applied.</span></span>|
|<span data-ttu-id="95240-301">段</span><span class="sxs-lookup"><span data-stu-id="95240-301">Segments</span></span>     |<span data-ttu-id="95240-302">使用**OrganizationSegment** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95240-302">Use the **Get-OrganizationSegment** cmdlet.</span></span><p><span data-ttu-id="95240-303">语法`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="95240-303">Syntax: `Get-OrganizationSegment`</span></span> <p><span data-ttu-id="95240-304">这将显示为您的组织定义的所有网段的列表。</span><span class="sxs-lookup"><span data-stu-id="95240-304">This will display a list of all segments defined for your organization.</span></span>         |
|<span data-ttu-id="95240-305">信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="95240-305">Information barrier policies</span></span>     |<span data-ttu-id="95240-306">使用**InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95240-306">Use the **Get-InformationBarrierPolicy** cmdlet.</span></span> <p> <span data-ttu-id="95240-307">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="95240-307">Syntax: `Get-InformationBarrierPolicy`</span></span> <p><span data-ttu-id="95240-308">这将显示已定义的信息障碍策略的列表及其状态。</span><span class="sxs-lookup"><span data-stu-id="95240-308">This will display a list of information barrier policies that were defined, and their status.</span></span>       |
|<span data-ttu-id="95240-309">最新的信息屏障策略应用程序</span><span class="sxs-lookup"><span data-stu-id="95240-309">The most recent information barrier policy application</span></span>     | <span data-ttu-id="95240-310">使用**InformationBarrierPoliciesApplicationStatus** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95240-310">Use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span> <p><span data-ttu-id="95240-311">语法`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="95240-311">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span><p>    <span data-ttu-id="95240-312">这将显示有关策略应用程序是已完成、失败还是正在进行的信息。</span><span class="sxs-lookup"><span data-stu-id="95240-312">This will display information about whether policy application completed, failed, or is in progress.</span></span>       |
|<span data-ttu-id="95240-313">所有信息屏障策略应用程序</span><span class="sxs-lookup"><span data-stu-id="95240-313">All information barrier policy applications</span></span>|<span data-ttu-id="95240-314">改用`Get-InformationBarrierPoliciesApplicationStatus -All $true`</span><span class="sxs-lookup"><span data-stu-id="95240-314">Use `Get-InformationBarrierPoliciesApplicationStatus -All $true`</span></span><p><span data-ttu-id="95240-315">这将显示有关策略应用程序是已完成、失败还是正在进行的信息。</span><span class="sxs-lookup"><span data-stu-id="95240-315">This will display information about whether policy application completed, failed, or is in progress.</span></span>|

## <a name="stop-a-policy-application"></a><span data-ttu-id="95240-316">停止策略应用程序</span><span class="sxs-lookup"><span data-stu-id="95240-316">Stop a policy application</span></span>

<span data-ttu-id="95240-317">如果在您开始应用信息屏障策略后, 您想要停止应用这些策略, 请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="95240-317">If, after you have started applying information barrier policies, you want to stop those policies from being applied, use the following procedure.</span></span> <span data-ttu-id="95240-318">请注意, 此过程将需要大约30-35 分钟才能开始。</span><span class="sxs-lookup"><span data-stu-id="95240-318">Keep in mind that it will take approximately 30-35 minutes for the process to begin.</span></span>

1. <span data-ttu-id="95240-319">若要查看最新信息屏障策略应用程序的状态, 请使用**InformationBarrierPoliciesApplicationStatus** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95240-319">To view the status of the most recent information barrier policy application, use the **Get-InformationBarrierPoliciesApplicationStatus** cmdlet.</span></span>

    <span data-ttu-id="95240-320">语法`Get-InformationBarrierPoliciesApplicationStatus`</span><span class="sxs-lookup"><span data-stu-id="95240-320">Syntax: `Get-InformationBarrierPoliciesApplicationStatus`</span></span>

    <span data-ttu-id="95240-321">记下应用程序的 GUID。</span><span class="sxs-lookup"><span data-stu-id="95240-321">Note the application's GUID.</span></span>

2. <span data-ttu-id="95240-322">将**InformationBarrierPoliciesApplication** Cmdlet 与 Identity 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="95240-322">Use the **Stop-InformationBarrierPoliciesApplication** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="95240-323">语法`Stop-InformationBarrierPoliciesApplication -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="95240-323">Syntax:  `Stop-InformationBarrierPoliciesApplication -Identity GUID`</span></span>

    <span data-ttu-id="95240-324">示例：`InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span><span class="sxs-lookup"><span data-stu-id="95240-324">Example: `InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1`</span></span>

## <a name="edit-a-segment-or-a-policy"></a><span data-ttu-id="95240-325">编辑段或策略</span><span class="sxs-lookup"><span data-stu-id="95240-325">Edit a segment or a policy</span></span>

### <a name="edit-a-segment"></a><span data-ttu-id="95240-326">编辑段</span><span class="sxs-lookup"><span data-stu-id="95240-326">Edit a segment</span></span>

1. <span data-ttu-id="95240-327">若要查看所有现有段, 请使用**OrganizationSegment** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95240-327">To view all existing segments, use the **Get-OrganizationSegment** cmdlet.</span></span>
    
    <span data-ttu-id="95240-328">语法`Get-OrganizationSegment`</span><span class="sxs-lookup"><span data-stu-id="95240-328">Syntax: `Get-OrganizationSegment`</span></span>

    <span data-ttu-id="95240-329">你将看到每个段的列表和详细信息, 如段类型、其 UserGroupFilter 值、创建日期或上次修改时间、GUID 等。</span><span class="sxs-lookup"><span data-stu-id="95240-329">You will see a list of segments and details for each, such as segment type, its UserGroupFilter value, who created or last modified it, GUID, and so on.</span></span>

    > [!TIP]
    > <span data-ttu-id="95240-330">打印或保存段列表以便日后参考。</span><span class="sxs-lookup"><span data-stu-id="95240-330">Print or save your list of segments for reference later.</span></span> <span data-ttu-id="95240-331">例如, 如果您想要编辑某一段, 则需要知道它的名称或标识值 (这与 Identity 参数一起使用)。</span><span class="sxs-lookup"><span data-stu-id="95240-331">For example, if you want to edit a segment, you will need to know its name or identify value (this is used with the Identity parameter).</span></span>

2. <span data-ttu-id="95240-332">若要编辑分段, 请使用**OrganizationSegment** Cmdlet 和**Identity**参数以及相关详细信息。</span><span class="sxs-lookup"><span data-stu-id="95240-332">To edit a segment, use the **Set-OrganizationSegment** cmdlet with the **Identity** parameter and relevant details.</span></span> 

    <span data-ttu-id="95240-333">语法`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span><span class="sxs-lookup"><span data-stu-id="95240-333">Syntax: `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`</span></span>

    <span data-ttu-id="95240-334">示例：`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span><span class="sxs-lookup"><span data-stu-id="95240-334">Example: `Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"`</span></span>

    <span data-ttu-id="95240-335">在此示例中, 对于具有 GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*的段, 我们将部门名称更新为 "HRDept"。</span><span class="sxs-lookup"><span data-stu-id="95240-335">In this example, for the segment that has the GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*, we updated the department name to "HRDept".</span></span>

<span data-ttu-id="95240-336">为组织编辑完段后, 可以继续[定义](#part-2-define-information-barrier-policies)或[编辑](#edit-a-policy)信息屏障策略。</span><span class="sxs-lookup"><span data-stu-id="95240-336">When you have finished editing segments for your organization, you can proceed to [define](#part-2-define-information-barrier-policies) or [edit](#edit-a-policy) information barrier policies.</span></span>

### <a name="edit-a-policy"></a><span data-ttu-id="95240-337">编辑策略</span><span class="sxs-lookup"><span data-stu-id="95240-337">Edit a policy</span></span>

1. <span data-ttu-id="95240-338">若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95240-338">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="95240-339">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="95240-339">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="95240-340">在结果列表中, 标识要更改的策略。</span><span class="sxs-lookup"><span data-stu-id="95240-340">In the list of results, identify the policy that you want to change.</span></span> <span data-ttu-id="95240-341">记下策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="95240-341">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="95240-342">将**InformationBarrierPolicy** Cmdlet 与**Identity**参数一起使用, 并指定要进行的更改。</span><span class="sxs-lookup"><span data-stu-id="95240-342">Use the **Set-InformationBarrierPolicy** cmdlet with an **Identity** parameter, and specify the changes you want to make.</span></span>

    <span data-ttu-id="95240-343">示例: 假设定义了一个策略来阻止与*销售*和*市场营销*部门通信的*研究*分段。</span><span class="sxs-lookup"><span data-stu-id="95240-343">Example: Suppose a policy was defined to block the *Research* segment from communicating with the *Sales* and *Marketing* segments.</span></span> <span data-ttu-id="95240-344">该策略是使用以下 cmdlet 定义的:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span><span class="sxs-lookup"><span data-stu-id="95240-344">The policy was defined by using this cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`</span></span>
    
    <span data-ttu-id="95240-345">假设我们要对其进行更改, 以便*研究*部门中的人员只能与*HR*部门中的人员进行通信。</span><span class="sxs-lookup"><span data-stu-id="95240-345">Suppose we want to change it so that people in the *Research* segment can only communicate with people in the *HR* segment.</span></span> <span data-ttu-id="95240-346">若要进行此更改, 我们使用以下 cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span><span class="sxs-lookup"><span data-stu-id="95240-346">To make this change, we use this cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`</span></span>

    <span data-ttu-id="95240-347">在此示例中, 我们将 "SegmentsBlocked" 更改为 "SegmentsAllowed", 并指定*HR*段。</span><span class="sxs-lookup"><span data-stu-id="95240-347">In this example, we changed "SegmentsBlocked" to "SegmentsAllowed" and specified the *HR* segment.</span></span>

3. <span data-ttu-id="95240-348">完成策略的编辑后, 请确保应用所做的更改。</span><span class="sxs-lookup"><span data-stu-id="95240-348">When you are finished editing a policy, make sure to apply your changes.</span></span> <span data-ttu-id="95240-349">(请参阅[Apply 信息屏障策略](#part-3-apply-information-barrier-policies)。)</span><span class="sxs-lookup"><span data-stu-id="95240-349">(See [Apply information barrier policies](#part-3-apply-information-barrier-policies).)</span></span>

### <a name="remove-a-policy"></a><span data-ttu-id="95240-350">删除策略</span><span class="sxs-lookup"><span data-stu-id="95240-350">Remove a policy</span></span>

1. <span data-ttu-id="95240-351">若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95240-351">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="95240-352">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="95240-352">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="95240-353">在结果列表中, 标识要删除的策略。</span><span class="sxs-lookup"><span data-stu-id="95240-353">In the list of results, identify the policy that you want to remove.</span></span> <span data-ttu-id="95240-354">记下策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="95240-354">Note the policy's GUID and name.</span></span> <span data-ttu-id="95240-355">请确保将策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="95240-355">Make sure the policy is set to inactive status.</span></span>

2. <span data-ttu-id="95240-356">将**InformationBarrierPolicy** Cmdlet 与 Identity 参数一起使用。</span><span class="sxs-lookup"><span data-stu-id="95240-356">Use the **Remove-InformationBarrierPolicy** cmdlet with an Identity parameter.</span></span>

    <span data-ttu-id="95240-357">语法`Remove-InformationBarrierPolicy -Identity GUID`</span><span class="sxs-lookup"><span data-stu-id="95240-357">Syntax: `Remove-InformationBarrierPolicy -Identity GUID`</span></span>

    <span data-ttu-id="95240-358">示例: 假设我们要删除 GUID 为*43c37853-ea10-4b90-a23d-ab8c93772471*的策略。</span><span class="sxs-lookup"><span data-stu-id="95240-358">Example: Suppose we want to remove a policy that has GUID *43c37853-ea10-4b90-a23d-ab8c93772471*.</span></span> <span data-ttu-id="95240-359">为此, 我们使用此 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="95240-359">To do this, we use this cmdlet:</span></span>
    
    `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471`

    <span data-ttu-id="95240-360">出现提示时, 请确认更改。</span><span class="sxs-lookup"><span data-stu-id="95240-360">When prompted, confirm the change.</span></span>

3. <span data-ttu-id="95240-361">对要删除的每个策略重复步骤1-2。</span><span class="sxs-lookup"><span data-stu-id="95240-361">Repeat steps 1-2 for each policy you want to remove.</span></span>

4. <span data-ttu-id="95240-362">删除完策略后, 应用所做的更改。</span><span class="sxs-lookup"><span data-stu-id="95240-362">When you are finished removing policies, apply your changes.</span></span> <span data-ttu-id="95240-363">为此, 请使用**InformationBarrierPoliciesApplication** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95240-363">To do this, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="95240-364">语法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="95240-364">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="95240-365">为您的组织应用更改的用户。</span><span class="sxs-lookup"><span data-stu-id="95240-365">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="95240-366">如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="95240-366">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span>

### <a name="set-a-policy-to-inactive-status"></a><span data-ttu-id="95240-367">将策略设置为非活动状态</span><span class="sxs-lookup"><span data-stu-id="95240-367">Set a policy to inactive status</span></span>

1. <span data-ttu-id="95240-368">若要查看当前信息屏障策略的列表, 请使用**InformationBarrierPolicy** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95240-368">To view a list of current information barrier policies, use the **Get-InformationBarrierPolicy** cmdlet.</span></span>

    <span data-ttu-id="95240-369">语法`Get-InformationBarrierPolicy`</span><span class="sxs-lookup"><span data-stu-id="95240-369">Syntax: `Get-InformationBarrierPolicy`</span></span>

    <span data-ttu-id="95240-370">在结果列表中, 标识要更改 (或删除) 的策略。</span><span class="sxs-lookup"><span data-stu-id="95240-370">In the list of results, identify the policy that you want to change (or remove).</span></span> <span data-ttu-id="95240-371">记下策略的 GUID 和名称。</span><span class="sxs-lookup"><span data-stu-id="95240-371">Note the policy's GUID and name.</span></span>

2. <span data-ttu-id="95240-372">若要将策略的状态设置为 "非活动", 请使用带有 Identity 参数的**InformationBarrierPolicy** cmdlet, 将 State 参数设置为 "非活动"。</span><span class="sxs-lookup"><span data-stu-id="95240-372">To set the policy's status to inactive, use the **Set-InformationBarrierPolicy** cmdlet with an Identity parameter and the State parameter set to Inactive.</span></span>

    <span data-ttu-id="95240-373">语法`Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span><span class="sxs-lookup"><span data-stu-id="95240-373">Syntax: `Set-InformationBarrierPolicy -Identity GUID -State Inactive`</span></span>

    `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive`

    <span data-ttu-id="95240-374">在此示例中, 我们将具有 GUID *43c37853-ea10-4b90-a23d-ab8c9377247*的信息屏障策略设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="95240-374">In this example, we set an information barrier policy that has GUID *43c37853-ea10-4b90-a23d-ab8c9377247* to an inactive status.</span></span>

3. <span data-ttu-id="95240-375">若要应用所做的更改, 请使用**InformationBarrierPoliciesApplication** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="95240-375">To apply your changes, use the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span>

    <span data-ttu-id="95240-376">语法`Start-InformationBarrierPoliciesApplication`</span><span class="sxs-lookup"><span data-stu-id="95240-376">Syntax: `Start-InformationBarrierPoliciesApplication`</span></span>

    <span data-ttu-id="95240-377">为您的组织应用更改的用户。</span><span class="sxs-lookup"><span data-stu-id="95240-377">Changes are applied, user by user, for your organization.</span></span> <span data-ttu-id="95240-378">如果您的组织规模较大, 则可能需要24小时 (或更多) 才能完成此过程。</span><span class="sxs-lookup"><span data-stu-id="95240-378">If your organization is large, it can take 24 hours (or more) for this process to complete.</span></span> <span data-ttu-id="95240-379">(一般原则是, 处理5000用户帐户需要大约一小时的时间。)</span><span class="sxs-lookup"><span data-stu-id="95240-379">(As a general guideline, it takes about an hour to process 5,000 user accounts.)</span></span>

<span data-ttu-id="95240-380">在这种情况下, 一个或多个信息障碍策略将设置为非活动状态。</span><span class="sxs-lookup"><span data-stu-id="95240-380">At this point, one or more information barrier policies are set to inactive status.</span></span> <span data-ttu-id="95240-381">在这里, 您可以执行以下任一操作:</span><span class="sxs-lookup"><span data-stu-id="95240-381">From here, you can do any of the following:</span></span>
- <span data-ttu-id="95240-382">将其保留为 (策略设置为非活动状态对用户没有影响)</span><span class="sxs-lookup"><span data-stu-id="95240-382">Keep it as is (a policy set to inactive status has no effect on users)</span></span>
- [<span data-ttu-id="95240-383">编辑策略</span><span class="sxs-lookup"><span data-stu-id="95240-383">Edit a policy</span></span>](#edit-a-policy) 
- [<span data-ttu-id="95240-384">删除策略</span><span class="sxs-lookup"><span data-stu-id="95240-384">Remove a policy</span></span>](#remove-a-policy)

## <a name="example-contosos-departments-segments-and-policies"></a><span data-ttu-id="95240-385">示例: Contoso 的部门、分段和策略</span><span class="sxs-lookup"><span data-stu-id="95240-385">Example: Contoso's departments, segments, and policies</span></span>

<span data-ttu-id="95240-386">若要了解组织如何采用定义段落和策略的方法, 请考虑以下示例。</span><span class="sxs-lookup"><span data-stu-id="95240-386">To see how an organization might approach defining segments and policies, consider the following example.</span></span>

### <a name="contosos-departments-and-plan"></a><span data-ttu-id="95240-387">Contoso 的部门和规划</span><span class="sxs-lookup"><span data-stu-id="95240-387">Contoso's departments and plan</span></span>

<span data-ttu-id="95240-388">Contoso 有五个部门: HR、销售、营销、研究和制造。</span><span class="sxs-lookup"><span data-stu-id="95240-388">Contoso has five departments: HR, Sales, Marketing, Research, and Manufacturing.</span></span> <span data-ttu-id="95240-389">为了保持与行业法规的兼容性, 某些部门中的人员不应与其他部门通信, 如下表所示:</span><span class="sxs-lookup"><span data-stu-id="95240-389">In order to remain compliant with industry regulations, people in some departments are not supposed to communicate with other departments, as listed in the following table:</span></span>

|<span data-ttu-id="95240-390">段落</span><span class="sxs-lookup"><span data-stu-id="95240-390">Segment</span></span>  |<span data-ttu-id="95240-391">可以与</span><span class="sxs-lookup"><span data-stu-id="95240-391">Can talk to</span></span>  |<span data-ttu-id="95240-392">无法对话</span><span class="sxs-lookup"><span data-stu-id="95240-392">Cannot talk to</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="95240-393">HR</span><span class="sxs-lookup"><span data-stu-id="95240-393">HR</span></span>     |<span data-ttu-id="95240-394">每个人</span><span class="sxs-lookup"><span data-stu-id="95240-394">Everyone</span></span>         |<span data-ttu-id="95240-395">(无限制)</span><span class="sxs-lookup"><span data-stu-id="95240-395">(no restrictions)</span></span>         |
|<span data-ttu-id="95240-396">销售</span><span class="sxs-lookup"><span data-stu-id="95240-396">Sales</span></span>     |<span data-ttu-id="95240-397">HR、营销、制造业</span><span class="sxs-lookup"><span data-stu-id="95240-397">HR, Marketing, Manufacturing</span></span>         |<span data-ttu-id="95240-398">信息检索</span><span class="sxs-lookup"><span data-stu-id="95240-398">Research</span></span>         |
|<span data-ttu-id="95240-399">营销</span><span class="sxs-lookup"><span data-stu-id="95240-399">Marketing</span></span>     |<span data-ttu-id="95240-400">每个人</span><span class="sxs-lookup"><span data-stu-id="95240-400">Everyone</span></span>         |<span data-ttu-id="95240-401">(无限制)</span><span class="sxs-lookup"><span data-stu-id="95240-401">(no restrictions)</span></span>         |
|<span data-ttu-id="95240-402">信息检索</span><span class="sxs-lookup"><span data-stu-id="95240-402">Research</span></span>     |<span data-ttu-id="95240-403">HR、营销、制造业</span><span class="sxs-lookup"><span data-stu-id="95240-403">HR, Marketing, Manufacturing</span></span>        |<span data-ttu-id="95240-404">销售</span><span class="sxs-lookup"><span data-stu-id="95240-404">Sales</span></span>     |
|<span data-ttu-id="95240-405">制造业</span><span class="sxs-lookup"><span data-stu-id="95240-405">Manufacturing</span></span> |<span data-ttu-id="95240-406">HR、营销</span><span class="sxs-lookup"><span data-stu-id="95240-406">HR, Marketing</span></span> |<span data-ttu-id="95240-407">除 HR 或营销之外的任何人</span><span class="sxs-lookup"><span data-stu-id="95240-407">Anyone other than HR or Marketing</span></span> |

<span data-ttu-id="95240-408">考虑到这一点, Contoso 的计划包括三个信息屏障策略:</span><span class="sxs-lookup"><span data-stu-id="95240-408">With this in mind, Contoso's plan includes three information barrier policies:</span></span>

1. <span data-ttu-id="95240-409">旨在防止销售人员与信息检索通信的策略 (和另一个策略, 以防止与销售通信的信息检索)</span><span class="sxs-lookup"><span data-stu-id="95240-409">A policy designed to prevent Sales from communicating with Research (and another policy to prevent Research from communicating with Sales)</span></span>
2. <span data-ttu-id="95240-410">旨在允许制造业仅与 HR 和营销进行通信的策略</span><span class="sxs-lookup"><span data-stu-id="95240-410">A policy designed to allow Manufacturing to communicate with HR and Marketing only</span></span> 

<span data-ttu-id="95240-411">不需要为 HR 或营销定义策略。</span><span class="sxs-lookup"><span data-stu-id="95240-411">It's not necessary to define policies for HR or Marketing.</span></span>

### <a name="contosos-defined-segments"></a><span data-ttu-id="95240-412">Contoso 定义的段</span><span class="sxs-lookup"><span data-stu-id="95240-412">Contoso's defined segments</span></span>

<span data-ttu-id="95240-413">Contoso 将使用 Azure Active Directory 中的 "部门" 属性来定义段, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="95240-413">Contoso will use the Department attribute in Azure Active Directory to define segments, as follows:</span></span>

|<span data-ttu-id="95240-414">部门</span><span class="sxs-lookup"><span data-stu-id="95240-414">Department</span></span>  |<span data-ttu-id="95240-415">段定义</span><span class="sxs-lookup"><span data-stu-id="95240-415">Segment Definition</span></span>  |
|---------|---------|
|<span data-ttu-id="95240-416">HR</span><span class="sxs-lookup"><span data-stu-id="95240-416">HR</span></span>     | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"`        |
|<span data-ttu-id="95240-417">销售</span><span class="sxs-lookup"><span data-stu-id="95240-417">Sales</span></span>     | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"`        |
|<span data-ttu-id="95240-418">营销</span><span class="sxs-lookup"><span data-stu-id="95240-418">Marketing</span></span>     | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"`        |
|<span data-ttu-id="95240-419">信息检索</span><span class="sxs-lookup"><span data-stu-id="95240-419">Research</span></span>     | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"`        |
|<span data-ttu-id="95240-420">制造业</span><span class="sxs-lookup"><span data-stu-id="95240-420">Manufacturing</span></span>     | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"`        |

<span data-ttu-id="95240-421">定义段后, Contoso 将继续定义策略。</span><span class="sxs-lookup"><span data-stu-id="95240-421">With the segments defined, Contoso proceeds to define policies.</span></span> 

### <a name="contosos-information-barrier-policies"></a><span data-ttu-id="95240-422">Contoso 的信息屏障策略</span><span class="sxs-lookup"><span data-stu-id="95240-422">Contoso's information barrier policies</span></span>

<span data-ttu-id="95240-423">Contoso 定义了三种策略, 如下表所述:</span><span class="sxs-lookup"><span data-stu-id="95240-423">Contoso defines three polices, as described in the following table:</span></span>

|<span data-ttu-id="95240-424">策略</span><span class="sxs-lookup"><span data-stu-id="95240-424">Policy</span></span>  |<span data-ttu-id="95240-425">策略定义</span><span class="sxs-lookup"><span data-stu-id="95240-425">Policy Definition</span></span>  |
|---------|---------|
|<span data-ttu-id="95240-426">策略 1: 防止销售与信息检索通信</span><span class="sxs-lookup"><span data-stu-id="95240-426">Policy 1: Prevent Sales from communicating with Research</span></span>     | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> <span data-ttu-id="95240-427">在此示例中, 信息屏障策略称为 "*销售-研究*"。</span><span class="sxs-lookup"><span data-stu-id="95240-427">In this example, the information barrier policy is called *Sales-Research*.</span></span> <span data-ttu-id="95240-428">当此策略处于活动状态且已应用时, 它将有助于阻止销售部门中的用户与研究网段中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="95240-428">When this policy is active and applied, it will help prevent users who are in the Sales segment from communicating with users in the Research segment.</span></span> <span data-ttu-id="95240-429">这是单向策略;它不会阻止研究与销售通信。</span><span class="sxs-lookup"><span data-stu-id="95240-429">This is a one-way policy; it won't prevent Research from communicating with Sales.</span></span> <span data-ttu-id="95240-430">为此, 需要策略2。</span><span class="sxs-lookup"><span data-stu-id="95240-430">For that, Policy 2 is needed.</span></span>      |
|<span data-ttu-id="95240-431">策略 2: 防止与销售通信的研究</span><span class="sxs-lookup"><span data-stu-id="95240-431">Policy 2: Prevent Research from communicating with Sales</span></span>     | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> <span data-ttu-id="95240-432">在此示例中, 信息屏障策略称为 "*研究-销售*"。</span><span class="sxs-lookup"><span data-stu-id="95240-432">In this example, the information barrier policy is called *Research-Sales*.</span></span> <span data-ttu-id="95240-433">当此策略处于活动状态且已应用时, 它将有助于防止在研究网段中的用户与销售部门中的用户进行通信。</span><span class="sxs-lookup"><span data-stu-id="95240-433">When this policy is active and applied, it will help prevent users who are in the Research segment from communicating with users in the Sales segment.</span></span>       |
|<span data-ttu-id="95240-434">策略 3: 允许制造业仅与 HR 和营销进行通信</span><span class="sxs-lookup"><span data-stu-id="95240-434">Policy 3: Allow Manufacturing to communicate with HR and Marketing only</span></span>     | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing" -State Inactive` <p><span data-ttu-id="95240-435">在这种情况下, 信息屏障策略称为 "*制造业-HRMarketing*"。</span><span class="sxs-lookup"><span data-stu-id="95240-435">In this case, the information barrier policy is called *Manufacturing-HRMarketing*.</span></span> <span data-ttu-id="95240-436">当此策略处于活动状态且已应用时, 生产只能与 HR 和 Marketing 进行通信。</span><span class="sxs-lookup"><span data-stu-id="95240-436">When this policy is active and applied, Manufacturing can communicate only with HR and Marketing.</span></span> <span data-ttu-id="95240-437">请注意, 不限制 HR 和市场营销与其他段进行通信。</span><span class="sxs-lookup"><span data-stu-id="95240-437">Note that HR and Marketing are not restricted from communicating with other segments.</span></span> |

<span data-ttu-id="95240-438">通过定义的段和策略, Contoso 通过运行**InformationBarrierPoliciesApplication** cmdlet 来应用这些策略。</span><span class="sxs-lookup"><span data-stu-id="95240-438">With segments and policies defined, Contoso applies the policies by running the **Start-InformationBarrierPoliciesApplication** cmdlet.</span></span> 

<span data-ttu-id="95240-439">完成后, Contoso 就符合法律和行业要求。</span><span class="sxs-lookup"><span data-stu-id="95240-439">When that finishes, Contoso is compliant with legal and industry requirements.</span></span>

## <a name="related-articles"></a><span data-ttu-id="95240-440">相关文章</span><span class="sxs-lookup"><span data-stu-id="95240-440">Related articles</span></span>

[<span data-ttu-id="95240-441">获取信息障碍概述</span><span class="sxs-lookup"><span data-stu-id="95240-441">Get an overview of information barriers</span></span>](information-barriers.md)

[<span data-ttu-id="95240-442">了解有关 Microsoft 团队中的信息障碍的详细信息</span><span class="sxs-lookup"><span data-stu-id="95240-442">Learn more about information barriers in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[<span data-ttu-id="95240-443">信息屏障策略的属性 (预览)</span><span class="sxs-lookup"><span data-stu-id="95240-443">Attributes for information barrier policies (Preview)</span></span>](information-barriers-attributes.md)

[<span data-ttu-id="95240-444">解决信息障碍 (预览)</span><span class="sxs-lookup"><span data-stu-id="95240-444">Troubleshooting information barriers (Preview)</span></span>](information-barriers-troubleshooting.md)
