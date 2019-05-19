---
title: 出于 S/MIME 目的将用户证书同步到 Office 365
ms.author: chrisda
author: chrisda
manager: Serdars
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
description: 必须先设置适当的证书，然后才能够发送受 S/MIME 保护的邮件。发件人的电子邮件程序使用收件人的公用证书对邮件进行加密，以通过 Exchange Online 发送加密邮件。此公用 X.509 证书必须向 Office 365 发布。
ms.openlocfilehash: 4453912ed6d52fb1610c93ca56ae24f3f1e47c27
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34158244"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="8ed77-105">出于 S/MIME 目的将用户证书同步到 Office 365</span><span class="sxs-lookup"><span data-stu-id="8ed77-105">Sync user certificates to Office 365 for S/MIME</span></span>

<span data-ttu-id="8ed77-106">在任何人可以在 Exchange Online 中发送受 S/MIME 保护的邮件之前, 必须设置相应的证书。</span><span class="sxs-lookup"><span data-stu-id="8ed77-106">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="8ed77-107">若要通过 Exchange Online 发送加密邮件, 发件人的电子邮件应用程序将使用收件人的公共证书来加密邮件。</span><span class="sxs-lookup"><span data-stu-id="8ed77-107">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="8ed77-108">此公用 X.509 证书必须向 Office 365 发布。</span><span class="sxs-lookup"><span data-stu-id="8ed77-108">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="8ed77-109">对支持 S/MIME 的证书进行同步</span><span class="sxs-lookup"><span data-stu-id="8ed77-109">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="8ed77-110">首先，通过颁发证书并在本地 Active Directory 域服务中发布证书来设置 S/MIME。</span><span class="sxs-lookup"><span data-stu-id="8ed77-110">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="8ed77-111">有关在 Exchange Server 中管理证书的详细信息, 请参阅[数字证书和 SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8ed77-111">For more information about managing certificates in Exchange Server, see [Digital Certificates and SSL](http://technet.microsoft.com/library/a9e2e08c-d46a-4135-a387-eb653212b676.aspx).</span></span>

<span data-ttu-id="8ed77-p104">发布证书之后，使用 Azure Active Directory 同步工具将本地 Exchange 环境中的用户数据同步至 Office 365。有关此过程的详细信息，请参阅[目录同步：目录同步工具版本历史](https://go.microsoft.com/fwlink/p/?LinkId=392587)。</span><span class="sxs-lookup"><span data-stu-id="8ed77-p104">After your certificates are published, use the Azure Active Directory Sync tool to synchronize user data from your on-premises Exchange environment to Office 365. For more information on this process, see [DirSync: Directory Sync Tool Version Release History](https://go.microsoft.com/fwlink/p/?LinkId=392587).</span></span>

<span data-ttu-id="8ed77-114">除了同步其他目录数据之外, 出于 S/MIME 目的, 该工具还会同步每个用户对象的**userCertificate**和**userSMIMECertificate**属性, 以便数据可用于对邮件进行签名和加密。</span><span class="sxs-lookup"><span data-stu-id="8ed77-114">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="8ed77-115">详细信息</span><span class="sxs-lookup"><span data-stu-id="8ed77-115">More Information</span></span>

[<span data-ttu-id="8ed77-116">将 S/MIME 用于邮件签名和加密</span><span class="sxs-lookup"><span data-stu-id="8ed77-116">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="8ed77-117">Azure Active Directory 同步工具</span><span class="sxs-lookup"><span data-stu-id="8ed77-117">Azure Active Directory Sync tool</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=392587)
