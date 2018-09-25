---
title: 避免垃圾邮件筛选器规则和垃圾邮件筛选器策略中的无效字符
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/24/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: 提供有关管理员在其反垃圾邮件配置具有无效字符，并尝试使用安全时遇到问题的帮助&amp;合规性中心。
ms.openlocfilehash: ca409b4daa7bec01417adb7cbfdfa2a128929e81
ms.sourcegitcommit: c168410974bc90aaf55f1dcaa9e05c09b2b78d76
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018731"
---
# <a name="avoid-invalid-characters-in-your-spam-filter-rules-and-spam-filter-policy"></a>避免垃圾邮件筛选器规则中的无效字符和垃圾邮件筛选器策略 

以前，Office 365 管理员设置和使用 Exchange 管理员中心 (EAC) 中配置垃圾邮件筛选器规则和垃圾邮件筛选器策略。现在，您使用安全&amp;合规性中心管理反垃圾邮件配置。以下字符已支持在 EAC 中，但不是支持使用安全中&amp;合规性中心。  

**无效字符：**
  
```\ % & * + / = ? { } | < > ( ) ; : , [ ] "```

如果垃圾邮件筛选器规则或您的垃圾邮件筛选器策略中包含无效字符，您可能会遇到任何或所有这些问题：
- 您可能无法找到安全中的规则或策略&amp;合规性中心。
- 尝试使用 Windows PowerShell 获取规则或策略时，可能会收到错误。
- 您可能会发现，策略或设置不要运行或按预期执行。

## <a name="remove-the-invalid-characters-from-the-spam-filter-policy-and-rules"></a>移除的垃圾邮件筛选器策略和规则的无效字符

一旦您确定的策略和规则包含无效字符，您可以通过使用 Windows PowerShell cmdlet 来更改名称。 

1. [连接到 Exchange Online 使用远程 PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps)。
    
2. 若要更改的垃圾邮件筛选器策略的名称，请运行 Set-hostedcontentfilterpolicy cmdlet，如下所示：
    
    ```
    Set-HostedContentFilterPolicy -Identity "Old policy name" -Name "New policy name"
    ```  

3. 若要更改垃圾邮件筛选器规则的名称，请运行 Set-hostedcontentfilterrule cmdlet，如下所示：
    
    ```
    Set-HostedContentFilterRule -Identity "Old rule name" -Name "New rule name"
    ```  

  
 ## <a name="for-more-information"></a>更多信息

[威胁安全中的管理&amp;合规性中心](threat-management.md)
  
[Set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy?view=exchange-ps)

[Set-hostedcontentfilterrule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule?view=exchange-ps)
