---
title: Microsoft 云中的加密
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
description: Microsoft 云中的加密概述。
ms.openlocfilehash: 8d4b94908e9847062ff5f4612b8726b44a36a59f
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275942"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Microsoft 云中的加密

Microsoft 企业云服务中的客户数据受各种技术和过程 (包括各种形式的加密) 的保护。(此文档中的 Office 365 客户数据包括 Exchange Online 邮箱内容 (电子邮件正文、日历条目和电子邮件附件的内容)、SharePoint Online 网站内容和存储在中的文件网站和上载到 OneDrive for business 或 Skype for business 的文件。)Microsoft 在其产品和服务中使用多种加密方法、协议和密码, 以帮助为客户数据提供安全路径, 以通过我们的云服务进行传输, 并帮助保护存储在中的客户数据的机密性我们的云服务。Microsoft 使用一些最强大、最安全的加密协议来抵御对客户数据的未授权访问的障碍。正确的密钥管理也是加密最佳实践的重要元素, microsoft 可以确保所有 microsoft 托管的加密密钥都得到了适当的保护。

无论客户配置如何, 存储在 Microsoft 企业云服务中的客户数据都使用一种或多种形式的加密进行保护。(我们的加密策略及其强制实施的验证将独立于多个第三方审计员进行验证, 这些审核的报告在[服务信任门户](https://aka.ms/stp)上可用。)

Microsoft 提供了在 rest 和途对客户数据进行加密的服务端技术。例如, 对于 rest 上的客户数据, microsoft Azure 使用[bitlocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview)和[DM-Crypt](https://en.wikipedia.org/wiki/Dm-crypt), 而 microsoft Office 365 使用 bitlocker、 [Azure 存储服务加密](https://azure.microsoft.com/documentation/articles/storage-service-encryption/)、[分布式密钥管理器](https://support.office.com/article/989ba10c-f73f-4efb-ad1b-af3322e5f376)(DKM) 和 Office 365 服务技术.对于传输中的客户数据、Azure、Office 365、microsoft 商业支持、microsoft Dynamics 365、microsoft Power BI 和 Visual Studio Team Services 使用行业标准安全传输协议, 如 Internet 协议安全性 (IPsec) 和Microsoft 数据中心之间和用户设备与 Microsoft 数据中心之间的传输层安全性 (TLS)。

除了 Microsoft 提供的加密安全的基准级别之外, 我们的云服务还包括您可以管理的其他加密选项。例如, 您可以对其 Azure 虚拟机 (vm) 及其用户之间的流量启用加密。使用[Azure 虚拟网络](https://azure.microsoft.com/services/virtual-network/), 您可以使用行业标准 IPsec 协议来加密公司 VPN 网关和 Azure 之间以及位于虚拟网络上的虚拟机之间的通信。此外,[新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)允许您向任何人发送加密邮件。

根据公钥基础结构运营安全标准 (这是[Microsoft 安全策略](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)的一个组件), microsoft 利用 Windows 操作系统中包含的加密功能来颁发证书和身份验证机制, 包括使用符合美国政府的[联邦信息处理标准](http://csrc.nist.gov/publications/PubsFIPS.html)(FIPS) 140-2 标准的加密模块。(可在处找到适用于 Microsoft 的可 NIST 证书号码。http://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> 便笺若要将 Microsoft 安全策略作为资源进行访问, 必须使用工作或学校帐户登录。如果你还没有订阅,[可以注册免费试用版](https://servicetrust.microsoft.com/Home/TrialSubscriptions)。

FIPS 140-2 是一种标准, 专门用于验证实施加密的产品模块, 而不是使用它们的产品。在服务内实施的加密模块可以通过符合哈希强度、密钥管理等的要求进行认证。任何时间都使用加密功能来保护 Microsoft 云服务中的数据的机密性、完整性或可用性, 使用的模块和密码符合 FIPS 140-2 标准。

Microsoft 通过每个新版本的 Windows 操作系统证明在云服务中使用的基础加密模块:
- azure 和 azure 美国政府版
- Dynamics 365 和 dynamics 365 美国政府版
- office 365、office 365 美国政府版和 office 365 美国政府防御

Office 365 客户数据的加密由多个服务端技术提供, 其中包括 BitLocker、DKM、Azure 存储服务加密和 Exchange Online 中的服务加密、Skype for business、OneDrive for business 和 SharePoint隐私声明.Office 365 服务加密包含一个选项, 可使用存储在 Azure Key Vault 中的客户托管的加密密钥。此客户管理的密钥选项称为[Office 365 customer key](https://support.office.com/article/f2cd475a-e592-46cf-80a3-1bfb0fa17697), 可用于 Exchange online、SharePoint online、Skype for business 和 OneDrive for business。

对于传输中的客户数据, 所有 Office 365 服务器在默认情况下将使用 TLS 与客户端计算机协商安全会话以保护客户数据。 这适用于客户端使用的任何设备 (如 Skype for business、outlook 和 outlook 网页版、移动客户端和 web 浏览器) 上的协议。

(默认情况下, 所有面向客户的服务器都将协商为 TLS 1.2, 但如果需要, 我们还支持根据较低的标准进行协商。)

## <a name="related-links"></a>相关链接

- [Azure 中的加密](office-365-azure-encryption.md)
- [用于加密的 BitLocker 和 Distributed Key Manager (DKM)](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Office 365 服务加密](office-365-service-encryption.md)
- [适用于 Skype for business、OneDrive for business、SharePoint online 和 Exchange online 的 Office 365 加密](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [传输中的数据的加密](office-365-encryption-for-data-in-transit.md)
- [客户管理的加密功能](office-365-customer-managed-encryption-features.md)
- [加密风险和保护](office-365-encryption-risks-and-protections.md)
- [Microsoft Dynamics 365 中的加密](office-365-encryption-in-microsoft-dynamics-365.md)