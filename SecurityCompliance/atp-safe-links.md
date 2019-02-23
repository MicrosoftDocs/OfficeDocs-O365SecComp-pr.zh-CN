---
title: Office 365 ATP 安全链接
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.date: 02/11/2019
ms.topic: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: "\"安全链接\" 功能可提供对 Office 文档中的超链接和电子邮件中的超链接的单击时间验证。使用安全链接保护组织免受网络钓鱼和其他攻击的攻击。"
ms.openlocfilehash: 3de79ec42a0d9534f93711741cb8427a0cde9fb1
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30214052"
---
# <a name="office-365-atp-safe-links"></a><span data-ttu-id="ffd38-104">Office 365 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="ffd38-104">Office 365 ATP Safe Links</span></span>

## <a name="overview-of-office-365-atp-safe-links"></a><span data-ttu-id="ffd38-105">Office 365 ATP 安全链接概述</span><span class="sxs-lookup"><span data-stu-id="ffd38-105">Overview of Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ffd38-p102">本文适用于商业客户。如果您是在 Outlook 中查找有关安全链接的信息的家庭用户, 请参阅[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p102">This article is intended for business customers. If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="ffd38-p103">Office 365 ATP 安全链接 ([高级威胁防护](office-365-atp.md)的一部分) 通过在[电子邮件](#how-atp-safe-links-works-with-email)和[Office 文档](#how-atp-safe-links-works-with-office-documents)中提供 web 地址 (url) 的验证时间, 可帮助保护您的组织。通过由 Office 365 安全团队设置的[ATP 安全链接策略](set-up-atp-safe-links-policies.md)定义保护。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p103">Office 365 ATP Safe Links (part of [Advanced Threat Protection](office-365-atp.md)) can help protect your organization by providing time-of-click verification of web addresses (URLs) in [email messages](#how-atp-safe-links-works-with-email) and [Office documents](#how-atp-safe-links-works-with-office-documents). Protection is defined through [ATP Safe Links policies](set-up-atp-safe-links-policies.md) that are set by your Office 365 security team.</span></span> 
  
<span data-ttu-id="ffd38-p104">在 ATP 安全链接策略准备就绪后, Office 365 全局管理员、安全管理员和安全读者可以[查看高级威胁防护报告](view-reports-for-atp.md)。这些报告中的信息可帮助您的安全小组采取进一步的措施来保护您的组织或研究安全事件。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p104">Once your ATP Safe Links policies are in place, Office 365 global administrators, security administrators, and security readers can [view reports for Advanced Threat Protection](view-reports-for-atp.md). The information in those reports can help your security team take further steps to protect your organization or research security incidents.</span></span>

<span data-ttu-id="ffd38-p105">在将[新功能添加到 ATP](office-365-atp.md#new-features-in-office-365-atp)时, Office 365 安全团队可以添加或编辑组织的 ATP 安全链接策略。此外, 您可能会注意到更改和改进, 如我们在 Outlook 中新修订过的[警告页面](atp-safe-links-warning-pages.md)和本机链接呈现。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p105">As [new features are added to ATP](office-365-atp.md#new-features-in-office-365-atp), your Office 365 security team can add or edit your organization's ATP Safe Links policies. In addition, you might notice changes and improvements, such as our newly revised [warning pages](atp-safe-links-warning-pages.md) and native link rendering in Outlook.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="ffd38-114">ATP 安全链接如何处理电子邮件中的 url</span><span class="sxs-lookup"><span data-stu-id="ffd38-114">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="ffd38-115">从较高的层次来看, ATP 安全链接保护对电子邮件中的 url 的工作方式 (托管在 Office 365 中, 而不是在本地中):</span><span class="sxs-lookup"><span data-stu-id="ffd38-115">At a high level, here's how ATP Safe Links protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="ffd38-116">用户接收包含 url 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="ffd38-116">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="ffd38-117">所有电子邮件都通过 Exchange Online 保护, 其中应用了 internet 协议 (IP) 和信封筛选器、基于签名的恶意软件保护、反垃圾邮件和反恶意软件筛选器。</span><span class="sxs-lookup"><span data-stu-id="ffd38-117">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="ffd38-118">电子邮件到达用户的收件箱。</span><span class="sxs-lookup"><span data-stu-id="ffd38-118">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="ffd38-119">用户登录到 Office 365, 并转到其电子邮件收件箱。</span><span class="sxs-lookup"><span data-stu-id="ffd38-119">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="ffd38-120">用户打开一封电子邮件, 然后单击电子邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="ffd38-120">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="ffd38-p106">ATP 安全链接功能将在打开网站之前立即检查 URL。该 URL 被标识为 "阻止"、"恶意" 或 "安全"。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p106">The ATP Safe Links feature immediately checks the URL before opening the website. The URL is identified as blocked, malicious, or safe.</span></span>
    
    - <span data-ttu-id="ffd38-123">如果 URL 指向的网站包含在适用于该用户的策略的[自定义 "不重写" url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)中, 则会打开该网站。</span><span class="sxs-lookup"><span data-stu-id="ffd38-123">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens.</span></span> 
    
    - <span data-ttu-id="ffd38-124">如果 URL 指向的网站包含在组织的[自定义阻止 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)中, 则会打开一个[警告页面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="ffd38-124">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="ffd38-125">如果 URL 指向已确定为恶意的网站, 将打开 "[警告" 页](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="ffd38-125">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="ffd38-126">如果 URL 转到一个可下载的文件, 并且您的组织的[ATP 安全链接策略](set-up-atp-safe-links-policies.md)已配置为扫描此类内容, 则会检查下载的文件。</span><span class="sxs-lookup"><span data-stu-id="ffd38-126">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
    - <span data-ttu-id="ffd38-127">如果确定该 URL 是安全的, 则会打开该网站。</span><span class="sxs-lookup"><span data-stu-id="ffd38-127">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="ffd38-128">ATP 安全链接如何处理 Office 文档中的 url</span><span class="sxs-lookup"><span data-stu-id="ffd38-128">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="ffd38-129">从较高的层次来看, ATP 安全链接保护对 Office 365 专业增强版应用程序中的 url (windows 或 Mac 上的 Word、Excel 和 PowerPoint 的当前版本、iOS 或 Android 设备上的 Office 应用、OneNote online 和 Office online 上的 Visio) 的工作方式:</span><span class="sxs-lookup"><span data-stu-id="ffd38-129">At a high level, here's how ATP Safe Links protection works for URLs in Office 365 ProPlus applications (current versions of Word, Excel, and PowerPoint on Windows or Mac, Office apps on iOS or Android devices, Visio on Windows, OneNote Online, and Office Online):</span></span>
  
1. <span data-ttu-id="ffd38-p107">用户在其计算机、智能手机或平板电脑上安装了 Office 365 专业增强版。(或者, 他们正在浏览器中使用 Office Online。)</span><span class="sxs-lookup"><span data-stu-id="ffd38-p107">People have installed Office 365 ProPlus on their computer, smartphone, or tablet. (Or, they are using Office Online in their browser.)</span></span>
    
2. <span data-ttu-id="ffd38-p108">用户打开 Word、Excel、PowerPoint 或 Visio, 并使用其工作或学校帐户登录到 Office 365 企业版。文档包含 url。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p108">A user opens a Word, Excel, PowerPoint, or Visio, and signs in to Office 365 Enterprise using their work or school account. The document contains URLs.</span></span>
    
3. <span data-ttu-id="ffd38-134">当用户单击文档中的某个 URL 时, ATP 安全链接服务将检查该链接。</span><span class="sxs-lookup"><span data-stu-id="ffd38-134">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
  - <span data-ttu-id="ffd38-135">如果 URL 指向的网站包含在适用于该用户的策略的[自定义 "不重写" url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)中, 则会将该用户转到该网站。</span><span class="sxs-lookup"><span data-stu-id="ffd38-135">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
  - <span data-ttu-id="ffd38-136">如果 URL 指向的网站包含在组织的[自定义阻止 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)中, 则会向用户提供一个[警告页面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="ffd38-136">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
  - <span data-ttu-id="ffd38-137">如果 URL 指向已确定为恶意的网站, 则会向用户提供[警告页面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="ffd38-137">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
  - <span data-ttu-id="ffd38-138">如果 URL 转到可下载的文件, 并且已将[ATP 安全链接策略](set-up-atp-safe-links-policies.md)配置为扫描此类下载, 则会检查可下载的文件。</span><span class="sxs-lookup"><span data-stu-id="ffd38-138">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
  - <span data-ttu-id="ffd38-139">如果该 URL 被认为是安全的, 则会将用户转到该网站。</span><span class="sxs-lookup"><span data-stu-id="ffd38-139">If the URL is considered safe, the user is taken to the website.</span></span>

## <a name="how-to-get-atp-safe-links-protection"></a><span data-ttu-id="ffd38-140">如何获取 ATP 安全链接保护</span><span class="sxs-lookup"><span data-stu-id="ffd38-140">How to get ATP Safe Links protection</span></span>

<span data-ttu-id="ffd38-p109">首先, 请确保你的订阅包括[高级威胁防护](office-365-atp.md)。在订阅中包含 ATP, 如[microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [microsoft 365 商业](https://www.microsoft.com/microsoft-365/business)版、office 365 企业版 E5、office 365 教育版 A5 等。如果您的组织有一个不包含 office 365 ATP 的 office 365 订阅, 则可能会将 ATP 作为加载项进行购买。有关详细信息, 请参阅[office 365 高级威胁防护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁防护服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p109">First, make sure your subscription includes [Advanced Threat Protection](office-365-atp.md). ATP is included in in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> 
  
<span data-ttu-id="ffd38-p110">接下来, 请确保已定义 ATP 安全链接策略。(请参阅[设置 Office 365 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。)ATP 安全链接功能在以下情况中处于活动状态:</span><span class="sxs-lookup"><span data-stu-id="ffd38-p110">Next, make sure your ATP Safe Links policies are defined. (See [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).) ATP Safe Links features are active when:</span></span>
  
- <span data-ttu-id="ffd38-p111">**ATP 安全链接策略是**为电子邮件和 Word、Excel、PowerPoint 和 Visio 文档设置的。(请参阅[在 Office 365 中设置 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。)</span><span class="sxs-lookup"><span data-stu-id="ffd38-p111">**ATP Safe Links policies are set up** for email and for Word, Excel, PowerPoint, and Visio documents. (See [Set up ATP safe links policies in Office 365](set-up-atp-safe-links-policies.md).)</span></span>

- <span data-ttu-id="ffd38-p112">将**Office 365 客户端应用配置为使用新式验证**(这适用于 Office 文档中的 ATP 安全链接保护)。(请参阅[适用于 Office 2016 的新式验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)。)</span><span class="sxs-lookup"><span data-stu-id="ffd38-p112">**Office 365 client apps are configured to use Modern Authentication** (this is for ATP Safe Links protection in Office documents). (See [Modern Authentication for Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).)</span></span> 
    
- <span data-ttu-id="ffd38-p113">用户使用其工作或学校帐户**登录到 Office 365** 。(请参阅[登录到 office 或 office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)。)</span><span class="sxs-lookup"><span data-stu-id="ffd38-p113">**Users have signed into Office 365** using their work or school account. (See [Sign in to Office or Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)</span></span>
    
- <span data-ttu-id="ffd38-152">**您的组织的电子邮件通过 Exchange Online Protection**。</span><span class="sxs-lookup"><span data-stu-id="ffd38-152">**Your organization's email passes through Exchange Online Protection**.</span></span>  

<span data-ttu-id="ffd38-p114">若要定义 (或编辑) ATP 策略, 必须为您分配适当的角色。下表介绍了一些示例:</span><span class="sxs-lookup"><span data-stu-id="ffd38-p114">To define (or edit) ATP policies, you must be assigned an appropriate role. Some examples are described in the following table:</span></span>

|<span data-ttu-id="ffd38-155">角色</span><span class="sxs-lookup"><span data-stu-id="ffd38-155">Role</span></span>  |<span data-ttu-id="ffd38-156">分配的位置/方式</span><span class="sxs-lookup"><span data-stu-id="ffd38-156">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="ffd38-157">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="ffd38-157">Office 365 Global Administrator</span></span> |<span data-ttu-id="ffd38-p115">默认情况下, 注册购买 Office 365 的人是全局管理员。(请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。)</span><span class="sxs-lookup"><span data-stu-id="ffd38-p115">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="ffd38-160">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="ffd38-160">Security Administrator</span></span> |<span data-ttu-id="ffd38-161">Azure Active Directory 管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="ffd38-161">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="ffd38-162">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="ffd38-162">Exchange Online Organization Management</span></span> |<span data-ttu-id="ffd38-163">Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="ffd38-163">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="ffd38-164">或</span><span class="sxs-lookup"><span data-stu-id="ffd38-164">or</span></span> <br>  <span data-ttu-id="ffd38-165">PowerShell cmdlet (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="ffd38-165">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a><span data-ttu-id="ffd38-166">如何确保已准备好 ATP 安全链接保护</span><span class="sxs-lookup"><span data-stu-id="ffd38-166">How to make sure ATP Safe Links protection is in place</span></span>

<span data-ttu-id="ffd38-p116">作为全局管理员或安全管理员, 请务必查看[ATP 安全链接策略](set-up-atp-safe-links-policies.md)。ATP 安全链接策略确定保护是否仅适用于电子邮件中的超链接或 Office 文档中的 url。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p116">As a global administrator or security administrator, be sure to review your [ATP Safe Links policies](set-up-atp-safe-links-policies.md). ATP Safe Links policies determine whether protection applies to hyperlinks in email messages only, or to URLs in Office documents as well.</span></span>

<span data-ttu-id="ffd38-169">在 ATP 安全链接策略准备就绪后, 贵组织的安全团队可以参阅查看[高级威胁防护的报告](view-reports-for-atp.md), 了解你的组织的 ATP 安全链接保护的工作原理。</span><span class="sxs-lookup"><span data-stu-id="ffd38-169">After ATP Safe Links policies are in place, your organization's security team can see see how ATP Safe Links protection is working for your organization is by [viewing reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span> 

## <a name="example-scenarios"></a><span data-ttu-id="ffd38-170">示例场景</span><span class="sxs-lookup"><span data-stu-id="ffd38-170">Example scenarios</span></span>
  
<span data-ttu-id="ffd38-p117">下表介绍了一些示例方案, 其中可能存在或可能未实施 ATP 安全链接保护。(在所有这些情况下, 我们假定组织拥有 Office 365 企业版 E5。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p117">The following table describes some example scenarios where ATP Safe Links protection might or might not be in place. (In all of these cases, we assume the organization has Office 365 Enterprise E5.)</span></span>
  
|<span data-ttu-id="ffd38-173">**示例应用场景**</span><span class="sxs-lookup"><span data-stu-id="ffd38-173">**Example scenario**</span></span>|<span data-ttu-id="ffd38-174">**在这种情况下 ATP 安全链接保护是否适用？**</span><span class="sxs-lookup"><span data-stu-id="ffd38-174">**Does ATP Safe Links protection apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ffd38-p118">Jean 是具有 ATP 安全链接策略的组的成员, 其中包含电子邮件和 Office 文档中的 url。Jean 打开某人发送的 PowerPoint 演示文稿, 然后单击演示文稿中的 URL。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p118">Jean is a member of a group that has ATP Safe Links policies covering URLs in email and Office documents. Jean opens a PowerPoint presentation that someone sent, and then clicks a URL in the presentation.</span></span>  <br/> |<span data-ttu-id="ffd38-p119">是的。定义的 ATP 安全链接策略适用于 Jean 的 group、Jean 的电子邮件以及 Jean 打开的 Word、Excel、PowerPoint 或 Visio 文档, 只要 Jean 已登录并使用 Windows、iOS 或 Android 设备上的 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p119">Yes. The ATP Safe Links policies that are defined apply to Jean's group, Jean's email, and Word, Excel, PowerPoint, or Visio documents that Jean opens, so long as Jean is signed in and using Office 365 ProPlus on Windows, iOS, or Android devices.</span></span>  <br/> |
|<span data-ttu-id="ffd38-p120">在 Chris 的组织中, 没有任何全局或安全管理员尚未定义任何 ATP 安全链接策略。Chris 收到一个电子邮件, 其中包含指向恶意网站的 URL。丽丽不知道 URL 是恶意的并单击链接。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p120">In Chris's organization, no global or security administrators have defined any ATP safe links policies yet. Chris receives an email that contains a URL to a malicious website. Chris is unaware the URL is malicious and clicks the link.</span></span>  <br/> |<span data-ttu-id="ffd38-p121">不。包含组织中每个人的 url 的默认策略必须进行定义, 以便保护生效。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p121">No. The default policy that covers URLs for everyone in the organization must be defined in order for protection to be in place.</span></span>  <br/> |
|<span data-ttu-id="ffd38-p122">在 Pat 的组织中, 没有任何全局或安全管理员尚未定义或编辑任何 ATP 安全链接策略。Pat 打开 Word 文档并单击文件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p122">In Pat's organization, no global or security administrators have defined or edited any ATP Safe Links policies yet. Pat opens a Word document and clicks a URL in the file.</span></span>  <br/> |<span data-ttu-id="ffd38-p123">否。必须定义包含 Office 文档的策略, 才能就地保护。请参阅[在 Office 365 中设置 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p123">No. A policy that includes Office documents must be defined in order for protection to be in place. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  </span></span><br/> |
|<span data-ttu-id="ffd38-p124">先生/她的组织具有一个列入 "已`http://tailspintoys.com`阻止" 网站的 ATP 安全链接策略。先生/她收到一封包含的 URL 的`http://tailspintoys.com/aboutus/trythispage`电子邮件。先生单击 URL。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p124">Lee's organization has a ATP Safe Links policy that has `http://tailspintoys.com` listed as a blocked website. Lee receives an email message that contains a URL to `http://tailspintoys.com/aboutus/trythispage`. Lee clicks the URL.  </span></span><br/> |<span data-ttu-id="ffd38-p125">这取决于整个网站及其所有子页是否包含在阻止的 url 列表中。请参阅[使用 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p125">It depends on whether the entire site and all its subpages are included in the list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).  </span></span><br/> |
|<span data-ttu-id="ffd38-194">晓明 (Jean 的同事) 向 Jean 发送电子邮件, 而不知道该电子邮件包含恶意 URL。</span><span class="sxs-lookup"><span data-stu-id="ffd38-194">Jamie, Jean's colleague, sends an email to Jean, not knowing that the email contains a malicious URL.</span></span>  <br/> |<span data-ttu-id="ffd38-p126">这取决于是否为在组织内发送的电子邮件定义 ATP 安全链接策略。请参阅[在 Office 365 中设置 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="ffd38-p126">It depends on whether ATP Safe Links policies are defined for email sent within the organization. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  </span></span><br/> |


  

