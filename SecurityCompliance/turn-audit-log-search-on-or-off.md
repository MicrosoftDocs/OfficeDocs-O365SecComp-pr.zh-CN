---
title: 启用或禁用 Office 365 审核日志搜索
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/18/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: 您可以打开 Office 365 安全性的审核日志搜索功能&amp;合规性中心。如果更改您应注意，您可以随时如果关闭。审核日志搜索关闭时，管理员无法在组织中搜索用户和管理活动的 Office 365 审核日志。
ms.openlocfilehash: 4fa6ac095222addce578294813cbd22dfc50a2ab
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525419"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a>启用或禁用 Office 365 审核日志搜索

您 （或其他管理员） 必须启用审核日志记录之前可以开始搜索的 Office 365 审核日志。当审核日志搜索 Office 365 安全性&amp;合规性中心处于打开状态，从您的组织的用户和管理活动中的审核日志记录并保留 90 天。但是，您的组织可能不希望记录并保留审核日志数据。或者，您可能要使用的第三方安全信息和事件管理 (SIEM) 应用程序来访问审核数据。在这些情况下，全局管理员可以关闭 Office 365 中的审核日志搜索。
  
## <a name="before-you-begin"></a>准备工作

- 您必须分配审核日志角色在 Exchange Online 以启用或禁用 Office 365 组织中的审核日志搜索。默认情况下，此角色分配给 Exchange 管理中心中的**权限**页上合规性管理和组织管理角色组。Office 365 中的全局管理员是 Organization Management 角色组的成员在 Exchange Online。 
    
    > [!IMPORTANT]
    > 用户必须为其分配权限在 Exchange Online 以启用或禁用的审核日志搜索。如果您将用户分配安全中**权限**页上的审核日志角色&amp;合规性中心，它们将无法打开或关闭的审核日志搜索。这是因为基础 cmdlet 是 Exchange Online cmdlet。 
  
- 如果要关闭 Office 365 中的审核日志搜索，您仍可以使用 Office 365 管理活动 API 访问审核数据的组织。按照本文中的步骤关闭审核日志搜索是指搜索使用安全的审核日志时，将返回任何结果&amp;合规性中心或 Exchange Online 中运行**搜索 UnifiedAuditLog** cmdlet 时PowerShell。但是，如果您已被授权访问 Office 365 管理活动 API 通过组织的审核数据的任何应用程序，这些应用程序将继续工作。 
    
- 搜索 Office 365 的分步指导审核日志，请参阅[Office 365 安全性搜索审核日志&amp;合规性中心](search-the-audit-log-in-security-and-compliance.md)。
    
## <a name="turn-on-audit-log-search"></a>启用审核日志搜索

您可以使用安全&amp;合规性中心或 PowerShell 打开 Office 365 中的审核日志搜索。可能需要几个小时后就启用审核日志搜索之前搜索审核日志时，可以返回结果。您必须分配审核日志角色在 Exchange Online 以启用审核日志搜索。
  
### <a name="use-the-security-amp-compliance-center-to-turn-on-audit-log-search"></a>使用安全&amp;打开审核日志搜索的合规性中心

1. 安全中&amp;合规性中心中，转到**搜索&amp;调查** \> **审核日志搜索**。
    
2. 单击**开始录制用户和管理活动**。
    
    ![单击“开始记录用户和管理员活动”启用审核](media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    告知用户和管理组织中的活动将对 Office 365 审核日志记录和报告中可查看来显示一个对话框。 
    
3. 单击" **开启** "。
    
    将显示一条消息，指出正在准备审核日志和，您可以在几个小时准备完毕后运行搜索。
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a>使用 PowerShell 启用审核日志搜索

1. [使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. 运行以下 PowerShell 命令打开 Office 365 中的审核日志搜索。
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    被显示一条消息，告知，可能需要最多 60 分钟更改才能生效。
  
## <a name="turn-off-audit-log-search"></a>关闭审核日志搜索

您需要使用远程 PowerShell 连接到 Exchange Online 组织关闭审核日志搜索。类似于打开审核日志搜索，您需要分配审核日志角色在 Exchange Online 关闭审核日志搜索。
  
1. [使用远程 PowerShell 连接到 Exchange Online](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. 运行以下 PowerShell 命令，将会关闭 Office 365 中的审核日志搜索。
    
    ```
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. 后一段时间，确认审核日志搜索关闭 （禁用）。有两种方法来执行此操作：
    
    - 在 PowerShell 中，运行以下命令：

        ```
        Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
        ```

        值`False`的_UnifiedAuditLogIngestionEnabled_属性指示处于关闭状态的审核日志搜索。 
    
    - 安全中&amp;合规性中心中，转到**搜索&amp;调查** \> **审核日志搜索**，然后单击**搜索**。
    
      反映审核日志搜索未开启来显示一条消息。 
    
      ![如果审核处于关闭状态，一条消息，则 dispayed](media/dca53da6-1cbe-4fa3-9860-f0d674de9538.png)
