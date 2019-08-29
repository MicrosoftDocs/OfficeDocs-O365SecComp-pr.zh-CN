---
title: 委派管理常见问题解答
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
description: 本主题为希望执行委派 Office 365 管理任务（包括能够为其他租户（公司）管理 Exchange Online Protection (EOP)）的 Microsoft 合作伙伴和经销商提供常见问题解答。
ms.openlocfilehash: 6de70859c7bcb5e735be8f29684c7fcd731f6ed5
ms.sourcegitcommit: 73f1db241c0686020167d43442e7b07a2199ea3a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2019
ms.locfileid: "36658108"
---
# <a name="delegated-administration-faq"></a><span data-ttu-id="4f5ca-103">委派管理常见问题解答</span><span class="sxs-lookup"><span data-stu-id="4f5ca-103">Delegated administration FAQ</span></span>

<span data-ttu-id="4f5ca-104">本主题为希望执行委派 Office 365 管理任务（包括能够为其他租户（公司）管理 Exchange Online Protection (EOP)）的 Microsoft 合作伙伴和经销商提供常见问题解答。</span><span class="sxs-lookup"><span data-stu-id="4f5ca-104">This topic provides frequently asked questions and answers for Microsoft partners and resellers who want to perform delegated Office 365 administration tasks, including the ability to manage Exchange Online Protection (EOP) for other tenants (companies).</span></span>
  
 <span data-ttu-id="4f5ca-105">**问：我是经销商，需要管理客户的租户。具体工作原理是什么？**</span><span class="sxs-lookup"><span data-stu-id="4f5ca-105">**Q. I'm a reseller and I need to manage my customer's tenants; how does this work?**</span></span>
  
<span data-ttu-id="4f5ca-106">A.</span><span class="sxs-lookup"><span data-stu-id="4f5ca-106">A.</span></span> <span data-ttu-id="4f5ca-107">如果你是 Microsoft 合作伙伴或经销商, 并且已注册为 Microsoft advisor, 则可以请求在管理中心内管理其租户的权限。</span><span class="sxs-lookup"><span data-stu-id="4f5ca-107">If you are a Microsoft partner or reseller, and you've signed up to be a Microsoft advisor, you can request permission to administer their tenant within the admin center.</span></span> <span data-ttu-id="4f5ca-108">这称为 "委派管理", 它允许您管理其 Office 365 租户 (包括 EOP 设置), 就像您是组织内的管理员一样。</span><span class="sxs-lookup"><span data-stu-id="4f5ca-108">This is known as delegated administration, and it allows you to manage their Office 365 tenant (including EOP settings) as if you were an administrator within their organization.</span></span> <span data-ttu-id="4f5ca-109">执行委派管理的步骤如下所示:</span><span class="sxs-lookup"><span data-stu-id="4f5ca-109">The steps for performing delegated administration are as follows:</span></span>
  
1. <span data-ttu-id="4f5ca-110">注册成为 [Microsoft Office 365 顾问](https://aka.ms/cloudbenefits)。</span><span class="sxs-lookup"><span data-stu-id="4f5ca-110">Sign up to be a [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).</span></span>

2. <span data-ttu-id="4f5ca-p102">注册以执行 Office 365 委派管理。在您开始管理客户帐户之前，客户必须将您授权为委派管理员。要获取此批准，您需首先向其[发送委派管理提议](https://go.microsoft.com/fwlink/?LinkId=396829)。（您也可以稍后向客户提供委派管理。）</span><span class="sxs-lookup"><span data-stu-id="4f5ca-p102">Sign up for Office 365 delegated administration. Before you can start administering a customer's account, they must authorize you as a delegated administrator. To obtain their approval, you first [send them an offer for delegated administration](https://go.microsoft.com/fwlink/?LinkId=396829). (You can also offer delegated administration to your customer at a later time.)</span></span>

3. <span data-ttu-id="4f5ca-115">使用 "[添加或删除委派管理员](https://go.microsoft.com/fwlink/?LinkId=396831)" 中的步骤创建委派的管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="4f5ca-115">Create the delegated admin account using the steps in [Add or delete a delegated admin](https://go.microsoft.com/fwlink/?LinkId=396831).</span></span>

<span data-ttu-id="4f5ca-116">访问[合作伙伴：建立您的业务和管理您的 Office 365 合作伙伴帐户](https://go.microsoft.com/fwlink/?LinkId=301485)，了解有关如何设置 Office 365 委派管理的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4f5ca-116">Visit [Partners: Build your business and administer your Office 365 partner account](https://go.microsoft.com/fwlink/?LinkId=301485) for more information about how to set up Office 365 delegated administration.</span></span>
  
 <span data-ttu-id="4f5ca-117">**问：我是客户，不是经销商，我应该如何为我的子租户设置委派管理员？**</span><span class="sxs-lookup"><span data-stu-id="4f5ca-117">**Q. I'm a customer, not a reseller, how can set up delegated administrator for my sub-tenants?**</span></span>
  
<span data-ttu-id="4f5ca-p103">答：委派管理目前仅适用于经销商和合作伙伴。但是，我们提供了一个示例 Windows PowerShell 脚本，可帮助您将策略应用到您的子租户（公司）。有关详细信息，请参阅[将 EOP 设置应用到多个租户的示例脚本](sample-script-for-applying-eop-settings-to-multiple-tenants.md)。</span><span class="sxs-lookup"><span data-stu-id="4f5ca-p103">A. Delegated administration is only available for resellers and partners at this time. However, we've provided a sample Windows PowerShell script that will help you apply policies to your sub-tenants (companies). For more information, see [Sample script for applying EOP settings to multiple tenants](sample-script-for-applying-eop-settings-to-multiple-tenants.md).</span></span>
  
 <span data-ttu-id="4f5ca-122">**问：能否防止子租户管理员修改我的策略？**</span><span class="sxs-lookup"><span data-stu-id="4f5ca-122">**Q. Can I prevent my sub-tenant admin from modifying my policy?**</span></span>
  
<span data-ttu-id="4f5ca-p104">答：Office 365 目前不具备此功能。</span><span class="sxs-lookup"><span data-stu-id="4f5ca-p104">A. Office 365 does not currently have this capability.</span></span>
  
 <span data-ttu-id="4f5ca-125">**问：能否将所有子租户的报告合并在一起？**</span><span class="sxs-lookup"><span data-stu-id="4f5ca-125">**Q. Can I get consolidated reporting across all of my sub-tenants?**</span></span>
  
<span data-ttu-id="4f5ca-126">A.</span><span class="sxs-lookup"><span data-stu-id="4f5ca-126">A.</span></span> <span data-ttu-id="4f5ca-127">目前, 跨你管理的公司的合并报告不适用于 Microsoft 365 管理中心报告。</span><span class="sxs-lookup"><span data-stu-id="4f5ca-127">Consolidated reporting across the companies you manage is not available for the Microsoft 365 admin center reports at this time.</span></span> <span data-ttu-id="4f5ca-128">但是, 可以使用远程 Windows PowerShell 或[报告 web 服务](https://go.microsoft.com/fwlink/?LinkId=279926)执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4f5ca-128">However, you can do this by using remote Windows PowerShell or the [reporting web service](https://go.microsoft.com/fwlink/?LinkId=279926).</span></span>
