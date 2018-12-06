---
title: 零时差自动清除 - 防范垃圾邮件和恶意软件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/05/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
description: 零时差自动清除 (ZAP) 是一个检测到的已发送到用户的收件箱，垃圾邮件或恶意软件的邮件的电子邮件保护功能，然后呈现恶意内容权衡。ZAP 原理这取决于检测到的恶意内容类型。
ms.openlocfilehash: 1cf14051e91801a74a0d739c69900bb3f825b318
ms.sourcegitcommit: 204fb0269b5c10b63941055824e863d77e3e9b02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2018
ms.locfileid: "27180842"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>零时差自动清除 - 防范垃圾邮件和恶意软件

## <a name="overview"></a>概述

零时差自动清除 (ZAP) 是一个检测到的已发送到用户的收件箱，与网络钓鱼诈骗、 垃圾邮件或恶意软件的邮件的电子邮件保护功能，然后呈现恶意内容权衡。ZAP 原理这取决于检测到; 恶意内容类型由于邮件内容、 Url 或附件，可以 zapped 邮件。
  
默认值是包含任何 Office 365 订阅包含 Exchange Online 邮箱的 Exchange Online Protection 提供 ZAP。

ZAP 已打开默认情况下，但必须满足下列条件：
  
- **垃圾邮件操作**设置为**移动到垃圾邮件文件夹的邮件**。 <br/>您还可以创建仅适用于一组用户如果您不希望通过 ZAP 屏蔽所有邮箱的新垃圾邮件筛选器策略。

- 用户具有保留其默认垃圾邮件设置，并不关闭垃圾邮件保护。（请参阅在 Outlook 中的用户选项的详细信息的[更改的垃圾邮件筛选保护级别](https://support.office.com/article/change-the-level-of-protection-in-the-junk-email-filter-e89c12d8-9d61-4320-8c57-d982c8d52f6b)。） 
  
## <a name="how-does-zap-work"></a>ZAP 如何工作？

Office 365 更新中的反垃圾邮件引擎和恶意软件签名实时每天。但是，用户可能仍获取恶意邮件传递到各种起见，如果内容 weaponized 传递给用户后包括其收件箱。将清除此通过不断监视更新到 Office 365 垃圾邮件和恶意软件签名的地址。ZAP 可以查找并删除以前发送的邮件已被用户的收件箱。 

- 标识为垃圾邮件的邮件，ZAP 将未读的邮件移动到用户的垃圾邮件文件夹。 

- 标识为垃圾邮件的邮件，ZAP 将邮件移动到用户的垃圾邮件文件夹，而不管是否已读取电子邮件。

- 对于新检测到恶意软件、 ZAP 中删除附件的电子邮件，而不管是否已读取电子邮件中。 
  
ZAP 操作是无缝的邮箱用户;他们不通知如果移动电子邮件。
  
允许列表、[邮件流规则](https://go.microsoft.com/fwlink/p/?LinkId=722755)和最终用户规则或其他筛选器优先于 ZAP。
  
## <a name="to-review-or-set-up-a-spam-filter-policy"></a>若要查看或设置的垃圾邮件筛选器策略
  
1. 转到[https://protection.office.com](https://protection.office.com)和 Office 365 中使用您的工作或学校帐户登录。

2. 在**威胁管理**下选择**反垃圾邮件**。

3. 查看标准的设置。 

4. 如果您想要自定义设置，选择**自定义**选项卡，并打开**自定义设置**。编辑您的设置，如果您希望，选择 **+ 创建策略**添加新策略。 
    
## <a name="to-see-if-zap-moved-your-message"></a>若要查看 ZAP 是否移动消息

如果您想要查看 ZAP 如果移动消息，您可以使用[威胁保护状态报告](view-email-security-reports.md#threat-protection-status-report-new)（或[威胁资源管理器](use-explorer-in-security-and-compliance.md)）。
    
## <a name="to-disable-zap"></a>若要禁用 ZAP
  
如果您想要禁用的 Office 365 租户，将清除或一组用户，使用[Set-hostedcontentfilterpolicy](https://go.microsoft.com/fwlink/p/?LinkId=722758)，EOP cmdlet 的**ZapEnabled**参数。
    
在以下示例中，名为"Test"的内容筛选器策略禁用 ZAP。
    
```
  Set-HostedContentFilterPolicy -Identity Test -ZapEnabled $false
```

## <a name="faq"></a>常见问题解答

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>如果合法邮件移动到垃圾邮件文件夹，则会发生什么情况？
  
您应遵循的误报报告的常规过程。应为邮件将从收件箱移动到垃圾邮件文件夹的唯一原因，因为该服务已确定的消息是垃圾邮件或恶意。
  
### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>如果使用 Office 365 隔离而不是垃圾邮件文件夹？
  
ZAP 不将邮件移动到隔离收件箱这一次。
  
### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>如果我有自定义邮件流规则 （阻止 / 允许规则）？
  
由管理员 （邮件流规则） 或阻止和允许规则创建的规则的优先级。此类邮件将排除在功能条件。
  
## <a name="related-topics"></a>相关主题

[Office 365 反垃圾邮件保护](anti-spam-protection.md)
  
[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](block-email-spam-to-prevent-false-negatives.md)
  

