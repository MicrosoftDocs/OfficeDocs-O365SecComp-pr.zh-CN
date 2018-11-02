---
title: 发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/01/2018
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
ms.openlocfilehash: 0f58f9f2270c8be38b3ea2ea81f04656eb10e7fb
ms.sourcegitcommit: 83406a3258e722020e46a82bbf4bc9d5d8a326ca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25899653"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="c2ed1-103">发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址</span><span class="sxs-lookup"><span data-stu-id="c2ed1-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="c2ed1-p101">如果用户从为垃圾邮件分类的 Office 365 持续发送电子邮件，它们将阻止发送任何详细消息。用户将列在作为错误出站发件人的服务，并将接收未送达报告 (NDR) 的状态：</span><span class="sxs-lookup"><span data-stu-id="c2ed1-p101">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="c2ed1-p102">无法将发送消息，因为您未被识别为有效的发件人。最常见原因是您的电子邮件地址可疑的垃圾邮件的发送和已不再允许发送组织外部的邮件。与电子邮件管理员联系以寻求帮助。 远程服务器返回 550 5.1.8 访问被拒绝，错误的出站发件人</span><span class="sxs-lookup"><span data-stu-id="c2ed1-p102">Your message couldn't be delivered because you weren't recognized as a valid sender. The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization. Contact your email admin for assistance.  Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

<span data-ttu-id="c2ed1-p103">您可以配置出站垃圾邮件策略设置，以便在 Office 365 用户阻止发送电子邮件时收到通知。解决用户邮箱的问题后，您可以删除的阻止的发件人。</span><span class="sxs-lookup"><span data-stu-id="c2ed1-p103">You can configure your outbound spam policy settings so that you get a notification when an Office 365 user is blocked from sending email. After the problem with the user's mailbox is resolved, you can remove the block on that sender.</span></span>
  
## <a name="unblock-a-blocked-office-365-email-account"></a><span data-ttu-id="c2ed1-112">解除对被阻止的 Office 365 电子邮件帐户的阻止</span><span class="sxs-lookup"><span data-stu-id="c2ed1-112">Unblock a blocked Office 365 email account</span></span>

<span data-ttu-id="c2ed1-p104">完成此任务中的 Office 365 安全性和合规性中心 (SCC)。有关 SCC 的详细信息[转到 Office 365 安全性和合规性中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="c2ed1-p104">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span>

1. <span data-ttu-id="c2ed1-115">使用具有 Office 365 全局管理员权限，登录到 Office 365 安全性和合规性中心和在左侧列表中，展开**威胁管理**，选择**查看**，然后选择**受限的工作或学校帐户用户**。</span><span class="sxs-lookup"><span data-stu-id="c2ed1-115">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="c2ed1-116">若要直接转到**受限制的用户**页上 （之前被称为操作中心） 中的安全&amp;合规性中心，使用以下 URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="c2ed1-116">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="c2ed1-p105">此页将包含已被阻止发送到组织外部的邮件的用户列表。 查找想要在删除限制，然后单击它在**取消阻止**用户。</span><span class="sxs-lookup"><span data-stu-id="c2ed1-p105">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="c2ed1-119">单击**是**以确认更改。</span><span class="sxs-lookup"><span data-stu-id="c2ed1-119">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="c2ed1-p106">没有帐户可以取消由租户管理员的次数限制如果已超出限制的用户，将显示一条错误消息。然后，您将需要联系支持取消阻止用户。</span><span class="sxs-lookup"><span data-stu-id="c2ed1-p106">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span></br></br> <span data-ttu-id="c2ed1-122">可能需要用户未被阻止之前 1 小时。</span><span class="sxs-lookup"><span data-stu-id="c2ed1-122">It may take up to 1 hour before the user is unblocked.</span></span>
  
## <a name="third-party-block-lists"></a><span data-ttu-id="c2ed1-123">第三方阻止列表</span><span class="sxs-lookup"><span data-stu-id="c2ed1-123">Third-party block lists</span></span>

<span data-ttu-id="c2ed1-p107">Exchange Online Protection 还使用第三方阻止列表来帮助在垃圾邮件筛选决策。可以添加用户、 网站、 域和 IP 地址阻止列表仅为显示在垃圾邮件。为 Office 365 管理中心中，您应尝试获取如果属于您从第三方列表提供程序中删除这些对象。</span><span class="sxs-lookup"><span data-stu-id="c2ed1-p107">Exchange Online Protection also uses third-party block lists to help make decisions in spam filtering. Users, websites, domains, and IP addresses can be added to block lists just for appearing in a spam message. As the Office 365 admin, you should try to get these objects removed from the third-party list providers if they belong to you.</span></span>

> [!NOTE]
> <span data-ttu-id="c2ed1-p108">如果 Office 365 外部的某个人无法将邮件发送给您的 Office 365 帐户，其帐户可能在外部的阻止发件人列表。Office 365 以外的用户可以尝试使用[自助服务除名门户](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)删除本身。</span><span class="sxs-lookup"><span data-stu-id="c2ed1-p108">If someone outside Office 365 cannot send messages to your Office 365 account, their account may be on the external blocked senders list. Users outside Office 365 can try to remove themselves by using the [self-service delisting portal](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span></span> 

## <a name="for-more-information"></a><span data-ttu-id="c2ed1-129">详细信息</span><span class="sxs-lookup"><span data-stu-id="c2ed1-129">For more information</span></span>

[<span data-ttu-id="c2ed1-130">响应受到攻击的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="c2ed1-130">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="c2ed1-131">配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="c2ed1-131">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="c2ed1-132">出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="c2ed1-132">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

  

  

