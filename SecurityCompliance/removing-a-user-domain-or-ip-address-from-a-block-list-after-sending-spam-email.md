---
title: 发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/05/2018
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
ms.openlocfilehash: 6665c405c62f75b77e7898419ebcfbc1c8c20f4c
ms.sourcegitcommit: 7b85c22fc85ec19e4b44a07e91bfa9ade768185a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "23998606"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="7347c-103">发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址</span><span class="sxs-lookup"><span data-stu-id="7347c-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="7347c-p101">如果用户从为垃圾邮件分类的 Office 365 持续发送电子邮件，它们将阻止发送任何详细消息。用户将列在作为错误出站发件人的服务，并将接收未送达报告 (NDR) 的状态：</span><span class="sxs-lookup"><span data-stu-id="7347c-p101">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="7347c-p102">无法将发送消息，因为您未被识别为有效的发件人。最常见原因是您的电子邮件地址可疑的垃圾邮件的发送和已不再允许发送组织外部的邮件。与电子邮件管理员联系以寻求帮助。 远程服务器返回 550 5.1.8 访问被拒绝，错误的出站发件人</span><span class="sxs-lookup"><span data-stu-id="7347c-p102">Your message couldn't be delivered because you weren't recognized as a valid sender. The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization. Contact your email admin for assistance.  Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

<span data-ttu-id="7347c-p103">您可以配置出站垃圾邮件策略设置，以便在 Office 365 用户阻止发送电子邮件时收到通知。解决用户邮箱的问题后，您可以删除的阻止的发件人。</span><span class="sxs-lookup"><span data-stu-id="7347c-p103">You can configure your outbound spam policy settings so that you get a notification when an Office 365 user is blocked from sending email. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="7347c-112">解除对被阻止的 Office 365 电子邮件帐户的阻止</span><span class="sxs-lookup"><span data-stu-id="7347c-112">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="7347c-p104">完成此任务中的 Office 365 安全性和合规性中心 (SCC)。有关 SCC 的详细信息[转到 Office 365 安全性和合规性中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7347c-p104">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span>

1. <span data-ttu-id="7347c-115">使用具有 Office 365 全局管理员权限，登录到 Office 365 安全性和合规性中心和在左侧列表中，展开**威胁管理**，选择**查看**，然后选择**受限的工作或学校帐户用户**。</span><span class="sxs-lookup"><span data-stu-id="7347c-115">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="7347c-116">若要直接转到安全中的**受限制的用户**页上&amp;合规性中心，使用以下 URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="7347c-116">To go directly to the **Restricted Users** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="7347c-p105">此页将包含已被阻止发送到组织外部的邮件的用户列表。 查找想要在删除限制，然后单击它在**取消阻止**用户。</span><span class="sxs-lookup"><span data-stu-id="7347c-p105">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="7347c-119">单击**是**以确认更改。</span><span class="sxs-lookup"><span data-stu-id="7347c-119">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="7347c-p106">没有帐户可以取消由租户管理员的次数限制如果已超出限制的用户，将显示一条错误消息。然后，您将需要联系支持取消阻止用户。</span><span class="sxs-lookup"><span data-stu-id="7347c-p106">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span>
  
## <a name="third-party-block-lists"></a><span data-ttu-id="7347c-122">第三方阻止列表</span><span class="sxs-lookup"><span data-stu-id="7347c-122">Third-party block lists</span></span>

<span data-ttu-id="7347c-p107">Exchange Online Protection 还使用第三方阻止列表来帮助在垃圾邮件筛选决策。可以添加用户、 网站、 域和 IP 地址阻止列表仅为显示在垃圾邮件。为 Office 365 管理中心中，您应尝试获取如果属于您从第三方列表提供程序中删除这些对象。使用中的链接表，每个第三方联系人，然后按照其说明下方。</span><span class="sxs-lookup"><span data-stu-id="7347c-p107">Exchange Online Protection also uses third-party block lists to help make decisions in spam filtering. Users, websites, domains, and IP addresses can be added to block lists just for appearing in a spam message. As the Office 365 admin, you should try to get these objects removed from the third-party list providers if they belong to you. Use the links in the below table to contact each third party and then follow their instructions.</span></span>

|<span data-ttu-id="7347c-127">**列表名称**</span><span class="sxs-lookup"><span data-stu-id="7347c-127">**List Name**</span></span>|<span data-ttu-id="7347c-128">**除名门户**</span><span class="sxs-lookup"><span data-stu-id="7347c-128">**Delisting Portal**</span></span>|<span data-ttu-id="7347c-129">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="7347c-129">**For more information**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7347c-130">URIBL</span><span class="sxs-lookup"><span data-stu-id="7347c-130">URIBL</span></span>  <br/> |[https://admin.uribl.com/?section=lookup](https://admin.uribl.com/?section=lookup) <br/> |[<span data-ttu-id="7347c-131">URIBL 网站</span><span class="sxs-lookup"><span data-stu-id="7347c-131">URIBL website </span></span>](https://uribl.com/) <br/> |
|<span data-ttu-id="7347c-132">SURBL</span><span class="sxs-lookup"><span data-stu-id="7347c-132">SURBL</span></span>  <br/> |[http://www.surbl.org/surbl-analysis](http://www.surbl.org/surbl-analysis) <br/> |[<span data-ttu-id="7347c-133">介绍 SURBL URI 信誉数据</span><span class="sxs-lookup"><span data-stu-id="7347c-133">Introducing SURBL URI reputation data</span></span>](http://www.surbl.org/) <br/> |
|<span data-ttu-id="7347c-134">Spamhaus </span><span class="sxs-lookup"><span data-stu-id="7347c-134">Spamhaus</span></span>  <br/> |[https://www.spamhaus.org/lookup/](https://www.spamhaus.org/lookup/) <br/> |[<span data-ttu-id="7347c-135">了解 DNSBL 筛选</span><span class="sxs-lookup"><span data-stu-id="7347c-135">Understanding DNSBL Filtering</span></span>](https://www.spamhaus.org/whitepapers/dnsbl_function/) <br/> |
|<span data-ttu-id="7347c-136">invaluement</span><span class="sxs-lookup"><span data-stu-id="7347c-136">invaluement</span></span>  <br/> |[http://dnsbl.invaluement.com/lookup/](http://dnsbl.invaluement.com/lookup/) <br/> |[<span data-ttu-id="7347c-137">invaluement 反垃圾邮件列表</span><span class="sxs-lookup"><span data-stu-id="7347c-137">invaluement anti-spam list</span></span>](http://dnsbl.invaluement.com/) <br/> |
|<span data-ttu-id="7347c-138">Phishtank</span><span class="sxs-lookup"><span data-stu-id="7347c-138">Phishtank</span></span>  <br/> |[https://www.phishtank.com/](https://www.phishtank.com/) <br/> |[<span data-ttu-id="7347c-139">PhishTank 常见问题</span><span class="sxs-lookup"><span data-stu-id="7347c-139">PhishTank FAQ</span></span>](https://www.phishtank.com/faq.php) <br/> |

> [!NOTE]
> <span data-ttu-id="7347c-p108">如果 Office 365 外部的某个人无法将邮件发送给您的 Office 365 帐户，其帐户可能在外部的阻止发件人列表。Office 365 以外的用户可以尝试使用[自助服务除名门户](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)删除本身。</span><span class="sxs-lookup"><span data-stu-id="7347c-p108">If someone outside Office 365 cannot send messages to your Office 365 account, their account may be on the external blocked senders list. Users outside Office 365 can try to remove themselves by using the [self-service delisting portal](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span></span> 

## <a name="for-more-information"></a><span data-ttu-id="7347c-142">更多信息</span><span class="sxs-lookup"><span data-stu-id="7347c-142">For more information</span></span>

[<span data-ttu-id="7347c-143">响应受到攻击的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="7347c-143">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="7347c-144">配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="7347c-144">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="7347c-145">出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="7347c-145">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

  

  

