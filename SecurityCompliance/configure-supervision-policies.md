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
ms.openlocfilehash: bb84520fed1eb5015d46c2c35931f786d29855e7
ms.sourcegitcommit: 13c601ea11ce6a3c71036fdafda059061c6998d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2019
ms.locfileid: "30313168"
---
# <a name="configure-supervision-policies-for-your-organization"></a><span data-ttu-id="2c878-103">配置组织的监督策略</span><span class="sxs-lookup"><span data-stu-id="2c878-103">Configure supervision policies for your organization</span></span>

<span data-ttu-id="2c878-p101">使用监督策略来捕获由内部或外部审阅者进行检查的员工通信。有关监察策略如何帮助您监视组织中的通信的详细信息, 请参阅[Office 365 中的监察策略](supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="2c878-p101">Use supervision policies to capture employee communications for examination by internal or external reviewers. For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="2c878-p102">监督策略监视的用户必须具有 office 365 企业版 E3 许可证和高级合规性加载项, 或者包含在 office 365 企业版 E5 订阅中。如果你没有现有的企业版 E5 计划, 并且想要尝试监督, 则可以[注册 Office 365 企业版 e5 的试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="2c878-p102">Users monitored by supervision policies must have either an Office 365 Enterprise E3 license with the Advanced Compliance add-on or be included in an Office 365 Enterprise E5 subscription. If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="2c878-108">按照以下步骤在 Office 365 组织中设置和使用监督:</span><span class="sxs-lookup"><span data-stu-id="2c878-108">Follow these steps to set up and use supervision in your Office 365 organization:</span></span>
  
- <span data-ttu-id="2c878-109">**步骤 1 (可选)** - [为监督设置组](configure-supervision-policies.md#exampledist)</span><span class="sxs-lookup"><span data-stu-id="2c878-109">**Step 1 (optional)** - [Set up groups for Supervision](configure-supervision-policies.md#exampledist)</span></span>

    <span data-ttu-id="2c878-p103">在开始使用监督之前, 请先确定谁将查看其通信, 以及谁将执行这些审阅。如果您只想开始几个用户来了解监督工作的工作方式, 则可以跳过 "立即" 设置组。</span><span class="sxs-lookup"><span data-stu-id="2c878-p103">Before you start using supervision, determine who will have their communications reviewed and who will perform those reviews. If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="2c878-112">**步骤 2 (必需)** - [使监督在您的组织中可用](configure-supervision-policies.md#MakeAvailable)</span><span class="sxs-lookup"><span data-stu-id="2c878-112">**Step 2 (required)** - [Make supervision available in your organization](configure-supervision-policies.md#MakeAvailable)</span></span>

    <span data-ttu-id="2c878-p104">将自己添加到监管审核角色组, 以便您可以设置策略。分配此角色的任何人都可以访问 Security & 合规中心内的**数据管理**下的**监督**页面。如果要审阅的电子邮件托管在 Exchange online 中, 则每个审阅者还必须具有[对 exchange online 的远程 PowerShell 访问权限](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2c878-p104">Add yourself to the Supervisory Review role group so you can set up policies. Anyone who has this role assigned can access the **Supervision** page under **Data Governance** in the Security & Compliance Center. If email to be reviewed is hosted on Exchange Online, each reviewer must also have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="2c878-116">**步骤 3 (可选)** - [配置自定义敏感信息类型或自定义关键字词典/词典](configure-supervision-policies.md#sensitiveinfo)</span><span class="sxs-lookup"><span data-stu-id="2c878-116">**Step 3 (optional)** - [Configure custom sensitive information types or custom keyword dictionaries/lexicons](configure-supervision-policies.md#sensitiveinfo)</span></span>

    <span data-ttu-id="2c878-117">如果需要对监督策略使用自定义敏感信息类型或自定义关键字词典, 则需要在启动监督向导之前创建它。</span><span class="sxs-lookup"><span data-stu-id="2c878-117">If you need to use a custom sensitive info type or a custom keyword dictionary for your supervision policy, you'll need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="2c878-118">**步骤 4 (必需)** - [设置监督策略](configure-supervision-policies.md#setupsuper)</span><span class="sxs-lookup"><span data-stu-id="2c878-118">**Step 4 (required)** - [Set up a supervision policy](configure-supervision-policies.md#setupsuper)</span></span>

    <span data-ttu-id="2c878-p105">你将在安全 & 合规中心中创建监督策略。这些策略定义哪些通信将在组织中进行审核, 并指定应执行审阅的用户。通信包括电子邮件和 Microsoft 团队通信, 以及第三方平台通信 (如 Facebook、Twitter 等)</span><span class="sxs-lookup"><span data-stu-id="2c878-p105">You'll create supervision policies in the Security & Compliance Center. These policies define which communications are subject to review in your organization and specifies who should perform reviews. Communications include email and Microsoft Teams communications, as well as 3rd-party platform communications (such as Facebook, Twitter, etc.)</span></span>

- <span data-ttu-id="2c878-122">**第5步-(可选)**[测试新的监督策略](configure-supervision-policies.md#TestPolicy)</span><span class="sxs-lookup"><span data-stu-id="2c878-122">**Step 5 - (optional)** [Test your new supervision policy](configure-supervision-policies.md#TestPolicy)</span></span>

    <span data-ttu-id="2c878-123">测试您的监督策略以确保其正常运行是确保合规性策略满足您的标准所需的重要部分。</span><span class="sxs-lookup"><span data-stu-id="2c878-123">Testing your supervision policy to make sure it is functioning as desired is an important part of ensuring that your compliance strategy is meeting your standards.</span></span>

- <span data-ttu-id="2c878-124">**步骤 6-(可选)**[为不希望使用 Office 365 监督仪表板或 web 上的 outlook (以前称为 Outlook web App) 的审阅者配置 Outlook 以查看受监督的通信](configure-supervision-policies.md#UseOutlook)</span><span class="sxs-lookup"><span data-stu-id="2c878-124">**Step 6 - (optional)** [Configure Outlook for reviewers who do not want to use Office 365 supervision dashboard or Outlook on the web (formerly known as Outlook Web App) to review supervised communications](configure-supervision-policies.md#UseOutlook)</span></span>

    <span data-ttu-id="2c878-125">outlook 可以配置为使审阅者能够访问 Outlook 客户端中的监督功能, 以便他们能够评估和分类每个项目。</span><span class="sxs-lookup"><span data-stu-id="2c878-125">Outlook can be configured to give reviewers access to the supervision functionality within the Outlook client so they can assess and categorize each item.</span></span>

<span data-ttu-id="2c878-126"><a name="exampledist"> </a></span><span class="sxs-lookup"><span data-stu-id="2c878-126"></span></span>

## <a name="step-1---set-up-groups-for-supervision-optional"></a><span data-ttu-id="2c878-127">步骤 1-设置监控组 (可选)</span><span class="sxs-lookup"><span data-stu-id="2c878-127">Step 1 - Set up groups for Supervision (optional)</span></span>

 <span data-ttu-id="2c878-p106">当您创建监督策略时, 您将确定谁将查看其通信, 以及谁将执行这些审阅。在策略中, 您将使用电子邮件地址来标识个人或用户组。若要简化设置, 请为将查看其通信的用户创建组, 并为将查看这些通信的用户分组。如果使用的是组, 则可能需要多个 (例如, 如果要监视两个不同的人员组之间的通信, 或者如果要指定不受监督的组)。有关其工作方式的详细信息, 请参阅[示例通讯组](configure-supervision-policies.md#GroupExample)。</span><span class="sxs-lookup"><span data-stu-id="2c878-p106">When you create a supervision policy, you'll determine who will have their communications reviewed and who will perform those reviews. In the policy, you'll use email addresses to identify individuals or groups of people. To simplify your setup, create groups for people who will have their communication reviewed and groups for people who will review those communications. If you're using groups, you might need several—for example, if you want to monitor communications between two distinct groups of people, or if you want to specify a group that isn't going to be supervised. See [Example distribution groups](configure-supervision-policies.md#GroupExample) for details about how this works.</span></span>
  
<span data-ttu-id="2c878-p107">若要监督组织中的组之间的通信, 请在 Exchange 管理中心内设置通讯组 (转到 "**收件人** \> **组**")。有关设置通讯组的详细信息, 请参阅[管理通讯组](http://go.microsoft.com/fwlink/?LinkId=613635)</span><span class="sxs-lookup"><span data-stu-id="2c878-p107">To supervise communications between or within groups in your organization, set up distribution groups in the Exchange admin center (go to **recipients** \> **groups**). For more information about setting up distribution groups, see [Manage distribution groups](http://go.microsoft.com/fwlink/?LinkId=613635)</span></span>
  
> [!NOTE]
> <span data-ttu-id="2c878-p108">如果你愿意, 也可以将动态通讯组或安全组用于监督。若要帮助您确定这些是否更适合您的组织需求, 请参阅[管理启用邮件的安全组](http://go.microsoft.com/fwlink/?LinkId=627033)和[管理动态通讯组](http://go.microsoft.com/fwlink/?LinkId=627058)。</span><span class="sxs-lookup"><span data-stu-id="2c878-p108">You can also use dynamic distribution groups or security groups for supervision if you prefer. To help you decide if these better fit your organization needs, see [Manage mail-enabled security groups](http://go.microsoft.com/fwlink/?LinkId=627033), and [Manage dynamic distribution groups](http://go.microsoft.com/fwlink/?LinkId=627058).</span></span>
  
<span data-ttu-id="2c878-137"><a name="GroupExample"> </a></span><span class="sxs-lookup"><span data-stu-id="2c878-137"></span></span>

### <a name="example-distribution-groups"></a><span data-ttu-id="2c878-138">示例通讯组</span><span class="sxs-lookup"><span data-stu-id="2c878-138">Example distribution groups</span></span>

<span data-ttu-id="2c878-139">此示例包含已为名为 Contoso 金融国际的财务组织设置的通讯组。</span><span class="sxs-lookup"><span data-stu-id="2c878-139">This example includes a distribution group that has been set up for a financial organization called Contoso Financial International.</span></span>
  
<span data-ttu-id="2c878-p109">在 Contoso Financial International 中，必须监督美国经纪人之间的通信抽样。但是，无需监督该组中的合规部主管。对于本例，我们可以创建以下组：</span><span class="sxs-lookup"><span data-stu-id="2c878-p109">In Contoso Financial International, a sampling of communications between brokers in the United States must be supervised. However, compliance officers within that group do not require supervision. For this example, we can create the following groups:</span></span>
  
|<span data-ttu-id="2c878-143">**设置此通讯组**</span><span class="sxs-lookup"><span data-stu-id="2c878-143">**Set up this distribution group**</span></span>|<span data-ttu-id="2c878-144">**组地址（别名）**</span><span class="sxs-lookup"><span data-stu-id="2c878-144">**Group address (alias)**</span></span>|<span data-ttu-id="2c878-145">**说明**</span><span class="sxs-lookup"><span data-stu-id="2c878-145">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2c878-146">所有美国经纪人</span><span class="sxs-lookup"><span data-stu-id="2c878-146">All US brokers</span></span> | <span data-ttu-id="2c878-147">US_Brokers@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c878-147">US_Brokers@Contoso.com</span></span> | <span data-ttu-id="2c878-148">此组包括为 Contoso 工作的所有在美国的经纪人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="2c878-148">This group includes email addresses for all US-based brokers who work for Contoso.</span></span> |
| <span data-ttu-id="2c878-149">所有美国合规部主管</span><span class="sxs-lookup"><span data-stu-id="2c878-149">All US compliance officers</span></span> | <span data-ttu-id="2c878-150">US_Compliance@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="2c878-150">US_Compliance@Contoso.com</span></span>  | <span data-ttu-id="2c878-p110">此组包含适用于 Contoso 的所有基于美国的合规性监察官的电子邮件地址。由于此组是所有基于美国的代理的子集, 因此您可以使用此别名将合规性监察官从监督策略中排除。</span><span class="sxs-lookup"><span data-stu-id="2c878-p110">This group includes email addresses for all US-based compliance officers who work for Contoso. Because this group is a subset of all US-based brokers, you can use this alias to exempt compliance officers from a supervision policy.</span></span> |
  
<span data-ttu-id="2c878-153"><a name="MakeAvailable"> </a></span><span class="sxs-lookup"><span data-stu-id="2c878-153"></span></span>

## <a name="step-2---make-supervision-available-in-your-organization-required"></a><span data-ttu-id="2c878-154">第2步-使监督在你的组织可用 (必需)</span><span class="sxs-lookup"><span data-stu-id="2c878-154">Step 2 - Make supervision available in your organization (required)</span></span>

<span data-ttu-id="2c878-155">若要在安全 & 合规中心中将**监察**功能作为菜单选项提供, 您必须分配有监管审核管理员角色。</span><span class="sxs-lookup"><span data-stu-id="2c878-155">To make **Supervision** available as a menu option in the Security & Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="2c878-156">若要执行此操作, 您可以将自己添加为监管审核角色组的成员, 也可以创建新的角色组。</span><span class="sxs-lookup"><span data-stu-id="2c878-156">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a new role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="2c878-157">将成员添加到监管审核角色组</span><span class="sxs-lookup"><span data-stu-id="2c878-157">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="2c878-158">在 Office [https://protection.office.com](https://protection.office.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="2c878-158">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="2c878-159">在 "安全 & 合规性中心" 中, 转到 "**权限**"。</span><span class="sxs-lookup"><span data-stu-id="2c878-159">In the Security & Compliance Center, go to **Permissions**.</span></span>

3. <span data-ttu-id="2c878-160">选择 "**监管审核**" 角色组, 然后单击 "编辑" 图标。</span><span class="sxs-lookup"><span data-stu-id="2c878-160">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="2c878-161">在 "**成员**" 部分, 添加要为组织管理监督的人员。</span><span class="sxs-lookup"><span data-stu-id="2c878-161">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="2c878-162">创建新的角色组</span><span class="sxs-lookup"><span data-stu-id="2c878-162">Create a new role group</span></span>

1. <span data-ttu-id="2c878-163">在 Office [https://protection.office.com](https://protection.office.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="2c878-163">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="2c878-164">在 "安全 & 合规性中心" 中, 转到 "**权限**"**+**, 然后单击 "添加" ()。</span><span class="sxs-lookup"><span data-stu-id="2c878-164">In the Security & Compliance Center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="2c878-p111">在 "**角色**" 部分中, 单击**+**"添加" (), 然后向下滚动到 "**监察审核管理员**"。将此角色添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="2c878-p111">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**. Add this role to the role group.</span></span>

4. <span data-ttu-id="2c878-167">在 "**成员**" 部分, 添加要为组织管理监督的人员。</span><span class="sxs-lookup"><span data-stu-id="2c878-167">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

<span data-ttu-id="2c878-168">有关角色组和权限的详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="2c878-168">For more information about role groups and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="2c878-169">为审阅者启用远程 PowerShell 访问 (如果 Exchange Online 上托管电子邮件)</span><span class="sxs-lookup"><span data-stu-id="2c878-169">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="2c878-170">按照[启用或禁用对 Exchange Online PowerShell 的访问](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)中的指导进行操作。</span><span class="sxs-lookup"><span data-stu-id="2c878-170">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

<span data-ttu-id="2c878-171"><a name="sensitiveinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="2c878-171"></span></span>
  
## <a name="step-3---create-custom-sensitive-information-types-or-custom-keyword-dictionaries-optional"></a><span data-ttu-id="2c878-172">步骤 3-创建自定义敏感信息类型或自定义关键字词典 (可选)</span><span class="sxs-lookup"><span data-stu-id="2c878-172">Step 3 - Create custom sensitive information types or custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="2c878-173">若要从监督策略向导中的现有自定义敏感信息类型或自定义关键字词典中进行选择, 需要先创建这些项目。</span><span class="sxs-lookup"><span data-stu-id="2c878-173">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="2c878-174">创建自定义敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="2c878-174">Create custom sensitive information types</span></span>

1. <span data-ttu-id="2c878-p112">在 Office 365 Security & 合规中心中创建新的敏感信息类型。导航到 "**分类** \> " "**敏感信息**类型", 然后按照新的 "**敏感信息类型" 向导**中的步骤操作。你将在此处执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="2c878-p112">Create a new sensitive information type in the Office 365 Security & Compliance Center. Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**. Here you will:</span></span>

    - <span data-ttu-id="2c878-178">定义敏感信息类型的名称和说明</span><span class="sxs-lookup"><span data-stu-id="2c878-178">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="2c878-179">定义邻近度、置信度和主要模式元素</span><span class="sxs-lookup"><span data-stu-id="2c878-179">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="2c878-180">查看您的选择并创建敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="2c878-180">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="2c878-181">有关更多详细信息, 请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="2c878-181">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

### <a name="create-custom-keyword-dictionarylexicon"></a><span data-ttu-id="2c878-182">创建自定义关键字词典/词典</span><span class="sxs-lookup"><span data-stu-id="2c878-182">Create custom keyword dictionary/lexicon</span></span>

1. <span data-ttu-id="2c878-p113">使用文本编辑器 (如记事本), 创建一个新文件, 其中包含要在监督策略中监视的关键字术语。确保每个术语都位于单独的行中, 并将该文件保存为**Unicode/utf-16 (小 Endian)** 格式。</span><span class="sxs-lookup"><span data-stu-id="2c878-p113">Using a text editor (like Notepad), create a new file that includes the keyword terms you'd like to monitor in a supervision policy. Make sure each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>
2. <span data-ttu-id="2c878-p114">使用 PowerShell 将关键字文件导入到 Office 365 租户中。若要使用 PowerShell 连接到 office 365, 请参阅[连接到 office 365 Security & 合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="2c878-p114">Import the keyword file into your Office 365 tenant using PowerShell. To connect to Office 365 with PowerShell, see [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

    <span data-ttu-id="2c878-187">在使用 PowerShell 连接到 Office 365 之后, 请运行以下命令以导入关键字词典:</span><span class="sxs-lookup"><span data-stu-id="2c878-187">After you've connected to Office 365 with PowerShell, run the following commands to import your keyword dictionary:</span></span>

    ```
    $fileData = Get-Content "your keyword path and file name" -Encoding Byte -ReadCount 0

    New-DlpKeywordDictionary -Name "Name for your keyword dictionary" -Description "optional description for your keyword dictionary" -FileData $fileData
    ```
    <span data-ttu-id="2c878-188">有关更多详细信息, 请参阅[Create a 关键字 dictionary](create-a-keyword-dictionary.md)。</span><span class="sxs-lookup"><span data-stu-id="2c878-188">For more detailed information, see [Create a keyword dictionary](create-a-keyword-dictionary.md).</span></span>

3. <span data-ttu-id="2c878-p115">在 Office 365 Security & 合规中心中创建新的敏感信息类型。导航到 "**分类** \> " "**敏感信息**类型", 然后按照新的 "**敏感信息类型" 向导**中的步骤操作。你将在此处执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="2c878-p115">Create a new sensitive information type in the Office 365 Security & Compliance Center. Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**. Here you will:</span></span>

    - <span data-ttu-id="2c878-192">定义敏感信息类型的名称和说明</span><span class="sxs-lookup"><span data-stu-id="2c878-192">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="2c878-193">添加您的自定义词典作为匹配元素的要求</span><span class="sxs-lookup"><span data-stu-id="2c878-193">Add your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="2c878-194">查看您的选择并创建敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="2c878-194">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="2c878-195">创建自定义词典/词典之后, 可以使用[DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet 查看配置的关键字, 也可以使用[DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet 添加和删除术语。</span><span class="sxs-lookup"><span data-stu-id="2c878-195">After the custom dictionary/lexicon is created, you can view the configured keywords using the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet.</span></span>

    <span data-ttu-id="2c878-196">有关更多详细信息, 请参阅[创建自定义敏感信息类型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="2c878-196">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

<span data-ttu-id="2c878-197"><a name="setupsuper"> </a></span><span class="sxs-lookup"><span data-stu-id="2c878-197"></span></span>

## <a name="step-4---set-up-a-supervision-policy-required"></a><span data-ttu-id="2c878-198">步骤 4-设置监督策略 (必需)</span><span class="sxs-lookup"><span data-stu-id="2c878-198">Step 4 - Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="2c878-199">在 Office [https://protection.office.com](https://protection.office.com) 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="2c878-199">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="2c878-200">在 "安全 & 合规中心" 中, 选择 "**监督**"。</span><span class="sxs-lookup"><span data-stu-id="2c878-200">In the Security & Compliance Center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="2c878-p116">选择 "**创建**", 然后按照向导设置此策略的以下页面。使用该向导, 您将:</span><span class="sxs-lookup"><span data-stu-id="2c878-p116">Select **Create** and then follow the wizard to set up the following pages of the policy. Using the wizard, you will:</span></span>

    - <span data-ttu-id="2c878-203">为策略指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="2c878-203">Give the policy a name and description.</span></span>
    - <span data-ttu-id="2c878-204">选择要监督的用户或组, 包括选择要排除的用户或组。</span><span class="sxs-lookup"><span data-stu-id="2c878-204">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="2c878-205">定义监督策略条件。</span><span class="sxs-lookup"><span data-stu-id="2c878-205">Define the supervision policy conditions.</span></span>
    - <span data-ttu-id="2c878-p117">选择是否要包含敏感信息类型。你可以在此处选择默认和自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="2c878-p117">Choose if you'd like to include sensitive information types. This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="2c878-208">定义要查看的通信百分比。</span><span class="sxs-lookup"><span data-stu-id="2c878-208">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="2c878-p118">选择策略的审阅者。审阅者可以是单个用户, 也可以是[启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。</span><span class="sxs-lookup"><span data-stu-id="2c878-p118">Choose the reviewers for the policy. Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span>
    - <span data-ttu-id="2c878-211">查看策略选择并创建策略。</span><span class="sxs-lookup"><span data-stu-id="2c878-211">Review your policy selections and create the policy.</span></span>

<span data-ttu-id="2c878-212"><a name="TestPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="2c878-212"></span></span>

## <a name="step-5---test-your-supervision-policy-optional"></a><span data-ttu-id="2c878-213">第5步-测试监察策略 (可选)</span><span class="sxs-lookup"><span data-stu-id="2c878-213">Step 5 - Test your supervision policy (optional)</span></span>

<span data-ttu-id="2c878-p119">创建监督策略后, 最好进行测试以确保策略正确地强制实施了您定义的条件。如果监督策略中包含敏感信息类型, 您可能还需要[测试数据丢失防护 (DLP) 策略](create-test-tune-dlp-policy.md)。按照以下步骤测试您的监察策略:</span><span class="sxs-lookup"><span data-stu-id="2c878-p119">After you create a supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy. You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types. Follow the steps below to test your supervision policy:</span></span>

1. <span data-ttu-id="2c878-217">打开以您要测试的策略中定义的监督用户身份登录的电子邮件客户端或 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="2c878-217">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="2c878-p120">发送符合您在监督策略中定义的条件的电子邮件或 Microsoft 团队聊天。它可以是关键字、附件大小、域等。请确保您确定策略中配置的条件设置过于严格或太 lenient。</span><span class="sxs-lookup"><span data-stu-id="2c878-p120">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy. This can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy is too restrictive or too lenient.</span></span>

    > [!Note]
    > <span data-ttu-id="2c878-p121">已定义策略的电子邮件将在接近实时的情况中进行处理, 并且可以在配置策略后立即进行测试。Microsoft 团队中的聊天可能需要长达24小时才能在策略中完全处理。</span><span class="sxs-lookup"><span data-stu-id="2c878-p121">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured. Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="2c878-p122">以监督策略中指定的审阅者的形式登录到 Office 365 租户。导航到 "**监控** > "*您的自定义策略* > **打开**以查看该策略的报告。</span><span class="sxs-lookup"><span data-stu-id="2c878-p122">Log into your Office 365 tenant as a reviewer designated in the supervision policy. Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

<span data-ttu-id="2c878-224"><a name="UseOutlook"> </a></span><span class="sxs-lookup"><span data-stu-id="2c878-224"></span></span>

## <a name="step-6---configure-outlook-for-reviewers-optional"></a><span data-ttu-id="2c878-225">步骤 6-配置 Outlook for 审阅者 (可选)</span><span class="sxs-lookup"><span data-stu-id="2c878-225">Step 6 - Configure Outlook for reviewers (optional)</span></span>

<span data-ttu-id="2c878-226">要使用 Outlook 而不是使用 Office 365 中的监督仪表板检查通信的审阅者必须配置其 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="2c878-226">Reviewers that want to use Outlook instead of using the Supervision dashboard in Office 365 to review communications must configure their Outlook client.</span></span>

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a><span data-ttu-id="2c878-227">步骤 1: 复制监督邮箱的地址</span><span class="sxs-lookup"><span data-stu-id="2c878-227">Step 1: Copy the address for the supervision mailbox</span></span>

<span data-ttu-id="2c878-228">若要为 outlook 桌面或 outlook for web 配置审阅, 你将需要作为监督策略安装程序的一部分创建的监督邮箱的地址。</span><span class="sxs-lookup"><span data-stu-id="2c878-228">To configure review for Outlook desktop or Outlook for the web, you'll need the address for the supervision mailbox that was created as part of the supervision policy setup.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2c878-229">如果其他人创建了该策略, 则需要从这些地址获取该地址以安装加载项。</span><span class="sxs-lookup"><span data-stu-id="2c878-229">If someone else created the policy, you'll need to get this address from them to install the add-in.</span></span>

 <span data-ttu-id="2c878-230">**查找监督邮箱地址**</span><span class="sxs-lookup"><span data-stu-id="2c878-230">**To find the supervision mailbox address**</span></span>
  
1. <span data-ttu-id="2c878-231">使用 Office 365 组织中的管理员帐户的凭据登录到[ &amp;安全合规中心](https://protection.office.com)。</span><span class="sxs-lookup"><span data-stu-id="2c878-231">Sign into the [Security &amp; Compliance Center](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="2c878-232">转到 "**监督**"。</span><span class="sxs-lookup"><span data-stu-id="2c878-232">Go to **Supervision**.</span></span>

3. <span data-ttu-id="2c878-233">单击收集您要查看的通信的监督策略。</span><span class="sxs-lookup"><span data-stu-id="2c878-233">Click the supervision policy that's gathering the communications you want to review.</span></span>

4. <span data-ttu-id="2c878-234">在 "策略详细信息" 浮出控件的 "**监督邮箱**" 下, 复制地址。</span><span class="sxs-lookup"><span data-stu-id="2c878-234">In the policy details flyout, under **Supervision mailbox**, copy the address.</span></span><br/><span data-ttu-id="2c878-235">![监督策略的详细信息浮出控件的 "监督邮箱" 部分, 显示监督邮箱地址突出显示](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span><span class="sxs-lookup"><span data-stu-id="2c878-235">![The 'Supervision Mailbox' section of a supervision policy's details flyout showing the supervision mailbox address highlighted](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span></span>
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-access"></a><span data-ttu-id="2c878-236">步骤 2: 为 Outlook access 配置监督邮箱</span><span class="sxs-lookup"><span data-stu-id="2c878-236">Step 2: Configure the supervision mailbox for Outlook access</span></span>

<span data-ttu-id="2c878-237">接下来, 审阅者将需要运行几个 Exchange Online PowerShell 命令, 以便他们可以将 Outlook 连接到监督邮箱。</span><span class="sxs-lookup"><span data-stu-id="2c878-237">Next, reviewers will need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.</span></span>
  
1. <span data-ttu-id="2c878-p123">连接到 Exchange Online PowerShell。[如何执行此操作？](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="2c878-p123">Connect to Exchange Online PowerShell. [How do I do this?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span></span>

2. <span data-ttu-id="2c878-240">运行以下命令, 其中*SupervisoryReview {GUID}* 是您在上面的步骤1中复制的地址,*用户*是将在步骤3中连接到监管邮箱的审阅者的姓名。</span><span class="sxs-lookup"><span data-stu-id="2c878-240">Run the following commands, where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will be connecting to the supervision mailbox in Step 3.</span></span>

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. <span data-ttu-id="2c878-241">请等待至少一小时, 然后再转到下面的步骤3。</span><span class="sxs-lookup"><span data-stu-id="2c878-241">Wait at least an hour before moving on to Step 3 below.</span></span>

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a><span data-ttu-id="2c878-242">步骤 3: 创建 Outlook 配置文件以连接到监督邮箱</span><span class="sxs-lookup"><span data-stu-id="2c878-242">Step 3: Create an Outlook profile to connect to the supervision mailbox</span></span>

<span data-ttu-id="2c878-243">在最后一步中, 审阅者将需要创建 Outlook 配置文件以连接到监督邮箱。</span><span class="sxs-lookup"><span data-stu-id="2c878-243">For the final step, reviewers will need to create an Outlook profile to connect to the supervision mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="2c878-p124">若要创建新的 Outlook 配置文件, 请使用 Windows 控制面板中的 "邮件" 设置。获取这些设置所需的路径可能取决于所使用的 windows 操作系统 (windows 7、windows 8 或 windows 10) 以及安装了哪个版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="2c878-p124">To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel. The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using, and which version of Outlook is installed.</span></span>
  
1. <span data-ttu-id="2c878-246">打开 "控制面板", 然后在窗口顶部的 "**搜索**" 框中, 键入**Mail**。</span><span class="sxs-lookup"><span data-stu-id="2c878-246">Open the Control Panel, and in the **Search** box at the top of the window, type **Mail**.</span></span><br/><span data-ttu-id="2c878-p125">(不确定如何访问控制面板？请参阅[控制面板在什么位置？](https://support.microsoft.com/help/13764/windows-where-is-control-panel)</span><span class="sxs-lookup"><span data-stu-id="2c878-p125">(Not sure how to get to the Control Panel? See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span></span>
  
2. <span data-ttu-id="2c878-249">打开**邮件**应用程序。</span><span class="sxs-lookup"><span data-stu-id="2c878-249">Open the **Mail** app.</span></span>

3. <span data-ttu-id="2c878-250">在**邮件安装程序-Outlook**中, 单击 "**显示配置文件**"。</span><span class="sxs-lookup"><span data-stu-id="2c878-250">In **Mail Setup - Outlook**, click **Show Profiles**.</span></span><br/><span data-ttu-id="2c878-251">![突出显示 "显示配置文件" 按钮的 "邮件设置-Outlook" 对话框](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span><span class="sxs-lookup"><span data-stu-id="2c878-251">![The 'Mail Setup - Outlook' dialog box with the 'Show Profiles' button highlighted](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span></span>
  
4. <span data-ttu-id="2c878-p126">在 "**邮件**" 中, 单击 "**添加**"。然后, 在 "**新建配置文件**" 中, 输入监督邮箱的名称 (如**监督**)。</span><span class="sxs-lookup"><span data-stu-id="2c878-p126">In **Mail**, click **Add**. Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).</span></span><br/><span data-ttu-id="2c878-254">!["新建配置文件" 对话框显示 "配置文件名称" 框中的 "监督" 名称](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span><span class="sxs-lookup"><span data-stu-id="2c878-254">![The 'New Profile' dialog showing the name 'Supervision' in the 'Profile Name' box](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span></span>
  
5. <span data-ttu-id="2c878-255">在 "**将 Outlook 连接到 Office 365**" 中, 单击 "**连接到其他帐户**"。</span><span class="sxs-lookup"><span data-stu-id="2c878-255">In **Connect Outlook to Office 365**, click **Connect to a different account**.</span></span><br/><span data-ttu-id="2c878-256">![突出显示了 "连接到不同帐户的 Office 365" 链接的 "将 Outlook 连接到 Office" 的消息](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span><span class="sxs-lookup"><span data-stu-id="2c878-256">![The 'Connect Outlook to Office 365' message with the 'Connect to a different account' link highlighted](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span></span>
  
6. <span data-ttu-id="2c878-257">在 "**自动帐户设置**" 中, 选择 "**手动安装或其他服务器类型**", 然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="2c878-257">In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.</span></span>

7. <span data-ttu-id="2c878-p127">在 "**选择帐户类型**" 中, 选择 " **Office 365**"。然后, 在 "**电子邮件地址**" 框中, 输入您之前复制的监督邮箱的地址。</span><span class="sxs-lookup"><span data-stu-id="2c878-p127">In **Choose Your Account Type**, choose **Office 365**. Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously.</span></span><br/><span data-ttu-id="2c878-260">![Outlook 中显示 "电子邮件地址" 框的 "选择帐户类型" 页面中的 "添加帐户" 对话框中突出显示了 "电子邮件地址" 框。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span><span class="sxs-lookup"><span data-stu-id="2c878-260">![The 'Choose Your Account Type' page of the 'Add Account' dialog in Outlook showing the 'Email Address' box highlighted.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span></span>
  
8. <span data-ttu-id="2c878-261">出现提示时, 请输入 Office 365 凭据。</span><span class="sxs-lookup"><span data-stu-id="2c878-261">When prompted, enter your Office 365 credentials.</span></span>

9. <span data-ttu-id="2c878-262">如果成功, 你将看到 "\*\*监督- \<策略名称\> \*\* " 文件夹列在 Outlook 的文件夹列表视图中。</span><span class="sxs-lookup"><span data-stu-id="2c878-262">If successful, you'll see the **Supervision - \<policy name\>** folder listed in the Folder List view in Outlook.</span></span>

## <a name="powershell-reference"></a><span data-ttu-id="2c878-263">PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="2c878-263">PowerShell reference</span></span>

<span data-ttu-id="2c878-264">如果需要, 可以使用以下 PowerShell cmdlet 创建和管理监督策略:</span><span class="sxs-lookup"><span data-stu-id="2c878-264">If needed, you can create and manage supervision policies using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="2c878-265">新 SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="2c878-265">New-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="2c878-266">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="2c878-266">Get-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="2c878-267">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="2c878-267">Set-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="2c878-268">SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="2c878-268">Remove-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="2c878-269">新 SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="2c878-269">New-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="2c878-270">SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="2c878-270">Set-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="2c878-271">SupervisoryReviewActivity</span><span class="sxs-lookup"><span data-stu-id="2c878-271">Get-SupervisoryReviewActivity</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [<span data-ttu-id="2c878-272">SupervisoryReviewOverallProgressReport</span><span class="sxs-lookup"><span data-stu-id="2c878-272">Get-SupervisoryReviewOverallProgressReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [<span data-ttu-id="2c878-273">SupervisoryReviewTopCasesReport</span><span class="sxs-lookup"><span data-stu-id="2c878-273">Get-SupervisoryReviewTopCasesReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)