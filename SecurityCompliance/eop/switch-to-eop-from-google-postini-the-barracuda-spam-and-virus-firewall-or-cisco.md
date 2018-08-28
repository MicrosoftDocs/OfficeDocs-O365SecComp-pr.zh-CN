---
title: 从 Google Postini、Barracuda 垃圾邮件和病毒防火墙或 Cisco IronPort 切换到 EOP
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
description: 本主题的目的是帮助您了解从内部部署电子邮件卫生设备或基于云的保护服务切换到 Exchange Online Protection (EOP) 的过程，然后为您提供开始操作的帮助资源。
ms.openlocfilehash: d1dc75e8d020f865e4f358899802d0da320deeb5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026399"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a><span data-ttu-id="24cd9-103">从 Google Postini、Barracuda 垃圾邮件和病毒防火墙或 Cisco IronPort 切换到 EOP</span><span class="sxs-lookup"><span data-stu-id="24cd9-103">Switch to EOP from Google Postini, the Barracuda Spam and Virus Firewall, or Cisco IronPort</span></span>

 <span data-ttu-id="24cd9-p101">本主题的目的是帮助您了解从内部部署电子邮件卫生设备或基于云的保护服务切换到 Exchange Online Protection (EOP) 的过程，然后为您提供开始操作的帮助资源。有许多垃圾邮件筛选解决方案，但是在大多数情况下切换到 EOP 的过程是相似的。</span><span class="sxs-lookup"><span data-stu-id="24cd9-p101">The purpose of this topic is to help you understand the process for switching to Exchange Online Protection (EOP) from an on-premises email hygiene appliance or cloud-based protection service, and then to provide you with help resources to get started. There are many spam-filtering solutions, but the process for switching to EOP is similar in most cases.</span></span>
  
<span data-ttu-id="24cd9-106">如果您刚开始使用 EOP 且想要在决定切换之前阅读其功能的概述，请从 TechNet 上的 [Exchange Online Protection 概述](exchange-online-protection-overview.md)开始入手。</span><span class="sxs-lookup"><span data-stu-id="24cd9-106">If you are new to EOP and you want to read an overview of its features before you decide to switch, start with the [Exchange Online Protection overview](exchange-online-protection-overview.md) on TechNet.</span></span> 
  
<span data-ttu-id="24cd9-p102">在切换到 EOP 之前，有必要考虑是要在云中、Exchange Online、内部部署还是在混合方案中托管 EOP 保护的邮箱。（混合方案意味着某些邮箱在内部部署中托管，其他一些邮箱使用 Exchange Online 托管。）各托管方案：可能是云、内部部署和混合，但安装步骤可能有所不同。有一些考虑事项可帮助您选择合适的部署：</span><span class="sxs-lookup"><span data-stu-id="24cd9-p102">Before you switch to EOP, it's important to think about whether you want to host your EOP-protected mailboxes in the cloud, with Exchange Online, on-premises, or in a hybrid scenario. (Hybrid means that you have some mailboxes hosted on-premises and another portion hosted with Exchange Online.) Each of these hosting scenarios: cloud, on-premises, and hybrid, is possible, but the setup steps can vary. Here are a few considerations to help you choose the appropriate deployment:</span></span>
  
- <span data-ttu-id="24cd9-p103">**使用内部部署邮箱的 EOP 保护** 如果您有要使用的现有邮件托管基础结构或者有在内部部署中保留邮箱的业务需要，且您希望使用 EOP 基于云的电子邮件保护，则适合选择此方案。 [独立切换到 EOP](#BKMK_SwitchStandalone.md)详细描述了此方案。</span><span class="sxs-lookup"><span data-stu-id="24cd9-p103">**EOP protection with on-premises mailboxes** This scenario is appropriate if you have existing mail-hosting infrastructure you want to use, or you have business requirements to keep mailboxes on-premises, and you want EOP's cloud-based email protection. [Switch to EOP standalone](#BKMK_SwitchStandalone.md) describes this scenario in more detail.</span></span> 
    
- <span data-ttu-id="24cd9-p104">**使用 Exchange Online 邮箱的 EOP 保护** 如果您希望使用 EOP 保护且在云中托管所有邮箱，则适合选择此方案。它可以帮助您降低复杂性，因为您不必维护内部部署邮件传递服务器。 [切换到 Exchange Online](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md#BKMK_SwitchEXO) 描述了此方案。</span><span class="sxs-lookup"><span data-stu-id="24cd9-p104">**EOP protection with Exchange Online mailboxes** This scenario is appropriate if you want EOP protection and all of your mailboxes hosted in the cloud. It can help you reduce complexity, because you don't have to maintain on-premises messaging servers. [Switch to Exchange Online](switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco.md#BKMK_SwitchEXO) describes this scenario.</span></span> 
    
- <span data-ttu-id="24cd9-p105">**使用混合邮箱的 EOP 保护** 可能您要使用云邮箱，但是需要在内部部署中为某些用户保留邮箱。如果您希望在内部部署中托管某些邮箱并使用 Exchange Online 托管其他邮箱，则选择此方案。 [切换到混合解决方案](#BKMK_SwitchHybrid.md)描述了此方案。</span><span class="sxs-lookup"><span data-stu-id="24cd9-p105">**EOP protection with hybrid mailboxes** Perhaps you want cloud mailboxes, but you need to keep mailboxes for some users on-premises. Choose this scenario if you want some mailboxes hosted on-premises and another portion hosted with Exchange Online. [Switch to a hybrid solution](#BKMK_SwitchHybrid.md) describes this scenario.</span></span> 
    
## <a name="switch-to-eop-standalone"></a><span data-ttu-id="24cd9-118">独立切换到 EOP</span><span class="sxs-lookup"><span data-stu-id="24cd9-118">Switch to EOP standalone</span></span>
<span data-ttu-id="24cd9-119"><a name="BKMK_SwitchStandalone"> </a></span><span class="sxs-lookup"><span data-stu-id="24cd9-119"></span></span>

<span data-ttu-id="24cd9-p106">如果当前在内部部署中托管邮箱，并使用内部部署保护设备或云邮件传递保护服务，则可以切换到 EOP 以利用其保护功能和可用性。要在独立方案中设置 EOP（这意味着在内部部署中托管邮箱并使用 EOP 提供电子邮件保护），可以按照[设置 EOP 服务](set-up-your-eop-service.md)中所述的步骤执行操作。该主题概述了设置 EOP 保护的步骤，包括注册、添加域和使用连接器设置邮件流。</span><span class="sxs-lookup"><span data-stu-id="24cd9-p106">If you currently host your mailboxes on premises and use an on-premises protection appliance or a cloud messaging-protection service, you can switch to EOP to take advantage of its protection features and availability. To set up EOP in a standalone scenario, which means you host your mailboxes on premises and use EOP to provide email protection, you can follow the steps outlined in [Set up your EOP service](set-up-your-eop-service.md). The topic outlines the steps for setting up EOP protection, which include sign up, adding your domain, and setting up mail flow with connectors.</span></span>
  
## <a name="switch-to-exchange-online"></a><span data-ttu-id="24cd9-123">切换到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="24cd9-123">Switch to Exchange Online</span></span>
<span data-ttu-id="24cd9-124"><a name="BKMK_SwitchEXO"> </a></span><span class="sxs-lookup"><span data-stu-id="24cd9-124"></span></span>

<span data-ttu-id="24cd9-p107">可能您有内部部署设备保护的内部部署邮箱，希望转到 Exchange Online 云托管的邮箱和 EOP 保护，以利用 Office 365 的云邮件传递和保护功能。要开始操作，您可以注册 Office 365 并添加域。此方案不需要您设置连接器，因为没有任何通往内部部署邮箱的路由。从 [Office 365 注册页面](https://www.microsoft.com/en-us/office365/online-software.aspx)开始操作。(（[Office 365 入门](https://go.microsoft.com/fwlink/p/?LinkId=275407)提供了用于熟悉其功能的资源。）</span><span class="sxs-lookup"><span data-stu-id="24cd9-p107">Perhaps you have on-premises mailboxes protected by an on-premises appliance, and you want to jump to Exchange Online cloud-hosted mailboxes and EOP protection to take advantage of Office 365 cloud messaging and protection features. To get started, you can sign up for Office 365 and add your domain. This scenario doesn't require you to setup connectors, because there isn't any routing to on-premises mailboxes. Begin at the [Office 365 sign up page](https://www.microsoft.com/en-us/office365/online-software.aspx). ([Get started with Office 365](https://go.microsoft.com/fwlink/p/?LinkId=275407) provides resources to get familiar with its features.)</span></span> 
  
<span data-ttu-id="24cd9-130">在 Office 365 设置过程中，将创建基于云的邮箱用户。</span><span class="sxs-lookup"><span data-stu-id="24cd9-130">During the Office 365 setup process, you will create your cloud-based mailbox users.</span></span>
  
## <a name="switch-to-a-hybrid-solution"></a><span data-ttu-id="24cd9-131">切换到混合解决方案</span><span class="sxs-lookup"><span data-stu-id="24cd9-131">Switch to a hybrid solution</span></span>
<span data-ttu-id="24cd9-132"><a name="BKMK_SwitchHybrid"> </a></span><span class="sxs-lookup"><span data-stu-id="24cd9-132"></span></span>

<span data-ttu-id="24cd9-p108">出于业务需要或法规考虑，您可能希望仅将一部分邮箱移动到云。当部署混合方案时，可以根据业务需要指示，将邮箱移动到云。迁移到具有 EOP 保护的混合方案比移动到全云方案更复杂，但是 Microsoft 提供了完全的混合支持和广泛的资源以使移动到混合方案更加简便。</span><span class="sxs-lookup"><span data-stu-id="24cd9-p108">You may want to move only a portion of your mailboxes to the cloud because of business requirements or regulatory considerations. When you deploy a hybrid scenario, you can move mailboxes to the cloud as your business requirements dictate. Migrating to a hybrid scenario with EOP protection is more complicated than moving to an all-cloud scenario, but Microsoft provides full hybrid support and ample resources to make the move to hybrid easier.</span></span>
  
<span data-ttu-id="24cd9-p109">如果您考虑混合部署，则最好从 [Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx) 开始。另外，有几种不同的在混合方案中路由邮件的方式需要重点了解。 [Transport Routing in Exchange 2013 Hybrid Deployments](http://technet.microsoft.com/library/36c2cea3-2e2f-40ac-88bd-7e1b6bd27828.aspx)解释了每种类型，因此您可以根据业务需求选择最佳路由方案。</span><span class="sxs-lookup"><span data-stu-id="24cd9-p109">The best place to start, if you are considering a hybrid deployment, is [Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx). Additionally, there are a few different ways you can route mail in a hybrid scenario that are important to understand. [Transport Routing in Exchange 2013 Hybrid Deployments](http://technet.microsoft.com/library/36c2cea3-2e2f-40ac-88bd-7e1b6bd27828.aspx) explains each type, so you can choose the best routing scenario, based on your business requirements.</span></span> 
  
## <a name="migration-planning"></a><span data-ttu-id="24cd9-139">迁移计划</span><span class="sxs-lookup"><span data-stu-id="24cd9-139">Migration planning</span></span>
<span data-ttu-id="24cd9-140"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="24cd9-140"></span></span>

<span data-ttu-id="24cd9-141">当决定切换到 EOP 时，请确保特别留意下列几个方面：</span><span class="sxs-lookup"><span data-stu-id="24cd9-141">When you decide to switch to EOP, make sure you give special consideration to the following areas:</span></span>
  
- <span data-ttu-id="24cd9-p110">**自定义筛选规则** 如果您有自定义筛选或业务策略规则来捕获特定垃圾邮件，则建议您迁移规则之前，尝试一段时间带有默认设置的 EOP。EOP 提供了具有默认设置的企业级垃圾邮件保护，这可能表示您不需要将某些规则迁移到 EOP。当然，如果您有现成的强制特定自定义业务策略的规则，则可以创建这些规则。 [Transport Rules](http://technet.microsoft.com/library/c3d2031c-fb7b-4866-8ae1-32928d0138ef.aspx)为在 EOP 中创建传输规则提供了详细说明。</span><span class="sxs-lookup"><span data-stu-id="24cd9-p110">**Custom Filtering Rules** If you have custom filtering or business-policy rules to catch specific spam, we recommend that you try EOP with the default settings for a period, before you migrate your rules. EOP offers enterprise-level spam protection with the default settings, it may turn out that you don't need to migrate some of your rules to EOP. Of course, if you have rules in place that enforce specific custom business policies, you can create those. [Transport Rules](http://technet.microsoft.com/library/c3d2031c-fb7b-4866-8ae1-32928d0138ef.aspx) provides detailed instructions for creating transport rules in EOP.</span></span> 
    
- <span data-ttu-id="24cd9-p111">**IP 允许列表和 IP 阻止列表**如果您有每个用户允许列表和阻止名单，允许一些时间来安装过程的一部分复制到 EOP 的列表。有关 IP 允许列表和 IP 阻止列表，请参阅[配置连接筛选器策略](../configure-the-connection-filter-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="24cd9-p111">**IP allow lists and IP block lists** If you have per-user allow lists and block lists, allow some time to copy the lists to EOP as part of your setup process. For more information about IP allow lists and IP block lists, see [Configure the connection filter policy](../configure-the-connection-filter-policy.md).</span></span>
    
- <span data-ttu-id="24cd9-p112">**安全通信** 如果您的合作伙伴需要加密邮件传递，我们建议在 Exchange 管理中心中进行该设置。若要配置此方案，请参阅 [Create connectors for a secure mail channel using transport layer security (TLS)](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx)。</span><span class="sxs-lookup"><span data-stu-id="24cd9-p112">**Secure Communication** If you have a partner that requires encrypted messaging, we recommend that you set this up in the Exchange admin center. To configure this scenario, see [Create connectors for a secure mail channel using transport layer security (TLS)](http://technet.microsoft.com/library/1ce4d6a4-41ba-4d1e-9ca9-e826252c1041.aspx).</span></span>
    
> [!TIP]
> <span data-ttu-id="24cd9-p113">从内部部署设备切换到 EOP 时，可以就地离开执行业务规则检查的设备或服务器。例如，如果设备对出站邮件执行自定义筛选，您希望它继续此操作，则可以配置 EOP 将邮件直接发送到设备以进行额外筛选，然后再路由到 Internet。[Exchange Online Protection Connectors - Outbound Smart Host Scenario](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx)演示了如何在此情况下设置邮件流。</span><span class="sxs-lookup"><span data-stu-id="24cd9-p113">When you switch from an on-premises appliance to EOP, it is possible to leave your appliance or a server in place that performs business rule checks. For instance, if your appliance performs custom filtering on outbound mail, and you want it to continue doing so, you can configure EOP to send mail directly to the appliance for additional filtering, before it is routed to the Internet. [Exchange Online Protection Connectors - Outbound Smart Host Scenario](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx) shows you how to set up mail flow in this case.</span></span> 
  
