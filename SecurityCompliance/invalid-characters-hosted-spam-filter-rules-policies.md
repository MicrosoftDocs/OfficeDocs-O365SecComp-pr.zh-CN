---
title: 避免垃圾邮件筛选器规则和垃圾邮件筛选器策略中的无效字符
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 9/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 为在反垃圾邮件配置中具有无效字符的管理员提供帮助, 并在尝试使用安全&amp;合规性中心时遇到问题。
ms.openlocfilehash: 90cf89d019a34658b676f02baa84c70f27200262
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276072"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>避免垃圾邮件筛选器规则和垃圾邮件筛选器策略中的无效字符 

以前, Office 365 管理员使用 Exchange 管理中心 (EAC) 设置和配置了垃圾邮件筛选器规则和垃圾邮件筛选器策略。现在, 您可以使用安全&amp;合规性中心管理您的反垃圾邮件配置。以下字符在 EAC 中受支持, 但不支持在安全&amp;合规性中心中使用。  

**无效字符:**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

如果垃圾邮件筛选器规则或垃圾邮件筛选器策略包含任何无效字符, 则可能会遇到以下任何或所有问题:
- 您可能无法在安全&amp;合规中心中找到策略或规则。
- 尝试使用 Windows PowerShell 获取规则或策略时, 可能会收到错误。
- 您可能会发现策略或设置未按预期方式运行或执行。

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>删除垃圾邮件筛选器策略和规则中的无效字符

在确定了包含无效字符的策略和规则后, 可以使用 Windows PowerShell cmdlet 更改这些名称。 

1. [使用远程 PowerShell 连接到 Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。
    
2. 若要更改垃圾邮件筛选器策略的名称, 请运行 set-hostedcontentfilterpolicy cmdlet, 如下所示:
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. 若要更改垃圾邮件筛选器规则的名称, 请运行 disable-hostedcontentfilterrule cmdlet, 如下所示:
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>更多信息

[安全&amp;合规性中心中的威胁管理](threat-management.md)
  
[set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[disable-hostedcontentfilterrule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)
