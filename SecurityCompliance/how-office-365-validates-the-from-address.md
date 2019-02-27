---
title: Office 365 如何验证发件人地址以防止仿冒
ms.author: tracyp
author: MSFTTracyp
manager: laurawi
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
ms.collection:
- M365-security-compliance
description: '为了帮助防止网络钓鱼, Office 365 和 Outlook.com 现在要求来自: 地址的 RFC 合规性。'
ms.openlocfilehash: e540e56a7a40d13a92719865fccefefa61de47c2
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276142"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Office 365 如何验证发件人地址以防止仿冒

Office 365 和 Outlook.com 电子邮件帐户会收到越来越多的网络钓鱼攻击。一种可仿冒者使用的技术是发送其发件人: 地址值不符合[RFC 5322](https://tools.ietf.org/html/rfc5322)的邮件。"发件人:" 地址也称为 "5322.from 地址"。为了帮助阻止此类型的网络钓鱼, Office 365 和 Outlook.com 要求服务收到的邮件包括符合 RFC 的 From: address, 如本文中所述。
  
> [!NOTE]
> 本文中的信息要求您对电子邮件地址的常规格式有一个基本的了解。有关详细信息, 请参阅[rfc 5322](https://tools.ietf.org/html/rfc5322) (尤其是3.2.3、3.4 和 3.4.1)、 [rfc 5321](https://tools.ietf.org/html/rfc5321)以及[rfc 3696](https://tools.ietf.org/html/rfc3696)。本文介绍了5322.from 地址的策略实施。本文不介绍5321的5321.mailfrom 地址。 
  
遗憾的是, 在 Internet 上仍有一些旧的电子邮件服务器会继续发送 "合法" 电子邮件, 这些邮件缺少或格式不正确的发件人: 地址。如果您定期收到使用这些旧系统的组织发来的电子邮件, 则鼓励这些组织更新其邮件服务器以遵守新式安全标准。
  
Microsoft 将开始在2017年11月9日开始推出本文所述策略的实施。
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a>Office 365 如何强制使用有效的 From: 地址来防止网络钓鱼攻击

Office 365 正在改变它在收到的邮件中强制使用 From: address 的方式, 以便更好地保护您免受网络钓鱼攻击。本文内容:
  
- [所有邮件都必须包含有效的发件人: 地址](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- ["发件人: 地址" 的格式 (如果不包含显示名称)](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- ["发件人: 地址" 的格式 (如果包含显示名称)](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [有效和无效发件人的其他示例: addresses](how-office-365-validates-the-from-address.md#Examples)
    
- [禁止自动答复您的自定义域, 而无需中断 "发件人:" 策略](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [替代 Office 365 发件人: 地址强制策略](how-office-365-validates-the-from-address.md#Override)
    
- [阻止和防止 cybercrimes 在 Office 365 中的其他方法](how-office-365-validates-the-from-address.md#OtherProtection)
    
代表其他用户发送邮件不受此更改的影响, 有关详细信息, 请阅读 Terry Zink 的博客 "[我们是什么？当我们引用电子邮件的 ' 发件人 '？" 时, 这是什么意思？](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)。
  
### <a name="all-messages-must-include-a-valid-from-address"></a>所有邮件都必须包含有效的发件人: 地址
<a name="MustIncludeFromAddress"> </a>

某些自动消息在发送时不包括发件人: 地址。过去, 当 Office 365 或 Outlook.com 收到不含发件人: 地址的邮件时, 该服务会将以下默认的 "发件人" 地址添加到邮件中, 以便其可交付结果如下:
  
```
From: <>
```

从2017年11月9日开始, office 365 将对其数据中心和邮件服务器进行更改, 这将强制实施一个新规则, 在该规则中, Office 365 或 Outlook.com 不再接受邮件地址 (如果邮件没有发件人: 地址)。相反, Office 365 接收到的所有邮件都必须已经包含有效的 From: address。否则, 邮件将被发送到 Outlook.com 和 Office 365 中的 "垃圾邮件" 或 "已删除邮件" 文件夹。 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a>语法概述: From: address for Office 365 的有效格式
<a name="SyntaxOverviewFromAddress"> </a>

"发件人: 地址" 的值的格式是在几个 rfc 中详细定义的。寻址方面有很多变化, 可视为有效或无效。为了使其简单, Microsoft 建议使用以下格式和定义:
  
```
From: "displayname " <emailaddress >
```

其中：
  
- Optional *displayname*是描述电子邮件地址所有者的短语。例如, 这可能是用户友好的名称, 用于描述发件人的名称, 而不是邮箱的名称。可选择使用显示名称。但是, 如果您选择使用显示名称, Microsoft 建议您始终将其括在引号中, 如下所示。 
    
- 需要 *emailaddress*由以下内容组成: 
    
  ```
  local-part @domain
  ```

    其中：
    
  - 需要 *local-part*是标识与地址关联的邮箱的字符串。这在域中是唯一的。邮箱所有者的用户名或 GUID 通常用作本地部分的值。 
    
  - 需要 *domain*是邮件服务器的完全限定域名 (FQDN), 该域名托管由电子邮件地址的本地部分标识的邮箱。 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a>"发件人: 地址" 的格式 (如果不包含显示名称)
<a name="FormatNoDisplayName"> </a>

格式正确的 "发件人:" 地址不包含显示名称仅包含一个电子邮件地址, 带有或不带尖括号。Microsoft 建议您不要用空格分隔尖括号。此外, 在电子邮件地址后不要包含任何内容。
  
下面的示例是有效的:
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

下面的示例是有效的, 但建议您不要这样做, 因为尖括号和电子邮件地址之间包含空格:
  
```
From: < sender@contoso.com >
```

下面的示例是无效的, 因为它在电子邮件地址后包含文本:
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a>"发件人: 地址" 的格式 (如果包含显示名称)
<a name="FormatDisplayName"> </a>

对于 "发件人:" 包含显示名称值的地址, 下列规则适用:
  
- 如果发件人地址包含显示名称, 并且显示名称中包含逗号, 则显示名称必须用引号括起来。例如:
    
    下面的示例是有效的:
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    以下示例无效:
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    如果显示名称包含逗号因 RFC 5322 而无效, 则不将显示名称括在引号中。
    
    作为最佳实践, 无论显示名称中是否有逗号, 都会在显示名称两边加上引号。
    
- 如果发件人地址包含显示名称, 则电子邮件地址必须括在尖括号中。
    
    作为一种最佳做法, Microsoft 强烈建议您在显示名称和电子邮件地址之间插入空格。
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a>有效和无效发件人的其他示例: addresses
<a name="Examples"> </a>

- 有效
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- 无效。电子邮件地址不带尖括号括起来:
    
  ```
  From: Office 365 sender@contoso.com
  ```

- 有效, 但不建议使用。显示名称不在引号中。最佳做法是, 始终在显示名称两边加上引号:
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- 无效。所有内容均括在引号内, 而不只是显示名称:
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- 无效。电子邮件地址周围没有尖括号:
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- 无效。显示名称和左尖括号之间没有空格:
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- 无效。在右引号周围的显示名称和左尖括号之间没有空格。
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a>禁止自动答复您的自定义域, 而无需中断 "发件人:" 策略
<a name="SuppressAutoReply"> </a>

使用新的 From: policy 强制, 您无法再使用: \< \>禁止显示自动答复。相反, 您需要为您的自定义域设置空的 MX 记录。
  
邮件交换器 (MX) 记录是 DNS 中的一条资源记录, 用于标识为您的域接收邮件的邮件服务器。自动答复 (和所有答复) 自然会被隐含, 因为没有任何已发布的地址发送到响应服务器可以向其发送邮件。
  
为自定义域设置空 MX 记录时:
  
- 选择要向其发送不接受 (接收) 电子邮件的邮件的域。例如, 如果您的主域是 contoso.com, 则可以选择 noreply.contoso.com。
    
- 为您的域设置空的 MX 记录。空的 MX 记录包含一个点, 例如:
    
  ```
  noreply.contoso.com IN MX .
  ```

有关发布空 MX 的详细信息, 请参阅[RFC 7505](https://tools.ietf.org/html/rfc7505)。
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a>替代 Office 365 发件人: 地址强制策略
<a name="Override"> </a>

完成新策略的操作后, 您只能通过使用下列方法之一, 对从 Office 365 接收的入站邮件绕过此策略: 
  
- IP 允许列表
    
- Exchange Online 邮件流规则
    
Microsoft 强烈建议您不要覆盖 From: policy 的强制执行。覆盖此策略可能会增加组织暴露给垃圾邮件、网络钓鱼和其他 cybercrimes 的风险。
  
您无法覆盖在 Office 365 中发送的出站邮件的此策略。此外, Outlook.com 不允许覆盖任何种类, 即使支持也是如此。 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>阻止和防止 cybercrimes 在 Office 365 中的其他方法
<a name="OtherProtection"> </a>

若要详细了解如何在 cybercrimes (如网络钓鱼、垃圾邮件、数据泄露和其他威胁) 上加强组织, 请参阅[Office 365 的安全性最佳实践](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3)。
  
## <a name="related-topics"></a>相关主题

[退信消息和 EOP](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

