---
title: 配置 EOP 的最佳实践
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: 请遵循所建议的这些 Exchange Online Protection (EOP) 最佳做法，以成功达到目的，并避免常见的配置错误。
ms.openlocfilehash: 991059b6823059b0e5eae784e21bfc0128cbd2d1
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599808"
---
# <a name="best-practices-for-configuring-eop"></a>配置 EOP 的最佳做法
  
请遵循所建议的这些 Exchange Online Protection (EOP) 最佳做法，以成功达到目的，并避免常见的配置错误。建议一般情况下使用默认的配置设置。参阅本主题的前提是，你已经完成安装过程。如果还没有完成 EOP 安装，请参阅[设置 EOP 服务](set-up-your-eop-service.md)。
  
## <a name="use-a-test-domain"></a>使用测试域

在高容量生产域上实施服务功能前，建议你使用测试域、子域或低容量域来尝试这些服务功能。
  
## <a name="synchronize-recipients"></a>同步收件人

如果你的组织在本地 Active Directory 环境中拥有现成的用户帐户，则可以将这些帐户同步到云中的 Azure Active Directory。建议使用目录同步。若要详细了解使用目录同步的具体优势以及安装步骤，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)。
  
## <a name="spf-record-customization-to-help-prevent-spoofing"></a>SPF 记录自定义帮助防止欺骗

在设置 EOP 时，添加了 EOP 的一个 SPF（发件人策略框架）记录到 DNS 记录中。 SPF 记录可帮助防止欺骗。 有关 SPF 记录如何阻止欺骗以及如何将本地 IP 地址添加到 SPF 记录的详细信息, 请参阅[Set UP SPF In Office 365 以帮助防止欺骗](../set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 
  
## <a name="set-anti-spam-options"></a>设置反垃圾邮件选项

通过将 IP 地址添加到 IP 允许和 IP 阻止列表来管理连接筛选器设置, 并选择 "**启用安全列表**" 选项, 该选项应减少收到的误报数 (适用于分类为垃圾邮件的邮件)。 有关详细信息, 请参阅[配置连接筛选器策略](../configure-the-connection-filter-policy.md)。 有关适用于整个组织的详细垃圾邮件设置，请参阅[如何帮助确保邮件不会被标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](https://go.microsoft.com/fwlink/p/?LinkId=534225)。 如果您拥有管理员级别控制，并且您想要阻止误报或漏报问题，这些会很有帮助。
  
通过查看和 (可选) 更改默认设置来管理内容筛选器。 例如, 您可以更改对垃圾邮件检测到的邮件发生的操作。 如果要采用严格的垃圾邮件筛选方法, 可以配置高级垃圾邮件筛选选项。 我们建议您先测试这些选项, 然后再在生产环境中实施它们 (通过启用它们), 建议关注网络钓鱼的组织启用 " **SPF 记录: 硬失败**" 选项。 有关详细信息, 请参阅[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)和[高级垃圾邮件筛选选项](../advanced-spam-filtering-asf-options.md)。
  
> [!IMPORTANT]
> 如果使用默认内容筛选器操作, 请**将邮件移动到 "垃圾邮件" 文件夹**, 以确保此操作适用于本地邮箱, 则必须在本地邮箱上配置 Exchange 邮件流规则 (也称为传输规则)用于检测由 EOP 添加的垃圾邮件头的服务器。 有关详细信息，请参阅[确保垃圾邮件已路由到每个用户的"垃圾邮件"文件夹](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 
  
我们建议您查看[反垃圾邮件保护常见问题解答](../anti-spam-protection-faq.md), 包括 "出站邮件最佳实践" 部分, 这将有助于确保出站邮件已送达。
  
可以通过多种方式向 Microsoft 提交漏报（垃圾邮件）和误报（非垃圾邮件）以供分析。 有关详细信息, 请参阅[将垃圾邮件、非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。
  
## <a name="set-anti-malware-options"></a>设置反恶意软件选项

在 Exchange 管理中心 (EAC) 中检查并微调恶意软件筛选器设置。 有关详细信息, 请参阅[配置反恶意软件策略](../configure-anti-malware-policies.md)。 我们还建议阅读有关反恶意软件[保护常见问题解答](../anti-malware-protection-faq-eop.md)中有关反恶意软件保护的其他常见问题和解答。
  
如果你对包含恶意软件的可执行文件有点担心，则可以创建一个 Exchange 邮件流规则来拦截所有包含可执行内容的电子邮件附件。 按照[如何通过 Exchange Online Protection 中的文件附件阻止功能降低恶意软件威胁](https://support.microsoft.com/kb/2959596)的步骤, 以阻止在[Exchange online 中使用邮件流规则检查邮件附件](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection)中列出的文件类型。
  
可以在 EAC 中使用常见附件类型筛选器。 选择 "**保护** \> **恶意软件筛选器**"。 您可以创建阻止任何具有可执行内容的电子邮件附件的邮件流规则。 
  
为了加强保护，我们仍建议你使用邮件流规则阻止以下部分或全部的扩展名：ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、ht、hta、inf、ins、isp、job、js、jse、lnk、mda、mdb、mde、mdz、msc、msi、msp、mst、pcd、reg、scr、sct、shs、url、vb、vbe、vbs、wsc、wsf 和 wsh。通过使用“**任何包含这些词的附件文件扩展名**”条件，可以完成这一操作。 
  
管理员和最终用户可以提交通过筛选器的恶意软件，或提交被误检为恶意软件的文件，只需将其发送给 Microsoft 进行分析即可。有关详细信息，请参阅[Submitting malware and non-malware to Microsoft for analysis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md)。
  
## <a name="create-mail-flow-rules"></a>创建邮件流规则

创建邮件流规则 (也称为传输规则) 或自定义筛选器, 以满足您的业务需求。
  
在对生产部署新规则时，首先选择测试模式之一，以查看规则的效果。 如果规则能够按照你预期的方式工作，则将规则模式更改为“**强制**”。
  
在部署新规则时，考虑添加附加操作“生成事件报告”****，以监视正在运行的规则。 
  
如果你的组织采用部分本地、部分 Office 365 的混合部署配置，可以创建应用于整个组织的规则。 为此，请使用本地和 Office 365 都适用的条件。 虽然大多数条件都可用于这两种部署，但也有少数条件特定于特定的部署方案。 有关详细信息, 请参阅[Exchange Online 中的邮件流规则 (传输规则)](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)。
  
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

如果关注包含恶意软件的可执行文件，可以配置反恶意软件策略来阻止含有可执行内容的任何电子邮件附件。 按照[配置反恶意软件策略](../configure-anti-malware-policies.md)中的步骤操作。
  
为了加强保护，仍建议阻止以下部分或全部的扩展名：ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、ht、hta、inf、ins、isp、job、js、jse、lnk、mda、mdb、mde、mdz、msc、msi、msp、mst、pcd、reg、scr、sct、shs、url、vb、vbe、vbs、wsc、wsf 和 wsh。
  
## <a name="reporting-and-troubleshooting"></a>报告和疑难解答

使用管理中心中的报告解决一般问题和趋势。 使用消息跟踪工具来查找有关邮件的单点数据。 有关报告的详细信息，请参阅 [Exchange Online Protection 中的报告和邮件跟踪](reporting-and-message-trace-in-exchange-online-protection.md)。 有关消息跟踪工具的详细信息，请参阅[Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)。
  
## <a name="for-more-information"></a>详细信息

[EOP 一般常见问题解答](eop-general-faq.md)
  
[EOP 帮助与支持](help-and-support-for-eop.md)
  
[如何帮助确保邮件不会标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

