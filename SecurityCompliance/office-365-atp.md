---
title: Office 365 高级威胁防护
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 02/08/2019
ms.audience: Admin
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
description: Office 365 高级威胁防护包括欺骗情报、安全链接、安全附件、高级反钓鱼功能和威胁情报。
ms.openlocfilehash: d78b37ca048187a298b6e083b54ad68b949638ef
ms.sourcegitcommit: 2af6c3e8a74995294a67429530af8f085e6ca136
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051173"
---
# <a name="office-365-advanced-threat-protection"></a><span data-ttu-id="65ff7-103">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="65ff7-103">Office 365 Advanced Threat Protection</span></span>

## <a name="overview-of-office-365-advanced-threat-protection"></a><span data-ttu-id="65ff7-104">Office 365 高级威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="65ff7-104">Overview of Office 365 Advanced Threat Protection</span></span>

> [!IMPORTANT]
> <span data-ttu-id="65ff7-p101">本文适用于商业客户。如果您是在 Outlook 中查找有关安全链接的信息的家庭用户, 请参阅[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="65ff7-p101">This article is intended for business customers. If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="65ff7-107">Office 365 高级威胁防护 (ATP) 通过以下方式帮助保护您的组织免受恶意攻击:</span><span class="sxs-lookup"><span data-stu-id="65ff7-107">Office 365 Advanced Threat Protection (ATP) helps to protect your organization from malicious attacks by:</span></span>
  
- <span data-ttu-id="65ff7-108">使用[ATP 安全附件](atp-safe-attachments.md)扫描电子邮件附件中的恶意软件</span><span class="sxs-lookup"><span data-stu-id="65ff7-108">Scanning email attachments for malware with [ATP Safe Attachments](atp-safe-attachments.md)</span></span>
    
- <span data-ttu-id="65ff7-109">使用[ATP 安全链接](atp-safe-links.md)扫描电子邮件和 Office 文档中的 web 地址 (url)</span><span class="sxs-lookup"><span data-stu-id="65ff7-109">Scanning web addresses (URLs) in email messages and Office documents with [ATP Safe Links](atp-safe-links.md)</span></span>
    
- <span data-ttu-id="65ff7-110">使用[适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP](atp-for-spo-odb-and-teams.md)识别和阻止在线库中的恶意文件</span><span class="sxs-lookup"><span data-stu-id="65ff7-110">Identifying and blocking malicious files in online libraries with [ATP for SharePoint, OneDrive, and Microsoft Teams](atp-for-spo-odb-and-teams.md)</span></span>
    
- <span data-ttu-id="65ff7-111">使用[欺骗智能](learn-about-spoof-intelligence.md)检查电子邮件, 以获取未经授权的欺骗</span><span class="sxs-lookup"><span data-stu-id="65ff7-111">Checking email messages for unauthorized spoofing with [spoof intelligence](learn-about-spoof-intelligence.md)</span></span>
    
- <span data-ttu-id="65ff7-112">当有人尝试使用[Office 365 中的 ATP 反钓鱼功能](atp-anti-phishing.md)模拟你的用户和你的组织的自定义域时进行检测</span><span class="sxs-lookup"><span data-stu-id="65ff7-112">Detecting when someone attempts to impersonate your users and your organization's custom domains with [ATP anti-phishing capabilities in Office 365](atp-anti-phishing.md)</span></span>
    
<span data-ttu-id="65ff7-p102">**通过 Office 365 ATP 进行保护取决于您的组织的安全团队为安全链接、安全附件和反网络钓鱼定义的策略**。定义策略并定期查看和修订这些策略以使其保持最新并充分利用添加到服务中的新功能, 这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="65ff7-p102">**Protection through Office 365 ATP is determined by policies that your organization's security team defines for Safe Links, Safe Attachments, and Anti-Phishing**. It's important to define policies, and to periodically review and revise those policies to keep them up to date and to take advantages of new features that are added to the service.</span></span> 

<span data-ttu-id="65ff7-p103">[报告可](view-reports-for-atp.md)用于显示 ATP 在您的组织中的工作原理。这些报告还可以向你显示可能需要查看和更新策略的领域。而且, 如果您的文件不应被标记为恶意软件, 或者您希望 Microsoft 检查的文件, 则可以[将文件提交到 microsoft 进行分析](#submit-a-suspicious-file-to-microsoft-for-analysis)。</span><span class="sxs-lookup"><span data-stu-id="65ff7-p103">[Reports are available](view-reports-for-atp.md) to show how ATP is working for your organization. These reports can also show you areas where you might need to review and update your policies. And, if you have files that are marked as malware that shouldn't be, or files you'd like Microsoft to examine, you can [submit a file to Microsoft for analysis](#submit-a-suspicious-file-to-microsoft-for-analysis).</span></span>

## <a name="new-features-are-continually-being-added-to-atp"></a><span data-ttu-id="65ff7-118">将新功能连续添加到 ATP</span><span class="sxs-lookup"><span data-stu-id="65ff7-118">New features are continually being added to ATP</span></span>

<span data-ttu-id="65ff7-p104">我们将继续向 Office 365 添加新功能, 其中包括 ATP。下面列出了几个新功能, 其中一些是用于检查和更新 ATP 策略的。若要了解有关即将 ATP (或常规 microsoft 365) 的新功能的详细信息, 请访问[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)。</span><span class="sxs-lookup"><span data-stu-id="65ff7-p104">We are continuing to add new features to Office 365, and that includes ATP. Below is a list of several new features, some of which call for an ATP policy to be reviewed and updated. To learn more about new features coming to ATP (or Microsoft 365 in general), visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=O365).</span></span>


|<span data-ttu-id="65ff7-122">功能更新</span><span class="sxs-lookup"><span data-stu-id="65ff7-122">Feature updates</span></span>  |<span data-ttu-id="65ff7-123">交办事项</span><span class="sxs-lookup"><span data-stu-id="65ff7-123">Action items</span></span>  |
|---------|---------|
|<span data-ttu-id="65ff7-p105">从2019年2月开始, 在接下来的几个月中推出, 将威胁智能功能添加到 ATP。此外, 如果您的组织当前没有 ATP, 您将具有要考虑的新选项, 包括 atp 计划1和 atp 计划2。若要了解详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)以及[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="65ff7-p105">Beginning in February 2019 and rolling out over the next several months, Threat Intelligence capabilities are being added to ATP. In addition, if your organization does not currently have ATP, you'll have new options to consider, including ATP Plan 1 and ATP Plan 2. To learn more, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> |<span data-ttu-id="65ff7-127">查看组织的订阅, 如果需要, 请[购买或编辑加载](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on)项。</span><span class="sxs-lookup"><span data-stu-id="65ff7-127">Review your organization's subscription, and if needed, [Buy or edit an add-on](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/buy-or-edit-an-add-on).</span></span>  |
|<span data-ttu-id="65ff7-p106">从10月2018开始, 在接下来的几个月中开始, 当用户使用 outlook 或 Outlook Web 应用程序 (OWA) 时, ATP 安全链接将呈现原始 url, 而不是重写的 url。(我们称之为本机链接呈现。)</span><span class="sxs-lookup"><span data-stu-id="65ff7-p106">Beginning in October 2018 and rolling out over the next several months, when people are using Outlook or Outlook Web Application (OWA), ATP Safe Links renders original URLs, not rewritten URLs. (We call this native link rendering.)</span></span><br><span data-ttu-id="65ff7-130">当您的组织提供本机链接呈现时, 此功能将在 Outlook 365 (即点即用) 和 OWA 中运行。</span><span class="sxs-lookup"><span data-stu-id="65ff7-130">When native link rendering is available for your organization, this feature will work in Outlook 365 (Click-to-Run) and OWA.</span></span>|<span data-ttu-id="65ff7-131">无</span><span class="sxs-lookup"><span data-stu-id="65ff7-131">None</span></span>         |
|<span data-ttu-id="65ff7-132">从9月2018日起开始, [Office 365 ATP 警告页面](atp-safe-links-warning-pages.md)可提供新的配色方案、更多详细信息和继续转到网站的功能, 尽管有警告和建议。</span><span class="sxs-lookup"><span data-stu-id="65ff7-132">Beginning in September 2018, [Office 365 ATP warning pages](atp-safe-links-warning-pages.md) feature a new color scheme, more details, and the ability to continue to a site despite given warnings and recommendations.</span></span> |<span data-ttu-id="65ff7-133">无</span><span class="sxs-lookup"><span data-stu-id="65ff7-133">None</span></span>         |
|<span data-ttu-id="65ff7-134">从2018的下半年开始, 将 ATP 安全链接保护扩展为适用于 office Online (Word Online、Excel Online、PowerPoint online 和 OneNote online) 中的 url 和 Mac 上的 office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="65ff7-134">Beginning in the second half of 2018, ATP Safe Links protection is extended to apply to URLs in Office Online (Word Online, Excel Online, PowerPoint Online, and OneNote Online) and Office 365 ProPlus on Mac.</span></span>   |[<span data-ttu-id="65ff7-135">查看和编辑 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="65ff7-135">Review and edit your ATP Safe Links policies</span></span>](set-up-atp-safe-links-policies.md)  |
|<span data-ttu-id="65ff7-136">从后期开始可能为 2018 [](quarantine-email-messages.md) , 安全&amp;合规中心中的隔离功能将扩展到[SharePoint Online、OneDrive for business 和 Microsoft 团队的 ATP](atp-for-spo-odb-and-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="65ff7-136">Beginning in late May 2018, [quarantine](quarantine-email-messages.md) capabilities in the Security &amp; Compliance Center are being extended to [ATP for SharePoint Online, OneDrive for Business, and Microsoft Teams](atp-for-spo-odb-and-teams.md).</span></span> |[<span data-ttu-id="65ff7-137">查看和编辑 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="65ff7-137">Review and edit your ATP Safe Attachments policies</span></span>](set-up-atp-safe-attachments-policies.md) |
|<span data-ttu-id="65ff7-138">从2018年3月起, 将对 ATP 安全链接保护进行扩展, 以应用于在组织内的人员之间发送的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="65ff7-138">Beginning in March 2018, ATP Safe Links protection is extended to apply to email sent between people within an organization.</span></span> |[<span data-ttu-id="65ff7-139">查看和编辑 ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="65ff7-139">Review and edit your ATP Safe Links policies</span></span>](set-up-atp-safe-links-policies.md) |
|<span data-ttu-id="65ff7-140">2006年10月2017日开始, 将 ATP 安全链接保护扩展为应用于电子邮件中的 url 以及 office 365 专业增强版文档 (如 Word、Excel、PowerPoint 和 Visio on Windows) 中的 url, 以及 iOS 和 Android 设备上的 office 应用。</span><span class="sxs-lookup"><span data-stu-id="65ff7-140">Beginning in late October 2017, ATP Safe Links protection is extended to apply to URLs in email as well as URLs in Office 365 ProPlus documents, such as Word, Excel, PowerPoint, and Visio on Windows, as well as Office apps on iOS and Android devices.</span></span>  |<span data-ttu-id="65ff7-141">确保您正在使用[Office 的新式验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)</span><span class="sxs-lookup"><span data-stu-id="65ff7-141">Make sure you're using [Modern Authentication for Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)</span></span> |

## <a name="get-office-365-atp"></a><span data-ttu-id="65ff7-142">获取 Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="65ff7-142">Get Office 365 ATP</span></span>

<span data-ttu-id="65ff7-p107">Office 365 ATP 包含在订阅中, 如[microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 商业](https://www.microsoft.com/microsoft-365/business)版、Office 365 企业版 E5 和 office 365 教育版 A5。如果您的组织有一个不包含 office 365 ATP 的 office 365 订阅, 则可能会将 ATP 作为加载项进行购买。有关详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="65ff7-p107">Office 365 ATP is included in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, and Office 365 Education A5. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> 

## <a name="define-policies-for-atp"></a><span data-ttu-id="65ff7-146">为 ATP 定义策略</span><span class="sxs-lookup"><span data-stu-id="65ff7-146">Define policies for ATP</span></span>

<span data-ttu-id="65ff7-147">若要定义 (或编辑) ATP 策略, 您必须分配下表中所述的角色之一:</span><span class="sxs-lookup"><span data-stu-id="65ff7-147">To define (or edit) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="65ff7-148">角色</span><span class="sxs-lookup"><span data-stu-id="65ff7-148">Role</span></span>  |<span data-ttu-id="65ff7-149">分配的位置/方式</span><span class="sxs-lookup"><span data-stu-id="65ff7-149">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="65ff7-150">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="65ff7-150">Office 365 Global Administrator</span></span> |<span data-ttu-id="65ff7-p108">默认情况下, 注册购买 Office 365 的人是全局管理员。(请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。)</span><span class="sxs-lookup"><span data-stu-id="65ff7-p108">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="65ff7-153">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="65ff7-153">Security Administrator</span></span> |<span data-ttu-id="65ff7-154">Azure Active Directory 管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="65ff7-154">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="65ff7-155">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="65ff7-155">Exchange Online Organization Management</span></span> |<span data-ttu-id="65ff7-156">Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="65ff7-156">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="65ff7-157">或</span><span class="sxs-lookup"><span data-stu-id="65ff7-157">or</span></span> <br>  <span data-ttu-id="65ff7-158">PowerShell cmdlet (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="65ff7-158">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="65ff7-159">若要了解有关角色和权限的详细信息, 请参阅[Office 365 &amp;安全合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="65ff7-159">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

<span data-ttu-id="65ff7-160">有几种 ATP 策略可供定义和定期查看。</span><span class="sxs-lookup"><span data-stu-id="65ff7-160">There are several kinds of ATP policies to define and periodically review.</span></span>

1. <span data-ttu-id="65ff7-161">**[在 Office 365 中设置 ATP 反网络钓鱼策略](set-up-anti-phishing-policies.md)**, 包括基于模拟的攻击, 以防止发出似乎来自受信任人或域的电子邮件的攻击者。</span><span class="sxs-lookup"><span data-stu-id="65ff7-161">**[Set up ATP anti-phishing policies in Office 365](set-up-anti-phishing-policies.md)** including impersonation-based attacks to protect against attackers who send email messages that appear to be from trusted people or domains.</span></span> 

2. <span data-ttu-id="65ff7-162">**[在 Office 365 中设置 ATP 安全链接策略](set-up-atp-safe-links-policies.md)**, 包括组织的[自定义阻止 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)和[自定义 "不重写" url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="65ff7-162">**[Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md)** including your organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md) and [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
    
3. <span data-ttu-id="65ff7-163">**[在 Office 365 中设置 ATP 安全附件策略](set-up-atp-safe-attachments-policies.md)**, 并从多个选项 (例如[动态传递和预览](dynamic-delivery-and-previewing.md)) 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="65ff7-163">**[Set up ATP Safe Attachments policies in Office 365](set-up-atp-safe-attachments-policies.md)** and choose from several options, such as [Dynamic Delivery and previewing](dynamic-delivery-and-previewing.md).</span></span>
  
## <a name="see-how-atp-is-working-by-viewing-reports"></a><span data-ttu-id="65ff7-164">查看报表查看 ATP 的工作原理</span><span class="sxs-lookup"><span data-stu-id="65ff7-164">See how ATP is working by viewing reports</span></span>

<span data-ttu-id="65ff7-p109">在 ATP 策略准备就绪后, 报告可用于显示服务的工作方式。(在 "Office 365 安全 & 合规中心" 中, 转到 "**报告** > "**仪表板**。)</span><span class="sxs-lookup"><span data-stu-id="65ff7-p109">After your ATP policies are in place, reports are available to show how the service is working. (In the Office 365 Security & Compliance Center, go to **Reports** > **Dashboard**.)</span></span>

<span data-ttu-id="65ff7-167">[![安全&amp;合规中心仪表板可帮助您了解高级威胁防护的工作情况](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span><span class="sxs-lookup"><span data-stu-id="65ff7-167">[![The Security &amp; Compliance Center dashboard can help you see where Advanced Threat Protection is working](media/6b213d34-adbb-44af-8549-be9a7e2db087.png)](view-reports-for-atp.md)</span></span>
  
1. <span data-ttu-id="65ff7-168">作为 Office 365 全局管理员、安全管理员或安全阅读者, 请转到[https://protection.office.com](https://protection.office.com)并登录。</span><span class="sxs-lookup"><span data-stu-id="65ff7-168">As an Office 365 global administrator, a security administrator, or a security reader, go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span>
    
2. <span data-ttu-id="65ff7-p110">转到 "**报表** > "**仪表板**。(若要获取有关这些报告的帮助, 请参阅[查看高级威胁防护的报告](view-reports-for-atp.md)。)</span><span class="sxs-lookup"><span data-stu-id="65ff7-p110">Go to **Reports** > **Dashboard**. (To get help with these reports, see [View reports for Advanced Threat Protection](view-reports-for-atp.md).)</span></span>
    
3. <span data-ttu-id="65ff7-p111">如果需要, 请对安全策略进行调整。若要获取有关此方面的帮助, 请参阅以下资源:</span><span class="sxs-lookup"><span data-stu-id="65ff7-p111">If needed, make adjustments to your security policies. To get help with this, see the following resources:</span></span>
    - [<span data-ttu-id="65ff7-173">ATP 反网络钓鱼策略</span><span class="sxs-lookup"><span data-stu-id="65ff7-173">ATP anti-phishing policies</span></span>](set-up-anti-phishing-policies.md)
    - [<span data-ttu-id="65ff7-174">ATP 安全链接策略</span><span class="sxs-lookup"><span data-stu-id="65ff7-174">ATP Safe Links policies</span></span>](set-up-atp-safe-links-policies.md)
    - [<span data-ttu-id="65ff7-175">ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="65ff7-175">ATP Safe Attachments policies</span></span>](set-up-atp-safe-attachments-policies.md)
    
    
## <a name="submit-a-suspicious-file-to-microsoft-for-analysis"></a><span data-ttu-id="65ff7-176">将可疑文件提交给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="65ff7-176">Submit a suspicious file to Microsoft for analysis</span></span>

- <span data-ttu-id="65ff7-p112">如果您收到怀疑可能是恶意软件的文件, 则可以将该文件提交给 Microsoft 进行分析。访问[Windows Defender 安全智能提交门户](https://go.microsoft.com/fwlink/?linkid=857185)。</span><span class="sxs-lookup"><span data-stu-id="65ff7-p112">If you get a file that you suspect could be malware, you can submit that file to Microsoft for analysis. Visit the [Windows Defender Security Intelligence submission portal](https://go.microsoft.com/fwlink/?linkid=857185).</span></span>

- <span data-ttu-id="65ff7-179">如果你收到一封要提交给 Microsoft 进行分析的电子邮件 (带有或不带附件), 请使用[报告邮件加载项](enable-the-report-message-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="65ff7-179">If you get an email message (with or without an attachment) that you'd like to submit to Microsoft for analysis, use the [Report Message add-in](enable-the-report-message-add-in.md).</span></span> 
  

