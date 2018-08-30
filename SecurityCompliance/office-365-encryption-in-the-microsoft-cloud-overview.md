---
title: Microsoft 云中的加密
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
description: Overview of Microsoft 云中的加密。
ms.openlocfilehash: b8dee7ca7a791878763b885ada40a1d87f074e8e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525822"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Microsoft 云中的加密

各种技术和过程，包括各种形式的加密受 Microsoft 的企业云服务中的客户数据。(本文档中的 office 365 客户数据包括 Exchange Online 邮箱内容 (电子邮件正文、 日历项和电子邮件附件的内容，如果适用，则业务内容的 Skype)、 SharePoint Online 网站内容和文件存储中网站和文件上载到 OneDrive 适用于商务或 for Business 的 Skype。）Microsoft 使用多个加密方法、 协议和密码在其产品和服务之间提供客户数据经过我们云的服务，并帮助保护的客户数据存储中的机密性安全路径帮助云服务。Microsoft 使用一些可用于提供针对未经授权访问客户数据的障碍的强大、 最安全的加密协议。Microsoft 致力于确保所有 Microsoft 托管加密密钥正确都安全和正确的密钥管理也是加密最佳实践，基本元素。

无论客户配置客户数据存储在 Microsoft 的企业云服务中使用的加密的一个或多个窗体保护。（我们加密的策略和其实施的验证独立验证的多个的第三方审核员和的这些审核报告是[服务信任门户](https://aka.ms/stp)上可用。）

Microsoft 提供的加密在 rest 和在传输过程中的客户数据的服务商技术。例如，对于在 rest 客户数据，Microsoft Azure 使用[BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview)和[DM Crypt](https://en.wikipedia.org/wiki/Dm-crypt)，和 Microsoft Office 365 使用 BitLocker、 [Azure 存储服务加密](https://azure.microsoft.com/documentation/articles/storage-service-encryption/)、[分布式密钥管理器](https://support.office.com/article/989ba10c-f73f-4efb-ad1b-af3322e5f376)(DKM) 和 Office 365 服务加密。对于在传输过程中的客户数据，Azure、 Office 365、 Microsoft 商业支持、 Microsoft Dynamics 365、 Microsoft Power BI 和 Visual Studio Team Services 使用行业标准安全传输协议，如 Internet 协议安全性 (IPsec) 和Microsoft 数据中心之间以及用户设备与 Microsoft 数据中心之间传输层安全性 (TLS)。

除了由 Microsoft 提供的加密安全基准级别，我们云服务还包括您可以管理的其他加密选项。例如，您可以启用加密其 Azure 虚拟机 (Vm) 与他们的用户之间的通信。使用[Azure 虚拟网络](https://azure.microsoft.com/services/virtual-network/)，可以使用行业标准 IPsec 协议以及 Azure 虚拟机上虚拟网络产权您公司的 VPN 网关之间的通信进行加密。此外，此外，[新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)，可以向任何人发送加密的邮件。

Microsoft 按照公共密钥基础结构操作安全标准，它是[Microsoft 安全策略](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)的一个组件，利用包含证书的 Windows 操作系统中的加密功能和身份验证机制，包括使用满足 140-2 标准的美国政府[联邦信息处理标准](http://csrc.nist.gov/publications/PubsFIPS.html)(FIPS) 的加密模块。（microsoft 相关 NIST 证书号码，请访问http://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> [注意]若要访问作为资源的 Microsoft 安全策略，您必须使用工作或学校帐户登录。如果您没有订阅尚未，[您可以注册免费试用版](https://servicetrust.microsoft.com/Home/TrialSubscriptions)。

FIPS 140 2 是专为验证实现加密，而不是使用这些产品的产品模块设计标准。在服务中实现的加密模块可以认证为会议哈希强度、 密钥管理和类似内容的要求。随时加密功能用于保护保密性、 完整性或 Microsoft 云服务中的数据的可用性的模块和密码使用符合 FIPS 140-2 标准。

Microsoft 认证我们与每个新版本的 Windows 操作系统的云服务中使用的基础加密模块：
- Azure 和 Azure 美国政府
- Dynamics 365 和 Dynamics 365 美国政府
- Office 365、 Office 365 美国政府和 Office 365 美国政府国防

加密的 Office 365 客户静态数据是由提供多个服务端技术，包括 BitLocker、 DKM、 Azure 存储服务加密和服务加密在 Exchange Online、 Skype for Business、 OneDrive for Business 和 SharePoint联机。Office 365 服务加密包括选项，可使用 Azure 键存储库中存储的客户管理加密密钥。此客户托管密钥选项，请调用[Office 365 客户参数](https://support.office.com/article/f2cd475a-e592-46cf-80a3-1bfb0fa17697)，仅供 Exchange Online、 SharePoint Online、 Skype for Business，以及 OneDrive for Business。

对于在传输过程中的客户数据，所有 Office 365 服务器都协商安全会话使用 TLS 默认客户端计算机以确保以安全客户数据。 这适用于使用的客户端，如 Skype 业务、 Outlook 和 Outlook web、 移动客户端和 web 浏览器上的任何设备上的协议。

（所有面向客户的服务器到 TLS 1.2 都协商默认情况下，但我们还支持协商下较低的标准，如果需要）。

## <a name="related-links"></a>相关的链接

- [Azure 中的加密](office-365-azure-encryption.md)
- [用于加密的 BitLocker 和 Distributed Key Manager (DKM)](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 服务加密](office-365-service-encryption.md)
- [Skype for Business、 OneDrive for Business、 SharePoint Online 和 Exchange Online 的 office 365 加密](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [传输中的数据的加密](office-365-encryption-for-data-in-transit.md)
- [客户管理的加密功能](office-365-customer-managed-encryption-features.md)
- [加密风险和保护](office-365-encryption-risks-and-protections.md)
- [Microsoft Dynamics 365 中的加密](office-365-encryption-in-microsoft-dynamics-365.md)