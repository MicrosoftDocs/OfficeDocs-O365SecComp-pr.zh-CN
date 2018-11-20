---
title: 设置自定义阻止 Url 列表使用 Office 365 ATP 安全链接
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: 阅读此文，了解如何设置为使用 Office 365 高级威胁保护组织的阻止 Url 的列表。阻止的 Url 将适用于电子邮件和根据您 ATP 安全链接策略的 Office 文档。
ms.openlocfilehash: 1f7a991b9ab8f3a9f16616379cfb6c4c3c546260
ms.sourcegitcommit: 147768bbe44c8c98c02fa29ae9d882cee4ec2d6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/09/2018
ms.locfileid: "26238364"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="2e40f-104">设置自定义阻止 Url 列表使用 Office 365 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="2e40f-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="2e40f-p102">使用[Office 365 高级威胁保护](office-365-atp.md)(ATP)，您的组织可以自定义列表的被阻止的网站地址 (Url)。当阻止 URL 时，单击指向阻止 URL 的人员将转到[警告页](atp-safe-links-warning-pages.md)类似于下图中：</span><span class="sxs-lookup"><span data-stu-id="2e40f-p102">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![阻止此网站](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="2e40f-108">阻止的 Url 列表定义由您组织的 Office 365 安全组，并且该列表适用于 Office 365 ATP 安全链接策略覆盖组织中的每个人。</span><span class="sxs-lookup"><span data-stu-id="2e40f-108">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="2e40f-109">阅读此文，了解如何为[ATP Office 365 中的安全链接](atp-safe-links.md)设置组织的自定义阻止 Url 列表。</span><span class="sxs-lookup"><span data-stu-id="2e40f-109">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="2e40f-110">查看或编辑被阻止 Url 的自定义列表</span><span class="sxs-lookup"><span data-stu-id="2e40f-110">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="2e40f-p103">[ATP Office 365 中的安全链接](atp-safe-links.md)使用多个列表，其中包括您组织的自定义阻止的 Url 列表。如果您有必要的权限，您可以设置组织的自定义列表。通过编辑您的组织的默认安全链接策略执行此操作。</span><span class="sxs-lookup"><span data-stu-id="2e40f-p103">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>
  
1. <span data-ttu-id="2e40f-114">转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="2e40f-114">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="2e40f-115">在左侧导航窗格中，**威胁管理**下面，选择**策略** \> **安全的链接**。</span><span class="sxs-lookup"><span data-stu-id="2e40f-115">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="2e40f-116">在**应用于整个组织的策略**部分中，选择**默认**，，然后选择**编辑**（编辑按钮图像类似铅笔）。</span><span class="sxs-lookup"><span data-stu-id="2e40f-116">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span> 
    
    ![单击编辑来编辑您的安全链接保护的默认策略](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)
  
    <span data-ttu-id="2e40f-p104">这是您转查看阻止 Url 的列表。请注意，在第一个，则不会有任何列出的 Url。</span><span class="sxs-lookup"><span data-stu-id="2e40f-p104">This is where you go to view your list of blocked URLs. Note that at first, you won't have any URLs listed.</span></span>
    
    ![阻止 Url 列表是在默认适用于您的整个组织的安全链接策略。](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)
  
4. <span data-ttu-id="2e40f-p105">选择**输入一个有效的 URL**框中，然后键入一个 URL，然后选择加号 （+）。以下是几件事，需要注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="2e40f-p105">Select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+). Here are a few things to keep in mind:</span></span> 
    
  - <span data-ttu-id="2e40f-p106">您可以指定仅域 URL (如`contoso.com`或`tailspintoys.com`)。这将阻止单击任何包含域的 url。</span><span class="sxs-lookup"><span data-stu-id="2e40f-p106">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>
    
  - <span data-ttu-id="2e40f-p107">不包含正斜杠 ( **/**) URL 的末尾。例如，而输入不是`http://www.contoso.com/`，输入`http://www.contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="2e40f-p107">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
  - <span data-ttu-id="2e40f-p108">您可以包括三个通配符星号 (\*) 每个 URL。下表列出了您可以输入和什么影响这些条目的一些示例。</span><span class="sxs-lookup"><span data-stu-id="2e40f-p108">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="2e40f-129">**示例条目**</span><span class="sxs-lookup"><span data-stu-id="2e40f-129">**Example Entry**</span></span>|<span data-ttu-id="2e40f-130">**它的用途**</span><span class="sxs-lookup"><span data-stu-id="2e40f-130">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2e40f-131">`contoso.com`或`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="2e40f-131">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="2e40f-132">阻止的域、 子域和路径，如`https://www.contoso.com`， `http://sub.contoso.com`，和`http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="2e40f-132">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="2e40f-133">阻止对网站`http://contoso.com/a`，但不是其他子路径 like`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="2e40f-133">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="2e40f-134">阻止对网站`http://contoso.com/a`以及其他子路径 like`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="2e40f-134">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
5. <span data-ttu-id="2e40f-135">当您完成在屏幕的右下角中添加 Url 时，选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="2e40f-135">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="2e40f-136">如何在组织中定义的特定用户的例外</span><span class="sxs-lookup"><span data-stu-id="2e40f-136">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="2e40f-p109">如果您希望某些组能够查看其他人可能被阻止的 Url，您可以指定适用于特定收件人 ATP 安全链接策略。请参阅[设置自定义"执行不重写"Url 列表使用 ATP 安全链接](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="2e40f-p109">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

