---
title: 查看有关在 SharePoint、 OneDrive 或的 Microsoft 团队中检测到的恶意文件的信息
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 5ed8abf1-c0e9-4e5b-a5b7-2059cea50b61
description: 了解在哪里查看有关在 SharePoint、 OneDrive 或团队中检测到的恶意文件的信息以及如何对这些文件执行操作。
ms.openlocfilehash: 370e5e3d4d7fd5f35caa8ef993f6245d15ee9999
ms.sourcegitcommit: 099bbfb1d16b251fd5cf18ec6515faaf9a989176
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25454269"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>查看有关在 SharePoint、 OneDrive 或的 Microsoft 团队中检测到的恶意文件的信息

[SharePoint、 OneDrive 和 Microsoft 团队的 office 365 ATP](atp-for-spo-odb-and-teams.md)从文档库和工作组网站中的恶意文件保护您的组织。检测到恶意文件时，该文件被阻止，以便没有打开、 复制、 移动或共享它，直到由组织的安全组采取进一步的操作。阅读此文，了解如何查看有关检测到的文件的信息和要采取的操作。 

若要执行本文中描述的任务，您必须具有必要[Office 365 安全性分配权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="view-reports-with-information-about-detected-files"></a>查看报告包含有关检测到的文件的信息

若要查看状态和有关通过 Office 365 ATP 检测到的文件的详细的信息，您可以使用威胁保护状态报告。
  
1. Office 365 安全性&amp;合规性中心中，选择**报告** \> **仪表板** \> **威胁保护状态**。
    
2. 在报表的右上角，选择**查看详细信息表**。
    
3. 查看报告中检测到的文件的列表。
    
4. 在查看详细的信息，包括执行的操作、 文件名、 文件路径，和列表中选择一个项目。
    
5. 选择**高级分析**选项卡查看信息，如观察到的行为和分析详细信息。 
  
## <a name="view-and-take-action-on-files-in-quarantine"></a>查看并隔离中对文件执行操作

1. Office 365 安全性&amp;合规性中心中，选择**威胁管理** \> **审阅** \> **隔离**。
    
2. 左上角，将筛选器从**电子邮件**更改为**内容**。
    
3. 在查看详细的信息，包括文件的 URL 列表中选择一个项目。
    
4. 选择可用操作。
    
  - 选择**版本&amp;报告**取消阻止的文件。 
    
    选择**将报告发送给 Microsoft**以向 Microsoft 将该文件报告为误报。 
    
  - 选择**文件下载**来进行调查进一步的文件。 
    
  - 选择**删除**以从隔离项目的列表中删除该文件。如果您选择此选项，还必须适用于商务或 Microsoft 团队从其各自的库中 SharePoint Online、 OneDrive 删除该文件。打开或共享，则此选项不会不取消阻止被文件。 
    
5. 选择**关闭**以关闭的选定项的详细信息。 
  
## <a name="related-topics"></a>相关主题

[Office 365 高级威胁防护](office-365-atp.md)
  
[查看 Office 365 高级威胁保护报告](view-reports-for-atp.md)
  
[Office 365 安全性权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)

[为 Office 365 中的管理员管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)
  

