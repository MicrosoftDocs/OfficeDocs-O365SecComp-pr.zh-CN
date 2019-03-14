---
title: Office 365 中的防欺骗保护
ms.author: tracyp
author: MSFTtracyp
manager: laurawi
ms.date: 3/6/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: 本文介绍了 Office 365 如何缓解使用伪造的发件人域 (即欺骗的域) 的网络钓鱼攻击。 这是通过分析邮件并阻止可通过使用标准电子邮件身份验证方法 (也不是其他发件人信誉技术) 进行身份验证的邮件来完成的。 此更改已实现, 以减少对 Office 365 中的组织公开的网络钓鱼攻击的数量。
ms.openlocfilehash: 377bc75e7538dacab1180045ddfdeb1a2ac32a65
ms.sourcegitcommit: 5eb664b6ecef94aef4018a75684ee4ae66c486bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2019
ms.locfileid: "30492871"
---
# <a name="anti-spoofing-protection-in-office-365"></a>Office 365 中的防欺骗保护

本文介绍了 Office 365 如何缓解使用伪造的发件人域 (即欺骗的域) 的网络钓鱼攻击。 它通过分析邮件并阻止无法使用标准电子邮件身份验证方法 (也不能通过其他发件人信誉技术) 进行身份验证的邮件来实现这一点。 此更改已实现, 以减少对 Office 365 中的组织公开的网络钓鱼攻击的数量。
  
此外, 本文还介绍了进行此更改的原因、客户如何准备进行此更改、如何查看将受到影响的邮件、如何对邮件进行报告、如何减少误报, 以及 Microsoft 的发件人如何为此做好准备更改.
  
Microsoft 的反欺骗技术最初部署到其组织中的 office 365 企业版 E5 订阅或购买了 office 365 高级威胁防护 (ATP) 附加的订阅。 从10月起, 2018 我们扩展了对同时拥有 Exchange Online protection (EOP) 的组织的保护。 此外, 由于所有筛选器彼此之间都了解, Outlook.com 用户可能也会受到影响。
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a>如何在网络钓鱼攻击中使用欺骗

在保护其用户的过程中, Microsoft 会严肃对待网络钓鱼威胁。 垃圾邮件制造者和仿冒者通常使用的一种技术是哄骗, 这就是当发件人被伪造时, 消息显示为来自于实际来源以外的某人或其他地方。 此技术通常用在旨在获取用户凭据的网络钓鱼活动中。 Microsoft 的反欺骗技术专门检查 "发件人: 头" 的伪造, 即在电子邮件客户端 (如 Outlook) 中显示的。 当 Microsoft 对 "发件人" 标头具有欺骗性的可信度时, 它会将邮件标识为欺骗邮件。
  
哄骗邮件对真实用户有两个负面影响:
  
### <a name="1-spoofed-messages-deceive-users"></a>1. 欺骗性邮件欺骗用户
  
首先, 欺骗性邮件可能会欺骗用户单击链接并放弃其凭据、下载恶意软件或回复包含敏感内容的邮件 (后者称为业务电子邮件泄露)。 例如, 以下是具有 msoutlook94@service.outlook.com 欺骗发件人的网络钓鱼邮件:
  
![网络钓鱼邮件模拟 service.outlook.com](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
上面实际上并不是来自 service.outlook.com, 而是由 phisher 欺骗以使其看起来像是一样。 它试图欺骗用户单击邮件中的链接。
  
下一个示例是哄骗 contoso.com:
  
![网络钓鱼邮件-业务电子邮件受损](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
邮件看起来合法, 但实际上是欺骗。 此网络钓鱼邮件是一种商业电子邮件泄露, 它是网络钓鱼的子类别。

### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2. 用户混淆了假冒邮件的真实邮件
  
其次, 欺骗邮件为了解网络钓鱼邮件的用户带来不确定性, 但不能辨别实际邮件和欺骗邮件之间的区别。 例如, 以下是 Microsoft 安全帐户电子邮件地址中的实际密码重置示例:
  
![Microsoft 合法密码重置](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
上述邮件确实来自 Microsoft, 但同时也用于获取网络钓鱼邮件, 这些邮件可能会欺骗用户单击链接并放弃其凭据、下载恶意软件或回复包含敏感内容的邮件。 由于很难区分实际密码重置和伪造密码的区别, 许多用户会忽略这些邮件, 将它们报告为垃圾邮件, 或者不必要地将邮件作为错过的网络钓鱼骗局报告给 Microsoft。

为了防止欺骗, 电子邮件筛选行业制定了电子邮件身份验证协议, 如[SPF](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)、 [DKIM](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)和[DMARC](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)。 DMARC 阻止电子邮件的发件人 (在其电子邮件客户端中看到的是用户在其电子邮件客户端中看到的) (在上述示例中, 为 service.outlook.com、outlook.com 和 accountprotection.microsoft.com) 以及通过了已通过 SPF 或 DKIM 的域。 也就是说, 用户看到的域已经过身份验证, 因此是不欺骗的。 有关更全面的讨论, 请参阅本文后面的 "*了解为什么电子邮件身份验证并非总是足以阻止欺骗"* 一节。
  
但是, 问题在于电子邮件身份验证记录是可选的, 而不是必需的。 因此, 当保护具有类似 microsoft.com 和 skype.com 等强身份验证策略的域时, 不会受到欺骗的攻击、发布不够安全的身份验证策略或根本没有策略的域都是欺骗目标。从2018年3月起, 在财富500中仅有 9% 的公司将发布强大的电子邮件身份验证策略。 其余 91% 可能被 phisher 欺骗, 除非电子邮件筛选器使用另一个策略检测它, 否则可能会将其传递给最终用户并欺骗他们:
  
![《财富500》公司的 DMARC 策略](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
发布强电子邮件身份验证策略的不在财富500中的中小型公司的比例较小, 并且对北美和西欧范围之外的域仍然较小。
  
这是一个很大的问题, 因为企业可能不知道电子邮件身份验证的工作方式, 而仿冒确实知道并充分利用缺少的电子邮件。
  
有关设置 SPF、DKIM 和 DMARC 的信息, 请参阅本文档后面的 "*Office 365 的客户*" 一节。 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a>通过隐式电子邮件身份验证停止欺骗

由于网络钓鱼和 spear 的网络钓鱼是这样一个问题, 并且由于强大的电子邮件身份验证策略的采用有限, Microsoft 将继续投资保护其客户的功能。 因此, microsoft 将继续进行*隐式电子邮件身份验证*-如果域不进行身份验证, 则 microsoft 会将其视为已发布的电子邮件身份验证记录, 并在未通过的情况下进行相应处理。 
  
为实现此目的, Microsoft 已为常规电子邮件身份验证 (包括发件人信誉、发件人/收件人历史记录、行为分析和其他高级技术) 构建了大量扩展。 从不发布电子邮件身份验证的域发送的邮件将被标记为欺骗, 除非它包含其他指示它是合法的信号。
  
通过执行此操作, 最终用户可以确信发送给他们的电子邮件未被欺骗, 发件人可以确信没有人模拟其域, 而 Office 365 的客户可以提供更好的保护, 如模拟保护。
  
若要查看 Microsoft 的常规通知, 请参阅[网络钓鱼的海洋第2部分-Office 365 中增强的反欺骗](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)。
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>确定邮件已分类为欺骗邮件

### <a name="composite-authentication"></a>复合身份验证

虽然 SPF、DKIM 和 DMARC 本身都很有用, 但在邮件没有显式身份验证记录的情况下, 它们不会传达足够的身份验证状态。 因此, Microsoft 已经开发了将多个信号组合为单个称为复合身份验证的值的算法, 或将 compauth 用于短时间。 Office 365 中的客户具有在邮件头的*身份验证结果*标头中标记的 compauth 值。 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**CompAuth 结果**|**说明**|
|:-----|:-----|
|失败|消息无法显式身份验证 (在 dns 中显式发送域已发布的记录) 或隐式身份验证 (发送域在 dns 中未发布记录, 因此 Office 365 将结果插上为已发布的记录一样)。|
|超出|邮件已通过显式身份验证 (通过 DMARC 传递的邮件, 或[最佳推测传递的 DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)) 或具有高可信度的隐式身份验证 (发送域不会发布电子邮件身份验证记录, 但 Office 365 具有强大的后端信号来指明邮件可能是合法的。|
|softpass|邮件已通过低到中等可信度的隐式身份验证 (发送域不会发布电子邮件身份验证, 但 Office 365 有后端信号指示邮件是合法的, 但信号强度较弱)。|
|无|邮件未进行身份验证 (或身份验证但未对齐), 但由于发件人信誉或其他因素而未应用复合身份验证。|
   
|||
|:-----|:-----|
|**原因**|**说明**|
|0xx|邮件的复合身份验证失败。<br/>**000**表示邮件失败, DMARC 操作为 "拒绝" 或 "隔离"。  <br/>**001**表示邮件的隐式电子邮件身份验证失败。 这意味着发送域未发布电子邮件身份验证记录, 或者如果用户执行了此操作, 则它们具有较弱的失败策略 (SPF soft fail 或中立性, p = none 的 DMARC 策略)。  <br/>**002**表示组织具有对发件人/域对 (明确禁止发送欺骗电子邮件) 的策略, 管理员手动设置此设置。  <br/>**010**表示邮件失败, DMARC 操作为 "拒绝或隔离", 并且发送域是组织的接受域之一 (这是自到自助或组织内电子欺骗的一部分)。  <br/>**011**表示邮件的隐式电子邮件身份验证失败, 并且发送域是组织的接受域之一 (这是自到自助或组织内电子欺骗的一部分)。|
|所有其他代码 (1xx、2xx、3xx、4xx、5xx)|对应于邮件通过隐式身份验证传递的原因的各种内部代码, 或者不进行身份验证但未应用任何操作。|
   
通过查看邮件的邮件头, 管理员甚至最终用户可以确定 Office 365 如何达到最终的结果, 即发件人可能被欺骗。
  
### <a name="differentiating-between-different-types-of-spoofing"></a>区分不同类型的欺骗

Microsoft 在两种不同类型的欺骗邮件中进行区分:
  
 **组织内欺骗**
  
如果发件人: address 中的域与收件人域相同 (当收件人域是组织的[接受域](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)之一时), 则会出现这种情况。或者, 当 "发件人:" 地址中的域是同一组织的一部分时。
  
例如, 下面的发件人和收件人来自同一个域 (contoso.com)。 在电子邮件地址中插入空格, 以防止垃圾邮件程序在此页上收集):
  
发件人: 发件人 @ contoso.com
  
收件人: 收件人 @ contoso.com
  
以下是发件人和收件人域与组织域 (fabrikam.com) 的协调:
  
发件人: 发件人 @ foo.fabrikam.com
  
收件人: 收件人 @ bar.fabrikam.com
  
以下发件人和收件人域不同 (microsoft.com 和 bing.com), 但它们属于同一组织 (即, 这两个都是组织的接受域的一部分):
  
发件人: 发件人 @ microsoft.com
  
收件人: 收件人 @ bing.com
  
在组织内欺骗失败的邮件包含标头中的以下值:
  
X-Forefront-反垃圾邮件报告: .。。CAT: SPM/HSPM/PHSH; .。。SFTY: 9.11
  
CAT 是邮件的类别, 通常被标记为 SPM (垃圾邮件), 但偶尔可能是 HSPM (高可信度垃圾邮件) 或网络钓鱼 (网络钓鱼), 具体取决于邮件中出现的其他类型的模式。
  
SFTY 是邮件的安全级别, 第一个数字 (9) 表示邮件是网络钓鱼, 而点 (11) 后的第二组数字表示它是组织内欺骗。
  
组织内欺骗的复合身份验证没有特定的原因代码, 将在 2018 (尚未定义时间线) 中稍后对其进行标记。
  
 **跨域欺骗**
  
当发件人: address 中的发送域是接收组织的外部域时, 会发生这种情况。 由于跨域欺骗导致复合身份验证失败的邮件包含标头中的以下值:
  
身份验证-结果: .。。 compauth = 失败原因 = 000/001
  
X-Forefront-反垃圾邮件报告: .。。分类程序: 欺骗; .。。SFTY: 9.22
  
在这两种情况下, 邮件中都会标记以下红色安全提示, 或将自定义为收件人邮箱语言的等效项:
  
![红色安全提示-欺诈检测](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
仅通过查看 "发件人:" 地址和了解收件人电子邮件的内容, 或通过检查电子邮件头来区分您可以区分组织内部和跨域欺骗。
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>Office 365 的客户如何为新的反欺骗保护进行自我准备

### <a name="information-for-administrators"></a>为管理员提供的信息

作为 Office 365 中的组织的管理员, 您应了解几个重要的信息部分。
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>了解为什么电子邮件身份验证始终不足以阻止欺骗

新的反欺骗保护依赖于电子邮件身份验证 (SPF、DKIM 和 DMARC), 而不是将邮件标记为欺骗。 一个常见的示例是发送域中从未发布的 SPF 记录。 如果没有 SPF 记录或未正确设置它们, 则发送的邮件将被标记为 "欺骗", 除非 Microsoft 具有表明该邮件是合法邮件的后端智能。
  
例如, 在部署反欺骗之前, 可能会出现一条消息, 看起来没有 SPF 记录, 没有 DKIM 记录, 并且没有 DMARC 记录: 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
反欺骗之后, 如果您有 Office 365 企业版 E5、EOP 或 ATP, compauth 值将被标记:
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

如果 example.com 通过设置 spf 记录而不是 DKIM 记录进行修复, 则此操作将传递复合身份验证, 因为在 From: address: 中传递了与域对齐的 SPF 的域。 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

或者, 如果他们设置的是 DKIM 记录, 而不是 SPF 记录, 这也会通过复合身份验证, 因为 DKIM 签名中的域与 "发件人: address:" 中的域相一致。 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

但是, phisher 还可以设置 SPF 和 DKIM, 并使用其自己的域对邮件进行签名, 但在 "发件人:" 地址中指定不同的域。 SPF 和 DKIM 都不要求域与 From: address 中的域对齐, 因此, 除非 example.com 发布 DMARC 记录, 否则不会将其标记为使用 DMARC 的欺骗: 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

在电子邮件客户端 (outlook、web 上的 outlook 或任何其他电子邮件客户端) 中, 仅显示 "发件人: 域", 而不是 SPF 或 DKIM 中的域, 这会误导用户认为邮件来自 example.com, 但实际上来自 maliciousDomain.com.
  
![经过身份验证的邮件, 但发件人: 域与传递的 SPF 或 DKIM 不一致](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
出于此原因, Office 365 要求 "发件人: 地址" 中的域与 SPF 或 DKIM 签名中的域对齐, 如果不是, 则包含其他一些内部信号, 指示邮件是合法的。 否则, 邮件将为 compauth 失败。 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

因此, Office 365 反欺骗可防止不进行身份验证的域, 并针对设置身份验证但不与 "发件人: 地址" 中的域不匹配的域 (即, "发件人" 地址中的域不匹配) 的域, 这是邮件的发件人。 这既适用于组织外部的域, 也是组织中的域。
  
因此, 如果您收到一条消息, 表明复合身份验证失败, 并且被标记为欺骗, 即使邮件已通过 spf 和 DKIM, 也是因为传递的 spf 和 DKIM 的域与 From: address 中的域不一致。
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>了解如何处理欺骗性电子邮件的更改

目前, 对于 Office 365 中的所有组织, 通过拒绝或隔离策略将 DMARC 失败的电子邮件将被标记为垃圾邮件, 并且通常会采取高可信度垃圾邮件操作 (具体取决于其他垃圾邮件操作), 也可以是常规垃圾邮件操作 (具体取决于其他垃圾邮件)。规则首先将其标识为垃圾邮件)。 组织内部欺骗检测采用常规的垃圾邮件操作。 此行为不需要启用, 也不会被禁用。
  
但是, 对于跨域欺骗邮件, 在此更改之前, 它们将通过常规垃圾邮件、网络钓鱼和恶意软件检查, 如果筛选器的其他部分识别为可疑, 则应分别将其标记为垃圾邮件、网络钓鱼或恶意软件。 通过新的跨域欺骗保护, 默认情况下, 任何无法通过身份验证的邮件都将采取反欺骗性\>反欺骗策略中定义的操作。 如果未定义, 则会将其移动到 "用户垃圾邮件" 文件夹。 在某些情况下, 更可疑的邮件也会添加到邮件中的红色安全提示。
  
这可能会导致一些以前标记为垃圾邮件的邮件仍被标记为垃圾邮件, 但现在也会显示红色安全提示;在其他情况下, 以前标记为非垃圾邮件的邮件会开始添加红色安全提示, 并将其标记为垃圾邮件 (CAT: 欺骗)。 在其他情况下, 将所有垃圾邮件和网络钓鱼转到隔离的客户现在会看到它们转到 "垃圾邮件" 文件夹 (此行为可能会更改, 请参阅[更改反欺骗设置](#changing-your-anti-spoofing-settings))。
  
有多种不同的方法可欺骗邮件 (请参阅本文前面的[不同类型的欺骗之间的区分](#differentiating-between-different-types-of-spoofing)), 但从3月2018日起, Office 365 处理这些邮件的方式还不是统一的。 下表是一个快速摘要, 其中包含跨域欺骗保护的新行为: 
  
|**哄骗类型**|**类别**|**是否添加安全提示？**|**应用于**|
|:-----|:-----|:-----|:-----|
|DMARC 失败 (隔离或拒绝)  <br/> |HSPM (默认值), 也可以是 SPM 或 PHSH  <br/> |否 (尚未)  <br/> |所有 Office 365 客户, Outlook.com  <br/> |
|自到自我  <br/> |SPM  <br/> |是  <br/> |所有 Office 365 组织, Outlook.com  <br/> |
|跨域  <br/> |哄骗  <br/> |是  <br/> |Office 365 高级威胁防护和 E5 客户  <br/> |

### <a name="changing-your-anti-spoofing-settings"></a>更改反欺骗设置

若要创建或更新 (跨域) 的反欺骗设置, 请导航到安全\> \> &amp;合规中心中 "威胁管理策略" 选项卡下的 "反钓鱼" 反欺骗设置。 如果从未创建任何反网络钓鱼设置, 您将需要创建一个:
  
![反网络钓鱼-创建新策略](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
如果您已经创建了一个, 可以选择它来修改它:
  
![反网络钓鱼-修改现有策略](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
选择您刚刚创建的策略, 并按照[详细了解欺骗情报](learn-about-spoof-intelligence.md)中所述的步骤进行操作。
  
![启用或禁用反欺骗](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![启用或禁用反欺骗安全提示](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
若要使用 PowerShell 创建新策略, 请执行以下操作: 
  
```powershell
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: The name should not exclude 64 characters, including spaces.
# If it does, you will need to pick a smaller name.
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy $name -RecipientDomainIs $domains
```

然后, 您可以按照[AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps)中的文档修改使用 PowerShell 的反网络钓鱼策略参数。 您可以将 $name 指定为参数:
  
```powershell
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

稍后在2018中, 而不是创建默认策略时, 将为您创建一个范围限定于组织中的所有收件人的用户, 以便您无需手动指定它 (下图中的屏幕截图将在最终实施之前更改)。
  
![反网络钓鱼的默认策略](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
与所创建的策略不同, 您不能删除默认策略, 也不能修改其优先级, 也不能选择将其作用域的用户、域或组。
  
![反网络钓鱼默认策略详细信息](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
使用 PowerShell 设置默认保护的具体步骤:
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishPolicy | ? {$_.IsDefault -eq $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

如果你在 Office 365 前端使用其他邮件服务器或服务器, 应仅禁用反欺骗保护 (有关详细信息, 请参阅合法方案以禁用反欺骗)。
  
```powershell
$defaultAntiphishPolicy = Get-AntiphishiPolicy | ? {$_.IsDefault $true}
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> 如果您的电子邮件路径中的第一个跃点是 Office 365, 并且您要将过多的合法电子邮件标记为欺骗, 应首先设置允许向您的域发送欺骗电子邮件的发件人 (请参阅 *"管理正在发送的合法发件人" 一节。nauthenticated email "* )。 如果仍收到过多误报 (即被标记为欺骗的合法邮件), 我们建议您不要完全禁用反欺骗保护。 相反, 我们建议选择 "基本" 而不是 "高" 保护。 与向组织公开欺骗性的电子邮件相比, 更好的方法是使用误报, 这可能会导致长期产生显著增加的成本。

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>管理发送未经身份验证的电子邮件的合法发件人

Office 365 跟踪向您的组织发送未经身份验证的电子邮件的用户。 如果服务认为发件人不合法, 它会将其标记为*compauth*失败。 这将归为欺骗, 尽管这取决于应用于邮件的反欺骗策略。
  
但是, 作为管理员, 您可以指定允许哪些发件人发送欺骗电子邮件, 替代 Office 365 的决定。
  
**方法 1-如果你的组织拥有域, 请设置电子邮件身份验证**
  
此方法可用于在您拥有或与多个租户进行交互的情况下解析组织内欺骗和跨域欺骗。 它还有助于解析在 Office 365 中发送给其他客户的跨域欺骗, 以及其他提供商托管的第三方。
  
有关更多详细信息, 请参阅[Office 365 的客户](#customers-of-office-365)。

**方法 2-使用欺骗智能配置未经身份验证的电子邮件的允许发件人**
  
您还可以使用[欺骗智能](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf), 以允许发件人将未经过身份验证的邮件传输到您的组织。 
  
对于外部域, 欺骗用户是 "发件人" 地址中的域, 而 "发送" 基础结构是发送 IP 地址 (分成/24 个 CIDR 范围) 或 PTR 记录的组织域 (在下面的屏幕截图中, 发送 IP 可能是131.107.18.4 其 PTR 记录是 outbound.mail.protection.outlook.com 的, 这将显示为发送基础结构的 outlook.com。
  
若要允许此发件人发送未经身份验证的电子邮件, 请将**No**改为**是**。
  
![设置允许发件人的反欺骗](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
您还可以使用 PowerShell 来允许特定发件人欺骗您的域:
  
```powershell
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```powershell
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![从 Powershell 获取欺骗发件人](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
在上图中, 添加了其他换行符以使此屏幕截图合适。 通常情况下, 所有值都将显示在单行中。
  
编辑文件并查找与 outlook.com 和 bing.com 相对应的行, 并将 AllowedToSpoof 条目从 "否" 更改为 "是":
  
![在 Powershell 中将欺骗允许设置为 "是"](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
保存该文件, 然后运行:
  
```powershell
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

这现在将允许 bing.com 从 outlook.com 发送未经身份\*验证的电子邮件。

**方法 3-为发件人/收件人对创建允许条目**
  
您还可以选择绕过特定发件人的所有垃圾邮件筛选。 有关更多详细信息, 请参阅[如何在 Office 365 中安全地将发件人添加到允许列表](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/)。
  
如果使用此方法, 它将跳过垃圾邮件和某些网络钓鱼筛选, 但不会对恶意软件进行筛选。
  
**方法 4-联系发件人并要求他们设置电子邮件身份验证**
  
由于垃圾邮件和网络钓鱼问题, Microsoft 建议所有发件人设置电子邮件身份验证。 如果您知道发送域的管理员, 请与他们联系并请求他们设置电子邮件身份验证记录, 这样您就不必添加任何替代。 有关详细信息, 请参阅本文后面的[非 Office 365 客户的域管理员](#administrators-of-domains-that-are-not-office-365-customers)。 
  
有时, 随着时间的推移, 如果越来越多的电子邮件筛选器启动 junking 甚至拒绝他们的电子邮件, 可能会很难进行身份验证, 这将导致用户设置正确的记录以确保更好地进行传递。
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>查看标记为欺骗的邮件的报告

启用反欺骗策略后, 您可以使用威胁情报获取有关标记为网络钓鱼的邮件数的数字。 为此, 请进入 "威胁管理&amp; \>资源管理器" 下的 "安全合规中心 (SCC)", 将视图设置为网络钓鱼, 并按发件人域或保护状态分组:
  
![查看标记为网络钓鱼的邮件数](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
您可以与各种报告进行交互, 以查看标记为网络钓鱼的邮件数, 包括标记为欺骗的邮件。 若要了解详细信息, 请参阅[Office 365 威胁智能入门入门](get-started-with-ti.md)。
  
您还不能拆分那些由于哄骗而被标记的邮件, 而不是其他类型的网络钓鱼 (常规网络钓鱼、域或用户模拟等)。 但是, 稍后你将能够通过安全&amp;合规中心执行此操作。 执行此操作后, 您可以使用此报告作为一种开始位置, 用于识别可能是合法的发送域, 因为身份验证失败而被标记为欺骗。
  
下面的屏幕截图是此数据外观的建议, 但在发布后可能会发生变化:
  
![按检测类型查看网络钓鱼报告](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
对于非 ATP 和 E5 客户, 这些报告将在后面的威胁防护状态 (TPS) 报告中可用, 但将延迟至少24小时。 此页面将在集成到安全&amp;合规性中心时进行更新。
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>预测将把多少封邮件标记为欺骗

一旦 Office 365 更新了其设置以使您能够关闭反欺骗强制实施, 或者在基本或高强制实施的情况下, 您就可以查看邮件处置在各种设置上的更改方式。 也就是说, 如果反欺骗已关闭, 你将能够查看将被检测为欺骗的邮件的数量 (如果你启用了 "基本");或者, 如果它是基本的, 您将能够查看将多少封邮件检测为欺骗邮件 (如果您将其设为 "高")。
  
此功能目前正在开发中。 由于定义了更多详细信息, 此页面将随安全与合规中心的屏幕截图以及 PowerShell 示例一起进行更新。
  
![启用反欺骗的 "假设" 报告](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![允许欺骗发件人的可能的 UX](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a>了解如何组合垃圾邮件、网络钓鱼和高级网络钓鱼检测

使用 Exchange Online (带有或不带 ATP) 的组织可以指定在服务将邮件标识为恶意软件、垃圾邮件、高可信度垃圾邮件、网络钓鱼和批量时要采取的操作。 对于 atp 客户的 atp 反网络钓鱼策略和 EOP 客户的反网络钓鱼策略, 以及邮件可能遇到多个检测类型 (例如, 恶意软件、网络钓鱼和用户模拟) 的情况下, 可能会对其产生一些困惑。策略适用。
  
通常情况下, 应用于邮件的策略在 CAT (Category) 属性中的 X-Forefront-反垃圾邮件报告标头中进行标识。
  
|**Priority**|**策略**|**类别**|**在什么情况下托管？**|**应用于**|
|:-----|:-----|:-----|:-----|:-----|
|1  <br/> |受到  <br/> |MALW  <br/> |[恶意软件策略](configure-anti-malware-policies.md) <br/> |所有组织  <br/> |
|双面  <br/> |骗术  <br/> |PHSH  <br/> |[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md) <br/> |所有组织  <br/> |
|第三章  <br/> |可信度高的垃圾邮件  <br/> |HSPM  <br/> |[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md) <br/> |所有组织  <br/> |
|4  <br/> |网络钓鱼  <br/> |哄骗  <br/> |[反网络钓鱼策略](https://go.microsoft.com/fwlink/?linkid=864553)、[欺骗性智能](learn-about-spoof-intelligence.md) <br/> |所有组织  <br/> |
|5  <br/> |垃圾邮件  <br/> |SPM  <br/> |[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md) <br/> |所有组织  <br/> |
|型  <br/> |群发  <br/> |群发  <br/> |[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md) <br/> |所有组织  <br/> |
|步  <br/> |域模拟  <br/> |DIMP  <br/> |[设置 Office 365 ATP 反网络钓鱼和反网络钓鱼策略](set-up-anti-phishing-policies.md) <br/> |仅含 ATP 的组织  <br/> |
|utf-8  <br/> |用户模拟  <br/> |UIMP  <br/> |[设置 Office 365 ATP 反网络钓鱼和反网络钓鱼策略](set-up-anti-phishing-policies.md) <br/> |仅含 ATP 的组织 <br/> |

如果有多个不同的反网络钓鱼策略, 则会应用最高优先级的策略。 例如, 假设您有两个策略:

|**策略**|**Priority**|**用户/域模拟**|**反欺骗**|
|:-----|:-----|:-----|:-----|
|A  <br/> |1  <br/> |位置  <br/> |关  <br/> |
|B  <br/> |双面  <br/> |关  <br/> |位置  <br/> |

如果邮件传入且被标识为欺骗和用户模拟, 并且同一组用户的范围限定为策略 a 和策略 B, 则邮件将被视为欺骗邮件, 但由于反欺骗已关闭, 因此不会应用任何操作, 并且欺骗以高于用户模拟的优先级 (4) 运行 (8)。
  
若要应用其他类型的网络钓鱼策略, 您将需要调整应用不同策略的用户的设置。
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>禁用反欺骗的合法方案

反欺骗可更好地保护客户免受网络钓鱼攻击, 因此强烈建议不要禁用反欺骗保护。 通过禁用它, 可以解决某些短期误报, 但长期会暴露给更多风险。 在发件人端上设置身份验证或在网络钓鱼策略中进行调整的成本通常是一次性事件, 或者只需要最少的定期维护。 但是, 从数据泄露的网络钓鱼攻击中恢复的成本, 或资产受到危害的成本高得多。
  
因此, 最好通过反欺骗误报, 而不是禁用反欺骗保护。
  
但是, 有一个合法方案应禁用反欺骗, 这就是邮件路由中存在其他邮件筛选产品, 而 Office 365 不是电子邮件路径中的第一个跃点:
  
![客户 MX 记录未指向 Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
其他服务器可以是 Exchange 本地邮件服务器、邮件筛选设备 (如 Ironport) 或其他云托管服务。
  
如果收件人域的 MX 记录未指向 Office 365, 则无需禁用反欺骗, 因为 Office 365 会查看您的接收域的 MX 记录, 如果它指向其他服务, 则禁止反欺骗。 如果您不知道您的域在前面是否有另一台服务器, 则可以使用 mx 工具箱等网站来查找 mx 记录。 它可能会说出如下所示的内容:
  
![MX 记录指示域未指向 Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
此域具有不指向 office 365 的 MX 记录, 因此 Office 365 将不会应用反欺骗强制实施。
  
但是, 如果收件人域的 MX 记录指向 office ** 365, 即使 office 365 前面有另一个服务, 也应禁用反欺骗。 最常见的示例是使用收件人重写: 
  
![收件人重写的路由关系图](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
域 contoso .com 的 mx 记录指向内部部署服务器, 而域 @office365 的 mx 记录指向 Office 365, 因为它包含\*protection.outlook.com 或\*eo.outlook.com 在 MX 记录中:
  
![MX 记录指向 Office 365, 因此可能会重写收件人](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
请务必区分收件人域的 MX 记录不指向 Office 365 时, 以及当它完成了收件人重写的时间。 一定要区分这两种情况的区别。
  
如果您不确定接收域是否已完成收件人重写, 有时可以通过查看邮件头来判断。
  
a) 首先, 在身份验证-结果标头中查看收件人域邮件中的邮件头:
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

在上面的红色粗体文本中找到收件人域, 在此示例中为 office365.contoso.net。 这可能与收件人: 头中的收件人不同:
  
收件人: 示例收件人\<收件人 @ contoso.com\>
  
执行实际收件人域的 MX 记录查找。 如果它包含\*protection.outlook.com、mail.messaging.microsoft.com、 \*eo.outlook.com 或 mail.global.frontbridge.com, 则表示 MX 指向 Office 365。
  
如果它不包含这些值, 则表示 MX 不指向 Office 365。 您可以使用一种工具来验证这是 MX 工具箱。
  
在此特定示例中, 以下说出的是 contoso.com, 因为它是 "收件人: 标头" 的域, MX 记录指向本地 server:
  
![MX 记录指向本地服务器](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
但是, 实际的收件人是 office365.contoso.net, 其 MX 记录指向 Office 365:
  
![MX 指向 Office 365, 必须是收件人重写](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
因此, 此邮件可能已完成收件人重写。
  
b) 其次, 请务必区分收件人重写的常见用例。 如果要将收件人域\*重写为 onmicrosoft.com, 则改为将其重写\*为. mail.onmicrosoft.com。
  
确定了路由到另一台服务器后面的最终收件人域, 并且收件人域的 MX 记录实际指向 Office 365 (在其 DNS 记录中发布) 后, 您可以继续禁用反欺骗。
  
请记住, 如果路由路径中的第一个跃点是 Office 365, 则不需要禁用反欺骗, 仅当它位于一个或多个服务的后面时。
  
### <a name="how-to-disable-anti-spoofing"></a>如何禁用反欺骗

如果您已创建了一个反网络钓鱼策略, 请将 EnableAntispoofEnforcement 参数设置为 $false:
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false

```

如果您不知道要禁用的策略的名称 (或策略), 则可以显示它们:
  
```
Get-AntiphishPolicy | fl Name
```

如果没有任何现有的反网络钓鱼策略, 则可以创建一个这些策略, 然后将其禁用 (即使您没有策略, 仍会应用反欺骗; 在2018中, 稍后将为您创建一个默认策略, 然后您可以禁用它而不是创建一个). 您必须按多个步骤执行此操作:
  
```
$org = Get-OrganizationConfig
$name = "My first anti-phishing policy for " + $org.Name
# Note: If the name is more than 64 characters, you will need to choose a smaller one
```

```
# Next, create a new anti-phishing policy with the default values
New-AntiphishPolicy -Name $Name
# Select the domains to scope it to
# Multiple domains are specified in a comma-separated list
$domains = "domain1.com, domain2.com, domain3.com"
# Next, create the anti-phishing rule, scope it to the anti-phishing rule
New-AntiphishRule -Name $name -AntiphishPolicy -RecipientDomainIs $domains
# Finally, scope the anti-phishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false

```

禁用反欺骗只是通过 cmdlet 提供 (稍后将在安全&amp;合规中心中提供)。 如果您对 PowerShell 没有访问权限, 请创建支持票证。
  
请记住, 这仅适用于发送到 Office 365 时进行间接路由的域。 避免由于某些误报而禁用反欺骗的诱惑, 它在运行时可能会更好。
  
### <a name="information-for-individual-users"></a>单个用户的信息

单个用户在如何与反欺骗安全提示进行交互方面受到限制。 不过, 可以通过几种方法来解决常见方案。
  
### <a name="common-scenario-1---mailbox-forwarding"></a>常见方案 #1-邮箱转发

如果使用其他电子邮件服务并将电子邮件转发到 Office 365 或 Outlook.com, 则可能会将您的电子邮件标记为哄骗并收到红色的安全提示。 当转发器是 Outlook.com、Office 365、Gmail 或任何其他使用[ARC 协议](https://arc-spec.org)的服务之一时, Office 365 和 Outlook.com 计划自动解决此情况。 但是, 在部署该修补程序之前, 用户应使用 "已连接帐户" 功能直接导入邮件, 而不是使用转发选项。
  
若要在 office 365 中设置连接的帐户, 请选择 office 365 web \>界面邮件\>邮件\>帐户\>连接帐户右上角的齿轮图标。
  
!["Office 365-已连接帐户" 选项](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
在 Outlook.com 中, 该过程是 "齿轮\> " \>图标\>选项\>邮件帐户已连接帐户。
  
### <a name="common-scenario-2---discussion-lists"></a>常见方案 #2-讨论列表

如果讨论列表转发邮件和修改其内容, 则这些列表会遇到防欺骗问题, 同时保留原始的发件人: 地址。
  
例如, 假设您的电子邮件地址是用户 @ contoso.com, 并且您希望鸟瞰和加入讨论列表 birdwatchers @ example.com。 向讨论列表发送邮件时, 可以通过以下方式发送邮件:
  
**发件人:** John Doe \<用户 @ contoso.com\> 
  
**到:** Birdwatcher 的讨论列表\<birdwatchers @ example.com\> 
  
**主题:** 很好地查看 Mt 顶部的蓝色 jays。 本周 Rainier 
  
任何人都希望从 Mt 查看本周查看。 Rainier？
  
当电子邮件列表收到邮件时, 它们会对邮件进行格式设置, 修改其内容, 并将其重放到讨论列表上的其余成员, 这些内容由许多不同的电子邮件接收器的参与者组成。
  
**发件人:** John Doe \<用户 @ contoso.com\> 
  
**到:** Birdwatcher 的讨论列表\<birdwatchers @ example.com\> 
  
**主题:**[BIRDWATCHERS]很好地查看 Mt 顶部的蓝色 jays。 本周 Rainier 
  
任何人都希望从 Mt 查看本周查看。 Rainier？
  
---
  
此邮件已发送到 Birdwatchers 讨论列表。 您可以随时取消订阅。
  
在上面的邮件中, 重播邮件与 "address" (user @ contoso.com) 相同, 但原始邮件已通过将标记添加到 "主题" 行, 并将页脚添加到邮件底部来进行修改。 这种类型的邮件修改在邮件列表中很常见, 可能会导致误报。
  
如果您或组织中的某个人是邮寄列表的管理员, 则可以将其配置为传递反欺骗检查。
  
- 检查 DMARC.org 中的 FAQ:[我运行的是邮寄列表, 我想与 DMARC 进行互操作, 我该怎么办？](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)

- 阅读以下博客文章中的说明:[用于与 DMARC 进行互操作以避免故障的邮件列表运算符提示](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)

- 请考虑在邮寄列表服务器上安装更新以支持 ARC, 请参阅[https://arc-spec.org](https://arc-spec.org/)

如果您没有邮寄列表的所有权:
  
- 您可以请求邮件列表的 maintainer 实现上述选项之一 (他们还应为邮寄列表正在中继的域设置电子邮件身份验证)

- 您可以在电子邮件客户端中创建邮箱规则, 将邮件移动到 "收件箱"。 您还可以请求贵组织的管理员设置允许规则或重写, 如管理发送未经身份验证的电子邮件的合法发件人一节中所述。

- 您可以使用 Office 365 创建支持票证, 以创建用于将其视为合法邮件列表的覆盖

### <a name="other-scenarios"></a>其他方案

1. 如果上述两种方案都不适合您的情况, 请将邮件报告为误报返回给 Microsoft。 有关详细信息, 请参阅本文后面的[如何向 Microsoft 报告垃圾邮件或非垃圾邮件消息](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)一节。 

2. 你也可以联系你的电子邮件管理员, 将其作为 Microsoft 的支持票证提出。 Microsoft 工程团队将调查邮件被标记为欺骗的原因。

3. 此外, 如果您知道发件人是谁, 并且确信他们不是恶意欺骗的, 则可以回复给发件人, 以表明他们正在从不进行身份验证的邮件服务器发送邮件。 这有时会导致原始发件人联系其 IT 管理员, 以设置所需的电子邮件身份验证记录。
  
当发件人回复到应设置电子邮件身份验证记录的域所有者时, 它会 spurs 他们采取措施。 虽然 Microsoft 也能与域所有者合作以发布所需的记录, 但在各个用户请求的情况下, 它更有帮助。

4. (可选) 将发件人添加到安全发件人列表。 但是, 请注意, 如果 phisher 假冒该帐户, 则会将其传递到您的邮箱。 因此, 应谨慎使用此选项。

## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>发件人到 Microsoft 应如何为反欺骗保护做准备

如果你是当前向 Microsoft 发送邮件的管理员 (Office 365 或 Outlook.com, 则应确保你的电子邮件进行了正确的身份验证, 否则可能会将其标记为垃圾邮件或网络钓鱼。
  
### <a name="customers-of-office-365"></a>Office 365 的客户

如果你是 office 365 客户, 并且使用 office 365 发送出站电子邮件:
  
- 对于您的域, 请[在 Office 365 中设置 SPF 以帮助防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- 对于主域, 请[使用 DKIM 验证从 Office 365 中的自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)

- 考虑为您的域[设置 DMARC 记录](use-dmarc-to-validate-email.md), 以确定您的合法发件人。

Microsoft 不提供每个 SPF、DKIM 和 DMARC 的详细实施指南。 但是, 联机发布了大量信息。 还有第三方公司专门帮助您的组织设置电子邮件身份验证记录。
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>非 Office 365 客户的域的管理员

如果你是域管理员, 但不是 Office 365 客户:
  
- 应设置 SPF 以发布域的发送 IP 地址, 还应设置 DKIM (如果可用) 以对邮件进行数字签名。 您还可以考虑设置 DMARC 记录。

- 如果你有代表你传输电子邮件的批量发件人, 则应使用它们以一种方式发送电子邮件, 以便发件人: address (如果属于你) 中的发送域与传递 SPF 或 DMARC 的域相一致。

- 如果您有本地邮件服务器, 或从软件即服务提供商或从云托管服务 (如 Microsoft Azure、GoDaddy、Rackspace、Amazon Web 服务或类似的云托管服务) 发送, 则应确保它们已添加到您的 SPF 记录中。

- 如果您是由 isp 托管的小型域, 则应根据 isp 提供给您的说明设置 SPF 记录。 大多数 isp 提供这些类型的说明, 可在公司的支持页面中找到。

- 即使您在之前没有发布电子邮件身份验证记录, 并且它正常工作, 您仍必须发布电子邮件身份验证记录以发送给 Microsoft。 通过执行此操作, 你可以帮助抵御网络钓鱼, 并减少你或你发送到的组织将获得 phished 的可能性。

### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>如果你不知道谁将电子邮件作为你的域发送, 该怎么办？

许多域不会发布 SPF 记录, 因为它们不知道其所有发件人是谁。 这没关系, 您无需知道所有这些都是谁。 相反, 应首先发布您知道的一个 SPF 记录 (尤其是公司流量所在的位置), 并发布一个中性的 spf 策略？所有:
  
TXT "v = spf1 中的 example.com 包括 include spf.protection.outlook.com？ all"
  
非特定 SPF 策略意味着, 来自企业基础结构的任何电子邮件都将在所有其他电子邮件接收器中传递电子邮件身份验证。 来自你不知道的发件人的电子邮件将回退到中立, 这几乎与根本不发布任何 SPF 记录相同。
  
发送到 Office 365 时, 来自公司流量的电子邮件将被标记为已通过身份验证, 但是来自你不知道的来源的电子邮件可能仍被标记为欺骗 (取决于 Office 365 能否对其进行隐式身份验证)。 但是, 这仍是从 Office 365 标记为欺骗的所有电子邮件中的改进。
  
开始使用回退策略为 "全部" 的 SPF 记录后, 可以逐步包含更多的发送基础结构, 然后发布更严格的策略。 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>如果您是邮寄列表的所有者, 该怎么办？

请参阅 "[常见方案 #2-讨论列表](#common-scenario-2---discussion-lists)" 一节。
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>如果您是基础结构提供商 (ISP)、电子邮件服务提供商 (ESP) 或云托管服务, 该怎么办？

如果你托管域的电子邮件, 并且它发送电子邮件或提供可发送电子邮件的托管基础结构, 则应执行以下操作:
  
- 确保您的客户具有详细说明在其 SPF 记录中发布的内容的文档

- 考虑对出站电子邮件签名 DKIM-签名, 即使客户未明确设置 (使用默认域进行签名) 也是如此。 您甚至可以使用 DKIM 签名对电子邮件进行双重签名 (如果用户已对其进行了设置, 则使用一次对其进行双重签名) 以及公司的 DKIM 签名的第二次。

即使您对源自您的平台的电子邮件进行身份验证, 也不能保证 Deliverability, 但至少可确保 microsoft 不会对您的电子邮件进行垃圾邮件, 因为它未经过身份验证。 有关 Outlook.com 如何筛选电子邮件的更多详细信息, 请参阅[Outlook.com 邮局主管页](https://postmaster.live.com/pm/postmaster.aspx)。
  
有关服务提供商最佳做法的更多详细信息, 请参阅[M3AAWG Mobile 消息处理最佳实践 for service providers](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)。
  
## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="why-is-microsoft-making-this-change"></a>为什么 Microsoft 要进行此更改？

由于网络钓鱼攻击的影响, 并且电子邮件身份验证已有超过15年的时间, Microsoft 认为, 继续允许未经身份验证的电子邮件的风险高于丢失合法电子邮件的风险。
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>此更改是否会导致合法电子邮件被标记为垃圾邮件？

最初, 会有一些邮件被标记为垃圾邮件。 然而, 随着时间的推移, 发件人将会进行调整, 然后 mislabeled 的邮件数量将被视为可忽略的大多数电子邮件路径。
  
Microsoft 本身在将此功能部署到其客户的其余部分之前, 先在几周内采用此功能。 在第一次发生中断时, 会逐渐拒绝。
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>Microsoft 是否会将此功能引入 Office 365 的 Outlook.com 和非高级威胁防护客户？

Microsoft 的反欺骗技术最初部署到其组织中的 office 365 企业版 E5 订阅或购买了 office 365 高级威胁防护 (ATP) 附加的订阅。 从10月起, 2018 我们已扩展了对具有 Exchange Online protection (EOP) 的组织的保护。 将来, 我们可能会将其发布到 Outlook.com。 但是, 如果我们这样做, 可能会有一些未应用的功能, 如报告和自定义替代。
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>如何将垃圾邮件或非垃圾邮件报告回 Microsoft？

您可以使用 Outlook 的[报告消息外接程序](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2), 如果未安装, 请将垃圾邮件[、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx)。
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>我是一个不知道我的所有发件人是谁的域管理员!

请参阅[不是 Office 365 客户的域的管理员](#administrators-of-domains-that-are-not-office-365-customers)。
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>如果我对我的组织禁用反欺骗保护 (即使 Office 365 是我的主要筛选器), 会发生什么情况？

我们不建议这样做, 因为你将暴露给更多丢失的网络钓鱼和垃圾邮件。 并不是所有的网络钓鱼都是哄骗, 并且并非所有欺骗都将丢失。 但是, 您的风险将高于启用反欺骗的客户。
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>启用反欺骗保护意味着我将受到保护, 防止所有网络钓鱼？

遗憾的是, 因为仿冒者将使用其他技术 (如受损帐户) 或设置免费服务帐户进行调整。 但是, 反网络钓鱼保护的工作速度更好, 可以检测到这些其他类型的网络钓鱼方法, 因为 Office 365 的保护层设计在一起, 并在彼此之上构建。
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>其他大型电子邮件接收器是否阻止未经身份验证的电子邮件？

几乎所有大型电子邮件接收器都实现传统的 SPF、DKIM 和 DMARC。 有些接收器具有比这些标准更严格的其他检查, 但几乎不像 Office 365 那样阻止未经身份验证的电子邮件, 并将其视为欺骗。 但是, 大多数行业越来越严格地了解这种特定类型的电子邮件, 尤其是由于网络钓鱼问题。
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>如果启用反欺骗, 我是否仍需要为 "SPF Hard Fail" 启用高级垃圾邮件筛选选项？

不需要, 此选项不再是必需的, 因为反欺骗功能不仅认为 SPF 硬失败, 而且一组更广泛的条件。 如果启用了反欺骗并启用了 "SPF 硬故障" 选项, 则可能会获得更多误报。 我们建议禁用此功能, 因为它不会为垃圾邮件或网络钓鱼提供几乎额外的捕获, 而是生成大多数误报。
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>发件人重写方案 (SRS) 是否帮助修复转发的电子邮件？

SRS 仅部分修复了转发的电子邮件的问题。 通过重写 SMTP 邮件, SRS 可以确保转发的邮件在下一个目的地传递 SPF。 但是, 由于反欺骗是基于发件人: 地址与邮件发件人或 DKIM 签名域 (或其他信号) 的结合, 因此阻止转发的电子邮件被标记为欺骗的是不够的。