---
title: 使用 Office 365 ATP 安全链接设置自定义不重写 url 列表
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
ms.collection: M365-security-compliance
description: 设置 ATP 安全链接策略时, 可以包括 "不重写" 的 url 列表, 以使组织中的某些人能够访问包含在列表中的网站。
ms.openlocfilehash: 7fbc7d0d0caec79dcdbb3dc5b1b5a8a4e085dc09
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30215022"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="cb644-103">使用 Office 365 ATP 安全链接设置自定义不重写 url 列表</span><span class="sxs-lookup"><span data-stu-id="cb644-103">Set up a custom do-not-rewrite URLs list using Office 365 ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cb644-p101">本文适用于商业客户。如果您是在 Outlook 中查找有关安全链接的信息的家庭用户, 请参阅[Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2)。</span><span class="sxs-lookup"><span data-stu-id="cb644-p101">This article is intended for business customers. If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.office.com/article/advanced-outlook-com-security-for-office-365-subscribers-882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="cb644-p102">使用[Office 365 高级威胁防护](office-365-atp.md)(ATP), 您的组织可以有一个[自定义的阻止 url](set-up-a-custom-blocked-urls-list-wtih-atp.md), 这样, 当用户单击电子邮件中的 web 地址 (url) 或某些 Office 文档时, 将阻止这些 url 转到这些 url。您的组织还可以为组织中的特定组提供自定义的 "不重写" 列表。"不重写" 列表使某些用户能够访问由[Office 365 中的 ATP 安全链接](atp-safe-links.md)阻止的 url。</span><span class="sxs-lookup"><span data-stu-id="cb644-p102">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-wtih-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs. Your organization can also have custom "do not rewrite" lists for specific groups in your organization. A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span> 
  
<span data-ttu-id="cb644-109">本文介绍如何指定从 ATP 安全链接扫描中排除的 url 的列表, 以及需要牢记的几个重要事项。</span><span class="sxs-lookup"><span data-stu-id="cb644-109">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="cb644-110">设置 "不重写" 列表</span><span class="sxs-lookup"><span data-stu-id="cb644-110">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="cb644-p103">ATP 安全链接保护使用多个列表, 包括组织的阻止 url 列表和 "不重写" 列表中的例外。如果您具有必要的权限, 则可以设置自定义的 "不重写" 列表。在添加或编辑适用于组织中特定收件人的安全链接策略时, 可以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="cb644-p103">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions. If you have the necessary permissions, you can set up your custom "do not rewrite" lists. You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span> 

<span data-ttu-id="cb644-114">若要编辑 (或定义) ATP 策略, 您必须分配下表中所述的角色之一:</span><span class="sxs-lookup"><span data-stu-id="cb644-114">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

|<span data-ttu-id="cb644-115">角色</span><span class="sxs-lookup"><span data-stu-id="cb644-115">Role</span></span>  |<span data-ttu-id="cb644-116">分配的位置/方式</span><span class="sxs-lookup"><span data-stu-id="cb644-116">Where/how assigned</span></span>  |
|---------|---------|
|<span data-ttu-id="cb644-117">Office 365 全局管理员</span><span class="sxs-lookup"><span data-stu-id="cb644-117">Office 365 Global Administrator</span></span> |<span data-ttu-id="cb644-p104">默认情况下, 注册购买 Office 365 的人是全局管理员。(请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。)</span><span class="sxs-lookup"><span data-stu-id="cb644-p104">The person who signs up to buy Office 365 is a global admin by default. (See [About Office 365 admin roles](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) to learn more.)</span></span>         |
|<span data-ttu-id="cb644-120">Security Administrator</span><span class="sxs-lookup"><span data-stu-id="cb644-120">Security Administrator</span></span> |<span data-ttu-id="cb644-121">Azure Active Directory 管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span><span class="sxs-lookup"><span data-stu-id="cb644-121">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="cb644-122">Exchange Online 组织管理</span><span class="sxs-lookup"><span data-stu-id="cb644-122">Exchange Online Organization Management</span></span> |<span data-ttu-id="cb644-123">Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span><span class="sxs-lookup"><span data-stu-id="cb644-123">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="cb644-124">或</span><span class="sxs-lookup"><span data-stu-id="cb644-124">or</span></span> <br>  <span data-ttu-id="cb644-125">PowerShell cmdlet (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span><span class="sxs-lookup"><span data-stu-id="cb644-125">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps))</span></span> |

> [!TIP]
> <span data-ttu-id="cb644-126">若要了解有关角色和权限的详细信息, 请参阅[Office 365 &amp;安全合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="cb644-126">To learn more about roles and permissions, see [Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-do-not-rewrite-urls-list"></a><span data-ttu-id="cb644-127">查看或编辑自定义 "不重写" url 列表</span><span class="sxs-lookup"><span data-stu-id="cb644-127">To view or edit a custom "do not rewrite" URLs list</span></span>
  
1. <span data-ttu-id="cb644-128">转到[https://protection.office.com](https://protection.office.com)并使用你的工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="cb644-128">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="cb644-129">在左侧导航中的 "**威胁管理** \> **策略** \> **安全链接**" 下。</span><span class="sxs-lookup"><span data-stu-id="cb644-129">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="cb644-p105">在 "**适用于特定收件人的策略**" 部分, 选择 "**新建**" ("新建" 按钮类似**+** 于加号 ()) 以创建新策略。(也可以编辑现有策略。)</span><span class="sxs-lookup"><span data-stu-id="cb644-p105">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy. (Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="cb644-132">![选择 "新建" 为特定的电子邮件收件人添加安全链接策略](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="cb644-132">![Choose New to add a Safe Links policy for specific email recipients](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>
  
4. <span data-ttu-id="cb644-133">为策略指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="cb644-133">Specify a name and description for your policy.</span></span>
    
5. <span data-ttu-id="cb644-134">在 "**不重写以下 url"** 部分, 选择 "**输入一个有效的 url** " 框, 然后键入 URL, 然后选择加号 (+)。</span><span class="sxs-lookup"><span data-stu-id="cb644-134">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+).</span></span> 
    
6. <span data-ttu-id="cb644-p106">在 "**应用**于" 部分中, 选择 **"收件人是其成员**", 然后选择要包括在策略中的组。选择 "**添加**", 然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="cb644-p106">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
7. <span data-ttu-id="cb644-137">添加完 url 后, 在屏幕的右下角, 选择 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="cb644-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cb644-p107">请务必查看您的组织的已阻止 url 的自定义列表。请参阅[使用 ATP 安全链接设置自定义阻止的 url 列表](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="cb644-p107">Make sure to review your organization's custom list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span> 
  
## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="cb644-140">需要牢记的要点</span><span class="sxs-lookup"><span data-stu-id="cb644-140">Important points to keep in mind</span></span>

- <span data-ttu-id="cb644-141">您在 "不重写" 列表中指定的任何 url 将从 ATP 安全链接扫描中排除, 用于您指定的收件人。</span><span class="sxs-lookup"><span data-stu-id="cb644-141">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>
 
- <span data-ttu-id="cb644-p108">当您为 ATP 安全链接策略指定 "不重写" 列表时, 可以包含最大为三个通配符星号 (\*)。对于诸如\* `contoso.com` `http://`或`https://`之类的条目, 将假定为通配符 ()。这表示条目, `contoso.com`例如类似于 "不重`*contoso.com*`写" 列表的条目。</span><span class="sxs-lookup"><span data-stu-id="cb644-p108">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcard asterisks (\*). Wildcards (\*) are assumed for entries such as `contoso.com`, which do not explicitly include prefixes or subdomains, like `http://` or `https://`. This means an entry, such as `contoso.com` is similar to `*contoso.com*` for your "do not rewrite" list.</span></span>

- <span data-ttu-id="cb644-p109">如果您在 "不重写" 列表中已经有 url 列表, 请务必查看该列表并根据需要添加通配符。例如, 如果您的现有列表中有类似`http://contoso.com/a`的条目, 并且您希望在策略`http://contoso.com/a/b`中包含类似的子路径, 请将通配符添加到您的`http://contoso.com/a*`条目, 使其看起来像这样。</span><span class="sxs-lookup"><span data-stu-id="cb644-p109">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate. For example, if your existing list has an entry like `http://contoso.com/a` and you want to include subpaths like `http://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `http://contoso.com/a*`.</span></span>
    
- <span data-ttu-id="cb644-p110">请勿在 "不重写" 列表中指定的 url 中包含正斜杠 (/)。例如, 而不是在`contoso.com/` "不重写" 列表中输入, 而`contoso.com`是输入。</span><span class="sxs-lookup"><span data-stu-id="cb644-p110">Do not include a forward slash (/) in the URLs that you specify in your "do not rewrite" list. For example, rather than enter `contoso.com/` in your "do not rewrite" list, enter `contoso.com`.</span></span>
    
<span data-ttu-id="cb644-149">下表列出了可以输入的内容的示例以及这些项有何影响。</span><span class="sxs-lookup"><span data-stu-id="cb644-149">The following table lists examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="cb644-150">**示例条目**</span><span class="sxs-lookup"><span data-stu-id="cb644-150">**Example Entry**</span></span>|<span data-ttu-id="cb644-151">**功能**</span><span class="sxs-lookup"><span data-stu-id="cb644-151">**What It Does**</span></span>|
|:-----|:-----|
|`*contoso.com*`  <br/> |<span data-ttu-id="cb644-152">允许特定收件人访问域、子域和路径, 例如`http://www.contoso.com`、 `https://www.contoso.com` `https://maps.contoso.com`、或`http://www.contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="cb644-152">Allows specific recipients to visit a domain, subdomains, and paths, such as `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `http://www.contoso.com/a`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="cb644-153">允许特定收件人访问类似`http://contoso.com/a`的网站, 但不允许像这样的子路径`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="cb644-153">Allows specific recipients to visit a site like `http://contoso.com/a`, but not subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="cb644-154">允许特定收件人访问像这样的子`http://contoso.com/a`网站之类的子网站`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="cb644-154">Allows specific recipients to visit a site like `http://contoso.com/a` and subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
 