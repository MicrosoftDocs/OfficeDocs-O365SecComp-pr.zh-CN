---
title: 控制 Office 365 中的出站垃圾邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6a601501-a6a8-4559-b2e7-56b59c96a586
description: 如果您的组织发送大量的批量邮件标记为垃圾邮件，您无法获取阻止发送电子邮件与 Office 365。阅读此文，了解有关发生此问题，以及有关该产品可实现的功能。
ms.openlocfilehash: a18e584a260218a53494ef49dd2d7380a0a9a3f1
ms.sourcegitcommit: 03e64ead7805f3dfa9149252be8606efe50375df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2019
ms.locfileid: "27769778"
---
# <a name="controlling-outbound-spam-in-office-365"></a>控制 Office 365 中的出站垃圾邮件

我们需要认真地管理出站垃圾邮件，因为我们是共享的服务。 有许多客户后面共享资源，其中如果一个客户发送出站垃圾邮件，则它会降低服务的出站 IP 信誉和影响的其他客户的电子邮件的成功的可交付性池中。如果客户 B 会发送垃圾邮件和各种第三方 IP blocklists 列表它使用的 IP 地址，则向客户 A 不平等。

## <a name="what-admins-can-do-to-control-outbound-spam"></a>管理员可以做什么控制出站垃圾邮件

- **启用通知时发送垃圾邮件或关闭帐户**。管理员可以获取密，每当消息被标记为出站垃圾邮件并发送通过高风险池。通过监视此邮箱，管理员可以检测到，如果其网络中都拥有受到攻击的帐户或者垃圾邮件筛选器地将其标记为垃圾邮件其电子邮件。 设置出站垃圾邮件策略的详细信息可以找到[此处](configure-the-outbound-spam-policy.md)。
 
- **手动查看从第三方电子邮件提供商的垃圾邮件投诉**。许多第三方电子邮件服务如 Outlook.com、 Yahoo 和 AOL 提供反馈循环其中其服务中的任何用户标记为垃圾邮件我们服务从电子邮件，如果邮件是打包，回向我们发送候审。若要了解有关 Outlook.com 的发件人支持的详细信息，请单击[此处](https://sendersupport.olc.protection.outlook.com/pm/services.aspx)。

## <a name="what-eop-does-to-control-outbound-spam"></a>EOP 用途控制出站垃圾邮件 

1. **职责划分到单独的 Ip 的池的出站通信**。为垃圾邮件扫描客户发送出站通过服务每条消息。如果邮件是垃圾邮件，它通过高风险传递池路由。该 IP 池包含非可交付结果的状态通知和垃圾邮件。不能保证传递到预期接收人，如许多第三方将不会接受电子邮件，因为它发出的电子邮件的质量。

拆分流量这样可确保低品质电子邮件 （垃圾邮件，Ndr 退信） 不拖动下的正则出站电子邮件池信誉。高风险池通常具有低信誉在很多接收器周围 Internet，尽管这不是通用。 

2. **监控的 IP 信誉**。Office 365 查询各种第三方 IP blocklists 和如果我们出站 Ip 任一排列这些生成警报。这样，我们时垃圾邮件已导致我们信誉降低快速做出反应。生成警报时，我们具有内部文档外围需要获取列表中清除哪些步骤。 

3. **禁用的其余部分帐户发送太多电子邮件时标记为垃圾邮件**。尽管我们将数据库分隔到我们的垃圾邮件和非垃圾邮件到两个单独的出站 IP 池，电子邮件帐户不能无限期地发送垃圾邮件。我们监视其帐户发送垃圾邮件，并且如果它超出披露的限制，阻止帐户发送垃圾邮件。

单个邮件标记为垃圾邮件可能是垃圾邮件引擎和也称为误报 misclassification。我们要为其提供的传出; 有机会的高风险池通过发送但是，大量的短时间框架中的消息表明问题以及的发生时，我们阻止从发送任何多个电子邮件帐户。有不同存在单个电子邮件帐户以及聚合整个租户的阈值。

4. **禁用的其余部分帐户发送太多太短时间框架中的电子邮件时**。除了上面的标记为垃圾邮件的邮件比例的外观的限制，还有时到达总体无论将邮件标记为垃圾邮件限制阻止帐户的限制。存在此限制的原因是因为受到攻击的帐户无法发送垃圾邮件筛选器的已错过的零时差垃圾邮件。如果可能，有时会让合法批量邮件活动和大规模垃圾邮件市场活动之间的差异很难，，因为这些限制激活限制任何潜在损坏。

> [!NOTE]
> #3 和 4 中，我们不公布准确的限制。 这是以阻止垃圾邮件游戏系统的发送者并确保，我们在需要时，我们可以更改的限制。限制为足够高，以便平均业务用户将从不命中它们和低，它包含的大多数破坏垃圾消息发送者可以执行操作。 

## <a name="recommended-workarounds-for-customers-who-want-to-send-outbound-a-lot-of-email-through-eop"></a>需要发送出站大量 EOP 通过电子邮件的客户推荐的解决方法

很难想要发送大量与该服务防止受到攻击的帐户和与较差的邮件列表获取做法的批量邮件发件人的电子邮件客户之间的平衡。同样，出站 IP 上第三方 blocklist 登录的成本是高于阻止发送出站电子邮件客户。如在[Exchange Online Service Description](https://technet.microsoft.com/en-us/library/exchange-online-limits.aspx#Receiving and sending limits)中所述，使用 EOP 发送批量电子邮件不支持使用的服务和仅允许基于"最大努力"。对于想发送批量电子邮件的客户，我们建议：

答：**将通过其自己的本地批量电子邮件发送邮件服务器**。这意味着客户需要维护其自己的电子邮件基础结构这种类型的电子邮件。

b.**使用第三方批量 emailer 发送大量通信**。有几个第三方批量邮件发件人其唯一业务会发送批量电子邮件。它们可以与客户合作以确保它们已良好在通过做法并拥有专用于强制实施该资源。 

消息、 移动、 恶意软件防滥用工作组 (MAAWG) 发布其成员资格名单[此处](http://www.maawg.org/about/roster)。多个批量电子邮件提供程序的列表上，而已知负责 Internet 市民。 
  
## <a name="for-more-information"></a>更多信息

[发件人被阻止发送出站垃圾邮件时的示例通知](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md)

[Office 365 电子邮件反垃圾邮件保护](anti-spam-protection.md)

[Office 365 中的防欺骗保护](anti-spoofing-protection.md)

[垃圾邮件可信度](spam-confidence-levels.md)
