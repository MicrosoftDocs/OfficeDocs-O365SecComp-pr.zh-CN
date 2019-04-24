---
title: 配置组织的监督策略
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: 设置监管审核策略以捕获员工通信以供审阅。
ms.openlocfilehash: 92630b1405af6e297390751d9b00e24a82e03087
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32259510"
---
# <a name="configure-supervision-policies-for-your-organization"></a><span data-ttu-id="a64d7-103">配置组织的监督策略</span><span class="sxs-lookup"><span data-stu-id="a64d7-103">Configure supervision policies for your organization</span></span>

<span data-ttu-id="a64d7-104">使用监督策略来捕获由内部或外部审阅者进行检查的员工通信。</span><span class="sxs-lookup"><span data-stu-id="a64d7-104">Use supervision policies to capture employee communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="a64d7-105">有关监察策略如何帮助您监视组织中的通信的详细信息, 请参阅[Office 365 中的监察策略](supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="a64d7-105">For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a64d7-106">监督策略监视的用户必须拥有 Microsoft 365 E5 合规性许可证、具有高级合规性加载项的 Office 365 企业版 E3 许可证, 或包含在 office 365 企业版 E5 订阅中。</span><span class="sxs-lookup"><span data-stu-id="a64d7-106">Users monitored by supervision policies must have either a Microsoft 365 E5 Compliance license, an Office 365 Enterprise E3 license with the Advanced Compliance add-on, or be included in an Office 365 Enterprise E5 subscription.</span></span>
<span data-ttu-id="a64d7-107">如果你没有现有的企业版 E5 计划, 并且想要尝试监督, 则可以[注册 Office 365 企业版 e5 的试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="a64d7-107">If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="a64d7-108">按照以下步骤在 Office 365 组织中设置和使用监督:</span><span class="sxs-lookup"><span data-stu-id="a64d7-108">Follow these steps to set up and use supervision in your Office 365 organization:</span></span>
  
- <span data-ttu-id="a64d7-109">**步骤 1 (可选)** - [为监督设置组 (可选)](#step-1---set-up-groups-for-supervision-optional)</span><span class="sxs-lookup"><span data-stu-id="a64d7-109">**Step 1 (optional)** - [Set up groups for Supervision (optional)](#step-1---set-up-groups-for-supervision-optional)</span></span>

    <span data-ttu-id="a64d7-110">在开始使用监督之前, 请确定哪些用户需要查看通信以及谁将执行检查。</span><span class="sxs-lookup"><span data-stu-id="a64d7-110">Before you start using supervision, determine who needs communications reviewed and who will perform reviews.</span></span> <span data-ttu-id="a64d7-111">如果您只想开始几个用户来了解监督工作的工作方式, 则可以跳过 "立即" 设置组。</span><span class="sxs-lookup"><span data-stu-id="a64d7-111">If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="a64d7-112">**步骤 2 (必需)** - [使监督在您的组织中可用 (必需)](#step-2---make-supervision-available-in-your-organization-required)</span><span class="sxs-lookup"><span data-stu-id="a64d7-112">**Step 2 (required)** - [Make supervision available in your organization (required)](#step-2---make-supervision-available-in-your-organization-required)</span></span>

    <span data-ttu-id="a64d7-113">将自己添加到监管审核角色组, 以便您可以设置策略。</span><span class="sxs-lookup"><span data-stu-id="a64d7-113">Add yourself to the Supervisory Review role group so you can set up policies.</span></span> <span data-ttu-id="a64d7-114">分配此角色的任何人都可以访问合规中心中的**监督**页面。</span><span class="sxs-lookup"><span data-stu-id="a64d7-114">Anyone who has this role assigned can access the **Supervision** page in the Compliance Center.</span></span> <span data-ttu-id="a64d7-115">如果 reviewable 电子邮件托管在 Exchange online 中, 则每个审阅者都必须具有[对 exchange online 的远程 PowerShell 访问权限](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a64d7-115">If reviewable email is hosted on Exchange Online, each reviewer must have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="a64d7-116">**步骤 3 (可选)** - [创建自定义敏感信息类型和自定义关键字词典](#step-3---create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span><span class="sxs-lookup"><span data-stu-id="a64d7-116">**Step 3 (optional)** - [Create custom sensitive information types and custom keyword dictionaries](#step-3---create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)</span></span>

    <span data-ttu-id="a64d7-117">如果您需要针对监督策略的自定义敏感信息类型或自定义关键字词典, 则需要在启动监督向导之前创建它。</span><span class="sxs-lookup"><span data-stu-id="a64d7-117">If you need a custom sensitive info type or a custom keyword dictionary for your supervision policy, you need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="a64d7-118">**步骤 4 (必需)** - [设置监督策略](#step-4---set-up-a-supervision-policy-required)</span><span class="sxs-lookup"><span data-stu-id="a64d7-118">**Step 4 (required)** - [Set up a supervision policy](#step-4---set-up-a-supervision-policy-required)</span></span>

    <span data-ttu-id="a64d7-119">在合规中心中创建监督策略。</span><span class="sxs-lookup"><span data-stu-id="a64d7-119">You create supervision policies in the Compliance Center.</span></span> <span data-ttu-id="a64d7-120">这些策略定义哪些通信将在组织中进行审核, 并指定执行审阅的用户。</span><span class="sxs-lookup"><span data-stu-id="a64d7-120">These policies define which communications are subject to review in your organization and specifies who performs reviews.</span></span> <span data-ttu-id="a64d7-121">通信包括电子邮件和 Microsoft 团队通信, 以及第三方平台通信 (如 Facebook、Twitter 等)</span><span class="sxs-lookup"><span data-stu-id="a64d7-121">Communications include email and Microsoft Teams communications, and 3rd-party platform communications (such as Facebook, Twitter, etc.)</span></span>

- <span data-ttu-id="a64d7-122">**第5步-(可选)**[测试监督策略](#step-5---test-your-supervision-policy-optional)</span><span class="sxs-lookup"><span data-stu-id="a64d7-122">**Step 5 - (optional)** [Test your supervision policy](#step-5---test-your-supervision-policy-optional)</span></span>

    <span data-ttu-id="a64d7-123">测试您的监督策略以确保其按预期工作。</span><span class="sxs-lookup"><span data-stu-id="a64d7-123">Test your supervision policy to make sure it functions as desired.</span></span> <span data-ttu-id="a64d7-124">一定要确保符合性策略满足您的标准。</span><span class="sxs-lookup"><span data-stu-id="a64d7-124">It is important to ensure that your compliance strategy is meeting your standards.</span></span>

- <span data-ttu-id="a64d7-125">**步骤 6-(可选)**[为不希望使用 Office 365 监督仪表板或 web 上的 outlook (以前称为 Outlook web App) 的审阅者配置 Outlook 以查看受监督的通信](#step-6---configure-outlook-for-reviewers-optional)</span><span class="sxs-lookup"><span data-stu-id="a64d7-125">**Step 6 - (optional)** [Configure Outlook for reviewers who do not want to use Office 365 supervision dashboard or Outlook on the web (formerly known as Outlook Web App) to review supervised communications](#step-6---configure-outlook-for-reviewers-optional)</span></span>

    <span data-ttu-id="a64d7-126">将 outlook 配置为向审阅者授予对 outlook 客户端中的监督功能的访问权限, 以便他们能够评估和分类每个项目。</span><span class="sxs-lookup"><span data-stu-id="a64d7-126">Configure Outlook to give reviewers access to the supervision functionality within the Outlook client so they can assess and categorize each item.</span></span>

## <a name="step-1---set-up-groups-for-supervision-optional"></a><span data-ttu-id="a64d7-127">步骤 1-设置监控组 (可选)</span><span class="sxs-lookup"><span data-stu-id="a64d7-127">Step 1 - Set up groups for Supervision (optional)</span></span>

 <span data-ttu-id="a64d7-128">在创建监督策略时, 您需要定义哪些用户已查看其通信, 以及谁执行了评论。</span><span class="sxs-lookup"><span data-stu-id="a64d7-128">When you create a supervision policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="a64d7-129">在策略中, 您将使用电子邮件地址来标识个人或用户组。</span><span class="sxs-lookup"><span data-stu-id="a64d7-129">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="a64d7-130">为简化您的设置, 您可以为已查看其通信的用户创建组, 并为查看这些通信的用户分组。</span><span class="sxs-lookup"><span data-stu-id="a64d7-130">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="a64d7-131">如果使用的是组, 可能需要多个。</span><span class="sxs-lookup"><span data-stu-id="a64d7-131">If you're using groups, you may need several.</span></span> <span data-ttu-id="a64d7-132">例如, 您想要监视两个不同的人员组之间的通信, 或者如果您想要指定一个不受监督的组。</span><span class="sxs-lookup"><span data-stu-id="a64d7-132">For example, you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="a64d7-133">使用以下图表可帮助您在组织中配置监督策略的组:</span><span class="sxs-lookup"><span data-stu-id="a64d7-133">Use the following chart to help you configure groups in your organization for supervision policies:</span></span>

| <span data-ttu-id="a64d7-134">**Policy 成员**</span><span class="sxs-lookup"><span data-stu-id="a64d7-134">**Policy Member**</span></span> | <span data-ttu-id="a64d7-135">**支持的组**</span><span class="sxs-lookup"><span data-stu-id="a64d7-135">**Supported Groups**</span></span> | <span data-ttu-id="a64d7-136">**不受支持的组**</span><span class="sxs-lookup"><span data-stu-id="a64d7-136">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="a64d7-137">受监督用户</span><span class="sxs-lookup"><span data-stu-id="a64d7-137">Supervised users</span></span> | <span data-ttu-id="a64d7-138">通讯组</span><span class="sxs-lookup"><span data-stu-id="a64d7-138">Distribution groups</span></span> <br> <span data-ttu-id="a64d7-139">Office 365 组</span><span class="sxs-lookup"><span data-stu-id="a64d7-139">Office 365 groups</span></span> | <span data-ttu-id="a64d7-140">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="a64d7-140">Dynamic distribution groups</span></span> |
| <span data-ttu-id="a64d7-141">Reviewers</span><span class="sxs-lookup"><span data-stu-id="a64d7-141">Reviewers</span></span> | <span data-ttu-id="a64d7-142">启用邮件功能的安全组</span><span class="sxs-lookup"><span data-stu-id="a64d7-142">Mail-enabled security groups</span></span>  | <span data-ttu-id="a64d7-143">通讯组</span><span class="sxs-lookup"><span data-stu-id="a64d7-143">Distribution groups</span></span> <br> <span data-ttu-id="a64d7-144">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="a64d7-144">Dynamic distribution groups</span></span> |
  
<span data-ttu-id="a64d7-145">若要在大型企业组织中管理受监督的用户, 您可能需要监视跨大型组的所有用户。</span><span class="sxs-lookup"><span data-stu-id="a64d7-145">To manage supervised users in large enterprise organizations, you may need to monitor all users across large groups.</span></span> <span data-ttu-id="a64d7-146">您可以使用 PowerShell 为分配的组配置全局监督策略的通讯组。</span><span class="sxs-lookup"><span data-stu-id="a64d7-146">You can use PowerShell to configure a distribution group for a global supervision policy for the assigned group.</span></span> <span data-ttu-id="a64d7-147">这使您可以使用单个策略监视数千个用户, 并在新员工加入您的组织时保持监督策略的更新。</span><span class="sxs-lookup"><span data-stu-id="a64d7-147">This enables you to monitor thousands of users with a single policy and keep the supervision policy updated as new employees join your organization.</span></span>

1. <span data-ttu-id="a64d7-148">为具有以下属性的全局监督策略创建专用[通讯组](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps): 确保此通讯组不用于其他目的或其他 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="a64d7-148">Create a dedicated [distribution group](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps) for your global supervision policy with the following properties: Make sure that this distribution group isn't used for other purposes or other Office 365 services.</span></span>

    - <span data-ttu-id="a64d7-149">**MemberDepartRestriction = 已关闭**。</span><span class="sxs-lookup"><span data-stu-id="a64d7-149">**MemberDepartRestriction = Closed**.</span></span> <span data-ttu-id="a64d7-150">确保用户无法将自己从通讯组中删除。</span><span class="sxs-lookup"><span data-stu-id="a64d7-150">Ensures that users cannot remove themselves from the distribution group.</span></span>
    - <span data-ttu-id="a64d7-151">**MemberJoinRestriction = 已关闭**。</span><span class="sxs-lookup"><span data-stu-id="a64d7-151">**MemberJoinRestriction = Closed**.</span></span> <span data-ttu-id="a64d7-152">确保用户无法将自己添加到通讯组。</span><span class="sxs-lookup"><span data-stu-id="a64d7-152">Ensures that users cannot add themselves to the distribution group.</span></span>
    - <span data-ttu-id="a64d7-153">**ModerationEnabled = True**。</span><span class="sxs-lookup"><span data-stu-id="a64d7-153">**ModerationEnabled = True**.</span></span> <span data-ttu-id="a64d7-154">确保发送到此组的所有邮件均可供审批, 并且该组未用于在监督策略配置外部进行通信。</span><span class="sxs-lookup"><span data-stu-id="a64d7-154">Ensures that all messages sent to this group are subject to approval and that the group is not being used to communicate outside of the supervision policy configuration.</span></span>

    ```
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```
2. <span data-ttu-id="a64d7-155">选择一个未使用的[Exchange 自定义属性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww)来跟踪添加到组织中的监督策略的用户。</span><span class="sxs-lookup"><span data-stu-id="a64d7-155">Select an unused [Exchange custom attribute](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww) to track users added to the supervision policy in your organization.</span></span>

3. <span data-ttu-id="a64d7-156">定期对计划运行以下 PowerShell 脚本, 以将用户添加到监督策略:</span><span class="sxs-lookup"><span data-stu-id="a64d7-156">Run the following PowerShell script on a recurring schedule to add users to the supervision policy:</span></span>

    ```
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

<span data-ttu-id="a64d7-157">有关设置组的详细信息, 请参阅:</span><span class="sxs-lookup"><span data-stu-id="a64d7-157">For more information about setting up groups, see:</span></span>
- [<span data-ttu-id="a64d7-158">创建和管理通讯组</span><span class="sxs-lookup"><span data-stu-id="a64d7-158">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="a64d7-159">管理启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="a64d7-159">Manage mail-enabled security groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [<span data-ttu-id="a64d7-160">Office 365 组概述</span><span class="sxs-lookup"><span data-stu-id="a64d7-160">Overview of Office 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2---make-supervision-available-in-your-organization-required"></a><span data-ttu-id="a64d7-161">第2步-使监督在你的组织可用 (必需)</span><span class="sxs-lookup"><span data-stu-id="a64d7-161">Step 2 - Make supervision available in your organization (required)</span></span>

<span data-ttu-id="a64d7-162">若要使**监督**成为合规中心中的菜单选项, 您必须分配有监管审核管理员角色。</span><span class="sxs-lookup"><span data-stu-id="a64d7-162">To make **Supervision** available as a menu option in the Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="a64d7-163">若要执行此操作, 您可以将自己添加为监管审核角色组的成员, 也可以创建角色组。</span><span class="sxs-lookup"><span data-stu-id="a64d7-163">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="a64d7-164">将成员添加到监管审核角色组</span><span class="sxs-lookup"><span data-stu-id="a64d7-164">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="a64d7-165">在 Office [https://protection.office.com](https://protection.office.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="a64d7-165">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="a64d7-166">在 "合规性中心" 中, 转到 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="a64d7-166">In the Compliance Center, go to **Permissions**.</span></span>

3. <span data-ttu-id="a64d7-167">选择 "**监管审核**" 角色组, 然后单击 "编辑" 图标。</span><span class="sxs-lookup"><span data-stu-id="a64d7-167">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="a64d7-168">在 "**成员**" 部分, 添加要为组织管理监督的人员。</span><span class="sxs-lookup"><span data-stu-id="a64d7-168">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="a64d7-169">创建新的角色组</span><span class="sxs-lookup"><span data-stu-id="a64d7-169">Create a new role group</span></span>

1. <span data-ttu-id="a64d7-170">在 Office [https://protection.office.com](https://protection.office.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="a64d7-170">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="a64d7-171">在 "合规性中心" 中, 转到 "**权限**"**+**, 然后单击 "添加" ()。</span><span class="sxs-lookup"><span data-stu-id="a64d7-171">In the Compliance Center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="a64d7-172">在 "**角色**" 部分中, 单击**+**"添加" (), 然后向下滚动到 "**监察审核管理员**"。</span><span class="sxs-lookup"><span data-stu-id="a64d7-172">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**.</span></span> <span data-ttu-id="a64d7-173">将此角色添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="a64d7-173">Add this role to the role group.</span></span>

4. <span data-ttu-id="a64d7-174">在 "**成员**" 部分, 添加要为组织管理监督的人员。</span><span class="sxs-lookup"><span data-stu-id="a64d7-174">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

<span data-ttu-id="a64d7-175">有关角色组和权限的详细信息, 请参阅[合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="a64d7-175">For more information about role groups and permissions, see [Permissions in the Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="a64d7-176">为审阅者启用远程 PowerShell 访问 (如果 Exchange Online 上托管电子邮件)</span><span class="sxs-lookup"><span data-stu-id="a64d7-176">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="a64d7-177">按照[启用或禁用对 Exchange Online PowerShell 的访问](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)中的指导进行操作。</span><span class="sxs-lookup"><span data-stu-id="a64d7-177">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

## <a name="step-3---create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a><span data-ttu-id="a64d7-178">步骤 3-创建自定义敏感信息类型和自定义关键字词典 (可选)</span><span class="sxs-lookup"><span data-stu-id="a64d7-178">Step 3 - Create custom sensitive information types and custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="a64d7-179">若要从监督策略向导中的现有自定义敏感信息类型或自定义关键字词典中进行选择, 需要先创建这些项目。</span><span class="sxs-lookup"><span data-stu-id="a64d7-179">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-keyword-dictionarylexicon-optional"></a><span data-ttu-id="a64d7-180">创建自定义关键字词典/词典 (可选)</span><span class="sxs-lookup"><span data-stu-id="a64d7-180">Create custom keyword dictionary/lexicon (optional)</span></span>

<span data-ttu-id="a64d7-181">使用文本编辑器 (如记事本) 创建一个新文件, 其中包含要在监督策略中监视的关键字术语。</span><span class="sxs-lookup"><span data-stu-id="a64d7-181">Use a text editor (like Notepad), to create a new file that includes the keyword terms you'd like to monitor in a supervision policy.</span></span> <span data-ttu-id="a64d7-182">确保每个术语都位于单独的行中, 并将文件保存为**Unicode/UTF-16 (小 Endian)** 格式。</span><span class="sxs-lookup"><span data-stu-id="a64d7-182">Make sure that each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="a64d7-183">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a64d7-183">Create custom sensitive information types</span></span>

1. <span data-ttu-id="a64d7-184">创建新的敏感信息类型, 并将您的自定义词典添加到 Office 365 Security & 合规中心。</span><span class="sxs-lookup"><span data-stu-id="a64d7-184">Create a new sensitive information type and add your custom dictionary in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="a64d7-185">导航到 "**分类** \> " "**敏感信息**类型", 然后按照新的 "**敏感信息类型" 向导**中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="a64d7-185">Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**.</span></span> <span data-ttu-id="a64d7-186">你将在此处执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="a64d7-186">Here you will:</span></span>

    - <span data-ttu-id="a64d7-187">定义敏感信息类型的名称和说明</span><span class="sxs-lookup"><span data-stu-id="a64d7-187">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="a64d7-188">定义邻近度、置信度和主要模式元素</span><span class="sxs-lookup"><span data-stu-id="a64d7-188">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="a64d7-189">将自定义词典作为匹配元素的要求导入</span><span class="sxs-lookup"><span data-stu-id="a64d7-189">Import your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="a64d7-190">查看您的选择并创建敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="a64d7-190">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="a64d7-191">有关更多详细信息, 请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)和[创建关键字词典](create-a-keyword-dictionary.md)</span><span class="sxs-lookup"><span data-stu-id="a64d7-191">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md) and [Create a keyword dictionary](create-a-keyword-dictionary.md)</span></span>

    <span data-ttu-id="a64d7-192">创建自定义词典/词典之后, 可以使用[DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet 查看配置的关键字, 也可以使用[DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet 添加和删除术语。</span><span class="sxs-lookup"><span data-stu-id="a64d7-192">After the custom dictionary/lexicon is created, you can view the configured keywords with the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet.</span></span>

## <a name="step-4---set-up-a-supervision-policy-required"></a><span data-ttu-id="a64d7-193">步骤 4-设置监督策略 (必需)</span><span class="sxs-lookup"><span data-stu-id="a64d7-193">Step 4 - Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="a64d7-194">在 Office [https://protection.office.com](https://protection.office.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="a64d7-194">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="a64d7-195">在 "合规性中心" 中, 选择 "**监督**"。</span><span class="sxs-lookup"><span data-stu-id="a64d7-195">In the Compliance Center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="a64d7-196">选择 "**创建**", 然后按照向导设置此策略的以下页面。</span><span class="sxs-lookup"><span data-stu-id="a64d7-196">Select **Create** and then follow the wizard to set up the following pages of the policy.</span></span> <span data-ttu-id="a64d7-197">使用该向导, 您将:</span><span class="sxs-lookup"><span data-stu-id="a64d7-197">Using the wizard, you will:</span></span>

    - <span data-ttu-id="a64d7-198">为策略指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="a64d7-198">Give the policy a name and description.</span></span>
    - <span data-ttu-id="a64d7-199">选择要监督的用户或组, 包括选择要排除的用户或组。</span><span class="sxs-lookup"><span data-stu-id="a64d7-199">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="a64d7-200">定义监督策略条件。</span><span class="sxs-lookup"><span data-stu-id="a64d7-200">Define the supervision policy conditions.</span></span>
    - <span data-ttu-id="a64d7-201">选择是否要包含敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="a64d7-201">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="a64d7-202">你可以在此处选择默认和自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="a64d7-202">This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="a64d7-203">定义要查看的通信百分比。</span><span class="sxs-lookup"><span data-stu-id="a64d7-203">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="a64d7-204">选择策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="a64d7-204">Choose the reviewers for the policy.</span></span> <span data-ttu-id="a64d7-205">审阅者可以是单个用户, 也可以是[启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。</span><span class="sxs-lookup"><span data-stu-id="a64d7-205">Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span> <span data-ttu-id="a64d7-206">所有审阅者都必须在 Exchange Online 上托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="a64d7-206">All reviewers must have mailboxes hosted on Exchange Online.</span></span>
    - <span data-ttu-id="a64d7-207">查看策略选择并创建策略。</span><span class="sxs-lookup"><span data-stu-id="a64d7-207">Review your policy selections and create the policy.</span></span>

## <a name="step-5---test-your-supervision-policy-optional"></a><span data-ttu-id="a64d7-208">第5步-测试监察策略 (可选)</span><span class="sxs-lookup"><span data-stu-id="a64d7-208">Step 5 - Test your supervision policy (optional)</span></span>

<span data-ttu-id="a64d7-209">创建监督策略后, 最好进行测试以确保策略正确地强制实施了您定义的条件。</span><span class="sxs-lookup"><span data-stu-id="a64d7-209">After you create a supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="a64d7-210">如果监督策略中包含敏感信息类型, 您可能还需要[测试数据丢失防护 (DLP) 策略](create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="a64d7-210">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types.</span></span> <span data-ttu-id="a64d7-211">按照以下步骤测试您的监督策略:</span><span class="sxs-lookup"><span data-stu-id="a64d7-211">Follow these steps to test your supervision policy:</span></span>

1. <span data-ttu-id="a64d7-212">打开以您要测试的策略中定义的监督用户身份登录的电子邮件客户端或 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="a64d7-212">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="a64d7-213">发送符合您在监督策略中定义的条件的电子邮件或 Microsoft 团队聊天。</span><span class="sxs-lookup"><span data-stu-id="a64d7-213">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy.</span></span> <span data-ttu-id="a64d7-214">它可以是关键字、附件大小、域等。请确保您确定策略中配置的条件设置过于严格或太 lenient。</span><span class="sxs-lookup"><span data-stu-id="a64d7-214">This can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!Note]
    > <span data-ttu-id="a64d7-215">已定义策略的电子邮件将在接近实时的情况中进行处理, 并且可以在配置策略后立即进行测试。</span><span class="sxs-lookup"><span data-stu-id="a64d7-215">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured.</span></span> <span data-ttu-id="a64d7-216">Microsoft 团队中的聊天可能需要长达24小时才能在策略中完全处理。</span><span class="sxs-lookup"><span data-stu-id="a64d7-216">Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="a64d7-217">以监督策略中指定的审阅者的形式登录到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="a64d7-217">Log into your Office 365 tenant as a reviewer designated in the supervision policy.</span></span> <span data-ttu-id="a64d7-218">导航到 "**监控** > "*您的自定义策略* > **打开**以查看该策略的报告。</span><span class="sxs-lookup"><span data-stu-id="a64d7-218">Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

## <a name="step-6---configure-outlook-for-reviewers-optional"></a><span data-ttu-id="a64d7-219">步骤 6-配置 Outlook for 审阅者 (可选)</span><span class="sxs-lookup"><span data-stu-id="a64d7-219">Step 6 - Configure Outlook for reviewers (optional)</span></span>

<span data-ttu-id="a64d7-220">要使用 outlook 而不是 Office 365 中的监督仪表板检查通信的审阅者必须配置其 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="a64d7-220">Reviewers that want to use Outlook instead of the Supervision dashboard in Office 365 to review communications must configure their Outlook client.</span></span>

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a><span data-ttu-id="a64d7-221">步骤 1: 复制监督邮箱的地址</span><span class="sxs-lookup"><span data-stu-id="a64d7-221">Step 1: Copy the address for the supervision mailbox</span></span>

<span data-ttu-id="a64d7-222">若要为 outlook 桌面或 outlook for web 配置审阅, 您需要作为监督策略安装程序的一部分创建的监督邮箱的地址。</span><span class="sxs-lookup"><span data-stu-id="a64d7-222">To configure review for Outlook desktop or Outlook for the web, you need the address for the supervision mailbox created as part of the supervision policy setup.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a64d7-223">如果其他人创建了该策略, 则需要从这些地址获取此地址以安装加载项。</span><span class="sxs-lookup"><span data-stu-id="a64d7-223">If someone else created the policy, you need to get this address from them to install the add-in.</span></span>

 <span data-ttu-id="a64d7-224">**查找监督邮箱地址**</span><span class="sxs-lookup"><span data-stu-id="a64d7-224">**To find the supervision mailbox address**</span></span>
  
1. <span data-ttu-id="a64d7-225">使用组织中的管理员帐户的凭据登录[合规性中心](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="a64d7-225">Sign into the [Compliance Center](https://compliance.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="a64d7-226">转到 "**监督**"。</span><span class="sxs-lookup"><span data-stu-id="a64d7-226">Go to **Supervision**.</span></span>

3. <span data-ttu-id="a64d7-227">为要查看的通信选择监督策略。</span><span class="sxs-lookup"><span data-stu-id="a64d7-227">Select a supervision policy for the communications you want to review.</span></span>

4. <span data-ttu-id="a64d7-228">在 "策略详细信息" 浮出控件的 "**监督邮箱**" 下, 复制地址。</span><span class="sxs-lookup"><span data-stu-id="a64d7-228">In the policy details flyout, under **Supervision mailbox**, copy the address.</span></span><br/><span data-ttu-id="a64d7-229">![监督策略的详细信息浮出控件的 "监督邮箱" 部分, 显示监督邮箱地址突出显示](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span><span class="sxs-lookup"><span data-stu-id="a64d7-229">![The 'Supervision Mailbox' section of a supervision policy's details flyout showing the supervision mailbox address highlighted](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span></span>
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-access"></a><span data-ttu-id="a64d7-230">步骤 2: 为 Outlook access 配置监督邮箱</span><span class="sxs-lookup"><span data-stu-id="a64d7-230">Step 2: Configure the supervision mailbox for Outlook access</span></span>

<span data-ttu-id="a64d7-231">接下来, 审阅者需要运行几个 Exchange Online PowerShell 命令, 以便他们可以将 Outlook 连接到监督邮箱。</span><span class="sxs-lookup"><span data-stu-id="a64d7-231">Next, reviewers need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.</span></span>
  
1. <span data-ttu-id="a64d7-232">连接到 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="a64d7-232">Connect to Exchange Online PowerShell.</span></span> [<span data-ttu-id="a64d7-233">我该如何做？</span><span class="sxs-lookup"><span data-stu-id="a64d7-233">How do I do this?</span></span>](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)

2. <span data-ttu-id="a64d7-234">运行以下命令, 其中*SupervisoryReview {GUID}* 是您在上面的步骤1中复制的地址,*用户*是将在步骤3中连接到监督邮箱的审阅者的姓名。</span><span class="sxs-lookup"><span data-stu-id="a64d7-234">Run the following commands, where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will connect to the supervision mailbox in Step 3.</span></span>

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. <span data-ttu-id="a64d7-235">请等待至少一小时, 然后再继续执行步骤3。</span><span class="sxs-lookup"><span data-stu-id="a64d7-235">Wait at least an hour before moving on to Step 3.</span></span>

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a><span data-ttu-id="a64d7-236">步骤 3: 创建 Outlook 配置文件以连接到监督邮箱</span><span class="sxs-lookup"><span data-stu-id="a64d7-236">Step 3: Create an Outlook profile to connect to the supervision mailbox</span></span>

<span data-ttu-id="a64d7-237">在最后一步中, 审阅者需要创建 Outlook 配置文件以连接到监督邮箱。</span><span class="sxs-lookup"><span data-stu-id="a64d7-237">For the final step, reviewers need to create an Outlook profile to connect to the supervision mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="a64d7-238">若要创建新的 Outlook 配置文件, 请使用 Windows 控制面板中的 "邮件" 设置。</span><span class="sxs-lookup"><span data-stu-id="a64d7-238">To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel.</span></span> <span data-ttu-id="a64d7-239">获取这些设置所需的路径可能取决于所使用的 windows 操作系统 (windows 7、windows 8 或 windows 10) 以及安装了哪个版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="a64d7-239">The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using, and which version of Outlook is installed.</span></span>
  
1. <span data-ttu-id="a64d7-240">打开 "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="a64d7-240">Open the Control Panel.</span></span> <span data-ttu-id="a64d7-241">在窗口顶部的**搜索**框中, 键入**Mail**。</span><span class="sxs-lookup"><span data-stu-id="a64d7-241">In the **Search** box at the top of the window, type **Mail**.</span></span><br/><span data-ttu-id="a64d7-242">(不确定如何访问控制面板？</span><span class="sxs-lookup"><span data-stu-id="a64d7-242">(Not sure how to get to the Control Panel?</span></span> <span data-ttu-id="a64d7-243">请参阅[控制面板在什么位置？](https://support.microsoft.com/help/13764/windows-where-is-control-panel)</span><span class="sxs-lookup"><span data-stu-id="a64d7-243">See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span></span>
  
2. <span data-ttu-id="a64d7-244">打开**邮件**应用程序。</span><span class="sxs-lookup"><span data-stu-id="a64d7-244">Open the **Mail** app.</span></span>

3. <span data-ttu-id="a64d7-245">在**邮件安装程序-Outlook**中, 单击 "**显示配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="a64d7-245">In **Mail Setup - Outlook**, click **Show Profiles**.</span></span><br/><span data-ttu-id="a64d7-246">![突出显示 "显示配置文件" 按钮的 "邮件设置-Outlook" 对话框](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span><span class="sxs-lookup"><span data-stu-id="a64d7-246">![The 'Mail Setup - Outlook' dialog box with the 'Show Profiles' button highlighted](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span></span>
  
4. <span data-ttu-id="a64d7-247">在 "**邮件**" 中, 单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="a64d7-247">In **Mail**, click **Add**.</span></span> <span data-ttu-id="a64d7-248">然后, 在 "**新建配置文件**" 中, 输入监督邮箱的名称 (如**监督**)。</span><span class="sxs-lookup"><span data-stu-id="a64d7-248">Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).</span></span><br/><span data-ttu-id="a64d7-249">!["新建配置文件" 对话框显示 "配置文件名称" 框中的 "监督" 名称](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span><span class="sxs-lookup"><span data-stu-id="a64d7-249">![The 'New Profile' dialog showing the name 'Supervision' in the 'Profile Name' box](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span></span>
  
5. <span data-ttu-id="a64d7-250">在 "**将 Outlook 连接到 Office 365**" 中, 单击 "**连接到其他帐户**"。</span><span class="sxs-lookup"><span data-stu-id="a64d7-250">In **Connect Outlook to Office 365**, click **Connect to a different account**.</span></span><br/><span data-ttu-id="a64d7-251">![突出显示了 "连接到不同帐户的 Office 365" 链接的 "将 Outlook 连接到 Office" 的消息](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span><span class="sxs-lookup"><span data-stu-id="a64d7-251">![The 'Connect Outlook to Office 365' message with the 'Connect to a different account' link highlighted](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span></span>
  
6. <span data-ttu-id="a64d7-252">在 "**自动帐户设置**" 中, 选择 "**手动安装或其他服务器类型**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="a64d7-252">In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.</span></span>

7. <span data-ttu-id="a64d7-253">在 "**选择帐户类型**" 中, 选择 " **Office 365**"。</span><span class="sxs-lookup"><span data-stu-id="a64d7-253">In **Choose Your Account Type**, choose **Office 365**.</span></span> <span data-ttu-id="a64d7-254">然后, 在 "**电子邮件地址**" 框中, 输入您之前复制的监督邮箱的地址。</span><span class="sxs-lookup"><span data-stu-id="a64d7-254">Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously.</span></span><br/><span data-ttu-id="a64d7-255">![Outlook 中显示 "电子邮件地址" 框的 "选择帐户类型" 页面中的 "添加帐户" 对话框中突出显示了 "电子邮件地址" 框。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span><span class="sxs-lookup"><span data-stu-id="a64d7-255">![The 'Choose Your Account Type' page of the 'Add Account' dialog in Outlook showing the 'Email Address' box highlighted.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span></span>
  
8. <span data-ttu-id="a64d7-256">出现提示时, 请输入 Office 365 凭据。</span><span class="sxs-lookup"><span data-stu-id="a64d7-256">When prompted, enter your Office 365 credentials.</span></span>

9. <span data-ttu-id="a64d7-257">如果成功, 你将看到 "\*\*监督- \<策略名称\> \*\* " 文件夹列在 Outlook 中的文件夹列表视图中。</span><span class="sxs-lookup"><span data-stu-id="a64d7-257">If successful, you'll see the **Supervision — \<policy name\>** folder listed in the Folder List view in Outlook.</span></span>

## <a name="powershell-reference"></a><span data-ttu-id="a64d7-258">PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="a64d7-258">PowerShell reference</span></span>

<span data-ttu-id="a64d7-259">如果需要, 可以使用以下 PowerShell cmdlet 创建和管理监督策略:</span><span class="sxs-lookup"><span data-stu-id="a64d7-259">If needed, you can create and manage supervision policies with the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="a64d7-260">新 SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="a64d7-260">New-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="a64d7-261">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="a64d7-261">Get-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="a64d7-262">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="a64d7-262">Set-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="a64d7-263">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="a64d7-263">Remove-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="a64d7-264">新 SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="a64d7-264">New-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="a64d7-265">SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="a64d7-265">Set-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="a64d7-266">SupervisoryReviewActivity</span><span class="sxs-lookup"><span data-stu-id="a64d7-266">Get-SupervisoryReviewActivity</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [<span data-ttu-id="a64d7-267">SupervisoryReviewOverallProgressReport</span><span class="sxs-lookup"><span data-stu-id="a64d7-267">Get-SupervisoryReviewOverallProgressReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [<span data-ttu-id="a64d7-268">SupervisoryReviewTopCasesReport</span><span class="sxs-lookup"><span data-stu-id="a64d7-268">Get-SupervisoryReviewTopCasesReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)