---
title: 配置出站垃圾邮件策略
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/10/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
description: 如果您使用出站垃圾邮件筛选来发送出站电子邮件，那么将始终启用该服务，从而保护使用此服务的组织及其目标收件人。
ms.openlocfilehash: 3a3e07731e16da148131ceb6f555e84ed94f7ae5
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026299"
---
# <a name="configure-the-outbound-spam-policy"></a><span data-ttu-id="b6dc1-103">配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="b6dc1-103">Configure the outbound spam policy</span></span>

<span data-ttu-id="b6dc1-p101">如果您使用出站垃圾邮件筛选来发送出站电子邮件，那么将始终启用该服务，从而保护使用此服务的组织及其目标收件人。与入站筛选类似，出站垃圾邮件筛选由连接筛选和内容筛选构成，但出站筛选设置无法配置。如果出站邮件确定为垃圾邮件，则会通过高风险传送池进行路由，这会降低正常出站 IP 池添加到阻止列表的可能性。如果客户继续通过该服务发送出站垃圾邮件，其邮件的发送将受到阻止。尽管无法禁用或更改出站垃圾邮件筛选，但您可以通过默认出站垃圾邮件策略来配置几个全公司的出站垃圾邮件设置。</span><span class="sxs-lookup"><span data-stu-id="b6dc1-p101">Outbound spam filtering is always enabled if you use the service for sending outbound email, thereby protecting organizations using the service and their intended recipients. Similar to inbound filtering, outbound spam filtering is comprised of connection filtering and content filtering, however the outbound filter settings are not configurable. If an outbound message is determined to be spam, it is routed through the higher risk delivery pool, which reduces the probability of the normal outbound-IP pool being added to a block list. If a customer continues to send outbound spam through the service, they will be blocked from sending messages. Although outbound spam filtering cannot be disabled or changed, you can configure several company-wide outbound spam settings via the default outbound spam policy.</span></span> 
  
<span data-ttu-id="b6dc1-109">以下视频显示了如何配置出站垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="b6dc1-109">The following video shows how to configure the outbound spam policy:</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/1f20d655-0d3d-4141-9cae-e57f5a6cffe8?autoplay=false]
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b6dc1-110">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="b6dc1-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="b6dc1-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="b6dc1-111"></span></span>

<span data-ttu-id="b6dc1-112">估计完成时间：5 分钟</span><span class="sxs-lookup"><span data-stu-id="b6dc1-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="b6dc1-p102">您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅"反垃圾邮件[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的条目。</span><span class="sxs-lookup"><span data-stu-id="b6dc1-p102">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
  
<span data-ttu-id="b6dc1-115">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="b6dc1-115">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
  
<span data-ttu-id="b6dc1-p103">也可以通过远程 PowerShell 执行以下过程。使用[Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) cmdlet 可以查看您的设置，并[设置 HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx)编辑您的出站垃圾邮件策略设置。若要了解如何使用 Windows PowerShell 连接到 Exchange Online Protection，请参阅[Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290)。若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="b6dc1-p103">The following procedure can also be performed via remote PowerShell. Use the [Get-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/8f15c83c-c10a-4d9d-b135-35321430bdc2.aspx) cmdlet to review your settings, and the [Set-HostedOutboundSpamFilterPolicy](http://technet.microsoft.com/library/665d1b04-d4b5-4a0e-811a-4e37096ccbfd.aspx) to edit your outbound spam policy settings. To learn how to use Windows PowerShell to connect to Exchange Online Protection, see [Connect to Exchange Online Protection PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627290). To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>
  
## <a name="use-the-eac-to-edit-the-default-outbound-spam-policy"></a><span data-ttu-id="b6dc1-120">使用 EAC 编辑默认出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="b6dc1-120">Use the EAC to edit the default outbound spam policy</span></span>
<span data-ttu-id="b6dc1-121"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="b6dc1-121"></span></span>

<span data-ttu-id="b6dc1-122">使用以下步骤编辑默认出站垃圾邮件策略：</span><span class="sxs-lookup"><span data-stu-id="b6dc1-122">Use the following procedure to edit the default outbound spam policy:</span></span>
  
### <a name="to-configure-the-default-outbound-spam-policy"></a><span data-ttu-id="b6dc1-123">要配置默认出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="b6dc1-123">To configure the default outbound spam policy</span></span>

1. <span data-ttu-id="b6dc1-124">在 Exchange 管理员中心 (EAC) 中，导航到**保护** \> **出站垃圾邮件**，然后双击默认策略。</span><span class="sxs-lookup"><span data-stu-id="b6dc1-124">In the Exchange admin center (EAC), navigate to **Protection** \> **Outbound spam**, and then double-click the default policy.</span></span>
    
2. <span data-ttu-id="b6dc1-125">选择**出站垃圾邮件首选项**菜单选项。</span><span class="sxs-lookup"><span data-stu-id="b6dc1-125">Select the **Outbound spam preferences** menu option.</span></span> 
    
3. <span data-ttu-id="b6dc1-126">选中以下与出站邮件有关的复选框，然后在显示的输入框中指定关联的电子邮件地址或地址（如果这些地址解析为有效 SMTP 目标，则它们可能是通讯组列表）：</span><span class="sxs-lookup"><span data-stu-id="b6dc1-126">Select the following check boxes pertaining to outbound messages, and then specify an associated email address or addresses in the accompanying input box (these can be distribution lists if they resolve as valid SMTP destinations):</span></span>
    
1. <span data-ttu-id="b6dc1-p104">**发送到的以下电子邮件地址或地址的所有可疑出站电子邮件的副本**。这些是由 （无论 scl) 筛选器标记为垃圾邮件的邮件。它们不被拒绝由筛选器，但通过高风险传送池路由。用分号分隔多个地址。请注意，以指定的收件人将收到邮件密件抄送 (Bcc) 地址 (From 且到字段的原始发件人和收件人)。</span><span class="sxs-lookup"><span data-stu-id="b6dc1-p104">**Send a copy of all suspicious outbound email messages to the following email address or addresses**. These are messages that are marked as spam by the filter (regardless of the SCL rating). They are not rejected by the filter but are routed through the higher risk delivery pool. Separate multiple addresses with a semicolon. Note that the recipients specified will receive the messages as a Blind carbon copy (Bcc) address (the From and To fields are the original sender and recipient).</span></span>
    
2. <span data-ttu-id="b6dc1-p105">**发送通知发件人被阻止发送出站垃圾邮件时的以下电子邮件地址**。用分号分隔多个地址。</span><span class="sxs-lookup"><span data-stu-id="b6dc1-p105">**Send a notification to the following email address when a sender is blocked sending outbound spam**. Separate multiple addresses with a semicolon.</span></span>
    
    <span data-ttu-id="b6dc1-p106">当大量垃圾邮件源自特定用户时，该用户将被禁止发送电子邮件。使用该设置指定的域管理员将收到该用户的出站邮件被阻止的通知。若要查看此通知的样式，请参阅[发件人被阻止发送出站垃圾邮件时的示例通知](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)。有关重新启用的详细信息，请参阅[Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b6dc1-p106">When a significant amount of spam is originating from a particular user, the user is disabled from sending email messages. The administrator for the domain, who is specified using this setting, will be informed that outbound messages are blocked for this user. To see what this notification looks like, see [Sample notification when a sender is blocked sending outbound spam](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md). For information about getting re-enabled, see [Removing a user, domain, or IP address from a block list after sending spam email](http://technet.microsoft.com/library/712cfcc1-31e8-4e51-8561-b64258a8f1e5.aspx).</span></span>
    
4. <span data-ttu-id="b6dc1-p107">单击**保存**。在右窗格中显示的默认策略设置摘要。</span><span class="sxs-lookup"><span data-stu-id="b6dc1-p107">Click **save**. A summary of your default policy settings appears in the right pane.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="b6dc1-140">详细信息</span><span class="sxs-lookup"><span data-stu-id="b6dc1-140">For more information</span></span>
<span data-ttu-id="b6dc1-141"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="b6dc1-141"></span></span>

[<span data-ttu-id="b6dc1-142">出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="b6dc1-142">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)
  
[<span data-ttu-id="b6dc1-143">反垃圾邮件保护常见问题</span><span class="sxs-lookup"><span data-stu-id="b6dc1-143">Anti-spam protection FAQ</span></span>](anti-spam-protection-faq.md)
  

