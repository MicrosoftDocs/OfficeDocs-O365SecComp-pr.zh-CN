---
title: Office 365 高级威胁防护
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/04/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: Office 365 高级威胁保护包括欺骗智能、 安全链接、 安全的附件和高级的防钓鱼功能。For Business 和 Microsoft 团队之前，还进行了高级的威胁保护扩展到 SharePoint Online、 OneDrive 中的文件。
ms.openlocfilehash: b483ceb0da53b2f1c216f60d5271781072ebcf17
ms.sourcegitcommit: d6a28c4f6db6a676ca960173e8ff8f17d4aa1c4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29755223"
---
# <a name="office-365-advanced-threat-protection"></a><span data-ttu-id="59fce-104">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="59fce-104">Office 365 Advanced Threat Protection</span></span>

## <a name="overview-of-office-365-advanced-threat-protection"></a><span data-ttu-id="59fce-105">Office 365 的高级的威胁保护的概述</span><span class="sxs-lookup"><span data-stu-id="59fce-105">Overview of Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="59fce-106">Office 365 高级威胁保护 (ATP) 有助于防止恶意攻击通过您的组织：</span><span class="sxs-lookup"><span data-stu-id="59fce-106">Office 365 Advanced Threat Protection (ATP) helps to protect your organization from malicious attacks by:</span></span>
  
- <span data-ttu-id="59fce-107">带[ATP 安全附件](atp-safe-attachments.md)的恶意软件扫描电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="59fce-107">Scanning email attachments for malware with [ATP Safe Attachments](atp-safe-attachments.md)</span></span>
    
- <span data-ttu-id="59fce-108">扫描的 web 地址 (Url) 中的电子邮件和 Office 文档[ATP 安全链接](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="59fce-108">Scanning web addresses (URLs) in email messages and Office documents with [ATP Safe Links](atp-safe-links.md)</span></span>
    
- <span data-ttu-id="59fce-109">识别和阻止与[SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)联机库中的恶意文件</span><span class="sxs-lookup"><span data-stu-id="59fce-109">Identifying and blocking malicious files in online libraries with [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)</span></span>
    
- <span data-ttu-id="59fce-110">检查未经授权欺骗[欺骗智能](learn-about-spoof-intelligence.md)与电子的邮件</span><span class="sxs-lookup"><span data-stu-id="59fce-110">Checking email messages for unauthorized spoofing with [spoof intelligence](learn-about-spoof-intelligence.md)</span></span>
    
- <span data-ttu-id="59fce-111">检测何时某人尝试模拟用户和组织的自定义域与[Office 365 中的 ATP 防钓鱼功能](atp-anti-phishing.md)</span><span class="sxs-lookup"><span data-stu-id="59fce-111">Detecting when someone attempts to impersonate your users and your organization's custom domains with [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md)</span></span>
    
<span data-ttu-id="59fce-p102">**通过 Office 365 ATP 保护由您组织的安全工作组的安全链接、 安全的附件和防钓鱼定义的策略**。务必定义策略，并进行定期查看和修改这些策略，以使其保持最新和要执行的新功能添加到服务的优点。</span><span class="sxs-lookup"><span data-stu-id="59fce-p102">**Protection through Office 365 ATP is determined by policies that your organization's security team defines for Safe Links, Safe Attachments, and Anti-Phishing**. It's important to define policies, and to periodically review and revise those policies to keep them up to date and to take advantages of new features that are added to the service.</span></span> 

<span data-ttu-id="59fce-p103">[报告可](view-reports-for-atp.md)显示如何使用 ATP 运行您的组织。这些报告还可以显示您可能需要以查看并更新您的策略的区域。然后，如果您有标记为恶意软件不应是，或文件您希望 Microsoft 要检查的文件，可以[将文件提交给 Microsoft 进行分析](#submit-a-suspicious-file-to-microsoft-for-analysis)。</span><span class="sxs-lookup"><span data-stu-id="59fce-p103">[Reports are available](view-reports-for-atp.md) to show how ATP is working for your organization. These reports can also show you areas where you might need to review and update your policies. And, if you have files that are marked as malware that shouldn't be, or files you'd like Microsoft to examine, you can [submit a file to Microsoft for analysis](#submit-a-suspicious-file-to-microsoft-for-analysis).</span></span>

## <a name="new-features-are-continually-being-added-to-atp"></a><span data-ttu-id="59fce-117">到 ATP 不断添加了新功能</span><span class="sxs-lookup"><span data-stu-id="59fce-117">New features are continually being added to ATP</span></span>

<span data-ttu-id="59fce-p104">我们将继续向 Office 365 中，添加新功能，并包含 ATP。下面是一些新功能，其中一些调用 ATP 策略必须经过审核和更新的列表。若要了解有关至此 ATP （或 Microsoft 365 一般） 的新功能的详细信息，请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。</span><span class="sxs-lookup"><span data-stu-id="59fce-p104">We are continuing to add new features to Office 365, and that includes ATP. Below is a list of several new features, some of which call for an ATP policy to be reviewed and updated. To learn more about new features coming to ATP (or Microsoft 365 in general), visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).</span></span>


|<span data-ttu-id="59fce-121">功能更新</span><span class="sxs-lookup"><span data-stu-id="59fce-121">Feature updates</span></span>  |<span data-ttu-id="59fce-122">拟办事项</span><span class="sxs-lookup"><span data-stu-id="59fce-122">Action items</span></span>  |
|---------|---------|
|<span data-ttu-id="59fce-p105">开始在年 10 月 2018年以及推出通过下的几个月，当人员使用的 Outlook 或 Outlook Web 应用程序 (OWA)、 ATP 安全链接不呈现原始 Url 重写 Url。（我们调用此本机链接呈现）。</span><span class="sxs-lookup"><span data-stu-id="59fce-p105">Beginning in October 2018 and rolling out over the next several months, when people are using Outlook or Outlook Web Application (OWA), ATP Safe Links renders original URLs, not rewritten URLs. (We call this native link rendering.)</span></span><br><span data-ttu-id="59fce-125">适用于您的组织本机链接呈现后，此功能将工作 Outlook 365 （单击以运行） 和 OWA 中。</span><span class="sxs-lookup"><span data-stu-id="59fce-125">When native link rendering is available for your organization, this feature will work in Outlook 365 (Click-to-Run) and OWA.</span></span>|<span data-ttu-id="59fce-126">无</span><span class="sxs-lookup"><span data-stu-id="59fce-126">None</span></span>         |
|<span data-ttu-id="59fce-127">年 9 月 2018年中的开始、 [Office 365 ATP 警告页](atp-safe-links-warning-pages.md)功能新的配色方案、 更多详细信息，和以继续前进到尽管网站的功能在给定警告和建议。</span><span class="sxs-lookup"><span data-stu-id="59fce-127">Beginning in September 2018, [Office 365 ATP warning pages](atp-safe-links-warning-pages.md) feature a new color scheme, more details, and the ability to continue to a site despite given warnings and recommendations.</span></span> |<span data-ttu-id="59fce-128">无</span><span class="sxs-lookup"><span data-stu-id="59fce-128">None</span></span>         |
|<span data-ttu-id="59fce-129">开始在 2018年的第二部分中，ATP 安全链接被扩展保护于 Url 的 Office Online （Word Online、 Excel Online、 PowerPoint Online 和 OneNote 联机） 和 Office 365 ProPlus 上 mac。</span><span class="sxs-lookup"><span data-stu-id="59fce-129">Beginning in the second half of 2018, ATP Safe Links protection is extended to apply to URLs in Office Online (Word Online, Excel Online, PowerPoint Online, and OneNote Online) and Office 365 ProPlus on Mac.</span></span>   |[<span data-ttu-id="59fce-130">查看和编辑 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="59fce-130">Review and edit your ATP Safe Links policies</span></span>](set-up-atp-safe-links-policies.md)  |
|<span data-ttu-id="59fce-131">开始在后期年 5 月 2018 安全中[隔离](quarantine-email-messages.md)功能&amp;合规性中心将正在扩展到[的 SharePoint Online 的 OneDrive for Business 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="59fce-131">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to [ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> |[<span data-ttu-id="59fce-132">查看和编辑 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="59fce-132">Review and edit your ATP Safe Attachments policies</span></span>](set-up-atp-safe-attachments-policies.md) |
|<span data-ttu-id="59fce-133">从开始年 3 月 2018年，被扩展 ATP 安全链接保护应用于组织内的人员之间发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="59fce-133">Beginning in March 2018, ATP Safe Links protection is extended to apply to email sent between people within an organization.</span></span> |[<span data-ttu-id="59fce-134">查看和编辑 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="59fce-134">Review and edit your ATP Safe Links policies</span></span>](set-up-atp-safe-links-policies.md) |
|<span data-ttu-id="59fce-135">从开始后期年 10 月 2017年，ATP 安全链接保护扩展到 Url 为 Url 或电子邮件中 Office 365 ProPlus 的文档，如 Word、 Excel、 PowerPoint 和 Visio 中对应用 Windows，以及 Office iOS 和 Android 设备上的应用程序。</span><span class="sxs-lookup"><span data-stu-id="59fce-135">Beginning in late October 2017, ATP Safe Links protection is extended to apply to URLs in email as well as URLs in Office 365 ProPlus documents, such as Word, Excel, PowerPoint, and Visio on Windows, as well as Office apps on iOS and Android devices.</span></span>  |<span data-ttu-id="59fce-136">请确保您使用的[Office 现代身份验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)</span><span class="sxs-lookup"><span data-stu-id="59fce-136">Make sure you're using [Modern Authentication for Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)</span></span> |
  
## <a name="get-office-365-atp"></a><span data-ttu-id="59fce-137">获取 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="59fce-137">Get Office 365 ATP</span></span>

<span data-ttu-id="59fce-p106">Office 365 ATP 包含订阅，如[Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 业务](https://www.microsoft.com/microsoft-365/business)、 Office 365 企业 E5，和 Office 365 教育版 A5 中。如果您的组织具有不包括 Office 365 ATP 的 Office 365 订阅，您可能可以作为购买 ATP。有关详细信息，请参阅[Office 365 高级威胁 Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="59fce-p106">Office 365 ATP is included in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, and Office 365 Education A5. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> 

## <a name="define-policies-for-atp"></a><span data-ttu-id="59fce-141">为 ATP 定义策略</span><span class="sxs-lookup"><span data-stu-id="59fce-141">Define policies for ATP</span></span>

<span data-ttu-id="59fce-142">若要定义 （或编辑） ATP 策略，您必须为分配下表中所述的角色之一：</span><span class="sxs-lookup"><span data-stu-id="59fce-142">To define (or edit) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="59fce-143">角色</span><span class="sxs-lookup"><span data-stu-id="59fce-143">Role</span></span>  |<span data-ttu-id="59fce-144">其中/如何分配</span><span class="sxs-lookup"><span data-stu-id="59fce-144">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="59fce-145">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="59fce-145">Office 365 Global Administrator</span></span> |<span data-ttu-id="59fce-p107">注册以购买 Office 365 的人是默认情况下是全局管理员。（请参阅要了解的[有关 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)）。</span><span class="sxs-lookup"><span data-stu-id="59fce-p107">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="59fce-148">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="59fce-148">Security Administrator</span></span> |<span data-ttu-id="59fce-149">Azure Active Directory 管理员中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="59fce-149">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="59fce-150">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="59fce-150">Exchange Online Organization Management</span></span> |<span data-ttu-id="59fce-151">Exchange 管理员中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="59fce-151">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="59fce-152">或</span><span class="sxs-lookup"><span data-stu-id="59fce-152">or</span></span> <br>  <span data-ttu-id="59fce-153">PowerShell cmdlet (请参阅[Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="59fce-153">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="59fce-154">若要了解有关角色和权限的详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="59fce-154">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="59fce-155">有几种 ATP 策略用于定义和定期查看。</span><span class="sxs-lookup"><span data-stu-id="59fce-155">There are several kinds of ATP policies to define and periodically review.</span></span>

1. <span data-ttu-id="59fce-156">**[设置 Office 365 中的 ATP 防钓鱼策略](set-up-anti-phishing-policies.md)** 包括基于模拟的攻击保护的攻击者发送电子邮件消息的显示为来自受信任的人员或域。</span><span class="sxs-lookup"><span data-stu-id="59fce-156">**[Set up ATP anti-phishing policies in Office 365](set-up-anti-phishing-policies.md)** including impersonation-based attacks to protect against attackers who send email messages that appear to be from trusted people or domains.</span></span> 

2. <span data-ttu-id="59fce-157">**[设置 Office 365 中的安全链接 ATP 策略](set-up-atp-safe-links-policies.md)** 包括您组织的[自定义被阻止的 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)和[自定义"执行不重写"Url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="59fce-157">**[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)** including your organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md) and [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
    
3. <span data-ttu-id="59fce-158">**[设置 Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)** 和从多个选项，如[动态交付和预览过程](dynamic-delivery-and-previewing.md)中进行选择。</span><span class="sxs-lookup"><span data-stu-id="59fce-158">**[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)** and choose from several options, such as [Dynamic Delivery and previewing](dynamic-delivery-and-previewing.md).</span></span>
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a><span data-ttu-id="59fce-159">请参阅 ATP 通过查看报告的工作方式</span><span class="sxs-lookup"><span data-stu-id="59fce-159">See how ATP is working by viewing reports</span></span>

<span data-ttu-id="59fce-p108">ATP 策略后，报告是可用于显示如何服务运行正常。(在 Office 365 安全性 & 合规性中心中，转到**报告** > **仪表板**。)</span><span class="sxs-lookup"><span data-stu-id="59fce-p108">After your ATP policies are in place, reports are available to show how the service is working. (In the Office 365 Security & Compliance Center, go to **Reports** > **Dashboard**.)</span></span>

<span data-ttu-id="59fce-162">[![安全&amp;合规性中心仪表板可帮助您看到正常高级威胁保护](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span><span class="sxs-lookup"><span data-stu-id="59fce-162">[![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span></span>
  
1. <span data-ttu-id="59fce-163">为 Office 365 全局管理员、 安全管理员或安全读取器，转到[https://protection.office.com](https://protection.office.com)和登录。</span><span class="sxs-lookup"><span data-stu-id="59fce-163">As an Office 365 global administrator, security administrator, or security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>
    
2. <span data-ttu-id="59fce-p109">转到**报告** > **仪表板**。（若要获取这些报告的帮助，请参阅[View reports 高级威胁 protection](view-reports-for-atp.md)。）</span><span class="sxs-lookup"><span data-stu-id="59fce-p109">Go to **Reports** > **Dashboard**. (To get help with these reports, see [View reports for Advanced Threat Protection](view-reports-for-atp.md).)</span></span>
    
3. <span data-ttu-id="59fce-p110">如果需要对进行调整您的安全策略。若要获取与此帮助，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="59fce-p110">If needed, make adjustments to your security policies. To get help with this, see the following resources:</span></span>
      - [<span data-ttu-id="59fce-168">Office 365 中的 ATP 防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="59fce-168">ATP anti-phishing policies in Office 365</span></span>](set-up-anti-phishing-policies.md)
      - [<span data-ttu-id="59fce-169">Office 365 中的安全链接 ATP 策略</span><span class="sxs-lookup"><span data-stu-id="59fce-169">ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
      - [<span data-ttu-id="59fce-170">Office 365 中的 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="59fce-170">ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a><span data-ttu-id="59fce-171">可疑将文件提交给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="59fce-171">Submit a suspicious file to Microsoft for analysis</span></span>

- <span data-ttu-id="59fce-p111">如果您收到您怀疑可能恶意软件的文件，您可以提交给 Microsoft 进行分析该文件。请访问[Windows Defender 安全智能提交门户](https://go.microsoft.com/fwlink/?linkid=857185)。</span><span class="sxs-lookup"><span data-stu-id="59fce-p111">If you get a file that you suspect could be malware, you can submit that file to Microsoft for analysis. Visit the [Windows Defender Security Intelligence submission portal](https://go.microsoft.com/fwlink/?linkid=857185).</span></span>

- <span data-ttu-id="59fce-174">如果您要获取想要提交给 Microsoft 进行分析的电子邮件 （使用或不附件），请使用[报告消息加载项](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="59fce-174">If you get an email message (with or without an attachment) that you'd like to submit to Microsoft for analysis, use the [Report Message add-in](enable-the-report-message-add-in.md).</span></span> 
  

