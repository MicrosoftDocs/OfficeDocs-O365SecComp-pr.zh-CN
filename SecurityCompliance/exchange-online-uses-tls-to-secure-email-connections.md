---
title: Exchange Online 如何使用 TLS 保护 Office 365 中的电子邮件连接
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/2/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 4cde0cda-3430-4dc0-b489-f2c0736c929f
description: 了解 Exchange Online 和 Office 365 使用传输层安全性 (TLS) 和向前保密 (FS) 安全电子邮件通信。也会获得有关 Microsoft Exchange Online 的颁发证书的信息。
ms.openlocfilehash: 079a6f574838f5710dbbbcb53726799abfae1d3a
ms.sourcegitcommit: ddfa0ac1f8ef95a78dcc1468241ef29363d56b5b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "23520141"
---
# <a name="how-exchange-online-uses-tls-to-secure-email-connections-in-office-365"></a><span data-ttu-id="4d2e9-104">Exchange Online 如何使用 TLS 保护 Office 365 中的电子邮件连接</span><span class="sxs-lookup"><span data-stu-id="4d2e9-104">How Exchange Online uses TLS to secure email connections in Office 365</span></span>

<span data-ttu-id="4d2e9-p102">了解 Exchange Online 和 Office 365 使用传输层安全性 (TLS) 和向前保密 (FS) 安全电子邮件通信。此外提供了有关 Exchange Online 的由 Microsoft 颁发证书的信息。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-p102">Learn how Exchange Online and Office 365 use Transport Layer Security (TLS) and Forward Secrecy (FS) to secure email communications. Also provides information about the certificate issued by Microsoft for Exchange Online.</span></span>
  
## <a name="tls-basics-for-office-365-and-exchange-online"></a><span data-ttu-id="4d2e9-107">Office 365 和 Exchange Online 的 TLS 基础</span><span class="sxs-lookup"><span data-stu-id="4d2e9-107">TLS basics for Office 365 and Exchange Online</span></span>

<span data-ttu-id="4d2e9-p103">传输层安全性 (TLS) 和 SSL 了 TLS 以前, 是通过使用安全证书加密计算机之间的连接通过网络安全通信的加密协议。TLS 取代安全套接字层 (SSL) 和通常称作 SSL 3.1。为 Exchange Online 中，我们使用 TLS 加密我们 Exchange 服务器之间的连接我们 Exchange 服务器和其他服务器，例如您的本地 Exchange 服务器或收件人的邮件服务器之间的连接。一旦加密的连接，通过该连接发送的所有数据被都发送通过加密通道。但是，如果转发通过 TLS 加密连接发送一条消息，该邮件不一定被加密。这是因为简单地说，TLS 不加密邮件，只需的连接。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-p103">Transport Layer Security (TLS), and SSL that came before TLS, are cryptographic protocols that secure communication over a network by using security certificates to encrypt a connection between computers. TLS supersedes Secure Sockets Layer (SSL) and is often referred to as SSL 3.1. For Exchange Online, we use TLS to encrypt the connections between our Exchange servers and the connections between our Exchange servers and other servers such as your on-premises Exchange servers or your recipients' mail servers. Once the connection is encrypted, all data sent through that connection is sent through the encrypted channel. However, if you forward a message that was sent through a TLS-encrypted connection, that message isn't necessarily encrypted. This is because, in simple terms, TLS doesn't encrypt the message, just the connection.</span></span>
  
<span data-ttu-id="4d2e9-p104">如果您想要加密邮件，您需要使用一种加密技术对邮件内容进行加密，例如 Office 邮件加密。有关 Office 365 中邮件加密选项的信息，请参阅 [Email encryption in Office 365](email-encryption.md)和 [Office 365 Message Encryption (OME)](ome.md)。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-p104">If you want to encrypt the message you need to use an encryption technology that encrypts the message contents, for example, something like Office Message Encryption. See [Email encryption in Office 365](email-encryption.md) and [Office 365 Message Encryption (OME)](ome.md) for information on message encryption options in Office 365.</span></span> 
  
<span data-ttu-id="4d2e9-p105">我们建议在想要设置的 Office 365 和内部部署组织或其他组织，如合作伙伴之间的通信方式安全通道的情况下使用 TLS。Exchange Online 总是首先尝试使用 TLS 保护您的电子邮件但不能始终如果这样做另一方不提供 TLS 安全。继续阅读以找出如何使用*连接器*保护您的内部服务器或重要的合作伙伴的所有邮件。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-p105">We recommend using TLS in situations where you want to set up a secure channel of correspondence between Office 365 and your on-premises organization or another organization, such as a partner. Exchange Online always attempts to use TLS first to secure your email but cannot always do this if the other party does not offer TLS security. Keep reading to find out how you can secure all mail to your on-premises servers or important partners by using  *connectors*.</span></span> 
  
## <a name="how-exchange-online-uses-tls-between-exchange-online-customers"></a><span data-ttu-id="4d2e9-119">Exchange Online 如何在 Exchange Online 客户之间使用 TLS</span><span class="sxs-lookup"><span data-stu-id="4d2e9-119">How Exchange Online uses TLS between Exchange Online customers</span></span>

<span data-ttu-id="4d2e9-p106">Exchange Online 服务器始终通过 TLS 1.2 加密到我们数据中心其他 Exchange Online 服务器的连接。当你发送邮件至 Office 365 组织内的收件人时，该电子邮件将自动通过使用 TLS 加密的连接发送。此外，你发送至其他 Office 365 客户的所有电子邮件都将通过使用 TLS 加密的连接发送，并使用向前保密进行保护。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-p106">Exchange Online servers always encrypt connections to other Exchange Online servers in our datacenters with TLS 1.2. When you send mail to a recipient that is within your Office 365 organization, that email is automatically sent over a connection that is encrypted using TLS. Also, all email that you send to other Office 365 customers is sent over connections that are encrypted using TLS and are secured using Forward Secrecy.</span></span>
  
## <a name="how-office-365-uses-tls-between-office-365-and-external-trusted-partners"></a><span data-ttu-id="4d2e9-123">Office 365 如何使用 Office 365 和外部的受信任合作伙伴之间的 TLS</span><span class="sxs-lookup"><span data-stu-id="4d2e9-123">How Office 365 uses TLS between Office 365 and external, trusted partners</span></span>

<span data-ttu-id="4d2e9-p107">默认情况下，Exchange Online 始终使用机会型 TLS。这意味着 Exchange Online 始终尝试首先，加密连接与最安全的 TLS 版本然后直到找到一个双方都同意在其上的工作方式向列表下的 TLS 密码。除非您已配置 Exchange Online 以确保安全连接通过仅发送给该收件人的邮件，然后默认情况下将发送邮件未加密如果收件人组织不支持 TLS 加密。机会型 TLS 足以满足大多数企业。但是，for business 内具有合规性要求，例如医疗、 银行业或政府机构，您可以配置 Exchange Online 需要，或强制，TLS。有关说明，请参阅[配置邮件流，使用 Office 365 中的连接器](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-p107">By default, Exchange Online always uses opportunistic TLS. This means Exchange Online always tries to encrypt connections with the most secure version of TLS first, then works its way down the list of TLS ciphers until it finds one on which both parties can agree. Unless you have configured Exchange Online to ensure that messages to that recipient are only sent through secure connections, then by default the message will be sent unencrypted if the recipient organization doesn't support TLS encryption. Opportunistic TLS is sufficient for most businesses. However, for business that have compliance requirements such as medical, banking, or government organizations, you can configure Exchange Online to require, or force, TLS. For instructions, see [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).</span></span>
  
<span data-ttu-id="4d2e9-p108">如果您决定组织和受信任的合作伙伴组织之间配置 TLS，Exchange Online 可用于强制的 TLS 创建受信任的通信通道。强制的 TLS 需要合作伙伴组织进行身份验证到 Exchange Online 安全证书才能将邮件发送给您。您的伙伴需要管理他们自己的证书，才能执行此操作。在 Exchange Online 中，我们使用连接器来保护您从未经授权的访问到达收件人的电子邮件提供商之前发送的邮件。有关使用连接器配置邮件流的信息，请参阅[配置邮件流，使用 Office 365 中的连接器](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-p108">If you decide to configure TLS between your organization and a trusted partner organization, Exchange Online can use forced TLS to create trusted channels of communication. Forced TLS requires your partner organization to authenticate to Exchange Online with a security certificate in order to send mail to you. Your partner will need to manage their own certificates in order to do this. In Exchange Online, we use connectors to protect messages that you send from unauthorized access before they arrive at the recipient's email provider. For information on using connectors to configure mail flow, see [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).</span></span>
  
## <a name="tls-and-hybrid-exchange-server-deployments"></a><span data-ttu-id="4d2e9-135">TLS 和混合 Exchange Server 部署</span><span class="sxs-lookup"><span data-stu-id="4d2e9-135">TLS and hybrid Exchange Server deployments</span></span>

<span data-ttu-id="4d2e9-p109">如果您在管理 Exchange 混合部署，您的内部部署 Exchange 服务器需要对 Office 365 使用以便其邮箱向收件人发送邮件的安全证书进行身份验证是仅在 Office 365。因此，您需要管理自己的本地 Exchange 服务器的安全证书。您还可以安全地必须存储和维护这些服务器证书。有关管理混合部署中的证书的详细信息，请参阅[混合部署的证书要求](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-p109">If you are managing a hybrid Exchange deployment, your on-premises Exchange server needs to authenticate to Office 365 using a security certificate in order to send mail to recipients whose mailboxes are only in Office 365. As a result, you need to manage your own security certificates for your on-premises Exchange servers. You must also securely store and maintain these server certificates. For more information about managing certificates in hybrid deployments, see [Certificate requirements for hybrid deployments](https://technet.microsoft.com/library/hh563848%28v=exchg.150%29.aspx).</span></span>
  
## <a name="how-to-set-up-forced-tls-for-exchange-online-in-office-365"></a><span data-ttu-id="4d2e9-140">如何在 Office 365 中为 Exchange Online 设置强制 TLS</span><span class="sxs-lookup"><span data-stu-id="4d2e9-140">How to set up forced TLS for Exchange Online in Office 365</span></span>

<span data-ttu-id="4d2e9-p110">对于 Exchange Online 客户，为了强制 TLS，以保护所有发送和接收电子邮件，您需要设置多个连接器的要求 TLS。您需要一个连接器的电子邮件发送到用户邮箱和其他从您的用户邮箱发送的电子邮件的连接器。在 Office 365 中 Exchange 管理中心创建这些连接器。有关说明，请参阅[配置邮件流，使用 Office 365 中的连接器](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-p110">For Exchange Online customers, in order for forced TLS to work to secure all of your sent and received email, you need to set up more than one connector that requires TLS. You'll need one connector for email sent to your user mailboxes and another connector for email sent from your user mailboxes. Create these connectors in the Exchange admin center in Office 365. For instructions, see [Configure mail flow using connectors in Office 365](https://technet.microsoft.com/library/ms.exch.eac.connectorselection%28v=exchg.150%29.aspx).</span></span>
  
## <a name="tls-certificate-information-for-exchange-online"></a><span data-ttu-id="4d2e9-145">Exchange Online 的 TLS 证书信息</span><span class="sxs-lookup"><span data-stu-id="4d2e9-145">TLS certificate information for Exchange Online</span></span>

<span data-ttu-id="4d2e9-p111">下表中介绍了使用 Exchange Online 证书信息。如果您的业务合作伙伴设置其电子邮件服务器上强制 TLS，您需要提供此信息与它们。请注意，为了安全起见，我们证书执行更改经常。我们已推出更新到我们证书我们数据中心内。有效的 2018 年 9 月 3，是新的证书。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-p111">The certificate information used by Exchange Online is described in the following table. If your business partner is setting up forced TLS on their email server, you will need to provide this information to them. Be aware that for security reasons, our certificates do change from time to time. We have rolled out an update to our certificate within our datacenters. The new certificate is valid from September 3, 2018.</span></span>
  
 <span data-ttu-id="4d2e9-151">**当前 2018 年 9 月 3，从有效的证书信息**</span><span class="sxs-lookup"><span data-stu-id="4d2e9-151">**Current certificate information valid from September 3, 2018**</span></span>
  
|<span data-ttu-id="4d2e9-152">**属性**</span><span class="sxs-lookup"><span data-stu-id="4d2e9-152">**Attribute**</span></span>|<span data-ttu-id="4d2e9-153">**值**</span><span class="sxs-lookup"><span data-stu-id="4d2e9-153">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4d2e9-154">证书颁发机构根颁发者</span><span class="sxs-lookup"><span data-stu-id="4d2e9-154">Certificate authority root issuer</span></span>  <br/> |<span data-ttu-id="4d2e9-155">GlobalSign 根 CA – R1</span><span class="sxs-lookup"><span data-stu-id="4d2e9-155">GlobalSign Root CA – R1</span></span> <br/> |
|<span data-ttu-id="4d2e9-156">证书名称</span><span class="sxs-lookup"><span data-stu-id="4d2e9-156">Certificate name</span></span>  <br/> |<span data-ttu-id="4d2e9-157">mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4d2e9-157">mail.protection.outlook.com</span></span>  <br/> |
|<span data-ttu-id="4d2e9-158">组织</span><span class="sxs-lookup"><span data-stu-id="4d2e9-158">Organization</span></span>  <br/> |<span data-ttu-id="4d2e9-159">Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="4d2e9-159">Microsoft Corporation</span></span>  <br/> |
|<span data-ttu-id="4d2e9-160">组织单位</span><span class="sxs-lookup"><span data-stu-id="4d2e9-160">Organization unit</span></span>  <br/> |  <br/> |
|<span data-ttu-id="4d2e9-161">证书的密钥长度</span><span class="sxs-lookup"><span data-stu-id="4d2e9-161">Certificate key strength</span></span>  <br/> |<span data-ttu-id="4d2e9-162">2048</span><span class="sxs-lookup"><span data-stu-id="4d2e9-162">2048</span></span>  <br/> |
   
 <span data-ttu-id="4d2e9-163">**有效 2018 年 9 月 3，直到已弃用的证书信息**</span><span class="sxs-lookup"><span data-stu-id="4d2e9-163">**Deprecated certificate information valid until September 3, 2018**</span></span>
  
<span data-ttu-id="4d2e9-164">为了帮助确保顺利过渡，我们将继续提供您引用的旧证书信息的一些时间，但是，您应使用当前的证书信息从现在起。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-164">To help ensure a smooth transition, we will continue to provide the old certificate information for your reference for some time, however, you should use the current certificate information from now on.</span></span>
  
****

|<span data-ttu-id="4d2e9-165">**属性**</span><span class="sxs-lookup"><span data-stu-id="4d2e9-165">**Attribute**</span></span>|<span data-ttu-id="4d2e9-166">**值**</span><span class="sxs-lookup"><span data-stu-id="4d2e9-166">**Value**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4d2e9-167">证书颁发机构根颁发者</span><span class="sxs-lookup"><span data-stu-id="4d2e9-167">Certificate authority root issuer</span></span>  <br/> |<span data-ttu-id="4d2e9-168">Baltimore CyberTrust 根</span><span class="sxs-lookup"><span data-stu-id="4d2e9-168">Baltimore CyberTrust Root</span></span>  <br/> |
|<span data-ttu-id="4d2e9-169">证书名称</span><span class="sxs-lookup"><span data-stu-id="4d2e9-169">Certificate name</span></span>  <br/> |<span data-ttu-id="4d2e9-170">mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="4d2e9-170">mail.protection.outlook.com</span></span>  <br/> |
|<span data-ttu-id="4d2e9-171">组织</span><span class="sxs-lookup"><span data-stu-id="4d2e9-171">Organization</span></span>  <br/> |<span data-ttu-id="4d2e9-172">Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="4d2e9-172">Microsoft Corporation</span></span>  <br/> |
|<span data-ttu-id="4d2e9-173">组织单位</span><span class="sxs-lookup"><span data-stu-id="4d2e9-173">Organization unit</span></span>  <br/> |<span data-ttu-id="4d2e9-174">Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="4d2e9-174">Microsoft Corporation</span></span>  <br/> |
|<span data-ttu-id="4d2e9-175">证书的密钥长度</span><span class="sxs-lookup"><span data-stu-id="4d2e9-175">Certificate key strength</span></span>  <br/> |<span data-ttu-id="4d2e9-176">2048</span><span class="sxs-lookup"><span data-stu-id="4d2e9-176">2048</span></span>  <br/> |
   
## <a name="prepare-for-the-new-exchange-online-certificate"></a><span data-ttu-id="4d2e9-177">准备新的 Exchange Online 证书</span><span class="sxs-lookup"><span data-stu-id="4d2e9-177">Prepare for the new Exchange Online certificate</span></span>

<span data-ttu-id="4d2e9-p112">新的证书是由不同的证书颁发机构 (CA) 颁发的使用 Exchange Online 的上一个证书。因此，您可能需要执行一些操作才能使用新的证书。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-p112">The new certificate is issued by a different certificate authority (CA) from the previous certificate used by Exchange Online. As a result, you may need to perform some actions in order to use the new certificate.</span></span>

<span data-ttu-id="4d2e9-p113">新的证书要求连接到该新 CA 的验证证书一部分的终结点。无法执行此操作会导致受到产生负面影响的邮件流。如果您有防火墙，仅允许的邮件服务器的服务器连接使用某些目标的邮件保护需要检查您的服务器是否能够验证新的证书。若要确认您的服务器可以使用新的证书，请完成下列步骤：</span><span class="sxs-lookup"><span data-stu-id="4d2e9-p113">The new certificate requires connecting to the endpoints of the new CA as part of validating the certificate. Failure to do so can result in mail flow being negatively affected. If you protect your mail servers with firewalls that only let the mail servers connect with certain destinations you need to check if your server is able to validate the new certificate. To confirm that your server can use the new certificate, complete these steps:</span></span>

1. <span data-ttu-id="4d2e9-184">连接到本地 Exchange 服务器使用 Windows PowerShell，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4d2e9-184">Connect to your local Exchange Server using Windows PowerShell and then run the following command:</span></span>  
  `certutil -URL http://crl.globalsign.com/gsorganizationvalsha2g3.crl`
2. <span data-ttu-id="4d2e9-185">在出现的窗口中，选择**检索**。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-185">On the window that appears, choose **Retrieve**.</span></span>
3. <span data-ttu-id="4d2e9-p114">当该实用程序完成其检查它返回状态。如果状态显示**确定**，然后您的邮件服务器可以成功验证新的证书。如果没有，您需要确定导致失败的连接。很可能需要更新的防火墙设置。需要访问的终结点的完整列表包括：</span><span class="sxs-lookup"><span data-stu-id="4d2e9-p114">When the utility completes its check it returns a status. If the status displays **OK**, then your mail server can successfully validate the new certificate. If not, you need to determine what is causing the connections to fail. Most likely, you need to update the settings of a firewall. The full list of endpoints that need to be accessed include:</span></span>
    - <span data-ttu-id="4d2e9-191">ocsp.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="4d2e9-191">ocsp.globalsign.com</span></span>
     - <span data-ttu-id="4d2e9-192">crl.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="4d2e9-192">crl.globalsign.com</span></span>
     - <span data-ttu-id="4d2e9-193">secure.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="4d2e9-193">secure.globalsign.com</span></span>   

<span data-ttu-id="4d2e9-p115">通常，您收到更新为自动通过 Windows Update 根证书。但是某些部署具有其他安全就地禁止自动发生这些更新。在其中 Windows Update 不能自动更新根证书这些锁定的部署中，您需要确保安装了正确的根 CA 证书通过完成下列步骤：</span><span class="sxs-lookup"><span data-stu-id="4d2e9-p115">Normally, you receive updates to your root certificates automatically through Windows Update. However some deployments have additional security in place that prevents these updates from occurring automatically. In these locked-down deployments where Windows Update can't automatically update root certificates, you need to ensure that the correct root CA certificate is installed by completing these steps:</span></span>
1.  <span data-ttu-id="4d2e9-197">连接到本地 Exchange 服务器使用 Windows PowerShell，然后运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4d2e9-197">Connect to your local Exchange Server using Windows PowerShell and then run the following command:</span></span>  
  `certmgr.msc`
2. <span data-ttu-id="4d2e9-198">下**受信任根证书颁发机构/证书**，请确认列出了新的证书。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-198">Under **Trusted Root Certification Authority/Certificates**, confirm that the new certificate is listed.</span></span>

## <a name="get-more-information-about-tls-and-office-365"></a><span data-ttu-id="4d2e9-199">详细了解 TLS 和 Office 365</span><span class="sxs-lookup"><span data-stu-id="4d2e9-199">Get more information about TLS and Office 365</span></span>

<span data-ttu-id="4d2e9-200">支持的密码套件的列表，请参阅[有关 Office 365 中的加密技术参考详细信息](technical-reference-details-about-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="4d2e9-200">For a list of supported cipher suites, see [Technical reference details about encryption in Office 365](technical-reference-details-about-encryption.md).</span></span>
  
[<span data-ttu-id="4d2e9-201">将连接器设置为确保与合作伙伴组织之间实现安全的邮件流</span><span class="sxs-lookup"><span data-stu-id="4d2e9-201">Set up connectors for secure mail flow with a partner organization</span></span>](https://technet.microsoft.com/library/dn751021%28v=exchg.150%29.aspx)
  
[<span data-ttu-id="4d2e9-202">电子邮件安全性已提高的连接器</span><span class="sxs-lookup"><span data-stu-id="4d2e9-202">Connectors with enhanced email security</span></span>](https://technet.microsoft.com/library/261d92e4-7371-4555-b781-2062b5bb5278.aspx)
  
[<span data-ttu-id="4d2e9-203">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="4d2e9-203">Encryption in Office 365</span></span>](encryption.md)
  

