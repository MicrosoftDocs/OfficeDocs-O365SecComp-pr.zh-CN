---
title: 邮件签名和加密的 S/MIME
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/9/2016
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 可以使用 S/MIME 加密电子邮件，并对它们进行数字签名。当您使用 S/MIME 与电子邮件时，它有助于收到该消息以确认他们在其收件箱中看到的内容是确切入门发件人的消息的人员。
ms.openlocfilehash: 3ce95132476417df8949cdc12f2d825047f6b76d
ms.sourcegitcommit: 22bca85c3c6d946083d3784f72e886c068d49f4a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2018
ms.locfileid: "22027589"
---
# <a name="smime-for-message-signing-and-encryption"></a>邮件签名和加密的 S/MIME

S/MIME （安全/多用途 Internet 邮件扩展） 是被广泛接受的方法，或更精确地协议，用于发送数字签名和加密邮件。可以使用 S/MIME 加密电子邮件，并对它们进行数字签名。当您使用 S/MIME 与电子邮件时，它有助于收到该消息以确认他们在其收件箱中看到的内容是确切入门发件人的消息的人员。它还将的邮件来自特定发件人而不是从某人伪装发件人帮助接收消息为特定的人员。若要执行此操作，S/MIME 提供加密的安全服务，如身份验证、 消息完整性和不可否认性的原点而言的 （使用数字签名）。它还有助于提高隐私和数据安全性 （使用加密） 的电子邮件。有关的历史记录和电子邮件的上下文中的 S/MIME 的体系结构的更完整背景，请参阅[Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)。 
  
作为管理员，您可以为组织启用基于 S/MIME 的安全如果您具有邮箱的 Exchange 2013 SP1 或 Exchange Online，Office 365 的一部分。使用主题中的指南以及 Exchange Management Shell，以设置 S/MIME 此处链接。若要使用 S/MIME 中受支持版本的 Outlook 或 ActiveSync，与 Exchange 2013 SP1 或 Exchange Online 中，您的组织中的用户必须为了签名和加密颁发的证书和发布到您的本地 Active Directory 数据域服务 (AD DS)。AD DS 必须位于您控制物理位置而不是在远程设施或 internet 上某个位置的基于云的服务的计算机上。有关 AD DS 的详细信息，请参阅[Active Directory 域服务](https://go.microsoft.com/fwlink/?LinkID=394064)。
  
## <a name="supported-scenarios-and-technical-considerations"></a>支持的场景和技术考虑因素
<a name="sectionSection0"> </a>

如果您的组织使用 Exchange 2013 SP1 或 Exchange Online，您可以设置 S/MIME 若要使用任何以下端点： 
  
- Outlook 2010
    
- Outlook 2013
    
- Outlook Web App
    
- Exchange ActiveSync (EAS)
    
根据您选择的终结点，为这些终结点设置 S/MIME 时需遵循的步骤可能略有不同。通常情况下，您需要完成以下步骤：
  
- 安装基于 Windows 的证书颁发机构和公钥基础结构设置为颁发 S/MIME 证书。此外支持第三方证书提供程序颁发的证书。有关详细信息，请参阅[Active Directory 证书服务概述](https://technet.microsoft.com/library/hh831740.aspx)。
    
- 在内部部署 AD DS 帐户的 UserSMIMECertificate 和/或 UserCertificate 属性中发布用户证书。
    
- 对于 Exchange Online 组织，使用目录同步的适当版本同步到 Azure Active Directory 用户证书从 AD DS。这些证书将然后获取从 Azure Active Directory 同步到 Exchange Online 目录，并将加密发送给收件人的邮件时使用。
    
- 设置虚拟证书集合以验证 S/MIME。此信息供 OWA 用于验证电子邮件的前面并确保它是由可信证书签名的。
    
- 将 Outlook 或 EAS 终结点设置为使用 S/MIME。 
    
## <a name="setup-smime-with-outlook-web-app"></a>将 S/MIME 设置为用于 Outlook Web App
<a name="sectionSection1"> </a>

Exchange 2013 SP1 或 Exchange Online 与 Outlook Web App 的 S/MIME 设置涉及以下关键步骤：
  
1. [配置 Outlook Web App 的 S/MIME 设置](configure-s-mime-settings-for-outlook-web-app.md)
    
2. [设置虚拟证书集合以验证 S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
    
3. [用户证书同步到 Office 365 for S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)此步骤仅适用于 Exchange Online。 
    
## <a name="related-message-encryption-technologies"></a>相关邮件加密技术
<a name="sectionSection2"> </a>

为邮件安全变得更为重要，管理员需要了解的原则和安全消息的概念。了解尤其重要，这是不断增长各种保护相关技术，如 S/MIME 的已损坏可用的。若要了解有关 S/MIME 和电子邮件的上下文中的工作方式的详细信息，请参阅[Understanding S/MIME](https://go.microsoft.com/fwlink/?LinkID=393948)。加密技术各种一起提供的 rest 和传输过程中的邮件保护。S/MIME 与下列技术可同时进行工作，但不依赖于这些：
  
> **传输层安全 (TLS)** 对电子邮件服务器之间的隧道或路由进行加密，以帮助阻止窥探和窃听。 
    
> **安全套接字层 (SSL)** 对电子邮件客户端和 Office 365 服务器之间的连接进行加密。 
    
> **BitLocker**对数据中心中硬盘驱动器上的数据进行加密，以便如果某人获取未经授权的访问，他们无法读取。 
    
### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME 与 Office 365 邮件加密对比

S/MIME 需要通常用于在企业到企业和企业客户的情况下一个证书和发布基础结构。用户控制 S/mime 加密密钥，并可以选择是否将其用于发送每条消息。如 Outlook 电子邮件程序搜索执行数字签名和验证签名的受信任的根证书颁发机构位置。Office 365 邮件加密是管理员，并不是单个用户加密邮件发送给内部或外部组织的任何人都可以配置一基于策略的加密服务。它是内置 Azure 权限管理 (RMS)，不依赖于公钥基础结构的联机服务。Office 365 邮件加密还提供其他功能，例如自定义品牌的组织的邮件的功能。有关 Office 365 邮件加密的详细信息，请参阅[Office 365 邮件加密](https://go.microsoft.com/fwlink/?LinkID=392525)。
  
## <a name="more-information"></a>详细信息
<a name="sectionSection3"> </a>

[Outlook Web App](http://technet.microsoft.com/library/3814b665-01e8-4881-9a44-163f14789ee4.aspx)
  
[安全邮件 (2000)](https://technet.microsoft.com/en-us/library/cc962043.aspx)
  

