---
title: 反垃圾邮件邮件头
ms.author: krowley
author: kccross
manager: laurawi
ms.date: ''
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
description: Exchange Online Protection 扫描到入站电子邮件时，它会在每封邮件中插入" **X-Forefront-Antispam-Report**"标头。
ms.openlocfilehash: 5632aa28a0d23186e6a36fdf63f7968322c93e39
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29686442"
---
# <a name="anti-spam-message-headers"></a>反垃圾邮件邮件头

Exchange Online Protection 扫描到入站电子邮件时，它会在每封邮件中插入" **X-Forefront-Antispam-Report**"标头。该邮件头中的这些字段有助于为管理员提供与邮件及其处理方式有关的信息。" **X-Microsoft-Antispam**"标头中的字段提供批量邮件和网络钓鱼的更多信息。除这两种标头外，Exchange Online Protection 还会在" **Authentication-results**"标头中为每封邮件插入其处理的电子邮件身份验证结果。
  
> [!TIP]
> 有关如何查看各种电子邮件客户端中的电子邮件头的信息，请参阅[邮件头分析器](https://go.microsoft.com/fwlink/p/?LinkId=306583)。你可以将邮件头的内容复制并粘贴到[邮件头分析器](https://testconnectivity.microsoft.com/?tabid=mha)工具中。当你在 Exchange 管理中心隔离邮箱中选择一封邮件时，" **查看邮件头**"链接也使你可以轻松地将邮件头文本复制并粘贴到工具中。进入邮件头分析器工具后，单击" **分析标头**"以检索关于标头的信息。
  
## <a name="x-forefront-antispam-report-message-header-fields"></a>X-Forefront-Antispam-Report 邮件标头字段
<a name="sectionSection0"> </a>

获取邮件头信息后，搜索" **X-Forefront-Antispam-Report**"，然后查找这些字段。此标头中的其他字段专供 Microsoft 反垃圾邮件团队用于进行诊断。

|**标头字段**|**描述**|
|:-----|:-----|
|CIP：[IP 地址]|连接 IP 地址。在连接筛选器中创建 IP 允许列表或 IP 阻止列表时，您可能需要指定此 IP 地址。有关详细信息，请参阅[配置连接筛选器策略](configure-the-connection-filter-policy.md)。  |
|CTRY|邮件与服务连接时所处的国家/地区。该值由连接 IP 地址决定，它可能与原始发送 IP 地址不同。|
|LANG|邮件的编写语言，由国家/地区代码指定（例如，俄语的代码为 ru_RU）。|
|SCL|邮件的垃圾邮件可信度 (SCL) 值。有关这些值的详细解释信息，请参阅[垃圾邮件可信度](spam-confidence-levels.md)。  |
|PCL|邮件的网络钓鱼可能性等级 (PCL) 值。 |
|SRV:BULK|邮件被标识为批量电子邮件。如果" **阻止所有批量电子邮件高级垃圾邮件筛选选项**"已启用，则相应的邮件会被标记为垃圾邮件。如果未启用，则该邮件只会在剩余筛选规则确定邮件是垃圾邮件时才被标记为垃圾邮件。  |
|SFV:SFE|由于邮件发送自个人的安全发件人列表上的地址，因此邮件会跳过筛选并得以通过。|
|SFV:BLK|由于邮件发送自个人的阻止的发件人名单上的地址，因此邮件会跳过筛选并得以阻止。  <br/> **提示**： 有关如何最终用户可以创建白名单和黑名单发件人列表的详细信息，请参阅[阻止或允许 （垃圾邮件设置）](https://go.microsoft.com/fwlink/p/?LinkId=294862) (在 web 上的 Outlook) 和[垃圾邮件筛选器的概述](https://go.microsoft.com/fwlink/p/?LinkId=270065)(Outlook)。|
|IPV:CAL|邮件已获得垃圾邮件筛选器的允许，因为 IP 地址已在连接筛选器的 IP 允许列表中指定。|
|IPV:NLI|IP 地址没有在任何 IP 信誉列表中列出。|
|SFV:SPM|邮件由内容筛选器标记为垃圾邮件。|
|SFV:SKS|在内容筛选器处理之前，邮件被标记为垃圾邮件。这包括符合以下传输规则条件的邮件：自动将邮件标记为垃圾邮件并规避其他所有筛选。|
|SFV:SKA|邮件已跳过筛选并已传递到收件箱，因为它匹配垃圾邮件筛选器策略中，如**发件人允许**列表中的允许列表。|
|SFV:SKB|邮件被标记为垃圾邮件，因为它符合垃圾邮件筛选器策略中的阻止列表，例如" **发件人阻止**"列表。|
|SFV:SKN|在内容筛选器处理之前，邮件被标记为非垃圾邮件。这包括符合以下传输规则条件的邮件：自动将邮件标记为非垃圾邮件并绕过其他所有筛选。|
|SFV:SKI|与 SFV:SKN 类似，由于其他原因而导致邮件跳过筛选，例如该邮件是租户内的组织间电子邮件。|
|SFV:SKQ|邮件从隔离区释放，并发送给目标收件人。|
|SFV:NSPM|邮件被标记为非垃圾邮件并发送给预期收件人。|
|H:[helostring]|连接邮件服务器的 HELO 或 EHLO 字符串。|
|PTR:[ReverseDNS]|发送 IP 地址的 PTR 记录或指针记录，亦称为反向 DNS 地址。|
|SFTY|邮件标识为网络钓鱼并也将具有下列值之一标记： <br/>• 9.1： 默认值。邮件包含网络钓鱼 URL、 可能包含其他仿冒内容，或可能已被标记为网络钓鱼另一个邮件筛选器，如 Exchange 服务器的内部部署版本中继到 Office 365 邮件之前。 <br/>• 9.11： 失败的消息反欺骗检查其中在从的发送域： 页眉相同，或与，或属于同一组织为接收域。这指示组织内欺骗安全提示将添加到邮件。 <br/>• 9.19： 失败的消息的发送域尝试模拟归接收器的域或自定义受防钓鱼策略的域的域模拟检查。这指示模拟安全提示将添加到邮件中，如果启用通过反 Phishig 策略。 <br/>• 9.20： 失败的消息用户模拟检查发送用户尝试模拟接收器组织内的用户或防钓鱼策略受保护的自定义的用户的位置。这指示模拟安全提示将添加到邮件中，如果启用通过反 Phishig 策略。 <br/>• 9.21： 反欺骗检查和发送域在从失败的消息： 页眉的身份验证不和来自外部域。与 CompAuth 结合使用 （请参阅身份验证结果）。 <br/>• 9.22： 相同 9.21，只不过用户具有已被重写安全发件人。 <br/>• 9.23： 相同 9.22，只不过组织具有允许的发件人或域已被重写的。 <br/>• 9.24： 相同 9.23，只不过用户具有已被重写 Exchange 邮件流规则。|
|X-CustomSpam：[ASFOption]|邮件匹配高级垃圾邮件筛选选项。例如， **X-customspam： 到远程站点的链接图像**表示**到远程站点的图像链接**ASF 选项是否相匹配。若要找出哪些 X 标头文本被添加为每个特定 ASF 选项，请参阅[高级垃圾邮件筛选选项](advanced-spam-filtering-asf-options.md)。|
   
## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft-Antispam 邮件标头字段
<a name="sectionSection1"> </a>

下表描述了" **X-Microsoft-Antispam**"邮件头中的有用字段。此标头中的其他字段专供 Microsoft 反垃圾邮件团队用于进行诊断。
  
|**标头字段**|**说明**|
|:-----|:-----|
|BCL|邮件的批量投诉级别 (BCL)。有关详细信息，请参阅[批量投诉级别值](bulk-complaint-level-values.md)。  |
|PCL|网络钓鱼可信度级别 (PCL) 的消息，指示是否网络钓鱼邮件。可为以下数值的一个返回此状态：<br/>• **0-3**： 消息的内容不可能网络钓鱼。 <br/>• **4-8**： 消息的内容很可能是网络钓鱼。 <br/>• **-9990**: (仅限 Exchange Online Protection) 消息的内容很可能是网络钓鱼。  <br/>  值用于确定您的电子邮件客户端承担邮件的操作。例如，Outlook 使用 PCL 戳阻止的可疑邮件内容。有关网络钓鱼和 Outlook 如何处理网络钓鱼邮件的详细信息，请参阅[打开或关闭电子邮件中的链接](https://support.office.com/article/2D79B907-93B6-4774-82E6-1F0385CF20F8)。|
   
## <a name="authentication-results-message-header"></a>"Authentication-results"邮件头
<a name="sectionSection2"> </a>

邮件服务器收到电子邮件后，Office 365 将基于 SPF、DKIM 或 DMARC 将检查结果记录或标记在" **Authentication-results**"邮件头中。
  
### <a name="check-stamp-syntax-and-examples"></a>检查标记语法和示例
<a name="referenceSPFstamp"> </a>

以下语法示例演示了 Office 365 应用于每封电子邮件（在由我们的邮件服务器接收时执行电子邮件身份验证检查）的邮件头的部分文本"标记"。此标记已添加到" **Authentication-Results**"标头。
  
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

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Office 365 电子邮件身份验证使用的"Authentication-results"邮件头字段
<a name="referenceSPFstamp"> </a>

本表描述了每封电子邮件身份验证检查的字段和可能的值。
  
|**标头字段**|**说明**|
|:-----|:-----|
|spf|说明邮件的 SPF 检查结果。可能的值包括：  <br/>•**传递 （IP 地址）**： 指示邮件传递 SPF 检查并包含发件人的 IP 地址。客户端授权发送，或中继代表发件人的域的电子邮件。<br/>•**失败 （IP 地址）**： 指示对失败的消息的 SPF 检查并包含发件人的 IP 地址。有时称为_硬失败_。<br/>• **softfail （原因）**： 指示 SPF 记录已指定为未被允许发送的主机，但正在转换。 <br/>•**中性**： 指示 SPF 记录具有明确规定的不断言是否授权的 IP 地址。 <br/>•**无**： 指示域没有 SPF 记录或 SPF 记录不计算结果为。 <br/>• **temperror**： 指示出现的错误可能是临时性质，例如，DNS 错误。尝试以后可能会成功不需要任何管理员操作。<br/>• **permerror**： 指示永久错误发生。例如，域具有格式不正确的 SPF 记录时，发生这种情况。|
|smtp.mailfrom|包含发送邮件的源域。此电子邮件的任何错误都将发送到负责此域的 postmaster 或实体。在邮件信封上有时也称其为"5321.MailFrom 地址"或"反向路径地址"。|
|dkim|说明邮件的 DKIM 检查结果。可能的值包括：  <br/>•**传递**： 指示邮件传递 DKIM 检查。 <br/>•**失败 （原因）**： 指示失败的消息 DKIM 检查及使用原因。例如，如果未签名邮件或不验证签名。<br/>•**无**： 指示邮件未签名。这可能也可能不表示域中具有 DKIM 记录或者 DKIM 记录不计算为结果，仅将此消息未签名。|
|header.d|DKIM 签名中标识的域（如有）。这指的是 针对公钥查询的域。|
|dmarc|说明邮件的 DMARC 检查结果。可能的值包括：  <br/>•**传递**： 指示邮件传递 DMARC 检查。 <br/>•**失败**： 指示 DMARC 检查失败的邮件。 <br/>• **bestguesspass**： 指示域没有 DMARC TXT 记录存在，但如果一个具有已存在，将传递邮件 DMARC 检查。这是因为 5321.MailFrom 地址中的域匹配 5322.From 地址中的域。<br/>•**无**： 指示没有 DKIM TXT 记录存在 DNS 中发送的域。|
|action|指示垃圾邮件筛选器基于 DMARC 检查结果执行的操作。例如：  <br/>• **permerror**: 永久过程中出错 DMARC 评估，如遇到格式不正确的 DMARC TXT 记录在 DNS 中。尝试重新发送此邮件不可能结尾不同的结果。相反，您可能需要联系以解决问题的域的所有者。<br/>• **temperror**: 临时过程中出错 DMARC 评估。您可能能够请求发件人重新发送更高版本才能正确处理电子邮件的邮件。<br/>• **oreject**或**o.reject**： 代表重写拒绝。在此案例 Office 365 使用此操作时收到一条消息，失败 DMARC 检查从其 DMARC TXT 记录具有的 p 的策略的域 = 拒绝。而不是删除或拒绝该邮件，Office 365 将邮件标记为垃圾邮件。为什么这种方式配置 Office 365 的详细信息，请参阅[Office 365 如何处理入站电子邮件的失败 DMARC](use-dmarc-to-validate-email.md#inbounddmarcfail)。<br/>• **pct.quarantine**： 指示百分比小于 100%的未传递 DMARC 的消息将被仍然传递。这意味着失败的消息的 DMARC 策略设置为隔离，但百分比域未设置为 100%和系统随机确定不应用 DMARC 操作，按照指定的域策略。<br/>• **pct.reject**： 指示百分比小于 100%的未传递 DMARC 的消息将被仍然传递。这意味着失败的消息的 DMARC 策略设置为拒绝，但百分比域未设置为 100%和系统随机确定不应用 DMARC 操作，按照指定的域策略。|
|header.from|发件人地址的电子邮件邮件头中的域。有时称为_5322.From_地址。|
|compauth|复合身份验证结果。由 Office 365 用于组合多个类型的身份验证，如 SPF、 DKIM、 DMARC 或任何其他部件的邮件以确定对邮件进行身份验证。使用 From： 域作为评估的基础。|
|原因|原因复合身份验证通过或失败。原因的值由三个数字组成：<br/>• **000**： 显式失败的身份验证的消息。例如，消息接收的隔离或拒绝操作 DMARC 失败。<br/>• **001**： 隐式失败的身份验证的消息和发送域未发布身份验证策略。例如，p DMARC 策略 = none。<br/>• **1xx**： 邮件传递身份验证。两个数字是内部使用的 Office 365 的代码。<br/>• **2xx**： 消息软传递身份验证。两个数字是内部使用的 Office 365 的代码。<br/>• **3xx**： 邮件未签复合身份验证。 <br/>• **4xx**： 的消息被忽略复合身份验证。两个数字是内部使用的 Office 365 的代码。|
