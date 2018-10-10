---
title: Office 365 高级威胁防护
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 10/09/2018
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
description: Office 365 高级威胁保护包括欺骗智能、 安全链接、 安全的附件和高级的防钓鱼功能。For Business 和 Microsoft 团队之前，还进行了高级的威胁保护扩展到 SharePoint Online、 OneDrive 中的文件。
ms.openlocfilehash: fed816ec8cd0e3e7a6b5118fde35d81647b94f02
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454349"
---
# <a name="office-365-advanced-threat-protection"></a><span data-ttu-id="919df-104">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="919df-104">Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="919df-105">Office 365 高级威胁保护 (ATP) 有助于防止恶意攻击通过您的组织：</span><span class="sxs-lookup"><span data-stu-id="919df-105">Office 365 Advanced Threat Protection (ATP) helps to protect your organization from malicious attacks by:</span></span>
  
- <span data-ttu-id="919df-106">带[ATP 安全附件](atp-safe-attachments.md)的恶意软件扫描电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="919df-106">Scanning email attachments for malware with [ATP Safe Attachments](atp-safe-attachments.md)</span></span>
    
- <span data-ttu-id="919df-107">扫描的 web 地址 (Url) 中的电子邮件和 Office 文档[ATP 安全链接](atp-safe-links.md)</span><span class="sxs-lookup"><span data-stu-id="919df-107">Scanning web addresses (URLs) in email messages and Office documents with [ATP Safe Links](atp-safe-links.md)</span></span>
    
- <span data-ttu-id="919df-108">识别和阻止与[SharePoint、 OneDrive 和 Microsoft 团队 ATP](atp-for-spo-odb-and-teams.md)联机库中的恶意文件</span><span class="sxs-lookup"><span data-stu-id="919df-108">Identifying and blocking malicious files in online libraries with [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)</span></span>
    
- <span data-ttu-id="919df-109">检查未经授权欺骗[欺骗智能](learn-about-spoof-intelligence.md)与电子的邮件</span><span class="sxs-lookup"><span data-stu-id="919df-109">Checking email messages for unauthorized spoofing with [spoof intelligence](learn-about-spoof-intelligence.md)</span></span>
    
- <span data-ttu-id="919df-110">检测何时某人尝试模拟用户和组织的自定义域与[Office 365 中的 ATP 防钓鱼功能](atp-anti-phishing.md)</span><span class="sxs-lookup"><span data-stu-id="919df-110">Detecting when someone attempts to impersonate your users and your organization's custom domains with [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md)</span></span>
    
<span data-ttu-id="919df-p102">**通过 Office 365 ATP 保护由您组织的安全工作组的安全链接、 安全的附件和防钓鱼定义的策略**。非常重要定期查看和修改您的策略，以使其保持最新和要执行的新功能添加到服务的优点。[报告可](view-reports-for-atp.md)显示如何使用 ATP 运行您的组织。这些报告还可以显示您可能需要以查看并更新您的策略的区域。然后，如果您有标记为恶意软件不应是，或文件您希望 Microsoft 要检查的文件，可以[将文件提交给 Microsoft 进行分析](#submit-a-suspicious-file-to-microsoft-for-analysis)。</span><span class="sxs-lookup"><span data-stu-id="919df-p102">**Protection through Office 365 ATP is determined by policies that your organization's security team defines for Safe Links, Safe Attachments, and Anti-Phishing**. It's important to periodically review and revise your policies to keep them up to date and to take advantages of new features that are added to the service. [Reports are available](view-reports-for-atp.md) to show how ATP is working for your organization. These reports can also show you areas where you might need to review and update your policies. And, if you have files that are marked as malware that shouldn't be, or files you'd like Microsoft to examine, you can [submit a file to Microsoft for analysis](#submit-a-suspicious-file-to-microsoft-for-analysis).</span></span>
      
## <a name="get-office-365-atp"></a><span data-ttu-id="919df-116">获取 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="919df-116">Get Office 365 ATP</span></span>

> [!IMPORTANT]
> <span data-ttu-id="919df-p103">Office 365 ATP 包含订阅，如 Microsoft 365 企业版、 Office 365 企业 E5、 Office 365 教育版 A5，和[Microsoft 365 企业版](https://support.office.com/article/c123694a-1efb-459e-a8d5-2187975373dc)中。如果您的组织具有不包括 Office 365 ATP 的 Office 365 订阅，您可能可以作为购买 ATP。有关详细信息，请参阅[Office 365 高级威胁 Protection Service Description](https://technet.microsoft.com/library/exchange-online-advanced-threat-protection-service-description.aspx)。</span><span class="sxs-lookup"><span data-stu-id="919df-p103">Office 365 ATP is included in subscriptions, such as Microsoft 365 Enterprise, Office 365 Enterprise E5, Office 365 Education A5, and [Microsoft 365 Business](https://support.office.com/article/c123694a-1efb-459e-a8d5-2187975373dc). If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection Service Description](https://technet.microsoft.com/library/exchange-online-advanced-threat-protection-service-description.aspx).</span></span> 

1. <span data-ttu-id="919df-120">作为全局或安全管理员，请转到[https://portal.office.com](https://portal.office.com)和使用 Office 365 您工作或学校的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="919df-120">As a global or security administrator, go to [https://portal.office.com](https://portal.office.com) and sign in with your work or school account for Office 365.</span></span> 
    
2. <span data-ttu-id="919df-121">选择**管理** \> **帐单**以查看您的当前订阅所包含的内容。</span><span class="sxs-lookup"><span data-stu-id="919df-121">Choose **Admin** \> **Billing** to see what your current subscription includes.</span></span> <br/><span data-ttu-id="919df-122">![以全局管理员身份，登录在 portal.office.com 并转到管理\>帐单](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)</span><span class="sxs-lookup"><span data-stu-id="919df-122">![As a global admin, sign in at portal.office.com and go to Admin \> Billing](media/18a3546c-bd1f-4f49-82ec-0184909b42c2.png)</span></span>
  
3. <span data-ttu-id="919df-123">如果您看到**Office 365 企业 E5**、 **Office 365 教育版 A5**或**Microsoft 365 企业版**，然后您的组织具有 ATP。</span><span class="sxs-lookup"><span data-stu-id="919df-123">If you see **Office 365 Enterprise E5**, **Office 365 Education A5**, or **Microsoft 365 Business**, then your organization has ATP.</span></span> <br/><span data-ttu-id="919df-p104">如果您看到其他订阅，例如**Office 365 企业版 E3**或**Office 365 企业版 E1**，请考虑添加 ATP。为此，请选择 **+ 添加订阅**。</span><span class="sxs-lookup"><span data-stu-id="919df-p104">If you see a different subscription, such as **Office 365 Enterprise E3** or **Office 365 Enterprise E1**, consider adding ATP. To do that, choose **+ Add subscription**.</span></span>
    
<span data-ttu-id="919df-126">ATP 后下, 一步是为您的安全团队定义策略。</span><span class="sxs-lookup"><span data-stu-id="919df-126">Once you have ATP, the next step is for your security team to define policies.</span></span> 
  
## <a name="define-policies-for-atp"></a><span data-ttu-id="919df-127">为 ATP 定义策略</span><span class="sxs-lookup"><span data-stu-id="919df-127">Define policies for ATP</span></span>

- <span data-ttu-id="919df-128">**[设置 Office 365 中的 ATP 防钓鱼策略](set-up-atp-anti-phishing-policies.md)** 包括基于模拟的攻击保护的攻击者发送电子邮件消息的状态显示为来自受信任的人员或域</span><span class="sxs-lookup"><span data-stu-id="919df-128">**[Set up ATP anti-phishing policies in Office 365](set-up-atp-anti-phishing-policies.md)** including impersonation-based attacks to protect against attackers who send email messages that appear to be from trusted people or domains</span></span> 

- <span data-ttu-id="919df-129">**[设置 Office 365 中的安全链接 ATP 策略](set-up-atp-safe-links-policies.md)** 包括您组织的[自定义被阻止的 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)和[自定义"执行不重写"Url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)</span><span class="sxs-lookup"><span data-stu-id="919df-129">**[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)** including your organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md) and [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)</span></span>
    
- <span data-ttu-id="919df-130">**[Office 365 中的策略设置 ATP 安全附件](set-up-atp-safe-attachments-policies.md)** 中可以包含[动态传递以及预览](dynamic-delivery-and-previewing.md)</span><span class="sxs-lookup"><span data-stu-id="919df-130">**[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)** that can include [dynamic delivery and previewing](dynamic-delivery-and-previewing.md)</span></span>
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a><span data-ttu-id="919df-131">请参阅 ATP 通过查看报告的工作方式</span><span class="sxs-lookup"><span data-stu-id="919df-131">See how ATP is working by viewing reports</span></span>

<span data-ttu-id="919df-132">ATP 策略后，报告是可用于显示如何服务运行正常。</span><span class="sxs-lookup"><span data-stu-id="919df-132">After your ATP policies are in place, reports are available to show how the service is working.</span></span>

<span data-ttu-id="919df-133">[![安全&amp;合规性中心仪表板可帮助您看到正常高级威胁保护](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span><span class="sxs-lookup"><span data-stu-id="919df-133">[![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span></span>
  
1. <span data-ttu-id="919df-p105">请确保您是 Office 365 全局管理员、 安全管理员或安全读取器。(请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。)</span><span class="sxs-lookup"><span data-stu-id="919df-p105">Make sure that you are an Office 365 global administrator, security administrator, or security reader. (See [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>
    
2. <span data-ttu-id="919df-136">[查看报告的高级威胁保护](view-reports-for-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="919df-136">[View reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span>
    
3. <span data-ttu-id="919df-p106">如果需要对进行调整您的安全策略。请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="919df-p106">If needed, make adjustments to your security policies. See the following resources:</span></span>

  - [<span data-ttu-id="919df-139">Office 365 中的 ATP 防钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="919df-139">ATP anti-phishing policies in Office 365</span></span>](set-up-atp-anti-phishing-policies.md)
    
  - [<span data-ttu-id="919df-140">Office 365 中的安全链接 ATP 策略</span><span class="sxs-lookup"><span data-stu-id="919df-140">ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
    
  - [<span data-ttu-id="919df-141">Office 365 中的 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="919df-141">ATP Safe Attachments policies in Office 365</span></span>](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a><span data-ttu-id="919df-142">可疑将文件提交给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="919df-142">Submit a suspicious file to Microsoft for analysis</span></span>

- <span data-ttu-id="919df-p107">如果您收到您怀疑可能恶意软件的文件，您可以提交给 Microsoft 进行分析该文件。请访问[Windows Defender 安全智能提交门户](https://go.microsoft.com/fwlink/?linkid=857185)。</span><span class="sxs-lookup"><span data-stu-id="919df-p107">If you get a file that you suspect could be malware, you can submit that file to Microsoft for analysis. Visit the [Windows Defender Security Intelligence submission portal](https://go.microsoft.com/fwlink/?linkid=857185).</span></span>

- <span data-ttu-id="919df-145">如果您要获取想要提交给 Microsoft 进行分析的电子邮件 （使用或不附件），请使用[报告消息加载项](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="919df-145">If you get an email message (with or without an attachment) that you'd like to submit to Microsoft for analysis, use the [Report Message add-in](enable-the-report-message-add-in.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="919df-146">相关主题</span><span class="sxs-lookup"><span data-stu-id="919df-146">Related topics</span></span>

[<span data-ttu-id="919df-147">查看高级威胁保护报告</span><span class="sxs-lookup"><span data-stu-id="919df-147">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  
[<span data-ttu-id="919df-148">威胁管理 Office 365 安全性&amp;合规性中心</span><span class="sxs-lookup"><span data-stu-id="919df-148">Threat management in the Office 365 Security &amp; Compliance Center</span></span>](threat-management.md)
  

