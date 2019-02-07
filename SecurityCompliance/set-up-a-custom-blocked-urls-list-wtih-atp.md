---
title: 设置自定义阻止 Url 列表使用 Office 365 ATP 安全链接
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
description: 了解如何设置为使用 Office 365 高级威胁保护组织的阻止 Url 的列表。阻止的 Url 将适用于电子邮件和根据您 ATP 安全链接策略的 Office 文档。
ms.openlocfilehash: 4d8c9c669310137d3f491f5a79c93f4d6af71ac5
ms.sourcegitcommit: d6a28c4f6db6a676ca960173e8ff8f17d4aa1c4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29755313"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="c0532-104">设置自定义阻止 Url 列表使用 Office 365 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="c0532-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="c0532-p102">使用[Office 365 高级威胁保护](office-365-atp.md)(ATP)，您的组织可以自定义列表的被阻止的网站地址 (Url)。当阻止 URL 时，单击指向阻止 URL 的人员将转到[警告页](atp-safe-links-warning-pages.md)类似于下图中：</span><span class="sxs-lookup"><span data-stu-id="c0532-p102">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked. When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![阻止此网站](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="c0532-108">阻止的 Url 列表定义由您组织的 Office 365 安全组，并且该列表适用于 Office 365 ATP 安全链接策略覆盖组织中的每个人。</span><span class="sxs-lookup"><span data-stu-id="c0532-108">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="c0532-109">阅读此文，了解如何为[ATP Office 365 中的安全链接](atp-safe-links.md)设置组织的自定义阻止 Url 列表。</span><span class="sxs-lookup"><span data-stu-id="c0532-109">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="c0532-110">查看或编辑被阻止 Url 的自定义列表</span><span class="sxs-lookup"><span data-stu-id="c0532-110">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="c0532-p103">[ATP Office 365 中的安全链接](atp-safe-links.md)使用多个列表，其中包括您组织的自定义阻止的 Url 列表。如果您有必要的权限，您可以设置组织的自定义列表。通过编辑您的组织的默认安全链接策略执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c0532-p103">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list. If you have the necessary permissions, you can set up your organization's custom list. You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="c0532-114">若要编辑 （或定义） ATP 策略，您必须为分配下表中所述的角色之一：</span><span class="sxs-lookup"><span data-stu-id="c0532-114">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="c0532-115">角色</span><span class="sxs-lookup"><span data-stu-id="c0532-115">Role</span></span>  |<span data-ttu-id="c0532-116">其中/如何分配</span><span class="sxs-lookup"><span data-stu-id="c0532-116">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="c0532-117">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="c0532-117">Office 365 Global Administrator</span></span> |<span data-ttu-id="c0532-p104">注册以购买 Office 365 的人是默认情况下是全局管理员。（请参阅要了解的[有关 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)）。</span><span class="sxs-lookup"><span data-stu-id="c0532-p104">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="c0532-120">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="c0532-120">Security Administrator</span></span> |<span data-ttu-id="c0532-121">Azure Active Directory 管理员中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="c0532-121">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="c0532-122">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="c0532-122">Exchange Online Organization Management</span></span> |<span data-ttu-id="c0532-123">Exchange 管理员中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="c0532-123">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="c0532-124">或</span><span class="sxs-lookup"><span data-stu-id="c0532-124">or</span></span> <br>  <span data-ttu-id="c0532-125">PowerShell cmdlet (请参阅[Exchange Online PowerShell 中](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="c0532-125">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="c0532-126">若要了解有关角色和权限的详细信息，请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="c0532-126">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="c0532-127">若要查看或编辑自定义阻止的 Url 列表</span><span class="sxs-lookup"><span data-stu-id="c0532-127">To view or edit a custom blocked URLs list</span></span>
  
1. <span data-ttu-id="c0532-128">转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c0532-128">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="c0532-129">在左侧导航窗格中，**威胁管理**下面，选择**策略** \> **安全的链接**。</span><span class="sxs-lookup"><span data-stu-id="c0532-129">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="c0532-130">在**应用于整个组织的策略**部分中，选择**默认**，，然后选择**编辑**（编辑按钮图像类似铅笔）。</span><span class="sxs-lookup"><span data-stu-id="c0532-130">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="c0532-131">![单击编辑来编辑您的安全链接保护的默认策略](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="c0532-131">![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="c0532-p105">这样，您可以查看您阻止 Url 的列表。首先，您可能没有任何此处列出的 Url。</span><span class="sxs-lookup"><span data-stu-id="c0532-p105">This enables you to view your list of blocked URLs. At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="c0532-134">![阻止默认的安全链接策略中的 Url 列表](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="c0532-134">![Blocked URLs list in the default Safe Links policy](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="c0532-135">选择**输入一个有效的 URL**框中，键入 URL，然后选择加号 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="c0532-135">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="c0532-136">当您完成在屏幕的右下角中添加 Url 时，选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="c0532-136">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="c0532-137">要记住的几件事</span><span class="sxs-lookup"><span data-stu-id="c0532-137">A few things to keep in mind</span></span>

<span data-ttu-id="c0532-138">时向列表添加 Url，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="c0532-138">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="c0532-p106">不包含正斜杠 ( **/**) URL 的末尾。例如，而输入不是`http://www.contoso.com/`，输入`http://www.contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="c0532-p106">Do not include a forward slash ( **/**) at the end of the URL. For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
- <span data-ttu-id="c0532-p107">您可以指定仅域 URL (如`contoso.com`或`tailspintoys.com`)。这将阻止单击任何包含域的 url。</span><span class="sxs-lookup"><span data-stu-id="c0532-p107">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`). This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="c0532-p108">您可以指定子域 (如`toys.contoso.com*`) 不阻止完整的域 (如`contoso.com`)。这将阻止单击任何 URL 包含子域，但不会阻止单击到包含完整的域的 URL。</span><span class="sxs-lookup"><span data-stu-id="c0532-p108">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`). This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="c0532-p109">您可以包括三个通配符星号 (\*) 每个 URL。下表列出了您可以输入和什么影响这些条目的一些示例。</span><span class="sxs-lookup"><span data-stu-id="c0532-p109">You can include up to three wildcard asterisks (\*) per URL. The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="c0532-147">**示例条目**</span><span class="sxs-lookup"><span data-stu-id="c0532-147">**Example Entry**</span></span>|<span data-ttu-id="c0532-148">**它的用途**</span><span class="sxs-lookup"><span data-stu-id="c0532-148">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0532-149">`contoso.com`或`*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="c0532-149">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="c0532-150">阻止的域、 子域和路径，如`https://www.contoso.com`， `http://sub.contoso.com`，和`http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="c0532-150">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="c0532-151">阻止对网站`http://contoso.com/a`，但不是其他子路径 like`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="c0532-151">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="c0532-152">阻止对网站`http://contoso.com/a`以及其他子路径 like`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="c0532-152">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://toys.contoso.com*`  <br/> |<span data-ttu-id="c0532-153">一个子域 （在本例中的"玩具"） 的块但允许单击到其他域 Url (如`http://contoso.com`或`http://home.contoso.com`)。</span><span class="sxs-lookup"><span data-stu-id="c0532-153">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `http://contoso.com` or `http://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="c0532-154">如何在组织中定义的特定用户的例外</span><span class="sxs-lookup"><span data-stu-id="c0532-154">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="c0532-p110">如果您希望某些组能够查看其他人可能被阻止的 Url，您可以指定适用于特定收件人 ATP 安全链接策略。请参阅[设置自定义"执行不重写"Url 列表使用 ATP 安全链接](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="c0532-p110">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients. See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

