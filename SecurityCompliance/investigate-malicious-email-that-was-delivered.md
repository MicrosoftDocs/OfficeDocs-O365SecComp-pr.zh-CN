---
title: 查找并调查恶意电子邮件已送达 （Office 365 威胁智能）
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 8/6/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
description: 了解如何使用威胁智能来查找和调查恶意电子邮件。
ms.openlocfilehash: b6d4f8a5d1fcfce4461b91796b1264f94d1eb4d1
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014914"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-office-365-threat-intelligence"></a><span data-ttu-id="5d9bb-103">查找并调查恶意电子邮件已送达 （Office 365 威胁智能）</span><span class="sxs-lookup"><span data-stu-id="5d9bb-103">Find and investigate malicious email that was delivered (Office 365 Threat Intelligence)</span></span>

<span data-ttu-id="5d9bb-p101">[Office 365 威胁智能](office-365-ti.md)可以调查您的用户处于风险，采取措施来保护您的组织的活动。例如，如果您是组织的安全工作组的一部分，您可以查找和调查的可疑邮件已送达您的用户。您可以使用[威胁资源管理器](get-started-with-ti.md#threat-explorer)来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-p101">[Office 365 Threat Intelligence](office-365-ti.md) enables you to investigate activities that put your users at risk and take action to protect your organization. For example, if you are part of your organization's security team, you can find and investigate suspicious email messages that were delivered to your users. You can do this by using [Threat Explorer](get-started-with-ti.md#threat-explorer).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d9bb-p102">Office 365 威胁智能是在 Office 365 企业 E5 中可用。如果您的组织使用的另一个 Office 365 企业版订阅，可以作为购买 Office 365 威胁智能。(作为全局管理员，在 Office 365 管理中心中，选择**帐单** \> **添加订阅**。)有关详细信息，请参阅[Office 365 平台服务说明： Office 365 安全性&amp;合规性中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[购买或编辑企业的 Office 365 的加载项](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-p102">Office 365 Threat Intelligence is available in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Office 365 Threat Intelligence can be purchased as an add-on. (As a global administrator, in the Office 365 admin center, choose **Billing** \> **Add subscriptions**.) For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="5d9bb-110">开始之前...</span><span class="sxs-lookup"><span data-stu-id="5d9bb-110">Before you begin...</span></span>

<span data-ttu-id="5d9bb-111">请确保满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="5d9bb-111">Make sure that the following requirements are met:</span></span>
  
- <span data-ttu-id="5d9bb-112">您的组织具有[Office 365 威胁智能](office-365-ti.md)和[分配给为企业的 Office 365 中的用户的许可证](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-112">Your organization has [Office 365 Threat Intelligence](office-365-ti.md) and [Assign licenses to users in Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
- <span data-ttu-id="5d9bb-113">[Office 365 审核日志记录](turn-audit-log-search-on-or-off.md)处于打开状态为您的组织。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-113">[Office 365 audit logging](turn-audit-log-search-on-or-off.md) is turned on for your organization.</span></span> 
    
- <span data-ttu-id="5d9bb-p103">贵组织拥有的反垃圾邮件、 反恶意软件、 防钓鱼等定义的策略。请参阅[威胁管理 Office 365 安全性&amp;合规性中心](threat-management.md)。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-p103">Your organization has policies defined for anti-spam, anti-malware, anti-phishing, and so on. See [Threat management in the Office 365 Security &amp; Compliance Center](threat-management.md).</span></span>
    
- <span data-ttu-id="5d9bb-p104">您是 Office 365 全局管理员，或您具有安全管理员或分配安全中搜索和清除角色&amp;合规性中心。请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-p104">You are an Office 365 global administrator, or you have either the Security Administrator or the Search and Purge role assigned in the Security &amp; Compliance Center. See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    
## <a name="dealing-with-suspicious-emails"></a><span data-ttu-id="5d9bb-118">处理可疑的电子邮件</span><span class="sxs-lookup"><span data-stu-id="5d9bb-118">Dealing with suspicious emails</span></span>

<span data-ttu-id="5d9bb-p105">恶意攻击者可能将邮件发送到您的用户尝试和网络钓鱼诈骗其凭据，并可以访问您的公司机密 ！为了防止此，您应使用提供的 Office 365，包括 Exchange Online Protection 和高级威胁保护威胁保护服务。但是，有攻击者可以向您包含 URL 的用户发送邮件并仅更高版本上对恶意内容 （恶意软件等） 的 URL 点时的时间。此外，您可能会发现晚已泄露您组织内的用户，和时该用户已泄露，攻击者使用该帐户向公司中的其他用户发送电子邮件。作为清理这两种方案的一部分，您可能要从用户收件箱中删除电子邮件。在以下情况下，您可以利用威胁资源管理器中，找到并删除这些邮件 ！</span><span class="sxs-lookup"><span data-stu-id="5d9bb-p105">Malicious attackers may be sending mail to your users to try and phish their credentials and gain access to your corporate secrets! In order to prevent this, you should use the threat protection services offered by Office 365, including Exchange Online Protection and Advanced Threat Protection. However, there are times when an attacker could send mail to your users containing a URL and only later on make that URL point to malicious content (malware, etc.). Alternatively, you may realize too late that a user in your organization has been compromised, and while that user was compromised, an attacker used that account to send email to other users in your company. As part of cleaning up both of these scenarios, you may want to remove email messages from user inboxes. In situations like these, you can leverage Threat Explorer to find and remove those email messages!</span></span>
  
## <a name="find-and-delete-suspicious-email-that-was-delivered"></a><span data-ttu-id="5d9bb-125">查找并删除可疑的已发送的电子邮件</span><span class="sxs-lookup"><span data-stu-id="5d9bb-125">Find and delete suspicious email that was delivered</span></span>

> [!TIP]
> <span data-ttu-id="5d9bb-p106">[威胁资源管理器](get-started-with-ti.md#threat-explorer)（也称为资源管理器） 是一个强大的报表，可以提供多种用途，如查找和删除邮件、 标识恶意电子邮件发件人的 IP 地址或启动进一步调查事件。下面的过程重点介绍使用资源管理器查找并从收件人邮箱删除恶意电子邮件。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-p106">[Threat Explorer](get-started-with-ti.md#threat-explorer) (also referred to as Explorer), is a powerful report that can serve multiple purposes, such as finding and deleting messages, identifying the IP address of a malicious email sender, or starting an incident for further investigation. The following procedure focuses on using Explorer to find and delete malicious email from recipients mailboxes.</span></span> 
  
1. <span data-ttu-id="5d9bb-p107">转到[https://protection.office.com](https://protection.office.com)和 Office 365 中使用您的工作或学校帐户登录。您将转到安全&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-p107">Go to [https://protection.office.com](https://protection.office.com) and sign in using your work or school account for Office 365. This takes you to the Security &amp; Compliance Center.</span></span> 
    
2. <span data-ttu-id="5d9bb-130">在左侧导航窗格中，选择**威胁管理** \> **资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-130">In the left navigation, choose **Threat management** \> **Explorer**.</span></span>
    
3. <span data-ttu-id="5d9bb-131">在视图菜单中，选择**所有电子邮件**。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-131">In the View menu, choose **All email**.</span></span><br/><span data-ttu-id="5d9bb-132">![使用视图菜单选择之间电子邮件和内容的报告](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span><span class="sxs-lookup"><span data-stu-id="5d9bb-132">![Use the View menu to choose between Email and Content reports](media/d39013ff-93b6-42f6-bee5-628895c251c2.png)</span></span>
  
4. <span data-ttu-id="5d9bb-133">请注意报表，如**传递**、**未知**，或**传递到垃圾**中显示的标签。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-133">Notice the labels that appear in the report, such as **Delivered**, **Unknown**, or **Delivered to junk**.</span></span><br/><span data-ttu-id="5d9bb-134">![威胁资源管理器中显示的所有电子邮件的数据](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span><span class="sxs-lookup"><span data-stu-id="5d9bb-134">![Threat Explorer showing data for all email](media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)</span></span><br/><span data-ttu-id="5d9bb-135">（具体取决于您的组织的电子邮件所采取的操作，您可能会看到更多标签，如**已阻止**或**取代**。）</span><span class="sxs-lookup"><span data-stu-id="5d9bb-135">(Depending on the actions that were taken on email messages for your organization, you might see additional labels, such as **Blocked** or **Replaced**.)</span></span>
    
5. <span data-ttu-id="5d9bb-136">在报表中，选择以查看仅用户的收件箱中的最后的电子邮件已**传递**。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-136">In the report, choose **Delivered** to view only emails that ended up in users' inboxes.</span></span><br/><span data-ttu-id="5d9bb-137">![单击"传递到垃圾邮件"从视图中删除该数据](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span><span class="sxs-lookup"><span data-stu-id="5d9bb-137">![Clicking "Delivered to junk" removes that data from view](media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)</span></span>
  
6. <span data-ttu-id="5d9bb-138">图表，下方查看位于图表下方的**电子邮件**列表。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-138">Below the chart, review the **Email** list below the chart.</span></span><br/><span data-ttu-id="5d9bb-139">![图表，下方查看检测到的电子邮件的列表](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span><span class="sxs-lookup"><span data-stu-id="5d9bb-139">![Below the chart, view a list of email messages that were detected](media/dfb60590-1236-499d-97da-86c68621e2bc.png)</span></span>
  
7. <span data-ttu-id="5d9bb-p108">在列表中，选择一个项目以查看有关该电子邮件的详细信息。例如，您可以单击以查看信息发件人、 收件人、 附件和其他类似的电子邮件的主题行。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-p108">In the list, choose an item to view more details about that email message. For example, you can click the subject line to view information about the sender, recipients, attachments, and other similar email messages.</span></span><br/>![您可以查看关于该项，包括详细信息和任何附件的其他信息](media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
8. <span data-ttu-id="5d9bb-143">查看有关电子邮件的信息后, 激活 **+ 操作**列表中选择一个或多个项目。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-143">After viewing information about email messages, select one or more items in the list to activate **+ Actions**.</span></span>
    
9. <span data-ttu-id="5d9bb-p109">使用 **+ 操作**列表中应用操作，如**移动到已删除**项目。这将从收件人的邮箱中删除选定的邮件。</span><span class="sxs-lookup"><span data-stu-id="5d9bb-p109">Use the **+ Actions** list to apply an action, such as **Move to deleted** items. This will delete the selected messages from the recipients' mailboxes.</span></span><br/><span data-ttu-id="5d9bb-146">![选择一个或多个电子邮件时，您可以从几个可用操作](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span><span class="sxs-lookup"><span data-stu-id="5d9bb-146">![When you select one or more email messages, you can choose from several available actions](media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5d9bb-147">相关主题</span><span class="sxs-lookup"><span data-stu-id="5d9bb-147">Related topics</span></span>

[<span data-ttu-id="5d9bb-148">Office 365 威胁智能</span><span class="sxs-lookup"><span data-stu-id="5d9bb-148">Office 365 Threat Intelligence</span></span>](office-365-ti.md)
  
[<span data-ttu-id="5d9bb-149">Office 365 中的威胁防护</span><span class="sxs-lookup"><span data-stu-id="5d9bb-149">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="5d9bb-150">Office 365 高级威胁保护的视图报告</span><span class="sxs-lookup"><span data-stu-id="5d9bb-150">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

