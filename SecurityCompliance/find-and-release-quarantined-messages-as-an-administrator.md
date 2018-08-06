---
title: 以管理员身份查找并释放隔离邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/16/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
description: 本主题介绍了 Exchange Online 和 Exchange Online Protection (EOP) 管理员如何在 Exchange 管理中心 (EAC) 中查找、释放和报告隔离邮件。
ms.openlocfilehash: 5ebe65bf703087e8ad4bace827d84833eddb038f
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027479"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a><span data-ttu-id="af489-103">以管理员身份查找并释放隔离邮件</span><span class="sxs-lookup"><span data-stu-id="af489-103">Find and release quarantined messages as an administrator</span></span>

<span data-ttu-id="af489-p101">本主题介绍了 Exchange Online 和 Exchange Online Protection (EOP) 管理员如何在 Exchange 管理中心 (EAC) 中查找、释放和报告隔离邮件。Office 365 将这些邮件发送到隔离邮箱的原因是，它们被标识为垃圾邮件或与传输规则匹配。</span><span class="sxs-lookup"><span data-stu-id="af489-p101">This topic describes how Exchange Online and Exchange Online Protection (EOP) admins can find, release, and report on quarantined messages in the Exchange admin center (EAC). Office 365 directs messages to quarantine either because they were identified as spam or they matched a transport rule.</span></span> 
  
<span data-ttu-id="af489-p102">使用安全&amp;而不是 EAC 完成这些任务以及视图的任何和发送到隔离因为它们包含恶意软件的邮件处理的合规性中心。有关详细信息，请参阅[Office 365 中的隔离电子邮件](https://support.office.com/en-US/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b)。</span><span class="sxs-lookup"><span data-stu-id="af489-p102">Use the Security &amp; Compliance Center instead of the EAC to complete any of these tasks as well as view and work with messages that were sent to quarantine because they contain malware. For more information, see [Quarantine email messages in Office 365](https://support.office.com/en-US/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).</span></span>
  
<span data-ttu-id="af489-p103">在 EAC 中的**隔离**页上列出了隔离的邮件。默认情况下，消息按降序对**RECEIVED**字段中。**发件人**、**主题**和**EXPIRES**值还会列出的每条消息。可以通过单击其邮件头在其中的任何字段进行排序。如果第二次单击列标题，将反转排序顺序。**隔离**页上显示最多 500 个邮件。</span><span class="sxs-lookup"><span data-stu-id="af489-p103">Quarantined messages are listed on the **quarantine** page in EAC. By default, messages are sorted from newest to oldest on the **RECEIVED** field. **SENDER**, **SUBJECT**, and **EXPIRES** values are also listed for each message. You can sort on any of these fields by clicking their headers. If you click a column header a second time, the sort order reverses. The **quarantine** page displays a maximum of 500 messages.</span></span> 
  
<span data-ttu-id="af489-p104">您可以查看所有隔离邮件的列表，或者通过指定筛选条件来搜索特定邮件（如果邮件超过 500 封，筛选还可以帮助减少结果集）。搜索并找到特定的隔离邮件之后，可以查看关于邮件的详细信息。您还可以：</span><span class="sxs-lookup"><span data-stu-id="af489-p104">You can view a list of all quarantined messages, or you can search for specific messages by specifying filter criteria (filtering can also help reduce your result set if you have more than 500 messages). After searching for and locating a specific quarantined message, you can view details about the message. You can also:</span></span>
  
- <span data-ttu-id="af489-p105">向一个或多个收件人释放邮件，并且选择向 Microsoft 垃圾邮件分析团队将其报告为误报（非垃圾邮件），他们将评估并分析该邮件。根据分析结果的不同，可能会调整服务范围内的垃圾邮件内容筛选规则，以允许发送该邮件。</span><span class="sxs-lookup"><span data-stu-id="af489-p105">Release the message to one or more recipients, and optionally report it as a false positive (not junk) message to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span>
    
- <span data-ttu-id="af489-119">释放邮件并允许接收该发件人未来发送的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="af489-119">Release the message and allow all future messages from that sender.</span></span>
    
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="af489-120">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="af489-120">What do you need to know before you begin?</span></span>
<span data-ttu-id="af489-121"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="af489-121"></span></span>

- <span data-ttu-id="af489-p106">您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的"隔离"条目。</span><span class="sxs-lookup"><span data-stu-id="af489-p106">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Quarantine" entry in the [Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx) topic.</span></span> 
    
- <span data-ttu-id="af489-p107">您可以释放或同时将多个邮件报告**隔离**页上。或者，您可以创建远程 Windows PowerShell 脚本来完成此任务。使用[Get-quarantinemessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet 以搜索的邮件，并使用其发布[版本 QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="af489-p107">You can release or report multiple messages at once on the **quarantine** page. Alternatively you can create a remote Windows PowerShell script to accomplish this task. Use the [Get-QuarantineMessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet to search for messages, and the [Release-QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet to release them.</span></span> 
    
- <span data-ttu-id="af489-127">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="af489-127">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="af489-p108">遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="af489-p108">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a><span data-ttu-id="af489-131">使用高级搜索来筛选和查找隔离邮件</span><span class="sxs-lookup"><span data-stu-id="af489-131">Use advanced search to filter and locate quarantined messages</span></span>
<span data-ttu-id="af489-132"><a name="BKMK_UseAdvancedSearchtoFilterMessages"> </a></span><span class="sxs-lookup"><span data-stu-id="af489-132"></span></span>

<span data-ttu-id="af489-p109">在 Exchange 管理中心 (EAC) 中，您可以使用高级搜索根据一些不同的条件筛选隔离邮件。这些条件可以单独使用，也可以结合使用。搜索将提供满足您的所有筛选条件的邮件列表。</span><span class="sxs-lookup"><span data-stu-id="af489-p109">In the Exchange admin center (EAC), you can filter quarantined items based on several different conditions using advanced search. You can use these conditions separately or in combination with one another. The search will provide a list of messages that meet all your filter criteria.</span></span>
  
1. <span data-ttu-id="af489-136">在 EAC 中，导航到**保护** \> **隔离**，然后单击**高级的搜索**。</span><span class="sxs-lookup"><span data-stu-id="af489-136">In EAC, navigate to **Protection** \> **quarantine**, and then click **Advanced search**.</span></span>
    
2. <span data-ttu-id="af489-p110">在**高级搜索**窗口中，选择以下条件的任意组合。选择关联复选框以启用每个条件。不支持通配符。</span><span class="sxs-lookup"><span data-stu-id="af489-p110">In the **Advanced search** window, select any combination of the following conditions. Select the associated check box to enable each condition. Wildcards aren't supported.</span></span> 
    
1. <span data-ttu-id="af489-p111">**消息 ID**此参数可用于执行目标的搜索特定邮件。例如，如果发送，或专为在组织中用户特定的邮件，但它从不到达其目标，您可以搜索邮件使用邮件跟踪功能。有关详细信息，请参阅[运行邮件跟踪和查看结果](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx)。如果您发现邮件已发送到隔离，可能是因为它匹配一个规则或被标识为垃圾邮件，然后可以轻松地找到此消息隔离通过指定其邮件 id。请确保包含完整的消息 ID 字符串。这可能包括尖括号 (\<\>)。</span><span class="sxs-lookup"><span data-stu-id="af489-p111">**Message ID** You can use this parameter to perform a targeted search for a specific message. For example, if a specific message is sent by, or intended for, a user in your organization, but it never reaches its destination, you can search for the message using the message trace feature. For details, see [Run a Message Trace and View Results](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx). If you discover that the message was sent to the quarantine, perhaps because it matched a rule or was identified as spam, you can then easily find this message in the quarantine by specifying its Message ID. Be sure to include the full Message ID string. This might include angle brackets (\<\>).</span></span> 
    
2. <span data-ttu-id="af489-146">**发件人电子邮件地址**指定邮件发件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="af489-146">**Sender email address** Specify the email address of the person who sent the message.</span></span> 
    
3. <span data-ttu-id="af489-147">**收件人电子邮件地址**指定邮件预期收件人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="af489-147">**Recipient email address** Specify the email address of the intended recipient of the message.</span></span> 
    
4. <span data-ttu-id="af489-148">**主题**指定邮件的主题行的文本。</span><span class="sxs-lookup"><span data-stu-id="af489-148">**Subject** Specify the subject line text of the message.</span></span> 
    
5. <span data-ttu-id="af489-149">**接收**您可以选择在过去 24 小时内 （**今天**），过去 48 小时内 （**最后一个 2 天**），（**最近 7 天**），过去的一周内收到的隔离邮件，或者可以选择期间消息是一个自定义的时间间隔接收隔离邮箱。</span><span class="sxs-lookup"><span data-stu-id="af489-149">**Received** You can select that the message was received by quarantine within the past 24 hours ( **Today**), within the past 48 hours ( **Last 2 days**), within the past week ( **Last 7 days**), or you can select a custom time interval during which the message was received by the quarantine.</span></span> 
    
6. <span data-ttu-id="af489-150">**过期**您可以选择邮件从隔离区删除下一个 24 小时内 （**今天**） 下, 一步 48 小时内 （**下一步 2 天**），在下一周 （**下一步 7 天**），或您可以选择自定义的时间间隔期间邮件将从隔离中删除。</span><span class="sxs-lookup"><span data-stu-id="af489-150">**Expires** You can select that the message will be deleted from quarantine within the next 24 hours ( **Today**), within the next 48 hours ( **Next 2 days**), within the next week ( **Next 7 days**), or you can select a custom time interval during which the message will be deleted from quarantine.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="af489-p112">默认情况下垃圾邮件隔离邮件将保存在隔离的 15 天时匹配传输规则的隔离的邮件隔离邮箱中保留 7 天。在这段时间后 Office 365 中删除邮件，并且他们不可检索。匹配传输规则的隔离邮件的保留期不可配置。但是，可以通过在内容筛选器策略的**保留期限 （天） 的垃圾邮件**设置缩短的垃圾邮件隔离邮件的保留期。有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="af489-p112">By default, spam-quarantined messages are kept in quarantine for 15 days, while quarantined messages that matched a transport rule are kept in the quarantine for 7 days. After this period of time Office 365 deletes the messages and they are not retrievable. The retention period for quarantined messages that matched a transport rule is not configurable. However, the retention period for spam-quarantined messages can be lowered via the **Retain spam for (days)** setting in your content filter policies. For more information, see [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span> 
  
7. <span data-ttu-id="af489-156">**类型**您可以指定是否要搜索的隔离邮件的被标识为**垃圾邮件**，或者是否搜索匹配**传输规则**的邮件。</span><span class="sxs-lookup"><span data-stu-id="af489-156">**Type** You can specify whether to search for quarantined messages that have been identified as **Spam**, or whether to search for messages that matched a **Transport rule**.</span></span>
    
3. <span data-ttu-id="af489-157">单击**确定**开始运行高级的搜索。</span><span class="sxs-lookup"><span data-stu-id="af489-157">Click **OK** to start running the advanced search.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="af489-158">若要清除搜索条件并查看隔离邮箱中的所有邮件，清除**高级搜索**窗口中的所有复选框，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="af489-158">To clear your search criteria and view all messages in the quarantine, clear all the check boxes in the **Advanced search** window, and then click **OK**.</span></span> 
  
<span data-ttu-id="af489-p113">在搜索好邮件后，匹配您的指定条件的结果将显示在用户界面中。EAC 中可显示最多 500 封邮件。</span><span class="sxs-lookup"><span data-stu-id="af489-p113">After searching for messages, the results that match your specified criteria will display in the user interface. A maximum of 500 messages can be displayed in the EAC.</span></span> 
  
## <a name="view-details-about-a-specific-quarantined-message"></a><span data-ttu-id="af489-161">查看有关特定隔离邮件的详细信息</span><span class="sxs-lookup"><span data-stu-id="af489-161">View details about a specific quarantined message</span></span>
<span data-ttu-id="af489-162"><a name="BKMK_ViewDetailsAboutaSpecificQuarantinedMessage"> </a></span><span class="sxs-lookup"><span data-stu-id="af489-162"></span></span>

<span data-ttu-id="af489-163">在**隔离**页上查找特定的隔离的邮件后，您可以查看它的详细信息。</span><span class="sxs-lookup"><span data-stu-id="af489-163">After locating a specific quarantined message on the **quarantine** page, you can view details about it.</span></span> 
  
1. <span data-ttu-id="af489-164">在**隔离**页中，选择特定的邮件，屏幕右侧的详细信息窗格中就会出现该邮件的属性摘要。</span><span class="sxs-lookup"><span data-stu-id="af489-164">On the **quarantine** page, select a specific message and a summary of the properties of that message appear in the details pane on the right side of the screen.</span></span> 
    
    <span data-ttu-id="af489-165">**邮件状态**值如下所示：</span><span class="sxs-lookup"><span data-stu-id="af489-165">The **Message status** values are as follows:</span></span> 
    
  - <span data-ttu-id="af489-166">**类型**表示邮件是否已被标识为**垃圾邮件**或与**传输规则**匹配。</span><span class="sxs-lookup"><span data-stu-id="af489-166">**Type** Denotes whether the message has been identified as **Spam** or matched a **Transport rule**.</span></span>
    
  - <span data-ttu-id="af489-167">**过期**邮件从隔离区中的删除时的日期。</span><span class="sxs-lookup"><span data-stu-id="af489-167">**Expires** The date when the message will be deleted from the quarantine.</span></span> 
    
    <span data-ttu-id="af489-168">**邮件详细信息**值如下所示：</span><span class="sxs-lookup"><span data-stu-id="af489-168">The **Message details** values are as follows:</span></span> 
    
  - <span data-ttu-id="af489-169">**发件人**发送邮件的人的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="af489-169">**Sender** The email address of the person who sent the message.</span></span> 
    
  - <span data-ttu-id="af489-170">**主题**邮件主题行文本。</span><span class="sxs-lookup"><span data-stu-id="af489-170">**Subject** The subject line text of the message.</span></span> 
    
  - <span data-ttu-id="af489-171">**接收**在其隔离邮箱收到邮件的日期。</span><span class="sxs-lookup"><span data-stu-id="af489-171">**Received** The date on which the message was received by the quarantine.</span></span> 
    
  - <span data-ttu-id="af489-172">**大小**大小 (kb) 中的消息，或者，如果邮件大小超过 999 Kb，以兆字节 (MB)。</span><span class="sxs-lookup"><span data-stu-id="af489-172">**Size** The size of the message, in kilobytes (KB), or, if the message size is greater than 999 KBs, in megabytes (MB).</span></span> 
    
  - <span data-ttu-id="af489-p114">**查看邮件头**单击此链接以打开**邮件头**对话框，让您查看消息标头文本。您还可以将消息标头文本复制到剪贴板上，并将其粘贴到[邮件标头分析器](https://testconnectivity.microsoft.com/?tabid=mha)。一次在邮件标头分析器工具中，单击以检索有关标头信息的**分析的邮件头**。</span><span class="sxs-lookup"><span data-stu-id="af489-p114">**View message header** Click this link to open the **message header** dialog box, which lets you view the message header text. You can also copy the message header text to your clipboard and paste it into the [Message Header Analyzer](https://testconnectivity.microsoft.com/?tabid=mha). Once in the Message Header Analyzer tool, click **Analyze headers** in order to retrieve information about the header.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="af489-176">有关服务插入的特定反垃圾邮件的邮件头字段的信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="af489-176">For information about specific anti-spam message header fields inserted by the service, see [Anti-spam message headers](anti-spam-message-headers.md).</span></span> 
  
  - <span data-ttu-id="af489-177">**预览电子邮件**单击此链接以查看邮件的文本。</span><span class="sxs-lookup"><span data-stu-id="af489-177">**Preview email message** Click this link to review the text of the message.</span></span> 
    
2. <span data-ttu-id="af489-178">如果双击隔离的邮件，**隔离邮件**窗口打开，并显示以下信息：</span><span class="sxs-lookup"><span data-stu-id="af489-178">If you double-click a quarantined message, the **Quarantined message** window opens and displays the following information:</span></span> 
    
  - <span data-ttu-id="af489-179">**释放到**向其邮件被释放，如果有的所有电子邮件地址列表。</span><span class="sxs-lookup"><span data-stu-id="af489-179">**Released to** A list of all email addresses to whom the message has been released, if any.</span></span> 
    
  - <span data-ttu-id="af489-p115">**尚未释放到**向其邮件不被释放，如果有的所有电子邮件地址列表。您可以单击**发布到**链接以释放邮件;有关发布一条消息的详细信息，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="af489-p115">**Not yet released to** A list of all email addresses to whom the message has not been released, if any. You can click the **Release to** link in order to release the message; for more information about releasing a message, see the next section.</span></span> 
    
  - <span data-ttu-id="af489-182">**消息 ID**Internet 邮件 ID (也称为客户端 ID) 的邮件头中找到。</span><span class="sxs-lookup"><span data-stu-id="af489-182">**Message ID** The Internet Message ID (also known as the Client ID) found in the header of the message.</span></span> 
    
    <span data-ttu-id="af489-183">单击**关闭**以返回到主隔离邮件窗格。</span><span class="sxs-lookup"><span data-stu-id="af489-183">Click **Close** to return to the main quarantine pane.</span></span> 
    
## <a name="release-messages-from-quarantine"></a><span data-ttu-id="af489-184">从隔离区中释放邮件</span><span class="sxs-lookup"><span data-stu-id="af489-184">Release messages from quarantine</span></span>
<span data-ttu-id="af489-185"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="af489-185"></span></span>

<span data-ttu-id="af489-186">如果您想将邮件释放给收件人，您可以：</span><span class="sxs-lookup"><span data-stu-id="af489-186">If you want to release messages to recipients, your options are:</span></span>
  
- [<span data-ttu-id="af489-187">释放隔离邮件并允许接收该发件人未来发送的邮件</span><span class="sxs-lookup"><span data-stu-id="af489-187">Release a quarantined message and allow future messages from the sender</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessageallowfuturemessagesfromsender)
    
- [<span data-ttu-id="af489-188">将隔离邮件释放给特定收件人，而不将其报告为误报</span><span class="sxs-lookup"><span data-stu-id="af489-188">Release a quarantined message to specific recipients without reporting it as a false positive</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive)
    
- [<span data-ttu-id="af489-189">将一个或多个隔离邮件释放给所有收件人</span><span class="sxs-lookup"><span data-stu-id="af489-189">Release one or more quarantined messages to all recipients</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipients)
    
- [<span data-ttu-id="af489-190">将一个或多个隔离邮件释放给所有收件人并将其报告为误报</span><span class="sxs-lookup"><span data-stu-id="af489-190">Release one or more quarantined messages to all recipients and report false positives</span></span>](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives)
    
### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a><span data-ttu-id="af489-191">释放隔离邮件并允许接收该发件人未来发送的邮件</span><span class="sxs-lookup"><span data-stu-id="af489-191">Release a quarantined message and allow future messages from the sender</span></span>
<span data-ttu-id="af489-192"><a name="Releasequarantinedmessageallowfuturemessagesfromsender"> </a></span><span class="sxs-lookup"><span data-stu-id="af489-192"></span></span>

1. <span data-ttu-id="af489-193">在 EAC 中，导航到**保护** \> **隔离**。</span><span class="sxs-lookup"><span data-stu-id="af489-193">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="af489-194">单击要选择它，然后单击**释放邮件**图标，如以下屏幕截图中所示的消息。</span><span class="sxs-lookup"><span data-stu-id="af489-194">Click on a message to select it and then click the **Release Message** icon as shown in the following screen shot.</span></span> 
  
![显示隔离页（包含突出显示的释放邮件图标和释放选项）](media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)
  
<span data-ttu-id="af489-196">从下拉列表中单击**所选的邮件释放并允许发件人**。</span><span class="sxs-lookup"><span data-stu-id="af489-196">Click **Release selected message and allow sender** from the drop-down list.</span></span> 
    
3. <span data-ttu-id="af489-p116">**释放邮件并允许发件人**对话框将打开。（可选） 您可以选择将邮件报告给 Microsoft，然后单击**释放，并允许**。邮件将被释放给所有收件人它向其发送，并将允许来自此发件人以后的所有邮件。但是，如果此消息由于传输规则而隔离了或阻止发件人，发件人将继续为以后的邮件被阻止。</span><span class="sxs-lookup"><span data-stu-id="af489-p116">The **release message and allow sender** dialog box opens. Optionally, you can choose to report the message to Microsoft, then click **release and allow**. The message will be released to all recipients it's addressed to and all future messages from this sender will be allowed. However, if this message was quarantined because of a transport rule or blocked sender, the sender will continue to be blocked for future messages.</span></span> 
    
### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a><span data-ttu-id="af489-201">将隔离邮件释放给特定收件人，而不将其报告为误报</span><span class="sxs-lookup"><span data-stu-id="af489-201">Release a quarantined message to specific recipients without reporting it as a false positive</span></span>
<span data-ttu-id="af489-202"><a name="Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive"> </a></span><span class="sxs-lookup"><span data-stu-id="af489-202"></span></span>

1. <span data-ttu-id="af489-203">在 EAC 中，导航到**保护** \> **隔离**。</span><span class="sxs-lookup"><span data-stu-id="af489-203">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="af489-204">选择一封邮件，单击**释放邮件**图标，然后单击从下拉列表中的**释放到特定收件人的邮件**。</span><span class="sxs-lookup"><span data-stu-id="af489-204">Select a message, click the **Release Message** icon, and then click **Release message to specific recipients** from the drop-down list.</span></span> 
    
3. <span data-ttu-id="af489-205">在**释放邮件**对话框中，选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="af489-205">In the **release message** dialog box, select one of the following options:</span></span> 
    
  - <span data-ttu-id="af489-p117">**释放给所有收件人的邮件**如果选择此选项时，都可以识别一条消息，不能多次释放到同一个收件人。如果收件人先前已接收邮件，它将不会释放再次到该收件人。</span><span class="sxs-lookup"><span data-stu-id="af489-p117">**Release message to all recipients** When you select this option, be aware that a message cannot be released more than once to the same recipient. If a recipient has previously received the message, it will not be released again to that recipient.</span></span> 
    
  - <span data-ttu-id="af489-p118">**释放给指定的收件人的邮件**选择的收件人可以向其释放邮件。仅可以每个收件人一次发布一条消息，因为仅收件人可以发布向其显示在此列表。支持多选择。收件人选择后，单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="af489-p118">**Release message to specified recipients** Select the recipient(s) to whom the message can be released. Because a message can only be released once to each recipient, only recipients to whom it can be released appear in this list. Multi-selection is supported. After making your recipient selections, click **add**.</span></span>
    
4. <span data-ttu-id="af489-212">单击**版本**。</span><span class="sxs-lookup"><span data-stu-id="af489-212">Click **release**.</span></span> 
    
<span data-ttu-id="af489-213">如果单击**刷新**![刷新图标](media/ITPro-EAC-RefreshIcon.png)图标可刷新数据，然后双击邮件，您应看到它已释放给预期收件人。</span><span class="sxs-lookup"><span data-stu-id="af489-213">If you click the **Refresh**![Refresh Icon](media/ITPro-EAC-RefreshIcon.png) icon to refresh your data, and then double-click the message, you should see that it's been released to the intended recipients.</span></span> 
  
### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a><span data-ttu-id="af489-214">将一个或多个隔离邮件释放给所有收件人</span><span class="sxs-lookup"><span data-stu-id="af489-214">Release one or more quarantined messages to all recipients</span></span>
<span data-ttu-id="af489-215"><a name="Releaseoneormorequarantinedmessagestoallrecipients"> </a></span><span class="sxs-lookup"><span data-stu-id="af489-215"></span></span>

1. <span data-ttu-id="af489-216">在 EAC 中，导航到**保护** \> **隔离**。</span><span class="sxs-lookup"><span data-stu-id="af489-216">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="af489-p119">单击要选择它，或者使用 shift 键选择多个邮件的消息。然后单击**释放邮件**图标。</span><span class="sxs-lookup"><span data-stu-id="af489-p119">Click on a message to select it, or use the shift key to select multiple messages. Then click the **Release Message** icon.</span></span> 
    
3. <span data-ttu-id="af489-219">从下拉列表中单击**版本选定的邮件给所有收件人**。</span><span class="sxs-lookup"><span data-stu-id="af489-219">Click **Release selected message(s) to ALL recipients** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="af489-p120">警告对话框将打开。阅读警告，如果您想要继续，请选择**是**。如果选择此选项时，都可以识别一条消息，不能多次释放到同一个收件人。如果收件人先前已接收邮件，它将不会释放再次到该收件人。</span><span class="sxs-lookup"><span data-stu-id="af489-p120">The warning dialog box opens. Read the warning and select **Yes** if you want to proceed. When you select this option, be aware that a message cannot be released more than once to the same recipient. If a recipient has previously received the message, it will not be released again to that recipient.</span></span> 
    
### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a><span data-ttu-id="af489-224">将一个或多个隔离邮件释放给所有收件人并将其报告为误报</span><span class="sxs-lookup"><span data-stu-id="af489-224">Release one or more quarantined messages to all recipients and report false positives</span></span>
<span data-ttu-id="af489-225"><a name="Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives"> </a></span><span class="sxs-lookup"><span data-stu-id="af489-225"></span></span>

1. <span data-ttu-id="af489-226">在 EAC 中，导航到**保护** \> **隔离**。</span><span class="sxs-lookup"><span data-stu-id="af489-226">In EAC, navigate to **Protection** \> **quarantine**.</span></span>
    
2. <span data-ttu-id="af489-p121">单击要选择它，或者使用 shift 键选择多个邮件的消息。然后单击**释放邮件**图标。</span><span class="sxs-lookup"><span data-stu-id="af489-p121">Click on a message to select it, or use the shift key to select multiple messages. Then click the **Release Message** icon.</span></span> 
    
3. <span data-ttu-id="af489-229">从下拉列表中单击**发布所选邮件并报告为误报**。</span><span class="sxs-lookup"><span data-stu-id="af489-229">Click **Release selected message(s) and report as false positive** from the drop-down list.</span></span> 
    
4. <span data-ttu-id="af489-p122">警告对话框将打开。阅读警告，如果您想要继续，请选择**是**。如果选择此选项时，都可以识别一条消息，不能多次释放到同一个收件人。如果收件人先前已接收邮件，它将不会释放再次到该收件人。</span><span class="sxs-lookup"><span data-stu-id="af489-p122">The warning dialog box opens. Read the warning and select **Yes** if you want to proceed. When you select this option, be aware that a message cannot be released more than once to the same recipient. If a recipient has previously received the message, it will not be released again to that recipient.</span></span> 
    
     <span data-ttu-id="af489-p123">选择此选项时，会将邮件释放到所有尚未收到此邮件的收件人。如果此邮件是隔离的垃圾邮件，还会将其报告给 Microsoft 垃圾邮件分析团队，该团队将评估和分析该邮件。根据分析结果的不同，可能会调整服务范围内的垃圾邮件内容筛选规则，以允许发送该邮件。</span><span class="sxs-lookup"><span data-stu-id="af489-p123">When you choose this option, the message will be released to all recipients who have not yet received it. If it's a spam-quarantined message, it will also be reported to the Microsoft Spam Analysis Team, who will evaluate and analyze the message. Depending on the results of the analysis, the service-wide spam content filter rules may be adjusted to allow the message through.</span></span> 
    
> [!TIP]
> <span data-ttu-id="af489-237">按照[如何确保邮件不会标记为垃圾邮件](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md)中的步骤，确保邮件未标记为垃圾邮件。</span><span class="sxs-lookup"><span data-stu-id="af489-237">Help ensure that a message isn't marked as spam by following the steps in [How to help ensure that a message isn't marked as spam](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md).</span></span> 
  
<span data-ttu-id="af489-238">如果单击**刷新**![刷新图标](media/ITPro-EAC-RefreshIcon.png)图标可刷新数据，然后双击邮件，您应看到它已释放给预期收件人。</span><span class="sxs-lookup"><span data-stu-id="af489-238">If you click the **Refresh**![Refresh Icon](media/ITPro-EAC-RefreshIcon.png) icon to refresh your data, and then double-click the message, you should see that it's been released to the intended recipients.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="af489-239">详细信息</span><span class="sxs-lookup"><span data-stu-id="af489-239">For more information</span></span>
<span data-ttu-id="af489-240"><a name="sectionSection4"> </a></span><span class="sxs-lookup"><span data-stu-id="af489-240"></span></span>

[<span data-ttu-id="af489-241">隔离常见问题解答</span><span class="sxs-lookup"><span data-stu-id="af489-241">Quarantine FAQ</span></span>](quarantine-faq.md)
  

