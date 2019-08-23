---
title: 查找并调查在 Office 365 中传递的恶意电子邮件、TIMailData、安全事件、事件、ATP Powershell、电子邮件恶意软件、已泄露的用户、电子邮件网络钓鱼诈骗、电子邮件恶意软件、阅读电子邮件头、阅读邮件头、打开电子邮件头
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 08/07/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 了解如何使用威胁调查和响应功能查找和调查恶意电子邮件。
ms.openlocfilehash: 25eb1f4a13ad698d7b6817ea7917ccabea7210ae
ms.sourcegitcommit: f473bf7f215ba4eb2f49e0dd23a9d2e39fa512c9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "36566220"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="41cff-103">查找并调查 Office 365 中提供的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="41cff-103">Find and investigate malicious email that was delivered in Office 365</span></span>

<span data-ttu-id="41cff-104">[Office 365 高级威胁防护](office-365-atp.md)使您能够调查让用户面临风险的活动, 并采取措施来保护您的组织。</span><span class="sxs-lookup"><span data-stu-id="41cff-104">[Office 365 Advanced Threat Protection](office-365-atp.md) enables you to investigate activities that put your users at risk and take action to protect your organization.</span></span> <span data-ttu-id="41cff-105">例如, 如果您是组织的安全团队的一部分, 则可以查找并调查传递给用户的可疑电子邮件。</span><span class="sxs-lookup"><span data-stu-id="41cff-105">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered to your users.</span></span> <span data-ttu-id="41cff-106">可以使用[威胁资源管理器 (或实时检测)](threat-explorer.md)执行此操作。</span><span class="sxs-lookup"><span data-stu-id="41cff-106">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="41cff-107">开始之前 .。。</span><span class="sxs-lookup"><span data-stu-id="41cff-107">Before you begin...</span></span>

<span data-ttu-id="41cff-108">请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="41cff-108">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="41cff-109">您的组织具有[Office 365 高级威胁防护](office-365-atp.md), 并将[许可证分配给用户](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="41cff-109">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) and [licenses are assigned to users](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>
    
- <span data-ttu-id="41cff-110">为你的组织启用了[Office 365 审核日志记录](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="41cff-110">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="41cff-111">您的组织具有为反垃圾邮件、反恶意软件、反网络钓鱼等定义的策略。</span><span class="sxs-lookup"><span data-stu-id="41cff-111">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="41cff-112">请参阅防御[Office 365 中的威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="41cff-112">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="41cff-113">您是 Office 365 全局管理员, 或者您具有安全管理员或在安全&amp;合规中心中分配的搜索和清除角色。</span><span class="sxs-lookup"><span data-stu-id="41cff-113">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="41cff-114">请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="41cff-114">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="dealing-with-suspicious-emails"></a><span data-ttu-id="41cff-115">处理可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="41cff-115">Dealing with suspicious emails</span></span>

<span data-ttu-id="41cff-116">恶意攻击者可能会向你的用户发送邮件, 以尝试对其凭据进行网络钓鱼并获取对公司机密的访问权限!</span><span class="sxs-lookup"><span data-stu-id="41cff-116">Malicious attackers may be sending mail to your users to try and phish their credentials and gain access to your corporate secrets!</span></span> <span data-ttu-id="41cff-117">为避免这种情况, 应使用 Office 365 中的威胁防护服务, 包括[Exchange Online protection](eop/exchange-online-protection-overview.md)和[高级威胁防护](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="41cff-117">To prevent this, you should use the threat protection services in Office 365, including [Exchange Online Protection](eop/exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="41cff-118">但是, 有时攻击者可能会向包含 URL 的用户发送邮件, 并在稍后使该 URL 指向恶意内容 (恶意软件等)。</span><span class="sxs-lookup"><span data-stu-id="41cff-118">However, there are times when an attacker could send mail to your users containing a URL and only later on make that URL point to malicious content (malware, etc.).</span></span> 

<span data-ttu-id="41cff-119">或者, 您可能会发现您的组织中的某个用户已受到威胁, 而该用户受到威胁时, 攻击者使用该帐户向公司中的其他用户发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="41cff-119">Alternately, you may realize too late that a user in your organization has been compromised, and while that user was compromised, an attacker used that account to send email to other users in your company.</span></span> <span data-ttu-id="41cff-120">在清理这两个方案的过程中, 您可能需要从用户收件箱中删除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="41cff-120">As part of cleaning up both of these scenarios, you may want to remove email messages from user inboxes.</span></span> <span data-ttu-id="41cff-121">在这种情况下, 您可以利用[威胁浏览器 (或实时检测)](threat-explorer.md)来查找和删除这些电子邮件!</span><span class="sxs-lookup"><span data-stu-id="41cff-121">In situations like these, you can leverage [Threat Explorer (or real-time detections)](threat-explorer.md) to find and remove those email messages!</span></span>

## <a name="where-re-routed-emails-are-located-after-actions-are-taken"></a><span data-ttu-id="41cff-122">在执行操作后, 重新路由的电子邮件位于何处</span><span class="sxs-lookup"><span data-stu-id="41cff-122">Where re-routed emails are located after actions are taken</span></span>

<span data-ttu-id="41cff-123">那么, 在哪里有问题的电子邮件, 以及哪些工具可帮助调查人员了解他们会怎么办？</span><span class="sxs-lookup"><span data-stu-id="41cff-123">So where do problem emails go, and what tools help investigators understand what happened to them?</span></span> <span data-ttu-id="41cff-124">威胁资源管理器字段报告可帮助管理员解码问题电子邮件事件的信息。</span><span class="sxs-lookup"><span data-stu-id="41cff-124">Threat Explorer fields report information that will help Admins decode problem email events.</span></span>

### <a name="view-the-email-headers-and-download-the-email-body"></a><span data-ttu-id="41cff-125">查看电子邮件头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="41cff-125">View the email headers and download the email body</span></span>

<span data-ttu-id="41cff-126">电子邮件**头预览和下载电子邮件正文**是威胁资源管理器中可用的有用的电子邮件威胁管理功能。</span><span class="sxs-lookup"><span data-stu-id="41cff-126">**Email header preview, and download of the email body** are helpful email threat management features available in Threat Explorer.</span></span> <span data-ttu-id="41cff-127">管理员将能够分析和下载邮件头和电子邮件的威胁。</span><span class="sxs-lookup"><span data-stu-id="41cff-127">Admins will be able to analyse and download headers and emails for threats.</span></span> <span data-ttu-id="41cff-128">使用此功能的访问权限由基于角色的访问控制 (RBAC) 控制, 以降低用户电子邮件内容泄露的风险。</span><span class="sxs-lookup"><span data-stu-id="41cff-128">Access to use this feature is controlled by roles-based access control (RBAC), to reduce the risk of exposure of user email contents.</span></span>

<span data-ttu-id="41cff-129">必须将名为 "Preview" 的新*角色*添加到另一个 Office 365 角色组 (例如, 在 sec 操作 (或 sec 管理员) 中, 以授予在所有电子邮件视图中下载邮件和预览邮件头的功能。</span><span class="sxs-lookup"><span data-stu-id="41cff-129">A new *role*, called 'Preview' must be added into another Office 365 role group (for example into sec operations, or sec admin) to grant the ability to download mails and preview headers in all-emails view.</span></span>

<span data-ttu-id="41cff-130">若要查看包含您的电子邮件下载和电子邮件头预览选项的浮出控件:</span><span class="sxs-lookup"><span data-stu-id="41cff-130">To see the flyout with your email download and email header preview options:</span></span> 

1. <span data-ttu-id="41cff-131">请转[https://protection.office.com](https://protection.office.com)到使用 Office 365 的工作或学校帐户登录并登录。</span><span class="sxs-lookup"><span data-stu-id="41cff-131">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="41cff-132">这会将您带到&amp;安全合规中心。</span><span class="sxs-lookup"><span data-stu-id="41cff-132">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="41cff-133">在左侧导航中, 选择 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="41cff-133">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>

3. <span data-ttu-id="41cff-134">单击 "威胁资源管理器" 表中的主题。</span><span class="sxs-lookup"><span data-stu-id="41cff-134">Click on a subject in the Threat Explorer table.</span></span>

<span data-ttu-id="41cff-135">这将打开浮出控件, 同时定位页眉预览和电子邮件下载链接。</span><span class="sxs-lookup"><span data-stu-id="41cff-135">This will open the flyout, where both header preview and email download links are positioned.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41cff-136">同时使用后面的表。</span><span class="sxs-lookup"><span data-stu-id="41cff-136">Use both the tables that follow together.</span></span> <span data-ttu-id="41cff-137">一种方式告诉您必需的 RBAC, 另一个是应在其中授予权限的位置。</span><span class="sxs-lookup"><span data-stu-id="41cff-137">One tells you the RBAC required, the other, the location where rights should be granted.</span></span>
<p>

|<span data-ttu-id="41cff-138">活动</span><span class="sxs-lookup"><span data-stu-id="41cff-138">Activity</span></span>  |<span data-ttu-id="41cff-139">具有访问权限的 RBAC new-rolegroup</span><span class="sxs-lookup"><span data-stu-id="41cff-139">RBAC rolegroup with access</span></span> |<span data-ttu-id="41cff-140">需要 "预览" 角色？</span><span class="sxs-lookup"><span data-stu-id="41cff-140">'Preview' role needed?</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="41cff-141">使用威胁浏览器 (和实时检测) 分析威胁</span><span class="sxs-lookup"><span data-stu-id="41cff-141">Use Threat Explorer (and real-time detections) to analyze threats</span></span>     |  <span data-ttu-id="41cff-142">Office 365 全局管理员,</span><span class="sxs-lookup"><span data-stu-id="41cff-142">Office 365 Global Administrator,</span></span><br> <span data-ttu-id="41cff-143">安全管理员、</span><span class="sxs-lookup"><span data-stu-id="41cff-143">Security Administrator,</span></span> <br> <span data-ttu-id="41cff-144">安全读者</span><span class="sxs-lookup"><span data-stu-id="41cff-144">Security Reader</span></span>      | <span data-ttu-id="41cff-145">否</span><span class="sxs-lookup"><span data-stu-id="41cff-145">No</span></span>   |
|<span data-ttu-id="41cff-146">使用威胁浏览器 (和实时检测) 查看电子邮件的邮件头, 以及预览和下载隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="41cff-146">Use Threat Explorer (and real-time detections) to view headers for emails as well as preview and download quarantined emails</span></span>    |     <span data-ttu-id="41cff-147">Office 365 全局管理员,</span><span class="sxs-lookup"><span data-stu-id="41cff-147">Office 365 Global Administrator,</span></span> <br> <span data-ttu-id="41cff-148">安全管理员、</span><span class="sxs-lookup"><span data-stu-id="41cff-148">Security Administrator,</span></span> <br><span data-ttu-id="41cff-149">安全读者</span><span class="sxs-lookup"><span data-stu-id="41cff-149">Security Reader</span></span>    |       <span data-ttu-id="41cff-150">否</span><span class="sxs-lookup"><span data-stu-id="41cff-150">No</span></span>  |
|<span data-ttu-id="41cff-151">使用威胁浏览器查看邮件头并下载传递给邮箱的电子邮件</span><span class="sxs-lookup"><span data-stu-id="41cff-151">Use Threat Explorer to view headers and download emails delivered to mailboxes</span></span>     |      <span data-ttu-id="41cff-152">Office 365 全局管理员,</span><span class="sxs-lookup"><span data-stu-id="41cff-152">Office 365 Global Administrator,</span></span> <br><span data-ttu-id="41cff-153">安全管理员、</span><span class="sxs-lookup"><span data-stu-id="41cff-153">Security Administrator,</span></span><br> <span data-ttu-id="41cff-154">安全读者、</span><span class="sxs-lookup"><span data-stu-id="41cff-154">Security Reader,</span></span> <br> <span data-ttu-id="41cff-155">预览</span><span class="sxs-lookup"><span data-stu-id="41cff-155">Preview</span></span>    |   <span data-ttu-id="41cff-156">是</span><span class="sxs-lookup"><span data-stu-id="41cff-156">Yes</span></span>      |

<br>

|<span data-ttu-id="41cff-157">RBAC new-rolegroup</span><span class="sxs-lookup"><span data-stu-id="41cff-157">RBAC rolegroup</span></span>  |<span data-ttu-id="41cff-158">将用户分配到的位置</span><span class="sxs-lookup"><span data-stu-id="41cff-158">Where users are assigned to them</span></span>  |
|---------|---------|
| <span data-ttu-id="41cff-159">全局管理员</span><span class="sxs-lookup"><span data-stu-id="41cff-159">Global Admin</span></span>   | <span data-ttu-id="41cff-160">Office 365 管理中心</span><span class="sxs-lookup"><span data-stu-id="41cff-160">Office 365 Admin Center</span></span>        |
| <span data-ttu-id="41cff-161">安全管理员</span><span class="sxs-lookup"><span data-stu-id="41cff-161">Security Admin</span></span>      |    <span data-ttu-id="41cff-162">安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="41cff-162">Security & Compliance Center</span></span>     |
| <span data-ttu-id="41cff-163">安全读者</span><span class="sxs-lookup"><span data-stu-id="41cff-163">Security Reader</span></span>   |    <span data-ttu-id="41cff-164">安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="41cff-164">Security & Compliance Center</span></span>     |
|      |    <span data-ttu-id="41cff-165">安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="41cff-165">Security & Compliance Center</span></span>     |


> [!CAUTION]
> <span data-ttu-id="41cff-166">请记住, "预览" 是一个角色, 而不是一个 new-rolegroup, 并且必须在随后将该角色添加到 New-rolegroup 中。</span><span class="sxs-lookup"><span data-stu-id="41cff-166">Remember, 'Preview' is a role and not a rolegroup and that role must be added to a Rolegroup afterwards.</span></span>

![在页面上具有下载和预览链接的威胁资源管理器浮出控件。](media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> <span data-ttu-id="41cff-168">此功能不会显示在用户邮箱中从未找到的电子邮件, 如果删除电子邮件或传递失败, 则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="41cff-168">This capability doesn't show up for emails that were never found in a user's mailbox, which can happen if an email was dropped or its delivery failed.</span></span> <span data-ttu-id="41cff-169">对于从用户邮箱中删除电子邮件的情况, 管理员将看到涉及 "找不到邮件" 的错误。</span><span class="sxs-lookup"><span data-stu-id="41cff-169">For cases when emails were deleted from users' mailboxes, admins will see an  error mentioning 'Mail not found'.</span></span>

### <a name="check-the-delivery-action-and-location"></a><span data-ttu-id="41cff-170">检查传递操作和位置</span><span class="sxs-lookup"><span data-stu-id="41cff-170">Check the delivery action and location</span></span>

<span data-ttu-id="41cff-171">威胁资源管理器实时检测已在 "传递" 状态下添加了 "传递操作" 和 "送达位置" 字段。</span><span class="sxs-lookup"><span data-stu-id="41cff-171">Threat Explorer real-time detections has added the Delivery Action and Delivery Location fields in the place of Delivery Status.</span></span> <span data-ttu-id="41cff-172">这将使您的电子邮件土地的更完整的了解。</span><span class="sxs-lookup"><span data-stu-id="41cff-172">This results in a more complete picture of where your emails land.</span></span> <span data-ttu-id="41cff-173">此更改的目标部分是使搜索更易于进行安全操作人员, 但最终结果是了解问题电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="41cff-173">Part of the goal of this change is to make hunting easier for Security Ops people, but the net result is knowing the location of problem emails at a glance.</span></span>

<span data-ttu-id="41cff-174">传递状态现已分为两列:</span><span class="sxs-lookup"><span data-stu-id="41cff-174">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="41cff-175">**传递操作**-此电子邮件的状态是什么？</span><span class="sxs-lookup"><span data-stu-id="41cff-175">**Delivery action** - What is the status of this email?</span></span>
- <span data-ttu-id="41cff-176">**送达位置**-此电子邮件的路由结果</span><span class="sxs-lookup"><span data-stu-id="41cff-176">**Delivery location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="41cff-177">传递操作是由于现有策略或检测而导致对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="41cff-177">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="41cff-178">以下是电子邮件可能执行的操作:</span><span class="sxs-lookup"><span data-stu-id="41cff-178">Here are the possible actions an email can take:</span></span>

- <span data-ttu-id="41cff-179">**传递**–将电子邮件传递到用户的收件箱或文件夹, 用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="41cff-179">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>
- <span data-ttu-id="41cff-180">**Junked** –将电子邮件发送到用户的 "垃圾邮件" 文件夹或 "已删除" 文件夹, 并且用户可以访问其 "垃圾邮件" 或 "已删除" 文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="41cff-180">**Junked** – email was sent to either user’s junk folder or deleted folder, and the user has access to emails in their Junk or Deleted folder.</span></span>
- <span data-ttu-id="41cff-181">已**阻止**–任何已隔离、失败或已丢弃的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="41cff-181">**Blocked** – any emails that's quarantined, that  failed, or was dropped.</span></span> <span data-ttu-id="41cff-182">用户完全无法访问它!</span><span class="sxs-lookup"><span data-stu-id="41cff-182">This is completely inaccessible by the user!</span></span>
- <span data-ttu-id="41cff-183">**已替换**–所有恶意附件都被替换为 .txt 文件的电子邮件, 这些文件的状态为 "恶意附件"。</span><span class="sxs-lookup"><span data-stu-id="41cff-183">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>
 
<span data-ttu-id="41cff-184">"送达位置" 显示运行送达后的策略和检测结果。</span><span class="sxs-lookup"><span data-stu-id="41cff-184">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="41cff-185">它已链接到传递操作。</span><span class="sxs-lookup"><span data-stu-id="41cff-185">It's linked to a Delivery Action.</span></span> <span data-ttu-id="41cff-186">添加此字段是为了深入了解在发现问题邮件时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="41cff-186">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="41cff-187">以下是送达位置的可能值:</span><span class="sxs-lookup"><span data-stu-id="41cff-187">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="41cff-188">**收件箱或文件夹**–电子邮件位于收件箱或文件夹中 (根据您的电子邮件规则)。</span><span class="sxs-lookup"><span data-stu-id="41cff-188">**Inbox or folder** – The email is in inbox or a folder (according to your email rules).</span></span>
- <span data-ttu-id="41cff-189">**本地或外部**–邮箱在云上不存在, 但在本地。</span><span class="sxs-lookup"><span data-stu-id="41cff-189">**On-prem or external** – The mailbox doesn’t exist on cloud but is on -premises.</span></span>
- <span data-ttu-id="41cff-190">**垃圾邮件文件夹**–在用户的 "垃圾邮件" 文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="41cff-190">**Junk folder** – The email in in the Junk folder of a user.</span></span>
- <span data-ttu-id="41cff-191">"**已删除**邮件" 文件夹–用户的 "已删除邮件" 文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="41cff-191">**Deleted items folder** – The email in the Deleted items folder of a user.</span></span>
- <span data-ttu-id="41cff-192">**隔离**–隔离中的电子邮件, 并且不在用户的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="41cff-192">**Quarantine** – The email in quarantine, and is not in a user’s mailbox.</span></span>
- <span data-ttu-id="41cff-193">**失败**–电子邮件无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="41cff-193">**Failed** – The email failed to reach the mailbox.</span></span>
- <span data-ttu-id="41cff-194">**丢弃**–电子邮件在邮件流中的某个位置丢失。</span><span class="sxs-lookup"><span data-stu-id="41cff-194">**Dropped** – The email gets lost somewhere in the Mailflow.</span></span>

### <a name="view-the-timeline-of-your-email"></a><span data-ttu-id="41cff-195">查看你的电子邮件的日程表</span><span class="sxs-lookup"><span data-stu-id="41cff-195">View the timeline of your email</span></span>
  
 <span data-ttu-id="41cff-196">**电子邮件日程表**威胁资源管理器中的另一个字段也会 ake 对管理员更易于搜寻。</span><span class="sxs-lookup"><span data-stu-id="41cff-196">**Email Timeline** another field in Threat Explorer will also ake hunting easier for admins.</span></span> <span data-ttu-id="41cff-197">在电子邮件中同时发生多个事件时, 在电子邮件上发生多个事件时, 或在电子邮件上的同一时间段内发生多个事件时, 不需要花费宝贵的时间检查电子邮件可能已丢失的时间, 而是在调查事件时使用。</span><span class="sxs-lookup"><span data-stu-id="41cff-197">Instead of spending valuable time checking where the email might have gone, when, while investigating an event, when multiple events happen at, or close to, the same time on an email, those events will show up in a timeline view.</span></span> <span data-ttu-id="41cff-198">将在 "*特殊操作*" 列中捕获对您的邮件执行传递后发生的一些事件。</span><span class="sxs-lookup"><span data-stu-id="41cff-198">Some events that happen post-delivery to your mail will be captured in the '*Special action*' column.</span></span> <span data-ttu-id="41cff-199">将邮件的时间线中的信息与对邮件传递后执行的特殊操作组合在一起, 管理员可以深入了解策略和威胁处理 (例如邮件路由的位置, 在某些情况下, 在某些情况下, 最终评估是什么)。</span><span class="sxs-lookup"><span data-stu-id="41cff-199">Combining  information from the timeline of the mail with the special action taken on the mail post-delivery gives admins insight into policies and threat handling (such as where the mail was routed, and, in some cases, what the final assessment was).</span></span>

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="41cff-200">查找并删除已传递的可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="41cff-200">Find and delete suspicious email that was delivered</span></span>

> [!TIP]
> <span data-ttu-id="41cff-201">威胁资源管理器 (有时称为资源管理器) 是一种功能强大的报告, 可用于多种用途, 如查找和删除邮件、标识恶意电子邮件发件人的 IP 地址或启动事件以进行进一步调查。</span><span class="sxs-lookup"><span data-stu-id="41cff-201">Threat Explorer (sometimes called Explorer), is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="41cff-202">下面的过程重点介绍如何使用资源管理器查找和删除收件人邮箱中的恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="41cff-202">The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span>

<span data-ttu-id="41cff-203">若要查看对前一个传递状态字段的更改 (现在为传递操作和送达位置), 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="41cff-203">To see the changes to the former Delivery Status field (now Delivery Action and Delivery Location):</span></span> 

1. <span data-ttu-id="41cff-204">请转[https://protection.office.com](https://protection.office.com)到使用 Office 365 的工作或学校帐户登录并登录。</span><span class="sxs-lookup"><span data-stu-id="41cff-204">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="41cff-205">这会将您带到&amp;安全合规中心。</span><span class="sxs-lookup"><span data-stu-id="41cff-205">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="41cff-206">在左侧导航中, 选择 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="41cff-206">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>


![带有 "传递操作" 和 "送达位置" 字段的威胁资源管理器。](media/ThreatExFields.PNG)

<span data-ttu-id="41cff-208">您可能会注意到此图形中的新 "特殊操作" 列。</span><span class="sxs-lookup"><span data-stu-id="41cff-208">You may notice the new 'Special actions' column in this graphic.</span></span> <span data-ttu-id="41cff-209">此功能旨在告诉管理员处理电子邮件的结果。</span><span class="sxs-lookup"><span data-stu-id="41cff-209">This feature is aimed at telling admins the outcome of processing an email.</span></span> <span data-ttu-id="41cff-210">在威胁浏览器的*电子邮件日程表*结束时, 可能会更新特殊操作, 这是旨在使求职体验更好地用于管理员的新功能。</span><span class="sxs-lookup"><span data-stu-id="41cff-210">Special actions may be updated at the end of Threat Explorer's *email timeline*, which is a new feature aimed at making the hunting experience better for admins.</span></span>

<span data-ttu-id="41cff-211">电子邮件日程表在随机时减少, 因为检查不同位置的时间较少, 以尝试了解自电子邮件到达后发生的事件。</span><span class="sxs-lookup"><span data-stu-id="41cff-211">Email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="41cff-212">当电子邮件上的多个事件发生时, 或在同一时间结束时, 这些事件将显示在 "日程表" 视图中。</span><span class="sxs-lookup"><span data-stu-id="41cff-212">When multiple events happen at, or close to, the same time on an email, those events will show up in a timeline view.</span></span> <span data-ttu-id="41cff-213">将在 "特殊操作" 列中捕获到您的邮件的送达后发生的一些事件。</span><span class="sxs-lookup"><span data-stu-id="41cff-213">Some events that happen post-delivery to your mail will be captured in the 'Special actions' column.</span></span> <span data-ttu-id="41cff-214">将该邮件的*电子邮件时间线*中的信息与邮件投递后所执行的*特殊操作*组合在一起, 管理员可以了解其策略的工作原理, 其中邮件最后是路由的, 在某些情况下, 在某些情况下, 最终评估为。</span><span class="sxs-lookup"><span data-stu-id="41cff-214">Combining the information from the *email timeline* of that mail with the *Special actions* taken on the mail post-delivery will give admins insight into how their policies work, where the mail was finally routed, and, in some cases, what the final assessment was.</span></span> <span data-ttu-id="41cff-215">可以在与传递操作和传递位置相同的位置访问 "特殊操作" 列, 但若要查看电子邮件日程表, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="41cff-215">The Special actions column can be accessed in the same place as Delivery action and Delivery location, but to see an email timeline:</span></span>

1. <span data-ttu-id="41cff-216">单击电子邮件的主题。</span><span class="sxs-lookup"><span data-stu-id="41cff-216">Click on the subject of the email.</span></span>
2. <span data-ttu-id="41cff-217">在出现的面板上, 单击 "*电子邮件日程表*"。</span><span class="sxs-lookup"><span data-stu-id="41cff-217">On the panel that appears, click *Email timeline*.</span></span> <span data-ttu-id="41cff-218">(它将显示在面板上的其他标题中, 如 "摘要" 或 "详细信息")。</span><span class="sxs-lookup"><span data-stu-id="41cff-218">(It will appear among other headings on the panel like 'Summary' or 'Details', et cetera.)</span></span>

<span data-ttu-id="41cff-219">打开电子邮件日程表后, 您应该会看到一个表, 告诉您该邮件的送达事件, 或者, 如果没有针对该电子邮件的进一步事件, 则会看到原始传递的单个事件, 该事件将声明*阻止*的结果。带有类似*网络钓鱼*的结论。</span><span class="sxs-lookup"><span data-stu-id="41cff-219">Once you've opened the email timeline, you should see a table that tells you the post-delivery events for that mail, or, in the case of no further events for the email, you should see a single event for the original delivery that will state a result like *Blocked* with a verdict like *Phish*.</span></span> <span data-ttu-id="41cff-220">该选项卡还具有导出整个电子邮件时间线的选项, 这将导出该选项卡上的所有详细信息, 以及有关电子邮件的详细信息 (如主题、发件人、收件人、网络和邮件 ID 等)。</span><span class="sxs-lookup"><span data-stu-id="41cff-220">The tab also has the option to export the entire email timeline, and this will export all the details on the tab and details on the email (things like Subject, Sender, Recipient, Network, and Message ID).</span></span>

3. <span data-ttu-id="41cff-221">在 "视图" 菜单中, 选择 "**所有电子邮件**"。</span><span class="sxs-lookup"><span data-stu-id="41cff-221">In the View menu, choose **All email**.</span></span><br/><span data-ttu-id="41cff-222">![使用 "视图" 菜单在电子邮件和内容报告之间进行选择](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span><span class="sxs-lookup"><span data-stu-id="41cff-222">![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span></span>
  
4. <span data-ttu-id="41cff-223">请注意报告中显示的标签, 如 "已**交货**"、"**未知**" 或 "已**传递到垃圾邮件**"。</span><span class="sxs-lookup"><span data-stu-id="41cff-223">Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.</span></span><br/><span data-ttu-id="41cff-224">![显示所有电子邮件的数据的威胁资源管理器](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span><span class="sxs-lookup"><span data-stu-id="41cff-224">![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span></span><br/><span data-ttu-id="41cff-225">(根据对组织的电子邮件执行的操作, 可能会看到其他标签, 如 "已**阻止**" 或 "**已替换**"。)</span><span class="sxs-lookup"><span data-stu-id="41cff-225">(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)</span></span>
    
5. <span data-ttu-id="41cff-226">在报告中, 选择 "已**传递**" 以仅查看在用户收件箱中结束的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="41cff-226">In the report, choose **Delivered** to view only emails that ended up in users' inboxes.</span></span><br/><span data-ttu-id="41cff-227">![单击 "传递给垃圾邮件" 将从视图中删除该数据](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span><span class="sxs-lookup"><span data-stu-id="41cff-227">![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span></span>
  
6. <span data-ttu-id="41cff-228">在图表下方, 查看图表下方的**电子邮件**列表。</span><span class="sxs-lookup"><span data-stu-id="41cff-228">Below the chart, review the **Email** list below the chart.</span></span><br/><span data-ttu-id="41cff-229">![在图表下方, 查看检测到的电子邮件的列表](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span><span class="sxs-lookup"><span data-stu-id="41cff-229">![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span></span>
  
7. <span data-ttu-id="41cff-230">在列表中, 选择一个项目以查看有关该电子邮件的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="41cff-230">In the list, choose an item to view more details about that email message.</span></span> <span data-ttu-id="41cff-231">例如, 您可以单击 "主题" 行来查看有关发件人、收件人、附件和其他类似电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="41cff-231">For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.</span></span><br/>![您可以查看有关项目的其他信息, 包括详细信息和任何附件](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. <span data-ttu-id="41cff-233">查看有关电子邮件的信息后, 选择列表中的一个或多个项目以激活 **+ 操作**。</span><span class="sxs-lookup"><span data-stu-id="41cff-233">After viewing information about email messages, select one or more items in the list to activate **+ Actions**.</span></span>
    
9. <span data-ttu-id="41cff-234">使用 **+ 操作**列表应用操作, 例如**移到 "已删除**邮件"。</span><span class="sxs-lookup"><span data-stu-id="41cff-234">Use the **+ Actions** list to apply an action, such as **Move to deleted** items.</span></span> <span data-ttu-id="41cff-235">这将从收件人邮箱中删除所选邮件。</span><span class="sxs-lookup"><span data-stu-id="41cff-235">This will delete the selected messages from the recipients' mailboxes.</span></span><br/><span data-ttu-id="41cff-236">![当您选择一个或多个电子邮件时, 可以从多个可用的操作中进行选择](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span><span class="sxs-lookup"><span data-stu-id="41cff-236">![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="41cff-237">相关主题</span><span class="sxs-lookup"><span data-stu-id="41cff-237">Related topics</span></span>

[<span data-ttu-id="41cff-238">Office 365 高级威胁防护计划2</span><span class="sxs-lookup"><span data-stu-id="41cff-238">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="41cff-239">防御 Office 365 中的威胁</span><span class="sxs-lookup"><span data-stu-id="41cff-239">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="41cff-240">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="41cff-240">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

