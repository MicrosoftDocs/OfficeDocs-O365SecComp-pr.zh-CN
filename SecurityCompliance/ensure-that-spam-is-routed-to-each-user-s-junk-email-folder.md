---
title: 确保垃圾邮件已路由到每个用户的“垃圾邮件”文件夹
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/16/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 0cbaccf8-4afc-47e3-a36d-a84598a55fb8
description: EOP 客户的默认反垃圾邮件操作是将垃圾邮件移动到收件人的垃圾邮件文件夹。为了使此操作，以与内部部署邮箱一起使用，您必须来检测垃圾邮件邮件头由 EOP 添加您的内部边缘或集线器服务器上配置 Exchange 传输规则。这些传输规则设置 Set-organizationconfig cmdlet 的 SclJunkThreshold 属性用来将垃圾邮件移动到垃圾邮件文件夹中每个邮箱的垃圾邮件可信度 (SCL)。
ms.openlocfilehash: 290a3cc6aed07cd4d91df65350fd49c9226a0d64
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026629"
---
# <a name="ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>确保垃圾邮件已路由到每个用户的“垃圾邮件”文件夹

> [!IMPORTANT]
> 本主题仅适用于承载邮箱的本地混合部署中的 Exchange Online Protection (EOP) 客户。邮箱已在 Office 365 中完全承载的 Exchange Online 客户不需要运行以下命令。 
  
EOP 客户的默认反垃圾邮件操作是将垃圾邮件移动到收件人的垃圾邮件文件夹。为了使此操作，以与内部部署邮箱一起使用，您必须来检测垃圾邮件邮件头由 EOP 添加您的内部边缘或集线器服务器上配置 Exchange 传输规则。这些传输规则设置 Set-organizationconfig cmdlet 的 SclJunkThreshold 属性用来将垃圾邮件移动到垃圾邮件文件夹中每个邮箱的垃圾邮件可信度 (SCL)。 
  
### <a name="to-add-transport-rules-to-ensure-spam-is-moved-to-the-junk-email-folder-by-using-windows-powershell"></a>将传输规则以确保垃圾邮件移动到垃圾邮件文件夹使用 Windows PowerShell

1. 访问 Exchange 命令行管理程序在本地 Exchange 服务器。若要了解如何在本地 Exchange 组织中打开 Exchange Management Shell，请参阅**打开命令行管理程序**。
    
2. 运行以下命令以将内容经过筛选的垃圾邮件路由到垃圾邮件文件夹：
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SPM" -SetSCL 6
  ```

    其中_NameForRule_是新规则，例如 JunkContentFilteredMail 的名称。 
    
3. 运行以下命令以将在到达内容筛选器之前标记为垃圾邮件的邮件路由到垃圾邮件文件夹：
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKS" -SetSCL 6
  ```

    其中_NameForRule_是新规则，例如 JunkMailBeforeReachingContentFilter 的名称。 
    
4. 运行以下命令，以确保来自垃圾邮件筛选器策略中阻止列表的发件人的邮件（如**发件人阻止**列表）都会被路由到垃圾邮件文件夹： 
    
  ```
  New-TransportRule "NameForRule" -HeaderContainsMessageHeader "X-Forefront-Antispam-Report" -HeaderContainsWords "SFV:SKB" -SetSCL 6
  ```

    其中_NameForRule_是新规则，例如 JunkMailInSenderBlockList 的名称。 
    
如果不希望使用**移动到垃圾邮件文件夹的邮件**操作，您可以选择您在 Exchange 管理中心中的内容筛选器策略中的另一项操作。有关详细信息，请参阅[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)。有关这些邮件头中的字段的详细信息，请参阅[反垃圾邮件邮件头](anti-spam-message-headers.md)。
  
## <a name="see-also"></a>另请参阅

[New-transportrule cmdlet](https://technet.microsoft.com/library/bb125138%28v=exchg.160%29.aspx)

