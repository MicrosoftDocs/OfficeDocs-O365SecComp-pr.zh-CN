---
title: 信息管理策略简介
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/16/2014
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
description: 信息管理策略是一种内容类型的规则的一组。信息管理策略启用到控件的组织和跟踪类似内容保留多长时间或操作用户可以对该内容。信息管理策略可帮助组织符合法律或政府法规，或只是可以强制执行内部业务流程。
ms.openlocfilehash: 9ec64cd7e015acc6a7d8da324ba18cf74405cc71
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525300"
---
# <a name="introduction-to-information-management-policies"></a><span data-ttu-id="702c7-105">信息管理策略简介</span><span class="sxs-lookup"><span data-stu-id="702c7-105">Introduction to information management policies</span></span>

<span data-ttu-id="702c7-p102">信息管理策略是一种内容类型的规则的一组。信息管理策略启用到控件的组织和跟踪类似内容保留多长时间或操作用户可以对该内容。信息管理策略可帮助组织符合法律或政府法规，或只是可以强制执行内部业务流程。</span><span class="sxs-lookup"><span data-stu-id="702c7-p102">An information management policy is a set of rules for a type of content. Information management policies enable organizations to control and track things like how long content is retained or what actions users can take with that content. Information management policies can help organizations comply with legal or governmental regulations, or they can simply enforce internal business processes.</span></span> 
  
<span data-ttu-id="702c7-109">例如，必须符合政府法规要求它们演示"足够控件"其财务报表的组织可能会创建一个或多个信息管理策略的审核中创作的特定操作和在与财务存档相关的所有文档审批流程。</span><span class="sxs-lookup"><span data-stu-id="702c7-109">For example, an organization that must follow government regulations requiring that they demonstrate "adequate controls" of their financial statements might create one or more information management policies that audit specific actions in the authoring and approval process for all documents related to financial filings.</span></span>
  
<span data-ttu-id="702c7-110">操作方法信息，请参阅[创建和应用信息管理策略](create-info-mgmt-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="702c7-110">For how-to information, see [Create and apply information management policies](create-info-mgmt-policies.md).</span></span>
  
## <a name="features-of-information-management-policies"></a><span data-ttu-id="702c7-111">信息管理策略的功能</span><span class="sxs-lookup"><span data-stu-id="702c7-111">Features of information management policies</span></span>
<span data-ttu-id="702c7-112"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="702c7-112"></span></span>

<span data-ttu-id="702c7-113">有四个基本类别的预定义的策略功能，以便组织用单独或结合使用来管理内容和进程。</span><span class="sxs-lookup"><span data-stu-id="702c7-113">There are four basic categories of predefined policy features that organizations can use individually or in combination to manage content and processes.</span></span> 
  
![类型的内容的策略](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
<span data-ttu-id="702c7-p103">审核策略功能可帮助组织分析日志记录事件和对文档和列表项执行的操作如何使用其内容管理系统。您可以配置审核策略功能要记录事件，例如当编辑文档或项目，查看签入、 签出，删除或更改其权限。所有获得审核信息都存储在服务器上的单个审核日志和网站管理员可以对其运行报告。</span><span class="sxs-lookup"><span data-stu-id="702c7-p103">The Auditing policy feature helps organizations analyze how their content management systems are used by logging events and operations that are performed on documents and list items. You can configure the Auditing policy feature to log events such as when a document or item is edited, viewed, checked in, checked out, deleted, or has its permissions changed. All of the audit information is stored in a single audit log on the server, and site administrators can run reports on it.</span></span> 
  
<span data-ttu-id="702c7-p104">过期策略功能可帮助组织删除或一致的、 可跟踪的方式从其网站中删除过期的内容。这有助于您管理的成本和保留过期内容相关联的风险。您可以配置过期策略，以指定某些类型的内容过期在特定日期或之后文档已创建或上次修改时间一段时间内。</span><span class="sxs-lookup"><span data-stu-id="702c7-p104">The Expiration policy feature helps organizations delete or remove out-of-date content from their sites in a consistent, trackable way. This helps you manage both the cost and risk associated with retaining out-of-date content. You can configure an Expiration policy to specify that certain types of content expire on a particular date or within a period of time after the document was created or last modified.</span></span>
  
<span data-ttu-id="702c7-p105">组织还可以创建和部署自定义策略功能以满足特定需求。例如，制造组织可能想要定义信息管理策略的所有草稿产品设计规范文档的打印份上不安全的打印机的这些文档可禁止用户。若要定义这种类型的信息管理策略，您可以创建和部署打印限制策略功能可以添加到 product 设计规范内容类型的相关信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="702c7-p105">Organizations can also create and deploy custom policy features to meet specific needs. For example, a manufacturing organization might want to define an information management policy for all draft product-design specification documents that prohibits users from printing copies of these documents on nonsecure printers. To define this kind of information management policy, you can create and deploy a Printing Restriction policy feature that can be added to the relevant information management policy for the product design specification content type.</span></span>
  
## <a name="locations-to-use-an-information-management-policy"></a><span data-ttu-id="702c7-124">若要使用的信息管理策略的位置</span><span class="sxs-lookup"><span data-stu-id="702c7-124">Locations to use an information management policy</span></span>
<span data-ttu-id="702c7-125"><a name="__toc340213528"> </a></span><span class="sxs-lookup"><span data-stu-id="702c7-125"></span></span>

<span data-ttu-id="702c7-p106">若要实现信息管理策略，您必须将其添加到列表、 库或网站中的内容类型。创建或添加信息管理策略的位置影响应用该策略的范围或范围使用它。您可以：</span><span class="sxs-lookup"><span data-stu-id="702c7-p106">To implement an information management policy, you must add it to a list, library, or content type in a site. The location where you create or add an information management policy affects how broadly the policy applies or how broadly it can be used. You can:</span></span>
  
 <span data-ttu-id="702c7-p107">**创建网站集策略，然后添加到内容类型、 列表或库此策略**在网站集的首要网站的策略列表中，可以创建网站集策略。创建网站集策略后，您可以导出它使的其他网站集管理员可以将其导入其策略列表。创建可导出的网站集策略，可以跨组织中的网站标准化信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="702c7-p107">**Create a site collection policy and then add this policy to a content type, list, or library** You can create a site collection policy in the Policies list in the top-level site of a site collection. After you create a site collection policy, you can export it so that administrators of other site collections can import it into their Policies list. Creating an exportable site collection policy enables you to standardize the information management policies across the sites in your organization.</span></span> 
  
<span data-ttu-id="702c7-p108">时向网站内容类型添加网站集策略，该网站内容类型的实例添加到列表或库的列表或库所有者无法修改的列表或库的网站集策略。添加网站集策略向网站内容类型一个恰当的方式，以确保该网站集策略的网站层次结构的每个级别强制实施。</span><span class="sxs-lookup"><span data-stu-id="702c7-p108">When you add a site collection policy to a site content type, and an instance of that site content type is added to a list or library, the owner of that list or library cannot modify the site collection policy for the list or library. Adding a site collection policy to a site content type is a good way to ensure that site collection policies are enforced at each level of your site hierarchy.</span></span>
  
![在网站设置页的内容类型策略模板链接](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 <span data-ttu-id="702c7-p109">**创建首要网站的网站内容类型库中的网站内容类型的信息管理策略，然后添加到一个或多个列表或库的内容类型**您还可以创建直接为网站内容类型的信息管理策略，然后将该网站内容类型实例与多个列表或库相关联。如果这种方式创建信息管理策略，该内容类型或内容类型从该内容类型继承的网站集合中每一项了策略。但是，如果创建信息管理策略直接为网站内容类型，就更加难以重用该信息管理策略的其他网站集，因为无法导出创建这样的策略。</span><span class="sxs-lookup"><span data-stu-id="702c7-p109">**Create an information management policy for a site content type in the top-level site's Site Content Type Gallery, and then add that content type to one or more lists or libraries** You can also create an information management policy directly for a site content type and then associate an instance of that site content type with multiple lists or libraries. If you create an information management policy this way, every item in the site collection of that content type or a content type that inherits from that content type has the policy. However, if you create an information management policy directly for a site content type, it is more difficult to reuse this information management policy in other site collections, because policies that are created this way cannot be exported.</span></span> 
  
![在网站设置页的网站内容类型链接](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![在网站内容类型设置页上的信息管理策略链接](media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
<span data-ttu-id="702c7-p110">注意： 要控制网站集中使用的策略，网站集管理员可以禁用能够直接在内容类型上设置的策略功能。当此限制生效，创建内容类型的用户被限制为从网站集策略列表中选择策略。</span><span class="sxs-lookup"><span data-stu-id="702c7-p110">Note To control which policies are used in a site collection, site collection administrators can disable the ability to set policy features directly on a content type. When this restriction is in effect, users who create content types are limited to selecting policies from the site collection Policies list.</span></span>
  
 <span data-ttu-id="702c7-p111">**创建列表或库的信息管理策略**如果您的组织需要将特定信息管理策略应用于一组非常有限的内容，您可以创建仅适用于各个列表或库的信息管理策略。创建信息管理策略的此方法是至少灵活，因为该策略仅适用于同一个位置，并且无法导出或重复使用的其他位置。但是，有时您可能需要具有有限的适用性满足特定情况下创建唯一的信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="702c7-p111">**Create an information management policy for a list or library** If your organization needs to apply a specific information management policy to a very limited set of content, you can create an information management policy that applies only to an individual list or library. This method of creating an information management policy is the least flexible, because the policy applies only to one location, and it cannot be exported or reused for other locations. However, sometimes you may need to create unique information management policies with limited applicability to address specific situations.</span></span> 
  
![在文档库设置页面上的信息管理策略链接](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
<span data-ttu-id="702c7-146">注释</span><span class="sxs-lookup"><span data-stu-id="702c7-146">Notes</span></span> 
  
<span data-ttu-id="702c7-p112">仅当该列表或库不支持多种内容类型，可以创建列表或库的信息管理策略。如果列表或库支持多种内容类型，您需要定义与列表或库关联的每个单独的列表内容类型的信息管理策略。（与特定列表或库关联的网站内容类型实例称为列表内容类型。）</span><span class="sxs-lookup"><span data-stu-id="702c7-p112">You can create an information management policy for a list or library only if that list or library does not support multiple content types. If a list or library supports multiple content types, you need to define an information management policy for each individual list content type that is associated with that list or library. (Instances of a site content type that are associated with a specific list or library are known as list content types.)</span></span>
  
<span data-ttu-id="702c7-p113">若要控制网站集中使用的策略，网站集管理员可以禁用能够直接在列表或库上设置的策略功能。此限制在生效时，管理列表或库的用户被限制为从网站集策略列表中选择策略。</span><span class="sxs-lookup"><span data-stu-id="702c7-p113">To control which policies are used in a site collection, site collection administrators can disable the ability to set policy features directly on a list or library. When this restriction is in effect, users who manage lists or libraries are limited to selecting policies from the site collection Policies list.</span></span>
  
[<span data-ttu-id="702c7-152">信息管理策略是一种内容类型的规则的一组。信息管理策略启用到控件的组织和跟踪类似内容保留多长时间或操作用户可以对该内容。信息管理策略可帮助组织符合法律或政府法规，或只是可以强制执行内部业务流程。例如，必须符合政府法规要求它们演示"足够控件"其财务报表的组织可能会创建一个或多个信息管理策略的审核中创作的特定操作和在与财务存档相关的所有文档审批流程。操作方法信息，请参阅创建和应用信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="702c7-152">An information management policy is a set of rules for a type of content. Information management policies enable organizations to control and track things like how long content is retained or what actions users can take with that content. Information management policies can help organizations comply with legal or governmental regulations, or they can simply enforce internal business processes. For example, an organization that must follow government regulations requiring that they demonstrate "adequate controls" of their financial statements might create one or more information management policies that audit specific actions in the authoring and approval process for all documents related to financial filings.For how-to information, see Create and apply information management policies.</span></span>](intro-to-info-mgmt-policies.md#__top)
  

