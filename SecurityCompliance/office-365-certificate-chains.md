---
title: Office 365 证书链
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.assetid: 0c03e6b3-e73f-4316-9e2b-bf4091ae96bb
description: Office 365 利用大量的不同的证书提供商。下面介绍已知客户访问 Office 365 时可能遇到的 Office 365 根证书的完整的列表。您可能需要您自己的基础结构中安装证书的信息，请参阅 Plan 第三方 SSL 证书的 Office 365。下面的证书信息适用于 Office 365 的所有全球和国家/地区云实例。
ms.openlocfilehash: 1dcc2dc38bb8e3239a3be3983791b0c60917dc5e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525287"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="d87bd-106">Office 365 证书链</span><span class="sxs-lookup"><span data-stu-id="d87bd-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="d87bd-p102">Office 365 利用大量的不同的证书提供商。下面介绍已知客户访问 Office 365 时可能遇到的 Office 365 根证书的完整的列表。您可能需要您自己的基础结构中安装证书信息，请参阅[Office 365 的第三方 SSL 证书计划](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce)。下面的证书信息适用于 Office 365 的所有全球和国家/地区云实例。</span><span class="sxs-lookup"><span data-stu-id="d87bd-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="d87bd-111">**证书类型**</span><span class="sxs-lookup"><span data-stu-id="d87bd-111">**Certificate type**</span></span>|<span data-ttu-id="d87bd-112">**P7b 下载**</span><span class="sxs-lookup"><span data-stu-id="d87bd-112">**P7b download**</span></span>|<span data-ttu-id="d87bd-113">**CRL 终结点**</span><span class="sxs-lookup"><span data-stu-id="d87bd-113">**CRL Endpoints**</span></span>|<span data-ttu-id="d87bd-114">**OCSP 终结点**</span><span class="sxs-lookup"><span data-stu-id="d87bd-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="d87bd-115">**AIA 终结点**</span><span class="sxs-lookup"><span data-stu-id="d87bd-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="d87bd-116">公共受信任的根证书</span><span class="sxs-lookup"><span data-stu-id="d87bd-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="d87bd-117">Office 365 根证书绑定 (P7B)</span><span class="sxs-lookup"><span data-stu-id="d87bd-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="d87bd-118">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="d87bd-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="d87bd-119">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="d87bd-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="d87bd-120">不适用</span><span class="sxs-lookup"><span data-stu-id="d87bd-120">N/A</span></span>  <br/> |<span data-ttu-id="d87bd-121">不适用</span><span class="sxs-lookup"><span data-stu-id="d87bd-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="d87bd-122">公共受信任的中间证书</span><span class="sxs-lookup"><span data-stu-id="d87bd-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="d87bd-123">Office 365 中间证书绑定 (P7B)</span><span class="sxs-lookup"><span data-stu-id="d87bd-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="d87bd-124">cdp1.public trust.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="d87bd-125">crl.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="d87bd-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="d87bd-126">crl.entrust.net</span><span class="sxs-lookup"><span data-stu-id="d87bd-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="d87bd-127">crl.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="d87bd-128">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="d87bd-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="d87bd-129">crl.identrust.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="d87bd-130">crl.thawte.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="d87bd-131">crl3.digicert.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="d87bd-132">crl4.digicert.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="d87bd-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="d87bd-134">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="d87bd-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="d87bd-135">isrg.trustid.ocsp.identrust.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="d87bd-136">ocsp.digicert.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="d87bd-137">ocsp.entrust.net</span><span class="sxs-lookup"><span data-stu-id="d87bd-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="d87bd-138">ocsp.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="d87bd-139">ocsp.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="d87bd-140">ocsp.startssl.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="d87bd-141">ocsp.thawte.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="d87bd-142">ocsp2.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="d87bd-143">ocspcnnicroot.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="d87bd-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="d87bd-144">根-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="d87bd-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="d87bd-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="d87bd-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="d87bd-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="d87bd-147">aia.startssl.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="d87bd-148">apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="d87bd-149">cacert.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="d87bd-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="d87bd-150">www.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="d87bd-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="d87bd-151">展开根和下面有关证书提供商的其他详细信息，请参阅的中间部分。</span><span class="sxs-lookup"><span data-stu-id="d87bd-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="d87bd-152">Office 365 根证书的详细信息</span><span class="sxs-lookup"><span data-stu-id="d87bd-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="d87bd-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="d87bd-153"></span></span>

 <span data-ttu-id="d87bd-154">**Baltimore CyberTrust 根**</span><span class="sxs-lookup"><span data-stu-id="d87bd-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="d87bd-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="d87bd-155">|:-----|</span></span>
|<span data-ttu-id="d87bd-156">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="d87bd-157">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-157">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-158">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-158"></span></span>|
|<span data-ttu-id="d87bd-159">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-159">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-160">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-160"></span></span>|
|<span data-ttu-id="d87bd-161">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-162">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-162"></span></span>|
|<span data-ttu-id="d87bd-163">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-164">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-164"></span></span>|
|<span data-ttu-id="d87bd-165">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-165">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-166">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-166"></span></span>|
|<span data-ttu-id="d87bd-167">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-168">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-168"></span></span>|
|<span data-ttu-id="d87bd-169">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-170">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-170"></span></span>|
|<span data-ttu-id="d87bd-171">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-172">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-172"></span></span>|
|<span data-ttu-id="d87bd-173">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-174">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-174"></span></span>|
   
 <span data-ttu-id="d87bd-175">**CNNIC 根**</span><span class="sxs-lookup"><span data-stu-id="d87bd-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-176">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-176">**Subject**</span></span>|
|<span data-ttu-id="d87bd-177">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-177"></span></span>|
|<span data-ttu-id="d87bd-178">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-178">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-179">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-179"></span></span>|
|<span data-ttu-id="d87bd-180">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-180">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-181">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-181"></span></span>|
|<span data-ttu-id="d87bd-182">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-183">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-183"></span></span>|
|<span data-ttu-id="d87bd-184">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-185">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-185"></span></span>|
|<span data-ttu-id="d87bd-186">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-186">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-187">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-187"></span></span>|
|<span data-ttu-id="d87bd-188">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-189">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-189"></span></span>|
|<span data-ttu-id="d87bd-190">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-191">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-191"></span></span>|
|<span data-ttu-id="d87bd-192">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-193">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-193"></span></span>|
|<span data-ttu-id="d87bd-194">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-195">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-195"></span></span>|
|<span data-ttu-id="d87bd-196">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-197">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-197"></span></span>|
   
 <span data-ttu-id="d87bd-198">**DigiCert 全局根 CA**</span><span class="sxs-lookup"><span data-stu-id="d87bd-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-199">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-199">**Subject**</span></span>|
|<span data-ttu-id="d87bd-200">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-200"></span></span>|
|<span data-ttu-id="d87bd-201">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-201">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-202">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-202"></span></span>|
|<span data-ttu-id="d87bd-203">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-203">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-204">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-204"></span></span>|
|<span data-ttu-id="d87bd-205">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-206">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-206"></span></span>|
|<span data-ttu-id="d87bd-207">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-208">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-208"></span></span>|
|<span data-ttu-id="d87bd-209">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-209">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-210">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-210"></span></span>|
|<span data-ttu-id="d87bd-211">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-212">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-212"></span></span>|
|<span data-ttu-id="d87bd-213">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-214">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-214"></span></span>|
|<span data-ttu-id="d87bd-215">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-216">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-216"></span></span>|
|<span data-ttu-id="d87bd-217">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-218">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-218"></span></span>|
|<span data-ttu-id="d87bd-219">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-220">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-220"></span></span>|
   
 <span data-ttu-id="d87bd-221">**DigiCert 高保证 EV 根 CA**</span><span class="sxs-lookup"><span data-stu-id="d87bd-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-222">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-222">**Subject**</span></span>|
|<span data-ttu-id="d87bd-223">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-223"></span></span>|
|<span data-ttu-id="d87bd-224">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-224">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-225">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-225"></span></span>|
|<span data-ttu-id="d87bd-226">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-226">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-227">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-227"></span></span>|
|<span data-ttu-id="d87bd-228">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-229">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-229"></span></span>|
|<span data-ttu-id="d87bd-230">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-231">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-231"></span></span>|
|<span data-ttu-id="d87bd-232">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-232">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-233">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-233"></span></span>|
|<span data-ttu-id="d87bd-234">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-235">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-235"></span></span>|
|<span data-ttu-id="d87bd-236">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-237">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-237"></span></span>|
|<span data-ttu-id="d87bd-238">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-239">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-239"></span></span>|
|<span data-ttu-id="d87bd-240">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-241">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-241"></span></span>|
|<span data-ttu-id="d87bd-242">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-243">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-243"></span></span>|
   
 <span data-ttu-id="d87bd-244">**D 信任根类 3 CA 2 2009**</span><span class="sxs-lookup"><span data-stu-id="d87bd-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-245">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-245">**Subject**</span></span>|
|<span data-ttu-id="d87bd-246">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-246"></span></span>|
|<span data-ttu-id="d87bd-247">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-247">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-248">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-248"></span></span>|
|<span data-ttu-id="d87bd-249">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-249">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-250">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-250"></span></span>|
|<span data-ttu-id="d87bd-251">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-252">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-252"></span></span>|
|<span data-ttu-id="d87bd-253">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-254">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-254"></span></span>|
|<span data-ttu-id="d87bd-255">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-255">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-256">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-256"></span></span>|
|<span data-ttu-id="d87bd-257">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-258">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-258"></span></span>|
|<span data-ttu-id="d87bd-259">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-260">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-260"></span></span>|
|<span data-ttu-id="d87bd-261">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-262">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-262"></span></span>|
|<span data-ttu-id="d87bd-263">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-264">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-264"></span></span>|
|<span data-ttu-id="d87bd-265">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-265">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-266">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-266"></span></span>|
   
 <span data-ttu-id="d87bd-267">**D 信任根类 3 CA 2 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="d87bd-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-268">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-268">**Subject**</span></span>|
|<span data-ttu-id="d87bd-269">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-269"></span></span>|
|<span data-ttu-id="d87bd-270">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-270">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-271">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-271"></span></span>|
|<span data-ttu-id="d87bd-272">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-272">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-273">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-273"></span></span>|
|<span data-ttu-id="d87bd-274">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-275">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-275"></span></span>|
|<span data-ttu-id="d87bd-276">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-277">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-277"></span></span>|
|<span data-ttu-id="d87bd-278">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-278">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-279">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-279"></span></span>|
|<span data-ttu-id="d87bd-280">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-281">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-281"></span></span>|
|<span data-ttu-id="d87bd-282">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-283">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-283"></span></span>|
|<span data-ttu-id="d87bd-284">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-285">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-285"></span></span>|
|<span data-ttu-id="d87bd-286">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-287">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-287"></span></span>|
|<span data-ttu-id="d87bd-288">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-288">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-289">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-289"></span></span>|
   
 <span data-ttu-id="d87bd-290">**DST 根 CA X3**</span><span class="sxs-lookup"><span data-stu-id="d87bd-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-291">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-291">**Subject**</span></span>|
|<span data-ttu-id="d87bd-292">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-292"></span></span>|
|<span data-ttu-id="d87bd-293">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-293">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-294">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-294"></span></span>|
|<span data-ttu-id="d87bd-295">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-295">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-296">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-296"></span></span>|
|<span data-ttu-id="d87bd-297">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-298">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-298"></span></span>|
|<span data-ttu-id="d87bd-299">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-300">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-300"></span></span>|
|<span data-ttu-id="d87bd-301">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-301">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-302">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-302"></span></span>|
|<span data-ttu-id="d87bd-303">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-304">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-304"></span></span>|
|<span data-ttu-id="d87bd-305">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-306">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-306"></span></span>|
|<span data-ttu-id="d87bd-307">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-308">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-308"></span></span>|
|<span data-ttu-id="d87bd-309">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-310">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-310"></span></span>|
   
 <span data-ttu-id="d87bd-311">**委托根证书颁发机构-G2**</span><span class="sxs-lookup"><span data-stu-id="d87bd-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-312">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-312">**Subject**</span></span>|
|<span data-ttu-id="d87bd-313">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-313"></span></span>|
|<span data-ttu-id="d87bd-314">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-314">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-315">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-315"></span></span>|
|<span data-ttu-id="d87bd-316">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-316">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-317">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-317"></span></span>|
|<span data-ttu-id="d87bd-318">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-319">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-319"></span></span>|
|<span data-ttu-id="d87bd-320">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-321">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-321"></span></span>|
|<span data-ttu-id="d87bd-322">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-322">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-323">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-323"></span></span>|
|<span data-ttu-id="d87bd-324">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-325">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-325"></span></span>|
|<span data-ttu-id="d87bd-326">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-327">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-327"></span></span>|
|<span data-ttu-id="d87bd-328">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-329">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-329"></span></span>|
|<span data-ttu-id="d87bd-330">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-331">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-331"></span></span>|
   
 <span data-ttu-id="d87bd-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-333">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-333">**Subject**</span></span>|
|<span data-ttu-id="d87bd-334">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-334"></span></span>|
|<span data-ttu-id="d87bd-335">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-335">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-336">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-336"></span></span>|
|<span data-ttu-id="d87bd-337">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-337">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-338">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-338"></span></span>|
|<span data-ttu-id="d87bd-339">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-340">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-340"></span></span>|
|<span data-ttu-id="d87bd-341">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-342">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-342"></span></span>|
|<span data-ttu-id="d87bd-343">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-343">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-344">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-344"></span></span>|
|<span data-ttu-id="d87bd-345">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-346">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-346"></span></span>|
|<span data-ttu-id="d87bd-347">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-348">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-348"></span></span>|
|<span data-ttu-id="d87bd-349">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-350">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-350"></span></span>|
|<span data-ttu-id="d87bd-351">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-352">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-352"></span></span>|
   
 <span data-ttu-id="d87bd-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="d87bd-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-354">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-354">**Subject**</span></span>|
|<span data-ttu-id="d87bd-355">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-355"></span></span>|
|<span data-ttu-id="d87bd-356">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-356">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-357">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-357"></span></span>|
|<span data-ttu-id="d87bd-358">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-358">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-359">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-359"></span></span>|
|<span data-ttu-id="d87bd-360">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-361">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-361"></span></span>|
|<span data-ttu-id="d87bd-362">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-363">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-363"></span></span>|
|<span data-ttu-id="d87bd-364">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-364">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-365">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-365"></span></span>|
|<span data-ttu-id="d87bd-366">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-367">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-367"></span></span>|
|<span data-ttu-id="d87bd-368">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-369">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-369"></span></span>|
|<span data-ttu-id="d87bd-370">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-371">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-371"></span></span>|
|<span data-ttu-id="d87bd-372">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-373">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-373"></span></span>|
|<span data-ttu-id="d87bd-374">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-375">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-375"></span></span>|
|<span data-ttu-id="d87bd-376">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-376">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-377">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-377"></span></span>|
   
 <span data-ttu-id="d87bd-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="d87bd-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-379">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-379">**Subject**</span></span>|
|<span data-ttu-id="d87bd-380">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-380"></span></span>|
|<span data-ttu-id="d87bd-381">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-381">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-382">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-382"></span></span>|
|<span data-ttu-id="d87bd-383">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-383">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-384">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-384"></span></span>|
|<span data-ttu-id="d87bd-385">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-386">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-386"></span></span>|
|<span data-ttu-id="d87bd-387">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-388">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-388"></span></span>|
|<span data-ttu-id="d87bd-389">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-389">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-390">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-390"></span></span>|
|<span data-ttu-id="d87bd-391">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-392">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-392"></span></span>|
|<span data-ttu-id="d87bd-393">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-394">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-394"></span></span>|
|<span data-ttu-id="d87bd-395">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-396">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-396"></span></span>|
|<span data-ttu-id="d87bd-397">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-398">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-398"></span></span>|
   
 <span data-ttu-id="d87bd-399">**thawte 主根 CA-G3**</span><span class="sxs-lookup"><span data-stu-id="d87bd-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-400">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-400">**Subject**</span></span>|
|<span data-ttu-id="d87bd-401">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-401"></span></span>|
|<span data-ttu-id="d87bd-402">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-402">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-403">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-403"></span></span>|
|<span data-ttu-id="d87bd-404">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-404">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-405">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-405"></span></span>|
|<span data-ttu-id="d87bd-406">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-407">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-407"></span></span>|
|<span data-ttu-id="d87bd-408">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-409">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-409"></span></span>|
|<span data-ttu-id="d87bd-410">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-410">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-411">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-411"></span></span>|
|<span data-ttu-id="d87bd-412">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-413">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-413"></span></span>|
|<span data-ttu-id="d87bd-414">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-415">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-415"></span></span>|
|<span data-ttu-id="d87bd-416">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-417">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-417"></span></span>|
|<span data-ttu-id="d87bd-418">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-419">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-419"></span></span>|
   
 <span data-ttu-id="d87bd-420">**VeriSign 类 3 主要公用证书颁发机构-G5**</span><span class="sxs-lookup"><span data-stu-id="d87bd-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-421">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-421">**Subject**</span></span>|
|<span data-ttu-id="d87bd-422">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-422"></span></span>|
|<span data-ttu-id="d87bd-423">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-423">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-424">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-424"></span></span>|
|<span data-ttu-id="d87bd-425">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-425">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-426">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-426"></span></span>|
|<span data-ttu-id="d87bd-427">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-428">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-428"></span></span>|
|<span data-ttu-id="d87bd-429">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-430">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-430"></span></span>|
|<span data-ttu-id="d87bd-431">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-431">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-432">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-432"></span></span>|
|<span data-ttu-id="d87bd-433">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-434">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-434"></span></span>|
|<span data-ttu-id="d87bd-435">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-436">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-436"></span></span>|
|<span data-ttu-id="d87bd-437">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-438">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-438"></span></span>|
|<span data-ttu-id="d87bd-439">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-440">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="d87bd-441">Office 365 中间证书详细信息</span><span class="sxs-lookup"><span data-stu-id="d87bd-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="d87bd-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="d87bd-442"></span></span>

 <span data-ttu-id="d87bd-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="d87bd-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-444">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-444">**Subject**</span></span>|
|<span data-ttu-id="d87bd-445">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-445"></span></span>|
|<span data-ttu-id="d87bd-446">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-446">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-447">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-447"></span></span>|
|<span data-ttu-id="d87bd-448">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-448">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-449">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-449"></span></span>|
|<span data-ttu-id="d87bd-450">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-450">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-451">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-451"></span></span>|
|<span data-ttu-id="d87bd-452">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-453">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-453"></span></span>|
|<span data-ttu-id="d87bd-454">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-455">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-455"></span></span>|
|<span data-ttu-id="d87bd-456">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-456">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-457">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-457"></span></span>|
|<span data-ttu-id="d87bd-458">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-459">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-459"></span></span>|
|<span data-ttu-id="d87bd-460">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-461">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-461"></span></span>|
|<span data-ttu-id="d87bd-462">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-463">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-463"></span></span>|
|<span data-ttu-id="d87bd-464">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-465">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-465"></span></span>|
|<span data-ttu-id="d87bd-466">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-467">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-467"></span></span>|
|<span data-ttu-id="d87bd-468">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-468">**AIA URLs**</span></span>|
|<span data-ttu-id="d87bd-469">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-469"></span></span>|
|<span data-ttu-id="d87bd-470">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-470">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-471">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-471"></span></span>|
|<span data-ttu-id="d87bd-472">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-473">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-473"></span></span>|
   
 <span data-ttu-id="d87bd-474">**D 信任 SSL 类 3 CA 1 2009**</span><span class="sxs-lookup"><span data-stu-id="d87bd-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-475">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-475">**Subject**</span></span>|
|<span data-ttu-id="d87bd-476">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-476"></span></span>|
|<span data-ttu-id="d87bd-477">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-477">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-478">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-478"></span></span>|
|<span data-ttu-id="d87bd-479">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="d87bd-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="d87bd-480">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-480"></span></span>|
|<span data-ttu-id="d87bd-481">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-481">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-482">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-482"></span></span>|
|<span data-ttu-id="d87bd-483">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-483">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-484">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-484"></span></span>|
|<span data-ttu-id="d87bd-485">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-486">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-486"></span></span>|
|<span data-ttu-id="d87bd-487">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-488">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-488"></span></span>|
|<span data-ttu-id="d87bd-489">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-489">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-490">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-490"></span></span>|
|<span data-ttu-id="d87bd-491">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-492">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-492"></span></span>|
|<span data-ttu-id="d87bd-493">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-494">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-494"></span></span>|
|<span data-ttu-id="d87bd-495">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-496">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-496"></span></span>|
|<span data-ttu-id="d87bd-497">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-498">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-498"></span></span>|
|<span data-ttu-id="d87bd-499">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-500">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-500"></span></span>|
|<span data-ttu-id="d87bd-501">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-501">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-502">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-502"></span></span>|
|<span data-ttu-id="d87bd-503">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-504">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-504"></span></span>|
   
 <span data-ttu-id="d87bd-505">**D 信任 SSL 类 3 CA 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="d87bd-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-506">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-506">**Subject**</span></span>|
|<span data-ttu-id="d87bd-507">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-507"></span></span>|
|<span data-ttu-id="d87bd-508">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-508">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-509">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-509"></span></span>|
|<span data-ttu-id="d87bd-510">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="d87bd-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="d87bd-511">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-511"></span></span>|
|<span data-ttu-id="d87bd-512">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-512">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-513">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-513"></span></span>|
|<span data-ttu-id="d87bd-514">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-514">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-515">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-515"></span></span>|
|<span data-ttu-id="d87bd-516">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-517">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-517"></span></span>|
|<span data-ttu-id="d87bd-518">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-519">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-519"></span></span>|
|<span data-ttu-id="d87bd-520">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-520">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-521">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-521"></span></span>|
|<span data-ttu-id="d87bd-522">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-523">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-523"></span></span>|
|<span data-ttu-id="d87bd-524">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-525">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-525"></span></span>|
|<span data-ttu-id="d87bd-526">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-527">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-527"></span></span>|
|<span data-ttu-id="d87bd-528">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-529">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-529"></span></span>|
|<span data-ttu-id="d87bd-530">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-531">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-531"></span></span>|
|<span data-ttu-id="d87bd-532">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-532">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-533">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-533"></span></span>|
|<span data-ttu-id="d87bd-534">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-535">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-535"></span></span>|
   
 <span data-ttu-id="d87bd-536">**DigiCert 云服务 CA-1**</span><span class="sxs-lookup"><span data-stu-id="d87bd-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-537">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-537">**Subject**</span></span>|
|<span data-ttu-id="d87bd-538">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-538"></span></span>|
|<span data-ttu-id="d87bd-539">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-539">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-540">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-540"></span></span>|
|<span data-ttu-id="d87bd-541">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-541">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-542">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-542"></span></span>|
|<span data-ttu-id="d87bd-543">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-543">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-544">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-544"></span></span>|
|<span data-ttu-id="d87bd-545">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-546">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-546"></span></span>|
|<span data-ttu-id="d87bd-547">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-548">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-548"></span></span>|
|<span data-ttu-id="d87bd-549">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-549">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-550">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-550"></span></span>|
|<span data-ttu-id="d87bd-551">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-552">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-552"></span></span>|
|<span data-ttu-id="d87bd-553">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-554">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-554"></span></span>|
|<span data-ttu-id="d87bd-555">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-556">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-556"></span></span>|
|<span data-ttu-id="d87bd-557">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-558">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-558"></span></span>|
|<span data-ttu-id="d87bd-559">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-560">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-560"></span></span>|
|<span data-ttu-id="d87bd-561">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-561">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-562">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-562"></span></span>|
|<span data-ttu-id="d87bd-563">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-564">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-564"></span></span>|
   
 <span data-ttu-id="d87bd-565">**DigiCert SHA2 高保证服务器 CA**</span><span class="sxs-lookup"><span data-stu-id="d87bd-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-566">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-566">**Subject**</span></span>|
|<span data-ttu-id="d87bd-567">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-567"></span></span>|
|<span data-ttu-id="d87bd-568">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-568">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-569">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-569"></span></span>|
|<span data-ttu-id="d87bd-570">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-570">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-571">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-571"></span></span>|
|<span data-ttu-id="d87bd-572">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-572">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-573">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-573"></span></span>|
|<span data-ttu-id="d87bd-574">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-575">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-575"></span></span>|
|<span data-ttu-id="d87bd-576">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-577">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-577"></span></span>|
|<span data-ttu-id="d87bd-578">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-578">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-579">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-579"></span></span>|
|<span data-ttu-id="d87bd-580">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-581">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-581"></span></span>|
|<span data-ttu-id="d87bd-582">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-583">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-583"></span></span>|
|<span data-ttu-id="d87bd-584">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-585">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-585"></span></span>|
|<span data-ttu-id="d87bd-586">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-587">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-587"></span></span>|
|<span data-ttu-id="d87bd-588">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-589">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-589"></span></span>|
|<span data-ttu-id="d87bd-590">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-590">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-591">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-591"></span></span>|
|<span data-ttu-id="d87bd-592">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-593">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-593"></span></span>|
   
 <span data-ttu-id="d87bd-594">**DigiCert SHA2 安全服务器 CA**</span><span class="sxs-lookup"><span data-stu-id="d87bd-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-595">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-595">**Subject**</span></span>|
|<span data-ttu-id="d87bd-596">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-596"></span></span>|
|<span data-ttu-id="d87bd-597">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-597">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-598">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-598"></span></span>|
|<span data-ttu-id="d87bd-599">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-599">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-600">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-600"></span></span>|
|<span data-ttu-id="d87bd-601">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-601">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-602">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-602"></span></span>|
|<span data-ttu-id="d87bd-603">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-604">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-604"></span></span>|
|<span data-ttu-id="d87bd-605">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-606">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-606"></span></span>|
|<span data-ttu-id="d87bd-607">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-607">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-608">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-608"></span></span>|
|<span data-ttu-id="d87bd-609">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-610">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-610"></span></span>|
|<span data-ttu-id="d87bd-611">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-612">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-612"></span></span>|
|<span data-ttu-id="d87bd-613">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-614">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-614"></span></span>|
|<span data-ttu-id="d87bd-615">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-616">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-616"></span></span>|
|<span data-ttu-id="d87bd-617">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-618">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-618"></span></span>|
|<span data-ttu-id="d87bd-619">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-619">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-620">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-620"></span></span>|
|<span data-ttu-id="d87bd-621">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-622">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-622"></span></span>|
   
 <span data-ttu-id="d87bd-623">**委托 L1C 的证书颁发机构-**</span><span class="sxs-lookup"><span data-stu-id="d87bd-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-624">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-624">**Subject**</span></span>|
|<span data-ttu-id="d87bd-625">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-625"></span></span>|
|<span data-ttu-id="d87bd-626">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-626">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-627">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-627"></span></span>|
|<span data-ttu-id="d87bd-628">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-628">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-629">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-629"></span></span>|
|<span data-ttu-id="d87bd-630">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-630">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-631">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-631"></span></span>|
|<span data-ttu-id="d87bd-632">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-633">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-633"></span></span>|
|<span data-ttu-id="d87bd-634">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-635">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-635"></span></span>|
|<span data-ttu-id="d87bd-636">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-636">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-637">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-637"></span></span>|
|<span data-ttu-id="d87bd-638">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-639">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-639"></span></span>|
|<span data-ttu-id="d87bd-640">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-641">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-641"></span></span>|
|<span data-ttu-id="d87bd-642">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-643">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-643"></span></span>|
|<span data-ttu-id="d87bd-644">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-645">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-645"></span></span>|
|<span data-ttu-id="d87bd-646">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-647">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-647"></span></span>|
|<span data-ttu-id="d87bd-648">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-648">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-649">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-649"></span></span>|
|<span data-ttu-id="d87bd-650">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-651">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-651"></span></span>|
   
 <span data-ttu-id="d87bd-652">**委托 L1K 的证书颁发机构-**</span><span class="sxs-lookup"><span data-stu-id="d87bd-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-653">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-653">**Subject**</span></span>|
|<span data-ttu-id="d87bd-654">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-654"></span></span>|
|<span data-ttu-id="d87bd-655">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-655">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-656">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-656"></span></span>|
|<span data-ttu-id="d87bd-657">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-657">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-658">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-658"></span></span>|
|<span data-ttu-id="d87bd-659">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-659">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-660">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-660"></span></span>|
|<span data-ttu-id="d87bd-661">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-662">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-662"></span></span>|
|<span data-ttu-id="d87bd-663">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-664">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-664"></span></span>|
|<span data-ttu-id="d87bd-665">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-665">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-666">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-666"></span></span>|
|<span data-ttu-id="d87bd-667">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-668">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-668"></span></span>|
|<span data-ttu-id="d87bd-669">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-670">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-670"></span></span>|
|<span data-ttu-id="d87bd-671">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-672">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-672"></span></span>|
|<span data-ttu-id="d87bd-673">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-674">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-674"></span></span>|
|<span data-ttu-id="d87bd-675">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-676">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-676"></span></span>|
|<span data-ttu-id="d87bd-677">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-677">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-678">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-678"></span></span>|
|<span data-ttu-id="d87bd-679">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-680">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-680"></span></span>|
   
 <span data-ttu-id="d87bd-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="d87bd-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-682">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-682">**Subject**</span></span>|
|<span data-ttu-id="d87bd-683">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-683"></span></span>|
|<span data-ttu-id="d87bd-684">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-684">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-685">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-685"></span></span>|
|<span data-ttu-id="d87bd-686">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-686">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-687">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-687"></span></span>|
|<span data-ttu-id="d87bd-688">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-688">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-689">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-689"></span></span>|
|<span data-ttu-id="d87bd-690">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-691">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-691"></span></span>|
|<span data-ttu-id="d87bd-692">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-693">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-693"></span></span>|
|<span data-ttu-id="d87bd-694">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-694">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-695">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-695"></span></span>|
|<span data-ttu-id="d87bd-696">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-697">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-697"></span></span>|
|<span data-ttu-id="d87bd-698">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-699">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-699"></span></span>|
|<span data-ttu-id="d87bd-700">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-701">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-701"></span></span>|
|<span data-ttu-id="d87bd-702">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-703">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-703"></span></span>|
|<span data-ttu-id="d87bd-704">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-705">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-705"></span></span>|
|<span data-ttu-id="d87bd-706">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-706">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-707">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-707"></span></span>|
|<span data-ttu-id="d87bd-708">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-709">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-709"></span></span>|
   
 <span data-ttu-id="d87bd-710">**GlobalSign 扩展验证 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="d87bd-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-711">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-711">**Subject**</span></span>|
|<span data-ttu-id="d87bd-712">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-712"></span></span>|
|<span data-ttu-id="d87bd-713">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-713">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-714">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-714"></span></span>|
|<span data-ttu-id="d87bd-715">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-715">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-716">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-716"></span></span>|
|<span data-ttu-id="d87bd-717">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-717">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-718">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-718"></span></span>|
|<span data-ttu-id="d87bd-719">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-720">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-720"></span></span>|
|<span data-ttu-id="d87bd-721">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-722">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-722"></span></span>|
|<span data-ttu-id="d87bd-723">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-723">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-724">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-724"></span></span>|
|<span data-ttu-id="d87bd-725">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-726">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-726"></span></span>|
|<span data-ttu-id="d87bd-727">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-728">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-728"></span></span>|
|<span data-ttu-id="d87bd-729">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-730">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-730"></span></span>|
|<span data-ttu-id="d87bd-731">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-732">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-732"></span></span>|
|<span data-ttu-id="d87bd-733">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-734">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-734"></span></span>|
|<span data-ttu-id="d87bd-735">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-735">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-736">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-736"></span></span>|
|<span data-ttu-id="d87bd-737">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-738">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-738"></span></span>|
   
 <span data-ttu-id="d87bd-739">**GlobalSign 扩展验证 CA-SHA256-G3**</span><span class="sxs-lookup"><span data-stu-id="d87bd-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-740">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-740">**Subject**</span></span>|
|<span data-ttu-id="d87bd-741">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-741"></span></span>|
|<span data-ttu-id="d87bd-742">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-742">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-743">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-743"></span></span>|
|<span data-ttu-id="d87bd-744">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-744">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-745">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-745"></span></span>|
|<span data-ttu-id="d87bd-746">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-746">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-747">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-747"></span></span>|
|<span data-ttu-id="d87bd-748">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-749">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-749"></span></span>|
|<span data-ttu-id="d87bd-750">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-751">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-751"></span></span>|
|<span data-ttu-id="d87bd-752">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-752">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-753">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-753"></span></span>|
|<span data-ttu-id="d87bd-754">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-755">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-755"></span></span>|
|<span data-ttu-id="d87bd-756">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-757">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-757"></span></span>|
|<span data-ttu-id="d87bd-758">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-759">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-759"></span></span>|
|<span data-ttu-id="d87bd-760">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-761">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-761"></span></span>|
|<span data-ttu-id="d87bd-762">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-763">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-763"></span></span>|
|<span data-ttu-id="d87bd-764">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-764">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-765">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-765"></span></span>|
|<span data-ttu-id="d87bd-766">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-767">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-767"></span></span>|
   
 <span data-ttu-id="d87bd-768">**GlobalSign 组织验证 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="d87bd-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-769">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-769">**Subject**</span></span>|
|<span data-ttu-id="d87bd-770">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-770"></span></span>|
|<span data-ttu-id="d87bd-771">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-771">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-772">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-772"></span></span>|
|<span data-ttu-id="d87bd-773">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-773">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-774">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-774"></span></span>|
|<span data-ttu-id="d87bd-775">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-775">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-776">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-776"></span></span>|
|<span data-ttu-id="d87bd-777">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-778">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-778"></span></span>|
|<span data-ttu-id="d87bd-779">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-780">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-780"></span></span>|
|<span data-ttu-id="d87bd-781">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-781">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-782">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-782"></span></span>|
|<span data-ttu-id="d87bd-783">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-784">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-784"></span></span>|
|<span data-ttu-id="d87bd-785">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-786">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-786"></span></span>|
|<span data-ttu-id="d87bd-787">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-788">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-788"></span></span>|
|<span data-ttu-id="d87bd-789">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-790">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-790"></span></span>|
|<span data-ttu-id="d87bd-791">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-792">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-792"></span></span>|
|<span data-ttu-id="d87bd-793">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-793">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-794">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-794"></span></span>|
|<span data-ttu-id="d87bd-795">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-796">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-796"></span></span>|
   
 <span data-ttu-id="d87bd-797">**GlobalSign 组织验证 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="d87bd-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-798">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-798">**Subject**</span></span>|
|<span data-ttu-id="d87bd-799">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-799"></span></span>|
|<span data-ttu-id="d87bd-800">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-800">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-801">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-801"></span></span>|
|<span data-ttu-id="d87bd-802">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-802">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-803">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-803"></span></span>|
|<span data-ttu-id="d87bd-804">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-804">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-805">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-805"></span></span>|
|<span data-ttu-id="d87bd-806">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-807">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-807"></span></span>|
|<span data-ttu-id="d87bd-808">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-809">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-809"></span></span>|
|<span data-ttu-id="d87bd-810">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-810">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-811">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-811"></span></span>|
|<span data-ttu-id="d87bd-812">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-813">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-813"></span></span>|
|<span data-ttu-id="d87bd-814">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-815">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-815"></span></span>|
|<span data-ttu-id="d87bd-816">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-817">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-817"></span></span>|
|<span data-ttu-id="d87bd-818">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-819">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-819"></span></span>|
|<span data-ttu-id="d87bd-820">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-821">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-821"></span></span>|
|<span data-ttu-id="d87bd-822">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-822">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-823">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-823"></span></span>|
|<span data-ttu-id="d87bd-824">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-825">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-825"></span></span>|
   
 <span data-ttu-id="d87bd-826">**让我们加密证书颁发机构 X3**</span><span class="sxs-lookup"><span data-stu-id="d87bd-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-827">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-827">**Subject**</span></span>|
|<span data-ttu-id="d87bd-828">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-828"></span></span>|
|<span data-ttu-id="d87bd-829">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-829">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-830">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-830"></span></span>|
|<span data-ttu-id="d87bd-831">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-831">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-832">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-832"></span></span>|
|<span data-ttu-id="d87bd-833">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-833">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-834">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-834"></span></span>|
|<span data-ttu-id="d87bd-835">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-836">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-836"></span></span>|
|<span data-ttu-id="d87bd-837">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-838">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-838"></span></span>|
|<span data-ttu-id="d87bd-839">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-839">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-840">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-840"></span></span>|
|<span data-ttu-id="d87bd-841">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-842">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-842"></span></span>|
|<span data-ttu-id="d87bd-843">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-844">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-844"></span></span>|
|<span data-ttu-id="d87bd-845">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-846">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-846"></span></span>|
|<span data-ttu-id="d87bd-847">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-848">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-848"></span></span>|
|<span data-ttu-id="d87bd-849">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-850">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-850"></span></span>|
|<span data-ttu-id="d87bd-851">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-851">**AIA URLs**</span></span>|
|<span data-ttu-id="d87bd-852">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-852"></span></span>|
|<span data-ttu-id="d87bd-853">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-853">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-854">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-854"></span></span>|
|<span data-ttu-id="d87bd-855">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-856">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-856"></span></span>|
   
 <span data-ttu-id="d87bd-857">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="d87bd-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-858">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-858">**Subject**</span></span>|
|<span data-ttu-id="d87bd-859">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-859"></span></span>|
|<span data-ttu-id="d87bd-860">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-860">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-861">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-861"></span></span>|
|<span data-ttu-id="d87bd-862">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-862">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-863">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-863"></span></span>|
|<span data-ttu-id="d87bd-864">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-864">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-865">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-865"></span></span>|
|<span data-ttu-id="d87bd-866">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-867">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-867"></span></span>|
|<span data-ttu-id="d87bd-868">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-869">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-869"></span></span>|
|<span data-ttu-id="d87bd-870">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-870">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-871">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-871"></span></span>|
|<span data-ttu-id="d87bd-872">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-873">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-873"></span></span>|
|<span data-ttu-id="d87bd-874">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-875">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-875"></span></span>|
|<span data-ttu-id="d87bd-876">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-877">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-877"></span></span>|
|<span data-ttu-id="d87bd-878">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-879">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-879"></span></span>|
|<span data-ttu-id="d87bd-880">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-881">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-881"></span></span>|
|<span data-ttu-id="d87bd-882">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-882">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-883">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-883"></span></span>|
   
 <span data-ttu-id="d87bd-884">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="d87bd-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-885">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-885">**Subject**</span></span>|
|<span data-ttu-id="d87bd-886">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-886"></span></span>|
|<span data-ttu-id="d87bd-887">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-887">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-888">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-888"></span></span>|
|<span data-ttu-id="d87bd-889">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-889">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-890">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-890"></span></span>|
|<span data-ttu-id="d87bd-891">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-891">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-892">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-892"></span></span>|
|<span data-ttu-id="d87bd-893">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-894">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-894"></span></span>|
|<span data-ttu-id="d87bd-895">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-896">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-896"></span></span>|
|<span data-ttu-id="d87bd-897">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-897">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-898">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-898"></span></span>|
|<span data-ttu-id="d87bd-899">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-900">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-900"></span></span>|
|<span data-ttu-id="d87bd-901">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-902">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-902"></span></span>|
|<span data-ttu-id="d87bd-903">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-904">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-904"></span></span>|
|<span data-ttu-id="d87bd-905">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-906">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-906"></span></span>|
|<span data-ttu-id="d87bd-907">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-908">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-908"></span></span>|
|<span data-ttu-id="d87bd-909">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-909">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-910">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-910"></span></span>|
|<span data-ttu-id="d87bd-911">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-912">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-912"></span></span>|
   
 <span data-ttu-id="d87bd-913">**Microsoft IT TLS CA 1**</span><span class="sxs-lookup"><span data-stu-id="d87bd-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-914">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-914">**Subject**</span></span>|
|<span data-ttu-id="d87bd-915">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-915"></span></span>|
|<span data-ttu-id="d87bd-916">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-916">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-917">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-917"></span></span>|
|<span data-ttu-id="d87bd-918">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-918">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-919">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-919"></span></span>|
|<span data-ttu-id="d87bd-920">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-920">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-921">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-921"></span></span>|
|<span data-ttu-id="d87bd-922">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-923">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-923"></span></span>|
|<span data-ttu-id="d87bd-924">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-925">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-925"></span></span>|
|<span data-ttu-id="d87bd-926">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-926">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-927">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-927"></span></span>|
|<span data-ttu-id="d87bd-928">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-929">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-929"></span></span>|
|<span data-ttu-id="d87bd-930">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-931">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-931"></span></span>|
|<span data-ttu-id="d87bd-932">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-933">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-933"></span></span>|
|<span data-ttu-id="d87bd-934">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-935">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-935"></span></span>|
|<span data-ttu-id="d87bd-936">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-937">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-937"></span></span>|
|<span data-ttu-id="d87bd-938">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-938">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-939">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-939"></span></span>|
|<span data-ttu-id="d87bd-940">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-941">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-941"></span></span>|
   
 <span data-ttu-id="d87bd-942">**Microsoft IT TLS CA 2**</span><span class="sxs-lookup"><span data-stu-id="d87bd-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-943">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-943">**Subject**</span></span>|
|<span data-ttu-id="d87bd-944">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-944"></span></span>|
|<span data-ttu-id="d87bd-945">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-945">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-946">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-946"></span></span>|
|<span data-ttu-id="d87bd-947">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-947">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-948">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-948"></span></span>|
|<span data-ttu-id="d87bd-949">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-949">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-950">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-950"></span></span>|
|<span data-ttu-id="d87bd-951">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-952">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-952"></span></span>|
|<span data-ttu-id="d87bd-953">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-954">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-954"></span></span>|
|<span data-ttu-id="d87bd-955">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-955">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-956">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-956"></span></span>|
|<span data-ttu-id="d87bd-957">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-958">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-958"></span></span>|
|<span data-ttu-id="d87bd-959">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-960">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-960"></span></span>|
|<span data-ttu-id="d87bd-961">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-962">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-962"></span></span>|
|<span data-ttu-id="d87bd-963">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-964">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-964"></span></span>|
|<span data-ttu-id="d87bd-965">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-966">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-966"></span></span>|
|<span data-ttu-id="d87bd-967">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-967">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-968">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-968"></span></span>|
|<span data-ttu-id="d87bd-969">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-970">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-970"></span></span>|
   
 <span data-ttu-id="d87bd-971">**Microsoft IT TLS CA 4**</span><span class="sxs-lookup"><span data-stu-id="d87bd-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-972">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-972">**Subject**</span></span>|
|<span data-ttu-id="d87bd-973">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-973"></span></span>|
|<span data-ttu-id="d87bd-974">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-974">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-975">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-975"></span></span>|
|<span data-ttu-id="d87bd-976">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-976">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-977">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-977"></span></span>|
|<span data-ttu-id="d87bd-978">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-978">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-979">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-979"></span></span>|
|<span data-ttu-id="d87bd-980">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-981">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-981"></span></span>|
|<span data-ttu-id="d87bd-982">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-983">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-983"></span></span>|
|<span data-ttu-id="d87bd-984">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-984">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-985">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-985"></span></span>|
|<span data-ttu-id="d87bd-986">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-987">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-987"></span></span>|
|<span data-ttu-id="d87bd-988">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-989">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-989"></span></span>|
|<span data-ttu-id="d87bd-990">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-991">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-991"></span></span>|
|<span data-ttu-id="d87bd-992">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-993">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-993"></span></span>|
|<span data-ttu-id="d87bd-994">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-995">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-995"></span></span>|
|<span data-ttu-id="d87bd-996">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-996">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-997">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-997"></span></span>|
|<span data-ttu-id="d87bd-998">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-999">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-999"></span></span>|
   
 <span data-ttu-id="d87bd-1000">**Microsoft IT TLS CA 5**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-1001">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1001">**Subject**</span></span>|
|<span data-ttu-id="d87bd-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1002"></span></span>|
|<span data-ttu-id="d87bd-1003">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1003">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1004"></span></span>|
|<span data-ttu-id="d87bd-1005">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1005">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1006"></span></span>|
|<span data-ttu-id="d87bd-1007">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1008"></span></span>|
|<span data-ttu-id="d87bd-1009">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1010"></span></span>|
|<span data-ttu-id="d87bd-1011">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1012"></span></span>|
|<span data-ttu-id="d87bd-1013">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1014"></span></span>|
|<span data-ttu-id="d87bd-1015">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1016"></span></span>|
|<span data-ttu-id="d87bd-1017">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1018"></span></span>|
|<span data-ttu-id="d87bd-1019">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1020"></span></span>|
|<span data-ttu-id="d87bd-1021">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1022"></span></span>|
|<span data-ttu-id="d87bd-1023">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1024"></span></span>|
|<span data-ttu-id="d87bd-1025">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1026"></span></span>|
|<span data-ttu-id="d87bd-1027">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1028"></span></span>|
   
 <span data-ttu-id="d87bd-1029">**Symantec 类 3 EV SSL CA G3**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-1030">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1030">**Subject**</span></span>|
|<span data-ttu-id="d87bd-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1031"></span></span>|
|<span data-ttu-id="d87bd-1032">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1032">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1033"></span></span>|
|<span data-ttu-id="d87bd-1034">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="d87bd-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1035"></span></span>|
|<span data-ttu-id="d87bd-1036">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1036">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1037"></span></span>|
|<span data-ttu-id="d87bd-1038">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1039"></span></span>|
|<span data-ttu-id="d87bd-1040">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1041"></span></span>|
|<span data-ttu-id="d87bd-1042">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1043"></span></span>|
|<span data-ttu-id="d87bd-1044">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1045"></span></span>|
|<span data-ttu-id="d87bd-1046">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1047"></span></span>|
|<span data-ttu-id="d87bd-1048">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1049"></span></span>|
|<span data-ttu-id="d87bd-1050">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1051"></span></span>|
|<span data-ttu-id="d87bd-1052">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1053"></span></span>|
|<span data-ttu-id="d87bd-1054">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1055"></span></span>|
|<span data-ttu-id="d87bd-1056">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1057"></span></span>|
|<span data-ttu-id="d87bd-1058">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1059"></span></span>|
   
 <span data-ttu-id="d87bd-1060">**Symantec 类 3 安全服务器 CA-G4**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-1061">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1061">**Subject**</span></span>|
|<span data-ttu-id="d87bd-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1062"></span></span>|
|<span data-ttu-id="d87bd-1063">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1063">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1064"></span></span>|
|<span data-ttu-id="d87bd-1065">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="d87bd-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1066"></span></span>|
|<span data-ttu-id="d87bd-1067">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1067">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1068"></span></span>|
|<span data-ttu-id="d87bd-1069">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1070"></span></span>|
|<span data-ttu-id="d87bd-1071">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1072"></span></span>|
|<span data-ttu-id="d87bd-1073">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1074"></span></span>|
|<span data-ttu-id="d87bd-1075">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1076"></span></span>|
|<span data-ttu-id="d87bd-1077">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1078"></span></span>|
|<span data-ttu-id="d87bd-1079">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1080"></span></span>|
|<span data-ttu-id="d87bd-1081">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1082"></span></span>|
|<span data-ttu-id="d87bd-1083">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1084"></span></span>|
|<span data-ttu-id="d87bd-1085">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1086"></span></span>|
|<span data-ttu-id="d87bd-1087">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1088"></span></span>|
|<span data-ttu-id="d87bd-1089">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1090"></span></span>|
   
 <span data-ttu-id="d87bd-1091">**thawte SHA256 SSL CA**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-1092">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1092">**Subject**</span></span>|
|<span data-ttu-id="d87bd-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1093"></span></span>|
|<span data-ttu-id="d87bd-1094">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1094">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1095"></span></span>|
|<span data-ttu-id="d87bd-1096">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="d87bd-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1097"></span></span>|
|<span data-ttu-id="d87bd-1098">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1098">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1099"></span></span>|
|<span data-ttu-id="d87bd-1100">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1101"></span></span>|
|<span data-ttu-id="d87bd-1102">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1103"></span></span>|
|<span data-ttu-id="d87bd-1104">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1105"></span></span>|
|<span data-ttu-id="d87bd-1106">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1107"></span></span>|
|<span data-ttu-id="d87bd-1108">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1109"></span></span>|
|<span data-ttu-id="d87bd-1110">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1111"></span></span>|
|<span data-ttu-id="d87bd-1112">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1113"></span></span>|
|<span data-ttu-id="d87bd-1114">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1115"></span></span>|
|<span data-ttu-id="d87bd-1116">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1117"></span></span>|
|<span data-ttu-id="d87bd-1118">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1119"></span></span>|
|<span data-ttu-id="d87bd-1120">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1121"></span></span>|
   
 <span data-ttu-id="d87bd-1122">**Verizon Akamai SureServer CA G14 SHA2**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="d87bd-1123">**主题**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1123">**Subject**</span></span>|
|<span data-ttu-id="d87bd-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1124"></span></span>|
|<span data-ttu-id="d87bd-1125">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1125">**Issuer**</span></span>|
|<span data-ttu-id="d87bd-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1126"></span></span>|
|<span data-ttu-id="d87bd-1127">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1127">**Serial Number**</span></span>|
|<span data-ttu-id="d87bd-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1128"></span></span>|
|<span data-ttu-id="d87bd-1129">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="d87bd-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1130"></span></span>|
|<span data-ttu-id="d87bd-1131">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="d87bd-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1132"></span></span>|
|<span data-ttu-id="d87bd-1133">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="d87bd-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1134"></span></span>|
|<span data-ttu-id="d87bd-1135">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="d87bd-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1136"></span></span>|
|<span data-ttu-id="d87bd-1137">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1138"></span></span>|
|<span data-ttu-id="d87bd-1139">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="d87bd-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1140"></span></span>|
|<span data-ttu-id="d87bd-1141">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="d87bd-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1142"></span></span>|
|<span data-ttu-id="d87bd-1143">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1144"></span></span>|
|<span data-ttu-id="d87bd-1145">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="d87bd-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1146"></span></span>|
|<span data-ttu-id="d87bd-1147">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="d87bd-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1148"></span></span>|
|<span data-ttu-id="d87bd-1149">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="d87bd-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1150"></span></span>|
|<span data-ttu-id="d87bd-1151">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="d87bd-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="d87bd-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="d87bd-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="d87bd-1153">额外的证书路径</span><span class="sxs-lookup"><span data-stu-id="d87bd-1153">Additional certificate paths</span></span>
<span data-ttu-id="d87bd-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="d87bd-1154"></span></span>

<span data-ttu-id="d87bd-1155">以下包括旧的证书不包括上面且随着时间的推移将与上面的列表合并。</span><span class="sxs-lookup"><span data-stu-id="d87bd-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
```
evsecure-aia.verisign.com
sa.symcb.com
sd.symcb.com
*.omniroot.com
*.verisign.com
*.symcb.com
*.symcd.com
*.verisign.net
*.geotrust.com
*.entrust.net
*.public-trust.com
EVIntl-ocsp.verisign.com
EVSecure-ocsp.verisign.com
isrg.trustid.ocsp.identrust.com
ocsp.digicert.com
ocsp.entrust.net
ocsp.globalsign.com/ExtendedSSLSHA256CACross
ocsp.globalsign.com/rootr1
ocsp.globalsign.com/rootr2
ocsp2.globalsign.com/rootr3
ocsp.int-x3.letsencrypt.org/
ocsp.msocsp.com
ocsp.omniroot.com/baltimoreroot
ocsp2.globalsign.com/gsextendvalsha2g3r3
ocsp2.globalsign.com/gsorganizationvalsha2g2
ocsp2.globalsign.com/gsorganizationvalsha2g3
ocsp2.globalsign.com/rootr3
ocspx.digicert.com
s2.symcb.com
sr.symcd.com
su.symcd.com
vassg142.ocsp.omniroot.com
cdp1.public-trust.com/CRL/Omniroot2025.crl
crl.entrust.net/2048ca.crl
crl.entrust.net/g2ca.crl
crl.entrust.net/level1k.crl
crl.entrust.net/rootca1.crl
crl.globalsign.com/gs/gsextendvalsha2g3r3.crl
crl.globalsign.com/gs/gsorganizationvalsha2g2.crl
crl.globalsign.com/gsorganizationvalsha2g3.crl
crl.globalsign.com/root.crl
crl.globalsign.net/root-r2.crl
crl.globalsign.com/root-r3.crl
crl.globalsign.net/root.crl
crl.identrust.com/DSTROOTCAX3CRL.crl
crl.microsoft.com/pki/mscorp/crl/msitwww1.crl
crl.microsoft.com/pki/mscorp/crl/msitwww2.crl
crl3.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl3.digicert.com/DigiCertGlobalRootCA.crl
crl3.digicert.com/sha2-ev-server-g1.crl
crl3.digicert.com/sha2-ha-server-g5.crl
crl3.digicert.com/ssca-sha2-g5.crl
crl4.digicert.com/DigiCertCloudServicesCA-1-g1.crl
crl4.digicert.com/DigiCertGlobalRootCA.crl
crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl
crl4.digicert.com/sha2-ev-server-g1.crl
crl4.digicert.com/sha2-ha-server-g5.crl
crl4.digicert.com/ssca-sha2-g5.crl
EVIntl-crl.verisign.com/EVIntl2006.crl
EVSecure-crl.verisign.com/pca3-g5.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww1.crl
mscrl.microsoft.com/pki/mscorp/crl/msitwww2.crl
s1.symcb.com/pca3-g5.crl
sr.symcb.com/sr.crl
su.symcb.com/su.crl
vassg142.crl.omniroot.com/vassg142.crl
aia.entrust.net/l1k-chain256.cer
apps.identrust.com/roots/dstrootcax3.p7c
https://cacert.a.omniroot.com/vassg142.crt
https://cacert.a.omniroot.com/vassg142.der
https://cacert.omniroot.com/baltimoreroot.crt
https://cacert.omniroot.com/baltimoreroot.der
cacerts.digicert.com/DigiCertCloudServicesCA-1.crt
cacerts.digicert.com/DigiCertSHA2ExtendedValidationServerCA.crt
cacerts.digicert.com/DigiCertSHA2HighAssuranceServerCA.crt
cacerts.digicert.com/DigiCertSHA2SecureServerCA.crt
cert.int-x3.letsencrypt.org/
EVIntl-aia.verisign.com/EVIntl2006.cer
secure.globalsign.com/cacert/gsextendvalsha2g2r2.crt
secure.globalsign.com/cacert/gsextendvalsha2g3r3.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g2r1.crt
secure.globalsign.com/cacert/gsorganizationvalsha2g3.crt
sr.symcb.com/sr.crt
su.symcb.com/su.crt
https://www.digicert.com/CACerts/DigiCertGlobalRootCA.crt
https://www.digicert.com/CACerts/DigiCertHighAssuranceEVRootCA.crt
www.microsoft.com/pki/mscorp/msitwww1.crt
www.microsoft.com/pki/mscorp/msitwww2.crt

```


