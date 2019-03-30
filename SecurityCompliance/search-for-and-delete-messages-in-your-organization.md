---
title: 在 Office 365 组织中搜索和删除电子邮件-管理员帮助
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 使用 Office 365 的 Security & 合规性中心中的 "搜索和清除" 功能搜索和删除组织中所有邮箱的电子邮件。
ms.openlocfilehash: c6fa0d09852016b918375dbff5a19468886d86b3
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000265"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a><span data-ttu-id="d5656-103">在 Office 365 组织中搜索和删除电子邮件-管理员帮助</span><span class="sxs-lookup"><span data-stu-id="d5656-103">Search for and delete email messages in your Office 365 organization - Admin Help</span></span>

<span data-ttu-id="d5656-104">**本文适用于管理员。您是否正在尝试查找您要删除的邮箱中的项目？请参阅[使用即时搜索查找邮件或项目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|</span><span class="sxs-lookup"><span data-stu-id="d5656-104">**This article is for administrators. Are you trying to find items in your mailbox that you want to delete? See [Find a message or item with Instant Search](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|</span></span>
   
<span data-ttu-id="d5656-105">您可以使用 Office 365 中的内容搜索功能搜索和删除组织中所有邮箱的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d5656-105">You can use the Content Search feature in Office 365 to search for and delete an email message from all mailboxes in your organization.</span></span> <span data-ttu-id="d5656-106">这可以帮助您查找并删除可能有害的或存在高风险的电子邮件，如：</span><span class="sxs-lookup"><span data-stu-id="d5656-106">This can help you find and remove potentially harmful or high-risk email, such as:</span></span>
  
- <span data-ttu-id="d5656-107">包含危险附件或病毒的邮件</span><span class="sxs-lookup"><span data-stu-id="d5656-107">Messages that contain dangerous attachments or viruses</span></span>
    
- <span data-ttu-id="d5656-108">网络仿冒邮件</span><span class="sxs-lookup"><span data-stu-id="d5656-108">Phishing messages</span></span>
    
- <span data-ttu-id="d5656-109">包含敏感数据的邮件</span><span class="sxs-lookup"><span data-stu-id="d5656-109">Messages that contain sensitive data</span></span>
    
> [!CAUTION]
> <span data-ttu-id="d5656-110">搜索和清除是一项强大的功能, 允许分配有必要权限的任何人从组织中的邮箱中删除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d5656-110">Search and purge is a powerful feature that allows anyone that is assigned the necessary permissions to delete email messages from mailboxes in your organization.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="d5656-111">开始之前</span><span class="sxs-lookup"><span data-stu-id="d5656-111">Before you begin</span></span>

- <span data-ttu-id="d5656-112">若要创建和运行内容搜索, 您必须是**电子数据展示管理器**角色组的成员, 或分配有**合规性搜索**管理角色。</span><span class="sxs-lookup"><span data-stu-id="d5656-112">To create and run a Content Search, you have to be a member of the **eDiscovery Manager** role group or be assigned the **Compliance Search** management role.</span></span> <span data-ttu-id="d5656-113">若要删除邮件, 您必须是 "**组织管理**" 角色组的成员, 或者分配有 "**搜索和清除**" 管理角色。</span><span class="sxs-lookup"><span data-stu-id="d5656-113">To delete messages, you have to be a member of the **Organization Management** role group or be assigned the **Search And Purge** management role.</span></span> <span data-ttu-id="d5656-114">有关向角色组添加用户的信息, 请参阅[向用户授予对安全与合规中心的访问权限](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="d5656-114">For information about adding users to a role group, see [Give users access to the security and compliance center](grant-access-to-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="d5656-115">您必须使用 Security & 合规性中心 PowerShell 删除邮件。</span><span class="sxs-lookup"><span data-stu-id="d5656-115">You have to use Security & Compliance Center PowerShell to delete messages.</span></span> <span data-ttu-id="d5656-116">有关如何连接的说明, 请参阅[步骤 2](#step-2-connect-to-security--compliance-center-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="d5656-116">See [Step 2](#step-2-connect-to-security--compliance-center-powershell) for instructions about how to connect.</span></span>
    
- <span data-ttu-id="d5656-117">每个邮箱最多可以一次删除10个项目。</span><span class="sxs-lookup"><span data-stu-id="d5656-117">A maximum of 10 items per mailbox can be removed at one time.</span></span> <span data-ttu-id="d5656-118">因为搜索和删除邮件的功能旨在作为事件响应工具, 所以此限制有助于确保快速从邮箱中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="d5656-118">Because the capability to search for and remove messages is intended to be an incident-response tool, this limit helps ensure that messages are quickly removed from mailboxes.</span></span> <span data-ttu-id="d5656-119">此功能并不是为了清理用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="d5656-119">This feature isn't intended to clean up user mailboxes.</span></span> <span data-ttu-id="d5656-120">若要删除10个以上的项目, 您可以使用 Exchange Online PowerShell 中的**搜索-邮箱-DeleteContent**命令。</span><span class="sxs-lookup"><span data-stu-id="d5656-120">To delete more than 10 items, you can use the **Search-Mailbox -DeleteContent** command in Exchange Online PowerShell.</span></span> <span data-ttu-id="d5656-121">请参阅[搜索和删除邮件-管理员帮助](search-for-and-delete-messagesadmin-help.md)。</span><span class="sxs-lookup"><span data-stu-id="d5656-121">See [Search for and delete messages - Admin help](search-for-and-delete-messagesadmin-help.md).</span></span>
    
- <span data-ttu-id="d5656-122">通过执行搜索和清除操作, 可以在内容搜索中删除项目的最大邮箱数为50000。</span><span class="sxs-lookup"><span data-stu-id="d5656-122">The maximum number of mailboxes in a Content Search that you can delete items in by doing a search and purge action is 50,000.</span></span> <span data-ttu-id="d5656-123">如果在[第1步](#step-1-create-a-content-search-to-find-the-message-to-delete)中创建的内容搜索的源邮箱多于50000个, 则清除操作 (在步骤3中创建) 将会失败。</span><span class="sxs-lookup"><span data-stu-id="d5656-123">If the Content Search (that you create in [Step 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) has more than 50,000 source mailboxes, the purge action (that you create in Step 3) will fail.</span></span> <span data-ttu-id="d5656-124">有关在50000以上邮箱上执行搜索和清除操作的提示, 请参阅[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="d5656-124">See the [More information](#more-information) section for a tip on performing a search and purge operation on more than 50,000 mailboxes.</span></span> 
    
- <span data-ttu-id="d5656-125">本文中的过程仅可用于删除 Exchange Online 邮箱和公用文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="d5656-125">The procedure in this article can only be used to delete items in Exchange Online mailboxes and public folders.</span></span> <span data-ttu-id="d5656-126">您不能使用它从 SharePoint 或 OneDrive for business 网站中删除内容。</span><span class="sxs-lookup"><span data-stu-id="d5656-126">You can't use it to delete content from SharePoint or OneDrive for Business sites.</span></span>
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a><span data-ttu-id="d5656-127">步骤 1：创建内容搜索来查找要删除的邮件</span><span class="sxs-lookup"><span data-stu-id="d5656-127">Step 1: Create a Content Search to find the message to delete</span></span>

<span data-ttu-id="d5656-128">第一步是创建并运行内容搜索以查找您想要从组织的邮箱中删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="d5656-128">The first step is to create and run a Content Search to find the message that you want to remove from mailboxes in your organization.</span></span> <span data-ttu-id="d5656-129">您可以使用 Security & 合规性中心或通过运行**new-compliancesearch**和**new-compliancesearch** cmdlet 来创建搜索。</span><span class="sxs-lookup"><span data-stu-id="d5656-129">You can create the search by using the Security & Compliance Center or by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets.</span></span> <span data-ttu-id="d5656-130">通过在[步骤 3](#step-3-delete-the-message)中运行**new-compliancesearchaction-清除**命令, 与此搜索的查询相匹配的邮件将被删除。</span><span class="sxs-lookup"><span data-stu-id="d5656-130">The messages that match the query for this search will be deleted by running the **New-ComplianceSearchAction -Purge** command in [Step 3](#step-3-delete-the-message).</span></span> <span data-ttu-id="d5656-131">有关创建内容搜索和配置搜索查询的信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="d5656-131">For information about creating a Content Search and configuring search queries, see the following topics:</span></span> 
  
- [<span data-ttu-id="d5656-132">Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="d5656-132">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="d5656-133">内容搜索的关键字查询</span><span class="sxs-lookup"><span data-stu-id="d5656-133">Keyword queries for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="d5656-134">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="d5656-134">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [<span data-ttu-id="d5656-135">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="d5656-135">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> <span data-ttu-id="d5656-136">在此步骤中创建的内容搜索中搜索的内容位置不能包含 SharePoint 或 OneDrive for business 网站。</span><span class="sxs-lookup"><span data-stu-id="d5656-136">The content locations that are searched in the Content Search that you create in this step can't include SharePoint or OneDrive for Business sites.</span></span> <span data-ttu-id="d5656-137">只能在将用于电子邮件的内容搜索中包含邮箱和公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="d5656-137">You can include only mailboxes and public folders in a Content Search that will be used to email messages.</span></span> <span data-ttu-id="d5656-138">如果内容搜索包括网站, 则在运行**new-compliancesearchaction** cmdlet 时, 您将在步骤3中收到错误。</span><span class="sxs-lookup"><span data-stu-id="d5656-138">If the Content Search includes sites, you'll receive an error in Step 3 when you run the **New-ComplianceSearchAction** cmdlet.</span></span> 
  
### <a name="tips-for-finding-messages-to-remove"></a><span data-ttu-id="d5656-139">查找要删除的邮件的提示</span><span class="sxs-lookup"><span data-stu-id="d5656-139">Tips for finding messages to remove</span></span>

<span data-ttu-id="d5656-p109">搜索查询的目标是将搜索结果的范围缩小到仅包含您想要删除的邮件。以下是一些提示：</span><span class="sxs-lookup"><span data-stu-id="d5656-p109">The goal of the search query is to narrow the results of the search to only the message or messages that you want to remove. Here are some tips:</span></span>
  
- <span data-ttu-id="d5656-142">如果您知道邮件的主题行中使用的确切文本或短语, 请在搜索查询中使用**subject**属性。</span><span class="sxs-lookup"><span data-stu-id="d5656-142">If you know the exact text or phrase used in the subject line of the message, use the **Subject** property in the search query.</span></span> 
    
- <span data-ttu-id="d5656-143">如果您知道邮件的确切日期（或日期范围），请在搜索查询中包括 **Received** 属性。</span><span class="sxs-lookup"><span data-stu-id="d5656-143">If you know that exact date (or date range) of the message, include the **Received** property in the search query.</span></span> 
    
- <span data-ttu-id="d5656-144">如果您知道邮件的发件人，请在搜索查询中包括 **From** 属性。</span><span class="sxs-lookup"><span data-stu-id="d5656-144">If you know who sent the message, include the **From** property in the search query.</span></span> 
    
- <span data-ttu-id="d5656-145">预览搜索结果以验证搜索是否仅返回您想要删除的一个或一封邮件。</span><span class="sxs-lookup"><span data-stu-id="d5656-145">Preview the search results to verify that the search returned only the message (or messages) that you want to delete.</span></span>
    
- <span data-ttu-id="d5656-146">使用搜索估计统计信息 (显示在 Security & 合规性中心中的搜索的细节窗格中或通过使用[new-compliancesearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) 来获取总结果数。</span><span class="sxs-lookup"><span data-stu-id="d5656-146">Use the search estimate statistics (displayed in the details pane of the search in the Security & Compliance Center or by using the [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) to get a count of the total number of results.</span></span> 
    
<span data-ttu-id="d5656-147">以下是查找可疑电子邮件的两个查询示例。</span><span class="sxs-lookup"><span data-stu-id="d5656-147">Here are two examples of queries to find suspicious email messages.</span></span>
  
- <span data-ttu-id="d5656-148">此查询返回用户在 2016 年 4 月 13 日至 2016 年 4 月 14 日之间收到的邮件，而且包含主题行中的单词“操作”和“必需”。</span><span class="sxs-lookup"><span data-stu-id="d5656-148">This query returns messages that were received by users between April 13, 2016 and April 14, 2016 and that contain the words "action" and "required" in the subject line.</span></span>
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- <span data-ttu-id="d5656-149">此查询返回由 chatsuwloginsset12345@outlook.com 发送的邮件，而且包含主题行中的完全匹配的短语“更新您的帐户信息”。</span><span class="sxs-lookup"><span data-stu-id="d5656-149">This query returns messages that were sent by chatsuwloginsset12345@outlook.com and that contain the exact phrase "Update your account information" in the subject line.</span></span>
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="d5656-150">步骤 2: 连接到安全 & 合规中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5656-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="d5656-151">下一步是连接到组织的安全 & 合规中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d5656-151">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="d5656-152">有关分步说明, 请参阅[连接到 Security & 合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d5656-152">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="d5656-153">如果您的 Office 365 帐户使用多重身份验证 (MFA) 或联合身份验证, 则不能使用上一主题中有关连接到安全 & 合规中心 PowerShell 的说明。</span><span class="sxs-lookup"><span data-stu-id="d5656-153">If your Office 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="d5656-154">请参阅主题[使用多重身份验证连接到安全 & 合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)中的说明。</span><span class="sxs-lookup"><span data-stu-id="d5656-154">Instead, see the instructions in the topic [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>
  
## <a name="step-3-delete-the-message"></a><span data-ttu-id="d5656-155">步骤 3: 删除邮件</span><span class="sxs-lookup"><span data-stu-id="d5656-155">Step 3: Delete the message</span></span>

<span data-ttu-id="d5656-156">创建并优化内容搜索后, 若要返回要删除并连接到安全 & 合规中心 PowerShell 的邮件, 最后一步是运行**new-compliancesearchaction** cmdlet 以删除该邮件。</span><span class="sxs-lookup"><span data-stu-id="d5656-156">After you've created and refined a Content Search to return the message that you want to remove and are connected to Security & Compliance Center PowerShell, the final step is to run the **New-ComplianceSearchAction** cmdlet to delete the message.</span></span> <span data-ttu-id="d5656-157">您可以软或硬删除邮件。</span><span class="sxs-lookup"><span data-stu-id="d5656-157">You can soft- or hard-delete the message.</span></span> <span data-ttu-id="d5656-158">软删除的邮件将移至用户的 "可恢复的项目" 文件夹并保留, 直到已删除项目的保留期过期。</span><span class="sxs-lookup"><span data-stu-id="d5656-158">A soft-deleted message is moved to a user's Recoverable Items folder and retained until the deleted item retention period expires.</span></span> <span data-ttu-id="d5656-159">硬删除的邮件被标记为从邮箱永久删除, 并且在下次邮箱由托管文件夹助理处理时将被永久删除。</span><span class="sxs-lookup"><span data-stu-id="d5656-159">Hard-deleted messages are marked for permanent removal from the mailbox and will be permanently removed the next time the mailbox is processed by the Managed Folder Assistant.</span></span> <span data-ttu-id="d5656-160">如果为邮箱启用了单个项目恢复, 则删除的项目保留期过期后, 将永久删除硬删除的项目。</span><span class="sxs-lookup"><span data-stu-id="d5656-160">If single item recovery is enabled for the mailbox, hard-deleted items will be permanently removed after the deleted item retention period expires.</span></span> <span data-ttu-id="d5656-161">如果将邮箱置于保留状态, 则会保留已删除邮件, 直到项目的保留期过期或从邮箱中删除保留期间为止。</span><span class="sxs-lookup"><span data-stu-id="d5656-161">If a mailbox is placed on hold, deleted messages are preserved until the hold duration for the item expires or until the hold is removed from the mailbox.</span></span>
  
<span data-ttu-id="d5656-162">在下面的示例中, 该命令将软删除名为 "删除仿冒邮件" 的内容搜索返回的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="d5656-162">In the following example, the command will soft-delete the search results returned by a Content Search named "Remove Phishing Message".</span></span> 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

<span data-ttu-id="d5656-163">若要硬删除 "删除仿冒邮件" 内容搜索返回的项目, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="d5656-163">To hard-deleted the items returned by the  "Remove Phishing Message" content search, you would run this command:</span></span>

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

<span data-ttu-id="d5656-164">请注意, 在运行以前的命令以软删除或硬删除邮件时, 由*SearchName*参数指定的搜索是您在步骤1中创建的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="d5656-164">Note that when you run the previous command to soft- or hard-delete messages, the search specified by the  *SearchName*  parameter is the Content Search that you created in Step 1.</span></span> 
  
<span data-ttu-id="d5656-165">有关详细信息, 请参阅[new-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)。</span><span class="sxs-lookup"><span data-stu-id="d5656-165">For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).</span></span>

## <a name="more-information"></a><span data-ttu-id="d5656-166">更多信息</span><span class="sxs-lookup"><span data-stu-id="d5656-166">More information</span></span>

- <span data-ttu-id="d5656-167">**如何获取搜索和删除操作的状态？**</span><span class="sxs-lookup"><span data-stu-id="d5656-167">**How do you get status on the search and remove operation?**</span></span>

    <span data-ttu-id="d5656-168">运行 **Get-ComplianceSearchAction** 获取有关删除操作的状态。</span><span class="sxs-lookup"><span data-stu-id="d5656-168">Run the **Get-ComplianceSearchAction** to get the status on the delete operation.</span></span> <span data-ttu-id="d5656-169">请注意, 在运行**new-compliancesearchaction** cmdlet 时创建的对象是使用以下格式命名的: `<name of Content Search>_Purge`。</span><span class="sxs-lookup"><span data-stu-id="d5656-169">Note that the object that is created when you run the **New-ComplianceSearchAction** cmdlet is named using this format:  `<name of Content Search>_Purge`.</span></span> 
    
- <span data-ttu-id="d5656-170">**在删除邮件后会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="d5656-170">**What happens after you delete a message?**</span></span>

   <span data-ttu-id="d5656-171">使用该`New-ComplianceSearchAction -Purge -PurgeType HardDelete`命令删除的邮件将移至 "清除" 文件夹, 用户不能访问该邮件。</span><span class="sxs-lookup"><span data-stu-id="d5656-171">A message that's deleted with the  `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command is moved to the Purges folder and can't be accessed by the user.</span></span> <span data-ttu-id="d5656-172">将邮件移动到 "清除" 文件夹后, 如果为该邮箱启用了单个项目恢复, 则邮件将保留已删除项目的保留期的持续时间。</span><span class="sxs-lookup"><span data-stu-id="d5656-172">After the message is moved to the Purges folder, the message is retained for the duration of the deleted item retention period if single item recovery is enabled for the mailbox.</span></span> <span data-ttu-id="d5656-173">(在 Office 365 中, 创建新邮箱时, 默认情况下将启用单个项目恢复。)在已删除项目的保留期过期后, 该邮件将被标记为永久删除, 并将在下次邮箱由托管文件夹助理处理时从 Office 365 中清除。</span><span class="sxs-lookup"><span data-stu-id="d5656-173">(In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time the mailbox is processed by the Managed Folder assistant.</span></span> 

   <span data-ttu-id="d5656-174">如果使用此`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`命令, 则邮件将移至用户的 "可恢复的项目" 文件夹中的 "删除" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="d5656-174">If you use the `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command, messages are moved to the Deletions folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="d5656-175">它不会立即从 Office 365 中清除。</span><span class="sxs-lookup"><span data-stu-id="d5656-175">It isn't immediately purged from Office 365.</span></span> <span data-ttu-id="d5656-176">在基于为邮箱配置的已删除邮件保留期的持续时间内，用户可以恢复“已删除邮件”文件夹中的邮件。</span><span class="sxs-lookup"><span data-stu-id="d5656-176">The user can recover messages in the Deleted Items folder for the duration based on the deleted item retention period configured for the mailbox.</span></span> <span data-ttu-id="d5656-177">此保留期过期（或如果用户在过期之前清除邮件）后，邮件将移动到“清除”文件夹，用户将无法再访问。</span><span class="sxs-lookup"><span data-stu-id="d5656-177">After this retention period expires (or if user purges the message before it expires), the message is moved to the Purges folder and can no longer be accessed by the user.</span></span> <span data-ttu-id="d5656-178">在 "清除" 文件夹中, 如果为邮箱启用了单个项目恢复, 则将根据为邮箱配置的已删除项目保留期来保留邮件的持续时间。</span><span class="sxs-lookup"><span data-stu-id="d5656-178">Once in the Purges folder, the message is retained for the duration based on the deleted item retention period configured for the mailbox if single items recovery is enabled for the mailbox.</span></span> <span data-ttu-id="d5656-179">(在 Office 365 中, 创建新邮箱时, 默认情况下将启用单个项目恢复。)在已删除项目的保留期过期后, 该邮件将被标记为永久删除, 并将在下次该邮箱由托管文件夹助理处理时从 Office 365 中清除。</span><span class="sxs-lookup"><span data-stu-id="d5656-179">(In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time that the mailbox is processed by the Managed Folder assistant.</span></span> 
    
- <span data-ttu-id="d5656-180">**如果您必须删除超过50000个邮箱的邮件, 该怎么办？**</span><span class="sxs-lookup"><span data-stu-id="d5656-180">**What if you have to delete a message from more than 50,000 mailboxes?**</span></span>

    <span data-ttu-id="d5656-181">如前面所述, 您可以对最多50000个邮箱执行搜索和清除操作。</span><span class="sxs-lookup"><span data-stu-id="d5656-181">As previously stated, you can perform a search and purge operation on a maximum of 50,000 mailboxes.</span></span> <span data-ttu-id="d5656-182">如果您必须对超过50000个邮箱执行搜索和清除操作, 请考虑创建临时搜索权限筛选器, 这将减少搜索到低于50000邮箱的邮箱数。</span><span class="sxs-lookup"><span data-stu-id="d5656-182">If you have to do a search and purge operation on more than 50,000 mailboxes, consider creating temporary search permissions filters that would reduce the number of mailboxes that would be searched to less than 50,000 mailboxes.</span></span> <span data-ttu-id="d5656-183">例如, 如果您的组织包含不同部门、州或国家/地区的邮箱, 则可以基于其中一个邮箱属性创建邮箱搜索权限筛选器, 以搜索组织中的邮箱子集。</span><span class="sxs-lookup"><span data-stu-id="d5656-183">For example, if your organization contains mailboxes in different departments, states, or countries, you can create a mailbox search permissions filter based on one of those mailbox properties to search a subset of mailboxes in your organization.</span></span> <span data-ttu-id="d5656-184">创建搜索权限筛选器之后, 您将创建搜索 (在步骤1中介绍), 然后删除该邮件 (如步骤3中所述)。</span><span class="sxs-lookup"><span data-stu-id="d5656-184">After you create the search permissions filter, you would create the search (described in Step 1) and then delete the message (described in Step 3).</span></span> <span data-ttu-id="d5656-185">然后, 您可以编辑筛选器以搜索和清除不同组邮箱中的邮件。</span><span class="sxs-lookup"><span data-stu-id="d5656-185">Then you can edit the filter to search for and purge messages in a different set of mailboxes.</span></span> <span data-ttu-id="d5656-186">有关创建搜索权限筛选器的详细信息, 请参阅[Configure 权限筛选以进行内容搜索](permissions-filtering-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d5656-186">For more information about creating search permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
    
- <span data-ttu-id="d5656-187">**是否将删除搜索结果中包含的未编制索引的项目？**</span><span class="sxs-lookup"><span data-stu-id="d5656-187">**Will unindexed items included in the search results be deleted?**</span></span>

    <span data-ttu-id="d5656-188">否, "new-compliancesearchaction-清除" 命令不会删除未编制索引的项目。</span><span class="sxs-lookup"><span data-stu-id="d5656-188">No, the  \`New-ComplianceSearchAction -Purge command doesn't delete unindexed items.</span></span> 
    
- <span data-ttu-id="d5656-189">**如果从已置于就地保留或诉讼保留中的邮箱中删除邮件或将其分配给 Office 365 保留策略, 将会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="d5656-189">**What happens if a message is deleted from a mailbox that has been placed on In-Place Hold or Litigation Hold or is assigned to an Office 365 retention policy?**</span></span>

    <span data-ttu-id="d5656-190">清除邮件并将其移动到 "清除" 文件夹后, 邮件将一直保留到保留持续时间过期。</span><span class="sxs-lookup"><span data-stu-id="d5656-190">After the message is purged and moved to the Purges folder, the message is retained until the hold duration expires.</span></span> <span data-ttu-id="d5656-191">如果为无限期的保留期，则这些项目会一直保留到您删除保留设置或更改保留期。</span><span class="sxs-lookup"><span data-stu-id="d5656-191">If the hold duration is unlimited, then items are retained until the hold is removed or the hold duration is changed.</span></span>
    
- <span data-ttu-id="d5656-192">**为什么在不同的安全与合规中心角色组之间划分搜索和删除工作流？**</span><span class="sxs-lookup"><span data-stu-id="d5656-192">**Why is the search and remove workflow divided among different security and compliance center role groups?**</span></span>

    <span data-ttu-id="d5656-193">如前所述，必须是电子数据展示管理员角色组的成员或者分配有合规性搜索管理角色的用户才能搜索邮箱。</span><span class="sxs-lookup"><span data-stu-id="d5656-193">As previously explained, a person has to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role to search mailboxes.</span></span> <span data-ttu-id="d5656-194">若要删除邮件，必须是组织管理角色组的成员，或分配有“搜索并清除”管理角色。</span><span class="sxs-lookup"><span data-stu-id="d5656-194">To delete messages, a person has to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="d5656-195">这就使得可以控制哪些人可以搜索组织中的邮箱以及哪些人可以删除邮件。</span><span class="sxs-lookup"><span data-stu-id="d5656-195">This makes it possible to control who can search mailboxes in the organization and who can delete messages.</span></span> 
