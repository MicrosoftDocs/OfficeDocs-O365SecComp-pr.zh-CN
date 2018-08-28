---
title: 搜索和删除邮件 - 管理员帮助
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: 管理员可以使用 Search-Mailbox cmdlet 来搜索用户邮箱，然后从邮箱中删除邮件。
ms.openlocfilehash: ed110c4a3e36a93970af99e9548aa293d94307fd
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026579"
---
# <a name="search-for-and-delete-messages---admin-help"></a><span data-ttu-id="56c0f-103">搜索和删除邮件 - 管理员帮助</span><span class="sxs-lookup"><span data-stu-id="56c0f-103">Search for and delete messages - Admin help</span></span>
  
<span data-ttu-id="56c0f-104">管理员可以使用 **Search-Mailbox** cmdlet 来搜索用户邮箱，然后从邮箱中删除邮件。</span><span class="sxs-lookup"><span data-stu-id="56c0f-104">Administrators can use the **Search-Mailbox** cmdlet to search user mailboxes and then delete messages from a mailbox.</span></span> 
  
<span data-ttu-id="56c0f-p101">若要使用一个步骤搜索并删除邮件，请运行带有  **DeleteContent** 开关的 _Search-Mailbox_ cmdlet。但是，在执行此操作时，无法预览搜索结果或生成搜索返回的邮件的日志，您可能意外删除不想删除的邮件。若要在删除搜索中找到的邮件之前预览这些邮件的日志，需要运行带有  **LogOnly** 开关的 _Search-Mailbox_ cmdlet。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p101">To search and delete messages in one step, run the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch. However, when you do this, you can't preview search results or generate a log of messages that will be returned by the search, and you may inadvertently delete messages that you didn't intend to. To preview a log of the messages found in the search before they're deleted, run the **Search-Mailbox** cmdlet with the  _LogOnly_ switch.</span></span> 
  
<span data-ttu-id="56c0f-p102">作为额外保护措施，可以使用  _TargetMailbox_ 和  _TargetFolder_ 参数，首先将邮件复制到另一个邮箱。这样可保留已删除邮件的副本，以防需要再次访问这些邮件。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p102">As an additional safeguard, you can first copy the messages to another mailbox by using the  _TargetMailbox_ and  _TargetFolder_ parameters. By doing this, you retain a copy of the deleted messages in case you need to access them again.</span></span> 
  
## <a name="what-do-i-need-to-know-before-i-begin"></a><span data-ttu-id="56c0f-110">在开始之前，我需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="56c0f-110">What do I need to know before I begin?</span></span>
<span data-ttu-id="56c0f-111"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="56c0f-111"></span></span>

- <span data-ttu-id="56c0f-p103">估计完成时间：10 分钟。实际时间可能因邮箱大小和搜索查询而异。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p103">Estimated time to complete: 10 minutes. The actual time may vary depending on the size of the mailbox and the search query.</span></span>
    
- <span data-ttu-id="56c0f-p104">不能使用 Exchange 管理中心 (EAC) 执行这些过程。必须使用命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p104">You can't use the Exchange admin center (EAC) to perform these procedures. You must use the Shell.</span></span>
    
- <span data-ttu-id="56c0f-116">您需要分配有以下两个管理角色才能在用户邮箱中搜索和删除邮件：</span><span class="sxs-lookup"><span data-stu-id="56c0f-116">You need to be assigned both of the following management roles to search for and delete messages in users' mailboxes:</span></span>
    
  - <span data-ttu-id="56c0f-p105">**邮箱搜索**此角色允许您跨组织中的多个邮箱搜索的邮件。默认情况下，管理员不分配此角色。若要指定自己此角色，以便您可以搜索邮箱，请将自己添加为发现管理角色组的成员。请参阅[将用户添加到发现管理角色组](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx)。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p105">**Mailbox Search** This role allows you to search for messages across multiple mailboxes in your organization. Administrators aren't assigned this role by default. To assign yourself this role so that you can search mailboxes, add yourself as a member of the Discovery Management role group. See [Add a User to the Discovery Management Role Group](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx).</span></span>
    
  - <span data-ttu-id="56c0f-p106">**邮箱导入导出**此角色可以从用户的邮箱中删除邮件。默认情况下，此角色不分配给任何角色组。若要从用户的邮箱中删除邮件，您可以向组织管理角色组添加邮箱导入导出角色。有关详细信息，请参阅[管理角色组](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx)中的"将角色添加到角色组"部分。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p106">**Mailbox Import Export** This role allows you to delete messages from a user's mailbox. By default, this role isn't assigned to any role group. To delete messages from users' mailboxes, you can add the Mailbox Import Export role to the Organization Management role group. For more information, see the "Add a role to a role group" section in [Manage Role Groups](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx) .</span></span> 
    
- <span data-ttu-id="56c0f-p107">如果要从中删除邮件的邮箱启用了单个项目恢复，则必须首先禁用该功能。有关详细信息，请参阅[启用或禁用邮箱的单个项目恢复](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx)。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p107">If the mailbox from which you want to delete messages has single item recovery enabled, you must first disable the feature. For more information, see [Enable or disable single item recovery for a mailbox](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx).</span></span>
    
- <span data-ttu-id="56c0f-p108">如果您要从中删除邮件的邮箱置于保持状态，建议您先咨询您的记录管理或法律部门之前保留中移除并删除邮箱内容。您获得批准后，请按照列出[Clean Up Recoverable Items Folder](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx)主题中的步骤。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p108">If the mailbox from which you want to delete messages is placed on hold, we recommend that you check with your records management or legal department before removing the hold and deleting the mailbox content. After you obtain approval, follow the steps listed in the topic [Clean Up the Recoverable Items Folder](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx).</span></span>
    
- <span data-ttu-id="56c0f-p109">使用 **Search-Mailbox** cmdlet，最多可搜索到 10,000 个邮箱。如果你是 Exchange Online 组织，并拥有超过 10,000 个邮箱，则可以使用合规性搜索功能（或相应的 **New-ComplianceSearch** cmdlet）搜索任意数量的邮箱。然后，你可以使用 **New-ComplianceSearchAction** cmdlet 删除由合规性搜索返回的邮件。有关详细信息，请参阅 [从你的 Office 365 组织搜索和删除电子邮件](https://go.microsoft.com/fwlink/p/?LinkId=786856)。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p109">You can search a maximum of 10,000 mailboxes using the **Search-Mailbox** cmdlet. If you're an Exchange Online organization and have more than 10,000 mailboxes, you can use the Compliance Search feature (or the corresponding **New-ComplianceSearch** cmdlet) to search an unlimited number of mailboxes. Then you can use the **New-ComplianceSearchAction** cmdlet to delete the messages returned by a compliance search. For more information, see [Search for and delete email messages from your Office 365 organization](https://go.microsoft.com/fwlink/p/?LinkId=786856).</span></span>
    
- <span data-ttu-id="56c0f-p110">如果添加一个搜索查询（通过使用  *SearchQuery*  参数）， **Search-Mailbox** cmdlet 最多返回搜索结果中的 10,000 个项目。因此，如果添加一个搜索查询，则可能需要多次运行 **Search-Mailbox** 命令才能将 10,000 多个项目删除。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p110">If you include a search query (by using the  *SearchQuery*  parameter), the **Search-Mailbox** cmdlet will return a maximum of 10,000 items in the search results. Therefore if you include a search query, you might have to run the **Search-Mailbox** command multiple times to delete more than 10,000 items.</span></span> 
    
- <span data-ttu-id="56c0f-p111">运行**Search-mailbox** cmdlet 时，还将搜索用户的存档邮箱。同样，使用**Search-mailbox** cmdlet 与_DeleteContent_开关时，将删除主存档邮箱中的项目。要防止这样，您可以包括*DoNotIncludeArchive*开关。此外，我们建议不用于_DeleteContent_开关删除邮件在 Exchange Online 邮箱的自动扩展启用了存档因为可能出现意外的数据丢失。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p111">The user's archive mailbox will also be searched when you run the **Search-Mailbox** cmdlet. Similarly, items in the primary archive mailbox will be deleted when you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch. To prevent this, you can include the  *DoNotIncludeArchive*  switch. Also, we recommend that you don't use the  _DeleteContent_ switch to delete messages in Exchange Online mailboxes that have auto-expanding archiving enabled because unexpected data loss may occur.</span></span> 
    
## <a name="search-messages-and-log-the-search-results"></a><span data-ttu-id="56c0f-139">搜索邮件并记录搜索结果</span><span class="sxs-lookup"><span data-stu-id="56c0f-139">Search messages and log the search results</span></span>
<span data-ttu-id="56c0f-140"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="56c0f-140"></span></span>

<span data-ttu-id="56c0f-p112">本示例在 April Stewart 的邮箱中搜索 Subject 字段中包含“Your bank statement”短语的邮件，并将搜索结果记录在管理员邮箱的 SearchAndDeleteLog 文件夹中。不会将邮件复制到目标邮箱或从目标邮箱删除。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p112">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and logs the search results in the SearchAndDeleteLog folder of the administrator's mailbox. Messages aren't copied to or deleted from the target mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="56c0f-143">此示例将搜索组织的所有邮箱，查找文件名中包含"特洛伊木马"一词的任何类型的附加文件的邮件，并向管理员的邮箱发送一封日志邮件。</span><span class="sxs-lookup"><span data-stu-id="56c0f-143">This example searches all mailboxes in the organization for messages that have any type of attached file that contains the word "Trojan" in the filename and sends a log message to the administrator's mailbox.</span></span>
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

<span data-ttu-id="56c0f-144">有关详细的语法和参数信息，请参阅 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。</span><span class="sxs-lookup"><span data-stu-id="56c0f-144">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>
  
[<span data-ttu-id="56c0f-145">返回顶部</span><span class="sxs-lookup"><span data-stu-id="56c0f-145">Return to top</span></span>](search-for-and-delete-messagesadmin-help.md#top)
  
## <a name="search-and-delete-messages"></a><span data-ttu-id="56c0f-146">搜索并删除邮件</span><span class="sxs-lookup"><span data-stu-id="56c0f-146">Search and delete messages</span></span>
<span data-ttu-id="56c0f-147"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="56c0f-147"></span></span>

<span data-ttu-id="56c0f-p113">本示例在 April Stewart 的邮箱中搜索 Subject 字段中包含"Your bank statement"短语的邮件，然后从源邮箱中删除这些邮件，而不将搜索结果复制到另一个文件夹。如前所述，您需要分配"邮箱导入导出"管理角色才能从用户邮箱删除邮件。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p113">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field and deletes the messages from the source mailbox without copying the search results to another folder. As previously explained, you need to be assigned the Mailbox Import Export management role to delete messages from a user's mailbox.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="56c0f-p114">在使用带有  **DeleteContent** 开关的 _Search-Mailbox_ cmdlet 时，会从源邮箱中永久删除邮件。在永久删除邮件之前，建议您在删除搜索中找到的邮件之前使用  _LogOnly_ 开关生成这些邮件的日志，或是在从源邮箱中删除这些邮件之前将其复制到另一个邮箱。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p114">When you use the **Search-Mailbox** cmdlet with the  _DeleteContent_ switch, messages are permanently deleted from the source mailbox. Before you permanently delete messages, we recommend that you either use the  _LogOnly_ switch to generate a log of the messages found in the search before they're deleted or copy the messages to another mailbox before deleting them from the source mailbox.</span></span> 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

<span data-ttu-id="56c0f-152">本示例在 April Stewart 的邮箱中搜索 Subject 字段中包含"Your bank statement"短语的邮件，将搜索结果复制到 BackupMailbox 邮箱中的 AprilStewart-DeletedMessages 文件夹，然后从 April 的邮箱中删除这些邮件。</span><span class="sxs-lookup"><span data-stu-id="56c0f-152">This example searches April Stewart's mailbox for messages that contain the phrase "Your bank statement" in the Subject field, copies the search results to the folder AprilStewart-DeletedMessages in the mailbox BackupMailbox, and deletes the messages from April's mailbox.</span></span>
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

<span data-ttu-id="56c0f-153">此示例将搜索组织的所有邮箱，查找主题行为"下载此文件"邮件，然后将其永久删除。</span><span class="sxs-lookup"><span data-stu-id="56c0f-153">This example searches all mailboxes in the organization for messages with the subject line "Download this file", and then permanently deletes them.</span></span> 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

<span data-ttu-id="56c0f-154">有关详细的语法和参数信息，请参阅 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。</span><span class="sxs-lookup"><span data-stu-id="56c0f-154">For detailed syntax and parameter information, see [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx).</span></span>
  
[<span data-ttu-id="56c0f-155">返回顶部</span><span class="sxs-lookup"><span data-stu-id="56c0f-155">Return to top</span></span>](search-for-and-delete-messagesadmin-help.md#top)
  
## <a name="using-the--loglevel-full-parameter"></a><span data-ttu-id="56c0f-156">使用 -LogLevel Full 参数</span><span class="sxs-lookup"><span data-stu-id="56c0f-156">Using the -LogLevel Full parameter</span></span>
<span data-ttu-id="56c0f-157"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="56c0f-157"></span></span>

<span data-ttu-id="56c0f-p115">在上述部分示例中， _LogLevel_ 参数和  `Full` 值用于记录由 **Search-Mailbox** cmdlet 返回的结果的详细信息。 包含此参数时，将创建电子邮件并将其发送到  _TargetMailbox_ 参数指定的邮箱。日志文件（名为 Search Results.csv 的 CSV 格式文件）附加到此电子邮件，并置于由  _TargetFolder_ 参数指定的文件夹中。运行 **Search-Mailbox** cmdlet 时，日志文件包含搜索结果中的每个邮件的行。</span><span class="sxs-lookup"><span data-stu-id="56c0f-p115">In some of the previous examples, the  _LogLevel_ parameter, with the  `Full` value is used to log detailed information about the results returned by the **Search-Mailbox** cmdlet. When you included this parameter, an email message is created and sent to the mailbox specified by the  _TargetMailbox_ parameter. The log file (which is a CSV-formatted file named Search Results.csv) is attached to this email message, and will be located in the folder specified by the  _TargetFolder_ parameter. The log file contains a row for each message that's included in the search results when you run the **Search-Mailbox** cmdlet.</span></span> 
  
