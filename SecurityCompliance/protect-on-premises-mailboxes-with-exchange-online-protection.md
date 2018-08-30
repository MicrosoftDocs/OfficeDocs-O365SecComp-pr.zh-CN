---
title: 保护内部部署邮箱与 Exchange Online Protection
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/1/2017
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
description: 即使您打算承载邮箱本地的部分或全部，您仍可以保护邮箱与 Exchange Online Protection (EOP)。若要配置连接器，您的帐户必须是 Office 365 全局管理员或 Exchange 公司管理员 （组织管理角色组）。有关 Office 365 权限与 Exchange 权限的相关信息，请参阅由 21Vianet 的 Office 365 中的分配管理员角色。如果您的 Exchange 邮箱的所有内部部署，请按照下列步骤设置 EOP 服务。
ms.openlocfilehash: 4751bb2183e61d292805d1799519644b77b08c2a
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526055"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a><span data-ttu-id="dc3d5-106">保护内部部署邮箱与 Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="dc3d5-106">Protect on-premises mailboxes with Exchange Online Protection</span></span>

> [!NOTE]
> <span data-ttu-id="dc3d5-107">本文仅适用于 Office 365 21Vianet 在中国由。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-107">This article applies only to Office 365 operated by 21Vianet in China.</span></span> 
  
<span data-ttu-id="dc3d5-p102">即使您打算承载邮箱本地的部分或全部，您仍可以保护邮箱与 Exchange Online Protection (EOP)。若要配置连接器，您的帐户必须是 Office 365 全局管理员或 Exchange 公司管理员 （组织管理角色组）。有关 Office 365 权限与 Exchange 权限的相关信息，请参阅[由 21Vianet 的 Office 365 中的分配管理员角色](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac)。如果您的 Exchange 邮箱的所有内部部署，请按照下列步骤设置 EOP 服务。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-p102">Even if you plan to host some or all of your mailboxes on-premises, you can still protect the mailboxes with Exchange Online Protection (EOP). To configure connectors, your account must be an Office 365 Global Admin, or an Exchange Company Administrator (the Organization Management role group). For information about how Office 365 permissions relate to Exchange permissions, see [Assigning admin roles in Office 365 operated by 21Vianet](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac). If all of your Exchange mailboxes are on-premise, follow these steps to set up your EOP service.</span></span> 
  
## <a name="step-1-use-the-office-365-admin-center-to-add-and-verify-your-domain"></a><span data-ttu-id="dc3d5-112">步骤 1：使用 Office 365 管理中心添加并验证你的域</span><span class="sxs-lookup"><span data-stu-id="dc3d5-112">Step 1: Use the Office 365 admin center to add and verify your domain</span></span>

1. <span data-ttu-id="dc3d5-113">在 Office 365 管理中心中，导航至" 设置"，将你的域添加到服务中。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-113">In the Office 365 admin center, navigate to Setup to add your domain to the service.</span></span>
    
2.  <span data-ttu-id="dc3d5-114">按照将适用的 DNS 记录添加到您的 DNS 托管提供商，以验证域所有权门户中的步骤。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-114">Follow the steps in the portal to add the applicable DNS records to your DNS-hosting provider in order to verify domain ownership.</span></span> 
    
> [!TIP]
> <span data-ttu-id="dc3d5-115">[添加您的域和用户移动到 Office 365 由 21Vianet](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78)和[为 Office 365 管理 DNS 记录时创建 DNS 记录](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)是引用您的域添加到服务和配置 DNS 的有用资源。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-115">[Add your domain and users to Office 365 operated by 21Vianet](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78) and [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b) are helpful resources to reference as you add your domain to the service and configure DNS.</span></span> 
  
### <a name="step-2-add-recipients-and-configure-the-domain-type"></a><span data-ttu-id="dc3d5-116">步骤 2： 添加收件人并配置域类型</span><span class="sxs-lookup"><span data-stu-id="dc3d5-116">Step 2: Add recipients and configure the domain type</span></span>

<span data-ttu-id="dc3d5-p103">在配置您的邮件，使其流动到 EOP 服务和从 EOP 服务流出之前，我们建议将您的收件人添加到服务。执行此操作有几种方法，如[在 EOP 中管理邮件用户](https://go.microsoft.com/fwlink/?LinkId=506782)中所述。此外，如果您希望启用基于目录的边缘阻止 (DBEB)，以便在添加收件人之后强制实施服务内的收件人验证，您需要将域类型设置为"权威"。有关 DBEB 的详细信息，请参阅[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781)。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-p103">Before configuring your mail to flow to and from the EOP service, we recommend adding your recipients to the service. There are several ways in which you can do this, as documented in [Manage mail users in EOP](https://go.microsoft.com/fwlink/?LinkId=506782). Also, if you want to enable Directory Based Edge Blocking (DBEB) in order to enforce recipient verification within the service after adding your recipients, you need to set your domain type to Authoritative. For more information about DBEB, see [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781).</span></span>
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a><span data-ttu-id="dc3d5-121">步骤 3：使用 EAC 设置邮件流</span><span class="sxs-lookup"><span data-stu-id="dc3d5-121">Step 3: Use the EAC to set up mail flow</span></span>

<span data-ttu-id="dc3d5-p104">在启用 EOP 与内部部署邮件服务器之间的邮件流 Exchange 管理员中心 (EAC) 创建连接器。有关详细说明，请参阅[创建所需的连接线设置通过 EOP 的基本电子邮件流](https://go.microsoft.com/fwlink/?LinkId=506780)。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-p104">Create connectors in the Exchange admin center (EAC) that enable mail flow between EOP and your on-premises mail servers. For detailed instructions, see [Create required connectors to set up basic email flow through EOP](https://go.microsoft.com/fwlink/?LinkId=506780).</span></span>
  
 <span data-ttu-id="dc3d5-124">您如何知道此任务有效？</span><span class="sxs-lookup"><span data-stu-id="dc3d5-124">How do you know this task worked?</span></span> 
  
 <span data-ttu-id="dc3d5-p105">使用远程连接分析器运行检查服务和您的环境之间的邮件流测试。有关详细信息，请参阅[测试 with Remote Connectivity Analyzer 的邮件流](https://go.microsoft.com/fwlink/?LinkId=506784)中的"使用远程连接分析器测试电子邮件传递"一节。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-p105">Use the Remote Connectivity Analyzer to run a test that checks mail flow between the service and your environment. For more information, see the "Use the Remote Connectivity Analyzer to test email delivery" section in [Test mail flow with the Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/?LinkId=506784).</span></span>
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a><span data-ttu-id="dc3d5-127">步骤 4：允许入站端口 25 SMTP 访问</span><span class="sxs-lookup"><span data-stu-id="dc3d5-127">Step 4: Allow inbound port 25 SMTP access</span></span>

<span data-ttu-id="dc3d5-p106">配置连接器后，等待 72 小时允许的 DNS 记录更新传播。接着，限制防火墙或邮件服务器以仅接受来自邮件到 EOP 数据中心，特别是从[Url 和 IP 地址范围由 21Vianet 的 Office 365](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection)中列出的 IP 地址上的入站的端口 25 SMTP 通信。这将通过限制范围可以接收的入站邮件保护您的内部部署环境。此外，如果必须在您的邮件服务器的控制允许的邮件中继连接的 IP 地址的设置，更新以及这些设置。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-p106">After you configured connectors, wait 72 hours to allow propagation of your DNS-record updates. Following this, restrict inbound port-25 SMTP traffic on your firewall or mail servers to accept mail only from the EOP datacenters, specifically from the IP addresses listed at [URLs and IP address ranges for Office 365 operated by 21Vianet](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection). This protects your on-premises environment by limiting the scope of inbound messages you can receive. Additionally, if you have settings on your mail server that control the IP addresses allowed to connect for mail relay, update those settings as well.</span></span>
  
> [!TIP]
> <span data-ttu-id="dc3d5-p107">将 SMTP 服务器上的设置配置 60 秒的连接时间。此设置在大多数情况下都可接受，例如，在发送带有很大附件的邮件时允许有些延迟。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-p107">Configure settings on the SMTP server with a connection time out of 60 seconds. This setting is acceptable for most situations, allowing for some delay in the case of a message sent with a large attachment, for instance.</span></span> 
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="dc3d5-134">步骤 5：使用命令行管理程序确保垃圾邮件被路由到每个用户的垃圾邮件文件夹</span><span class="sxs-lookup"><span data-stu-id="dc3d5-134">Step 5: Use the Shell to ensure that spam is routed to each user's junk email folder</span></span>

<span data-ttu-id="dc3d5-p108">若要确保垃圾邮件 （垃圾） 电子邮件正确路由到每个用户的垃圾邮件文件夹，您必须执行以下几个配置步骤。[确保垃圾邮件被路由到每个用户的垃圾邮件文件夹](https://go.microsoft.com/fwlink/?LinkId=506804)中提供的步骤。如果您不想要将邮件移动到每个用户的垃圾邮件文件夹，您可以通过编辑您在 Exchange 管理中心中的内容筛选器策略选择另一项操作。有关详细信息，请参阅[Configure Content Filter Policies](https://go.microsoft.com/fwlink/?LinkId=506805)。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-p108">To ensure that spam (junk) email is routed correctly to each user's Junk Email folder, you must perform a couple of configuration steps. The steps are provided in [Ensure that spam is routed to each user's Junk Email folder](https://go.microsoft.com/fwlink/?LinkId=506804). If you don't want to move messages to each user's Junk Email folder, you may choose another action by editing your content filter policies in the Exchange admin center. For more information, see [Configure Content Filter Policies](https://go.microsoft.com/fwlink/?LinkId=506805).</span></span> 
  
## <a name="step-6-use-the-office-365-admin-center-to-point-your-mx-record-to-eop"></a><span data-ttu-id="dc3d5-139">步骤 6：使用 Office 365 管理中心将 MX 记录指向 EOP</span><span class="sxs-lookup"><span data-stu-id="dc3d5-139">Step 6: Use the Office 365 admin center to point your MX record to EOP</span></span>

<span data-ttu-id="dc3d5-p109">遵循更新为您的域，MX 记录的 Office 365 域配置步骤，以便通过 EOP 的入站电子邮件流。有关详细信息，可以再次引用[为 Office 365 管理 DNS 记录时创建 DNS 记录](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b)。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-p109">Follow the Office 365 domain configuration steps to update your MX record for your domain, so that your inbound email flows through EOP. For more information, you can again reference [Create DNS records for Office 365 when you manage your DNS records](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b).</span></span>
  
<span data-ttu-id="dc3d5-142">您如何知道此任务有效？</span><span class="sxs-lookup"><span data-stu-id="dc3d5-142">How do you know this task worked?</span></span>
  
 <span data-ttu-id="dc3d5-p110">使用远程连接分析器来运行测试，验证 MX 记录。有关详细信息，请参阅[测试 with Remote Connectivity Analyzer 的邮件流](https://go.microsoft.com/fwlink/?LinkId=506784)中的"使用远程连接分析器测试 MX 记录和出站连接器"一节。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-p110">Use the Remote Connectivity Analyzer to run a test that verifies your MX record. For more information, see the "Use the Remote Connectivity Analyzer to test your MX record and Outbound connector" section in [Test mail flow with the Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/?LinkId=506784).</span></span> 
  
<span data-ttu-id="dc3d5-p111">此时，您已验证经过适当配置的出站内部部署连接器的服务传递，而且已验证 MX 记录是否指向 EOP。现在，您可以选择运行以下其他测试来验证该服务是否会将电子邮件成功传递到内部部署环境：</span><span class="sxs-lookup"><span data-stu-id="dc3d5-p111">At this point, you've verified service delivery for a properly configured Outbound on-premises connector, and you've verified that your MX record is pointing to EOP. You can now choose to run the following additional tests to verify that an email will be successfully delivered by the service to your on-premises environment:</span></span>
  
- <span data-ttu-id="dc3d5-147">在远程连接分析器中，单击**Office 365**选项卡，，然后运行**入站 SMTP 电子邮件**测试位于下**Internet 电子邮件测试**。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-147">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span></span>
    
- <span data-ttu-id="dc3d5-p112">将来自基于 Web 的任何电子邮件帐户的电子邮件发送到组织中的邮件收件人，组织的域与您添加到服务上的域相匹配。使用 Microsoft Outlook 或另一个电子邮件客户端确认邮件是否已传递到内部部署邮箱。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-p112">Send an email message from any web-based email account to a mail recipient in your organization whose domain matches the domain you added to the service. Confirm delivery of the message to the on-premises mailbox using Microsoft Outlook or another email client.</span></span>
    
- <span data-ttu-id="dc3d5-150">如果您想进行出站电子邮件测试，可以发送组织中一个用户的电子邮件到基于 Web 的电子邮件帐户并确认是否收到邮件。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-150">If you want to run an outbound email test, you can send an email message from a user in your organization to a web-based email account and confirm that the message is received.</span></span>
    
## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a><span data-ttu-id="dc3d5-151">通常不： 混合安装与本地邮箱，并在云中</span><span class="sxs-lookup"><span data-stu-id="dc3d5-151">Less common: A hybrid setup with mailboxes on-premises and in the cloud</span></span>

<span data-ttu-id="dc3d5-p113">如果您拥有 Exchange 本地邮箱和一个或多个邮箱必须在 Exchange Online 中云中，*混合*安装程序。在混合设置中，如功能共享忙/闲日历和邮件路由内部部署中协同工作和云环境。转换到 Exchange Online 邮箱时，您可能必须就地混合安装程序。混合环境设置不同 EOP 独立保护。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-p113">If you have Exchange mailboxes on-premises and one or more mailboxes in the cloud in Exchange Online, you have a  *hybrid*  setup. In a hybrid setup, features such as free/busy calendar sharing and mail routing work together in your on-premises and cloud environments. You might have a hybrid setup in place while you transition mailboxes to Exchange Online. A hybrid environment is set up differently than EOP standalone protection.</span></span> 
  
<span data-ttu-id="dc3d5-p114">您可能选择混合方案以利用大部分员工的基于云的电子邮件。您可以执行此操作时还承载一些本地邮箱;例如，对于您的法律部门。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-p114">You might choose a hybrid scenario to take advantage of cloud-based email for most of your employees. You can do this while also hosting some mailboxes on-premises; for example, for your legal department.</span></span> 
  
<span data-ttu-id="dc3d5-p115">混合安装程序可能会很复杂，但它具有许多好处。若要了解有关设置与 Exchange 的混合方案，请参阅[与 Office 365 由 21Vianet 配置 Exchange 混合部署功能](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d)。</span><span class="sxs-lookup"><span data-stu-id="dc3d5-p115">A hybrid setup can be complex, but it has many benefits. To learn more about setting up hybrid scenarios with Exchange, see [Configuring Exchange hybrid deployment features with Office 365 operated by 21Vianet](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d).</span></span>
  

