---
title: 零时差自动清除 - 防范垃圾邮件和恶意软件
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/11/2019
audience: Admin
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
description: 零小时自动清除 (ZAP) 是一种电子邮件保护功能, 可检测到已发送到用户收件箱的垃圾邮件或恶意软件的邮件, 然后将恶意内容无害。 ZAP 的工作方式取决于检测到的恶意内容的类型。
ms.openlocfilehash: 91bb167c988e49a40895f851a518ee255abdbf08
ms.sourcegitcommit: 769b506c828c475c713dbb337e115714dcc7f17c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2019
ms.locfileid: "36698964"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>零时差自动清除 - 防范垃圾邮件和恶意软件

## <a name="overview"></a>概述

零小时自动清除 (ZAP) 是一种电子邮件保护功能, 可检测到已传递给用户的收件箱的包含网络钓鱼、垃圾邮件或恶意软件的邮件, 然后将恶意内容无害。 ZAP 的工作方式取决于检测到的恶意内容的类型;由于邮件内容、Url 或附件, 邮件可能会 zapped。
  
ZAP 可与包含 Exchange Online 邮箱的任何 Office 365 订阅附带的默认 Exchange Online 保护一起使用。

默认情况下, ZAP 处于打开状态, 但必须满足以下条件:
  
- **垃圾邮件操作**设置为 "**将邮件移动到垃圾邮件" 文件夹**。 您还可以创建仅适用于一组用户的新垃圾邮件筛选器策略 (如果您不希望由 ZAP 筛选所有邮箱)。

- 用户保留其默认的垃圾邮件设置, 但尚未关闭垃圾邮件保护。 (有关 Outlook 中用户选项的详细信息, 请参阅[更改垃圾邮件筛选器中的保护级别](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。)
  
## <a name="how-zap-works"></a>ZAP 的工作方式

Office 365 每天实时更新反垃圾邮件引擎和恶意软件签名。 但是, 用户仍可能会因各种原因而将恶意邮件传递到其收件箱, 其中包括在将内容传递给用户后 weaponized 内容。 ZAP 通过持续监控对 Office 365 垃圾邮件和恶意软件签名的更新来解决此情况。 ZAP 可查找并删除已在用户收件箱中的以前传递的邮件。

对于邮箱用户, ZAP 操作是无缝的;如果移动电子邮件, 则不会收到通知。 消息不得早于2天。
  
允许列表、[邮件流规则](https://go.microsoft.com/fwlink/p/?LinkId=722755)(也称为传输规则) 和最终用户规则或其他筛选器优先于 ZAP。

### <a name="malware-zap"></a>恶意软件 ZAP

对于新检测到的恶意软件, ZAP 将从电子邮件中删除附件, 并将邮件正文保留在用户邮箱中。 无论邮件的阅读状态如何, 都会删除附件。

在恶意软件策略中, 默认情况下会启用恶意软件 ZAP。 您可以使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的[get-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy) cmdlet 上的*ZapEnabled*参数禁用恶意软件 ZAP。

### <a name="phish-zap"></a>网络钓鱼 ZAP

对于在传递后被标识为网络钓鱼的邮件, ZAP 将根据用户所涵盖的垃圾邮件策略采取措施。 如果将策略网络钓鱼操作设置为对邮件执行操作 (重定向、删除、隔离、移动到垃圾), 则 ZAP 会将邮件移动到用户收件箱的 "垃圾邮件" 文件夹, 而不管邮件的阅读状态如何。 如果策略网络钓鱼操作未设置为 "采取操作" (添加 X 标头、"修改主题"、"无操作"), 则 ZAP 不会对邮件执行操作。 了解有关如何在此处[配置垃圾邮件筛选器策略](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies)的详细信息。

默认情况下, 会在垃圾邮件策略中启用网络钓鱼 ZAP。 您可以使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) cmdlet 上的*ZapEnabled*参数禁用网络钓鱼 ZAP。

### <a name="spam-zap"></a>垃圾邮件 ZAP

对于在传递后被标识为垃圾邮件的邮件, ZAP 将根据用户所涵盖的垃圾邮件策略采取措施。 如果 "策略垃圾邮件" 操作设置为 "对邮件执行操作 (重定向、删除、隔离、移动到垃圾)", 则 ZAP 会将邮件移到用户收件箱的 "垃圾邮件" 文件夹中 (如果该邮件未读)。 如果策略垃圾操作未设置为 "采取操作" (添加 X 标头、"修改主题"、"无操作"), 则 ZAP 不会对邮件执行操作。 了解有关如何在此处[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)的详细信息。

垃圾邮件策略中默认启用垃圾邮件 ZAP。 您可以使用 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中的[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758) Cmdlet 的*ZapEnabled*参数禁用垃圾邮件 ZAP。

> [!NOTE]
> **Set-hostedcontentfilterpolicy** cmdlet 上的*ZapEnabled*参数将禁用或启用此策略的网络钓鱼 ZAP 和垃圾邮件 zap。 您不能在同一策略中单独启用或禁用网络钓鱼 ZAP 和垃圾邮件 ZAP。

## <a name="how-to-see-if-zap-moved-your-message"></a>如何查看 ZAP 是否移动了邮件

若要确定 ZAP 是否移动了邮件, 可以使用[威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)或[威胁浏览器 (和实时检测)](threat-explorer.md)。

## <a name="disable-zap"></a>禁用 ZAP

若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。 若要连接到 Exchange Online Protection PowerShell, 请参阅[连接到 Exchange Online Protection powershell](https://go.microsoft.com/fwlink/p/?linkid=627290)。

### <a name="disable-malware-zap"></a>禁用恶意软件 ZAP * *

此示例在名为 "Test" 的恶意软件筛选器策略中禁用 ZAP。

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

有关语法和参数的详细信息, 请参阅[get-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)。

### <a name="disable-phish-zap-and-spam-zap"></a>禁用网络钓鱼 ZAP 和垃圾邮件 ZAP

此示例在名为 "Test" 的内容筛选器策略中禁用了网络钓鱼 ZAP 和垃圾邮件 ZAP。

```Powershell
Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

有关语法和参数的详细信息, 请参阅[set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)。

## <a name="faq"></a>常见问题

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>如果将合法邮件移动到 "垃圾邮件" 文件夹中, 会发生什么情况？
  
您应遵循正常的报告过程[假阳性](prevent-email-from-being-marked-as-spam.md)。 将邮件从 "收件箱" 移动到 "垃圾邮件" 文件夹的唯一原因是, 该服务已确定邮件是垃圾邮件还是恶意邮件。
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>如果我使用的是 Office 365 隔离, 而不是垃圾邮件文件夹, 该怎么办？
  
此时, ZAP 不会将邮件从收件箱中移入隔离区。
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>如果我有自定义邮件流规则 (阻止/允许规则), 该怎么办？
  
由管理员 (邮件流规则) 或阻止和允许规则创建的规则优先。 将从功能条件中排除此类邮件, 以便邮件流遵循规则操作 (阻止/允许规则)。

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a>如果邮件被移到另一个文件夹 (例如收件箱规则), 该怎么办？

在这种情况下, ZAP 仍适用, 除非邮件已被删除或在垃圾邮件中。

## <a name="related-topics"></a>相关主题

[Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)
  
[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](reduce-spam-email.md)
