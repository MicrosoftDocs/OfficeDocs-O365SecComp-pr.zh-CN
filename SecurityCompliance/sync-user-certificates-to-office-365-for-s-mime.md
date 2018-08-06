---
title: 出于 S/MIME 目的将用户证书同步到 Office 365
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: 必须先设置适当的证书，然后才能够发送受 S/MIME 保护的邮件。发件人的电子邮件程序使用收件人的公用证书对邮件进行加密，以通过 Exchange Online 发送加密邮件。此公用 X.509 证书必须向 Office 365 发布。
ms.openlocfilehash: aa94dfa6702a25b3fc6b8b883daceddf31d2f66a
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22026189"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="9f0a3-105">出于 S/MIME 目的将用户证书同步到 Office 365</span><span class="sxs-lookup"><span data-stu-id="9f0a3-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="9f0a3-p102">必须先设置适当的证书，然后才能够发送受 S/MIME 保护的邮件。发件人的电子邮件程序使用收件人的公用证书对邮件进行加密，以通过 Exchange Online 发送加密邮件。此公用 X.509 证书必须向 Office 365 发布。</span><span class="sxs-lookup"><span data-stu-id="9f0a3-p102">Before anyone can send S/MIME-protected messages, the appropriate certificates must be set up. In order to send encrypted messages through Exchange Online, the sender's email program uses the public certificate of the recipient to encrypt the message. This public X.509 certificate has to be published to Office 365.</span></span>
  
## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="9f0a3-109">对支持 S/MIME 的证书进行同步</span><span class="sxs-lookup"><span data-stu-id="9f0a3-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="9f0a3-p103">首先，通过颁发证书并在本地 Active Directory 域服务中发布证书来设置 S/MIME。有关在 Exchange 2013 中管理证书的详细信息，请参阅[Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9f0a3-p103">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service. For more information about managing certificates in Exchange 2013, see [Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span></span>
  
<span data-ttu-id="9f0a3-p104">发布证书之后，使用 Azure Active Directory 同步工具将本地 Exchange 环境中的用户数据同步至 Office 365。有关此过程的详细信息，请参阅[目录同步：目录同步工具版本历史](https://go.microsoft.com/fwlink/p/?LinkId=392587)。</span><span class="sxs-lookup"><span data-stu-id="9f0a3-p104">After your certificates are published, use the Azure Active Directory Sync tool to synchronize user data from your on-premises Exchange environment to Office 365. For more information on this process, see [DirSync: Directory Sync Tool Version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span></span>
  
<span data-ttu-id="9f0a3-114">在（出于 S/MIME 目的）同步其他目录数据的同时，该工具还会同步每个用户对象的  `userCertificate` 和  `userSMIMECertificate` 属性，以便这些数据可用于签名和加密邮件。</span><span class="sxs-lookup"><span data-stu-id="9f0a3-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  `userCertificate` and  `userSMIMECertificate` attributes for each user object so the data can be used to sign and encrypt messages.</span></span> 
  
## <a name="more-information"></a><span data-ttu-id="9f0a3-115">详细信息</span><span class="sxs-lookup"><span data-stu-id="9f0a3-115">More Information</span></span>

[<span data-ttu-id="9f0a3-116">邮件签名和加密的 S/MIME</span><span class="sxs-lookup"><span data-stu-id="9f0a3-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
  
[<span data-ttu-id="9f0a3-117">Azure Active Directory 同步工具</span><span class="sxs-lookup"><span data-stu-id="9f0a3-117">Azure Active Directory Sync tool</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=392587)
  

