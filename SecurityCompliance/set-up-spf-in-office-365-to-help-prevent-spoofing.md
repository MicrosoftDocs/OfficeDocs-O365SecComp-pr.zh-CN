---
title: 在 Office 365 中设置 SPF 以防止欺骗
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 2/19/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
description: 摘要： 本文介绍了如何更新域名服务 (DNS) 记录，以便可以在 Office 365 中结合使用发件人策略框架 (SPF) 和自定义域。 SPF 有助于验证从自定义域发送的出站电子邮件。
ms.openlocfilehash: 15472900986a367e084c6126580cef85d286a94b
ms.sourcegitcommit: 33c8e9c16143650ca443d73e91631f9180a9268e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "35854786"
---
# <a name="set-up-spf-in-office-365-to-help-prevent-spoofing"></a>在 Office 365 中设置 SPF 以防止欺骗

 **摘要：** 本文介绍了如何更新域名服务 (DNS) 记录，以便可以在 Office 365 中结合使用发件人策略框架 (SPF) 和自定义域。SPF 有助于验证从自定义域发送的出站电子邮件。 
  
若要使用自定义域，Office 365 要求你将发件人策略框架 (SPF) TXT 记录添加到 DNS 记录中，这样做有助于防止欺骗发生。SPF 标识允许哪些邮件服务器代表你发送邮件。一般来说，SPF 以及 DKIM、DMARC 和 Office 365 支持的其他技术可有助于防止欺骗和钓鱼发生。以 TXT 记录的形式添加 SPF 后，DNS 可使用此记录来确定哪些邮件服务器可以代表你的自定义域发送邮件。收件人邮件系统可以参阅 SPF TXT 记录，从而确定从你的自定义域发送的邮件是否来自已获授权的邮件服务器。
  
例如，假设自定义域 contoso.com 使用 Office 365。你添加一个 SPF TXT 记录，将 Office 365 邮件服务器列为你的域的合法邮件服务器。当接收邮件服务器从 joe@contoso.com 收到一封邮件时，服务器会查找 contoso.com 的 SPF TXT 记录，并确定这封邮件是否有效。如果接收服务器确定这封邮件不是来自 SPF 记录中列出的 Office 365 邮件服务器，则可以选择将这封邮件作为垃圾邮件拒绝。
  
另外，如果自定义域没有 SPF TXT 记录，某些接收服务器可能会彻底拒绝邮件。这是因为接收服务器无法验证邮件是否来自已获授权的邮件服务器。
  
如果你已经为 Office 365 设置了邮件，则表明已经将 Microsoft 的邮件服务器作为 SPF TXT 记录添加在 DNS 中。不过，在某些情况下，可能需要在 DNS 中更新 SPF TXT 记录。例如：
  
- 以前，如果要使用 SharePoint Online，必须向自定义域添加不同的 SPF TXT 记录。现在，不再需要这样做。此更改应该会降低 SharePoint Online 通知邮件最终被转入垃圾电子邮件文件夹的风险。如果即将达到查找限制 10 次，且看到"超出了查找限制"和"跃点过多"的错误消息，请更新 SPF TXT 记录。
    
- 如果您拥有安装了 Office 365 和本地 Exchange 的混合环境。
    
- 打算设置 DKIM 和 DMARC（推荐）。
    
## <a name="updating-your-spf-txt-record-for-office-365"></a>为 Office 365 更新您的 SPF TXT 记录

更新 DNS 中的 TXT 记录之前，需要收集一些信息，并确定记录的格式。这将有助于防止生成 DNS 错误。有关高级示例（更详细地介绍了支持的 SPF 语法），请参阅 [SPF 在 Office 365 中防止欺骗和钓鱼的工作原理](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。
  
收集此信息：
  
- 自定义域的当前 SPF TXT 记录。有关说明，请参阅[收集创建 Office 365 DNS 记录所需的信息](https://support.office.microsoft.com/en-us/article/Gather-the-information-you-need-to-create-Office-365-DNS-records-77f90d4a-dc7f-4f09-8972-c1b03ea85a67)。
    
- 所有本地邮件服务器的 IP 地址。例如， **192.168.0.1**。
    
- 用于需要包含在 SPF TXT 记录中的所有第三方域的域名。一些批量邮件提供商已设置供其客户使用的子域。例如，MailChimp 公司已经设置了 **servers.mcsv.net**。
    
- 确定要对 SPF TXT 记录使用的强制规则。我们建议使用 **-all**。有关其他语法选项的详细信息，请参阅 [Office 365 的 SPF TXT 记录语法](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365)。
    
### <a name="to-add-or-update-your-spf-txt-record"></a>添加或更新您的 SPF TXT 记录

1. 如果尚未执行此操作，请通过使用下表中的语法构成 SPF TXT 记录：
    
||**如果您使用的是...**|**对于 Office 365 客户很常见？**|**添加以下内容...**|
|:-----|:-----|:-----|:-----|
|1  <br/> |所有电子邮件系统（必需）  <br/> |常见。所有 SPF TXT 记录都以此值开头  <br/> |v=spf1  <br/> |
|双面  <br/> |Exchange Online  <br/> |常见  <br/> |include:spf.protection.outlook.com  <br/> |
|第三章  <br/> |Exchange Online 专用  <br/> |不常见  <br/> |ip4: 23.103.224.0/19 ip4: 206.191.224.0/19 ip4: 40.103.0.0/16 包含 include spf.protection.outlook.com. .com  <br/> |
|4  <br/> |仅 Office 365 Germany、Microsoft Cloud Germany  <br/> |不常见  <br/> |包括 "include spf.protection.outlook.com"。  <br/> |
|5  <br/> |第三方电子邮件系统  <br/> |不常见  <br/> |include:\<域名\>  <br/> 其中域名是第三方电子邮件系统的域名。  <br/> |
|型  <br/> |本地邮件系统。例如，Exchange Online Protection 和另一个邮件系统  <br/> |不常见  <br/> | 为每个附加的邮件系统使用以下其中一个：  <br/>  ip4:\<  _IP address_\>  <br/>  ip6:\<  _IP address_\>  <br/>  include:\<  _domain name_\>  <br/>  其中 \<  _IP address_\>的值是其他邮件系统的 IP 地址，\< _domain name_\> 是另一个代表您的域发送邮件的邮件系统的 IP 地址。  <br/> |
|步  <br/> |所有电子邮件系统（必需）  <br/> |常见。所有 SPF TXT 记录都以此值结尾  <br/> |\< _enforcement rule_\>  <br/> 这可以是多个值之一。我们建议您使用 **-all**。  <br/> |
   
1.1 例如, 如果您完全托管在 Office 365 中, 即没有本地邮件服务器, SPF TXT 记录将包括行1、2和 7, 如下所示:
    
  ```
   v=spf1 include:spf.protection.outlook.com -all
  ```

1.2 这是最常见的 Office 365 SPF TXT 记录。 此记录仅适用于所有人, 而不管您的 Office 365 数据中心是位于美国, 还是在欧洲 (包括德国) 或其他位置。
    
1.3 但是, 如果你已购买 Office 365 德国的一部分, Microsoft 云德国的一部分应使用的 include 语句来自第4行, 而不是第2行。 例如，如果完全托管在 Office 365 Germany中（即没有本地邮件服务器），则 SPF TXT 记录包括行 1、4 和 7，如下所示：
    
  ```
   v=spf1 include:spf.protection.outlook.de -all
  ```

1.4 如果已部署在 Office 365 中, 并且已为您的自定义域设置 SPF TXT 记录, 并且要迁移到 Office 365 德国, 则需要更新 SPF TXT 记录。 若要执行此操作, 请更改**包含 include spf.protection.outlook.com**以**包含 include spf.protection.outlook.com**的安全。
    
2. 在构造 SPF TXT 记录后, 您需要在 DNS 中更新该记录。 一个域只能有一个 SPF TXT 记录。 如果存在 SPF TXT 记录, 则需要更新现有记录, 而不是添加新记录。 转到为[Office 365 创建 DNS 记录](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-worldwide), 然后单击 DNS 主机的链接。 
    
3. 测试 SPF TXT 记录。
    
## <a name="more-information-about-spf"></a>有关 SPF 的详细信息

有关支持的 SPF 语法、欺骗、故障排除以及 Office 365 如何支持 SPF 的更加详细的探讨的高级示例，请参阅 [SPF 在 Office 365 中防止欺骗和钓鱼的工作原理](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks)。
  
## <a name="next-steps-after-you-set-up-spf-for-office-365"></a>后续步骤：为 Office 365 设置 SPF 之后

是否遇到与 SPF TXT 记录相关的问题？阅读[疑难解答：Office 365 中 SPF 的最佳实践。](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot)。
  
 SPF 旨在帮助防止欺骗，但还有 SPF 无法防止的欺骗技术。为了防止这些欺骗，在你设置 SPF 后，也应该为 Office 365 配置 DKIM 和 DMARC。请参阅 [使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)，了解入门知识。之后，请参阅[使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)。
  

