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
# <a name="best-practices-for-configuring-eop"></a><span data-ttu-id="dec61-103">配置 EOP 的最佳实践</span><span class="sxs-lookup"><span data-stu-id="dec61-103">Best practices for configuring EOP</span></span>
  
<span data-ttu-id="dec61-p101">请遵循所建议的这些 Exchange Online Protection (EOP) 最佳做法，以成功达到目的，并避免常见的配置错误。建议一般情况下使用默认的配置设置。参阅本主题的前提是，你已经完成安装过程。如果还没有完成 EOP 安装，请参阅[设置 EOP 服务](set-up-your-eop-service.md)。</span><span class="sxs-lookup"><span data-stu-id="dec61-p101">Follow these best-practice recommendations for Exchange Online Protection (EOP) in order to set yourself up for success and avoid common configuration errors. We recommend using the default configuration settings as a general rule. This topic assumes that you've already completed the setup process. If you haven't completed EOP setup, see [Set up your EOP service](set-up-your-eop-service.md).</span></span>
  
## <a name="use-a-test-domain"></a><span data-ttu-id="dec61-108">使用测试域</span><span class="sxs-lookup"><span data-stu-id="dec61-108">Use a test domain</span></span>

<span data-ttu-id="dec61-109">在高容量生产域上实施服务功能前，建议你使用测试域、子域或低容量域来尝试这些服务功能。</span><span class="sxs-lookup"><span data-stu-id="dec61-109">We recommend that you use a test domain, subdomain, or low volume domain for trying out service features before implementing them on your higher-volume, production domains.</span></span>
  
## <a name="synchronize-recipients"></a><span data-ttu-id="dec61-110">同步收件人</span><span class="sxs-lookup"><span data-stu-id="dec61-110">Synchronize recipients</span></span>

<span data-ttu-id="dec61-p102">如果你的组织在本地 Active Directory 环境中拥有现成的用户帐户，则可以将这些帐户同步到云中的 Azure Active Directory。建议使用目录同步。若要详细了解使用目录同步的具体优势以及安装步骤，请参阅[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)。</span><span class="sxs-lookup"><span data-stu-id="dec61-p102">If your organization has existing user accounts in an on-premisesActive Directory environment, you can synchronize those accounts to Azure Active Directory in the cloud. Using directory synchronization is recommended. To learn more about the benefits of using directory synchronization, and the steps for setting it up, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>
  
## <a name="spf-record-customization-to-help-prevent-spoofing"></a><span data-ttu-id="dec61-114">SPF 记录自定义帮助防止欺骗</span><span class="sxs-lookup"><span data-stu-id="dec61-114">SPF record customization to help prevent spoofing</span></span>

<span data-ttu-id="dec61-p103">时设置 EOP，您添加 SPF （发件人策略框架） 记录 eop 到您的 DNS 记录。SPF 记录有助于防止欺骗。有关如何 SPF 记录阻止欺骗和如何将您的本地 IP 地址添加到 SPF 记录的详细信息，请参阅[Set up Office 365 为了帮助防止欺骗中的 SPF](../set-up-spf-in-office-365-to-help-prevent-spoofing.md)。</span><span class="sxs-lookup"><span data-stu-id="dec61-p103">When you set up EOP, you added an SPF (sender policy framework) record for EOP to your DNS records. The SPF record helps prevent spoofing. For more information about how an SPF record prevents spoofing and how you can add your on-premises IP addresses to the SPF record, see [Set up SPF in Office 365 to help prevent spoofing](../set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> 
  
## <a name="set-anti-spam-options"></a><span data-ttu-id="dec61-118">设置反垃圾邮件选项</span><span class="sxs-lookup"><span data-stu-id="dec61-118">Set anti-spam options</span></span>

<span data-ttu-id="dec61-p104">管理您的连接筛选器设置通过将 IP 地址添加到 IP 允许和 IP 阻止列表，以及选择**启用安全列表**选项，其中应减少误报 （为垃圾邮件分类的良好邮件） 数收到。有关详细信息[配置连接筛选器策略](../configure-the-connection-filter-policy.md)。对于应用于整个组织的多个垃圾邮件设置，请了解一下[如何帮助确保邮件未标记为垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534224)或[阻止电子邮件与 Office 365 垃圾邮件筛选器以阻止假负问题垃圾邮件](https://go.microsoft.com/fwlink/p/?LinkId=534225)。如果您具有管理员级控件，并且想要防止误报或 false 负片，这些是非常有用。</span><span class="sxs-lookup"><span data-stu-id="dec61-p104">Mange your connection filter settings by adding IP addresses to IP Allow and IP Block lists, and by selecting the **Enable safe list** option, which should reduce the number of false positives (good mail that's classified as spam) you receive. Learn more at [Configure the connection filter policy](../configure-the-connection-filter-policy.md). For more spam settings that apply to the whole organization, take a look at [How to help ensure that a message isn't marked as spam](https://go.microsoft.com/fwlink/p/?LinkId=534224) or [Block email spam with the Office 365 spam filter to prevent false negative issues](https://go.microsoft.com/fwlink/p/?LinkId=534225). These are helpful if you have administrator-level control and you want to prevent false positives or false negatives.</span></span>
  
<span data-ttu-id="dec61-p105">通过审阅和 （可选） 更改默认设置来管理您的内容筛选器。例如，您可以更改为垃圾邮件检测到的邮件时会发生什么情况的操作。如果您想要使用垃圾邮件筛选保守方法，您可以配置高级垃圾邮件筛选选项。我们建议您测试这些选项首先之前实现它们在生产环境中 （通过打开其） 建议关注网络钓鱼的组织打开**SPF 记录： 硬失败**选项。有关详细信息[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)和[高级垃圾邮件筛选选项](../advanced-spam-filtering-asf-options.md)。</span><span class="sxs-lookup"><span data-stu-id="dec61-p105">Manage your content filters by reviewing and optionally changing the default settings. For example, you can change the action for what happens to spam-detected messages. If you want to pursue an aggressive approach to spam filtering, you can configure advanced spam filtering  options. We recommend that you test these options first before implementing them in your production environment (by turning them on) It's recommended that organizations who are concerned about phishing turn on the **SPF record: hard fail** option. Learn more at [Configure your spam filter policies](../configure-your-spam-filter-policies.md) and [Advanced spam filtering  options](../advanced-spam-filtering-asf-options.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dec61-p106">如果您使用默认内容筛选器操作，**移动到垃圾邮件文件夹的邮件**，以确保此操作将处理的本地邮箱，则必须配置 Exchange 邮件流规则，也称为内部部署上的传输规则服务器来检测由 EOP 添加的垃圾邮件邮件头。有关详细信息，请参阅[确保垃圾邮件被路由到每个用户的垃圾邮件文件夹](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="dec61-p106">If you are using the default content filter action, **Move message to Junk Email folder**, in order to ensure that this action will work with on-premises mailboxes, you must configure Exchange mail flow rules, also called transport rules, on your on-premises servers to detect spam headers added by EOP. For details, see [Ensure that spam is routed to each user's Junk Email folder](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> 
  
<span data-ttu-id="dec61-130">我们建议您查看[anti-spam protection FAQ](../anti-spam-protection-faq.md)，其中包括出站邮件最佳实践部分，有助于确保出站邮件传递。</span><span class="sxs-lookup"><span data-stu-id="dec61-130">We recommend that you review the [Anti-spam protection FAQ](../anti-spam-protection-faq.md), including the outbound mailing best practices section, which will help ensure that your outbound mail is delivered.</span></span>
  
<span data-ttu-id="dec61-p107">您可以提交假负 （垃圾邮件） 和误报 （非垃圾邮件） 向 Microsoft 进行分析以下几种方式。有关详细信息，请参阅[提交垃圾邮件和非垃圾邮件和网络钓鱼诈骗邮件提交给 Microsoft 进行分析](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="dec61-p107">You can submit false negatives (spam) and false positives (non-spam) to Microsoft for analysis in several ways. For details, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](../submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span>
  
## <a name="set-anti-malware-options"></a><span data-ttu-id="dec61-133">设置反恶意软件选项</span><span class="sxs-lookup"><span data-stu-id="dec61-133">Set anti-malware options</span></span>

<span data-ttu-id="dec61-p108">查看并微调 Exchange 管理员 center(EAC) 中的恶意软件筛选器设置。有关详细信息[配置反恶意软件策略](../configure-anti-malware-policies.md)。我们还建议阅读有关其他的常见问题和解答与我们的[反恶意软件保护常见问题](../anti-malware-protection-faq-eop.md)中的反恶意软件保护。</span><span class="sxs-lookup"><span data-stu-id="dec61-p108">Review and fine tune your malware filter settings in the Exchange admin center(EAC). Learn more at [Configure anti-malware policies](../configure-anti-malware-policies.md). We also recommend reading about other frequently asked questions and answers pertaining to anti-malware protection in our [Anti-malware protection FAQ ](../anti-malware-protection-faq-eop.md).</span></span>
  
<span data-ttu-id="dec61-p109">如果你对包含恶意软件的可执行文件有点担心，则可以创建一个 Exchange 邮件流规则来拦截所有包含可执行内容的电子邮件附件。若要拦截[Use mail flow rules to inspect message attachments](https://support.microsoft.com/kb/2959596)中"传输规则检查支持的可执行文件类型"下方列出的文件类型，请按 [How to reduce malware threats through file attachment blocking in Exchange Online Protection](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)（如何在 Exchange Online Protection 中通过文件附件拦截来减少恶意软件威胁）中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="dec61-p109">If you're concerned about executable files containing malware, you can create an Exchange mail flow rule that blocks any email attachment that has executable content. Follow the steps in [How to reduce malware threats through file attachment blocking in Exchange Online Protection](https://support.microsoft.com/kb/2959596) in order to block the file types listed under "Supported executable file types for transport rule inspection" in [Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx).</span></span>
  
<span data-ttu-id="dec61-p110">在 EAC 中，可以使用常见的附件类型筛选器。选择**保护** \> **恶意软件筛选器**。您可以创建 Exchange 邮件流规则，也称为传输规则，阻止具有可执行内容任何电子邮件附件。</span><span class="sxs-lookup"><span data-stu-id="dec61-p110">You can use the Common Attachment Types Filter in the EAC. Select **protection** \> **malware filters**. You can create an Exchange mail flow rule, also known as transport rule, that blocks any email attachment that has executable content.</span></span> 
  
<span data-ttu-id="dec61-p111">为加强保护，我们还建议使用邮件流规则阻止下列扩展名的部分或全部： ade、 adp、 ani、 营业活动报表、 bat、 chm、 cmd、 com、 cpl、 crt、 hlp、 超线程、 hta、 inf、 项、 isp、 作业、 js、 jse、 lnk，mda、 mdb、 mde、 mdz、 msc、 msi、 mspmst、 pcd、 注册表、 scr、 sct、 shs、 url、 vb、 vbe、 vbs、 wsc、 wsf、 wsh。这可以通过使用的**任何附件的文件扩展名包含这些词**的条件。</span><span class="sxs-lookup"><span data-stu-id="dec61-p111">For increased protection, we also recommend using mail flow rules to block some or all of the following extensions: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh. This can be done by using the **Any attachment file extension includes these words** condition.</span></span> 
  
<span data-ttu-id="dec61-p112">管理员和最终用户可以提交通过筛选器的恶意软件，或提交被误检为恶意软件的文件，只需将其发送给 Microsoft 进行分析即可。有关详细信息，请参阅[Submitting malware and non-malware to Microsoft for analysis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md)。</span><span class="sxs-lookup"><span data-stu-id="dec61-p112">Administrators and end users can submit malware that made it past the filters, or submit a file that you think was incorrectly identified as malware, by sending it to Microsoft for analysis. For more information, see [Submitting malware and non-malware to Microsoft for analysis](../submitting-malware-and-non-malware-to-microsoft-for-analysis.md).</span></span>
  
## <a name="create-mail-flow-rules"></a><span data-ttu-id="dec61-146">创建邮件流规则</span><span class="sxs-lookup"><span data-stu-id="dec61-146">Create mail flow rules</span></span>

<span data-ttu-id="dec61-147">创建邮件流规则（也称为传输规则或自定义筛选器），满足业务需求。</span><span class="sxs-lookup"><span data-stu-id="dec61-147">Create mail flow rules, also called transport rules or custom filters, to meet your business needs.</span></span>
  
<span data-ttu-id="dec61-p113">到生产环境中部署一个新规则时，选择一种测试模式，查看规则的效果。满意规则处理预期的方式，将规则模式更改为**Enforce**。</span><span class="sxs-lookup"><span data-stu-id="dec61-p113">When you deploy a new rule to production, select one of the test modes first to see the effect of the rule. Once you are satisfied that the rule is working in the manner intended, change the rule mode to **Enforce**.</span></span>
  
<span data-ttu-id="dec61-150">在部署新规则时，请考虑添加附加操作**生成事件报告**，以监视操作中的规则。</span><span class="sxs-lookup"><span data-stu-id="dec61-150">When you deploy new rules, consider adding the additional action of **Generate Incident Report** to monitor the rule in action.</span></span> 
  
<span data-ttu-id="dec61-p114">如果你的组织采用部分本地、部分 Office 365 的混合部署配置，可以创建应用于整个组织的规则。为此，请使用本地和 Office 365 都适用的条件。虽然大多数条件都可用于这两种部署，但也有少数条件特定于特定的部署方案。有关详细信息，请参阅[Mail flow or Transport rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx)。</span><span class="sxs-lookup"><span data-stu-id="dec61-p114">If you are in a hybrid deployment configuration, with part of your organization on-premises and part in Office 365, you can create rules that apply to the entire organization. To do this, use conditions that are available both on-premises and in Office 365. While most conditions are available in both deployments, there is a small set that is specific to a particular deployment scenario. Learn more at [Mail flow or Transport rules](http://technet.microsoft.com/library/743bd525-0ca2-426d-b76c-b4a052bc8886.aspx).</span></span>
  
<span data-ttu-id="dec61-p115">如果希望检查在组织内部传递的邮件的附件，可以通过设置邮件流规则来实现。然后，可以根据这些附件的内容或特征对经过检查的邮件采取操作。有关详细信息，请参阅[Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx)。</span><span class="sxs-lookup"><span data-stu-id="dec61-p115">If you want to inspect email attachments for messages in-transit within your organization, you can do this by setting up mail flow rules. Then, take action on the messages that were inspected based on the content or characteristics of those attachments. Learn more at [Use mail flow rules to inspect message attachments](http://technet.microsoft.com/library/874d1c78-a8ec-4938-b388-d3208c2fa971.aspx).</span></span>
  
### <a name="phishing-and-spoofing-prevention"></a><span data-ttu-id="dec61-158">网络钓鱼和欺骗预防</span><span class="sxs-lookup"><span data-stu-id="dec61-158">Phishing and Spoofing Prevention</span></span>

<span data-ttu-id="dec61-p116">通过检测电子邮件中个人信息退出组织的时间，可以提高防钓鱼保护。例如，可以在邮件流规则中使用下列正则表达式，检测可能危及隐私的个人财务数据或信息传输：</span><span class="sxs-lookup"><span data-stu-id="dec61-p116">You can improve anti-phishing protection by the detecting when personal information exits the organization in email. For example, you can use the following regular expressions in mail flow rules to detect transmission of personal financial data or information that may compromise privacy:</span></span>
  
- <span data-ttu-id="dec61-161">\d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d (MasterCard Visa)</span><span class="sxs-lookup"><span data-stu-id="dec61-161">\d\d\d\d\s\d\d\d\d\s\d\d\d\d\s\d\d\d\d (MasterCard Visa)</span></span>
    
- <span data-ttu-id="dec61-162">\d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d (American Express)</span><span class="sxs-lookup"><span data-stu-id="dec61-162">\d\d\d\d\s\d\d\d\d\d\d\s\d\d\d\d\d (American Express)</span></span>
    
- <span data-ttu-id="dec61-163">\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d（任何 16 位数字）</span><span class="sxs-lookup"><span data-stu-id="dec61-163">\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d\d (any 16-digit number)</span></span>
    
- <span data-ttu-id="dec61-164">\d\d\d\-\d\d\-\d\d\d\d (Social Security Numbers)</span><span class="sxs-lookup"><span data-stu-id="dec61-164">\d\d\d\-\d\d\-\d\d\d\d (Social Security Numbers)</span></span>
    
<span data-ttu-id="dec61-p117">通过阻止似乎是从你自己的域发送的入站恶意电子邮件，也可以成功减少垃圾邮件和网络钓鱼。例如，可以创建一个邮件流规则，拒绝从你的公司域发送到同一个公司域的邮件，以阻止此类发件人伪造。</span><span class="sxs-lookup"><span data-stu-id="dec61-p117">Successful spam and phishing campaigns can also be reduced by blocking inbound, malicious emails that appear to have been sent from your own domain. For example, you can create a mail flow rule that rejects messages from your company domain sent to the same company domain to block this type of sender forgery.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="dec61-p118">我们建议仅当您确定您的域中没有合法电子邮件从 Internet 发送到邮件服务器时，才创建此拒绝规则。当邮件从组织中的某位用户发送给外部收件人，并随后转发给组织中的其他收件人时，会发生此问题。</span><span class="sxs-lookup"><span data-stu-id="dec61-p118">We recommend creating this reject rule only in cases where you are certain that no legitimate email from your domain is sent from the Internet to your mail server. This can happen in cases where a message is sent from a user in your organization to an outside recipient and subsequently forwarded to another recipient in your organization.</span></span> 
  
### <a name="extension-blocking"></a><span data-ttu-id="dec61-169">扩展名阻止</span><span class="sxs-lookup"><span data-stu-id="dec61-169">Extension Blocking</span></span>

<span data-ttu-id="dec61-p119">如果您担心包含恶意软件的可执行文件，您可以配置反恶意软件策略来阻止具有可执行内容任何电子邮件附件。按照[配置反恶意软件策略](../configure-anti-malware-policies.md)中的步骤。</span><span class="sxs-lookup"><span data-stu-id="dec61-p119">If you're concerned about executable files containing malware, you can configure anti-malware policies to block any email attachment that has executable content. Follow the steps in [Configure anti-malware policies](../configure-anti-malware-policies.md).</span></span>
  
<span data-ttu-id="dec61-172">为了加强保护，仍建议阻止以下部分或全部的扩展名：ade、adp、ani、bas、bat、chm、cmd、com、cpl、crt、hlp、ht、hta、inf、ins、isp、job、js、jse、lnk、mda、mdb、mde、mdz、msc、msi、msp、mst、pcd、reg、scr、sct、shs、url、vb、vbe、vbs、wsc、wsf 和 wsh。</span><span class="sxs-lookup"><span data-stu-id="dec61-172">For increased protection, we also recommend that you block some or all of the following extensions: ade, adp, ani, bas, bat, chm, cmd, com, cpl, crt, hlp, ht, hta, inf, ins, isp, job, js, jse, lnk, mda, mdb, mde, mdz, msc, msi, msp, mst, pcd, reg, scr, sct, shs, url, vb, vbe, vbs, wsc, wsf, wsh.</span></span>
  
## <a name="reporting-and-troubleshooting"></a><span data-ttu-id="dec61-173">报告和疑难解答</span><span class="sxs-lookup"><span data-stu-id="dec61-173">Reporting and troubleshooting</span></span>

<span data-ttu-id="dec61-p120">查看 Office 365 管理中心内的报告，对常见问题和趋势进行故障排除。使用消息跟踪工具来查找有关邮件的单点数据。有关报告的详细信息，请参阅 [Exchange Online Protection 中的报告和邮件跟踪](reporting-and-message-trace-in-exchange-online-protection.md)。有关消息跟踪工具的详细信息，请参阅[Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx)。</span><span class="sxs-lookup"><span data-stu-id="dec61-p120">Troubleshoot general issues and trends by using the reports in the Office 365 admin center. Find single point specific data about a message by using the message trace tool. Learn more about reporting at [Reporting and message trace in Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Learn more about the message trace tool at [Trace an Email Message](http://technet.microsoft.com/library/0c83cde6-5b09-4106-8587-c200cdc59094.aspx).</span></span>
  
## <a name="for-more-information"></a><span data-ttu-id="dec61-178">详细信息</span><span class="sxs-lookup"><span data-stu-id="dec61-178">For more information</span></span>

[<span data-ttu-id="dec61-179">EOP 一般常见问题解答</span><span class="sxs-lookup"><span data-stu-id="dec61-179">EOP general FAQ</span></span>](eop-general-faq.md)
  
[<span data-ttu-id="dec61-180">EOP 帮助与支持</span><span class="sxs-lookup"><span data-stu-id="dec61-180">Help and support for EOP</span></span>](help-and-support-for-eop.md)
  
[<span data-ttu-id="dec61-181">EOP 入门视频</span><span class="sxs-lookup"><span data-stu-id="dec61-181">Videos for getting started with EOP</span></span>](videos-for-getting-started-with-eop.md)
  
[<span data-ttu-id="dec61-182">如何帮助确保邮件不会标记为垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="dec61-182">How to help ensure that a message isn't marked as spam</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534224)
  
[<span data-ttu-id="dec61-183">使用 Office 365 垃圾邮件筛选器阻止垃圾电子邮件，以防止出现漏报问题</span><span class="sxs-lookup"><span data-stu-id="dec61-183">Block email spam with the Office 365 spam filter to prevent false negative issues</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=534225)
  

