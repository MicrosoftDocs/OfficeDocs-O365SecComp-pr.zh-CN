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
description: 使用 Office 365 安全&amp;合规中心中的 "搜索和清除" 功能搜索和删除组织中所有邮箱的电子邮件。
ms.openlocfilehash: 15d67e42e4bdc63838f7ec1701d643391fa5c552
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30296855"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a><span data-ttu-id="25f97-103">在 Office 365 组织中搜索和删除电子邮件-管理员帮助</span><span class="sxs-lookup"><span data-stu-id="25f97-103">Search for and delete email messages in your Office 365 organization - Admin Help</span></span>

<span data-ttu-id="25f97-104">**本文适用于管理员。您是否正在尝试查找您要删除的邮箱中的项目？请参阅[使用即时搜索查找邮件或项目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|</span><span class="sxs-lookup"><span data-stu-id="25f97-104">**This article is for administrators. Are you trying to find items in your mailbox that you want to delete? See [Find a message or item with Instant Search](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|</span></span>
   
<span data-ttu-id="25f97-p101">您可以使用 Office 365 中的内容搜索功能搜索和删除组织中所有邮箱的电子邮件。这可帮助你查找和删除可能有害或高风险的电子邮件, 例如:</span><span class="sxs-lookup"><span data-stu-id="25f97-p101">You can use the Content Search feature in Office 365 to search for and delete an email message from all mailboxes in your organization. This can help you find and remove potentially harmful or high-risk email, such as:</span></span>
  
- <span data-ttu-id="25f97-107">包含危险附件或病毒的邮件</span><span class="sxs-lookup"><span data-stu-id="25f97-107">Messages that contain dangerous attachments or viruses</span></span>
    
- <span data-ttu-id="25f97-108">网络仿冒邮件</span><span class="sxs-lookup"><span data-stu-id="25f97-108">Phishing messages</span></span>
    
- <span data-ttu-id="25f97-109">包含敏感数据的邮件</span><span class="sxs-lookup"><span data-stu-id="25f97-109">Messages that contain sensitive data</span></span>
    
> [!CAUTION]
> <span data-ttu-id="25f97-110">搜索和清除是一项强大的功能, 允许分配有必要权限的任何人从组织中的邮箱中删除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="25f97-110">Search and purge is a powerful feature that allows anyone that is assigned the necessary permissions to delete email messages from mailboxes in your organization.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="25f97-111">准备工作</span><span class="sxs-lookup"><span data-stu-id="25f97-111">Before you begin</span></span>

- <span data-ttu-id="25f97-p102">若要创建和运行内容搜索, 您必须是**电子数据展示管理器**角色组的成员, 或分配有**合规性搜索**管理角色。若要删除邮件, 您必须是 "**组织管理**" 角色组的成员, 或者分配有 "**搜索和清除**" 管理角色。有关向角色组添加用户的信息, 请参阅[为用户提供对 Office 365 Security & 合规中心的访问权限](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="25f97-p102">To create and run a Content Search, you have to be a member of the **eDiscovery Manager** role group or be assigned the **Compliance Search** management role. To delete messages, you have to be a member of the **Organization Management** role group or be assigned the **Search And Purge** management role. For information about adding users to a role group, see [Give users access to the Office 365 Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="25f97-p103">您必须使用 Security & 合规性中心 PowerShell 删除邮件。有关如何连接的说明, 请参阅[步骤 2](#step-2-connect-to-security-amp-compliance-center-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="25f97-p103">You have to use Security & Compliance Center PowerShell to delete messages. See [Step 2](#step-2-connect-to-security-amp-compliance-center-powershell) for instructions about how to connect.</span></span>
    
- <span data-ttu-id="25f97-p104">每个邮箱最多可以一次删除10个项目。因为搜索和删除邮件的功能旨在作为事件响应工具, 所以此限制有助于确保快速从邮箱中删除邮件。此功能不适用于清理用户邮箱。若要删除10个以上的项目, 您可以使用 Exchange Online PowerShell 中的**搜索-邮箱-DeleteContent**命令。请参阅[搜索和删除邮件-管理员帮助](search-for-and-delete-messagesadmin-help.md)。</span><span class="sxs-lookup"><span data-stu-id="25f97-p104">A maximum of 10 items per mailbox can be removed at one time. Because the capability to search for and remove messages is intended to be an incident-response tool, this limit helps ensure that messages are quickly removed from mailboxes. This feature isn't intended to clean up user mailboxes. To delete more than 10 items, you can use the **Search-Mailbox -DeleteContent** command in Exchange Online PowerShell. See [Search for and delete messages - Admin help](search-for-and-delete-messagesadmin-help.md).</span></span>
    
- <span data-ttu-id="25f97-p105">通过执行搜索和清除操作, 可以在内容搜索中删除项目的最大邮箱数为50000。如果在[第1步](#step-1-create-a-content-search-to-find-the-message-to-delete)中创建的内容搜索的源邮箱多于50000个, 则清除操作 (在步骤3中创建) 将会失败。有关在50000以上邮箱上执行搜索和清除操作的提示, 请参阅[详细信息](#more-information)部分。</span><span class="sxs-lookup"><span data-stu-id="25f97-p105">The maximum number of mailboxes in a Content Search that you can delete items in by doing a search and purge action is 50,000. If the Content Search (that you create in [Step 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) has more than 50,000 source mailboxes, the purge action (that you create in Step 3) will fail. See the [More information](#more-information) section for a tip on performing a search and purge operation on more than 50,000 mailboxes.</span></span> 
    
- <span data-ttu-id="25f97-p106">本文中的过程仅可用于删除 Exchange Online 邮箱和公用文件夹中的项目。您不能使用它从 SharePoint 或 OneDrive for business 网站中删除内容。</span><span class="sxs-lookup"><span data-stu-id="25f97-p106">The procedure in this article can only be used to delete items in Exchange Online mailboxes and public folders. You can't use it to delete content from SharePoint or OneDrive for Business sites.</span></span>
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a><span data-ttu-id="25f97-127">步骤 1：创建内容搜索来查找要删除的邮件</span><span class="sxs-lookup"><span data-stu-id="25f97-127">Step 1: Create a Content Search to find the message to delete</span></span>

<span data-ttu-id="25f97-p107">第一步是创建并运行内容搜索, 以查找要从组织中的邮箱中删除的邮件。您可以使用安全&amp;合规性中心或通过运行**new-compliancesearch**和**new-compliancesearch** cmdlet 来创建搜索。通过在[步骤 3](#step-3-delete-the-message)中运行**new-compliancesearchaction-清除**命令, 与此搜索的查询相匹配的邮件将被删除。有关创建内容搜索和配置搜索查询的信息, 请参阅下列主题:</span><span class="sxs-lookup"><span data-stu-id="25f97-p107">The first step is to create and run a Content Search to find the message that you want to remove from mailboxes in your organization. You can create the search by using the Security &amp; Compliance Center or by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets. The messages that match the query for this search will be deleted by running the **New-ComplianceSearchAction -Purge** command in [Step 3](#step-3-delete-the-message). For information about creating a Content Search and configuring search queries, see the following topics:</span></span> 
  
- [<span data-ttu-id="25f97-132">Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="25f97-132">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="25f97-133">内容搜索的关键字查询</span><span class="sxs-lookup"><span data-stu-id="25f97-133">Keyword queries for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="25f97-134">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="25f97-134">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [<span data-ttu-id="25f97-135">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="25f97-135">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> <span data-ttu-id="25f97-p108">在此步骤中创建的内容搜索中搜索的内容位置不能包含 SharePoint 或 OneDrive for business 网站。只能在将用于电子邮件的内容搜索中包含邮箱和公用文件夹。如果内容搜索包括网站, 则在运行**new-compliancesearchaction** cmdlet 时, 您将在步骤3中收到错误。</span><span class="sxs-lookup"><span data-stu-id="25f97-p108">The content locations that are searched in the Content Search that you create in this step can't include SharePoint or OneDrive for Business sites. You can include only mailboxes and public folders in a Content Search that will be used to email messages. If the Content Search includes sites, you'll receive an error in Step 3 when you run the **New-ComplianceSearchAction** cmdlet.</span></span> 
  
### <a name="tips-for-finding-messages-to-remove"></a><span data-ttu-id="25f97-139">查找要删除的邮件的提示</span><span class="sxs-lookup"><span data-stu-id="25f97-139">Tips for finding messages to remove</span></span>

<span data-ttu-id="25f97-p109">搜索查询的目标是将搜索结果的范围缩小到仅包含您想要删除的邮件。以下是一些提示：</span><span class="sxs-lookup"><span data-stu-id="25f97-p109">The goal of the search query is to narrow the results of the search to only the message or messages that you want to remove. Here are some tips:</span></span>
  
- <span data-ttu-id="25f97-142">如果您知道邮件的主题行中使用的确切文本或短语, 请在搜索查询中使用**subject**属性。</span><span class="sxs-lookup"><span data-stu-id="25f97-142">If you know the exact text or phrase used in the subject line of the message, use the **Subject** property in the search query.</span></span> 
    
- <span data-ttu-id="25f97-143">如果您知道邮件的确切日期（或日期范围），请在搜索查询中包括 **Received** 属性。</span><span class="sxs-lookup"><span data-stu-id="25f97-143">If you know that exact date (or date range) of the message, include the **Received** property in the search query.</span></span> 
    
- <span data-ttu-id="25f97-144">如果您知道邮件的发件人，请在搜索查询中包括 **From** 属性。</span><span class="sxs-lookup"><span data-stu-id="25f97-144">If you know who sent the message, include the **From** property in the search query.</span></span> 
    
- <span data-ttu-id="25f97-145">预览搜索结果以验证搜索是否仅返回您想要删除的一个或一封邮件。</span><span class="sxs-lookup"><span data-stu-id="25f97-145">Preview the search results to verify that the search returned only the message (or messages) that you want to delete.</span></span>
    
- <span data-ttu-id="25f97-146">使用搜索估计统计信息 (在安全&amp;合规性中心中的搜索的细节窗格中显示, 或使用[new-compliancesearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) 获取总结果数的计数。</span><span class="sxs-lookup"><span data-stu-id="25f97-146">Use the search estimate statistics (displayed in the details pane of the search in the Security &amp; Compliance Center or by using the [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) to get a count of the total number of results.</span></span> 
    
<span data-ttu-id="25f97-147">以下是查找可疑电子邮件的两个查询示例。</span><span class="sxs-lookup"><span data-stu-id="25f97-147">Here are two examples of queries to find suspicious email messages.</span></span>
  
- <span data-ttu-id="25f97-148">此查询返回用户在 2016 年 4 月 13 日至 2016 年 4 月 14 日之间收到的邮件，而且包含主题行中的单词“操作”和“必需”。</span><span class="sxs-lookup"><span data-stu-id="25f97-148">This query returns messages that were received by users between April 13, 2016 and April 14, 2016 and that contain the words "action" and "required" in the subject line.</span></span>
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- <span data-ttu-id="25f97-149">此查询返回由 chatsuwloginsset12345@outlook.com 发送的邮件，而且包含主题行中的完全匹配的短语“更新您的帐户信息”。</span><span class="sxs-lookup"><span data-stu-id="25f97-149">This query returns messages that were sent by chatsuwloginsset12345@outlook.com and that contain the exact phrase "Update your account information" in the subject line.</span></span>
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="25f97-150">步骤 2: 连接到安全 & 合规中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="25f97-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="25f97-p110">下一步是连接到组织的安全 & 合规中心 PowerShell。有关分步说明, 请参阅[连接到 Office 365 安全&amp;合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="25f97-p110">The next step is to connect to Security & Compliance Center PowerShell for your organization. For step-by-step instructions, see [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="25f97-p111">如果您的 Office 365 帐户使用多重身份验证 (MFA) 或联合身份验证, 则不能使用上一主题中有关连接到安全 & 合规中心 PowerShell 的说明。有关使用多重身份验证的主题中的说明, 请参阅[连接到 Office 365 Security & 合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)中的说明。</span><span class="sxs-lookup"><span data-stu-id="25f97-p111">If your Office 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security & Compliance Center PowerShell. Instead, see the instructions in the topic [Connect to Office 365 Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>
  
## <a name="step-3-delete-the-message"></a><span data-ttu-id="25f97-155">步骤 3: 删除邮件</span><span class="sxs-lookup"><span data-stu-id="25f97-155">Step 3: Delete the message</span></span>

<span data-ttu-id="25f97-p112">创建并优化内容搜索后, 若要返回要删除并连接到安全&amp;合规中心 PowerShell 的邮件, 最后一步是运行**new-compliancesearchaction** cmdlet 以删除该邮件。您可以软或硬删除邮件。软删除的邮件将移至用户的 "可恢复的项目" 文件夹并保留, 直到已删除项目的保留期过期。硬删除的邮件被标记为从邮箱永久删除, 并且在下次邮箱由托管文件夹助理处理时将被永久删除。如果为邮箱启用了单个项目恢复, 则删除的项目保留期过期后, 将永久删除硬删除的项目。如果将邮箱置于保留状态, 则会保留已删除邮件, 直到项目的保留期过期或从邮箱中删除保留期间为止。</span><span class="sxs-lookup"><span data-stu-id="25f97-p112">After you've created and refined a Content Search to return the message that you want to remove and are connected to Security &amp; Compliance Center PowerShell, the final step is to run the **New-ComplianceSearchAction** cmdlet to delete the message. You can soft- or hard-delete the message. A soft-deleted message is moved to a user's Recoverable Items folder and retained until the deleted item retention period expires. Hard-deleted messages are marked for permanent removal from the mailbox and will be permanently removed the next time the mailbox is processed by the Managed Folder Assistant. If single item recovery is enabled for the mailbox, hard-deleted items will be permanently removed after the deleted item retention period expires. If a mailbox is placed on hold, deleted messages are preserved until the hold duration for the item expires or until the hold is removed from the mailbox.</span></span>
  
<span data-ttu-id="25f97-162">在下面的示例中, 该命令将软删除名为 "删除仿冒邮件" 的内容搜索返回的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="25f97-162">In the following example, the command will soft-delete the search results returned by a Content Search named "Remove Phishing Message".</span></span> 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

<span data-ttu-id="25f97-163">若要硬删除 "删除仿冒邮件" 内容搜索返回的项目, 请运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="25f97-163">To hard-deleted the items returned by the  "Remove Phishing Message" content search, you would run this command:</span></span>

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

<span data-ttu-id="25f97-164">请注意, 在运行以前的命令以软删除或硬删除邮件时, 由*SearchName*参数指定的搜索是您在步骤1中创建的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="25f97-164">Note that when you run the previous command to soft- or hard-delete messages, the search specified by the  *SearchName*  parameter is the Content Search that you created in Step 1.</span></span> 
  
<span data-ttu-id="25f97-165">有关详细信息, 请参阅[new-compliancesearchaction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)。</span><span class="sxs-lookup"><span data-stu-id="25f97-165">For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).</span></span>

## <a name="more-information"></a><span data-ttu-id="25f97-166">更多信息</span><span class="sxs-lookup"><span data-stu-id="25f97-166">More information</span></span>

- <span data-ttu-id="25f97-167">**如何获取搜索和删除操作的状态？**</span><span class="sxs-lookup"><span data-stu-id="25f97-167">**How do you get status on the search and remove operation?**</span></span>

    <span data-ttu-id="25f97-p113">运行**new-compliancesearchaction**以获取有关删除操作的状态。请注意, 在运行**new-compliancesearchaction** cmdlet 时创建的对象是使用以下格式命名的: `<name of Content Search>_Purge`。</span><span class="sxs-lookup"><span data-stu-id="25f97-p113">Run the **Get-ComplianceSearchAction** to get the status on the delete operation. Note that the object that is created when you run the **New-ComplianceSearchAction** cmdlet is named using this format:  `<name of Content Search>_Purge`.</span></span> 
    
- <span data-ttu-id="25f97-170">**删除邮件后会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="25f97-170">**What happens after you delete a message?**</span></span>

   <span data-ttu-id="25f97-p114">使用该`New-ComplianceSearchAction -Purge -PurgeType HardDelete`命令删除的邮件将移至 "清除" 文件夹, 用户不能访问该邮件。将邮件移动到 "清除" 文件夹后, 如果为该邮箱启用了单个项目恢复, 则邮件将保留已删除项目的保留期的持续时间。(在 Office 365 中, 创建新邮箱时, 默认情况下将启用单个项目恢复。)在已删除项目的保留期过期后, 该邮件将被标记为永久删除, 并将在下次邮箱由托管文件夹助理处理时从 Office 365 中清除。</span><span class="sxs-lookup"><span data-stu-id="25f97-p114">A message that's deleted with the  `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command is moved to the Purges folder and can't be accessed by the user. After the message is moved to the Purges folder, the message is retained for the duration of the deleted item retention period if single item recovery is enabled for the mailbox. (In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time the mailbox is processed by the Managed Folder assistant.</span></span> 

   <span data-ttu-id="25f97-p115">如果使用此`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`命令, 则邮件将移至用户的 "可恢复的项目" 文件夹中的 "删除" 文件夹。它不会立即从 Office 365 中清除。用户可以根据为邮箱配置的已删除邮件保留期, 在 "已删除邮件" 文件夹中恢复邮件的持续时间。此保留期到期后 (或者, 如果用户在邮件过期之前清除邮件), 则会将邮件移至 "清除" 文件夹, 并且用户无法再访问该邮件。在 "清除" 文件夹中, 如果为邮箱启用了单个项目恢复, 则将根据为邮箱配置的已删除项目保留期来保留邮件的持续时间。(在 Office 365 中, 创建新邮箱时, 默认情况下将启用单个项目恢复。)在已删除项目的保留期过期后, 该邮件将被标记为永久删除, 并将在下次该邮箱由托管文件夹助理处理时从 Office 365 中清除。</span><span class="sxs-lookup"><span data-stu-id="25f97-p115">If you use the `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command, messages are moved to the Deletions folder in the user's Recoverable Items folder. It isn't immediately purged from Office 365. The user can recover messages in the Deleted Items folder for the duration based on the deleted item retention period configured for the mailbox. After this retention period expires (or if user purges the message before it expires), the message is moved to the Purges folder and can no longer be accessed by the user. Once in the Purges folder, the message is retained for the duration based on the deleted item retention period configured for the mailbox if single items recovery is enabled for the mailbox. (In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time that the mailbox is processed by the Managed Folder assistant.</span></span> 
    
- <span data-ttu-id="25f97-180">**如果您必须删除超过50000个邮箱的邮件, 该怎么办？**</span><span class="sxs-lookup"><span data-stu-id="25f97-180">**What if you have to delete a message from more than 50,000 mailboxes?**</span></span>

    <span data-ttu-id="25f97-p116">如前面所述, 您可以对最多50000个邮箱执行搜索和清除操作。如果您必须对超过50000个邮箱执行搜索和清除操作, 请考虑创建临时搜索权限筛选器, 这将减少搜索到低于50000邮箱的邮箱数。例如, 如果您的组织包含不同部门、州或国家/地区的邮箱, 则可以基于其中一个邮箱属性创建邮箱搜索权限筛选器, 以搜索组织中的邮箱子集。创建搜索权限筛选器之后, 您将创建搜索 (在步骤1中介绍), 然后删除该邮件 (如步骤3中所述)。然后, 您可以编辑筛选器以搜索和清除不同组邮箱中的邮件。有关创建搜索权限筛选器的详细信息, 请参阅[Configure 权限筛选以进行内容搜索](permissions-filtering-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="25f97-p116">As previously stated, you can perform a search and purge operation on a maximum of 50,000 mailboxes. If you have to do a search and purge operation on more than 50,000 mailboxes, consider creating temporary search permissions filters that would reduce the number of mailboxes that would be searched to less than 50,000 mailboxes. For example, if your organization contains mailboxes in different departments, states, or countries, you can create a mailbox search permissions filter based on one of those mailbox properties to search a subset of mailboxes in your organization. After you create the search permissions filter, you would create the search (described in Step 1) and then delete the message (described in Step 3). Then you can edit the filter to search for and purge messages in a different set of mailboxes. For more information about creating search permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
    
- <span data-ttu-id="25f97-187">**是否将删除搜索结果中包含的未编制索引的项目？**</span><span class="sxs-lookup"><span data-stu-id="25f97-187">**Will unindexed items included in the search results be deleted?**</span></span>

    <span data-ttu-id="25f97-188">否, "new-compliancesearchaction-清除" 命令不会删除未编制索引的项目。</span><span class="sxs-lookup"><span data-stu-id="25f97-188">No, the  \`New-ComplianceSearchAction -Purge command doesn't delete unindexed items.</span></span> 
    
- <span data-ttu-id="25f97-189">**如果从已置于就地保留或诉讼保留中的邮箱中删除邮件或将其分配给 Office 365 保留策略, 将会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="25f97-189">**What happens if a message is deleted from a mailbox that has been placed on In-Place Hold or Litigation Hold or is assigned to an Office 365 retention policy?**</span></span>

    <span data-ttu-id="25f97-p117">清除邮件并将其移动到 "清除" 文件夹后, 邮件将一直保留到保留持续时间过期。如果保留持续时间不受限制, 则在删除保留或更改保留期之前, 将保留项目。</span><span class="sxs-lookup"><span data-stu-id="25f97-p117">After the message is purged and moved to the Purges folder, the message is retained until the hold duration expires. If the hold duration is unlimited, then items are retained until the hold is removed or the hold duration is changed.</span></span>
    
- <span data-ttu-id="25f97-192">**为什么在不同的安全 & 合规中心角色组之间划分搜索和删除工作流？**</span><span class="sxs-lookup"><span data-stu-id="25f97-192">**Why is the search and remove workflow divided among different Security & Compliance Center role groups?**</span></span>

    <span data-ttu-id="25f97-p118">如前所述, 某个人必须是电子数据展示管理器角色组的成员, 或者被分配了合规性搜索管理角色以搜索邮箱。若要删除邮件, 某个人必须是 "组织管理" 角色组的成员, 或被分配了 "搜索和清除" 管理角色。这样, 就可以控制谁可以搜索组织中的邮箱以及谁可以删除邮件。</span><span class="sxs-lookup"><span data-stu-id="25f97-p118">As previously explained, a person has to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role to search mailboxes. To delete messages, a person has to be a member of the Organization Management role group or be assigned the Search And Purge management role. This makes it possible to control who can search mailboxes in the organization and who can delete messages.</span></span> 
