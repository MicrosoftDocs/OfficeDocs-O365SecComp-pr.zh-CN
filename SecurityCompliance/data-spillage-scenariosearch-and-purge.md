---
title: 电子数据展示解决方案系列数据泄漏方案-搜索和清除
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: 使用 Office 365 电子数据展示和搜索工具来管理并响应在组织中的数据泄漏事件。
ms.openlocfilehash: 2bf17923408bd5cf8325d27a38595331d169906f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524912"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>电子数据展示解决方案系列： 数据泄漏方案-搜索和清除

 **什么是数据泄漏为什么小心您？** 机密文档发布到不受信任的环境时，数据泄漏。检测到数据泄漏事件时，务必快速评估的大小和位置的损耗情况、 检查周围的用户活动，然后在系统中永久清除溅入的数据。 
  
## <a name="data-spillage-scenario"></a>数据泄漏方案

您在 Contoso 的潜在顾客信息安全专员。其中员工不知情的情况下共享高度机密文档与多人通过电子邮件的数据泄漏情况的情况下将通知您。您希望快速评估内部和外部，用户会收到此文档。确定后，您想要与其他调查员查看，，然后从 Office 365 永久移除数据共享案例研究结果。完成调查后，您想要永久删除和其他案例的详细信息的任何供他们将来参考的证据生成报告。
  
### <a name="scope-of-this-article"></a>本文的范围

本文档提供有关如何从中永久删除一条消息，Office 365，以便不访问或可恢复的说明的列表。若要删除一条消息，并使其可恢复已删除的邮件保留期限过期之前，请参阅[搜索和删除 Office 365 组织中的电子邮件](search-for-and-delete-messages-in-your-organization.md)。
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>用于管理数据泄漏事件工作流

下面是如何管理数据泄漏事件：

![用于管理数据泄漏事件 8 步骤工作流](media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[（可选）步骤 1： 管理谁可以访问案例和设置合规性边界](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[步骤 2： 创建电子数据展示事例](#step-2-create-an-ediscovery-case)<br/>
[步骤 3： 搜索溅入数据](#step-3-search-for-the-spilled-data)<br/>
[步骤 4： 检查和验证案例研究结果](#step-4-review-and-validate-case-findings)<br/>
[步骤 5： 使用邮件跟踪日志以检查如何溅入的数据的共享](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[步骤 6： 准备邮箱](#step-6-prepare-the-mailboxes)<br/>
[步骤 7： 永久删除溅入的数据](#step-7-permanently-delete-the-spilled-data)<br/>
[步骤 8： 验证，提供身份证明删除，并审核](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>在开始前须知

- 置于保持状态的邮箱后，已删除的邮件将一直在可恢复邮件文件夹保留期到期或保留释放。[步骤 6](#step-6-prepare-the-mailboxes)介绍如何删除邮箱的保留。删除保留之前咨询您的记录管理或法律部门。您的组织可能必须定义上的邮箱是否保留策略或数据泄漏事件优先。 
    
- 若要控制哪些用户邮箱数据泄漏调查员可以搜索和管理谁可以访问这种情况，可以设置合规性边界，还可以创建自定义角色组，[第 1 步](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)中所述。若要执行此操作，您必须是组织管理角色组的成员或角色管理角色分配。如果您或在组织中的管理员已设置合规性边界，则可以跳过步骤 1。
    
- 创建用例，您必须是电子数据展示管理员角色组的成员，或者是已分配的案例管理角色自定义角色组的成员。如果您不是成员，请求[将您添加到电子数据展示管理员角色组](assign-ediscovery-permissions.md)向 Office 365 管理员。
    
- 若要删除溢出至您的组织的数据，您需要在 Exchange Online PowerShell 中使用[Search-mailbox DeleteContent](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps)命令。此外，若要使用*DeleteContent*参数，您还必须是 Exchange Online 邮箱导入导出角色分配中角色组的成员。请参阅在[管理角色组](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx)"将角色添加到角色组"部分。
    
- 若要在步骤 8 中搜索的 Office 365 审核日志电子数据展示活动，必须打开审核为您的组织。您可以搜索最近 90 天内执行的活动。若要详细了解如何启用和使用审核，请参阅步骤 8 中的[审核数据泄漏调查过程](#auditing-the-data-spillage-investigation-process)一节。 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>（可选）步骤 1： 管理谁可以访问案例和设置合规性边界

根据您组织的做法是，您需要控制哪些人可以访问用于调查数据泄漏事件并设置合规性边界电子数据展示事例。执行此操作的最简单方式是为 Office 365 安全性和合规性中心中的现有角色组的成员添加调查人员，然后添加以电子数据展示事例的成员身份的角色组。有关内置电子数据展示角色组以及如何将成员添加到电子数据展示事例的信息，请参阅[分配 Office 365 安全性的电子数据展示权限&amp;合规性中心](assign-ediscovery-permissions.md)。
  
您还可以创建新的角色组的与您组织的需求。例如，您可能希望来访问和协作的所有数据泄漏情况下在组织中的数据泄漏调查人员组。您可以通过创建"数据泄漏调查员"角色组、 分配适当的角色 （导出、 RMS 解密、 审阅、 预览、 合规性搜索和案例管理）、 向角色组中，添加数据泄漏调查人员，然后添加执行此操作数据泄漏电子数据展示事例的成员身份的角色组。有关如何执行此操作的详细说明，请参阅[设置 Office 365 中的电子数据展示调查的合规性边界](set-up-compliance-boundaries.md)。 
  
## <a name="step-2-create-an-ediscovery-case"></a>步骤 2： 创建电子数据展示事例

电子数据展示事例提供有效的方式来管理您的数据泄漏调查。可以将成员添加到您在步骤 1 中创建的角色组、 角色组添加成员的新电子数据展示事例，身份执行迭代搜索以查找溅入的数据、 导出报表以共享、 跟踪状态的情况下，然后回顾到 c 的详细信息如果需要，ase。请考虑建立用于数据泄漏事件的电子数据展示事例的命名约定，并提供尽可能多的信息，您可以在的大小写的名称和说明，以便您可以找到并如有必要，以便将来参考。
  
若要创建新的用例，可以使用电子数据展示中安全&amp;合规性中心。请参阅[Office 365 安全性和合规性中心中的电子数据展示事例](ediscovery-cases.md#step-2-create-a-new-case)中的"创建新的用例"。
  
## <a name="step-3-search-for-the-spilled-data"></a>步骤 3： 搜索溅入数据

现在您已创建案例和托管的访问，您可以使用这种情况反复搜索来查找溅入的数据并确定包含溅入的数据的邮箱。您将使用您用来查找要删除在[步骤 7](#step-7-permanently-delete-the-spilled-data)中这些相同的邮件的电子邮件的同一个搜索查询。
  
若要创建内容电子数据展示事例与搜索关联，请参阅[Office 365 安全性和合规性中心中的电子数据展示事例](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case)中的"创建和运行与案例相关的内容搜索"。
  
 **重要：** 搜索查询中使用的关键字可能包含您要搜索的实际溅入的数据。例如，如果搜索包含社会保险号码和您的文档使用 it 作为搜索关键字，则必须删除查询以后避免进一步损耗情况。请参阅在步骤 8 中的[删除搜索查询](#deleting-the-search-query)。 
  
## <a name="step-4-review-and-validate-case-findings"></a>步骤 4： 检查和验证案例研究结果

创建内容搜索后，您需要能够查看并验证搜索结果，并验证仅包含，必须先删除电子邮件。在内容搜索中，您可以预览 1,000 电子邮件的随机采样而不导出搜索结果，以避免更多数据泄漏。您可以阅读更多有关预览限制在[Limits for Office 365 安全性内容搜索&amp;合规性中心](limits-for-content-search.md)。
  
如果您有邮箱，可查看每 1,000 个以上的邮箱或 100 多个电子邮件，您可以使用其他关键字或日期范围或发件人/收件人如条件的初始搜索将多个搜索分成并查看每个搜索结果单独。请确保记下您删除[步骤 7](#step-7-permanently-delete-the-spilled-data)中的邮件时要使用的所有搜索查询。

如果管理员或最终用户分配一个 Office 36 E5 许可证，您可以检查最多 10,000 同时使用 Office 365 高级电子数据展示的搜索结果。如果有 10,000 个以上的电子邮件以查看，您可以除以日期范围的搜索查询并按日期排序结果的搜索单独查看每个结果。在高级电子数据展示，可以标记预览面板中使用**标签作为**功能的搜索结果，并按您标记的标记筛选搜索结果。与辅助审阅者协作时，这非常有用。使用高级电子数据展示，如光学字符识别、 电子邮件超线程，和预测编码中其他分析工具可以快速处理和查看数千个邮件并标记这些进行进一步审阅。请参阅[快速设置 Office 365 高级电子数据展示](quick-setup-for-advanced-ediscovery.md)。

找到包含溅入的数据的电子邮件后，检查邮件以确定共享已从外部的收件人。为进一步的跟踪消息，可以收集发件人信息和日期范围，以便您可以使用邮件跟踪日志，[步骤 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)中所述。

验证搜索结果的做，您可能想要第二审阅与其他人共享您的发现。分配给这种情况，在步骤 1 中的人员可以查看案例中电子数据展示和高级电子数据展示内容和批准案例研究结果。您还可以生成报表，而不将导出的实际内容。您还可以用作此相同的报告证明删除[第 8 步](#step-8-verify-provide-a-proof-of-deletion-and-audit)中所述。
  
 **若要生成统计报告：**
  
1. 转到电子数据展示案例，在**搜索**页上，单击您想要生成的报告的搜索。 
    
2. 在弹出页上，单击**更多 > 将报表导出**。
 
      显示导出报告页。

    ![选择搜索，然后单击更多 > 导出弹出上的报告](media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. 选择**所有项目，包括具有无法识别的格式进行加密，或出于其他原因或者没有索引**，然后单击**生成报表**。

4. 在电子数据展示案例中，单击**导出**要显示的导出作业列表。您可能需要单击**刷新**更新该列表以显示您刚创建的导出作业。

5. 单击导出作业，，然后单击**下载**弹出页上的报告。
 
    ![在导出页上，单击导出，然后单击"下载报告"](media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

**导出摘要**报告中包含位置发现结果和大小的搜索结果数。您可以使用此进行比较的删除后生成的报告中提供与证明删除。**结果**报告包含搜索结果，包括主题、 发件人、 收件人，如果读取的电子邮件、 日期和每封邮件的大小的更详细的摘要。如果在此报告的详细信息的任何包含实际溅入的数据，请务必完成调查后永久删除 Results.csv 文件。

有关导出报告的详细信息，请参阅[导出内容的搜索报告](export-a-content-search-report.md)。
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>步骤 5： 使用邮件跟踪日志以检查如何溅入的数据的共享

若要进一步调查如果共享溅入数据的电子邮件，您可以 （可选） 查询邮件跟踪日志的发件人信息和步骤 4 中收集的日期范围信息。请注意，邮件跟踪的保留期 30 天的实时数据和 90 天的历史数据。
  
您可以使用安全性和合规性中心中的邮件跟踪，或使用相应的 cmdlet 在 Exchange Online PowerShell。请务必注意邮件跟踪不提供完整保证能返回的数据完整性。有关使用邮件跟踪的详细信息，请参阅： 
  
- [邮件跟踪 Office 365 安全性&amp;合规性中心](https://support.office.com/article/3e64f99d-ac33-4aba-91c5-9cb4ca476803.aspx)
    
- [新的 Message Trace in Office 365 安全性&amp;合规性中心](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a>步骤 6： 准备邮箱

查看并验证搜索结果包含必须删除邮件之后，您需要收集受影响的邮箱，运行**搜索邮箱 DeleteContent**命令时，在步骤 7 中使用的电子邮件地址的列表。您可能还需要准备邮箱之前，可永久删除电子邮件，具体取决于是否在包含溅入的数据或如果任何这些邮箱上保留的邮箱启用单个项目恢复。
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>获取与溅入数据的邮箱的地址列表

有两种方法来收集的与溅入数据的邮箱的电子邮件地址列表。

**选项 1： 获取与溅入数据的邮箱的地址列表**

1. 打开电子数据展示事例，转到**搜索**页并选择适当的内容搜索。 
    
2. 在弹出页上，单击**查看结果**。
    
3. 在**单个结果**下拉列表中单击**搜索统计信息**。
    
4. 在**类型**下拉列表中，单击**顶部的位置**。
    
    ![获取包含在搜索统计信息的顶部的位置页上的搜索结果的邮箱的列表](media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    显示包含搜索结果的邮箱的列表。此外会显示每个邮箱中的搜索查询匹配的项目数。
    
5. 列表中的信息复制和保存到文件或单击**下载**以下载到 CSV 文件的信息。 
    
**选项 2： 将邮箱位置获得导出报告**

在[步骤 4](#step-4-review-and-validate-case-findings)中打开您下载的导出摘要报表。在报表的第一列，**位置**下列出每个邮箱的电子邮件地址。
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>准备邮箱，因此您可以删除溅入的数据

如果启用单个项目恢复或邮箱置于保持状态，则将可恢复的项目文件夹中保留永久删除 （清除） 的邮件。因此，可以清除溅入的数据之前，您需要检查的现有邮箱配置并禁用单个项目恢复，删除任何保持或 Office 365 保留策略。请记住，您可以准备一个邮箱一次，然后在不同的邮箱上运行在同一个命令或创建同时准备多个邮箱的 PowerShell 脚本。

- 请参阅"步骤 1： 收集信息有关邮箱"中的说明有关如何检查是否启用单个项目恢复或如果邮箱置于保留或分配给[删除在可恢复项目文件夹中的基于云的邮箱的保留项](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox)保留策略。 
    
- 请参阅"步骤 2： 准备邮箱"中[删除在可恢复项目文件夹中的基于云的邮箱的保留的项目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox)有关禁用单个项目恢复的说明。 
    
- 请参阅"步骤 3： 删除邮箱的所有保留项"中[删除在可恢复项目文件夹中的基于云的邮箱的保留的项目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox)有关如何从邮箱中删除保持或保留策略的说明。 
    
 **重要：** 删除保留或保留策略之前，请与记录管理或法律部门。您的组织可能有定义上的邮箱是否保留策略或数据泄漏事件优先。 
  
请务必验证溅入的数据已被永久删除后还原到先前的配置的邮箱。请参阅[步骤 7](#step-7-permanently-delete-the-spilled-data)中的详细信息。

## <a name="step-7-permanently-delete-the-spilled-data"></a>步骤 7： 永久删除溅入的数据

使用收集和准备步骤 6 和创建和精简查找包含溅入的数据的电子邮件的步骤 3 中的搜索查询中的邮箱位置，您可以立即永久删除溅入的数据。如前所述，您必须为其分配邮箱导入导出角色在 Exchange Online 中删除邮件使用以下过程。
  
1. [连接到 Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/?linkid=396554)。
    
2. 运行以下命令：
    
    ```
    Search-Mailbox -Identity <mailbox identity> -SearchDumpster -DeleteContent $true -SearchQuery <search query>
    ```
  
3. 重新运行前面的命令通过将为 Identity 参数; 值包含溅入的数据，每个邮箱例如：

    ```
    Search-Mailbox -Identity sarad@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

    ```
    Search-Mailbox -Identity janets@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

   ```
   Search-Mailbox -Identity pilarp@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
   ```
  
如前面所述，您还可以创建[powershell 脚本](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6)并运行对邮箱的列表，以便该脚本将删除每个邮箱中的溅入的数据。
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>步骤 8： 验证，提供身份证明删除，并审核

工作流来管理数据泄漏事件中的最后一步是确认溅入的数据被永久删除从邮箱通过转到电子数据展示事例并重新运行用于删除该数据，以确认没有结果 ar 同一个搜索查询返回的 e。确认已被永久移除溅入的数据后，可以将报表导出并将其作为证明删除包含 （以及原始报告）。然后，您可以[关闭这种情况](ediscovery-cases.md#optional-step-9-close-a-case)，将使您能够重新打开它，如果将来引用到它。此外，还可以恢复邮箱为其以前的状态，删除用于查找溅入的数据，并搜索审核记录的任务管理数据泄漏事件时执行的搜索查询。 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>还原到其以前的状态的邮箱

如果您已经更改准备邮箱溅入的数据被删除之前的步骤 6 中的任何邮箱配置，您需要将其还原为其以前的状态。请参阅"步骤 5： 将恢复其先前状态的邮箱"中[删除在可恢复项目文件夹中的基于云的邮箱的保留的项目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-5-revert-the-mailbox-to-its-previous-state)。
  
### <a name="deleting-the-search-query"></a>删除搜索查询

如果您创建和使用在步骤 3 中的搜索查询中的关键字包含的所有实际溅入数据的一些，应删除的搜索查询，以防止进一步数据泄漏。
  
1. 中安全性和合规性中心中，打开电子数据展示事例，转到**搜索**页上，然后选择适当的内容搜索。
    
2. 在弹出页上，单击**删除**。

    ![选择搜索，然后单击弹出页上的删除](media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a>审核数据泄漏调查过程

您可以搜索在调查期间已执行的电子数据展示活动的 Office 365 审核日志。您还可以搜索审核日志来返回审核记录运行**搜索邮箱 DeleteContent**命令以删除溅入的数据时创建的。有关详细信息，请参阅：

- [在 Office 365 安全&amp;合规中心搜索审核日志](search-the-audit-log-in-security-and-compliance.md)

- [Office 365 审核日志中的电子数据展示活动搜索](search-for-ediscovery-activities-in-the-audit-log.md)

- 请参阅有关如何搜索审核记录与 Exchange Online 中运行 cmdlet 的指南[搜索审核日志在 Office 365 安全性和合规性中心](search-the-audit-log-in-security-and-compliance.md#audited-activities)中的"审核活动-Exchange 管理员审核日志"部分。
  

