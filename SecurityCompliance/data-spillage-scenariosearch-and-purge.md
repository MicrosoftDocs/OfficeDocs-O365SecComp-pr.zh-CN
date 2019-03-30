---
title: 电子数据展示解决方案系列数据外泄方案-搜索和清除
ms.author: markjjo
author: markjjo
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MET150
ms.assetid: d945f7dd-f62f-4ca7-b3e7-469824cfd493
description: 使用 Office 365 电子数据展示和搜索工具来管理和响应组织中的数据外泄事件。
ms.openlocfilehash: 50078e3f22ede8a1af2a252a7a6f75710534c062
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "31000145"
---
# <a name="ediscovery-solution-series-data-spillage-scenario---search-and-purge"></a>电子数据展示解决方案系列: Data 外泄方案-搜索和清除

 **什么是数据外泄, 为什么要关注？** 数据外泄是将机密文档发布到不受信任的环境时。 检测到 data 外泄事件时, 务必要快速评估外泄的大小和位置, 检查其周围的用户活动, 然后从系统中永久清除溢出的数据。 
  
## <a name="data-spillage-scenario"></a>Data 外泄方案

你是 Contoso 的潜在客户信息安全官员。 您会收到一种数据外泄情况, 其中员工在不知情的情况下通过电子邮件与多个人共享高度机密的文档。 您希望快速评估在内部和外部接收此文档的用户。 确定后, 您想要与其他调查人员共享案例发现以进行审核, 然后永久删除 Office 365 中的数据。 调查完成后, 您需要生成一个报告, 其中包含永久删除的证据和其他案例的详细信息, 以供将来参考。
  
### <a name="scope-of-this-article"></a>本文的范围

本文档提供了有关如何从 Office 365 中永久删除邮件以使其不可访问或可恢复的说明的列表。 若要在已删除项目的保留期过期之前删除邮件并使其可恢复, 请参阅[在 Office 365 组织中搜索和删除电子邮件](search-for-and-delete-messages-in-your-organization.md)。
  
## <a name="workflow-for-managing-data-spillage-incidents"></a>用于管理数据外泄事件的工作流

下面介绍了如何管理数据外泄事件:

![用于管理数据外泄事件的8步工作流](media/O365-eDiscoverySolutions-DataSpillage-workflow.png)
  
[Optional第1步: 管理可访问事例和设置合规性边界的人士](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)<br/>
[步骤 2: 创建电子数据展示事例](#step-2-create-an-ediscovery-case)<br/>
[步骤 3: 搜索溢出的数据](#step-3-search-for-the-spilled-data)<br/>
[步骤 4: 查看和验证案例发现](#step-4-review-and-validate-case-findings)<br/>
[步骤 5: 使用邮件跟踪日志检查溢出数据的共享方式](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)<br/>
[步骤 6: 准备邮箱](#step-6-prepare-the-mailboxes)<br/>
[步骤 7: 永久删除溢出的数据](#step-7-permanently-delete-the-spilled-data)<br/>
[步骤 8: 验证、提供删除证明和审核](#step-8-verify-provide-a-proof-of-deletion-and-audit)<br/>

## <a name="things-to-know-before-you-start"></a>开始之前需要了解的事项

- 当邮箱处于保留状态时, 已删除邮件将保留在 "可恢复的项目" 文件夹中, 直到保留期过期或释放保留期。 [步骤 6](#step-6-prepare-the-mailboxes)介绍了如何从邮箱中删除保留。 在删除保留之前, 请与您的记录管理或法律部门确认。 您的组织可能有定义邮箱处于保留状态或 data 外泄事件是否优先的策略。 
    
- 若要控制数据外泄调查人员可以搜索和管理可访问该案例的用户邮箱, 您可以设置合规性边界并创建自定义角色组, 如[步骤 1](#optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries)中所述。 若要执行此操作, 您必须是 "组织管理" 角色组的成员, 或分配有角色管理角色。 如果您或您的组织中的管理员已设置了合规性边界, 则可以跳过步骤1。
    
- 若要创建案例, 您必须是电子数据展示管理器角色组的成员, 或者是分配有案例管理角色的自定义角色组的成员。 如果你不是成员, 请让 Office 365 管理员[将你添加到电子数据展示管理器角色组](assign-ediscovery-permissions.md)。
    
- 若要删除溢出组织中的数据, 需要使用 Exchange Online PowerShell 中的[搜索-邮箱-DeleteContent](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Search-Mailbox?view=exchange-ps)命令。 此外, 若要使用*DeleteContent*参数, 您还必须是 Exchange Online 中分配有邮箱导入导出角色的角色组的成员。 请参阅[管理角色组](https://technet.microsoft.com/library/jj657480%28v=exchg.150%29.aspx)中的 "向角色组添加角色" 部分。
    
- 若要在步骤8中搜索 Office 365 审核日志电子数据展示活动, 必须为您的组织启用审核。 您可以搜索在过去的90天内执行的活动。 若要了解有关如何启用和使用审核的详细信息, 请参阅步骤8中的 "[审核数据外泄调查过程](#auditing-the-data-spillage-investigation-process)" 一节。 
    
## <a name="optional-step-1-manage-who-can-access-the-case-and-set-compliance-boundaries"></a>Optional第1步: 管理可访问事例和设置合规性边界的人士

根据您的组织实践, 您需要控制谁可以访问用于调查 data 外泄事件和设置合规性边界的电子数据展示事例。 执行此操作最简单的方法是将调查人员添加为安全 & 合规性中心中现有角色组的成员, 然后将角色组添加为电子数据展示事例的成员。 有关内置电子数据展示角色组以及如何将成员添加到电子数据展示事例的信息, 请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md)。
  
您还可以创建与您的组织需求相符的新角色组。 例如, 您可能希望组织中的一组数据外泄调查人员访问所有数据外泄案例并对其进行协作。 若要执行此操作, 可以创建 "Data 外泄调查者" 角色组, 分配适当的角色 (导出、RMS 解密、审阅、预览、合规性搜索和事例管理), 将数据外泄调查人员添加到角色组, 然后添加作为数据外泄电子数据展示事例的成员的角色组。 有关如何执行此操作的详细说明, 请参阅为[Office 365 中的电子数据展示调查设置合规性边界](set-up-compliance-boundaries.md)。 
  
## <a name="step-2-create-an-ediscovery-case"></a>步骤 2: 创建电子数据展示事例

电子数据展示案例提供了一种有效的方法来管理数据外泄调查。 您可以将成员添加到您在步骤1中创建的角色组, 将角色组添加为新的电子数据展示事例的成员, 执行迭代搜索以查找溢出的数据、将报告导出到共享、跟踪该事例的状态, 然后返回 c 的详细信息。如果需要, 则为 ase。 考虑为数据外泄事件使用的电子数据展示事例建立命名约定, 并在事例名称和说明中提供尽可能多的信息, 以便在将来必要时可以找到并参考。
  
若要创建新的案例, 可以在安全与合规中心中使用电子数据展示。 请参阅[电子数据展示事例](ediscovery-cases.md#step-2-create-a-new-case)中的 "创建新事例"。
  
## <a name="step-3-search-for-the-spilled-data"></a>步骤 3: 搜索溢出的数据

现在, 您已经创建了一个事例和托管访问, 您可以使用这种情况进行反复搜索, 以查找溢出的数据, 并识别包含溢出数据的邮箱。 您将使用相同的搜索查询来查找在[步骤 7](#step-7-permanently-delete-the-spilled-data)中删除这些相同邮件的电子邮件。
  
若要创建与电子数据展示事例相关联的内容搜索, 请参阅[电子数据展示事例](ediscovery-cases.md#step-5-create-and-run-a-content-search-associated-with-a-case)中的 "创建和运行与事例关联的内容搜索"。
  
 **重要说明:** 您在搜索查询中使用的关键字可能包含要搜索的实际溢出数据。 例如, 如果您搜索包含社会保险号码的文档, 并将其用作搜索关键字, 则必须随后删除该查询以避免进一步外泄。 请参阅在步骤8中[删除搜索查询](#deleting-the-search-query)。 
  
## <a name="step-4-review-and-validate-case-findings"></a>步骤 4: 查看和验证案例发现

创建内容搜索后, 需要查看并验证搜索结果, 并验证它们是否仅包含必须删除的电子邮件。 在内容搜索中, 可以预览1000电子邮件的随机采样, 而无需导出搜索结果以避免进一步的数据外泄。 您可以阅读有关[内容搜索限制](limits-for-content-search.md)的预览限制的详细信息。
  
如果要查看的邮箱超过1000个或多于100个电子邮件, 可以使用其他关键字或条件 (如日期范围或发件人/收件人) 并查看每个搜索的结果, 将初始搜索划分为多个搜索。零售. 请务必记下在[步骤 7](#step-7-permanently-delete-the-spilled-data)中删除邮件时要使用的所有搜索查询。

如果为保管人或最终用户分配了 Office 36 E5 许可证, 则可以使用 office 365 高级电子数据展示一次性检查10000个搜索结果。 如果要查看的电子邮件数超过10000个, 可以按日期范围划分搜索查询, 并在搜索结果按日期排序时分别查看每个结果。 在高级电子数据展示中, 可以使用预览面板中的 "**标签为**" 功能标记搜索结果, 并按标记的标记筛选搜索结果。 当您与辅助审阅者进行协作时, 这将非常有用。 通过使用高级电子数据展示中的其他分析工具 (如光学字符识别、电子邮件线程和预测编码), 您可以快速处理和查看成千上万封邮件, 并标记它们以供进一步审阅。 请参阅[Office 365 高级电子数据展示的快速设置](quick-setup-for-advanced-ediscovery.md)。

当您找到包含溢出数据的电子邮件时, 请检查邮件的收件人以确定它是否是在外部共享的。 若要进一步跟踪邮件, 可以收集发件人信息和日期范围, 以便您可以使用[步骤 5](#step-5-use-message-trace-log-to-check-how-spilled-data-was-shared)中所述的邮件跟踪日志。

Afer 您验证了搜索结果, 您可能需要与其他人共享你的发现以进行辅助评审。 在步骤1中分配案例的人员可以在电子数据展示和高级电子数据展示和批准案例发现中查看事例内容。 您还可以在不导出实际内容的情况下生成报告。 您还可以使用此报告作为删除证明, 如[步骤 8](#step-8-verify-provide-a-proof-of-deletion-and-audit)中所述。
  
 **生成统计报告:**
  
1. 转到电子数据展示事例中的 "**搜索**" 页, 然后单击要为其生成报告的搜索。 
    
2. 在弹出页面上, 单击 "**更多 > 导出报告**"。
 
      将显示 "导出报告" 页。

    ![选择搜索, 然后单击弹出页面上的 "更多 > 导出报告"。](media/O365-eDiscoverySolutions-DataSpillage-ExportReport1.png)
    
3. 选择**所有项目, 包括不可识别格式的项目、加密的项目或未针对其他原因编制索引的项目**, 然后单击 "**生成报告**"。

4. 在电子数据展示事例中, 单击 "**导出**" 以显示导出作业的列表。 您可能需要单击 "**刷新**" 以更新列表, 以显示刚创建的导出作业。

5. 单击 "导出" 作业, 然后单击弹出页面上的 "**下载**报告"。
 
    ![在 "导出" 页上, 单击 "导出", 然后单击 "下载报告"](media/O365-eDiscoverySolutions-DataSpillage-ExportReport2.png)

"**导出摘要**" 报告包含找到的位置数以及搜索结果的大小。 您可以使用它来与删除后生成的报告进行比较, 并作为删除证明提供。 **结果**报告包含搜索结果的更详细摘要, 包括主题、发件人、收件人、电子邮件的阅读时间、日期以及每封邮件的大小。 如果此报告中的任何详细信息包含实际溢出的数据, 请务必在调查完成后永久删除结果 .csv 文件。

有关导出报告的详细信息, 请参阅[导出内容搜索报告](export-a-content-search-report.md)。
    
## <a name="step-5-use-message-trace-log-to-check-how-spilled-data-was-shared"></a>步骤 5: 使用邮件跟踪日志检查溢出数据的共享方式

若要进一步调查是否已共享带有溢出数据的电子邮件, 您可以选择使用您在步骤4中收集的发件人信息和日期范围信息查询邮件跟踪日志。 请注意, 邮件跟踪的保留期为实时数据的30天, 历史数据为90天。
  
您可以使用 "安全与合规中心" 中的 "邮件跟踪" 或在 Exchange Online PowerShell 中使用相应的 cmdlet。 需要注意的重要一点是, 邮件跟踪没有提供对返回数据完整性的完全保证。 有关使用邮件跟踪的详细信息, 请参阅: 
  
- [安全与合规中心内的消息跟踪](https://support.office.com/article/3e64f99d-ac33-4aba-91c5-9cb4ca476803.aspx)
    
- [Security & 合规中心中的新邮件跟踪](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)
    
## <a name="step-6-prepare-the-mailboxes"></a>步骤 6: 准备邮箱

在查看并验证搜索结果只包含必须删除的邮件之后, 您需要收集受影响邮箱的电子邮件地址列表, 以便在运行**搜索邮箱-DeleteContent**命令时在步骤7中使用。 您可能还必须准备邮箱, 然后才能永久删除电子邮件, 具体取决于是否在包含溢出数据的邮箱上启用单个项目恢复, 或者这些邮箱处于保留状态。
  
### <a name="get-a-list-of-addresses-of-mailboxes-with-spilled-data"></a>获取带溢出数据的邮箱的地址列表

有两种方法可以收集带有溢出数据的邮箱的电子邮件地址列表。

**选项 1: 获取带有溢出数据的邮箱的地址列表**

1. 打开电子数据展示事例, 转到 "**搜索**" 页并选择相应的内容搜索。 
    
2. 在弹出页面上, 单击 "**查看结果**"。
    
3. 在 "**单个结果**" 下拉列表中, 单击 "**搜索统计信息**"。
    
4. 在 "**类型**" 下拉列表中, 单击 "**顶部位置**"。
    
    ![获取搜索统计信息的 "顶部位置" 页上包含搜索结果的邮箱的列表](media/O365-eDiscoverySolutions-DataSpillage-TopLocations.png)

    将显示包含搜索结果的邮箱的列表。 同时显示与搜索查询匹配的每个邮箱中的项目数。
    
5. 复制列表中的信息并将其保存到文件中, 或单击 "**下载**" 将信息下载到 CSV 文件中。 
    
**选项 2: 从导出报告中获取邮箱位置**

打开您在[步骤 4](#step-4-review-and-validate-case-findings)中下载的导出摘要报告。 在报告中的第一列中, 每个邮箱的电子邮件地址在 "**位置**" 下列出。
  
### <a name="prepare-the-mailboxes-so-you-can-delete-the-spilled-data"></a>准备邮箱, 以便您可以删除溢出的数据

如果启用了单个项目恢复或将邮箱置于保留状态, 则将在 "可恢复的项目" 文件夹中保留永久删除的 (清除的) 邮件。 因此, 在清除溢出的数据之前, 您需要检查现有的邮箱配置并禁用单个项目恢复, 并删除任何保留或 Office 365 保留策略。 请注意, 您可以一次准备一个邮箱, 然后在不同的邮箱上运行相同的命令, 也可以创建一个 PowerShell 脚本来同时准备多个邮箱。

- 请参阅 "[删除基于云的邮箱的可恢复项目文件夹中的邮件" 文件夹](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-1-collect-information-about-the-mailbox)中的 "步骤 1: 收集有关邮箱的信息", 了解有关如何检查是否启用了单个项目恢复或者是否将邮箱置于保留状态或分配给了邮箱的说明保留策略。 
    
- 若要了解如何禁用单个项目恢复, 请参阅 "[删除基于云的邮箱的可恢复项目文件夹中的项目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-2-prepare-the-mailbox)" 中的 "步骤 2: 准备邮箱"。 
    
- 有关如何从邮箱中删除保留策略或保留策略的说明, 请参阅在[保留基于云的邮箱的 "可恢复的项目" 文件夹的 "删除邮件](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-3-remove-all-holds-from-the-mailbox)" 中的 "删除邮箱中的所有保留"。 

- 请参阅在 "[删除基于云的邮箱的可恢复项目" 文件夹](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-4-remove-the-delay-hold-from-the-mailbox)中的 "删除项目" 中的 "删除邮箱中的延迟保留" 中的 "删除项目" 中有关删除在删除任何类型的保留后邮箱的延迟保留的说明。
    
 **重要说明:** 在删除保留策略或保留策略之前, 请与您的记录管理或法律部门进行确认。 您的组织可能有定义邮箱处于保留状态或 data 外泄事件是否优先的策略。 
  
确认溢出的数据已永久删除后, 请务必将邮箱还原为以前的配置。 请参阅[第7步](#step-7-permanently-delete-the-spilled-data)中的详细信息。

## <a name="step-7-permanently-delete-the-spilled-data"></a>步骤 7: 永久删除溢出的数据

使用您在步骤6中收集和准备的邮箱位置以及在步骤3中创建并完善的搜索查询中的步骤 3, 以查找包含溢出数据的电子邮件, 您现在可以永久删除溢出的数据。 如前所述, 您必须分配有 Exchange Online 中的 "邮箱导入导出" 角色, 才能使用以下过程删除邮件。
  
1. [连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/?linkid=396554)。
    
2. 运行以下命令：
    
    ```
    Search-Mailbox -Identity <mailbox identity> -SearchDumpster -DeleteContent $true -SearchQuery <search query>
    ```
  
3. 通过替换 Identity 参数的值, 为包含溢出数据的每个邮箱重新运行上一个命令;例如:

    ```
    Search-Mailbox -Identity sarad@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

    ```
    Search-Mailbox -Identity janets@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
    ```

   ```
   Search-Mailbox -Identity pilarp@contoso.onmicrosoft.com -SearchQuery <search query> -DeleteContent
   ```
  
如前所述, 您还可以创建[powershell 脚本](https://docs.microsoft.com/powershell/scripting/powershell-scripting?view=powershell-6)并对邮箱列表运行该脚本, 以便脚本删除每个邮箱中溢出的数据。
  
## <a name="step-8-verify-provide-a-proof-of-deletion-and-audit"></a>步骤 8: 验证、提供删除证明和审核

工作流中用于管理数据外泄事件的最后一步是, 通过转到电子数据展示事例并重新运行用于删除数据的相同搜索查询来验证溢出的数据是否已从邮箱中永久删除, 以确认没有结果 are 返回。 确认溢出的数据被永久删除后, 您可以导出报告并将其包含 (连同原始报告) 作为删除证明。 然后, 你可以[关闭该事例](ediscovery-cases.md#optional-step-9-close-a-case), 如果你将来引用它, 将允许你重新打开它。 此外, 还可以将邮箱还原到以前的状态, 删除用于查找溢出数据的搜索查询, 并搜索在管理 data 外泄事件时执行的任务的审核记录。 
  
### <a name="reverting-the-mailboxes-to-their-previous-state"></a>将邮箱还原到其以前的状态

如果在步骤6中更改了任何邮箱配置, 以在溢出的数据被删除之前准备邮箱, 则需要将其还原到以前的状态。 请参阅在[保留的基于云的邮箱的 "可恢复的项目" 文件夹中的 "删除项目](delete-items-in-the-recoverable-items-folder-of-mailboxes-on-hold.md#step-6-revert-the-mailbox-to-its-previous-state)" 中的 "步骤 6: 将邮箱还原为以前的状态"。
  
### <a name="deleting-the-search-query"></a>删除搜索查询

如果您在步骤3中创建和使用的搜索查询中的关键字包含一些实际溢出的数据, 则应删除搜索查询以防止进一步的数据外泄。
  
1. 在 "安全与合规中心" 中, 打开电子数据展示事例, 转到 "**搜索**" 页, 然后选择适当的内容搜索。
    
2. 在弹出页面上, 单击 "**删除**"。

    ![选择搜索, 然后单击弹出页面上的 "删除"。](media/O365-eDiscoverySolutions-DataSpillage-DeleteSearch.png)
    
### <a name="auditing-the-data-spillage-investigation-process"></a>审核数据外泄调查过程

您可以在 Office 365 审核日志中搜索在调查过程中执行的电子数据展示活动。 您还可以搜索审核日志, 以返回运行**搜索邮箱-DeleteContent**命令删除溢出的数据时创建的审核记录。 有关详细信息，请参阅：

- [搜索审核日志](search-the-audit-log-in-security-and-compliance.md)

- [在审核日志中搜索电子数据展示活动](search-for-ediscovery-activities-in-the-audit-log.md)

- 有关如何在 Exchange Online 中搜索与运行的 cmdlet 相关的审核记录的指南, 请参阅[search the audit log](search-the-audit-log-in-security-and-compliance.md#audited-activities)中的 "已审核的活动-Exchange 管理员审核日志" 一节。
  

