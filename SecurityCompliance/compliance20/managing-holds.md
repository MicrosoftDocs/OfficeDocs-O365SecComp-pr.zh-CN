---
title: 管理保留项中高级电子数据展示 （预览）
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 476ea80e61b5354c53368613e29a79c55a50276f
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29695178"
---
# <a name="manage-holds-in-advanced-ediscovery-preview"></a>管理保留项中高级电子数据展示 （预览）

高级电子数据展示 （预览） 案例可用于创建保留项以保留可能与您的案例相关的内容。使用高级电子数据展示 （预览） 保留功能，就可以保留对管理员和它们的数据源。此外，您可以置于非监控保留邮箱和 OneDrive for Business 站点。您还可以进行保留组邮箱、 SharePoint 网站和 OneDrive for Business 站点 for Office 365 组。同样，您可以置于保留的邮箱和关联的 Microsoft 团队使用的网站。当您将内容位置置于保持状态时，内容将保存，直到释放 custodian、 删除一个特定的数据的位置，或完全删除保留策略。

## <a name="manage-custodian-based-holds"></a>管理基于 custodian 保留项

在某些情况下，您可能必须选择保留和一组数据管理员的标识。在高级电子数据展示 （预览），这些管理员置于保持状态时用户和其所选的数据源将自动添加到管理员保留策略。 

若要查看 custodian 保留策略：

1. 在**安全 & 合规性中心**中，单击**电子数据展示 > 高级电子数据展示 （预览）** 以显示组织中的情况下列表。
   
2. 转到**管理员**选项卡添加您的案例中的管理员。若要了解如何添加和置于高级电子数据展示 （预览） 案例中保持状态的管理员，请参阅[的高级电子数据展示 （预览） 添加管理员案例](add-custodians-to-case.md)。如果您已经添加管理员并置于保持状态，请转到步骤 3。
   
3. 转到**保留**选项卡，并选择 Custodian 策略。
   
4. 在弹出页上，您可以看到保留策略的统计信息。您还可以执行操作类似于您基于 custodian 保留查询。有关创建保留查询和使用情况的详细信息，请参阅[关键字查询和内容搜索的搜索条件](../keyword-queries-and-search-conditions.md)。
 
## <a name="manage-non-custodial-holds"></a>管理非监控保留项

创建保留项时，您具有以下选项范围保留在指定的内容位置的内容：

  - 创建所有内容将都置于保持状态无限期保留。或者，您可以创建基于查询的保留匹配一个搜索查询的唯一内容置于保持状态。
  - 您可以指定日期范围以保留内容发送、 接收，或创建的日期范围内。此外，您可以保留无论时发送、 接收，或创建的所有内容。

创建高级电子数据展示 （预览） 用例保留：

1. 在**安全 & 合规性中心**中，单击**电子数据展示 > 高级电子数据展示 （预览）** 以显示组织中的情况下列表。
  
2. 单击旁边的情况下，您想要创建保留项中的**打开**。
  
3. 从用例主页页中，单击**保存**选项卡。
  
4. 在**保存**选项卡中，单击**创建**。
  
5. 在**名称您保留**页中，赋予保留项的名称。保留项的名称必须是您的组织中唯一的。
 
6. （可选）在**说明**框中，添加的保留项的说明。
  
7. 单击"下一步"。
  
8. 选择您想要置于内容位置保留。您可以将置于保持状态的邮箱、 网站和公用文件夹。

   答： **Exchange 电子邮件**-单击**选择用户、 组或团队**，，然后单击**选择用户、 组或团队**再次指定邮箱置于保留。使用搜索框查找用户邮箱和通讯组 （用于组成员的邮箱置于保留） 以将置于保持状态。此外可以为 Office 365 组或 Microsoft 团队对关联的邮箱进行保留。选择用户、 组和团队复选框，单击**选择**，然后单击**完成**。
 
    > [!NOTE]
    > 当您单击**选择用户、 组或团队**以指定要将置于保持状态的邮箱，显示邮箱选取器为空。这是设计以提高性能。要将联系人添加到此列表中，请在搜索框中键入名称 （最少的 3 个字符）。

    b. **SharePoint 网站**-单击**选择站点**，然后单击再次要指定 SharePoint 和 OneDrive for Business 站点置于保留的**选择网站**。键入您想要将置于保持状态的每个网站的 URL。您还可以为 Office 365 组或 Microsoft 团队添加 SharePoint 网站的 URL。单击**选择**，然后单击**完成**。
    
     请参阅上放置置于保持状态的 Office 365 组和 Microsoft 团队的提示和技巧**常见问题**一节。

    > [!NOTE]
    > 在已更改的人员的用户主体名称 (UPN) 极少数情况下，其 OneDrive 帐户的 URL 也将更改为合并新的 UPN。如果发生这种情况，您将需要通过添加用户的新 OneDrive URL 和删除旧修改保留项。

     c. **Exchange 公用文件夹**-在将移动到的所有位置将所有公用文件夹放入在 Exchange Online 组织上的保留的切换开关。请注意，不能选择特定的公用文件夹，以将置于保持状态。保留设置为**None** ，如果您不想要保留置于公用文件夹切换开关。

9. 完成添加到保留项的内容位置后，单击**下一步**。
  
10. 若要创建基于查询的保留与条件，完成以下。否则，只需单击**下一步**。
    
    - 在在**关键字**下框中，键入搜索查询的框中，以便仅符合搜索条件的内容置于保留。您可以指定关键字、 消息属性或文档属性，如文件名。您还可以使用或不使用布尔运算符，例如 AND、 OR 的更复杂的查询。如果您保留关键字框为空，则位于指定的内容位置的所有内容将都置于保持状态。

    - 单击**添加**条件以添加一个或多个条件以缩小范围的搜索查询的保留项。每个条件将子句添加到 KQL 搜索查询创建和运行时创建保留项。例如可以指定日期范围，以便电子邮件或网站的日期范围内创建的文档置于保持状态。条件逻辑 AND 运算符通过连接到 （在关键字框中指定） 的关键字查询。意味着项目需要满足关键字查询和条件的置于保持状态。

     有关创建搜索查询和使用情况的详细信息，请参阅[关键字查询和内容搜索的搜索条件](https://docs.microsoft.com/en-us/office365/SecurityCompliance/keyword-queries-and-search-conditions)。

12. 后配置基于查询的保留，单击**下一步**。
 
13. 检查您的设置，然后单击**创建此保留**。


## <a name="view-hold-statistics"></a>查看保留统计信息

段时间后的所选保留**保留**选项卡上详细信息窗格中显示有关新保留的信息。此信息包括的邮箱数和上的网站保留统计信息的内容的已置于保留，如置于保持状态的总数量和大小的项目和上一次的保留计算的统计信息。这些保留统计信息帮助您确定要保留与电子数据展示案例相关的内容量。

注意有关保留统计信息并按以下几点：

- 置于保留状态的项目总数指示置于保持状态的所有内容源中的项目数。如果您已创建基于查询的保留，此统计信息指示与查询匹配的项目数。
  
- 置于保留状态的项目数还包括内容的位置中找到的未编制索引的项。请注意，是否创建基于查询的保留，但内容的位置中的所有未编制索引的项目置于保持状态。这包括与搜索条件的基于查询的保留不匹配的未编制索引的项和可能属于外部日期范围条件的未编制索引的项。这是不同于运行内容的搜索，在其中未编制索引的项不匹配的搜索查询或排除的日期范围条件不包括在搜索结果时，会发生什么情况。有关未编制索引的项目的详细信息，请参阅[部分，索引项目在 Office 365 中的内容搜索](../partially-indexed-items-in-content-search.md)。 

- 您可以通过单击更新统计信息以重新运行计算当前置于保持状态的项目数的搜索估计获取的最新的保留统计信息。

- 如有必要，单击在工具栏中更新的详细信息窗格中的保留统计信息的刷新。

- 它的普通上的项目数保留来提高随着时间的推移，因为其邮箱或网站处于保留状态的用户通常发送或接收新电子邮件并创建新的 SharePoint 和 OneDrive 的业务文档。

- 如果将 SharePoint 网站或 OneDrive 帐户移动到多地理环境中的不同区域，该网站的统计信息不会包含在保留统计信息。但是，网站中的内容仍将置于保持状态。此外，如果网站移至不同的区域将不会更新保留项中显示的 URL。您将需要编辑保留和更新 URL。

## <a name="frequently-asked-questions"></a>常见问题

- 如何将其他的 Office 365 组或 Microsoft 团队网站映射到 custodian **？和什么样的培训发出非监控保留对 Office 365 组和 Microsoft 团队？** 在 Office 365 组上构建的 Microsoft 团队。因此，将它们放在保留中电子数据展示事例是非常类似。将 Office 365 组和上的 Microsoft 团队保留时保留记住以下事项。
  - 若要放置内容位于 Office 365 组和 Microsoft 团队置于保持状态，您必须指定邮箱和 SharePoint 网站的组或团队相关联。
  
  - Exchange Online 的 Office 365 组或 Microsoft 团队查看属性中运行**Get UnifiedGroup** cmdlet。这是一个好方法获取与 Office 365 组或 Microsoft 团队相关联的网站的 URL。例如，下面的命令的一个名为高级领导团队的 Office 365 组显示所选的属性：


    ```
    Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
    DisplayName            : Senior Leadership Team
    Alias                  : seniorleadershipteam
    PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
    SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
    ```

    > [!NOTE]
    > 若要运行 Get UnifiedGroup cmdlet，您必须分配 View-Only Recipients 角色在 Exchange Online 或是角色组的成员的已分配 View-Only Recipients 角色。

 - 用户的邮箱搜索，搜索时不会搜索任何 Office 365 组或 Microsoft 团队的成员的用户。同样，将 Office 365 组或 Microsoft 团队保持状态并置于组邮箱和组网站时保留;除非您明确将它们作为管理员添加或将其数据源保留，邮箱和 OneDrive for Business 网站组成员的不被置于保持状态。因此，如果您需要将 Office 365 组或 Microsoft 团队置于保留为特定的管理员，请考虑映射到 custodian （请参阅管理管理员高级电子数据展示 (Preview) 中） 的组网站和组邮箱。如果不属于单个管理员的 Office 365 组或 Microsoft 团队，请考虑添加到非监控源保留。 
 
 - 若要获取 Office 365 组或 Microsoft 团队的成员的列表，您可以在 Office 365 管理中心主页 > 组页上查看属性。此外，还可以在 Exchange Online PowerShell 中运行以下命令：

   ``` 
   Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress
   ```

    > [!NOTE]
    > 若要运行**Get UnifiedGroupLinks** cmdlet，您必须分配 View-Only Recipients 角色在 Exchange Online 或是角色组的成员的已分配 View-Only Recipients 角色。

- 与团队具有关联的邮箱中存储的一部分的 Microsoft 团队通道通道对话。同样，在频道的工作组成员共享的文件存储团队的 SharePoint 网站上。因此，您必须放置的 Microsoft 团队邮箱和 SharePoint 网站上的保留保留对话和通道中的文件。
  
- 此外，对话中的 Microsoft 团队的聊天列表的一部分存储在用户的邮箱的用户参与聊天。 用户共享聊天对话中的文件存储在 OneDrive for Business 站点的用户的共享文件。因此，您必须将单个用户邮箱和 OneDrive for Business 站点上保留保留对话和聊天列表中的文件。 
  
- 每个通道，Microsoft 团队或团队包含 Wiki 笔记记录和协作。Wiki 内容将自动保存到.mht 格式的文件时。此文件存储在团队的 SharePoint 网站上的团队 Wiki 数据文档库。通过将置于保持状态的团队的 SharePoint 网站，可以保持在 Wiki 中放置内容。

  > [!NOTE]
  > 2017 年 6 月 22，发布功能时要保留的 Microsoft 团队或团队通道 Wiki 内容 （团队的 SharePoint 网站将置于保持状态时）。如果工作组网站上保留的 Wiki 将保留内容，在该日期开始。但是，如果工作组网站处于保留状态，Wiki 内容已被删除之前 2017 年 6 月 22，已将不会为保留 Wiki 内容。
