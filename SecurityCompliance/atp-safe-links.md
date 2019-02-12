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
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: 安全链接功能提供的超链接中 Office 文档和电子邮件中的时间的单击验证。使用安全的链接可从网络钓鱼和其他攻击保护您的组织。
ms.openlocfilehash: 4d83aa65af47ea6723d6e2042c230fb2b07c174c
ms.sourcegitcommit: 065f5e72676511b5ecf7f10a17685999780e92d8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29888028"
---
# <a name="office-365-atp-safe-links"></a><span data-ttu-id="dd6e8-104">Office 365 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="dd6e8-104">Office 365 ATP Safe Links</span></span>

## <a name="overview-of-office-365-atp-safe-links"></a><span data-ttu-id="dd6e8-105">Overview of Office 365 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="dd6e8-105">Overview of Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd6e8-p102">本文适用于企业客户。如果您是家庭用户查找有关在 Outlook 中的安全链接的信息，请参阅[高级 Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p102">This article is intended for business customers. If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="dd6e8-p103">Office 365 ATP 安全链接 （[高级威胁保护](office-365-atp.md)的一部分） 可帮助保护您的组织提供的[电子邮件](#how-atp-safe-links-works-with-email)和[Office 文档](#how-atp-safe-links-works-with-office-documents)中的 web 地址 (Url) 的时间的单击验证。保护通过[ATP 安全链接策略](set-up-atp-safe-links-policies.md)设置您的 Office 365 安全工作组的定义。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p103">Office 365 ATP Safe Links (part of [Advanced Threat Protection](office-365-atp.md)) can help protect your organization by providing time-of-click verification of web addresses (URLs) in [email messages](#how-atp-safe-links-works-with-email) and [Office documents](#how-atp-safe-links-works-with-office-documents). Protection is defined through [ATP Safe Links policies](set-up-atp-safe-links-policies.md) that are set by your Office 365 security team.</span></span> 
  
<span data-ttu-id="dd6e8-p104">位置 ATP 安全链接策略后，Office 365 全局管理员、 安全管理员和安全读者可以[用于高级威胁保护查看报告](view-reports-for-atp.md)。这些报告中的信息可帮助您采取进一步措施保护您的组织或调查安全事件的安全团队。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p104">Once your ATP Safe Links policies are in place, Office 365 global administrators, security administrators, and security readers can [view reports for Advanced Threat Protection](view-reports-for-atp.md). The information in those reports can help your security team take further steps to protect your organization or research security incidents.</span></span>

<span data-ttu-id="dd6e8-p105">为[新功能添加到 ATP](office-365-atp.md#new-features-are-continually-being-added-to-atp)，您的 Office 365 安全团队可以添加或编辑您的组织 ATP 安全链接策略。此外，您可能会注意到更改和增强功能，如我们的新修改的[警告页面](atp-safe-links-warning-pages.md)和呈现在 Outlook 中的本机链接。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p105">As [new features are added to ATP](office-365-atp.md#new-features-are-continually-being-added-to-atp), your Office 365 security team can add or edit your organization's ATP Safe Links policies. In addition, you might notice changes and improvements, such as our newly revised [warning pages](atp-safe-links-warning-pages.md) and native link rendering in Outlook.</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="dd6e8-114">ATP 安全链接如何处理电子邮件中的 Url</span><span class="sxs-lookup"><span data-stu-id="dd6e8-114">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="dd6e8-115">在高级别，下面是 ATP 安全链接保护的工作原理 Url 的电子邮件 （托管在 Office 365 中，不在本地） 中：</span><span class="sxs-lookup"><span data-stu-id="dd6e8-115">At a high level, here's how ATP Safe Links protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="dd6e8-116">人员接收电子邮件，其中一些包含 Url。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-116">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="dd6e8-117">基于签名的恶意软件保护，反垃圾邮件通过 Exchange Online Protection，其中 internet 协议 (IP) 和信封筛选器，转所有电子邮件和反恶意软件筛选器应用。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-117">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="dd6e8-118">电子邮件到达人的收件箱中。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-118">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="dd6e8-119">用户登录到 Office 365，并转到其电子邮件收件箱。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-119">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="dd6e8-120">用户打开一封电子邮件，并单击电子邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-120">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="dd6e8-p106">ATP 安全链接功能立即打开网站之前检查的 URL。URL 标识为阻止，恶意，或安全。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p106">The ATP Safe Links feature immediately checks the URL before opening the website. The URL is identified as blocked, malicious, or safe.</span></span>
    
    - <span data-ttu-id="dd6e8-123">如果 URL 包含应用于用户的策略[自定义"执行不重写"Url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)中的网站，网站打开。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-123">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens.</span></span> 
    
    - <span data-ttu-id="dd6e8-124">如果 URL 是到组织的[自定义被阻止的 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的网站，[警告页](atp-safe-links-warning-pages.md)将打开。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-124">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="dd6e8-125">如果已确定要恶意的网站 URL，打开[警告页](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-125">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="dd6e8-126">如果 URL 转到一个可下载的文件和组织的[安全链接 ATP 策略](set-up-atp-safe-links-policies.md)配置为扫描此类内容，则检查可下载文件。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-126">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
    - <span data-ttu-id="dd6e8-127">如果 URL 确定为安全起见，打开网站。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-127">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="dd6e8-128">ATP 安全链接如何处理在 Office 文档中的 Url</span><span class="sxs-lookup"><span data-stu-id="dd6e8-128">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="dd6e8-129">在高级别，下面是 ATP 安全链接保护的工作原理 Url 的 Office 365 ProPlus 应用程序 （当前版本的 Word、 Excel 和 PowerPoint 在 Windows 或 Mac 上 iOS 或 Android 设备，在 Windows、 OneNote Online 和 Office Online 上的 Visio 的 Office 应用程序上） 中：</span><span class="sxs-lookup"><span data-stu-id="dd6e8-129">At a high level, here's how ATP Safe Links protection works for URLs in Office 365 ProPlus applications (current versions of Word, Excel, and PowerPoint on Windows or Mac, Office apps on iOS or Android devices, Visio on Windows, OneNote Online, and Office Online):</span></span>
  
1. <span data-ttu-id="dd6e8-p107">人员已在其计算机、 smartphone 或平板电脑上安装 Office 365 ProPlus。（或者，将 Office Online，在其浏览器中。）</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p107">People have installed Office 365 ProPlus on their computer, smartphone, or tablet. (Or, they are using Office Online in their browser.)</span></span>
    
2. <span data-ttu-id="dd6e8-p108">用户打开 Word、 Excel、 PowerPoint 或 Visio，并登录到 Office 365 企业版使用其工作或学校帐户。文档包含的 Url。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p108">A user opens a Word, Excel, PowerPoint, or Visio, and signs in to Office 365 Enterprise using their work or school account. The document contains URLs.</span></span>
    
3. <span data-ttu-id="dd6e8-134">当用户单击文档中的 URL 时，链接将检查 ATP 安全链接服务。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-134">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
  - <span data-ttu-id="dd6e8-135">如果应用于用户的策略[自定义"执行不重写"Url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)中包含的网站 URL，该用户是转到网站。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-135">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
  - <span data-ttu-id="dd6e8-136">如果到组织的[自定义被阻止的 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的网站 URL，用户将转到[警告页](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-136">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
  - <span data-ttu-id="dd6e8-137">如果已确定要恶意的网站 URL，用户进入，[警告页](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-137">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
  - <span data-ttu-id="dd6e8-138">如果 URL 转到一个可下载的文件和[ATP 安全链接策略](set-up-atp-safe-links-policies.md)配置为扫描此类下载，则检查可下载文件。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-138">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
  - <span data-ttu-id="dd6e8-139">如果认为 URL 是安全的用户将转到网站。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-139">If the URL is considered safe, the user is taken to the website.</span></span>

## <a name="how-to-get-atp-safe-links-protection"></a><span data-ttu-id="dd6e8-140">如何获取 ATP 安全链接保护</span><span class="sxs-lookup"><span data-stu-id="dd6e8-140">How to get ATP Safe Links protection</span></span>

<span data-ttu-id="dd6e8-p109">首先，请确保您的订阅包括[高级威胁保护](office-365-atp.md)。ATP 中包含在订阅，如[Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise/home)、 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/business)、 Office 365 企业 E5、 Office 365 教育版 A5 等。如果您的组织具有不包括 Office 365 ATP 的 Office 365 订阅，您可能可以作为购买 ATP。有关详细信息，请参阅[Office 365 高级威胁保护计划和定价](https://products.office.com/exchange/advance-threat-protection)和[Office 365 高级威胁 Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p109">First, make sure your subscription includes [Advanced Threat Protection](office-365-atp.md). ATP is included in in subscriptions, such as [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise/home), [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business), Office 365 Enterprise E5, Office 365 Education A5, etc. If your organization has an Office 365 subscription that does not include Office 365 ATP, you can potentially purchase ATP as an add-on. For more information, see [Office 365 Advanced Threat Protection plans and pricing](https://products.office.com/exchange/advance-threat-protection) and the [Office 365 Advanced Threat Protection Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span> 
  
<span data-ttu-id="dd6e8-p110">接下来，请确保您 ATP 安全链接的策略定义。（请参阅[Set up Office 365 ATP 安全链接策略](set-up-atp-safe-links-policies.md)）。ATP 安全链接功能处于活动状态时：</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p110">Next, make sure your ATP Safe Links policies are defined. (See [Set up Office 365 ATP Safe Links policies](set-up-atp-safe-links-policies.md).) ATP Safe Links features are active when:</span></span>
  
- <span data-ttu-id="dd6e8-p111">为电子邮件和 Word、 Excel、 PowerPoint 和 Visio 文档中，则**ATP 安全链接策略设置**。（请参阅[Set up ATP Office 365 中的安全链接策略](set-up-atp-safe-links-policies.md)）。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p111">**ATP Safe Links policies are set up** for email and for Word, Excel, PowerPoint, and Visio documents. (See [Set up ATP safe links policies in Office 365](set-up-atp-safe-links-policies.md).)</span></span>

- <span data-ttu-id="dd6e8-p112">**Office 365 客户端应用程序配置为使用现代身份验证**（这是 ATP 安全链接保护 Office 文档中的值）。（请参阅[Office 2016 现代身份验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)。）</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p112">**Office 365 client apps are configured to use Modern Authentication** (this is for ATP Safe Links protection in Office documents). (See [Modern Authentication for Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).)</span></span> 
    
- <span data-ttu-id="dd6e8-p113">**用户已登录到 Office 365**使用其工作或学校帐户。（请参阅[登录到 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)）。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p113">**Users have signed into Office 365** using their work or school account. (See [Sign in to Office or Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)</span></span>
    
- <span data-ttu-id="dd6e8-152">**贵组织的电子邮件通过 Exchange Online Protection**。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-152">**Your organization's email passes through Exchange Online Protection**.</span></span>  

<span data-ttu-id="dd6e8-153">若要定义 （或编辑） ATP 策略，您必须为分配下表中所述的角色之一：</span><span class="sxs-lookup"><span data-stu-id="dd6e8-153">To define (or edit) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="dd6e8-154">角色</span><span class="sxs-lookup"><span data-stu-id="dd6e8-154">Role</span></span>  |<span data-ttu-id="dd6e8-155">其中/如何分配</span><span class="sxs-lookup"><span data-stu-id="dd6e8-155">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="dd6e8-156">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="dd6e8-156">Office 365 Global Administrator</span></span> |<span data-ttu-id="dd6e8-p114">注册以购买 Office 365 的人是默认情况下是全局管理员。（请参阅要了解的[有关 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)）。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p114">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="dd6e8-159">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="dd6e8-159">Security Administrator</span></span> |<span data-ttu-id="dd6e8-160">Azure Active Directory 管理员中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="dd6e8-160">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="dd6e8-161">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="dd6e8-161">Exchange Online Organization Management</span></span> |<span data-ttu-id="dd6e8-162">Exchange 管理员中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="dd6e8-162">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="dd6e8-163">或</span><span class="sxs-lookup"><span data-stu-id="dd6e8-163">or</span></span> <br>  <span data-ttu-id="dd6e8-164">PowerShell cmdlet (请参阅[Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="dd6e8-164">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |
    
## <a name="how-to-make-sure-atp-safe-links-protection-is-in-place"></a><span data-ttu-id="dd6e8-165">如何使确保 ATP 安全链接保护已就绪</span><span class="sxs-lookup"><span data-stu-id="dd6e8-165">How to make sure ATP Safe Links protection is in place</span></span>

<span data-ttu-id="dd6e8-p115">以全局管理员或安全管理员，务必要查看您的[ATP 安全链接策略](set-up-atp-safe-links-policies.md)。ATP 安全链接策略确定是否保护适用于电子邮件中的超链接，或 Url 以及 Office 文档中。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p115">As a global administrator or security administrator, be sure to review your [ATP Safe Links policies](set-up-atp-safe-links-policies.md). ATP Safe Links policies determine whether protection applies to hyperlinks in email messages only, or to URLs in Office documents as well.</span></span>

<span data-ttu-id="dd6e8-168">贵组织的安全工作组 ATP 安全链接策略后，可以查看如何 ATP 安全链接保护正常为贵组织的[高级威胁 protection 查看报表](view-reports-for-atp.md)，请参阅。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-168">After ATP Safe Links policies are in place, your organization's security team can see see how ATP Safe Links protection is working for your organization is by [viewing reports for Advanced Threat Protection](view-reports-for-atp.md).</span></span> 

## <a name="example-scenarios"></a><span data-ttu-id="dd6e8-169">示例场景</span><span class="sxs-lookup"><span data-stu-id="dd6e8-169">Example scenarios</span></span>
  
<span data-ttu-id="dd6e8-p116">下表介绍了一些示例方案 ATP 安全链接保护可能或可能不是就地的位置。（在所有这些情况下，我们假定组织具有 Office 365 企业 E5。）</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p116">The following table describes some example scenarios where ATP Safe Links protection might or might not be in place. (In all of these cases, we assume the organization has Office 365 Enterprise E5.)</span></span>
  
|<span data-ttu-id="dd6e8-172">**示例应用场景**</span><span class="sxs-lookup"><span data-stu-id="dd6e8-172">**Example scenario**</span></span>|<span data-ttu-id="dd6e8-173">**ATP 安全链接保护不适用于这种情况下？**</span><span class="sxs-lookup"><span data-stu-id="dd6e8-173">**Does ATP Safe Links protection apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dd6e8-p117">Jean 是组的具有 ATP 安全链接策略涵盖电子邮件和 Office 文档中的 Url 的成员。Jean 某人发送，打开 PowerPoint 演示文稿，然后单击演示文稿中的 URL。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p117">Jean is a member of a group that has ATP Safe Links policies covering URLs in email and Office documents. Jean opens a PowerPoint presentation that someone sent, and then clicks a URL in the presentation.</span></span>  <br/> |<span data-ttu-id="dd6e8-p118">是的。定义 ATP 安全链接策略应用于 Jean 的组、 Jean 的电子邮件、 Word、 Excel、 PowerPoint 或 Visio 文档 Jean 打开，只要 Jean 登录，并在 Windows、 iOS 或 Android 设备上使用 Office 365 ProPlus。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p118">Yes. The ATP Safe Links policies that are defined apply to Jean's group, Jean's email, and Word, Excel, PowerPoint, or Visio documents that Jean opens, so long as Jean is signed in and using Office 365 ProPlus on Windows, iOS, or Android devices.</span></span>  <br/> |
|<span data-ttu-id="dd6e8-p119">Chris 的组织，不全局或安全管理员具有尚未定义任何 ATP 安全链接策略。Chris 接收的电子邮件包含恶意网站的 URL。Chris 不知道是恶意 URL，并单击的链接。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p119">In Chris's organization, no global or security administrators have defined any ATP safe links policies yet. Chris receives an email that contains a URL to a malicious website. Chris is unaware the URL is malicious and clicks the link.</span></span>  <br/> |<span data-ttu-id="dd6e8-p120">不。为了保护，以准备就绪，必须定义默认策略，以涵盖的组织中的每个人的 Url。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p120">No. The default policy that covers URLs for everyone in the organization must be defined in order for protection to be in place.</span></span>  <br/> |
|<span data-ttu-id="dd6e8-p121">在 Pat 组织，不全局或安全管理员定义或者尚未编辑 ATP 安全链接的任何策略。Pat 打开 Word 文档，并单击该文件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p121">In Pat's organization, no global or security administrators have defined or edited any ATP Safe Links policies yet. Pat opens a Word document and clicks a URL in the file.</span></span>  <br/> |<span data-ttu-id="dd6e8-p122">为了保护，以准备就绪，必须定义否。 A 策略，其中包括 Office 文档。请参阅[Office 365 中的安全链接 ATP 策略设置](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p122">No. A policy that includes Office documents must be defined in order for protection to be in place. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  </span></span><br/> |
|<span data-ttu-id="dd6e8-p123">李的组织具有 ATP 安全链接策略已`http://tailspintoys.com`列为被阻止的网站。李接收电子邮件包含 URL 的`http://tailspintoys.com/aboutus/trythispage`。李单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p123">Lee's organization has a ATP Safe Links policy that has `http://tailspintoys.com` listed as a blocked website. Lee receives an email message that contains a URL to `http://tailspintoys.com/aboutus/trythispage`. Lee clicks the URL.  </span></span><br/> |<span data-ttu-id="dd6e8-p124">这取决于整个网站及其所有及其子页都包含在列表中是否阻止 Url。请参阅[设置自定义阻止 Url 列表使用 ATP 安全链接](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p124">It depends on whether the entire site and all its subpages are included in the list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).  </span></span><br/> |
|<span data-ttu-id="dd6e8-193">晓明，Jean 的同事，将电子邮件发送到 Jean，不知道电子邮件包含恶意的 URL。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-193">Jamie, Jean's colleague, sends an email to Jean, not knowing that the email contains a malicious URL.</span></span>  <br/> |<span data-ttu-id="dd6e8-p125">这取决于是否为在组织中发送电子邮件定义 ATP 安全链接策略。请参阅[Office 365 中的安全链接 ATP 策略设置](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="dd6e8-p125">It depends on whether ATP Safe Links policies are defined for email sent within the organization. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  </span></span><br/> |


  

