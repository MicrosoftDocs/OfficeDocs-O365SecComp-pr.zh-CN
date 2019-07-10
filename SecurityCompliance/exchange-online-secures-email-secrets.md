---
title: Exchange Online 如何进行电子邮件保密
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 07/01/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: 除了提供 Office 365 的安全性、隐私和合规性信息的 Office 365 信任中心之外, 您可能还需要了解 Office 365 如何帮助保护您在其数据中心中提供的密码。 我们使用一种称为 "分布式密钥管理器" (DKM) 的技术。
ms.openlocfilehash: 8350785968c68b22c58be17ec68d94ff908c95d9
ms.sourcegitcommit: 32ecff689ae32c59a39b7633ca0f36a304e7516e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2019
ms.locfileid: "35599428"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a><span data-ttu-id="81d74-104">Exchange Online 如何进行电子邮件保密</span><span class="sxs-lookup"><span data-stu-id="81d74-104">How Exchange Online secures your email secrets</span></span>

<span data-ttu-id="81d74-105">本文介绍了 Microsoft 如何在其数据中心中保护你的电子邮件机密。</span><span class="sxs-lookup"><span data-stu-id="81d74-105">This article describes how Microsoft secures your email secrets in its datacenters.</span></span>
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a><span data-ttu-id="81d74-106">我们如何保护你提供的机密信息的安全？</span><span class="sxs-lookup"><span data-stu-id="81d74-106">How do we secure secret information provided by you?</span></span>

<span data-ttu-id="81d74-107">除了提供[office 365 的安全性、隐私和合规性信息](https://go.microsoft.com/fwlink/?linkid=874644)的 Office 365 信任中心之外, 您可能还需要了解 office 365 如何帮助保护您在其数据中心中提供的密码。</span><span class="sxs-lookup"><span data-stu-id="81d74-107">In addition to the Office 365 Trust Center which provides [Security, Privacy and Compliance Information for Office 365](https://go.microsoft.com/fwlink/?linkid=874644), you might want to know how Office 365 helps protects secrets you provide in its datacenters.</span></span> <span data-ttu-id="81d74-108">我们使用一种称为 "分布式密钥管理器" (DKM) 的技术。</span><span class="sxs-lookup"><span data-stu-id="81d74-108">We use a technology called Distributed Key Manager (DKM).</span></span>
  
<span data-ttu-id="81d74-109">[分布式密钥管理器](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)(DKM) 是一种客户端功能, 使用一组密钥对信息进行加密和解密。</span><span class="sxs-lookup"><span data-stu-id="81d74-109">[Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) (DKM) is a client-side functionality that uses a set of secret keys to encrypt and decrypt information.</span></span> <span data-ttu-id="81d74-110">只有 Active Directory 域服务中特定安全组的成员才能访问这些密钥, 以便对由 DKM 加密的数据进行解密。</span><span class="sxs-lookup"><span data-stu-id="81d74-110">Only members of a specific security group in Active Directory Domain Services can access those keys in order to decrypt the data that is encrypted by DKM.</span></span> <span data-ttu-id="81d74-111">在 Exchange Online 中, 仅在运行 Exchange 进程的特定服务帐户是该安全组的一部分。</span><span class="sxs-lookup"><span data-stu-id="81d74-111">In Exchange Online, only certain service accounts under which the Exchange processes run are part of that security group.</span></span> <span data-ttu-id="81d74-112">作为数据中心中的标准操作过程的一部分, 将不会向任何人提供属于此安全组的凭据, 因此没有人能够访问可以解密这些机密的密钥。</span><span class="sxs-lookup"><span data-stu-id="81d74-112">As part of standard operating procedure in the datacenter, no human is given credentials that are part of this security group and therefore no human has access to the keys that can decrypt these secrets.</span></span>
  
<span data-ttu-id="81d74-113">对于调试、故障排除或审核目的, 数据中心管理员必须请求提升的访问权限, 才能获取属于安全组一部分的临时凭据。</span><span class="sxs-lookup"><span data-stu-id="81d74-113">For debugging, troubleshooting, or auditing purposes, a datacenter administrator must request elevated access to gain temporary credentials that are part of the security group.</span></span> <span data-ttu-id="81d74-114">此过程需要多个合法的法律审批级别。</span><span class="sxs-lookup"><span data-stu-id="81d74-114">This process requires multiple levels of legal approval.</span></span> <span data-ttu-id="81d74-115">如果授予访问权限, 则会记录并审核所有活动。</span><span class="sxs-lookup"><span data-stu-id="81d74-115">If access is granted, all activity is logged and audited.</span></span> <span data-ttu-id="81d74-116">此外, 仅授予对设置的时间间隔的访问权限, 在此间隔之后它将自动过期。</span><span class="sxs-lookup"><span data-stu-id="81d74-116">In addition access is only granted for a set interval of time after which it automatically expires.</span></span>
  
<span data-ttu-id="81d74-117">对于额外保护, DKM 技术包括自动化密钥滚动更新和存档。</span><span class="sxs-lookup"><span data-stu-id="81d74-117">For extra protection, DKM technology includes automated key rollover and archiving.</span></span> <span data-ttu-id="81d74-118">这还可确保您可以继续访问较旧的内容, 而无需无限期地依赖相同的密钥。</span><span class="sxs-lookup"><span data-stu-id="81d74-118">This also ensures that you can continue to access your older content without having to rely on the same key indefinitely.</span></span>
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a><span data-ttu-id="81d74-119">Exchange Online 在哪里使用 DKM？</span><span class="sxs-lookup"><span data-stu-id="81d74-119">Where does Exchange Online make use of DKM?</span></span>

<span data-ttu-id="81d74-120">Microsoft 使用[分布式密钥管理器](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)在 Exchange Online 数据中心中对机密进行加密。</span><span class="sxs-lookup"><span data-stu-id="81d74-120">Microsoft uses [Distributed Key Manager](office-365-bitlocker-and-distributed-key-manager-for-encryption.md) to encrypt your secrets in Exchange Online datacenters.</span></span> <span data-ttu-id="81d74-121">例如：</span><span class="sxs-lookup"><span data-stu-id="81d74-121">For example:</span></span>
  
- <span data-ttu-id="81d74-122">已连接帐户的电子邮件帐户凭据。</span><span class="sxs-lookup"><span data-stu-id="81d74-122">Email account credentials for connected accounts.</span></span> <span data-ttu-id="81d74-123">已连接帐户是第三方帐户, 如 Hotmail、Gmail 和 Yahoo!</span><span class="sxs-lookup"><span data-stu-id="81d74-123">Connected accounts are third-party accounts such as Hotmail, Gmail, and Yahoo!</span></span> <span data-ttu-id="81d74-124">邮件帐户。</span><span class="sxs-lookup"><span data-stu-id="81d74-124">mail accounts.</span></span>
    
- <span data-ttu-id="81d74-125">Customer 键。</span><span class="sxs-lookup"><span data-stu-id="81d74-125">Customer key.</span></span> <span data-ttu-id="81d74-126">如果使用的是[Office 365 中的客户密钥](controlling-your-data-using-customer-key.md), 你将使用[Azure 密钥保管库](https://docs.microsoft.com/azure/key-vault/key-vault-whatis)来保护你的密码。</span><span class="sxs-lookup"><span data-stu-id="81d74-126">If you are using [Customer Key in Office 365](controlling-your-data-using-customer-key.md), you'll use [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) to safeguard your secrets.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="81d74-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="81d74-127">Related topics</span></span>

[<span data-ttu-id="81d74-128">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="81d74-128">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="81d74-129">有关 Office 365 加密的技术参考详情</span><span class="sxs-lookup"><span data-stu-id="81d74-129">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="81d74-130">Office 365 安全&amp;合规中心中的服务保证</span><span class="sxs-lookup"><span data-stu-id="81d74-130">Service assurance in the Office 365 Security &amp; Compliance Center</span></span>](https://go.microsoft.com/fwlink/?linkid=874645)
  

