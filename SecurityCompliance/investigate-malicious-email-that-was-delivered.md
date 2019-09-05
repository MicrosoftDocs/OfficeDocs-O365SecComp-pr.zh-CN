---
title: 查找并调查 Office 365 中提供的恶意电子邮件
keywords: TIMailData-Inline，安全事件，事件，ATP PowerShell，电子邮件恶意软件，已损坏的用户，电子邮件网络钓鱼诈骗，电子邮件恶意软件，读取电子邮件头，读取邮件头，打开电子邮件头
ms.author: deniseb
author: denisebmsft
manager: dansimp
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
ms.openlocfilehash: a57e72c74a7b2f819ecee7fbf604795e4a094693
ms.sourcegitcommit: 4a2bde56178609e75c1ad7ecad2db5e049fc0c45
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/05/2019
ms.locfileid: "36761678"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-in-office-365"></a><span data-ttu-id="7ca76-104">查找并调查 Office 365 中提供的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="7ca76-104">Find and investigate malicious email that was delivered in Office 365</span></span>

<span data-ttu-id="7ca76-105">[Office 365 高级威胁防护](office-365-atp.md)使您能够调查将组织中的人员面临风险的活动，并采取措施保护组织。</span><span class="sxs-lookup"><span data-stu-id="7ca76-105">[Office 365 Advanced Threat Protection](office-365-atp.md) enables you to investigate activities that put people in your organization at risk, and to take action to protect your organization.</span></span> <span data-ttu-id="7ca76-106">例如，如果您是组织的安全团队的一部分，则可以查找并调查已传递的可疑电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7ca76-106">For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered.</span></span> <span data-ttu-id="7ca76-107">可以使用[威胁资源管理器（或实时检测）](threat-explorer.md)执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7ca76-107">You can do this by using [Threat Explorer (or real-time detections)](threat-explorer.md).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="7ca76-108">开始之前 .。。</span><span class="sxs-lookup"><span data-stu-id="7ca76-108">Before you begin...</span></span>

<span data-ttu-id="7ca76-109">请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="7ca76-109">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="7ca76-110">您的组织具有[Office 365 高级威胁防护](office-365-atp.md)，并将[许可证分配给用户](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users)。</span><span class="sxs-lookup"><span data-stu-id="7ca76-110">Your organization has [Office 365 Advanced Threat Protection](office-365-atp.md) and [licenses are assigned to users](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>
    
- <span data-ttu-id="7ca76-111">为你的组织启用了[Office 365 审核日志记录](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="7ca76-111">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="7ca76-112">您的组织具有为反垃圾邮件、反恶意软件、反网络钓鱼等定义的策略。</span><span class="sxs-lookup"><span data-stu-id="7ca76-112">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on.</span></span> <span data-ttu-id="7ca76-113">请参阅防御[Office 365 中的威胁](protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="7ca76-113">See [Protect against threats in Office 365](protect-against-threats.md).</span></span>
    
- <span data-ttu-id="7ca76-114">您是 Office 365 全局管理员，或者您具有安全管理员或在安全&amp;合规中心中分配的搜索和清除角色。</span><span class="sxs-lookup"><span data-stu-id="7ca76-114">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center.</span></span> <span data-ttu-id="7ca76-115">请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7ca76-115">See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span> <span data-ttu-id="7ca76-116">对于某些操作，还必须分配新的预览角色。</span><span class="sxs-lookup"><span data-stu-id="7ca76-116">For some actions, you must also have a new Preview role assigned.</span></span> 

#### <a name="preview-role-permissions"></a><span data-ttu-id="7ca76-117">预览角色权限</span><span class="sxs-lookup"><span data-stu-id="7ca76-117">Preview role permissions</span></span>

<span data-ttu-id="7ca76-118">若要执行某些操作（如查看邮件头或下载电子邮件内容），您必须具有一个名为*Preview*的新角色，并将其添加到另一个相应的 Office 365 角色组。</span><span class="sxs-lookup"><span data-stu-id="7ca76-118">To perform certain actions, such as viewing message headers or downloading email message content, you must have a new role called *Preview* added to another appropriate Office 365 role group.</span></span> <span data-ttu-id="7ca76-119">下表阐明了所需的角色和权限。</span><span class="sxs-lookup"><span data-stu-id="7ca76-119">The following table clarifies required roles and permissions.</span></span>

|<span data-ttu-id="7ca76-120">活动</span><span class="sxs-lookup"><span data-stu-id="7ca76-120">Activity</span></span>  |<span data-ttu-id="7ca76-121">角色组</span><span class="sxs-lookup"><span data-stu-id="7ca76-121">Role group</span></span> |<span data-ttu-id="7ca76-122">是否需要预览角色？</span><span class="sxs-lookup"><span data-stu-id="7ca76-122">Preview role needed?</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="7ca76-123">使用威胁浏览器（和实时检测）分析威胁</span><span class="sxs-lookup"><span data-stu-id="7ca76-123">Use Threat Explorer (and real-time detections) to analyze threats</span></span>     |<span data-ttu-id="7ca76-124">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="7ca76-124">Office 365 Global Administrator</span></span> <br> <span data-ttu-id="7ca76-125">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="7ca76-125">Security Administrator</span></span> <br> <span data-ttu-id="7ca76-126">安全读者</span><span class="sxs-lookup"><span data-stu-id="7ca76-126">Security Reader</span></span>     | <span data-ttu-id="7ca76-127">否</span><span class="sxs-lookup"><span data-stu-id="7ca76-127">No</span></span>   |
|<span data-ttu-id="7ca76-128">使用威胁资源管理器（和实时检测）查看电子邮件的邮件头，以及预览和下载隔离的电子邮件</span><span class="sxs-lookup"><span data-stu-id="7ca76-128">Use Threat Explorer (and real-time detections) to view headers for email messages as well as preview and download quarantined email messages</span></span>    |<span data-ttu-id="7ca76-129">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="7ca76-129">Office 365 Global Administrator</span></span> <br> <span data-ttu-id="7ca76-130">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="7ca76-130">Security Administrator</span></span> <br><span data-ttu-id="7ca76-131">安全读者</span><span class="sxs-lookup"><span data-stu-id="7ca76-131">Security Reader</span></span>   |       <span data-ttu-id="7ca76-132">否</span><span class="sxs-lookup"><span data-stu-id="7ca76-132">No</span></span>  |
|<span data-ttu-id="7ca76-133">使用威胁浏览器查看邮件头并下载传递给邮箱的电子邮件</span><span class="sxs-lookup"><span data-stu-id="7ca76-133">Use Threat Explorer to view headers and download email messages delivered to mailboxes</span></span>     |<span data-ttu-id="7ca76-134">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="7ca76-134">Office 365 Global Administrator</span></span> <br><span data-ttu-id="7ca76-135">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="7ca76-135">Security Administrator</span></span> <br> <span data-ttu-id="7ca76-136">安全读者</span><span class="sxs-lookup"><span data-stu-id="7ca76-136">Security Reader</span></span> <br> <span data-ttu-id="7ca76-137">预览</span><span class="sxs-lookup"><span data-stu-id="7ca76-137">Preview</span></span>   |   <span data-ttu-id="7ca76-138">是</span><span class="sxs-lookup"><span data-stu-id="7ca76-138">Yes</span></span>      |

> [!NOTE]
> <span data-ttu-id="7ca76-139">*预览*是一个角色，而不是角色组;必须将预览角色添加到 Office 365 的现有角色组中。</span><span class="sxs-lookup"><span data-stu-id="7ca76-139">*Preview* is a role and not a role group; the Preview role must be added to an existing role group for Office 365.</span></span> <span data-ttu-id="7ca76-140">Office 365 全局管理员角色分配有 Microsoft 365 管理中心（[https://admin.microsoft.com](https://admin.microsoft.com)），安全管理员和安全读者角色是在 Office 365 安全 & 合规中心（[https://protection.office.com](https://protection.office.com)）中分配的。</span><span class="sxs-lookup"><span data-stu-id="7ca76-140">The Office 365 Global Administrator role is assigned the Microsoft 365 admin center ([https://admin.microsoft.com](https://admin.microsoft.com)), and the Security Administrator and Security Reader roles are assigned in the Office 365 Security & Compliance Center ([https://protection.office.com](https://protection.office.com)).</span></span> <span data-ttu-id="7ca76-141">若要了解有关角色和权限的详细信息，请参阅[Office 365 Security & 合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7ca76-141">To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="7ca76-142">查找并删除已传递的可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="7ca76-142">Find and delete suspicious email that was delivered</span></span>

<span data-ttu-id="7ca76-143">威胁资源管理器是一种功能强大的报告，可用于多种用途，如查找和删除邮件、标识恶意电子邮件发件人的 IP 地址或启动事件以进行进一步调查。</span><span class="sxs-lookup"><span data-stu-id="7ca76-143">Threat Explorer is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation.</span></span> <span data-ttu-id="7ca76-144">下面的过程重点介绍如何使用资源管理器查找和删除收件人邮箱中的恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7ca76-144">The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span>

1. <span data-ttu-id="7ca76-145">请转[https://protection.office.com](https://protection.office.com)到使用 Office 365 的工作或学校帐户登录并登录。</span><span class="sxs-lookup"><span data-stu-id="7ca76-145">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="7ca76-146">这会将您带到&amp;安全合规中心。</span><span class="sxs-lookup"><span data-stu-id="7ca76-146">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="7ca76-147">在左侧导航中，选择 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="7ca76-147">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>

    ![具有 "传递操作" 和 "送达位置" 字段的资源管理器。](media/ThreatExFields.PNG)

    <span data-ttu-id="7ca76-149">您可能会注意到 "新建**特殊操作**" 列。</span><span class="sxs-lookup"><span data-stu-id="7ca76-149">You may notice the new **Special actions** column.</span></span> <span data-ttu-id="7ca76-150">此功能旨在告诉管理员处理电子邮件的结果。</span><span class="sxs-lookup"><span data-stu-id="7ca76-150">This feature is aimed at telling admins the outcome of processing an email.</span></span> <span data-ttu-id="7ca76-151">可以在与**传递操作**和**传递位置**相同的位置访问 "**特殊操作**" 列。</span><span class="sxs-lookup"><span data-stu-id="7ca76-151">The **Special actions** column can be accessed in the same place as **Delivery action** and **Delivery location**.</span></span> <span data-ttu-id="7ca76-152">在威胁资源管理器的电子邮件日程表结束时，可能会更新特殊操作，这是旨在使求职体验更适合管理员的新功能。</span><span class="sxs-lookup"><span data-stu-id="7ca76-152">Special actions might be updated at the end of Threat Explorer's email timeline, which is a new feature aimed at making the hunting experience better for admins.</span></span>

3. <span data-ttu-id="7ca76-153">若要查看电子邮件日程表，请单击电子邮件的主题，然后单击 "**电子邮件日程表**"。</span><span class="sxs-lookup"><span data-stu-id="7ca76-153">To view an email timeline, click on the subject of an email message, and then click **Email timeline**.</span></span> <span data-ttu-id="7ca76-154">（它显示在面板上的其他标题中，如**摘要**或**详细信息**。）</span><span class="sxs-lookup"><span data-stu-id="7ca76-154">(It appears among other headings on the panel like **Summary** or **Details**.)</span></span>

    <span data-ttu-id="7ca76-155">打开电子邮件日程表后，您应该会看到一个表，告诉您该邮件的传递后事件。</span><span class="sxs-lookup"><span data-stu-id="7ca76-155">Once you've opened the email timeline, you should see a table that tells you the post-delivery events for that mail.</span></span> <span data-ttu-id="7ca76-156">对于没有对电子邮件的进一步事件的情况，您应该会看到原始传递的单个事件，该事件指出**了类似于\*\*\*\*网络钓鱼**等判定的结果。</span><span class="sxs-lookup"><span data-stu-id="7ca76-156">In the case of no further events for the email, you should see a single event for the original delivery that states a result like **Blocked** with a verdict like **Phish**.</span></span> <span data-ttu-id="7ca76-157">该选项卡还具有导出整个电子邮件时间线的选项，此操作将导出该选项卡上的所有详细信息，以及有关电子邮件的详细信息（如主题、发件人、收件人、网络和邮件 ID 等）。</span><span class="sxs-lookup"><span data-stu-id="7ca76-157">The tab also has the option to export the entire email timeline, and this exports all the details on the tab and details on the email (things like Subject, Sender, Recipient, Network, and Message ID).</span></span>

    <span data-ttu-id="7ca76-158">电子邮件日程表在随机时减少，因为检查不同位置的时间较少，以尝试了解自电子邮件到达后发生的事件。</span><span class="sxs-lookup"><span data-stu-id="7ca76-158">The email timeline cuts down on randomization because there is less time spent checking different locations to try to understand events that happened since the email arrived.</span></span> <span data-ttu-id="7ca76-159">当电子邮件上的多个事件发生时，或在同一时间结束时，这些事件将显示在 "日程表" 视图中。</span><span class="sxs-lookup"><span data-stu-id="7ca76-159">When multiple events happen at, or close to, the same time on an email, those events show up in a timeline view.</span></span> 
    
    <span data-ttu-id="7ca76-160">在 "**特殊操作**" 列中捕获对您的邮件执行送达后发生的一些事件。</span><span class="sxs-lookup"><span data-stu-id="7ca76-160">Some events that happen post-delivery to your mail are captured in the **Special actions** column.</span></span> <span data-ttu-id="7ca76-161">将电子邮件时间线中的信息与在送达电子邮件后进行的特殊操作组合在一起，管理员可以深入了解其策略的工作方式，即最后路由电子邮件的方式，在某些情况下，最终评估是什么。</span><span class="sxs-lookup"><span data-stu-id="7ca76-161">Combining the information from the email timeline along with special actions taken on email post-delivery gives admins insight into how their policies work, where the email was finally routed, and, in some cases, what the final assessment was.</span></span> 

4. <span data-ttu-id="7ca76-162">在 "**视图**" 菜单中，选择 "**所有电子邮件**"。</span><span class="sxs-lookup"><span data-stu-id="7ca76-162">In the **View** menu, choose **All email**.</span></span>

    ![使用 "视图" 菜单在电子邮件和内容报告之间进行选择](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    <span data-ttu-id="7ca76-164">请注意报告中显示的标签，如 "已**交货**"、"**未知**" 或 "已**传递到垃圾邮件**"。</span><span class="sxs-lookup"><span data-stu-id="7ca76-164">Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.</span></span>

    ![显示所有电子邮件的数据的威胁资源管理器](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    <span data-ttu-id="7ca76-166">（根据对组织的电子邮件执行的操作，可能会看到其他标签，如 "已**阻止**" 或 "**已替换**"。）</span><span class="sxs-lookup"><span data-stu-id="7ca76-166">(Depending on the actions that were taken on email messages for your organization, you might see other labels, such as **Blocked** or **Replaced**.)</span></span>
    
6. <span data-ttu-id="7ca76-167">在报告中，选择 "已**传递**" 以仅查看在用户收件箱中最后结束的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7ca76-167">In the report, choose **Delivered** to view only email messages that ended up in users' inboxes.</span></span>

    ![单击 "传递给垃圾邮件" 将从视图中删除该数据](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
7. <span data-ttu-id="7ca76-169">在图表下方，查看图表下方的**电子邮件**列表。</span><span class="sxs-lookup"><span data-stu-id="7ca76-169">Below the chart, review the **Email** list below the chart.</span></span>

    ![在图表下方，查看检测到的电子邮件的列表](media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
8. <span data-ttu-id="7ca76-171">在列表中，选择一个项目以查看有关该电子邮件的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="7ca76-171">In the list, choose an item to view more details about that email message.</span></span> <span data-ttu-id="7ca76-172">例如，您可以单击 "主题" 行来查看有关发件人、收件人、附件和其他类似电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="7ca76-172">For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.</span></span>

    ![您可以查看有关项目的其他信息](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
9. <span data-ttu-id="7ca76-174">查看有关电子邮件的信息后，选择列表中的一个或多个项目以激活 **+ 操作**。</span><span class="sxs-lookup"><span data-stu-id="7ca76-174">After viewing information about email messages, select one or more items in the list to activate **+ Actions**.</span></span>
    
10. <span data-ttu-id="7ca76-175">使用 **+ 操作**列表应用操作，例如**移到 "已删除**邮件"。</span><span class="sxs-lookup"><span data-stu-id="7ca76-175">Use the **+ Actions** list to apply an action, such as **Move to deleted** items.</span></span> <span data-ttu-id="7ca76-176">这将从收件人邮箱中删除所选邮件。</span><span class="sxs-lookup"><span data-stu-id="7ca76-176">This deletes the selected messages from the recipients' mailboxes.</span></span>

    ![当您选择一个或多个电子邮件时，可以从多个可用的操作中进行选择](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## <a name="dealing-with-suspicious-email-messages"></a><span data-ttu-id="7ca76-178">处理可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="7ca76-178">Dealing with suspicious email messages</span></span>

<span data-ttu-id="7ca76-179">恶意攻击者可能会向组织中的人员发送邮件，以尝试对其凭据进行网络钓鱼并获取对公司机密的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7ca76-179">Malicious attackers might be sending mail to people in your organization in an attempt to phish their credentials and gain access to your corporate secrets.</span></span> <span data-ttu-id="7ca76-180">为了帮助防止这种情况，请使用 Office 365 中的威胁防护服务，包括[Exchange Online protection](eop/exchange-online-protection-overview.md)和[高级威胁防护](office-365-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="7ca76-180">To help prevent this, you use the threat protection services in Office 365, including [Exchange Online Protection](eop/exchange-online-protection-overview.md) and [Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="7ca76-181">但是，偶尔会发生攻击者发送包含仅指向恶意内容（如恶意软件）的链接（URL）的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7ca76-181">However, it occasionally happens that an attacker sends email that contains a link (URL) that only later points to malicious content (such as malware).</span></span> <span data-ttu-id="7ca76-182">或者，您可能会发现组织中的某个人已受到威胁，而他们受到威胁时，攻击者使用其帐户向组织中的其他人发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7ca76-182">Or, you might realize too late that someone in your organization has been compromised, and while they were compromised, an attacker used their account to send email to other people in your organization.</span></span> <span data-ttu-id="7ca76-183">在处理上述任一情况的过程中，您可以从用户收件箱中删除可疑电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7ca76-183">As part of dealing with either of these scenarios, you can remove suspicious email messages from user inboxes.</span></span> <span data-ttu-id="7ca76-184">若要执行此操作，可以使用[威胁资源管理器](threat-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="7ca76-184">To do that, you can use [Threat Explorer](threat-explorer.md).</span></span>

## <a name="finding-re-routed-email-messages-after-actions-are-taken"></a><span data-ttu-id="7ca76-185">在执行操作后查找重新路由的电子邮件</span><span class="sxs-lookup"><span data-stu-id="7ca76-185">Finding re-routed email messages after actions are taken</span></span>

<span data-ttu-id="7ca76-186">威胁资源管理器为安全操作团队提供调查可疑电子邮件所需的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7ca76-186">Threat Explorer provides your security operations team with the details they need to investigate suspicious email.</span></span> <span data-ttu-id="7ca76-187">您的安全操作团队可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7ca76-187">Your security operations team can:</span></span>

- [<span data-ttu-id="7ca76-188">查看电子邮件头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="7ca76-188">View the email headers and download the email body</span></span>](#view-the-email-headers-and-download-the-email-body) 

- [<span data-ttu-id="7ca76-189">检查传递操作和位置</span><span class="sxs-lookup"><span data-stu-id="7ca76-189">Check the delivery action and location</span></span>](#check-the-delivery-action-and-location)

- [<span data-ttu-id="7ca76-190">查看你的电子邮件的日程表</span><span class="sxs-lookup"><span data-stu-id="7ca76-190">View the timeline of your email</span></span>](#view-the-timeline-of-your-email)

### <a name="view-the-email-headers-and-download-the-email-body"></a><span data-ttu-id="7ca76-191">查看电子邮件头并下载电子邮件正文</span><span class="sxs-lookup"><span data-stu-id="7ca76-191">View the email headers and download the email body</span></span>

<span data-ttu-id="7ca76-192">在威胁资源管理器中，预览电子邮件头和下载电子邮件正文的能力是强大的功能。</span><span class="sxs-lookup"><span data-stu-id="7ca76-192">The ability to preview email headers and download the body of an email body are powerful capabilities in Threat Explorer.</span></span> <span data-ttu-id="7ca76-193">必须分配适当的[权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="7ca76-193">Appropriate [permissions](permissions-in-the-security-and-compliance-center.md) must be assigned.</span></span> <span data-ttu-id="7ca76-194">请参阅[预览角色权限](#preview-role-permissions)。</span><span class="sxs-lookup"><span data-stu-id="7ca76-194">See [Preview role permissions](#preview-role-permissions).</span></span>

<span data-ttu-id="7ca76-195">若要访问您的邮件头和电子邮件下载选项，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="7ca76-195">To access your message header and email download options, follow these steps:</span></span> 

1. <span data-ttu-id="7ca76-196">请转[https://protection.office.com](https://protection.office.com)到使用 Office 365 的工作或学校帐户登录并登录。</span><span class="sxs-lookup"><span data-stu-id="7ca76-196">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365.</span></span> <span data-ttu-id="7ca76-197">这会将您带到&amp;安全合规中心。</span><span class="sxs-lookup"><span data-stu-id="7ca76-197">This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="7ca76-198">在左侧导航中，选择 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="7ca76-198">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>

3. <span data-ttu-id="7ca76-199">单击 "威胁资源管理器" 表中的主题。</span><span class="sxs-lookup"><span data-stu-id="7ca76-199">Click on a subject in the Threat Explorer table.</span></span> 

    <span data-ttu-id="7ca76-200">这将打开浮出控件，同时定位页眉预览和电子邮件下载链接。</span><span class="sxs-lookup"><span data-stu-id="7ca76-200">This opens the flyout, where both header preview and email download links are positioned.</span></span>

    ![在页面上具有下载和预览链接的威胁资源管理器浮出控件。](media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> <span data-ttu-id="7ca76-202">此功能不会显示在用户邮箱中从未找到的电子邮件，如果删除电子邮件或传递失败，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="7ca76-202">This capability doesn't show up for email messages that were never found in a user's mailbox, which can happen if an email was dropped or its delivery failed.</span></span> <span data-ttu-id="7ca76-203">在从用户邮箱中删除电子邮件的情况下，管理员会看到 "找不到邮件" 错误消息。</span><span class="sxs-lookup"><span data-stu-id="7ca76-203">In cases where email messages were deleted from users' mailboxes, admins see a "Mail not found" error message.</span></span>

### <a name="check-the-delivery-action-and-location"></a><span data-ttu-id="7ca76-204">检查传递操作和位置</span><span class="sxs-lookup"><span data-stu-id="7ca76-204">Check the delivery action and location</span></span>

<span data-ttu-id="7ca76-205">在[威胁资源管理器（和实时检测）](threat-explorer.md)中，您现在具有**传递操作**列和 "**传递位置**" 列，而不是以前的 "**传递状态**" 列。</span><span class="sxs-lookup"><span data-stu-id="7ca76-205">In [Threat Explorer (and real-time detections)](threat-explorer.md), you now have **Delivery Action** and **Delivery Location** columns instead of the former **Delivery Status** column.</span></span> <span data-ttu-id="7ca76-206">这将导致您的电子邮件位于何处的更完整的图片。</span><span class="sxs-lookup"><span data-stu-id="7ca76-206">This results in a more complete picture of where your email messages land.</span></span> <span data-ttu-id="7ca76-207">此更改的目标部分是使搜索更易于进行安全操作，但最终结果是，快速了解问题电子邮件的位置。</span><span class="sxs-lookup"><span data-stu-id="7ca76-207">Part of the goal of this change is to make hunting easier for security operations, but the net result is knowing the location of problem email messages at a glance.</span></span>

<span data-ttu-id="7ca76-208">传递状态现已分为两列：</span><span class="sxs-lookup"><span data-stu-id="7ca76-208">Delivery Status is now broken out into two columns:</span></span>

- <span data-ttu-id="7ca76-209">**传递操作**-此电子邮件的状态是什么？</span><span class="sxs-lookup"><span data-stu-id="7ca76-209">**Delivery action** - What is the status of this email?</span></span>

- <span data-ttu-id="7ca76-210">**送达位置**-此电子邮件的路由结果</span><span class="sxs-lookup"><span data-stu-id="7ca76-210">**Delivery location** - Where was this email routed as a result?</span></span>

<span data-ttu-id="7ca76-211">传递操作是由于现有策略或检测而导致对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="7ca76-211">Delivery action is the action taken on an email due to existing policies or detections.</span></span> <span data-ttu-id="7ca76-212">以下是电子邮件可能执行的操作：</span><span class="sxs-lookup"><span data-stu-id="7ca76-212">Here are the possible actions an email can take:</span></span>

- <span data-ttu-id="7ca76-213">**传递**–将电子邮件传递到用户的收件箱或文件夹，用户可以直接访问它。</span><span class="sxs-lookup"><span data-stu-id="7ca76-213">**Delivered** – email was delivered to inbox or folder of a user and the user can directly access it.</span></span>

- <span data-ttu-id="7ca76-214">**Junked** –将电子邮件发送到用户的 "垃圾邮件" 文件夹或 "已删除" 文件夹，并且用户可以访问其 "垃圾邮件" 或 "已删除" 文件夹中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7ca76-214">**Junked** – email was sent to either user’s junk folder or deleted folder, and the user has access to email messages in their Junk or Deleted folder.</span></span>

- <span data-ttu-id="7ca76-215">已**阻止**–隔离、失败或丢弃的任何电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7ca76-215">**Blocked** – any email messages that are quarantined, that failed, or were dropped.</span></span> <span data-ttu-id="7ca76-216">（这是用户完全无法访问的。）</span><span class="sxs-lookup"><span data-stu-id="7ca76-216">(This is completely inaccessible by the user.)</span></span>

- <span data-ttu-id="7ca76-217">**已替换**–所有恶意附件都被替换为 .txt 文件的电子邮件，这些文件的状态为 "恶意附件"。</span><span class="sxs-lookup"><span data-stu-id="7ca76-217">**Replaced** – any email where malicious attachments are replaced by .txt files that state the attachment was malicious.</span></span>
 
<span data-ttu-id="7ca76-218">"送达位置" 显示运行送达后的策略和检测结果。</span><span class="sxs-lookup"><span data-stu-id="7ca76-218">Delivery location shows the results of policies and detections that run post-delivery.</span></span> <span data-ttu-id="7ca76-219">它已链接到传递操作。</span><span class="sxs-lookup"><span data-stu-id="7ca76-219">It's linked to a Delivery Action.</span></span> <span data-ttu-id="7ca76-220">添加此字段是为了深入了解在发现问题邮件时所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="7ca76-220">This field was added to give insight into the action taken when a problem mail is found.</span></span> <span data-ttu-id="7ca76-221">以下是送达位置的可能值：</span><span class="sxs-lookup"><span data-stu-id="7ca76-221">Here are the possible values of delivery location:</span></span>

- <span data-ttu-id="7ca76-222">**收件箱或文件夹**–电子邮件位于收件箱或文件夹中（根据您的电子邮件规则）。</span><span class="sxs-lookup"><span data-stu-id="7ca76-222">**Inbox or folder** – The email is in the inbox or a folder (according to your email rules).</span></span>

- <span data-ttu-id="7ca76-223">**本地或外部**–邮箱在云上不存在，但在本地。</span><span class="sxs-lookup"><span data-stu-id="7ca76-223">**On-prem or external** – The mailbox doesn’t exist on cloud but is on-premises.</span></span>

- <span data-ttu-id="7ca76-224">**垃圾邮件文件夹**–电子邮件位于用户的垃圾邮件文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7ca76-224">**Junk folder** – The email is in a user's Junk folder.</span></span>

- <span data-ttu-id="7ca76-225">"**已删除邮件" 文件夹**–电子邮件位于用户的 "已删除邮件" 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="7ca76-225">**Deleted items folder** – The email is in a user's Deleted items folder.</span></span>

- <span data-ttu-id="7ca76-226">**隔离**–隔离的电子邮件，而不是用户邮箱中的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="7ca76-226">**Quarantine** – The email in quarantine, and not in a user’s mailbox.</span></span>

- <span data-ttu-id="7ca76-227">**失败**–电子邮件无法访问邮箱。</span><span class="sxs-lookup"><span data-stu-id="7ca76-227">**Failed** – The email failed to reach the mailbox.</span></span>

- <span data-ttu-id="7ca76-228">**丢弃**–电子邮件在邮件流中的某个位置丢失。</span><span class="sxs-lookup"><span data-stu-id="7ca76-228">**Dropped** – The email gets lost somewhere in the mail flow.</span></span>

### <a name="view-the-timeline-of-your-email"></a><span data-ttu-id="7ca76-229">查看你的电子邮件的日程表</span><span class="sxs-lookup"><span data-stu-id="7ca76-229">View the timeline of your email</span></span>
  
<span data-ttu-id="7ca76-230">**电子邮件日程表**是威胁资源管理器中的一个字段，可使您的安全操作团队更轻松地使用查找。</span><span class="sxs-lookup"><span data-stu-id="7ca76-230">**Email Timeline** is a field in Threat Explorer that makes hunting easier for your security operations team.</span></span> <span data-ttu-id="7ca76-231">当电子邮件上的多个事件同时发生或在同一时间结束时，这些事件将显示在 "日程表" 视图中。</span><span class="sxs-lookup"><span data-stu-id="7ca76-231">When multiple events happen at or close to the same time on an email, those events show up in a timeline view.</span></span> <span data-ttu-id="7ca76-232">在 "**特殊操作**" 列中捕获到电子邮件的传递后发生的一些事件。</span><span class="sxs-lookup"><span data-stu-id="7ca76-232">Some events that happen post-delivery to email are captured in the **Special actions** column.</span></span> <span data-ttu-id="7ca76-233">将电子邮件的时间线中的信息与所执行的任何特殊操作组合在一起，可使管理员深入了解策略和威胁处理（例如邮件路由的位置，在某些情况下，在某些情况下，最终评估是什么）。</span><span class="sxs-lookup"><span data-stu-id="7ca76-233">Combining information from the timeline of an email message with any special actions that were taken post-delivery gives admins insight into policies and threat handling (such as where the mail was routed, and, in some cases, what the final assessment was).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7ca76-234">相关主题</span><span class="sxs-lookup"><span data-stu-id="7ca76-234">Related topics</span></span>

[<span data-ttu-id="7ca76-235">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="7ca76-235">Office 365 Advanced Threat Protection</span></span>](office-365-ti.md)
  
[<span data-ttu-id="7ca76-236">防御 Office 365 中的威胁</span><span class="sxs-lookup"><span data-stu-id="7ca76-236">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="7ca76-237">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="7ca76-237">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

