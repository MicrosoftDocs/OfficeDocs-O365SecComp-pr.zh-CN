---
title: 设置 EOP 服务
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/23/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: 本主题介绍了如何设置 Microsoft Exchange Online Protection (EOP)。如果您已从 Office 365 域向导登录到这里，则假如您不想使用 Exchange Online Protection，请返回到 Office 365 域向导。若要详细了解如何配置连接器，请参阅Configure mail flow using connectors in Office 365。
ms.openlocfilehash: 6c9e3becf0f86deeee92ec7cf336bdbd950ac5e2
ms.sourcegitcommit: f49ab866e21da83a0be6cb23ab7b6b4366a6a7ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "25715898"
---
# <a name="set-up-your-eop-service"></a><span data-ttu-id="3336a-105">设置 EOP 服务</span><span class="sxs-lookup"><span data-stu-id="3336a-105">Set up your EOP service</span></span>

<span data-ttu-id="3336a-p102">本主题介绍了如何设置 Microsoft Exchange Online Protection (EOP)。如果您已从 Office 365 域向导登录到这里，则假如您不想使用 Exchange Online Protection，请返回到 Office 365 域向导。若要详细了解如何配置连接器，请参阅[Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3336a-p102">This topic explains how to set up Microsoft Exchange Online Protection (EOP). If you landed here from the Office 365 domains wizard, go back to the Office 365 domains wizard if you don't want to use Exchange Online Protection. If you're looking for more information on how to configure connectors, see [Configure mail flow using connectors in Office 365](http://technet.microsoft.com/library/854b5a50-4462-4836-a092-37e208d29624.aspx).</span></span>
  
> [!NOTE]
> <span data-ttu-id="3336a-p103">此主题假设你拥有内部部署邮箱，并且想使用 EOP 对其进行保护，这称为独立方案。如果你想在使用 Exchange Online 的云中托管所有邮箱，那么不必完成本主题中的所有步骤。转到 [Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286312) 注册并购买云邮箱。如果你想在内部部署和云中分别托管一部分邮箱，这称为 混合方案。这需要更高级的邮件流设置。[Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx)解释了混合邮件流，其中包含说明如何进行设置的资源链接。</span><span class="sxs-lookup"><span data-stu-id="3336a-p103">This topic assumes you have on-premises mailboxes and you want to protect them with EOP, which is known as a standalone scenario. If you want to host all of your mailboxes in the cloud with Exchange Online, you don't have to complete all of the steps in this topic. Go to [Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286312) to sign up and purchase cloud mailboxes. If you want to host some of your mailboxes on premises and some in the cloud, this is known as a hybrid scenario. It requires more advanced mail-flow settings. [Exchange Server 2013 Hybrid Deployments](http://technet.microsoft.com/library/59e32000-4fcf-417f-a491-f1d8f9aeef9b.aspx) explains hybrid mail flow and has links to resources that show how to set it up.</span></span> 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="3336a-115">在开始之前，您需要知道什么？</span><span class="sxs-lookup"><span data-stu-id="3336a-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="3336a-116">估计完成该任务的时间：1 小时</span><span class="sxs-lookup"><span data-stu-id="3336a-116">Estimated time to complete this task: 1 hour</span></span>
    
- <span data-ttu-id="3336a-p104">要配置连接器，你的帐户必须是 Office 365 全局管理员或 Exchange 公司管理员（组织管理角色组）。有关 Office 365 权限与 Exchange 权限有何关联的信息，请参阅 [Office 365 中的权限](https://go.microsoft.com/fwlink/p/?LinkID=335814)。</span><span class="sxs-lookup"><span data-stu-id="3336a-p104">To configure connectors, your account must be an Office 365 Global Admin, or an Exchange Company Administrator (the Organization Management role group). For information about how Office 365 permissions relate to Exchange permissions, see [Permissions in Office 365](https://go.microsoft.com/fwlink/p/?LinkID=335814).</span></span>
    
- <span data-ttu-id="3336a-119">如果你还未注册 EOP，请访问 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=282660) 并选择购买或者试用服务。</span><span class="sxs-lookup"><span data-stu-id="3336a-119">If you haven't signed up for EOP, visit [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=282660) and choose to buy or try the service.</span></span> 
    
- <span data-ttu-id="3336a-120">若要了解可能适用于此主题中过程的键盘快捷键，请参阅 **Exchange 管理中心内的键盘快捷键**。</span><span class="sxs-lookup"><span data-stu-id="3336a-120">For information about keyboard shortcuts that may apply to the procedures in this topic, see **Keyboard shortcuts in the Exchange admin center**.</span></span>
    
> [!TIP]
> <span data-ttu-id="3336a-p105">遇到问题了吗？请在 Exchange 论坛中寻求帮助。 请访问以下论坛：[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612)、[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542)或 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)。</span><span class="sxs-lookup"><span data-stu-id="3336a-p105">Having problems? Ask for help in the Exchange forums. Visit the forums at [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), or [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).</span></span> 
  
## <a name="how-do-you-do-this"></a><span data-ttu-id="3336a-124">您该如何做？</span><span class="sxs-lookup"><span data-stu-id="3336a-124">How do you do this?</span></span>

### <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a><span data-ttu-id="3336a-125">步骤 1：使用 Office 365 管理中心添加并验证你的域</span><span class="sxs-lookup"><span data-stu-id="3336a-125">Step 1: Use the Office 365 admin center to add and verify your domain</span></span>

1. <span data-ttu-id="3336a-126">在 Office 365 管理中心中，导航至" **设置**"，将你的域添加到服务中。</span><span class="sxs-lookup"><span data-stu-id="3336a-126">In the Office 365 admin center, navigate to **Setup** to add your domain to the service.</span></span> 
    
    <span data-ttu-id="3336a-p106">不确定在哪里可以找到 Office 365 管理中心？在[关于 Office 365 管理中心](https://go.microsoft.com/fwlink/p/?LinkId=521888)中了解更多相关信息。</span><span class="sxs-lookup"><span data-stu-id="3336a-p106">Not sure where to find the Office 365 admin center? Learn more at [About the Office 365 admin center](https://go.microsoft.com/fwlink/p/?LinkId=521888).</span></span>
    
2. <span data-ttu-id="3336a-129">按照该步骤将适用的 DNS 记录添加到您的 DNS 托管提供程序以验证域所有权。</span><span class="sxs-lookup"><span data-stu-id="3336a-129">Follow the steps to add the applicable DNS records to your DNS-hosting provider in order to verify domain ownership.</span></span>
    
> [!TIP]
> <span data-ttu-id="3336a-130">[将域添加到 Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611) 和 [为 Office 365 创建 DNS 记录](https://support.office.com/en-us/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166)都是将你的域添加到服务和配置 DNS 的有用参考资源。</span><span class="sxs-lookup"><span data-stu-id="3336a-130">[Add your domain to Office 365](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611) and [Create DNS records for Office 365](https://support.office.com/en-us/article/create-dns-records-at-any-dns-hosting-provider-for-office-365-7b7b075d-79f9-4e37-8a9e-fb60c1d95166) are helpful resources to reference as you add your domain to the service and configure DNS.</span></span> 
  
### <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a><span data-ttu-id="3336a-131">步骤 2：添加收件人，并选择性启用 DBEB</span><span class="sxs-lookup"><span data-stu-id="3336a-131">Step 2: Add recipients and optionally enable DBEB</span></span>

<span data-ttu-id="3336a-p107">在配置您的邮件，使其流动到 EOP 服务和从 EOP 服务流出之前，我们建议将您的收件人添加到服务。执行此操作有几种方法，如[在 EOP 中管理邮件用户](manage-mail-users-in-eop.md)中所述。此外，如果您希望启用基于目录的边缘阻止 (DBEB)，以便在添加收件人之后强制实施服务内的收件人验证，您需要将域类型设置为"权威"。有关 DBEB 的详细信息，请参阅[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3336a-p107">Before configuring your mail to flow to and from the EOP service, we recommend adding your recipients to the service. There are several ways in which you can do this, as documented in [Manage mail users in EOP](manage-mail-users-in-eop.md). Also, if you want to enable Directory Based Edge Blocking (DBEB) in order to enforce recipient verification within the service after adding your recipients, you need to set your domain type to Authoritative. For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](http://technet.microsoft.com/library/ca7b7416-92ed-40ad-abdb-695be46ea2e4.aspx).</span></span>
  
### <a name="step-3-use-the-eac-to-set-up-mail-flow"></a><span data-ttu-id="3336a-136">步骤 3：使用 EAC 设置邮件流</span><span class="sxs-lookup"><span data-stu-id="3336a-136">Step 3: Use the EAC to set up mail flow</span></span>

<span data-ttu-id="3336a-p108">在能使邮件在 EOP 和你的内部部署邮件服务器间流动的 [Set up connectors to route mail between Office 365 and your own email servers](http://technet.microsoft.com/library/2e93fd60-a5ef-4e64-8e62-2b862b2d1033.aspx) (EAC) 中创建连接器。有关详细说明，请参阅Exchange 管理中心。</span><span class="sxs-lookup"><span data-stu-id="3336a-p108">Create connectors in the Exchange admin center (EAC) that enable mail flow between EOP and your on-premises mail servers. For detailed instructions, see [Set up connectors to route mail between Office 365 and your own email servers](http://technet.microsoft.com/library/2e93fd60-a5ef-4e64-8e62-2b862b2d1033.aspx).</span></span>
  
#### <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="3336a-139">您如何知道此任务有效？</span><span class="sxs-lookup"><span data-stu-id="3336a-139">How do you know this task worked?</span></span>

<span data-ttu-id="3336a-p109">使用远程连接分析器来运行测试，该测试将检查服务与您的环境之间的邮件流。有关详细信息，请参阅[Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)中的"使用远程连接分析器测试电子邮件传递"部分。</span><span class="sxs-lookup"><span data-stu-id="3336a-p109">Use the Remote Connectivity Analyzer to run a test that checks mail flow between the service and your environment. For more information, see the "Use the Remote Connectivity Analyzer to test email delivery" section in [Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx).</span></span>
  
### <a name="step-4-allow-inbound-port-25-smtp-access"></a><span data-ttu-id="3336a-142">步骤 4：允许入站端口 25 SMTP 访问</span><span class="sxs-lookup"><span data-stu-id="3336a-142">Step 4: Allow inbound port 25 SMTP access</span></span>

<span data-ttu-id="3336a-p110">配置连接器后，请等待 72 小时，允许准备 DNS 记录更新。在此之后，限制防火墙或邮件服务器上的入站端口-25 SMTP 通信，以仅接受来自 EOP 数据中心的邮件，特别是来自 [Exchange Online Protection IP 地址](exchange-online-protection-ip-addresses.md)中列出的 IP 地址的邮件。此操作将通过限制可以接收的入站邮件范围，保护内部部署环境。此外，如果邮件服务器上的设置控制了允许为邮件中继连接的 IP 地址，也要更新这些设置。</span><span class="sxs-lookup"><span data-stu-id="3336a-p110">After you configured connectors, wait 72 hours to allow propagation of your DNS-record updates. Following this, restrict inbound port-25 SMTP traffic on your firewall or mail servers to accept mail only from the EOP datacenters, specifically from the IP addresses listed at [Exchange Online Protection IP addresses](exchange-online-protection-ip-addresses.md). This protects your on-premises environment by limiting the scope of inbound messages you can receive. Additionally, if you have settings on your mail server that control the IP addresses allowed to connect for mail relay, update those settings as well.</span></span>
  
> [!TIP]
> <span data-ttu-id="3336a-p111">将 SMTP 服务器上的设置配置 60 秒的连接时间。此设置在大多数情况下都可接受，例如，在发送带有很大附件的邮件时允许有些延迟。</span><span class="sxs-lookup"><span data-stu-id="3336a-p111">Configure settings on the SMTP server with a connection time out of 60 seconds. This setting is acceptable for most situations, allowing for some delay in the case of a message sent with a large attachment, for instance.</span></span> 
  
### <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="3336a-149">步骤 5：使用命令行管理程序确保垃圾邮件被路由到每个用户的垃圾邮件文件夹</span><span class="sxs-lookup"><span data-stu-id="3336a-149">Step 5: Use the Shell to ensure that spam is routed to each user's junk email folder</span></span>

<span data-ttu-id="3336a-p112">若要确保垃圾邮件 （垃圾） 电子邮件正确路由到每个用户的垃圾邮件文件夹，您必须执行以下几个配置步骤。[确保垃圾邮件被路由到每个用户的垃圾邮件文件夹](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)中提供的步骤。</span><span class="sxs-lookup"><span data-stu-id="3336a-p112">To ensure that spam (junk) email is routed correctly to each user's Junk Email folder, you must perform a couple of configuration steps. The steps are provided in [Ensure that spam is routed to each user's Junk Email folder](../ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span>
  
<span data-ttu-id="3336a-p113">如果您不想要将邮件移动到每个用户的垃圾邮件文件夹，您可以通过编辑您在 Exchange 管理中心中的内容筛选器策略选择另一项操作。有关详细信息，请参阅[配置垃圾邮件筛选器策略](../configure-your-spam-filter-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3336a-p113">If you don't want to move messages to each user's Junk Email folder, you may choose another action by editing your content filter policies in the Exchange admin center. For more information, see [Configure your spam filter policies](../configure-your-spam-filter-policies.md).</span></span>
  
### <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a><span data-ttu-id="3336a-154">步骤 6：使用 Office 365 管理中心将 MX 记录指向 EOP</span><span class="sxs-lookup"><span data-stu-id="3336a-154">Step 6: Use the Office 365 admin center to point your MX record to EOP</span></span>

<span data-ttu-id="3336a-p114">按照 Office 365 域配置步骤更新你的域的 MX 记录，以便于你的入站电子邮件能够通过 EOP。请务必将你的 MX 记录直接指向 EOP 而不是让第三方筛选服务将电子邮件中继到 EOP。有关详细信息，请再次参阅[为 Office 365 创建 DNS 记录](https://go.microsoft.com/fwlink/p/?LinkId=304219)。</span><span class="sxs-lookup"><span data-stu-id="3336a-p114">Follow the Office 365 domain configuration steps to update your MX record for your domain, so that your inbound email flows through EOP. Be sure to point your MX record directly to EOP as opposed to having a third-party filtering service relay email to EOP. For more information, you can again reference [Create DNS records for Office 365](https://go.microsoft.com/fwlink/p/?LinkId=304219).</span></span>
  
#### <a name="how-do-you-know-this-task-worked"></a><span data-ttu-id="3336a-158">您如何知道此任务有效？</span><span class="sxs-lookup"><span data-stu-id="3336a-158">How do you know this task worked?</span></span>

<span data-ttu-id="3336a-p115">使用远程连接分析器运行测试，该测试验证您的 MX 记录。有关详细信息，请参阅[Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx)中的"使用远程连接分析器测试 MX 记录和出站连接器"部分。</span><span class="sxs-lookup"><span data-stu-id="3336a-p115">Use the Remote Connectivity Analyzer to run a test that verifies your MX record. For more information, see the "Use the Remote Connectivity Analyzer to test your MX record and Outbound connector" section in [Testing Mail Flow with the Remote Connectivity Analyzer](http://technet.microsoft.com/library/6c8c2964-d553-4329-8166-6e508dd63fa0.aspx).</span></span> 
  
<span data-ttu-id="3336a-p116">此时，您已验证经过适当配置的出站内部部署连接器的服务传递，而且已验证 MX 记录是否指向 EOP。现在，您可以选择运行以下其他测试来验证该服务是否会将电子邮件成功传递到内部部署环境：</span><span class="sxs-lookup"><span data-stu-id="3336a-p116">At this point, you've verified service delivery for a properly configured Outbound on-premises connector, and you've verified that your MX record is pointing to EOP. You can now choose to run the following additional tests to verify that an email will be successfully delivered by the service to your on-premises environment:</span></span>
  
- <span data-ttu-id="3336a-163">在远程连接分析器中，单击**Office 365**选项卡，，然后运行**入站 SMTP 电子邮件**测试位于下**Internet 电子邮件测试**。</span><span class="sxs-lookup"><span data-stu-id="3336a-163">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span></span> 
    
- <span data-ttu-id="3336a-p117">将来自基于 Web 的任何电子邮件帐户的电子邮件发送到组织中的邮件收件人，组织的域与您添加到服务上的域相匹配。使用 Microsoft Outlook 或另一个电子邮件客户端确认邮件是否已传递到内部部署邮箱。</span><span class="sxs-lookup"><span data-stu-id="3336a-p117">Send an email message from any web-based email account to a mail recipient in your organization whose domain matches the domain you added to the service. Confirm delivery of the message to the on-premises mailbox using Microsoft Outlook or another email client.</span></span>
    
- <span data-ttu-id="3336a-166">如果您想进行出站电子邮件测试，可以发送组织中一个用户的电子邮件到基于 Web 的电子邮件帐户并确认是否收到邮件。</span><span class="sxs-lookup"><span data-stu-id="3336a-166">If you want to run an outbound email test, you can send an email message from a user in your organization to a web-based email account and confirm that the message is received.</span></span>
    
> [!TIP]
> <span data-ttu-id="3336a-p118">完成安装后，您无需进行其他操作，EOP 即可删除垃圾邮件和恶意软件。EOP 会自动删除垃圾邮件和恶意软件。但是，您可以根据您的业务需求调整 EAC 中的设置。有关详细信息，请参阅[Anti-Spam and Anti-Malware Protection](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx)。 > 既然您的服务正在运行，我们建议您阅读 [配置 EOP 的最佳实践](best-practices-for-configuring-eop.md)，其中介绍了安装 EOP 后建议的设置和注意事项。</span><span class="sxs-lookup"><span data-stu-id="3336a-p118">When you've completed your setup, you don't have to perform extra steps to make EOP remove spam and malware. EOP removes spam and malware automatically. However, you can fine tune your settings in the EAC, based on your business requirements. For more information, see [Anti-Spam and Anti-Malware Protection](http://technet.microsoft.com/library/93c6c227-7442-4293-b64d-ec8f15c928db.aspx). > Now that your service is running, we recommend reading [Best practices for configuring EOP](best-practices-for-configuring-eop.md), which describes recommended settings and considerations for after you set up EOP.</span></span> 
  

