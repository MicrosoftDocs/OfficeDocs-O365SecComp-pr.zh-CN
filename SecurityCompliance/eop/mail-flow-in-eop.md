---
title: EOP 中的邮件流
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: e109077e-cc85-4c19-ae40-d218ac7d0548
description: 作为 Exchange Online Protection (EOP) 客户，发送到您的组织的所有邮件都将先通过 EOP，然后工作人员才能看到这些邮件。不论您是在云中托管所有 Exchange Online 邮箱，还是在本地托管邮箱（称为独立方案），为了继续利用现有基础结构，您可以选择如何路由邮件，这些邮件将首先通过 EOP 处理，然后才能路由到工作人员收件箱。
ms.openlocfilehash: 2081aff8da44244a1476b51eed49e5f23a5a9b9a
ms.sourcegitcommit: 361aab46b1bb295ed2dcc1a417ac81f699b8ff78
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2019
ms.locfileid: "36676755"
---
# <a name="mail-flow-in-eop"></a><span data-ttu-id="8bea7-104">EOP 中的邮件流</span><span class="sxs-lookup"><span data-stu-id="8bea7-104">Mail flow in EOP</span></span>

<span data-ttu-id="8bea7-p102">作为 Exchange Online Protection (EOP) 客户，发送到您的组织的所有邮件都将先通过 EOP，然后工作人员才能看到这些邮件。不论您是在云中托管所有 Exchange Online 邮箱，还是在本地托管邮箱（称为独立方案），为了继续利用现有基础结构，您可以选择如何路由邮件，这些邮件将首先通过 EOP 处理，然后才能路由到工作人员收件箱。</span><span class="sxs-lookup"><span data-stu-id="8bea7-p102">As an Exchange Online Protection (EOP) customer, all messages sent to your organization pass through EOP before your workers see them. Whether you host all of your mailboxes in the cloud with Exchange Online, or you host your mailboxes on premises (called a standalone scenario), perhaps to continue taking advantage of your existing infrastructure, you have options about how to route messages that will pass through EOP for processing before they are routed to your worker inboxes.</span></span>
  
<span data-ttu-id="8bea7-p103">您可能需要配置自定义邮件路由，使邮件传递满足您的业务要求。例如，您可以通过策略筛选装置传递所有出站邮件。</span><span class="sxs-lookup"><span data-stu-id="8bea7-p103">You may want to configure custom mail routing to conform your messaging to a business requirement. For instance, you can pass all of your outbound mail through a policy-filtering appliance.</span></span>
  
## <a name="working-with-messages-and-message-access-options"></a><span data-ttu-id="8bea7-109">使用邮件和邮件访问选项</span><span class="sxs-lookup"><span data-stu-id="8bea7-109">Working with messages and message access options</span></span>

<span data-ttu-id="8bea7-p104">EOP 在您的邮件路由方式上提供了很大的灵活性。以下主题说明了邮件流过程中的步骤。</span><span class="sxs-lookup"><span data-stu-id="8bea7-p104">EOP offers a lot of flexibility in how your messages are routed. The following topics explain steps in the mail flow process.</span></span>
  
<span data-ttu-id="8bea7-112">[使用基于目录的边缘阻止拒绝发送给无效收件人的邮件](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)介绍基于目录的边缘阻止功能, 该功能使您可以在服务网络外围拒绝对无效收件人的邮件。</span><span class="sxs-lookup"><span data-stu-id="8bea7-112">[Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking) Describes the Directory Based Edge Blocking feature which lets you reject messages for invalid recipients at the service network perimeter.</span></span> 
  
<span data-ttu-id="8bea7-113">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)介绍了如何管理与 EOP 服务相关的域。</span><span class="sxs-lookup"><span data-stu-id="8bea7-113">[View or Edit Managed Domains in EOP](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) describes how to manage domains that are associated with your EOP service.</span></span>
  
<span data-ttu-id="8bea7-114">如果将子域添加到组织，则 EOP 服务也可以帮助您管理这些子域。</span><span class="sxs-lookup"><span data-stu-id="8bea7-114">If you add subdomains to your organization, your EOP service can help you manage these too.</span></span> <span data-ttu-id="8bea7-115">有关子域的详细信息, 请参阅在[Exchange Online 中为子域启用邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)。</span><span class="sxs-lookup"><span data-stu-id="8bea7-115">Learn more about subdomains at [Enable mail flow for subdomains in Exchange Online](https://docs.microsoft.com/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>
  
<span data-ttu-id="8bea7-p106">[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)介绍了连接器以及如何使用连接器自定义邮件路由。方案包括确保与合作伙伴组织进行安全通信，并设置智能主机。</span><span class="sxs-lookup"><span data-stu-id="8bea7-p106">[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) introduces connectors and shows how you can use them to customize mail routing. Scenarios include ensuring secure communication with a partner organization and setting up a smart host.</span></span>
  
<span data-ttu-id="8bea7-118">若要确保将垃圾邮件正确路由到每个用户的垃圾邮件文件夹, 您必须执行几个配置步骤。</span><span class="sxs-lookup"><span data-stu-id="8bea7-118">To ensure that junk email is routed correctly to each user's junk-email folder, you must perform a couple configuration steps.</span></span> <span data-ttu-id="8bea7-119">在[确保垃圾邮件被路由到每个用户的 "垃圾邮件" 文件夹](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)时, 会对这些信息进行详细说明。</span><span class="sxs-lookup"><span data-stu-id="8bea7-119">These are detailed in [Ensure that spam is routed to each user's Junk Email folder](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="8bea7-120">如果不想将邮件移动到每个用户的垃圾邮件文件夹, 则可以通过在 Exchange 管理中心中编辑内容筛选器策略来选择另一个操作。</span><span class="sxs-lookup"><span data-stu-id="8bea7-120">If you do not want to move messages to each user's junk-email folder, you may choose another action by editing your content filter policies in the Exchange admin center.</span></span> <span data-ttu-id="8bea7-121">有关详细信息，请参阅[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8bea7-121">For more information, see [Configure your spam filter policies](../configure-your-spam-filter-policies.md).</span></span>
  
## <a name="verify-mail-flow"></a><span data-ttu-id="8bea7-122">验证邮件流</span><span class="sxs-lookup"><span data-stu-id="8bea7-122">Verify mail flow</span></span>

<span data-ttu-id="8bea7-p108">要验证包括连接器配置在内的 EOP 安装是否正常工作，请参阅[设置 EOP 服务](set-up-your-eop-service.md)中的"您如何知道此任务有效？"部分。</span><span class="sxs-lookup"><span data-stu-id="8bea7-p108">To verify that your EOP setup, including your connector configuration, is working correctly, see the "How do you know this task worked?" section in [Set up your EOP service](set-up-your-eop-service.md).</span></span>
  
<span data-ttu-id="8bea7-125">[通过验证 Office 365 连接器测试邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)提供了有关测试您的邮件流设置正确的说明。</span><span class="sxs-lookup"><span data-stu-id="8bea7-125">[Test mail flow by validating your Office 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow) provides instructions for testing that your mail flow is set up correctly.</span></span>
