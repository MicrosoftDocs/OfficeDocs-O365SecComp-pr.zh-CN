---
title: Office 365 加密风险和保护
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: '摘要: 了解 Microsoft Office 365 中的数据恢复能力。'
ms.openlocfilehash: 8cfdcc62a28ba5feaf9a76e0ec004fd1b3890831
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30276152"
---
# <a name="encryption-risks-and-protections"></a>加密风险和保护

Microsoft 遵循控制和合规性框架, 重点关注 Office 365 服务和客户数据的风险。Microsoft 实施了一套大型技术和基于过程的方法 (称为 "控件") 来缓解这些风险。通过控件确定、评估和缓解风险是一个持续的过程。 

云服务 (如设施、网络、服务器、应用程序、用户 (如 Microsoft 管理员) 和数据构成纵深防御策略的各个层中的控件的实现。此策略的关键是, 许多不同的控件都是在不同的层实现的, 以防止出现相同或类似的风险方案。如果由于某种原因控件失败, 这种多层方法将提供失效安全保护。

下面列出了一些风险方案和可缓解它们的当前可用加密技术。在许多情况下, 也可以通过 Office 365 中实现的其他控件来缓解这些情况。

| 加密技术 | 服务 | 密钥管理 | 风险方案 | 值 |
|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BitLocker | Exchange online、SharePoint online 和 Skype for business | Microsoft | Office 365 中的磁盘或服务器被盗或未正确回收。 | BitLocker 提供了一种防故障方法, 可防止因被盗或错误回收的硬件 (服务器/磁盘) 而导致数据丢失。 |
| 服务加密 | SharePoint Online、Skype for business 和 OneDrive for business;Exchange Online (在路线图上) | Microsoft | 内部或外部黑客尝试以 blob 的形式访问各个文件/数据。 | 在不访问密钥的情况下, 无法解密加密的数据。帮助缓解黑客访问数据的风险。 |
| 客户密钥 | SharePoint Online、OneDrive for business、Exchange Online 和 Skype for business | 客户 | N/A (此功能旨在实现合规性功能; 不作为任何风险的缓解措施。) | 帮助客户满足内部法规和合规性义务, 并能够退出 Office 365 服务并撤销 Microsoft 对数据的访问权限 |
| Office 365 和客户端之间的 TLS | Exchange online、SharePoint online、OneDrive for business、Skype for business、团队和 Yammer | Microsoft、客户 | 通过 Internet 点击 Office 365 和客户端计算机之间的数据流的中间人或其他攻击。 | 此实现为 Microsoft 和客户提供了价值, 并确保了在 Office 365 和客户端之间流动时的数据完整性。 |
| Microsoft 数据中心之间的 TLS | Exchange online、SharePoint online、OneDrive for business 和 Skype for business | Microsoft | 中间人或其他攻击, 可点击位于不同 Microsoft 数据中心的 Office 365 服务器之间的客户数据流。 | 此实现是保护数据免受 Microsoft 数据中心之间的攻击的另一种方法。 |
| Azure 权限管理 (包括在 Office 365 或 Azure 信息保护中) | Exchange online、SharePoint online 和 OneDrive for business | 客户 | 数据落入不应访问数据的人的手中。 | azure 信息保护使用 azure RMS, 它通过使用加密、标识和授权策略为客户提供价值, 以帮助保护跨多个设备的文件和电子邮件。Azure RMS 向客户提供了价值, 在这些电子邮件中, 从符合特定条件的所有电子邮件 (即, 所有电子邮件发送到某个地址) 都可以自动加密, 然后再将其发送到另一个收件人。 |
| S/MIME | Exchange Online | 客户 | 电子邮件落入不是预期收件人的人的手中。 | s/mime 通过确保使用 S/mime 加密的电子邮件只能由电子邮件的直接收件人解密来为客户提供价值。 |
| Office 365 邮件加密 | Exchange online、SharePoint online | 客户 | 电子邮件 (包括受保护的附件) 是在不是电子邮件的预期收件人的情况下, 在 Office 365 内部或外部的人。 | OME 为客户提供了价值, 在这些电子邮件从符合特定条件的所有电子邮件 (即, 所有电子邮件发送到某个地址) 之前, 将自动对其进行加密, 然后再将其发送到其他内部或外部收件人。 |
| 具有合作伙伴组织的 SMTP TLS | Exchange Online | 客户 | 在从 Office 365 租户传输到另一个合作伙伴组织时, 会通过中间人或其他攻击截获电子邮件。 | 此方案为客户提供了价值, 以便他们可以在其 Office 365 租户及其合作伙伴的电子邮件组织中的加密 SMTP 通道中发送/接收所有电子邮件。 |

## <a name="encryption-technologies-available-in-office-365-multi-tenant-environments"></a>Office 365 多租户环境中提供的加密技术

| 加密技术 | 实现者 | 密钥交换算法和强度 | 密钥管理 * | 验证 FIPS 140-2 |
|----------------------------------------------------------------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 128-位 + | AES 外部密钥存储在 Exchange 服务器的秘密安全和注册表中。机密安全是一种受保护的存储库, 需要高级别提升和访问权限。只能通过使用名为 "密码箱" 的内部工具来请求和批准访问。AES 外部密钥也存储在服务器的受信任的平台模块中。48位数字密码存储在 Active Directory 中并受密码箱保护。 | 是, 适用于使用 AES 256-bit * * 的服务器 |
|  | SharePoint Online | AES 256 位 | AES 外部密钥存储在秘密安全中。机密安全是一种受保护的存储库, 需要高级别提升和访问权限。只能通过使用名为 "密码箱" 的内部工具来请求和批准访问。AES 外部密钥也存储在服务器的受信任的平台模块中。48位数字密码存储在 Active Directory 中并受密码箱保护。 | 是 |
|  | Skype for Business | AES 256 位 | AES 外部密钥存储在秘密安全中。机密安全是一种受保护的存储库, 需要高级别提升和访问权限。只能通过使用名为 "密码箱" 的内部工具来请求和批准访问。AES 外部密钥也存储在服务器的受信任的平台模块中。48位数字密码存储在 Active Directory 中并受密码箱保护。 | 是 |
| 服务加密 | SharePoint Online | AES 256 位 | 用于加密 blob 的密钥存储在 SharePoint Online 内容数据库中。SharePoint Online 内容数据库受数据库访问控制和静态加密的保护。使用 Azure SQL Database 中的 TDE 执行加密。这些机密是 SharePoint Online 的服务级别, 而不是租户级别。这些机密 (有时称为主密钥) 存储在单独的安全存储库中, 称为 "密钥存储区"。TDE 为活动数据库和数据库备份和事务日志提供了 rest 的安全性。当客户提供可选密钥时, 客户密钥存储在 Azure key Vault 中, 服务使用密钥来加密租户密钥, 该密钥用于加密网站密钥, 然后使用它来加密文件级密钥。实质上, 当客户提供密钥时, 会引入新的密钥层次结构。 | 是 |
|  | Skype for Business | AES 256 位 | 使用不同的随机生成的256位密钥对每个数据片段进行加密。加密密钥存储在相应的元数据 XML 文件中, 该文件也是由每会议主密钥加密的。每次会议中也随机生成一次主密钥。 | 是 |
|  | Exchange Online | AES 256 位 | 每个邮箱都使用使用 Microsoft (在路线图) 控制的加密密钥的数据加密策略或客户 (使用客户密钥时) 进行加密。 | 是 |
| Office 365 与客户端/合作伙伴之间的 TLS | Exchange Online | [支持多个密码套件的机会 TLS](https://technet.microsoft.com/en-us/library/mt163898.aspx) | Exchange Online (outlook.office.com) 的 TLS 证书是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA256RSA 证书。 <br> <br> Exchange Online 的 TLS 根证书是由巴尔的摩 CyberTrust root 颁发的2048位 SHA1RSA 证书。 | 是, 当使用带256位密码强度的 TLS 1.2 时 |
|  | SharePoint Online | 使用 AES 256 的 TLS 1。2 <br> <br> [OneDrive for Business 和 SharePoint Online 中的数据加密](https://technet.microsoft.com/en-us/library/dn905447.aspx) | SharePoint Online (* sharepoint.com) 的 TLS 证书是由巴尔的摩 CyberTrust 根颁发的2048位 SHA256RSA 证书。 <br> <br> SharePoint Online 的 TLS 根证书是由巴尔的摩 CyberTrust root 颁发的2048位 SHA1RSA 证书。 | 是 |
|  | Skype for Business | [适用于 SIP 通信和 PSOM 数据共享会话的 TLS](https://support.office.com/article/Set-up-your-network-for-Skype-for-Business-Online-d21f89b0-3afc-432e-b735-036b2432fdbf) | 适用于 Skype for business 的 TLS 证书 (* lync.com) 是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA256RSA 证书。 <br> <br> Skype for business 的 TLS 根证书是由巴尔的摩 CyberTrust root 颁发的2048位 SHA256RSA 证书。 | 是 |
|  | Microsoft Teams | 使用 AES 256 的 TLS 1。2 <br> <br> [有关 Microsoft 团队的常见问题-管理员帮助](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft 团队的 TLS 证书 (teams.microsoft.com、edge.skype.com) 是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA256RSA 证书。 <br> <br> Microsoft 团队的 TLS 根证书是由巴尔的摩 CyberTrust root 颁发的2048位 SHA256RSA 证书。 | 是 |
| Microsoft 数据中心之间的 TLS | 所有 Office 365 服务 | 使用 AES 256 的 TLS 1。2 <br> <br> 安全实时传输协议 (SRTP) | microsoft 使用内部托管和部署的证书颁发机构来实现 Microsoft 数据中心之间的服务器到服务器的通信。 | 是 |
| Azure 权限管理 (包括在 Office 365 或 Azure 信息保护中) | Exchange Online | 支持[加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)), 这是一个更新和增强的 RMS 加密实现。它支持签名和加密的 RSA 2048, 以及针对签名中的 SHA-256。 | [由 Microsoft 进行管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支持[加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)), 这是一个更新和增强的 RMS 加密实现。它支持签名和加密的 RSA 2048, 以及用于签名的 SHA-256。 | [由 Microsoft 进行管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key), 这是默认设置;和 <br> <br> 客户管理的是 Microsoft 托管密钥的替代方法。具有 IT 托管的 Azure 订阅的组织可以使用 BYOK 并记录其使用情况, 而无需额外付费。有关详细信息, 请参阅[实现提供自己的密钥](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。在此配置中, 将使用 Thales hsm 来保护你的密钥。有关详细信息, 请参阅[Thales hsm 和 Azure RMS](http://www.thales-esecurity.com/msrms/cloud)。 | 是 |
| S/MIME | Exchange Online | 加密邮件语法标准 1.5 (PKCS #7) | 取决于已部署的客户管理的公钥基础结构。客户执行密钥管理, Microsoft 永远无法访问用于签名和解密的私钥。 | 是, 当配置为使用3des 或 AES256 加密传出邮件时 |
| Office 365 邮件加密 | Exchange Online | 与 Azure RMS 相同 ([加密模式 2](https://technet.microsoft.com/en-us/library/dn569290.aspx) -用于签名和加密的 RSA 2048, 对于签名, 则为 SHA-256) | 使用 Azure 信息保护作为其加密基础结构。使用的加密方法取决于您获取用于加密和解密邮件的 RMS 密钥的位置。 | 是 |
| 具有合作伙伴组织的 SMTP TLS | Exchange Online | 使用 AES 256 的 TLS 1。2 | Exchange Online (outlook.office.com) 的 TLS 证书是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA256RSA 证书。 <br> <br> Exchange Online 的 TLS 根证书是由巴尔的摩 CyberTrust root 颁发的2048位 SHA1RSA 证书。 | 是, 当使用带256位密码强度的 TLS 1.2 时 |

**此表中引用的 TLS 证书适用于美国数据中心;非美国数据中心也使用2048位 SHA256RSA 证书。*

***Exchange Online 多租户环境中的大多数服务器都是通过 AES 256 位加密为 BitLocker 进行部署。使用 AES 128 位的服务器将逐步推出。*

## <a name="encryption-technologies-available-in-government-cloud-community-environments"></a>政府云社区环境中提供的加密技术

| 加密技术 | 实现者 | 密钥交换算法和强度 | 密钥管理 * | 验证 FIPS 140-2 |
|---------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 256 位 | AES 外部密钥存储在 Exchange 服务器的秘密安全和注册表中。机密安全是一种受保护的存储库, 需要高级别提升和访问权限。只能通过使用名为 "密码箱" 的内部工具来请求和批准访问。AES 外部密钥也存储在服务器的受信任的平台模块中。48位数字密码存储在 Active Directory 中并受密码箱保护。 | 是 |
|  | SharePoint Online | AES 256 位 | AES 外部密钥存储在秘密安全中。机密安全是一种受保护的存储库, 需要高级别提升和访问权限。只能通过使用名为 "密码箱" 的内部工具来请求和批准访问。AES 外部密钥也存储在服务器的受信任的平台模块中。48位数字密码存储在 Active Directory 中并受密码箱保护。 | 是 |
|  | Skype for Business | AES 256 位 | AES 外部密钥存储在秘密安全中。机密安全是一种受保护的存储库, 需要高级别提升和访问权限。只能通过使用名为 "密码箱" 的内部工具来请求和批准访问。AES 外部密钥也存储在服务器的受信任的平台模块中。48位数字密码存储在 Active Directory 中并受密码箱保护。 | 是 |
| 服务加密 | SharePoint Online | AES 256 位 | 用于加密 blob 的密钥存储在 SharePoint Online 内容数据库中。SharePoint Online 内容数据库受数据库访问控制和静态加密的保护。使用 Azure SQL Database 中的 TDE 执行加密。这些机密是 SharePoint Online 的服务级别, 而不是租户级别。这些机密 (有时称为主密钥) 存储在单独的安全存储库中, 称为 "密钥存储区"。TDE 为活动数据库和数据库备份和事务日志提供了 rest 的安全性。当客户提供可选密钥时, 客户密钥存储在 Azure key Vault 中, 服务使用密钥来加密租户密钥, 该密钥用于加密网站密钥, 然后使用它来加密文件级密钥。实质上, 当客户提供密钥时, 会引入新的密钥层次结构。 | 是 |
|  | Skype for Business | AES 256 位 | 使用不同的随机生成的256位密钥对每个数据片段进行加密。加密密钥存储在相应的元数据 XML 文件中, 该文件也是由每会议主密钥加密的。每次会议中也随机生成一次主密钥。 | 是 |
|  | Exchange Online | AES 256 位 | 每个邮箱都使用使用 Microsoft 或客户控制的加密密钥的数据加密策略进行加密 (使用客户密钥时)。 | 是 |
| Office 365 与客户端/合作伙伴之间的 TLS | Exchange Online | [支持多个密码套件的机会 TLS](https://technet.microsoft.com/en-us/library/mt163898.aspx) | Exchange Online (outlook.office.com) 的 TLS 证书是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA256RSA 证书。 <br> <br> Exchange Online 的 TLS 根证书是由巴尔的摩 CyberTrust root 颁发的2048位 SHA1RSA 证书。 | 是, 当使用带256位密码强度的 TLS 1.2 时 |
|  | SharePoint Online | 使用 AES 256 的 TLS 1。2 | SharePoint Online (* sharepoint.com) 的 TLS 证书是由巴尔的摩 CyberTrust 根颁发的2048位 SHA256RSA 证书。 <br> <br> SharePoint Online 的 TLS 根证书是由巴尔的摩 CyberTrust root 颁发的2048位 SHA1RSA 证书。 | 是 |
|  | Skype for Business | 适用于 SIP 通信和 PSOM 数据共享会话的 TLS | 适用于 Skype for business 的 TLS 证书 (* lync.com) 是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA256RSA 证书。 <br> <br> Skype for business 的 TLS 根证书是由巴尔的摩 CyberTrust root 颁发的2048位 SHA256RSA 证书。 | 是 |
|  | Microsoft Teams | [有关 Microsoft 团队的常见问题-管理员帮助](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft 团队的 TLS 证书 (teams.microsoft.com; edge.skype.com) 是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA256RSA 证书。 <br> <br> Microsoft 团队的 TLS 根证书是由巴尔的摩 CyberTrust root 颁发的2048位 SHA256RSA 证书。 | 是 |
| Microsoft 数据中心之间的 TLS | Exchange online、SharePoint online、Skype for business | 使用 AES 256 的 TLS 1。2 | microsoft 使用内部托管和部署的证书颁发机构来实现 Microsoft 数据中心之间的服务器到服务器的通信。 | 是 |
|  |  | 安全实时传输协议 (SRTP) |  |  |
| Azure 权限管理服务 | Exchange Online | 支持[加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)), 这是一个更新和增强的 RMS 加密实现。它支持签名和加密的 RSA 2048, 以及针对签名中的 SHA-256。 | [由 Microsoft 进行管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支持[加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10)), 这是一个更新和增强的 RMS 加密实现。它支持签名和加密的 RSA 2048, 以及针对签名中的 SHA-256。 | [由 Microsoft 进行管理](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key), 这是默认设置;和 <br> <br> 客户托管 (也称为 BYOK), 这是 Microsoft 托管密钥的替代方法。具有 IT 托管的 Azure 订阅的组织可以使用 BYOK 并记录其使用情况, 而无需额外付费。有关详细信息, 请参阅[实现提供自己的密钥](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。<br> <br> 在 BYOK 方案中, Thales hsm 用于保护你的密钥。有关详细信息, 请参阅[Thales hsm 和 Azure RMS](http://www.thales-esecurity.com/msrms/cloud)。 | 是 |
| S/MIME | Exchange Online | 加密邮件语法标准 1.5 (PKCS #7) | 取决于部署的公钥基础结构。 | 是, 当配置为使用3des 或 AES-256 加密传出邮件时。 |
| Office 365 邮件加密 | Exchange Online | 与 Azure RMS 相同 ([加密模式 2](https://technet.microsoft.com/en-us/library/dn569290.aspx) -用于签名和加密的 RSA 2048, 对于签名中的哈希, 为 SHA-256) | 使用 Azure RMS 作为其加密基础结构。使用的加密方法取决于您获取用于加密和解密邮件的 RMS 密钥的位置。 <br> <br> 如果使用 Microsoft Azure RMS 获取密钥, 则使用加密模式2。如果使用 Active Directory (AD) RMS 获取密钥, 则使用的是加密模式1或加密模式2。所使用的方法取决于您的内部部署 AD RMS 部署。加密模式1是最初的 AD RMS 加密实现。它支持针对签名和加密的 RSA 1024, 并支持对 SHA-1 进行签名。除了使用 hsm 的 BYOK 配置之外, 所有当前版本的 RMS 仍将继续支持此模式。 | 是 |
| 具有合作伙伴组织的 SMTP TLS | Exchange Online | 使用 AES 256 的 TLS 1。2 | Exchange Online (outlook.office.com) 的 TLS 证书是由巴尔的摩 CyberTrust Root 颁发的2048位 SHA256RSA 证书。 <br> <br> Exchange Online 的 TLS 根证书是由巴尔的摩 CyberTrust root 颁发的2048位 sha1RSA 证书。 <br> <br> 请注意, 出于安全考虑, 我们的证书随时都会发生变化。 | 是 |

**此表中引用的 TLS 证书适用于美国数据中心;非美国数据中心也使用2048位 SHA256RSA 证书。*