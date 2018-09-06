---
title: 为 Office 365 中的管理员管理隔离的邮件和文件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 09/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
description: '作为一名管理员，您可以查看、 释放和报告误报隔离的邮件 Office 365 中。您可以设置策略，以便 Office 365 筛选消息，并将其原因有多种隔离发送： 因为他们已标识为垃圾邮件、 批量、 网络钓鱼、 恶意软件，或者因为它们匹配的邮件流规则。 '
ms.openlocfilehash: be6384d8937e25aec55d82d8212c49d25b64b9a1
ms.sourcegitcommit: d85fc77cba3a17d5ddf215e2f506f61b499e0cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "23839096"
---
# <a name="manage-quarantined-messages-and-files-as-an-administrator-in-office-365"></a><span data-ttu-id="632b6-104">为 Office 365 中的管理员管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="632b6-104">Manage quarantined messages and files as an administrator in Office 365</span></span>

<span data-ttu-id="632b6-p102">作为一名管理员，您可以查看、 释放，并删除隔离的邮件，和报告误报隔离的邮件 Office 365 中。您还可以查看、 下载和删除捕获的高级威胁保护 (ATP) 的 SharePoint Online、 OneDrive for Business 和 Microsoft 团队的隔离的文件。您可以设置策略，以便 Office 365 筛选消息，并将其原因有多种隔离发送： 因为他们已标识为垃圾邮件，批量邮件、 网络钓鱼邮件，包含恶意软件，或者因为它们匹配的邮件流规则。</span><span class="sxs-lookup"><span data-stu-id="632b6-p102">As an admin, you can view, release, and delete quarantined messages, and report false positive quarantined messages in Office 365. You can also view, download, and delete quarantined files captured by Advance Threat Protection (ATP) for SharePoint Online, OneDrive for Business, and Microsoft Teams. You can set up policies so that Office 365 filters messages and sends them to quarantine for several reasons: Because they were identified as spam, bulk mail, phishing mail, containing malware, or because they matched a mail flow rule.</span></span>
  
<span data-ttu-id="632b6-p103">默认情况下，Office 365 发送网络钓鱼邮件和邮件包含恶意软件直接到隔离。其他筛选的邮件被发送到用户的垃圾邮件文件夹，除非策略设置发送到隔离。</span><span class="sxs-lookup"><span data-stu-id="632b6-p103">By default, Office 365 sends phishing messages and messages containing malware directly to quarantine. Other filtered messages are sent to users' Junk Email folder unless you set up a policy to send them to quarantine.</span></span>
  
<span data-ttu-id="632b6-110">Office 365 使用发送到其他用户的隔离邮件并使用隔离文件中，您必须具有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="632b6-110">You must have admin permissions in Office 365 to work with quarantined messages that were sent to other users and to work with quarantined files.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="632b6-p104">默认情况下垃圾邮件、 批量、 恶意软件、 网络钓鱼和已隔离，因为它们与邮件流规则匹配的邮件将保留在隔离 30 天。您可以自定义安全中的反垃圾邮件设置的隔离时间&amp;合规性中心。Office 365 从隔离区中删除一条消息时, 不能将其恢复。如果您愿意，您可以在您的反垃圾邮件筛选器策略更改隔离邮件的保留的期。有关详细信息，请参阅本文中的[Setting 隔离的保留期](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime)。</span><span class="sxs-lookup"><span data-stu-id="632b6-p104">By default, spam, bulk, malware, phishing, and messages that were quarantined because they matched a mail flow rule are kept in quarantine for 30 days. You can customize the quarantine time in anti-spam settings in the Security &amp; Compliance Center. When Office 365 deletes a message from quarantine, you can't get it back. If you like, you can change the retention period for quarantined messages in your anti-spam filter policies. For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in this article.</span></span> 
  
## <a name="view-your-organizations-quarantined-messages"></a><span data-ttu-id="632b6-116">查看贵组织的隔离的邮件</span><span class="sxs-lookup"><span data-stu-id="632b6-116">View your organization's quarantined messages</span></span>

1. <span data-ttu-id="632b6-117">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，登录到 Office 365 并[转到的安全性和合规性中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="632b6-117">Using a work or school account that has global administrator privileges in your Office 365 organization, sign into Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="632b6-118">在左侧列表中，展开**威胁管理**，选择**查看**，，然后选择**隔离**。</span><span class="sxs-lookup"><span data-stu-id="632b6-118">In the list on the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="632b6-119">若要直接转到安全中的**隔离**页上&amp;合规性中心，使用以下 URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="632b6-119">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>
  
    <span data-ttu-id="632b6-p105">默认情况下，安全&amp;合规性中心显示为垃圾邮件已隔离的所有电子邮件。邮件是从降序基于排序收到邮件的**日期**。关于每封邮件还显示**发件人**、**主题**和 （在下**Expires** ) 的到期日期。可以通过单击相应的列标题; 来对字段排序第二次单击列标题反转排序顺序。</span><span class="sxs-lookup"><span data-stu-id="632b6-p105">By default, the Security &amp; Compliance Center displays all email messages that have been quarantined as spam. The messages are sorted from newest to oldest based on the **Date** the message was received. **Sender**, **Subject**, and the expiration date (under **Expires** ) are also displayed for each message. You can sort on a field by clicking the corresponding column header; click a column header a second time to reverse the sort order.</span></span> 
    
3. <span data-ttu-id="632b6-p106">您可以查看所有隔离邮件、 列表或可以减少结果集中筛选。您可以仅执行批量操作达 100 个项目，以便筛选还有助于降低您的结果如果您有多个设置。通过从页面顶部的筛选器选择一个选项，可以快速单个隔离原因筛选邮件。选项包括：</span><span class="sxs-lookup"><span data-stu-id="632b6-p106">You can view a list of all quarantined messages, or you can reduce the result set by filtering. You can only do bulk operations on up to 100 items, so filtering can also help reduce your result set if you have more than that. You can quickly filter messages for a single quarantine reason by choosing an option from the filter at the top of the page. Options include:</span></span>
    
  - <span data-ttu-id="632b6-128">邮件标识为垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="632b6-128">Mail identified as spam</span></span>
    
  - <span data-ttu-id="632b6-129">由于它匹配的策略设置邮件流规则 （也称作传输规则） 隔离邮件</span><span class="sxs-lookup"><span data-stu-id="632b6-129">Mail quarantined because it matched a policy set by a mail flow rule (also called a transport rule)</span></span>
    
  - <span data-ttu-id="632b6-130">邮件标识为批量邮件</span><span class="sxs-lookup"><span data-stu-id="632b6-130">Mail identified as bulk mail</span></span>
    
  - <span data-ttu-id="632b6-131">邮件标识为网络钓鱼邮件</span><span class="sxs-lookup"><span data-stu-id="632b6-131">Mail identified as phishing mail</span></span>
    
  - <span data-ttu-id="632b6-132">隔离因为它包含恶意软件的邮件</span><span class="sxs-lookup"><span data-stu-id="632b6-132">Mail quarantined because it contains malware</span></span>
    
<span data-ttu-id="632b6-p107">另外，作为一名管理员，您可以选择筛选器为您的组织的所有邮件或仅发送给您的邮件。结束用户可以仅查看和使用向他们发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="632b6-p107">In addition, as an admin, you can choose to filter all messages for your organization or only messages sent to you. End users can only view and work with messages sent to them.</span></span>
  
<span data-ttu-id="632b6-p108">您可以筛选结果以查找特定的邮件。提示，请参阅[来筛选结果和查找隔离的邮件和文件](manage-quarantined-messages-and-files.md#BKMK_AdvSearch)本文中。</span><span class="sxs-lookup"><span data-stu-id="632b6-p108">You can also filter your results to find specific messages. For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span> 
  
<span data-ttu-id="632b6-137">查找特定的隔离的邮件后，单击该消息即可查看详细信息，并执行操作，如释放消息与某人的收件箱。</span><span class="sxs-lookup"><span data-stu-id="632b6-137">After you find a specific quarantined message, click the message to view details about it, and take actions, like releasing the message to someone's inbox.</span></span>
  
## <a name="view-your-organizations-quarantined-files"></a><span data-ttu-id="632b6-138">查看贵组织的隔离的文件</span><span class="sxs-lookup"><span data-stu-id="632b6-138">View your organization's quarantined files</span></span>

1. <span data-ttu-id="632b6-139">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，登录到 Office 365 和[转到的安全性和合规性中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="632b6-139">Using a work or school account that has global administrator privileges in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="632b6-140">在左侧，展开**威胁管理**，选择**审阅**，，然后选择**隔离**。</span><span class="sxs-lookup"><span data-stu-id="632b6-140">On the left, expand **Threat Management**, choose **Review**, and then choose **Quarantine**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="632b6-141">若要直接转到安全中的**隔离**页上&amp;合规性中心，使用以下 URL: >[https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span><span class="sxs-lookup"><span data-stu-id="632b6-141">To go directly to the **Quarantine** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/quarantine](https://protection.office.com/?hash=/quarantine)</span></span>
  
3. <span data-ttu-id="632b6-p109">默认情况下，页上显示隔离的电子邮件。若要查看隔离的文件，设置顶部的页后，可以显示隔离的**文件**，由于**恶意软件**筛选器。Office 365 使用隔离文件中，您必须具有管理员权限。</span><span class="sxs-lookup"><span data-stu-id="632b6-p109">By default, the page displays quarantined email messages. To view quarantined files, set the filters at the top of the page to show **files**, quarantined due to **malware**. You must have admin permissions in Office 365 to work with quarantined files.</span></span> 
    
4. <span data-ttu-id="632b6-p110">文件被排序从降序基于文件被隔离的日期。**用户**上次修改文件的文件，**服务**向其发布文件，**位置****文件名**、**文件大小**，和到期日期 ( **Expires**) 还会列出每个。可以通过单击标题，则来对字段排序第二次单击列标题反转排序顺序。</span><span class="sxs-lookup"><span data-stu-id="632b6-p110">The files are sorted from newest to oldest based on the date the file was quarantined. The **User** who last modified the file, the **Service** to which the file was posted, the **File Name**, **Location**, **File Size**, and the expiration date ( **Expires**) are also listed for each file. You can sort on a field by clicking a header; click a column header a second time to reverse the sort order.</span></span>
    
<span data-ttu-id="632b6-p111">您可以查看所有隔离文件的列表，或通过筛选搜索特定的文件。一样消息，只能执行批量操作达 100 个项目。目前，安全&amp;合规性中心允许您查看和管理正在隔离，因为它们被标识为包含恶意软件的文件。提示，请参阅[来筛选结果和查找隔离的邮件和文件](manage-quarantined-messages-and-files.md#BKMK_AdvSearch)本文中。</span><span class="sxs-lookup"><span data-stu-id="632b6-p111">You can view a list of all quarantined files, or you can search for specific files by filtering. Just like messages, you can only do bulk operations on up to 100 items. Currently, the Security &amp; Compliance Center lets you view and manage files that are in quarantine because they have been identified as containing malware. For tips, see [To filter results and find quarantined messages and files](manage-quarantined-messages-and-files.md#BKMK_AdvSearch) in this article.</span></span> 
  
## <a name="to-filter-results-and-find-quarantined-messages-and-files"></a><span data-ttu-id="632b6-152">若要筛选结果，并查找隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="632b6-152">To filter results and find quarantined messages and files</span></span>
<span data-ttu-id="632b6-153"><a name="BKMK_AdvSearch"> </a></span><span class="sxs-lookup"><span data-stu-id="632b6-153"></span></span>

<span data-ttu-id="632b6-p112">根据您的设置，可能有大量的隔离的邮件和文件。要查找特定的邮件或文件或消息或文件的设置，可以筛选隔离根据不同的其他信息的项目。</span><span class="sxs-lookup"><span data-stu-id="632b6-p112">Depending on your settings, there may be a lot of quarantined messages and files. To find a specific message or file or set of messages or files, you can filter quarantined items based on a variety of additional information.</span></span>
  
1. <span data-ttu-id="632b6-156">在**隔离**页上，确保筛选器的顶行设置以根据需要显示消息或文件:</span><span class="sxs-lookup"><span data-stu-id="632b6-156">On the **Quarantine** page, ensure that the top row of filters is set to display messages or files as appropriate:</span></span> 
    
  - <span data-ttu-id="632b6-157">若要搜索的文件，设置为显示隔离由于**恶意软件****文件**的筛选器。</span><span class="sxs-lookup"><span data-stu-id="632b6-157">To search for files, set the filters to show **files** quarantined due to **malware**.</span></span>
    
    <span data-ttu-id="632b6-158">对于隔离文件，该页将显示所有被隔离的文件，而不仅仅是显示您自己的情况下，无论您的判断 it。</span><span class="sxs-lookup"><span data-stu-id="632b6-158">For quarantined files, the page displays all quarantined files, not just your own, regardless of what you tell it to show.</span></span>
    
  - <span data-ttu-id="632b6-p113">若要搜索的隔离邮件，设置筛选器以显示**所有**或**只有我****电子邮件**。最后一个筛选器选择的隔离邮件的类型为您要寻找。您可以搜索隔离被标识为**垃圾邮件**，为匹配的邮件流或**传输规则**、**批量**邮件、**网络钓鱼**邮件或包含**恶意软件**的邮件的邮件的邮件。</span><span class="sxs-lookup"><span data-stu-id="632b6-p113">To search for quarantined messages, set filters to show **all** or **only my** **email**. For the last filter choose the type of quarantined message that you're looking for. You can search for quarantined messages that have been identified as **spam**, for messages that matched a mail flow or **transport rule**, **bulk** mail, **phishing** mail, or mail that contains **malware**.</span></span>
    
2. <span data-ttu-id="632b6-p114">在**按结果进行排序**，下选择的筛选器或想要用于搜索下拉列表中的筛选器。根据您要搜索的文件或消息选项有所不同。不支持通配符在搜索字段中这一次。</span><span class="sxs-lookup"><span data-stu-id="632b6-p114">Under **Sort results by**, choose the filter or filters you want to use to search from the drop-down lists. The options vary based on whether you are searching for files or messages. Wildcards are not supported in search fields at this time.</span></span>
    
    <span data-ttu-id="632b6-p115">有关文件和消息，您可以选择按日期筛选邮件或文件被发送到隔离。您可以指定日期或日期范围，包括时间。您还可以通过在其的文件或消息将被删除，从隔离，或者您可以使用的筛选器组合的到期日期筛选搜索结果。若要搜索的到期日期，选择**高级筛选器**。下**过期**，您可以选择下一步 24 小时内 （**今天**） 下, 一步 48 小时内 （**下一步 2 天**），在下一周 （**下一步 7 天**），将从隔离区删除的消息，或选择自定义时间间隔。</span><span class="sxs-lookup"><span data-stu-id="632b6-p115">For both files and messages, you can choose to filter by the date the message or file was sent to quarantine. You can specify the date or a date range, including the time. You can also filter your search results by the expiration date on which the file or message will be deleted from quarantine, or you can use a combination of filters. To search by expiration date, choose **Advanced filter**. Under **Expires**, you can select messages that will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval.</span></span>
    
    <span data-ttu-id="632b6-170">对于邮件，必须对以下其他选项：</span><span class="sxs-lookup"><span data-stu-id="632b6-170">For messages, you have the following additional options:</span></span>
    
  - <span data-ttu-id="632b6-p116">**邮件 ID**。用于标识特定的邮件时您知道邮件 id。</span><span class="sxs-lookup"><span data-stu-id="632b6-p116">**Message ID**. Use this to identify a specific message when you know the message ID.</span></span> 
    
    <span data-ttu-id="632b6-p117">例如，如果发送，或专为在组织中用户特定的邮件，但它永远达到其目标，您可以搜索的邮件使用邮件跟踪 （请参阅[运行邮件跟踪和查看结果](https://go.microsoft.com/fwlink/?LinkId=799737)）。如果您发现邮件被发送到隔离，可能是因为它匹配的邮件流规则或被标识为垃圾邮件，然后，您可以轻松地找到此消息隔离通过指定其邮件 id。请确保包含完整的消息 ID 字符串。这可能包括尖括号 (\<\>)，例如：</span><span class="sxs-lookup"><span data-stu-id="632b6-p117">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reached its destination, you can search for the message by using a message trace (see [Run a Message trace and View Results](https://go.microsoft.com/fwlink/?LinkId=799737)). If you discover that the message was sent to quarantine, perhaps because it matched a mail flow rule or was identified as spam, you can then easily find this message in quarantine by specifying its message ID. Be sure to include the full message ID string. This might include angle brackets (\<\>), for example:</span></span>
    
    <span data-ttu-id="632b6-177">\<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\></span><span class="sxs-lookup"><span data-stu-id="632b6-177">\<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com\></span></span>
    
  - <span data-ttu-id="632b6-p118">**发件人电子邮件地址**。选择要筛选的单个发件人电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="632b6-p118">**Sender email address**. Choose to filter by a single sender email address.</span></span> 
    
  - <span data-ttu-id="632b6-p119">**收件人电子邮件地址**。选择要筛选的单个收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="632b6-p119">**Recipient email address**. Choose to filter by a single recipient email address.</span></span> 
    
  - <span data-ttu-id="632b6-p120">**主题**。输入您想要查找的电子邮件地址的主题。由于不支持通配符搜索，您必须使用整个邮件的主题顺序搜索结果中返回消息。搜索不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="632b6-p120">**Subject**. Enter the subject of an email address you want to find. Since wildcard searching is not supported, you must use the entire subject of the message in order for search to return the message in the results. The search is not case-sensitive.</span></span> 
    
## <a name="view-details-about-quarantined-messages-and-files"></a><span data-ttu-id="632b6-186">查看有关隔离的邮件和文件的详细信息</span><span class="sxs-lookup"><span data-stu-id="632b6-186">View details about quarantined messages and files</span></span>
<span data-ttu-id="632b6-187"><a name="BKMK_ViewDetails"> </a></span><span class="sxs-lookup"><span data-stu-id="632b6-187"></span></span>

<span data-ttu-id="632b6-188">当您选择隔离列表中显示的项时，您将看到其**详细信息**窗格中的属性摘要安全右侧&amp;合规性中心。</span><span class="sxs-lookup"><span data-stu-id="632b6-188">When you select an item displayed in the quarantine list, you'll see a summary of its properties in the **Details** pane on the right side of the Security &amp; Compliance Center.</span></span> 
  
 <span data-ttu-id="632b6-189">**显示的隔离邮件的详细信息**</span><span class="sxs-lookup"><span data-stu-id="632b6-189">**Details displayed for quarantined messages**</span></span>
  
- <span data-ttu-id="632b6-p121">**邮件 ID**。消息的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="632b6-p121">**Message ID**. The unique identifier for the message.</span></span> 
    
- <span data-ttu-id="632b6-p122">**发件人地址**。邮件发件人。</span><span class="sxs-lookup"><span data-stu-id="632b6-p122">**Sender Address**. Who sent the message.</span></span> 
    
- <span data-ttu-id="632b6-p123">**接收**。日期和时间收到邮件。</span><span class="sxs-lookup"><span data-stu-id="632b6-p123">**Received**. The date and time the message was received.</span></span> 
    
- <span data-ttu-id="632b6-p124">**主题**。邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="632b6-p124">**Subject**. The text of the subject line of the message.</span></span> 
    
- <span data-ttu-id="632b6-p125">**类型**。显示一条消息，是否已标识为**垃圾邮件**、**批量**、**网络钓鱼诈骗**，匹配的邮件流规则 （**传输规则**），或标识为包含**恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="632b6-p125">**Type**. Shows if a message has been identified as **Spam**, **Bulk**, **Phish**, matched a mail flow rule ( **Transport rule**), or was identified as containing **Malware**.</span></span>
    
- <span data-ttu-id="632b6-p126">**过期**。日期和时间时将自动删除邮件从隔离区中。</span><span class="sxs-lookup"><span data-stu-id="632b6-p126">**Expires**. The date and time when the message will automatically be deleted from quarantine.</span></span> 
    
- <span data-ttu-id="632b6-p127">**释放到**。所有电子邮件地址 （如果有） 到已发布消息。</span><span class="sxs-lookup"><span data-stu-id="632b6-p127">**Released to**. All email addresses (if any) to which the message has been released.</span></span> 
    
- <span data-ttu-id="632b6-p128">**尚未释放到**。所有电子邮件地址 （如果有） 到其邮件还没有已释放。</span><span class="sxs-lookup"><span data-stu-id="632b6-p128">**Not yet released to**. All email addresses (if any) to which the message has not yet been released.</span></span> 
    
 <span data-ttu-id="632b6-206">**显示隔离文件的详细信息**</span><span class="sxs-lookup"><span data-stu-id="632b6-206">**Details displayed for quarantined files**</span></span>
  
- <span data-ttu-id="632b6-207">**文件名**隔离中的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="632b6-207">**File Name** The name of the file in quarantine.</span></span> 
    
- <span data-ttu-id="632b6-208">**网站路径**Office 365 中定义的文件的位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="632b6-208">**Site path** URL that defines the location of the file in Office 365.</span></span> 
    
- <span data-ttu-id="632b6-209">**检测到日期 / 时间**日期和时间文件被隔离。</span><span class="sxs-lookup"><span data-stu-id="632b6-209">**Detected Date / Time** The date and time the file was quarantined.</span></span> 
    
- <span data-ttu-id="632b6-210">**过期**邮件从隔离区中的删除时的日期。</span><span class="sxs-lookup"><span data-stu-id="632b6-210">**Expires** The date when the message will be deleted from quarantine.</span></span> 
    
- <span data-ttu-id="632b6-p129">**通过检测**用于在文件中检测到恶意软件的方法。这可以是 Microsoft 的反恶意软件引擎或 ATP （高级威胁保护）。</span><span class="sxs-lookup"><span data-stu-id="632b6-p129">**Detected By** The method used to detect the malware in the file. This can be either ATP (Advanced Threat Protection) or Microsoft's anti-malware engine.</span></span> 
    
- <span data-ttu-id="632b6-213">**发布**描述已发布该文件。</span><span class="sxs-lookup"><span data-stu-id="632b6-213">**Released** Describes whether or not the file has been released.</span></span> 
    
- <span data-ttu-id="632b6-214">**恶意软件名称**系列和文件中检测到的恶意软件的名称。</span><span class="sxs-lookup"><span data-stu-id="632b6-214">**Malware Name** Family and name of the malware detected in the file.</span></span> 
    
- <span data-ttu-id="632b6-215">**文档 ID**文档的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="632b6-215">**Document ID** A unique identifier for the document.</span></span> 
    
- <span data-ttu-id="632b6-216">**文件大小**Kb 文件的大小。</span><span class="sxs-lookup"><span data-stu-id="632b6-216">**File Size** The size of the file in KB.</span></span> 
    
- <span data-ttu-id="632b6-217">**组织**贵组织的 Office 365 中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="632b6-217">**Organization** Your organization's unique ID in Office 365.</span></span> 
    
- <span data-ttu-id="632b6-218">**修改人**工作或学校上次修改文件的用户的帐户。</span><span class="sxs-lookup"><span data-stu-id="632b6-218">**Modified By** The work or school account of the user who last modified the file.</span></span> 
    
- <span data-ttu-id="632b6-219">**文件大小**Kb 文件的大小。</span><span class="sxs-lookup"><span data-stu-id="632b6-219">**File Size** The size of the file in KB.</span></span> 
    
- <span data-ttu-id="632b6-p130">**SHA256 哈希值**文件的哈希值。您可以使用此以查找您可能或调查其中 else 文件可能在您的环境中其他信誉存储。</span><span class="sxs-lookup"><span data-stu-id="632b6-p130">**SHA256 Hash** The hash of the file. You can use this to look up other reputation stores you may have or investigate where else the file might be in your environment.</span></span> 
    
## <a name="managing-messages-and-files-in-quarantine"></a><span data-ttu-id="632b6-222">管理邮件和隔离文件</span><span class="sxs-lookup"><span data-stu-id="632b6-222">Managing messages and files in quarantine</span></span>
<span data-ttu-id="632b6-223"><a name="BKMK_ManageQuarantinedItem"> </a></span><span class="sxs-lookup"><span data-stu-id="632b6-223"></span></span>

<span data-ttu-id="632b6-224">选择邮件或消息的数目的组后可以针对管理隔离中的邮件的几个选项。</span><span class="sxs-lookup"><span data-stu-id="632b6-224">After you select a message or group of messages you have several options for managing messages in quarantine.</span></span>
  
- <span data-ttu-id="632b6-p131">不执行任何操作。如果您选择不执行任何操作，消息将被删除 Office 365 自动到期时。默认情况下垃圾邮件、 批量、 恶意软件、 网络钓鱼和由于它们匹配的邮件流规则隔离的邮件将保留在隔离 30 天。Office 365 从隔离区中删除一条消息时, 不能将其恢复。如果您愿意，您可以通过在您的反垃圾邮件策略中配置的**保留期限 （天） 的垃圾邮件**设置更改隔离邮件的保留的期。有关详细信息，请参阅本文中的[Setting 隔离的保留期](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime)。</span><span class="sxs-lookup"><span data-stu-id="632b6-p131">Do nothing. If you choose to do nothing, the message will be deleted by Office 365 automatically upon expiration. By default, spam, bulk, malware, phishing, and messages quarantined because they matched a mail flow rule are kept in quarantine for 30 days. When Office 365 deletes a message from quarantine, you can't get it back. If you like, you can change the retention period for quarantined messages by configuring the **Retain spam for (days)** setting in your anti-spam policies. For more information, see [Setting the quarantine retention period](manage-quarantined-messages-and-files.md#BKMK_ModQuarantineTime) in this article.</span></span> 
    
- <span data-ttu-id="632b6-p132">**查看邮件头**选择此链接可以看到消息标头文本。若要分析深度中的页眉，将消息标头文本复制到剪贴板上，，然后选择**Microsoft 消息标头分析器**以转到远程连接分析器 （右键单击并选择**新选项卡中打开**的如果您不想要保留 Office365 才能完成此任务)。在邮件标头分析器部分中，粘贴到该页上的邮件头，然后选择**分析标头**。</span><span class="sxs-lookup"><span data-stu-id="632b6-p132">**View message header** Choose this link to see the message header text. To analyze the header in depth, copy the message header text to your clipboard, and then choose **Microsoft Message Header Analyzer** to go to the Remote Connectivity Analyzer (right-click and choose **Open in a new tab** if you don't want to leave Office 365 to complete this task).Paste the message header onto the page in the Message Header Analyzer section, and choose **Analyze headers**.</span></span>
    
- <span data-ttu-id="632b6-p133">**预览消息**允许您，请参阅原始或消息正文文本的 HTML 版本。在 HTML 视图中，将被禁用的链接。</span><span class="sxs-lookup"><span data-stu-id="632b6-p133">**Preview message** Lets you see raw or HTML versions of the message body text. In the HTML view, links are disabled.</span></span> 
    
- <span data-ttu-id="632b6-p134">**下载邮件**或**下载文件**。选择此选项可将邮件或文件的副本下载到您的本地设备。您需要确认您了解与之前将允许您为此，从隔离区下载项目相关的风险。邮件保存到指定文件夹.eml 格式。隔离的文件将保存其原始格式。</span><span class="sxs-lookup"><span data-stu-id="632b6-p134">**Download message** or **Download file**. Choose this option to download a copy of the message or file to your local device. You'll need to confirm that you understand the risks associated with downloading items from quarantine before you'll be allowed to do so. Messages are saved in .eml format to a folder you specify. Quarantined files are saved in their original format.</span></span>
    
- <span data-ttu-id="632b6-p135">**删除**如果您希望，您可以立即删除隔离的项目 （或一组项目） 而不是等待通过 Office 365 设置的到期日期。删除消息或文件，请在隔离列表中，选择项目，然后选择**删除**。若要同时删除多个项目，在隔离列表中，选择项目左侧的复选框，然后在显示**批量操作**页上，选择**删除所选的邮件**或**删除选定的文件**。</span><span class="sxs-lookup"><span data-stu-id="632b6-p135">**Delete** If you want, you can immediately delete a quarantined item (or set of items) instead of waiting for the expiration date set by Office 365. To delete a message or file, in the quarantine list, select the item and then choose **Delete**. To delete multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Delete selected messages** or **Delete selected files**.</span></span>
    
- <span data-ttu-id="632b6-243">**发行版**释放隔离的项目 （或一组项目），并向 Microsoft 报告为虚假隔离 （误报） 的项目。</span><span class="sxs-lookup"><span data-stu-id="632b6-243">**Release** Release a quarantined item (or set of items) and report the items as falsely quarantined (false positives) to Microsoft.</span></span> 
    
    <span data-ttu-id="632b6-p136">释放和报告单个邮件或文件，请在隔离列表中，选择项目，选择**版本文件**或**释放邮件**。在下一页上，确保**报表邮件提交给 Microsoft 进行分析**或**报告给 Microsoft 进行分析的文件**已选中。</span><span class="sxs-lookup"><span data-stu-id="632b6-p136">To release and report a single message or file, in the quarantine list, select the item, choose **Release file** or **Release message**. On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span> 
    
    <span data-ttu-id="632b6-p137">同时释放多个项目，在隔离列表中，选择项目左侧的复选框，然后在显示**批量操作**页上，选择**释放文件**或**释放邮件**。在下一页上，确保**报表邮件提交给 Microsoft 进行分析**或**报告给 Microsoft 进行分析的文件**已选中。</span><span class="sxs-lookup"><span data-stu-id="632b6-p137">To release multiple items at once, select the checkbox to the left of the items in the quarantine list, and then on the **Bulk actions** page that appears, choose **Release files** or **Release messages**. On the next page, ensure that **report messages to Microsoft for analysis** or **report files to Microsoft for analysis** is selected.</span></span> 
    
<span data-ttu-id="632b6-248">当您释放邮件，请注意下列选项：</span><span class="sxs-lookup"><span data-stu-id="632b6-248">When you're releasing messages, be aware of the following:</span></span>
  
- <span data-ttu-id="632b6-p138">同时执行多个邮件的批量版本时，邮件所释放到所有最初标识收件人。如果您只想要释放仅向特定收件人的邮件，您需要一次释放邮件一个单独标识收件人。</span><span class="sxs-lookup"><span data-stu-id="632b6-p138">When you perform a bulk release of multiple messages at once, the messages are released to all originally identified recipients. If you only want to release messages only to specific recipients, you need to release the messages one at a time and identify the recipients individually.</span></span>
    
- <span data-ttu-id="632b6-251">一条消息，不能多次释放到同一个收件人。</span><span class="sxs-lookup"><span data-stu-id="632b6-251">A message cannot be released more than once to the same recipient.</span></span>
    
- <span data-ttu-id="632b6-252">当您释放邮件到多个收件人时，只有以前未收到邮件的收件人将显示的潜在的收件人列表中。</span><span class="sxs-lookup"><span data-stu-id="632b6-252">When you're releasing a message to more than one recipient, only recipients who have not previously received the message will appear in the list of potential recipients.</span></span>
    
- <span data-ttu-id="632b6-p139">当您选择报告误报，如果释放的邮件已隔离作为垃圾邮件、 批量、 网络钓鱼，或包含恶意软件时，还会向 Microsoft 垃圾邮件分析团队报告消息。团队将评估和分析邮件，以及根据分析结果，可能调整服务范围垃圾邮件内容筛选器规则以允许通过此邮件。</span><span class="sxs-lookup"><span data-stu-id="632b6-p139">When you choose to report false positives, if the message or messages you release were quarantined as spam, bulk, phishing, or as containing malware, the message will also be reported to the Microsoft Spam Analysis Team. The team will evaluate and analyze the message, and, depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>
    
## <a name="setting-the-quarantine-retention-period"></a><span data-ttu-id="632b6-255">设置隔离的保留期</span><span class="sxs-lookup"><span data-stu-id="632b6-255">Setting the quarantine retention period</span></span>
<span data-ttu-id="632b6-256"><a name="BKMK_ModQuarantineTime"> </a></span><span class="sxs-lookup"><span data-stu-id="632b6-256"></span></span>

<span data-ttu-id="632b6-p140">您可以配置长消息和文件将保留在隔离到期前进行。默认情况下，隔离的项目保留 30 天。配置为每个策略创建的此设置。您还可以修改默认策略，如本文中所述的值。</span><span class="sxs-lookup"><span data-stu-id="632b6-p140">You can configure how long messages and files will remain in quarantine before they expire. By default, quarantined items are kept for 30 days. You configure this setting for each policy that you create. You can also modify the value for the default policy as described in this article.</span></span> 
  
### <a name="to-modify-the-quarantine-retention-period-for-the-default-spam-filter-policy-in-the-security-and-compliance-center"></a><span data-ttu-id="632b6-261">修改默认垃圾邮件筛选器策略隔离的保留期中的安全性和合规性中心</span><span class="sxs-lookup"><span data-stu-id="632b6-261">To modify the quarantine retention period for the default spam filter policy in the Security and Compliance Center</span></span>

1. <span data-ttu-id="632b6-262">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，登录到 Office 365 和[转到的安全性和合规性中心](go-to-the-securitycompliance-center.md)。</span><span class="sxs-lookup"><span data-stu-id="632b6-262">Using a work or school account that has global administrator privileges in your Office 365 organization, sign in to Office 365 and [go to the Security and Compliance Center](go-to-the-securitycompliance-center.md).</span></span>
    
2. <span data-ttu-id="632b6-263">在左侧，展开**威胁管理**，选择**策略**，，然后选择**反垃圾邮件**。</span><span class="sxs-lookup"><span data-stu-id="632b6-263">On the left, expand **Threat Management**, choose **Policy**, and then choose **Anti-spam**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="632b6-264">若要直接转到安全中的**反垃圾邮件**页上&amp;合规性中心，使用以下 URL: >[https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span><span class="sxs-lookup"><span data-stu-id="632b6-264">To go directly to the **anti-spam** page in the Security &amp; Compliance Center, use this URL: > [https://protection.office.com/?hash=/antispam](https://protection.office.com/?hash=/antispam)</span></span>
  
3. <span data-ttu-id="632b6-265">选择**自定义**以显示**自定义设置**选项卡。</span><span class="sxs-lookup"><span data-stu-id="632b6-265">Choose **Custom** to display the **Custom settings** tab.</span></span> 
    
4. <span data-ttu-id="632b6-266">展开的**默认垃圾邮件筛选器策略 (始终 ON)** 行。</span><span class="sxs-lookup"><span data-stu-id="632b6-266">Expand the **Default spam filter policy (always ON)** row.</span></span> 
    
5. <span data-ttu-id="632b6-p141">选择**编辑策略**。在新页中显示的默认垃圾邮件筛选器策略的设置。</span><span class="sxs-lookup"><span data-stu-id="632b6-p141">Choose **Edit policy**. The settings for the default spam filter policy appear in a new page.</span></span>
    
6. <span data-ttu-id="632b6-269">展开**垃圾邮件和批量操作**。</span><span class="sxs-lookup"><span data-stu-id="632b6-269">Expand **Spam and bulk actions**.</span></span>
    
7. <span data-ttu-id="632b6-p142">在**隔离**下的**保留期限 （天） 的垃圾邮件**文本框中，输入您希望 Office 365 保留在隔离的邮件和文件的时间量。默认值为 30 天。这也是最大值。</span><span class="sxs-lookup"><span data-stu-id="632b6-p142">Under **Quarantine**, in the **Retain spam for (days)** text box, enter the amount of time you want Office 365 to retain messages and files in quarantine. The default is 30 days. This is also the maximum.</span></span> 
    
8. <span data-ttu-id="632b6-273">选择**保存**。</span><span class="sxs-lookup"><span data-stu-id="632b6-273">Choose **Save**.</span></span>
    

