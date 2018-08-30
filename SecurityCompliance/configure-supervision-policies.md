---
title: 配置组织的监督策略
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
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
ms.openlocfilehash: a919d65f5c0967a44ac12b7e02d477dac2113704
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526081"
---
# <a name="configure-supervision-policies-for-your-organization"></a><span data-ttu-id="6abcb-103">配置组织的监督策略</span><span class="sxs-lookup"><span data-stu-id="6abcb-103">Configure supervision policies for your organization</span></span>

<span data-ttu-id="6abcb-104">使用监督策略来捕获员工通信的内部或外部的审阅者的检查。</span><span class="sxs-lookup"><span data-stu-id="6abcb-104">Use supervision policies to capture employee communications for examination by internal or external reviewers.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6abcb-p101">使用监督策略要求对您的组织的 Office 365 E5 订阅。如果您不具有该计划，并且想要尝试监督，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p101">Using supervision policies requires an Office 365 E5 subscription for your organization. If you don't have that plan and want to try supervision, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="6abcb-107">请按照下列步骤设置和 Office 365 组织中使用监督：</span><span class="sxs-lookup"><span data-stu-id="6abcb-107">Follow these steps to set up and use supervision in your Office 365 organization:</span></span> 
  
- [<span data-ttu-id="6abcb-108">为监督设置组</span><span class="sxs-lookup"><span data-stu-id="6abcb-108">Set up groups for Supervision</span></span>](configure-supervision-policies.md#exampledist)
    
    <span data-ttu-id="6abcb-p102">开始使用监督之前，确定谁将其通信检查以及谁将执行这些 reviews （英文）。如果您想要开始使用几个用户查看监督的工作方式，则可以跳过现在设置组。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p102">Before you start using supervision, determine who will have their communications reviewed and who will perform those reviews. If you want to get started with just a few users to see how supervision works, you can skip setting up groups for now.</span></span>
    
- [<span data-ttu-id="6abcb-111">您的组织中公开监督</span><span class="sxs-lookup"><span data-stu-id="6abcb-111">Make supervision available in your organization</span></span>](configure-supervision-policies.md#SRavailable)
    
    <span data-ttu-id="6abcb-p103">将自己添加到监督审阅角色组以便您可以设置策略。已分配该角色的任何人都可以访问下安全中的**数据调控****监督**页&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p103">Add yourself to the Supervisory Review role group so you can set up policies. Anyone who has this role assigned can access the **Supervision** page under **Data Governance** in the Security &amp; Compliance Center.</span></span> 
    
- [<span data-ttu-id="6abcb-114">设置监督策略</span><span class="sxs-lookup"><span data-stu-id="6abcb-114">Set up a supervision policy</span></span>](configure-supervision-policies.md#setupsuper)
    
    <span data-ttu-id="6abcb-p104">您将创建监督策略中安全&amp;合规性中心。这些策略定义的通信将受到组织中查看和指定用户应执行 reviews （英文）。Communications 包括电子邮件，以及第三方平台 communications （如 Facebook、 Twitter 等。）</span><span class="sxs-lookup"><span data-stu-id="6abcb-p104">You'll create supervision policies in the Security &amp; Compliance Center. These policies define which communications are subject to review in your organization, and specifies who should perform reviews. Communications include email as well as 3rd-party platform communications (such as Facebook, Twitter, etc.)</span></span>
    
- [<span data-ttu-id="6abcb-118">使用 Outlook web app 查看 communications 标识监督策略</span><span class="sxs-lookup"><span data-stu-id="6abcb-118">Use Outlook web app to review communications identified by a supervision policy</span></span>](configure-supervision-policies.md#UseOutlook)
    
    <span data-ttu-id="6abcb-p105">监督外接程序，审阅者访问 Outlook web app 中右监督功能这样他们可以评估并对每个项目进行分类。对桌面的 Outlook 版本支持即将提供。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p105">The Supervision add-in gives reviewers access to the supervision functionality right within Outlook web app so they can assess and categorize each item. Support for the desktop version of Outlook is coming soon.</span></span>
    
- <span data-ttu-id="6abcb-121">**运行监督报告**</span><span class="sxs-lookup"><span data-stu-id="6abcb-121">**Run the supervision report**</span></span>
    
    <span data-ttu-id="6abcb-p106">使用监督报表查看级别的策略和审阅者的查看活动。对于每个策略，您还可以查看活动的当前状态查看 live 统计信息。有关详细信息，请参阅[监督 reports](supervision-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p106">Use the supervision reports to see the review activity at the policy and reviewer level. For each policy, you can also view live statistics on the current state of review activity. For details, see [Supervision reports](supervision-reports.md).</span></span>
    
## <a name="set-up-groups-for-supervision"></a><span data-ttu-id="6abcb-125">为监督设置组</span><span class="sxs-lookup"><span data-stu-id="6abcb-125">Set up groups for Supervision</span></span>
<span data-ttu-id="6abcb-126"><a name="exampledist"> </a></span><span class="sxs-lookup"><span data-stu-id="6abcb-126"></span></span>

 <span data-ttu-id="6abcb-p107">创建监督策略时，您将决定谁将具有检查其通信以及谁将执行这些 reviews （英文）。在策略，您将使用电子邮件地址来标识个人或组的人员。若要简化您的设置，创建组会检查其通信的人员和组将查看这些通信的人员。如果您使用的组，则可能需要几个 — 例如，如果您想要监控的人员，两个不同组之间的通信，或如果您想要指定不打算管理组。有关此工作原理的详细信息，请参阅[示例通讯组](configure-supervision-policies.md#GroupExample)。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p107">When you create a supervision policy, you'll determine who will have their communications reviewed and who will perform those reviews. In the policy, you'll use email addresses to identify individuals or groups of people. To simplify your setup, create groups for people who will have their communication reviewed and groups for people who will review those communications. If you're using groups, you might need several—for example, if you want to monitor communications between two distinct groups of people, or if you want to specify a group that isn't going to be supervised. See [Example distribution groups](configure-supervision-policies.md#GroupExample) for details about how this works.</span></span> 
  
<span data-ttu-id="6abcb-p108">监督 communications 之间或在组织中的组中，请在 Exchange 管理中心中设置通讯组 (转到**收件人** \> **组**)。有关设置通讯组的详细信息，请参阅[管理通讯组](http://go.microsoft.com/fwlink/?LinkId=613635)</span><span class="sxs-lookup"><span data-stu-id="6abcb-p108">To supervise communications between or within groups in your organization, set up distribution groups in the Exchange admin center (go to **recipients** \> **groups**). For more information about setting up distribution groups, see [Manage distribution groups](http://go.microsoft.com/fwlink/?LinkId=613635)</span></span>
  
> [!NOTE]
> <span data-ttu-id="6abcb-p109">您可还用于动态通讯组或安全组监督如果您愿意。为了帮助您决定是否这些更好地满足组织需求，请参阅[管理已启用邮件的安全组](http://go.microsoft.com/fwlink/?LinkId=627033)和[管理动态通讯组](http://go.microsoft.com/fwlink/?LinkId=627058)。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p109">You can also use dynamic distribution groups or security groups for supervision if you prefer. To help you decide if these better fit your organization needs, see [Manage mail-enabled security groups](http://go.microsoft.com/fwlink/?LinkId=627033), and [Manage dynamic distribution groups](http://go.microsoft.com/fwlink/?LinkId=627058).</span></span> 
  
### <a name="example-distribution-groups"></a><span data-ttu-id="6abcb-136">示例通讯组</span><span class="sxs-lookup"><span data-stu-id="6abcb-136">Example distribution groups</span></span>
<span data-ttu-id="6abcb-137"><a name="GroupExample"> </a></span><span class="sxs-lookup"><span data-stu-id="6abcb-137"></span></span>

<span data-ttu-id="6abcb-138">本示例包含已设置名为 Contoso 财务国际财务组织的通讯组。</span><span class="sxs-lookup"><span data-stu-id="6abcb-138">This example includes a distribution group that has been set up for a financial organization called Contoso Financial International.</span></span> 
  
<span data-ttu-id="6abcb-p110">在 Contoso Financial International 中，必须监督美国经纪人之间的通信抽样。但是，无需监督该组中的合规部主管。对于本例，我们可以创建以下组：</span><span class="sxs-lookup"><span data-stu-id="6abcb-p110">In Contoso Financial International, a sampling of communications between brokers in the United States must be supervised. However, compliance officers within that group do not require supervision. For this example, we can create the following groups:</span></span>
  
|<span data-ttu-id="6abcb-142">**设置此通讯组**</span><span class="sxs-lookup"><span data-stu-id="6abcb-142">**Set up this distribution group**</span></span>|<span data-ttu-id="6abcb-143">**组地址（别名）**</span><span class="sxs-lookup"><span data-stu-id="6abcb-143">**Group address (alias)**</span></span>|<span data-ttu-id="6abcb-144">**说明**</span><span class="sxs-lookup"><span data-stu-id="6abcb-144">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6abcb-145">所有美国经纪人</span><span class="sxs-lookup"><span data-stu-id="6abcb-145">All US brokers</span></span>  <br/> |<span data-ttu-id="6abcb-146">US_Brokers@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="6abcb-146">US_Brokers@Contoso.com</span></span>  <br/> |<span data-ttu-id="6abcb-147">此组包括为 Contoso 工作的所有在美国的经纪人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6abcb-147">This group includes email addresses for all US-based brokers who work for Contoso.</span></span>  <br/> |
|<span data-ttu-id="6abcb-148">所有美国合规部主管</span><span class="sxs-lookup"><span data-stu-id="6abcb-148">All US compliance officers</span></span>  <br/> |<span data-ttu-id="6abcb-149">US_Compliance@Contoso.com</span><span class="sxs-lookup"><span data-stu-id="6abcb-149">US_Compliance@Contoso.com</span></span>  <br/> |<span data-ttu-id="6abcb-p111">此组包括所有美国合规部主管，就职 contoso 电子邮件地址。由于此组的所有美国经纪人子集，因此可以从监督策略到例外合规部主管使用此别名。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p111">This group includes email addresses for all US-based compliance officers who work for Contoso. Because this group is a subset of all US-based brokers, you can use this alias to exempt compliance officers from a supervision policy.</span></span>  <br/> |
   
<span data-ttu-id="6abcb-152">[设置监督策略](configure-supervision-policies.md#setupsuper)一节描述如何配置策略时使用这些组。</span><span class="sxs-lookup"><span data-stu-id="6abcb-152">The [Set up a supervision policy](configure-supervision-policies.md#setupsuper) section describes how you can use these groups when you configure the policy.</span></span> 
  
## <a name="make-supervision-available-in-your-organization"></a><span data-ttu-id="6abcb-153">您的组织中公开监督</span><span class="sxs-lookup"><span data-stu-id="6abcb-153">Make supervision available in your organization</span></span>
<span data-ttu-id="6abcb-154"><a name="SRavailable"> </a></span><span class="sxs-lookup"><span data-stu-id="6abcb-154"></span></span>

<span data-ttu-id="6abcb-155">为了使**监督**菜单选项安全&amp;合规性中心，您必须分配监督审阅管理员角色。</span><span class="sxs-lookup"><span data-stu-id="6abcb-155">To make **Supervision** available as a menu option in the Security &amp; Compliance Center, you must be assigned the Supervisory Review Administrator role.</span></span> 
  
<span data-ttu-id="6abcb-156">若要执行此操作，也可以将自己添加为监督审阅角色组的成员，也可以创建新的角色组。</span><span class="sxs-lookup"><span data-stu-id="6abcb-156">To do this, you can either add yourself as a member of the Supervisory Review role group, or you can create a new role group.</span></span>
  
### <a name="add-members-to-the-supervisory-review-role-group"></a><span data-ttu-id="6abcb-157">向主管审阅角色组添加成员</span><span class="sxs-lookup"><span data-stu-id="6abcb-157">Add members to the Supervisory Review role group</span></span>

1. <span data-ttu-id="6abcb-158">登录到[https://protection.office.com](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="6abcb-158">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="6abcb-159">安全中&amp;合规性中心中，转到**权限**。</span><span class="sxs-lookup"><span data-stu-id="6abcb-159">In the Security &amp; Compliance Center, go to **Permissions**.</span></span>
    
3. <span data-ttu-id="6abcb-160">选择**监督审阅**角色组，然后单击编辑图标。</span><span class="sxs-lookup"><span data-stu-id="6abcb-160">Select the **Supervisory Review** role group and then click the Edit icon.</span></span> 
    
4. <span data-ttu-id="6abcb-161">在**成员**部分中，添加您要管理您的组织的监督的人员。</span><span class="sxs-lookup"><span data-stu-id="6abcb-161">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span> 
    
### <a name="create-a-new-role-group"></a><span data-ttu-id="6abcb-162">创建新的角色组</span><span class="sxs-lookup"><span data-stu-id="6abcb-162">Create a new role group</span></span>

1. <span data-ttu-id="6abcb-163">登录到[https://protection.office.com](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="6abcb-163">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="6abcb-164">安全中&amp;合规性中心，转到**权限**，然后单击添加 ( **+**)。</span><span class="sxs-lookup"><span data-stu-id="6abcb-164">In the Security &amp; Compliance Center, go to **Permissions** and then click Add ( **+**).</span></span>
    
3. <span data-ttu-id="6abcb-p112">在**角色**部分中，单击添加 ( **+**) 和向下的滚动到**监督审阅管理员**。将此角色添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p112">In the **Roles** section, click Add ( **+**) and scroll down to **Supervisory Review Administrator**. Add this role to the role group.</span></span>
    
4. <span data-ttu-id="6abcb-167">在**成员**部分中，添加您要管理您的组织的监督的人员。</span><span class="sxs-lookup"><span data-stu-id="6abcb-167">In the **Members** section, add the people who you want to manage supervision for your organization.</span></span> 
    
<span data-ttu-id="6abcb-168">有关角色组和权限的详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="6abcb-168">For more information about role groups and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center ](permissions-in-the-security-and-compliance-center.md).</span></span>
  
## <a name="set-up-a-supervision-policy"></a><span data-ttu-id="6abcb-169">设置监督策略</span><span class="sxs-lookup"><span data-stu-id="6abcb-169">Set up a supervision policy</span></span>
<span data-ttu-id="6abcb-170"><a name="setupsuper"> </a></span><span class="sxs-lookup"><span data-stu-id="6abcb-170"></span></span>

> [!IMPORTANT]
> <span data-ttu-id="6abcb-171">创建监督策略之前，必须首先删除任何现有的监督审阅策略。</span><span class="sxs-lookup"><span data-stu-id="6abcb-171">Before creating a supervision policy, you must first remove any existing supervisory review policies.</span></span> 
  
1. <span data-ttu-id="6abcb-172">登录到[https://protection.office.com](https://protection.office.com)使用 Office 365 组织中的管理帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="6abcb-172">Sign into [https://protection.office.com](https://protection.office.com) using credentials for an admin account in your Office 365 organization.</span></span> 
    
2. <span data-ttu-id="6abcb-173">安全中&amp;合规性中心中，转到单击**数据调控** \> **监督**。</span><span class="sxs-lookup"><span data-stu-id="6abcb-173">In the Security &amp; Compliance Center, go to click **Data governance** \> **Supervision**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="6abcb-p113">在左侧导航窗格中作为**监督审阅 (retiring 很快)** 可能会显示以前版本的功能。将很快否决此版本，并为其移除。调用**监督**的新版本需要其位置。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p113">The previous version of the feature may show in the left-hand navigation as **Supervisory Review (retiring soon)**. This version will soon be deprecated and removed. The new version called **Supervision** will take its place.</span></span> 
  
3. <span data-ttu-id="6abcb-177">单击**创建**，然后按照向导设置策略的以下页面。</span><span class="sxs-lookup"><span data-stu-id="6abcb-177">Click **Create** and then follow the wizard to set up the following pages of the policy.</span></span> 
    
### <a name="policy-name-and-description"></a><span data-ttu-id="6abcb-178">策略名称和说明</span><span class="sxs-lookup"><span data-stu-id="6abcb-178">Policy name and description</span></span>

<span data-ttu-id="6abcb-p114">输入名称和您的策略的说明。出于举例目的，我们将命名策略 Contoso 美国经纪人。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p114">Enter a name and a description for your policy. For example purposes, we'll name the policy Contoso US Brokers.</span></span>
  
### <a name="choose-users-to-supervise"></a><span data-ttu-id="6abcb-181">选择要管理用户</span><span class="sxs-lookup"><span data-stu-id="6abcb-181">Choose users to supervise</span></span>

- <span data-ttu-id="6abcb-p115">在**Supervise 这些用户或组**框中，选择用户或组监督您希望其通信。为 Contoso 美国经纪人粘滞与我们的示例，我们将选择组 US_Brokers@Contoso.com 此处。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p115">In the **Supervise these users or groups** box, choose the users or groups whose communications your want to supervise. Sticking with our example for Contoso US Brokers, we'll choose the group US_Brokers@Contoso.com here.</span></span> 
    
- <span data-ttu-id="6abcb-p116">如果您选择某个组将监督，您可以使用**来排除这些用户**框中选择不受监督的组的成员。使用的示例，我们将排除组 US_Compliance@Contoso.com 此处。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p116">If you chose a group to supervise, you can use the **Exclude these users** box to choose members of the group who are exempt from supervision . Using the example , we'll exclude the group US_Compliance@Contoso.com here.</span></span> 
    
### <a name="choose-communications-to-review"></a><span data-ttu-id="6abcb-186">选择通信查看</span><span class="sxs-lookup"><span data-stu-id="6abcb-186">Choose communications to review</span></span>
<span data-ttu-id="6abcb-187"><a name="CommsToReview"> </a></span><span class="sxs-lookup"><span data-stu-id="6abcb-187"></span></span>

<span data-ttu-id="6abcb-p117">默认情况下，**方向**条件显示，并且无法删除。如果您想要范围 （如仅查看内容，其中包含特定词或短语），进一步查看，请单击**添加条件**。如果需要您可以指定多个条件。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p117">By default, the **Direction is** condition is displayed and can't be removed. If you want to scope the review further (such as only reviewing content that contains certain words or phrases), click **Add a condition**. You can specify multiple conditions if needed.</span></span>
  
<span data-ttu-id="6abcb-p118">您选择的条件 （类似于从 Facebook 或收存箱） 在组织中的电子邮件和第三方源中将适用于通讯。关于导入您的 Office 365 组织的第三方通信的详细信息，请参阅[Office 365 中的存档第三方数据](https://technet.microsoft.com/EN-US/library/mt621583.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p118">The conditions you choose will apply to communications from both email and 3rd-party sources in your organization (like from Facebook or DropBox). For details about importing 3rd-party communications into your Office 365 organization, see [Archiving third-party data in Office 365](https://technet.microsoft.com/EN-US/library/mt621583.aspx).</span></span>
  
<span data-ttu-id="6abcb-193">下表详细解释每个条件。</span><span class="sxs-lookup"><span data-stu-id="6abcb-193">The following table explains more about each condition.</span></span>
  
|<span data-ttu-id="6abcb-194">**条件**</span><span class="sxs-lookup"><span data-stu-id="6abcb-194">**Condition**</span></span>|<span data-ttu-id="6abcb-195">**如何使用此条件**</span><span class="sxs-lookup"><span data-stu-id="6abcb-195">**How to use this condition**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6abcb-196">用法说明</span><span class="sxs-lookup"><span data-stu-id="6abcb-196">Direction is</span></span>  <br/> |<span data-ttu-id="6abcb-197">选择**入站**查看 communications 发送**到**您选择监督**从**人员的人不包含在策略。</span><span class="sxs-lookup"><span data-stu-id="6abcb-197">Choose **Inbound** to review communications that are sent **to** the people you chose to supervise **from** people not included in the policy.</span></span>  <br/> <span data-ttu-id="6abcb-198">如果您想要查看的通信选择**出站****发送您选择监督的人员*** * 到 * * 人员不包含在策略。</span><span class="sxs-lookup"><span data-stu-id="6abcb-198">Choose **Outbound** if you want to review communications that are sent **from** the people you chose to supervise ** to ** people not included in the policy.</span></span>  <br/> <span data-ttu-id="6abcb-199">在策略，选择**内部**查看发送通信**之间**标识的人员。</span><span class="sxs-lookup"><span data-stu-id="6abcb-199">Choose **Internal** to review communications sent **between** the people you identified in the policy.</span></span>  <br/> |
|<span data-ttu-id="6abcb-200">邮件包含以下任何词语</span><span class="sxs-lookup"><span data-stu-id="6abcb-200">Message contains any of these words</span></span>  <br/> <span data-ttu-id="6abcb-201">邮件包含无下列单词</span><span class="sxs-lookup"><span data-stu-id="6abcb-201">Message contains none of these words</span></span>  <br/> |<span data-ttu-id="6abcb-p119">若要将策略应用时包括或排除在邮件中特定词或短语，输入每个单词或短语单独占一行。将分别应用您输入的单词的每一行 （要应用于邮件的策略必须应用这些行中的只有一个）。关于输入词或短语的详细信息，请参阅下一节[匹配单词和短语针对电子邮件或附件](configure-supervision-policies.md#Matchwords)。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p119">To apply the policy when certain words or phrases are included or excluded in a message, enter each word or phrase on a separate line. Each line of words you enter will be applied separately (only one of these lines must apply for the policy to apply to the message). For more information about entering words or phrases, see the next section [Matching words and phrases to emails or attachments](configure-supervision-policies.md#Matchwords).  </span></span><br/> |
|<span data-ttu-id="6abcb-205">附件包含以下任何词语</span><span class="sxs-lookup"><span data-stu-id="6abcb-205">Attachment contains any of these words</span></span>  <br/> <span data-ttu-id="6abcb-206">附件包含无下列单词</span><span class="sxs-lookup"><span data-stu-id="6abcb-206">Attachment contains none of these words</span></span>  <br/> |<span data-ttu-id="6abcb-p120">若要将策略应用时包括或排除在邮件附件 （如 Word 文档） 中特定词或短语，输入每个单词或短语单独占一行。将分别应用您输入的单词的每一行 （只有一个行必须应用于附件的策略）。关于输入词或短语的详细信息，请参阅下一节[匹配单词和短语针对电子邮件或附件](configure-supervision-policies.md#Matchwords)。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p120">To apply the policy when certain words or phrases are included or excluded in a message attachment (such as a Word document), enter each word or phrase on a separate line. Each line of words you enter will be applied separately (only one line must apply for the policy to apply to the attachment). For more information about entering words or phrases, see the next section [Matching words and phrases to emails or attachments](configure-supervision-policies.md#Matchwords).  </span></span><br/> |
|<span data-ttu-id="6abcb-210">附件是任何这些文件类型</span><span class="sxs-lookup"><span data-stu-id="6abcb-210">Attachment is any of these file types</span></span>  <br/> <span data-ttu-id="6abcb-211">附件是无这些文件类型</span><span class="sxs-lookup"><span data-stu-id="6abcb-211">Attachment is none of these file types</span></span>  <br/> |<span data-ttu-id="6abcb-p121">监督 communications 包含或排除特定类型的附件，输入 （如.exe 或.pdf） 的文件扩展名。如果您想要包括或排除多个文件扩展名，输入这些在单独的行。只有一个附件扩展需要匹配要应用的策略。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p121">To supervise communications that include or exclude specific types of attachments, enter the file extensions (such as .exe or .pdf). If you want to include or exclude multiple file extensions, enter these on separate lines. Only one attachment extension needs to match for the policy to apply.</span></span>  <br/> |
|<span data-ttu-id="6abcb-215">邮件大小大于</span><span class="sxs-lookup"><span data-stu-id="6abcb-215">Message size is larger than</span></span>  <br/> <span data-ttu-id="6abcb-216">不能超过消息大小</span><span class="sxs-lookup"><span data-stu-id="6abcb-216">Message size is not larger than</span></span>  <br/> |<span data-ttu-id="6abcb-p122">若要查看基于特定大小的邮件，使用这些条件来指定受到审阅之前，可以是一条消息的最大值或最小大小。例如，如果您指定**邮件大小大于** \> **1.0 MB**，为 1.01 MB 和较大将的所有邮件采用审阅。您可以选择字节、 千字节、 兆字节或此条件千兆字节。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p122">To review messages based on a certain size, use these conditions to specify the maximum or minimum size a message can be before it is subject to review. For example, if you specify **Message size is larger than** \> **1.0 MB**, all messages that are 1.01 MB and larger will be subject to review. You can choose bytes, kilobytes, megabytes, or gigabytes for this condition.  </span></span><br/> |
|<span data-ttu-id="6abcb-220">附件大于</span><span class="sxs-lookup"><span data-stu-id="6abcb-220">Attachment is larger than</span></span>  <br/> <span data-ttu-id="6abcb-221">附件是不大于</span><span class="sxs-lookup"><span data-stu-id="6abcb-221">Attachment is not larger than</span></span>  <br/> |<span data-ttu-id="6abcb-p123">若要查看邮件及其附件的大小，指定附件的最大值或最小大小可在消息之前和及其附件将受到审阅。例如，如果您指定**附件大于** \> **2.0 MB**，所有邮件的附件 2.01 MB 和转移将采用审阅。您可以选择字节、 千字节、 兆字节或此条件千兆字节。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p123">To review messages based on the size of their attachments, specify the maximum or minimum size an attachment can be before the message and its attachments are subject to review. For example, if you specify **Attachment is larger than** \> **2.0 MB**, all messages with attachments 2.01 MB and over will be subject to review. You can choose bytes, kilobytes, megabytes, or gigabytes for this condition.  </span></span><br/> |
   
#### <a name="matching-words-and-phrases-to-emails-or-attachments"></a><span data-ttu-id="6abcb-225">将字词和短语与电子邮件或附件匹配</span><span class="sxs-lookup"><span data-stu-id="6abcb-225">Matching words and phrases to emails or attachments</span></span>
<span data-ttu-id="6abcb-226"><a name="Matchwords"> </a></span><span class="sxs-lookup"><span data-stu-id="6abcb-226"></span></span>

<span data-ttu-id="6abcb-p124">将分别应用您输入的单词的每一行 （只有一个行必须应用于电子邮件或附件策略条件）。例如，我们使用条件时，**邮件包含以下任何词语**，与关键字"四"和"内幕交易"置于单独的行。该策略将应用到包括"四"单词或短语"内幕交易"任何消息。只有一个这些单词或短语必须进行要应用此策略条件。在邮件或附件的单词必须完全匹配您的输入。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p124">Each line of words you enter will be applied separately (only one line must apply for the policy condition to apply to the email or attachment). For example, let's use the condition, **Message contains any of these words**, with the keywords "banker" and "insider trading" on separate lines. The policy will apply to any messages that includes the word "banker" or the phrase "insider trading". Only one of these words or phrases must occur for this policy condition to apply. Words in the message or attachment must exactly match what you enter.</span></span>
  
#### <a name="entering-multiple-conditions"></a><span data-ttu-id="6abcb-232">输入多个条件</span><span class="sxs-lookup"><span data-stu-id="6abcb-232">Entering multiple conditions</span></span>
<span data-ttu-id="6abcb-233"><a name="Matchwords"> </a></span><span class="sxs-lookup"><span data-stu-id="6abcb-233"></span></span>

<span data-ttu-id="6abcb-p125">如果您输入多个条件，Office 365 使用的所有条件一起确定何时将策略应用于通信项。当您设置了多个条件时，它们必须所有满足策略应用，除非您输入的例外。例如，假设您需要创建的策略，应该应用如果邮件包含单词"贸易"，并且大于 2 MB。不过，如果邮件还包含单词"contoso 财务已批准"，应该不会应用策略。因此，在这种情况下，三个条件将，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6abcb-p125">If you enter multiple conditions, Office 365 uses all the conditions together to determine when to apply the policy to communication items. When you set up multiple conditions, they must all be met for the policy to apply, unless you enter an exception. For example, let's say you need to create a policy that should apply if a message contains the word "trade", and is larger than 2MB. However, if the message also contains the words "Approved by Contoso financial", the policy should not apply. Thus, in this case, the three conditions would be as follows:</span></span> 
  
- <span data-ttu-id="6abcb-239">**邮件包含以下任何词语**，与"贸易"的关键字</span><span class="sxs-lookup"><span data-stu-id="6abcb-239">**Message contains any of these words**, with the keywords "trade"</span></span>
    
- <span data-ttu-id="6abcb-240">**邮件大小大于**，与值 2 MB</span><span class="sxs-lookup"><span data-stu-id="6abcb-240">**Message size is larger than**, with the value 2 MB</span></span>
    
- <span data-ttu-id="6abcb-241">**邮件包含无下列单词**，与关键字"Contoso 财务团队已批准"。</span><span class="sxs-lookup"><span data-stu-id="6abcb-241">**Message contains none of these words**, with the keywords "Approved by Contoso financial team".</span></span>
    
### <a name="specify-percentage-to-review"></a><span data-ttu-id="6abcb-242">指定要查看的百分比</span><span class="sxs-lookup"><span data-stu-id="6abcb-242">Specify percentage to review</span></span>
<span data-ttu-id="6abcb-243"><a name="CommsToReview"> </a></span><span class="sxs-lookup"><span data-stu-id="6abcb-243"></span></span>

<span data-ttu-id="6abcb-p126">如果您希望以减少要查看的内容量，指定百分比。从您选择的条件匹配的总，我们将随机选择的内容量。如果您希望的审阅者的所有项目，输入**100%**。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p126">If you want to reduce the amount of content to review, specify a percentage. We'll randomly select that amount of content from the total that matched the conditions you chose. If you want reviewers to review all items, enter **100%**.</span></span>
  
### <a name="choose-reviewers"></a><span data-ttu-id="6abcb-247">选择审阅者</span><span class="sxs-lookup"><span data-stu-id="6abcb-247">Choose reviewers</span></span>
<span data-ttu-id="6abcb-248"><a name="CommsToReview"> </a></span><span class="sxs-lookup"><span data-stu-id="6abcb-248"></span></span>

<span data-ttu-id="6abcb-p127">用户和组您选择将用于监督应用程序 Outlook web app 中检查通信返回此策略。您可以包括内部或外部的审阅者的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p127">The users and groups you choose will use the Supervision app in Outlook web app to examine the communications that are returned by this policy. You can include email addresses for internal or external reviewers.</span></span> 
  
### <a name="review-your-settings"></a><span data-ttu-id="6abcb-251">检查您的设置</span><span class="sxs-lookup"><span data-stu-id="6abcb-251">Review your settings</span></span>
<span data-ttu-id="6abcb-252"><a name="CommsToReview"> </a></span><span class="sxs-lookup"><span data-stu-id="6abcb-252"></span></span>

<span data-ttu-id="6abcb-p128">您已完成所有节的监督策略后，查看您的设置，然后单击**完成**以保存您的策略。可能需要几个小时要启动捕获通信的策略。监督到的共享文件夹的审阅者可以访问 Outlook web app 中提供了供审阅的所有通信。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p128">After you've completed all sections of the supervision policy, review your settings and then click **Finish** to save your policy. It might take a few hours for the policy to start capturing communications. Supervision delivers all communications for review into a shared folder that reviewers can access in Outlook web app.</span></span> 
  
## <a name="use-outlook-web-app-to-review-communications-identified-by-a-supervision-policy"></a><span data-ttu-id="6abcb-256">使用 Outlook web app 查看 communications 标识监督策略</span><span class="sxs-lookup"><span data-stu-id="6abcb-256">Use Outlook web app to review communications identified by a supervision policy</span></span>
<span data-ttu-id="6abcb-257"><a name="UseOutlook"> </a></span><span class="sxs-lookup"><span data-stu-id="6abcb-257"></span></span>

<span data-ttu-id="6abcb-p129">审阅者将使用监督外接程序 Outlook web app 查看 communications。外接程序是自动安装 Outlook web app 中的所有策略中指定的审阅者。对桌面的 Outlook 版本支持即将提供。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p129">Reviewers will use the Supervision add-in for Outlook web app to review communications. The add-in is installed automatically in Outlook web app for all reviewers you specified in the policy. Support for the desktop version of Outlook is coming soon.</span></span>
  
 <span data-ttu-id="6abcb-261">**查看 Outlook web app 中的通信**</span><span class="sxs-lookup"><span data-stu-id="6abcb-261">**Reviewing communications in Outlook web app**</span></span>
  
1. <span data-ttu-id="6abcb-262">在 Outlook web app 中，展开**监督-\<策略名称\>** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6abcb-262">In Outlook web app, expand the **Supervision - \<policy name\>** folder.</span></span> 
    
2. <span data-ttu-id="6abcb-263">在**\<策略名称\>** 子文件夹，审阅者会看到该监督策略被标识的所有通信。</span><span class="sxs-lookup"><span data-stu-id="6abcb-263">In the **\<policy name\>** subfolder, reviewers will see all the communications identified by that supervision policy.</span></span> 
    
    ![监督外接程序显示所选的监督策略子文件夹的 Outlook web app 中](media/eef329bf-2bd0-477e-a715-76ca19b3347f.jpg)
  
3. <span data-ttu-id="6abcb-265">打开一个项目以查看并单击**监督**加载项。</span><span class="sxs-lookup"><span data-stu-id="6abcb-265">Open an item to review and click the **Supervision** add-in.</span></span> 
    
4. <span data-ttu-id="6abcb-p130">使用外接程序对项目进行分类为**符合**、**不兼容**， **Questionable**或**已解决**。您已分类项目后，它将移到下的相应子文件夹**\<策略名称\>** 文件夹。</span><span class="sxs-lookup"><span data-stu-id="6abcb-p130">Use the add-in to classify the item as **Compliant**, **Non-Compliant**, **Questionable,** or **Resolved**. After you've classified an item, it will be moved to the corresponding subfolder under the **\<policy name\>** folder.</span></span> 
    

