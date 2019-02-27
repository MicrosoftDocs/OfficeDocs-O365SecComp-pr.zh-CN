---
title: 零时差自动清除 - 防范垃圾邮件和恶意软件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: 零小时自动清除 (ZAP) 是一种电子邮件保护功能, 可检测到已发送到用户收件箱的垃圾邮件或恶意软件的邮件, 然后将恶意内容无害。ZAP 的工作方式取决于检测到的恶意内容的类型。
ms.openlocfilehash: 84d9c1dc12c3caf0630d25a3980cdaea1830a4c0
ms.sourcegitcommit: baf23be44f1ed5abbf84f140b5ffa64fce605478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30295635"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>零时差自动清除 - 防范垃圾邮件和恶意软件

## <a name="overview"></a>概述

零小时自动清除 (ZAP) 是一种电子邮件保护功能, 可检测到已传递给用户的收件箱的包含网络钓鱼、垃圾邮件或恶意软件的邮件, 然后将恶意内容无害。ZAP 的工作方式取决于检测到的恶意内容的类型;由于邮件内容、url 或附件, 邮件可能会 zapped。
  
ZAP 可与包含 exchange online 邮箱的任何 Office 365 订阅附带的默认 Exchange Online 保护一起使用。

默认情况下, ZAP 处于打开状态, 但必须满足以下条件:
  
- **垃圾邮件操作**设置为 "**将邮件移动到垃圾邮件" 文件夹**。 <br/>您还可以创建仅适用于一组用户的新垃圾邮件筛选器策略 (如果您不希望由 ZAP 筛选所有邮箱)。

- 用户保留其默认的垃圾邮件设置, 但尚未关闭垃圾邮件保护。(有关 Outlook 中用户选项的详细信息, 请参阅[更改垃圾邮件筛选器中的保护级别](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b)。) 
  
## <a name="how-does-zap-work"></a>ZAP 的工作原理是什么？

Office 365 每天实时更新反垃圾邮件引擎和恶意软件签名。但是, 用户仍可能会因各种原因而将恶意邮件传递到其收件箱, 其中包括在将内容传递给用户后 weaponized 内容。ZAP 通过持续监控对 Office 365 垃圾邮件和恶意软件签名的更新来解决此情况。ZAP 可查找并删除已在用户收件箱中的以前传递的邮件。 

- 对于被标识为垃圾邮件的邮件, ZAP 将未读邮件移动到用户的 "垃圾邮件" 文件夹。 

- 对于被标识为垃圾邮件的邮件, ZAP 将邮件移动到用户的垃圾邮件文件夹, 而不管是否已阅读电子邮件。

- 对于新检测到的恶意软件, ZAP 将从电子邮件中删除附件, 而不管是否已阅读电子邮件。 
  
对于邮箱用户, ZAP 操作是无缝的;如果移动电子邮件, 则不会收到通知。
  
允许列表、[邮件流规则](https://go.microsoft.com/fwlink/p/?LinkId=722755)和最终用户规则或其他筛选器优先于 ZAP。
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a>查看或设置垃圾邮件筛选器策略
  
1. 请转[https://protection.office.com](https://protection.office.com)到使用 Office 365 的工作或学校帐户登录并登录。

2. 在 "**威胁管理**" 下, 选择 "**反垃圾邮件**"。

3. 查看标准设置。 

4. 如果要自定义设置, 请选择 "**自定义**" 选项卡, 然后打开 "**自定义设置**"。编辑设置, 如果需要, 请选择 " **+ 创建策略**" 以添加新策略。 
    
## <a name="to-see-if-zap-moved-your-message"></a>查看 ZAP 是否移动了邮件

如果要查看 ZAP 是否移动了邮件, 可以使用 "[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)" (或 "[威胁资源管理器](use-explorer-in-security-and-compliance.md)")。
    
## <a name="to-disable-zap"></a>禁用 ZAP
  
如果要对 Office 365 租户或一组用户禁用 ZAP, 请使用[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)的**ZapEnabled**参数 (EOP cmdlet)。
    
在下面的示例中, 对名为 "Test" 的内容筛选器策略禁用了 ZAP。
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a>常见问题解答

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>如果将合法邮件移动到 "垃圾邮件" 文件夹中, 会发生什么情况？
  
您应遵循正常的报告过程假阳性。将邮件从 "收件箱" 移动到 "垃圾邮件" 文件夹的唯一原因是, 该服务已确定邮件是垃圾邮件还是恶意邮件。
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>如果我使用的是 Office 365 隔离, 而不是垃圾邮件文件夹, 该怎么办？
  
此时, ZAP 不会将邮件从收件箱中移入隔离区。
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>如果我有自定义邮件流规则 (阻止/允许规则), 该怎么办？
  
由管理员 (邮件流规则) 或阻止和允许规则创建的规则优先。将从功能条件中排除此类邮件。
  
## <a name="related-topics"></a>相关主题

[Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)
  
[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](reduce-spam-email.md)
  

