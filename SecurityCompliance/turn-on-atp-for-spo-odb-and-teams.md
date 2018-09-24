---
title: 打开 Office 365 ATP SharePoint、 OneDrive 和 Microsoft 团队
ms.author: derng
author: derng
manager: laurawi
ms.date: 5/31/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
description: 了解如何开启 ATP for OneDrive 和团队，包括如何设置检测到的文件的通知。
ms.openlocfilehash: bb99aee0887f15f065a47d691c59ce47639bdc32
ms.sourcegitcommit: 17c7e18d7d00135b1af40cbea117c9a817a41117
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "24972234"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>打开 Office 365 ATP SharePoint、 OneDrive 和 Microsoft 团队

[Office 365 ATP SharePoint、 OneDrive 和 Microsoft 团队](atp-for-spo-odb-and-teams.md)可防止组织不小心共享恶意文件。检测到恶意文件时，该文件被阻止，以便没有打开、 复制、 移动或共享它，直到由组织的安全组采取进一步的操作。阅读此文，针对 SharePoint 打开 ATP，OneDrive 和团队，设置警报通知有关检测到的文件，并执行您下一步步骤。 
  
> [!TIP]
> 若要执行本文中描述的任务，您必须分配 Office 365 中和安全性的必要权限&amp;合规性中心。
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>开启适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP

 **开始此过程，请确保审核日志记录您的 Office 365 环境已开启**。这通常是具有审核日志角色分配在 Exchange Online 的人。有关详细信息，请参阅[打开或关闭，打开 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。
  
1. 以全局管理员或 security 管理员程序中，转到[https://protection.office.com](https://protection.office.com)，并使用您的工作或学校帐户登录。
    
2. Office 365 安全性&amp;合规性中心在左侧的导航窗格中，**威胁管理**下面，选择**策略** \> **安全的附件**。
    
    ![安全中&amp;合规性中心中，选择威胁管理\>策略](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)
  
3. 选择**SharePoint、 OneDrive 和 Microsoft 团队 ATP 打开**。
    
    ![启用高级的威胁 Protection for SharePoint Online，OneDrive for Business 和 Microsoft 团队](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)
  
4. 单击“保存”****。
    
5. 查看 （和，根据需要编辑） 贵组织的[安全附件策略](set-up-atp-safe-attachments-policies.md)和[安全链接策略](set-up-atp-safe-links-policies.md)。
    
6. （推荐）以全局管理员或 SharePoint Online 管理员，运行**[Set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet， **DisallowInfectedFileDownload**参数设置为*true* 。 <br/><br/>设置为*true*的块的参数 （除删除） 的所有操作检测到文件。人员无法打开、 移动、 复制或共享检测到的文件。<br/><br/>参数设置为*false*会阻止除删除和下载的所有操作。人员可以选择接受风险并下载检测到的文件。<br/><br/>我们建议将参数设置为*true*。 
   
7. 允许您更改传播到所有 Office 365 数据中心最多 30 分钟。
    
8. （推荐）继续设置通知检测到的文件。
    
> [!TIP]
> 若要了解有关使用 Office 365 PowerShell 的详细信息，请参阅[使用 PowerShell 管理 Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)。> 到时为恶意检测到一个文件，请了解有关用户体验的详细信息，请参阅[SharePoint Online、 OneDrive 或的 Microsoft 团队中找到的恶意文件时要执行什么](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。 
  
## <a name="set-up-alerts-for-detected-files"></a>设置通知检测到的文件

若要在 SharePoint Online、 OneDrive 业务，或 Microsoft 团队的文件已被标识为恶意时收到通知，您可以设置一条通知。
  
1. Office 365 安全性&amp;合规性中心中，选择**警报** \> **管理通知**。
    
2. 选择**新建通知的策略**。
    
3. 指定通知的名称。例如，您可以在库中键入恶意文件。
    
4. 键入通知的说明。例如，SharePoint Online、 OneDrive 或的 Microsoft 团队中检测到恶意文件时，您可以键入通知管理员。
    
5. 在**发送此通知时...** 部分中，执行以下操作： 
    
  - 在**活动**列表中，选择**文件中的检测到恶意软件**。
    
  - 该**用户**字段留空。 
    
6. 在**发送到此通知...** 部分中，选择一个或多个全局管理员、 安全管理员或安全读者应在检测到恶意文件时收到通知。 
    
7. 单击“保存”****。
    
> [!TIP]
> 若要了解有关通知的详细信息，请参阅[在 Office 365 安全性中创建活动通知&amp;合规性中心](create-activity-alerts.md)。 
  
## <a name="next-steps"></a>后续步骤

- [查看有关在 SharePoint、 OneDrive 或的 Microsoft 团队中检测到的恶意文件的信息](malicious-files-detected-in-spo-odb-or-teams.md)
    
- [为 Office 365 中的管理员管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)
    
## <a name="related-topics"></a>相关主题

[Office 365 高级威胁防护](office-365-atp.md)
  
[查看 Office 365 高级威胁保护报告](view-reports-for-atp.md)
  
[Office 365 安全性权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)
  

