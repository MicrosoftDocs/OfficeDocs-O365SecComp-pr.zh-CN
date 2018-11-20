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
# <a name="technical-reference-details-about-encryption-in-office-365"></a><span data-ttu-id="a579b-103">有关 Office 365 加密的技术参考详情</span><span class="sxs-lookup"><span data-stu-id="a579b-103">Technical reference details about encryption in Office 365</span></span>

<span data-ttu-id="a579b-p101">请参阅本文以了解有关证书、 技术和 TLS 用于[Office 365 中的加密](encryption.md)密码套件。本文还提供了有关计划弃用情况的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a579b-p101">Refer to this article to learn about certificates, technologies, and TLS cipher suites used for [encryption in Office 365](encryption.md). This article also provides details about planned deprecations.</span></span>
  
- <span data-ttu-id="a579b-106">如果您正在寻找概述信息，请参阅[Office 365 中的加密](encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="a579b-106">If you're looking for overview information, see [Encryption in Office 365](encryption.md).</span></span>
    
- <span data-ttu-id="a579b-107">如果您正在寻找安装信息，请参阅[Office 365 企业版中的加密设置](set-up-encryption.md)。</span><span class="sxs-lookup"><span data-stu-id="a579b-107">If you're looking for setup information, see [Set up encryption in Office 365 Enterprise](set-up-encryption.md).</span></span>
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a><span data-ttu-id="a579b-108">Microsoft Office 365 证书所有权和管理</span><span class="sxs-lookup"><span data-stu-id="a579b-108">Microsoft Office 365 certificate ownership and management</span></span>

<span data-ttu-id="a579b-109">无需为 Office 365 购买或维护证书，因为 Microsoft 使用其自己的证书。</span><span class="sxs-lookup"><span data-stu-id="a579b-109">You do not need to purchase or maintain certificates for Office 365 because Microsoft uses its own certificates.</span></span>
  
## <a name="current-encryption-standards-and-planned-deprecations"></a><span data-ttu-id="a579b-110">当前加密标准和计划弃用情况</span><span class="sxs-lookup"><span data-stu-id="a579b-110">Current encryption standards and planned deprecations</span></span>

<span data-ttu-id="a579b-p102">若要继续提供最佳的 Office 365 加密，Microsoft 定期审查支持的加密标准。有时，我们需要弃用旧标准，如随即过期，因此不安全。本主题介绍有关规划弃用情况当前支持的密码套件和其他标准以及详细信息。</span><span class="sxs-lookup"><span data-stu-id="a579b-p102">In order to continue to provide best-in-class encryption for Office 365, Microsoft regularly reviews supported encryption standards. Sometimes, we need to deprecate old standards as they become out of date and therefore less secure. This topic describes currently supported cipher suites and other standards as well as details about planned deprecations.</span></span>
  
## <a name="versions-of-tls-supported-by-office-365"></a><span data-ttu-id="a579b-114">Office 365 支持的 TLS 版本</span><span class="sxs-lookup"><span data-stu-id="a579b-114">Versions of TLS supported by Office 365</span></span>

<span data-ttu-id="a579b-p103">传输层安全性 (TLS) 和 TLS 之前的 SSL 都是一种加密协议，通过使用安全证书加密计算机之间的连接来保护网络通信的安全。Office 365 支持若干个 TLS 版本，其中包括：</span><span class="sxs-lookup"><span data-stu-id="a579b-p103">Transport Layer Security (TLS), and SSL that came before TLS, are cryptographic protocols that secure communication over a network by using security certificates to encrypt a connection between computers. Office 365 supports several versions of TLS, including:</span></span>
  
- <span data-ttu-id="a579b-117">TLS 版本 1.2 (TLS 1.2)</span><span class="sxs-lookup"><span data-stu-id="a579b-117">TLS version 1.2 (TLS 1.2)</span></span>
    
- <span data-ttu-id="a579b-118">TLS 版本 1.1 (TLS 1.1)</span><span class="sxs-lookup"><span data-stu-id="a579b-118">TLS version 1.1 (TLS 1.1)</span></span>
    
- <span data-ttu-id="a579b-119">TLS 版本 1.0 (TLS 1.0)</span><span class="sxs-lookup"><span data-stu-id="a579b-119">TLS version 1.0 (TLS 1.0)</span></span>
    
 <span data-ttu-id="a579b-p104">TLS 1.0 和 TLS 1.1 支持将被弃用 2018 年 10 月 31。有关详细信息，请参阅[Deprecating TLS 1.0 和 1.1 这意味着您的支持](technical-reference-details-about-encryption.md#TLS11and12deprecation)。</span><span class="sxs-lookup"><span data-stu-id="a579b-p104">TLS 1.0 and TLS 1.1 support will be deprecated October 31, 2018. See [Deprecating support for TLS 1.0 and 1.1 and what this means for you](technical-reference-details-about-encryption.md#TLS11and12deprecation) for more information.</span></span> 
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a><span data-ttu-id="a579b-122">弃用的 TLS 1.0 和 1.1 这意味着您的支持</span><span class="sxs-lookup"><span data-stu-id="a579b-122">Deprecating support for TLS 1.0 and 1.1 and what this means for you</span></span>
<span data-ttu-id="a579b-123"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="a579b-123"></span></span>

<span data-ttu-id="a579b-p105">从年 10 月 31 2018 TLS 1.0 和 1.1 将不再支持 Office 365。这意味着，Microsoft 将无法修复的客户端、 设备或使用 TLS 1.0 和 1.1 连接到 Office 365 服务中找到新问题。</span><span class="sxs-lookup"><span data-stu-id="a579b-p105">As of October 31, 2018, Office 365 will no longer support TLS 1.0 and 1.1. This means that Microsoft will not fix new issues that are found in clients, devices, or services that connect to Office 365 by using TLS 1.0 and 1.1.</span></span>

<span data-ttu-id="a579b-p106">请注意这并不意味着 Office 365 将阻止 TLS 1.0 和 1.1 连接。禁用或删除 TLS 1.0 和 1.1 TLS 服务的客户连接中没有官方日期。最终否决日期将由客户遥测和还不知道。决定是后，将会通知六个月提前除非我们意识到已知威胁，在这种情况下，我们可能需要操作在小于六个月，以保护客户使用的服务。</span><span class="sxs-lookup"><span data-stu-id="a579b-p106">Note This doesn't mean Office 365 will block TLS 1.0 and 1.1 connections. There is no official date for disabling or removing TLS 1.0 and 1.1 in the TLS service for customer connections. The eventual deprecation date will be determined by customer telemetry and is not yet known. After a decision is made, there will be an announcement six months in advance unless we become aware of a known compromise, in which case we may have to act in less than six months to protect customers who use the services.</span></span>

<span data-ttu-id="a579b-p107">您应确保所有客户端-服务器和服务器浏览器的组合使用 TLS 1.2 （或更高版本） 以保持连接到 Office 365 服务。您可能需要更新某些客户端-服务器和服务器浏览器的组合。有关如何影响您的信息，请参阅[强制使用 TLS 1.2 Office 365 中的 Preparing](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365)。</span><span class="sxs-lookup"><span data-stu-id="a579b-p107">You should make sure that all client-server and browser-server combinations use TLS 1.2 (or a later version) to maintain connection to Office 365 services. You may have to update certain client-server and browser-server combinations. For information about how this impacts you, see [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365).</span></span>
  
## <a name="deprecating-support-for-3des"></a><span data-ttu-id="a579b-133">弃用支持 3DES</span><span class="sxs-lookup"><span data-stu-id="a579b-133">Deprecating support for 3DES</span></span>
<span data-ttu-id="a579b-134"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="a579b-134"></span></span>

<span data-ttu-id="a579b-p108">从年 10 月 31 2018 Office 365 将不再到 Office 365 的通信中支持 3DES 加密套件的使用。更具体地说，Office 365 将不再支持 TLS_RSA_WITH_3DES_EDE_CBC_SHA 密码套件。本主题中列出的客户端和服务器与 O365 后此日期必须支持至少一个更安全的密码 （请参阅[TLS 密码支持 Office 365 套件](technical-reference-details-about-encryption.md#TLSCipherSuites)）。</span><span class="sxs-lookup"><span data-stu-id="a579b-p108">As of October 31, 2018, Office 365 will no longer support the use of 3DES cipher suites for communication to Office 365. More specifically, Office 365 will no longer support the TLS_RSA_WITH_3DES_EDE_CBC_SHA cipher suite. Clients and servers communicating with O365 after this date must support at least one of the more secure ciphers listed in this topic (see [TLS cipher suites supported by Office 365](technical-reference-details-about-encryption.md#TLSCipherSuites)).</span></span>
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a><span data-ttu-id="a579b-138">在 Office 365 中弃用 SHA-1 证书支持</span><span class="sxs-lookup"><span data-stu-id="a579b-138">Deprecating SHA-1 certificate support in Office 365</span></span>
<span data-ttu-id="a579b-139"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="a579b-139"></span></span>

<span data-ttu-id="a579b-p109">6 月 2016，从 Office 365 不再接受 sha-1 证书对出站或入站连接。如果您是当前正在使用证书与 sha-1 证书链中，您将需要更新链使用 160、SHA-2 (安全哈希算法 2) 还是更强的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="a579b-p109">As of June 2016, Office 365 no longer accepts a SHA-1 certificate for outbound or inbound connections. If you are currently using a certificate with SHA-1 in the certificate chain, you will need to update the chain to use SHA-2 (Secure Hash Algorithm 2) or a stronger hashing algorithm.</span></span>
  
## <a name="deprecating-rc4-support-in-office-365"></a><span data-ttu-id="a579b-142">在 Office 365 中弃用 RC4 支持</span><span class="sxs-lookup"><span data-stu-id="a579b-142">Deprecating RC4 support in Office 365</span></span>
<span data-ttu-id="a579b-143"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="a579b-143"></span></span>

<span data-ttu-id="a579b-144">2015 年 7 月已停止对以下 RC4 密码套件的支持：</span><span class="sxs-lookup"><span data-stu-id="a579b-144">In July 2015, support for the following RC4 cipher suites was discontinued:</span></span>
  
- <span data-ttu-id="a579b-145">TLS_RSA_WITH_RC4_128_SHA</span><span class="sxs-lookup"><span data-stu-id="a579b-145">TLS_RSA_WITH_RC4_128_SHA</span></span>
    
- <span data-ttu-id="a579b-146">TLS_RSA_WITH_RC4_128_MD5</span><span class="sxs-lookup"><span data-stu-id="a579b-146">TLS_RSA_WITH_RC4_128_MD5</span></span>
    
## <a name="deprecating-secure-sockets-layer-ssl-30-support-in-office-365"></a><span data-ttu-id="a579b-147">弃用 Office 365 中的安全套接字层 (SSL) 3.0 支持</span><span class="sxs-lookup"><span data-stu-id="a579b-147">Deprecating Secure Sockets Layer (SSL) 3.0 support in Office 365</span></span>
<span data-ttu-id="a579b-148"><a name="TLS11and12deprecation"> </a></span><span class="sxs-lookup"><span data-stu-id="a579b-148"></span></span>

<span data-ttu-id="a579b-p110">启动 2014 年 12 月 1 日，Office 365 开始禁用支持的安全套接字层 (SSL) 3.0，TLS 前置任务。有关详细信息，请参阅[Security 顾问 3009008](https://technet.microsoft.com/library/security/3009008.aspx)。有关说明如何确保客户端使用 TLS 1.0 或更高版本，并禁用 SSL 3.0，请参阅[保护 SSL 3.0 漏洞](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/)。</span><span class="sxs-lookup"><span data-stu-id="a579b-p110">Starting December 1, 2014, Office 365 began disabling support for Secure Sockets Layer (SSL) 3.0, the predecessor to TLS. For more information, see [Security advisory 3009008](https://technet.microsoft.com/library/security/3009008.aspx). For instructions on how to ensure clients are using TLS 1.0 or higher and to disable SSL 3.0, see [Protecting SSL 3.0 vulnerability](http://blogs.office.com/2014/10/29/protecting-ssl-3-0-vulnerability/).</span></span>
  
## <a name="tls-cipher-suites-supported-by-office-365"></a><span data-ttu-id="a579b-152">Office 365 支持 TLS 加密套件</span><span class="sxs-lookup"><span data-stu-id="a579b-152">TLS cipher suites supported by Office 365</span></span>
<span data-ttu-id="a579b-153"><a name="TLSCipherSuites"> </a></span><span class="sxs-lookup"><span data-stu-id="a579b-153"></span></span>

<span data-ttu-id="a579b-p111">密码套件是 TLS 用于建立安全连接的加密算法集合。Office 365 支持的密码套件按强度顺序从最强的密码套件开始依次在下表列出。当 Office 365 收到一个连接请求时，Office 365 首先会尝试使用最上面的密码套件进行连接，如果不成功，则会尝试使用列表中的第二个密码套件，以此类推。当 Office 365 发送连接请求至其他服务器或客户端时，由接收服务器或客户端决定是选择密码套件还是使用 TLS。</span><span class="sxs-lookup"><span data-stu-id="a579b-p111">A cipher suite is a collection of encryption algorithms that TLS uses to establish secure connections. Cipher suites supported by Office 365 are listed in the following table in order of strength with the strongest cipher suite listed first. When Office 365 receives a connection request, Office 365 first attempts to connect using the topmost cipher suite then, if unsuccessful, tries the second cipher suite in the list and so on down the list. When Office 365 sends a connection request to another server or to a client, it's up to the receiving server or client to choose the cipher suite or whether TLS will be used at all.</span></span>
  
|<span data-ttu-id="a579b-158">**协议**</span><span class="sxs-lookup"><span data-stu-id="a579b-158">**Protocols**</span></span>|<span data-ttu-id="a579b-159">**密码套件名称**</span><span class="sxs-lookup"><span data-stu-id="a579b-159">**Cipher suite name**</span></span>|<span data-ttu-id="a579b-160">**密钥交换算法/强度**</span><span class="sxs-lookup"><span data-stu-id="a579b-160">**Key exchange algorithm/Strength**</span></span>|<span data-ttu-id="a579b-161">**完全向前保密支持**</span><span class="sxs-lookup"><span data-stu-id="a579b-161">**Perfect Forward Secrecy support**</span></span>|<span data-ttu-id="a579b-162">**身份验证算法/强度**</span><span class="sxs-lookup"><span data-stu-id="a579b-162">**Authentication algorithm/Strength**</span></span>|<span data-ttu-id="a579b-163">**密码/强度**</span><span class="sxs-lookup"><span data-stu-id="a579b-163">**Cipher/Strength**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a579b-164">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="a579b-164">TLS 1.2</span></span>  <br/> |<span data-ttu-id="a579b-165">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384</span><span class="sxs-lookup"><span data-stu-id="a579b-165">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384</span></span>  <br/> |<span data-ttu-id="a579b-166">ECDH/192</span><span class="sxs-lookup"><span data-stu-id="a579b-166">ECDH/192</span></span>  <br/> |<span data-ttu-id="a579b-167">是</span><span class="sxs-lookup"><span data-stu-id="a579b-167">Yes</span></span>  <br/> |<span data-ttu-id="a579b-168">RSA/112</span><span class="sxs-lookup"><span data-stu-id="a579b-168">RSA/112</span></span>  <br/> |<span data-ttu-id="a579b-169">AES/256</span><span class="sxs-lookup"><span data-stu-id="a579b-169">AES/256</span></span>  <br/> |
|<span data-ttu-id="a579b-170">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="a579b-170">TLS 1.2</span></span>  <br/> |<span data-ttu-id="a579b-171">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256</span><span class="sxs-lookup"><span data-stu-id="a579b-171">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256</span></span>  <br/> |<span data-ttu-id="a579b-172">ECDH/128</span><span class="sxs-lookup"><span data-stu-id="a579b-172">ECDH/128</span></span>  <br/> |<span data-ttu-id="a579b-173">是</span><span class="sxs-lookup"><span data-stu-id="a579b-173">Yes</span></span>  <br/> |<span data-ttu-id="a579b-174">RSA/112</span><span class="sxs-lookup"><span data-stu-id="a579b-174">RSA/112</span></span>  <br/> |<span data-ttu-id="a579b-175">AES/128</span><span class="sxs-lookup"><span data-stu-id="a579b-175">AES/128</span></span>  <br/> |
|<span data-ttu-id="a579b-176">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="a579b-176">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="a579b-177">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384</span><span class="sxs-lookup"><span data-stu-id="a579b-177">TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384</span></span>  <br/> |<span data-ttu-id="a579b-178">ECDH/192</span><span class="sxs-lookup"><span data-stu-id="a579b-178">ECDH/192</span></span>  <br/> |<span data-ttu-id="a579b-179">是</span><span class="sxs-lookup"><span data-stu-id="a579b-179">Yes</span></span>  <br/> |<span data-ttu-id="a579b-180">RSA/112</span><span class="sxs-lookup"><span data-stu-id="a579b-180">RSA/112</span></span>  <br/> |<span data-ttu-id="a579b-181">AES/256</span><span class="sxs-lookup"><span data-stu-id="a579b-181">AES/256</span></span>  <br/> |
|<span data-ttu-id="a579b-182">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="a579b-182">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="a579b-183">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256</span><span class="sxs-lookup"><span data-stu-id="a579b-183">TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256</span></span>  <br/> |<span data-ttu-id="a579b-184">ECDH/128</span><span class="sxs-lookup"><span data-stu-id="a579b-184">ECDH/128</span></span>  <br/> |<span data-ttu-id="a579b-185">是</span><span class="sxs-lookup"><span data-stu-id="a579b-185">Yes</span></span>  <br/> |<span data-ttu-id="a579b-186">RSA/112</span><span class="sxs-lookup"><span data-stu-id="a579b-186">RSA/112</span></span>  <br/> |<span data-ttu-id="a579b-187">AES/128</span><span class="sxs-lookup"><span data-stu-id="a579b-187">AES/128</span></span>  <br/> |
|<span data-ttu-id="a579b-188">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="a579b-188">TLS 1.2</span></span>  <br/> |<span data-ttu-id="a579b-189">TLS_RSA_WITH_AES_256_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="a579b-189">TLS_RSA_WITH_AES_256_CBC_SHA256</span></span>  <br/> |<span data-ttu-id="a579b-190">RSA/112</span><span class="sxs-lookup"><span data-stu-id="a579b-190">RSA/112</span></span>  <br/> |<span data-ttu-id="a579b-191">否</span><span class="sxs-lookup"><span data-stu-id="a579b-191">No</span></span>  <br/> |<span data-ttu-id="a579b-192">RSA/112</span><span class="sxs-lookup"><span data-stu-id="a579b-192">RSA/112</span></span>  <br/> |<span data-ttu-id="a579b-193">AES/256</span><span class="sxs-lookup"><span data-stu-id="a579b-193">AES/256</span></span>  <br/> |
|<span data-ttu-id="a579b-194">TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="a579b-194">TLS 1.2</span></span>  <br/> |<span data-ttu-id="a579b-195">TLS_RSA_WITH_AES_128_CBC_SHA256</span><span class="sxs-lookup"><span data-stu-id="a579b-195">TLS_RSA_WITH_AES_128_CBC_SHA256</span></span>  <br/> |<span data-ttu-id="a579b-196">RSA/112</span><span class="sxs-lookup"><span data-stu-id="a579b-196">RSA/112</span></span>  <br/> |<span data-ttu-id="a579b-197">否</span><span class="sxs-lookup"><span data-stu-id="a579b-197">No</span></span>  <br/> |<span data-ttu-id="a579b-198">RSA/112</span><span class="sxs-lookup"><span data-stu-id="a579b-198">RSA/112</span></span>  <br/> |<span data-ttu-id="a579b-199">AES/128</span><span class="sxs-lookup"><span data-stu-id="a579b-199">AES/128</span></span>  <br/> |
|<span data-ttu-id="a579b-200">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="a579b-200">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="a579b-201">TLS_RSA_WITH_AES_256_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="a579b-201">TLS_RSA_WITH_AES_256_CBC_SHA</span></span>  <br/> |<span data-ttu-id="a579b-202">RSA/112</span><span class="sxs-lookup"><span data-stu-id="a579b-202">RSA/112</span></span>  <br/> |<span data-ttu-id="a579b-203">否</span><span class="sxs-lookup"><span data-stu-id="a579b-203">No</span></span>  <br/> |<span data-ttu-id="a579b-204">RSA/112</span><span class="sxs-lookup"><span data-stu-id="a579b-204">RSA/112</span></span>  <br/> |<span data-ttu-id="a579b-205">AES/256</span><span class="sxs-lookup"><span data-stu-id="a579b-205">AES/256</span></span>  <br/> |
|<span data-ttu-id="a579b-206">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="a579b-206">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="a579b-207">TLS_RSA_WITH_AES_128_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="a579b-207">TLS_RSA_WITH_AES_128_CBC_SHA</span></span>  <br/> |<span data-ttu-id="a579b-208">RSA/112</span><span class="sxs-lookup"><span data-stu-id="a579b-208">RSA/112</span></span>  <br/> |<span data-ttu-id="a579b-209">否</span><span class="sxs-lookup"><span data-stu-id="a579b-209">No</span></span>  <br/> |<span data-ttu-id="a579b-210">RSA/112</span><span class="sxs-lookup"><span data-stu-id="a579b-210">RSA/112</span></span>  <br/> |<span data-ttu-id="a579b-211">AES/128</span><span class="sxs-lookup"><span data-stu-id="a579b-211">AES/128</span></span>  <br/> |
|<span data-ttu-id="a579b-212">TLS 1.0、1.1、1.2</span><span class="sxs-lookup"><span data-stu-id="a579b-212">TLS 1.0, 1.1, 1.2</span></span>  <br/> |<span data-ttu-id="a579b-213">TLS_RSA_WITH_3DES_EDE_CBC_SHA</span><span class="sxs-lookup"><span data-stu-id="a579b-213">TLS_RSA_WITH_3DES_EDE_CBC_SHA</span></span>  <br/> |<span data-ttu-id="a579b-214">RSA/112</span><span class="sxs-lookup"><span data-stu-id="a579b-214">RSA/112</span></span>  <br/> |<span data-ttu-id="a579b-215">否</span><span class="sxs-lookup"><span data-stu-id="a579b-215">No</span></span>  <br/> |<span data-ttu-id="a579b-216">RSA/112</span><span class="sxs-lookup"><span data-stu-id="a579b-216">RSA/112</span></span>  <br/> |<span data-ttu-id="a579b-217">3DES/192</span><span class="sxs-lookup"><span data-stu-id="a579b-217">3DES/192</span></span>  <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="a579b-218">相关主题</span><span class="sxs-lookup"><span data-stu-id="a579b-218">Related topics</span></span>
<span data-ttu-id="a579b-219"><a name="TLSCipherSuites"> </a></span><span class="sxs-lookup"><span data-stu-id="a579b-219"></span></span>

[<span data-ttu-id="a579b-220">Office 365 中的加密</span><span class="sxs-lookup"><span data-stu-id="a579b-220">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="a579b-221">设置 Office 365 企业版中的加密</span><span class="sxs-lookup"><span data-stu-id="a579b-221">Set up encryption in Office 365 Enterprise</span></span>](set-up-encryption.md)
  
[<span data-ttu-id="a579b-222">Windows 安全状态更新中的 TLS 1.0 的 Schannel 实现： 2015 年 11 月 24 日</span><span class="sxs-lookup"><span data-stu-id="a579b-222">Schannel implementation of TLS 1.0 in Windows security status update: November 24, 2015</span></span>](https://support.microsoft.com/kb/3117336)
  
[<span data-ttu-id="a579b-223">TLS/SSL 加密增强功能 (Windows IT 中心)</span><span class="sxs-lookup"><span data-stu-id="a579b-223">TLS/SSL Cryptographic Enhancements (Windows IT Center)</span></span>](https://technet.microsoft.com/en-us/library/cc766285%28v=ws.10%29.aspx)
  

