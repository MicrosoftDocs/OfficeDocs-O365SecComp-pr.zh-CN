---
title: Office 365 中的加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/3/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: 使用 Office 365, 你的内容将在静态和传输过程中使用最强的加密、协议和技术进行加密。获取 Office 365 中的加密概述。
ms.openlocfilehash: 7099609ca142f6ed094ccafc95aab48059a1aa36
ms.sourcegitcommit: 7adfd8eda038cf25449bdf3df78b5e2fcc1999e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "30357503"
---
# <a name="encryption-in-office-365"></a>Office 365 中的加密

加密是文件保护和信息保护策略的重要组成部分。阅读本文, 了解对 office 365 的所有版本使用的加密的概述, 并获取加密任务的帮助, 从为组织设置加密以对 office 文档进行密码保护。
  
- 如果你要查找有关 TLS 等证书和技术的信息, 请参阅[Office 365 中有关加密的技术参考详细信息](technical-reference-details-about-encryption.md)。

- 如果你正在查找有关如何为组织配置或设置加密的信息, 请参阅[在 Office 365 企业版中设置加密](set-up-encryption.md)。

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>什么是加密, 它在 Office 365 中的工作原理是什么？

从较高的层次来看, 加密是将数据编码 (称为纯文本) 到密文的过程, 除非在密码文本解密之后, 用户或计算机才能使用。解密需要仅授权用户拥有的加密密钥。加密有助于确保只有经过授权的收件人才能解密您的内容, 如电子邮件和文件。
  
加密本身并不会阻止内容 (如文件、电子邮件、日历条目等) 落入错误的手中。加密是组织的更大的信息保护策略的一部分。通过使用加密, 可以帮助确保只有那些应能够使用加密数据的用户才能够使用。
  
可以同时进行多层加密。例如, 您可以对电子邮件进行加密, 也可以对通过其发送电子邮件流的通信通道进行加密。使用 Office 365, 您的数据在静态和传输过程中进行加密, 使用多个强加密协议, 以及包含传输层安全性/安全套接字层 (TLS/SSL)、Internet 协议安全性 (IPSec) 和高级加密的技术Standard (AES)。
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>静态数据的加密和传输中的数据

 **rest 中的数据示例**包括已上传到 SharePoint 库的文件、Project Online 数据、已在 Skype for business 会议中上载的文档、电子邮件和存储在 Office 365 中的文件夹中的附件邮箱, 以及上传到 OneDrive for business 的文件。 
  
 **传输中的数据示例**包括正在传递的邮件或联机会议中正在进行的对话。在 office 365 中, 只要用户的设备与 office 365 服务器通信, 或当 Office 365 服务器与另一台服务器通信时, 数据就会被传输。 
  
使用 Office 365, 可以有多个层和加密类型协同工作来保护您的数据。下表包括一些示例, 并提供了指向其他信息的链接。
  
|**内容的种类**|**加密技术**|**要了解详细信息的资源**|
|:-----|:-----|:-----|
|设备上的文件。这可能包括保存在文件夹中的电子邮件、保存在计算机上的 Office 文档、平板电脑或电话或保存到 Microsoft 云的数据。  <br/> |Microsoft 数据中心中的 BitLocker。BitLocker 也可用于客户端计算机, 如 Windows 计算机和平板电脑  <br/> Microsoft 数据中心内的分布式密钥管理器 (DKM)  <br/> 适用于 Office 365 的客户密钥  <br/> |[Windows IT 中心: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft 信任中心: 加密](https://www.microsoft.com/en-us/TrustCenter/Security/Encryption) <br/> [云安全性控制系列: 静态数据加密](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online 如何进行电子邮件保密](exchange-online-secures-email-secrets.md) <br/> [使用客户密钥控制 Office 365 中的数据](controlling-your-data-using-customer-key.md) <br/> |
|用户之间传输的文件。这可能包括在用户之间共享的 Office 文档或 SharePoint 列表项。  <br/> |传输中的文件的 TLS  <br/> |[OneDrive for Business 和 SharePoint Online 中的数据加密](data-encryption-in-odb-and-spo.md) <br/> [Skype for business Online: 安全性和存档](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|在收件人之间传输电子邮件。这包括 Exchange Online 托管的电子邮件。  <br/> |Office 365 在传输过程中电子邮件的 Azure 权限管理、S/MIME 和 TLS 的邮件加密  <br/> |[Office 365 邮件加密 (OME)](ome.md) <br/> [Office 365 中的电子邮件加密](email-encryption.md) <br/> [Exchange Online 如何使用 TLS 保护 Office 365 中的电子邮件连接](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>如果需要更多控制加密以满足安全性和合规性要求, 该怎么办？

除了 Microsoft 托管的批量加密、文件加密和邮箱加密的解决方案, 在 Office 365 中, 客户管理的选项可用于满足更严格的安全性和合规性要求。此类解决方案将 Azure 权限管理 (azure RMS) 与 Office 365 结合使用。
  
若要了解详细信息, 请参阅以下资源:
  
- [什么是 Azure 权限管理？](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [激活 Office 365 管理中心的权限管理](https://support.office.com/article/5b6d3ac7-b1ac-428e-b03e-50e882f85a6e)

- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)

## <a name="how-do-i"></a>如何实现 .。。

|**执行此任务**|**查看这些资源**|
|:-----|:-----|
|为我的组织设置加密  <br/> |[设置 Office 365 企业版中的加密](set-up-encryption.md) <br/> |
|查看有关 Office 365 中的证书、技术和 TLS 密码套件的详细信息  <br/> |[有关 Office 365 中的加密技术的详细信息](technical-reference-details-about-encryption.md) <br/> |
|在移动设备上处理加密邮件  <br/> |[在 Android 设备上查看加密邮件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [查看 iPhone 或 iPad 上的加密邮件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|使用密码保护对文档进行加密  <br/><br/>  目前, Office Online 不支持密码保护。使用适用于密码保护的 Word、Excel 和 PowerPoint 的桌面版本。           |[在文档、工作簿或演示文稿中添加或删除保护](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)(选择 "**添加保护**" 部分, 然后查看 "**使用密码进行加密**")  <br/> |
|从文档中删除加密  <br/> |[在文档、工作簿或演示文稿中添加或删除保护](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)(选择 "**删除保护**" 部分, 然后参阅 "**删除密码加密**")  <br/> |

## <a name="related-topics"></a>相关主题

[规划 Office 365 安全和信息保护功能](https://support.office.com/article/3d4ac4a1-3920-4ff9-918f-011f3ce60408)
  
[Office 365 for business 中的安全性和合规性-管理员帮助](https://support.office.com/article/7fe448f7-49bd-4d3e-919d-0a6d1cf675bb)
  

