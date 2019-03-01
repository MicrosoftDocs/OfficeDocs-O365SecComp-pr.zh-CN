---
title: 反垃圾邮件保护常见问题解答
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c534a35d-b121-45da-9d0a-ce738ce51fce
ms.collection:
- M365-security-compliance
description: 本主题提供了有关反垃圾邮件保护的常见问题和解答。 解答适用于 Microsoft Exchange Online 和 Exchange Online Protection (EOP) 客户。
ms.openlocfilehash: 47ab5202e4f20bbb8cdcf1d83987b0c0c20e8f29
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341673"
---
# <a name="anti-spam-protection-faq"></a>反垃圾邮件保护常见问题解答

本主题提供了有关反垃圾邮件保护的常见问题和解答。 解答适用于 Microsoft Exchange Online 和 Exchange Online Protection (EOP) 客户。 
  
> [!TIP]
> 有关安全发件人和阻止发件人列表的问题和解答, 请参阅[Exchange Online 中的安全发件人和阻止发件人列表](safe-sender-and-blocked-sender-lists-faq.md)。有关隔离的问题和解答, 请参阅[隔离 FAQ](quarantine-faq.md)。 
  
 **问：默认情况下，如何处理检测到的垃圾邮件？**
  
A. **对于入站邮件：** 大部分垃圾邮件都是通过基于发件人 IP 地址的连接筛选检测到的。 然后，服务会检查邮件内容。 默认情况下，内容筛选的垃圾邮件会发送到发件人的垃圾邮件文件夹。 可以更改此操作。 例如，可以选择将垃圾邮件发送到隔离区，而不是配置内容筛选策略。 
  
> [!IMPORTANT]
> 对于 EOP 独立客户: 为了确保 "**将邮件移动到垃圾邮件文件夹**" 操作可用于内部部署邮箱, 您必须在您的本地服务器上配置两个 Exchange 邮件流规则 (也称为传输规则), 以检测由 EOP 添加的垃圾邮件头。有关详细信息, 请参阅[确保垃圾邮件已路由到每个用户的 "垃圾邮件" 文件夹](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 
  
 **对于出站邮件：** 邮件要么通过高风险传递池进行路由，要么被退回、未传递。不管是哪种情况，发件人都会收到一封告知其邮件未传递的传递状态通知 (DSN) 邮件。 
  
 **问：什么是零日垃圾邮件变体，该服务将如何处理它？**
  
一天: 零天垃圾邮件变种是指第一代未知的垃圾邮件, 即从未捕获或分析的垃圾邮件, 因此我们的垃圾邮件内容筛选器尚未提供任何可用于检测到的信息。由垃圾邮件分析员捕获和分析零天的垃圾邮件示例后, 如果它满足垃圾邮件分类标准, 我们的垃圾邮件内容筛选器将进行更新以进行检测, 并且不再被视为 "零天"。(**注意:** 如果收到的邮件可能是零天垃圾邮件变种, 为了帮助我们改进服务, 请使用将[垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件中所述的方法之一提交给 microsoft 以进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。)
  
 **问：我需要配置用于提供反垃圾邮件保护的服务吗？**
  
答：在您注册服务和添加域之后，反垃圾邮件筛选通过默认反垃圾邮件策略在全公司自动启用。 无需进行任何其他配置，即可优化默认策略，为您提供保护（除了上文提及的针对 EOP 独立客户的例外情况以外）。 作为管理员，您可以编辑默认反垃圾邮件策略，以便最好地满足贵组织的需求。 更精确地讲，您也可以创建自定义内容筛选策略，并将其应用到特定的用户、组或者组织中的域。 自定义策略的优先级总是高于默认策略，但您可以更改自定义策略的优先级（即运行顺序）。
  
有关配置反垃圾邮件策略的详细信息，请参阅以下主题：
  
[配置连接筛选器策略](configure-the-connection-filter-policy.md)
  
[配置垃圾邮件筛选器策略](configure-your-spam-filter-policies.md)
  
[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)
  
 **问：如果我对一个反垃圾邮件策略进行了更改，更改保存之后需要多久才会生效？**
  
答：可能需要 1 小时，更改才会生效。
  
 **问：批量电子邮件筛选会自动启用吗？**
  
。默认情况下, 为新客户启用**批量邮件**高级垃圾邮件筛选选项。对于已迁移的客户, 此设置将与您的 FOPE 配置相匹配。有关批量电子邮件的详细信息, 请参阅[垃圾邮件和批量电子邮件之间有何区别？](what-s-the-difference-between-junk-email-and-bulk-email.md)
  
 **问：该服务是否提供 URL 筛选？**
  
答：提供，该服务具有可检查邮件内的 URL 的 URL 筛选器。 如果检测到与已知垃圾邮件或恶意内容相关联的 URL，则将该邮件标记为垃圾邮件。
  
 **问：客户如何使用此服务将假负（垃圾邮件）和误报（非垃圾邮件）邮件发送到 Microsoft？**
  
在几个方面, 可以将垃圾邮件和非垃圾邮件提交给 Microsoft 进行分析。有关详细信息, 请参阅[将垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。 
  
 **问：我可以获取垃圾邮件报告吗？**
  
答：可以，例如，您可以在 Office 365 管理中心中获取垃圾邮件检测报告。 此报告将垃圾邮件数量显示为唯一邮件的计数。 有关报告的详细信息，请参阅下列链接：
  
exchange online 客户: [exchange online 中的监视、报告和邮件跟踪](http://technet.microsoft.com/library/87bdeeae-bd80-4a3b-95c5-62fbaf97c2e8.aspx)
  
exchange online protection 客户: [exchange online protection 中的报告和邮件跟踪](eop/reporting-and-message-trace-in-exchange-online-protection.md)
  
 **问：有人发送一封邮件给我，但是我找不到它。 我怀疑此邮件可能被检测为垃圾邮件了。 有什么工具可以让我找到这封邮件吗？**
  
答：有的，邮件跟踪工具可以使您在电子邮件通过服务时跟踪它们，以了解所发生的情况。 有关如何使用邮件跟踪工具找到邮件被标识为垃圾邮件的原因的详细信息，请参阅[邮件被标记为垃圾邮件？](http://technet.microsoft.com/library/aa49e3f9-a5b1-4410-aac2-ddbbf3f5bfb2.aspx#BKMB_Whywasamessagemarkedasspam)
  
 **问：如果我的用户发送出站垃圾邮件，服务将会限制（速率限制）我的邮件吗？**
  
A.如果通过服务发送自用户的超过一半的邮件是在某段时间范围内（例如，每小时）发送的，则邮件被 Office 365 确定为垃圾邮件，该用户将被阻止发送邮件。大多数情况下，如果出站邮件确定为垃圾邮件，将会通过高风险传送池路由，这会降低正常的出站 IP 池添加至阻止列表的可能性。
  
当发件人被阻止发送出站垃圾邮件时，您可以发送通知到一个特定的电子邮件地址。 有关此设置的详细信息，请参阅[配置出站垃圾邮件策略](configure-the-outbound-spam-policy.md)。
  
 **问：是否可以与 Exchange Online 同时使用第三方反垃圾邮件和反恶意软件提供程序？**
  
答：可以，您可以配置另一个垃圾邮件和恶意软件筛选服务来保护 Exchange Online 邮箱。 要对入站邮件执行此操作，您应通过将 MX 记录更改为指向第三方提供程序来将电子邮件重定向到第三方提供程序，然后将邮件重定向到 EOP 进行其他处理。 要对出站邮件执行此操作，请将邮件传递目标配置为第三方提供程序（智能主机），如[Scenario: Outbound Smart Hosting](http://technet.microsoft.com/library/431b3f02-4efd-4bd3-94e7-eecd03f8ef5e.aspx)中所示。
  
 **Q. Microsoft 是否拥有任何有关如何保护自己免受网络钓鱼诈骗之害的文档？**
  
答：我们有。请参阅下列文章：
  
[获取有关网络钓鱼诈骗、彩票欺诈和其他类型的诈骗的帮助](http://go.microsoft.com/fwlink/p/?LinkId=325606)
  
[电子邮件和网络诈骗： 如何保护自己](http://go.microsoft.com/fwlink/p/?LinkID=325607)
  
 **问：正在调查将垃圾邮件和恶意邮件发送给谁，还是正在移交给执法机构？**
  
答：此服务专注于垃圾邮件和恶意软件检测和删除，尽管我们可能有时会专门调查危险或破坏性的垃圾邮件或攻击活动，并找到肇事者。 这可能涉及与法律和数字犯罪机构合作，以击溃垃圾邮件制造者僵尸网络、阻止垃圾邮件制造者使用服务（如果他们使用此服务来向外发送邮件）并向执法机构提供刑事诉讼的相关信息。
  
 **问：确保我的电子邮件已发送的一系列发送出站电子邮件的最佳做法是什么？**
  
答：以下所述的指导是发送出站电子邮件的最佳做法。
  
1. **电子邮件的发送域应在 DNS 中解析。**
    
    例如, 如果发件人为 user@example.com, 则域 example.com 解析为 IP 地址192.0.43.10。如果发送域在 DNS 中没有 a 记录且无 MX 记录, 则该服务将通过其更高的风险传递池路由邮件, 而不管邮件的内容是否为垃圾邮件。有关更高风险传递池的详细信息, 请参阅[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)。 
    
2. **出站电子邮件服务器的发送 IP 地址应该有一个反向 DNS (PTR) 条目。**
    
    例如，如果从 IP 地址 192.0.43.10 发送，该 IP 的反向 DNS 条目就是 43-10.any.icann.org。 
    
3. **HELO/EHLO 和 MAIL FROM 命令需要保持一致，并且不是以 IP 地址形式呈现，而是以域名形式呈现。**
    
    HELO/EHLO 命令需要配置成与发送 IP 地址的反向 DNS 相匹配，使域在邮件头的各个部分保持相同。
    
4. **确保在 DNS 中设置了正确的 SPF。**
    
    SPF 记录是一种机制，用于验证从域发出的邮件是否确实来自域并且不带有欺骗性质。 有关 SPF 记录的详细信息，请参阅下列链接：
    
    [在 Office 365 中设置 SPF 以防止欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)
    
    [为 Office 365 创建 DNS 记录](https://go.microsoft.com/fwlink/?LinkID=275414)
    
5. **使用 DKIM 对电子邮件签名，用较宽松的规范签名。**
    
    如果发件人希望使用域名密钥识别邮件标准 (DKIM) 对邮件签名，并想通过服务发送出站电子邮件，需要使用较宽松的标头规范化算法签名。 用严格的标头规范签名可能导致签名通过服务时变得无效。
    
6. **域所有者在 WHOIS 数据库中需要有正确的信息。**
    
    这标识了域所有者以及如何通过稳定的父公司、联系点和名称服务器联系他们。
    
7. **对于邮件群发程序，发件人： 名字需要反映发送邮件的人，而邮件的主题行应该是对邮件内容的简短摘要。**
    
    邮件正文应该对提供内容、服务或产品有一个清楚的说明。 例如，如果发件人为 Contoso 公司发送一个群发邮件，电子邮件的"发件人"以及"主题"应与以下内容类似：
    
    发件人： marketing@contoso.com
    
    主题： 圣诞季的新更新目录！ 
    
    以下是不能执行的操作的一个示例，因为该示例是非描述性的：
    
    发件人： user@hotmail.com
    
    主题： 目录
    
8. **如果将群发邮件发送给很多个收件人，并且邮件是新闻稿的格式，那么在邮件底部应该存在取消订阅的方法。**
    
    取消订阅的选项应该与以下内容相似：
    
    该邮件由 sender@fabrikam.com 发送给 example@contoso.com。更新配置文件/电子邮件地址 | 通过 **SafeUnsubscribe** 即时删除 | 隐私策略
    
9. **如果发送群发邮件，需使用双重选择执行列表获取。如果您是一个邮件群发者，双重选择是行业的最佳做法。**
    
    双重加入是要求用户采取以下两种操作注册市场邮件的做法。
    
1. 第一次在用户单击一个之前未选中的复选框（其中他们选择接收营销人员发送的其他促销或电子邮件）时选择。
    
2. 第二次在营销人员向用户提供的电子邮件地址发送确认邮件，要求用户在时间敏感型链接上单击时选择。
    
    使用双重选择为群发邮件发件人构建良好的信誉。
    
10. **群发邮件发件人应创建透明内容，以便他们负起责任：**
    
1. 收件人将发件人添加到通讯簿上的冗长请求应清楚地表明这些操作无法保证邮件传送的安全性。
    
2. 当在邮件正文构建重定向时，使用一致的链接样式。
    
3. 请不要发送大容量图片或附件，或仅含一张图片的邮件。
    
4. 当采用跟踪像素（网络臭虫或信号），清楚地说明公开隐私或 P3P 设置。
    
11. **格式出站传输状态通知。**
    
    当生成传送状态通知邮件时，发件人需按照 [RFC 3464](https://go.microsoft.com/fwlink/?LinkId=279715) 指定的退回格式发送邮件。
    
12. **清除退回的不存在用户的电子邮件地址。**
    
    如果您接收到一个指示不再使用某电子邮件地址的 NDR，请从列表中清除不存在的电子邮件别名。 电子邮件地址会随时间发生变化，大家有时会丢弃这些地址。
    
13. **使用 Hotmail 的智能网络数据服务 (SNDS) 程序。**
    
    Hotmail 使用名为智能网络数据服务的程序，使发件人可以检查最终用户提交的抱怨。 SNDS 是疑难解答 Hotmail 传送问题的初始门户。
    
## <a name="for-more-information"></a>详细信息

[Office 365 电子邮件反垃圾邮件保护](https://support.office.com/article/6a601501-a6a8-4559-b2e7-56b59c96a586)
  
[Exchange Online 中的安全发件人和阻止发件人列表](safe-sender-and-blocked-sender-lists-faq.md)
  
[反垃圾邮件邮件头](anti-spam-message-headers.md)
  
[退信消息和 EOP](backscatter-messages-and-eop.md)
  

