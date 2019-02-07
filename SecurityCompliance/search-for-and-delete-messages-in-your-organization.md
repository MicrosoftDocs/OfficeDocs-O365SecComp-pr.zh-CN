---
title: 搜索并删除您的 Office 365 组织的管理员帮助中的电子邮件
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 使用搜索和清除 Office 365 安全性功能&amp;合规性中心以搜索并删除从您的组织中的所有邮箱的电子邮件。
ms.openlocfilehash: be83b2e3e765980ae401356b924c26c53386a2b3
ms.sourcegitcommit: d6a28c4f6db6a676ca960173e8ff8f17d4aa1c4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29755253"
---
# <a name="search-for-and-delete-email-messages-in-your-office-365-organization---admin-help"></a><span data-ttu-id="518e4-103">搜索并删除您的 Office 365 组织的管理员帮助中的电子邮件</span><span class="sxs-lookup"><span data-stu-id="518e4-103">Search for and delete email messages in your Office 365 organization - Admin Help</span></span>

<span data-ttu-id="518e4-104">**本文是针对管理员。您正在尝试查找您想要删除的邮箱中的项目吗？请参阅[查找邮件或即时搜索的项目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|</span><span class="sxs-lookup"><span data-stu-id="518e4-104">**This article is for administrators. Are you trying to find items in your mailbox that you want to delete? See [Find a message or item with Instant Search](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**|</span></span>
   
<span data-ttu-id="518e4-p101">可以使用 Office 365 中的内容的搜索功能搜索和您的组织中所有邮箱中删除电子邮件。这可以帮助您查找并删除可能有害或高风险电子邮件，如：</span><span class="sxs-lookup"><span data-stu-id="518e4-p101">You can use the Content Search feature in Office 365 to search for and delete an email message from all mailboxes in your organization. This can help you find and remove potentially harmful or high-risk email, such as:</span></span>
  
- <span data-ttu-id="518e4-107">包含危险的附件或病毒的邮件</span><span class="sxs-lookup"><span data-stu-id="518e4-107">Messages that contain dangerous attachments or viruses</span></span>
    
- <span data-ttu-id="518e4-108">网络仿冒邮件</span><span class="sxs-lookup"><span data-stu-id="518e4-108">Phishing messages</span></span>
    
- <span data-ttu-id="518e4-109">包含敏感数据的邮件</span><span class="sxs-lookup"><span data-stu-id="518e4-109">Messages that contain sensitive data</span></span>
    
> [!CAUTION]
> <span data-ttu-id="518e4-110">搜索和清除是强大功能，允许任何人都分配所需的权限从您的组织中的邮箱中删除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="518e4-110">Search and purge is a powerful feature that allows anyone that is assigned the necessary permissions to delete email messages from mailboxes in your organization.</span></span> 
  
## <a name="before-you-begin"></a><span data-ttu-id="518e4-111">准备工作</span><span class="sxs-lookup"><span data-stu-id="518e4-111">Before you begin</span></span>

- <span data-ttu-id="518e4-p102">若要创建和运行内容的搜索，您必须是**电子数据展示管理员**角色组的成员或**合规性搜索**管理角色分配。若要删除的邮件，您必须是**组织管理**角色组的成员或**搜索和清除**管理角色分配。有关将用户添加到角色组的信息，请参阅[授予用户对 Office 365 安全性 & 合规中心的访问](grant-access-to-the-security-and-compliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="518e4-p102">To create and run a Content Search, you have to be a member of the **eDiscovery Manager** role group or be assigned the **Compliance Search** management role. To delete messages, you have to be a member of the **Organization Management** role group or be assigned the **Search And Purge** management role. For information about adding users to a role group, see [Give users access to the Office 365 Security & Compliance Center](grant-access-to-the-security-and-compliance-center.md).</span></span>
    
- <span data-ttu-id="518e4-p103">您必须使用安全 & 合规性中心 PowerShell 删除邮件。有关如何将连接的说明，请参阅[Step 2](#step-2-connect-to-security-amp-compliance-center-powershell) 。</span><span class="sxs-lookup"><span data-stu-id="518e4-p103">You have to use Security & Compliance Center PowerShell to delete messages. See [Step 2](#step-2-connect-to-security-amp-compliance-center-powershell) for instructions about how to connect.</span></span>
    
- <span data-ttu-id="518e4-p104">每个邮箱的 10 项最多可以一次中删除。搜索并删除邮件的功能要用作事件响应工具，因为此限制有助于确保邮件快速将从邮箱中删除。此功能不适用于用户邮箱清理。若要删除 10 个以上的项目，可以在 Exchange Online PowerShell 中使用**Search-mailbox DeleteContent**命令。请参阅[搜索并删除邮件的管理员技术](search-for-and-delete-messagesadmin-help.md)。</span><span class="sxs-lookup"><span data-stu-id="518e4-p104">A maximum of 10 items per mailbox can be removed at one time. Because the capability to search for and remove messages is intended to be an incident-response tool, this limit helps ensure that messages are quickly removed from mailboxes. This feature isn't intended to clean up user mailboxes. To delete more than 10 items, you can use the **Search-Mailbox -DeleteContent** command in Exchange Online PowerShell. See [Search for and delete messages - Admin help](search-for-and-delete-messagesadmin-help.md).</span></span>
    
- <span data-ttu-id="518e4-p105">在内容搜索，您可以通过执行搜索删除中的项目和清除操作的邮箱的最大数量为 50000。如果内容搜索 （即您在[步骤 1](#step-1-create-a-content-search-to-find-the-message-to-delete)中创建） 具有超过 50,000 个源邮箱，则清除操作 （即您在步骤 3 中创建） 将失败。请参阅用于执行搜索提示的[详细信息](#more-information)部分和清除超过 50,000 个邮箱上的操作。</span><span class="sxs-lookup"><span data-stu-id="518e4-p105">The maximum number of mailboxes in a Content Search that you can delete items in by doing a search and purge action is 50,000. If the Content Search (that you create in [Step 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) has more than 50,000 source mailboxes, the purge action (that you create in Step 3) will fail. See the [More information](#more-information) section for a tip on performing a search and purge operation on more than 50,000 mailboxes.</span></span> 
    
- <span data-ttu-id="518e4-p106">本文中的过程只可用于删除 Exchange Online 邮箱和公用文件夹中的项目。不能用于业务网站删除 SharePoint 或 OneDrive 中的内容。</span><span class="sxs-lookup"><span data-stu-id="518e4-p106">The procedure in this article can only be used to delete items in Exchange Online mailboxes and public folders. You can't use it to delete content from SharePoint or OneDrive for Business sites.</span></span>
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a><span data-ttu-id="518e4-127">步骤 1：创建内容搜索来查找要删除的邮件</span><span class="sxs-lookup"><span data-stu-id="518e4-127">Step 1: Create a Content Search to find the message to delete</span></span>

<span data-ttu-id="518e4-p107">第一步是创建和运行内容搜索以查找您想要从您的组织中的邮箱中删除的消息。您可以通过使用安全创建搜索&amp;合规性中心或通过运行**新建 ComplianceSearch**和**开始 ComplianceSearch** cmdlet。与查询匹配将删除此搜索运行的邮件**新建 ComplianceSearchAction-清除**命令在[步骤 3](#step-3-delete-the-message)。有关创建内容搜索和配置搜索查询的信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="518e4-p107">The first step is to create and run a Content Search to find the message that you want to remove from mailboxes in your organization. You can create the search by using the Security &amp; Compliance Center or by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets. The messages that match the query for this search will be deleted by running the **New-ComplianceSearchAction -Purge** command in [Step 3](#step-3-delete-the-message). For information about creating a Content Search and configuring search queries, see the following topics:</span></span> 
  
- [<span data-ttu-id="518e4-132">Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="518e4-132">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="518e4-133">内容搜索的关键字查询</span><span class="sxs-lookup"><span data-stu-id="518e4-133">Keyword queries for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="518e4-134">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="518e4-134">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [<span data-ttu-id="518e4-135">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="518e4-135">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> <span data-ttu-id="518e4-p108">在此步骤中创建的内容搜索中搜索的内容位置的业务网站不能包含 SharePoint 或 OneDrive。可以将用于电子邮件内容搜索中包括仅邮箱和公用文件夹。如果内容搜索包括网站，您将步骤 3 中收到错误，当您运行**新建 ComplianceSearchAction** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="518e4-p108">The content locations that are searched in the Content Search that you create in this step can't include SharePoint or OneDrive for Business sites. You can include only mailboxes and public folders in a Content Search that will be used to email messages. If the Content Search includes sites, you'll receive an error in Step 3 when you run the **New-ComplianceSearchAction** cmdlet.</span></span> 
  
### <a name="tips-for-finding-messages-to-remove"></a><span data-ttu-id="518e4-139">查找要删除的邮件提示</span><span class="sxs-lookup"><span data-stu-id="518e4-139">Tips for finding messages to remove</span></span>

<span data-ttu-id="518e4-p109">搜索查询的目标是将搜索结果的范围缩小到仅包含您想要删除的邮件。以下是一些提示：</span><span class="sxs-lookup"><span data-stu-id="518e4-p109">The goal of the search query is to narrow the results of the search to only the message or messages that you want to remove. Here are some tips:</span></span>
  
- <span data-ttu-id="518e4-142">如果您知道确切文本或短语的邮件的主题行中使用，请搜索查询中使用**Subject**属性。</span><span class="sxs-lookup"><span data-stu-id="518e4-142">If you know the exact text or phrase used in the subject line of the message, use the **Subject** property in the search query.</span></span> 
    
- <span data-ttu-id="518e4-143">如果您知道邮件的确切日期（或日期范围），请在搜索查询中包括 **Received** 属性。</span><span class="sxs-lookup"><span data-stu-id="518e4-143">If you know that exact date (or date range) of the message, include the **Received** property in the search query.</span></span> 
    
- <span data-ttu-id="518e4-144">如果您知道邮件的发件人，请在搜索查询中包括 **From** 属性。</span><span class="sxs-lookup"><span data-stu-id="518e4-144">If you know who sent the message, include the **From** property in the search query.</span></span> 
    
- <span data-ttu-id="518e4-145">预览搜索结果，以验证搜索返回仅邮件 （或消息） 所需删除。</span><span class="sxs-lookup"><span data-stu-id="518e4-145">Preview the search results to verify that the search returned only the message (or messages) that you want to delete.</span></span>
    
- <span data-ttu-id="518e4-146">使用搜索 estimate 统计信息 (安全中搜索的详细信息窗格中显示&amp;合规性中心或通过使用[Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) 以获取结果的总数的计数。</span><span class="sxs-lookup"><span data-stu-id="518e4-146">Use the search estimate statistics (displayed in the details pane of the search in the Security &amp; Compliance Center or by using the [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) to get a count of the total number of results.</span></span> 
    
<span data-ttu-id="518e4-147">以下是查找可疑电子邮件的两个查询示例。</span><span class="sxs-lookup"><span data-stu-id="518e4-147">Here are two examples of queries to find suspicious email messages.</span></span>
  
- <span data-ttu-id="518e4-148">此查询返回用户在 2016 年 4 月 13 日至 2016 年 4 月 14 日之间收到的邮件，而且包含主题行中的单词“操作”和“必需”。</span><span class="sxs-lookup"><span data-stu-id="518e4-148">This query returns messages that were received by users between April 13, 2016 and April 14, 2016 and that contain the words "action" and "required" in the subject line.</span></span>
    
    ```
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```
   
- <span data-ttu-id="518e4-149">此查询返回由 chatsuwloginsset12345@outlook.com 发送的邮件，而且包含主题行中的完全匹配的短语“更新您的帐户信息”。</span><span class="sxs-lookup"><span data-stu-id="518e4-149">This query returns messages that were sent by chatsuwloginsset12345@outlook.com and that contain the exact phrase "Update your account information" in the subject line.</span></span>
    
    ```
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="518e4-150">步骤 2： 连接到安全 & 合规性中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="518e4-150">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="518e4-p110">下一步是连接到您的组织的安全 & 合规性中心 PowerShell。有关分步说明，请参阅[连接到 Office 365 安全性&amp;合规性中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="518e4-p110">The next step is to connect to Security & Compliance Center PowerShell for your organization. For step-by-step instructions, see [Connect to Office 365 Security &amp; Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="518e4-p111">如果您的 Office 365 帐户使用多因素身份验证 (MFA) 或联合身份验证，不能使用以前在连接到安全 & 合规性中心 PowerShell 主题中的说明。相反，请参阅[连接到 Office 365 安全性 & 合规性中心 PowerShell 使用多因素身份验证](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell)的主题中的说明。</span><span class="sxs-lookup"><span data-stu-id="518e4-p111">If your Office 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security & Compliance Center PowerShell. Instead, see the instructions in the topic [Connect to Office 365 Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>
  
## <a name="step-3-delete-the-message"></a><span data-ttu-id="518e4-155">步骤 3： 删除邮件</span><span class="sxs-lookup"><span data-stu-id="518e4-155">Step 3: Delete the message</span></span>

<span data-ttu-id="518e4-p112">您已创建并精简内容搜索以返回要删除并连接到安全的消息后&amp;合规性中心 PowerShell 中，最后一步是运行**新建 ComplianceSearchAction** cmdlet 删除邮件。您还可以软-或硬-删除邮件。软删除邮件移动到用户的可恢复项目文件夹，保留已删除的邮件保留期限过期之前。硬已删除的邮件被标记为从邮箱中永久删除，将被永久删除的下次由托管文件夹助理处理邮箱。如果为邮箱启用单个项目恢复，则已删除的邮件保留期过后，将永久删除硬已删除邮件。如果邮箱置于保持状态，直到过期项目的保留持续时间或直到保留被删除从邮箱保留已删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="518e4-p112">After you've created and refined a Content Search to return the message that you want to remove and are connected to Security &amp; Compliance Center PowerShell, the final step is to run the **New-ComplianceSearchAction** cmdlet to delete the message. You can soft- or hard-delete the message. A soft-deleted message is moved to a user's Recoverable Items folder and retained until the deleted item retention period expires. Hard-deleted messages are marked for permanent removal from the mailbox and will be permanently removed the next time the mailbox is processed by the Managed Folder Assistant. If single item recovery is enabled for the mailbox, hard-deleted items will be permanently removed after the deleted item retention period expires. If a mailbox is placed on hold, deleted messages are preserved until the hold duration for the item expires or until the hold is removed from the mailbox.</span></span>
  
<span data-ttu-id="518e4-162">在以下示例中，命令将软删除名为"删除网络钓鱼邮件"内容搜索返回的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="518e4-162">In the following example, the command will soft-delete the search results returned by a Content Search named "Remove Phishing Message".</span></span> 

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

<span data-ttu-id="518e4-163">硬-删除"删除网络钓鱼邮件"内容搜索返回的项，需要运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="518e4-163">To hard-deleted the items returned by the  "Remove Phishing Message" content search, you would run this command:</span></span>

```
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

<span data-ttu-id="518e4-164">请注意，软-或硬-删除邮件到运行上述命令时，搜索*SearchName*参数指定您在步骤 1 中创建内容搜索。</span><span class="sxs-lookup"><span data-stu-id="518e4-164">Note that when you run the previous command to soft- or hard-delete messages, the search specified by the  *SearchName*  parameter is the Content Search that you created in Step 1.</span></span> 
  
<span data-ttu-id="518e4-165">有关详细信息，请参阅[新建 ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)。</span><span class="sxs-lookup"><span data-stu-id="518e4-165">For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).</span></span>

## <a name="more-information"></a><span data-ttu-id="518e4-166">更多信息</span><span class="sxs-lookup"><span data-stu-id="518e4-166">More information</span></span>

- <span data-ttu-id="518e4-167">**您如何获取的搜索状态并删除操作？**</span><span class="sxs-lookup"><span data-stu-id="518e4-167">**How do you get status on the search and remove operation?**</span></span>

    <span data-ttu-id="518e4-p113">运行**Get ComplianceSearchAction**若要获取的删除操作状态。请注意，使用以下格式命名该对象时运行**新建 ComplianceSearchAction** cmdlet 创建： `<name of Content Search>_Purge`。</span><span class="sxs-lookup"><span data-stu-id="518e4-p113">Run the **Get-ComplianceSearchAction** to get the status on the delete operation. Note that the object that is created when you run the **New-ComplianceSearchAction** cmdlet is named using this format:  `<name of Content Search>_Purge`.</span></span> 
    
- <span data-ttu-id="518e4-170">**删除一条消息后，会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="518e4-170">**What happens after you delete a message?**</span></span>

   <span data-ttu-id="518e4-p114">一条消息，与删除`New-ComplianceSearchAction -Purge -PurgeType HardDelete`命令会移动到清除文件夹，并且用户无法访问。将邮件移至清除文件夹后，邮件保留已删除的邮件保留期限的持续时间内，如果为邮箱启用单个项目恢复。（Office 365 中单个项目恢复为默认启用创建新邮箱时。）已删除的邮件保留期过后，邮件被标记为永久删除，并将被清除从 Office 365 的下次由托管文件夹助理处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="518e4-p114">A message that's deleted with the  `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command is moved to the Purges folder and can't be accessed by the user. After the message is moved to the Purges folder, the message is retained for the duration of the deleted item retention period if single item recovery is enabled for the mailbox. (In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time the mailbox is processed by the Managed Folder assistant.</span></span> 

   <span data-ttu-id="518e4-p115">如果您使用`New-ComplianceSearchAction -Purge -PurgeType SoftDelete`命令，邮件被移到用户的可恢复的项目文件夹中的删除文件夹。它不立即清除已从 Office 365。用户可以恢复基于配置邮箱的已删除的邮件保留期的持续时间内的已删除邮件文件夹中的邮件。此保留期 （或如果用户清除之前的邮件已到期） 后，邮件被移动到清除文件夹，并不再可以由用户访问。一次在清除文件夹中，邮件保留的基于如果为邮箱启用单个项目恢复配置邮箱的已删除的邮件保留期的持续时间。（Office 365 中单个项目恢复为默认启用创建新邮箱时。）已删除的邮件保留期过后，邮件被标记为永久删除，并将被清除从 Office 365 下次由托管文件夹助理处理邮箱。</span><span class="sxs-lookup"><span data-stu-id="518e4-p115">If you use the `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command, messages are moved to the Deletions folder in the user's Recoverable Items folder. It isn't immediately purged from Office 365. The user can recover messages in the Deleted Items folder for the duration based on the deleted item retention period configured for the mailbox. After this retention period expires (or if user purges the message before it expires), the message is moved to the Purges folder and can no longer be accessed by the user. Once in the Purges folder, the message is retained for the duration based on the deleted item retention period configured for the mailbox if single items recovery is enabled for the mailbox. (In Office 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Office 365 the next time that the mailbox is processed by the Managed Folder assistant.</span></span> 
    
- <span data-ttu-id="518e4-180">**如果您必须从超过 50,000 个邮箱中删除一条消息？**</span><span class="sxs-lookup"><span data-stu-id="518e4-180">**What if you have to delete a message from more than 50,000 mailboxes?**</span></span>

    <span data-ttu-id="518e4-p116">如前面所述，您可以执行搜索和清除 50,000 邮箱的最大操作。如果您需要执行搜索和清除超过 50,000 个邮箱上的操作，请考虑创建临时搜索权限筛选器会降低将到不超过 50,000 的邮箱搜索的邮箱数。例如，如果您的组织包含中不同部门、 州或国家/地区的邮箱，您可以创建基于其中一个邮箱属性搜索您的组织中的一部分邮箱的邮箱搜索权限筛选器。创建搜索权限筛选器后，您将创建搜索 （在步骤 1 中所述），然后删除邮件 （步骤 3 中所述）。然后您可以编辑的筛选器来搜索和清除一组不同的邮箱中的消息。有关创建搜索权限筛选器的详细信息，请参阅[筛选内容搜索配置权限](permissions-filtering-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="518e4-p116">As previously stated, you can perform a search and purge operation on a maximum of 50,000 mailboxes. If you have to do a search and purge operation on more than 50,000 mailboxes, consider creating temporary search permissions filters that would reduce the number of mailboxes that would be searched to less than 50,000 mailboxes. For example, if your organization contains mailboxes in different departments, states, or countries, you can create a mailbox search permissions filter based on one of those mailbox properties to search a subset of mailboxes in your organization. After you create the search permissions filter, you would create the search (described in Step 1) and then delete the message (described in Step 3). Then you can edit the filter to search for and purge messages in a different set of mailboxes. For more information about creating search permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
    
- <span data-ttu-id="518e4-187">**将删除未编制索引的项目包含在搜索结果？**</span><span class="sxs-lookup"><span data-stu-id="518e4-187">**Will unindexed items included in the search results be deleted?**</span></span>

    <span data-ttu-id="518e4-188">否，新建 ComplianceSearchAction-清除命令不删除未编制索引的项目。</span><span class="sxs-lookup"><span data-stu-id="518e4-188">No, the  \`New-ComplianceSearchAction -Purge command doesn't delete unindexed items.</span></span> 
    
- <span data-ttu-id="518e4-189">**如果从已被置于就地保留或诉讼保留或已分配给 Office 365 保留策略的邮箱中删除一条消息，则会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="518e4-189">**What happens if a message is deleted from a mailbox that has been placed on In-Place Hold or Litigation Hold or is assigned to an Office 365 retention policy?**</span></span>

    <span data-ttu-id="518e4-p117">清除邮件并将其移至清除文件夹后，邮件保留，直到保留持续时间过期。如果是无限保留持续时间，然后直到保留被删除或更改保留持续时间也将保留项。</span><span class="sxs-lookup"><span data-stu-id="518e4-p117">After the message is purged and moved to the Purges folder, the message is retained until the hold duration expires. If the hold duration is unlimited, then items are retained until the hold is removed or the hold duration is changed.</span></span>
    
- <span data-ttu-id="518e4-192">**为什么是搜索并删除划分不同安全 & 合规中心的角色组的工作流？**</span><span class="sxs-lookup"><span data-stu-id="518e4-192">**Why is the search and remove workflow divided among different Security & Compliance Center role groups?**</span></span>

    <span data-ttu-id="518e4-p118">如前所述，人员必须是电子数据展示管理员角色组的成员，或者要搜索邮箱的合规性搜索管理角色分配。若要删除的邮件，人员必须是组织管理角色组的成员或搜索和清除管理角色分配。这便可以控制谁可以在组织中搜索邮箱和谁可以删除邮件。</span><span class="sxs-lookup"><span data-stu-id="518e4-p118">As previously explained, a person has to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role to search mailboxes. To delete messages, a person has to be a member of the Organization Management role group or be assigned the Search And Purge management role. This makes it possible to control who can search mailboxes in the organization and who can delete messages.</span></span> 
