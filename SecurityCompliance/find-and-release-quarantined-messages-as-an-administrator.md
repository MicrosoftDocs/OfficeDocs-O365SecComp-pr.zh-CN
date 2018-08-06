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
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a>以管理员身份查找并释放隔离邮件

本主题介绍了 Exchange Online 和 Exchange Online Protection (EOP) 管理员如何在 Exchange 管理中心 (EAC) 中查找、释放和报告隔离邮件。Office 365 将这些邮件发送到隔离邮箱的原因是，它们被标识为垃圾邮件或与传输规则匹配。 
  
使用安全&amp;而不是 EAC 完成这些任务以及视图的任何和发送到隔离因为它们包含恶意软件的邮件处理的合规性中心。有关详细信息，请参阅[Office 365 中的隔离电子邮件](https://support.office.com/en-US/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b)。
  
在 EAC 中的**隔离**页上列出了隔离的邮件。默认情况下，消息按降序对**RECEIVED**字段中。**发件人**、**主题**和**EXPIRES**值还会列出的每条消息。可以通过单击其邮件头在其中的任何字段进行排序。如果第二次单击列标题，将反转排序顺序。**隔离**页上显示最多 500 个邮件。 
  
您可以查看所有隔离邮件的列表，或者通过指定筛选条件来搜索特定邮件（如果邮件超过 500 封，筛选还可以帮助减少结果集）。搜索并找到特定的隔离邮件之后，可以查看关于邮件的详细信息。您还可以：
  
- 向一个或多个收件人释放邮件，并且选择向 Microsoft 垃圾邮件分析团队将其报告为误报（非垃圾邮件），他们将评估并分析该邮件。根据分析结果的不同，可能会调整服务范围内的垃圾邮件内容筛选规则，以允许发送该邮件。
    
- 释放邮件并允许接收该发件人未来发送的所有邮件。
    
## <a name="what-do-you-need-to-know-before-you-begin"></a>在开始之前，您需要知道什么？
<a name="sectionSection0"> </a>

- 您需要执行此过程之前为其分配权限。若要查看所需的权限，请参阅[Feature Permissions in Exchange Online](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的"隔离"条目。 
    
- 您可以释放或同时将多个邮件报告**隔离**页上。或者，您可以创建远程 Windows PowerShell 脚本来完成此任务。使用[Get-quarantinemessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet 以搜索的邮件，并使用其发布[版本 QuarantineMessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet。 
    
- 若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
    
> [!TIP]
> 遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a>使用高级搜索来筛选和查找隔离邮件
<a name="BKMK_UseAdvancedSearchtoFilterMessages"> </a>

在 Exchange 管理中心 (EAC) 中，您可以使用高级搜索根据一些不同的条件筛选隔离邮件。这些条件可以单独使用，也可以结合使用。搜索将提供满足您的所有筛选条件的邮件列表。
  
1. 在 EAC 中，导航到**保护** \> **隔离**，然后单击**高级的搜索**。
    
2. 在**高级搜索**窗口中，选择以下条件的任意组合。选择关联复选框以启用每个条件。不支持通配符。 
    
1. **消息 ID**此参数可用于执行目标的搜索特定邮件。例如，如果发送，或专为在组织中用户特定的邮件，但它从不到达其目标，您可以搜索邮件使用邮件跟踪功能。有关详细信息，请参阅[运行邮件跟踪和查看结果](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx)。如果您发现邮件已发送到隔离，可能是因为它匹配一个规则或被标识为垃圾邮件，然后可以轻松地找到此消息隔离通过指定其邮件 id。请确保包含完整的消息 ID 字符串。这可能包括尖括号 (\<\>)。 
    
2. **发件人电子邮件地址**指定邮件发件人的电子邮件地址。 
    
3. **收件人电子邮件地址**指定邮件预期收件人的电子邮件地址。 
    
4. **主题**指定邮件的主题行的文本。 
    
5. **接收**您可以选择在过去 24 小时内 （**今天**），过去 48 小时内 （**最后一个 2 天**），（**最近 7 天**），过去的一周内收到的隔离邮件，或者可以选择期间消息是一个自定义的时间间隔接收隔离邮箱。 
    
6. **过期**您可以选择邮件从隔离区删除下一个 24 小时内 （**今天**） 下, 一步 48 小时内 （**下一步 2 天**），在下一周 （**下一步 7 天**），或您可以选择自定义的时间间隔期间邮件将从隔离中删除。
    
    > [!IMPORTANT]
    > 默认情况下垃圾邮件隔离邮件将保存在隔离的 15 天时匹配传输规则的隔离的邮件隔离邮箱中保留 7 天。在这段时间后 Office 365 中删除邮件，并且他们不可检索。匹配传输规则的隔离邮件的保留期不可配置。但是，可以通过在内容筛选器策略的**保留期限 （天） 的垃圾邮件**设置缩短的垃圾邮件隔离邮件的保留期。有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。 
  
7. **类型**您可以指定是否要搜索的隔离邮件的被标识为**垃圾邮件**，或者是否搜索匹配**传输规则**的邮件。
    
3. 单击**确定**开始运行高级的搜索。 
    
    > [!NOTE]
    > 若要清除搜索条件并查看隔离邮箱中的所有邮件，清除**高级搜索**窗口中的所有复选框，然后单击**确定**。 
  
在搜索好邮件后，匹配您的指定条件的结果将显示在用户界面中。EAC 中可显示最多 500 封邮件。 
  
## <a name="view-details-about-a-specific-quarantined-message"></a>查看有关特定隔离邮件的详细信息
<a name="BKMK_ViewDetailsAboutaSpecificQuarantinedMessage"> </a>

在**隔离**页上查找特定的隔离的邮件后，您可以查看它的详细信息。 
  
1. 在**隔离**页中，选择特定的邮件，屏幕右侧的详细信息窗格中就会出现该邮件的属性摘要。 
    
    **邮件状态**值如下所示： 
    
  - **类型**表示邮件是否已被标识为**垃圾邮件**或与**传输规则**匹配。
    
  - **过期**邮件从隔离区中的删除时的日期。 
    
    **邮件详细信息**值如下所示： 
    
  - **发件人**发送邮件的人的电子邮件地址。 
    
  - **主题**邮件主题行文本。 
    
  - **接收**在其隔离邮箱收到邮件的日期。 
    
  - **大小**大小 (kb) 中的消息，或者，如果邮件大小超过 999 Kb，以兆字节 (MB)。 
    
  - **查看邮件头**单击此链接以打开**邮件头**对话框，让您查看消息标头文本。您还可以将消息标头文本复制到剪贴板上，并将其粘贴到[邮件标头分析器](https://testconnectivity.microsoft.com/?tabid=mha)。一次在邮件标头分析器工具中，单击以检索有关标头信息的**分析的邮件头**。 
    
    > [!TIP]
    > 有关服务插入的特定反垃圾邮件的邮件头字段的信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。 
  
  - **预览电子邮件**单击此链接以查看邮件的文本。 
    
2. 如果双击隔离的邮件，**隔离邮件**窗口打开，并显示以下信息： 
    
  - **释放到**向其邮件被释放，如果有的所有电子邮件地址列表。 
    
  - **尚未释放到**向其邮件不被释放，如果有的所有电子邮件地址列表。您可以单击**发布到**链接以释放邮件;有关发布一条消息的详细信息，请参阅下一节。 
    
  - **消息 ID**Internet 邮件 ID (也称为客户端 ID) 的邮件头中找到。 
    
    单击**关闭**以返回到主隔离邮件窗格。 
    
## <a name="release-messages-from-quarantine"></a>从隔离区中释放邮件
<a name="sectionSection3"> </a>

如果您想将邮件释放给收件人，您可以：
  
- [释放隔离邮件并允许接收该发件人未来发送的邮件](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessageallowfuturemessagesfromsender)
    
- [将隔离邮件释放给特定收件人，而不将其报告为误报](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive)
    
- [将一个或多个隔离邮件释放给所有收件人](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipients)
    
- [将一个或多个隔离邮件释放给所有收件人并将其报告为误报](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives)
    
### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a>释放隔离邮件并允许接收该发件人未来发送的邮件
<a name="Releasequarantinedmessageallowfuturemessagesfromsender"> </a>

1. 在 EAC 中，导航到**保护** \> **隔离**。
    
2. 单击要选择它，然后单击**释放邮件**图标，如以下屏幕截图中所示的消息。 
  
![显示隔离页（包含突出显示的释放邮件图标和释放选项）](media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)
  
从下拉列表中单击**所选的邮件释放并允许发件人**。 
    
3. **释放邮件并允许发件人**对话框将打开。（可选） 您可以选择将邮件报告给 Microsoft，然后单击**释放，并允许**。邮件将被释放给所有收件人它向其发送，并将允许来自此发件人以后的所有邮件。但是，如果此消息由于传输规则而隔离了或阻止发件人，发件人将继续为以后的邮件被阻止。 
    
### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a>将隔离邮件释放给特定收件人，而不将其报告为误报
<a name="Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive"> </a>

1. 在 EAC 中，导航到**保护** \> **隔离**。
    
2. 选择一封邮件，单击**释放邮件**图标，然后单击从下拉列表中的**释放到特定收件人的邮件**。 
    
3. 在**释放邮件**对话框中，选择下列选项之一： 
    
  - **释放给所有收件人的邮件**如果选择此选项时，都可以识别一条消息，不能多次释放到同一个收件人。如果收件人先前已接收邮件，它将不会释放再次到该收件人。 
    
  - **释放给指定的收件人的邮件**选择的收件人可以向其释放邮件。仅可以每个收件人一次发布一条消息，因为仅收件人可以发布向其显示在此列表。支持多选择。收件人选择后，单击**添加**。
    
4. 单击**版本**。 
    
如果单击**刷新**![刷新图标](media/ITPro-EAC-RefreshIcon.png)图标可刷新数据，然后双击邮件，您应看到它已释放给预期收件人。 
  
### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a>将一个或多个隔离邮件释放给所有收件人
<a name="Releaseoneormorequarantinedmessagestoallrecipients"> </a>

1. 在 EAC 中，导航到**保护** \> **隔离**。
    
2. 单击要选择它，或者使用 shift 键选择多个邮件的消息。然后单击**释放邮件**图标。 
    
3. 从下拉列表中单击**版本选定的邮件给所有收件人**。 
    
4. 警告对话框将打开。阅读警告，如果您想要继续，请选择**是**。如果选择此选项时，都可以识别一条消息，不能多次释放到同一个收件人。如果收件人先前已接收邮件，它将不会释放再次到该收件人。 
    
### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a>将一个或多个隔离邮件释放给所有收件人并将其报告为误报
<a name="Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives"> </a>

1. 在 EAC 中，导航到**保护** \> **隔离**。
    
2. 单击要选择它，或者使用 shift 键选择多个邮件的消息。然后单击**释放邮件**图标。 
    
3. 从下拉列表中单击**发布所选邮件并报告为误报**。 
    
4. 警告对话框将打开。阅读警告，如果您想要继续，请选择**是**。如果选择此选项时，都可以识别一条消息，不能多次释放到同一个收件人。如果收件人先前已接收邮件，它将不会释放再次到该收件人。 
    
     选择此选项时，会将邮件释放到所有尚未收到此邮件的收件人。如果此邮件是隔离的垃圾邮件，还会将其报告给 Microsoft 垃圾邮件分析团队，该团队将评估和分析该邮件。根据分析结果的不同，可能会调整服务范围内的垃圾邮件内容筛选规则，以允许发送该邮件。 
    
> [!TIP]
> 按照[如何确保邮件不会标记为垃圾邮件](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md)中的步骤，确保邮件未标记为垃圾邮件。 
  
如果单击**刷新**![刷新图标](media/ITPro-EAC-RefreshIcon.png)图标可刷新数据，然后双击邮件，您应看到它已释放给预期收件人。 
  
## <a name="for-more-information"></a>详细信息
<a name="sectionSection4"> </a>

[隔离常见问题解答](quarantine-faq.md)
  

