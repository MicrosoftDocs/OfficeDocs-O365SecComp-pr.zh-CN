---
title: 文档删除策略概述
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 55e8d858-f278-482b-a198-2e62d6a2e6e5
description: 由于合规性、法律或其他业务要求, 你的组织可能需要将文档保留一段时间。 但是, 如果您的组织保留的文档比所需时间长, 则会带来不必要的法律风险。 使用文档删除策略, 您可以通过在特定时间段后删除网站中的文档来主动降低风险, 例如, 在创建文档五年后, 可以在用户的 OneDrive for Business 网站中删除文档。
ms.openlocfilehash: 59bc100a19f3597aa1bf16506bf6c7049a35af3b
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34154854"
---
# <a name="overview-of-document-deletion-policies"></a><span data-ttu-id="936ec-105">文档删除策略概述</span><span class="sxs-lookup"><span data-stu-id="936ec-105">Overview of document deletion policies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="936ec-106">向前移动时, 建议使用保留策略或在 Microsoft 365 合规性中心、Microsoft 365 安全中心或 Office 365 安全&amp;合规中心 (而不是文档删除策略) 中创建的标签。</span><span class="sxs-lookup"><span data-stu-id="936ec-106">Moving forward, we recommend that you use a retention policy or labels created in the Microsoft 365 compliance center, Microsoft 365 security center, or Office 365 Security &amp; Compliance Center instead of a document deletion policy.</span></span> <span data-ttu-id="936ec-107">文档删除策略将继续与保留策略一起工作, 但如果您需要保留或删除 Office 365 中任何位置的内容, 我们建议使用保留策略。</span><span class="sxs-lookup"><span data-stu-id="936ec-107">Document deletion policies will continue to work side by side with retention policies, but if you need to retain or delete content anywhere in Office 365, we recommend that you use a retention policy.</span></span> <span data-ttu-id="936ec-108">有关详细信息, 请参阅[使用保留策略而不是这些功能](retention-policies.md#use-a-retention-policy-instead-of-these-features)。</span><span class="sxs-lookup"><span data-stu-id="936ec-108">For more information, see [Use a retention policy instead of these features](retention-policies.md#use-a-retention-policy-instead-of-these-features).</span></span>
  
<span data-ttu-id="936ec-109">由于合规性、法律或其他业务要求, 你的组织可能需要将文档保留一段时间。</span><span class="sxs-lookup"><span data-stu-id="936ec-109">Your organization may be required to retain documents for a period of time because of compliance, legal, or other business requirements.</span></span> <span data-ttu-id="936ec-110">但是, 如果您的组织保留的文档比所需时间长, 则会带来不必要的法律风险。</span><span class="sxs-lookup"><span data-stu-id="936ec-110">However, if your organization keeps documents longer than required, you create unnecessary legal risk.</span></span> <span data-ttu-id="936ec-111">使用文档删除策略, 您可以通过在特定时间段后删除网站中的文档来主动降低风险, 例如, 在创建文档五年后, 可以在用户的 OneDrive for Business 网站中删除文档。</span><span class="sxs-lookup"><span data-stu-id="936ec-111">With a document deletion policy, you can proactively reduce risk by deleting documents in a site after a specific period of time—for example, you can delete documents in users' OneDrive for Business sites five years after the documents were created.</span></span>
  
<span data-ttu-id="936ec-112">文档删除策略功能强大且灵活, 例如, 您可以:</span><span class="sxs-lookup"><span data-stu-id="936ec-112">Document deletion policies are powerful yet flexible—for example, you can:</span></span>
  
- <span data-ttu-id="936ec-p104">允许网站所有者从您集中创建和管理的策略中进行选择。您还可以在网站所有者确定策略不适用于其内容的情况下，允许其选择完全退出。</span><span class="sxs-lookup"><span data-stu-id="936ec-p104">Allow site owners to choose from policies that you centrally create and manage. You can also allow site owners to opt out altogether if they decide a policy does not apply to their content.</span></span>
    
- <span data-ttu-id="936ec-115">针对网站集中的所有网站（如所有 OneDrive for Business 网站）强制执行一个强制性策略，或者甚至针对使用特定网站集模板（如团队网站模板）创建的所有网站集强制执行一个策略。</span><span class="sxs-lookup"><span data-stu-id="936ec-115">Enforce a single mandatory policy on all sites in a site collection, such as all OneDrive for Business sites, or even enforce a policy on all site collections created from a specific site collection template, such as the Team Site template.</span></span>
    
- <span data-ttu-id="936ec-116">提供具有默认规则的默认策略，该规则会自动应用，无需网站所有者执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="936ec-116">Provide a default policy with a default rule that will be automatically applied without any action required by site owners.</span></span>
    
- <span data-ttu-id="936ec-117">创建一个策略，其中包括可供网站所有者选择的几个删除规则。</span><span class="sxs-lookup"><span data-stu-id="936ec-117">Create a policy that includes several deletion rules that a site owner can choose from.</span></span>
    
<span data-ttu-id="936ec-118">您可以使用文档删除策略中心来创建和管理文档删除策略。</span><span class="sxs-lookup"><span data-stu-id="936ec-118">You create and manage document deletion policies by using the Document Deletion Policy Center.</span></span> <span data-ttu-id="936ec-119">或者, 您可以通过[创建网站集](https://go.microsoft.com/fwlink/p/?LinkID=404342)并在 "**企业**" 选项卡上选择 "**合规性策略中心**" 来手动创建策略中心。每个租户只能有一个文档删除策略中心。</span><span class="sxs-lookup"><span data-stu-id="936ec-119">Alternatively, you can create the policy center manually by [creating the site collection](https://go.microsoft.com/fwlink/p/?LinkID=404342) and choosing **Compliance Policy Center** on the **Enterprise** tab. Each tenant can have only one Document Deletion Policy Center.</span></span> 
  
![文档删除策略中心首页](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="when-to-use-document-deletion-policies"></a><span data-ttu-id="936ec-121">使用文件删除策略的情况</span><span class="sxs-lookup"><span data-stu-id="936ec-121">When to use document deletion policies</span></span>

<span data-ttu-id="936ec-122">除了文件删除策略，Office 365 针对网站内容提供以下保留策略：</span><span class="sxs-lookup"><span data-stu-id="936ec-122">In addition to document deletion policies, Office 365 provides these retention policies for site content:</span></span>
  
- [<span data-ttu-id="936ec-123">记录管理</span><span class="sxs-lookup"><span data-stu-id="936ec-123">Records management</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404250)
    
- [<span data-ttu-id="936ec-124">针对内容类型、列表和库的信息管理策略</span><span class="sxs-lookup"><span data-stu-id="936ec-124">Information management policies for content types, lists, and libraries</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404239)
    
- [<span data-ttu-id="936ec-125">网站策略</span><span class="sxs-lookup"><span data-stu-id="936ec-125">Site policies</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=404242)
    
<span data-ttu-id="936ec-p106">每种类型的策略都最适合特定类型的网站或数据。例如，您的组织可能拥有使用内容类型的高度结构化网站，如合同相关的金融网站或文章相关的知识库。在这种情况下，您可以使用内容类型策略。或者，您的组织可能需要保留法律文件，此时您可以使用内容类型和记录中心来实现文件计划。</span><span class="sxs-lookup"><span data-stu-id="936ec-p106">Each type of policy works best for a specific type of site or data. For example, your organization may have a highly structured site that uses content types, such as a financial site for contracts or a knowledge base for articles. In this case, you can use content type policies. Or your organization may need to retain legal documents, in which case you might use content types and a Records Center to implement a file plan.</span></span>
  
<span data-ttu-id="936ec-130">文档删除策略不会替换记录管理或信息管理策略, 这最适用于结构化数据和内容类型。</span><span class="sxs-lookup"><span data-stu-id="936ec-130">Document deletion policies don't replace records management or information management policies, which work best with structured data and content types.</span></span> <span data-ttu-id="936ec-131">相反，当您需要全面管理对非结构化数据（如 OneDrive for Business 网站或团队网站）的自动删除时，应使用文件删除策略。</span><span class="sxs-lookup"><span data-stu-id="936ec-131">Instead, you should use document deletion policies when you need to broadly manage the automatic deletion of unstructured data such as OneDrive for Business sites and team sites.</span></span>
  
![显示网站内容的保留选项的图表](media/IP-Retention-policies-for-site-content.png)
  
<span data-ttu-id="936ec-133">如果文件删除策略所应用的网站已使用内容类型策略或针对列表或库的信息管理策略，则这些策略会在文件删除策略生效时被忽略。</span><span class="sxs-lookup"><span data-stu-id="936ec-133">If you apply a document deletion policy to a site that already uses content type policies or information management policies for a list or library, those policies are ignored while the document deletion policy is in effect.</span></span> <span data-ttu-id="936ec-134">这表示您应该对网站进行规划，以仅使用针对结构化内容或非结构化内容的策略，而非同时使用。</span><span class="sxs-lookup"><span data-stu-id="936ec-134">This means you should plan for a site to use only policies meant for structured or unstructured content, not both.</span></span> <span data-ttu-id="936ec-135">有关文件删除策略如何覆盖其他策略的详细信息，请参阅[Apply or remove a document deletion policy for a site](apply-or-remove-a-document-deletion-policy-for-a-site.md)。</span><span class="sxs-lookup"><span data-stu-id="936ec-135">For more information on how document deletion policies override other policies, see [Apply or remove a document deletion policy for a site](apply-or-remove-a-document-deletion-policy-for-a-site.md).</span></span>
  
<span data-ttu-id="936ec-136">与其他策略不同，文件删除策略仅适用于文档库，而不适用于列表。</span><span class="sxs-lookup"><span data-stu-id="936ec-136">Unlike other policies, document deletion policies work only on document libraries, not lists.</span></span>
  
## <a name="deletion-policies-and-rules"></a><span data-ttu-id="936ec-137">删除策略和规则</span><span class="sxs-lookup"><span data-stu-id="936ec-137">Deletion policies and rules</span></span>

<span data-ttu-id="936ec-138">文件删除策略包含一个或多个删除规则，该规则指定：</span><span class="sxs-lookup"><span data-stu-id="936ec-138">A document deletion policy contains one or more delete rules that specify:</span></span>
  
- <span data-ttu-id="936ec-139">直至删除的时间段。</span><span class="sxs-lookup"><span data-stu-id="936ec-139">The time period until deletion.</span></span>
    
- <span data-ttu-id="936ec-140">是根据文件创建时间还是最后修改时间计算删除日期。</span><span class="sxs-lookup"><span data-stu-id="936ec-140">Whether to calculate the deletion date from the when the document was created or last modified.</span></span>
    
- <span data-ttu-id="936ec-141">是永久删除文件还是将其删除到回收站中。</span><span class="sxs-lookup"><span data-stu-id="936ec-141">Whether to delete the document permanently or to the Recycle Bin.</span></span>
    
<span data-ttu-id="936ec-142">如果一个策略包含多个规则，网站所有者可以选择最适合其内容的规则。</span><span class="sxs-lookup"><span data-stu-id="936ec-142">If a policy contains more than one rule, site owners can select the rule that best applies to their content.</span></span>
  
![新建删除规则页](media/IP-New-deletion-rule.png)
  
## <a name="policies-and-assignments"></a><span data-ttu-id="936ec-144">策略和分配</span><span class="sxs-lookup"><span data-stu-id="936ec-144">Policies and assignments</span></span>

<span data-ttu-id="936ec-145">创建文档删除策略后, 可以将其分配到网站集模板, 例如, 可以将策略分配到 OneDrive for business 模板, 以便它包含每个用户的 OneDrive 网站。</span><span class="sxs-lookup"><span data-stu-id="936ec-145">After you create a document deletion policy, you can assign it to a site collection template — for example, you can assign a policy to the OneDrive for Business template so that it includes every user's OneDrive site.</span></span> <span data-ttu-id="936ec-146">将策略分配到网站集模板时, 这会应用于已使用该模板创建的所有网站集, 以及以后使用该模板创建的任何网站集。</span><span class="sxs-lookup"><span data-stu-id="936ec-146">When you assign a policy to a site collection template, this applies to all site collections already created from that template, in addition to any site collections created from that template in the future.</span></span>
  
![显示 OneDrive 选项的“选择模板”页面](media/IP-Choose-a-template.png)
  
<span data-ttu-id="936ec-p110">您还可以向特定网站集分配策略，这将覆盖已分配给该网站集模板的所有策略。例如，您可以将策略分配给团队网站模板，但之后对使用该模板创建的特定网站集应用另一组策略，以覆盖之前的策略。</span><span class="sxs-lookup"><span data-stu-id="936ec-p110">You can also assign a policy to a specific site collection— doing so overrides any policies that have been assigned to that site collection template. For example, you may assign policies to the Team Site template, but then override them by applying a different set of policies to a specific site collection created from that template.</span></span>
  
### <a name="one-mandatory-policy-or-several-policies-to-choose-from"></a><span data-ttu-id="936ec-150">一个强制性策略或可供选择的多个策略</span><span class="sxs-lookup"><span data-stu-id="936ec-150">One mandatory policy or several policies to choose from</span></span>

<span data-ttu-id="936ec-p111">分配策略时，您可以选择使其成为强制性策略，从而只有该策略可供分配，并将应用于网站集中的所有网站。网站所有者不能选择退出强制性策略，这意味着在任何情况下，网站中的文件都必须遵从该删除策略。</span><span class="sxs-lookup"><span data-stu-id="936ec-p111">When you assign a policy, you can choose to make it mandatory, so that only this policy can be assigned and that it will be applied to all sites in the site collection. Site owners cannot opt out of a mandatory policy, which means documents in the site will be subject to the delete policy no matter what.</span></span>
  
<span data-ttu-id="936ec-p112">除了使单个策略成为强制性策略，您还可以向网站集分配多个策略，从而允许每个网站所有者选择要应用于其网站的策略，或者甚至可以选择完全退出。例如，您可以为一般业务文件创建一个策略，并为具有不同保留计划的财务文件创建另一个策略。网站所有者通常最了解自己的网站包含哪些内容，因此也最清楚要应用哪个文件删除策略。每个网站只能应用一个策略。</span><span class="sxs-lookup"><span data-stu-id="936ec-p112">Instead of making a single policy mandatory, you can also assign several policies to a site collection, which allows each site owner to choose which policy to apply to their site, or even to opt out altogether. For example, you can create one policy for general business documents and another policy for financial documents that have a different retention schedule. A site owner often knows best what content their site contains and therefore which document deletion policy to apply. Each site can have only one policy applied to it.</span></span>
  
### <a name="one-rule-or-several-rules-to-choose-from"></a><span data-ttu-id="936ec-157">一个规则或可供选择的多个规则</span><span class="sxs-lookup"><span data-stu-id="936ec-157">One rule or several rules to choose from</span></span>

<span data-ttu-id="936ec-158">反过来, 每个策略可以包含多个规则, 例如, 用于一般业务文档的删除策略可能有两个规则:</span><span class="sxs-lookup"><span data-stu-id="936ec-158">In turn, each policy can contain many rules—for example, a deletion policy for general business documents may have two rules:</span></span>
  
- <span data-ttu-id="936ec-159">不需要根据法律义务或持续业务需求保留保留的文档不应保留一年以上的创建。</span><span class="sxs-lookup"><span data-stu-id="936ec-159">Documents that don't need retention based on legal obligations or ongoing business need should not be retained for more than one year from creation.</span></span>
    
- <span data-ttu-id="936ec-160">对于有效的现行业务使用所必需的文档（需要超过一年时间），不应保留自创建日期起超过三年的时间。</span><span class="sxs-lookup"><span data-stu-id="936ec-160">Documents necessary for active, ongoing business use that are needed for more than one year, should not be retained for more than three years from creation.</span></span>
    
<span data-ttu-id="936ec-161">网站所有者可以确定其网站是否包含一般业务文件，选择该删除策略，然后从策略中选择适当的规则。</span><span class="sxs-lookup"><span data-stu-id="936ec-161">A site owner can determine that their site contains general business documents, select this deletion policy, and then select the appropriate rule from the policy.</span></span> <span data-ttu-id="936ec-162">您只能从当前应用于网站的策略 (而不是从任何策略) 中选择规则, 并且该规则将应用于网站中的所有文档库。</span><span class="sxs-lookup"><span data-stu-id="936ec-162">You can only select a rule from the policy that's currently applied to the site (not from any policy), and the rule applies to all document libraries in the site.</span></span>
  
## <a name="the-relationship-of-site-collections-policies-and-rules"></a><span data-ttu-id="936ec-163">网站集、策略和规则的关系</span><span class="sxs-lookup"><span data-stu-id="936ec-163">The relationship of site collections, policies, and rules</span></span>

<span data-ttu-id="936ec-164">基本关系如下：</span><span class="sxs-lookup"><span data-stu-id="936ec-164">The basic relationship is this:</span></span>
  
<span data-ttu-id="936ec-165">可对网站集或网站集模板分配一个或多个策略，其中每个策略可以有一个或多个规则。</span><span class="sxs-lookup"><span data-stu-id="936ec-165">A site collection or a site collection template can have one or more policies assigned to it, and each of those policies can have one or more rules.</span></span> <span data-ttu-id="936ec-166">但是, 每个站点只能有一个处于活动状态的策略, 并且网站中的库在任何时候都只能有一个活动的删除规则。</span><span class="sxs-lookup"><span data-stu-id="936ec-166">However, there can be only one policy that's active per site, and there can be only one deletion rule that's active at any time for the libraries within the site.</span></span>
  
![显示策略之间关系的图表](media/IP-Two-policies-four-rules.png)
  
## <a name="document-deletion-policies-are-inherited"></a><span data-ttu-id="936ec-168">文件删除策略具有继承性</span><span class="sxs-lookup"><span data-stu-id="936ec-168">Document deletion policies are inherited</span></span>

<span data-ttu-id="936ec-p115">与权限、导航及其他许多网站功能一样，文件删除策略具有继承性。网站所有者可以为其网站选择一个文件删除策略，所有子网站将从父网站继承该策略。子网站所有者可通过选择其他策略和规则组合来中断继承性，此时的策略会应用于所有子网站，直到继承性再次被中断。</span><span class="sxs-lookup"><span data-stu-id="936ec-p115">Like permissions, navigation, and many other site features, document deletion policies are inherited. A site owner can select a document deletion policy for their site, and all subsites inherit the policy from the parent. An owner of a subsite can break inheritance by selecting a different policy and rule combination, and that policy applies to all subsites until inheritance is broken again.</span></span>
  
## <a name="assigning-document-deletion-policies-for-the-first-time"></a><span data-ttu-id="936ec-172">首次分配文件删除策略</span><span class="sxs-lookup"><span data-stu-id="936ec-172">Assigning document deletion policies for the first time</span></span>

<span data-ttu-id="936ec-173">请务必了解为文档删除策略指定的时间段是指自创建或修改文档以来的时间, 而不是分配该策略以来的时间。</span><span class="sxs-lookup"><span data-stu-id="936ec-173">It's important to understand that the time period specified for a document deletion policy means the time since the document was created or modified, not the time since the policy was assigned.</span></span> <span data-ttu-id="936ec-174">例如，您可能创建一个文件删除策略，该策略将在文件创建两年后将其永久删除，然后将该策略分配给一个网站集模板，该模板在四五年前曾用于创建几个网站集。</span><span class="sxs-lookup"><span data-stu-id="936ec-174">For example, you might create a document deletion policy that permanently deletes documents two years after they were created, and then assign that policy to a site collection template from which several site collections were created four or five years ago.</span></span> <span data-ttu-id="936ec-175">在这种情况下, 现有网站集可能包含多个已早于删除策略指定的年份的文档, 这意味着在为第一个文件分配文档删除策略后, 会立即删除大量内容时候.</span><span class="sxs-lookup"><span data-stu-id="936ec-175">In this case, it's likely that the existing site collections contain many documents that are already older than the two years specified by the deletion policy—this means a lot of content will be deleted soon after assigning the document deletion policy for the first time.</span></span>
  
<span data-ttu-id="936ec-p117">当您首次分配策略时，将对网站中的所有文件进行计算，满足删除条件的文件将被删除。这适用于所有现有文件，而不仅仅针对分配策略后新建的文件。还要记住，时间段是针对每个文件的年龄而言，而不是自首次分配策略后的时间。</span><span class="sxs-lookup"><span data-stu-id="936ec-p117">When you assign the policy for the first time, all documents in the site are evaluated and, if they meet the criteria, they will be deleted. This applies to all existing documents, not just new documents created since the policy was assigned. And remember that the time period is for the age of each document, not the time from when the policy was first assigned.</span></span>
  
<span data-ttu-id="936ec-p118">因此，在首次将策略分配到网站之前，您应该首先考虑现有内容的年龄，以及该策略对现有内容的影响。在分配策略之前，您还需要与网站所有者就新的策略进行沟通，以便其有时间评估可能的影响。</span><span class="sxs-lookup"><span data-stu-id="936ec-p118">Therefore, before you assign a policy to a site for the first time, you should first consider the age of the existing content and how the policy may impact that existing content. You may also want to communicate the new policy to site owners before assigning it, to give them time to assess the possible impact.</span></span>
  
## <a name="time-lag-for-propagating-policies"></a><span data-ttu-id="936ec-181">传播策略的时间延迟</span><span class="sxs-lookup"><span data-stu-id="936ec-181">Time lag for propagating policies</span></span>

<span data-ttu-id="936ec-182">将策略分配到网站集之后，网站所有者可使用“网站设置”\*\*\*\* 页上的“文件删除策略”\*\*\*\* 链接查看和应用适用于网站的策略。</span><span class="sxs-lookup"><span data-stu-id="936ec-182">After you assign policies to a site collection, site owners use the **Document Deletion Policies** link on the **Site Settings** page to view and apply policies available for the site.</span></span> 
  
<span data-ttu-id="936ec-183">除非已将策略分配给网站集, 否则不会显示 "**文档删除策略**" 链接。</span><span class="sxs-lookup"><span data-stu-id="936ec-183">The **Document Deletion Policies** link won't appear unless policies have been assigned to the site collection.</span></span> <span data-ttu-id="936ec-184">此外, 在将策略分配给网站后, 链接不会立即显示出来, 在显示 "**文档删除策略**" 链接时, 可能需要从策略分配到24小时。</span><span class="sxs-lookup"><span data-stu-id="936ec-184">Also, the link doesn't appear immediately after policies have been assigned to the site—it can take up to 24 hours from when the policies are assigned to when the **Document Deletion Policies** link appears.</span></span> 
  
## <a name="permissions"></a><span data-ttu-id="936ec-185">权限</span><span class="sxs-lookup"><span data-stu-id="936ec-185">Permissions</span></span>

<span data-ttu-id="936ec-p120">将使用文件删除策略中心的合规性团队成员需要具有对策略中心和策略将应用到的网站的访问权限。我们建议您：</span><span class="sxs-lookup"><span data-stu-id="936ec-p120">Members of your compliance team who will use the Document Deletion Policy Center need permissions to both the policy center and site collections to which policies will be applied. We recommend that you:</span></span>
  
1. <span data-ttu-id="936ec-188">创建一个安全组, 其中包含文档删除策略中心的所有用户—您很可能是合规性策略管理团队。</span><span class="sxs-lookup"><span data-stu-id="936ec-188">Create a security group that contains all users of the Document Deletion Policy Center—most likely your compliance policy-management team.</span></span> <span data-ttu-id="936ec-189">有关详细信息, 请参阅[管理启用邮件的安全组](https://go.microsoft.com/fwlink/p/?LinkID=404345)。</span><span class="sxs-lookup"><span data-stu-id="936ec-189">See [Manage Mail-Enabled Security Groups](https://go.microsoft.com/fwlink/p/?LinkID=404345) for more information.</span></span> 
    
2. <span data-ttu-id="936ec-190">在文件删除策略中心，将网站集所有者权限分配给安全组。</span><span class="sxs-lookup"><span data-stu-id="936ec-190">In the Document Deletion Policy Center, assign site collection owner permissions to the security group.</span></span> <span data-ttu-id="936ec-191">有关详细信息, 请参阅[网站集管理员的权限](https://go.microsoft.com/fwlink/p/?LinkID=404346)。</span><span class="sxs-lookup"><span data-stu-id="936ec-191">See [Permissions for site collection administrators](https://go.microsoft.com/fwlink/p/?LinkID=404346) for more information.</span></span> 
    
3. <span data-ttu-id="936ec-192">在需要将文件删除策略分配到的每个网站集中，将网站集所有者权限分配给安全组。</span><span class="sxs-lookup"><span data-stu-id="936ec-192">In each site collection to which you need to assign document deletion policies, assign site collection owner permissions to the security group.</span></span>
    
## <a name="how-document-deletion-policies-work-with-hold-policies"></a><span data-ttu-id="936ec-193">文件删除策略如何与保留策略结合使用</span><span class="sxs-lookup"><span data-stu-id="936ec-193">How document deletion policies work with hold policies</span></span>

<span data-ttu-id="936ec-194">保留策略可确保将所有内容保留特定时间，而文件删除策略可确保所有内容在特定时间段后删除。</span><span class="sxs-lookup"><span data-stu-id="936ec-194">A hold policy ensures that all content is preserved for a specific period of time, while a document deletion policy ensures that all content is deleted after a specific period of time.</span></span>
  
<span data-ttu-id="936ec-p123">如果需要将文件保留固定时间段，则可以将保留策略与删除策略结合使用。例如，您可以在修改文件后将其保留三年，然后设置删除策略，以在最后修改这些文件的三年后删除。</span><span class="sxs-lookup"><span data-stu-id="936ec-p123">If you need to retain documents for a fixed period of time, you can use a hold policy in conjunction with a deletion policy. For example, you could hold documents for three years after they are modified, and then set up a deletion policy to delete those documents three years after they were last modified.</span></span>
  
<span data-ttu-id="936ec-p124">请注意，删除策略无法覆盖保留策略。如果网站处于保留状态，而文件删除策略删除了一个文件，那么该文件会保留在保存保留库中，与手动删除文件的方式相同。</span><span class="sxs-lookup"><span data-stu-id="936ec-p124">Note that a deletion policy cannot override a hold. If a site is on hold and a document deletion policy deletes a document, then the document will be preserved in the Preservation Hold library in the same way as if the document had been deleted manually.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="936ec-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="936ec-199">See also</span></span>

[<span data-ttu-id="936ec-200">应用或删除网站的文件删除策略</span><span class="sxs-lookup"><span data-stu-id="936ec-200">Apply or remove a document deletion policy for a site</span></span>](apply-or-remove-a-document-deletion-policy-for-a-site.md)

[<span data-ttu-id="936ec-201">创建文档删除策略</span><span class="sxs-lookup"><span data-stu-id="936ec-201">Create a document deletion policy</span></span>](create-a-document-deletion-policy.md)


