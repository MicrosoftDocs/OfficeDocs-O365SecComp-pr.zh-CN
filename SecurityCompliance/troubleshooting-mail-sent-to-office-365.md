---
title: 向 Office 365 发送故障排除邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/2/2016
ms.audience: ITPro
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: f4caa4e1-e414-4b21-8822-31c08064c059
description: 本文提供了发件人尝试向 Office 365 中的收件箱发送邮件时遇到的问题的故障排除信息，以及向 Office 365 客户群发邮件的最佳做法。
ms.openlocfilehash: 3d8c0a05d096da87b9f686222055d76a6ae96ff2
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23003201"
---
# <a name="troubleshooting-mail-sent-to-office-365"></a>向 Office 365 发送故障排除邮件

本文提供了发件人尝试向 Office 365 中的收件箱发送邮件时遇到的问题的故障排除信息，以及向 Office 365 客户群发邮件的最佳做法。
  
## <a name="troubleshooting-common-problems-with-mail-delivery-to-office-365"></a>有关 Office 365 邮件传送的常见问题的故障排除

选择经常遇到的问题之一。
  
- [您是否正在管理您的 IP 和域的发送信誉？](troubleshooting-mail-sent-to-office-365.md#ManageRep)
    
- [您是否正从新的 IP 地址发送电子邮件？](troubleshooting-mail-sent-to-office-365.md#NewIPs)
    
- [确认您的 DNS 设置正确](troubleshooting-mail-sent-to-office-365.md#ConfirmDNSsetup)
    
- [确保您没有将自己标识为不可路由的 IP](troubleshooting-mail-sent-to-office-365.md#NoReverseDNS)
    
- [您向 Office 365 的用户发送电子邮件时，收到一个未送达报告 (NDR)](troubleshooting-mail-sent-to-office-365.md#NDRInbound)
    
- [我的电子邮件进入到 EOP 中收件人的垃圾邮件文件夹](troubleshooting-mail-sent-to-office-365.md#JunkMailBox)
    
- [来自我的 IP 地址的流量被 EOP 限制](troubleshooting-mail-sent-to-office-365.md#AllowEOPIPs)
    
### <a name="are-you-managing-your-ip-and-domains-sending-reputation"></a>您是否正在管理您的 IP 和域的发送信誉？
<a name="ManageRep"> </a>

经设计的 EOP 筛选技术为 Microsoft Office 365 和其他 Microsoft 产品（如 Exchange Server、Microsoft Office Outlook 和 Windows Live Maill）提供反垃圾邮件保护。我们还利用 SPF、DKIM、DMARC 和电子邮件身份验证技术来帮助解决欺骗和网络钓鱼的问题，通过验证发送电子邮件的域是否被授权执行此操作来帮助解决。EOP 筛选受到许多因素的影响，如发送 IP、域、身份验证、列表精度、投诉率和内容等相关因素。其中，拉低发件人信誉和传送电子邮件能力的关键因素之一是他们的垃圾邮件投诉率。 
  
### <a name="are-you-sending-email-from-new-ip-addresses"></a>您是否正从新的 IP 地址发送电子邮件？
<a name="NewIPs"> </a>

如果您之前没有使用这个 IP 地址发送电子邮件，那么通常在我们的系统里不会为其建立任何信誉。因此，来自新 IP 的电子邮件更有可能遇到传送问题。一旦 IP 建立了非发送垃圾邮件的信誉，EOP 通常会允许更好的电子邮件传送体验。
  
添加到域（在现有 SPF 记录下验证的）的新 IP 通常继承了一些域的发送信誉的额外优势。如果您的域有良好的发送信誉，那么新 IP 可能会有更快的加速时间体验。一个新的 IP 可以在几周内或更快的时间内完全加速，这取决于容量、列表精度和垃圾邮件投诉率。
  
### <a name="confirm-that-your-dns-is-set-up-correctly"></a>确认您的 DNS 设置正确
<a name="ConfirmDNSsetup"> </a>

有关如何创建和维护 DNS 记录的说明，包括邮件路由所需的 MX 记录，您将需要联系您的 DNS 托管提供者。
  
### <a name="ensure-that-you-do-not-advertise-yourself-as-a-non-routable-ip"></a>确保您没有将自己标识为不可路由的 IP
<a name="NoReverseDNS"> </a>

我们可能不接受来自反向 DNS 查找失败的发件人的电子邮件。在某些情况下，当合法发件人在尝试打开一个 EOP 的连接时，他们错误地将自己标识为非面向 Internet 的可路由的 IP。为专用（不可路由的）网保留的 IP 地址包括：
  
- 192.168.0.0/16 (or 192.168.0.0 - 192.168.255.255)
    
- 10.0.0.0/8 (or 10.0.0.0 - 10.255.255.255)
    
- 172.16.0.0/11 (or 172.16.0.0 - 172.31.255.255)
    
### <a name="you-received-a-non-delivery-report-ndr-when-sending-email-to-a-user-in-office-365"></a>您向 Office 365 的用户发送电子邮件时，收到一个未送达报告 (NDR)
<a name="NDRInbound"> </a>

出现一些传送问题是因为发件人的 IP 地址被 Microsoft 阻止或用户账户由于以前的垃圾邮件活动被标识为已禁止的发件人。如果您认为您错误地收到了 NDR，首先按照在 NDR 邮件中解决此问题的说明进行操作。 
  
有关您收到错误的详细信息，请参阅[DSNs and NDRs in On-Premises Exchange 2013 and Office 365](http://technet.microsoft.com/library/8e91de84-76fa-49b2-898c-c5eface76560.aspx) 中 SMTP 错误代码的完整列表。
  
 例如，如果您收到以下 NDR，则表明发送 IP 地址已被 Microsoft 阻止。 
  
 `550 5.7.606-649 Access denied, banned sending IP [x.x.x.x]; To request removal from this list please visit https://sender.office.com/ and follow the directions.`
  
若请求从此列表删除，您可以[使用除名门户来将自己从 Office 365 阻止的发件人名单中删除](use-the-delist-portal-to-remove-yourself-from-the-office-365-blocked-senders-lis.md)。
  
### <a name="my-email-landed-in-the-recipients-junk-folder-in-eop"></a>我的电子邮件进入到 EOP 中收件人的垃圾邮件文件夹
<a name="JunkMailBox"> </a>

如果某封邮件被 EOP 错误地标识为垃圾邮件，您可以与收件人一起将此误报邮件提交给 Microsoft 垃圾邮件分析团队，他们将对该邮件进行评估和分析。根据分析结果的不同，可能会调整服务范围内的垃圾邮件内容筛选规则，以允许发送该邮件。使用电子邮件向 Microsoft 提交的消息不应被归类为垃圾邮件。这样做时，请务必遵循以下过程中的步骤。
  
### <a name="to-use-email-to-submit-false-positive-messages-to-the-microsoft-spam-analysis-team"></a>使用电子邮件将误报邮件提交给 Microsoft 垃圾邮件分析团队

1. 将您想要提交的邮件保存为非垃圾邮件。
    
2. 创建一个新的空白邮件并对其附加非垃圾邮件。
    
    您可以根据需要附加多个非垃圾邮件。
    
3. 复制和粘贴初始的邮件主题行至新的邮件主题行。
    
    > [!IMPORTANT]
    > 保留新的邮件正文空白。 
  
4. 将您的新邮件发送到 [not_junk@office365.microsoft.com](mailto:not_junk@office365.microsoft.com)。
    
### <a name="traffic-from-my-ip-address-is-throttled-by-eop"></a>来自我的 IP 地址的流量被 EOP 限制
<a name="AllowEOPIPs"> </a>

如果您收到来自 EOP 的 NDR，则表明您的 IP 地址被 EOP 限制，例如：
  
 `host xxxx.outlook.com [x.x.x.x]: 451 4.7.550 Access denied, please try again later`
  
您收到了 NDR，因为从 IP 地址检测出可疑活动，且该地址在接受进一步评估时已暂时受限。如果通过评估后该怀疑被解除，则该限制将很快取消。
  
### <a name="i-cant-receive-email-from-senders-in-office-365"></a>我不能接收来自 Office 365 中的发件人的电子邮件
<a name="AllowEOPIPs"> </a>

 以接收来自我们用户的邮件，确保您的网络允许来自 EOP 使用我们的数据中心中的 IP 地址连接。有关详细信息，请参阅[Exchange Online Protection IP 地址](eop/exchange-online-protection-ip-addresses.md)。记录的所有 IP 地址已添加，更改或弃用在过去一年中，请参阅[更改 EOP IP 地址的通知](eop/change-notification-for-eop-ip-addresses.md)。
  
## <a name="best-practices-for-bulk-emailing-to-office-365-users"></a>向 Office 365 用户群发邮件的最佳做法
<a name="BulkMailer"> </a>

如果您经常向 Office 365 用户发起批量邮件活动，并想要确保您的电子邮件安全及时地到达，请执行本部分的操作。
  
### <a name="ensure-that-the-from-name-reflects-who-is-sending-the-message"></a>确保"发件人:"的名称体现出邮件的发送人。

邮件主题应是邮件内容的简要概括，且邮件正文应清楚并简洁地表明优惠、服务或产品的相关内容。 例如：
  
正确
  
 ` From: marketing@shoppershandbag.com `
  
 `Subject: Updated catalog for the Christmas season!`
  
不正确
  
 `From: someone@outlook.com`
  
 `Subject: Catalogs`
  
越容易让人知道您是谁、在做什么，您在通过大部分垃圾邮件筛选器传送邮件时遇到的困难就会越少。
  
### <a name="always-include-an-unsubscribe-option-in-campaign-emails"></a>始终在营销邮件中包含"取消订阅"选项

营销邮件，尤其是新闻稿，应始终包含取消订阅未来邮件的方法。例如：
  
 `This email was sent to example@contoso.com by sender@fabrikam.com.`
  
 `Update Profile/Email Address | Instant removal with SafeUnsubscribe™ | Privacy Policy`
  
一些发件人通过要求收件人发送一封主题包含"取消订阅"的电子邮件到特定别名的方法包含此选项。与上面一键单击的示例相比较，此方法并不可取。如果您一定要选择要求收件人发送邮件，请确保当他们单击链接时，所有要求的字段都已被预设。
  
### <a name="use-the-double-opt-in-option-for-marketing-email-or-newsletter-registration"></a>为营销电子邮件或新闻稿注册使用双重加入方案。

如果您的公司要求或鼓励用户注册他们的联系信息以访问您的产品或服务，则推荐本行业的最佳做法。一些公司是在注册阶段自动注册他们的用户，用于营销电子邮件或电子新闻稿，但是这在世界范围内的电子邮件筛选中，被认为是可疑的市场营销活动。
  
在注册过程中，如果"是，请向我发送您的新闻稿"或"是，请向我发送您的优惠"复选框在默认情况下处于选中状态，没有仔细查看的用户可能会无意中注册他们并不想接收的营销邮件或新闻稿。
  
 我们建议使用双重加入方案来代替，这意味着营销电子邮件或新闻稿的复选框在默认状态下处于未选中的状态。此外，用户一旦提交了注册表，就会收到一封带有 URL 的验证电子邮件，允许他们确认是否决定接收营销电子邮件。 
  
 这将有助于确保只有想要接收营销电子邮件的用户注册电子邮件，随后清除任何可疑的电子邮件营销活动的发送公司。 
  
### <a name="ensure-that-email-message-content-is-transparent-and-traceable"></a>确保电子邮件消息内容透明且可跟踪。

与发送电子邮件的方法同样重要的，是邮件包含的内容。在创建电子邮件的内容时，使用以下最佳做法确保您的电子邮件不会被电子邮件筛选服务标记。
  
- 当电子邮件要求收件人将发件人添加到通讯簿时，应清楚地表明此操作无法保证邮件传送。
    
- 包含在邮件正文中的重定向应当是相似且一致的，不能是多样的和各不相同的。本文中的重定向不指向邮件，例如链接和文档。如果您有大量广告或"取消订阅"链接或"更新配置文件"链接，它们应全部指向同一个域。例如：
    
    正确
    
     `unsubscribe.bulkmailer.com`
    
     `profile.bulkmailer.com`
    
     `options.bulkmailer.com`
    
    不正确
    
     `unsubscribe.bulkmailer.com`
    
     `profiles.excite.com`
    
     `options.yahoo.com`
    
- 请避免包含大容量图片和附件的内容，或仅含一张图片的邮件。
    
- 您的公开隐私或 P3P 设置应清楚地说明跟踪像素（Web bug 或信号）的状态。
    
### <a name="remove-incorrect-email-aliases-from-your-databases"></a>从您的数据库中删除不正确的电子邮件别名

在您的数据库中创建跳回的任何电子邮件别名都是不必要的，它将使您的出站邮件面临风险 - 会受到电子邮件筛选服务的进一步审查。请确保您的电子邮件数据库是最新的。
  

