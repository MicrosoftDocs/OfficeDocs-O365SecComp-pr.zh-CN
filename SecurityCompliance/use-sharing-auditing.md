---
title: 使用共享 Office 365 审核日志中的审核功能
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 2/13/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- BCS160
- MET150
ms.assetid: 50bbf89f-7870-4c2a-ae14-42635e0cfc01
description: '共享是 SharePoint Online 和 OneDrive for Business 中的主要活动。管理员可以立即使用共享 Office 365 审核日志中的审核功能来确定如何共享中正使用的组织。 '
ms.openlocfilehash: 511f8b0e61d450659d78177d5b87fac9ee636cd4
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525514"
---
# <a name="use-sharing-auditing-in-the-office-365-audit-log"></a>使用共享 Office 365 审核日志中的审核功能

共享是一项关键活动在 SharePoint Online 和 OneDrive for Business，且广泛使用 Office 365 组织中。管理员可以立即使用共享 Office 365 审核日志中的审核功能来确定如何共享中正使用的组织。 
  
## <a name="the-sharepoint-sharing-schema"></a>SharePoint 共享架构

共享事件 （不包括共享策略和共享链接事件） 与具有不同的文件和文件夹相关的事件中主要的一种方法： 一个用户正在影响某些另一个用户操作。例如，用户 A 使用户 B 访问文件。本示例中，用户 A 是 *、 用户*和用户 B 是*目标用户*。在 SharePoint 文件架构中的活动用户操作只影响该文件本身。当用户 A 打开一个文件， **FileAccessed**事件中所需的唯一信息是活动的用户。为了解决这种差异，没有单独的架构，调用*SharePoint 共享架构*，捕获有关共享事件的详细信息。这样可确保管理员具有更多深入人员共享资源和用户资源已与共享。 
  
共享架构提供了与共享事件相关的审核日志中的两个其他字段： 
  
- **TargetUserOrGroupName** -存储的 UPN 或目标用户或组将与 (在前面的示例用户 B) 中的共享资源的名称。 
    
- **TargetUserOrGroupType** -标识是否目标用户或组的成员、 来宾、 组或合作伙伴。 
    
这两个字段，除了从 Office 365 的其他属性审核日志架构，如用户、 操作和日期可以判断有关*哪些*用户共享*哪些*资源使用*其*和*时*的全部内容。 
  
没有另一个共享文章对重要的架构属性。**EventData**属性存储有关共享事件的其他信息。例如，如果用户与其他用户共享网站，这一点通过向 SharePoint 组添加目标用户。**EventData**属性捕获此其他信息来为管理员提供的上下文。 

## <a name="the-sharepoint-sharing-model-and-sharing-events"></a>SharePoint 共享模型和共享事件

共享由三个单独的事件实际上定义： **SharingSet**、 **SharingInvitationCreated**和**SharingInvitaitonAccepted**。下面是如何共享事件的工作流登录 Office 365 审核日志。 
  
![共享审核的工作方式的流程图](media/d83dd40f-919b-484f-bfd6-5dc8de31bff6.png)
  
当用户 （活动用户） 希望与另一个用户 （目标用户） 共享资源时，SharePoint （或 OneDrive for Business） 首先检查目标用户的电子邮件地址是否已在组织目录中的用户帐户相关联。如果目标用户位于组织的目录中，SharePoint 将执行以下操作：
  
-  立即分配访问该资源的目标用户权限。 
    
- 向目标用户的电子邮件地址发送共享通知。
    
- 记录**SharingSet**事件。 
    
 如果目标用户的用户帐户不在组织的目录，SharePoint 将执行以下操作： 
  
- 创建共享邀请并将其发送到目标用户的电子邮件地址。
    
- 记录**SharingInvitationCreated**事件。 
    
    > [!NOTE]
    > **SharingInvitationCreated**事件最始终是与外部或来宾共享目标用户不具有对共享资源的访问时相关联。 
  
当目标用户接受共享邀请已发送给他们 （通过单击邀请中的链接），SharePoint 日志**SharingInvitationAccepted**事件，并分配访问该资源的目标用户权限。有关目标用户的其他信息也会记录，如邀请发送给用户和实际接受邀请的用户的标识。在某些情况下，这些用户 （或电子邮件地址） 可能会有所不同。 
  

  
## <a name="how-to-identify-resources-shared-with-external-users"></a>如何识别与外部用户共享资源

管理员的常见要求创建与组织外部的用户共享的所有资源的列表。通过使用共享 Office 365 中的审核功能，管理员可以立即生成此列表。下面是如何。
  
### <a name="step-1-search-for-sharing-events-and-export-the-results-to-a-csv-file"></a>步骤 1： 搜索共享事件并将结果导出到 CSV 文件

第一步是搜索 Office 365 审核日志中的共享事件。有关详细信息 （包括所需的权限） 搜索审核日志，请参阅[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)。
  
1. 转到[https://protection.office.com](https://protection.office.com)。
    
2. 登录到 Office 365 使用工作或学校帐户。
    
3. 安全的左窗格中&amp;合规性中心，单击**搜索&amp;调查**，然后单击**审核日志搜索**。
    
    将显示**审核日志搜索**页。 
    
4. 在下**活动**，单击**共享活动**搜索仅共享事件。 
    
    ![在活动下，选择共享活动](media/46bb25b7-1eb2-4adf-903a-cc9ab58639f9.png)
  
5.  选择要查找在该时间段内发生的共享事件日期和时间范围。 
    
6. 单击**搜索**以运行 search。 
    
7. 完成搜索时将显示运行和结果，单击**导出结果** \> **下载所有结果**。
    
    选择导出选项后，将提示您打开或保存 CSV 文件的窗口底部显示一条消息。
    
8. 单击**保存** \> **另存为**本地计算机上将 CSV 文件保存到一个文件夹。 
    

  
### <a name="step-2-filter-the-csv-file-for-resources-shared-with-external-users"></a>步骤 2： 筛选与外部用户共享资源的 CSV 文件

下一步是其中**TargetUserOrGroupType**属性是**来宾**筛选对于**SharingSet**和**SharingInvitationCreated**事件，CSV 并显示这些事件。您将在 Excel 中使用高级查询功能来执行此操作。Excel 2016 中执行以下过程。 
  
1. 在 Excel 2016 打开一个空白工作簿。
    
2. 单击“数据”**** 选项卡。 
    
3. 单击**新建查询** \> **文件从** \> **从 CSV**。
    
    ![数据选项卡中，选择新建查询、 从文件中，选择，然后选择从 CSV](media/5170ab34-b449-40ea-bd3f-f1432c1c5973.png)
  
4. 在步骤 1 中打开您下载的 CSV 文件。
    
    在查询编辑器中打开 CSV 文件。请注意，有四列：**时间**、**用户**、**操作**和**详细信息**。**详细信息**列是多个属性字段。下一步是为每个**详细信息**列中的属性创建新列。 
    
5. 选择**详细信息**列中，，然后单击在**主页**选项卡上的**拆分列** \> **通过分隔符**。
    
    ![在主页选项卡上，单击拆分列，然后单击通过分隔符](media/aeb503e8-565b-42ea-91e2-9f127a74c00c.png)
  
6. 在**拆分列分隔符由**窗口中，执行以下操作： 
    
      - 在**选择或输入分隔符**，选择**逗号**。
    
      - **拆分**，选择**在分隔符的每次出现**。
    
7. 单击“确定”****。
    
    **详细信息**列拆分为多个列。**Detail.1**、 **Detail.2**、 **Detail.3**，等名为每个新列。您会注意到的名称属性; 对于发自**Detail.n**列中的每个单元格中的值例如，**操作： SharingSet**、**操作： SharingInvitationAccepted**和**操作： SharingInvitationCreated**。
    
    ![详细信息列拆分成多列，一个用于每个属性](media/4b104ead-0313-4bd4-b2a9-f143ccb378ac.png)
  
8. 在**文件**选项卡上单击**关闭&amp;负载**关闭查询编辑器，并在 Excel 工作簿中打开该文件。 
    
    下一步是筛选要仅显示的**SharingSet**和**SharingInvitationCreated**事件的文件。 
    
9. 转到**主页**选项卡，然后选择**操作**列。 
    
10. 在**排序&amp;筛选器**下拉列表中，清除所有的选项，然后选择**SharingSet**和**SharingInvitationCreated**，然后单击**确定**。
    
    Excel 将显示的**SharingSet**和**SharingInvitationCreated**事件中的行。 
    
11. 转到名为**Detail.17** （或任何列包含**TargetUserOrGroupType**属性） 的列，并选择它。 
    
12. 在**排序&amp;筛选器**下拉列表中，清除所有的选项，然后选择**TargetUserOrGroupType:Guest**，并单击**确定**。
    
    现在 Excel 显示**SharingInvitationCreated**和**SharingSet**事件和目标用户所在组织外部的行，因为由值**TargetUserOrGroupType:Guest**标识外部用户。 
    
下表显示与指定的日期范围内来宾用户共享资源的组织中的所有用户。
  
![Office 365 中的共享事件审核日志](media/0e0ecbe3-c794-4ca6-a2ca-63478fb3bb34.png)
  
尽管它不包括上表中， **Detail.10**列 （或任何列包含**ObjectId**属性） 标识与目标用户; 已共享的资源例如`ObjectId:https:\/\/contoso-my.sharepoint.com\/personal\/sarad_contoso_com\/Documents\/Southwater Proposal.docx`。
  
> [!TIP]
> 如果您想要确定当访客用户已实际分配访问权限资源 (而不是只需的资源的位置与他们共享)、 重复步骤 10 和 11，12，和筛选所依据的**SharingInvitationAccepted**和**SharingSet**步骤 10 中的事件。 