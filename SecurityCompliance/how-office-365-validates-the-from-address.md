---
title: Office 365 如何验证发件人地址以防止网络钓鱼
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- OWC150
- MET150
ms.assetid: eef8408b-54d3-4d7d-9cf7-ad2af10b2e0e
description: 为了帮助防止网络钓鱼，Office 365 和 Outlook.com 现在需要 RFC 法规遵从性从： 地址。
ms.openlocfilehash: 562e08aa54cb6544beccb6f0e8760735f67b834b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524844"
---
# <a name="how-office-365-validates-the-from-address-to-prevent-phishing"></a>Office 365 如何验证发件人地址以防止网络钓鱼

Office 365 和 Outlook.com 电子邮件帐户接收越来越多的网络钓鱼攻击。网络钓鱼者使用的一种方法是发送邮件的发件人具有值： 不符合[RFC 5322](https://tools.ietf.org/html/rfc5322)的地址。从： 地址也称为 5322.From 地址。为了帮助防止此类型的网络钓鱼，Office 365 和 Outlook.com 需要邮件服务收到包含符合 RFC 从： 解决这篇文章中所述。
  
> [!NOTE]
> 本文中的信息，需要具有基本了解电子邮件地址的一般格式。有关详细信息，请参阅[RFC 5322](https://tools.ietf.org/html/rfc5322) （特别是部分 3.2.3、 3.4、 和 3.4.1）、 [RFC 5321](https://tools.ietf.org/html/rfc5321)，以及[RFC 3696](https://tools.ietf.org/html/rfc3696)。本文是有关策略实施，5322.From 地址。本文不是有关 5321.MailFrom 地址。 
  
很遗憾，还有仍继续发送"合法"电子邮件已缺少某些旧的电子邮件服务器在 Internet 上或从格式不正确： 地址。如果您经常使用这些旧系统的组织中收到电子邮件，鼓励这些组织要更新其邮件服务器，以符合现代安全标准。
  
Microsoft 将开始推出上 2017 年 11 月 9，本文中所述的策略的实施。
  
## <a name="how-office-365-enforces-the-use-of-a-valid-from-address-to-prevent-phishing-attacks"></a>Office 365 如何强制从一个有效的使用： 地址阻止网络钓鱼攻击

Office 365 正在更改的方式，它强制使用 From： 为了更好的接收的消息中的地址保护您从网络钓鱼攻击。本文内容：
  
- [所有邮件都必须都包括从有效： 地址](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [所有邮件都必须都包括从有效： 地址](how-office-365-validates-the-from-address.md#MustIncludeFromAddress)
    
- [从的格式： 如果不包括的显示名称的地址](how-office-365-validates-the-from-address.md#FormatNoDisplayName)
    
- [从的格式： 地址如果包括的显示名称](how-office-365-validates-the-from-address.md#FormatDisplayName)
    
- [有效和从无效的其他示例： 地址](how-office-365-validates-the-from-address.md#Examples)
    
- [禁止对您的自定义域的自动答复，而不会破坏 From： 策略](how-office-365-validates-the-from-address.md#SuppressAutoReply)
    
- [Office 365 中重写： 地址实施策略](how-office-365-validates-the-from-address.md#Override)
    
- [防止和抵御犯罪 Office 365 中的其他方法](how-office-365-validates-the-from-address.md#OtherProtection)
    
代表另一个用户发送不受此更改的详细信息，阅读 Terry Zink 博客"[这意味着什么呢时我们统称其发件人电子邮件？](https://blogs.msdn.microsoft.com/tzink/2017/06/22/what-do-we-mean-when-we-refer-to-the-sender-of-an-email/)"。
  
### <a name="all-messages-must-include-a-valid-from-address"></a>所有邮件都必须都包括从有效： 地址
<a name="MustIncludeFromAddress"> </a>

某些自动的邮件不包括 From： 地址发送时。在过去，Office 365 或 Outlook.com 时收到消息，而不从： 地址，该服务添加从下面的默认： 地址以使其可交付结果的消息：
  
```
From: <>
```

启动 2017 年 11 月 9，Office 365 将推出更改到其数据中心和邮件服务器，其中将强制实施新规则其中 From 的情况下消息： 地址将无法再接受通过 Office 365 或 Outlook.com。而是接收的 Office 365 的所有邮件必须已经都包含有效从： 地址。否则，消息将发送到 Outlook.com 和 Office 365 中的垃圾邮件或已删除邮件文件夹。 
  
### <a name="syntax-overview-valid-format-for-the-from-address-for-office-365"></a>语法概述： 发件人的有效格式： Office 365 的地址
<a name="SyntaxOverviewFromAddress"> </a>

从值的格式： 详细跨多个 Rfc 定义地址。有许多变体寻址和内容可能被视为有效或无效。若要保留简单，Microsoft 建议您使用以下格式和定义：
  
```
From: "displayname " <emailaddress >
```

其中：
  
- （可选） *displayname*是一个短语描述的所有者的电子邮件地址。例如，这可能是邮箱的一个更为用户友好名称，以描述发件人。使用的显示名称是可选的。但是，如果您选择要使用的显示名称，Microsoft 建议，则始终将它引号括起来如下所示。 
    
- （必需） *emailaddress*组成： 
    
  ```
  local-part @domain
  ```

    其中：
    
  - （必需） *本地部分*是一个字符串，标识与地址关联的邮箱。这是唯一域中。通常，邮箱所有者的用户名或 GUID 用于为值本地部分。 
    
  - （必需） *域*是承载本地一部分的电子邮件地址所标识的邮箱的邮件服务器的完全限定的域名 (FQDN)。 
    
### <a name="format-of-the-from-address-if-you-dont-include-a-display-name"></a>从的格式： 如果不包括的显示名称的地址
<a name="FormatNoDisplayName"> </a>

从格式正确 A： 不包括的显示名称的地址包括只有单个电子邮件地址使用或不尖括号。Microsoft 建议您不要用空格分隔尖括号。此外，不包括任何内容后的电子邮件地址。
  
下面的示例是有效的：
  
```
From: sender@contoso.com
```

```
From: <sender@contoso.com>
```

下面的示例是有效的但不是建议包含尖括号和电子邮件地址之间的空格，因此：
  
```
From: < sender@contoso.com >
```

下面的示例无效，因为它包含文本后的电子邮件地址：
  
```
From: "Office 365" <sender@contoso.com> (Sent by a process)
```

### <a name="format-of-the-from-address-if-you-include-a-display-name"></a>从的格式： 地址如果包括的显示名称
<a name="FormatDisplayName"> </a>

有关从： 包括的显示名称的值的地址，则适用以下规则：
  
- 如果发件人地址中包含的显示名称，并显示名称包括逗号，然后的显示名称必须括在引号内。例如：
    
    下面的示例是有效的：
    
  ```
  From: "Sender, Example" <sender.example@contoso.com>
  ```

    下面的示例无效：
    
  ```
  From: Sender, Example <sender.example@contoso.com>
  ```

    不在引号内封闭的显示名称，如果该显示名称中包含逗号根据 RFC 5322 无效。
    
    作为最佳实践，无论的显示名称周围的 put 的引号是否存在为逗号中的显示名称。
    
- 如果发件人地址中包含的显示名称，然后尖括号必须括起来的电子邮件地址。
    
    作为最佳实践，Microsoft 强烈建议您插入间距的显示名称和电子邮件地址。
    
### <a name="additional-examples-of-valid-and-invalid-from-addresses"></a>有效和从无效的其他示例： 地址
<a name="Examples"> </a>

- 有效：
    
  ```
  From: "Office 365" <sender@contoso.com>
  ```

- 无效。使用尖括号不包含的电子邮件地址：
    
  ```
  From: Office 365 sender@contoso.com
  ```

- 有效的但不是建议这样做。显示名称不在引号中。作为最佳实践，始终加引号的显示名称：
    
  ```
  From: Office 365 <sender@contoso.com>
  ```

- 无效。所有内容括在引号内，而不仅仅是的显示名称：
    
  ```
  From: "Office 365 <sender@contoso.com>"
  ```

- 无效。有无尖括号周围的电子邮件地址：
    
  ```
  From: "Office 365 <sender@contoso.com>" sender@contoso.com
  ```

- 无效。没有之间的显示名称和左的尖括号空间：
    
  ```
  From: Office 365<sender@contoso.com>
  ```

- 无效。结束 quotation mark 周围的显示名称和左的尖括号之间没有空间。
    
  ```
  From: "Office 365"<sender@contoso.com>
  ```

### <a name="suppress-auto-replies-to-your-custom-domain-without-breaking-the-from-policy"></a>禁止对您的自定义域的自动答复，而不会破坏 From： 策略
<a name="SuppressAutoReply"> </a>

与从新： 策略实施，您不能再使用从： \< \>禁止自动答复。相反，您需要设置您的自定义域的 null MX 记录。
  
邮件交换器 (MX) 记录是标识接收为您的域的邮件的邮件服务器的 DNS a 资源记录。因为没有响应的服务器可以向其发送消息的已发布地址自然禁止自动答复 （和所有回复）。
  
当您设置为空的 MX 记录为您的自定义域：
  
- 选择一个域从其发送消息的不接受 （接收） 电子邮件。例如，如果您的主要域是 contoso.com，您可能选择 noreply.contoso.com。
    
- 设置为您的域为空的 MX 记录。空的 MX 记录包含的一个点，例如：
    
  ```
  noreply.contoso.com IN MX .
  ```

关于发布空的 MX 的详细信息，请参阅[RFC 7505](https://tools.ietf.org/html/rfc7505)。
  
### <a name="overriding-the-office-365-from-address-enforcement-policy"></a>Office 365 中重写： 地址实施策略
<a name="Override"> </a>

利用新策略的滚动完成后，仅可以跳过此策略使用下列方法之一接收来自 Office 365 的入站邮件： 
  
- IP 允许列表
    
- Exchange Online 邮件流规则
    
Microsoft 强烈建议针对替代 From 实施： 策略。覆盖此策略可以增加暴露垃圾邮件和网络钓鱼，其他犯罪贵组织的风险。
  
不能重写为 Office 365 中发送的出站邮件此策略。此外，Outlook.com 将不允许覆盖任何种类的即使通过支持。 
  
### <a name="other-ways-to-prevent-and-protect-against-cybercrimes-in-office-365"></a>防止和抵御犯罪 Office 365 中的其他方法
<a name="OtherProtection"> </a>

有关如何可以增强您的组织免受犯罪网络钓鱼等的详细信息，发送垃圾邮件、 数据泄露和其他威胁，请参阅[Office 365 的安全性最佳实践](https://support.office.com/article/9295e396-e53d-49b9-ae9b-0b5828cdedc3)。
  
## <a name="related-topics"></a>相关主题

[退信消息和 EOP](https://technet.microsoft.com/en-us/library/dn499795%28v=exchg.150%29.aspx)
  

