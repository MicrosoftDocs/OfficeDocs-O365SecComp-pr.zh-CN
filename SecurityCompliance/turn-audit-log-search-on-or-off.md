---
title: 启用或禁用 Office 365 审核日志搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: 您可以在安全 & 合规中心启用审核日志搜索功能。 如果你更改了想法, 你可以随时关闭。 当 "审核日志搜索" 关闭时, 管理员无法在组织中搜索用户和管理员活动的 Office 365 审核日志。
ms.openlocfilehash: 0619b19f9dc6e8bdc21e26275f02a81948b40bf4
ms.sourcegitcommit: 69d0c739a2f3b4a335b42182a2c7267ef554eb76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2019
ms.locfileid: "31389706"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a>启用或禁用 Office 365 审核日志搜索

您 (或另一个管理员) 必须先启用审核日志记录, 然后才能开始搜索 Office 365 审核日志。 当 Security & 合规中心中的审核日志搜索打开时, 您的组织中的用户和管理员活动将记录在审核日志中, 并在90天内保留。 但是, 您的组织可能不想记录和保留审核日志数据。 或者, 您可能使用第三方安全信息和事件管理 (SIEM) 应用程序访问您的审核数据。 在这些情况下, 全局管理员可以在 Office 365 中关闭审核日志搜索。
  
## <a name="before-you-begin"></a>开始之前

- 您必须在 Exchange Online 中向您分配 "审核日志" 角色, 才能在 Office 365 组织中打开或关闭审核日志搜索。 默认情况下, 此角色在 Exchange 管理中心中的 "**权限**" 页上分配给合规性管理和组织管理角色组。 Office 365 中的全局管理员是 Exchange Online 中的 "组织管理" 角色组的成员。 
    
    > [!IMPORTANT]
    > 必须在 Exchange Online 中向用户分配权限, 才能打开或关闭审核日志搜索。 如果在 Security & 合规性中心中向用户分配 "**权限**" 页面上的 "审核日志" 角色, 他们将无法打开或关闭审核日志搜索。 这是因为基础 cmdlet 是 Exchange Online cmdlet。 
  
- 如果关闭了 office 365 中的审核日志搜索, 将无法使用 office 365 管理活动 API 来访问您的组织的审核数据。 按照本文中的步骤关闭审核日志搜索意味着, 在使用 Security & 合规性中心搜索审核日志时, 或者在 Exchange Online 中运行**UnifiedAuditLog** cmdlet 时, 不会返回任何结果。PowerShell. 这也意味着你的审核日志将无法通过 Office 365 管理活动 API 提供。  
    
- 有关搜索 Office 365 审核日志的分步说明, 请参阅[在 Security & 合规性中心搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。
    
## <a name="turn-on-audit-log-search"></a>启用审核日志搜索

您可以使用安全 & 合规性中心或 PowerShell 在 Office 365 中启用审核日志搜索。 在您打开审核日志搜索后, 可能需要几个小时才能在搜索审核日志时返回结果。 您必须在 Exchange Online 中向您分配 "审核日志" 角色, 才能启用审核日志搜索。
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a>使用安全 & 合规性中心启用审核日志搜索

1. 在 "安全 & 合规性中心" 中, 转到 "**搜索** \> **审核日志搜索**"。
    
2. 单击 "**开始记录用户和管理员活动**"。
    
    ![单击 "开始记录用户和管理员活动" 以启用审核](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    将显示一个对话框, 指出组织中的用户和管理员活动将记录到 Office 365 审核日志中, 并可在报告中查看。 
    
3. 单击" **开启** "。
    
    将显示一条消息, 指出正在准备审核日志, 并且您可以在准备完成后的几小时内运行搜索。
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a>使用 PowerShell 打开审核日志搜索

1. [连接 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. 运行以下 PowerShell 命令以在 Office 365 中启用审核日志搜索。
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    将显示一条消息, 指出可能需要长达60分钟的时间才能使更改生效。
  
## <a name="turn-off-audit-log-search"></a>关闭审核日志搜索

您必须使用连接到 Exchange Online 组织的远程 PowerShell, 才能关闭审核日志搜索。 与启用审核日志搜索类似, 您必须在 Exchange Online 中将 "审核日志" 角色分配给 "关闭审核日志搜索"。
  
1. [连接 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. 运行以下 PowerShell 命令以关闭 Office 365 中的审核日志搜索。
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. 一段时间后, 验证审核日志搜索是否已关闭 (已禁用)。 可通过 2 种方法执行此操作：
    
    - 在 PowerShell 中, 运行以下命令:

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        UnifiedAuditLogIngestionEnabled 属性的`False`值指示__ 已关闭审核日志搜索。 
    
    - 在 "安全 & 合规性中心" 中, 转到 "**搜索** \> **审核日志搜索**", 然后单击 "**搜索**"。
    
      将显示一条消息, 指出未启用审核日志搜索。 
    
      ![如果禁用了审核功能, 则会显示一条消息](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
