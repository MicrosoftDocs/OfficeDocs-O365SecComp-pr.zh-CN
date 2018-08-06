---
title: 配置 EOP 的最佳实践
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: 请遵循所建议的这些 Exchange Online Protection (EOP) 最佳做法，以成功达到目的，并避免常见的配置错误。
ms.openlocfilehash: ef58e2cd5a3ffdbbeb02124442c355974d174073
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027269"
---
# <a name="best-practices-for-configuring-eop"></a>配置 EOP 的最佳实践
  
请遵循所建议的这些 Exchange Online Protection (EOP) 最佳做法，以成功达到目的，并避免常见的配置错误。建议一般情况下使用默认的配置设置。参阅本主题的前提是，你已经完成安装过程。如果还没有完成 EOP 安装，请参阅[设置 EOP 服务](set-up-your-eop-service.md)。
  
## <a name="use-a-test-domain"></a>使用测试域

在高容量生产域上实施服务功能前，建议你使用测试域、子域或低容量域来尝试这些服务功能。
  
## <a name="synchronize-recipients"></a>同步收件人

如果你的组织在本地 Active Directory 环境中拥有现成的用户帐户，则可以将这些帐户同步到云中的 Azure Active Directory。建议使用目录同步。若要详细了解使用目录同步的具体优势以及安装步骤，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)。
  
## <a name="spf-record-customization-to-help-prevent-spoofing"></a>SPF 记录自定义帮助防止欺骗

时设置 EOP，您添加 SPF （发件人策略框架） 记录 eop 到您的 DNS 记录。SPF 记录有助于防止欺骗。有关如何 SPF 记录阻止欺骗和如何将您的本地 IP 地址添加到 SPF 记录的详细信息，请参阅[Set up Office 365 为了帮助防止欺骗中的 SPF](../set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 
  
## <a name="set-anti-spam-options"></a>设置反垃圾邮件选项

管理您的连接筛选器设置通过将 IP 地址添加到 IP 允许和 IP 阻止列表，以及选择**启用安全列表**选项，其中应减少误报 （为垃圾邮件分类的良好邮件） 数收到。有关详细信息[配置连接筛选器策略](../configure-the-connection-filter-policy.md)。对于应用于整个组织的多个垃圾邮件设置，请了解一下[如何帮助确保邮件未标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[阻止电子邮件与 Office 365 垃圾邮件筛选器以阻止假负问题垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534225)。如果您具有管理员级控件，并且想要防止误报或 false 负片，这些是非常有用。
  
通过审阅和 （可选） 更改默认设置来管理您的内容筛选器。例如，您可以更改为垃圾邮件检测到的邮件时会发生什么情况的操作。如果您想要使用垃圾邮件筛选保守方法，您可以配置高级垃圾邮件筛选选项。我们建议您测试这些选项首先之前实现它们在生产环境中 （通过打开其） 建议关注网络钓鱼的组织打开**SPF 记录： 硬失败**选项。有关详细信息[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)和[高级垃圾邮件筛选选项](../advanced-spam-filtering-asf-options.md)。
  
> [!IMPORTANT]
> 如果您使用默认内容筛选器操作，**移动到垃圾邮件文件夹的邮件**，以确保此操作将处理的本地邮箱，则必须配置 Exchange 邮件流规则，也称为内部部署上的传输规则服务器来检测由 EOP 添加的垃圾邮件邮件头。有关详细信息，请参阅[确保垃圾邮件被路由到每个用户的垃圾邮件文件夹](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 
  
我们建议您查看[anti-spam protection FAQ](../anti-spam-protection-faq.md)，其中包括出站邮件最佳实践部分，有助于确保出站邮件传递。
  
您可以提交假负 （垃圾邮件） 和误报 （非垃圾邮件） 向 Microsoft 进行分析以下几种方式。有关详细信息，请参阅[提交垃圾邮件和非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。
  
## <a name="set-anti-malware-options"></a>设置反恶意软件选项

查看并微调 Exchange 管理员 center(EAC) 中的恶意软件筛选器设置。有关详细信息[配置反恶意软件策略](../configure-anti-malware-policies.md)。我们还建议阅读有关其他的常见问题和解答与我们的[反恶意软件保护常见问题](../anti-malware-protection-faq-eop.md)中的反恶意软件保护。
  
如果你对包含恶意软件的可执行文件有点担心，则可以创建一个 Exchange 邮件流规则来拦截所有包含可执行内容的电子邮件附件。若要拦截[Use mail flow rules to inspect message attachments](https://support.microsoft.com/kb/2959596)中"传输规则检查支持的可执行文件类型"下方列出的文件类型，请按 [How to reduce malware threats through file attachment blocking in Exchange Online Protection](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)（如何在 Exchange Online Protection 中通过文件附件拦截来减少恶意软件威胁）中的步骤操作。
  
在 EAC 中，可以使用常见的附件类型筛选器。选择**保护** \> **恶意软件筛选器**。您可以创建 Exchange 邮件流规则，也称为传输规则，阻止具有可执行内容任何电子邮件附件。 
  
为加强保护，我们还建议使用邮件流规则阻止下列扩展名的部分或全部： ade、 adp、 ani、 营业活动报表、 bat、 chm、 cmd、 com、 cpl、 crt、 hlp、 超线程、 hta、 inf、 项、 isp、 作业、 js、 jse、 lnk，mda、 mdb、 mde、 mdz、 msc、 msi、 mspmst、 pcd、 注册表、 scr、 sct、 shs、 url、 vb、 vbe、 vbs、 wsc、 wsf、 wsh。这可以通过使用的**任何附件的文件扩展名包含这些词**的条件。 
  
管理员和最终用户可以提交通过筛选器的恶意软件，或提交被误检为恶意软件的文件，只需将其发送给 Microsoft 进行分析即可。有关详细信息，请参阅[Submitting malware and non-malware to Microsoft for analysis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md)。
  
## <a name="create-mail-flow-rules"></a>创建邮件流规则

创建邮件流规则（也称为传输规则或自定义筛选器），满足业务需求。
  
到生产环境中部署一个新规则时，选择一种测试模式，查看规则的效果。满意规则处理预期的方式，将规则模式更改为**Enforce**。
  
在部署新规则时，请考虑添加附加操作**生成事件报告**，以监视操作中的规则。 
  
如果你的组织采用部分本地、部分 Office 365 的混合部署配置，可以创建应用于整个组织的规则。为此，请使用本地和 Office 365 都适用的条件。虽然大多数条件都可用于这两种部署，但也有少数条件特定于特定的部署方案。有关详细信息，请参阅[Mail flow or Transport rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)。
  
如果希望检查在组织内部传递的邮件的附件，可以通过设置邮件流规则来实现。然后，可以根据这些附件的内容或特征对经过检查的邮件采取操作。有关详细信息，请参阅[Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)。
  
### <a name="phishing-and-spoofing-prevention"></a>网络钓鱼和欺骗预防

通过检测电子邮件中个人信息退出组织的时间，可以提高防钓鱼保护。例如，可以在邮件流规则中使用下列正则表达式，检测可能危及隐私的个人财务数据或信息传输：
  
- \d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d (MasterCard Visa)
    
- \d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d (American Express)
    
- \d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d（任何 16 位数字）
    
- \d\d\d\-\d\d\-\d\d\d\d (Social Security Numbers)
    
通过阻止似乎是从你自己的域发送的入站恶意电子邮件，也可以成功减少垃圾邮件和网络钓鱼。例如，可以创建一个邮件流规则，拒绝从你的公司域发送到同一个公司域的邮件，以阻止此类发件人伪造。
  
> [!CAUTION]
> 我们建议仅当您确定您的域中没有合法电子邮件从 Internet 发送到邮件服务器时，才创建此拒绝规则。当邮件从组织中的某位用户发送给外部收件人，并随后转发给组织中的其他收件人时，会发生此问题。 
  
### <a name="extension-blocking"></a>扩展名阻止

如果您担心包含恶意软件的可执行文件，您可以配置反恶意软件策略来阻止具有可执行内容任何电子邮件附件。按照[配置反恶意软件策略](../configure-anti-malware-policies.md)中的步骤。
  
为了加强保护，仍建议阻止以下部分或全部的扩展名：ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、ht、hta、inf、ins、isp、job、js、jse、lnk、mda、mdb、mde、mdz、msc、msi、msp、mst、pcd、reg、scr、sct、shs、url、vb、vbe、vbs、wsc、wsf 和 wsh。
  
## <a name="reporting-and-troubleshooting"></a>报告和疑难解答

查看 Office 365 管理中心内的报告，对常见问题和趋势进行故障排除。使用消息跟踪工具来查找有关邮件的单点数据。有关报告的详细信息，请参阅 [Exchange Online Protection 中的报告和邮件跟踪](reporting-and-message-trace-in-exchange-online-protection.md)。有关消息跟踪工具的详细信息，请参阅[Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)。
  
## <a name="for-more-information"></a>详细信息

[EOP 一般常见问题解答](eop-general-faq.md)
  
[EOP 帮助与支持](help-and-support-for-eop.md)
  
[EOP 入门视频](videos-for-getting-started-with-eop.md)
  
[如何帮助确保邮件不会标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

