---
title: 配置组织的监督策略
ms.author: robmazz
author: robmazz
manager: laurawi
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: d14ae7c3-fcb0-4a03-967b-cbed861bb086
description: 设置监督审阅策略来捕获员工通信进行审阅。
ms.openlocfilehash: 898ef9951ea20dec1e0cc6c28ad1ed6f9a0ded6e
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29768033"
---
# <a name="configure-supervision-policies-for-your-organization"></a><span data-ttu-id="389d4-103">配置组织的监督策略</span><span class="sxs-lookup"><span data-stu-id="389d4-103">Configure supervision policies for your organization</span></span>

<span data-ttu-id="389d4-p101">使用监督策略来捕获员工通信的内部或外部的审阅者的检查。有关监督策略可以帮助您监控您的组织中的通信的详细信息，请参阅[Office 365 中的监督策略](supervision-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="389d4-p101">Use supervision policies to capture employee communications for examination by internal or external reviewers. For more information about how supervision policies can help you monitor communications in your organization, see [Supervision policies in Office 365](supervision-policies.md).</span></span>

> [!NOTE]
> <span data-ttu-id="389d4-p102">由监督策略监控的用户必须具有与高级合规性加载项的 Office 365 企业版 E3 许可证或包含在 Office 365 企业 E5 订阅。如果您不具有现有企业 E5 计划，并需要尝试监督，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="389d4-p102">Users monitored by supervision policies must have either an Office 365 Enterprise E3 license with the Advanced Compliance add-on or be included in an Office 365 Enterprise E5 subscription. If you don't have an existing Enterprise E5 plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span>
  
<span data-ttu-id="389d4-108">请按照下列步骤设置和 Office 365 组织中使用监督：</span><span class="sxs-lookup"><span data-stu-id="389d4-108">Follow these steps to set up and use supervision in your Office 365 organization:</span></span>
  
- <span data-ttu-id="389d4-109">**步骤 1 （可选）** - [为监督设置组](configure-supervision-policies.md#exampledist)</span><span class="sxs-lookup"><span data-stu-id="389d4-109">**Step 1 (optional)** - [Set up groups for Supervision](configure-supervision-policies.md#exampledist)</span></span>

    <span data-ttu-id="389d4-p103">开始使用监督之前，确定谁将其通信检查以及谁将执行这些 reviews （英文）。如果您想要开始使用几个用户查看监督的工作方式，则可以跳过现在设置组。</span><span class="sxs-lookup"><span data-stu-id="389d4-p103">Before you start using supervision, determine who will have their communications reviewed and who will perform those reviews. If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>

- <span data-ttu-id="389d4-112">**步骤 2 （必需）** - [使监督在组织中可用](configure-supervision-policies.md#MakeAvailable)</span><span class="sxs-lookup"><span data-stu-id="389d4-112">**Step 2 (required)** - [Make supervision available in your organization](configure-supervision-policies.md#MakeAvailable)</span></span>

    <span data-ttu-id="389d4-p104">将自己添加到监督审阅角色组以便您可以设置策略。已分配该角色的任何人都可以访问下**数据调控**中安全 & 合规中心的**监督**页。如果要审阅的电子邮件位于 Exchange Online，每个审阅者还必须[对 Exchange Online 的远程 PowerShell 访问](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="389d4-p104">Add yourself to the Supervisory Review role group so you can set up policies. Anyone who has this role assigned can access the **Supervision** page under **Data Governance** in the Security & Compliance Center. If email to be reviewed is hosted on Exchange Online, each reviewer must also have [remote PowerShell access to Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="389d4-116">**步骤 3 （可选）** - [配置自定义的敏感信息类型或自定义关键字词典/词典](configure-supervision-policies.md#sensitiveinfo)</span><span class="sxs-lookup"><span data-stu-id="389d4-116">**Step 3 (optional)** - [Configure custom sensitive information types or custom keyword dictionaries/lexicons](configure-supervision-policies.md#sensitiveinfo)</span></span>

    <span data-ttu-id="389d4-117">如果您需要监督策略中用于自定义的敏感信息类型或自定义关键字字典，您需要在启动监督向导之前创建它。</span><span class="sxs-lookup"><span data-stu-id="389d4-117">If you need to use a custom sensitive info type or a custom keyword dictionary for your supervision policy, you'll need to create it before starting the supervision wizard.</span></span>

- <span data-ttu-id="389d4-118">**步骤 4 （必需）** - [设置监督策略](configure-supervision-policies.md#setupsuper)</span><span class="sxs-lookup"><span data-stu-id="389d4-118">**Step 4 (required)** - [Set up a supervision policy](configure-supervision-policies.md#setupsuper)</span></span>

    <span data-ttu-id="389d4-p105">在安全 & 合规性中心，您将创建监督策略。这些策略定义的通信将受到您的组织中查看和指定用户应执行 reviews （英文）。Communications 包括电子邮件和 Microsoft 团队通信，以及第三方平台 communications （如 Facebook、 Twitter 等。）</span><span class="sxs-lookup"><span data-stu-id="389d4-p105">You'll create supervision policies in the Security & Compliance Center. These policies define which communications are subject to review in your organization and specifies who should perform reviews. Communications include email and Microsoft Teams communications, as well as 3rd-party platform communications (such as Facebook, Twitter, etc.)</span></span>

- <span data-ttu-id="389d4-122">**步骤 5-（可选）**[测试新监督策略](configure-supervision-policies.md#TestPolicy)</span><span class="sxs-lookup"><span data-stu-id="389d4-122">**Step 5 - (optional)** [Test your new supervision policy](configure-supervision-policies.md#TestPolicy)</span></span>

    <span data-ttu-id="389d4-123">测试您的监督策略以确保其正常根据需要是确保合规性策略会议您标准的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="389d4-123">Testing your supervision policy to make sure it is functioning as desired is an important part of ensuring that your compliance strategy is meeting your standards.</span></span>

- <span data-ttu-id="389d4-124">**步骤 6-（可选）**[Outlook 外接程序审阅人不想使用 Office 365 监督仪表板或 OWA 查看监管的通信设置](configure-supervision-policies.md#UseOutlook)</span><span class="sxs-lookup"><span data-stu-id="389d4-124">**Step 6 - (optional)** [Set up Outlook add-in for reviewers who do not want to use Office 365 supervision dashboard or OWA to review supervised communications](configure-supervision-policies.md#UseOutlook)</span></span>

    <span data-ttu-id="389d4-125">监督外接程序 Outlook 使审阅者访问监督功能右 Outlook 客户端中，以便他们可以评估并对每个项目进行分类。</span><span class="sxs-lookup"><span data-stu-id="389d4-125">The Supervision add-in for Outlook gives reviewers access to the supervision functionality right within the Outlook client so they can assess and categorize each item.</span></span>

<span data-ttu-id="389d4-126"><a name="exampledist"> </a></span><span class="sxs-lookup"><span data-stu-id="389d4-126"></span></span>

## <a name="step-1---set-up-groups-for-supervision-optional"></a><span data-ttu-id="389d4-127">步骤 1-设置组的监督 （可选）</span><span class="sxs-lookup"><span data-stu-id="389d4-127">Step 1 - Set up groups for Supervision (optional)</span></span>

 <span data-ttu-id="389d4-p106">创建监督策略时，您将决定谁将具有检查其通信以及谁将执行这些 reviews （英文）。在策略，您将使用电子邮件地址来标识个人或组的人员。若要简化您的设置，创建组会检查其通信的人员和组将查看这些通信的人员。如果您使用的组，则可能需要几个 — 例如，如果您想要监控的人员，两个不同组之间的通信，或如果您想要指定不打算管理组。有关此工作原理的详细信息，请参阅[示例通讯组](configure-supervision-policies.md#GroupExample)。</span><span class="sxs-lookup"><span data-stu-id="389d4-p106">When you create a supervision policy, you'll determine who will have their communications reviewed and who will perform those reviews. In the policy, you'll use email addresses to identify individuals or groups of people. To simplify your setup, create groups for people who will have their communication reviewed and groups for people who will review those communications. If you're using groups, you might need several—for example, if you want to monitor communications between two distinct groups of people, or if you want to specify a group that isn't going to be supervised. See [Example distribution groups](configure-supervision-policies.md#GroupExample) for details about how this works.</span></span>
  
<span data-ttu-id="389d4-p107">监督 communications 之间或在组织中的组中，请在 Exchange 管理中心中设置通讯组 (转到**收件人** \> **组**)。有关设置通讯组的详细信息，请参阅[管理通讯组](http://go.microsoft.com/fwlink/?LinkId=613635)</span><span class="sxs-lookup"><span data-stu-id="389d4-p107">To supervise communications between or within groups in your organization, set up distribution groups in the Exchange admin center (go to **recipients** \> **groups**). For more information about setting up distribution groups, see [Manage distribution groups](http://go.microsoft.com/fwlink/?LinkId=613635)</span></span>
  
> [!NOTE]
> <span data-ttu-id="389d4-p108">您可还用于动态通讯组或安全组监督如果您愿意。为了帮助您决定是否这些更好地满足组织需求，请参阅[管理已启用邮件的安全组](http://go.microsoft.com/fwlink/?LinkId=627033)和[管理动态通讯组](http://go.microsoft.com/fwlink/?LinkId=627058)。</span><span class="sxs-lookup"><span data-stu-id="389d4-p108">You can also use dynamic distribution groups or security groups for supervision if you prefer. To help you decide if these better fit your organization needs, see [Manage mail-enabled security groups](http://go.microsoft.com/fwlink/?LinkId=627033), and [Manage dynamic distribution groups](http://go.microsoft.com/fwlink/?LinkId=627058).</span></span>
  
<span data-ttu-id="389d4-137"><a name="GroupExample"> </a></span><span class="sxs-lookup"><span data-stu-id="389d4-137"></span></span>

### <a name="example-distribution-groups"></a><span data-ttu-id="389d4-138">示例通讯组</span><span class="sxs-lookup"><span data-stu-id="389d4-138">Example distribution groups</span></span>

<span data-ttu-id="389d4-139">本示例包含已设置名为 Contoso 财务国际财务组织的通讯组。</span><span class="sxs-lookup"><span data-stu-id="389d4-139">This example includes a distribution group that has been set up for a financial organization called Contoso Financial International.</span></span>
  
<span data-ttu-id="389d4-p109">在 Contoso Financial International 中，必须监督美国经纪人之间的通信抽样。但是，无需监督该组中的合规部主管。对于本例，我们可以创建以下组：</span><span class="sxs-lookup"><span data-stu-id="389d4-p109">In Contoso Financial International, a sampling of communications between brokers in the United States must be supervised. However, compliance officers within that group do not require supervision. For this example, we can create the following groups:</span></span>
  
|<span data-ttu-id="389d4-143">**设置此通讯组**</span><span class="sxs-lookup"><span data-stu-id="389d4-143">**Set up this distribution group**</span></span>|<span data-ttu-id="389d4-144">**组地址（别名）**</span><span class="sxs-lookup"><span data-stu-id="389d4-144">**Group address (alias)**</span></span>|<span data-ttu-id="389d4-145">**说明**</span><span class="sxs-lookup"><span data-stu-id="389d4-145">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="389d4-146">所有美国经纪人</span><span class="sxs-lookup"><span data-stu-id="389d4-146">All US brokers</span></span> | <span data-ttu-id="389d4-147">US_Brokers@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="389d4-147">US_Brokers@Contoso.com</span></span> | <span data-ttu-id="389d4-148">此组包括为 Contoso 工作的所有在美国的经纪人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="389d4-148">This group includes email addresses for all US-based brokers who work for Contoso.</span></span> |
| <span data-ttu-id="389d4-149">所有美国合规部主管</span><span class="sxs-lookup"><span data-stu-id="389d4-149">All US compliance officers</span></span> | <span data-ttu-id="389d4-150">US_Compliance@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="389d4-150">US_Compliance@Contoso.com</span></span>  | <span data-ttu-id="389d4-p110">此组包括所有美国合规部主管，就职 contoso 电子邮件地址。由于此组的所有美国经纪人子集，因此可以从监督策略到例外合规部主管使用此别名。</span><span class="sxs-lookup"><span data-stu-id="389d4-p110">This group includes email addresses for all US-based compliance officers who work for Contoso. Because this group is a subset of all US-based brokers, you can use this alias to exempt compliance officers from a supervision policy.</span></span> |
  
<span data-ttu-id="389d4-153"><a name="MakeAvailable"> </a></span><span class="sxs-lookup"><span data-stu-id="389d4-153"></span></span>

## <a name="step-2---make-supervision-available-in-your-organization-required"></a><span data-ttu-id="389d4-154">步骤 2-使监督 （必需） 在组织中可用</span><span class="sxs-lookup"><span data-stu-id="389d4-154">Step 2 - Make supervision available in your organization (required)</span></span>

<span data-ttu-id="389d4-155">为了使安全 & 合规性中心**监督**菜单选项，您必须为分配的监督审阅管理员角色。</span><span class="sxs-lookup"><span data-stu-id="389d4-155">To make **Supervision** available as a menu option in the Security & Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span>
  
<span data-ttu-id="389d4-156">若要执行此操作，也可以将自己添加为监督审阅角色组的成员，也可以创建新的角色组。</span><span class="sxs-lookup"><span data-stu-id="389d4-156">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a new role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="389d4-157">向主管审阅角色组添加成员</span><span class="sxs-lookup"><span data-stu-id="389d4-157">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="389d4-158">登录到[https://protection.office.com](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="389d4-158">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="389d4-159">在安全 & 合规性中心中，转到**权限**。</span><span class="sxs-lookup"><span data-stu-id="389d4-159">In the Security & Compliance Center, go to **Permissions**.</span></span>

3. <span data-ttu-id="389d4-160">选择**监督审阅**角色组，然后单击编辑图标。</span><span class="sxs-lookup"><span data-stu-id="389d4-160">Select the **Supervisory Review** role group and then click the Edit icon.</span></span>

4. <span data-ttu-id="389d4-161">在**成员**部分中，添加您要管理您的组织的监督的人员。</span><span class="sxs-lookup"><span data-stu-id="389d4-161">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

### <a name="create-a-new-role-group"></a><span data-ttu-id="389d4-162">创建新的角色组</span><span class="sxs-lookup"><span data-stu-id="389d4-162">Create a new role group</span></span>

1. <span data-ttu-id="389d4-163">登录到[https://protection.office.com](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="389d4-163">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="389d4-164">在安全 & 合规性中心中，转到**权限**，然后单击添加 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="389d4-164">In the Security & Compliance Center, go to **Permissions** and then click Add (**+**).</span></span>

3. <span data-ttu-id="389d4-p111">在**角色**部分中，单击添加 (**+**) 和向下的滚动到**监督审阅管理员**。将此角色添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="389d4-p111">In the **Roles** section, click Add (**+**) and scroll down to **Supervisory Review Administrator**. Add this role to the role group.</span></span>

4. <span data-ttu-id="389d4-167">在**成员**部分中，添加您要管理您的组织的监督的人员。</span><span class="sxs-lookup"><span data-stu-id="389d4-167">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span>

<span data-ttu-id="389d4-168">有关角色组和权限的详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="389d4-168">For more information about role groups and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a><span data-ttu-id="389d4-169">远程 PowerShell 访问启用审阅者 （如果电子邮件位于 Exchange Online）</span><span class="sxs-lookup"><span data-stu-id="389d4-169">Enable remote PowerShell access for reviewers (if email is hosted on Exchange Online)</span></span>

1. <span data-ttu-id="389d4-170">按照[启用或禁用访问 to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)中的指南。</span><span class="sxs-lookup"><span data-stu-id="389d4-170">Follow the guidance in [Enable or disable access to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell).</span></span>

<span data-ttu-id="389d4-171"><a name="sensitiveinfo"> </a></span><span class="sxs-lookup"><span data-stu-id="389d4-171"></span></span>
  
## <a name="step-3---create-custom-sensitive-information-types-or-custom-keyword-dictionaries-optional"></a><span data-ttu-id="389d4-172">步骤 3-创建自定义的敏感信息类型或自定义关键字词典 （可选）</span><span class="sxs-lookup"><span data-stu-id="389d4-172">Step 3 - Create custom sensitive information types or custom keyword dictionaries (optional)</span></span>

<span data-ttu-id="389d4-173">若要选择从现有的自定义的敏感信息类型或自定义关键字词典监督策略向导中的，首先需要创建这些项，如果需要。</span><span class="sxs-lookup"><span data-stu-id="389d4-173">In order to pick from existing custom sensitive information types or custom keyword dictionaries in the supervision policy wizard, you first need to create these items if needed.</span></span>

### <a name="create-custom-sensitive-information-types"></a><span data-ttu-id="389d4-174">创建自定义的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="389d4-174">Create custom sensitive information types</span></span>

1. <span data-ttu-id="389d4-p112">在 Office 365 安全性 & 合规性中心中创建新的敏感信息类型。导航到**分类** \> **敏感信息类型**并按照**新敏感信息类型向导**中的步骤。此处，您将：</span><span class="sxs-lookup"><span data-stu-id="389d4-p112">Create a new sensitive information type in the Office 365 Security & Compliance Center. Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**. Here you will:</span></span>

    - <span data-ttu-id="389d4-178">定义的名称和说明的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="389d4-178">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="389d4-179">定义邻近、 可信度级别和主模式元素</span><span class="sxs-lookup"><span data-stu-id="389d4-179">Define the proximity, confidence level, and primary pattern elements</span></span>
    - <span data-ttu-id="389d4-180">检查您的选择并创建敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="389d4-180">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="389d4-181">有关详细信息，请参阅[创建自定义的敏感信息类型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="389d4-181">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

### <a name="create-custom-keyword-dictionarylexicon"></a><span data-ttu-id="389d4-182">创建自定义关键字词典/词汇表</span><span class="sxs-lookup"><span data-stu-id="389d4-182">Create custom keyword dictionary/lexicon</span></span>

1. <span data-ttu-id="389d4-p113">使用文本编辑器 （如记事本)，创建一个新文件，其中包含您想要监视监督策略中的关键字术语。确保每个术语是单独占一行和**Unicode/utf-16 (少 Endian)** 格式保存文件。</span><span class="sxs-lookup"><span data-stu-id="389d4-p113">Using a text editor (like Notepad), create a new file that includes the keyword terms you'd like to monitor in a supervision policy. Make sure each term is on a separate line and save the file in the **Unicode/UTF-16 (Little Endian)** format.</span></span>
2. <span data-ttu-id="389d4-p114">关键字文件导入使用 PowerShell Office 365 租户。若要连接到 Office 365 PowerShell，请参阅[连接到 Office 365 安全性 & 合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="389d4-p114">Import the keyword file into your Office 365 tenant using PowerShell. To connect to Office 365 with PowerShell, see [Connect to Office 365 Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

    <span data-ttu-id="389d4-187">您已连接到 Office 365 with PowerShell 后，运行以下命令以导入关键字字典：</span><span class="sxs-lookup"><span data-stu-id="389d4-187">After you've connected to Office 365 with PowerShell, run the following commands to import your keyword dictionary:</span></span>

    ```
    $fileData = Get-Content "your keyword path and file name" -Encoding Byte -ReadCount 0

    New-DlpKeywordDictionary -Name "Name for your keyword dictionary" -Description "optional description for your keyword dictionary" -FileData $fileData
    ```
    <span data-ttu-id="389d4-188">有关详细信息，请参阅[Create 关键字词典](create-a-keyword-dictionary.md)。</span><span class="sxs-lookup"><span data-stu-id="389d4-188">For more detailed information, see [Create a keyword dictionary](create-a-keyword-dictionary.md).</span></span>

3. <span data-ttu-id="389d4-p115">在 Office 365 安全性 & 合规性中心中创建新的敏感信息类型。导航到**分类** \> **敏感信息类型**并按照**新敏感信息类型向导**中的步骤。此处，您将：</span><span class="sxs-lookup"><span data-stu-id="389d4-p115">Create a new sensitive information type in the Office 365 Security & Compliance Center. Navigate to **Classifications** \> **Sensitive info types** and follow the steps in the **New sensitive info type wizard**. Here you will:</span></span>

    - <span data-ttu-id="389d4-192">定义的名称和说明的敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="389d4-192">Define a name and description for the sensitive info type</span></span>
    - <span data-ttu-id="389d4-193">将自定义词典添加为匹配的元素的要求</span><span class="sxs-lookup"><span data-stu-id="389d4-193">Add your custom dictionary as a requirement for the matching element</span></span>
    - <span data-ttu-id="389d4-194">检查您的选择并创建敏感信息类型</span><span class="sxs-lookup"><span data-stu-id="389d4-194">Review your selections and create the sensitive info type</span></span>

    <span data-ttu-id="389d4-195">创建自定义词典词汇表后，您可以查看使用[Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet 配置的关键字或添加和删除术语使用[集 DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="389d4-195">After the custom dictionary/lexicon is created, you can view the configured keywords using the [Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) cmdlet or add and remove terms using the [Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) cmdlet.</span></span>

    <span data-ttu-id="389d4-196">有关详细信息，请参阅[创建自定义的敏感信息类型](create-a-custom-sensitive-information-type.md)。</span><span class="sxs-lookup"><span data-stu-id="389d4-196">For more detailed information, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

<span data-ttu-id="389d4-197"><a name="setupsuper"> </a></span><span class="sxs-lookup"><span data-stu-id="389d4-197"></span></span>

## <a name="step-4---set-up-a-supervision-policy-required"></a><span data-ttu-id="389d4-198">步骤 4-设置 （必需） 监督策略</span><span class="sxs-lookup"><span data-stu-id="389d4-198">Step 4 - Set up a supervision policy (required)</span></span>
  
1. <span data-ttu-id="389d4-199">登录到[https://protection.office.com](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="389d4-199">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="389d4-200">在安全 & 合规性中心中，选择**监控**。</span><span class="sxs-lookup"><span data-stu-id="389d4-200">In the Security & Compliance Center, select **Supervision**.</span></span>
  
3. <span data-ttu-id="389d4-p116">选择**创建**，然后按照向导设置策略的以下页面。使用向导中，您将：</span><span class="sxs-lookup"><span data-stu-id="389d4-p116">Select **Create** and then follow the wizard to set up the following pages of the policy. Using the wizard, you will:</span></span>

    - <span data-ttu-id="389d4-203">为策略指定的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="389d4-203">Give the policy a name and description.</span></span>
    - <span data-ttu-id="389d4-204">选择用户或组监督，包括选择用户或您想要排除的组。</span><span class="sxs-lookup"><span data-stu-id="389d4-204">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    - <span data-ttu-id="389d4-205">定义监督策略条件。</span><span class="sxs-lookup"><span data-stu-id="389d4-205">Define the supervision policy conditions.</span></span>
    - <span data-ttu-id="389d4-p117">选择是否您想要包含敏感信息类型。这是您可以在其中选择默认和自定义的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="389d4-p117">Choose if you'd like to include sensitive information types. This is where you can select default and custom sensitive info types.</span></span>
    - <span data-ttu-id="389d4-208">定义通信，若要查看的百分比。</span><span class="sxs-lookup"><span data-stu-id="389d4-208">Define the percentage of communications to review.</span></span>
    - <span data-ttu-id="389d4-p118">选择审阅者的策略。审阅者可以是单个用户或[已启用邮件的安全组](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)。</span><span class="sxs-lookup"><span data-stu-id="389d4-p118">Choose the reviewers for the policy. Reviewers can be individual users or [mail-enabled security groups](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group).</span></span>
    - <span data-ttu-id="389d4-211">检查您的策略选择并创建策略。</span><span class="sxs-lookup"><span data-stu-id="389d4-211">Review your policy selections and create the policy.</span></span>

<span data-ttu-id="389d4-212"><a name="TestPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="389d4-212"></span></span>

## <a name="step-5---test-your-supervision-policy-optional"></a><span data-ttu-id="389d4-213">步骤 5-测试 （可选） 您监督策略</span><span class="sxs-lookup"><span data-stu-id="389d4-213">Step 5 - Test your supervision policy (optional)</span></span>

<span data-ttu-id="389d4-p119">创建监督策略后，最好进行测试以确保您定义的条件正在正确强制实施策略。如果您监督策略中包括的敏感信息类型，还可能希望向[测试您的数据丢失防护 (DLP) 策略](create-test-tune-dlp-policy.md)。请按照以下步骤以测试监督策略：</span><span class="sxs-lookup"><span data-stu-id="389d4-p119">After you create a supervision policy, it's a good idea to test to make sure that the conditions you defined are being properly enforced by the policy. You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your supervision policies include sensitive information types. Follow the steps below to test your supervision policy:</span></span>

1. <span data-ttu-id="389d4-217">打开电子邮件客户端或 Microsoft 团队作为监管用户登录要用于测试的策略中定义。</span><span class="sxs-lookup"><span data-stu-id="389d4-217">Open an email client or Microsoft Teams logged in as a supervised user defined in the policy you want to test.</span></span>
2. <span data-ttu-id="389d4-p120">发送电子邮件或 Microsoft 团队聊天满足监督策略中已定义的条件。这可以是关键字、 附件大小、 域等。请确保您确定是否太严格或太宽松您配置的条件设置在策略。</span><span class="sxs-lookup"><span data-stu-id="389d4-p120">Send an email or Microsoft Teams chat that meets the criteria you've defined in the supervision policy. This can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy is too restrictive or too lenient.</span></span>

    > [!Note]
    > <span data-ttu-id="389d4-p121">受到定义的策略的电子邮件以处理几乎可以实时和配置的策略后，立即可以测试。在 Microsoft 团队中的聊天可能需要 24 小时完全处理策略中。</span><span class="sxs-lookup"><span data-stu-id="389d4-p121">Emails subject to defined policies are processed in near real-time and can be tested immediately after the policy is configured. Chats in Microsoft Teams can take up to 24 hours to fully process in a policy.</span></span> 

3. <span data-ttu-id="389d4-p122">登录到 Office 365 租户为审阅者监督策略中指定。导航到**监督** > *您自定义策略* > **打开**以查看策略的报告。</span><span class="sxs-lookup"><span data-stu-id="389d4-p122">Log into your Office 365 tenant as a reviewer designated in the supervision policy. Navigate to **Supervision** > *Your Custom Policy* > **Open** to view the report for the policy.</span></span>

<span data-ttu-id="389d4-224"><a name="UseOutlook"> </a></span><span class="sxs-lookup"><span data-stu-id="389d4-224"></span></span>

## <a name="step-6---set-up-outlook-add-in-for-reviewers-optional"></a><span data-ttu-id="389d4-225">步骤 6-Set up Outlook 外接程序审阅者 （可选）</span><span class="sxs-lookup"><span data-stu-id="389d4-225">Step 6 - Set up Outlook add-in for reviewers (optional)</span></span>

<span data-ttu-id="389d4-226">要使用 Outlook 而不是使用 Office 365 或在 web 上的 Outlook 中的监督仪表板查看 communications 审阅者必须安装监督外接程序其 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="389d4-226">Reviewers that want to use Outlook instead of using the Supervision dashboard in Office 365 or Outlook on the web to review communications must install the Supervision add-in for their Outlook client.</span></span>

### <a name="step-1-copy-the-address-for-the-supervision-mailbox"></a><span data-ttu-id="389d4-227">步骤 1： 复制监督邮箱的地址</span><span class="sxs-lookup"><span data-stu-id="389d4-227">Step 1: Copy the address for the supervision mailbox</span></span>

<span data-ttu-id="389d4-228">若要安装外接程序 Outlook 桌面程序，您将需要作为监督策略设置的一部分创建的监督邮箱地址。</span><span class="sxs-lookup"><span data-stu-id="389d4-228">To install the add-in for Outlook desktop, you'll need the address for the supervision mailbox that was created as part of the supervision policy setup.</span></span>
  
> [!NOTE]
> <span data-ttu-id="389d4-229">如果其他人创建策略，您将需要从原始安装外接程序获得此地址。</span><span class="sxs-lookup"><span data-stu-id="389d4-229">If someone else created the policy, you'll need to get this address from them to install the add-in.</span></span>

 <span data-ttu-id="389d4-230">**若要查找的监督邮箱地址**</span><span class="sxs-lookup"><span data-stu-id="389d4-230">**To find the supervision mailbox address**</span></span>
  
1. <span data-ttu-id="389d4-231">登录到[安全&amp;合规性中心](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="389d4-231">Sign into the [Security &amp; Compliance Center](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span>

2. <span data-ttu-id="389d4-232">转到**监督**。</span><span class="sxs-lookup"><span data-stu-id="389d4-232">Go to **Supervision**.</span></span>

3. <span data-ttu-id="389d4-233">单击收集的通信您想要查看的监督策略。</span><span class="sxs-lookup"><span data-stu-id="389d4-233">Click the supervision policy that's gathering the communications you want to review.</span></span>

4. <span data-ttu-id="389d4-234">在策略的详细信息弹出下**监管邮箱**，, 复制地址。</span><span class="sxs-lookup"><span data-stu-id="389d4-234">In the policy details flyout, under **Supervision mailbox**, copy the address.</span></span><br/><span data-ttu-id="389d4-235">![显示突出显示的监督邮箱地址监督策略的详细信息弹出的监督邮箱部分](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span><span class="sxs-lookup"><span data-stu-id="389d4-235">![The 'Supervision Mailbox' section of a supervision policy's details flyout showing the supervision mailbox address highlighted](media/71779d0e-4f01-4dd3-8234-5f9c30eeb067.jpg)</span></span>
  
### <a name="step-2-configure-the-supervision-mailbox-for-outlook-desktop-access"></a><span data-ttu-id="389d4-236">步骤 2： 配置 Outlook 桌面访问的监督邮箱</span><span class="sxs-lookup"><span data-stu-id="389d4-236">Step 2: Configure the supervision mailbox for Outlook desktop access</span></span>

<span data-ttu-id="389d4-237">接下来，审阅者将需要运行的几 Exchange Online PowerShell 命令，以便他们可以将 Outlook 连接到监督邮箱。</span><span class="sxs-lookup"><span data-stu-id="389d4-237">Next, reviewers will need to run a couple Exchange Online PowerShell commands so they can connect Outlook to the supervision mailbox.</span></span>
  
1. <span data-ttu-id="389d4-p123">连接到 Exchange Online PowerShell 中。[我该如何做？](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="389d4-p123">Connect to Exchange Online PowerShell. [How do I do this?](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)</span></span>

2. <span data-ttu-id="389d4-240">运行以下命令，其中*SupervisoryReview{GUID}@domain.onmicrosoft.com*是您在上面的步骤 1 中复制的地址，*用户*是将连接到步骤 3 中的监督邮箱审核者的名称。</span><span class="sxs-lookup"><span data-stu-id="389d4-240">Run the following commands, where  *SupervisoryReview{GUID}@domain.onmicrosoft.com*  is the address you copied in Step 1 above, and  *User*  is the name of the reviewer who will be connecting to the supervision mailbox in Step 3.</span></span>

    ```Add-MailboxPermission "SupervisoryReview{GUID}@domain.onmicrosoft.com" -User <alias or email address of the account that has reviewer permissions to the supervision mailbox> -AccessRights FullAccess```

    ```Set-Mailbox "<SupervisoryReview{GUID}@domain.onmicrosoft.com>" -HiddenFromAddressListsEnabled: $false```

3. <span data-ttu-id="389d4-241">等待至少一个小时之后才能接着下面的步骤 3。</span><span class="sxs-lookup"><span data-stu-id="389d4-241">Wait at least an hour before moving on to Step 3 below.</span></span>

### <a name="step-3-create-an-outlook-profile-to-connect-to-the-supervision-mailbox"></a><span data-ttu-id="389d4-242">步骤 3： 创建 Outlook 配置文件连接到监督邮箱</span><span class="sxs-lookup"><span data-stu-id="389d4-242">Step 3: Create an Outlook profile to connect to the supervision mailbox</span></span>

<span data-ttu-id="389d4-243">最后一步，将需要审阅者创建的 Outlook 配置文件连接到监督邮箱。</span><span class="sxs-lookup"><span data-stu-id="389d4-243">For the final step, reviewers will need to create an Outlook profile to connect to the supervision mailbox.</span></span>

> [!NOTE]
> <span data-ttu-id="389d4-p124">若要创建新的 Outlook 配置文件，您将使用 Windows 控制面板中邮件设置。您需要访问这些设置的路径可能取决于您使用 Windows 操作系统 （Windows 7、 Windows 8 或 Windows 10），并安装哪个版本的 Outlook。</span><span class="sxs-lookup"><span data-stu-id="389d4-p124">To create a new Outlook profile, you'll use the Mail settings in the Windows Control Panel. The path you take to get to these settings might depend on which Windows operating system (Windows 7, Windows 8, or Windows 10) you're using, and which version of Outlook is installed.</span></span>
  
1. <span data-ttu-id="389d4-246">打开控制面板，并在窗口顶部的**搜索**框中，键入**邮件**。</span><span class="sxs-lookup"><span data-stu-id="389d4-246">Open the Control Panel, and in the **Search** box at the top of the window, type **Mail**.</span></span><br/><span data-ttu-id="389d4-p125">(不确定如何获取控制面板？请参阅[其中是 Control Panel？](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span><span class="sxs-lookup"><span data-stu-id="389d4-p125">(Not sure how to get to the Control Panel? See [Where is Control Panel?](https://support.microsoft.com/help/13764/windows-where-is-control-panel))</span></span>
  
2. <span data-ttu-id="389d4-249">打开**邮件**应用程序。</span><span class="sxs-lookup"><span data-stu-id="389d4-249">Open the **Mail** app.</span></span>

3. <span data-ttu-id="389d4-250">在**邮件设置-Outlook**中，单击**显示配置文件**。</span><span class="sxs-lookup"><span data-stu-id="389d4-250">In **Mail Setup - Outlook**, click **Show Profiles**.</span></span><br/><span data-ttu-id="389d4-251">![邮件设置的 Outlook 与显示配置文件按钮突出显示的对话框](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span><span class="sxs-lookup"><span data-stu-id="389d4-251">![The 'Mail Setup - Outlook' dialog box with the 'Show Profiles' button highlighted](media/28b5dae9-d10c-4f2b-926a-294c857d555c.jpg)</span></span>
  
4. <span data-ttu-id="389d4-p126">在**邮件**框中，单击**添加**。然后，在**新的配置文件**中，输入监督邮箱 （例如**监督**） 的名称。</span><span class="sxs-lookup"><span data-stu-id="389d4-p126">In **Mail**, click **Add**. Then, in **New Profile**, enter a name for the supervision mailbox (such as **Supervision**).</span></span><br/><span data-ttu-id="389d4-254">![在配置文件名称框中显示名称监督' 新配置文件对话框](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span><span class="sxs-lookup"><span data-stu-id="389d4-254">![The 'New Profile' dialog showing the name 'Supervision' in the 'Profile Name' box](media/d02ae181-b541-4ec6-8f51-698f30033204.jpg)</span></span>
  
5. <span data-ttu-id="389d4-255">在**将 Outlook 连接到 Office 365**中，单击**连接到不同的帐户**。</span><span class="sxs-lookup"><span data-stu-id="389d4-255">In **Connect Outlook to Office 365**, click **Connect to a different account**.</span></span><br/><span data-ttu-id="389d4-256">![突出显示的连接到不同的帐户链接连接到 Office 365 Outlook 邮件](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span><span class="sxs-lookup"><span data-stu-id="389d4-256">![The 'Connect Outlook to Office 365' message with the 'Connect to a different account' link highlighted](media/fac49ff8-a7f0-4e82-a271-9ec045a95de1.jpg)</span></span>
  
6. <span data-ttu-id="389d4-257">在**自动帐户设置**中，选择**手动安装或其他服务器类型**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="389d4-257">In **Auto Account Setup**, choose **Manual setup or additional server types**, and then click **Next**.</span></span>

7. <span data-ttu-id="389d4-p127">在**选择帐户类型**，选择**Office 365**。然后，在**电子邮件地址**框中，输入之前复制监督邮箱的地址。</span><span class="sxs-lookup"><span data-stu-id="389d4-p127">In **Choose Your Account Type**, choose **Office 365**. Then, in the **Email Address** box, enter the address of the supervision mailbox you copied previously.</span></span><br/><span data-ttu-id="389d4-260">![在 Outlook 中显示电子邮件地址框中突出显示添加帐户对话框的选择您的帐户类型页面。](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span><span class="sxs-lookup"><span data-stu-id="389d4-260">![The 'Choose Your Account Type' page of the 'Add Account' dialog in Outlook showing the 'Email Address' box highlighted.](media/4f601236-9f69-4cf6-a58c-0b91204aa8cb.jpg)</span></span>
  
8. <span data-ttu-id="389d4-261">出现提示时，输入您的 Office 365 凭据。</span><span class="sxs-lookup"><span data-stu-id="389d4-261">When prompted, enter your Office 365 credentials.</span></span>

9. <span data-ttu-id="389d4-262">如果成功，您将看到**监督-\<策略名称\>** 在 Outlook 的文件夹列表视图中列出的文件夹。</span><span class="sxs-lookup"><span data-stu-id="389d4-262">If successful, you'll see the **Supervision - \<policy name\>** folder listed in the Folder List view in Outlook.</span></span>

## <a name="powershell-reference"></a><span data-ttu-id="389d4-263">PowerShell 参考</span><span class="sxs-lookup"><span data-stu-id="389d4-263">PowerShell reference</span></span>

<span data-ttu-id="389d4-264">如果需要您可以创建和管理使用以下 PowerShell cmdlet 的监督策略：</span><span class="sxs-lookup"><span data-stu-id="389d4-264">If needed, you can create and manage supervision policies using the following PowerShell cmdlets:</span></span>

- [<span data-ttu-id="389d4-265">新 SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="389d4-265">New-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="389d4-266">Get SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="389d4-266">Get-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/get-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="389d4-267">设置 SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="389d4-267">Set-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="389d4-268">删除 SupervisoryReviewPolicyV2</span><span class="sxs-lookup"><span data-stu-id="389d4-268">Remove-SupervisoryReviewPolicyV2</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/remove-supervisoryreviewpolicyv2?view=exchange-ps)
- [<span data-ttu-id="389d4-269">新 SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="389d4-269">New-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="389d4-270">设置 SupervisoryReviewRule</span><span class="sxs-lookup"><span data-stu-id="389d4-270">Set-SupervisoryReviewRule</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/set-supervisoryreviewrule?view=exchange-ps)
- [<span data-ttu-id="389d4-271">Get SupervisoryReviewActivity</span><span class="sxs-lookup"><span data-stu-id="389d4-271">Get-SupervisoryReviewActivity</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewactivity)
- [<span data-ttu-id="389d4-272">Get SupervisoryReviewOverallProgressReport</span><span class="sxs-lookup"><span data-stu-id="389d4-272">Get-SupervisoryReviewOverallProgressReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewoverallprogressreport)
- [<span data-ttu-id="389d4-273">Get SupervisoryReviewTopCasesReport</span><span class="sxs-lookup"><span data-stu-id="389d4-273">Get-SupervisoryReviewTopCasesReport</span></span>](https://docs.microsoft.com/powershell/module/exchange/reporting/get-supervisoryreviewtopcasesreport)