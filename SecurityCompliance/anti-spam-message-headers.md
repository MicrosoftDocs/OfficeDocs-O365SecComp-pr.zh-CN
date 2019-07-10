---
title: 反垃圾邮件邮件头
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Exchange Online Protection 扫描到入站电子邮件时，它会在每封邮件中插入" **X-Forefront-Antispam-Report**"标头。
ms.openlocfilehash: c6b6282e3c5bb1c6ae1e3be54c0d8fa6a6ce3fe3
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35598192"
---
# <a name="anti-spam-message-headers"></a>反垃圾邮件邮件头

Exchange Online Protection 扫描到入站电子邮件时，它会在每封邮件中插入" **X-Forefront-Antispam-Report**"标头。该邮件头中的这些字段有助于为管理员提供与邮件及其处理方式有关的信息。" **X-Microsoft-Antispam**"标头中的字段提供批量邮件和网络钓鱼的更多信息。除这两种标头外，Exchange Online Protection 还会在" **Authentication-results**"标头中为每封邮件插入其处理的电子邮件身份验证结果。

有关如何查看各种电子邮件客户端中的电子邮件头的信息，请参阅[邮件头分析器](https://go.microsoft.com/fwlink/p/?LinkId=306583)。 
  
> [!TIP]
>  您可以将邮件头的内容复制并粘贴到[邮件分析器](https://testconnectivity.microsoft.com/?tabid=mha)工具中。 此工具有助于分析标头, 并将其放在更 readible 的格式中。
  
## <a name="x-forefront-antispam-report-message-header-fields"></a>X-Forefront-Antispam-Report 邮件标头字段

获取邮件头信息后，搜索“**X-Forefront-Antispam-Report**”，然后查找这些字段。此标头中的其他字段专供 Microsoft 反垃圾邮件团队用于进行诊断。

|**标头字段**|**描述**|
|:-----|:-----|
|CIP：[IP 地址]|连接 IP 地址。在连接筛选器中创建 IP 允许列表或 IP 阻止列表时，您可能需要指定此 IP 地址。有关详细信息，请参阅[配置连接筛选器策略](configure-the-connection-filter-policy.md)。  |
|CTRY|邮件与服务连接时所处的国家/地区。该值由连接 IP 地址决定，它可能与原始发送 IP 地址不同。|
|LANG|邮件的编写语言，由国家/地区代码指定（例如，俄语的代码为 ru_RU）。|
|SCL|邮件的垃圾邮件可信度 (SCL) 值。有关这些值的详细解释信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。  |
|PCL|邮件的网络钓鱼可能性等级 (PCL) 值。|
|SRV:BULK|邮件被标识为批量电子邮件。如果" **阻止所有批量电子邮件高级垃圾邮件筛选选项**"已启用，则相应的邮件会被标记为垃圾邮件。如果未启用，则该邮件只会在剩余筛选规则确定邮件是垃圾邮件时才被标记为垃圾邮件。  |
|SFV:SFE|由于邮件发送自个人的安全发件人列表上的地址，因此邮件会跳过筛选并得以通过。|
|SFV:BLK|由于邮件发送自个人的阻止的发件人名单上的地址，因此邮件会跳过筛选并得以阻止。  <br/> **提示**: 有关最终用户如何创建安全和阻止的发件人列表的详细信息, 请参阅[阻止或允许 (垃圾邮件设置)](https://go.microsoft.com/fwlink/p/?LinkId=294862) (outlook 网页版) 和[垃圾邮件筛选器](https://go.microsoft.com/fwlink/p/?LinkId=270065)(outlook) 概述。|
|IPV:CAL|邮件已获得垃圾邮件筛选器的允许，因为 IP 地址已在连接筛选器的 IP 允许列表中指定。|
|IPV:NLI|IP 地址没有在任何 IP 信誉列表中列出。|
|SFV:SPM|邮件由内容筛选器标记为垃圾邮件。|
|SFV:SKS|在内容筛选器处理之前，邮件被标记为垃圾邮件。 这包括邮件与邮件流规则匹配的邮件 (也称为传输规则), 以自动将其标记为垃圾邮件, 并绕过所有其他筛选。|
|SFV:SKA|The message skipped filtering and was delivered to the inbox because it matched an allow list in the spam filter policy, such as the **Sender allow** list.|
|SFV:SKB|邮件被标记为垃圾邮件，因为它符合垃圾邮件筛选器策略中的阻止列表，例如" **发件人阻止**"列表。|
|SFV:SKN|在内容筛选器处理之前，邮件被标记为非垃圾邮件。 这包括邮件与邮件流规则匹配的邮件, 以自动将其标记为非垃圾邮件, 并绕过所有其他筛选。|
|SFV:SKI|与 SFV:SKN 类似，由于其他原因而导致邮件跳过筛选，例如该邮件是租户内的组织间电子邮件。|
|SFV:SKQ|邮件从隔离区释放，并发送给目标收件人。|
|SFV:NSPM|邮件被标记为非垃圾邮件并发送给预期收件人。|
|H:[helostring]|连接邮件服务器的 HELO 或 EHLO 字符串。|
|PTR:[ReverseDNS]|发送 IP 地址的 PTR 记录或指针记录，亦称为反向 DNS 地址。|
|SFTY|该邮件被标识为 "网络钓鱼", 也将使用以下值之一进行标记: <br/>• 9.1: 默认值。 邮件包含仿冒 URL, 可能包含其他仿冒内容, 或者在将邮件中继到 Office 365 之前, 另一个邮件筛选器 (如本地版本的 Exchange Server) 已将其标记为 "仿冒"。 <br/>• 9.11: 邮件未通过反欺骗检查, 发件人: 头中的发送域与接收域相同, 或与之对齐, 或者是同一个组织的一部分。 这表示将向邮件中添加组织内欺骗安全提示。 <br/>• 9.19: 邮件未能通过域模拟检查, 其中发送域尝试模拟收件人拥有的域, 或由反网络钓鱼策略保护的自定义域。 这表示将向邮件中添加模拟安全提示 (如果通过反网络钓鱼策略启用)。 <br/>• 9.20: 邮件失败用户模拟检查, 其中发送用户试图模拟收件人组织内的用户, 或由反网络钓鱼策略保护的自定义用户。 这表示将向邮件中添加模拟安全提示 (如果通过反网络钓鱼策略启用)。 <br/>• 9.21: 邮件未能通过反欺骗检查, 发件人: 头中的发送域不会进行身份验证, 并且来自外部域。 与 CompAuth 结合使用 (请参阅身份验证-结果)。 <br/>• 9.22: 与9.21 相同, 不同之处在于用户的安全发件人已被覆盖。 <br/>• 9.23: 与9.22 相同, 不同之处在于组织具有允许的已覆盖发件人或域。 <br/>• 9.24: 与9.23 相同, 不同之处在于用户具有替代的 Exchange 邮件流规则。|
|X-CustomSpam：[ASFOption]|邮件符合高级垃圾邮件筛选选项。 For example, **X-CustomSpam: Image links to remote sites** denotes that the **Image links to remote sites** ASF option was matched. 若要了解为每个特定 ASF 选项添加的 X 标头文本, 请参阅[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)。|
   
## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft-Antispam 邮件标头字段

下表描述了“**X-Microsoft-Antispam**”邮件头中的有用字段。此标头中的其他字段专供 Microsoft 反垃圾邮件团队用于进行诊断。
  
|**标头字段**|**说明**|
|:-----|:-----|
|BCL|邮件的批量投诉级别 (BCL)。有关详细信息，请参阅[批量投诉级别值](bulk-complaint-level-values.md)。  |
|PCL|邮件的网络钓鱼可能性等级 (PCL) 显示这是否为网络钓鱼邮件。 此状态会以下列其中一个数值返回： <br/>• **0-3**: 邮件的内容不太可能是网络钓鱼。 <br/>• **4-8**: 邮件的内容可能是网络钓鱼。 <br/>• **-9990**: (仅限 Exchange Online Protection) 邮件的内容可能是网络钓鱼。  <br/>  这些值用于确定你的电子邮件客户端对这些邮件采取什么操作。 例如, Outlook 使用 PCL 标记来阻止可疑邮件的内容。 有关网络钓鱼和 Outlook 如何处理网络钓鱼邮件的详细信息，请参阅 [打开或关闭电子邮件中的链接](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8)。|
   
## <a name="authentication-results-message-header"></a>“Authentication-results”邮件头

邮件服务器收到电子邮件后，Office 365 将基于 SPF、DKIM 或 DMARC 将检查结果记录或标记在“**Authentication-results**”邮件头中。
  
### <a name="check-stamp-syntax-and-examples"></a>检查标记语法和示例

以下语法示例演示了 Office 365 应用于每封电子邮件（在由我们的邮件服务器接收时执行电子邮件身份验证检查）的邮件头的部分文本“标记”。此标记已添加到“**Authentication-Results**”标头。
  
**语法：SPF 检查标记**
  
以下语法适用于 SPF。
  
```
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

**示例：SPF 检查标记**
  
```
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

**语法：DKIM 检查标记**
  
以下语法适用于 DKIMF。
  
```
dkim=<pass|fail (reason)|none> header.d=<domain>
```

**示例：DKIM 检查标记**
  
```
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

**语法：DMARC 检查标记**
  
以下语法适用于 DMARC。
  
```
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

**示例：DMARC 检查标记**
  
```
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Office 365 电子邮件身份验证使用的“Authentication-results”邮件头字段

本表描述了每封电子邮件身份验证检查的字段和可能的值。
  
|**标头字段**|**说明**|
|:-----|:-----|
|spf|说明邮件的 SPF 检查结果。可能的值包括：  <br/>• **pass (IP 地址)**: 指示已传递邮件的 SPF 检查, 并包括发件人的 IP 地址。 已授权客户端代表发件人的域发送或中继电子邮件。 <br/>•**故障 (IP 地址)**: 指示邮件的 SPF 检查失败, 并包括发件人的 IP 地址。 这有时称为_硬失败_。 <br/>• **softfail (原因)**: 指示 SPF 记录已将主机指定为不允许发送但处于转换状态。 <br/>•无**特定**说明: 指示 SPF 记录已明确声明它不会断言 IP 地址是否已获得授权。 <br/>•**无**: 指示域没有 SPF 记录或 spf 记录未计算结果。 <br/>• **temperror 出现**: 指示发生了可能是暂时临时错误的错误, 例如, DNS 错误。 无需任何管理员操作，稍后再次尝试可能 就会成功。 <br/>• **permerror**: 指示发生了永久性错误。 例如，域的 SPF 记录格式非常不规范时会出现此值。|
|5321.mailfrom|包含发送邮件的源域。此电子邮件的任何错误都将发送到负责此域的 postmaster 或实体。在邮件信封上有时也称其为"5321.MailFrom 地址"或"反向路径地址"。|
|dkim|说明邮件的 DKIM 检查结果。可能的值包括：  <br/>• **pass**: 指示对传递的邮件的 DKIM 检查。 <br/>•**失败 (原因)**: 指示邮件的 DKIM 检查失败以及原因。 例如，如果邮件未签名或签名未经验证。 <br/>•**无**: 指示邮件未签名。 这可能表示或不表示域存在 DKIM 记录或 DKIM 记录未生成结果，仅表示该邮件未签名。|
|头. d|DKIM 签名中标识的域（如有）。这指的是 针对公钥查询的域。|
|dmarc|说明邮件的 DMARC 检查结果。可能的值包括：  <br/>• **pass**: 指示对传递的邮件的 DMARC 检查。 <br/>•**失败**: 指示邮件的 DMARC 检查失败。 <br/>• **bestguesspass**: 指示域不存在任何 DMARC TXT 记录, 但如果其中一个存在, 则邮件的 DMARC 检查将通过。 这是因为 5321.MailFrom 地址中的域与 5322.From 地址中的域相匹配。 <br/>•**无**: 指示 DNS 中不存在发送域的任何 DKIM TXT 记录。|
|action|指示垃圾邮件筛选器基于 DMARC 检查结果执行的操作。例如：  <br/>• **permerror**: 在 DMARC 评估期间发生永久错误, 例如, 在 DNS 中遇到格式不正确的 DMARC TXT 记录。 尝试重新发送此邮件不太可能产生不同的结果。 你反而可能需要联系域的所有者，以解决该问题。 <br/>• **temperror 出现**: DMARC 评估期间发生临时错误。 你可以请求发件人稍后重新发送邮件，以正确处理电子邮件。 <br/>• **oreject**或**o. 拒绝**: 代表替代拒绝。 在这种情况下，Office 365 在从 DMARC TXT 记录的策略为 p=reject 的域中接收未通过 DMARC 检查的邮件时使用此操作。 Office 365 将该邮件标记为垃圾邮件，而不是删除或拒绝该邮件。 有关这样配置 Office 365 的原因的详细信息，请参阅 [Office 365 如何处理未通过 DMARC 的入站电子邮件](use-dmarc-to-validate-email.md#inbounddmarcfail)。 <br/>• **pct**: 指明不传递 DMARC 的邮件百分比小于 100% 的邮件仍将传递。 这表示邮件未通过 DMARC 且已将策略设置为隔离，但 pct 字段未设置为 100% 且系统根据每个特定域的策略随机决定不执行 DMARC 操作。 <br/>•**百分比拒绝**: 指示仍将传递小于 100% 且未传递 DMARC 的邮件的百分比。 这表示邮件未通过 DMARC 且已将策略设置为拒绝，但 pct 字段未设置为 100% 且系统根据每个特定域的策略随机决定不执行 DMARC 操作。|
|标头。从|电子邮件标头中发件人地址的域。 这有时称为 " _5322.from_地址"。|
|compauth|复合身份验证结果。 由 Office 365 用于将多种类型的身份验证 (如 SPF、DKIM、DMARC 或邮件的任何其他部分) 结合使用, 以确定是否对邮件进行身份验证。 使用 From: 域作为评估基础。|
|在于|复合身份验证通过或失败的原因。 Reason 的值由三个数字组成: <br/>• **000**: 邮件显式失败的身份验证。 例如, 邮件收到 DMARC 失败, 并出现 "隔离" 或 "拒绝" 操作。 <br/>• **001**: 邮件隐式身份验证失败, 且发送域未发布身份验证策略。 例如, DMARC 的策略为 p = none。 <br/>• **1xx**: 邮件已通过身份验证。 第二个两位数是 Office 365 使用的内部代码。 <br/>• **2xx**: 邮件软传递身份验证。 第二个两位数是 Office 365 使用的内部代码。 <br/>• **3xx**: 不检查邮件的复合身份验证。 <br/>• **4xx**: 邮件绕过复合身份验证。 第二个两位数是 Office 365 使用的内部代码。|
