---
title: 适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.date: 03/19/2019
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
description: 将 Office 365 高级威胁防护扩展到 SharePoint Online、OneDrive for Business 和 Microsoft 团队中的文件, 为您的组织启用更安全的协作。
ms.openlocfilehash: 1a9fbf54b1393f250bc259ecb2e8bb9fd36f2ae0
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598638"
---
# <a name="office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP

## <a name="overview-of-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP 概述

用户定期共享文件, 并使用 SharePoint、OneDrive 和 Microsoft 团队进行协作。 使用[Office 365 高级威胁防护](office-365-atp.md)(ATP), 您的组织可以更安全地进行协作。 ATP 可帮助检测和阻止在工作组网站和文档库中被标识为恶意的文件。  
  
## <a name="how-it-works"></a>运作方式

如果 SharePoint Online、OneDrive for Business 和 Microsoft 团队中的文件被标识为恶意, ATP 将直接与文件存储集成以锁定该文件。 下图显示了在库中检测到的恶意文件的示例。
  
[![OneDrive for business 中一个检测为恶意的文件](media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
尽管阻止的文件仍在文档库和 web、移动设备或桌面应用程序中列出, 但无法打开、复制、移动或共享被阻止的文件。 但是, 用户可以删除被阻止的文件。 下面的示例展示了在用户的移动设备上显示的内容:
  
[![从 OneDrive 移动应用程序中删除 OneDrive for business 中的阻止文件](media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
根据配置 Office 365 的方式, 用户可能会或可能无法下载被阻止的文件。 下面介绍了如何在用户的移动设备上下载被阻止的文件:
  
[![在 OneDrive for Business 中下载阻止的文件](media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
  
若要了解详细信息, 请参阅[打开 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。
  
## <a name="keep-these-points-in-mind"></a>记住这些要点

- ATP 将不会扫描 SharePoint Online、OneDrive for Business 或 Microsoft 团队中的每个单个文件。 这是设计造成的。 通过使用共享和来宾活动事件的进程以及智能试探和威胁信号识别恶意文件, 异步扫描文件。

- 确保您的 SharePoint 网站已配置为使用[新式体验](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)。 当文件被标识为恶意的且被阻止时, 人们可以看到这种情况发生在新式体验中, 而不是经典视图中。 ATP protection 适用于是否使用新式体验或经典视图;但是, 仅在新式体验中, 才会出现阻止文件的视觉指示器。
    
- 在 SharePoint Online、OneDrive for Business 或 Microsoft 团队中被标识为恶意的文件将显示在[Office 365 高级威胁防护](view-reports-for-atp.md)和[资源管理器 (和实时检测)](threat-explorer.md)的报告中。
    
- ATP 是组织整体威胁防护策略的一部分, 其中包括反垃圾邮件和反恶意软件保护, 以及安全链接和安全附件。 若要了解详细信息, 请参阅[在 Office 365 中防御威胁](protect-against-threats.md)。
    
- SharePoint Online 管理员可以确定是否允许用户下载被检测为恶意的文件。 这是通过使用 DisallowInfectedFileDownload 参数运行 Set-spotenant PowerShell cmdlet 来实现的 (请参阅[打开 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md))。
    
## <a name="quarantine-in-atp-for-sharepoint-online-onedrive-for-business-and-microsoft-teams"></a>SharePoint Online、OneDrive for Business 和 Microsoft 团队的 ATP 中的隔离

 从后期开始可能为 2018 [](quarantine-email-messages.md) , 安全&amp;合规中心中的隔离功能将扩展到 SharePoint Online、OneDrive For business 和 Microsoft 团队的 ATP。
  
当 SharePoint Online、OneDrive for Business 或 Microsoft 团队中的文件被标识为恶意文件时, 除了 ATP 阻止打开或共享该文件之外, 该文件还包含在隔离项目的列表中。 (在安全&amp;合规性中心中, 转到 "**威胁管理** \> " "**查看** \> **隔离**" 和 "筛选**内容**"。) 
  
如果您是组织的 Office 365 安全团队的一部分, 并且拥有[在 Office 365 安全&amp;合规中心中分配](permissions-in-the-security-and-compliance-center.md)的必要权限, 则可以通过 ATP 下载、发布、报告和删除被检测为恶意的文件。从隔离区。
  
- **释放和报告**文件将在 SharePoint、OneDrive 或 Microsoft 团队的相应团队网站或文档库中删除文件上的 ATP 块。 然后, 用户可以打开、共享和下载文件。 当选择 "**向 Microsoft 发送报告**" 选项时, 该文件将报告为 "误报到 microsoft"。 
    
- **删除文件**会将文件从隔离区中删除。但是, 仍阻止打开或共享文件。 此外, 还必须在其各自的文档库或团队网站 (SharePoint Online、OneDrive for Business 或 Microsoft 团队) 中删除该文件。 
    
- 通过**下载文件**, 您可以下载并分析文件, 以查找任何误报。 
    
## <a name="next-steps"></a>后续步骤

1. [打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)
    
2. [查看有关在 SharePoint、OneDrive 或 Microsoft 团队中检测到的恶意文件的信息](malicious-files-detected-in-spo-odb-or-teams.md)
    
