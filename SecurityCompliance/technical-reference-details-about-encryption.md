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
ms.openlocfilehash: d86692119f7558d74e2083165b4eb6ab4a07da70
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525807"
---
# <a name="technical-reference-details-about-encryption-in-office-365"></a><span data-ttu-id="c6c6a-103">有关 Office 365 加密的技术参考详情</span><span class="sxs-lookup"><span data-stu-id="c6c6a-103">Technical reference details about encryption in Office 365</span></span>

<span data-ttu-id="c6c6a-p101">请参阅本文以了解有关证书、 技术和 TLS 用于[Office 365 中的加密](encryption.md)密码套件。本文还提供了有关计划弃用情况的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c6c6a-p101">Refer to this article to learn about certificates, technologies, and TLS cipher suites used for [encryption in Office 365](encryption.md). This article also provides details about planned deprecations.</span></span>
  
- <span data-ttu-id="c6c6a-106">如果您正在寻找概述信息，请参阅[Office 365 中的加密](encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="c6c6a-106">If you're looking for overview information, see [Encryption in Office 365](encryption.md).</span></span>
    
- <span data-ttu-id="c6c6a-107">如果您正在寻找安装信息，请参阅[Office 365 企业版中的加密设置](set-up-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="c6c6a-107">If you're looking for setup information, see [Set up encryption in Office 365 Enterprise](set-up-encryption.md).</span></span>
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a><span data-ttu-id="c6c6a-108">Microsoft Office 365 证书所有权和管理</span><span class="sxs-lookup"><span data-stu-id="c6c6a-108">Microsoft Office 365 certificate ownership and management</span></span>

<span data-ttu-id="c6c6a-109">无需为 Office 365 购买或维护证书，因为 Microsoft 使用其自己的证书。</span><span class="sxs-lookup"><span data-stu-id="c6c6a-109">You do not need to purchase or maintain certificates for Office 365 because Microsoft uses its own certificates.</span></span>
  
## <a name="current-encryption-standards-and-planned-deprecations"></a><span data-ttu-id="c6c6a-110">当前加密标准和计划弃用情况</span><span class="sxs-lookup"><span data-stu-id="c6c6a-110">Current encryption standards and planned deprecations</span></span>

<span data-ttu-id="c6c6a-p102">若要继续提供最佳的 Office 365 加密，Microsoft 定期审查支持的加密标准。有时，我们需要弃用旧标准，如随即过期，因此不安全。本主题介绍有关规划弃用情况当前支持的密码套件和其他标准以及详细信息。</span><span class="sxs-lookup"><span data-stu-id="c6c6a-p102">In order to continue to provide best-in-class encryption for Office 365, Microsoft regularly reviews supported encryption standards. Sometimes, we need to deprecate old standards as they become out of date and therefore less secure. This topic describes currently supported cipher suites and other standards as well as details about planned deprecations.</span></span>
  
## <a name="versions-of-tls-supported-by-office-365"></a><span data-ttu-id="c6c6a-114">Office 365 支持的 TLS 版本</span><span class="sxs-lookup"><span data-stu-id="c6c6a-114">Versions of TLS supported by Office 365</span></span>

<span data-ttu-id="c6c6a-p103">传输层安全性 (TLS) 和 TLS 之前的 SSL 都是一种加密协议，通过使用安全证书加密计算机之间的连接来保护网络通信的安全。Office 365 支持若干个 TLS 版本，其中包括：</span><span class="sxs-lookup"><span data-stu-id="c6c6a-p103">Transport Layer Security (TLS), and SSL that came before TLS, are cryptographic protocols that secure communication over a network by using security certificates to encrypt a connection between computers. Office 365 supports several versions of TLS, including:</span></span>
  
- <span data-ttu-id="c6c6a-117">TLS 版本 1.2 (TLS 1.2)</span><span class="sxs-lookup"><span data-stu-id="c6c6a-117">TLS version 1.2 (TLS 1.2)</span></span>
    
- <span data-ttu-id="c6c6a-118">TLS 版本 1.1 (TLS 1.1)</span><span class="sxs-lookup"><span data-stu-id="c6c6a-118">TLS version 1.1 (TLS 1.1)</span></span>
    
- <span data-ttu-id="c6c6a-119">TLS 版本 1.0 (TLS 1.0)</span><span class="sxs-lookup"><span data-stu-id="c6c6a-119">TLS version 1.0 (TLS 1.0)</span></span>
    
 <span data-ttu-id="c6c6a-p104">TLS 1.0 和 TLS 1.1 支持将被弃用 2018 年 10 月 31。有关详细信息，请参阅[Deprecating TLS 1.0 和 1.1 这意味着您的支持](technical-reference-details-about-encryption.md#TLS11and12deprecation)。</span><span class="sxs-lookup"><span data-stu-id="c6c6a-p104">TLS 1.0 and TLS 1.1 support will be deprecated October 31, 2018. See [Deprecating support for TLS 1.0 and 1.1 and what this means for you](technical-reference-details-about-encryption.md#TLS11and12deprecation) for more information.</span></span> 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a><span data-ttu-id="c6c6a-122">弃用的 TLS 1.0 和 1.1 这意味着您的支持</span><span class="sxs-lookup"><span data-stu-id="c6c6a-122">Deprecating support for TLS 1.0 and 1.1 and what this means for you</span></span>
<span data-ttu-id="c6c6a-123"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="c6c6a-123"></span></span>

<span data-ttu-id="c6c6a-p105">重要更改至此 Office 365 支持的加密选项。从年 10 月 31 2018 Office 365 将使用 TLS 1.0 或 1.1 不再支持到 Office 365 的通信。一旦 Office 365 成为对这些协议的支持，需要使用 TLS 1.2 与 Office 365 服务器的所有通信。有关如何影响您的信息，请参阅[强制使用 TLS 1.2 Office 365 中的 Preparing](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365)。服务器和客户端与此日期之后的 O365 必须支持 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="c6c6a-p105">Important changes are coming to supported encryption options for Office 365. As of October 31, 2018, Office 365 will no longer support the use of TLS 1.0 or 1.1 for communication to Office 365. Once Office 365 deprecates support for these protocols, all communication to and from Office 365 servers will need to use TLS 1.2. For information about how this impacts you, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365). Servers and clients communicating with O365 after this date must support TLS 1.2.</span></span>
  
## <a name="deprecating-support-for-3des"></a><span data-ttu-id="c6c6a-129">弃用支持 3DES</span><span class="sxs-lookup"><span data-stu-id="c6c6a-129">Deprecating support for 3DES</span></span>
<span data-ttu-id="c6c6a-130"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="c6c6a-130"></span></span>

<span data-ttu-id="c6c6a-p106">从年 10 月 31 2018 Office 365 将不再到 Office 365 的通信中支持 3DES 加密套件的使用。更具体地说，Office 365 将不再支持 TLS_RSA_WITH_3DES_EDE_CBC_SHA 密码套件。本主题中列出的客户端和服务器与 O365 后此日期必须支持至少一个更安全的密码 （请参阅[TLS 密码支持 Office 365 套件](technical-reference-details-about-encryption.md#TLSCipherSuites)）。</span><span class="sxs-lookup"><span data-stu-id="c6c6a-p106">As of October 31, 2018, Office 365 will no longer support the use of 3DES cipher suites for communication to Office 365. More specifically, Office 365 will no longer support the TLS_RSA_WITH_3DES_EDE_CBC_SHA cipher suite. Clients and servers communicating with O365 after this date must support at least one of the more secure ciphers listed in this topic (see [TLS cipher suites supported by Office 365](technical-reference-details-about-encryption.md#TLSCipherSuites)).</span></span>
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a><span data-ttu-id="c6c6a-134">在 Office 365 中弃用 SHA-1 证书支持</span><span class="sxs-lookup"><span data-stu-id="c6c6a-134">Deprecating SHA-1 certificate support in Office 365</span></span>
<span data-ttu-id="c6c6a-135"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="c6c6a-135"></span></span>

<span data-ttu-id="c6c6a-p107">6 月 2016，从 Office 365 不再接受 sha-1 证书对出站或入站连接。如果您是当前正在使用证书与 sha-1 证书链中，您将需要更新链使用 160、SHA-2 (安全哈希算法 2) 还是更强的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="c6c6a-p107">As of June 2016, Office 365 no longer accepts a SHA-1 certificate for outbound or inbound connections. If you are currently using a certificate with SHA-1 in the certificate chain, you will need to update the chain to use SHA-2 (Secure Hash Algorithm 2) or a stronger hashing algorithm.</span></span>
  
## <a name="deprecating-rc4-support-in-office-365"></a><span data-ttu-id="c6c6a-138">在 Office 365 中弃用 RC4 支持</span><span class="sxs-lookup"><span data-stu-id="c6c6a-138">Deprecating RC4 support in Office 365</span></span>
<span data-ttu-id="c6c6a-139"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="c6c6a-139"></span></span>

<span data-ttu-id="c6c6a-140">2015 年 7 月已停止对以下 RC4 密码套件的支持：</span><span class="sxs-lookup"><span data-stu-id="c6c6a-140">In July 2015, support for the following RC4 cipher suites was discontinued:</span></span>
  
- <span data-ttu-id="c6c6a-141">TLS_RSA_WITH_RC4_128_SHA</span><span class="sxs-lookup"><span data-stu-id="c6c6a-141">TLS_RSA_WITH_RC4_128_SHA</span></span>
    
- <span data-ttu-id="c6c6a-142">TLS_RSA_WITH_RC4_128_MD5</span><span class="sxs-lookup"><span data-stu-id="c6c6a-142">TLS_RSA_WITH_RC4_128_MD5</span></span>
    
## <a name="deprecating-secure-sockets-layer-ssl-30-support-in-office-365"></a><span data-ttu-id="c6c6a-143">弃用 Office 365 中的安全套接字层 (SSL) 3.0 支持</span><span class="sxs-lookup"><span data-stu-id="c6c6a-143">Deprecating Secure Sockets Layer (SSL) 3.0 support in Office 365</span></span>
<span data-ttu-id="c6c6a-144"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="c6c6a-144"></span></span>

<span data-ttu-id="c6c6a-p108">启动 2014 年 12 月 1 日，Office 365 开始禁用支持的安全套接字层 (SSL) 3.0，TLS 前置任务。有关详细信息，请参阅[Security 顾问 3009008](https://technet.microsoft.com/library/security/3009008.aspx)。有关说明如何确保客户端使用 TLS 1.0 或更高版本，并禁用 SSL 3.0，请参阅[保护 SSL 3.0 漏洞](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/)。</span><span class="sxs-lookup"><span data-stu-id="c6c6a-p108">Starting December 1, 2014, Office 365 began disabling support for Secure Sockets Layer (SSL) 3.0, the predecessor to TLS. For more information, see [Security advisory 3009008](https://technet.microsoft.com/library/security/3009008.aspx). For instructions on how to ensure clients are using TLS 1.0 or higher and to disable SSL 3.0, see [Protecting SSL 3.0 vulnerability](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/).</span></span>
  
## <a name="tls-cipher-suites-supported-by-office-365"></a><span data-ttu-id="c6c6a-148">Office 365 支持 TLS 加密套件</span><span class="sxs-lookup"><span data-stu-id="c6c6a-148">TLS cipher suites supported by Office 365</span></span>
<span data-ttu-id="c6c6a-149"><a name="TLSCipherSuites"> </a></span><span class="sxs-lookup"><span data-stu-id="c6c6a-149"></span></span>

<span data-ttu-id="c6c6a-p109">密码套件是 TLS 用于建立安全连接的加密算法集合。Office 365 支持的密码套件按强度顺序从最强的密码套件开始依次在下表列出。当 Office 365 收到一个连接请求时，Office 365 首先会尝试使用最上面的密码套件进行连接，如果不成功，则会尝试使用列表中的第二个密码套件，以此类推。当 Office 365 发送连接请求至其他服务器或客户端时，由接收服务器或客户端决定是选择密码套件还是使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="c6c6a-p109">A cipher suite is a collection of encryption algorithms that TLS uses to establish secure connections. Cipher suites supported by Office 365 are listed in the following table in order of strength with the strongest cipher suite listed first. When Office 365 receives a connection request, Office 365 first attempts to connect using the topmost cipher suite then, if unsuccessful, tries the second cipher suite in the list and so on down the list. When Office 365 sends a connection request to another server or to a client, it's up to the receiving server or client to choose the cipher suite or whether TLS will be used at all.</span></span>
  
|<span data-ttu-id="c6c6a-154">**协议**</span><span class="sxs-lookup"><span data-stu-id="c6c6a-154">**Protocols**</span></span>|<span data-ttu-id="c6c6a-155">**密码套件名称**</span><span class="sxs-lookup"><span data-stu-id="c6c6a-155">**Cipher suite name**</span></span>|<span data-ttu-id="c6c6a-156">**密钥交换算法/强度**</span><span class="sxs-lookup"><span data-stu-id="c6c6a-156">**Key exchange algorithm/Strength**</span></span>|<span data-ttu-id="c6c6a-157">**完全向前保密支持**</span><span class="sxs-lookup"><span data-stu-id="c6c6a-157">**Perfect Forward Secrecy support**</span></span>|<span data-ttu-id="c6c6a-158">**身份验证算法/强度**</span><span class="sxs-lookup"><span data-stu-id="c6c6a-158">**Authentication algorithm/Strength**</span></span>|<span data-ttu-id="c6c6a-159">**密码/强度**</span><span class="sxs-lookup"><span data-stu-id="c6c6a-159">**Cipher/Strength**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c6c6a-160">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="c6c6a-160">TLS 1.2</span></span>  <br/> |<span data-ttu-id="c6c6a-161">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384</span><span class="sxs-lookup"><span data-stu-id="c6c6a-161">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384</span></span>  <br/> |<span data-ttu-id="c6c6a-162">ECDH/192</span><span class="sxs-lookup"><span data-stu-id="c6c6a-162">ECDH/192</span></span>  <br/> |<span data-ttu-id="c6c6a-163">是</span><span class="sxs-lookup"><span data-stu-id="c6c6a-163">Yes</span></span>  <br/> |<span data-ttu-id="c6c6a-164">RSA/112</span><span class="sxs-lookup"><span data-stu-id="c6c6a-164">RSA/112</span></span>  <br/> |<span data-ttu-id="c6c6a-165">AES/256</span><span class="sxs-lookup"><span data-stu-id="c6c6a-165">AES/256</span></span>  <br/> |
|<span data-ttu-id="c6c6a-166">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="c6c6a-166">TLS 1.2</span></span>  <br/> |<span data-ttu-id="c6c6a-167">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256</span><span class="sxs-lookup"><span data-stu-id="c6c6a-167">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256</span></span>  <br/> |<span data-ttu-id="c6c6a-168">ECDH/128</span><span class="sxs-lookup"><span data-stu-id="c6c6a-168">ECDH/128</span></span>  <br/> |<span data-ttu-id="c6c6a-169">是</span><span class="sxs-lookup"><span data-stu-id="c6c6a-169">Yes</span></span>  <br/> |<span data-ttu-id="c6c6a-170">RSA/112</span><span class="sxs-lookup"><span data-stu-id="c6c6a-170">RSA/112</span></span>  <br/> |<span data-ttu-id="c6c6a-171">AES/128</span><span class="sxs-lookup"><span data-stu-id="c6c6a-171">AES/128</span></span>  <br/> |
|<span data-ttu-id="c6c6a-172">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="c6c6a-172">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="c6c6a-173">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384</span><span class="sxs-lookup"><span data-stu-id="c6c6a-173">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384</span></span>  <br/> |<span data-ttu-id="c6c6a-174">ECDH/192</span><span class="sxs-lookup"><span data-stu-id="c6c6a-174">ECDH/192</span></span>  <br/> |<span data-ttu-id="c6c6a-175">是</span><span class="sxs-lookup"><span data-stu-id="c6c6a-175">Yes</span></span>  <br/> |<span data-ttu-id="c6c6a-176">RSA/112</span><span class="sxs-lookup"><span data-stu-id="c6c6a-176">RSA/112</span></span>  <br/> |<span data-ttu-id="c6c6a-177">AES/256</span><span class="sxs-lookup"><span data-stu-id="c6c6a-177">AES/256</span></span>  <br/> |
|<span data-ttu-id="c6c6a-178">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="c6c6a-178">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="c6c6a-179">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256</span><span class="sxs-lookup"><span data-stu-id="c6c6a-179">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256</span></span>  <br/> |<span data-ttu-id="c6c6a-180">ECDH/128</span><span class="sxs-lookup"><span data-stu-id="c6c6a-180">ECDH/128</span></span>  <br/> |<span data-ttu-id="c6c6a-181">是</span><span class="sxs-lookup"><span data-stu-id="c6c6a-181">Yes</span></span>  <br/> |<span data-ttu-id="c6c6a-182">RSA/112</span><span class="sxs-lookup"><span data-stu-id="c6c6a-182">RSA/112</span></span>  <br/> |<span data-ttu-id="c6c6a-183">AES/128</span><span class="sxs-lookup"><span data-stu-id="c6c6a-183">AES/128</span></span>  <br/> |
|<span data-ttu-id="c6c6a-184">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="c6c6a-184">TLS 1.2</span></span>  <br/> |<span data-ttu-id="c6c6a-185">TLS_RSA_WITH_AES_256_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="c6c6a-185">TLS_RSA_WITH_AES_256_CBC_SHA256</span></span>  <br/> |<span data-ttu-id="c6c6a-186">RSA/112</span><span class="sxs-lookup"><span data-stu-id="c6c6a-186">RSA/112</span></span>  <br/> |<span data-ttu-id="c6c6a-187">否</span><span class="sxs-lookup"><span data-stu-id="c6c6a-187">No</span></span>  <br/> |<span data-ttu-id="c6c6a-188">RSA/112</span><span class="sxs-lookup"><span data-stu-id="c6c6a-188">RSA/112</span></span>  <br/> |<span data-ttu-id="c6c6a-189">AES/256</span><span class="sxs-lookup"><span data-stu-id="c6c6a-189">AES/256</span></span>  <br/> |
|<span data-ttu-id="c6c6a-190">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="c6c6a-190">TLS 1.2</span></span>  <br/> |<span data-ttu-id="c6c6a-191">TLS_RSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="c6c6a-191">TLS_RSA_WITH_AES_128_CBC_SHA256</span></span>  <br/> |<span data-ttu-id="c6c6a-192">RSA/112</span><span class="sxs-lookup"><span data-stu-id="c6c6a-192">RSA/112</span></span>  <br/> |<span data-ttu-id="c6c6a-193">否</span><span class="sxs-lookup"><span data-stu-id="c6c6a-193">No</span></span>  <br/> |<span data-ttu-id="c6c6a-194">RSA/112</span><span class="sxs-lookup"><span data-stu-id="c6c6a-194">RSA/112</span></span>  <br/> |<span data-ttu-id="c6c6a-195">AES/128</span><span class="sxs-lookup"><span data-stu-id="c6c6a-195">AES/128</span></span>  <br/> |
|<span data-ttu-id="c6c6a-196">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="c6c6a-196">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="c6c6a-197">TLS_RSA_WITH_AES_256_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="c6c6a-197">TLS_RSA_WITH_AES_256_CBC_SHA</span></span>  <br/> |<span data-ttu-id="c6c6a-198">RSA/112</span><span class="sxs-lookup"><span data-stu-id="c6c6a-198">RSA/112</span></span>  <br/> |<span data-ttu-id="c6c6a-199">否</span><span class="sxs-lookup"><span data-stu-id="c6c6a-199">No</span></span>  <br/> |<span data-ttu-id="c6c6a-200">RSA/112</span><span class="sxs-lookup"><span data-stu-id="c6c6a-200">RSA/112</span></span>  <br/> |<span data-ttu-id="c6c6a-201">AES/256</span><span class="sxs-lookup"><span data-stu-id="c6c6a-201">AES/256</span></span>  <br/> |
|<span data-ttu-id="c6c6a-202">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="c6c6a-202">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="c6c6a-203">TLS_RSA_WITH_AES_128_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="c6c6a-203">TLS_RSA_WITH_AES_128_CBC_SHA</span></span>  <br/> |<span data-ttu-id="c6c6a-204">RSA/112</span><span class="sxs-lookup"><span data-stu-id="c6c6a-204">RSA/112</span></span>  <br/> |<span data-ttu-id="c6c6a-205">否</span><span class="sxs-lookup"><span data-stu-id="c6c6a-205">No</span></span>  <br/> |<span data-ttu-id="c6c6a-206">RSA/112</span><span class="sxs-lookup"><span data-stu-id="c6c6a-206">RSA/112</span></span>  <br/> |<span data-ttu-id="c6c6a-207">AES/128</span><span class="sxs-lookup"><span data-stu-id="c6c6a-207">AES/128</span></span>  <br/> |
|<span data-ttu-id="c6c6a-208">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="c6c6a-208">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="c6c6a-209">TLS_RSA_WITH_3DES_EDE_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="c6c6a-209">TLS_RSA_WITH_3DES_EDE_CBC_SHA</span></span>  <br/> |<span data-ttu-id="c6c6a-210">RSA/112</span><span class="sxs-lookup"><span data-stu-id="c6c6a-210">RSA/112</span></span>  <br/> |<span data-ttu-id="c6c6a-211">否</span><span class="sxs-lookup"><span data-stu-id="c6c6a-211">No</span></span>  <br/> |<span data-ttu-id="c6c6a-212">RSA/112</span><span class="sxs-lookup"><span data-stu-id="c6c6a-212">RSA/112</span></span>  <br/> |<span data-ttu-id="c6c6a-213">3DES/192</span><span class="sxs-lookup"><span data-stu-id="c6c6a-213">3DES/192</span></span>  <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="c6c6a-214">相关主题</span><span class="sxs-lookup"><span data-stu-id="c6c6a-214">Related topics</span></span>
<span data-ttu-id="c6c6a-215"><a name="TLSCipherSuites"> </a></span><span class="sxs-lookup"><span data-stu-id="c6c6a-215"></span></span>

[<span data-ttu-id="c6c6a-216">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="c6c6a-216">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="c6c6a-217">设置 Office 365 企业版中的加密</span><span class="sxs-lookup"><span data-stu-id="c6c6a-217">Set up encryption in Office 365 Enterprise</span></span>](set-up-encryption.md)
  
[<span data-ttu-id="c6c6a-218">Windows 安全状态更新中的 TLS 1.0 的 Schannel 实现： 2015 年 11 月 24 日</span><span class="sxs-lookup"><span data-stu-id="c6c6a-218">Schannel implementation of TLS 1.0 in Windows security status update: November 24, 2015</span></span>](https://support.microsoft.com/kb/3117336)
  
[<span data-ttu-id="c6c6a-219">TLS/SSL 加密增强功能 (Windows IT 中心)</span><span class="sxs-lookup"><span data-stu-id="c6c6a-219">TLS/SSL Cryptographic Enhancements (Windows IT Center)</span></span>](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

