---
title: Office 365 ATP 安全链接的工作原理
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.date: 05/19/2019
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: "\"安全链接\" 功能可提供对 Office 文档中的超链接和电子邮件中的超链接的单击时间验证。 阅读本文, 了解 ATP 安全链接的工作原理。"
ms.openlocfilehash: 7570fd65a9831a6436eec8c402a2bc0c2ae09b40
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599178"
---
# <a name="how-office-365-atp-safe-links-works"></a><span data-ttu-id="987d2-104">Office 365 ATP 安全链接的工作原理</span><span class="sxs-lookup"><span data-stu-id="987d2-104">How Office 365 ATP Safe Links works</span></span>
         
## <a name="how-atp-safe-links-works-with-urls-in-email"></a><span data-ttu-id="987d2-105">ATP 安全链接如何处理电子邮件中的 Url</span><span class="sxs-lookup"><span data-stu-id="987d2-105">How ATP Safe Links works with URLs in email</span></span>

<span data-ttu-id="987d2-106">从较高的层次来看, [ATP 安全链接](atp-safe-links.md)保护对电子邮件中的 url 的工作方式 (托管在 Office 365 中, 而不是在本地中):</span><span class="sxs-lookup"><span data-stu-id="987d2-106">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in email (hosted in Office 365, not on-premises):</span></span>
  
1. <span data-ttu-id="987d2-107">用户接收包含 Url 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="987d2-107">People receive email messages, some of which contain URLs.</span></span>
    
2. <span data-ttu-id="987d2-108">所有电子邮件都通过 Exchange Online 保护, 其中应用了 internet 协议 (IP) 和信封筛选器、基于签名的恶意软件保护、反垃圾邮件和反恶意软件筛选器。</span><span class="sxs-lookup"><span data-stu-id="987d2-108">All email goes through Exchange Online Protection, where internet protocol (IP) and envelope filters, signature-based malware protection, anti-spam and anti-malware filters are applied.</span></span> 
    
3. <span data-ttu-id="987d2-109">电子邮件到达用户的收件箱。</span><span class="sxs-lookup"><span data-stu-id="987d2-109">Email arrives in people's inboxes.</span></span>
    
4. <span data-ttu-id="987d2-110">用户登录到 Office 365, 并转到其电子邮件收件箱。</span><span class="sxs-lookup"><span data-stu-id="987d2-110">A user signs in to Office 365, and goes to their email inbox.</span></span>
    
5. <span data-ttu-id="987d2-111">用户打开一封电子邮件, 然后单击电子邮件中的 URL。</span><span class="sxs-lookup"><span data-stu-id="987d2-111">The user opens an email message, and clicks on a URL in the email message.</span></span>
    
6. <span data-ttu-id="987d2-112">ATP 安全链接功能将在打开网站之前立即检查 URL。</span><span class="sxs-lookup"><span data-stu-id="987d2-112">The ATP Safe Links feature immediately checks the URL before opening the website.</span></span> <span data-ttu-id="987d2-113">该 URL 被标识为 "阻止"、"恶意" 或 "安全"。</span><span class="sxs-lookup"><span data-stu-id="987d2-113">The URL is identified as blocked, malicious, or safe.</span></span>
    
    - <span data-ttu-id="987d2-114">如果 URL 指向的网站包含在适用于该用户的策略的[自定义 "不重写" url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)中, 则会打开该网站。</span><span class="sxs-lookup"><span data-stu-id="987d2-114">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, the website opens.</span></span> 
    
    - <span data-ttu-id="987d2-115">如果 URL 指向的网站包含在组织的[自定义阻止 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)中, 则会打开一个[警告页面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="987d2-115">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="987d2-116">如果 URL 指向已确定为恶意的网站, 将打开 "[警告" 页](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="987d2-116">If the URL is to a website that has been determined to be malicious, a [warning page](atp-safe-links-warning-pages.md) opens.</span></span> 
    
    - <span data-ttu-id="987d2-117">如果 URL 转到一个可下载的文件, 并且您的组织的[ATP 安全链接策略](set-up-atp-safe-links-policies.md)已配置为扫描此类内容, 则会检查下载的文件。</span><span class="sxs-lookup"><span data-stu-id="987d2-117">If the URL goes to a downloadable file and your organization's [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such content, the downloadable file is checked.</span></span> 
    
    - <span data-ttu-id="987d2-118">如果确定该 URL 是安全的, 则会打开该网站。</span><span class="sxs-lookup"><span data-stu-id="987d2-118">If the URL is determined to be safe, the website opens.</span></span>
    
## <a name="how-atp-safe-links-works-with-urls-in-office-documents"></a><span data-ttu-id="987d2-119">ATP 安全链接如何处理 Office 文档中的 Url</span><span class="sxs-lookup"><span data-stu-id="987d2-119">How ATP Safe Links works with URLs in Office documents</span></span>

<span data-ttu-id="987d2-120">在较高级别, 以下是[ATP 安全链接](atp-safe-links.md)保护对 Office 365 专业增强版应用程序中的 url 的工作方式 (Windows 或 Mac 上的当前版本的 Word、Excel 和 PowerPoint、IOS 或 Android 设备上的 Office 应用、OneNote Online 和 Office)联机):</span><span class="sxs-lookup"><span data-stu-id="987d2-120">At a high level, here's how [ATP Safe Links](atp-safe-links.md) protection works for URLs in Office 365 ProPlus applications (current versions of Word, Excel, and PowerPoint on Windows or Mac, Office apps on iOS or Android devices, Visio on Windows, OneNote Online, and Office Online):</span></span>
  
1. <span data-ttu-id="987d2-121">用户在其计算机、智能手机或平板电脑上安装了 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="987d2-121">People have installed Office 365 ProPlus on their computer, smartphone, or tablet.</span></span> <span data-ttu-id="987d2-122">(或者, 他们正在浏览器中使用 Office Online。)</span><span class="sxs-lookup"><span data-stu-id="987d2-122">(Or, they are using Office Online in their browser.)</span></span>
    
2. <span data-ttu-id="987d2-123">用户打开 Word、Excel、PowerPoint 或 Visio, 并使用其工作或学校帐户登录到 Office 365 企业版。</span><span class="sxs-lookup"><span data-stu-id="987d2-123">A user opens a Word, Excel, PowerPoint, or Visio, and signs in to Office 365 Enterprise using their work or school account.</span></span> <span data-ttu-id="987d2-124">文档包含 Url。</span><span class="sxs-lookup"><span data-stu-id="987d2-124">The document contains URLs.</span></span>
    
3. <span data-ttu-id="987d2-125">当用户单击文档中的某个 URL 时, ATP 安全链接服务将检查该链接。</span><span class="sxs-lookup"><span data-stu-id="987d2-125">When the user clicks on a URL in the document, the link is checked by the ATP Safe Links service.</span></span>
    
      - <span data-ttu-id="987d2-126">如果 URL 指向的网站包含在适用于该用户的策略的[自定义 "不重写" url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)中, 则会将该用户转到该网站。</span><span class="sxs-lookup"><span data-stu-id="987d2-126">If the URL is to a website that is included in a [custom "Do not rewrite" URLs list](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md) for a policy that applies to the user, that user is taken to the website.</span></span> 
    
      - <span data-ttu-id="987d2-127">如果 URL 指向的网站包含在组织的[自定义阻止 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)中, 则会向用户提供一个[警告页面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="987d2-127">If the URL is to a website that is included in the organization's [custom blocked URLs list](set-up-a-custom-blocked-urls-list-wtih-atp.md), the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
      - <span data-ttu-id="987d2-128">如果 URL 指向已确定为恶意的网站, 则会向用户提供[警告页面](atp-safe-links-warning-pages.md)。</span><span class="sxs-lookup"><span data-stu-id="987d2-128">If the URL is to a website that has been determined to be malicious, the user is taken to a [warning page](atp-safe-links-warning-pages.md).</span></span>
    
      - <span data-ttu-id="987d2-129">如果 URL 转到可下载的文件, 并且已将[ATP 安全链接策略](set-up-atp-safe-links-policies.md)配置为扫描此类下载, 则会检查可下载的文件。</span><span class="sxs-lookup"><span data-stu-id="987d2-129">If the URL goes to a downloadable file and the [ATP Safe Links policies](set-up-atp-safe-links-policies.md) are configured to scan such downloads, the downloadable file is checked.</span></span> 
    
      - <span data-ttu-id="987d2-130">如果该 URL 被认为是安全的, 则会将用户转到该网站。</span><span class="sxs-lookup"><span data-stu-id="987d2-130">If the URL is considered safe, the user is taken to the website.</span></span>

