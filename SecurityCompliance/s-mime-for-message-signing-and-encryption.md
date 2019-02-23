---
title: Exchange Online 中的邮件签名和加密的 S/MIME
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: S/MIME 允许您对电子邮件进行加密并对其进行数字签名。当您在电子邮件中使用 S/MIME 时, 将会帮助接收该邮件的人确信他们在 "收件箱" 中看到的内容与发件人启动的邮件完全一致。
ms.openlocfilehash: 41a84d5332092748f9a8cc8fe4936c39e5fd2012
ms.sourcegitcommit: 06d6e63225f912d0f3c6bb836c61eb11c1dbe97a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "30206505"
---
# <a name="smime-for-message-signing-and-encryption"></a><span data-ttu-id="7bd5c-104">用于邮件签名和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="7bd5c-104">S/MIME for message signing and encryption</span></span>

<span data-ttu-id="7bd5c-p102">S/MIME (安全/多用途 Internet 邮件扩展) 是一种广泛接受的方法, 或更精确地发送经过数字签名和加密的邮件的协议。S/MIME 允许您对电子邮件进行加密并对其进行数字签名。当您在电子邮件中使用 S/MIME 时, 将会帮助接收该邮件的人确信他们在 "收件箱" 中看到的内容与发件人启动的邮件完全一致。它还将帮助接收邮件的用户确信邮件来自特定发件人, 而不是假装为发件人的人。为此, S/MIME 提供了加密安全服务, 例如身份验证、邮件完整性和源不可否认 (使用数字签名)。它还有助于加强电子邮件的隐私和数据安全 (使用加密)。有关电子邮件上下文中 S/mime 的历史记录和体系结构的更多完整背景, 请参阅[了解 S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)。</span><span class="sxs-lookup"><span data-stu-id="7bd5c-p102">S/MIME (Secure/Multipurpose Internet Mail Extensions) is a widely accepted method, or more precisely a protocol, for sending digitally signed and encrypted messages. S/MIME allows you to encrypt emails and digitally sign them. When you use S/MIME with an email message, it helps the people who receive that message to be certain that what they see in their inbox is the exact message that started with the sender. It will also help people who receive messages to be certain that the message came from the specific sender and not from someone pretending to be the sender. To do this, S/MIME provides for cryptographic security services such as authentication, message integrity, and non-repudiation of origin (using digital signatures). It also helps enhance privacy and data security (using encryption) for electronic messaging. For a more complete background about the history and architecture of S/MIME in the context of email, see [Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948).</span></span> 
  
<span data-ttu-id="7bd5c-p103">作为管理员, 如果 exchange 2013 SP1 或 exchange Online (Office 365 的一部分) 中有邮箱, 则可以为您的组织启用基于 S/MIME 的安全性。使用此处链接的主题中的指南和 Exchange 命令行管理程序设置 S/MIME。若要在受支持的 Outlook 或 ActiveSync 版本中使用 S/MIME, 同时使用 exchange 2013 SP1 或 exchange Online, 组织中的用户必须为签名和加密目的颁发证书, 并将数据发布到本地 Active Directory域服务 (AD DS)。您的 AD DS 必须位于您控制的物理位置的计算机上, 而不是位于 internet 上某个位置的远程设施或基于云的服务中。有关 AD DS 的详细信息, 请参阅[Active Directory 域服务](https://go.microsoft.com/fwlink/?LinkID=394064)。</span><span class="sxs-lookup"><span data-stu-id="7bd5c-p103">As an administrator, you can enable S/MIME-based security for your organization if you have mailboxes in either Exchange 2013 SP1 or Exchange Online, a part of Office 365. Use the guidance in the topics linked here along with the Exchange Management Shell to set up S/MIME. To use S/MIME in supported versions of Outlook or ActiveSync, with either Exchange 2013 SP1 or Exchange Online, the users in your organization must have certificates issued for signing and encryption purposes and data published to your on-premises Active Directory Domain Service (AD DS). Your AD DS must be located on computers at a physical location that you control and not at a remote facility or cloud-based service somewhere on the internet. For more information about AD DS, see [Active Directory Domain Services](https://go.microsoft.com/fwlink/?LinkID=394064).</span></span>
  
## <a name="supported-scenarios-and-technical-considerations"></a><span data-ttu-id="7bd5c-117">支持的场景和技术考虑因素</span><span class="sxs-lookup"><span data-stu-id="7bd5c-117">Supported scenarios and technical considerations</span></span>
<span data-ttu-id="7bd5c-118"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="7bd5c-118"></span></span>

<span data-ttu-id="7bd5c-119">可以将 S/MIME 设置为用于以下任一终结点：</span><span class="sxs-lookup"><span data-stu-id="7bd5c-119">You can set up S/MIME to work with any of the following end points:</span></span> 
  
- <span data-ttu-id="7bd5c-120">Outlook 2010 或更高版本</span><span class="sxs-lookup"><span data-stu-id="7bd5c-120">Outlook 2010 or later</span></span>
    
- <span data-ttu-id="7bd5c-121">Web 上的 Outlook（以前称为 Outlook Web App）</span><span class="sxs-lookup"><span data-stu-id="7bd5c-121">Outlook on the web (formerly known as Outlook Web App)</span></span>
    
- <span data-ttu-id="7bd5c-122">Exchange ActiveSync (EAS)</span><span class="sxs-lookup"><span data-stu-id="7bd5c-122">Exchange ActiveSync (EAS)</span></span>
    
<span data-ttu-id="7bd5c-p104">根据您选择的终结点，为这些终结点设置 S/MIME 时需遵循的步骤可能略有不同。通常情况下，您需要完成以下步骤：</span><span class="sxs-lookup"><span data-stu-id="7bd5c-p104">The steps that you follow to set up S/MIME with each of these end points is slightly different depending on which you choose. Generally, you will need to accomplish the following:</span></span>
  
- <span data-ttu-id="7bd5c-p105">安装基于 Windows 的证书颁发机构, 并设置公钥基础结构以颁发 S/MIME 证书。此外, 还支持第三方证书提供商颁发的证书。有关详细信息, 请参阅[Active Directory 证书服务概述](https://technet.microsoft.com/library/hh831740.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7bd5c-p105">Install a Windows-based Certification Authority and set up a public key infrastructure to issue S/MIME certificates. Certificates issued by third-party certificate providers are also supported. For details, see [Active Directory Certificate Services Overview](https://technet.microsoft.com/library/hh831740.aspx).</span></span>
    
- <span data-ttu-id="7bd5c-128">在内部部署 AD DS 帐户的 UserSMIMECertificate 和/或 UserCertificate 属性中发布用户证书。</span><span class="sxs-lookup"><span data-stu-id="7bd5c-128">Publish the user certificate in an on-premises AD DS account in the UserSMIMECertificate and/or UserCertificate attributes.</span></span>
    
- <span data-ttu-id="7bd5c-p106">对于 Exchange Online 组织, 使用相应版本的 DirSync 将用户证书从 AD DS 同步到 Azure Active Directory。然后, 这些证书将从 Azure Active directory 同步到 Exchange Online 目录, 并将在将邮件加密给收件人时使用。</span><span class="sxs-lookup"><span data-stu-id="7bd5c-p106">For Exchange Online organizations, synchronize the user certificates from AD DS to Azure Active Directory by using an appropriate version of DirSync. These certificates will then get synchronized from Azure Active Directory to Exchange Online directory and will be used when encrypting a message to a recipient.</span></span>
    
- <span data-ttu-id="7bd5c-p107">设置虚拟证书集合以验证 S/MIME。此信息由 Outlook 在验证电子邮件的签名并确保它是由受信任的证书签名时在 web 上使用 (以前称为 Outlook 网页上的 outlook)。</span><span class="sxs-lookup"><span data-stu-id="7bd5c-p107">Set up a virtual certificate collection in order to validate S/MIME. This information is used by Outlook on the web (formerly known as Outlook on the web) when validating the signature of an email and ensuring that it was signed by a trusted certificate.</span></span>
    
- <span data-ttu-id="7bd5c-133">将 Outlook 或 EAS 终结点设置为使用 S/MIME。</span><span class="sxs-lookup"><span data-stu-id="7bd5c-133">Set up the Outlook or EAS end point to use S/MIME.</span></span> 
    
## <a name="setup-smime-with-outlook-on-the-web"></a><span data-ttu-id="7bd5c-134">设置 web 上的 Outlook 的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="7bd5c-134">Setup S/MIME with Outlook on the web</span></span>
<span data-ttu-id="7bd5c-135"><a name="sectionSection1"> </a></span><span class="sxs-lookup"><span data-stu-id="7bd5c-135"></span></span>

<span data-ttu-id="7bd5c-136">使用 web 上的 Outlook 为 Exchange Online 设置 S/MIME 涉及以下关键步骤:</span><span class="sxs-lookup"><span data-stu-id="7bd5c-136">Setting up S/MIME for Exchange Online with Outlook on the web involves the following key steps:</span></span>
  
1. [<span data-ttu-id="7bd5c-137">Configure S/MIME settings for Outlook on the web</span><span class="sxs-lookup"><span data-stu-id="7bd5c-137">Configure S/MIME settings for Outlook on the web</span></span>](configure-s-mime-settings-for-outlook-web-app.md)
    
2. [<span data-ttu-id="7bd5c-138">设置虚拟证书集合以验证 S/MIME</span><span class="sxs-lookup"><span data-stu-id="7bd5c-138">Set up virtual certificate collection to validate S/MIME</span></span>](set-up-virtual-certificate-collection-to-validate-s-mime.md)
    
3. <span data-ttu-id="7bd5c-139">[将用户证书同步到 Office 365 for S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)此步骤仅适用于 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="7bd5c-139">[Sync user certificates to Office 365 for S/MIME](sync-user-certificates-to-office-365-for-s-mime.md) This step applies to Exchange Online only.</span></span> 
    
## <a name="related-message-encryption-technologies"></a><span data-ttu-id="7bd5c-140">相关邮件加密技术</span><span class="sxs-lookup"><span data-stu-id="7bd5c-140">Related message encryption technologies</span></span>
<span data-ttu-id="7bd5c-141"><a name="sectionSection2"> </a></span><span class="sxs-lookup"><span data-stu-id="7bd5c-141"></span></span>

<span data-ttu-id="7bd5c-p108">随着邮件安全性变得更加重要, 管理员需要了解安全邮件的原则和概念。这种理解尤其重要, 因为存在越来越多的与保护相关的技术 (如 S/MIME) 已经推出。若要详细了解 s/MIME 以及它在电子邮件上下文中的工作方式, 请参阅[了解 s/mime](https://go.microsoft.com/fwlink/?LinkID=393948)。各种加密技术协同工作, 为静态和传输中的邮件提供保护。S/MIME 可以同时与以下技术一起使用, 但不依赖于它们:</span><span class="sxs-lookup"><span data-stu-id="7bd5c-p108">As message security becomes more important, administrators need to understand the principles and concepts of secure messaging. This understanding is especially important because of the growing variety of protection-related technologies, such as S/MIME, that have become available. To understand more about S/MIME and how it works in context of email, see [Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948). A variety of encryption technologies work together to provide protection for messages at rest and in-transit. S/MIME can work simultaneously with the following technologies but is not dependent on them:</span></span>
  
> <span data-ttu-id="7bd5c-147">**传输层安全 (TLS)** 对电子邮件服务器之间的隧道或路由进行加密，以帮助阻止窥探和窃听。</span><span class="sxs-lookup"><span data-stu-id="7bd5c-147">**Transport Layer Security (TLS)** encrypts the tunnel or the route between email servers in order to help prevent snooping and eavesdropping.</span></span> 
    
> <span data-ttu-id="7bd5c-148">**安全套接字层 (SSL)** 对电子邮件客户端和 Office 365 服务器之间的连接进行加密。</span><span class="sxs-lookup"><span data-stu-id="7bd5c-148">**Secure Sockets Layer (SSL)** encrypts the connection between email clients and Office 365 servers.</span></span> 
    
> <span data-ttu-id="7bd5c-149">**BitLocker**将对数据中心中的硬盘驱动器上的数据进行加密, 以便在有人未经授权访问的情况下对其进行读取。</span><span class="sxs-lookup"><span data-stu-id="7bd5c-149">**BitLocker** encrypts the data on a hard drive in a datacenter so that if someone gets unauthorized access, they can't read it.</span></span> 
    
### <a name="smime-compared-with-office-365-message-encryption"></a><span data-ttu-id="7bd5c-150">S/MIME 与 Office 365 邮件加密对比</span><span class="sxs-lookup"><span data-stu-id="7bd5c-150">S/MIME compared with Office 365 Message Encryption</span></span>

<span data-ttu-id="7bd5c-p109">S/MIME 需要一个在企业到企业和企业到消费者的情形中经常使用的证书和发布基础结构。用户控制 S/MIME 中的加密密钥, 并可以选择是否对其发送的每封邮件使用它们。Outlook 等电子邮件程序搜索受信任的根证书颁发机构位置, 以对签名进行数字签名和验证。Office 365 邮件加密是一种基于策略的加密服务, 可由管理员而不是单个用户配置, 以加密发送给组织内部或外部的任何人的邮件。它是基于 Azure 权限管理 (RMS) 构建的在线服务, 不依赖公钥基础结构。Office 365 邮件加密还提供了其他功能, 例如, 使用组织品牌自定义邮件的功能。有关 office 365 邮件加密的详细信息, 请参阅[office 365 邮件加密](https://go.microsoft.com/fwlink/?LinkID=392525)。</span><span class="sxs-lookup"><span data-stu-id="7bd5c-p109">S/MIME requires a certificate and publishing infrastructure that is often used in business-to-business and business-to-consumer situations. The user controls the cryptographic keys in S/MIME and can choose whether to use them for each message they send. Email programs such as Outlook search a trusted root certificate authority location to perform digital signing and verification of the signature. Office 365 Message Encryption is a policy-based encryption service that can be configured by an administrator, and not an individual user, to encrypt mail sent to anyone inside or outside of the organization. It's an online service that's built on Azure Rights Management (RMS) and does not rely on a public key infrastructure. Office 365 Message Encryption also provides additional capabilities, such as the capability to customize the mail with organization's brand. For more information about Office 365 Message Encryption, see [Office 365 Message Encryption](https://go.microsoft.com/fwlink/?LinkID=392525).</span></span>
  
## <a name="more-information"></a><span data-ttu-id="7bd5c-158">详细信息</span><span class="sxs-lookup"><span data-stu-id="7bd5c-158">More information</span></span>
<span data-ttu-id="7bd5c-159"><a name="sectionSection3"> </a></span><span class="sxs-lookup"><span data-stu-id="7bd5c-159"></span></span>

[<span data-ttu-id="7bd5c-160">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="7bd5c-160">Outlook on the web</span></span>](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)
  
[<span data-ttu-id="7bd5c-161">安全邮件 (2000)</span><span class="sxs-lookup"><span data-stu-id="7bd5c-161">Secure Mail (2000)</span></span>](https://technet.microsoft.com/en-us/library/cc962043.aspx)
  

