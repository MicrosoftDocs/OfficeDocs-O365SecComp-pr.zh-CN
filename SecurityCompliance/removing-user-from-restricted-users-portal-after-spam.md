---
title: 发送垃圾电子邮件后，从受限用户门户删除用户
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 03/12/2019
audience: ITPro
ms.topic: article
f1_keywords:
- ms.exch.eac.ActionCenter.Restricted.Users.RestrictedUsers
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 712cfcc1-31e8-4e51-8561-b64258a8f1e5
ms.collection:
- M365-security-compliance
description: 如果用户不断发送来自受分类为垃圾邮件的 Office 365 的电子邮件, 则会受到限制, 无法发送更多的邮件。
ms.openlocfilehash: 80eb03ccb96f2178f168139234de8700b9b97e29
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35601149"
---
# <a name="removing-a-user-from-the-restricted-users-portal-after-sending-spam-email"></a><span data-ttu-id="48f99-103">发送垃圾电子邮件后，从受限用户门户删除用户</span><span class="sxs-lookup"><span data-stu-id="48f99-103">Removing a user from the Restricted Users portal after sending spam email</span></span>

<span data-ttu-id="48f99-104">如果用户持续发送的电子邮件是来自 Office 365 的垃圾邮件, 则他们将受到限制, 无法发送电子邮件, 但仍然能够收到。</span><span class="sxs-lookup"><span data-stu-id="48f99-104">If a user continuously sends emails that are classified as spam from Office 365, they will be restricted from sending email, but will still be able to receive it.</span></span> <span data-ttu-id="48f99-105">用户将在服务中列为错误的出站发件人, 并将收到一份状态为的未送达报告 (NDR):</span><span class="sxs-lookup"><span data-stu-id="48f99-105">The user will be listed in the service as a bad outbound sender and will receive a Non-Delivery Report (NDR) that states:</span></span>

> <span data-ttu-id="48f99-106">无法传递你的消息, 因为你未被识别为有效的发件人。</span><span class="sxs-lookup"><span data-stu-id="48f99-106">"Your message couldn't be delivered because you weren't recognized as a valid sender.</span></span> <span data-ttu-id="48f99-107">导致此问题的最常见原因是, 你的电子邮件地址怀疑发送垃圾邮件, 并且不再允许它发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="48f99-107">The most common reason for this is that your email address is suspected of sending spam and it's no longer allowed to send email.</span></span>  <span data-ttu-id="48f99-108">请联系你的电子邮件管理员以获取帮助。</span><span class="sxs-lookup"><span data-stu-id="48f99-108">Contact  your email admin for assistance.</span></span> <span data-ttu-id="48f99-109">远程服务器返回 "550 5.1.8 访问被拒绝, 错误的出站发件人"。</span><span class="sxs-lookup"><span data-stu-id="48f99-109">Remote Server returned '550 5.1.8 Access denied, bad outbound sender."</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="48f99-110">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="48f99-110">What do you need to know before you begin?</span></span>
<span data-ttu-id="48f99-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="48f99-111"></span></span>

<span data-ttu-id="48f99-112">估计完成时间：5 分钟</span><span class="sxs-lookup"><span data-stu-id="48f99-112">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="48f99-113">您必须先获得权限，然后才能执行此过程或多个过程。</span><span class="sxs-lookup"><span data-stu-id="48f99-113">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="48f99-114">若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的 "反垃圾邮件" 条目。</span><span class="sxs-lookup"><span data-stu-id="48f99-114">To see what permissions you need, see the "Anti-spam entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span>

<span data-ttu-id="48f99-115">还可以通过远程 PowerShell 执行以下过程。</span><span class="sxs-lookup"><span data-stu-id="48f99-115">The following procedure can also be performed via remote PowerShell.</span></span> <span data-ttu-id="48f99-116">使用 BlockedSenderAddress cmdlet 获取受限制的用户列表, 并删除-BlockedSenderAddress 以删除限制。</span><span class="sxs-lookup"><span data-stu-id="48f99-116">Use the Get-BlockedSenderAddress cmdlet to get the list of restricted users and Remove-BlockedSenderAddress to remove the restriction.</span></span> <span data-ttu-id="48f99-117">若要了解如何使用 Windows PowerShell 连接到 Exchange Online，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。</span><span class="sxs-lookup"><span data-stu-id="48f99-117">To learn how to use Windows PowerShell to connect to Exchange Online, see [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).</span></span>

## <a name="remove-restrictions-for-a-blocked-office-365-email-account"></a><span data-ttu-id="48f99-118">删除对被阻止的 Office 365 电子邮件帐户的限制</span><span class="sxs-lookup"><span data-stu-id="48f99-118">Remove restrictions for a blocked Office 365 email account</span></span>

<span data-ttu-id="48f99-119">您在安全 & 合规中心 (SCC) 中完成此任务。</span><span class="sxs-lookup"><span data-stu-id="48f99-119">You complete this task in the Security & Compliance Center (SCC).</span></span> <span data-ttu-id="48f99-120">有关 SCC 的更多详细信息,[请转到 Security & 合规性中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="48f99-120">[Go to the Security & Compliance Center](go-to-the-securitycompliance-center.md) for more details about SCC.</span></span> <span data-ttu-id="48f99-121">必须在 "**组织管理**" 或 "**安全管理员**" 角色组中, 才能执行这些功能。</span><span class="sxs-lookup"><span data-stu-id="48f99-121">You need to be in the **Organization Management** or the **Security Administrator** role group in order to perform these functions.</span></span> <span data-ttu-id="48f99-122">若要详细了解 SCC 角色组,[请转到 Security & 合规性中心中的 "权限"](permissions-in-the-security-and-compliance-center.md) 。</span><span class="sxs-lookup"><span data-stu-id="48f99-122">[Go to Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) for more details about SCC role groups.</span></span>

1. <span data-ttu-id="48f99-123">使用具有 Office 365 全局管理员权限的工作或学校帐户登录到 Office 365 安全性和合规性中心, 并在左侧的列表中展开 "**威胁管理**", 选择 "**查看**", 然后选择 "**受限"用户**。</span><span class="sxs-lookup"><span data-stu-id="48f99-123">Using a work or school account that has Office 365 global administrator privileges, sign into the Office 365 Security and Compliance Center and in the list on the left, expand **Threat Management**, choose **Review**, and then choose **Restricted Users**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="48f99-124">若要直接转到安全&amp;合规性中心中的 "**受限用户**" 页 (以前称为 "操作中心"), 请使用以下 URL: >[https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span><span class="sxs-lookup"><span data-stu-id="48f99-124">To go directly to the **Restricted Users** page (formerly known as the Action Center) in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/#/restrictedusers](https://protection.office.com/?hash=/restrictedusers)</span></span>

2. <span data-ttu-id="48f99-125">此页面将包含已阻止发送电子邮件的用户的列表。</span><span class="sxs-lookup"><span data-stu-id="48f99-125">This page will contain the list of users that have been blocked from sending email.</span></span>  <span data-ttu-id="48f99-126">查找要从中删除限制的用户, 然后选择 "**取消阻止**"。</span><span class="sxs-lookup"><span data-stu-id="48f99-126">Find the user you wish to remove restrictions from, and select **Unblock**.</span></span>

3. <span data-ttu-id="48f99-127">飞出将进入有关其发送受限的帐户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="48f99-127">A fly-out will go into the details about the account whose sending is restricted.</span></span> <span data-ttu-id="48f99-128">应仔细考虑这些建议, 以确保在帐户实际受到危害时采取正确的措施。</span><span class="sxs-lookup"><span data-stu-id="48f99-128">You should go through the recommendations to ensure you're taking the proper actions in case the account is actually compromised.</span></span> <span data-ttu-id="48f99-129">完成后, 单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="48f99-129">Click **Next** when done.</span></span>

4. <span data-ttu-id="48f99-130">下一个屏幕提供了有助于防止将来受到危害的建议。</span><span class="sxs-lookup"><span data-stu-id="48f99-130">The next screen has recommendations to help prevent future compromise.</span></span> <span data-ttu-id="48f99-131">启用多重身份验证 (MFA) 和更改密码是一项良好的防御措施。</span><span class="sxs-lookup"><span data-stu-id="48f99-131">Enabling multi-factor authentication (MFA) and changing the passwords are a good defense.</span></span> <span data-ttu-id="48f99-132">完成后, 单击 "**取消阻止用户**"。</span><span class="sxs-lookup"><span data-stu-id="48f99-132">Click **Unblock user** when done.</span></span>

5. <span data-ttu-id="48f99-133">单击 **"是"** 确认更改。</span><span class="sxs-lookup"><span data-stu-id="48f99-133">Click **Yes** to confirm the change.</span></span>

    > [!NOTE]
    > <span data-ttu-id="48f99-134">删除限制可能需要30分钟或更长时间。</span><span class="sxs-lookup"><span data-stu-id="48f99-134">It may take 30 minutes or more before restrictions are removed.</span></span> 

## <a name="making-sure-admins-are-alerted-when-this-happens"></a><span data-ttu-id="48f99-135">确保在发生此情况时提醒管理员</span><span class="sxs-lookup"><span data-stu-id="48f99-135">Making sure admins are alerted when this happens</span></span>

<span data-ttu-id="48f99-136">"Office 365 Security & 合规性警报策略" 页下的 "将受限制的用户发送电子邮件" 警报作为策略提供。</span><span class="sxs-lookup"><span data-stu-id="48f99-136">A "User restricted from sending email" alert is available as a policy under the Office 365 Security & Compliance Alert policies page.</span></span> <span data-ttu-id="48f99-137">这是以前的出站垃圾邮件策略, 但现在是 Office 365 警报平台的本地。</span><span class="sxs-lookup"><span data-stu-id="48f99-137">This was formerly the outbound spam policy but is now native to the Office 365 alerting platform.</span></span> <span data-ttu-id="48f99-138">有关通知的详细信息, 请转到[Security & 合规性中心中的 "通知策略](alert-policies.md)"。</span><span class="sxs-lookup"><span data-stu-id="48f99-138">Go to [Alert policies in the Security & Compliance Center](alert-policies.md) for more information on alerts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="48f99-139">若要使警报正常运行, 必须打开审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="48f99-139">For alerts to work, audit log search must to be turned on.</span></span> <span data-ttu-id="48f99-140">有关详细信息, 请参阅如何[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="48f99-140">See how to [Turn Office 365 audit log search on or off](turn-audit-log-search-on-or-off.md) for more information.</span></span>

<span data-ttu-id="48f99-141">此警报的策略是默认策略, 并附带每个 Office 365 租户, 无需进行设置。</span><span class="sxs-lookup"><span data-stu-id="48f99-141">The policy for this alert is a default one and comes with every Office 365 tenant and does not need to be set up.</span></span> <span data-ttu-id="48f99-142">它被视为高严重性警报, 当用户被限制发送邮件时, 将通过电子邮件通知已配置的 TenantAdmins 组。</span><span class="sxs-lookup"><span data-stu-id="48f99-142">It is considered a High severity alert and will email the configured TenantAdmins group when the alert is fired whenever a user has been restricted from sending mail.</span></span> <span data-ttu-id="48f99-143">管理员可以通过转到 SCC 门户 > 警报 > 通知策略 > 受限制发送电子邮件的用户) 在此通知发生警报时更新组通知。</span><span class="sxs-lookup"><span data-stu-id="48f99-143">Admins can update the group notified when this alert happens by going to the alert under the SCC portal > Alerts > Alert policies > Users restricted from sending email.</span></span>

<span data-ttu-id="48f99-144">你可以将此通知编辑为:</span><span class="sxs-lookup"><span data-stu-id="48f99-144">You will be able to Edit the alert to:</span></span>
- <span data-ttu-id="48f99-145">打开/关闭电子邮件通知</span><span class="sxs-lookup"><span data-stu-id="48f99-145">Turn email notifications On/Off</span></span>
- <span data-ttu-id="48f99-146">通过电子邮件发送所需收件人</span><span class="sxs-lookup"><span data-stu-id="48f99-146">Email the required recipients</span></span>
- <span data-ttu-id="48f99-147">限制每天获取的通知</span><span class="sxs-lookup"><span data-stu-id="48f99-147">Limit the notifications you get per day</span></span>

## <a name="for-more-information"></a><span data-ttu-id="48f99-148">详细信息</span><span class="sxs-lookup"><span data-stu-id="48f99-148">For more information</span></span>

[<span data-ttu-id="48f99-149">响应已泄露的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="48f99-149">Responding to a compromised email account</span></span>](responding-to-a-compromised-email-account.md)

[<span data-ttu-id="48f99-150">了解限制发送电子邮件通知的用户</span><span class="sxs-lookup"><span data-stu-id="48f99-150">Understanding the User restricted from sending email alert</span></span>](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)

[<span data-ttu-id="48f99-151">出站邮件的高风险传递池</span><span class="sxs-lookup"><span data-stu-id="48f99-151">High-risk delivery pool for outbound messages</span></span>](high-risk-delivery-pool-for-outbound-messages.md)

[<span data-ttu-id="48f99-152">安全与合规中心内的权限</span><span class="sxs-lookup"><span data-stu-id="48f99-152">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)

[<span data-ttu-id="48f99-153">安全 & 合规中心中的警报策略</span><span class="sxs-lookup"><span data-stu-id="48f99-153">Alert policies in the Security & Compliance Center</span></span>](https://docs.microsoft.com/en-us/office365/securitycompliance/alert-policies)
