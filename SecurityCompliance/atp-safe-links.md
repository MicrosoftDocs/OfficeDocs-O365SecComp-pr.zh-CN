---
title: Office 365 ATP 安全链接
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
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
ms.openlocfilehash: 9199c69d73a1585d76181c7a5feba79e465289db
ms.sourcegitcommit: e14dec9bed0c0009acbc1f1cb80b4d0794ad5739
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/05/2018
ms.locfileid: "25435109"
---
# <a name="office-365-atp-safe-links"></a><span data-ttu-id="0603b-104">Office 365 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="0603b-104">Office 365 ATP Safe Links</span></span>

<span data-ttu-id="0603b-p102">Office 365 ATP 安全链接 （ATP 安全链接） （以及[Office 365 ATP 安全附件](atp-safe-attachments.md)） 是一套安全功能的[Office 365 高级威胁保护](office-365-atp.md)企业组织的一部分提供。ATP 安全链接可帮助保护您的组织提供的[电子邮件](#how-atp-safe-links-works-with-email)和[Office 文档](#how-atp-safe-links-works-with-office-documents)中的 web 地址 (Url) 的时间的单击验证。保护通过[ATP 安全链接策略](set-up-atp-safe-links-policies.md)设置您的 Office 365 安全工作组的定义。</span><span class="sxs-lookup"><span data-stu-id="0603b-p102">Office 365 ATP Safe Links (ATP Safe Links) (along with [Office 365 ATP Safe Attachments](atp-safe-attachments.md)) is a set of security features offered as part of [Office 365 Advanced Threat Protection](office-365-atp.md) for enterprise organizations. ATP Safe Links can help protect your organization by providing time-of-click verification of web addresses (URLs) in [email messages](#how-atp-safe-links-works-with-email) and [Office documents](#how-atp-safe-links-works-with-office-documents). Protection is defined through [ATP Safe Links policies](set-up-atp-safe-links-policies.md) that are set by your Office 365 security team.</span></span> 
  
<span data-ttu-id="0603b-p103">位置 ATP 安全链接策略后，Office 365 全局管理员、 安全管理员和安全读者可以[用于高级威胁保护查看报告](view-reports-for-atp.md)。这些报告中的信息可帮助您采取进一步措施保护您的组织或调查安全事件的安全团队。</span><span class="sxs-lookup"><span data-stu-id="0603b-p103">Once your ATP Safe Links policies are in place, Office 365 global administrators, security administrators, and security readers can [view reports for Advanced Threat Protection](view-reports-for-atp.md). The information in those reports can help your security team take further steps to protect your organization or research security incidents.</span></span>
         
## <a name="how-atp-safe-links-works-with-email"></a><span data-ttu-id="0603b-110">电子邮件时，ATP 安全链接的工作方式</span><span class="sxs-lookup"><span data-stu-id="0603b-110">How ATP Safe Links works with email</span></span>

<span data-ttu-id="0603b-111">在高级别，下面是 ATP 安全链接保护的工作原理 Url 的电子邮件 （托管在 Office 365 中，不在本地） 中：</span><span class="sxs-lookup"><span data-stu-id="0603b-111">At a high level, here's how ATP Safe Links protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="0603b-112">人员接收电子邮件，其中一些包含 Url。</span><span class="sxs-lookup"><span data-stu-id="0603b-112">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="0603b-113">基于签名的恶意软件保护，反垃圾邮件通过 Exchange Online Protection，其中 internet 协议 (IP) 和信封筛选器，转所有电子邮件和反恶意软件筛选器应用。</span><span class="sxs-lookup"><span data-stu-id="0603b-113">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="0603b-114">电子邮件到达人的收件箱中。</span><span class="sxs-lookup"><span data-stu-id="0603b-114">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="0603b-115">用户登录到 Office 365，并转到其电子邮件收件箱。</span><span class="sxs-lookup"><span data-stu-id="0603b-115">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="0603b-116">用户打开一封电子邮件，并单击电子邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="0603b-116">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="0603b-p104">ATP 安全链接功能立即打开网站之前检查的 URL。URL 标识为阻止，恶意，或安全。</span><span class="sxs-lookup"><span data-stu-id="0603b-p104">The ATP Safe Links feature immediately checks the URL before opening the website. The URL is identified as blocked, malicious, or safe.</span></span>
    
    - <span data-ttu-id="0603b-119">如果 URL 包含应用于用户的策略[自定义"执行不重写"Url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)中的网站，网站打开。</span><span class="sxs-lookup"><span data-stu-id="0603b-119">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens.</span></span> 
    
    - <span data-ttu-id="0603b-120">如果 URL 是到组织的[自定义被阻止的 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的网站，[警告页](atp-safe-links-warning-pages.md)将打开。</span><span class="sxs-lookup"><span data-stu-id="0603b-120">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="0603b-121">如果已确定要恶意的网站 URL，打开[警告页](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="0603b-121">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="0603b-122">如果 URL 转到一个可下载的文件和组织的[安全链接 ATP 策略](set-up-atp-safe-links-policies.md)配置为扫描此类内容，则检查可下载文件。</span><span class="sxs-lookup"><span data-stu-id="0603b-122">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
    - <span data-ttu-id="0603b-123">如果 URL 确定为安全起见，打开网站。</span><span class="sxs-lookup"><span data-stu-id="0603b-123">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-office-documents"></a><span data-ttu-id="0603b-124">Office 文档时，ATP 安全链接的工作方式</span><span class="sxs-lookup"><span data-stu-id="0603b-124">How ATP Safe Links works with Office documents</span></span>

<span data-ttu-id="0603b-125">在高级别，下面是 ATP 安全链接保护的工作原理 Url 的 Office 365 ProPlus 应用程序 （当前版本的 Word、 Excel 和 PowerPoint 在 Windows 或 Mac 上 iOS 或 Android 设备，在 Windows、 OneNote Online 和 Office Online 上的 Visio 的 Office 应用程序上） 中：</span><span class="sxs-lookup"><span data-stu-id="0603b-125">At a high level, here's how ATP Safe Links protection works for URLs in Office 365 ProPlus applications (current versions of Word, Excel, and PowerPoint on Windows or Mac, Office apps on iOS or Android devices, Visio on Windows, OneNote Online, and Office Online):</span></span>
  
1. <span data-ttu-id="0603b-p105">人员已在其计算机、 smartphone 或平板电脑上安装 Office 365 ProPlus。（或者，将 Office Online，在其浏览器中。）</span><span class="sxs-lookup"><span data-stu-id="0603b-p105">People have installed Office 365 ProPlus on their computer, smartphone, or tablet. (Or, they are using Office Online in their browser.)</span></span>
    
2. <span data-ttu-id="0603b-p106">用户打开 Word、 Excel、 PowerPoint 或 Visio，并登录到 Office 365 企业版使用其工作或学校帐户。文档包含的 Url。</span><span class="sxs-lookup"><span data-stu-id="0603b-p106">A user opens a Word, Excel, PowerPoint, or Visio, and signs in to Office 365 Enterprise using their work or school account. The document contains URLs.</span></span>
    
3. <span data-ttu-id="0603b-130">当用户单击文档中的 URL 时，链接将检查 ATP 安全链接服务。</span><span class="sxs-lookup"><span data-stu-id="0603b-130">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
  - <span data-ttu-id="0603b-131">如果应用于用户的策略[自定义"执行不重写"Url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)中包含的网站 URL，该用户是转到网站。</span><span class="sxs-lookup"><span data-stu-id="0603b-131">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
  - <span data-ttu-id="0603b-132">如果到组织的[自定义被阻止的 Url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)中包含的网站 URL，用户将转到[警告页](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="0603b-132">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
  - <span data-ttu-id="0603b-133">如果已确定要恶意的网站 URL，用户进入，[警告页](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="0603b-133">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
  - <span data-ttu-id="0603b-134">如果 URL 转到一个可下载的文件和[ATP 安全链接策略](set-up-atp-safe-links-policies.md)配置为扫描此类下载，则检查可下载文件。</span><span class="sxs-lookup"><span data-stu-id="0603b-134">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
  - <span data-ttu-id="0603b-135">如果认为 URL 是安全的用户将转到网站。</span><span class="sxs-lookup"><span data-stu-id="0603b-135">If the URL is considered safe, the user is taken to the website.</span></span>

## <a name="new-features-added-to-atp-safe-links"></a><span data-ttu-id="0603b-136">新功能添加到 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="0603b-136">New features added to ATP Safe Links</span></span>

<span data-ttu-id="0603b-p107">我们将继续向 ATP 安全链接添加新功能。以下是几个示例：</span><span class="sxs-lookup"><span data-stu-id="0603b-p107">We are continuing to add new features to ATP Safe Links. Here are several examples:</span></span>
  
- <span data-ttu-id="0603b-p108">从开始后期年 10 月 2017年，ATP 安全链接保护扩展到 Url 为 Url 或电子邮件中 Office 365 ProPlus 的文档，如 Word、 Excel、 PowerPoint 和 Visio 中对应用 Windows，以及 Office iOS 和 Android 设备上的应用程序。（请确保您使用的[Office 现代身份验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)。）</span><span class="sxs-lookup"><span data-stu-id="0603b-p108">Beginning in late October 2017, ATP Safe Links protection is extended to apply to URLs in email as well as URLs in Office 365 ProPlus documents, such as Word, Excel, PowerPoint, and Visio on Windows, as well as Office apps on iOS and Android devices. (Make sure you're using [Modern Authentication for Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).)</span></span>
    
- <span data-ttu-id="0603b-p109">从开始年 3 月 2018年，被扩展 ATP 安全链接保护应用于组织内的人员之间发送的电子邮件。（请确保[查看](set-up-atp-safe-links-policies.md)和编辑 ATP 安全链接策略。）</span><span class="sxs-lookup"><span data-stu-id="0603b-p109">Beginning in March 2018, ATP Safe Links protection is extended to apply to email sent between people within an organization. (Make sure to [review and edit your ATP Safe Links policies](set-up-atp-safe-links-policies.md).)</span></span>

- <span data-ttu-id="0603b-p110">年 6 月 2018，当用户使用 Outlook Web 应用程序 (OWA)，在开始 ATP 安全链接呈现原始 Url，并不显示重写的 Url。这样用户电子邮件中查看原始的链接。（我们调用此本机链接 visbility）。</span><span class="sxs-lookup"><span data-stu-id="0603b-p110">Beginning in June 2018, when people are using Outlook Web Application (OWA), ATP Safe Links renders original URLs, and not show rewritten URLs. This enables users to view original links in email. (We call this native link visbility.)</span></span>

- <span data-ttu-id="0603b-146">年 9 月 2018年中的开始、 [Office 365 ATP 警告页](atp-safe-links-warning-pages.md)功能新的配色方案、 更多详细信息，和以继续前进到尽管网站的功能在给定警告和建议。</span><span class="sxs-lookup"><span data-stu-id="0603b-146">Beginning in September 2018, [Office 365 ATP warning pages](atp-safe-links-warning-pages.md) feature a new color scheme, more details, and the ability to continue to a site despite given warnings and recommendations.</span></span> 
  
- <span data-ttu-id="0603b-p111">开始在 2018年的第二部分中，ATP 安全链接被扩展保护于 Url 的 Office Online （Word Online、 Excel Online、 PowerPoint Online 和 OneNote 联机） 和 Office 365 ProPlus 上 mac。（请确保[查看](set-up-atp-safe-links-policies.md)和编辑 ATP 安全链接策略。）</span><span class="sxs-lookup"><span data-stu-id="0603b-p111">Beginning in the second half of 2018, ATP Safe Links protection is extended to apply to URLs in Office Online (Word Online, Excel Online, PowerPoint Online, and OneNote Online) and Office 365 ProPlus on Mac. (Make sure to [review and edit your ATP Safe Links policies](set-up-atp-safe-links-policies.md).)</span></span>
   
- <span data-ttu-id="0603b-p112">从开始后期 2018年，本机链接可见性是 Outlook 中可用。无论使用 OWA 或 Outlook，用户能够在电子邮件，查看原始 Url (不重写 Url)。</span><span class="sxs-lookup"><span data-stu-id="0603b-p112">Beginning in late 2018, native link visibility is available in Outlook. Users are able to view original URLs (not rewritten URLs) in email, whether they're using OWA or Outlook.</span></span>
    
## <a name="how-to-get-atp-safe-links-protection"></a><span data-ttu-id="0603b-151">如何获取 ATP 安全链接保护</span><span class="sxs-lookup"><span data-stu-id="0603b-151">How to get ATP Safe Links protection</span></span>

<span data-ttu-id="0603b-p113">ATP 安全链接功能是[高级威胁保护](office-365-atp.md)，包括在 Office 365 企业 E5 的一部分。如果您的组织使用的另一个 Office 365 企业版订阅，高级威胁保护可以作为加载项进行购买。有关详细信息，请参阅[Office 365 平台服务说明： Office 365 安全性&amp;合规性中心](https://technet.microsoft.com/en-us/library/dn933793.aspx)和[购买或编辑企业的 Office 365 的加载项](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6)。</span><span class="sxs-lookup"><span data-stu-id="0603b-p113">ATP Safe Links features are part of [Advanced Threat Protection](office-365-atp.md), included in Office 365 Enterprise E5. If your organization is using another Office 365 Enterprise subscription, Advanced Threat Protection can be purchased as an add-on. For more information, see [Office 365 Platform Service Description: Office 365 Security &amp; Compliance Center](https://technet.microsoft.com/en-us/library/dn933793.aspx) and [Buy or edit an add-on for Office 365 for business](https://support.office.com/article/4e7b57d6-b93b-457d-aecd-0ea58bff07a6).</span></span>
  
<span data-ttu-id="0603b-155">ATP 安全链接功能处于活动状态时：</span><span class="sxs-lookup"><span data-stu-id="0603b-155">The ATP Safe Links features are active when:</span></span>
  
- <span data-ttu-id="0603b-p114">为电子邮件和 Word、 Excel、 PowerPoint 和 Visio 文档中，则**ATP 安全链接策略设置**。（请参阅[Set up ATP Office 365 中的安全链接策略](set-up-atp-safe-links-policies.md)）。</span><span class="sxs-lookup"><span data-stu-id="0603b-p114">**ATP Safe Links policies are set up** for email and for Word, Excel, PowerPoint, and Visio documents. (See [Set up ATP safe links policies in Office 365](set-up-atp-safe-links-policies.md).)</span></span>

- <span data-ttu-id="0603b-p115">**Office 365 客户端应用程序配置为使用现代身份验证**。（请参阅[Office 2016 现代身份验证](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016)。）</span><span class="sxs-lookup"><span data-stu-id="0603b-p115">**Office 365 client apps are configured to use Modern Authentication**. (See [Modern Authentication for Office 2016](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).)</span></span> 
    
- <span data-ttu-id="0603b-p116">**用户已登录到 Office 365**使用其工作或学校帐户。（请参阅[登录到 Office 或 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426)）。</span><span class="sxs-lookup"><span data-stu-id="0603b-p116">**Users have signed into Office 365** using their work or school account. (See [Sign in to Office or Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426).)</span></span>
    
- <span data-ttu-id="0603b-162">**贵组织的电子邮件托管 Office 365 中**，不在内部部署服务器。</span><span class="sxs-lookup"><span data-stu-id="0603b-162">**Your organization's email is hosted in Office 365**, not in an on-premises server.</span></span> 
    
## <a name="make-sure-atp-safe-links-protection-is-in-place"></a><span data-ttu-id="0603b-163">请确保 ATP 安全链接保护就地</span><span class="sxs-lookup"><span data-stu-id="0603b-163">Make sure ATP Safe Links protection is in place</span></span>

<span data-ttu-id="0603b-p117">请参阅如何使用 ATP 安全链接保护运行您的组织的一个好办法是通过[查看高级威胁保护报告](view-reports-for-atp.md)。此外，作为全局或安全管理员，请务必查看您的[ATP 安全链接策略](set-up-atp-safe-links-policies.md)。ATP 安全链接策略确定是否保护适用于电子邮件中的超链接，或 Url 以及 Office 文档中。</span><span class="sxs-lookup"><span data-stu-id="0603b-p117">One good way to see how ATP Safe Links protection is working for your organization is by [viewing reports for Advanced Threat Protection](view-reports-for-atp.md). Additionally, as a global or security administrator, be sure to review your [ATP Safe Links policies](set-up-atp-safe-links-policies.md). ATP Safe Links policies determine whether protection applies to hyperlinks in email messages only, or to URLs in Office documents as well.</span></span>

## <a name="example-scenarios-where-atp-safe-links-protection-might-or-might-not-be-in-place"></a><span data-ttu-id="0603b-167">示例方案 ATP 安全链接保护可能或可能不是就地的位置</span><span class="sxs-lookup"><span data-stu-id="0603b-167">Example scenarios where ATP Safe Links protection might or might not be in place</span></span>
  
<span data-ttu-id="0603b-p118">下表介绍了一些示例方案 ATP 安全链接保护可能或可能不是就地的位置。（在所有这些情况下，我们假定组织具有 Office 365 企业 E5。）</span><span class="sxs-lookup"><span data-stu-id="0603b-p118">The following table describes some example scenarios where ATP Safe Links protection might or might not be in place. (In all of these cases, we assume the organization has Office 365 Enterprise E5.)</span></span>
  
|<span data-ttu-id="0603b-170">**示例应用场景**</span><span class="sxs-lookup"><span data-stu-id="0603b-170">**Example scenario**</span></span>|<span data-ttu-id="0603b-171">**ATP 安全链接保护不适用于这种情况下？**</span><span class="sxs-lookup"><span data-stu-id="0603b-171">**Does ATP Safe Links protection apply in this case?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0603b-p119">Jean 是组的具有 ATP 安全链接策略涵盖电子邮件和 Office 文档中的 Url 的成员。Jean 某人发送 PowerPoint 2016 中打开一个演示文稿，然后单击演示文稿中的 URL。</span><span class="sxs-lookup"><span data-stu-id="0603b-p119">Jean is a member of a group that has ATP Safe Links policies covering URLs in email and Office documents. Jean opens a presentation that someone sent in PowerPoint 2016, and then clicks a URL in the presentation.</span></span>  <br/> |<span data-ttu-id="0603b-p120">是的。定义 ATP 安全链接策略应用于 Jean 的组、 Jean 的电子邮件、 Word、 Excel、 PowerPoint 或 Visio 文档 Jean 打开，只要 Jean 登录，并在 Windows、 iOS 或 Android 设备上使用 Office 365 ProPlus。</span><span class="sxs-lookup"><span data-stu-id="0603b-p120">Yes. The ATP Safe Links policies that are defined apply to Jean's group, Jean's email, and Word, Excel, PowerPoint, or Visio documents that Jean opens, so long as Jean is signed in and using Office 365 ProPlus on Windows, iOS, or Android devices.</span></span>  <br/> |
|<span data-ttu-id="0603b-p121">Chris 的组织，不全局或安全管理员具有尚未定义任何 ATP 安全链接策略。Chris 接收的电子邮件包含恶意网站的 URL。Chris 不知道是恶意 URL，并单击的链接。</span><span class="sxs-lookup"><span data-stu-id="0603b-p121">In Chris's organization, no global or security administrators have defined any ATP safe links policies yet. Chris receives an email that contains a URL to a malicious website. Chris is unaware the URL is malicious and clicks the link.</span></span>  <br/> |<span data-ttu-id="0603b-p122">不。为了保护，以准备就绪，必须定义默认策略，以涵盖的组织中的每个人的 Url。</span><span class="sxs-lookup"><span data-stu-id="0603b-p122">No. The default policy that covers URLs for everyone in the organization must be defined in order for protection to be in place.</span></span>  <br/> |
|<span data-ttu-id="0603b-p123">在 Pat 组织，不全局或安全管理员定义或者尚未编辑 ATP 安全链接的任何策略。Pat 打开 Word 文档，并单击该文件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="0603b-p123">In Pat's organization, no global or security administrators have defined or edited any ATP Safe Links policies yet. Pat opens a Word document and clicks a URL in the file.</span></span>  <br/> |<span data-ttu-id="0603b-p124">为了保护，以准备就绪，必须定义否。 A 策略，其中包括 Office 文档。请参阅[Office 365 中的安全链接 ATP 策略设置](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0603b-p124">No. A policy that includes Office documents must be defined in order for protection to be in place. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  </span></span><br/> |
|<span data-ttu-id="0603b-p125">李的组织具有 ATP 安全链接策略已`http://tailspintoys.com`列为被阻止的网站。李接收电子邮件包含 URL 的`http://tailspintoys.com/aboutus/trythispage`。李单击的 URL。</span><span class="sxs-lookup"><span data-stu-id="0603b-p125">Lee's organization has a ATP Safe Links policy that has `http://tailspintoys.com` listed as a blocked website. Lee receives an email message that contains a URL to `http://tailspintoys.com/aboutus/trythispage`. Lee clicks the URL.  </span></span><br/> |<span data-ttu-id="0603b-p126">这取决于整个网站及其所有及其子页都包含在列表中是否阻止 Url。请参阅[设置自定义阻止 Url 列表使用 ATP 安全链接](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="0603b-p126">It depends on whether the entire site and all its subpages are included in the list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).  </span></span><br/> |
|<span data-ttu-id="0603b-191">晓明，Jean 的同事，将电子邮件发送到 Jean，不知道电子邮件包含恶意的 URL。</span><span class="sxs-lookup"><span data-stu-id="0603b-191">Jamie, Jean's colleague, sends an email to Jean, not knowing that the email contains a malicious URL.</span></span>  <br/> |<span data-ttu-id="0603b-p127">这取决于是否为在组织中发送电子邮件定义 ATP 安全链接策略。请参阅[Office 365 中的安全链接 ATP 策略设置](set-up-atp-safe-links-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="0603b-p127">It depends on whether ATP Safe Links policies are defined for email sent within the organization. See [Set up ATP Safe Links policies in Office 365](set-up-atp-safe-links-policies.md).  </span></span><br/> |
   
## <a name="related-topics"></a><span data-ttu-id="0603b-194">相关主题</span><span class="sxs-lookup"><span data-stu-id="0603b-194">Related topics</span></span>

[<span data-ttu-id="0603b-195">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="0603b-195">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
  
[<span data-ttu-id="0603b-196">设置 Office 365 中的安全链接 ATP 策略</span><span class="sxs-lookup"><span data-stu-id="0603b-196">Set up ATP Safe Links policies in Office 365</span></span>](set-up-atp-safe-links-policies.md)
  
[<span data-ttu-id="0603b-197">Office 365 中的 ATP 安全附件</span><span class="sxs-lookup"><span data-stu-id="0603b-197">ATP Safe Attachments in Office 365</span></span>](atp-safe-attachments.md)
  
[<span data-ttu-id="0603b-198">Office 365 中的 ATP 防钓鱼功能</span><span class="sxs-lookup"><span data-stu-id="0603b-198">ATP anti-phishing capabilities in Office 365</span></span>](atp-anti-phishing.md)
  
[<span data-ttu-id="0603b-199">查看高级威胁保护报告</span><span class="sxs-lookup"><span data-stu-id="0603b-199">View the reports for Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

