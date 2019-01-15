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
ms.openlocfilehash: 435e1f449003f670f698c4e6813e18f5e83c498d
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014794"
---
# <a name="view-information-about-malicious-files-detected-in-sharepoint-onedrive-or-microsoft-teams"></a>查看有关在 SharePoint、 OneDrive 或的 Microsoft 团队中检测到的恶意文件的信息

[SharePoint、 OneDrive 和 Microsoft 团队的 office 365 ATP](atp-for-spo-odb-and-teams.md)从文档库和工作组网站中的恶意文件保护您的组织。检测到恶意文件时，该文件被阻止，以便没有打开、 复制、 移动或共享它，直到由组织的安全组采取进一步的操作。阅读此文，了解如何查看有关检测到的文件的信息和要采取的操作。 

若要执行本文中描述的任务，您必须具有必要[Office 365 安全权限&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="view-reports-with-information-about-detected-files"></a>查看报告包含有关检测到的文件的信息

若要查看状态和有关通过 Office 365 ATP 检测到的文件的详细的信息，您可以使用威胁保护状态报告。
  
1. 在[Office 365 安全性&amp;合规性中心](https://protection.office.com)，选择**报告** \> **仪表板** \> **威胁保护状态**。
    
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
  
  

