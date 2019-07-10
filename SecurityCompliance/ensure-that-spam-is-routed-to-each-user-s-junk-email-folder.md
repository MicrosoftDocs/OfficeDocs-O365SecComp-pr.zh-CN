---
title: 确保垃圾邮件已路由到每个用户的“垃圾邮件”文件夹
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 7/16/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何将垃圾邮件路由到 Exchange Online Protection 中的用户垃圾邮件文件夹。
ms.openlocfilehash: dc37f2428e009f00a2d6d9dd15d5d2cd505f267a
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599848"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>确保垃圾邮件已路由到每个用户的“垃圾邮件”文件夹

> [!IMPORTANT]
> 本主题仅适用于在混合部署中承载本地邮箱的 Exchange Online Protection (EOP) 客户。 其邮箱在 Office 365 中完全托管的 Exchange Online 客户无需运行这些命令。 
  
EOP 客户的默认反垃圾邮件操作是将垃圾邮件移到收件人的 "垃圾邮件" 文件夹。 为了使此操作能够与本地邮箱配合使用, 必须在本地边缘或中心服务器上配置 Exchange 邮件流规则 (也称为传输规则), 以检测由 EOP 添加的垃圾邮件头。 这些邮件流规则将 Set-organizationconfig cmdlet 的 SclJunkThreshold 属性使用的垃圾邮件可信度 (SCL) 设置为将垃圾邮件移到每个邮箱的 "垃圾邮件" 文件夹中。 
  
### <a name="to-add-mail-flow-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a>添加邮件流规则, 以确保使用 Windows PowerShell 将垃圾邮件移动到 "垃圾邮件" 文件夹

1. 访问内部部署 Exchange 服务器的 Exchange 命令行管理程序。 若要了解如何在本地 Exchange 组织中打开 Exchange 命令行管理程序，请参阅 **Open the Shell**。
    
2. 运行以下命令以将内容经过筛选的垃圾邮件路由到垃圾邮件文件夹：
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    其中_NameForRule_是新规则的名称, 例如, JunkContentFilteredMail。 
    
3. 运行以下命令以将在到达内容筛选器之前标记为垃圾邮件的邮件路由到垃圾邮件文件夹：
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    其中_NameForRule_是新规则的名称, 例如, JunkMailBeforeReachingContentFilter。 
    
4. 运行以下命令，以确保来自垃圾邮件筛选器策略中阻止列表的发件人的邮件（如**发件人阻止**列表）都会被路由到垃圾邮件文件夹： 
    
  ```Powershell
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    其中_NameForRule_是新规则的名称, 例如, JunkMailInSenderBlockList。 
    
如果您不想使用 "**将邮件移动到垃圾邮件文件夹**" 操作, 则可以在 Exchange 管理中心中的内容筛选器策略中选择另一个操作。 有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。 有关邮件头中这些字段的详细信息, 请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。
  

> [!TIP]
> 如果不想使用 "**将邮件移动到垃圾邮件文件夹**" 操作, 则可以在 Exchange 管理中心中的内容筛选器策略中选择另一个操作。 有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。 有关邮件头中这些字段的详细信息, 请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。
> 
## <a name="see-also"></a>另请参阅

[New-transportrule cmdlet](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

