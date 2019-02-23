---
title: Exchange Online 中的邮件签名和加密的 S/MIME
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: S/MIME 允许您对电子邮件进行加密并对其进行数字签名。当您在电子邮件中使用 S/MIME 时, 将会帮助接收该邮件的人确信他们在 "收件箱" 中看到的内容与发件人启动的邮件完全一致。
ms.openlocfilehash: 41a84d5332092748f9a8cc8fe4936c39e5fd2012
ms.sourcegitcommit: 06d6e63225f912d0f3c6bb836c61eb11c1dbe97a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "30206505"
---
# <a name="smime-for-message-signing-and-encryption"></a>用于邮件签名和加密的 S/MIME

S/MIME (安全/多用途 Internet 邮件扩展) 是一种广泛接受的方法, 或更精确地发送经过数字签名和加密的邮件的协议。S/MIME 允许您对电子邮件进行加密并对其进行数字签名。当您在电子邮件中使用 S/MIME 时, 将会帮助接收该邮件的人确信他们在 "收件箱" 中看到的内容与发件人启动的邮件完全一致。它还将帮助接收邮件的用户确信邮件来自特定发件人, 而不是假装为发件人的人。为此, S/MIME 提供了加密安全服务, 例如身份验证、邮件完整性和源不可否认 (使用数字签名)。它还有助于加强电子邮件的隐私和数据安全 (使用加密)。有关电子邮件上下文中 S/mime 的历史记录和体系结构的更多完整背景, 请参阅[了解 S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)。 
  
作为管理员, 如果 exchange 2013 SP1 或 exchange Online (Office 365 的一部分) 中有邮箱, 则可以为您的组织启用基于 S/MIME 的安全性。使用此处链接的主题中的指南和 Exchange 命令行管理程序设置 S/MIME。若要在受支持的 Outlook 或 ActiveSync 版本中使用 S/MIME, 同时使用 exchange 2013 SP1 或 exchange Online, 组织中的用户必须为签名和加密目的颁发证书, 并将数据发布到本地 Active Directory域服务 (AD DS)。您的 AD DS 必须位于您控制的物理位置的计算机上, 而不是位于 internet 上某个位置的远程设施或基于云的服务中。有关 AD DS 的详细信息, 请参阅[Active Directory 域服务](https://go.microsoft.com/fwlink/?LinkID=394064)。
  
## <a name="supported-scenarios-and-technical-considerations"></a>支持的场景和技术考虑因素
<a name="sectionSection0"> </a>

可以将 S/MIME 设置为用于以下任一终结点： 
  
- Outlook 2010 或更高版本
    
- Web 上的 Outlook（以前称为 Outlook Web App）
    
- Exchange ActiveSync (EAS)
    
根据您选择的终结点，为这些终结点设置 S/MIME 时需遵循的步骤可能略有不同。通常情况下，您需要完成以下步骤：
  
- 安装基于 Windows 的证书颁发机构, 并设置公钥基础结构以颁发 S/MIME 证书。此外, 还支持第三方证书提供商颁发的证书。有关详细信息, 请参阅[Active Directory 证书服务概述](https://technet.microsoft.com/library/hh831740.aspx)。
    
- 在内部部署 AD DS 帐户的 UserSMIMECertificate 和/或 UserCertificate 属性中发布用户证书。
    
- 对于 Exchange Online 组织, 使用相应版本的 DirSync 将用户证书从 AD DS 同步到 Azure Active Directory。然后, 这些证书将从 Azure Active directory 同步到 Exchange Online 目录, 并将在将邮件加密给收件人时使用。
    
- 设置虚拟证书集合以验证 S/MIME。此信息由 Outlook 在验证电子邮件的签名并确保它是由受信任的证书签名时在 web 上使用 (以前称为 Outlook 网页上的 outlook)。
    
- 将 Outlook 或 EAS 终结点设置为使用 S/MIME。 
    
## <a name="setup-smime-with-outlook-on-the-web"></a>设置 web 上的 Outlook 的 S/MIME
<a name="sectionSection1"> </a>

使用 web 上的 Outlook 为 Exchange Online 设置 S/MIME 涉及以下关键步骤:
  
1. [Configure S/MIME settings for Outlook on the web](configure-s-mime-settings-for-outlook-web-app.md)
    
2. [设置虚拟证书集合以验证 S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
    
3. [将用户证书同步到 Office 365 for S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)此步骤仅适用于 Exchange Online。 
    
## <a name="related-message-encryption-technologies"></a>相关邮件加密技术
<a name="sectionSection2"> </a>

随着邮件安全性变得更加重要, 管理员需要了解安全邮件的原则和概念。这种理解尤其重要, 因为存在越来越多的与保护相关的技术 (如 S/MIME) 已经推出。若要详细了解 s/MIME 以及它在电子邮件上下文中的工作方式, 请参阅[了解 s/mime](https://go.microsoft.com/fwlink/?LinkID=393948)。各种加密技术协同工作, 为静态和传输中的邮件提供保护。S/MIME 可以同时与以下技术一起使用, 但不依赖于它们:
  
> **传输层安全 (TLS)** 对电子邮件服务器之间的隧道或路由进行加密，以帮助阻止窥探和窃听。 
    
> **安全套接字层 (SSL)** 对电子邮件客户端和 Office 365 服务器之间的连接进行加密。 
    
> **BitLocker**将对数据中心中的硬盘驱动器上的数据进行加密, 以便在有人未经授权访问的情况下对其进行读取。 
    
### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME 与 Office 365 邮件加密对比

S/MIME 需要一个在企业到企业和企业到消费者的情形中经常使用的证书和发布基础结构。用户控制 S/MIME 中的加密密钥, 并可以选择是否对其发送的每封邮件使用它们。Outlook 等电子邮件程序搜索受信任的根证书颁发机构位置, 以对签名进行数字签名和验证。Office 365 邮件加密是一种基于策略的加密服务, 可由管理员而不是单个用户配置, 以加密发送给组织内部或外部的任何人的邮件。它是基于 Azure 权限管理 (RMS) 构建的在线服务, 不依赖公钥基础结构。Office 365 邮件加密还提供了其他功能, 例如, 使用组织品牌自定义邮件的功能。有关 office 365 邮件加密的详细信息, 请参阅[office 365 邮件加密](https://go.microsoft.com/fwlink/?LinkID=392525)。
  
## <a name="more-information"></a>详细信息
<a name="sectionSection3"> </a>

[Outlook 网页版](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)
  
[安全邮件 (2000)](https://technet.microsoft.com/en-us/library/cc962043.aspx)
  

