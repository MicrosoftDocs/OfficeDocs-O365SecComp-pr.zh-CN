---
title: Office 365 客户托管加密功能
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
ms.openlocfilehash: e835587e07246154cd700555cc7263370bde8755
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22524814"
---
# <a name="customer-managed-encryption-features-in-office-365"></a>Office 365 中的客户托管加密功能

由 Microsoft 托管的 Office 365 中的加密技术，以及 Office 365 还适用于额外的加密技术，您可以管理和配置，如：
- [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)
- [安全多用途 Internet 邮件扩展](http://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)
- [Office 365 邮件加密](http://products.office.com/en-us/exchange/office-365-message-encryption)
- [使用合作伙伴组织的安全邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

此外可以[Office 365 服务说明](https://technet.microsoft.com/en-us/library/office-365-service-descriptions.aspx)中找到这些技术的其他信息。

## <a name="azure-rights-management"></a>Azure Rights Management
[Azure 权限管理](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)使用[Azure 信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)保护技术 (azure RMS)。它使用加密、 标识和授权策略来帮助保护您的文件以及跨多个平台和设备电子邮件 — 电话、 平板电脑和 pc 信息可以保护您的组织内外因为保护保持与数据。Azure RMS 提供的所有文件类型的持久保护、 保护文件无处不支持向企业协作和范围的 Windows 和非 Windows 设备。Azure RMS 保护还可以增大[数据丢失防护 (DLP) 策略](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。有关哪些应用程序和服务可以使用从 Azure 信息保护 Azure 权限管理服务的详细信息，请参阅[如何应用程序支持的 Azure 权限管理服务](https://docs.microsoft.com/information-protection/understand-explore/applications-support)。

Azure RMS 是与 Office 365 集成的和适用于所有的 Office 365 客户。若要配置为使用 Azure RMS 的 Office 365，请参阅[配置 IRM 以使用 Azure 权限管理和组设置 SharePoint 管理中心中的信息权限管理 (IRM)](https://technet.microsoft.com/en-us/library/dn151475(v=exchg.150).aspx)。如果在本地 Active Directory (AD) RMS 服务器的运行，则还可以[IRM 配置为使用内部部署 AD RMS 服务器](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)，但强烈建议您为[迁移到 Azure RMS](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms)使用与其他新功能，如安全协作组织。

保护客户数据与 Azure RMS 时，Azure RMS 会使用与 160、SHA 256 哈希算法的完整性 2048年位的 RSA 非对称密钥对数据进行加密。对称密钥的 Office 文档和电子邮件是 AES 128 位 （PKCS #7 填充 CBC 模式）。对于每个文档或由 Azure RMS 保护的电子邮件，Azure RMS 创建单个 AES 密钥 （在"内容"），和该键嵌入在文档中，通过版本的文档保留。组织的 RSA 密钥 （"Azure 信息保护租户密钥"） 文档中的策略的一部分受保护的内容项，并且该策略也签名文档的作者。此租户密钥是通用于所有文档和受 Azure RMS 组织的电子邮件，如果组织正在使用的是客户托管的租户密钥此项可仅由 Azure 信息保护管理员进行更改。有关使用 Azure RMS 加密控件的详细信息请参阅[Azure RMS 如何工作？幕后故事](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work)。

在默认 Azure RMS 实现中，Microsoft 生成并管理根密钥都是唯一的每个租户。客户可以通过使用调用[使您自己键 (BYOK)](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)的密钥管理方法管理使用 Azure 键仓库 Services Azure RMS 中其根密钥的生命周期），允许您在内部部署 Hsm 中生成您的密钥和位于此项之后的控件转接到 Microsoft 的 FIPS 140 2 级别 2 验证 Hsm。 访问根密钥不授予任何人员无法导出或从其保护硬件安全模块中提取的注册表项。此外，您可以访问任何时候显示所有访问根密钥的 near 实时日志。有关详细信息，请参阅[日志记录和分析 Azure 权限管理使用率](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)。

Azure 权限管理有助于缓解如 wire-tapping、 中间中中间人攻击、 数据窃取和无意冲突的组织的共享策略的威胁。同时，任何毫无根据的访问的客户数据传输过程中或在未经授权的用户不具备的 rest 适当的权限阻止通过按照数据，从而减轻通话质量在所在正确的数据的风险手之一的策略有意或无意出现并提供数据丢失防护函数。如果使用 Azure 信息保护的一部分，Azure RMS 还提供了数据分类和标记功能、 内容标记、 文档访问跟踪和访问吊销功能。若要了解有关这些功能，请参阅[什么是 Azure 信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)、 [Azure 信息保护部署路线图](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)和[Azure 信息保护的快速入门教程](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)。

## <a name="secure-multipurpose-internet-mail-extension"></a>安全多用途 Internet 邮件扩展
安全/多用途 Internet 邮件扩展 (S/MIME) 是一种标准的公钥加密和数字签名的 MIME 数据。S/MIME 中定义 Rfc 3369 3370，3850、 3851，和其他内容。它允许用户加密电子邮件和数字签名的电子邮件。只能使用其私钥仅可供该收件人的电子邮件的收件人解密使用 S/MIME 加密的电子邮件。此类由以外的电子邮件的收件人的任何人都无法解密电子邮件。

[Microsoft 支持 Office 365 中的 S/MIME](http://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)。公共证书是分配给客户的内部部署 Active Directory 以及存储在可以复制到 Office 365 租户的属性。对应于公钥的私钥保持内部部署，并且永远不会传输到 Office 365。用户可以撰写、 加密、 解密、 读取和数字签名的组织使用 Outlook web 和 Exchange ActiveSync 客户端上的 Outlook 中的两个用户之间的电子邮件。有关详细信息，请参阅[现在在 Office 365 中的 S/MIME 加密](http://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)。

## <a name="office-365-message-encryption"></a>Office 365 邮件加密
[Office 365 邮件加密](https://products.office.com/en-us/exchange/office-365-message-encryption)(OME) 构建在[Azure 信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)(AIP) 使您发送加密和受权限保护的任何人的邮件。OME 缓解如 wire-tapping 和中间中中间人攻击威胁和其他威胁，如毫无根据访问的数据未经授权的用户不具有适当权限。我们已为您提供更简单、 更直观、 安全电子邮件体验构建到 Azure 信息保护顶部的投资。您可以保护您的组织内外的任何人都从 Office 365 发送邮件。可以在一组不同的邮件客户端使用任何身份，包括 Azure Active Directory、 Microsoft 帐户和 Google Id 查看这些消息。有关如何组织可以使用加密的邮件的详细信息，请参阅[Office 365 邮件加密](https://support.office.com/article/F87CB016-7876-4317-AE3C-9169B311FF8A)。

## <a name="transport-layer-security"></a>传输层安全性
如果您想要确保与合作伙伴的安全通信，您可以使用入站和出站连接器提供安全性和消息完整性。您可以配置强制的入站和出站 TLS 上每个连接器，使用证书。使用加密的 SMTP 通道可以防止数据被盗通过中间中中间人攻击。有关详细信息，请参阅[如何 Exchange Online 使用 TLS 安全电子邮件连接](https://support.office.com/article/How-Exchange-Online-uses-TLS-to-secure-email-connections-in-Office-365-4CDE0CDA-3430-4DC0-B489-F2C0736C929F)。

## <a name="domain-keys-identified-mail"></a>域键标识邮件
Exchange Online Protection (EOP) 和 Exchange Online 支持入站的验证域键标识邮件 (DKIM) 消息的数目。DKIM 验证从其显示它来源于域已发送邮件，并已不造假其他人的方法。它将联系到组织负责，发送一封电子邮件和电子邮件加密一大模式的一部分。有关此范例的三个部分的详细信息，请参阅：
- [在 Office 365 中设置 SPF 以防止欺骗](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)
- [使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)
- [使用 DMARC 验证 Office 365 中的电子邮件](https://https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
