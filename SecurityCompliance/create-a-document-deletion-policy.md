---
title: 创建文档删除策略
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- SPO160
ms.assetid: 41b2ed73-eb8d-4429-945e-a8197894585a
description: 为了体现合规性以及遵守法律或其他法规，组织通常必须在一定期限内保留文档。不过，如果文档的保留时间长于要求时间，则会给组织带来法律风险。
ms.openlocfilehash: 115e4d7df93d81e7ee5a860f20a00d9cb175f927
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013996"
---
# <a name="create-a-document-deletion-policy"></a><span data-ttu-id="4c0a8-104">创建文档删除策略</span><span class="sxs-lookup"><span data-stu-id="4c0a8-104">Create a document deletion policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c0a8-p102">下一步，我们建议您使用保留策略或创建安全标签&amp;而不是文档删除策略的合规性中心。文档删除策略将继续工作并排保留策略，但如果需要保留还是删除 Office 365 中的任意位置的内容，我们建议您使用保留策略。有关详细信息，请参阅[使用保留策略而不是这些功能](retention-policies.md#use-a-retention-policy-instead-of-these-features)。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p102">Moving forward, we recommend that you use a retention policy or labels created in the Security &amp; Compliance Center instead of a document deletion policy. Document deletion policies will continue to work side by side with retention policies, but if you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy. For more information, see [Use a retention policy instead of these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span></span> 
  
<span data-ttu-id="4c0a8-p103">为了体现合规性以及遵守法律或其他法规，组织通常必须在一定期限内保留文档。不过，如果文档的保留时间长于要求时间，则会给组织带来法律风险。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p103">Organizations are often required to retain documents for a certain period of time due to compliance, legal, or other regulations. However, retaining documents for longer than required can expose the organization to legal risk.</span></span>
  
<span data-ttu-id="4c0a8-110">使用文档删除策略，您可以主动减少风险删除在特定的一段时间后的网站中的文档 — 例如，删除文档用户的 onedrive for Business 站点五年后创建文档。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-110">With a document deletion policy, you can proactively reduce risk by deleting documents in a site after a specific period of time—for example, you can delete documents in users' OneDrive for Business sites five years after the documents were created.</span></span> 
  
<span data-ttu-id="4c0a8-p104">创建文档删除策略后，您便可以将它分配到网站集模板，这样便可以将它应用于使用此模板创建的所有网站集。您还可以将策略分配到特定的网站集，这样会覆盖可能已分配到该网站集模板的任何策略。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p104">After you create a document deletion policy, you can assign it to a site collection template, so that the policy is available to all site collections created from that template. You can also assign a policy to a specific a site collection, which overrides any policies that may have been assigned to the template for that site collection.</span></span>
  
![文档删除策略中心首页](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="policy-templates"></a><span data-ttu-id="4c0a8-114">策略模板</span><span class="sxs-lookup"><span data-stu-id="4c0a8-114">Policy templates</span></span>

<span data-ttu-id="4c0a8-p105">您可以从头开始创建文档删除策略，也可以使用示例策略之一。合规性策略中心中包括了您可以原样使用的示例策略，您还可以将其作为起点，然后进行重命名或修改。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p105">You can create a document deletion policy from scratch, or you can use one of the sample policies. The Compliance Policy Center includes sample policies that you can use as is, or you can use them as a starting point and then rename or modify them.</span></span>
  
![示例文档删除策略](media/IP-Sample-deletion-policies.png)
  
## <a name="examples-of-how-to-use-document-deletion-policies"></a><span data-ttu-id="4c0a8-118">示例</span><span class="sxs-lookup"><span data-stu-id="4c0a8-118">Examples of how to use document deletion policies</span></span>

<span data-ttu-id="4c0a8-p106">网站集或网站集模板可以有一个更多的策略分配给它，并且这些策略可以有一个或多个规则。但是，可以处于活动状态的每个网站，只能有一个策略，并可以随时在网站库处于活动状态的只有一个删除规则。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p106">A site collection or a site collection template can have one more policies assigned to it, and each of those policies can have one or more rules. However, there can be only one policy that's active per site, and there can be only one deletion rule that's active at any time for the libraries within the site.</span></span>
  
![显示策略之间关系的图表](media/IP-Two-policies-four-rules.png)
  
<span data-ttu-id="4c0a8-122">此外，您还可以选择一个策略作为强制策略或默认策略，并选择一个删除规则作为默认规则：</span><span class="sxs-lookup"><span data-stu-id="4c0a8-122">In addition, you can select a policy as mandatory or default, and you can select a deletion rule as a default rule:</span></span> 
  
- <span data-ttu-id="4c0a8-p107">**强制性策略**当某个策略标记为必需时，只能有一个策略可分配给网站集或模板。策略必须标记为默认值，并将应用于所有网站。网站所有者无法选择退出策略。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p107">**Mandatory policy**When a policy is marked as mandatory, only one policy can be assigned to the site collection or template. The policy must be marked as default and will be applied to all sites. Site owners cannot opt out of the policy.</span></span>
    
- <span data-ttu-id="4c0a8-126">**默认策略**为默认设置策略后，策略是自动激活所有站点中分配给与需站点所有者执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-126">**Default policy**When a policy is set as default, the policy is automatically active in all sites that it's assigned to with no action required by site owner.</span></span>
    
- <span data-ttu-id="4c0a8-127">**默认规则**当某个删除规则设置为默认值时，它会自动应用到使用策略的站点中的所有库。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-127">**Default rule**When a deletion rule is set as default, it is automatically applied to all libraries in the sites that use the policy.</span></span>
    
<span data-ttu-id="4c0a8-128">下面的示例介绍了可能需要使用强制策略或默认策略和规则的情况。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-128">The following examples explain when you might want to use a mandatory policy or default policies and rules.</span></span>
  
### <a name="example-1-apply-a-single-policy-with-a-single-rule-to-a-site-collection-template"></a><span data-ttu-id="4c0a8-129">示例 1：将一个包含单一规则的策略应用于网站集模板</span><span class="sxs-lookup"><span data-stu-id="4c0a8-129">Example 1: Apply a single policy with a single rule to a site collection template</span></span>

<span data-ttu-id="4c0a8-p108">您不妨将文档删除策略强制应用于广泛存在的未结构化内容，如所有 OneDrive for Business 站点或所有团队网站。如果您要确保在使用网站集模板创建的所有站点上只有一个文档删除策略处于活动状态，则可以：</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p108">You may want to enforce a document deletion policy across a broad range of unstructured content, such as all OneDrive for Business sites or all team sites. If you want to ensure that a single document deletion policy is active in all sites created from a site collection template, you can:</span></span>
  
1. <span data-ttu-id="4c0a8-132">创建一个包含单一默认删除规则的策略。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-132">Create a single policy with a single default deletion rule.</span></span>
    
2. <span data-ttu-id="4c0a8-133">将此策略设置为强制策略和默认策略。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-133">Set the policy as mandatory and default.</span></span>
    
3. <span data-ttu-id="4c0a8-134">将此策略分配到网站集模板。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-134">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="4c0a8-p109">在本示例中，默认删除规则会应用于使用此模板创建的所有网站集中的全部库，且站点所有者无法选择取消应用该策略。这是广泛、严格地强制应用文档删除策略的最简单方法。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p109">In this example, the default deletion rule will be applied to all libraries in all site collections created from the template, and site owners cannot opt out of the policy. This is the simplest way to broadly and rigidly enforce a document deletion policy.</span></span>
  
![显示单个强制策略的图表](media/IP-Example-1-doc-deletion-policies.png)
  
### <a name="example-2-apply-a-single-policy-with-several-rules-to-a-site-collection-template"></a><span data-ttu-id="4c0a8-138">示例 2： 将一个包含多个规则的策略应用于网站集模板</span><span class="sxs-lookup"><span data-stu-id="4c0a8-138">Example 2: Apply a single policy with several rules to a site collection template</span></span>

<span data-ttu-id="4c0a8-p110">由于站点所有者通常最清楚他们的站点包含何种类型的内容，因此您可以选择让站点所有者来选择最适用于其站点的删除规则。您还不妨允许站点所有者取消应用整个策略。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p110">Site owners often know best what type of content their site contains, so you may choose to allow site owners to select the deletion rule that best applies to their site. You may also want to allow site owners to opt out of a policy entirely.</span></span>
  
<span data-ttu-id="4c0a8-p111">与此同时，您仍可以集中创建和管理策略。您还可以选择一个默认策略和规则，这样在站点所有者选择其他策略或选择取消应用策略之前，此策略会一直有效。如果您希望站点所有者能够这样灵活操作，则可以：</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p111">At the same time, you can still centrally create and manage the policies. You can also select one policy and rule as the default, so that a policy is always in effect until the site owner chooses a different one or opts out. If you want to provide such flexibility to site owners, you can:</span></span>
  
1. <span data-ttu-id="4c0a8-143">创建一个包含多个删除规则的策略，并将其中一个规则设置为默认规则。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-143">Create a single policy with several deletion rules, and set one rule as the default.</span></span>
    
2. <span data-ttu-id="4c0a8-144">将此策略设置为默认策略。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-144">Set the policy as the default policy.</span></span>
    
3. <span data-ttu-id="4c0a8-145">将此策略分配到网站集模板。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-145">Assign the policy to a site collection template.</span></span>
    
<span data-ttu-id="4c0a8-146">站点所有者可以从备用删除规则中选择一个、选择取消应用此策略，也可以不执行任何操作而采用默认策略和规则。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-146">Site owners can select one of the alternate deletion rules, opt out of the policy, or do nothing and be subject to the default policy and rule.</span></span>
  
![显示具有多个规则的单个策略的图表](media/IP-Example-2-doc-deletion-policies.png)
  
### <a name="example-3-apply-several-policies-with-one-or-more-rules-to-a-site-collection"></a><span data-ttu-id="4c0a8-148">示例 3：将多个包含一个或多个规则的策略应用于网站集</span><span class="sxs-lookup"><span data-stu-id="4c0a8-148">Example 3: Apply several policies with one or more rules to a site collection</span></span>

<span data-ttu-id="4c0a8-p112">本示例为站点所有者带来了最大灵活性，因为他们可以从多个策略中进行选择，而且在选择策略后通常还能从多个规则中进行选择。您可以设置一个默认策略和规则，这样在站点所有者选择其他策略或选择取消应用策略之前，此策略会一直有效。请注意，如果您没有设置默认的策略和规则，则在站点所有者选择并应用策略和规则之前，站点中的文档库没有活动的策略和规则。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p112">This example provides the maximum flexibility to site owners because they can choose from several policies, and after selecting a policy they can often choose from several rules. One policy and rule are set as default, so that a policy is always in effect until the site owner chooses a different one or opts out. Note that if you do not set a policy and rule as the default, then no policies or rules will be active for the document libraries in the site until the site owner takes action to select and apply them.</span></span>
  
<span data-ttu-id="4c0a8-p113">与上述两个示例不同，此类策略是分配到特定的网站集，而不是网站集模板。也就是说，可以为特定网站集中的内容定制更具体的策略。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p113">Unlike the previous two examples, these policies are assigned to a specific site collection — not the site collection template. This means the policies can be more specifically tailored for the content in a specific site collection.</span></span>
  
<span data-ttu-id="4c0a8-p114">策略和规则具有继承性。站点所有者可以为他们的站点选择一个策略和规则，这样所有子站点都能够从父站点继承此策略。不过，子站点的所有者可以通过选择其他策略和规则来中断继承，这样会在继承再次中断之前将此策略和规则应用于所有子站点。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p114">Policies and rules are inherited. Site owners can select a policy and rule for their site, and all subsites inherit the policy from the parent. However, an owner of a subsite can break inheritance by selecting a different policy and rule, which in turn applies to all subsites until inheritance is broken again.</span></span>
  
<span data-ttu-id="4c0a8-156">若要设置此方案，您可以：</span><span class="sxs-lookup"><span data-stu-id="4c0a8-156">To set up this scenario, you can:</span></span>
  
1. <span data-ttu-id="4c0a8-157">创建多个策略，每个策略都包含一个或多个规则。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-157">Create several policies that each contains one or more rules.</span></span>
    
2. <span data-ttu-id="4c0a8-158">设置默认的策略和规则。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-158">Set a policy and rule as the default.</span></span>
    
3. <span data-ttu-id="4c0a8-159">将这些策略分配到特定的网站集。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-159">Assign the policies to a specific site collection.</span></span>
    
<span data-ttu-id="4c0a8-160">此外，还可以为特定的网站集定制这些策略和规则，在这种情况下，站点所有者可以通过选择最适用于其站点的策略和规则来中断继承。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-160">In addition, the policies and rules are tailored to a specific site collection, where site owners can break inheritance by selecting the policy and rule that best applies to their site.</span></span>
  
![显示多个策略和规则的图表](media/IP-Example-3-doc-deletion-policies.png)
  
## <a name="create-a-document-deletion-policy"></a><span data-ttu-id="4c0a8-162">创建文档删除策略</span><span class="sxs-lookup"><span data-stu-id="4c0a8-162">Create a document deletion policy</span></span>

1. <span data-ttu-id="4c0a8-p115">在 Office 365Security&amp;合规性中心中，导航到**数据管理** \> **保留**。下**删除**，请单击**管理 SharePoint Online 和 OneDrive for Business 的文档删除策略**。在新浏览器选项卡中打开文档删除策略中心。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p115">In the Office 365Security &amp; Compliance Center, navigate to **Data management** \> **Retention**. Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**. The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
    <span data-ttu-id="4c0a8-p116">首次从安全导航&amp;合规性中心到文档删除策略中心，为您自动创建的策略中心。此外，您可以手动创建策略中心通过[创建网站集](http://go.microsoft.com/fwlink/p/?LinkID=404342)，并在**企业**选项卡上选择**合规性策略中心**。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p116">The first time you navigate from the Security &amp; Compliance Center to the Document Deletion Policy Center, the policy center is automatically created for you. Alternatively, you can manually create the policy center by [creating the site collection](http://go.microsoft.com/fwlink/p/?LinkID=404342) and choosing **Compliance Policy Center** on the **Enterprise** tab.</span></span> 
    
2. <span data-ttu-id="4c0a8-168">选择**删除策略**。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-168">Choose **Deletion Policies**.</span></span>
    
    ![删除策略选项](media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="4c0a8-170">选择**新项**。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-170">Choose **new item**.</span></span>
    
4. <span data-ttu-id="4c0a8-p117">输入策略名称和说明。由于站点所有者可能会根据此名称和说明来为其站点选择策略，因此请添加足够多的信息，以便站点所有者能够选择正确的策略。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p117">Enter a policy name and description. Site owners may be selecting a policy for their site based on this name and description, so include enough information for them to choose the correct policy.</span></span>
    
5. <span data-ttu-id="4c0a8-173">若要创建规则，选择**新建**。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-173">To create a rule, choose **New**.</span></span>
    
6. <span data-ttu-id="4c0a8-174">输入名称，然后选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="4c0a8-174">Enter a name and choose the following options:</span></span>
    
  - <span data-ttu-id="4c0a8-p118">选择是否规则将永久删除文档或将其删除到回收站的时间。The Recycle Bin 提供第二阶段 safety net 之前从网站中永久删除项目。有关回收站的详细信息，请参阅[清空回收站或还原文件](http://go.microsoft.com/fwlink/p/?LinkID=404348)。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p118">Choose whether the rule will permanently delete documents or delete them to the Recycle Bin. The Recycle Bin provides a second-stage safety net before an item is permanently deleted from a site. For more information about the Recycle Bin, see [Empty the Recycle Bin or restore your files](http://go.microsoft.com/fwlink/p/?LinkID=404348).</span></span>
    
  - <span data-ttu-id="4c0a8-178">选择删除日期是从文档的创建日期还是最后一次修改日期开始计算。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-178">Choose whether the deletion date is calculated from the date when a document was created or last modified.</span></span>
    
  - <span data-ttu-id="4c0a8-179">输入在删除文档之前保留的天数、月数或年数。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-179">Enter a number of days, months, or years as the time period after which a document will be deleted.</span></span>
    
  - <span data-ttu-id="4c0a8-p119">选择是否将此规则设置为默认规则。系统自动将您创建的第一个规则设置为默认规则。默认规则会自动应用于使用此策略的站点中的所有库。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p119">Choose whether the rule is a default rule. The first rule that you create is automatically set as the default rule. A default rule is automatically applied to all libraries in the sites that use the policy.</span></span>
    
![新建删除规则页](media/IP-New-deletion-rule.png)
  
7. <span data-ttu-id="4c0a8-184">单击“保存”****。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-184">Click **Save**.</span></span>
    
8. <span data-ttu-id="4c0a8-p120">如果您希望站点所有者能够选择不同的规则应用于其站点，请创建其他规则。如果站点所有者没有执行任何操作，则系统会应用默认规则（如有）。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p120">Create additional rules if you want site owners to be able to choose different rules to apply to their site. The default rule, if any, will be applied if the site owner takes no action.</span></span>
    
9. <span data-ttu-id="4c0a8-187">若要从策略中删除某个规则，选择该规则，单击**删除**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-187">To remove a rule from a policy, select the rule, click **Delete**, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4c0a8-188">如果删除规则，并且策略不包含默认规则，则没有规则将在该策略 — 换句话说，将删除任何文档。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-188">If you delete a rule, and the policy does not contain a default rule, then no rule will be in effect for that policy—in other words, no documents will be deleted.</span></span> 
  
![确认从策略消息中删除规则](media/IP-Remove-rule-from-policy-message.png)
  
## <a name="assign-the-document-deletion-policy-to-a-site-collection-template"></a><span data-ttu-id="4c0a8-190">将文档删除策略分配到网站集模板</span><span class="sxs-lookup"><span data-stu-id="4c0a8-190">Assign the document deletion policy to a site collection template</span></span>

<span data-ttu-id="4c0a8-191">通过将策略分配到网站集模板，您可以将此策略应用于使用该模板创建的所有网站集，包括现有网站集和今后创建的网站集。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-191">By assigning a policy to a site collection template, you make the policy available to all site collections created from that template, including both existing site collections and site collections created in the future.</span></span>
  
<span data-ttu-id="4c0a8-p121">务必要了解的指定文档的时间段删除策略意味着时间自文档已创建或修改，不自以来的时间已分配策略。当第一次分配策略时，计算网站中的所有文档，并且如果他们满足的条件，它们将删除。这适用于所有现有文档，不仅是新创建从该策略指定的文档。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p121">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned. When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted. This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="4c0a8-p122">安全中&amp;合规性中心中，导航到**数据管理** \> **保留**。下**删除**，请单击**管理 SharePoint Online 和 OneDrive for Business 的文档删除策略**。在新浏览器选项卡中打开文档删除策略中心。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p122">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**. Under **Delete**, click **Manage document deletion policies for SharePoint Online and OneDrive for Business**. The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="4c0a8-198">选择**模板的策略分配**。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-198">Choose **Policy Assignments for Templates**.</span></span>
    
    ![模板的策略分配选项](media/IP-Policy-Assignments-for-Templates-option.png)
  
3. <span data-ttu-id="4c0a8-200">选择**新项**。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-200">Choose **new item**.</span></span>
    
4. <span data-ttu-id="4c0a8-201">执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="4c0a8-201">Do one of the following:</span></span>
    
  - <span data-ttu-id="4c0a8-202">若要将策略分配到网站集模板，例如工作组网站模板，选择**分配到网站集模板**，然后选择网站集模板。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-202">To assign the policy to a site collection template such as the Team Site template, select **Assign to site collection template**, and then select the site collection template.</span></span>
    
  - <span data-ttu-id="4c0a8-203">若要将策略分配给用户的 Onedrive for Business 中，选择**分配到 OneDrive for Business 模板**，请突出显示如下。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-203">To assign the policy to users' One Drive for Business, choose **Assign to OneDrive for Business Template**, highlighted below.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4c0a8-204">如果您将策略分配到网站集模板，则此策略可应用于使用该模板创建的现有网站集和今后创建的网站集。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-204">When you assign a policy to a site collection template, that policy will be available both to existing site collections created from that template and to site collections created in the future.</span></span> 
  
![显示 OneDrive 选项的“选择模板”页面](media/IP-Choose-a-template.png)
  
5. <span data-ttu-id="4c0a8-206">单击“保存”****。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-206">Click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4c0a8-p123">每个模板都可以具有只有一组策略分配给它。如果您看到错误消息此模板已为其分配的策略，选择**取消**\>的左侧导航中的**分配到网站集**\>选择网站集以查看和管理组策略已分配。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p123">Each template can have only one set of policies assigned to it. If you see an error saying that this template already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** in the left navigation \> select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
6. <span data-ttu-id="4c0a8-p124">选择**管理分配策略**中，选择要分配，然后选择一个策略是否是默认策略的策略。当设置默认策略时，自动分配给策略的所有网站都不拥有需站点所有者执行任何操作活动的策略。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p124">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy. When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![“添加和管理策略”页面](media/IP-Add-and-manage-policies-page.png)
  
7. <span data-ttu-id="4c0a8-212">单击“保存”****。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-212">Click **Save**.</span></span>
    
8. <span data-ttu-id="4c0a8-p125">如果您想要但不允许网站所有者，若要选择退出强制所有网站上的策略，选择**为强制标记策略**。当您进行强制策略时，只的单个策略可分配给网站集模板。策略还必须标记为默认值。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p125">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection template. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="4c0a8-216">如果此选项灰显，选择**管理分配策略**，并确保至少一个策略是分配和设为默认值。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-216">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
9. <span data-ttu-id="4c0a8-217">单击“保存”****。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-217">Click **Save**.</span></span>
    
## <a name="assign-the-document-deletion-policy-to-a-site-collection"></a><span data-ttu-id="4c0a8-218">将文档删除策略分配到网站集</span><span class="sxs-lookup"><span data-stu-id="4c0a8-218">Assign the document deletion policy to a site collection</span></span>

<span data-ttu-id="4c0a8-p126">通过将策略分配到特定的网站集，您只能将此策略应用于相应的特定网站集。也就是说，您可以定制更贴近网站集中内容的策略。此外，分配到特定网站集的策略会覆盖分配到该网站集模板的所有策略。例如，分配到销售部门网站集（使用团队网站模板创建）的策略将覆盖分配到团队网站模板的所有策略。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p126">By assigning a policy to a specific site collection, you make the policy available only to that specific site collection. This means you can tailor policies more closely to the content in the site collection. Also, policies assigned to a specific site collection will override any policies that are assigned to the template for that site collection. For example, a policy assigned to the Sales Department site collection (created from the Team Site template) will override any policies assigned to the Team Site template.</span></span>
  
<span data-ttu-id="4c0a8-p127">务必要了解的指定文档的时间段删除策略意味着时间自文档已创建或修改，不自以来的时间已分配策略。当第一次分配策略时，计算网站中的所有文档，并且如果他们满足的条件，它们将删除。这适用于所有现有文档，不仅是新创建从该策略指定的文档。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p127">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned. When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted. This applies to all existing documents, not just new documents created since the policy was assigned.</span></span>
  
1. <span data-ttu-id="4c0a8-p128">安全中&amp;合规性中心中，导航到**数据管理** \> **保留**。在**删除**下选择**管理 SharePoint Online 和 OneDrive for Business 的文档删除策略**。在新浏览器选项卡中打开文档删除策略中心。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p128">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**. Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**. The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="4c0a8-229">选择**网站集的策略分配**。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-229">Choose **Policy Assignments for Site Collections**.</span></span>
    
    ![网站集的策略分配选项](media/IP-Policy-Assignments-for-Site-Collections-option.png)
  
3. <span data-ttu-id="4c0a8-231">选择**新项**。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-231">Choose **new item**.</span></span>
    
4. <span data-ttu-id="4c0a8-p129">选择**选择网站集**。按名称或 URL 的网站集搜索，选择网站集，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p129">Choose **Choose a site collection**. Search for the site collection by name or URL, select the site collection and click **Save**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4c0a8-p130">每个网站集可以具有只有一组策略分配给它。如果您看到错误消息此网站集已具有分配给它的策略，选择**取消** \> **将分配到网站集**和选择网站集来查看和管理组已分配的策略。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p130">Each site collection can have only one set of policies assigned to it. If you see an error saying that this site collection already has policies assigned to it, choose **Cancel** \> **Assign to Site Collection** and select a site collection to view and manage the set of policies that are already assigned.</span></span> 
  
![“选择网站集”页面](media/IP-Choose-a-site-collection-page.png)
  
5. <span data-ttu-id="4c0a8-p131">选择**管理分配策略**中，选择要分配，然后选择一个策略是否是默认策略的策略。当设置默认策略时，自动分配给策略的所有网站都不拥有需站点所有者执行任何操作活动的策略。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p131">Choose **Manage Assigned Policies**, select the policies that you want to assign, and then choose whether one policy is the default policy. When you set a default policy, all sites assigned to the policy automatically have the policy active with no action required by site owner.</span></span>
    
    ![“添加和管理策略”页面](media/IP-Add-and-manage-policies-page.png)
  
6. <span data-ttu-id="4c0a8-240">单击“保存”****。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-240">Click **Save**.</span></span>
    
7. <span data-ttu-id="4c0a8-p132">如果您想要但不允许网站所有者，若要选择退出强制所有网站上的策略，选择**为强制标记策略**。当您进行强制策略时，只的单个策略可分配给网站集。策略还必须标记为默认值。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p132">If you want to enforce the policy on all sites without allowing site owners to opt out, choose **Mark Policy as Mandatory**. When you make a policy mandatory, only that single policy can be assigned to the site collection. The policy must also be marked as default.</span></span>
    
    <span data-ttu-id="4c0a8-244">如果此选项灰显，选择**管理分配策略**，并确保至少一个策略是分配和设为默认值。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-244">If this option is grayed out, choose **Manage Assigned Policies** and make sure that at least one policy is assigned and set as default.</span></span> 
    
8. <span data-ttu-id="4c0a8-245">单击“保存”****。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-245">Click **Save**.</span></span>
    
## <a name="delete-a-policy-assignment"></a><span data-ttu-id="4c0a8-246">删除策略分配关系</span><span class="sxs-lookup"><span data-stu-id="4c0a8-246">Delete a policy assignment</span></span>

<span data-ttu-id="4c0a8-247">如果您删除策略分配关系，则已分配的策略将不再应用于网站集或网站集模板中的任何站点。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-247">When you delete an assignment, the assigned policies will no longer apply to any sites in the site collection or site collection template.</span></span>
  
1. <span data-ttu-id="4c0a8-p133">安全中&amp;合规性中心中，导航到**数据管理** \> **保留**。在**删除**下选择**管理 SharePoint Online 和 OneDrive for Business 的文档删除策略**。在新浏览器选项卡中打开文档删除策略中心。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p133">In the Security &amp; Compliance Center, navigate to **Data management** \> **Retention**. Under **Delete**, choose **Manage document deletion policies for SharePoint Online and OneDrive for Business**. The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="4c0a8-251">选择**模板的策略分配**或**网站集的策略分配**。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-251">Choose either **Policy Assignments for Templates** or **Policy Assignments for Site Collections**.</span></span>
    
3. <span data-ttu-id="4c0a8-252">选择分配项目，然后单击**删除项目**。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-252">Select the assignment item and click **Delete Item**.</span></span>
    
    ![策略分配的“删除项目”命令](media/IP-Delete-policy-assignment.png)
  
## <a name="delete-a-policy"></a><span data-ttu-id="4c0a8-254">删除策略</span><span class="sxs-lookup"><span data-stu-id="4c0a8-254">Delete a policy</span></span>

<span data-ttu-id="4c0a8-p134">不能删除正在使用的策略。您可以删除策略之前，首先需要删除所有分配给网站集和网站集模板包含该策略，请参阅上一节。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p134">You can't delete a policy that's in use. Before you can delete a policy, you first need to delete all assignments to site collections and site collection templates that include that policy—see the previous section.</span></span>
  
1. <span data-ttu-id="4c0a8-p135">安全中&amp;合规性中心\>选择**数据管理**\>左侧导航窗格中的**保留** \> **删除**下\>**管理文档删除策略的 SharePoint Online 和 OneDrive为业务**。在新浏览器选项卡中打开文档删除策略中心。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p135">In the Security &amp; Compliance Center \> choose **Data management** \> **Retention** in the left navigation \> under **Delete** \> **Manage document deletion policies for SharePoint Online and OneDrive for Business**. The Document Deletion Policy Center opens in a new browser tab.</span></span>
    
2. <span data-ttu-id="4c0a8-259">选择 * * 删除策略 * *。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-259">Choose ** Deletion Policies **.</span></span>
    
    ![删除策略选项](media/IP-Deletion-Policies-option.png)
  
3. <span data-ttu-id="4c0a8-261">选择策略。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-261">Select the policy.</span></span>
    
4. <span data-ttu-id="4c0a8-262">在功能区\>**项**选项卡\>**删除策略**。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-262">On the Ribbon \> **Items** tab \> **Remove Policy**.</span></span>
    
    ![功能区上的“删除策略”按钮](media/IP-Remove-Policy-button-on-Ribbon.png)
  
5. <span data-ttu-id="4c0a8-p136">使用策略时，系统将要求您是否要从所有使用位置的网站集删除策略。如果您确定，选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="4c0a8-p136">If the policy is in use, you'll be asked if you want to remove the policy from all of the site collections where it's being used. If you're sure, choose **OK**.</span></span>
    
    ![删除策略确认消息](media/IP-Delete-policy-confirmation.png)
  
## <a name="see-also"></a><span data-ttu-id="4c0a8-267">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c0a8-267">See also</span></span>

[<span data-ttu-id="4c0a8-268">文档删除策略概述</span><span class="sxs-lookup"><span data-stu-id="4c0a8-268">Overview of document deletion policies</span></span>](document-deletion-policies.md)

[<span data-ttu-id="4c0a8-269">应用或删除网站的文件删除策略</span><span class="sxs-lookup"><span data-stu-id="4c0a8-269">Apply or remove a document deletion policy for a site</span></span>](apply-or-remove-a-document-deletion-policy-for-a-site.md)
 

