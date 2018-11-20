---
title: 有关 Office 365 加密的技术参考详情
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/12/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Office 365 中查看有关加密技术详细信息。
ms.openlocfilehash: 69365b66479ab89a9c036fe489b4087d327460eb
ms.sourcegitcommit: e4ebef6aaf756eefb86c9f3a602cf75f5d344271
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26026519"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a>有关 Office 365 加密的技术参考详情

请参阅本文以了解有关证书、 技术和 TLS 用于[Office 365 中的加密](encryption.md)密码套件。本文还提供了有关计划弃用情况的详细信息。
  
- 如果您正在寻找概述信息，请参阅[Office 365 中的加密](encryption.md)。
    
- 如果您正在寻找安装信息，请参阅[Office 365 企业版中的加密设置](set-up-encryption.md)。
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 证书所有权和管理

无需为 Office 365 购买或维护证书，因为 Microsoft 使用其自己的证书。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>当前加密标准和计划弃用情况

若要继续提供最佳的 Office 365 加密，Microsoft 定期审查支持的加密标准。有时，我们需要弃用旧标准，如随即过期，因此不安全。本主题介绍有关规划弃用情况当前支持的密码套件和其他标准以及详细信息。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 支持的 TLS 版本

传输层安全性 (TLS) 和 TLS 之前的 SSL 都是一种加密协议，通过使用安全证书加密计算机之间的连接来保护网络通信的安全。Office 365 支持若干个 TLS 版本，其中包括：
  
- TLS 版本 1.2 (TLS 1.2)
    
- TLS 版本 1.1 (TLS 1.1)
    
- TLS 版本 1.0 (TLS 1.0)
    
 TLS 1.0 和 TLS 1.1 支持将被弃用 2018 年 10 月 31。有关详细信息，请参阅[Deprecating TLS 1.0 和 1.1 这意味着您的支持](technical-reference-details-about-encryption.md#TLS11and12deprecation)。 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>弃用的 TLS 1.0 和 1.1 这意味着您的支持
<a name="TLS11and12deprecation"> </a>

从年 10 月 31 2018 TLS 1.0 和 1.1 将不再支持 Office 365。这意味着，Microsoft 将无法修复的客户端、 设备或使用 TLS 1.0 和 1.1 连接到 Office 365 服务中找到新问题。

请注意这并不意味着 Office 365 将阻止 TLS 1.0 和 1.1 连接。禁用或删除 TLS 1.0 和 1.1 TLS 服务的客户连接中没有官方日期。最终否决日期将由客户遥测和还不知道。决定是后，将会通知六个月提前除非我们意识到已知威胁，在这种情况下，我们可能需要操作在小于六个月，以保护客户使用的服务。

您应确保所有客户端-服务器和服务器浏览器的组合使用 TLS 1.2 （或更高版本） 以保持连接到 Office 365 服务。您可能需要更新某些客户端-服务器和服务器浏览器的组合。有关如何影响您的信息，请参阅[强制使用 TLS 1.2 Office 365 中的 Preparing](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365)。
  
## <a name="deprecating-support-for-3des"></a>弃用支持 3DES
<a name="TLS11and12deprecation"> </a>

从年 10 月 31 2018 Office 365 将不再到 Office 365 的通信中支持 3DES 加密套件的使用。更具体地说，Office 365 将不再支持 TLS_RSA_WITH_3DES_EDE_CBC_SHA 密码套件。本主题中列出的客户端和服务器与 O365 后此日期必须支持至少一个更安全的密码 （请参阅[TLS 密码支持 Office 365 套件](technical-reference-details-about-encryption.md#TLSCipherSuites)）。
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>在 Office 365 中弃用 SHA-1 证书支持
<a name="TLS11and12deprecation"> </a>

6 月 2016，从 Office 365 不再接受 sha-1 证书对出站或入站连接。如果您是当前正在使用证书与 sha-1 证书链中，您将需要更新链使用 160、SHA-2 (安全哈希算法 2) 还是更强的哈希算法。
  
## <a name="deprecating-rc4-support-in-office-365"></a>在 Office 365 中弃用 RC4 支持
<a name="TLS11and12deprecation"> </a>

2015 年 7 月已停止对以下 RC4 密码套件的支持：
  
- TLS_RSA_WITH_RC4_128_SHA
    
- TLS_RSA_WITH_RC4_128_MD5
    
## <a name="deprecating-secure-sockets-layer-ssl-30-support-in-office-365"></a>弃用 Office 365 中的安全套接字层 (SSL) 3.0 支持
<a name="TLS11and12deprecation"> </a>

启动 2014 年 12 月 1 日，Office 365 开始禁用支持的安全套接字层 (SSL) 3.0，TLS 前置任务。有关详细信息，请参阅[Security 顾问 3009008](https://technet.microsoft.com/library/security/3009008.aspx)。有关说明如何确保客户端使用 TLS 1.0 或更高版本，并禁用 SSL 3.0，请参阅[保护 SSL 3.0 漏洞](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/)。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 支持 TLS 加密套件
<a name="TLSCipherSuites"> </a>

密码套件是 TLS 用于建立安全连接的加密算法集合。Office 365 支持的密码套件按强度顺序从最强的密码套件开始依次在下表列出。当 Office 365 收到一个连接请求时，Office 365 首先会尝试使用最上面的密码套件进行连接，如果不成功，则会尝试使用列表中的第二个密码套件，以此类推。当 Office 365 发送连接请求至其他服务器或客户端时，由接收服务器或客户端决定是选择密码套件还是使用 TLS。
  
|**协议**|**密码套件名称**|**密钥交换算法/强度**|**完全向前保密支持**|**身份验证算法/强度**|**密码/强度**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_3DES_EDE_CBC_SHA  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |3DES/192  <br/> |
   
## <a name="related-topics"></a>相关主题
<a name="TLSCipherSuites"> </a>

[Office 365 中的加密](encryption.md)
  
[设置 Office 365 企业版中的加密](set-up-encryption.md)
  
[Windows 安全状态更新中的 TLS 1.0 的 Schannel 实现： 2015 年 11 月 24 日](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL 加密增强功能 (Windows IT 中心)](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

