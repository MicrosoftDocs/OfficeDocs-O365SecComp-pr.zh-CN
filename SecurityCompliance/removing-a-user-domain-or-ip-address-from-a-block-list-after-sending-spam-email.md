---
title: 发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/20/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
description: 如果用户从为垃圾邮件分类的 Office 365 持续发送电子邮件，它们将阻止发送任何详细消息。
ms.openlocfilehash: 87b7083fe1345a15ea582f12a5b0d417bbe6b568
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002587"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="97a39-103">发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址</span><span class="sxs-lookup"><span data-stu-id="97a39-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="97a39-104">如果用户从为垃圾邮件分类的 Office 365 持续发送电子邮件，它们将阻止发送任何详细消息。</span><span class="sxs-lookup"><span data-stu-id="97a39-104">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages.</span></span> 
  
<span data-ttu-id="97a39-105">当发件人阻止发送电子邮件消息时，他们将收到未送达报告 （NDR 或无法发送邮件的电子邮件），提供有关所必须采取取消阻止自己的步骤的特定信息。</span><span class="sxs-lookup"><span data-stu-id="97a39-105">When a sender is blocked from sending emails messages, they receive a Non-Delivery Report (NDR or email failed to send message) that provides specific information about the steps that they have to take to unblock themselves.</span></span>
  
<span data-ttu-id="97a39-p101">不仅可以通过服务，而特定网站域，阻止各个用户，还会阻止 IP 地址。在某些情况下，域或网站可以被添加到阻止列表只是因为它们出现在垃圾邮件。为 Office 365 管理中心中，您可以尝试获取用户、 网站、 域和从第三方阻止列表删除 IP 地址。使用本主题底部表中的链接联系，每个第三方，然后按照说明进行操作。如果 Office 365 外部的某个人无法将邮件发送给您的 Office 365 帐户，其帐户可能外部阻止发件人列表上已结束。Office 365 以外的用户可以尝试通过使用[自助服务除名门户](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx)中将自己删除被阻止的发件人名单。</span><span class="sxs-lookup"><span data-stu-id="97a39-p101">Not only can individual users be blocked by the service, but specific websites, domains, and IP addresses can also be blocked. In some cases, domains or websites can be added to a block list just because they appear in a spam message. As the Office 365 admin, you can try to get users, websites, domains, and IP addresses removed from third-party block lists. Use the links in the table at the bottom of this topic to contact each third party, and then follow the instructions. If someone outside Office 365 cannot send messages to your Office 365 account, their account may have ended up on the external blocked senders list. Users outside Office 365 can try to remove themselves from the blocked senders list by using the [self-service delisting portal](https://technet.microsoft.com/library/mt661881%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="97a39-p102">您可以配置出站垃圾邮件设置，以便在 Office 365 用户阻止发送为垃圾邮件分类的电子邮件时获取 anotification。解决用户邮箱的问题后，您可以删除的阻止的发件人。</span><span class="sxs-lookup"><span data-stu-id="97a39-p102">You can configure outbound spam settings so that you get anotification when an Office 365 user is blocked from sending email that's classified as spam. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="97a39-114">解除对被阻止的 Office 365 电子邮件帐户的阻止</span><span class="sxs-lookup"><span data-stu-id="97a39-114">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="97a39-p103">完成 Exchange 管理员中心 (EAC) 中的此任务。有关 EAC 的详细信息，请查看[Exchange 管理员中心在 Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md) 。</span><span class="sxs-lookup"><span data-stu-id="97a39-p103">You complete this task in the Exchange admin center (EAC). Check out [Exchange admin center in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md) for details about the EAC.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="97a39-117">只有在 Exchange Online 的 EAC 中才能看到操作中心。</span><span class="sxs-lookup"><span data-stu-id="97a39-117">You won't see the action center unless you're in the EAC for Exchange Online.</span></span> 
  
1. <span data-ttu-id="97a39-118">在 EAC 中，导航到**保护** \> **操作中心**。</span><span class="sxs-lookup"><span data-stu-id="97a39-118">In the EAC, navigate to **protection** \> **action center**.</span></span>
    
    ![导航至 Exchange 管理中心的操作中心。](media/9bbf0844-7b34-4a86-a2b7-8c7e9c8519a3.png)
  
2. <span data-ttu-id="97a39-120">选择**搜索**图标，然后输入阻止用户的 SMTP 地址。</span><span class="sxs-lookup"><span data-stu-id="97a39-120">Select the **Search** icon, and then enter the SMTP address of the blocked user.</span></span> 
    
    ![在操作中心搜索受阻止的用户](media/f931b5a0-7115-4d95-9f6f-b403436031ba.png)
  
3. <span data-ttu-id="97a39-122">在说明窗格中，单击**取消阻止客户**。</span><span class="sxs-lookup"><span data-stu-id="97a39-122">Click **Unblock Account** in the description pane.</span></span> 
    
    ![在操作中心取消阻止用户](media/c5d5b1b9-8416-45aa-9631-881e94d1d056.png)
  
4. <span data-ttu-id="97a39-124">单击**是**以确认更改。</span><span class="sxs-lookup"><span data-stu-id="97a39-124">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="97a39-p104">没有帐户可以取消由租户管理员的次数限制如果已超出限制的用户，将显示一条错误消息。若要取消阻止用户的联系人支持。</span><span class="sxs-lookup"><span data-stu-id="97a39-p104">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. Contact Support to unblock the user.</span></span> 
  
## <a name="third-party-block-lists"></a><span data-ttu-id="97a39-127">第三方阻止列表</span><span class="sxs-lookup"><span data-stu-id="97a39-127">Third-party block lists</span></span>

|<span data-ttu-id="97a39-128">**列表名称**</span><span class="sxs-lookup"><span data-stu-id="97a39-128">**List Name**</span></span>|<span data-ttu-id="97a39-129">**除名门户**</span><span class="sxs-lookup"><span data-stu-id="97a39-129">**Delisting Portal**</span></span>|<span data-ttu-id="97a39-130">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="97a39-130">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="97a39-131">URIBL</span><span class="sxs-lookup"><span data-stu-id="97a39-131">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="97a39-132">URIBL 网站</span><span class="sxs-lookup"><span data-stu-id="97a39-132">URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="97a39-133">SURBL</span><span class="sxs-lookup"><span data-stu-id="97a39-133">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="97a39-134">介绍 SURBL URI 信誉数据</span><span class="sxs-lookup"><span data-stu-id="97a39-134">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="97a39-135">Spamhaus </span><span class="sxs-lookup"><span data-stu-id="97a39-135">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="97a39-136">了解 DNSBL 筛选</span><span class="sxs-lookup"><span data-stu-id="97a39-136">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="97a39-137">invaluement</span><span class="sxs-lookup"><span data-stu-id="97a39-137">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="97a39-138">invaluement 反垃圾邮件列表</span><span class="sxs-lookup"><span data-stu-id="97a39-138">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="97a39-139">Phishtank</span><span class="sxs-lookup"><span data-stu-id="97a39-139">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="97a39-140">PhishTank 常见问题</span><span class="sxs-lookup"><span data-stu-id="97a39-140">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |
   
> [!NOTE]
> <span data-ttu-id="97a39-141">Exchange Online Protection 还使用第三方阻止列表的垃圾邮件筛选。</span><span class="sxs-lookup"><span data-stu-id="97a39-141">Exchange Online Protection also uses third-party block lists for spam filtering.</span></span> 
   
## <a name="for-more-information"></a><span data-ttu-id="97a39-142">详细信息</span><span class="sxs-lookup"><span data-stu-id="97a39-142">For more information</span></span>

[<span data-ttu-id="97a39-143">配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="97a39-143">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="97a39-144">出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="97a39-144">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="97a39-145">使用除名门户来将自己从 Office 365 阻止的发件人名单中删除</span><span class="sxs-lookup"><span data-stu-id="97a39-145">Use the delist portal to remove yourself from the Office 365 blocked senders list</span></span>](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)
  

  

