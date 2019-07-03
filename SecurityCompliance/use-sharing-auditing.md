---
title: 审核共享以查找与外部用户共享的资源
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: '共享是 SharePoint Online 和 OneDrive for business 中的关键活动。 管理员现在可以在 Office 365 审核日志中使用共享审核来确定如何在组织中使用共享。 '
ms.openlocfilehash: e2865d35e988d8c0e42a6c51f78507db8b170d4c
ms.sourcegitcommit: b262d40f6daf06be26e7586f37b736e09f8a4511
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35435233"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a>审核共享以查找与外部用户共享的资源

共享是 SharePoint Online 和 OneDrive for business 中的关键活动, 并在 Office 365 组织中广泛使用。 管理员现在可以在 Office 365 审核日志中使用共享审核来确定如何在组织中使用共享。 
  
## <a name="the-sharepoint-sharing-schema"></a>SharePoint 共享架构

共享事件 (不包括共享策略和共享链接事件) 与文件和文件夹相关的事件有一个主要的不同之处: 一个用户正在采取对另一个用户有影响的操作。 例如, 用户 A 向用户 B 授予对文件的访问权限。 在此示例中, 用户 A 是*作用用户*, 而用户 B 是*目标用户*。 在 SharePoint 文件架构中, 作用用户的操作仅影响文件本身。 当用户 A 打开文件时, **FileAccessed**事件中所需的唯一信息是操作用户。 为了解决这种差异, 有一个称为*SharePoint 共享架构*的单独架构, 可捕获有关共享事件的详细信息。 这可确保管理员能够更好地了解共享资源的人员和共享资源的用户。 
  
共享架构在与共享事件相关的审核日志中提供了两个附加字段: 
  
- **TargetUserOrGroupName** –存储与之共享资源的目标用户或组的 UPN 或名称 (上一示例中的用户 B)。 
    
- **TargetUserOrGroupType** –标识目标用户或组是否为成员、来宾、组或合作伙伴。 
    
除了 Office 365 审核日志架构 (如用户、操作和日期) 以外的其他属性, 这两个字段还可以详细说明*哪些*用户共享了哪些用户与*谁*共享了*哪些*资源。 ** 
  
还有另一个架构属性, 对共享情景很重要。 **EventData**属性存储有关共享事件的其他信息。 例如, 当用户与其他用户共享网站时, 可以通过将目标用户添加到 SharePoint 组来实现此目的。 **EventData**属性捕获此附加信息, 以便为管理员提供上下文。 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a>SharePoint 共享模型和共享事件

共享由三个单独的事件定义: **SharingSet**、 **SharingInvitationCreated**和**SharingInvitaitonAccepted**。 下面介绍了如何在 Office 365 审核日志中记录共享事件的工作流。 
  
![共享审核工作原理的流程图](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
当用户 (用户) 想要与其他用户 (目标用户) 共享资源时, SharePoint (或 OneDrive for Business) 先检查目标用户的电子邮件地址是否已与组织目录中的用户帐户相关联。 如果目标用户在组织的目录中, 则 SharePoint 将执行以下操作:
  
-  立即向目标用户分配访问资源的权限。 
    
- 向目标用户的电子邮件地址发送共享通知。
    
- 记录**SharingSet**事件。 
    
 如果目标用户的用户帐户不在组织的目录中, 则 SharePoint 将执行以下操作: 
  
- 创建共享邀请, 并将其发送到目标用户的电子邮件地址。
    
- 记录**SharingInvitationCreated**事件。 
    
    > [!NOTE]
    > 当目标用户没有访问共享资源的权限时, **SharingInvitationCreated**事件最常与外部共享或来宾共享关联。 
  
当目标用户接受发送给他们的共享邀请 (通过单击邀请中的链接) 时, SharePoint 会记录一个**SharingInvitationAccepted**事件并为目标用户分配访问资源的权限。 还会记录有关目标用户的其他信息, 例如向其发送邀请的用户的标识以及实际接受邀请的用户。 在某些情况下, 这些用户 (或电子邮件地址) 可能会有所不同。 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a>如何识别与外部用户共享的资源

管理员的常见要求是创建已与组织外部的用户共享的所有资源的列表。 通过使用 Office 365 中的共享审核, 管理员现在可以生成此列表。 方法如下：
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>步骤 1: 搜索共享事件并将结果导出到 CSV 文件

第一步是在 Office 365 审核日志中搜索共享事件。 有关搜索审核日志的详细信息 (包括所需的权限), 请参阅[在安全 & 合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。
  
1. 转到 [https://protection.office.com](https://protection.office.com)。
    
2. 使用工作或学校帐户登录到 Office 365。
    
3. 在安全性 & 合规性中心的左侧窗格中, 单击 "**搜索**  > **审核日志搜索**"。
    
    将显示 "**审核日志搜索**" 页。 
    
4. 在 "**活动**" 下, 单击 "**共享和访问请求活动**" 以搜索与共享相关的事件。 
    
    ![在 "活动" 下, 选择 "共享和访问请求活动"](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  选择日期和时间范围以查找在该时间段内发生的共享事件。 
    
6. 单击 "**搜索**" 以运行搜索。 
    
7. 当搜索运行完成并显示结果后, 单击 "**导出结果** \> " "**下载所有结果**"。
    
    选择 "导出" 选项后, 会在窗口底部显示一条消息, 提示您打开或保存 CSV 文件。
    
8. 单击 "**另** \>存**为**", 然后将 CSV 文件保存到本地计算机上的文件夹中。 

### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a>步骤 2: 筛选 CSV 文件, 以获取与外部用户共享的资源

下一步是筛选**SharingSet**和**SHARINGINVITATIONCREATED**事件的 CSV, 并显示**TargetUserOrGroupType**属性为 "**来宾**" 的那些事件。 您可以使用 Excel 中的 Power Query 编辑器工具执行此操作。 有关分步说明, 请参阅[导出、配置和查看审核日志记录](export-view-audit-log-records.md)。 

按照上一主题中的说明准备 CSV 文件后, 请执行以下操作:
    
1. 打开使用 Power Query 编辑器准备的 CSV 文件。 

2. 在 "**开始**" 选项卡上, 单击 "**排序 & 筛选**", 然后单击 "**筛选**"。
    
3. 在 "**操作**" 列上的 "**排序 & 筛选**" 下拉列表中, 清除所有选择, 然后选择 " **SharingSet** " 和 " **SharingInvitationCreated**", 然后单击 **"确定"**。
    
    Excel 显示**SharingSet**和**SharingInvitationCreated**事件的行。 
    
4. 转到名为**TargetUserOrGroupType**的列, 然后选择它。 
    
5. 在 "**排序 & 筛选**" 下拉列表中, 清除 "所有选择", 然后选择 " **TargetUserOrGroupType: Guest**", 然后单击 **"确定"**。
    
    现在, Excel 将显示**SharingInvitationCreated**和**SharingSet**事件的行, 以及目标用户在组织外部的位置, 因为外部用户由值**TargetUserOrGroupType: Guest**标识。 
    
下表显示在指定日期范围内与来宾用户共享资源的组织中的所有用户。
  
![在 Office 365 审核日志中共享事件](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
[! 注意] **ObjectId**属性不包含在上表中, 但它标识与目标用户共享的资源;例如`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`。
  
> [!TIP]
> 如果要标识来宾用户实际何时被分配访问某个资源的权限 (而不只是与它们共享的资源), 请重复步骤2、3和 4, 并在**SharingInvitationAccepted**和**SharingSet**上进行筛选。步骤5中的事件。 
