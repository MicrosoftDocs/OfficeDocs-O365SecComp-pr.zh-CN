---
title: Office 365 中的加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/3/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
description: 与 Office 365 中，在 rest 和在传输过程中，使用最强的加密、 协议和技术，您的内容进行加密。获取 Office 365 中的加密的概述。
ms.openlocfilehash: 5f64d6e758818d410f54370adee549f565d4f042
ms.sourcegitcommit: efccf5b4f22d34a9674bc55ebf3d88bc8bda2972
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "29995103"
---
# <a name="encryption-in-office-365"></a>Office 365 中的加密

加密文件保护和信息保护策略的重要组成部分。阅读这篇文章，获取概述用于所有版本的 Office 365 的加密并获得帮助加密任务设置为您的组织使用密码保护的 Office 文档的加密。
  
- 如果您正在寻找有关证书和 TLS 技术信息，请参阅[Office 365 中的加密技术参考信息](technical-reference-details-about-encryption.md)。
    
- 如果您要查找有关如何配置或设置为您的组织的加密的信息，请参阅[Office 365 企业版中的加密设置](set-up-encryption.md)。
    
## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>什么是加密，以及它如何在 Office 365 中？

在高级别，加密是为不能由用户或计算机，直到解密密码文本的暗文编码数据 （称为纯文本） 的过程。解密需要仅限授权的用户具有的加密密钥。加密有助于确保只有授权的收件人可以解密您的内容，例如电子邮件和文件。
  
加密本身不阻止内容，如文件、 电子邮件、 日历项和等等，错误手中。加密属于您的组织的较大的信息保护策略。通过使用加密，您可以帮助确保只有应该能够使用加密的数据的用户能够。
  
您可以同时具有现成的加密的多个图层。例如，您可以加密电子邮件以及通过其电子邮件流的通信通道。与 Office 365 进行加密数据，在 rest 和在传输过程中，使用多个强的加密协议和技术，包括传输层安全性/安全套接字层 (TLS/SSL)、 Internet 协议安全性 (IPSec) 和高级加密标准 (AES)。
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>静态数据和在传输过程中的数据的加密

 **静态数据的示例**包括已上载到 SharePoint 库、 Project Online 数据、 业务会议、 电子邮件和附件存储在 Office 365 中的文件夹的 Skype 中已上载的文档的文件邮箱，并上载到 OneDrive for Business 的文件。 
  
 **在传输过程中的数据的示例**包括正在发送的邮件或正在联机会议中的进行的对话。在 Office 365 数据在传输过程中是，只要用户设备进行通信与 Office 365 服务器，或者当 Office 365 服务器与另一台服务器的。 
  
使用 Office 365 中，可以有多个图层和的协作要保护数据的加密类型。下表包含一些示例，并提供其他信息的链接。
  
|**种类的内容**|**加密技术**|**若要了解更多的资源**|
|:-----|:-----|:-----|
|在设备上的文件。这可能包括保存在文件夹、 保存计算机、 平板电脑或电话上的 Office 文档或数据保存到 Microsoft 云的电子邮件。  <br/> |在 Microsoft 数据中心中的 BitLocker。此外可以在客户端计算机，如 Windows 计算机和平板电脑上使用 BitLocker  <br/> 在 Microsoft 数据中心中的分布式密钥管理器 (DKM)  <br/> Office 365 的客户参数  <br/> |[Windows IT 中心： BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Microsoft 信任中心： 加密](https://www.microsoft.com/en-us/TrustCenter/Security/Encryption) <br/> [云安全控制系列： 在 Rest 加密的数据](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Exchange Online 如何进行电子邮件保密](exchange-online-secures-email-secrets.md) <br/> [使用客户密钥控制 Office 365 中的数据](controlling-your-data-using-customer-key.md) <br/> |
|在用户之间传输的文件。这可能包括 Office 文档或用户之间共享的 SharePoint 列表项。  <br/> |在传输过程中的文件的 TLS  <br/> |[OneDrive for Business 和 SharePoint Online 中的数据加密](data-encryption-in-odb-and-spo.md) <br/> [Skype for Business Online： 安全性和存档](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|电子邮件收件人之间传输。这包括承载的 Exchange Online 电子邮件。  <br/> |与 Azure 权限管理、 S/MIME 和 TLS 为电子邮件在传输过程中的 office 365 邮件加密  <br/> |[Office 365 邮件加密 (OME)](ome.md) <br/> [Office 365 中的电子邮件加密](email-encryption.md) <br/> [Exchange Online 如何使用 TLS 保护 Office 365 中的电子邮件连接](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
   
## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>如果需要更多控制通过加密，以满足安全性和合规性要求？

除了批量加密、 文件加密和 Office 365 中的邮箱加密的 Microsoft 托管解决方案，客户托管选项可用于满足更严格的安全性和合规性要求。此类解决方案使用与 Office 365 的 Azure 权限管理 (Azure RMS)。
  
请参阅以下资源，以了解详细信息：
  
- [什么是 Azure 权限管理？](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
    
- [激活 Office 365 管理中心的权限管理](https://support.office.com/article/5b6d3ac7-b1ac-428e-b03e-50e882f85a6e)
    
- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)
    
## <a name="how-do-i"></a>如何实现...

|**若要此任务**|**请参阅以下资源**|
|:-----|:-----|
|设置我的组织的加密  <br/> |[设置 Office 365 企业版中的加密](set-up-encryption.md) <br/> |
|Office 365 中查看有关证书、 技术和 TLS 加密套件的详细信息  <br/> |[有关 Office 365 中的加密技术详细信息](technical-reference-details-about-encryption.md) <br/> |
|在移动设备上处理加密邮件  <br/> |[在 Android 设备上查看加密的邮件](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [在 iPhone 或 iPad 上查看加密的邮件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|加密使用密码保护的文档  <br/><br/>  目前，在 Office Online 不支持密码保护。使用桌面版本的 Word、 Excel 和 PowerPoint 进行密码保护。           |[您的文档、 工作簿或演示文稿中添加或删除保护](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)（选择**添加 protection**内容中，，然后查看**用密码进行加密**）  <br/> |
|从文档中删除加密  <br/> |[您的文档、 工作簿或演示文稿中添加或删除保护](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826)（选择**删除保护**部分中，并随后看到**删除密码加密**）  <br/> |
   
## <a name="related-topics"></a>相关主题

[规划 Office 365 的安全性和信息保护功能](https://support.office.com/article/3d4ac4a1-3920-4ff9-918f-011f3ce60408)
  
[安全性和业务-管理帮助的 Office 365 中的合规性](https://support.office.com/article/7fe448f7-49bd-4d3e-919d-0a6d1cf675bb)
  

