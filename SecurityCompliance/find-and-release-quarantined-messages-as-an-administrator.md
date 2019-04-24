---
title: 以管理员身份查找并释放隔离邮件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: 本主题介绍了 Exchange Online 和 Exchange Online Protection (EOP) 管理员如何在 Exchange 管理中心 (EAC) 中查找、释放和报告隔离邮件。
ms.openlocfilehash: a973d3a3b1875ed1ba691f91c1c23373ac8d6694
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255254"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a><span data-ttu-id="4e73a-103">以管理员身份查找并释放隔离邮件</span><span class="sxs-lookup"><span data-stu-id="4e73a-103">Find and release quarantined messages as an administrator</span></span>

<span data-ttu-id="4e73a-104">本主题介绍了 Exchange Online 和 Exchange Online Protection (EOP) 管理员如何在 Exchange 管理中心 (EAC) 中查找、释放和报告隔离邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-104">This topic describes how Exchange Online and Exchange Online Protection (EOP) admins can find, release, and report on quarantined messages in the Exchange admin center (EAC).</span></span> <span data-ttu-id="4e73a-105">Office 365 将邮件定向到隔离区, 因为它们被标识为垃圾邮件或与邮件流规则匹配 (也称为 "传输规则")。</span><span class="sxs-lookup"><span data-stu-id="4e73a-105">Office 365 directs messages to quarantine either because they were identified as spam or they matched a mail flow rule (also known as a transport rule).</span></span> 
  
<span data-ttu-id="4e73a-106">使用安全&amp;合规中心 (而不是 EAC) 完成这些任务, 并查看和处理发送到隔离的邮件, 因为它们包含恶意软件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-106">Use the Security &amp; Compliance Center instead of the EAC to complete any of these tasks as well as view and work with messages that were sent to quarantine because they contain malware.</span></span> <span data-ttu-id="4e73a-107">有关详细信息, 请参阅[在 Office 365 中隔离电子邮件消息](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b)。</span><span class="sxs-lookup"><span data-stu-id="4e73a-107">For more information, see [Quarantine email messages in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).</span></span>
  
<span data-ttu-id="4e73a-108">已隔离邮件在 EAC 的 "**隔离**" 页面上列出。</span><span class="sxs-lookup"><span data-stu-id="4e73a-108">Quarantined messages are listed on the **quarantine** page in EAC.</span></span> <span data-ttu-id="4e73a-109">默认情况下, "**接收**时间" 字段中的邮件按从最新到最旧的顺序排列。</span><span class="sxs-lookup"><span data-stu-id="4e73a-109">By default, messages are sorted from newest to oldest on the **RECEIVED** field.</span></span> <span data-ttu-id="4e73a-110">还将为每封邮件列出“发件人”\*\*\*\*、“主题”\*\*\*\* 和“到期”\*\*\*\* 值。</span><span class="sxs-lookup"><span data-stu-id="4e73a-110">**SENDER**, **SUBJECT**, and **EXPIRES** values are also listed for each message.</span></span> <span data-ttu-id="4e73a-111">您可以通过单击标题来对任何字段排序。</span><span class="sxs-lookup"><span data-stu-id="4e73a-111">You can sort on any of these fields by clicking their headers.</span></span> <span data-ttu-id="4e73a-112">再次单击列标题将按相反顺序排序。</span><span class="sxs-lookup"><span data-stu-id="4e73a-112">If you click a column header a second time, the sort order reverses.</span></span> <span data-ttu-id="4e73a-113">"**隔离**" 页面最多显示500个邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-113">The **quarantine** page displays a maximum of 500 messages.</span></span> 
  
<span data-ttu-id="4e73a-p104">您可以查看所有隔离邮件的列表，或者通过指定筛选条件来搜索特定邮件（如果邮件超过 500 封，筛选还可以帮助减少结果集）。搜索并找到特定的隔离邮件之后，可以查看关于邮件的详细信息。您还可以：</span><span class="sxs-lookup"><span data-stu-id="4e73a-p104">You can view a list of all quarantined messages, or you can search for specific messages by specifying filter criteria (filtering can also help reduce your result set if you have more than 500 messages). After searching for and locating a specific quarantined message, you can view details about the message. You can also:</span></span>
  
- <span data-ttu-id="4e73a-p105">向一个或多个收件人释放邮件，并且选择向 Microsoft 垃圾邮件分析团队将其报告为误报（非垃圾邮件），他们将评估并分析该邮件。根据分析结果的不同，可能会调整服务范围内的垃圾邮件内容筛选规则，以允许发送该邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-p105">Release the message to one or more recipients, and optionally report it as a false positive (not junk) message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>
    
- <span data-ttu-id="4e73a-119">释放邮件并允许接收该发件人未来发送的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-119">Release the message and allow all future messages from that sender.</span></span>
    
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="4e73a-120">开始前，有必要了解什么？</span><span class="sxs-lookup"><span data-stu-id="4e73a-120">What do you need to know before you begin?</span></span>
<span data-ttu-id="4e73a-121"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="4e73a-121"></span></span>

- <span data-ttu-id="4e73a-122">您必须先获得权限，然后才能执行此过程或多个过程。</span><span class="sxs-lookup"><span data-stu-id="4e73a-122">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="4e73a-123">若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的 "隔离" 条目。</span><span class="sxs-lookup"><span data-stu-id="4e73a-123">To see what permissions you need, see the "Quarantine" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
    
- <span data-ttu-id="4e73a-124">您可以在 "**隔离**" 页面上一次释放或报告多封邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-124">You can release or report multiple messages at once on the **quarantine** page.</span></span> <span data-ttu-id="4e73a-125">或者, 您可以创建一个远程 Windows PowerShell 脚本来完成此任务。</span><span class="sxs-lookup"><span data-stu-id="4e73a-125">Alternatively you can create a remote Windows PowerShell script to accomplish this task.</span></span> <span data-ttu-id="4e73a-126">使用[get-quarantinemessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet 搜索邮件, 并使用[get-quarantinemessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet 释放邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-126">Use the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for messages, and the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet to release them.</span></span> 
    
- <span data-ttu-id="4e73a-127">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="4e73a-127">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="4e73a-p108">遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="4e73a-p108">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a><span data-ttu-id="4e73a-131">使用高级搜索来筛选和查找隔离邮件</span><span class="sxs-lookup"><span data-stu-id="4e73a-131">Use advanced search to filter and locate quarantined messages</span></span>
<span data-ttu-id="4e73a-132"><a name="BKMK_UseAdvancedSearchtoFilterMessages"> </a></span><span class="sxs-lookup"><span data-stu-id="4e73a-132"></span></span>

<span data-ttu-id="4e73a-p109">在 Exchange 管理中心 (EAC) 中，您可以使用高级搜索根据一些不同的条件筛选隔离邮件。这些条件可以单独使用，也可以结合使用。搜索将提供满足您的所有筛选条件的邮件列表。</span><span class="sxs-lookup"><span data-stu-id="4e73a-p109">In the Exchange admin center (EAC), you can filter quarantined items based on several different conditions using advanced search. You can use these conditions separately or in combination with one another. The search will provide a list of messages that meet all your filter criteria.</span></span>
  
1. <span data-ttu-id="4e73a-136">在 EAC 中, 导航到 "**保护** \> **隔离**", 然后单击 "**高级搜索**"。</span><span class="sxs-lookup"><span data-stu-id="4e73a-136">In EAC, navigate to **Protection** \> **quarantine**, and then click **Advanced search**.</span></span>
    
2. <span data-ttu-id="4e73a-137">在 "**高级搜索**" 窗口中, 选择下列条件的任意组合。</span><span class="sxs-lookup"><span data-stu-id="4e73a-137">In the **Advanced search** window, select any combination of the following conditions.</span></span> <span data-ttu-id="4e73a-138">选中关联的复选框，以启用各个条件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-138">Select the associated check box to enable each condition.</span></span> <span data-ttu-id="4e73a-139">不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="4e73a-139">Wildcards aren't supported.</span></span> 
    
1. <span data-ttu-id="4e73a-140">**邮件 ID**您可以使用此参数对特定邮件执行目标搜索。</span><span class="sxs-lookup"><span data-stu-id="4e73a-140">**Message ID** You can use this parameter to perform a targeted search for a specific message.</span></span> <span data-ttu-id="4e73a-141">例如，如果特定邮件由贵组织的用户发送，或准备发送给贵组织的用户，但是未抵达目标收件人，则您可以使用邮件跟踪功能搜索该邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-141">For example, if a specific message is sent by, or intended for, a user in your organization, but it never reaches its destination, you can search for the message using the message trace feature.</span></span> <span data-ttu-id="4e73a-142">有关详细信息，请参阅 [运行邮件跟踪和查看结果](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4e73a-142">For details, see [Run a Message Trace and View Results](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx).</span></span> <span data-ttu-id="4e73a-143">如果您发现邮件被发送到隔离区，可能是因为它符合某个规则或被标识为垃圾邮件，您可以通过指定其邮件 ID，在隔离区中轻松找到此邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-143">If you discover that the message was sent to the quarantine, perhaps because it matched a rule or was identified as spam, you can then easily find this message in the quarantine by specifying its Message ID.</span></span> <span data-ttu-id="4e73a-144">请务必包含完整的邮件 ID 字符串。</span><span class="sxs-lookup"><span data-stu-id="4e73a-144">Be sure to include the full Message ID string.</span></span> <span data-ttu-id="4e73a-145">这可能包括尖括号 (\<\>)。</span><span class="sxs-lookup"><span data-stu-id="4e73a-145">This might include angle brackets (\<\>).</span></span> 
    
2. <span data-ttu-id="4e73a-146">**发件人电子邮件地址**指定发送邮件的人员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="4e73a-146">**Sender email address** Specify the email address of the person who sent the message.</span></span> 
    
3. <span data-ttu-id="4e73a-147">**收件人电子邮件地址**指定邮件的预期收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="4e73a-147">**Recipient email address** Specify the email address of the intended recipient of the message.</span></span> 
    
4. <span data-ttu-id="4e73a-148">**主题**指定邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="4e73a-148">**Subject** Specify the subject line text of the message.</span></span> 
    
5. <span data-ttu-id="4e73a-149">**接收**您可以选择在过去24小时内 ("**今天**")、过去的48小时内 ("过去**2 天**")、过去一周内 ("过去**7 天**") 的隔离区中接收邮件, 也可以选择邮件的自定义时间间隔。由隔离区接收。</span><span class="sxs-lookup"><span data-stu-id="4e73a-149">**Received** You can select that the message was received by quarantine within the past 24 hours ( **Today**), within the past 48 hours ( **Last 2 days**), within the past week ( **Last 7 days**), or you can select a custom time interval during which the message was received by the quarantine.</span></span> 
    
6. <span data-ttu-id="4e73a-150">**过期**您可以选择在接下来的24小时内 ("**今天**"), 在接下来的48小时内 (**接下来的2天**), 在下一周内 ("**接下来7天**"), 或者您可以选择一个自定义时间间隔, 邮件将从隔离区中删除。</span><span class="sxs-lookup"><span data-stu-id="4e73a-150">**Expires** You can select that the message will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval during which the message will be deleted from quarantine.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="4e73a-151">默认情况下, 垃圾邮件隔离的邮件在15天内保留隔离, 而与邮件流规则匹配的隔离邮件将保留在隔离时间7天内。</span><span class="sxs-lookup"><span data-stu-id="4e73a-151">By default, spam-quarantined messages are kept in quarantine for 15 days, while quarantined messages that matched a mail flow rule are kept in the quarantine for 7 days.</span></span> <span data-ttu-id="4e73a-152">7 天后，这些邮件将被 Office 365 删除并且不可检索。</span><span class="sxs-lookup"><span data-stu-id="4e73a-152">After this period of time Office 365 deletes the messages and they are not retrievable.</span></span> <span data-ttu-id="4e73a-153">与邮件流规则匹配的隔离邮件的保留期不可配置。</span><span class="sxs-lookup"><span data-stu-id="4e73a-153">The retention period for quarantined messages that matched a mail flow rule is not configurable.</span></span> <span data-ttu-id="4e73a-154">但是, 垃圾邮件隔离邮件的保留期可以通过内容筛选器策略中的 "**保留垃圾邮件 (天)** " 设置来降低。</span><span class="sxs-lookup"><span data-stu-id="4e73a-154">However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies.</span></span> <span data-ttu-id="4e73a-155">有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="4e73a-155">For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> 
  
7. <span data-ttu-id="4e73a-156">**类型**您可以指定是否搜索已被标识为**垃圾**邮件的隔离邮件, 或者是否搜索与邮件流规则匹配的邮件 (**传输规则**)。</span><span class="sxs-lookup"><span data-stu-id="4e73a-156">**Type** You can specify whether to search for quarantined messages that have been identified as **Spam**, or whether to search for messages that matched a mail flow rule (**Transport rule**).</span></span>
    
3. <span data-ttu-id="4e73a-157">单击 **"确定"** 开始运行高级搜索。</span><span class="sxs-lookup"><span data-stu-id="4e73a-157">Click **OK** to start running the advanced search.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="4e73a-158">若要清除搜索条件并查看隔离中的所有邮件, 请清除 "**高级搜索**" 窗口中的所有复选框, 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="4e73a-158">To clear your search criteria and view all messages in the quarantine, clear all the check boxes in the **Advanced search** window, and then click **OK**.</span></span> 
  
<span data-ttu-id="4e73a-p113">在搜索好邮件后，匹配您的指定条件的结果将显示在用户界面中。EAC 中可显示最多 500 封邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-p113">After searching for messages, the results that match your specified criteria will display in the user interface. A maximum of 500 messages can be displayed in the EAC.</span></span> 
  
## <a name="view-details-about-a-specific-quarantined-message"></a><span data-ttu-id="4e73a-161">查看有关特定隔离邮件的详细信息</span><span class="sxs-lookup"><span data-stu-id="4e73a-161">View details about a specific quarantined message</span></span>
<span data-ttu-id="4e73a-162"><a name="BKMK_ViewDetailsAboutaSpecificQuarantinedMessage"> </a></span><span class="sxs-lookup"><span data-stu-id="4e73a-162"></span></span>

<span data-ttu-id="4e73a-163">在**隔离**页上找到特定的隔离邮件后, 您可以查看有关该邮件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4e73a-163">After locating a specific quarantined message on the **quarantine** page, you can view details about it.</span></span> 
  
1. <span data-ttu-id="4e73a-164">在 "**隔离**" 页面上, 选择特定的邮件, 屏幕右侧的详细信息窗格中将显示该邮件的属性摘要。</span><span class="sxs-lookup"><span data-stu-id="4e73a-164">On the **quarantine** page, select a specific message and a summary of the properties of that message appear in the details pane on the right side of the screen.</span></span> 
    
    <span data-ttu-id="4e73a-165">**邮件状态**值如下所示:</span><span class="sxs-lookup"><span data-stu-id="4e73a-165">The **Message status** values are as follows:</span></span> 
    
  - <span data-ttu-id="4e73a-166">**类型**指示是否已将邮件标识为**垃圾**邮件或与邮件流规则 (**传输规则**) 相匹配。</span><span class="sxs-lookup"><span data-stu-id="4e73a-166">**Type** Denotes whether the message has been identified as **Spam** or matched a mail flow rule (**Transport rule**).</span></span>
    
  - <span data-ttu-id="4e73a-167">**过期**将从隔离区中删除邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="4e73a-167">**Expires** The date when the message will be deleted from the quarantine.</span></span> 
    
    <span data-ttu-id="4e73a-168">**消息详细信息**值如下所示:</span><span class="sxs-lookup"><span data-stu-id="4e73a-168">The **Message details** values are as follows:</span></span> 
    
  - <span data-ttu-id="4e73a-169">**发件人**发送邮件的人员的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="4e73a-169">**Sender** The email address of the person who sent the message.</span></span> 
    
  - <span data-ttu-id="4e73a-170">**主题**邮件的主题行文本。</span><span class="sxs-lookup"><span data-stu-id="4e73a-170">**Subject** The subject line text of the message.</span></span> 
    
  - <span data-ttu-id="4e73a-171">**接收**隔离人收到邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="4e73a-171">**Received** The date on which the message was received by the quarantine.</span></span> 
    
  - <span data-ttu-id="4e73a-172">**尺寸**邮件的大小, 以千字节 (kb) 为单位, 如果邮件大小大于 999 kb, 则为兆字节 (mb)。</span><span class="sxs-lookup"><span data-stu-id="4e73a-172">**Size** The size of the message, in kilobytes (KB), or, if the message size is greater than 999 KBs, in megabytes (MB).</span></span> 
    
  - <span data-ttu-id="4e73a-173">**查看邮件头**单击此链接可打开 "**邮件头**" 对话框, 您可以通过该对话框查看邮件头文本。</span><span class="sxs-lookup"><span data-stu-id="4e73a-173">**View message header** Click this link to open the **message header** dialog box, which lets you view the message header text.</span></span> <span data-ttu-id="4e73a-174">您还可以将邮件头文本复制到剪贴板，并粘贴到 [邮件头分析器](https://testconnectivity.microsoft.com/?tabid=mha)。</span><span class="sxs-lookup"><span data-stu-id="4e73a-174">You can also copy the message header text to your clipboard and paste it into the [Message Header Analyzer](https://testconnectivity.microsoft.com/?tabid=mha).</span></span> <span data-ttu-id="4e73a-175">进入邮件头分析器工具后，单击" **分析标头**"以检索关于标头的信息。</span><span class="sxs-lookup"><span data-stu-id="4e73a-175">Once in the Message Header Analyzer tool, click **Analyze headers** in order to retrieve information about the header.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="4e73a-176">有关服务插入的特定反垃圾邮件的邮件头字段的信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="4e73a-176">For information about specific anti-spam message header fields inserted by the service, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span> 
  
  - <span data-ttu-id="4e73a-177">**预览电子邮件**单击此链接可查看邮件文本。</span><span class="sxs-lookup"><span data-stu-id="4e73a-177">**Preview email message** Click this link to review the text of the message.</span></span> 
    
2. <span data-ttu-id="4e73a-178">如果双击隔离邮件,**隔离的邮件**窗口将打开, 并显示以下信息:</span><span class="sxs-lookup"><span data-stu-id="4e73a-178">If you double-click a quarantined message, the **Quarantined message** window opens and displays the following information:</span></span> 
    
  - <span data-ttu-id="4e73a-179">**发布到**已发布邮件的所有电子邮件地址的列表 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="4e73a-179">**Released to** A list of all email addresses to whom the message has been released, if any.</span></span> 
    
  - <span data-ttu-id="4e73a-180">**尚未发布到**尚未发布邮件的所有电子邮件地址的列表 (如果有)。</span><span class="sxs-lookup"><span data-stu-id="4e73a-180">**Not yet released to** A list of all email addresses to whom the message has not been released, if any.</span></span> <span data-ttu-id="4e73a-181">您可以单击 "**发布到**" 链接以释放邮件;有关释放邮件的详细信息, 请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="4e73a-181">You can click the **Release to** link in order to release the message; for more information about releasing a message, see the next section.</span></span> 
    
  - <span data-ttu-id="4e73a-182">**邮件 ID**在邮件头中找到的 Internet 邮件 ID (也称为 "客户端 ID")。</span><span class="sxs-lookup"><span data-stu-id="4e73a-182">**Message ID** The Internet Message ID (also known as the Client ID) found in the header of the message.</span></span> 
    
    <span data-ttu-id="4e73a-183">单击 "**关闭**" 返回到主隔离窗格。</span><span class="sxs-lookup"><span data-stu-id="4e73a-183">Click **Close** to return to the main quarantine pane.</span></span> 
    
## <a name="release-messages-from-quarantine"></a><span data-ttu-id="4e73a-184">从隔离区中释放邮件</span><span class="sxs-lookup"><span data-stu-id="4e73a-184">Release messages from quarantine</span></span>
<span data-ttu-id="4e73a-185"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="4e73a-185"></span></span>

<span data-ttu-id="4e73a-186">如果您想将邮件释放给收件人，您可以：</span><span class="sxs-lookup"><span data-stu-id="4e73a-186">If you want to release messages to recipients, your options are:</span></span>
  
- [<span data-ttu-id="4e73a-187">释放隔离邮件并允许接收该发件人未来发送的邮件</span><span class="sxs-lookup"><span data-stu-id="4e73a-187">Release a quarantined message and allow future messages from the sender</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessageallowfuturemessagesfromsender)
    
- [<span data-ttu-id="4e73a-188">将隔离邮件释放给特定收件人，而不将其报告为误报</span><span class="sxs-lookup"><span data-stu-id="4e73a-188">Release a quarantined message to specific recipients without reporting it as a false positive</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive)
    
- [<span data-ttu-id="4e73a-189">将一个或多个隔离邮件释放给所有收件人</span><span class="sxs-lookup"><span data-stu-id="4e73a-189">Release one or more quarantined messages to all recipients</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipients)
    
- [<span data-ttu-id="4e73a-190">将一个或多个隔离邮件释放给所有收件人并将其报告为误报</span><span class="sxs-lookup"><span data-stu-id="4e73a-190">Release one or more quarantined messages to all recipients and report false positives</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives)
    
### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a><span data-ttu-id="4e73a-191">释放隔离邮件并允许接收该发件人未来发送的邮件</span><span class="sxs-lookup"><span data-stu-id="4e73a-191">Release a quarantined message and allow future messages from the sender</span></span>
<span data-ttu-id="4e73a-192"><a name="Releasequarantinedmessageallowfuturemessagesfromsender"> </a></span><span class="sxs-lookup"><span data-stu-id="4e73a-192"></span></span>

1. <span data-ttu-id="4e73a-193">在 EAC 中, 导航到 "**保护** \> **隔离**"。</span><span class="sxs-lookup"><span data-stu-id="4e73a-193">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="4e73a-194">单击邮件以将其选中, 然后单击 "**释放邮件**" 图标, 如下面的屏幕截图所示。</span><span class="sxs-lookup"><span data-stu-id="4e73a-194">Click on a message to select it and then click the **Release Message** icon as shown in the following screen shot.</span></span> 
  
![显示隔离页（包含突出显示的释放邮件图标和释放选项）](media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)
  
<span data-ttu-id="4e73a-196">从下拉列表中单击 "**释放所选邮件并允许发件人**"。</span><span class="sxs-lookup"><span data-stu-id="4e73a-196">Click **Release selected message and allow sender** from the drop-down list.</span></span> 
    
3. <span data-ttu-id="4e73a-197">将打开 "**释放邮件并允许发件人**" 对话框。</span><span class="sxs-lookup"><span data-stu-id="4e73a-197">The **release message and allow sender** dialog box opens.</span></span> <span data-ttu-id="4e73a-198">(可选) 您可以选择向 Microsoft 报告邮件, 然后单击 "**释放并允许**"。</span><span class="sxs-lookup"><span data-stu-id="4e73a-198">Optionally, you can choose to report the message to Microsoft, then click **release and allow**.</span></span> <span data-ttu-id="4e73a-199">该邮件将被释放给所有收件人并将允许接收此发件人未来发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-199">The message will be released to all recipients it's addressed to and all future messages from this sender will be allowed.</span></span> <span data-ttu-id="4e73a-200">但是, 如果此邮件是由于邮件流规则或阻止发件人而被隔离的, 则将继续阻止发件人的后续邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-200">However, if this message was quarantined because of a mail flow rule or blocked sender, the sender will continue to be blocked for future messages.</span></span> 
    
### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a><span data-ttu-id="4e73a-201">将隔离邮件释放给特定收件人，而不将其报告为误报</span><span class="sxs-lookup"><span data-stu-id="4e73a-201">Release a quarantined message to specific recipients without reporting it as a false positive</span></span>
<span data-ttu-id="4e73a-202"><a name="Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive"> </a></span><span class="sxs-lookup"><span data-stu-id="4e73a-202"></span></span>

1. <span data-ttu-id="4e73a-203">在 EAC 中, 导航到 "**保护** \> **隔离**"。</span><span class="sxs-lookup"><span data-stu-id="4e73a-203">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="4e73a-204">选择一封邮件, 单击 "**释放邮件**" 图标, 然后从下拉列表中单击 "**将邮件释放给特定收件人**"。</span><span class="sxs-lookup"><span data-stu-id="4e73a-204">Select a message, click the **Release Message** icon, and then click **Release message to specific recipients** from the drop-down list.</span></span> 
    
3. <span data-ttu-id="4e73a-205">在“释放邮件”\*\*\*\* 对话框中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="4e73a-205">In the **release message** dialog box, select one of the following options:</span></span> 
    
  - <span data-ttu-id="4e73a-206">**向所有收件人释放邮件**选择此选项时, 请注意, 不能将一封邮件释放到同一收件人的一次。</span><span class="sxs-lookup"><span data-stu-id="4e73a-206">**Release message to all recipients** When you select this option, be aware that a message cannot be released more than once to the same recipient.</span></span> <span data-ttu-id="4e73a-207">如果收件人之前已经收到此邮件，则邮件不会再次释放给该收件人。</span><span class="sxs-lookup"><span data-stu-id="4e73a-207">If a recipient has previously received the message, it will not be released again to that recipient.</span></span> 
    
  - <span data-ttu-id="4e73a-208">**将邮件释放给指定的收件人**选择可将邮件释放到的收件人。</span><span class="sxs-lookup"><span data-stu-id="4e73a-208">**Release message to specified recipients** Select the recipient(s) to whom the message can be released.</span></span> <span data-ttu-id="4e73a-209">由于一封邮件只能释放给每个收件人一次，因此该列表仅显示邮件可被释放给的目标收件人。</span><span class="sxs-lookup"><span data-stu-id="4e73a-209">Because a message can only be released once to each recipient, only recipients to whom it can be released appear in this list.</span></span> <span data-ttu-id="4e73a-210">支持多选。</span><span class="sxs-lookup"><span data-stu-id="4e73a-210">Multi-selection is supported.</span></span> <span data-ttu-id="4e73a-211">做出选择后, 单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="4e73a-211">After making your recipient selections, click **add**.</span></span>
    
4. <span data-ttu-id="4e73a-212">单击“释放”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4e73a-212">Click **release**.</span></span> 
    
<span data-ttu-id="4e73a-213">如果单击 "**刷新**![刷新" 图标](media/ITPro-EAC-RefreshIcon.gif)图标刷新数据, 然后双击邮件, 您应该会看到它已发布给预期的收件人。</span><span class="sxs-lookup"><span data-stu-id="4e73a-213">If you click the **Refresh**![Refresh Icon](media/ITPro-EAC-RefreshIcon.gif) icon to refresh your data, and then double-click the message, you should see that it's been released to the intended recipients.</span></span> 
  
### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a><span data-ttu-id="4e73a-214">将一个或多个隔离邮件释放给所有收件人</span><span class="sxs-lookup"><span data-stu-id="4e73a-214">Release one or more quarantined messages to all recipients</span></span>
<span data-ttu-id="4e73a-215"><a name="Releaseoneormorequarantinedmessagestoallrecipients"> </a></span><span class="sxs-lookup"><span data-stu-id="4e73a-215"></span></span>

1. <span data-ttu-id="4e73a-216">在 EAC 中, 导航到 "**保护** \> **隔离**"。</span><span class="sxs-lookup"><span data-stu-id="4e73a-216">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="4e73a-217">单击邮件以选中它，或使用 Shift 键来选择多封邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-217">Click on a message to select it, or use the shift key to select multiple messages.</span></span> <span data-ttu-id="4e73a-218">然后单击 "**释放邮件**" 图标。</span><span class="sxs-lookup"><span data-stu-id="4e73a-218">Then click the **Release Message** icon.</span></span> 
    
3. <span data-ttu-id="4e73a-219">从下拉列表中单击 "**将所选邮件释放给所有收件人**"。</span><span class="sxs-lookup"><span data-stu-id="4e73a-219">Click **Release selected message(s) to ALL recipients** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="4e73a-220">此时会打开一个警告对话框。</span><span class="sxs-lookup"><span data-stu-id="4e73a-220">The warning dialog box opens.</span></span> <span data-ttu-id="4e73a-221">阅读警告, 如果要继续, 请选择 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="4e73a-221">Read the warning and select **Yes** if you want to proceed.</span></span> <span data-ttu-id="4e73a-222">选择此选项时，请注意不能将一封邮件释放给同一收件人超过一次。</span><span class="sxs-lookup"><span data-stu-id="4e73a-222">When you select this option, be aware that a message cannot be released more than once to the same recipient.</span></span> <span data-ttu-id="4e73a-223">如果收件人之前已经收到此邮件，则邮件不会再次释放给该收件人。</span><span class="sxs-lookup"><span data-stu-id="4e73a-223">If a recipient has previously received the message, it will not be released again to that recipient.</span></span> 
    
### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a><span data-ttu-id="4e73a-224">将一个或多个隔离邮件释放给所有收件人并将其报告为误报</span><span class="sxs-lookup"><span data-stu-id="4e73a-224">Release one or more quarantined messages to all recipients and report false positives</span></span>
<span data-ttu-id="4e73a-225"><a name="Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives"> </a></span><span class="sxs-lookup"><span data-stu-id="4e73a-225"></span></span>

1. <span data-ttu-id="4e73a-226">在 EAC 中, 导航到 "**保护** \> **隔离**"。</span><span class="sxs-lookup"><span data-stu-id="4e73a-226">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="4e73a-227">单击邮件以选中它，或使用 Shift 键来选择多封邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-227">Click on a message to select it, or use the shift key to select multiple messages.</span></span> <span data-ttu-id="4e73a-228">然后单击 "**释放邮件**" 图标。</span><span class="sxs-lookup"><span data-stu-id="4e73a-228">Then click the **Release Message** icon.</span></span> 
    
3. <span data-ttu-id="4e73a-229">从下拉列表中单击 "**释放所选邮件并报告为误报**"。</span><span class="sxs-lookup"><span data-stu-id="4e73a-229">Click **Release selected message(s) and report as false positive** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="4e73a-230">此时会打开一个警告对话框。</span><span class="sxs-lookup"><span data-stu-id="4e73a-230">The warning dialog box opens.</span></span> <span data-ttu-id="4e73a-231">阅读警告, 如果要继续, 请选择 **"是"** 。</span><span class="sxs-lookup"><span data-stu-id="4e73a-231">Read the warning and select **Yes** if you want to proceed.</span></span> <span data-ttu-id="4e73a-232">选择此选项时，请注意不能将一封邮件释放给同一收件人超过一次。</span><span class="sxs-lookup"><span data-stu-id="4e73a-232">When you select this option, be aware that a message cannot be released more than once to the same recipient.</span></span> <span data-ttu-id="4e73a-233">如果收件人之前已经收到此邮件，则邮件不会再次释放给该收件人。</span><span class="sxs-lookup"><span data-stu-id="4e73a-233">If a recipient has previously received the message, it will not be released again to that recipient.</span></span> 
    
     <span data-ttu-id="4e73a-p123">选择此选项时，会将邮件释放到所有尚未收到此邮件的收件人。如果此邮件是隔离的垃圾邮件，还会将其报告给 Microsoft 垃圾邮件分析团队，该团队将评估和分析该邮件。根据分析结果的不同，可能会调整服务范围内的垃圾邮件内容筛选规则，以允许发送该邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-p123">When you choose this option, the message will be released to all recipients who have not yet received it. If it's a spam-quarantined message, it will also be reported to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span> 
    
> [!TIP]
> <span data-ttu-id="4e73a-237">按照[如何确保邮件不会标记为垃圾邮件](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md)中的步骤，确保邮件未标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="4e73a-237">Help ensure that a message isn't marked as spam by following the steps in [How to help ensure that a message isn't marked as spam](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md).</span></span> 
  
<span data-ttu-id="4e73a-238">如果单击 "**刷新**![刷新" 图标](media/ITPro-EAC-RefreshIcon.gif)图标刷新数据, 然后双击邮件, 您应该会看到它已发布给预期的收件人。</span><span class="sxs-lookup"><span data-stu-id="4e73a-238">If you click the **Refresh**![Refresh Icon](media/ITPro-EAC-RefreshIcon.gif) icon to refresh your data, and then double-click the message, you should see that it's been released to the intended recipients.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="4e73a-239">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="4e73a-239">For more information</span></span>
<span data-ttu-id="4e73a-240"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="4e73a-240"></span></span>

[<span data-ttu-id="4e73a-241">隔离常见问题解答</span><span class="sxs-lookup"><span data-stu-id="4e73a-241">Quarantine FAQ</span></span>](quarantine-faq.md)
  

