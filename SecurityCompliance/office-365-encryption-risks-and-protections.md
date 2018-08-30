---
title: Office 365 加密风险和保护功能
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 8/21/2018
audience: ITPro
ms.topic: article
ms.service: Office 365 Administration
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 摘要： 了解 Microsoft Office 365 中的数据恢复能力。
ms.openlocfilehash: 69956c5f32f74a93b2101d2651ef7de03ad1094f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526010"
---
# <a name="encryption-risks-and-protections"></a>加密风险和保护

Microsoft 遵循着重于风险到 Office 365 服务和客户数据的控制和合规性框架。Microsoft 实现一大组技术和 （也称为控件） 的基于流程的方法，以缓解这些风险。标识和评估的控件通过的风险缓解是连续的过程。我们的云服务设施、 网络、 服务器、 应用程序，用户 （例如 Microsoft 管理员） 和数据等各种图层中的控件的实现窗体的深层防护策略。此策略的关键是，在不同的层保护相同或类似的风险实现多个不同的控件。控件因某些原因而失败的情况下，此多层的方法提供防故障的保护。下面列出了一些风险和缓解它们的当前可用的加密技术。这些方案都是在许多情况下也缓解通过在 Office 365 中实现其他控件。

| 加密技术 | 服务 | 密钥管理 | 风险方案 | 值 |
|----------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------|---------------------|------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| BitLocker | Exchange Online、 SharePoint Online 和 Skype for Business | Microsoft | 盗取或不正确地都已回收磁盘或 Office 365 中的服务器。 | BitLocker 提供了防故障一种方法可以防止由于被盗或不正确地回收硬件 （服务器/磁盘） 的数据丢失。 |
| 服务加密 | SharePoint Online，for Business，Skype 和 OneDrive for Business;Exchange Online （在指南） | Microsoft | 内部或外部的黑客尝试访问各个文件/为 blob 数据。 | 无法访问键而无法解密的加密的数据。有助于缓解一些黑客访问数据的风险。 |
| 客户密钥 | SharePoint Online，OneDrive for Business、 Exchange Online 和 Skype for Business | 客户 | N/A （此功能旨在作为合规性功能; 不为任何风险缓解。） | 可帮助客户满足内部法规合规性义务和保留 Office 365 服务和取消对数据的 Microsoft 的访问的能力 |
| Office 365 和客户端之间的 TLS | Exchange Online，SharePoint Online 的 OneDrive for Business、 Business、 团队和 Yammer 的 Skype | Microsoft 客户 | 拦截中或其他攻击点击 Internet 上的 Office 365 和客户端计算机之间的数据流。 | 此实现为 Microsoft 和客户提供的价值，并确保数据完整性，Office 365 和客户端之间流动。 |
| Microsoft 数据中心之间的 TLS | Exchange Online，SharePoint Online，OneDrive for Business 和 Skype for Business | Microsoft | 拦截中或其他攻击点击客户位于不同的 Microsoft 数据中心中的 Office 365 服务器之间的数据流。 | 此实现是另一种方法来保护数据以免 Microsoft 数据中心之间的攻击。 |
| Azure 权限管理 （包括在 Office 365 或 Azure 信息保护） | Exchange Online、 SharePoint Online 和 OneDrive for Business | 客户 | 数据可分为手中不应包含访问数据的人员。 | Azure 信息保护使用 Azure RMS 它通过使用加密、 标识和授权策略来帮助保护文件和跨多个设备电子邮件向客户提供值。Azure RMS 其中来自 Office 365 某些条件 （即，所有电子邮件到特定地址） 相匹配的所有邮件可被自动都加密之前它们获取发送到另一个收件人的客户提供值。 |
| S/MIME | Exchange Online | 客户 | 电子邮件可分为手中的某个人不是预期接收人。 | S/MIME 确保使用 S/MIME 加密的电子邮件只能直接收件人的电子邮件解密，为客户提供值。 |
| Office 365 邮件加密 | Exchange Online，SharePoint Online | 客户 | 电子邮件，包括受保护的附件属于手中的某个人内部或外部 Office 365 不是预期的收件人的电子邮件中。 | OME value 提供客户其中来自 Office 365 某些条件 （即，所有电子邮件到特定地址） 相匹配的所有邮件将被自动都加密之前它们获取发送到另一个内部或外部收件人。 |
| 与合作伙伴组织的 SMTP TLS | Exchange Online | 客户 | 通过从 Office 365 租户到另一个合作伙伴组织的传输过程中拦截中或其他攻击，截获电子邮件。 | 这种情况下向客户提供值，以便他们还可以发送/接收其 Office 365 租户和加密 SMTP 通道内的其合作伙伴电子邮件组织之间的所有电子邮件。 |

下表汇总了在 Office 365 多租户和政府云社区环境中可用的加密技术。

| 加密技术 | 通过实现 | 密钥交换算法和强度 | 密钥管理 * | FIPS 140 2 验证 |
|----------------------------------------------------------------------------------|-------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| BitLocker | Exchange Online | AES 128-bit + | AES 外部密钥存储在密码安全和 Exchange 服务器的注册表中。机密的安全是需要高级提升和审批访问的安全存储库。访问可以请求和批准只能通过使用内部调用密码箱的工具。AES 外部密钥也存储在服务器中的受信任的平台模块。48 位数字密码是 Active Directory 中存储且受密码箱。 | 是的服务器使用 AES 256-位 * * |
|  | SharePoint Online | 256 位 AES | AES 密钥加密外部存储在密码安全。机密的安全是需要高级提升和审批访问的安全存储库。访问可以请求和批准只能通过使用内部调用密码箱的工具。AES 外部密钥也存储在服务器中的受信任的平台模块。48 位数字密码是 Active Directory 中存储且受密码箱。 | 是 |
|  | Skype for Business | 256 位 AES | AES 密钥加密外部存储在密码安全。机密的安全是需要高级提升和审批访问的安全存储库。访问可以请求和批准只能通过使用内部调用密码箱的工具。AES 外部密钥也存储在服务器中的受信任的平台模块。48 位数字密码是 Active Directory 中存储且受密码箱。 | 是 |
| 服务加密 | SharePoint Online | 256 位 AES | SharePoint Online 内容数据库中存储用于加密 blob 的键。数据库访问控制和静态加密受 SharePoint Online 内容数据库。Azure SQL 数据库中使用 TDE 执行加密。在 SharePoint Online，不能在租户级别的服务级别都是这些机密。这些机密 （有时称为主密钥） 存储在称为项存储区的单独安全存储库中。TDE 提供安全的活动数据库并将数据库备份和事务日志的其余部分。当客户提供可选的密钥时，客户参数存储在 Azure 键电子仓库，和服务使用密钥加密租户密钥，用于加密网站密钥，然后用来加密文件级别参数。实际上，引入了新的密钥层次结构时客户提供键。 | 是 |
|  | Skype for Business | 256 位 AES | 使用不同的随机生成的 256 位密钥加密每段数据。在按每个会议主密钥还加密相应元数据 XML 文件中存储加密密钥。每个会议也随机生成一次主密钥。 | 是 |
|  | Exchange Online | 256 位 AES | 每个邮箱都是使用数据加密策略使用加密密钥 （当使用客户键时） 控制由 Microsoft （在路线图） 或客户进行加密。 | 是 |
| Office 365 和客户端/合作伙伴之间的 TLS | Exchange Online | [支持多个密码套件的机会型 TLS](https://technet.microsoft.com/en-us/library/mt163898.aspx) | Exchange Online (outlook.office.com) 的 TLS 证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA256RSA 证书。 | 是，使用具有 256 位加密强度的 TLS 1.2 时 |
|  |  |  | Exchange Online 的 TLS 根证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA1RSA 证书。 |  |
|  | SharePoint Online | 与 AES 256 TLS 1.2 | SharePoint online 的 TLS 证书 (*。 sharepoint.com) 是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA256RSA 证书。 | 是 |
|  |  | [OneDrive for Business 和 SharePoint Online 中的数据加密](https://technet.microsoft.com/en-us/library/dn905447.aspx) | SharePoint online 的 TLS 根证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA1RSA 证书。 |  |
|  | Skype for Business | [TLS 进行 SIP 通信和 PSOM 数据共享会话](https://support.office.com/article/Set-up-your-network-for-Skype-for-Business-Online-d21f89b0-3afc-432e-b735-036b2432fdbf) | Skype for Business 的 TLS 证书 (*。 lync.com) 是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA256RSA 证书。 | 是 |
|  |  |  | Skype for Business 的 TLS 根证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA256RSA 证书。 |  |
|  | Microsoft Teams | 与 AES 256 TLS 1.2 | （teams.microsoft.com、 edge.skype.com） 的 Microsoft 团队的 TLS 证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA256RSA 证书。 | 是 |
|  |  | [有关常见问题的 Microsoft 团队 – 管理员帮助](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | Microsoft 团队的 TLS 根证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA256RSA 证书。 |  |
| Microsoft 数据中心之间的 TLS | 所有 Office 365 服务 | 与 AES 256 TLS 1.2 | Microsoft 使用内部托管和部署的证书颁发机构的 Microsoft 数据中心之间的服务器到服务器通信。 | 是 |
|  |  | 安全实时传输协议 (SRTP) |  |  |
| Azure 权限管理 （包括在 Office 365 或 Azure 信息保护） | Exchange Online | 支持[加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))，更新和增强 RMS 加密实现。它支持中签名的哈希 RSA 2048 进行签名和加密和 160、SHA 256。 | [由 Microsoft 托管](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支持[加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))，更新和增强 RMS 加密实现。它支持签名 RSA 2048 进行签名和加密和 160、SHA 256。 | [由 Microsoft 托管](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)，这是默认设置;或 | 是 |
|  |  |  | 客户管理的即 Microsoft 托管密钥的替代项。拥有 IT 托管的 Azure 订阅的组织可以使用 BYOK 并登录免费额外及其用法。有关详细信息，请参阅[Implementing 使您自己的密钥](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。在此配置中，Thales Hsm 用于保护您的密钥。有关详细信息，请参阅[Thales Hsm 和 Azure RMS](http://www.thales-esecurity.com/msrms/cloud)。 |  |
| S/MIME | Exchange Online | 加密消息语法标准 1.5 (PKCS #7) | 取决于客户托管公钥基础结构部署。密钥管理由客户、 执行和 Microsoft 永远不会有权访问用于签名和解密的私钥。 | 是，配置与 3DES 或 AES256 传出邮件进行加密时 |
| Office 365 邮件加密 | Exchange Online | Azure RMS ([加密模式 2](https://technet.microsoft.com/en-us/library/dn569290.aspx) -签名和加密的 RSA 2048 和 160、SHA-256 用于签名) 相同 | 使用 Azure 信息保护作为其加密基础结构。使用的加密方法取决于在其中获取用于加密和解密邮件的 RMS 密钥。 | 是 |
| 与合作伙伴组织的 SMTP TLS | Exchange Online | 与 AES 256 TLS 1.2 | Exchange Online (outlook.office.com) 的 TLS 证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA256RSA 证书。 | 是，使用具有 256 位加密强度的 TLS 1.2 时 |
|  |  |  | Exchange Online 的 TLS 根证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA1RSA 证书。 |  |

**此表中引用的 TLS 证书适用于美国数据中心;非美国数据中心还使用 2048年位 SHA256RSA 证书。*

***在 Exchange Online 的多租户环境中的大多数服务器已部署与 AES 256 位 BitLocker 加密。使用 AES 128 位服务器是正在淘汰。*

| 加密技术 | 通过实现 | 密钥交换算法和强度 | 密钥管理 * | FIPS 140 2 验证 |
|---------------------------------------------|--------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------|
| BitLocker | Exchange Online | 256 位 AES | AES 外部密钥存储在密码安全和 Exchange 服务器的注册表中。机密的安全是需要高级提升和审批访问的安全存储库。访问可以请求和批准只能通过使用内部调用密码箱的工具。AES 外部密钥也存储在服务器中的受信任的平台模块。48 位数字密码是 Active Directory 中存储且受密码箱。 | 是 |
|  | SharePoint Online | 256 位 AES | AES 密钥加密外部存储在密码安全。机密的安全是需要高级提升和审批访问的安全存储库。访问可以请求和批准只能通过使用内部调用密码箱的工具。AES 外部密钥也存储在服务器中的受信任的平台模块。48 位数字密码是 Active Directory 中存储且受密码箱。 | 是 |
|  | Skype for Business | 256 位 AES | AES 密钥加密外部存储在密码安全。机密的安全是需要高级提升和审批访问的安全存储库。访问可以请求和批准只能通过使用内部调用密码箱的工具。AES 外部密钥也存储在服务器中的受信任的平台模块。48 位数字密码是 Active Directory 中存储且受密码箱。 | 是 |
| 服务加密 | SharePoint Online | 256 位 AES | SharePoint Online 内容数据库中存储用于加密 blob 的键。数据库访问控制和静态加密受 SharePoint Online 内容数据库。Azure SQL 数据库中使用 TDE 执行加密。在 SharePoint Online，不能在租户级别的服务级别都是这些机密。这些机密 （有时称为主密钥） 存储在称为项存储区的单独安全存储库中。TDE 提供安全的活动数据库并将数据库备份和事务日志的其余部分。当客户提供可选的密钥时，客户参数存储在 Azure 键电子仓库，和服务使用密钥加密租户密钥，用于加密网站密钥，然后用来加密文件级别参数。实际上，引入了新的密钥层次结构时客户提供键。 | 是 |
|  | Skype for Business | 256 位 AES | 使用不同的随机生成的 256 位密钥加密每段数据。在按每个会议主密钥还加密相应元数据 XML 文件中存储加密密钥。每个会议也随机生成一次主密钥。 | 是 |
|  | Exchange Online | 256 位 AES | 每个邮箱都是使用数据加密策略使用加密密钥 （当使用客户键时） 控制由 Microsoft 或客户进行加密。 | 是 |
| Office 365 和客户端/合作伙伴之间的 TLS | Exchange Online | [支持多个密码套件的机会型 TLS](https://technet.microsoft.com/en-us/library/mt163898.aspx) | Exchange Online (outlook.office.com) 的 TLS 证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA256RSA 证书。 | 是，使用具有 256 位加密强度的 TLS 1.2 时 |
|  |  |  | Exchange Online 的 TLS 根证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA1RSA 证书。 |  |
|  | SharePoint Online | 与 AES 256 TLS 1.2 | SharePoint online 的 TLS 证书 (*。 sharepoint.com) 是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA256RSA 证书。 | 是 |
|  |  |  | SharePoint online 的 TLS 根证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA1RSA 证书。 |  |
|  | Skype for Business | TLS 进行 SIP 通信和 PSOM 数据共享会话 | Skype for Business 的 TLS 证书 (*。 lync.com) 是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA256RSA 证书。 | 是 |
|  |  |  | Skype for Business 的 TLS 根证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA256RSA 证书。 |  |
|  | Microsoft Teams | [有关常见问题的 Microsoft 团队 – 管理员帮助](https://docs.microsoft.com/MicrosoftTeams/teams-overview) | （teams.microsoft.com; edge.skype.com） 的 Microsoft 团队的 TLS 证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA256RSA 证书。 | 是 |
|  |  |  | Microsoft 团队的 TLS 根证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA256RSA 证书。 |  |
| Microsoft 数据中心之间的 TLS | Exchange Online，SharePoint Online，Skype for Business | 与 AES 256 TLS 1.2 | Microsoft 使用内部托管和部署的证书颁发机构的 Microsoft 数据中心之间的服务器到服务器通信。 | 是 |
|  |  | 安全实时传输协议 (SRTP) |  |  |
| Azure 权限管理服务 | Exchange Online | 支持[加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))，更新和增强 RMS 加密实现。它支持中签名的哈希 RSA 2048 进行签名和加密和 160、SHA 256。 | [由 Microsoft 托管](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 | 是 |
|  | SharePoint Online | 支持[加密模式 2](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/hh867439(v=ws.10))，更新和增强 RMS 加密实现。它支持中签名的哈希 RSA 2048 进行签名和加密和 160、SHA 256。 | [由 Microsoft 托管](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)，这是默认设置;或 | 是 |
|  |  |  | 客户管理 (也称为 BYOK)，这是 Microsoft 托管密钥的替代项。拥有 IT 托管的 Azure 订阅的组织可以使用 BYOK 并登录免费额外及其用法。有关详细信息，请参阅[Implementing 使您自己的密钥](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。 |  |
|  |  |  | 在 BYOK 方案中，Thales Hsm 用于保护您的密钥。有关详细信息，请参阅[Thales Hsm 和 Azure RMS](http://www.thales-esecurity.com/msrms/cloud)。 |  |
| S/MIME | Exchange Online | 加密消息语法标准 1.5 (PKCS #7) | 取决于公钥基础结构部署。 | 是，配置与 3DES 或 AES 256 的传出邮件进行加密时。 |
| Office 365 邮件加密 | Exchange Online | Azure RMS ([加密模式 2](https://technet.microsoft.com/en-us/library/dn569290.aspx) -签名和加密的 RSA 2048 和 160、SHA-256 用于签名中的哈希) 相同 | 使用 Azure RMS 作为其加密基础结构。使用的加密方法取决于在其中获取用于加密和解密邮件的 RMS 密钥。 | 是 |
|  |  |  | 如果您使用 Microsoft Azure RMS 获取密钥，则使用加密模式 2。如果您使用 Active Directory (AD) RMS 获取密钥，则使用加密模式 1 或加密模式 2。使用的方法取决于您的内部部署 AD RMS 部署。加密模式 1 是原始 AD RMS 加密实现。它支持 RSA 1024 签名和加密和签名支持 sha-1。此模式将继续受 RMS，除了使用 Hsm 的 BYOK 配置的所有当前版本。 |  |
| 与合作伙伴组织的 SMTP TLS | Exchange Online | 与 AES 256 TLS 1.2 | Exchange Online (outlook.office.com) 的 TLS 证书是由巴尔的摩 CyberTrust 根颁发 2048年位 SHA256RSA 证书。 | 是 |
|  |  |  | Exchange Online 的 TLS 根证书是由巴尔的摩 CyberTrust 根颁发 2048年位 sha1RSA 证书。 |  |
|  |  |  | *请注意，为了安全起见，我们证书执行更改经常。* |  |

**此表中引用的 TLS 证书适用于美国数据中心;非美国数据中心还使用 2048年位 SHA256RSA 证书。*