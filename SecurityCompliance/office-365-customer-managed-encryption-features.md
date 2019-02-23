---
title: Office 365 客户管理的加密功能
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '摘要: 了解 Microsoft Office 365 中的数据恢复能力。'
ms.openlocfilehash: 7c4817a2982733bc1d292117811cb21aa5278972
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216052"
---
# <a name="customer-managed-encryption-features-in-office-365"></a>Office 365 中的客户托管加密功能

通过 Microsoft 托管的 office 365 中的加密技术, office 365 也适用于您可以管理和配置的其他加密技术, 例如:
- [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)
- [安全多用途 Internet 邮件扩展](http://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)
- [Office 365 邮件加密](http://products.office.com/en-us/exchange/office-365-message-encryption)
- [与合作伙伴组织的安全邮件流](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

此外, 还可以在[Office 365 服务说明](https://technet.microsoft.com/en-us/library/office-365-service-descriptions.aspx)中找到有关这些技术的其他信息。

## <a name="azure-rights-management"></a>Azure Rights Management
[Azure 权限管理](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)(azure RMS) 是[Azure 信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)使用的保护技术。它使用加密、标识和授权策略来帮助保护您的文件和电子邮件跨多个平台和设备 (电话、平板电脑和电脑)。可以在组织内部和外部保护信息, 因为保护仍包含数据。Azure RMS 提供了对所有文件类型的持久保护, 保护了任何地方的文件, 支持企业到企业的协作以及各种 windows 和非 Windows 设备。Azure RMS 保护还可以扩充[数据丢失防护 (DLP) 策略](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)。有关哪些应用程序和服务可以从 azure 信息保护中使用 azure 权限管理服务的详细信息, 请参阅[应用程序如何支持 azure 权限管理服务](https://docs.microsoft.com/information-protection/understand-explore/applications-support)。

Azure RMS 与 office 365 集成在一起, 适用于所有 office 365 客户。若要将 Office 365 配置为使用 azure RMS, 请参阅[配置 IRM 以使用 azure 权限管理, 并在 SharePoint 管理中心中设置信息权限管理 (IRM)](https://technet.microsoft.com/en-us/library/dn151475(v=exchg.150).aspx)。如果您在本地 Active Directory (AD) rms 服务器上运行, 则还可以[将 IRM 配置为使用内部部署 AD RMS 服务器](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server), 但强烈建议您将其[迁移到 Azure RMS](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) , 以使用与其他用户的安全协作等新功能。企业.

使用 azure rms 保护客户数据时, azure rms 使用2048位 RSA 非对称密钥和 SHA-256 哈希算法进行完整性, 以对数据进行加密。Office 文档和电子邮件的对称密钥为 AES 128 位 (使用 PKCS # 7 填充的 CBC 模式)。对于受 azure rms 保护的每个文档或电子邮件, azure rms 都会创建一个 AES 密钥 ("内容密钥"), 并且该密钥嵌入在文档中, 并在文档的各个版本中保持。内容密钥受组织中的 RSA 密钥 ("Azure 信息保护租户密钥") 的保护, 作为文档中策略的一部分, 并且该策略也由文档的作者签名。此租户密钥对于组织受 Azure RMS 保护的所有文档和电子邮件来说是通用的, 如果组织使用的是由客户管理的租户密钥, 则此密钥只能由 azure 信息保护管理员更改。有关 azure rms 使用的加密控件的详细信息, 请参阅[azure rms 的工作原理是什么？在盖子的下方](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work)。

在默认的 Azure RMS 实施中, Microsoft 生成并管理每个租户特有的根密钥。客户可以使用称为 "[引入自己的密钥" (BYOK)](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)的密钥管理方法在 azure RMS 中管理其根密钥的根密钥生命周期, 允许您在本地 hsm 中生成密钥, 并在此之后控制此项。转移到 Microsoft 的 FIPS 140-2 级别2验证的 hsm。不向任何人员授予对根密钥的访问权限, 因为无法从硬件安全模块中导出或提取键。此外, 您还可以访问几乎实时日志, 以显示对根项的所有访问权限。有关详细信息, 请参阅[日志记录和分析 Azure 权限管理用法](https://docs.microsoft.com/azure/information-protection/log-analyze-usage)。

Azure 权限管理可帮助缓解各种威胁, 如点击式攻击、中间人攻击、数据失窃以及组织共享策略的意外冲突。同时, 如果未经授权的用户不具有适当的权限, 则无法通过这些数据在传输中或在 rest 上进行任何 unwarranted 访问, 从而可以降低该数据在错误的手中发生的风险。有意或无意中提供数据丢失防护函数。如果用作 azure 信息保护的一部分, 则 Azure RMS 还提供数据分类和标记功能、标记内容、文档访问跟踪和访问吊销功能。若要了解有关这些功能的详细信息, 请参阅 azure[信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)、 [azure 信息保护部署路线图](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)和[azure 信息保护的快速入门教程](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial)。

## <a name="secure-multipurpose-internet-mail-extension"></a>安全多用途 Internet 邮件扩展
安全/多用途 Internet 邮件扩展 (S/MIME) 是公共密钥加密和 MIME 数据的数字签名的标准。S/MIME 在 rfc 3369、3370、3850、3851和其他中进行了定义。它允许用户对电子邮件进行加密并对电子邮件进行数字签名。使用 S/MIME 加密的电子邮件只能通过电子邮件的收件人使用其专用密钥 (仅对该收件人可用) 进行解密。因此, 电子邮件不能由除电子邮件收件人以外的任何人解密。

[Microsoft 支持 Office 365 中的 S/MIME](http://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)。公用证书将分发给客户的本地 Active Directory, 并存储在可复制到 Office 365 租户的属性中。与公钥对应的私钥将保留在本地, 并且永远不会传输到 Office 365。用户可以使用 outlook、outlook 网页和 Exchange ActiveSync 客户端对组织中的两个用户之间的电子邮件进行撰写、加密、解密、读取和数字签名。有关详细信息, 请参阅[现在 Office 365 中的 S/MIME 加密](http://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/)。

## <a name="office-365-message-encryption"></a>Office 365 邮件加密
[Office 365 邮件加密](https://products.office.com/en-us/exchange/office-365-message-encryption)(OME) 构建在[Azure 信息保护](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)基础之上 (AIP) 使您能够向任何人发送加密和受权限保护的邮件。OME 可缓解诸如网络点击和中间人攻击的威胁, 以及其他威胁, 如不具有适当权限的未经授权用户对数据的 unwarranted 访问。我们已使你为你提供了基于 Azure 信息保护基础构建的更简单、更直观的安全电子邮件体验。您可以保护从 Office 365 发送给组织内部或外部的任何人的邮件。可以使用任何标识 (包括 Azure Active Directory、Microsoft 帐户和 Google id) 跨一组不同的邮件客户端查看这些邮件。有关贵组织如何使用加密邮件的详细信息, 请参阅[Office 365 邮件加密](https://support.office.com/article/F87CB016-7876-4317-AE3C-9169B311FF8A)。

## <a name="transport-layer-security"></a>传输层安全性
如果要确保与合作伙伴之间进行安全通信, 可以使用入站和出站连接器来提供安全性和邮件完整性。您可以使用证书配置每个连接器上的强制入站和出站 TLS。使用加密的 SMTP 通道可防止通过中间人攻击窃取数据。有关详细信息, 请参阅[Exchange Online 如何使用 TLS 保护电子邮件连接](https://support.office.com/article/How-Exchange-Online-uses-TLS-to-secure-email-connections-in-Office-365-4CDE0CDA-3430-4DC0-B489-F2C0736C929F)。

## <a name="domain-keys-identified-mail"></a>域密钥识别邮件
exchange online Protection (EOP) 和 exchange online 支持对域密钥标识邮件 (DKIM) 邮件进行入站验证。DKIM 是一种方法, 用于验证邮件是否已从其发出的域发送, 以及其他人未被别人盗用。它将电子邮件与负责发送电子邮件的组织联系在一起, 并且是电子邮件加密的较大范例的一部分。有关此范例的三个部分的详细信息, 请参阅:
- [在 Office 365 中设置 SPF 以防止欺骗](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)
- [使用 DKIM 在 Office 365 中验证从自定义域发送的出站电子邮件](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)
- [使用 DMARC 验证 Office 365 中的电子邮件](https://https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
