---
title: 查找并调查提供的恶意电子邮件 (Office 365 威胁智能)
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/13/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: 了解如何使用威胁智能查找和调查恶意电子邮件。
ms.openlocfilehash: d5b08338bc0a3a6a88ea498861ab9e27522b759d
ms.sourcegitcommit: 1c73c2f83703af0a30a5b0633db00d8e0e6b39b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/25/2019
ms.locfileid: "30241904"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-threat-intelligence"></a><span data-ttu-id="e5c30-103">查找并调查提供的恶意电子邮件 (Office 365 威胁智能)</span><span class="sxs-lookup"><span data-stu-id="e5c30-103">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>

<span data-ttu-id="e5c30-p101">[Office 365 威胁智能](office-365-ti.md)使您能够调查让用户面临风险的活动, 并采取措施来保护您的组织。例如, 如果您是组织的安全团队的一部分, 则可以查找并调查传递给用户的可疑电子邮件。可以使用[威胁资源管理器](get-started-with-ti.md#threat-explorer)执行此操作。</span><span class="sxs-lookup"><span data-stu-id="e5c30-p101">[Office 365 Threat Intelligence](office-365-ti.md) enables you to investigate activities that put your users at risk and take action to protect your organization. For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered to your users. You can do this by using [Threat Explorer](get-started-with-ti.md#threat-explorer).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e5c30-p102">从2019年2月起开始, 在接下来的几个月中, office 365 威胁情报将成为 office 365 高级威胁防护计划 2, 其中包含其他威胁防护功能。若要了解详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)以及[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="e5c30-p102">Beginning in February 2019 and rolling out over the next several months, Office 365 Threat Intelligence is becoming Office 365 Advanced Threat Protection Plan 2, with additional threat protection capabilities. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="e5c30-109">开始之前 .。。</span><span class="sxs-lookup"><span data-stu-id="e5c30-109">Before you begin...</span></span>

<span data-ttu-id="e5c30-110">请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="e5c30-110">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="e5c30-111">您的组织具有[office 365 威胁智能](office-365-ti.md), 并[将许可证分配给 Office 365 for business 中的用户](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="e5c30-111">Your organization has [Office 365 Threat Intelligence](office-365-ti.md) and [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
- <span data-ttu-id="e5c30-112">为你的组织启用了[Office 365 审核日志记录](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c30-112">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="e5c30-p103">您的组织具有为反垃圾邮件、反恶意软件、反网络钓鱼等定义的策略。请参阅[Office 365 安全&amp;合规中心中的威胁管理](threat-management.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c30-p103">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on. See [Threat management in the Office 365 Security &amp; Compliance Center](threat-management.md).</span></span>
    
- <span data-ttu-id="e5c30-p104">您是 Office 365 全局管理员, 或者您具有安全管理员或在安全&amp;合规中心中分配的搜索和清除角色。请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="e5c30-p104">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="dealing-with-suspicious-emails"></a><span data-ttu-id="e5c30-117">处理可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="e5c30-117">Dealing with suspicious emails</span></span>

<span data-ttu-id="e5c30-p105">恶意攻击者可能会向你的用户发送邮件, 以尝试对其凭据进行网络钓鱼并获取对公司机密的访问权限!为避免这种情况, 应使用 Office 365 提供的威胁防护服务, 包括 Exchange Online protection 和高级威胁防护。但是, 有时攻击者可能会向包含 url 的用户发送邮件, 并在稍后使该 url 指向恶意内容 (恶意软件等)。或者, 您可能会发现您的组织中的某个用户已受到威胁, 而该用户受到威胁时, 攻击者使用该帐户向公司中的其他用户发送电子邮件。在清理这两个方案的过程中, 您可能需要从用户收件箱中删除电子邮件。在这种情况下, 您可以利用威胁资源管理器查找和删除这些电子邮件!</span><span class="sxs-lookup"><span data-stu-id="e5c30-p105">Malicious attackers may be sending mail to your users to try and phish their credentials and gain access to your corporate secrets! In order to prevent this, you should use the threat protection services offered by Office 365, including Exchange Online Protection and Advanced Threat Protection. However, there are times when an attacker could send mail to your users containing a URL and only later on make that URL point to malicious content (malware, etc.). Alternatively, you may realize too late that a user in your organization has been compromised, and while that user was compromised, an attacker used that account to send email to other users in your company. As part of cleaning up both of these scenarios, you may want to remove email messages from user inboxes. In situations like these, you can leverage Threat Explorer to find and remove those email messages!</span></span>
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="e5c30-124">查找并删除已传递的可疑电子邮件</span><span class="sxs-lookup"><span data-stu-id="e5c30-124">Find and delete suspicious email that was delivered</span></span>

> [!TIP]
> <span data-ttu-id="e5c30-p106">[威胁资源管理器](get-started-with-ti.md#threat-explorer)(也称为 "资源管理器") 是一种功能强大的报表, 可用于多种用途, 如查找和删除邮件、标识恶意电子邮件发件人的 IP 地址或启动事件以进行进一步调查。下面的过程重点介绍如何使用资源管理器查找和删除收件人邮箱中的恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e5c30-p106">[Threat Explorer](get-started-with-ti.md#threat-explorer) (also referred to as Explorer), is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation. The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span> 
  
1. <span data-ttu-id="e5c30-p107">请转[https://protection.office.com](https://protection.office.com)到使用 Office 365 的工作或学校帐户登录并登录。这会将您带到&amp;安全合规中心。</span><span class="sxs-lookup"><span data-stu-id="e5c30-p107">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="e5c30-129">在左侧导航中, 选择 "**威胁管理** \> **资源管理器**"。</span><span class="sxs-lookup"><span data-stu-id="e5c30-129">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>
    
3. <span data-ttu-id="e5c30-130">在 "视图" 菜单中, 选择 "**所有电子邮件**"。</span><span class="sxs-lookup"><span data-stu-id="e5c30-130">In the View menu, choose **All email**.</span></span><br/><span data-ttu-id="e5c30-131">![使用 "视图" 菜单在电子邮件和内容报告之间进行选择](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span><span class="sxs-lookup"><span data-stu-id="e5c30-131">![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span></span>
  
4. <span data-ttu-id="e5c30-132">请注意报告中显示的标签, 如 "已**交货**"、"**未知**" 或 "已**传递到垃圾邮件**"。</span><span class="sxs-lookup"><span data-stu-id="e5c30-132">Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.</span></span><br/><span data-ttu-id="e5c30-133">![显示所有电子邮件的数据的威胁资源管理器](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span><span class="sxs-lookup"><span data-stu-id="e5c30-133">![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span></span><br/><span data-ttu-id="e5c30-134">(根据对组织的电子邮件执行的操作, 可能会看到其他标签, 如 "已**阻止**" 或 "**已替换**"。)</span><span class="sxs-lookup"><span data-stu-id="e5c30-134">(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)</span></span>
    
5. <span data-ttu-id="e5c30-135">在报告中, 选择 "已**传递**" 以仅查看在用户收件箱中结束的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="e5c30-135">In the report, choose **Delivered** to view only emails that ended up in users' inboxes.</span></span><br/><span data-ttu-id="e5c30-136">![单击 "传递给垃圾邮件" 将从视图中删除该数据](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span><span class="sxs-lookup"><span data-stu-id="e5c30-136">![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span></span>
  
6. <span data-ttu-id="e5c30-137">在图表下方, 查看图表下方的**电子邮件**列表。</span><span class="sxs-lookup"><span data-stu-id="e5c30-137">Below the chart, review the **Email** list below the chart.</span></span><br/><span data-ttu-id="e5c30-138">![在图表下方, 查看检测到的电子邮件的列表](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span><span class="sxs-lookup"><span data-stu-id="e5c30-138">![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span></span>
  
7. <span data-ttu-id="e5c30-p108">在列表中, 选择一个项目以查看有关该电子邮件的更多详细信息。例如, 您可以单击 "主题" 行来查看有关发件人、收件人、附件和其他类似电子邮件的信息。</span><span class="sxs-lookup"><span data-stu-id="e5c30-p108">In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.</span></span><br/>![您可以查看有关项目的其他信息, 包括详细信息和任何附件](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. <span data-ttu-id="e5c30-142">查看有关电子邮件的信息后, 选择列表中的一个或多个项目以激活 **+ 操作**。</span><span class="sxs-lookup"><span data-stu-id="e5c30-142">After viewing information about email messages, select one or more items in the list to activate **+ Actions**.</span></span>
    
9. <span data-ttu-id="e5c30-p109">使用 **+ 操作**列表应用操作, 例如**移到 "已删除**邮件"。这将从收件人邮箱中删除所选邮件。</span><span class="sxs-lookup"><span data-stu-id="e5c30-p109">Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This will delete the selected messages from the recipients' mailboxes.</span></span><br/><span data-ttu-id="e5c30-145">![当您选择一个或多个电子邮件时, 可以从多个可用的操作中进行选择](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span><span class="sxs-lookup"><span data-stu-id="e5c30-145">![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e5c30-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="e5c30-146">Related topics</span></span>

[<span data-ttu-id="e5c30-147">Office 365 威胁智能</span><span class="sxs-lookup"><span data-stu-id="e5c30-147">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="e5c30-148">Office 365 中的威胁防护</span><span class="sxs-lookup"><span data-stu-id="e5c30-148">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="e5c30-149">查看 Office 365 高级威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="e5c30-149">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

