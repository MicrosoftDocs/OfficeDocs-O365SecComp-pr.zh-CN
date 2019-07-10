---
title: 使用 Office 365 ATP 安全链接设置自定义已阻止 Url 列表
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
description: 了解如何使用 Office 365 高级威胁防护为您的组织设置阻止的 Url 的列表。 阻止的 Url 将根据 ATP 安全链接策略应用于电子邮件和 Office 文档。
ms.openlocfilehash: e032d19c519b797936b90a94729534c73606a1a8
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598758"
---
# <a name="set-up-a-custom-blocked-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="0d19b-104">使用 Office 365 ATP 安全链接设置自定义已阻止 Url 列表</span><span class="sxs-lookup"><span data-stu-id="0d19b-104">Set up a custom blocked URLs list using Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0d19b-105">本文适用于具有[Office 365 高级威胁防护](office-365-atp.md)的商业客户。</span><span class="sxs-lookup"><span data-stu-id="0d19b-105">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="0d19b-106">如果您是在 Outlook 中查找有关安全链接的信息的家庭用户, 请参阅[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="0d19b-106">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="0d19b-107">使用[Office 365 高级威胁防护](office-365-atp.md)(ATP), 您的组织可以拥有已阻止的网站地址 (url) 的自定义列表。</span><span class="sxs-lookup"><span data-stu-id="0d19b-107">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="0d19b-108">在阻止 URL 的情况下, 单击指向被阻止 URL 的链接的用户将被带到类似于以下图像的[警告页面](atp-safe-links-warning-pages.md):</span><span class="sxs-lookup"><span data-stu-id="0d19b-108">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span> 
  
![阻止此网站](media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)
  
<span data-ttu-id="0d19b-110">"阻止的 Url" 列表由组织的 Office 365 安全团队定义, 该列表适用于组织中由 Office 365 ATP 安全链接策略涵盖的所有人。</span><span class="sxs-lookup"><span data-stu-id="0d19b-110">The blocked URLs list is defined by your organization's Office 365 security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span> 
  
<span data-ttu-id="0d19b-111">阅读本文, 了解如何为[Office 365 中的 ATP 安全链接](atp-safe-links.md)设置组织的自定义 "阻止 url" 列表。</span><span class="sxs-lookup"><span data-stu-id="0d19b-111">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>
  
## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="0d19b-112">查看或编辑阻止的 Url 的自定义列表</span><span class="sxs-lookup"><span data-stu-id="0d19b-112">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="0d19b-113">[Office 365 中的 ATP 安全链接](atp-safe-links.md)使用多个列表, 包括组织的自定义阻止 url 列表。</span><span class="sxs-lookup"><span data-stu-id="0d19b-113">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="0d19b-114">如果您具有所需的权限, 则可以设置您的组织的自定义列表。</span><span class="sxs-lookup"><span data-stu-id="0d19b-114">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="0d19b-115">为此, 请编辑组织的默认安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="0d19b-115">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="0d19b-116">若要编辑 (或定义) ATP 策略, 您必须分配下表中所述的角色之一:</span><span class="sxs-lookup"><span data-stu-id="0d19b-116">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span> 

|<span data-ttu-id="0d19b-117">Role</span><span class="sxs-lookup"><span data-stu-id="0d19b-117">Role</span></span>  |<span data-ttu-id="0d19b-118">分配的位置/方式</span><span class="sxs-lookup"><span data-stu-id="0d19b-118">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="0d19b-119">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="0d19b-119">Office 365 Global Administrator</span></span> |<span data-ttu-id="0d19b-120">默认情况下, 注册购买 Office 365 的人是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="0d19b-120">The person who signs up to buy Office 365 is a global admin by default.</span></span> <span data-ttu-id="0d19b-121">(请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。)</span><span class="sxs-lookup"><span data-stu-id="0d19b-121">(See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="0d19b-122">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="0d19b-122">Security Administrator</span></span> |<span data-ttu-id="0d19b-123">Azure Active Directory 管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="0d19b-123">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="0d19b-124">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="0d19b-124">Exchange Online Organization Management</span></span> |<span data-ttu-id="0d19b-125">Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="0d19b-125">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="0d19b-126">或</span><span class="sxs-lookup"><span data-stu-id="0d19b-126">or</span></span> <br>  <span data-ttu-id="0d19b-127">PowerShell cmdlet (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="0d19b-127">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="0d19b-128">若要了解有关角色和权限的详细信息, 请参阅[Office 365 &amp;安全合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="0d19b-128">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="0d19b-129">查看或编辑自定义阻止的 Url 列表</span><span class="sxs-lookup"><span data-stu-id="0d19b-129">To view or edit a custom blocked URLs list</span></span>
  
1. <span data-ttu-id="0d19b-130">转到[https://protection.office.com](https://protection.office.com)并使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="0d19b-130">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="0d19b-131">在左侧导航中的 "**威胁管理**" 下, 选择 "**策略** \> **安全链接**"。</span><span class="sxs-lookup"><span data-stu-id="0d19b-131">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="0d19b-132">在 "**适用于整个组织的策略**" 部分, 选择 "**默认**", 然后选择 "**编辑**" ("编辑" 按钮类似于铅笔)。</span><span class="sxs-lookup"><span data-stu-id="0d19b-132">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="0d19b-133">![单击 "编辑" 编辑安全链接保护的默认策略](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="0d19b-133">![Click Edit to edit your default policy for Safe Links protection](media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="0d19b-134">这使您可以查看已阻止 Url 的列表。</span><span class="sxs-lookup"><span data-stu-id="0d19b-134">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="0d19b-135">首先, 你可能没有在此处列出的任何 Url。</span><span class="sxs-lookup"><span data-stu-id="0d19b-135">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="0d19b-136">!["默认安全链接策略" 中的 "阻止的 Url" 列表](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="0d19b-136">![Blocked URLs list in the default Safe Links policy](media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>
  
4. <span data-ttu-id="0d19b-137">选择 "**输入一个有效的 url** " 框, 键入 URL, 然后选择加号 (**+**)。</span><span class="sxs-lookup"><span data-stu-id="0d19b-137">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span> 

5. <span data-ttu-id="0d19b-138">添加完 Url 后, 在屏幕的右下角, 选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="0d19b-138">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="0d19b-139">请注意以下几点</span><span class="sxs-lookup"><span data-stu-id="0d19b-139">A few things to keep in mind</span></span>

<span data-ttu-id="0d19b-140">将 Url 添加到列表中时, 请记住以下几点:</span><span class="sxs-lookup"><span data-stu-id="0d19b-140">While you add URLs to your list, keep the following points in mind:</span></span> 

- <span data-ttu-id="0d19b-141">不要在 URL 的末尾包含正**/** 斜杠 ()。</span><span class="sxs-lookup"><span data-stu-id="0d19b-141">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="0d19b-142">例如, 而不是`http://www.contoso.com/`输入。 `http://www.contoso.com`</span><span class="sxs-lookup"><span data-stu-id="0d19b-142">For example, instead of entering `http://www.contoso.com/`, enter `http://www.contoso.com`.</span></span>
    
- <span data-ttu-id="0d19b-143">您可以指定一个仅域的 URL (如`contoso.com`或`tailspintoys.com`)。</span><span class="sxs-lookup"><span data-stu-id="0d19b-143">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="0d19b-144">这将阻止单击包含域的任何 URL。</span><span class="sxs-lookup"><span data-stu-id="0d19b-144">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="0d19b-145">您可以在不阻止整个域`toys.contoso.com*`的情况下 (如`contoso.com`) 指定子域 (如)。</span><span class="sxs-lookup"><span data-stu-id="0d19b-145">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="0d19b-146">这将阻止单击包含子域的任何 URL, 但它不会阻止单击包含完整域的 URL。</span><span class="sxs-lookup"><span data-stu-id="0d19b-146">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>  
    
- <span data-ttu-id="0d19b-147">每个 URL 最长可包含三个\*通配符星号 ()。</span><span class="sxs-lookup"><span data-stu-id="0d19b-147">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="0d19b-148">下表列出了您可以输入的内容的一些示例, 以及这些项有何影响。</span><span class="sxs-lookup"><span data-stu-id="0d19b-148">The following table lists some examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="0d19b-149">**示例条目**</span><span class="sxs-lookup"><span data-stu-id="0d19b-149">**Example Entry**</span></span>|<span data-ttu-id="0d19b-150">**功能**</span><span class="sxs-lookup"><span data-stu-id="0d19b-150">**What It Does**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0d19b-151">`contoso.com` 或 `*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="0d19b-151">`contoso.com` or `*contoso.com*`</span></span>  <br/> |<span data-ttu-id="0d19b-152">阻止域、子域和路径, 例如`https://www.contoso.com`、和`http://sub.contoso.com``http://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="0d19b-152">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `http://sub.contoso.com`, and `http://contoso.com/abc`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="0d19b-153">阻止网站`http://contoso.com/a` , 而不是其他子路径 (如`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="0d19b-153">Blocks a site `http://contoso.com/a` but not additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="0d19b-154">阻止网站`http://contoso.com/a`和其他子路径 (如`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="0d19b-154">Blocks a site `http://contoso.com/a` and additional subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://toys.contoso.com*`  <br/> |<span data-ttu-id="0d19b-155">阻止子域 (本例中为 "玩具"), 但允许单击其他域 Url (如`http://contoso.com`或`http://home.contoso.com`)。</span><span class="sxs-lookup"><span data-stu-id="0d19b-155">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `http://contoso.com` or `http://home.contoso.com`).</span></span>  <br/> |
   

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="0d19b-156">如何为组织中的某些用户定义例外</span><span class="sxs-lookup"><span data-stu-id="0d19b-156">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="0d19b-157">如果您希望某些组能够查看其他人可能阻止的 Url, 则可以指定适用于特定收件人的 ATP 安全链接策略。</span><span class="sxs-lookup"><span data-stu-id="0d19b-157">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="0d19b-158">请参阅[设置自定义 "不重写" 使用 ATP 安全链接的 url 列表](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="0d19b-158">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
  

