---
title: Exchange Online 中的邮件签名和加密的 S/MIME
ms.author: chrisda
author: chrisda
manager: serdars
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 管理员可以了解如何在 Exchange Online 中使用 S/MIME。
ms.openlocfilehash: 570e306ea1c781344bed120f1dd467d31a4a4fe6
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34156994"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a><span data-ttu-id="cfba6-103">Exchange Online 中的邮件签名和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="cfba6-103">S/MIME for message signing and encryption in Exchange Online</span></span>

<span data-ttu-id="cfba6-104">S/MIME (安全/多用途 Internet 邮件扩展) 是发送经过数字签名和加密的邮件的广泛接受的方法 (或更准确的一种协议)。</span><span class="sxs-lookup"><span data-stu-id="cfba6-104">S/MIME (Secure/Multipurpose Internet Mail Extensions) is a widely accepted method (or more precisely, a protocol) for sending digitally signed and encrypted messages.</span></span> <span data-ttu-id="cfba6-105">S/MIME 允许你加密电子邮件，并对它们进行数字签名。</span><span class="sxs-lookup"><span data-stu-id="cfba6-105">S/MIME allows you to encrypt emails and digitally sign them.</span></span> <span data-ttu-id="cfba6-106">当您在电子邮件中使用 S/MIME 时, 将会帮助接收该邮件的人确信他们在 "收件箱" 中看到的内容与发件人启动的邮件完全一致。</span><span class="sxs-lookup"><span data-stu-id="cfba6-106">When you use S/MIME with an email message, it helps the people who receive that message to be certain that what they see in their inbox is the exact message that started with the sender.</span></span> <span data-ttu-id="cfba6-107">它还将帮助接收邮件的用户确信邮件来自特定发件人, 而不是假装为发件人的人。</span><span class="sxs-lookup"><span data-stu-id="cfba6-107">It will also help people who receive messages to be certain that the message came from the specific sender and not from someone pretending to be the sender.</span></span> <span data-ttu-id="cfba6-108">为此，S/MIME 提供了加密安全服务，例如身份验证、邮件完整性和防发送方抵赖（使用数字签名）。</span><span class="sxs-lookup"><span data-stu-id="cfba6-108">To do this, S/MIME provides for cryptographic security services such as authentication, message integrity, and non-repudiation of origin (using digital signatures).</span></span> <span data-ttu-id="cfba6-109">它还有助于加强电子邮件的隐私和数据安全 (使用加密)。</span><span class="sxs-lookup"><span data-stu-id="cfba6-109">It also helps enhance privacy and data security (using encryption) for electronic messaging.</span></span> <span data-ttu-id="cfba6-110">有关电子邮件上下文中 S/MIME 的历史记录和体系结构的更多完整背景，请参阅[了解 S/MIMEE](https://go.microsoft.com/fwlink/?LinkID=393948)。</span><span class="sxs-lookup"><span data-stu-id="cfba6-110">For a more complete background about the history and architecture of S/MIME in the context of email, see [Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948).</span></span>

<span data-ttu-id="cfba6-111">作为 Exchange Online 管理员, 您可以为组织中的邮箱启用基于 S/MIME 的安全性。</span><span class="sxs-lookup"><span data-stu-id="cfba6-111">As an Exchange Online admin, you can enable S/MIME-based security for the mailboxes in your organization.</span></span> <span data-ttu-id="cfba6-112">使用此处链接的主题和 Exchange Online PowerShell 中的指导设置 S/MIME。</span><span class="sxs-lookup"><span data-stu-id="cfba6-112">Use the guidance in the topics linked here along with Exchange Online PowerShell to set up S/MIME.</span></span> <span data-ttu-id="cfba6-113">若要在受支持的电子邮件客户端中使用 S/MIME, 组织中的用户必须具有为签名和加密目的颁发的证书以及发布到内部部署 Active Directory 域服务 (AD DS) 的数据。</span><span class="sxs-lookup"><span data-stu-id="cfba6-113">To use S/MIME in supported email clients, the users in your organization must have certificates issued for signing and encryption purposes and data published to your on-premises Active Directory Domain Service (AD DS).</span></span> <span data-ttu-id="cfba6-114">您的 AD DS 必须位于您控制的物理位置的计算机上, 而不是位于 internet 上某个位置的远程设施或基于云的服务中。</span><span class="sxs-lookup"><span data-stu-id="cfba6-114">Your AD DS must be located on computers at a physical location that you control and not at a remote facility or cloud-based service somewhere on the internet.</span></span> <span data-ttu-id="cfba6-115">有关 AD DS 的详细信息，请参阅 [Active Directory 域服务](https://go.microsoft.com/fwlink/?LinkID=394064)。</span><span class="sxs-lookup"><span data-stu-id="cfba6-115">For more information about AD DS, see [Active Directory Domain Services](https://go.microsoft.com/fwlink/?LinkID=394064).</span></span>

## <a name="supported-scenarios-and-technical-considerations"></a><span data-ttu-id="cfba6-116">支持的方案和技术注意事项</span><span class="sxs-lookup"><span data-stu-id="cfba6-116">Supported scenarios and technical considerations</span></span>

<span data-ttu-id="cfba6-117">可以将 S/MIME 设置为用于以下任一终结点：</span><span class="sxs-lookup"><span data-stu-id="cfba6-117">You can set up S/MIME to work with any of the following end points:</span></span>

- <span data-ttu-id="cfba6-118">Outlook 2010 或更高版本</span><span class="sxs-lookup"><span data-stu-id="cfba6-118">Outlook 2010 or later</span></span>

- <span data-ttu-id="cfba6-119">Web 上的 Outlook（以前称为 Outlook Web App）</span><span class="sxs-lookup"><span data-stu-id="cfba6-119">Outlook on the web (formerly known as Outlook Web App)</span></span>

- <span data-ttu-id="cfba6-120">Exchange ActiveSync (EAS)</span><span class="sxs-lookup"><span data-stu-id="cfba6-120">Exchange ActiveSync (EAS)</span></span>

<span data-ttu-id="cfba6-121">为每个终结点设置 S/MIME 所遵循的步骤略有不同。</span><span class="sxs-lookup"><span data-stu-id="cfba6-121">The steps that you follow to set up S/MIME with each of these end points is slightly different.</span></span> <span data-ttu-id="cfba6-122">通常, 您需要执行以下步骤:</span><span class="sxs-lookup"><span data-stu-id="cfba6-122">Generally, you will need to do the following steps:</span></span>

- <span data-ttu-id="cfba6-123">安装基于 WIndows 的证书颁发机构，并设置公钥基础结构以颁发 S/MIME 证书。</span><span class="sxs-lookup"><span data-stu-id="cfba6-123">Install a Windows-based Certification Authority and set up a public key infrastructure to issue S/MIME certificates.</span></span> <span data-ttu-id="cfba6-124">此外, 还支持第三方证书提供商颁发的证书。</span><span class="sxs-lookup"><span data-stu-id="cfba6-124">Certificates issued by third-party certificate providers are also supported.</span></span> <span data-ttu-id="cfba6-125">有关详细信息，请参阅 [Active Directory 证书服务概述](https://technet.microsoft.com/library/hh831740.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cfba6-125">For details, see [Active Directory Certificate Services Overview](https://technet.microsoft.com/library/hh831740.aspx).</span></span>

- <span data-ttu-id="cfba6-126">在**UserSMIMECertificate**和/或**UserCertificate**属性中的本地 AD DS 帐户中发布用户证书。</span><span class="sxs-lookup"><span data-stu-id="cfba6-126">Publish the user certificate in an on-premises AD DS account in the **UserSMIMECertificate** and/or **UserCertificate** attributes.</span></span>

- <span data-ttu-id="cfba6-127">对于 Exchange Online 组织, 使用相应版本的 DirSync 将用户证书从 AD DS 同步到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="cfba6-127">For Exchange Online organizations, synchronize the user certificates from AD DS to Azure Active Directory by using an appropriate version of DirSync.</span></span> <span data-ttu-id="cfba6-128">然后, 这些证书将从 Azure Active Directory 同步到 Exchange Online 目录, 并将在将邮件加密给收件人时使用。</span><span class="sxs-lookup"><span data-stu-id="cfba6-128">These certificates will then get synchronized from Azure Active Directory to Exchange Online directory and will be used when encrypting a message to a recipient.</span></span>

- <span data-ttu-id="cfba6-p106">设置虚拟证书集合以验证 S/MIME。此信息供 Web 上的 Outlook 用于验证电子邮件的签名并确保它是由可信证书签名的。</span><span class="sxs-lookup"><span data-stu-id="cfba6-p106">Set up a virtual certificate collection in order to validate S/MIME. This information is used by Outlook on the web when validating the signature of an email and ensuring that it was signed by a trusted certificate.</span></span>

- <span data-ttu-id="cfba6-131">将 Outlook 或 EAS 终结点设置为使用 S/MIME。</span><span class="sxs-lookup"><span data-stu-id="cfba6-131">Set up the Outlook or EAS end point to use S/MIME.</span></span>

## <a name="setup-smime-with-outlook-on-the-web"></a><span data-ttu-id="cfba6-132">设置 web 上的 Outlook 的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="cfba6-132">Setup S/MIME with Outlook on the web</span></span>

<span data-ttu-id="cfba6-133">使用 web 上的 Outlook 为 Exchange Online 设置 S/MIME 涉及以下关键步骤:</span><span class="sxs-lookup"><span data-stu-id="cfba6-133">Setting up S/MIME for Exchange Online with Outlook on the web involves the following key steps:</span></span>

1. [<span data-ttu-id="cfba6-134">配置 Outlook 网页版的 S/MIME 设置</span><span class="sxs-lookup"><span data-stu-id="cfba6-134">Configure S/MIME settings for Outlook on the web</span></span>](configure-s-mime-settings-for-outlook-web-app.md)

2. [<span data-ttu-id="cfba6-135">设置虚拟证书集合以验证 S/MIME</span><span class="sxs-lookup"><span data-stu-id="cfba6-135">Set up virtual certificate collection to validate S/MIME</span></span>](set-up-virtual-certificate-collection-to-validate-s-mime.md)

3. [<span data-ttu-id="cfba6-136">出于 S/MIME 目的将用户证书同步到 Office 365</span><span class="sxs-lookup"><span data-stu-id="cfba6-136">Sync user certificates to Office 365 for S/MIME</span></span>](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a><span data-ttu-id="cfba6-137">相关邮件加密技术</span><span class="sxs-lookup"><span data-stu-id="cfba6-137">Related message encryption technologies</span></span>

<span data-ttu-id="cfba6-138">随着邮件安全性变得更加重要, 管理员需要了解安全邮件的原则和概念。</span><span class="sxs-lookup"><span data-stu-id="cfba6-138">As message security becomes more important, admins need to understand the principles and concepts of secure messaging.</span></span> <span data-ttu-id="cfba6-139">此理解尤其重要, 因为存在各种可用的保护相关技术 (包括 S/MIME)。</span><span class="sxs-lookup"><span data-stu-id="cfba6-139">This understanding is especially important because of the growing variety of protection-related technologies (including S/MIME) that are available.</span></span> <span data-ttu-id="cfba6-140">若要详细了解 S/MIME 以及它在电子邮件上下文中的工作方式, 请参阅[了解 s/mime](https://go.microsoft.com/fwlink/?LinkID=393948)。</span><span class="sxs-lookup"><span data-stu-id="cfba6-140">To understand more about S/MIME and how it works in context of email, see [Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948).</span></span> <span data-ttu-id="cfba6-141">各种加密技术协同工作, 为静态和传输中的邮件提供保护。</span><span class="sxs-lookup"><span data-stu-id="cfba6-141">A variety of encryption technologies work together to provide protection for messages at rest and in-transit.</span></span> <span data-ttu-id="cfba6-142">S/MIME 可以同时与以下技术一起使用, 但不依赖于它们:</span><span class="sxs-lookup"><span data-stu-id="cfba6-142">S/MIME can work simultaneously with the following technologies but is not dependent on them:</span></span>

- <span data-ttu-id="cfba6-143">**传输层安全性 (TLS)** 对电子邮件服务器之间的隧道或路由进行加密, 以帮助阻止窥探和窃听。</span><span class="sxs-lookup"><span data-stu-id="cfba6-143">**Transport Layer Security (TLS)** encrypts the tunnel or the route between email servers in order to help prevent snooping and eavesdropping.</span></span>

- <span data-ttu-id="cfba6-144">**安全套接字层 (SSL)** 对电子邮件客户端和 Office 365 服务器之间的连接进行加密。</span><span class="sxs-lookup"><span data-stu-id="cfba6-144">**Secure Sockets Layer (SSL)** encrypts the connection between email clients and Office 365 servers.</span></span>

- <span data-ttu-id="cfba6-145">**BitLocker**将对数据中心中的硬盘驱动器上的数据进行加密, 以便在有人未经授权访问的情况下对其进行读取。</span><span class="sxs-lookup"><span data-stu-id="cfba6-145">**BitLocker** encrypts the data on a hard drive in a datacenter so that if someone gets unauthorized access, they can't read it.</span></span>

### <a name="smime-compared-with-office-365-message-encryption"></a><span data-ttu-id="cfba6-146">S/MIME 与 Office 365 邮件加密进行比较</span><span class="sxs-lookup"><span data-stu-id="cfba6-146">S/MIME compared with Office 365 Message Encryption</span></span>

<span data-ttu-id="cfba6-147">S/MIME 需要证书和发布基础结构，通常用于企业到企业和企业到消费者的情况。</span><span class="sxs-lookup"><span data-stu-id="cfba6-147">S/MIME requires a certificate and publishing infrastructure that is often used in business-to-business and business-to-consumer situations.</span></span> <span data-ttu-id="cfba6-148">用户控制 S/MIME 中的加密密钥，并且可以选择是否为他们发送的每封邮件使用密钥。</span><span class="sxs-lookup"><span data-stu-id="cfba6-148">The user controls the cryptographic keys in S/MIME and can choose whether to use them for each message they send.</span></span> <span data-ttu-id="cfba6-149">Outlook 等电子邮件程序搜索可信任根证书颁发机构位置，以执行数字签名和签名验证。</span><span class="sxs-lookup"><span data-stu-id="cfba6-149">Email programs such as Outlook search a trusted root certificate authority location to perform digital signing and verification of the signature.</span></span> <span data-ttu-id="cfba6-150">Office 365 邮件加密是一种基于策略的加密服务, 可由管理员而不是单个用户配置, 以加密发送给组织内部或外部的任何人的邮件。</span><span class="sxs-lookup"><span data-stu-id="cfba6-150">Office 365 Message Encryption is a policy-based encryption service that can be configured by an administrator, and not an individual user, to encrypt mail sent to anyone inside or outside of the organization.</span></span> <span data-ttu-id="cfba6-151">它是基于 Azure 权限管理 (RMS) 构建的在线服务, 不依赖公钥基础结构。</span><span class="sxs-lookup"><span data-stu-id="cfba6-151">It's an online service that's built on Azure Rights Management (RMS) and does not rely on a public key infrastructure.</span></span> <span data-ttu-id="cfba6-152">Office 365 邮件加密还提供了其他功能, 例如, 使用组织品牌自定义邮件的功能。</span><span class="sxs-lookup"><span data-stu-id="cfba6-152">Office 365 Message Encryption also provides additional capabilities, such as the capability to customize the mail with organization's brand.</span></span> <span data-ttu-id="cfba6-153">有关 Office 365 邮件加密的详细信息, 请参阅[office 365 邮件加密](https://go.microsoft.com/fwlink/?LinkID=392525)。</span><span class="sxs-lookup"><span data-stu-id="cfba6-153">For more information about Office 365 Message Encryption, see [Office 365 Message Encryption](https://go.microsoft.com/fwlink/?LinkID=392525).</span></span>

## <a name="more-information"></a><span data-ttu-id="cfba6-154">更多信息</span><span class="sxs-lookup"><span data-stu-id="cfba6-154">More information</span></span>

[<span data-ttu-id="cfba6-155">Outlook 网页版</span><span class="sxs-lookup"><span data-stu-id="cfba6-155">Outlook on the web</span></span>](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)

[<span data-ttu-id="cfba6-156">安全邮件 (2000)</span><span class="sxs-lookup"><span data-stu-id="cfba6-156">Secure Mail (2000)</span></span>](https://technet.microsoft.com/en-us/library/cc962043.aspx)
