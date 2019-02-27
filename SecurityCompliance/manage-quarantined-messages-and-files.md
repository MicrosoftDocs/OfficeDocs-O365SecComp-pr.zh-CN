---
title: 以 Office 365 中的管理员身份管理隔离的邮件和文件
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 09/05/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: '作为管理员, 您可以在 Office 365 中查看、释放和报告误报的已隔离邮件。您可以设置策略, 以便 Office 365 筛选邮件并将其发送到隔离区, 原因如下: 因为它们被标识为垃圾邮件、批量、网络钓鱼和恶意软件, 或者它们与邮件流规则匹配。 '
ms.openlocfilehash: 797a2e54d6f0a0b1f0d06bd287dd636988f078b5
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276262"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator-in-office-365"></a><span data-ttu-id="fe7d1-104">以 Office 365 中的管理员身份管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="fe7d1-104">Manage quarantined messages and files as an administrator in Office 365</span></span>

<span data-ttu-id="fe7d1-p102">作为管理员, 您可以查看、释放和删除隔离邮件, 并在 Office 365 中报告假正隔离邮件。您还可以查看、下载和删除由 SharePoint Online、OneDrive for business 和 Microsoft 团队的高级威胁防护 (ATP) 捕获的隔离文件。您可以设置策略, 以便 Office 365 筛选邮件并将其发送到隔离区, 原因如下: 因为它们被标识为垃圾邮件、批量邮件、网络钓鱼邮件、包含恶意软件, 或者它们与邮件流规则匹配。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p102">As an admin, you can view, release, and delete quarantined messages, and report false positive quarantined messages in Office 365. You can also view, download, and delete quarantined files captured by Advance Threat Protection (ATP) for SharePoint Online, OneDrive for Business, and Microsoft Teams. You can set up policies so that Office 365 filters messages and sends them to quarantine for several reasons: Because they were identified as spam, bulk mail, phishing mail, containing malware, or because they matched a mail flow rule.</span></span>
  
<span data-ttu-id="fe7d1-p103">默认情况下, Office 365 将包含恶意软件的网络钓鱼邮件和邮件直接发送到隔离。其他筛选出的邮件将发送给用户的 "垃圾邮件" 文件夹, 除非您将策略设置为将其发送到隔离区。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p103">By default, Office 365 sends phishing messages and messages containing malware directly to quarantine. Other filtered messages are sent to users' Junk Email folder unless you set up a policy to send them to quarantine.</span></span>
  
<span data-ttu-id="fe7d1-110">您必须在 Office 365 中具有全局管理员 (GA) 权限, 才能处理发送给其他用户并使用隔离文件的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-110">You must have global administrator (GA) permissions in Office 365 to work with quarantined messages that were sent to other users and to work with quarantined files.</span></span>
  
> [!IMPORTANT]
><span data-ttu-id="fe7d1-p104">默认情况下, 垃圾邮件、批量和网络钓鱼邮件在30天内保持隔离状态。由于与邮件流规则匹配而被隔离的邮件将保留在7天内的隔离中。恶意软件邮件在15天内保留在隔离中。可以在安全&amp;合规性中心的 "反垃圾邮件" 设置中自定义垃圾邮件隔离时间。当 Office 365 从隔离区中删除邮件时, 无法将其恢复。如果你愿意, 可以在反垃圾邮件筛选器策略中更改隔离邮件的保留期。有关详细信息, 请参阅本文中[的设置隔离保留期](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime)。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p104">By default, spam, bulk and phishing messages are kept in quarantine for 30 days. Messages that are quarantined because they matched a mail flow rule are kept in quarantine for 7 days. Malware messages are kept in quarantine for 15 days. You can customize the spam quarantine time in anti-spam settings in the Security &amp; Compliance Center. When Office 365 deletes a message from quarantine, you can't get it back. If you like, you can change the retention period for quarantined messages in your anti-spam filter policies. For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in this article.</span></span> 
  
## <a name="view-your-organizations-quarantined-messages"></a><span data-ttu-id="fe7d1-118">查看组织的隔离邮件</span><span class="sxs-lookup"><span data-stu-id="fe7d1-118">View your organization's quarantined messages</span></span>

1. <span data-ttu-id="fe7d1-119">在 office 365 组织中使用具有全局管理员权限的工作或学校帐户, 登录 office 365 并[转到 "安全与合规中心"](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-119">Using a work or school account that has global administrator privileges in your Office 365 organization, sign into Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="fe7d1-120">在左侧的列表中, 展开 "**威胁管理**", 选择 "**查看**", 然后选择 "**隔离**"。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-120">In the list on the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="fe7d1-121">若要直接转到\*\*\*\* 安全&amp;合规性中心中的隔离页, 请使用以下 URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="fe7d1-121">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>
  
    <span data-ttu-id="fe7d1-p105">默认情况下, 安全&amp;合规性中心显示已被隔离为垃圾邮件的所有电子邮件。根据收到邮件的**日期**, 从最新到最旧的邮件进行排序。对于每封邮件, 还会显示**发件人**、**主题**和到期日期 (**过期**时间)。您可以通过单击相应的列标题对字段进行排序;再次单击列标题可反转排序顺序。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p105">By default, the Security &amp; Compliance Center displays all email messages that have been quarantined as spam. The messages are sorted from newest to oldest based on the **Date** the message was received. **Sender**, **Subject**, and the expiration date (under **Expires** ) are also displayed for each message. You can sort on a field by clicking the corresponding column header; click a column header a second time to reverse the sort order.</span></span> 
    
3. <span data-ttu-id="fe7d1-p106">您可以查看所有隔离邮件的列表, 也可以通过筛选减少结果集。您只能对最多为100个项目执行批量操作, 因此筛选还有助于减少您的结果集 (如果有多个)。您可以通过在页面顶部的筛选器中选择一个选项来快速筛选邮件的一个隔离原因。选项包括:</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p106">You can view a list of all quarantined messages, or you can reduce the result set by filtering. You can only do bulk operations on up to 100 items, so filtering can also help reduce your result set if you have more than that. You can quickly filter messages for a single quarantine reason by choosing an option from the filter at the top of the page. Options include:</span></span>
    
  - <span data-ttu-id="fe7d1-130">被标识为垃圾邮件的邮件</span><span class="sxs-lookup"><span data-stu-id="fe7d1-130">Mail identified as spam</span></span>
    
  - <span data-ttu-id="fe7d1-131">邮件被隔离, 因为它与邮件流规则 (也称为传输规则) 设置的策略相匹配</span><span class="sxs-lookup"><span data-stu-id="fe7d1-131">Mail quarantined because it matched a policy set by a mail flow rule (also called a transport rule)</span></span>
    
  - <span data-ttu-id="fe7d1-132">邮件被标识为批量邮件</span><span class="sxs-lookup"><span data-stu-id="fe7d1-132">Mail identified as bulk mail</span></span>
    
  - <span data-ttu-id="fe7d1-133">邮件被标识为仿冒邮件</span><span class="sxs-lookup"><span data-stu-id="fe7d1-133">Mail identified as phishing mail</span></span>
    
  - <span data-ttu-id="fe7d1-134">邮件被隔离, 因为它包含恶意软件</span><span class="sxs-lookup"><span data-stu-id="fe7d1-134">Mail quarantined because it contains malware</span></span>
    
<span data-ttu-id="fe7d1-p107">此外, 作为管理员, 您可以选择为您的组织或仅为发送给您的邮件筛选所有邮件。最终用户只能查看和处理发送给他们的邮件。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p107">In addition, as an admin, you can choose to filter all messages for your organization or only messages sent to you. End users can only view and work with messages sent to them.</span></span>
  
<span data-ttu-id="fe7d1-p108">您还可以筛选结果以查找特定邮件。有关提示, 请参阅[筛选结果和在本文中查找隔离的邮件和文件](manage-quarantined-messages-and-files.md#BKMK_AdvSearch)。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p108">You can also filter your results to find specific messages. For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span> 
  
<span data-ttu-id="fe7d1-139">找到特定的隔离邮件后, 单击该邮件以查看其详细信息, 并执行操作, 如将邮件释放到某人的邮箱。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-139">After you find a specific quarantined message, click the message to view details about it, and take actions, like releasing the message to someone's mailbox.</span></span>
  
## <a name="view-your-organizations-quarantined-files"></a><span data-ttu-id="fe7d1-140">查看组织的隔离文件</span><span class="sxs-lookup"><span data-stu-id="fe7d1-140">View your organization's quarantined files</span></span>

1. <span data-ttu-id="fe7d1-141">在 office 365 组织中使用具有全局管理员权限的工作或学校帐户, 登录 office 365 并[转到 "安全与合规中心"](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-141">Using a work or school account that has global administrator privileges in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="fe7d1-142">在左侧, 展开 "**威胁管理**", 选择 "**查看**", 然后选择 "**隔离**"。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-142">On the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span> <br/>
    > [!TIP]
    > <span data-ttu-id="fe7d1-143">若要直接转到\*\*\*\* 安全&amp;合规性中心中的隔离页, 请使用以下 URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="fe7d1-143">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>
  
3. <span data-ttu-id="fe7d1-p109">默认情况下, 页面显示隔离的电子邮件。若要查看隔离的文件, 请将页面顶部的筛选器设置为显示**文件**, 并根据**恶意软件**进行隔离。您必须具有 Office 365 中的管理员权限才能使用隔离的文件。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p109">By default, the page displays quarantined email messages. To view quarantined files, set the filters at the top of the page to show **files**, quarantined due to **malware**. You must have admin permissions in Office 365 to work with quarantined files.</span></span> 
    
4. <span data-ttu-id="fe7d1-p110">根据文件被隔离的日期, 从最新到最旧对文件进行排序。上次修改文件的**用户**、文件所发布到的**服务**、文件名、**位置**、**文件大小**和到期日期 (**过期**) 也将列出给每个文件。 \*\*\*\* 您可以通过单击某个标头对该字段进行排序;再次单击列标题可反转排序顺序。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p110">The files are sorted from newest to oldest based on the date the file was quarantined. The **User** who last modified the file, the **Service** to which the file was posted, the **File Name**, **Location**, **File Size**, and the expiration date ( **Expires**) are also listed for each file. You can sort on a field by clicking a header; click a column header a second time to reverse the sort order.</span></span>
    
<span data-ttu-id="fe7d1-p111">您可以查看所有隔离文件的列表, 也可以通过筛选来搜索特定文件。就像邮件一样, 您只能对最大为100个项目执行批量操作。目前, 安全&amp;合规性中心允许你查看和管理隔离中的文件, 因为这些文件已被标识为包含恶意软件。有关提示, 请参阅[筛选结果和在本文中查找隔离的邮件和文件](manage-quarantined-messages-and-files.md#BKMK_AdvSearch)。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p111">You can view a list of all quarantined files, or you can search for specific files by filtering. Just like messages, you can only do bulk operations on up to 100 items. Currently, the Security &amp; Compliance Center lets you view and manage files that are in quarantine because they have been identified as containing malware. For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span> 
  
## <a name="to-filter-results-and-find-quarantined-messages-and-files"></a><span data-ttu-id="fe7d1-154">筛选结果并查找隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="fe7d1-154">To filter results and find quarantined messages and files</span></span>
<span data-ttu-id="fe7d1-155"><a name="BKMK_AdvSearch"> </a></span><span class="sxs-lookup"><span data-stu-id="fe7d1-155"></span></span>

<span data-ttu-id="fe7d1-p112">根据你的设置, 可能会有大量隔离的邮件和文件。若要查找特定的邮件或文件或一组邮件或文件, 可以根据各种其他信息筛选隔离项目。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p112">Depending on your settings, there may be a lot of quarantined messages and files. To find a specific message or file or set of messages or files, you can filter quarantined items based on a variety of additional information.</span></span>
  
1. <span data-ttu-id="fe7d1-158">在 "**隔离**" 页面上, 确保 "筛选器首行" 设置为根据需要显示邮件或文件:</span><span class="sxs-lookup"><span data-stu-id="fe7d1-158">On the **Quarantine** page, ensure that the top row of filters is set to display messages or files as appropriate:</span></span> 
    
      - <span data-ttu-id="fe7d1-159">若要搜索文件, 请将筛选器设置为显示由于**恶意软件**而隔离的**文件**。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-159">To search for files, set the filters to show **files** quarantined due to **malware**.</span></span><br/>
    <span data-ttu-id="fe7d1-160">对于隔离的文件, 页面将显示所有隔离的文件, 而不只是您自己的文件, 而不考虑您告诉它显示的内容。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-160">For quarantined files, the page displays all quarantined files, not just your own, regardless of what you tell it to show.</span></span>
    
      - <span data-ttu-id="fe7d1-p113">若要搜索隔离邮件, 请将筛选器设置为显示**所有**或**仅显示我**的**电子邮件**。对于最后一个筛选器, 选择您要查找的隔离邮件的类型。可以搜索与邮件流或**传输规则**匹配的邮件、**批量**邮件、**网络钓鱼**邮件或包含**恶意软件**的邮件的已标识为**垃圾**邮件的隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p113">To search for quarantined messages, set filters to show **all** or **only my** **email**. For the last filter choose the type of quarantined message that you're looking for. You can search for quarantined messages that have been identified as **spam**, for messages that matched a mail flow or **transport rule**, **bulk** mail, **phishing** mail, or mail that contains **malware**.</span></span>
    
2. <span data-ttu-id="fe7d1-p114">在 "**排序结果依据**" 下, 从下拉列表中选择要用于搜索的筛选器或筛选器。根据您是否要搜索文件或邮件, 选项会有所不同。搜索字段中目前不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p114">Under **Sort results by**, choose the filter or filters you want to use to search from the drop-down lists. The options vary based on whether you are searching for files or messages. Wildcards are not supported in search fields at this time.</span></span><br/><br/><span data-ttu-id="fe7d1-p115">对于文件和邮件, 您可以选择按邮件或文件发送到隔离时的日期进行筛选。您可以指定日期或日期范围, 包括时间。您还可以按过期日期筛选搜索结果, 将从隔离区中删除文件或邮件, 也可以使用筛选器组合。若要按过期日期进行搜索, 请选择 "**高级筛选**"。在 "**过期**" 下, 可以选择将在接下来的24小时内 ("**今天**")、接下来的48小时 (**接下来2天**)、下一周内 ("**接下来7天**") 中删除隔离的邮件, 也可以选择自定义时间间隔。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p115">For both files and messages, you can choose to filter by the date the message or file was sent to quarantine. You can specify the date or a date range, including the time. You can also filter your search results by the expiration date on which the file or message will be deleted from quarantine, or you can use a combination of filters. To search by expiration date, choose **Advanced filter**. Under **Expires**, you can select messages that will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval.</span></span><br/><br/><span data-ttu-id="fe7d1-172">对于邮件, 您可以使用以下其他选项:</span><span class="sxs-lookup"><span data-stu-id="fe7d1-172">For messages, you have the following additional options:</span></span>
    
      - <span data-ttu-id="fe7d1-p116">**邮件 ID**。当您知道邮件 ID 时, 可以使用它来标识特定邮件。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p116">**Message ID**. Use this to identify a specific message when you know the message ID.</span></span><br/><br/><span data-ttu-id="fe7d1-p117">例如, 如果您的组织中的用户发送或预定某个特定的邮件, 但它从未到达其目标, 则可以使用邮件跟踪 (请参阅[运行邮件跟踪和查看结果](https://go.microsoft.com/fwlink/?LinkId=799737)) 搜索邮件。如果发现邮件已发送到隔离, 可能是因为它与邮件流规则匹配或被标识为垃圾邮件, 那么您可以通过指定邮件 ID 来轻松地在隔离中查找此邮件。确保包含完整的邮件 ID 字符串。这可能包括尖括号 (\<\>), 例如:</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p117"> For example, if a specific message is sent by, or intended for, a user in your organization, but it never reached its destination, you can search for the message by using a message trace (see [Run a Message trace and View Results](https://go.microsoft.com/fwlink/?LinkId=799737)). If you discover that the message was sent to quarantine, perhaps because it matched a mail flow rule or was identified as spam, you can then easily find this message in quarantine by specifying its message ID. Be sure to include the full message ID string. This might include angle brackets (\<\>), for example:</span></span><br/>
    `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`
    
      - <span data-ttu-id="fe7d1-p118">**发件人电子邮件地址**。选择按单个发件人电子邮件地址进行筛选。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p118">**Sender email address**. Choose to filter by a single sender email address.</span></span> 
    
      - <span data-ttu-id="fe7d1-p119">**收件人电子邮件地址**。选择按单个收件人电子邮件地址进行筛选。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p119">**Recipient email address**. Choose to filter by a single recipient email address.</span></span> 
    
      - <span data-ttu-id="fe7d1-p120">**主题**。输入要查找的电子邮件地址的主题。由于不支持通配符搜索, 因此您必须使用邮件的整个主题, 搜索才会在结果中返回邮件。搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p120">**Subject**. Enter the subject of an email address you want to find. Since wildcard searching is not supported, you must use the entire subject of the message in order for search to return the message in the results. The search is not case-sensitive.</span></span> 
    
## <a name="view-details-about-quarantined-messages-and-files"></a><span data-ttu-id="fe7d1-187">查看有关隔离邮件和文件的详细信息</span><span class="sxs-lookup"><span data-stu-id="fe7d1-187">View details about quarantined messages and files</span></span>

<span data-ttu-id="fe7d1-188">当您选择隔离列表中显示的项目时, 将在安全&amp;合规性中心右侧的**详细信息**窗格中看到其属性的摘要。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-188">When you select an item displayed in the quarantine list, you'll see a summary of its properties in the **Details** pane on the right side of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="fe7d1-189">**为隔离邮件显示的详细信息**</span><span class="sxs-lookup"><span data-stu-id="fe7d1-189">**Details displayed for quarantined messages**</span></span>
  
- <span data-ttu-id="fe7d1-p121">**邮件 ID**。邮件的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p121">**Message ID**. The unique identifier for the message.</span></span> 
    
- <span data-ttu-id="fe7d1-p122">**发件人地址**。邮件的发件商。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p122">**Sender Address**. Who sent the message.</span></span> 
    
- <span data-ttu-id="fe7d1-p123">**收到**。接收邮件的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p123">**Received**. The date and time the message was received.</span></span> 
    
- <span data-ttu-id="fe7d1-p124">**主题**。邮件主题行的文本。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p124">**Subject**. The text of the subject line of the message.</span></span> 
    
- <span data-ttu-id="fe7d1-p125">**类型**。显示邮件是否已被标识为**垃圾**邮件、**批量**、**网络钓鱼**、与邮件流规则匹配 (**传输规则**), 或被标识为包含**恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p125">**Type**. Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule ( **Transport rule**), or was identified as containing **Malware**.</span></span>
    
- <span data-ttu-id="fe7d1-p126">**过期**。将自动从隔离区中删除邮件的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p126">**Expires**. The date and time when the message will automatically be deleted from quarantine.</span></span> 
    
- <span data-ttu-id="fe7d1-p127">已**发布到**。邮件已释放到的所有电子邮件地址 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p127">**Released to**. All email addresses (if any) to which the message has been released.</span></span> 
    
- <span data-ttu-id="fe7d1-p128">**尚未发布到**。邮件尚未发布的所有电子邮件地址 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p128">**Not yet released to**. All email addresses (if any) to which the message has not yet been released.</span></span> 
    
 <span data-ttu-id="fe7d1-206">**为隔离文件显示的详细信息**</span><span class="sxs-lookup"><span data-stu-id="fe7d1-206">**Details displayed for quarantined files**</span></span>
  
- <span data-ttu-id="fe7d1-207">\*\*\*\* 文件名隔离中的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-207">**File Name** The name of the file in quarantine.</span></span> 
    
- <span data-ttu-id="fe7d1-208">**网站路径**定义文件在 Office 365 中的位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-208">**Site path** URL that defines the location of the file in Office 365.</span></span> 
    
- <span data-ttu-id="fe7d1-209">**检测到的日期/时间**文件被隔离的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-209">**Detected Date / Time** The date and time the file was quarantined.</span></span> 
    
- <span data-ttu-id="fe7d1-210">**过期**将从隔离区中删除邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-210">**Expires** The date when the message will be deleted from quarantine.</span></span> 
    
- <span data-ttu-id="fe7d1-p129">**检测人**用于检测文件中的恶意软件的方法。这可以是 ATP (高级威胁防护), 也可以是 Microsoft 的反恶意软件引擎。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p129">**Detected By** The method used to detect the malware in the file. This can be either ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span> 
    
- <span data-ttu-id="fe7d1-213">已**发布**描述文件是否已释放。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-213">**Released** Describes whether or not the file has been released.</span></span> 
    
- <span data-ttu-id="fe7d1-214">**恶意软件名称**文件中检测到的恶意软件的系列和名称。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-214">**Malware Name** Family and name of the malware detected in the file.</span></span> 
    
- <span data-ttu-id="fe7d1-215">**文档 ID**文档的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-215">**Document ID** A unique identifier for the document.</span></span> 
    
- <span data-ttu-id="fe7d1-216">**文件大小**文件大小 (以 KB 为单位)。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-216">**File Size** The size of the file in KB.</span></span> 
    
- <span data-ttu-id="fe7d1-217">**组织**您的组织在 Office 365 中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-217">**Organization** Your organization's unique ID in Office 365.</span></span> 
    
- <span data-ttu-id="fe7d1-218">**修改者**上次修改文件的用户的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-218">**Modified By** The work or school account of the user who last modified the file.</span></span> 
    
- <span data-ttu-id="fe7d1-219">**文件大小**文件大小 (以 KB 为单位)。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-219">**File Size** The size of the file in KB.</span></span> 
    
- <span data-ttu-id="fe7d1-p130">**SHA256 哈希**文件的哈希值。您可以使用它来查找其他信誉存储, 或调查该文件在您的环境中的其他位置。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p130">**SHA256 Hash** The hash of the file. You can use this to look up other reputation stores you may have or investigate where else the file might be in your environment.</span></span> 
    
## <a name="managing-messages-and-files-in-quarantine"></a><span data-ttu-id="fe7d1-222">管理隔离中的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="fe7d1-222">Managing messages and files in quarantine</span></span>
<span data-ttu-id="fe7d1-223"><a name="BKMK_ManageQuarantinedItem"> </a></span><span class="sxs-lookup"><span data-stu-id="fe7d1-223"></span></span>

<span data-ttu-id="fe7d1-224">选择一封邮件或一组邮件后, 您可以通过多个选项来管理隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-224">After you select a message or group of messages you have several options for managing messages in quarantine.</span></span>
  
- <span data-ttu-id="fe7d1-p131">不执行任何操作。如果选择不执行任何操作, 则在过期时, Office 365 将自动删除邮件。默认情况下, 因与邮件流规则匹配而隔离的垃圾邮件、批量、恶意软件、网络钓鱼和邮件将在30天内保留。当 Office 365 从隔离区中删除邮件时, 无法将其恢复。如果愿意, 可以通过在反垃圾邮件策略中配置 "**保留垃圾邮件 (天)** " 设置来更改隔离邮件的保留期。有关详细信息, 请参阅本文中[的设置隔离保留期](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime)。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p131">Do nothing. If you choose to do nothing, the message will be deleted by Office 365 automatically upon expiration. By default, spam, bulk, malware, phishing, and messages quarantined because they matched a mail flow rule are kept in quarantine for 30 days. When Office 365 deletes a message from quarantine, you can't get it back. If you like, you can change the retention period for quarantined messages by configuring the **Retain spam for (days)** setting in your anti-spam policies. For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in this article.</span></span> 
    
- <span data-ttu-id="fe7d1-p132">**查看邮件头**选择此链接可查看邮件头文本。若要分析深度的页眉, 请将邮件头文本复制到剪贴板, 然后选择 " **Microsoft 邮件头分析器**" 以转到远程连接分析器 (右键单击并选择 "**在新选项卡中打开**", 如果您不想离开 Office365完成此任务)。将邮件头粘贴到 "邮件头分析器" 部分中的页面上, 然后选择 "**分析邮件头**"。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p132">**View message header** Choose this link to see the message header text. To analyze the header in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**.</span></span>
    
- <span data-ttu-id="fe7d1-p133">**预览邮件**允许您查看邮件正文文本的原始版本或 HTML 版本。在 HTML 视图中, 链接被禁用。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p133">**Preview message** Lets you see raw or HTML versions of the message body text. In the HTML view, links are disabled.</span></span> 
    
- <span data-ttu-id="fe7d1-p134">**下载邮件**或**下载文件**。选择此选项可将邮件或文件的副本下载到本地设备。你需要确认你了解与从隔离区下载项目相关联的风险, 然后再允许你执行此操作。邮件以 .eml 格式保存到您指定的文件夹中。隔离的文件以其原始格式保存。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p134">**Download message** or **Download file**. Choose this option to download a copy of the message or file to your local device. You'll need to confirm that you understand the risks associated with downloading items from quarantine before you'll be allowed to do so. Messages are saved in .eml format to a folder you specify. Quarantined files are saved in their original format.</span></span>
    
- <span data-ttu-id="fe7d1-p135">**删除**如果需要, 可以立即删除隔离项目 (或项目集), 而不是等待 Office 365 设置的过期日期。若要删除邮件或文件, 请在 "隔离" 列表中选择该项目, 然后选择 "**删除**"。若要一次删除多个项目, 请选中 "隔离" 列表中项目左侧的复选框, 然后在出现的 "**批量操作**" 页面上, 选择 "**删除所选邮件**" 或 "**删除所选文件**"。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p135">**Delete** If you want, you can immediately delete a quarantined item (or set of items) instead of waiting for the expiration date set by Office 365. To delete a message or file, in the quarantine list, select the item and then choose **Delete**. To delete multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Delete selected messages** or **Delete selected files**.</span></span>
    
- <span data-ttu-id="fe7d1-243">**版本**释放隔离项目 (或项目集), 并将项目报告为 "虚假隔离 (误报)" 到 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-243">**Release** Release a quarantined item (or set of items) and report the items as falsely quarantined (false positives) to Microsoft.</span></span> 
    
    <span data-ttu-id="fe7d1-p136">若要释放和报告单个邮件或文件, 请在 "隔离" 列表中选择该项目, 然后选择 "**释放文件**" 或 "**释放邮件**"。在下一页上, 确保已选择 "**将邮件发送给 microsoft 进行分析**或将**报告文件报告给 microsoft 进行分析**"。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p136">To release and report a single message or file, in the quarantine list, select the item, choose **Release file** or **Release message**. On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span> 
    
    <span data-ttu-id="fe7d1-p137">若要一次释放多个项目, 请选中 "隔离" 列表中项目左侧的复选框, 然后在出现的 "**批量操作**" 页面上, 选择 "**释放文件**" 或 "**释放邮件**"。在下一页上, 确保已选择 "**将邮件发送给 microsoft 进行分析**或将**报告文件报告给 microsoft 进行分析**"。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p137">To release multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Release files** or **Release messages**. On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span> 
    
<span data-ttu-id="fe7d1-248">当您释放邮件时, 请注意以下事项:</span><span class="sxs-lookup"><span data-stu-id="fe7d1-248">When you're releasing messages, be aware of the following:</span></span>
  
- <span data-ttu-id="fe7d1-p138">当您同时执行多个邮件的批量释放时, 邮件将被释放给所有最初标识的收件人。如果只想要将邮件仅发布给特定收件人, 则需要一次释放一封邮件, 并单独标识收件人。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p138">When you perform a bulk release of multiple messages at once, the messages are released to all originally identified recipients. If you only want to release messages only to specific recipients, you need to release the messages one at a time and identify the recipients individually.</span></span>
    
- <span data-ttu-id="fe7d1-251">一封邮件不能多次释放给同一个收件人。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-251">A message cannot be released more than once to the same recipient.</span></span>
    
- <span data-ttu-id="fe7d1-252">当您将邮件发布到多个收件人时, 只有未收到该邮件的收件人才会显示在潜在收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-252">When you're releasing a message to more than one recipient, only recipients who have not previously received the message will appear in the list of potential recipients.</span></span>
    
- <span data-ttu-id="fe7d1-p139">当您选择报告误报时, 如果您发布的一个或一封邮件被隔离为垃圾邮件、批量、网络钓鱼或包含恶意软件, 则还会向 Microsoft 垃圾邮件分析团队报告该邮件。团队将评估和分析邮件, 根据分析结果, 可能会调整服务范围的垃圾邮件内容筛选器规则, 以允许邮件通过。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p139">When you choose to report false positives, if the message or messages you release were quarantined as spam, bulk, phishing, or as containing malware, the message will also be reported to the Microsoft Spam Analysis Team. The team will evaluate and analyze the message, and, depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>
    
## <a name="setting-the-quarantine-retention-period"></a><span data-ttu-id="fe7d1-255">设置隔离保留期</span><span class="sxs-lookup"><span data-stu-id="fe7d1-255">Setting the quarantine retention period</span></span>
<span data-ttu-id="fe7d1-256"><a name="BKMK_ModQuarantineTime"> </a></span><span class="sxs-lookup"><span data-stu-id="fe7d1-256"></span></span>

<span data-ttu-id="fe7d1-p140">您可以配置邮件和文件在过期前的保留时间。默认情况下, 隔离项目将保留30天。为您创建的每个策略配置此设置。您还可以修改默认策略的值, 如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p140">You can configure how long messages and files will remain in quarantine before they expire. By default, quarantined items are kept for 30 days. You configure this setting for each policy that you create. You can also modify the value for the default policy as described in this article.</span></span> 
  
### <a name="to-modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security-and-compliance-center"></a><span data-ttu-id="fe7d1-261">在安全与合规中心中修改默认垃圾邮件筛选器策略的隔离保留期</span><span class="sxs-lookup"><span data-stu-id="fe7d1-261">To modify the quarantine retention period for the default spam filter policy in the Security and Compliance Center</span></span>

1. <span data-ttu-id="fe7d1-262">在 office 365 组织中使用具有全局管理员权限的工作或学校帐户, 登录 office 365 并[转到 "安全与合规中心"](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-262">Using a work or school account that has global administrator privileges in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="fe7d1-263">在左侧, 展开 "**威胁管理**", 选择 "**策略**", 然后选择 "**反垃圾邮件**"。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-263">On the left, expand **Threat Management**, choose **Policy**, and then choose **Anti-spam**.</span></span> <br/>
    > [!TIP]
    > <span data-ttu-id="fe7d1-264">若要直接转到安全&amp;合规性中心中的**反垃圾邮件**页面, 请使用以下 URL: >[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span><span class="sxs-lookup"><span data-stu-id="fe7d1-264">To go directly to the **anti-spam** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span></span>
  
3. <span data-ttu-id="fe7d1-265">选择 "**自定义**" 以显示 "**自定义设置**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-265">Choose **Custom** to display the **Custom settings** tab.</span></span> 
    
4. <span data-ttu-id="fe7d1-266">展开 "**默认垃圾邮件筛选器策略 (总是打开)** " 行。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-266">Expand the **Default spam filter policy (always ON)** row.</span></span> 
    
5. <span data-ttu-id="fe7d1-p141">选择 "**编辑策略**"。默认垃圾邮件筛选器策略的设置将显示在新页面中。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p141">Choose **Edit policy**. The settings for the default spam filter policy appear in a new page.</span></span>
    
6. <span data-ttu-id="fe7d1-269">展开**垃圾邮件和批量操作**。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-269">Expand **Spam and bulk actions**.</span></span>
    
7. <span data-ttu-id="fe7d1-p142">在 "**隔离**" 下的 "**保留垃圾邮件 (天)** " 文本框中, 输入您希望 Office 365 在隔离中保留邮件和文件的时间量。默认值为30天。这也是最大值。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-p142">Under **Quarantine**, in the **Retain spam for (days)** text box, enter the amount of time you want Office 365 to retain messages and files in quarantine. The default is 30 days. This is also the maximum.</span></span> 
    
8. <span data-ttu-id="fe7d1-273">选择" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="fe7d1-273">Choose **Save**.</span></span>
    

