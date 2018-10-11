---
title: Office 365 中的防欺骗保护
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: d24bb387-c65d-486e-93e7-06a4f1a436c0
description: 本文介绍如何 Office 365 缓解了对网络钓鱼攻击使用伪造发件人域，即，造假的域。这是通过实现通过分析邮件和阻止的那些类型的值可以是经过 neithe 身份验证通过使用标准电子邮件身份验证方法，也其他发件人信誉方法。实现此更改是为了减少向公开 Office 365 中的组织的网络钓鱼攻击的数。
ms.openlocfilehash: 37eddfcad9bc5e412f62dd857178eafa8cac9355
ms.sourcegitcommit: ba2175e394d0cb9f8ede9206aabb44b5b677fa0a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2018
ms.locfileid: "25496896"
---
# <a name="anti-spoofing-protection-in-office-365"></a>Office 365 中的防欺骗保护

本文介绍如何 Office 365 缓解了对网络钓鱼攻击使用伪造发件人域，即，造假的域。它来实现此通过分析邮件和阻止的无法使用标准电子邮件身份验证方法，也其他发件人信誉技术身份验证。实现此更改是为了减少向公开客户的网络钓鱼攻击的数。
  
本文还介绍了为什么要进行此更改、 客户如何准备此更改、 如何查看将受影响的邮件，如何对邮件报告、 如何缓解误报，以及发件人向 Microsoft 对此应做好准备发生更改。
  
Microsoft 的反欺骗技术已最初部署到其组织的 Office 365 企业 E5 订阅或已购买 Office 365 高级威胁保护 (ATP) 加载项为其订阅。从 2018 年 10 月，我们已扩展到以及具有 Exchange Online Protection (EOP) 的组织的保护。此外，由于我们筛选器的所有相互学习的方式，Outlook.com 用户也可能受到影响。
  
## <a name="how-spoofing-is-used-in-phishing-attacks"></a>如何欺骗网络钓鱼攻击中使用

当谈到保护用户时，Microsoft 非常重视网络钓鱼的威胁。垃圾邮件和网络钓鱼者常使用的方法之一欺骗，这时伪造是发件人，并显示一条消息以源自从某人或其他地方之外的实际的源。在设计用来获取用户凭据的网络钓鱼活动中通常使用此技术。Microsoft 的反欺骗技术专门检查伪造的从： 标头这是如 Outlook 电子邮件客户端中显示的一个。当 Microsoft 具有高可信度的 From： 造假标头，它标识为欺骗的消息。
  
欺骗邮件都具有两个负面影响所作的实际用户：
  
### <a name="1-spoofed-messages-deceive-users"></a>1.欺骗邮件欺骗用户
  
首先，带欺骗性的消息可能会诱使用户单击的链接和放弃其凭据、 下载恶意软件，或答复邮件包含敏感内容 （后一种称为业务电子邮件威胁）。例如，下面是网络钓鱼邮件 msoutlook94@service.outlook.com 欺骗发件人为：
  
![网络钓鱼邮件模拟 service.outlook.com](media/1a441f21-8ef7-41c7-90c0-847272dc5350.jpg)
  
上述并不实际来自于 service.outlook.com，但网络钓鱼者以使其看一样而被盗用。正在尝试诱使用户单击消息中的链接。
  
下一个示例欺骗 contoso.com:
  
![网络钓鱼邮件的业务电子邮件威胁](media/da15adaa-708b-4e73-8165-482fc9182090.jpg)
  
消息看起来是合法，但实际上是欺骗。此网络钓鱼邮件是一种类型的业务电子邮件威胁即网络钓鱼的子类别。
    
### <a name="2-users-confuse-real-messages-for-fake-ones"></a>2.用户将混淆假结构的实际邮件
  
第二个、 带欺骗性消息创建用户了解网络钓鱼邮件，但无法判断实际消息和欺骗的一个之间的差异的不的确定性。例如，以下是从 Microsoft 安全帐户的电子邮件地址重置实际密码的示例：
  
![Microsoft 合法密码重置](media/58a3154f-e83d-4f86-bcfe-ae9e8c87bd37.jpg)
  
上面的消息未来自 Microsoft，但同时，用户将用来获取网络钓鱼邮件的可能会诱使用户单击的链接和放弃其凭据、 下载恶意软件，或答复邮件包含敏感内容。因为很难告知实际密码重置和一个虚假之间的差异，很多用户忽略这些消息、 将其报告为垃圾邮件，或不必要地邮件后向 Microsoft 报告为错过网络钓鱼诈骗。
    
若要停止欺骗，电子邮件筛选行业开发了[SPF](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx)、 [DKIM](https://technet.microsoft.com/en-us/library/mt695945%28v=exchg.150%29.aspx)，等[DMARC](https://technet.microsoft.com/en-us/library/mt734386%28v=exchg.150%29.aspx)电子邮件身份验证协议。DMARC 阻止欺骗检查邮件的发件人-用户看到其电子邮件客户端中的一个 （在上述示例中，这是 service.outlook.com、 outlook.com 和 accountprotection.microsoft.com）-使用 SPF 或 DKIM 传递的域。即，用户看到的域已经过身份验证，因此不被篡改。有关更全面讨论，请参阅"*了解为什么电子邮件身份验证并不总是足以停止欺骗"* 本文档中的更高版本上。 
  
但是，问题在于该记录是可选的不需要的电子邮件身份验证。因此，同时使用强身份验证策略的域 like microsoft.com ヘ skype.com シ シ 术从欺骗的所有发布较弱的身份验证策略或无策略，是正在造假的目标域。从年 3 月 2018年只有 9%的域中财富 500 的公司的发布强的电子邮件身份验证策略。剩余的 91%可能被钓鱼欺骗和除非电子邮件筛选器检测到它使用其他策略可能会传递给最终用户和欺骗它们：
  
![DMARC 策略的财富 500 公司](media/84e77d34-2073-4a8e-9f39-f109b32d06df.jpg)
  
小型到中型调整公司的比例不在发布强的电子邮件身份验证策略财富 500 是较小，和较小仍北美和西欧之外的域。
  
这是一个大问题，因为网络钓鱼者时企业可能不知道的电子邮件身份验证的工作方式，执行了解并充分利用缺乏。
  
SPF、 DKIM 和 DMARC 设置的信息，请参阅部分"本文档中的更高版本上*的 Office 365" 的客户*。 
  
## <a name="stopping-spoofing-with-implicit-email-authentication"></a>停止欺骗隐式电子邮件身份验证

由于网络钓鱼和矛网络钓鱼此类问题，且强的电子邮件身份验证策略的有限采用，因为 Microsoft 不断功能保护其客户购买。因此，Microsoft 将使用*隐式电子邮件身份验证*-提前移如果域不进行身份验证，Microsoft 将将其视为它具有发布电子邮件身份验证记录和将其视为相应地，如果它不传递。 
  
若要实现此目的，Microsoft 已经构建了大量扩展正则电子邮件身份验证包括发件人信誉、 发件人/收件人历史记录、 行为的分析和其他高级的技术。不发布电子邮件身份验证的域发送的消息将标记为欺骗除非它包含其他信号以指明它是合法。
  
这样，最终用户可以向其发送电子邮件不伪造可信度，发件人可以确信没有人正在模拟他们的域和 Office 365 的客户可以提供更好的保护，如模拟保护。
  
若要查看 Microsoft 的常规通知，请参阅[Sea 的网络钓鱼诈骗第 2 部分-Office 365 中的增强反欺骗](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Schooling-A-Sea-of-Phish-Part-2-Enhanced-Anti-spoofing/ba-p/176209)。
  
## <a name="identifying-that-a-message-is-classified-as-spoofed"></a>标识一条消息被归类为造假

### <a name="composite-authentication"></a>复合身份验证

时 SPF、 DKIM 和 DMARC 所有有用本身，它们不在事件消息的产生任何显式身份验证记录通信足够身份验证状态。因此，Microsoft 开发了将多个信号合并为单个值调用 short 复合身份验证或 compauth 算法。Office 365 中的客户具有到邮件头中的*身份验证结果*页眉标 compauth 值。 
  
```
Authentication-Results:
  compauth=<fail|pass|softpass|none> reason=<yyy>

```

|**CompAuth 结果**|**说明**|
|:-----|:-----|
|失败|邮件无法显式身份验证 （发送域发布记录显式在 DNS 中） 或隐式身份验证 （发送以便 Office 365 内结果，就好像它具有发布记录域未在 DNS 中，发布记录）。|
|传递|消息传递显式身份验证 （消息传递 DMARC 或[最佳猜测传递 DMARC](https://blogs.msdn.microsoft.com/tzink/2015/05/06/what-is-dmarc-bestguesspass-in-office-365)） 或使用高可信度隐式身份验证 （发送域不发布电子邮件身份验证记录，但 Office 365 具有强的后端信号以指明消息可能合法)。|
|softpass|消息传递低到中级自信地隐式身份验证 （发送域不发布电子邮件身份验证，但 Office 365 具有后端信号，以指示邮件是合法但较弱的信号的均强度）。|
|无|邮件未通过验证 （或者未进行身份验证但未在对齐），但不是应用由于发件人信誉或其他因素的复合身份验证。|
   
|||
|:-----|:-----|
|**原因**|**说明**|
|0xx|消息失败复合身份验证。<br/>**000**意味着 DMARC 与拒绝或隔离操作失败的消息。                   -001 意味着隐式电子邮件身份验证失败的消息。这意味着的发送域没有电子邮件身份验证记录发布，或者如果那样，它们必须较弱的失败策略 (SPF 软故障或 neutral，DMARC 策略的 p = none)。<br/>**002**表示组织具有显式禁止发送带欺骗性的电子邮件的发件人/域对的策略，由管理员手动设置此设置。  <br/>**010**表示 DMARC 与拒绝或隔离，操作失败的消息并发送域是您组织的接受域之一 (这是自签名自我或组织内的一部分欺骗)。  <br/>**011**表示隐式电子邮件身份验证失败的消息并发送域是您组织的接受域之一 (这是自签名自我或组织内的一部分欺骗)。|
|所有其他代码 （1xx 2xx、 3xx、 4xx、 5xx）|为什么一条消息传递隐式身份验证，或具有任何身份验证但不应用任何操作对应的各种内部代码。|
   
通过查看邮件的标头，管理员或甚至最终用户将可以确定 Office 365 如何到达发件人可能具有欺骗性组成部分。
  
### <a name="differentiating-between-different-types-of-spoofing"></a>区分不同类型的欺骗

Microsoft 区分两种不同类型的欺骗消息：
  
 **组织内欺骗**
  
也称为自我到自我欺骗时，发生这种情况时在从域： 地址相同，或与收件人域 （当收件人的域为贵组织的[接受域](https://technet.microsoft.com/en-us/library/jj945194%28v=exchg.150%29.aspx)之一）; 对齐或者，当在从域： 地址属于同一组织。
  
例如，以下包含发件人和收件人来自同一个域 (contoso.com)。空格插入到电子邮件地址，以防止此页上的 spambot 网络）：
  
从： 发件人 @ contoso.com
  
收件人: @ contoso.com 的收件人
  
以下具有与组织的域 (fabrikam.com) 对齐的发件人和收件人的域：
  
从： 发件人 @ foo.fabrikam.com
  
收件人: @ bar.fabrikam.com 收件人
  
下列发件人和收件人域不相同 （microsoft.com 和 bing.com），但属于同一组织 （即，两者都是组织的接受域的一部分）：
  
从： 发件人 @ microsoft.com
  
收件人: @ bing.com 收件人
  
失败欺骗组织内的邮件包含头中的以下值：
  
X Forefront 反垃圾邮件报告:...CAT:SPM/HSPM/PHSH;...SFTY:9.11
  
CAT is 消息的类别和它通常标为 SPM （垃圾邮件），但有时是 HSPM （高可信度垃圾邮件） 或网络钓鱼 （网络钓鱼） 具体取决于哪些其他类型的模式中可能会出现该邮件。
  
SFTY 是邮件的安全级别、 第一个数字 (9) 表示邮件是网络钓鱼，以及另一位数字后点 (11) 意味着它为组织内欺骗。
  
没有为复合身份验证组织内欺骗，都将标后面 2018 （尚未定义时间线） 的具体原因代码。
  
 **跨域欺骗**
  
发生这种情况时在从的发送域： 地址是到接收组织外部域。由于跨域欺骗失败复合身份验证的邮件包含头中的以下值：
  
身份验证结果:...compauth = 失败原因 = 000/001
  
X Forefront 反垃圾邮件报告:...CAT:SPOOF;...SFTY:9.22
  
在这两种情况下，以下红色安全提示被标邮件或为自定义为收件人邮箱的语言的等效项中：
  
![红色安全提示-欺诈检测](media/a366156a-14e8-4c14-bfe5-2031b21936f8.jpg)
  
它只是看 From： 地址和知道您收件人的电子邮件什么，或按检查电子邮件的标头，您可以区分组织内和跨域欺骗。
  
## <a name="how-customers-of-office-365-can-prepare-themselves-for-the-new-anti-spoofing-protection"></a>Office 365 的客户可以如何准备自己的新反欺骗保护

### <a name="information-for-administrators"></a>管理员的的信息

作为 Office 365 中组织的管理员，有几个关键您应了解的信息。
  
### <a name="understanding-why-email-authentication-is-not-always-enough-to-stop-spoofing"></a>了解为什么电子邮件身份验证并不总是足以停止欺骗

新反欺骗保护依赖于电子邮件身份验证 （SPF、 DKIM 和 DMARC），不标记为欺骗邮件。发送域已从不发布 SPF 记录时的常见示例。如果没有 SPF 记录或他们不正确设置，则已发送的邮件将被标记为造假除非 Microsoft 具有指示邮件是合法的后端智能。
  
例如，反欺骗正在部署前, 一条消息可能类似没有 SPF 记录，没有 DKIM 记录，与没有 DMARC 记录以下： 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```
后反欺骗，如果您具有 Office 365 企业 E5、 EOP 或 ATP，被标 compauth 值：
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=none
  action=none header.from=example.com; compauth=fail reason=001
From: sender @ example.com
To: receiver @ contoso.com

```

如果 example.com 解决这设置 SPF 记录，但不是一个 DKIM 记录，因为传递 SPF 的域与源中的域对齐，这将传递复合身份验证： 地址： 
  
```
Authentication-Results: spf=pass (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=none
  (message not signed) header.d=none; contoso.com; dmarc=bestguesspass
  action=none header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

或者，如果他们设置 DKIM 记录，但不是 SPF 记录，这会因为传递 DKIM 签名中的域与源中的域对齐地还通过复合身份验证： 地址： 
  
```
Authentication-Results: spf=none (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; contoso.com; dkim=pass
  (signature was verified) header.d=outbound.example.com;
  contoso.com; dmarc=bestguesspass action=none
  header.from=example.com; compauth=pass reason=109
From: sender @ example.com
To: receiver @ contoso.com
```

然而，钓鱼可能还设置 SPF 和 DKIM，签名邮件自己域，但在从指定不同的域： 地址。SPF 和 DKIM 都不需要符合在从域的域： 解决，除非 example.com 发布 DMARC 记录，这会将标记为使用 DMARC 欺骗，因此： 
  
```
Authentication-Results: spf=pass (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=example.com;
From: sender @ example.com
To: receiver @ contoso.com
```

在电子邮件客户端 (Outlook，在 web 或任何其他电子邮件客户端上的 Outlook)，仅从： 显示域、 不是在域中 SPF 或 DKIM，并且会以为消息来自 example.com，但实际上是来自 maliciousDomain.com 误导用户.
  
![经过身份验证的消息，但从： 域未与什么传递 SPF 或 DKIM 对齐](media/a9b5ab2a-dfd3-47c6-8ee8-e3dab2fae528.jpg)
  
因此，Office 365 需要在从域： 与 SPF 或 DKIM 签名中的域对齐地址和邮件如果它不，包含指示的某些其他内部信号是合法。否则，该消息将是 compauth 失败。 
  
```
Authentication-Results: spf=none (sender IP is 5.6.7.8)
  smtp.mailfrom=maliciousDomain.com; contoso.com; dkim=pass
  (signature was verified) header.d=maliciousDomain.com;
  contoso.com; dmarc=none action=none header.from=contoso.com;
  compauth=fail reason=001
From: sender@contoso.com
To: someone@example.com
```

因此，Office 365 反欺骗保护与无身份验证的域和设置身份验证，但不匹配，针对在从域的域： 地址，它是一个用户看到和认为是邮件的发件人。这是这两种为贵组织中的域或组织外部的域，则返回 true。
  
因此，如果您曾收到一条消息，复合身份验证失败和标记为造假，即使邮件传递 SPF 和 DKIM，这是因为传递 SPF 和 DKIM 域不符合在从域： 地址。
  
### <a name="understanding-changes-in-how-spoofed-emails-are-treated"></a>了解如何欺骗电子邮件中的更改被视为

目前，所有组织中 Office 365-ATP 和非-ATP-消息 DMARC 与拒绝或隔离的策略标记为垃圾邮件和通常需要高可信度垃圾邮件操作，或有时正则垃圾邮件操作的失败 (具体取决于其他垃圾邮件规则首先标识为垃圾邮件）。组织内欺骗检测执行常规垃圾邮件的操作。此行为不需要启用，也可以禁用。
  
但是的跨域欺骗邮件之前此更改它们经过正则垃圾邮件和网络钓鱼诈骗、 恶意软件检查并如果筛选器的其他部件将它们标识为可疑，会将它们标记为垃圾邮件、 网络钓鱼诈骗、 或恶意软件分别。通过使用新的跨域欺骗保护，无法进行身份验证的任何消息，默认情况下，需要防钓鱼中定义的操作\>防欺骗策略。如果未定义，它将移动到用户的垃圾邮件文件夹。在某些情况下，更可疑邮件还必须添加到邮件中的红色安全提示。
  
这可能会导致先前已标记为垃圾邮件仍获取标记为垃圾邮件，但现在还具有红色安全提示; 某些消息在其他情况下，添加先前已标记为非垃圾邮件将开始获取标记为垃圾邮件 (CAT:SPOOF) 的红色安全提示信息的邮件。在仍其他情况下，已将所有垃圾邮件和网络钓鱼诈骗移动到隔离邮箱的客户将立即看到到垃圾邮件文件夹将其 （此行为可更改，请参阅[更改反欺骗设置](#changing-your-anti-spoofing-settings)）。
  
有多种不同的方式可以 （请参阅上文中的[不同类型的欺骗之间 Differentiating](#differentiating-between-different-types-of-spoofing) ） 欺骗一条消息，但年 3 月 2018年从 Office 365 将这些邮件处理的方式不尚未统一。下表是摘要，使用跨域欺骗保护正在新行为： 
  
|**欺骗的类型**|**类别**|**添加的安全提示？**|**应用于**|
|:-----|:-----|:-----|:-----|
|DMARC 失败 （隔离或拒绝）  <br/> |HSPM （默认），也可能会 SPM 或 PHSH  <br/> |否 （尚未）  <br/> |所有 Office 365 客户 Outlook.com  <br/> |
|自我到自我  <br/> |SPM  <br/> |是  <br/> |所有 Office 365 组织 Outlook.com  <br/> |
|跨域  <br/> |欺骗  <br/> |是  <br/> |Office 365 高级威胁保护和 E5 客户  <br/> |
   
### <a name="changing-your-anti-spoofing-settings"></a>更改反欺骗设置

若要创建或更新 （跨域） 反欺骗设置，请导航到防钓鱼\>下威胁管理反欺骗设置\>安全中的策略选项卡&amp;合规性中心。如果从未创建任何防钓鱼设置，您需要创建一个权限级别：
  
![反钓鱼-创建新的策略](media/9337ec91-270e-4fa7-9dfa-a51a2d1eb95e.jpg)
  
如果您已经创建了一个，则可以选择它对其进行修改：
  
![反钓鱼-修改现有策略](media/75457a7c-882e-4984-80d1-21a12b42c53a.jpg)
  
选择您刚刚创建的策略，然后继续完成的步骤上, 所述[了解更多有关欺骗智能。](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)
  
![启用或禁用 antispoofing](media/c49e2147-c954-443c-9144-1cbd139e1166.jpg)
  
![启用或禁用 antispoofing 安全提示](media/eec7c407-31fc-4f73-8325-307d82d1fb53.jpg)
  
若要创建新策略通过 PowerShell 自定义： 
  
```
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

然后，您可以修改，使用 PowerShell 关注的文档[集 AntiphishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy?view=exchange-ps)防钓鱼策略参数。您可以指定 $name 作为参数：
  
```
Set-AntiphishPolicy -Identity $name <fill in rest of parameters>
```

更高版本中 2018，而不是您无需创建默认策略，将创建一个，因此您无需手动指定给您的组织中的所有收件人作用域 （下面的屏幕截图是最终的实现之前恕）。
  
![反钓鱼的默认策略](media/1f27a0bf-e202-4e12-bbac-24baf013c8f9.jpg)
  
与您创建的策略，不同，不能删除默认策略、 修改其优先级，或选择分配给哪些用户、 域或组。
  
![反钓鱼默认策略的详细信息](media/30c21ceb-df52-4c93-aa65-f44a55dc1009.jpg)
  
更高版本上中 2018，设置您通过 PowerShell 自定义的默认保护：
  
```
$defaultAntiphishPolicy = Get-AntiphishingPolicy -IsDefault $true
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement <$true|$false>
```

您只应禁用反欺骗保护，如果您有另一个邮件服务器或 Office 365 之前的服务器 （请参阅合法方案禁用反欺骗的详细信息）。 
  
```
$defaultAntiphishPolicy = Get-AntiphishingPolicy -IsDefault $true
Set-AntiphishPolicy -Identity $defaultAntiphishPolicy.Name -EnableAntispoofEnforcement $false 

```
> [!IMPORTANT]
> 如果您的电子邮件路径中的第一个跃点是 Office 365，并收到太多合法的电子邮件标记为欺骗，您应首先设置您允许欺骗电子邮件发送到您的域的发件人 （请参见 *"Managing 合法发件人发送 u 部分nauthenticated 电子邮件"* )。如果您仍收到太多误报 （例如，合法邮件标记为欺骗），建议您不要完全禁用反欺骗保护。相反，我们建议而不高保护中选择基本。                   最好能够通过误报比以公开其最终会强制显著提高成本施加长期欺骗电子邮件组织。

### <a name="managing-legitimate-senders-who-are-sending-unauthenticated-email"></a>管理合法发件人发送未经身份验证的电子邮件

跟踪人员将未经身份验证的电子邮件发送到您的组织的 office 365。如果服务认为发件人不是合法，它会将其标记为*compauth*失败。这将归类为欺骗，尽管这取决于您已应用于邮件的反欺骗策略。 
  
但是，作为管理员，您可以指定的发件人都可以发送带欺骗性的电子邮件，重写 Office 365 的决策。
  
**方法 1-如果您的组织拥有的域，设置电子邮件身份验证**
  
此方法可用于解决组织内欺骗，和跨域欺骗在您拥有或交互的情况下使用多个租户。它还有助于解决跨域欺骗，发送到 Office 365 中的其他客户以及第三方中其他提供程序承载的。
  
有关详细信息，请参阅[Office 365 客户](#customers-of-office-365)。 
 
**方法 2-使用欺骗智能配置允许的发件人的未经身份验证的电子邮件**
  
您还可以使用[欺骗智能](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf)允许发件人传输到您的组织的未经身份验证的消息。 
  
对于外部域，带欺骗性的用户是域中发件人地址，发送基础结构时发送 IP 地址 (分为/24 CIDR 范围)，或组织域的 PTR 记录 （在下面的屏幕截图，发送 IP 可能是的 131.107.18.4 其 PTR 记录是 outbound.mail.protection.outlook.com，并且这将显示为 outlook.com 发送基础结构）。
  
要允许此发件人发送未经身份验证的电子邮件，请将更改为**是**的**否**。
  
![设置允许的发件人的 antispoofing](media/d4334921-d820-4334-8217-788279701e94.jpg)
  
您还可以使用 PowerShell 允许特定发件人欺骗您的域： 
  
```
$file = "C:\My Documents\Summary Spoofed Internal Domains and Senders.csv"
```

```
Get-PhishFilterPolicy -Detailed -SpoofAllowBlockList -SpoofType External | Export-CSV $file
```

![获取欺骗发件人通过 Powershell 自定义](media/0e27ffcf-a5db-4c43-a19b-fa62326d5118.jpg)
  
在上图中，以使此屏幕截图适应，但实际上所有值会都显示在一行上，具有已添加其他换行符。
  
编辑文件寻找 outlook.com 和 bing.com，对应的行和 AllowedToSpoof 项更改为是无从：
  
![设置欺骗允许通过 Powershell 自定义是](media/62340452-62d3-4958-9ce9-afe5275a870d.jpg)
  
保存文件，然后运行： 
  
```
$UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
```

现在，这将使 bing.com 发送未经身份验证电子邮件从\*。 outlook.com。

**方法 3-创建发件人/收件人对允许条目**
  
您还可以选择绕过所有垃圾邮件筛选特定发件人。有关详细信息，请参阅[如何安全地添加到 Office 365 中的允许列表的发件人](https://blogs.msdn.microsoft.com/tzink/2017/11/29/how-to-securely-add-a-sender-to-an-allow-list-in-office-365/)。
  
如果您使用此方法，它将跳过垃圾邮件和一些网络钓鱼诈骗筛选，但不是恶意软件筛选。
  
**方法 4-联系人发件人，请他们设置电子邮件身份验证**
  
垃圾邮件和网络钓鱼的问题，因为 Microsoft 建议设置电子邮件身份验证的所有发件人。如果您知道的发送域管理员，请联系它们和他们设置电子邮件身份验证记录因此不需要添加任何重写的请求。有关详细信息，请参阅[不是 Office 365 客户的域的管理员](#administrators-of-domains-that-are-not-office-365-customers)"后面的这篇文章。 
  
可能会变得比较困难，首先获取发送域进行身份验证，随时间推移，越来越多电子邮件筛选器启动 junking 或甚至拒绝其电子邮件，它将导致他们设置相应的记录以确保提供更好。
  
### <a name="viewing-reports-of-how-many-messages-were-marked-as-spoofed"></a>查看多少邮件已标记为造假报告

启用您反欺骗策略后，您可以使用威胁智能若要解决多少邮件标记为网络钓鱼诈骗的号码。若要执行此操作，请转到安全&amp;下威胁管理合规性中心 (SCC)\>资源管理器中，通过发件人域或保护状态将视图设置为网络钓鱼诈骗、 和组：
  
![查看多少邮件标记为网络钓鱼诈骗](media/de25009a-44d4-4c5f-94ba-9c75cd9c64b3.jpg)
  
您可以与各种报告以查看多少已标记为网络钓鱼，包括消息标记为欺骗进行交互。若要了解详细信息，请参阅[开始使用 Office 365 威胁智能](https://support.office.com/article/get-started-with-office-365-threat-intelligence-38e9b67f-d188-490f-bc91-a1ae4b270441)。
  
尚未无法拆分出的邮件已标记由于欺骗与其他类型的网络钓鱼 （常规网络钓鱼、 域或用户模拟等）。但是，后面 2018，您将能够执行此操作通过安全&amp;合规性中心。做后，可以作为起点使用此报告来标识可能是合法的被标记为欺骗由于出现故障的身份验证的发送域。
  
下面的屏幕快照是如何此数据的外观，但可能会改变发布时的建议：
  
![查看网络钓鱼报告按检测类型](media/dd25d63f-152c-4c55-a07b-184ecda2de81.jpg)
  
对于非 ATP 和 E5 客户，这些报告更高版本中 2018 下威胁保护状态 (TP) 报告中，将提供，但将推迟至少 24 小时。该页面将更新，如集成安全性&amp;合规性中心。
  
### <a name="predicting-how-many-messages-will-be-marked-as-spoof"></a>预测多少邮件将被标记为欺骗

后面 2018 Office 365 一次更新其设置让您关闭反欺骗实施，或在与基本或高实施，将为您提供能够看到消息处置将如何在各种设置更改。也就是说，如果反欺骗处于关闭状态，您将能够看到多少邮件将被检测为欺骗，如果您启用到 Basic;或者，如果是 Basic，您将能够看到多少更多邮件将被检测为欺骗，如果将它转换为高。
  
此功能目前正在开发。定义更多详细信息，则该页面将更新同时与的安全性和合规性中心的屏幕截图和 PowerShell 示例。
  
!["如果"启用 antispoofing 报告](media/fdd085ae-02c1-4327-a063-bfe9a32ff1eb.jpg)
  
![可能允许欺骗发件人的 UX](media/53f9f73e-fb01-47f3-9a6d-850c1aef5efe.jpg)
  
### <a name="understanding-how-spam-phishing-and-advanced-phishing-detections-are-combined"></a>了解如何垃圾邮件、 网络钓鱼和检测兼而有之高级网络钓鱼

如果组织使用或不 ATP，使用 Exchange Online 中，可以指定的服务标识为恶意软件、 垃圾邮件、 高可信度垃圾邮件、 网络钓鱼和批量邮件时要采取哪些操作。使用 ATP 客户的 ATP 防钓鱼策略和 EOP 客户的防钓鱼策略和一条消息可能命中多个检测类型 （例如，恶意软件、 网络钓鱼和用户模拟） 这一事实，可能有一些混乱策略适用。 
  
一般情况下，CAT （类别） 属性中的 X Forefront 反垃圾邮件报表页眉中标识应用于邮件的策略。 
  
|**Priority**|**策略**|**类别**|**其中托管？**|**应用于**|
|:-----|:-----|:-----|:-----|:-----|
|1   <br/> |恶意软件  <br/> |MALW  <br/> |[恶意软件策略](https://technet.microsoft.com/en-us/library/jj200745%28v=exchg.150%29.aspx) <br/> |所有组织  <br/> |
|2   <br/> |网络钓鱼  <br/> |PHSH  <br/> |[承载的内容筛选器策略](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |所有组织  <br/> |
|3   <br/> |可信度高的垃圾邮件  <br/> |HSPM  <br/> |[承载的内容筛选器策略](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |所有组织  <br/> |
|4   <br/> |欺骗  <br/> |欺骗  <br/> |[防钓鱼策略](https://go.microsoft.com/fwlink/?linkid=864553)，[欺骗智能](https://support.office.com/article/Learn-more-about-spoof-intelligence-978c3173-3578-4286-aaf4-8a10951978bf) <br/> |所有组织  <br/> |
|5   <br/> |垃圾邮件  <br/> |SPM  <br/> |[承载的内容筛选器策略](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |所有组织  <br/> |
|6   <br/> |批量  <br/> |批量  <br/> |[承载的内容筛选器策略](https://technet.microsoft.com/library/jj200684%28v=exchg.150%29.aspx) <br/> |所有组织  <br/> |
|7   <br/> |域模拟  <br/> |DIMP  <br/> |[防钓鱼策略](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |仅组织 ATP  <br/> |
|8   <br/> |用户模拟  <br/> |UIMP  <br/> |[防钓鱼策略](https://go.microsoft.com/fwlink/?linkid=864553) <br/> |仅组织 ATP <br/> |
   
如果您有多个不同的防钓鱼策略，将应用的最高优先级的一个。例如，假设您有两个策略：
  
|**策略**|**Priority**|**用户/域模拟**|**反欺骗**|
|:-----|:-----|:-----|:-----|
|A  <br/> |1   <br/> |On  <br/> |Off  <br/> |
|B  <br/> |2   <br/> |关  <br/> |位置  <br/> |
   
如果一条消息起作用，并被标识为欺骗和用户模拟和一组相同的用户范围的策略和策略 B，则邮件将被视为欺骗但没有操作应用相防欺骗处于关闭状态并在用户模拟 (8) 比更高的优先级 (4) 欺骗运行。
  
若要进行其他类型的网络钓鱼策略应用，您将需要调整谁的各种策略应用于的设置。
  
### <a name="legitimate-scenarios-to-disable-anti-spoofing"></a>若要禁用反欺骗的合法方案

更好地反欺骗保证客户的网络钓鱼攻击，因此强烈建议您不要禁用反欺骗保护。通过禁用它，您可能会解决一些短期误报，但您将会面临详细风险的长期。设置在发件人一侧，身份验证或网络钓鱼策略中进行调整的成本通常一次性事件，或需要最少、 定期维护。但是，其中已公开数据，网络钓鱼攻击恢复成本或资产已泄露是高得多。
  
因此，最好能够通过比要禁用防欺骗保护反欺骗误报。
  
但是，没有合法的方案，其中应禁用反欺骗，并有其他邮件筛选时的邮件路由，和 Office 365 中的产品不是电子邮件路径中的第一个跃点：
  
![客户 MX 记录未指向 Office 365](media/62127c16-cfb8-4880-9cad-3c12d827c67e.jpg)
  
其他服务器可能 Exchange 内部部署邮件服务器，筛选设备 Ironport，如邮件或其他云托管服务。
  
如果收件人的域的 MX 记录未指向 Office 365，则不需要禁用反欺骗因为 Office 365 查找接收域的 MX 记录，并禁止反欺骗指向另一项服务。如果您不知道您的域如果前端具有另一台服务器，您可以使用类似 MX 工具箱的网站以查找 MX 记录。它可能会显示类似以下内容：
  
![MX 记录表示域不指向 Office 365](media/d868bb9f-3462-49aa-baea-9447a3ce4877.jpg)
  
此域有 MX 记录未指向 Office 365 中，以便 Office 365 不适用反欺骗实施的。
  
但是，如果*执行*的收件人域的 MX 记录指向 Office 365 中，即使没有之前 Office 365 另一项服务，然后您应禁用反欺骗。最常见的示例是通过使用收件人重写： 
  
![收件人重写的路由关系图](media/070d90d1-50a0-42e4-9fd3-920bc99a7cad.jpg)
  
域 contoso.com 的 MX 记录指向的内部服务器，同时域 @office365.contoso.net MX 记录指向在 Office 365，因为它包含\*。 protection.outlook.com，或\*。 eo.outlook.com 的 MX 记录中：
  
![MX 记录指向 Office 365，因此可能收件人重写](media/4101ad51-ef92-4907-b466-b41d14d344ca.jpg)
  
请务必区分以及它已经过收件人重写时的收件人域的 MX 记录未指向 Office 365。务必告知这两种情况之间的差异。
  
如果您不确定接收域已经过收件人重写，有时您可以通过查看判断在邮件头。
  
） 首先，查看中的身份验证结果标头中的收件人域的邮件的标头： 
  
```
Authentication-Results: spf=fail (sender IP is 1.2.3.4)
  smtp.mailfrom=example.com; office365.contoso.net; dkim=fail
  (body hash did not verify) header.d=simple.example.com;
  office365.contoso.net; dmarc=none action=none
  header.from=example.com; compauth=fail reason=001
```

上方，在此案例 office365.contoso.net 的加粗红色文本中找到的收件人的域。这可能不同，在收件人收件人： 标头：
  
收件人： 示例收件人\<@ contoso.com 收件人\>
  
执行实际的收件人域的 MX 记录查找。如果它包含\*。 protection.outlook.com、 mail.messaging.microsoft.com， \*。 eo.outlook.com 或 mail.global.frontbridge.com，这意味着 MX 指向 Office 365。
  
如果它不包含这些值，则意味着 MX 不指向 Office 365。一个工具可用于验证这是 MX 工具箱。
  
对于此特定的示例，以下显示该 contoso.com，如下所示收件人，因为它，收件人的域： 标头，具有 MX 记录指向上 prem 服务器：
  
![MX 记录指向上 prem 服务器](media/2444144a-9a90-4319-96b2-d115041f669f.jpg)
  
但是，实际收件人是的 office365.contoso.net 其 MX 记录执行指向 Office 365:
  
![MX 指向 Office 365 必须收件人重写](media/10cf3245-9b50-475a-b655-d8a51f99d812.jpg)
  
因此，此消息可能经历收件人重写。
  
b） 第二，请务必区分收件人重写的常见的使用案例。如果您要重写的收件人域\*。 onmicrosoft.com，而是将其重写\*。 mail.onmicrosoft.com。
  
一旦您已经确定路由后面另一台服务器的最终的收件人域并收件人域的 MX 记录实际指向 Office 365 （如发布其 DNS 记录中），您可以继续禁用反欺骗。
  
请记住，您不想要禁用反欺骗如果域的路由路径中的第一个跃点是 Office 365 中，仅时隐藏一个或多个服务。
  
### <a name="how-to-disable-anti-spoofing"></a>如何禁用反欺骗

如果您已创建的防钓鱼策略，设置为 $false EnableAntispoofEnforcement 参数： 
  
```
$name = "<name of policy>"
Set-AntiphishPolicy -Identity $name -EnableAntiSpoofEnforcement $false 

```

如果您不知道策略 （或策略） 若要禁用的名称，则可以显示它们： 
  
```
Get-AntiphishPolicy | fl Name
```

如果您没有任何现有的防钓鱼策略，可以创建一个，然后禁用它 （即使您没有策略、 反欺骗，则仍应用; 在 2018年中更高版本、 将为您创建的默认策略和您然后可以而不是创建一个禁用的）.您将需要执行此操作在多个步骤： 
  
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
# Finally, scope the antiphishing policy to the domains
Set-AntiphishPolicy -Identity $name -EnableAntispoofEnforcement $false 

```

禁用反欺骗才可用 cmdlet 通过 (后面 Q2 2018 它将提供安全中&amp;合规性中心)。如果您没有访问 PowerShell，创建支持票证，从而。
  
请记住，这只应应用到经过间接路由时发送到 Office 365 的域。抵御诱惑因某些误报禁用反欺骗，它将从长远来看最好通过这些工作。
  
### <a name="information-for-individual-users"></a>各个用户的的信息

单个用户将仅限于它们与反欺骗安全提示的交互方式。但是，有几个您可以执行的操作来解决常见方案。
  
### <a name="common-scenario-1---mailbox-forwarding"></a>常见方案 #1-邮箱转接

如果您使用其他电子邮件服务，并将您的电子邮件转发给 Office 365 或 Outlook.com，您的电子邮件可能被标记为欺骗和收到红色安全提示。Office 365 和 Outlook.com 计划自动解决此问题转发器时 Outlook.com、 Office 365、 Gmail 或使用[弧协议](https://arc-spec.org)的任何其他服务之一。但是，部署该修补程序，直到用户应使用已连接帐户功能导入其邮件直接，而不是使用转接选项。
  
若要设置 Office 365 中的已连接帐户，在 Office 365 web 接口的右上角中选择齿轮图标\>邮件\>邮件\>帐户\>连接帐户。
  
![连接的 office 365-帐户选项](media/e8e841ca-8861-4d83-8506-2a0858c51010.jpg)
  
在 Outlook.com，该过程将齿轮图标\>选项\>邮件\>帐户\>连接帐户。
  
### <a name="common-scenario-2---discussion-lists"></a>常见方案 #2-讨论列出

讨论列表已知遇到问题，请使用反欺骗由于方式它们转发邮件和修改其内容，但保留从原始： 地址。
  
例如，假设您的电子邮件地址是用户 @ contoso.com，以及您感兴趣鸟监视并加入讨论列表 birdwatchers @ example.com。当一条消息发送到讨论列表中时，您可能发送这种方式：
  
**从：** John Doe \<@ contoso.com 的用户\> 
  
**到：** Birdwatcher 的讨论列表\<@ example.com birdwatchers\> 
  
**使用者：** 本周的蓝色 jays 顶部保持联系突出的绝佳查看 
  
任何人都要签出查看从保持联系突出本周？
  
当电子邮件列表收到邮件时，他们格式化的消息、 修改其内容，并重播上从许多不同的电子邮件接收器的参与者构成讨论列表的成员的其余部分。
  
**从：** John Doe \<@ contoso.com 的用户\> 
  
**到：** Birdwatcher 的讨论列表\<@ example.com birdwatchers\> 
  
**使用者：**[BIRDWATCHERS]本周的蓝色 jays 顶部保持联系突出的绝佳查看 
  
任何人都要签出查看从保持联系突出本周？
  
---
  
此消息发送到 Birdwatchers 讨论列表。您可以随时取消订阅。
  
在上文中，重播的消息具有相同的： 地址 （用户 @ contoso.com），但原始邮件已被修改通过将标签添加到主题行和到底部的邮件页脚。此类型的邮件修改共同点邮件列表，并可能会导致误报。
  
如果您或您的组织中的某人的邮件列表管理员，您可能能够将其配置为通过反欺骗检查。
  
- 检查在 DMARC.org 常见问题：[我操作邮件列表和我希望与 DMARC 互操作，应该怎样做？](https://dmarc.org/wiki/FAQ#I_operate_a_mailing_list_and_I_want_to_interoperate_with_DMARC.2C_what_should_I_do.3F)
    
- 阅读此博客文章处的说明：[邮件列表运算符来实现互操作 DMARC 以避免出现故障的提示](https://blogs.msdn.microsoft.com/tzink/2017/03/22/a-tip-for-mailing-list-operators-to-interoperate-with-dmarc-to-avoid-failures/)
    
- 请考虑要支持弧，请参阅您邮件列表服务器上安装更新[https://arc-spec.org](https://arc-spec.org/)
    
如果您没有所有权的邮件列表：
  
- 您可以请求邮件列表的 maintainer，以实现上面 （他们应已设置为邮件列表来自的域的电子邮件身份验证） 的选项之一
    
- 您可以在您的电子邮件客户端将邮件移动到收件箱中创建邮箱规则。您还可以请求组织的管理员设置允许规则，或覆盖为节所述管理合法的发件人发送未经身份验证的电子邮件
    
- 您可以使用 Office 365 创建邮件列表会将其视为合法覆盖创建支持票证从而
    
### <a name="other-scenarios"></a>其他方案

1. 如果这两个以上的常见方案适用于您的情况，为 false 的正整数后向 Microsoft 报告邮件。有关详细信息，请参阅部分[如何报告垃圾邮件或非垃圾邮件后向 Microsoft？](#how-can-i-report-spam-or-non-spam-messages-back-to-microsoft)本文后面。 
    
2. 您还可以联系可引发它与 Microsoft 支持票证，从而为您的电子邮件管理员。Microsoft 工程团队将调查为什么邮件被标记为欺骗。
    
3. 此外，如果您知道发件人是且确信它们不被恶意造假，您可能回发件人，指示它们从邮件服务器的身份验证不发送邮件答复。这有时会导致原始发件人将设置所需的电子邮件身份验证记录其 IT 管理员联系。
  
当足够发件人答复回域所有者它们应设置电子邮件身份验证记录时，它 spurs 它们采取操作。当 Microsoft 还适用于域所有者发布所需的记录时，它帮助更多时各个用户请求。
    
4. （可选） 将发件人添加到安全发件人列表。但请注意，如果钓鱼欺骗该帐户，它将传递到您的邮箱。因此，应谨慎使用此选项。
    
## <a name="how-senders-to-microsoft-should-prepare-for-anti-spoofing-protection"></a>向 Microsoft 的发件人应如何准备反欺骗保护

如果您是当前将邮件发送给 Microsoft，管理员 Office 365 或 Outlook.com 中，您应该确保您的电子邮件进行正确身份验证否则被标记为垃圾邮件或网络钓鱼。 
  
### <a name="customers-of-office-365"></a>Office 365 的客户

如果您是 Office 365 客户，并且您使用 Office 365 发送出站电子邮件：
  
- 为您的域，[设置 Office 365 为了帮助防止欺骗中的 SPF](https://technet.microsoft.com/en-us/library/dn789058%28v=exchg.150%29.aspx)
    
- 有关主域，[使用 DKIM 验证从您在 Office 365 中的自定义域发送出站电子邮件](https://technet.microsoft.com/en-us/library/mt695945%28v=exchg.150%29.aspx)
    
- [考虑 DMARC 记录设置](https://technet.microsoft.com/en-us/library/mt734386%28v=exchg.150%29.aspx)为您的域以确定您的合法发件人是谁 
    
Microsoft 不提供对每个 SPF、 DKIM，以及 DMARC 详细的实现准则。但是，没有大量联机发布的信息。还有第三方公司专用于帮助组织设置电子邮件身份验证记录。
  
### <a name="administrators-of-domains-that-are-not-office-365-customers"></a>不是 Office 365 客户的域的管理员

如果您是域管理员，但不是 Office 365 客户：
  
- 您应当设置 SPF 以发布您的域的发送 IP 地址，并还设置 DKIM （如果可用） 消息进行数字签名。您可能会考虑设置 DMARC 记录。
    
- 如果您有批量的发件人正在传送代表您的电子邮件，则应使用它们的方式发送电子邮件以便在从的发送域： 地址 （如果您属于） 与将传递 SPF 或 DMARC 域对齐。
    
- 如果您具有内部部署邮件服务器，或从软件作为服务提供程序，或从云承载的服务，如 Microsoft Azure、 GoDaddy、 机架、 Amazon Web 服务发送或类似，您应该确保已添加到您的 SPF 记录。
    
- 如果您是位于由 ISP 较小的域，您应设置根据说明您的 ISP 提供给您的 SPF 记录。大多数 Isp 提供这些类型的说明，并可在公司的支持页面上找到。
    
- 即使您已经不发布电子邮件之前，身份验证记录，并且它正常运行，您仍必须发布电子邮件身份验证记录，将发送给 Microsoft。这样，您在网络钓鱼抵御帮助并减少您向的组织获取 phished 的可能性。
    
### <a name="what-if-you-dont-know-who-sends-email-as-your-domain"></a>如果您不知道谁将作为您的域发送电子邮件？

许多域不发布 SPF 记录，因为它们不知道其所有发件人是谁。没关系，不需要知道谁能全部。相反，您应开始通过发布为您知道，尤其是您企业的通信设备的位置，并发布的非特定的 SPF 策略的 SPF 记录？ 所有：
  
example.com IN TXT"v = spf1 include:spf.example.com？ 所有"
  
非特定的 SPF 策略意味着，利用您公司的基础结构中的任何电子邮件将通过电子邮件身份验证在所有其他电子邮件接收器。来自您不知道有关的发件人的电子邮件将回退到 neutral，几乎相同发布根本没有 SPF 记录。
  
在发送到 Office 365 时，来自您的企业通信的电子邮件将被标记为经过身份验证，但来自您不了解的内容源的电子邮件可能仍被标记为欺骗 （具体取决于 Office 365 可以隐式验证）。但是，这仍是来自所有电子邮件被标记为欺骗 Office 365 的改进。
  
一旦您已变得入门 SPF 记录与一个回退的策略？ 所有，您可以逐步包括更发送基础结构，然后发布更严格的策略。 
  
### <a name="what-if-you-are-the-owner-of-a-mailing-list"></a>如果您是邮件列表的所有者？

请参阅[常见方案 #2-讨论列出](#common-scenario-2---discussion-lists)的部分。 
  
### <a name="what-if-you-are-an-infrastructure-provider-such-as-an-internet-service-provider-isp-email-service-provider-esp-or-cloud-hosting-service"></a>如果您将如 Internet 服务提供程序 (ISP)、 电子邮件服务提供程序 (ESP) 或云承载服务的基础结构提供程序。

如果主机域的电子邮件，并且其发送电子邮件，或提供可发送电子邮件的宿主基础结构，您应执行以下操作：
  
- 确保您的客户详细介绍要在其 SPF 记录中发布的文档
    
- 请考虑 DKIM 签名登录出站电子邮件中，即使客户不明确其进行设置 （与默认域登录）。您可以偶数 double 登录 （一次使用他们具有其进行设置，如果客户的域和第二次与贵公司的 DKIM 签名） DKIM 签名与电子邮件
    
不能保证向 Microsoft 可交付性，即使验证电子邮件来自您的平台，但至少可确保 Microsoft 不会不垃圾电子邮件，因为它不进行身份验证。围绕 Outlook.com 如何筛选电子邮件的详细信息，请参阅[Outlook.com 邮局主管页](https://postmaster.live.com/pm/postmaster.aspx)。
  
有关服务提供程序的最佳实践的详细信息，请参阅[M3AAWG 移动消息的最佳实践服务提供商](https://www.m3aawg.org/sites/default/files/M3AAWG-Mobile-Messaging-Best-Practices-Service-Providers-2015-08.pdf)。
  
## <a name="frequently-asked-questions"></a>常见问题解答

### <a name="why-is-microsoft-making-this-change"></a>Microsoft 为什么进行此更改？

由于影响网络钓鱼的攻击，和电子邮件身份验证已围绕 15 年以上，因为 Microsoft 认为，继续允许未经身份验证的电子邮件的风险大于丢失合法的电子邮件的风险。
  
### <a name="will-this-change-cause-legitimate-email-to-be-marked-as-spam"></a>此更改会导致合法的电子邮件标记为垃圾邮件？

首先，将某些标记为垃圾邮件的邮件。但是，一段时间，发件人将调整并且将然后对于大多数电子邮件路径可以忽略错误地标记为带欺骗性的消息的数量。
  
Microsoft 本身首先采用此功能之前将其部署到其客户的其余部分的几周。时出现在第一张、 逐步拒绝其中断。
  
### <a name="will-microsoft-bring-this-feature-to-outlookcom-and-non-advanced-threat-protection-customers-of-office-365"></a>将 Microsoft 置于此功能的 Office 365 Outlook.com 和非高级威胁保护客户？

Microsoft 的反欺骗技术已最初部署到其组织的 Office 365 企业 E5 订阅或已购买 Office 365 高级威胁保护 (ATP) 加载项为其订阅。从 2018 年 10 月，我们已扩展到以及具有 Exchange Online Protection (EOP) 的组织的保护。将来，我们可能为 Outlook.com 发布它。但是，如果我们这样做，可能不会应用如报告某些功能，并将覆盖自定义。
  
### <a name="how-can-i-report-spam-or-non-spam-messages-back-to-microsoft"></a>如何报告垃圾邮件或非垃圾邮件后向 Microsoft？

您可以使用[报告消息外接程序 Outlook](https://support.office.com/article/use-the-report-message-add-in-b5caa9f1-cdf3-4443-af8c-ff724ea719d2)，或者如果它不安装，[提交垃圾邮件、 非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](https://technet.microsoft.com/en-us/library/jj200769%28v=exchg.150%29.aspx)。
  
### <a name="im-a-domain-administrator-who-doesnt-know-who-all-my-senders-are"></a>我不知道我所有发件人是谁域管理员 ！

请参阅[不是 Office 365 客户的域的管理员](#administrators-of-domains-that-are-not-office-365-customers)。
  
### <a name="what-happens-if-i-disable-anti-spoofing-protection-for-my-organization-even-though-office-365-is-my-primary-filter"></a>如果，？ 我禁用反欺骗保护我的组织，即使 Office 365 是我主要筛选器

建议不要这因为您将会面临更错过网络钓鱼和垃圾邮件。不是所有网络钓鱼欺骗，而且不是所有欺骗将会都丢失。但是，您风险将高于启用反欺骗的客户。
  
### <a name="does-enabling-anti-spoofing-protection-mean-i-will-be-protected-from-all-phishing"></a>启用反欺骗保护意思我将从所有网络钓鱼保护？

遗憾的是，否，因为适应网络钓鱼程序将使用其他方法，例如泄露帐户或设置的免费服务帐户。但是，防钓鱼保护的工作方式得更好地检测这些其他类型的网络钓鱼方法，因为层是 Office 365 保护一起设计工作和彼此构建。
  
### <a name="do-other-large-email-receivers-block-unauthenticated-email"></a>其他大型电子邮件接收器阻止未经身份验证的电子邮件？

几乎所有大型电子邮件接收器实现传统 SPF、 DKIM 和 DMARC。某些接收器具有其他检查比那些标准，但少转为未经验证的 Office 365 阻止更严格的电子邮件并将其视为欺骗。但是，大部分行业变得更严格有关此特定类型的电子邮件，特别是由于网络钓鱼的问题。
  
### <a name="do-i-still-need-the-advanced-spam-filtering-option-enabled-for-spf-hard-fail-if-i-enable-anti-spoofing"></a>是否仍需要启用"SPF 硬失败"如果启用反欺骗高级垃圾邮件筛选选项？

否，因为反欺骗功能不仅认为 SPF 硬失败，但更广泛的条件，则不再需要此选项。如果您具有启用反欺骗并启用了 SPF 硬失败选项，您可能会获得更多误报。建议为垃圾邮件或网络钓鱼诈骗、 提供几乎没有任何其他捕获并相反生成主要误报禁用此功能。
  
### <a name="does-sender-rewriting-scheme-srs-help-fix-forwarded-email"></a>发件人重写方案 (SR) 帮助修复转发电子邮件？

SR 仅部分修复的问题的转发电子邮件。通过重写 SMTP 邮件从，SR 可以确保转发的邮件传递 SPF 下一个目标上。但是，由于反欺骗基于 From： 地址结合 MAIL FROM 或 DKIM 签名域 （或其他信号），它是不够以防止被标记为造假转发电子邮件。
  

