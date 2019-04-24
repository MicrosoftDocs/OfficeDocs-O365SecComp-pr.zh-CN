---
title: 控制 Office 365 中的出站垃圾邮件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
ms.collection:
- M365-security-compliance
description: 如果您的组织发送大量垃圾邮件, 并将其标记为垃圾邮件, 则可能会阻止您使用 Office 365 发送电子邮件。 阅读本文, 了解有关此操作的原因以及您可以执行的操作的详细信息。
ms.openlocfilehash: 0fcbe0c7b9d1bd340e2ab2feb5edec8283ecaf9a
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32262304"
---
# <a name="controlling-outbound-spam-in-office-365"></a>控制 Office 365 中的出站垃圾邮件

我们会认真管理出站垃圾邮件, 因为我们是共享服务。  共享资源池背后有许多客户, 如果一个客户发送出站垃圾邮件, 它可能会降低服务的出站 IP 信誉, 并影响其他客户的电子邮件的成功 deliverability。

> [!IMPORTANT]
> 在发件人受到限制时的通知现在是安全 & 合规性中心 (SCC) 警报平台的一部分。 如果不使用下面概述的方法来发送通知, 则可以在 "用户限制发送电子邮件" 警报中找到要通知的用户列表。 请开始使用安全 & 合规中心中的 "[通知策略" 页](https://sip.protection.office.com/alertpolicies)来配置警报, 因为将来的方法将被删除。 阅读有关新的[受限用户体验](https://docs.microsoft.com/en-us/Office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)的信息。

## <a name="what-admins-can-do-to-control-outbound-spam"></a>管理员可控制出站垃圾邮件的操作

- **在帐户发送垃圾邮件或关机时启用通知**。 只要邮件被标记为出站垃圾邮件并通过高风险池发送, 管理员就可以获取密件抄送。 通过监视此邮箱, 管理员可以检测其网络中是否有受损帐户, 或垃圾邮件筛选器是否错误地将其电子邮件标记为垃圾邮件。  可在[此处](configure-the-outbound-spam-policy.md)找到有关设置出站垃圾邮件策略的详细信息。
 
- **手动查看第三方电子邮件提供商发来的垃圾邮件投诉**。 许多第三方电子邮件服务 (如 Outlook.com、Yahoo 和 AOL) 都提供反馈循环, 如果服务中的任何用户将我们的服务中的电子邮件标记为垃圾邮件, 则会将该邮件打包并发送回我们进行审阅。 若要了解有关 Outlook.com 的发件人支持的详细信息, 请单击[此处](https://sendersupport.olc.protection.outlook.com/pm/services.aspx)。

## <a name="what-eop-does-to-control-outbound-spam"></a>控制出站垃圾邮件的 EOP 

1. 将**出站流量分为不同 ip 池中的隔离流量**。 将扫描客户通过服务发送出站的每封邮件, 以查找垃圾邮件。 如果邮件是垃圾邮件, 它将通过高风险传递池进行路由。 此 IP 池包含未送达状态通知和垃圾邮件。 不能保证传递给预期收件人, 因为由于它发出电子邮件的质量原因, 许多第三方不会接受电子邮件。

以这种方式拆分流量可确保较低质量的电子邮件 (垃圾邮件、退信 ndr) 不会向下拖动常规出站电子邮件池的信誉。 在 Internet 周围的多个接收器上, 高风险池通常具有较低的声誉, 尽管这不是通用的。 

2. **监视 IP 信誉**。 Office 365 查询各种第三方 IP blocklists, 如果其中列出了任何出站 ip, 将生成警报。 这使我们能够在垃圾邮件导致名誉下降时快速做出反应。 生成警报时, 我们有内部文档外外部要采取什么步骤来获取 delisted。 

3. 在**发送过多电子邮件标记为垃圾邮件时禁用违犯的帐户**。 即使我们将垃圾邮件和非垃圾邮件隔离成两个单独的出站 IP 池, 电子邮件帐户也无法无限期发送垃圾邮件。 我们会监视哪些帐户将发送垃圾邮件, 如果超过 undisclosed 限制, 将阻止该帐户发送垃圾邮件。

标记为垃圾邮件的单个邮件可能是垃圾邮件引擎的 misclassification, 也称为误报。 我们将通过高风险池发送它, 为其带来了机会。但是, 短时间内的大量邮件表示存在问题, 在发生此问题时, 将阻止该帐户发送更多的电子邮件。 单个电子邮件帐户以及整个租户的聚合中存在不同的阈值。

4. 在**过短时间内发送电子邮件过多的电子邮件时禁用违犯的帐户**。 除了上述限制以查找标记为垃圾邮件的邮件的比例之外, 还会在达到总限制时阻止帐户, 而不管邮件是否被标记为垃圾邮件。 此限制存在的原因是因为受到威胁的帐户可能会发送垃圾邮件筛选器错过的零天垃圾邮件。 由于很难 (如果不可能), 有时会告知合法大宗邮件市场活动与大量垃圾邮件市场活动之间的区别, 这些限制将激活, 以限制任何可能的损坏。

> [!NOTE]
> 对于 #3 和 #4, 我们不会公布确切的限制。  这是为了防止垃圾邮件制造者游戏系统, 并确保我们可以在需要时更改限制。 这些限制值足够高, 因此一般的业务用户永远不会击中这些限制, 并且其不足以确保垃圾邮件制造者可以执行的大多数损坏。 

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a>对于希望通过 EOP 向出站发送大量电子邮件的客户推荐的解决方法

如果客户要发送大量的电子邮件, 则需要在客户之间达到平衡, 而不是使用较差的列表获取做法来保护服务免受受损帐户和批量 emailers。 此外, 第三方阻止列表上的出站 IP 登录的开销高于阻止客户发送出站电子邮件的成本。 如[Exchange Online 服务说明](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx#Receiving and sending limits)中所述, 使用 EOP 发送批量电子邮件不是服务的受支持的使用, 并且只允许 "最大努力"。 对于想要发送批量电子邮件的客户, 我们建议您执行以下操作:

a. **通过其自己的内部部署邮件服务器发送批量电子邮件**。 这意味着客户必须为此类电子邮件维护自己的电子邮件基础结构。

b. **使用第三方批量 emailer 发送大量通信**。 有几个第三方批量 emailers, 其唯一业务是指发送批量电子邮件。 他们可以与客户合作, 以确保他们具有良好的电子邮件活动, 并且他们有专门实施它的资源。 

消息传递、移动、恶意软件反滥用工作组 (MAAWG) 将[在此处](http://www.maawg.org/about/roster)发布其成员名单。 列表中有多个批量电子邮件提供商, 并且已知它们负责 Internet 公民。 
  
## <a name="for-more-information"></a>有关详细信息

[当发件人被阻止发送出站垃圾邮件时的示例通知](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)

[Office 365 中的防欺骗保护](anti-spoofing-protection.md)

[垃圾邮件可信度](spam-confidence-levels.md)
