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
description: 如果用户连续发送来自被分类为垃圾邮件的 Office 365 的电子邮件, 则会阻止发送更多的邮件。
ms.openlocfilehash: 3ffd8b65d6994699093237e9f9a0a3aaa802f5e2
ms.sourcegitcommit: a80bd8626720fabdf592b84e4424cd3a83d08280
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30223081"
---
# <a name="removing-a-user-domain-or-ip-address-from-a-block-list-after-sending-spam-email"></a><span data-ttu-id="69eac-103">发送垃圾电子邮件后，从阻止列表中删除用户、域或 IP 地址</span><span class="sxs-lookup"><span data-stu-id="69eac-103">Removing a user, domain, or IP address from a block list after sending spam email</span></span>

<span data-ttu-id="69eac-p101">如果用户连续发送来自被分类为垃圾邮件的 Office 365 的电子邮件, 则会阻止发送更多的邮件。用户将在服务中列为错误的出站发件人, 并将收到一份状态为的未送达报告 (NDR):</span><span class="sxs-lookup"><span data-stu-id="69eac-p101">If a user continuously sends email messages from Office 365 that is classified as spam, they will be blocked from sending any more messages. The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

- <span data-ttu-id="69eac-p102">无法传递你的邮件, 因为你未被识别为有效发件人。导致此问题的最常见原因是, 您的电子邮件地址怀疑发送垃圾邮件, 并且不再允许它在您的组织外部发送邮件。请联系你的电子邮件管理员以获取帮助。 远程服务器返回 "550 5.1.8 访问被拒绝, 错误的出站发件人"</span><span class="sxs-lookup"><span data-stu-id="69eac-p102">Your message couldn't be delivered because you weren't recognized as a valid sender. The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send messages outside of your organization. Contact your email admin for assistance.  Remote Server returned '550 5.1.8 Access denied, bad outbound sender'</span></span>

<span data-ttu-id="69eac-110">租户管理员还会收到一条警报, 指示用户已受到限制, 无法发送任何更多的出站邮件。</span><span class="sxs-lookup"><span data-stu-id="69eac-110">The tenant admins will also receive an alert stating that the user has been restricted from sending any more outbound messages.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="69eac-111">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="69eac-111">What do you need to know before you begin?</span></span>
<span data-ttu-id="69eac-112"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="69eac-112"></span></span>

<span data-ttu-id="69eac-113">估计完成时间：5 分钟</span><span class="sxs-lookup"><span data-stu-id="69eac-113">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="69eac-p103">您需要先分配权限, 然后才能执行此过程或过程。若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的 "反垃圾邮件" 条目。</span><span class="sxs-lookup"><span data-stu-id="69eac-p103">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

<span data-ttu-id="69eac-p104">还可以通过远程 PowerShell 执行以下过程。使用 BlockedSenderAddress cmdlet 获取受限制的用户列表, 并删除-BlockedSenderAddress 以删除限制。若要了解如何使用 Windows PowerShell 连接到 exchange online, 请参阅[连接到 exchange online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="69eac-p104">The following procedure can also be performed via remote PowerShell. Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction. To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="69eac-119">删除对被阻止的 Office 365 电子邮件帐户的限制</span><span class="sxs-lookup"><span data-stu-id="69eac-119">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="69eac-p105">您可以在 Office 365 Security & 合规中心 (SCC) 中完成此任务。有关 SCC 的更多详细信息,[请转到 Office 365 安全 & 合规中心](go-to-the-securitycompliance-center.md)。必须在 "**组织管理**" 或 "**安全管理员**" 角色组中, 才能执行这些功能。有关 SCC 角色组的详细信息,[请转到 Office 365 安全 & 合规中心中的 "权限"](permissions-in-the-security-and-compliance-center.md) 。</span><span class="sxs-lookup"><span data-stu-id="69eac-p105">You complete this task in the Office 365 Security & Compliance Center (SCC). [Go to the Office 365 Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC. You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions. [Go to Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="69eac-124">使用具有 office 365 全局管理员权限的工作或学校帐户登录到 office 365 安全性和合规性中心, 并在左侧的列表中展开 "**威胁管理**", 选择 "**查看**", 然后选择 "**受限"用户**。</span><span class="sxs-lookup"><span data-stu-id="69eac-124">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="69eac-125">若要直接转到安全&amp;合规性中心中的 "**受限用户**" 页 (以前称为 "操作中心"), 请使用以下 URL: >[https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="69eac-125">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="69eac-p106">此页面将包含已阻止向组织外部发送邮件的用户的列表。 查找要删除限制的用户, 然后单击 "**取消阻止**"。</span><span class="sxs-lookup"><span data-stu-id="69eac-p106">This page will contain the list of users that have been blocked from sending mail to outside of your organization.  Find the user you wish to remove restrictions on and then click on **Unblock**.</span></span>

3. <span data-ttu-id="69eac-128">单击 **"是"** 确认更改。</span><span class="sxs-lookup"><span data-stu-id="69eac-128">Click **Yes** to confirm the change.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="69eac-p107">限制某个帐户可被租户管理员取消阻止的次数。如果超过了用户的限制, 将显示一条错误消息。你将需要联系支持人员以取消阻止用户。</span><span class="sxs-lookup"><span data-stu-id="69eac-p107">There's a limit to the number of times that an account can be unblocked by the tenant admin. If the limit for a user has been exceeded, an error message appears. You will then need to contact Support to unblock the user.</span></span><br/><br/> <span data-ttu-id="69eac-131">在用户取消阻止之前, 可能需要长达1小时。</span><span class="sxs-lookup"><span data-stu-id="69eac-131">It may take up to 1 hour before the user is unblocked.</span></span>
  
## <a name="third-party-block-lists"></a><span data-ttu-id="69eac-132">第三方阻止列表</span><span class="sxs-lookup"><span data-stu-id="69eac-132">Third-party block lists</span></span>

<span data-ttu-id="69eac-p108">Exchange Online Protection 还使用第三方阻止列表来帮助在垃圾邮件筛选中做出决定。可以将用户、网站、域和 IP 地址添加到阻止列表中, 只是在垃圾邮件中显示。作为 Office 365 管理员, 如果用户属于您, 应尝试从第三方列表提供程序中删除这些对象。</span><span class="sxs-lookup"><span data-stu-id="69eac-p108">Exchange Online Protection also uses third-party block lists to help make decisions in spam filtering. Users, websites, domains, and IP addresses can be added to block lists just for appearing in a spam message. As the Office 365 admin, you should try to get these objects removed from the third-party list providers if they belong to you.</span></span>

> [!NOTE]
> <span data-ttu-id="69eac-p109">如果 office 365 外部的人员无法向您的 Office 365 帐户发送邮件, 则其帐户可能位于外部阻止发件人列表中。Office 365 之外的用户可以尝试使用[自助服务除名门户](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis)删除自己。</span><span class="sxs-lookup"><span data-stu-id="69eac-p109">If someone outside Office 365 cannot send messages to your Office 365 account, their account may be on the external blocked senders list. Users outside Office 365 can try to remove themselves by using the [self-service delisting portal](https://docs.microsoft.com/en-us/office365/SecurityCompliance/use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis).</span></span> 

## <a name="for-more-information"></a><span data-ttu-id="69eac-138">更多信息</span><span class="sxs-lookup"><span data-stu-id="69eac-138">For more information</span></span>

[<span data-ttu-id="69eac-139">响应已泄露的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="69eac-139">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="69eac-140">配置出站垃圾邮件策略</span><span class="sxs-lookup"><span data-stu-id="69eac-140">Configure the outbound spam policy</span></span>](configure-the-outbound-spam-policy.md)
  
[<span data-ttu-id="69eac-141">出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="69eac-141">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="69eac-142">Office 365 安全 & 合规中心中的权限</span><span class="sxs-lookup"><span data-stu-id="69eac-142">Permissions in the Office 365 Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

  

