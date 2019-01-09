---
title: Office 365 高级威胁防护
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/08/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: Office 365 高级威胁保护包括欺骗智能、 安全链接、 安全的附件和高级的防钓鱼功能。For Business 和 Microsoft 团队之前，还进行了高级的威胁保护扩展到 SharePoint Online、 OneDrive 中的文件。
ms.openlocfilehash: 6cdbdde2c91f8a9a77eb688ae27d509163da42a1
ms.sourcegitcommit: 03e64ead7805f3dfa9149252be8606efe50375df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "27769796"
---
# <a name="office-365-advanced-threat-protection"></a><span data-ttu-id="1c55c-104">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="1c55c-104">Office 365 Advanced Threat Protection</span></span>

## <a name="overview"></a><span data-ttu-id="1c55c-105">概述</span><span class="sxs-lookup"><span data-stu-id="1c55c-105">Overview</span></span>

<span data-ttu-id="1c55c-106">Office 365 高级威胁保护 (ATP) 有助于防止恶意攻击通过您的组织：</span><span class="sxs-lookup"><span data-stu-id="1c55c-106">Office 365 Advanced Threat Protection (ATP) helps to protect your organization from malicious attacks by:</span></span>
  
- <span data-ttu-id="1c55c-107">带[ATP 安全附件](atp-safe-attachments.md)的恶意软件扫描电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="1c55c-107">Scanning email attachments for malware with [ATP Safe Attachments](atp-safe-attachments.md)</span></span>
    
- <span data-ttu-id="1c55c-108">扫描的 web 地址 (Url) 中的电子邮件和 Office 文档[ATP 安全链接](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="1c55c-108">Scanning web addresses (URLs) in email messages and Office documents with [ATP Safe Links](atp-safe-links.md)</span></span>
    
- <span data-ttu-id="1c55c-109">识别和阻止与[SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)联机库中的恶意文件</span><span class="sxs-lookup"><span data-stu-id="1c55c-109">Identifying and blocking malicious files in online libraries with [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)</span></span>
    
- <span data-ttu-id="1c55c-110">检查未经授权欺骗[欺骗智能](learn-about-spoof-intelligence.md)与电子的邮件</span><span class="sxs-lookup"><span data-stu-id="1c55c-110">Checking email messages for unauthorized spoofing with [spoof intelligence](learn-about-spoof-intelligence.md)</span></span>
    
- <span data-ttu-id="1c55c-111">检测何时某人尝试模拟用户和组织的自定义域与[Office 365 中的 ATP 防钓鱼功能](atp-anti-phishing.md)</span><span class="sxs-lookup"><span data-stu-id="1c55c-111">Detecting when someone attempts to impersonate your users and your organization's custom domains with [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md)</span></span>
    
<span data-ttu-id="1c55c-p102">**通过 Office 365 ATP 保护由您组织的安全工作组的安全链接、 安全的附件和防钓鱼定义的策略**。非常重要定期查看和修改您的策略，以使其保持最新和要执行的新功能添加到服务的优点。</span><span class="sxs-lookup"><span data-stu-id="1c55c-p102">**Protection through Office 365 ATP is determined by policies that your organization's security team defines for Safe Links, Safe Attachments, and Anti-Phishing**. It's important to periodically review and revise your policies to keep them up to date and to take advantages of new features that are added to the service.</span></span> 

<span data-ttu-id="1c55c-p103">[报告可](view-reports-for-atp.md)显示如何使用 ATP 运行您的组织。这些报告还可以显示您可能需要以查看并更新您的策略的区域。然后，如果您有标记为恶意软件不应是，或文件您希望 Microsoft 要检查的文件，可以[将文件提交给 Microsoft 进行分析](#submit-a-suspicious-file-to-microsoft-for-analysis)。</span><span class="sxs-lookup"><span data-stu-id="1c55c-p103">[Reports are available](view-reports-for-atp.md) to show how ATP is working for your organization. These reports can also show you areas where you might need to review and update your policies. And, if you have files that are marked as malware that shouldn't be, or files you'd like Microsoft to examine, you can [submit a file to Microsoft for analysis](#submit-a-suspicious-file-to-microsoft-for-analysis).</span></span>

## <a name="new-features-are-continually-being-added-to-atp"></a><span data-ttu-id="1c55c-117">到 ATP 不断添加了新功能</span><span class="sxs-lookup"><span data-stu-id="1c55c-117">New features are continually being added to ATP</span></span>

<span data-ttu-id="1c55c-p104">我们将继续向 Office 365 中，添加新功能，并包含 ATP。下面是一些新功能，其中一些调用 ATP 策略必须经过审核和更新的列表。若要了解有关至此 ATP （或 Microsoft 365 一般） 的新功能的详细信息，请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。</span><span class="sxs-lookup"><span data-stu-id="1c55c-p104">We are continuing to add new features to Office 365, and that includes ATP. Below is a list of several new features, some of which call for an ATP policy to be reviewed and updated. To learn more about new features coming to ATP (or Microsoft 365 in general), visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).</span></span>


|<span data-ttu-id="1c55c-121">功能更新</span><span class="sxs-lookup"><span data-stu-id="1c55c-121">Feature updates</span></span>  |<span data-ttu-id="1c55c-122">拟办事项</span><span class="sxs-lookup"><span data-stu-id="1c55c-122">Action items</span></span>  |
|---------|---------|
|<span data-ttu-id="1c55c-p105">开始在年 10 月 2018年以及推出通过下的几个月，当用户正在使用 Outlook Web 应用程序 (OWA) 或 Outlook、 ATP 安全链接不呈现原始 Url 重写 Url。（我们调用此本机链接可见性）。</span><span class="sxs-lookup"><span data-stu-id="1c55c-p105">Beginning in October 2018 and rolling out over the next several months, when people are using Outlook Web Application (OWA) or Outlook, ATP Safe Links renders original URLs, not rewritten URLs. (We call this native link visibility.)</span></span>|<span data-ttu-id="1c55c-125">无</span><span class="sxs-lookup"><span data-stu-id="1c55c-125">None</span></span>         |
|<span data-ttu-id="1c55c-126">年 9 月 2018年中的开始、 [Office 365 ATP 警告页](atp-safe-links-warning-pages.md)功能新的配色方案、 更多详细信息，和以继续前进到尽管网站的功能在给定警告和建议。</span><span class="sxs-lookup"><span data-stu-id="1c55c-126">Beginning in September 2018, [Office 365 ATP warning pages](atp-safe-links-warning-pages.md) feature a new color scheme, more details, and the ability to continue to a site despite given warnings and recommendations.</span></span> |<span data-ttu-id="1c55c-127">无</span><span class="sxs-lookup"><span data-stu-id="1c55c-127">None</span></span>         |
|<span data-ttu-id="1c55c-128">开始在 2018年的第二部分中，ATP 安全链接被扩展保护于 Url 的 Office Online （Word Online、 Excel Online、 PowerPoint Online 和 OneNote 联机） 和 Office 365 ProPlus 上 mac。</span><span class="sxs-lookup"><span data-stu-id="1c55c-128">Beginning in the second half of 2018, ATP Safe Links protection is extended to apply to URLs in Office Online (Word Online, Excel Online, PowerPoint Online, and OneNote Online) and Office 365 ProPlus on Mac.</span></span>   |[<span data-ttu-id="1c55c-129">查看和编辑 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="1c55c-129">Review and edit your ATP Safe Links policies</span></span>](set-up-atp-safe-links-policies.md)  |
|<span data-ttu-id="1c55c-130">开始在后期年 5 月 2018 安全中[隔离](quarantine-email-messages.md)功能&amp;合规性中心将正在扩展到[的 SharePoint Online 的 OneDrive for Business 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="1c55c-130">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to [ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> |[<span data-ttu-id="1c55c-131">查看和编辑 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="1c55c-131">Review and edit your ATP Safe Attachments policies</span></span>](set-up-atp-safe-attachments-policies.md) |
|<span data-ttu-id="1c55c-132">从开始年 3 月 2018年，被扩展 ATP 安全链接保护应用于组织内的人员之间发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1c55c-132">Beginning in March 2018, ATP Safe Links protection is extended to apply to email sent between people within an organization.</span></span> |[<span data-ttu-id="1c55c-133">查看和编辑 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="1c55c-133">Review and edit your ATP Safe Links policies</span></span>](set-up-atp-safe-links-policies.md) |
|<span data-ttu-id="1c55c-134">从开始后期年 10 月 2017年，ATP 安全链接保护扩展到 Url 为 Url 或电子邮件中 Office 365 ProPlus 的文档，如 Word、 Excel、 PowerPoint 和 Visio 中对应用 Windows，以及 Office iOS 和 Android 设备上的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c55c-134">Beginning in late October 2017, ATP Safe Links protection is extended to apply to URLs in email as well as URLs in Office 365 ProPlus documents, such as Word, Excel, PowerPoint, and Visio on Windows, as well as Office apps on iOS and Android devices.</span></span>  |<span data-ttu-id="1c55c-135">请确保您使用的[Office 现代身份验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)</span><span class="sxs-lookup"><span data-stu-id="1c55c-135">Make sure you're using [Modern Authentication for Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)</span></span> |

      
## <a name="get-office-365-atp"></a><span data-ttu-id="1c55c-136">获取 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="1c55c-136">Get Office 365 ATP</span></span>

<span data-ttu-id="1c55c-p106">Office 365 ATP 包含订阅，如[Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 业务](https://www.microsoft.com/microsoft-365/business)、 Office 365 企业 E5，和 Office 365 教育版 A5 中。如果您的组织具有不包括 Office 365 ATP 的 Office 365 订阅，您可能可以作为购买 ATP。有关详细信息，请参阅[Office 365 高级威胁 Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="1c55c-p106">Office 365 ATP is included in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, and Office 365 Education A5. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> 

## <a name="define-policies-for-atp"></a><span data-ttu-id="1c55c-140">为 ATP 定义策略</span><span class="sxs-lookup"><span data-stu-id="1c55c-140">Define policies for ATP</span></span>

- <span data-ttu-id="1c55c-141">**[设置 Office 365 中的 ATP 防钓鱼策略](set-up-anti-phishing-policies.md)** 包括基于模拟的攻击保护的攻击者发送电子邮件消息的状态显示为来自受信任的人员或域</span><span class="sxs-lookup"><span data-stu-id="1c55c-141">**[Set up ATP anti-phishing policies in Office 365](set-up-anti-phishing-policies.md)** including impersonation-based attacks to protect against attackers who send email messages that appear to be from trusted people or domains</span></span> 

- <span data-ttu-id="1c55c-142">**[设置 Office 365 中的安全链接 ATP 策略](set-up-atp-safe-links-policies.md)** 包括您组织的[自定义被阻止的 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)和[自定义"执行不重写"Url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)</span><span class="sxs-lookup"><span data-stu-id="1c55c-142">**[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)** including your organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md) and [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)</span></span>
    
- <span data-ttu-id="1c55c-143">**[设置 Office 365 中的 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)** 和从多个选项，如[动态交付和预览过程](dynamic-delivery-and-previewing.md)中进行选择</span><span class="sxs-lookup"><span data-stu-id="1c55c-143">**[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)** and choose from several options, such as [Dynamic Delivery and previewing](dynamic-delivery-and-previewing.md)</span></span>
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a><span data-ttu-id="1c55c-144">请参阅 ATP 通过查看报告的工作方式</span><span class="sxs-lookup"><span data-stu-id="1c55c-144">See how ATP is working by viewing reports</span></span>

<span data-ttu-id="1c55c-145">ATP 策略后，报告是可用于显示如何服务运行正常。</span><span class="sxs-lookup"><span data-stu-id="1c55c-145">After your ATP policies are in place, reports are available to show how the service is working.</span></span>

<span data-ttu-id="1c55c-146">[![安全&amp;合规性中心仪表板可帮助您看到正常高级威胁保护](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span><span class="sxs-lookup"><span data-stu-id="1c55c-146">[![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span></span>
  
1. <span data-ttu-id="1c55c-p107">请确保您是 Office 365 全局管理员、 安全管理员或安全读取器。(请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。)</span><span class="sxs-lookup"><span data-stu-id="1c55c-p107">Make sure that you are an Office 365 global administrator, security administrator, or security reader. (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>
    
2. <span data-ttu-id="1c55c-149">[查看报告的高级威胁保护](view-reports-for-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="1c55c-149">[View reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span>
    
3. <span data-ttu-id="1c55c-p108">如果需要对进行调整您的安全策略。请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="1c55c-p108">If needed, make adjustments to your security policies. See the following resources:</span></span>
      - [<span data-ttu-id="1c55c-152">Office 365 中的 ATP 防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="1c55c-152">ATP anti-phishing policies in Office 365</span></span>](set-up-anti-phishing-policies.md)
      - [<span data-ttu-id="1c55c-153">Office 365 中的安全链接 ATP 策略</span><span class="sxs-lookup"><span data-stu-id="1c55c-153">ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
      - [<span data-ttu-id="1c55c-154">Office 365 中的 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="1c55c-154">ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a><span data-ttu-id="1c55c-155">可疑将文件提交给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="1c55c-155">Submit a suspicious file to Microsoft for analysis</span></span>

- <span data-ttu-id="1c55c-p109">如果您收到您怀疑可能恶意软件的文件，您可以提交给 Microsoft 进行分析该文件。请访问[Windows Defender 安全智能提交门户](https://go.microsoft.com/fwlink/?linkid=857185)。</span><span class="sxs-lookup"><span data-stu-id="1c55c-p109">If you get a file that you suspect could be malware, you can submit that file to Microsoft for analysis. Visit the [Windows Defender Security Intelligence submission portal](https://go.microsoft.com/fwlink/?linkid=857185).</span></span>

- <span data-ttu-id="1c55c-158">如果您要获取想要提交给 Microsoft 进行分析的电子邮件 （使用或不附件），请使用[报告消息加载项](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="1c55c-158">If you get an email message (with or without an attachment) that you'd like to submit to Microsoft for analysis, use the [Report Message add-in](enable-the-report-message-add-in.md).</span></span> 
  

