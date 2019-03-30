---
title: 有关 Office 365 加密的技术参考详情
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 03/29/2019
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: 查看有关 Office 365 中的 encyption 的技术详细信息。
ms.openlocfilehash: afe077fdedb3e01e5658d27a13e17ae3a3ab5929
ms.sourcegitcommit: 1261a37c414111f869df5791548a768d853fda60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/30/2019
ms.locfileid: "31004249"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a>有关 Office 365 加密的技术参考详情

请参阅本文, 了解用于[Office 365 中用于加密](encryption.md)的证书、技术和 TLS 密码套件。 此外, 本文还提供有关计划的 deprecations 的详细信息。
  
- 如果你正在寻找概述信息, 请参阅[Office 365 中的加密](encryption.md)。
- 如果你正在寻找安装程序信息, 请参阅[在 Office 365 企业版中设置加密](set-up-encryption.md)。
- 有关 Windows 特定版本支持的密码套件的信息, 请参阅[TLS/SSL 中的密码套件 (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)。
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Microsoft Office 365 证书所有权和管理

无需为 Office 365 购买或维护证书，因为 Microsoft 使用其自己的证书。
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>当前加密标准和计划的 deprecations

为了继续为 Office 365 提供一流的加密, Microsoft 会定期审查受支持的加密标准。 有时, 我们需要弃用旧的标准, 因为它们已过期, 因此安全性较低。 本主题介绍当前支持的密码套件和其他标准以及有关计划的 deprecations 的详细信息。 

## <a name="fips-compliance-for-office-365"></a>适用于 Office 365 的 FIPS 合规性
Office 365 支持的所有密码套件使用 FIPS 140-2 可接受的算法。 Office 365 继承 Windows 中的 FIPS 验证 (通过 Schannel)。 有关 Schannel 的信息, 请参阅[TLS/SSL 中的密码套件 (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)。
  
## <a name="versions-of-tls-supported-by-office-365"></a>Office 365 支持的 TLS 版本

传输层安全性 (TLS) 和 TLS 之前的 SSL 都是一种加密协议，通过使用安全证书加密计算机之间的连接来保护网络通信的安全。Office 365 支持若干个 TLS 版本，其中包括：
  
- TLS 版本 1.2 (TLS 1.2)
    
- TLS 版本 1.1 (TLS 1.1)
    
- TLS 版本 1.0 (TLS 1.0)
    
 tls 1.0 和 tls 1.1 支持将于年10月31日被弃用。 有关[TLS 1.0 和 1.1](technical-reference-details-about-encryption.md#TLS11and12deprecation)的详细信息, 请参阅弃用支持。 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>弃用支持 TLS 1.0 和1.1 以及这对您的含义
<a name="TLS11and12deprecation"> </a>

自2018年10月31日起, Office 365 不再支持 TLS 1.0 和1.1。 这意味着, Microsoft 不会修复在使用 TLS 1.0 和1.1 连接到 Office 365 的客户端、设备或服务中发现的新问题。

注意这并不意味着 Office 365 将阻止 TLS 1.0 和1.1 连接。 在客户连接的 tls 服务中禁用或删除 tls 1.0 和1.1 没有正式的日期。 最终的弃用日期将由客户遥测确定, 但尚不知道。 做出决定后, 将提前六个月宣布通知, 除非我们意识到已知的危害, 在这种情况下, 我们可能必须在不到六个月的时间内进行操作, 以保护使用服务的客户。

应确保所有客户端服务器和浏览器的组合均使用 TLS 1.2 (或更高版本), 以保持与 Office 365 服务的连接。 您可能需要更新某些客户端服务器和浏览器-服务器的组合。 有关这对你有何影响的信息, 请参阅在[Office 365 中强制使用 TLS 1.2 的准备工作](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365)。
  
## <a name="deprecating-support-for-3des"></a>对3des 的弃用支持
<a name="TLS11and12deprecation"> </a>

自2018年10月31日起, Office 365 不再支持使用3des 密码套件与 Office 365 通信。 更具体地说, Office 365 不再支持 TLS_RSA_WITH_3DES_EDE_CBC_SHA 密码套件。 自2019年2月28日起, 在 Office 365 中禁用此密码套件。 在此日期之后, 与 O365 进行通信的客户端和服务器必须至少支持本主题中列出的一个更安全的密码 (请参阅[Office 365 支持的 TLS 密码套件](technical-reference-details-about-encryption.md#TLSCipherSuites))。
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>在 Office 365 中弃用 SHA-1 证书支持
<a name="TLS11and12deprecation"> </a>

从6月 2016, Office 365 不再为出站或入站连接接受 SHA-1 证书。 如果您当前在证书链中使用 sha-1 证书, 则需要更新该链以使用 sha-1 (安全哈希算法 2) 或更强的哈希算法。
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Office 365 支持的 TLS 密码套件
<a name="TLSCipherSuites"> </a>

密码套件是 TLS 用于建立安全连接的加密算法集合。 Office 365 支持的密码套件在下表中按强度顺序列出, 最强密码套件排在前面。 当 Office 365 收到一个连接请求时，Office 365 首先会尝试使用最上面的密码套件进行连接，如果不成功，则会尝试使用列表中的第二个密码套件，以此类推。 当 Office 365 发送连接请求至其他服务器或客户端时，由接收服务器或客户端决定是选择密码套件还是使用 TLS。

> [!IMPORTANT]
> 请注意, TLS 版本弃用, 如果有更新的版本, 则*不应使用*此版本。 换句话说, 支持 TLS 1.0、1.1 和1.2 的任何位置, 选择*最新*版本 (TLS 1.2)。
  
|**协议**|**密码套件名称**|**密钥交换算法/强度**|**完全向前保密支持**|**身份验证算法/强度**|**密码/强度**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |是  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |是  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0、1.1、1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |否  <br/> |RSA/112  <br/> |AES/128  <br/> |
   
## <a name="related-topics"></a>相关主题
[Windows 10 v1607 中的 TLS 密码套件](https://docs.microsoft.com/windows/desktop/SecAuthN/tls-cipher-suites-in-windows-10-v1607)

[Office 365 中的加密](encryption.md)
  
[设置 Office 365 企业版中的加密](set-up-encryption.md)
  
[在 Windows 安全状态更新中, TLS 1.0 的 Schannel 实现:11 月24日, 2015](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL 加密增强功能 (Windows IT 中心)](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

