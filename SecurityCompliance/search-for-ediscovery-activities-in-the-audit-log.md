---
title: Office 365 审核日志中的电子数据展示活动搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/24/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 67cc7f42-a53d-4751-b929-6005c80798f7
description: 了解如何搜索 Office 365 审核日志中的合规性管理员安全中执行内容搜索和电子数据展示案例任务时都会被记录的事件&amp;合规性中心。
ms.openlocfilehash: a4cc3a6b5030a6412d739236e4c534f36948d57f
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038345"
---
# <a name="search-for-ediscovery-activities-in-the-office-365-audit-log"></a>Office 365 审核日志中的电子数据展示活动搜索

内容搜索和 Office 365 安全性执行的电子数据展示相关的活动&amp;合规性中心或通过运行相应的 Windows PowerShell cmdlet 会在 Office 365 的审核日志记录。管理员或合规性管理员 （或任何已分配的电子数据展示权限的用户） 执行以下内容的搜索和电子数据展示相关的任务 Office 365 安全性时都会被记录事件&amp;合规性中心：
  
- 创建和管理电子数据展示事例
    
- 创建、 启动和编辑内容搜索
    
- 执行内容搜索操作，如预览，导出，并删除搜索结果
    
- 配置内容搜索筛选的权限
    
- 管理电子数据展示管理员角色
    
> [!IMPORTANT]
> 本文中所述的活动是仅使用安全执行电子数据展示任务结果&amp;合规性中心。通过 Exchange Online 或 SharePoint Online 中的电子数据展示中心中的就地电子数据展示工具执行的电子数据展示任务不包括在内。 
  
有关搜索的 Office 365 审核日志的详细信息，权限的是必需的和导出搜索结果中，请参阅[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)。
  
## <a name="how-to-search-for-and-view-ediscovery-activities"></a>如何搜索和查看电子数据展示活动

目前，您需要执行几个特定的操作，以查看 Office 365 审核日志中的电子数据展示活动。下面是如何。
  
1. 转到 [https://protection.office.com](https://protection.office.com)。
    
2. 登录到 Office 365 使用工作或学校帐户。
    
3. 在左窗格中，单击**搜索&amp;调查**，然后单击**审核日志搜索**。
    
4. 在**活动**下拉列表下**电子数据展示活动**，单击要搜索的一个或多个活动。或者您可以单击要搜索的电子数据展示相关的所有活动的**电子数据展示活动**。 
    
    > [!NOTE]
    > 活动下拉列表还包括一组名为**电子数据展示 cmdlet 活动**将返回 cmdlet 审核日志中记录的活动。 
  
5.  选择要显示在该时间段内发生的电子数据展示事件日期和时间范围。 
    
6. 在**用户**框中，选择一个或多个用户，以显示搜索结果。将此框保留为空，返回的所有用户的条目。 
    
7. 单击**搜索**以运行搜索使用您的搜索条件。 
    
8. 搜索结果显示后，您可以单击**筛选结果**进行筛选或排序结果的活动记录。遗憾的是，不能使用筛选明确排除某些活动。 
    
9. 若要查看有关活动的详细信息，请单击搜索结果的列表中的活动记录。 
    
    **详细信息**飞出页将显示一个包含事件记录的详细的属性。若要显示的其他详细信息，请单击**详细信息**。有关这些属性的说明，请参阅[电子数据展示活动的详细的属性](#detailed-properties-for-ediscovery-activities)部分。 

  
## <a name="ediscovery-activities"></a>电子数据展示活动

下表介绍的内容搜索和电子数据展示相关的活动的管理员或用户通过使用安全执行电子数据展示相关活动时都会被记录&amp;合规性中心或通过运行的相应 cmdlet远程 PowerShell 连接到组织的安全的&amp;合规性中心。 
  
> [!NOTE]
> 本节中所述的电子数据展示活动提供了到下一节中所述的电子数据展示 cmdlet 活动的类似信息。我们建议您使用的电子数据展示活动，因为它们将在 30 分钟内显示审核日志搜索结果在本节中所述。计达 24 小时的电子数据展示 cmdlet 活动显示在审核日志搜索结果中。 
  
|**易记名称**|**Operation**|**相应的 cmdlet**|**说明**|
|:-----|:-----|:-----|:-----|
|添加了成员到电子数据展示事例  <br/> |CaseMemberAdded  <br/> |添加 ComplianceCaseMember  <br/> |用户被添加为电子数据展示事例的成员。作为将用例的成员，用户可以执行各种与案例相关的任务，具体取决于他们已被分配所需的权限。  <br/> |
|已更改内容的搜索  <br/> |SearchUpdated  <br/> |Set-ComplianceSearch  <br/> |现有的内容搜索已更改。更改可以包括添加或删除内容位置或编辑搜索查询。  <br/> |
|已更改的电子数据展示管理员成员资格  <br/> |CaseAdminUpdated  <br/> |更新 eDiscoveryCaseAdmin  <br/> |电子数据展示管理员在组织中的列表已更改。替换一组新的用户的电子数据展示管理员列表后，将记录此活动。如果添加或删除单个用户，将记录 CaseAdminAdded 操作。  <br/> |
|已更改的电子数据展示事例  <br/> |CaseUpdated  <br/> |设置 ComplianceCase  <br/> |电子数据展示事例已更改。更改包括关闭打开的案例或重新打开结束的案例。  <br/> |
|已更改的电子数据展示案例成员资格  <br/> |CaseMemberUpdated  <br/> |更新 ComplianceCaseMember  <br/> |电子数据展示事例的成员身份列表已更改。所有成员都替换为一组新的用户时记录此活动。如果添加或删除单个成员，则记录 CaseMemberAdded 或 CaseMemberRemoved 操作。  <br/> |
|更改搜索权限筛选器  <br/> |SearchPermissionUpdated  <br/> |设置 ComplianceSecurityFilter  <br/> |搜索权限筛选器已更改。  <br/> |
|电子数据展示案例保留已更改的搜索查询  <br/> |HoldUpdated  <br/> |设置 CaseHoldRule  <br/> |已更改基于查询的保留电子数据展示事例相关联。可能的更改包括编辑查询或日期范围基于查询的保留。  <br/> |
|下载内容搜索预览项目  <br/> |PreviewItemDownloaded  <br/> |不适用  <br/> |用户下载项目到其本地计算机 （通过单击**下载原始项目**链接） 时预览搜索结果。  <br/> |
|内容搜索预览项列出  <br/> |PreviewItemListed  <br/> |不适用  <br/> |用户单击**预览搜索结果**显示预览搜索结果页面，其中列出的内容的搜索结果中的最多 1000 个项目。  <br/> |
|内容搜索预览项查看  <br/> |PreviewItemRendered  <br/> |不适用  <br/> |电子数据展示管理器查看通过预览搜索结果时单击该项目。  <br/> |
|创建内容搜索  <br/> |SearchCreated  <br/> |New-ComplianceSearch  <br/> |创建一个新的内容搜索。  <br/> |
|创建电子数据展示管理员  <br/> |CaseAdminAdded  <br/> |添加 eDiscoveryCaseAdmin  <br/> |用户已添加为组织中电子数据展示管理员。  <br/> |
|创建电子数据展示事例  <br/> |CaseAdded  <br/> |新 ComplianceCase  <br/> |创建电子数据展示事例。创建案例后，您只需为其提供一个名称。其他与案例相关的任务，如添加成员、 创建保留项，以及创建案例结果中要记录的其他事件相关联的内容搜索。  <br/> |
|创建搜索权限筛选器  <br/> |SearchPermissionCreated  <br/> |新 ComplianceSecurityFilter  <br/> |创建搜索权限筛选器。  <br/> |
|电子数据展示案例保留创建的搜索查询  <br/> |HoldCreated  <br/> |新 CaseHoldRule  <br/> |创建基于查询的保留电子数据展示事例相关联。  <br/> |
|已删除的内容搜索  <br/> |SearchRemoved  <br/> |Remove-ComplianceSearch  <br/> |现有的内容搜索已删除。  <br/> |
|已删除电子数据展示管理员  <br/> |CaseAdminRemoved  <br/> |删除 eDiscoveryCaseAdmin  <br/> |从您的组织已删除电子数据展示管理员。  <br/> |
|已删除电子数据展示事例  <br/> |CaseRemoved  <br/> |删除 ComplianceCase  <br/> |已删除电子数据展示事例。请注意，与案例关联任何保留具有要删除之前可删除这种情况。  <br/> |
|已删除的搜索权限筛选器  <br/> |SearchPermissionRemoved  <br/> |删除 ComplianceSecurityFilter  <br/> |已删除的搜索权限筛选器。  <br/> |
|电子数据展示案例保留已删除的搜索查询  <br/> |HoldRemoved  <br/> |删除 CaseHoldRule  <br/> |已删除基于查询的保留电子数据展示事例相关联。从保留中删除查询通常是删除保留的结果。删除保留或保留查询时将释放已置于保持状态的内容位置。  <br/> |
|下载的导出的内容搜索  <br/> |SearchResultDownloaded  <br/> |不适用  <br/> |用户下载到他们的本地计算机的内容的搜索结果。请注意，**启动导出的内容搜索**活动具有可以下载搜索结果之前启动。<br/> |
|预览内容搜索结果  <br/> |SearchPreviewed  <br/> |不适用  <br/> |用户预览内容搜索的结果。  <br/> |
|清除内容的搜索结果  <br/> |SearchResultsPurged  <br/> |New-ComplianceSearchAction  <br/> |用户通过运行清除的内容的搜索结果**新建 ComplianceSearchAction-清除**命令。  <br/> |
|删除的分析的内容搜索  <br/> |RemovedSearchResultsSentToZoom  <br/> |删除 ComplianceSearchAction  <br/> |内容搜索准备 （要准备 Office 365 高级电子数据展示搜索结果） 操作已被删除。如果准备操作被小于两周时间，从 Microsoft Azure 存储区删除为高级电子数据展示已准备好的搜索结果。如果超过 2 个星期准备操作，此事件表示仅相应准备操作已被删除。  <br/> |
|删除的导出的内容搜索  <br/> |RemovedSearchExported  <br/> |删除 ComplianceSearchAction  <br/> |已删除的内容搜索导出操作。如果导出操作被小于两周内，已删除已上载到 Microsoft Azure 存储区的搜索结果。如果导出操作被早于 2 周，此事件表示仅相应的导出操作已被删除。  <br/> |
|从电子数据展示事例的已删除的成员  <br/> |CaseMemberRemoved  <br/> |删除 ComplianceCaseMember  <br/> |用户已删除电子数据展示事例的成员身份。  <br/> |
|删除预览内容搜索结果  <br/> |RemovedSearchPreviewed  <br/> |删除 ComplianceSearchAction  <br/> |已删除的内容搜索预览操作。  <br/> |
|删除的清除操作执行内容搜索  <br/> |RemovedSearchResultsPurged  <br/> |删除 ComplianceSearchAction  <br/> |内容搜索清除操作已被删除。  <br/> |
|删除搜索报告  <br/> |SearchReportRemoved  <br/> |删除 ComplianceSearchAction  <br/> |内容搜索导出操作已删除的报表。  <br/> |
|开始的分析的内容搜索  <br/> |SearchResultsSentToZoom  <br/> |New-ComplianceSearchAction  <br/> |高级电子数据展示中的分析已准备好的内容的搜索结果。  <br/> |
|启动内容搜索  <br/> |SearchStarted  <br/> |Start-ComplianceSearch  <br/> |内容搜索已启动。当您创建或使用安全更改内容的搜索&amp;合规性中心 GUI，搜索会自动启动。如果您创建或使用**新建 ComplianceSearch**或**集 ComplianceSearch** cmdlet 更改搜索，您必须运行**开始 ComplianceSearch** cmdlet 可启动搜索。<br/> |
|开始的导出的内容搜索  <br/> |SearchExported  <br/> |New-ComplianceSearchAction  <br/> |用户导出内容的搜索结果。  <br/> |
|开始的导出报告  <br/> |SearchReport  <br/> |New-ComplianceSearchAction  <br/> |用户导出内容的搜索报告。  <br/> |
|停止内容搜索  <br/> |SearchStopped  <br/> |Stop-ComplianceSearch  <br/> |用户停止内容的搜索。  <br/> |
  
## <a name="ediscovery-cmdlet-activities"></a>电子数据展示 cmdlet 活动

下表列出了管理员或用户通过使用安全执行电子数据展示相关活动时都会被记录的 cmdlet 审核日志记录&amp;合规性中心或通过远程 PowerShell 中运行相应 cmdlet 的连接到组织的安全&amp;合规性中心。请注意，此表中列出的 cmdlet 活动以及上一节中所述的电子数据展示活动的不同的审核日志记录中的详细的信息。 
  
如前面所述，它采用达 24 小时的电子数据展示 cmdlet 活动的审核日志搜索结果中显示。
  
> [!TIP]
> 下表中的**操作**列中的 cmdlet 链接到 TechNet 上相应的 cmdlet 的帮助主题。转至每个 cmdlet 的可用参数的说明 cmdlet 的帮助主题。记录每个电子数据展示 cmdlet 活动的审核日志条目中包含的参数和已与 cmdlet 一起使用的参数值。 
  
|**易记名称**|**操作 (cmdlet)**|**说明**|
|:-----|:-----|:-----|
|创建保留项中电子数据展示事例  <br/> |[新 CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823813) <br/> |为电子数据展示事例创建保留项。使用或不指定的内容源，则可以创建保留项。如果未指定内容源，则它们将审核日志条目中标识它们。  <br/> |
|从电子数据展示事例的已删除的保留  <br/> |[删除 CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823814) <br/> |保留电子数据展示事例与关联的已删除。删除保留释放所有保留中的内容位置。删除保留还将导致删除与保留项关联的案例保留规则 （请参阅**删除 CaseHoldRule**下）。<br/> |
|更改的保留中电子数据展示事例  <br/> |[设置 CaseHoldPolicy](https://go.microsoft.com/fwlink/p/?LinkId=823815) <br/> |保留与 eDiscovery 关联的已更改。可能更改包括添加或删除内容位置或关闭 （禁用） 保留项。  <br/> |
|电子数据展示案例保留创建的搜索查询  <br/> |[新 CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823816) <br/> |创建基于查询的保留电子数据展示事例相关联。  <br/> |
|电子数据展示案例保留已删除的搜索查询  <br/> |[删除 CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823820) <br/> |已删除基于查询的保留电子数据展示事例相关联。从保留中删除查询通常是删除保留的结果。删除保留或保留查询时将释放已置于保持状态的内容位置。  <br/> |
|电子数据展示案例保留已更改的搜索查询  <br/> |[设置 CaseHoldRule](https://go.microsoft.com/fwlink/p/?LinkId=823819) <br/> |已更改基于查询的保留电子数据展示事例相关联。可能的更改包括编辑查询或日期范围基于查询的保留。  <br/> |
|创建电子数据展示事例  <br/> |[新 ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823842) <br/> |创建电子数据展示事例。创建案例后，您只需为其提供一个名称。其他与案例相关的任务，如添加成员、 创建保留项，以及创建案例结果中要记录的其他事件相关联的内容搜索。  <br/> |
|已删除电子数据展示事例  <br/> |[删除 ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823844) <br/> |已删除电子数据展示事例。请注意，与案例关联任何保留具有要删除之前可删除这种情况。  <br/> |
|已更改的电子数据展示事例  <br/> |[设置 ComplianceCase](https://go.microsoft.com/fwlink/p/?LinkId=823846) <br/> |电子数据展示事例已更改。更改包括关闭打开的案例或重新打开结束的案例。  <br/> |
|添加了成员到电子数据展示事例  <br/> |[添加 ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823848) <br/> |用户被添加为电子数据展示事例的成员。作为将用例的成员，用户可以执行各种与案例相关的任务，具体取决于他们已被分配所需的权限。  <br/> |
|从电子数据展示事例的已删除的成员  <br/> |[删除 ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823849) <br/> |用户已删除电子数据展示事例的成员身份。  <br/> |
|已更改的电子数据展示案例成员资格  <br/> |[更新 ComplianceCaseMember](https://go.microsoft.com/fwlink/p/?LinkId=823850) <br/> |电子数据展示事例的成员身份列表已更改。所有成员都替换为一组新的用户时记录此活动。如果添加或删除单个成员，将记录**添加 ComplianceCaseMember**或**删除 ComplianceCaseMember**操作。<br/> |
|创建内容搜索  <br/> |[New-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517935) <br/> |创建一个新的内容搜索。  <br/> |
|已删除的内容搜索  <br/> |[Remove-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517936) <br/> |现有的内容搜索已删除。  <br/> |
|已更改内容的搜索  <br/> |[Set-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517937) <br/> |现有的内容搜索已更改。更改可以包括添加或删除搜索的内容位置以及编辑搜索查询。  <br/> |
|启动内容搜索  <br/> |[Start-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517938) <br/> |内容搜索已启动。当您创建或使用安全更改内容的搜索&amp;合规性中心 GUI，搜索会自动启动。如果您创建或使用**新建 ComplianceSearch**或**集 ComplianceSearch** cmdlet 更改搜索，您必须运行**开始 ComplianceSearch** cmdlet 可启动搜索。<br/> |
|停止内容搜索  <br/> |[Stop-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517939) <br/> |正在运行的内容搜索已停止。  <br/> |
|创建内容搜索操作  <br/> |[New-ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=527971) <br/> |已创建的内容搜索操作。内容搜索操作包括预览搜索结果、 导出搜索结果、 准备分析 Office 365 高级电子数据展示中搜索结果和永久删除符合搜索条件的内容搜索的项目。  <br/> |
|已删除的内容搜索操作  <br/> |[删除 ComplianceSearchAction](https://go.microsoft.com/fwlink/p/?LinkId=824027) <br/> |已删除的内容搜索操作。  <br/> |
|创建搜索权限筛选器  <br/> |[新 ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617542) <br/> |创建搜索权限筛选器。  <br/> |
|已删除的搜索权限筛选器  <br/> |[删除 ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617543) <br/> |已删除的搜索权限筛选器。  <br/> |
|更改搜索权限筛选器  <br/> |[设置 ComplianceSecurityFilter](https://go.microsoft.com/fwlink/p/?LinkId=617544) <br/> |搜索权限筛选器已更改。  <br/> |
|创建电子数据展示管理员  <br/> |[添加 eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=798217) <br/> |用户已添加为电子数据展示管理员在组织中。  <br/> |
|已删除电子数据展示管理员  <br/> |[删除 eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823945) <br/> |从您的组织已删除电子数据展示管理员。  <br/> |
|已更改的电子数据展示管理员成员资格  <br/> |[更新 eDiscoveryCaseAdmin](https://go.microsoft.com/fwlink/p/?LinkId=823946) <br/> |电子数据展示管理员在组织中的列表已更改。替换一组新的用户的电子数据展示管理员列表后，将记录此活动。如果添加或删除单个用户，将记录**添加 eDiscoveryCaseAdmin**或**删除 eDiscoveryCaseAdmin**操作。<br/> |
   
## <a name="detailed-properties-for-ediscovery-activities"></a>电子数据展示活动的详细的属性

下表介绍在列出搜索结果中的电子数据展示活动的**详细信息**页上单击**详细信息**时包含的属性。导出审核日志搜索结果时，这些属性还会包含该 CSV 文件中。注意： 为电子数据展示活动的审核日志记录不会包括下面列出的每个详细的属性。 
  
> [!TIP]
> 导出搜索结果时，该 CSV 文件将包含名为**详细信息**，其中包含下表中的多值属性中所述的详细的属性的列。可以使用 Excel 中的高级查询功能将此列拆分为多个列，以使每个属性具有其自己的列。这将允许您进行排序和上一个或多个属性筛选器。有关详细信息，请参阅[的搜索审核日志在 Office 365 安全性和合规性中心](search-the-audit-log-in-security-and-compliance.md#step-4-export-the-search-results-to-a-file)中的"将搜索结果导出到文件"一节。 
  
|**属性**|**说明**|
|:-----|:-----|
|情况  <br/> |创建、 更改或删除的电子数据展示事例的标识 (GUID)。  <br/> |
|ClientApplication  <br/> |电子数据展示 cmdlet 活动有此属性的值的**EMC** 。这指示活动已执行使用安全&amp;合规性中心 GUI 或在 PowerShell 中运行 cmdlet。<br/> |
|ClientIP  <br/> |活动已记录时所使用的设备的 IP 地址。IP 地址被显示在 IPv4 或 IPv6 地址格式。  <br/> |
|ClientRequestId  <br/> | 对于电子数据展示活动，此属性是通常空白。  <br/> |
|CmdletVersion  <br/> |内部版本号版本的安全&amp;运行您的组织中的合规性中心。  <br/> |
|CreationTime  <br/> |日期和时间以协调世界时 (UTC) 时电子数据展示活动的完成。  <br/> |
|EffectiveOrganization  <br/> |名称您的 Office 365 组织。  <br/> |
|ExchangeLocations  <br/> |Exchange Online 邮箱的内容搜索中包括还是置于保留中电子数据展示事例。  <br/> |
|排除  <br/> |邮箱或网站从内容搜索或保留电子数据展示事例中的排除的位置。  <br/> |
|ExtendedProperties  <br/> |从内容的其他属性进行搜索的内容搜索操作，或保留电子数据展示事例，如对象的 GUID 和相应 cmdlet 以及执行活动时所使用的 cmdlet 参数中。  <br/> |
|Id  <br/> |报告条目 ID。ID 唯一标识为审核日志条目。  <br/> |
|NonPIIParameters  <br/> |使用 cmdlet 中的操作属性标识使用的参数 （不带任何值） 的列表。此属性中列出的参数的 Parameters 属性中列出的相同。  <br/> |
|ObjectId  <br/> |GUID 或对象 （例如，内容搜索或电子数据展示事例） 的已创建、 更改或删除活动的操作属性中列出的名称。此对象还将审核日志搜索结果中的项目列中标识。  <br/> |
|ObjectType  <br/> |电子数据展示对象的用户创建、 删除或修改; 的类型例如 （预览、 导出或清除） 的内容搜索操作、 电子数据展示事例或内容的搜索。  <br/> |
|Operation  <br/> |对应于电子数据展示活动的执行操作的名称。  <br/> |
|组织 Id  <br/> |Office 365 组织的 GUID。  <br/> |
|Parameters  <br/> |名称和使用与相应的 cmdlet 的参数的值。  <br/> |
|PublicFolderLocations  <br/> |Exchange Online 的内容搜索中包括还是置于中的公用文件夹位置保留电子数据展示事例中。  <br/> |
|查询  <br/> |与活动，如内容搜索或基于查询的保留关联的搜索查询。  <br/> |
|RecordType  <br/> |由 record 表示的操作的类型。值为**18**指示[电子数据展示 cmdlet 活动](#ediscovery-cmdlet-activities)一节中列出的活动相关的事件。值为**24**指示[如何搜索和查看电子数据展示活动](#how-to-search-for-and-view-ediscovery-activities)一节中列出的活动相关的事件。<br/> |
|ResultStatus  <br/> |指示 （的 Operation 属性中指定） 的操作是成功还是失败。  <br/> |
|SecurityComplianceCenterEventType  <br/> |指示事件是安全&amp;合规性中心事件。所有电子数据展示活动将具有的值为**0** ，此属性。<br/> |
|SharepointLocations  <br/> |SharePoint Online 网站包含在内容搜索或置于保留中电子数据展示事例。  <br/> |
|StartTime  <br/> |日期和时间以协调世界时 (UTC) 启动电子数据展示活动时。  <br/> |
|用户 Id  <br/> |执行导致所记录的记录的活动 （在操作属性中指定） 的用户。请注意，审核日志中还包含由系统帐户 （例如 NT AUTHORITY\SYSTEM) 执行电子数据展示活动记录。  <br/> |
|UserKey  <br/> |UserId 属性中标识的用户的备用 ID。对于电子数据展示活动，此属性的值为通常是 UserId 属性相同。  <br/> |
|UserServicePlan  <br/> |使用您的组织的 Office 365 订阅。对于电子数据展示活动，此属性是通常空白。  <br/> |
|UserType  <br/> |用户执行操作的类型。下列值指示用户类型。  <br/> 0 的常规用户。2 Office 365 组织中的管理员。3 Microsoft 数据中心管理员或 datacenter 系统帐户。4 系统帐户。5 应用程序。6 服务主体。 |
|Version  <br/> |指示记录的活动 （由的 Operation 属性标识） 的版本号。  <br/> |
|工作负荷  <br/> |Office 365 服务活动出现的位置。电子数据展示活动，则值为**SecurityComplianceCenter**。<br/> |
