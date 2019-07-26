---
title: 发送垃圾电子邮件后，从受限用户门户删除用户
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/10/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 如果用户从 Office 365 连续发送被归类为垃圾邮件的电子邮件，这些用户将被限制发送任何其他电子邮件。
ms.openlocfilehash: 56f1a34fe4b47a722ff1dace73dd001f0c4812a2
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854716"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a><span data-ttu-id="1e889-103">发送垃圾电子邮件后，从受限用户门户删除用户</span><span class="sxs-lookup"><span data-stu-id="1e889-103">Removing a user from the Restricted Users portal after sending spam email</span></span>

<span data-ttu-id="1e889-104">如果用户从 Office 365 连续发送被归类为垃圾邮件的电子邮件，这些用户将被限制发送电子邮件，但仍然能够接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1e889-104">If a user continuously sends emails that are classified as spam from Office 365, they will be restricted from sending email, but will still be able to receive it.</span></span> <span data-ttu-id="1e889-105">该用户将在服务中列为错误的出站发件人，并且将收到未送达报告 (NDR)，其中指出：</span><span class="sxs-lookup"><span data-stu-id="1e889-105">The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

> <span data-ttu-id="1e889-106">“你的邮件无法送达，因为系统认为你不是有效的发件人。</span><span class="sxs-lookup"><span data-stu-id="1e889-106">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="1e889-107">这种情形最常见的原因是怀疑你的电子邮件地址正在发送垃圾邮件，且不再允许它发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1e889-107">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="1e889-108">请联系电子邮件管理员获取帮助。</span><span class="sxs-lookup"><span data-stu-id="1e889-108">Contact  your email admin for assistance.</span></span> <span data-ttu-id="1e889-109">远程服务器返回“550 5.1.8 拒绝访问，错误出站发件人”。</span><span class="sxs-lookup"><span data-stu-id="1e889-109">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="1e889-110">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="1e889-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="1e889-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="1e889-111"></span></span>

<span data-ttu-id="1e889-112">估计完成时间：5 分钟</span><span class="sxs-lookup"><span data-stu-id="1e889-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="1e889-113">您必须先获得权限，然后才能执行此过程或多个过程。</span><span class="sxs-lookup"><span data-stu-id="1e889-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="1e889-114">若要查看所需的权限，请参阅 [Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的“反垃圾邮件”条目。</span><span class="sxs-lookup"><span data-stu-id="1e889-114">To see what permissions you need, see the Anti-spam entry in the [Feature permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

<span data-ttu-id="1e889-115">以下步骤也可以通过远程 PowerShell 执行。</span><span class="sxs-lookup"><span data-stu-id="1e889-115">The following connection filter procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="1e889-116">使用 Get-BlockedSenderAddress cmdlet 获取受限用户的列表，并使用 Remove-BlockedSenderAddress  移除限制。</span><span class="sxs-lookup"><span data-stu-id="1e889-116">Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction.</span></span> <span data-ttu-id="1e889-117">若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="1e889-117">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="1e889-118">移除对阻止的 Office 365 电子邮件帐户的限制</span><span class="sxs-lookup"><span data-stu-id="1e889-118">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="1e889-119">可在安全与合规中心 (SCC) 中完成此任务。</span><span class="sxs-lookup"><span data-stu-id="1e889-119">You complete this task in the Security & Compliance Center (SCC).</span></span> <span data-ttu-id="1e889-120">有关 SCC 的详细信息, 请[转到安全与合规中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1e889-120">[Go to the Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span> <span data-ttu-id="1e889-121">若要执行这些功能，你需要在 **“组织管理”** 或 **“安全管理员”** 角色组中。</span><span class="sxs-lookup"><span data-stu-id="1e889-121">You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions.</span></span> <span data-ttu-id="1e889-122">有关 SCC 角色组的更多详细信息，请[转到安全与合规中心中的“权限”](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="1e889-122">[Go to Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="1e889-123">使用具有 office 365 全局管理员权限的工作或学校帐户登录到 office 365 安全与合规中心，然后在左侧的列表中展开 **“威胁管理”**，选择 **“审阅”**，然后选择 **“受限用户”**。</span><span class="sxs-lookup"><span data-stu-id="1e889-123">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="1e889-124">若要直接转到安全&amp;合规中心中的 **“受限用户”** 页面（以前称为“操作中心”），请使用此 URL：> [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="1e889-124">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="1e889-125">此页面将包含已被阻止发送电子邮件的用户的列表。</span><span class="sxs-lookup"><span data-stu-id="1e889-125">This page will contain the list of users that have been blocked from sending email.</span></span>  <span data-ttu-id="1e889-126">查找想要为其移除限制的用户，然后选择 **“取消阻止”**。</span><span class="sxs-lookup"><span data-stu-id="1e889-126">Find the user you wish to remove restrictions from, and select **Unblock**.</span></span>

3. <span data-ttu-id="1e889-127">一个飞出窗口将转到有关其发送受限的帐户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1e889-127">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="1e889-128">应按照建议进行操作，确保在帐户实际遭到破坏的情况下采取适当的措施。</span><span class="sxs-lookup"><span data-stu-id="1e889-128">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="1e889-129">完成后，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="1e889-129">Click **Next** when it's done.</span></span>

4. <span data-ttu-id="1e889-130">下一个屏幕包含可帮助防止以后遭到破坏的建议。</span><span class="sxs-lookup"><span data-stu-id="1e889-130">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="1e889-131">启用多重身份验证 (MFA) 和更改密码是一种很好的防御措施。</span><span class="sxs-lookup"><span data-stu-id="1e889-131">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="1e889-132">完成后，单击 **“解锁用户”**。</span><span class="sxs-lookup"><span data-stu-id="1e889-132">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="1e889-133">单击 **“是”** 确认更改。</span><span class="sxs-lookup"><span data-stu-id="1e889-133">Click **Yes**  to confirm the change.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1e889-134">移除限制可能需要 30 分钟或更长时间。</span><span class="sxs-lookup"><span data-stu-id="1e889-134">It may take 30 minutes or more before restrictions are removed.</span></span> 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a><span data-ttu-id="1e889-135">确保在这种情况下提醒管理员</span><span class="sxs-lookup"><span data-stu-id="1e889-135">Making sure admins are alerted when this happens</span></span>

<span data-ttu-id="1e889-136">Office 365 安全与合规性警报策略页下有一条“被限制发送电子邮件的用户”警报策略。</span><span class="sxs-lookup"><span data-stu-id="1e889-136">A "User restricted from sending email" alert is available as a policy under the Office 365 Security & Compliance Alert policies page.</span></span> <span data-ttu-id="1e889-137">此策略以前是出站垃圾邮件策略，但现在是 Office 365 警报平台的原生策略。</span><span class="sxs-lookup"><span data-stu-id="1e889-137">This was formerly the outbound spam policy but is now native to the Office 365 alerting platform.</span></span> <span data-ttu-id="1e889-138">有关警报的详细信息，请转到[安全与合规中心中的警报策略](alert-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1e889-138">Go to [Alert policies in the Security & Compliance Center](alert-policies.md) for more information on alerts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1e889-139">为了警报正常工作，必须启用审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="1e889-139">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="1e889-140">有关详细信息，请参阅[启用或禁用 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="1e889-140">See how to [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md) for more information.</span></span>

<span data-ttu-id="1e889-141">此警报的策略是默认策略，随每个 Office 365 租户提供，无需进行设置。</span><span class="sxs-lookup"><span data-stu-id="1e889-141">The policy for this alert is a default one and comes with every Office 365 tenant and does not need to be set up.</span></span> <span data-ttu-id="1e889-142">它被视为一种严重性警报，每当用户被限制发送电子邮件时，都会在触发警报时向配置的 TenantAdmins 组发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1e889-142">It is considered a High severity alert and will email the configured TenantAdmins group when the alert is fired whenever a user has been restricted from sending mail.</span></span> <span data-ttu-id="1e889-143">管理员可通过转到 SCC 门户 >“警报”>“警报策略”>“被限制发送电子邮件的用户”，更新在发生警报时收到通知的组。</span><span class="sxs-lookup"><span data-stu-id="1e889-143">Admins can update the group notified when this alert happens by going to the alert under the SCC portal > Alerts > Alert policies > Users restricted from sending email.</span></span>

<span data-ttu-id="1e889-144">你将能够编辑警报以便执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1e889-144">You will be able to Edit the alert to:</span></span>
- <span data-ttu-id="1e889-145">打开/关闭电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="1e889-145">Turn email notifications On/Off</span></span>
- <span data-ttu-id="1e889-146">向所需的收件人发送电子邮件</span><span class="sxs-lookup"><span data-stu-id="1e889-146">Email the required recipients</span></span>
- <span data-ttu-id="1e889-147">限制每天收到的通知</span><span class="sxs-lookup"><span data-stu-id="1e889-147">Limit the notifications you get per day</span></span>

## <a name="checking-for-and-removing-restrictions-using-powershell"></a><span data-ttu-id="1e889-148">使用 PowerShell 检查和移除限制</span><span class="sxs-lookup"><span data-stu-id="1e889-148">Checking for and removing restrictions using PowerShell</span></span>
<span data-ttu-id="1e889-149">适用于受限用户的 PowerShell 命令包括：</span><span class="sxs-lookup"><span data-stu-id="1e889-149">The PowerShell commands for Restricted Users are:</span></span>
- <span data-ttu-id="1e889-150">`Get-BlockedSenderAddress`：运行以检索被限制发送电子邮件的用户的列表</span><span class="sxs-lookup"><span data-stu-id="1e889-150">`Get-BlockedSenderAddress`: Run to retreive the list of users that are restricted from sending email</span></span>
- <span data-ttu-id="1e889-151">`Remove-BlockedSenderAddress`：运行以解除用户限制</span><span class="sxs-lookup"><span data-stu-id="1e889-151">`Remove-BlockedSenderAddress`: Run to remove user(s) from being restricted</span></span>

## <a name="for-more-information"></a><span data-ttu-id="1e889-152">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="1e889-152">For more information</span></span>

[<span data-ttu-id="1e889-153">响应遭到入侵的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="1e889-153">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

<span data-ttu-id="1e889-154">
  [了解“被限制发送电子邮件的用户”警报](https://docs.microsoft.com/zh-CN/office365/securitycompliance/alert-policies)</span><span class="sxs-lookup"><span data-stu-id="1e889-154">[Understanding the User restricted from sending email alert](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)</span></span>

[<span data-ttu-id="1e889-155">出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="1e889-155">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="1e889-156">安全与合规中心内的权限</span><span class="sxs-lookup"><span data-stu-id="1e889-156">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

<span data-ttu-id="1e889-157">
  [安全与合规中心内的警报策略](https://docs.microsoft.com/zh-CN/office365/securitycompliance/alert-policies)</span><span class="sxs-lookup"><span data-stu-id="1e889-157">[Alert policies in the Office 365 Security & Compliance Center](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)</span></span>
