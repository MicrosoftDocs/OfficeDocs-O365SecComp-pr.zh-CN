---
title: 打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection: M365-security-compliance
description: 了解如何为 SharePoint、OneDrive 和团队打开 ATP, 包括如何为检测到的文件设置通知。
ms.openlocfilehash: 8ba82a812881b53636f2fbc941ee04bc5dacdac1
ms.sourcegitcommit: 32cb896aef370764ec6e8f8278ebaf16f1c5ff37
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/20/2019
ms.locfileid: "30123893"
---
# <a name="turn-on-office-365-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP

[适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP](atp-for-spo-odb-and-teams.md)可防止您的组织无意中共享恶意文件。检测到恶意文件时, 将阻止该文件, 以便在组织的安全团队执行进一步操作之前, 任何人都无法打开、复制、移动或共享该文件。阅读本文以打开 SharePoint、OneDrive 和团队的 ATP, 设置通知以获得检测到的文件的通知, 并采取后续步骤。 
  
若要定义 (或编辑) ATP 策略, 必须为您分配适当的角色。下表介绍了一些示例:

|角色  |分配的位置/方式  |
|---------|---------|
|Office 365 全局管理员 |默认情况下, 注册购买 Office 365 的人是全局管理员。(请参阅[关于 Office 365 管理员角色](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)以了解详细信息。)         |
|Security Administrator |Azure Active Directory 管理中心 ([https://aad.portal.azure.com](https://aad.portal.azure.com))|
|Exchange Online 组织管理 |Exchange 管理中心 ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) <br>或 <br>  PowerShell cmdlet (请参阅[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)) |
  
## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP

在**开始此过程之前, 请确保已为您的 Office 365 环境启用审核日志记录**。这通常由在 Exchange Online 中分配了审核日志角色的人完成。有关详细信息, 请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。
  
1. 转到[https://protection.office.com](https://protection.office.com), 然后使用你的工作或学校帐户登录。
    
2. 在 "Office 365 安全&amp;合规中心" 的左侧导航窗格中的 "**威胁管理**" 下, 选择 "**策略** \> **安全附件**"。 <br/>![在 "安全&amp;合规性中心" 中, \>选择 "威胁管理策略"](media/08849c91-f043-4cd1-a55e-d440c86442f2.png)
  
3. 选择 "**为 SharePoint、OneDrive 和 Microsoft 团队启用 ATP**"。<br/>![为 SharePoint Online、OneDrive for business 和 Microsoft 团队启用高级威胁防护](media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)
  
4. 单击“**保存**”。
    
5. 查看 (并根据需要编辑) 您组织的[安全附件策略](set-up-atp-safe-attachments-policies.md)和[安全链接策略](set-up-atp-safe-links-policies.md)。
    
6. 适合作为全局管理员或 SharePoint Online 管理员, 运行**[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** cmdlet, 并将**DisallowInfectedFileDownload**参数设置为*true*。 <br/>
      - 如果将参数设置为*true, 则*会阻止检测到的文件的所有操作 (删除除外)。用户无法打开、移动、复制或共享检测到的文件。
      - 将参数设置为*false*将阻止除 "删除" 和 "下载" 以外的所有操作。用户可以选择接受风险并下载检测到的文件。  
   
7. 允许最长30分钟的更改传播到所有的 Office 365 数据中心。
    
8. 适合继续设置针对检测到的文件的通知。
    
若要了解有关在 Office 365 中使用 PowerShell 的详细信息, 请参阅[使用 powershell 管理 Office 365](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)。 

若要详细了解在将文件检测为恶意时的用户体验, 请参阅在[SharePoint Online、OneDrive 或 Microsoft 团队中找到恶意文件时应执行的操作](https://support.office.com/article/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。 
  
## <a name="set-up-alerts-for-detected-files"></a>为检测到的文件设置通知

若要在 SharePoint Online、OneDrive for business 或 Microsoft 团队中的文件被标识为恶意文件时收到通知, 可以设置警报。
  
1. 在 " [Office 365 安全&amp;合规中心](https://protection.office.com)" 中, 选择 "**通知** \> " "**管理通知**"。
    
2. 选择 "**新建警报策略**"。
    
3. 指定警报的名称。例如, 可以在库中键入恶意文件。
    
4. 键入警报的说明。例如, 可以键入在 SharePoint Online、OneDrive 或 Microsoft 团队中检测到恶意文件时通知管理员。
    
5. 在 "**发送此通知**的条件 ..." 部分, 执行下列操作: 
    
    在 "**活动**" 列表中, 选择 "**文件中检测到的恶意软件**"。
    
    b. 将 "**用户**" 字段留空。 
    
6. 在 "**将此通知发送给 ...** " 部分, 选择一个或多个全局管理员、安全管理员或在检测到恶意文件时应收到通知的安全阅读者。 
    
7. 单击“**保存**”。
    
若要了解有关通知的详细信息, 请参阅[在 Office 365 安全&amp;合规中心中创建活动通知](create-activity-alerts.md)。 
  
## <a name="next-steps"></a>后续步骤

1. [查看有关在 SharePoint、OneDrive 或 Microsoft 团队中检测到的恶意文件的信息](malicious-files-detected-in-spo-odb-or-teams.md)
    
2. [以 Office 365 中的管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)
    

  

