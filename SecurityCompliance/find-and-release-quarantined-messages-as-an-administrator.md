---
title: 以管理员身份查找并释放隔离邮件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/16/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: 本主题介绍了 Exchange Online 和 Exchange Online Protection (EOP) 管理员如何在 Exchange 管理中心 (EAC) 中查找、释放和报告隔离邮件。
ms.openlocfilehash: 1f2b3733cbba3c09e1ec7ca25377ac96d5c89147
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599378"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a>以管理员身份查找并释放隔离邮件

本主题介绍了 Exchange Online 和 Exchange Online Protection (EOP) 管理员如何在 Exchange 管理中心 (EAC) 中查找、释放和报告隔离邮件。 Office 365 将邮件定向到隔离区, 因为它们被标识为垃圾邮件或与邮件流规则匹配 (也称为 "传输规则")。 
  
使用安全&amp;合规中心 (而不是 EAC) 完成这些任务, 并查看和处理发送到隔离的邮件, 因为它们包含恶意软件。 有关详细信息, 请参阅[在 Office 365 中隔离电子邮件消息](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b)。
  
已隔离邮件在 EAC 的 "**隔离**" 页面上列出。 默认情况下, "**接收**时间" 字段中的邮件按从最新到最旧的顺序排列。 还将为每封邮件列出“发件人”****、“主题”**** 和“到期”**** 值。 您可以通过单击标题来对任何字段排序。 再次单击列标题将按相反顺序排序。 "**隔离**" 页面最多显示500个邮件。 
  
您可以查看所有隔离邮件的列表，或者通过指定筛选条件来搜索特定邮件（如果邮件超过 500 封，筛选还可以帮助减少结果集）。搜索并找到特定的隔离邮件之后，可以查看关于邮件的详细信息。您还可以：
  
- 向一个或多个收件人释放邮件，并且选择向 Microsoft 垃圾邮件分析团队将其报告为误报（非垃圾邮件），他们将评估并分析该邮件。根据分析结果的不同，可能会调整服务范围内的垃圾邮件内容筛选规则，以允许发送该邮件。
    
- 释放邮件并允许接收该发件人未来发送的所有邮件。
    
## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？
<a name="sectionSection0"> </a>

- 您必须先获得权限，然后才能执行此过程或多个过程。 若要查看所需的权限, 请参阅[Exchange Online 中的功能权限](http://technet.microsoft.com/library/15073ce1-0917-403b-8839-02a2ebc96e16.aspx)主题中的 "隔离" 条目。 
    
- 您可以在 "**隔离**" 页面上一次释放或报告多封邮件。 或者, 您可以创建一个远程 Windows PowerShell 脚本来完成此任务。 使用[get-quarantinemessage](http://technet.microsoft.com/library/88026da1-8dbc-49e7-80e8-112a32773c34.aspx) cmdlet 搜索邮件, 并使用[get-quarantinemessage](http://technet.microsoft.com/library/4a3aa05c-238f-46f2-b8dd-b0e3c38eab3e.aspx) cmdlet 释放邮件。 
    
- 若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。
    
> [!TIP]
> 遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。 
  
## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a>使用高级搜索来筛选和查找隔离邮件
<a name="BKMK_UseAdvancedSearchtoFilterMessages"> </a>

在 Exchange 管理中心 (EAC) 中，您可以使用高级搜索根据一些不同的条件筛选隔离邮件。这些条件可以单独使用，也可以结合使用。搜索将提供满足您的所有筛选条件的邮件列表。
  
1. 在 EAC 中, 导航到 "**保护** \> **隔离**", 然后单击 "**高级搜索**"。
    
2. 在 "**高级搜索**" 窗口中, 选择下列条件的任意组合。 选中关联的复选框，以启用各个条件。 不支持通配符。 
    
1. **邮件 ID**您可以使用此参数对特定邮件执行目标搜索。 例如，如果特定邮件由贵组织的用户发送，或准备发送给贵组织的用户，但是未抵达目标收件人，则您可以使用邮件跟踪功能搜索该邮件。 有关详细信息，请参阅 [运行邮件跟踪和查看结果](http://technet.microsoft.com/library/74a9fc59-7e0e-4832-baf9-2a86418b0079.aspx)。 如果您发现邮件被发送到隔离区，可能是因为它符合某个规则或被标识为垃圾邮件，您可以通过指定其邮件 ID，在隔离区中轻松找到此邮件。 请务必包含完整的邮件 ID 字符串。 这可能包括尖括号 (\<\>)。 
    
2. **发件人电子邮件地址**指定发送邮件的人员的电子邮件地址。 
    
3. **收件人电子邮件地址**指定邮件的预期收件人的电子邮件地址。 
    
4. **主题**指定邮件的主题行文本。 
    
5. **接收**您可以选择在过去24小时内 ("**今天**")、过去的48小时内 ("过去**2 天**")、过去一周内 ("过去**7 天**") 的隔离区中接收邮件, 也可以选择邮件的自定义时间间隔。由隔离区接收。 
    
6. **过期**您可以选择在接下来的24小时内 ("**今天**"), 在接下来的48小时内 (**接下来的2天**), 在下一周内 ("**接下来7天**"), 或者您可以选择一个自定义时间间隔, 邮件将从隔离区中删除。
    
    > [!IMPORTANT]
    > 默认情况下, 垃圾邮件隔离的邮件在15天内保留隔离, 而与邮件流规则匹配的隔离邮件将保留在隔离时间7天内。 7 天后，这些邮件将被 Office 365 删除并且不可检索。 与邮件流规则匹配的隔离邮件的保留期不可配置。 但是, 垃圾邮件隔离邮件的保留期可以通过内容筛选器策略中的 "**保留垃圾邮件 (天)** " 设置来降低。 有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。 
  
7. **类型**您可以指定是否搜索已被标识为**垃圾**邮件的隔离邮件, 或者是否搜索与邮件流规则匹配的邮件 (**传输规则**)。
    
3. 单击 **"确定"** 开始运行高级搜索。 
    
    > [!NOTE]
    > 若要清除搜索条件并查看隔离中的所有邮件, 请清除 "**高级搜索**" 窗口中的所有复选框, 然后单击 **"确定"**。 
  
在搜索好邮件后，匹配您的指定条件的结果将显示在用户界面中。EAC 中可显示最多 500 封邮件。 
  
## <a name="view-details-about-a-specific-quarantined-message"></a>查看有关特定隔离邮件的详细信息
<a name="BKMK_ViewDetailsAboutaSpecificQuarantinedMessage"> </a>

在**隔离**页上找到特定的隔离邮件后, 您可以查看有关该邮件的详细信息。 
  
1. 在 "**隔离**" 页面上, 选择特定的邮件, 屏幕右侧的详细信息窗格中将显示该邮件的属性摘要。 
    
    **邮件状态**值如下所示: 
    
  - **类型**指示是否已将邮件标识为**垃圾**邮件或与邮件流规则 (**传输规则**) 相匹配。
    
  - **过期**将从隔离区中删除邮件的日期。 
    
    **消息详细信息**值如下所示: 
    
  - **发件人**发送邮件的人员的电子邮件地址。 
    
  - **主题**邮件的主题行文本。 
    
  - **接收**隔离人收到邮件的日期。 
    
  - **尺寸**邮件的大小, 以千字节 (KB) 为单位, 如果邮件大小大于 999 Kb, 则为兆字节 (MB)。 
    
  - **查看邮件头**单击此链接可打开 "**邮件头**" 对话框, 您可以通过该对话框查看邮件头文本。 您还可以将邮件头文本复制到剪贴板，并粘贴到 [邮件头分析器](https://testconnectivity.microsoft.com/?tabid=mha)。 进入邮件头分析器工具后，单击" **分析标头**"以检索关于标头的信息。 
    
    > [!TIP]
    > 有关服务插入的特定反垃圾邮件的邮件头字段的信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。 
  
  - **预览电子邮件**单击此链接可查看邮件文本。 
    
2. 如果双击隔离邮件,**隔离的邮件**窗口将打开, 并显示以下信息: 
    
  - **发布到**已发布邮件的所有电子邮件地址的列表 (如果有)。 
    
  - **尚未发布到**尚未发布邮件的所有电子邮件地址的列表 (如果有)。 您可以单击 "**发布到**" 链接以释放邮件;有关释放邮件的详细信息, 请参阅下一节。 
    
  - **邮件 ID**在邮件头中找到的 Internet 邮件 ID (也称为 "客户端 ID")。 
    
    单击 "**关闭**" 返回到主隔离窗格。 
    
## <a name="release-messages-from-quarantine"></a>从隔离区中释放邮件
<a name="sectionSection3"> </a>

如果您想将邮件释放给收件人，您可以：
  
- [释放隔离邮件并允许接收该发件人未来发送的邮件](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessageallowfuturemessagesfromsender)
    
- [将隔离邮件释放给特定收件人，而不将其报告为误报](find-and-release-quarantined-messages-as-an-administrator.md#Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive)
    
- [将一个或多个隔离邮件释放给所有收件人](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipients)
    
- [将一个或多个隔离邮件释放给所有收件人并将其报告为误报](find-and-release-quarantined-messages-as-an-administrator.md#Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives)
    
### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a>释放隔离邮件并允许接收该发件人未来发送的邮件
<a name="Releasequarantinedmessageallowfuturemessagesfromsender"> </a>

1. 在 EAC 中, 导航到 "**保护** \> **隔离**"。
    
2. 单击邮件以将其选中, 然后单击 "**释放邮件**" 图标, 如下面的屏幕截图所示。 
  
![显示隔离页（包含突出显示的释放邮件图标和释放选项）](media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)
  
从下拉列表中单击 "**释放所选邮件并允许发件人**"。 
    
3. 将打开 "**释放邮件并允许发件人**" 对话框。 (可选) 您可以选择向 Microsoft 报告邮件, 然后单击 "**释放并允许**"。 该邮件将被释放给所有收件人并将允许接收此发件人未来发送的邮件。 但是, 如果此邮件是由于邮件流规则或阻止发件人而被隔离的, 则将继续阻止发件人的后续邮件。 
    
### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a>将隔离邮件释放给特定收件人，而不将其报告为误报
<a name="Releasequarantinedmessagetospecificrecipientswithoutreportingasfalsepositive"> </a>

1. 在 EAC 中, 导航到 "**保护** \> **隔离**"。
    
2. 选择一封邮件, 单击 "**释放邮件**" 图标, 然后从下拉列表中单击 "**将邮件释放给特定收件人**"。 
    
3. 在“释放邮件”**** 对话框中，选择下列选项之一： 
    
  - **向所有收件人释放邮件**选择此选项时, 请注意, 不能将一封邮件释放到同一收件人的一次。 如果收件人之前已经收到此邮件，则邮件不会再次释放给该收件人。 
    
  - **将邮件释放给指定的收件人**选择可将邮件释放到的收件人。 由于一封邮件只能释放给每个收件人一次，因此该列表仅显示邮件可被释放给的目标收件人。 支持多选。 做出选择后, 单击 "**添加**"。
    
4. 单击“释放”****。 
    
如果单击 "**刷新**![刷新" 图标](media/ITPro-EAC-RefreshIcon.gif)图标刷新数据, 然后双击邮件, 您应该会看到它已发布给预期的收件人。 
  
### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a>将一个或多个隔离邮件释放给所有收件人
<a name="Releaseoneormorequarantinedmessagestoallrecipients"> </a>

1. 在 EAC 中, 导航到 "**保护** \> **隔离**"。
    
2. 单击邮件以选中它，或使用 Shift 键来选择多封邮件。 然后单击 "**释放邮件**" 图标。 
    
3. 从下拉列表中单击 "**将所选邮件释放给所有收件人**"。 
    
4. 此时会打开一个警告对话框。 阅读警告, 如果要继续, 请选择 **"是"** 。 选择此选项时，请注意不能将一封邮件释放给同一收件人超过一次。 如果收件人之前已经收到此邮件，则邮件不会再次释放给该收件人。 
    
### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a>将一个或多个隔离邮件释放给所有收件人并将其报告为误报
<a name="Releaseoneormorequarantinedmessagestoallrecipientsandreportfalsepositives"> </a>

1. 在 EAC 中, 导航到 "**保护** \> **隔离**"。
    
2. 单击邮件以选中它，或使用 Shift 键来选择多封邮件。 然后单击 "**释放邮件**" 图标。 
    
3. 从下拉列表中单击 "**释放所选邮件并报告为误报**"。 
    
4. 此时会打开一个警告对话框。 阅读警告, 如果要继续, 请选择 **"是"** 。 选择此选项时，请注意不能将一封邮件释放给同一收件人超过一次。 如果收件人之前已经收到此邮件，则邮件不会再次释放给该收件人。 
    
     选择此选项时，会将邮件释放到所有尚未收到此邮件的收件人。如果此邮件是隔离的垃圾邮件，还会将其报告给 Microsoft 垃圾邮件分析团队，该团队将评估和分析该邮件。根据分析结果的不同，可能会调整服务范围内的垃圾邮件内容筛选规则，以允许发送该邮件。 
    
> [!TIP]
> 按照[如何确保邮件不会标记为垃圾邮件](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md)中的步骤，确保邮件未标记为垃圾邮件。 
  
如果单击 "**刷新**![刷新" 图标](media/ITPro-EAC-RefreshIcon.gif)图标刷新数据, 然后双击邮件, 您应该会看到它已发布给预期的收件人。 
  
## <a name="for-more-information"></a>详细信息
<a name="sectionSection4"> </a>

[隔离常见问题解答](quarantine-faq.md)
  

