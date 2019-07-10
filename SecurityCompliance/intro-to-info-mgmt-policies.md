---
title: 信息管理策略简介
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2014
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
ms.collection:
- M365-security-compliance
description: 信息管理策略是适用于特定类型内容的一组规则。 信息管理策略使组织能够控制和跟踪多类信息，例如将内容保留多长时间，或者用户可以对该内容执行哪些操作。 信息管理策略可帮助组织遵守法律或政府法规，或者可以仅强制执行内部业务流程。
ms.openlocfilehash: a5cf571b22b7d698daf8a70f8565b250e2388a1a
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599078"
---
# <a name="introduction-to-information-management-policies"></a><span data-ttu-id="988b5-105">信息管理策略简介</span><span class="sxs-lookup"><span data-stu-id="988b5-105">Introduction to information management policies</span></span>

<span data-ttu-id="988b5-106">信息管理策略是适用于特定类型内容的一组规则。</span><span class="sxs-lookup"><span data-stu-id="988b5-106">An information management policy is a set of rules for a type of content.</span></span> <span data-ttu-id="988b5-107">信息管理策略使组织能够控制和跟踪多类信息，例如将内容保留多长时间，或者用户可以对该内容执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="988b5-107">Information management policies enable organizations to control and track things like how long content is retained or what actions users can take with that content.</span></span> <span data-ttu-id="988b5-108">信息管理策略可帮助组织遵守法律或政府法规，或者可以仅强制执行内部业务流程。</span><span class="sxs-lookup"><span data-stu-id="988b5-108">Information management policies can help organizations comply with legal or governmental regulations, or they can simply enforce internal business processes.</span></span> 
  
<span data-ttu-id="988b5-109">例如, 必须遵守政府法规要求他们展示其财务声明的 "充分控制" 的组织可能会创建一个或多个信息管理策略, 以便在创作过程中审核特定操作并与财务存档相关的所有文档的审批流程。</span><span class="sxs-lookup"><span data-stu-id="988b5-109">For example, an organization that must follow government regulations requiring that they demonstrate "adequate controls" of their financial statements might create one or more information management policies that audit specific actions in the authoring and approval process for all documents related to financial filings.</span></span>
  
<span data-ttu-id="988b5-110">有关操作方法的信息, 请参阅[创建和应用信息管理策略](create-info-mgmt-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="988b5-110">For how-to information, see [Create and apply information management policies](create-info-mgmt-policies.md).</span></span>
  
## <a name="features-of-information-management-policies"></a><span data-ttu-id="988b5-111">信息管理策略的功能</span><span class="sxs-lookup"><span data-stu-id="988b5-111">Features of information management policies</span></span>
<span data-ttu-id="988b5-112"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="988b5-112"></span></span>

<span data-ttu-id="988b5-113">有四种基本类别的预定义策略功能, 组织可以单独或结合使用它们来管理内容和流程。</span><span class="sxs-lookup"><span data-stu-id="988b5-113">There are four basic categories of predefined policy features that organizations can use individually or in combination to manage content and processes.</span></span> 
  
![内容策略的类型](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
<span data-ttu-id="988b5-115">审核策略功能可帮助组织分析在对文档和列表项执行的事件和操作进行日志记录时如何使用其内容管理系统。</span><span class="sxs-lookup"><span data-stu-id="988b5-115">The Auditing policy feature helps organizations analyze how their content management systems are used by logging events and operations that are performed on documents and list items.</span></span> <span data-ttu-id="988b5-116">您可以将审核策略功能配置为记录事件, 例如, 在编辑、查看、签入、签出、删除文档或项目或更改其权限时。</span><span class="sxs-lookup"><span data-stu-id="988b5-116">You can configure the Auditing policy feature to log events such as when a document or item is edited, viewed, checked in, checked out, deleted, or has its permissions changed.</span></span> <span data-ttu-id="988b5-117">所有审核信息都存储在服务器上的单个审核日志中, 网站管理员可以对其运行报告。</span><span class="sxs-lookup"><span data-stu-id="988b5-117">All of the audit information is stored in a single audit log on the server, and site administrators can run reports on it.</span></span> 
  
<span data-ttu-id="988b5-118">过期策略功能可帮助组织以一致的、trackable 的方式从网站中删除过期的内容或删除过期的内容。</span><span class="sxs-lookup"><span data-stu-id="988b5-118">The Expiration policy feature helps organizations delete or remove out-of-date content from their sites in a consistent, trackable way.</span></span> <span data-ttu-id="988b5-119">这可帮助您管理与保留过时内容相关的成本和风险。</span><span class="sxs-lookup"><span data-stu-id="988b5-119">This helps you manage both the cost and risk associated with retaining out-of-date content.</span></span> <span data-ttu-id="988b5-120">您可以配置过期策略, 以指定某些类型的内容在特定日期或文档创建或上次修改后的一段时间内过期。</span><span class="sxs-lookup"><span data-stu-id="988b5-120">You can configure an Expiration policy to specify that certain types of content expire on a particular date or within a period of time after the document was created or last modified.</span></span>
  
<span data-ttu-id="988b5-121">组织还可以创建和部署自定义策略功能，以满足特定需求。</span><span class="sxs-lookup"><span data-stu-id="988b5-121">Organizations can also create and deploy custom policy features to meet specific needs.</span></span> <span data-ttu-id="988b5-122">例如, 制造组织可能需要为所有草稿产品-设计规范文档定义信息管理策略, 禁止用户在不安全的打印机上打印这些文档的副本。</span><span class="sxs-lookup"><span data-stu-id="988b5-122">For example, a manufacturing organization might want to define an information management policy for all draft product-design specification documents that prohibits users from printing copies of these documents on nonsecure printers.</span></span> <span data-ttu-id="988b5-123">若要定义此类型的信息管理策略, 您可以创建和部署打印限制策略功能, 该功能可添加到产品设计规范内容类型的相关信息管理策略中。</span><span class="sxs-lookup"><span data-stu-id="988b5-123">To define this kind of information management policy, you can create and deploy a Printing Restriction policy feature that can be added to the relevant information management policy for the product design specification content type.</span></span>
  
## <a name="locations-to-use-an-information-management-policy"></a><span data-ttu-id="988b5-124">使用信息管理策略的位置</span><span class="sxs-lookup"><span data-stu-id="988b5-124">Locations to use an information management policy</span></span>
<span data-ttu-id="988b5-125"><a name="__toc340213528"> </a></span><span class="sxs-lookup"><span data-stu-id="988b5-125"></span></span>

<span data-ttu-id="988b5-126">若要实现信息管理策略, 必须将其添加到网站中的列表、库或内容类型。</span><span class="sxs-lookup"><span data-stu-id="988b5-126">To implement an information management policy, you must add it to a list, library, or content type in a site.</span></span> <span data-ttu-id="988b5-127">您创建或添加信息管理策略的位置会影响策略应用范围的范围或可以使用的广泛程度。</span><span class="sxs-lookup"><span data-stu-id="988b5-127">The location where you create or add an information management policy affects how broadly the policy applies or how broadly it can be used.</span></span> <span data-ttu-id="988b5-128">可以执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="988b5-128">You can:</span></span>
  
 <span data-ttu-id="988b5-129">**创建网站集策略, 然后将此策略添加到内容类型、列表或库**您可以在网站集的首要网站中的 "策略" 列表中创建一个网站集策略。</span><span class="sxs-lookup"><span data-stu-id="988b5-129">**Create a site collection policy and then add this policy to a content type, list, or library** You can create a site collection policy in the Policies list in the top-level site of a site collection.</span></span> <span data-ttu-id="988b5-130">创建网站集策略后, 可以将其导出, 以便其他网站集的管理员可以将其导入到策略列表中。</span><span class="sxs-lookup"><span data-stu-id="988b5-130">After you create a site collection policy, you can export it so that administrators of other site collections can import it into their Policies list.</span></span> <span data-ttu-id="988b5-131">创建可导出的网站集策略使您能够在组织中的各个网站上标准化信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="988b5-131">Creating an exportable site collection policy enables you to standardize the information management policies across the sites in your organization.</span></span> 
  
<span data-ttu-id="988b5-132">向网站内容类型添加网站集策略时, 如果将该网站内容类型的一个实例添加到列表或库中, 则该列表或库的所有者将无法修改该列表或库的网站集策略。</span><span class="sxs-lookup"><span data-stu-id="988b5-132">When you add a site collection policy to a site content type, and an instance of that site content type is added to a list or library, the owner of that list or library cannot modify the site collection policy for the list or library.</span></span> <span data-ttu-id="988b5-133">向网站内容类型添加网站集策略是一种确保在网站层次结构的每个级别都强制实施网站集策略的良好方法。</span><span class="sxs-lookup"><span data-stu-id="988b5-133">Adding a site collection policy to a site content type is a good way to ensure that site collection policies are enforced at each level of your site hierarchy.</span></span>
  
!["网站设置" 页上的 "内容类型策略模板" 链接](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 <span data-ttu-id="988b5-135">**为顶级网站 "网站内容类型库" 中的网站内容类型创建信息管理策略, 然后将该内容类型添加到一个或多个列表或库中**您还可以直接为网站内容类型创建信息管理策略, 然后将该网站内容类型的一个实例与多个列表或库相关联。</span><span class="sxs-lookup"><span data-stu-id="988b5-135">**Create an information management policy for a site content type in the top-level site's Site Content Type Gallery, and then add that content type to one or more lists or libraries** You can also create an information management policy directly for a site content type and then associate an instance of that site content type with multiple lists or libraries.</span></span> <span data-ttu-id="988b5-136">如果使用此方法创建信息管理策略, 则该内容类型的网站集中的每个项目或从该内容类型继承的内容类型都具有该策略。</span><span class="sxs-lookup"><span data-stu-id="988b5-136">If you create an information management policy this way, every item in the site collection of that content type or a content type that inherits from that content type has the policy.</span></span> <span data-ttu-id="988b5-137">但是, 如果直接为网站内容类型创建信息管理策略, 则在其他网站集中重用此信息管理策略会更加困难, 因为无法导出以这种方式创建的策略。</span><span class="sxs-lookup"><span data-stu-id="988b5-137">However, if you create an information management policy directly for a site content type, it is more difficult to reuse this information management policy in other site collections, because policies that are created this way cannot be exported.</span></span> 
  
!["网站设置" 页上的 "网站内容类型" 链接](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![网站内容类型的 "设置" 页上的信息管理策略链接](media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
<span data-ttu-id="988b5-140">注释若要控制在网站集中使用的策略, 网站集管理员可以禁用直接对内容类型设置策略功能的功能。</span><span class="sxs-lookup"><span data-stu-id="988b5-140">Note To control which policies are used in a site collection, site collection administrators can disable the ability to set policy features directly on a content type.</span></span> <span data-ttu-id="988b5-141">当此限制生效时, 创建内容类型的用户将被限制为从 "网站集策略" 列表中选择策略。</span><span class="sxs-lookup"><span data-stu-id="988b5-141">When this restriction is in effect, users who create content types are limited to selecting policies from the site collection Policies list.</span></span>
  
 <span data-ttu-id="988b5-142">**为列表或库创建信息管理策略**如果您的组织需要将特定的信息管理策略应用于一组非常有限的内容, 则可以创建一个仅适用于单个列表或库的信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="988b5-142">**Create an information management policy for a list or library** If your organization needs to apply a specific information management policy to a very limited set of content, you can create an information management policy that applies only to an individual list or library.</span></span> <span data-ttu-id="988b5-143">这种创建信息管理策略的方法的灵活性最低, 因为该策略仅适用于一个位置, 不能在其他位置导出或重用。</span><span class="sxs-lookup"><span data-stu-id="988b5-143">This method of creating an information management policy is the least flexible, because the policy applies only to one location, and it cannot be exported or reused for other locations.</span></span> <span data-ttu-id="988b5-144">但是, 有时您可能需要创建具有有限适用性的独特的信息管理策略, 以解决特定情况。</span><span class="sxs-lookup"><span data-stu-id="988b5-144">However, sometimes you may need to create unique information management policies with limited applicability to address specific situations.</span></span> 
  
![文档库的 "设置" 页上的信息管理策略链接](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
<span data-ttu-id="988b5-146">注释</span><span class="sxs-lookup"><span data-stu-id="988b5-146">Notes</span></span> 
  
<span data-ttu-id="988b5-147">仅当列表或库不支持多个内容类型时, 才能为该列表或库创建信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="988b5-147">You can create an information management policy for a list or library only if that list or library does not support multiple content types.</span></span> <span data-ttu-id="988b5-148">如果列表或库支持多种内容类型, 则需要为与该列表或库关联的每个单独的列表内容类型定义一个信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="988b5-148">If a list or library supports multiple content types, you need to define an information management policy for each individual list content type that is associated with that list or library.</span></span> <span data-ttu-id="988b5-149">(与特定列表或库关联的网站内容类型的实例称为 "列表内容类型"。)</span><span class="sxs-lookup"><span data-stu-id="988b5-149">(Instances of a site content type that are associated with a specific list or library are known as list content types.)</span></span>
  
<span data-ttu-id="988b5-150">若要控制在网站集中使用哪些策略, 网站集管理员可以禁用直接在列表或库上设置策略功能的功能。</span><span class="sxs-lookup"><span data-stu-id="988b5-150">To control which policies are used in a site collection, site collection administrators can disable the ability to set policy features directly on a list or library.</span></span> <span data-ttu-id="988b5-151">当此限制生效时, 管理列表或库的用户将被限制为从 "网站集策略" 列表中选择策略。</span><span class="sxs-lookup"><span data-stu-id="988b5-151">When this restriction is in effect, users who manage lists or libraries are limited to selecting policies from the site collection Policies list.</span></span>
  
[<span data-ttu-id="988b5-152">信息管理策略是内容类型的一组规则。通过信息管理策略, 组织可以控制和跟踪内容保留的时间或用户可对该内容执行的操作等内容。信息管理策略可以帮助组织遵守法律或政府法规, 也可以仅强制实施内部业务流程。例如, 必须遵守政府法规要求他们展示其财务声明的 "充分控制" 的组织可能会创建一个或多个信息管理策略, 以便在创作过程中审核特定操作并与财务存档相关的所有文档的审批流程。有关操作方法的信息, 请参阅创建和应用信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="988b5-152">An information management policy is a set of rules for a type of content. Information management policies enable organizations to control and track things like how long content is retained or what actions users can take with that content. Information management policies can help organizations comply with legal or governmental regulations, or they can simply enforce internal business processes. For example, an organization that must follow government regulations requiring that they demonstrate "adequate controls" of their financial statements might create one or more information management policies that audit specific actions in the authoring and approval process for all documents related to financial filings.For how-to information, see Create and apply information management policies.</span></span>](intro-to-info-mgmt-policies.md#__top)
  

