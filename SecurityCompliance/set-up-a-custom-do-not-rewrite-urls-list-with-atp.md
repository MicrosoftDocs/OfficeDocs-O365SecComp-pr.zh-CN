---
title: 设置自定义重写不执行操作的 Url 列表使用 Office 365 ATP 安全链接
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
ms.assetid: 35dbfd99-da5a-422b-9b0e-c6caf3b645fa
description: 当您设置了您 ATP 的安全链接策略时，可以包括 do not 写以使您的组织中的某些用户访问列表中包括的网站的 Url 的列表。
ms.openlocfilehash: d3883d6aff29b9a061b62e4854e7aad52656769f
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2019
ms.locfileid: "28015044"
---
# <a name="set-up-a-custom-do-not-rewrite-urls-list-using-office-365-atp-safe-links"></a><span data-ttu-id="74277-103">设置自定义重写不执行操作的 Url 列表使用 Office 365 ATP 安全链接</span><span class="sxs-lookup"><span data-stu-id="74277-103">Set up a custom do-not-rewrite URLs list using Office 365 ATP Safe Links</span></span>

<span data-ttu-id="74277-p101">[Office 365 高级威胁保护](office-365-atp.md)(ATP)，您的组织可以[自定义被阻止的 Url](set-up-a-custom-blocked-urls-list-wtih-atp.md)，以便当人员单击 web 地址 (Url) 中的电子邮件或某些 Office 文档，他们无法转到这些 Url。您的组织也可以在组织中有特定的组的自定义"执行不重写"列表。"执行不重写"列表使一些人访问否则阻止通过[ATP Office 365 中的安全链接](atp-safe-links.md)的 Url。</span><span class="sxs-lookup"><span data-stu-id="74277-p101">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a [custom blocked URLs](set-up-a-custom-blocked-urls-list-wtih-atp.md), such that when people click on web addresses (URLs) in email messages or certain Office documents, they are prevented from going to those URLs. Your organization can also have custom "do not rewrite" lists for specific groups in your organization. A "do not rewrite" list enables some people to visit URLs that are otherwise blocked by [ATP Safe Links in Office 365](atp-safe-links.md).</span></span> 
  
<span data-ttu-id="74277-107">本文介绍如何指定将排除在扫描 ATP 安全链接和一些重要事项，需要注意以下事项的 Url 的列表。</span><span class="sxs-lookup"><span data-stu-id="74277-107">This article describes how to specify a list of URLs that are excluded from ATP Safe Links scanning, and a few important points to keep in mind.</span></span>

## <a name="set-up-a-do-not-rewrite-list"></a><span data-ttu-id="74277-108">设置"执行不重写"列表</span><span class="sxs-lookup"><span data-stu-id="74277-108">Set up a "do not rewrite" list</span></span>

<span data-ttu-id="74277-p102">ATP 安全链接保护使用多个列表，其中包括贵组织的阻止的 Url 列表和"执行不重写"的例外列表。如果您有必要的权限，您可以设置自定义"执行不重写"列表。添加或编辑将应用于特定收件人在组织中的安全链接策略时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="74277-p102">ATP Safe Links protection uses several lists, including your organization's blocked URLs list and the "do not rewrite" lists for exceptions. If you have the necessary permissions, you can set up your custom "do not rewrite" lists. You do this when you add or edit Safe Links policies that apply to specific recipients in your organization.</span></span> 
  
1. <span data-ttu-id="74277-112">转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="74277-112">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span> 
    
2. <span data-ttu-id="74277-113">在左侧导航窗格中，在**威胁管理**下\>**策略** \> **安全的链接**。</span><span class="sxs-lookup"><span data-stu-id="74277-113">In the left navigation, under **Threat management** \> **Policy** \> **Safe Links**.</span></span>
    
3. <span data-ttu-id="74277-p103">在**的可以应用到特定收件人的策略**部分中，选择**新建**(新建按钮图像类似一个加号 ( **+**)) 创建新策略。（或者，您可以编辑现有的策略。）</span><span class="sxs-lookup"><span data-stu-id="74277-p103">In the **Policies that apply to specific recipients** section, choose **New** (the New button resembles a plus sign ( **+**)) to create a new policy. (Alternatively, you can edit an existing policy.)</span></span><br/><span data-ttu-id="74277-116">![选择新建以添加特定的电子邮件收件人的安全链接策略](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span><span class="sxs-lookup"><span data-stu-id="74277-116">![Choose New to add a Safe Links policy for specific email recipients](media/01073f42-3cec-4ddb-8c10-4d33ec434676.png)</span></span>
  
4. <span data-ttu-id="74277-117">指定的名称和说明您的策略。</span><span class="sxs-lookup"><span data-stu-id="74277-117">Specify a name and description for your policy.</span></span>
    
5. <span data-ttu-id="74277-118">在**不重写以下 Url**部分中，选择**输入一个有效的 URL**框中，然后键入一个 URL，，然后选择加号 （+）。</span><span class="sxs-lookup"><span data-stu-id="74277-118">In the **Do not rewrite the following URLs** section, select the **Enter a valid URL** box, and then type a URL, and then choose the plus sign (+).</span></span> 
    
6. <span data-ttu-id="74277-p104">在**应用于**部分中，选择**收件人是的成员**，，然后选择您想要包括在您的策略的组。选择**添加**，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="74277-p104">In the **Applied To** section, choose **The recipient is a member of**, and then choose the group(s) you want to include in your policy. Choose **Add**, and then choose **OK**.</span></span>
    
7. <span data-ttu-id="74277-121">当您完成在屏幕的右下角中添加 Url 时，选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="74277-121">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="74277-p105">请务必查看贵组织的自定义阻止 Url 的列表。请参阅[设置自定义阻止 Url 列表使用 ATP 安全链接](set-up-a-custom-blocked-urls-list-wtih-atp.md)。</span><span class="sxs-lookup"><span data-stu-id="74277-p105">Make sure to review your organization's custom list of blocked URLs. See [Set up a custom blocked URLs list using ATP Safe Links](set-up-a-custom-blocked-urls-list-wtih-atp.md).</span></span> 
  
## <a name="important-points-to-keep-in-mind"></a><span data-ttu-id="74277-124">需要牢记的重要因素</span><span class="sxs-lookup"><span data-stu-id="74277-124">Important points to keep in mind</span></span>

- <span data-ttu-id="74277-125">从 ATP 安全链接您指定的收件人扫描中排除"执行不重写"列表中指定的任何 Url。</span><span class="sxs-lookup"><span data-stu-id="74277-125">Any URLs that you specify in the "do not rewrite" list are excluded from ATP Safe Links scanning for the recipients that you specify.</span></span>
 
- <span data-ttu-id="74277-p106">当您指定的 ATP 安全链接策略的"执行不重写"列表时，可以包括三个通配符星号 (\*)。通配符 (\*) 如假定条目`contoso.com`，其中不显式包括前缀或子域，如`http://`或`https://`。这意味着条目，如`contoso.com`类似于`*contoso.com*`"执行不重写"列表。</span><span class="sxs-lookup"><span data-stu-id="74277-p106">When you specify a "do not rewrite" list for an ATP Safe Links policy, you can include up to three wildcard asterisks (\*). Wildcards (\*) are assumed for entries such as `contoso.com`, which do not explicitly include prefixes or subdomains, like `http://` or `https://`. This means an entry, such as `contoso.com` is similar to `*contoso.com*` for your "do not rewrite" list.</span></span>

- <span data-ttu-id="74277-p107">如果您已有"执行不重写"列表中的 Url 的列表，请务必查看该列表并根据需要添加通配符。例如，如果您现有列表条目，如`http://contoso.com/a`并且想要包括类似的子路径`http://contoso.com/a/b`在您的策略，将通配符添加到您的项，使其类似`http://contoso.com/a*`。</span><span class="sxs-lookup"><span data-stu-id="74277-p107">If you already have a list of URLs in your "do not rewrite" list, make sure to review that list and add wildcards as appropriate. For example, if your existing list has an entry like `http://contoso.com/a` and you want to include subpaths like `http://contoso.com/a/b` in your policy, add a wildcard to your entry so it looks like `http://contoso.com/a*`.</span></span>
    
- <span data-ttu-id="74277-p108">在"执行不重写"列表中指定的 Url 中不包括斜线 （/）。例如，而不是输入`contoso.com/`在"执行不重写"列表中，输入`contoso.com`。</span><span class="sxs-lookup"><span data-stu-id="74277-p108">Do not include a forward slash (/) in the URLs that you specify in your "do not rewrite" list. For example, rather than enter `contoso.com/` in your "do not rewrite" list, enter `contoso.com`.</span></span>
    
<span data-ttu-id="74277-133">您可以输入和什么影响这些条目的以下表列表示例具有。</span><span class="sxs-lookup"><span data-stu-id="74277-133">The following table lists examples of what you can enter and what effect those entries have.</span></span>
    
|<span data-ttu-id="74277-134">**示例条目**</span><span class="sxs-lookup"><span data-stu-id="74277-134">**Example Entry**</span></span>|<span data-ttu-id="74277-135">**它的用途**</span><span class="sxs-lookup"><span data-stu-id="74277-135">**What It Does**</span></span>|
|:-----|:-----|
|`*contoso.com*`  <br/> |<span data-ttu-id="74277-136">允许特定收件人访问域、 子域和路径，如`http://www.contoso.com`， `https://www.contoso.com`， `https://maps.contoso.com`，或`http://www.contoso.com/a`</span><span class="sxs-lookup"><span data-stu-id="74277-136">Allows specific recipients to visit a domain, subdomains, and paths, such as `http://www.contoso.com`, `https://www.contoso.com`, `https://maps.contoso.com`, or `http://www.contoso.com/a`</span></span>  <br/> |
|`http://contoso.com/a`  <br/> |<span data-ttu-id="74277-137">允许特定收件人访问的站点，如`http://contoso.com/a`，但不是子路径 like`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="74277-137">Allows specific recipients to visit a site like `http://contoso.com/a`, but not subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
|`http://contoso.com/a*`  <br/> |<span data-ttu-id="74277-138">允许特定收件人访问的站点，如`http://contoso.com/a`以及 like 子路径`http://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="74277-138">Allows specific recipients to visit a site like `http://contoso.com/a` and subpaths like `http://contoso.com/a/b`</span></span>  <br/> |
   
 