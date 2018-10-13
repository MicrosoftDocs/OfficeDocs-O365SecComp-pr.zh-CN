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
ms.sourcegitcommit: 13f40ff7c1799152bf45af2d8110f4f3235b770a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/12/2018
ms.locfileid: "25549741"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="ca05f-106">Office 365 证书链</span><span class="sxs-lookup"><span data-stu-id="ca05f-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="ca05f-p102">Office 365 利用大量的不同的证书提供商。下面介绍已知客户访问 Office 365 时可能遇到的 Office 365 根证书的完整的列表。您可能需要您自己的基础结构中安装证书信息，请参阅[Office 365 的第三方 SSL 证书计划](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce)。下面的证书信息适用于 Office 365 的所有全球和国家/地区云实例。</span><span class="sxs-lookup"><span data-stu-id="ca05f-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="ca05f-111">**证书类型**</span><span class="sxs-lookup"><span data-stu-id="ca05f-111">**Certificate type**</span></span>|<span data-ttu-id="ca05f-112">**P7b 下载**</span><span class="sxs-lookup"><span data-stu-id="ca05f-112">**P7b download**</span></span>|<span data-ttu-id="ca05f-113">**CRL 终结点**</span><span class="sxs-lookup"><span data-stu-id="ca05f-113">**CRL Endpoints**</span></span>|<span data-ttu-id="ca05f-114">**OCSP 终结点**</span><span class="sxs-lookup"><span data-stu-id="ca05f-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="ca05f-115">**AIA 终结点**</span><span class="sxs-lookup"><span data-stu-id="ca05f-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="ca05f-116">公共受信任的根证书</span><span class="sxs-lookup"><span data-stu-id="ca05f-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="ca05f-117">Office 365 根证书绑定 (P7B)</span><span class="sxs-lookup"><span data-stu-id="ca05f-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="ca05f-118">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="ca05f-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="ca05f-119">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="ca05f-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="ca05f-120">不适用</span><span class="sxs-lookup"><span data-stu-id="ca05f-120">N/A</span></span>  <br/> |<span data-ttu-id="ca05f-121">不适用</span><span class="sxs-lookup"><span data-stu-id="ca05f-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="ca05f-122">公共受信任的中间证书</span><span class="sxs-lookup"><span data-stu-id="ca05f-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="ca05f-123">Office 365 中间证书绑定 (P7B)</span><span class="sxs-lookup"><span data-stu-id="ca05f-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="ca05f-124">cdp1.public trust.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="ca05f-125">crl.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="ca05f-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="ca05f-126">crl.entrust.net</span><span class="sxs-lookup"><span data-stu-id="ca05f-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="ca05f-127">crl.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="ca05f-128">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="ca05f-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="ca05f-129">crl.identrust.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="ca05f-130">crl.thawte.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="ca05f-131">crl3.digicert.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="ca05f-132">crl4.digicert.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="ca05f-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="ca05f-134">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="ca05f-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="ca05f-135">isrg.trustid.ocsp.identrust.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="ca05f-136">ocsp.digicert.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="ca05f-137">ocsp.entrust.net</span><span class="sxs-lookup"><span data-stu-id="ca05f-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="ca05f-138">ocsp.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="ca05f-139">ocsp.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="ca05f-140">ocsp.startssl.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="ca05f-141">ocsp.thawte.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="ca05f-142">ocsp2.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="ca05f-143">ocspcnnicroot.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="ca05f-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="ca05f-144">根-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="ca05f-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="ca05f-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="ca05f-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="ca05f-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="ca05f-147">aia.startssl.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="ca05f-148">apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="ca05f-149">cacert.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="ca05f-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="ca05f-150">www.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="ca05f-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="ca05f-151">展开根和下面有关证书提供商的其他详细信息，请参阅的中间部分。</span><span class="sxs-lookup"><span data-stu-id="ca05f-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="ca05f-152">Office 365 根证书的详细信息</span><span class="sxs-lookup"><span data-stu-id="ca05f-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="ca05f-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="ca05f-153"></span></span>

 <span data-ttu-id="ca05f-154">**Baltimore CyberTrust 根**</span><span class="sxs-lookup"><span data-stu-id="ca05f-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="ca05f-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="ca05f-155">|:-----|</span></span>
|<span data-ttu-id="ca05f-156">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="ca05f-157">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-157">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-158">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-158"></span></span>|
|<span data-ttu-id="ca05f-159">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-159">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-160">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-160"></span></span>|
|<span data-ttu-id="ca05f-161">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-162">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-162"></span></span>|
|<span data-ttu-id="ca05f-163">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-164">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-164"></span></span>|
|<span data-ttu-id="ca05f-165">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-165">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-166">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-166"></span></span>|
|<span data-ttu-id="ca05f-167">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-168">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-168"></span></span>|
|<span data-ttu-id="ca05f-169">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-170">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-170"></span></span>|
|<span data-ttu-id="ca05f-171">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-172">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-172"></span></span>|
|<span data-ttu-id="ca05f-173">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-174">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-174"></span></span>|
   
 <span data-ttu-id="ca05f-175">**CNNIC 根**</span><span class="sxs-lookup"><span data-stu-id="ca05f-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-176">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-176">**Subject**</span></span>|
|<span data-ttu-id="ca05f-177">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-177"></span></span>|
|<span data-ttu-id="ca05f-178">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-178">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-179">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-179"></span></span>|
|<span data-ttu-id="ca05f-180">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-180">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-181">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-181"></span></span>|
|<span data-ttu-id="ca05f-182">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-183">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-183"></span></span>|
|<span data-ttu-id="ca05f-184">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-185">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-185"></span></span>|
|<span data-ttu-id="ca05f-186">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-186">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-187">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-187"></span></span>|
|<span data-ttu-id="ca05f-188">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-189">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-189"></span></span>|
|<span data-ttu-id="ca05f-190">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-191">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-191"></span></span>|
|<span data-ttu-id="ca05f-192">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-193">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-193"></span></span>|
|<span data-ttu-id="ca05f-194">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-195">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-195"></span></span>|
|<span data-ttu-id="ca05f-196">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-197">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-197"></span></span>|
   
 <span data-ttu-id="ca05f-198">**DigiCert 全局根 CA**</span><span class="sxs-lookup"><span data-stu-id="ca05f-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-199">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-199">**Subject**</span></span>|
|<span data-ttu-id="ca05f-200">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-200"></span></span>|
|<span data-ttu-id="ca05f-201">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-201">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-202">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-202"></span></span>|
|<span data-ttu-id="ca05f-203">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-203">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-204">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-204"></span></span>|
|<span data-ttu-id="ca05f-205">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-206">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-206"></span></span>|
|<span data-ttu-id="ca05f-207">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-208">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-208"></span></span>|
|<span data-ttu-id="ca05f-209">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-209">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-210">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-210"></span></span>|
|<span data-ttu-id="ca05f-211">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-212">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-212"></span></span>|
|<span data-ttu-id="ca05f-213">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-214">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-214"></span></span>|
|<span data-ttu-id="ca05f-215">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-216">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-216"></span></span>|
|<span data-ttu-id="ca05f-217">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-218">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-218"></span></span>|
|<span data-ttu-id="ca05f-219">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-220">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-220"></span></span>|
   
 <span data-ttu-id="ca05f-221">**DigiCert 高保证 EV 根 CA**</span><span class="sxs-lookup"><span data-stu-id="ca05f-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-222">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-222">**Subject**</span></span>|
|<span data-ttu-id="ca05f-223">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-223"></span></span>|
|<span data-ttu-id="ca05f-224">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-224">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-225">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-225"></span></span>|
|<span data-ttu-id="ca05f-226">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-226">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-227">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-227"></span></span>|
|<span data-ttu-id="ca05f-228">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-229">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-229"></span></span>|
|<span data-ttu-id="ca05f-230">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-231">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-231"></span></span>|
|<span data-ttu-id="ca05f-232">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-232">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-233">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-233"></span></span>|
|<span data-ttu-id="ca05f-234">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-235">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-235"></span></span>|
|<span data-ttu-id="ca05f-236">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-237">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-237"></span></span>|
|<span data-ttu-id="ca05f-238">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-239">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-239"></span></span>|
|<span data-ttu-id="ca05f-240">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-241">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-241"></span></span>|
|<span data-ttu-id="ca05f-242">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-243">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-243"></span></span>|
   
 <span data-ttu-id="ca05f-244">**D 信任根类 3 CA 2 2009**</span><span class="sxs-lookup"><span data-stu-id="ca05f-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-245">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-245">**Subject**</span></span>|
|<span data-ttu-id="ca05f-246">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-246"></span></span>|
|<span data-ttu-id="ca05f-247">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-247">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-248">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-248"></span></span>|
|<span data-ttu-id="ca05f-249">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-249">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-250">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-250"></span></span>|
|<span data-ttu-id="ca05f-251">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-252">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-252"></span></span>|
|<span data-ttu-id="ca05f-253">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-254">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-254"></span></span>|
|<span data-ttu-id="ca05f-255">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-255">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-256">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-256"></span></span>|
|<span data-ttu-id="ca05f-257">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-258">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-258"></span></span>|
|<span data-ttu-id="ca05f-259">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-260">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-260"></span></span>|
|<span data-ttu-id="ca05f-261">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-262">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-262"></span></span>|
|<span data-ttu-id="ca05f-263">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-264">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-264"></span></span>|
|<span data-ttu-id="ca05f-265">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-265">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-266">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-266"></span></span>|
   
 <span data-ttu-id="ca05f-267">**D 信任根类 3 CA 2 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="ca05f-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-268">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-268">**Subject**</span></span>|
|<span data-ttu-id="ca05f-269">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-269"></span></span>|
|<span data-ttu-id="ca05f-270">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-270">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-271">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-271"></span></span>|
|<span data-ttu-id="ca05f-272">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-272">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-273">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-273"></span></span>|
|<span data-ttu-id="ca05f-274">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-275">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-275"></span></span>|
|<span data-ttu-id="ca05f-276">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-277">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-277"></span></span>|
|<span data-ttu-id="ca05f-278">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-278">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-279">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-279"></span></span>|
|<span data-ttu-id="ca05f-280">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-281">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-281"></span></span>|
|<span data-ttu-id="ca05f-282">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-283">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-283"></span></span>|
|<span data-ttu-id="ca05f-284">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-285">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-285"></span></span>|
|<span data-ttu-id="ca05f-286">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-287">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-287"></span></span>|
|<span data-ttu-id="ca05f-288">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-288">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-289">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-289"></span></span>|
   
 <span data-ttu-id="ca05f-290">**DST 根 CA X3**</span><span class="sxs-lookup"><span data-stu-id="ca05f-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-291">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-291">**Subject**</span></span>|
|<span data-ttu-id="ca05f-292">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-292"></span></span>|
|<span data-ttu-id="ca05f-293">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-293">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-294">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-294"></span></span>|
|<span data-ttu-id="ca05f-295">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-295">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-296">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-296"></span></span>|
|<span data-ttu-id="ca05f-297">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-298">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-298"></span></span>|
|<span data-ttu-id="ca05f-299">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-300">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-300"></span></span>|
|<span data-ttu-id="ca05f-301">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-301">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-302">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-302"></span></span>|
|<span data-ttu-id="ca05f-303">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-304">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-304"></span></span>|
|<span data-ttu-id="ca05f-305">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-306">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-306"></span></span>|
|<span data-ttu-id="ca05f-307">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-308">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-308"></span></span>|
|<span data-ttu-id="ca05f-309">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-310">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-310"></span></span>|
   
 <span data-ttu-id="ca05f-311">**委托根证书颁发机构-G2**</span><span class="sxs-lookup"><span data-stu-id="ca05f-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-312">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-312">**Subject**</span></span>|
|<span data-ttu-id="ca05f-313">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-313"></span></span>|
|<span data-ttu-id="ca05f-314">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-314">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-315">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-315"></span></span>|
|<span data-ttu-id="ca05f-316">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-316">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-317">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-317"></span></span>|
|<span data-ttu-id="ca05f-318">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-319">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-319"></span></span>|
|<span data-ttu-id="ca05f-320">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-321">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-321"></span></span>|
|<span data-ttu-id="ca05f-322">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-322">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-323">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-323"></span></span>|
|<span data-ttu-id="ca05f-324">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-325">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-325"></span></span>|
|<span data-ttu-id="ca05f-326">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-327">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-327"></span></span>|
|<span data-ttu-id="ca05f-328">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-329">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-329"></span></span>|
|<span data-ttu-id="ca05f-330">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-331">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-331"></span></span>|
   
 <span data-ttu-id="ca05f-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-333">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-333">**Subject**</span></span>|
|<span data-ttu-id="ca05f-334">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-334"></span></span>|
|<span data-ttu-id="ca05f-335">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-335">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-336">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-336"></span></span>|
|<span data-ttu-id="ca05f-337">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-337">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-338">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-338"></span></span>|
|<span data-ttu-id="ca05f-339">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-340">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-340"></span></span>|
|<span data-ttu-id="ca05f-341">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-342">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-342"></span></span>|
|<span data-ttu-id="ca05f-343">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-343">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-344">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-344"></span></span>|
|<span data-ttu-id="ca05f-345">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-346">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-346"></span></span>|
|<span data-ttu-id="ca05f-347">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-348">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-348"></span></span>|
|<span data-ttu-id="ca05f-349">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-350">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-350"></span></span>|
|<span data-ttu-id="ca05f-351">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-352">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-352"></span></span>|
   
 <span data-ttu-id="ca05f-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="ca05f-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-354">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-354">**Subject**</span></span>|
|<span data-ttu-id="ca05f-355">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-355"></span></span>|
|<span data-ttu-id="ca05f-356">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-356">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-357">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-357"></span></span>|
|<span data-ttu-id="ca05f-358">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-358">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-359">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-359"></span></span>|
|<span data-ttu-id="ca05f-360">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-361">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-361"></span></span>|
|<span data-ttu-id="ca05f-362">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-363">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-363"></span></span>|
|<span data-ttu-id="ca05f-364">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-364">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-365">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-365"></span></span>|
|<span data-ttu-id="ca05f-366">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-367">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-367"></span></span>|
|<span data-ttu-id="ca05f-368">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-369">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-369"></span></span>|
|<span data-ttu-id="ca05f-370">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-371">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-371"></span></span>|
|<span data-ttu-id="ca05f-372">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-373">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-373"></span></span>|
|<span data-ttu-id="ca05f-374">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-375">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-375"></span></span>|
|<span data-ttu-id="ca05f-376">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-376">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-377">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-377"></span></span>|
   
 <span data-ttu-id="ca05f-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="ca05f-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-379">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-379">**Subject**</span></span>|
|<span data-ttu-id="ca05f-380">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-380"></span></span>|
|<span data-ttu-id="ca05f-381">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-381">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-382">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-382"></span></span>|
|<span data-ttu-id="ca05f-383">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-383">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-384">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-384"></span></span>|
|<span data-ttu-id="ca05f-385">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-386">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-386"></span></span>|
|<span data-ttu-id="ca05f-387">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-388">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-388"></span></span>|
|<span data-ttu-id="ca05f-389">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-389">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-390">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-390"></span></span>|
|<span data-ttu-id="ca05f-391">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-392">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-392"></span></span>|
|<span data-ttu-id="ca05f-393">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-394">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-394"></span></span>|
|<span data-ttu-id="ca05f-395">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-396">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-396"></span></span>|
|<span data-ttu-id="ca05f-397">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-398">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-398"></span></span>|
   
 <span data-ttu-id="ca05f-399">**thawte 主根 CA-G3**</span><span class="sxs-lookup"><span data-stu-id="ca05f-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-400">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-400">**Subject**</span></span>|
|<span data-ttu-id="ca05f-401">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-401"></span></span>|
|<span data-ttu-id="ca05f-402">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-402">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-403">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-403"></span></span>|
|<span data-ttu-id="ca05f-404">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-404">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-405">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-405"></span></span>|
|<span data-ttu-id="ca05f-406">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-407">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-407"></span></span>|
|<span data-ttu-id="ca05f-408">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-409">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-409"></span></span>|
|<span data-ttu-id="ca05f-410">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-410">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-411">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-411"></span></span>|
|<span data-ttu-id="ca05f-412">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-413">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-413"></span></span>|
|<span data-ttu-id="ca05f-414">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-415">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-415"></span></span>|
|<span data-ttu-id="ca05f-416">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-417">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-417"></span></span>|
|<span data-ttu-id="ca05f-418">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-419">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-419"></span></span>|
   
 <span data-ttu-id="ca05f-420">**VeriSign 类 3 主要公用证书颁发机构-G5**</span><span class="sxs-lookup"><span data-stu-id="ca05f-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-421">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-421">**Subject**</span></span>|
|<span data-ttu-id="ca05f-422">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-422"></span></span>|
|<span data-ttu-id="ca05f-423">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-423">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-424">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-424"></span></span>|
|<span data-ttu-id="ca05f-425">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-425">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-426">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-426"></span></span>|
|<span data-ttu-id="ca05f-427">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-428">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-428"></span></span>|
|<span data-ttu-id="ca05f-429">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-430">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-430"></span></span>|
|<span data-ttu-id="ca05f-431">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-431">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-432">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-432"></span></span>|
|<span data-ttu-id="ca05f-433">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-434">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-434"></span></span>|
|<span data-ttu-id="ca05f-435">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-436">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-436"></span></span>|
|<span data-ttu-id="ca05f-437">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-438">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-438"></span></span>|
|<span data-ttu-id="ca05f-439">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-440">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="ca05f-441">Office 365 中间证书详细信息</span><span class="sxs-lookup"><span data-stu-id="ca05f-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="ca05f-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="ca05f-442"></span></span>

 <span data-ttu-id="ca05f-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="ca05f-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-444">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-444">**Subject**</span></span>|
|<span data-ttu-id="ca05f-445">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-445"></span></span>|
|<span data-ttu-id="ca05f-446">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-446">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-447">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-447"></span></span>|
|<span data-ttu-id="ca05f-448">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-448">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-449">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-449"></span></span>|
|<span data-ttu-id="ca05f-450">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-450">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-451">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-451"></span></span>|
|<span data-ttu-id="ca05f-452">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-453">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-453"></span></span>|
|<span data-ttu-id="ca05f-454">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-455">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-455"></span></span>|
|<span data-ttu-id="ca05f-456">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-456">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-457">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-457"></span></span>|
|<span data-ttu-id="ca05f-458">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-459">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-459"></span></span>|
|<span data-ttu-id="ca05f-460">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-461">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-461"></span></span>|
|<span data-ttu-id="ca05f-462">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-463">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-463"></span></span>|
|<span data-ttu-id="ca05f-464">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-465">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-465"></span></span>|
|<span data-ttu-id="ca05f-466">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-467">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-467"></span></span>|
|<span data-ttu-id="ca05f-468">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-468">**AIA URLs**</span></span>|
|<span data-ttu-id="ca05f-469">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-469"></span></span>|
|<span data-ttu-id="ca05f-470">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-470">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-471">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-471"></span></span>|
|<span data-ttu-id="ca05f-472">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-473">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-473"></span></span>|
   
 <span data-ttu-id="ca05f-474">**D 信任 SSL 类 3 CA 1 2009**</span><span class="sxs-lookup"><span data-stu-id="ca05f-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-475">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-475">**Subject**</span></span>|
|<span data-ttu-id="ca05f-476">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-476"></span></span>|
|<span data-ttu-id="ca05f-477">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-477">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-478">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-478"></span></span>|
|<span data-ttu-id="ca05f-479">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="ca05f-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="ca05f-480">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-480"></span></span>|
|<span data-ttu-id="ca05f-481">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-481">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-482">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-482"></span></span>|
|<span data-ttu-id="ca05f-483">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-483">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-484">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-484"></span></span>|
|<span data-ttu-id="ca05f-485">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-486">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-486"></span></span>|
|<span data-ttu-id="ca05f-487">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-488">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-488"></span></span>|
|<span data-ttu-id="ca05f-489">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-489">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-490">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-490"></span></span>|
|<span data-ttu-id="ca05f-491">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-492">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-492"></span></span>|
|<span data-ttu-id="ca05f-493">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-494">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-494"></span></span>|
|<span data-ttu-id="ca05f-495">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-496">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-496"></span></span>|
|<span data-ttu-id="ca05f-497">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-498">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-498"></span></span>|
|<span data-ttu-id="ca05f-499">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-500">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-500"></span></span>|
|<span data-ttu-id="ca05f-501">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-501">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-502">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-502"></span></span>|
|<span data-ttu-id="ca05f-503">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-504">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-504"></span></span>|
   
 <span data-ttu-id="ca05f-505">**D 信任 SSL 类 3 CA 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="ca05f-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-506">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-506">**Subject**</span></span>|
|<span data-ttu-id="ca05f-507">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-507"></span></span>|
|<span data-ttu-id="ca05f-508">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-508">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-509">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-509"></span></span>|
|<span data-ttu-id="ca05f-510">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="ca05f-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="ca05f-511">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-511"></span></span>|
|<span data-ttu-id="ca05f-512">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-512">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-513">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-513"></span></span>|
|<span data-ttu-id="ca05f-514">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-514">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-515">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-515"></span></span>|
|<span data-ttu-id="ca05f-516">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-517">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-517"></span></span>|
|<span data-ttu-id="ca05f-518">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-519">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-519"></span></span>|
|<span data-ttu-id="ca05f-520">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-520">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-521">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-521"></span></span>|
|<span data-ttu-id="ca05f-522">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-523">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-523"></span></span>|
|<span data-ttu-id="ca05f-524">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-525">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-525"></span></span>|
|<span data-ttu-id="ca05f-526">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-527">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-527"></span></span>|
|<span data-ttu-id="ca05f-528">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-529">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-529"></span></span>|
|<span data-ttu-id="ca05f-530">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-531">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-531"></span></span>|
|<span data-ttu-id="ca05f-532">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-532">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-533">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-533"></span></span>|
|<span data-ttu-id="ca05f-534">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-535">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-535"></span></span>|
   
 <span data-ttu-id="ca05f-536">**DigiCert 云服务 CA-1**</span><span class="sxs-lookup"><span data-stu-id="ca05f-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-537">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-537">**Subject**</span></span>|
|<span data-ttu-id="ca05f-538">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-538"></span></span>|
|<span data-ttu-id="ca05f-539">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-539">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-540">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-540"></span></span>|
|<span data-ttu-id="ca05f-541">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-541">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-542">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-542"></span></span>|
|<span data-ttu-id="ca05f-543">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-543">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-544">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-544"></span></span>|
|<span data-ttu-id="ca05f-545">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-546">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-546"></span></span>|
|<span data-ttu-id="ca05f-547">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-548">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-548"></span></span>|
|<span data-ttu-id="ca05f-549">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-549">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-550">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-550"></span></span>|
|<span data-ttu-id="ca05f-551">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-552">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-552"></span></span>|
|<span data-ttu-id="ca05f-553">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-554">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-554"></span></span>|
|<span data-ttu-id="ca05f-555">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-556">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-556"></span></span>|
|<span data-ttu-id="ca05f-557">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-558">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-558"></span></span>|
|<span data-ttu-id="ca05f-559">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-560">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-560"></span></span>|
|<span data-ttu-id="ca05f-561">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-561">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-562">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-562"></span></span>|
|<span data-ttu-id="ca05f-563">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-564">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-564"></span></span>|
   
 <span data-ttu-id="ca05f-565">**DigiCert SHA2 高保证服务器 CA**</span><span class="sxs-lookup"><span data-stu-id="ca05f-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-566">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-566">**Subject**</span></span>|
|<span data-ttu-id="ca05f-567">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-567"></span></span>|
|<span data-ttu-id="ca05f-568">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-568">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-569">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-569"></span></span>|
|<span data-ttu-id="ca05f-570">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-570">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-571">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-571"></span></span>|
|<span data-ttu-id="ca05f-572">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-572">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-573">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-573"></span></span>|
|<span data-ttu-id="ca05f-574">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-575">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-575"></span></span>|
|<span data-ttu-id="ca05f-576">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-577">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-577"></span></span>|
|<span data-ttu-id="ca05f-578">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-578">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-579">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-579"></span></span>|
|<span data-ttu-id="ca05f-580">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-581">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-581"></span></span>|
|<span data-ttu-id="ca05f-582">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-583">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-583"></span></span>|
|<span data-ttu-id="ca05f-584">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-585">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-585"></span></span>|
|<span data-ttu-id="ca05f-586">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-587">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-587"></span></span>|
|<span data-ttu-id="ca05f-588">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-589">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-589"></span></span>|
|<span data-ttu-id="ca05f-590">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-590">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-591">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-591"></span></span>|
|<span data-ttu-id="ca05f-592">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-593">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-593"></span></span>|
   
 <span data-ttu-id="ca05f-594">**DigiCert SHA2 安全服务器 CA**</span><span class="sxs-lookup"><span data-stu-id="ca05f-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-595">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-595">**Subject**</span></span>|
|<span data-ttu-id="ca05f-596">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-596"></span></span>|
|<span data-ttu-id="ca05f-597">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-597">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-598">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-598"></span></span>|
|<span data-ttu-id="ca05f-599">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-599">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-600">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-600"></span></span>|
|<span data-ttu-id="ca05f-601">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-601">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-602">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-602"></span></span>|
|<span data-ttu-id="ca05f-603">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-604">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-604"></span></span>|
|<span data-ttu-id="ca05f-605">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-606">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-606"></span></span>|
|<span data-ttu-id="ca05f-607">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-607">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-608">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-608"></span></span>|
|<span data-ttu-id="ca05f-609">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-610">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-610"></span></span>|
|<span data-ttu-id="ca05f-611">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-612">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-612"></span></span>|
|<span data-ttu-id="ca05f-613">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-614">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-614"></span></span>|
|<span data-ttu-id="ca05f-615">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-616">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-616"></span></span>|
|<span data-ttu-id="ca05f-617">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-618">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-618"></span></span>|
|<span data-ttu-id="ca05f-619">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-619">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-620">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-620"></span></span>|
|<span data-ttu-id="ca05f-621">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-622">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-622"></span></span>|
   
 <span data-ttu-id="ca05f-623">**委托 L1C 的证书颁发机构-**</span><span class="sxs-lookup"><span data-stu-id="ca05f-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-624">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-624">**Subject**</span></span>|
|<span data-ttu-id="ca05f-625">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-625"></span></span>|
|<span data-ttu-id="ca05f-626">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-626">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-627">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-627"></span></span>|
|<span data-ttu-id="ca05f-628">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-628">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-629">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-629"></span></span>|
|<span data-ttu-id="ca05f-630">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-630">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-631">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-631"></span></span>|
|<span data-ttu-id="ca05f-632">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-633">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-633"></span></span>|
|<span data-ttu-id="ca05f-634">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-635">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-635"></span></span>|
|<span data-ttu-id="ca05f-636">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-636">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-637">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-637"></span></span>|
|<span data-ttu-id="ca05f-638">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-639">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-639"></span></span>|
|<span data-ttu-id="ca05f-640">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-641">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-641"></span></span>|
|<span data-ttu-id="ca05f-642">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-643">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-643"></span></span>|
|<span data-ttu-id="ca05f-644">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-645">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-645"></span></span>|
|<span data-ttu-id="ca05f-646">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-647">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-647"></span></span>|
|<span data-ttu-id="ca05f-648">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-648">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-649">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-649"></span></span>|
|<span data-ttu-id="ca05f-650">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-651">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-651"></span></span>|
   
 <span data-ttu-id="ca05f-652">**委托 L1K 的证书颁发机构-**</span><span class="sxs-lookup"><span data-stu-id="ca05f-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-653">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-653">**Subject**</span></span>|
|<span data-ttu-id="ca05f-654">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-654"></span></span>|
|<span data-ttu-id="ca05f-655">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-655">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-656">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-656"></span></span>|
|<span data-ttu-id="ca05f-657">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-657">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-658">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-658"></span></span>|
|<span data-ttu-id="ca05f-659">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-659">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-660">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-660"></span></span>|
|<span data-ttu-id="ca05f-661">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-662">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-662"></span></span>|
|<span data-ttu-id="ca05f-663">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-664">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-664"></span></span>|
|<span data-ttu-id="ca05f-665">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-665">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-666">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-666"></span></span>|
|<span data-ttu-id="ca05f-667">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-668">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-668"></span></span>|
|<span data-ttu-id="ca05f-669">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-670">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-670"></span></span>|
|<span data-ttu-id="ca05f-671">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-672">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-672"></span></span>|
|<span data-ttu-id="ca05f-673">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-674">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-674"></span></span>|
|<span data-ttu-id="ca05f-675">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-676">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-676"></span></span>|
|<span data-ttu-id="ca05f-677">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-677">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-678">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-678"></span></span>|
|<span data-ttu-id="ca05f-679">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-680">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-680"></span></span>|
   
 <span data-ttu-id="ca05f-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="ca05f-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-682">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-682">**Subject**</span></span>|
|<span data-ttu-id="ca05f-683">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-683"></span></span>|
|<span data-ttu-id="ca05f-684">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-684">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-685">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-685"></span></span>|
|<span data-ttu-id="ca05f-686">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-686">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-687">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-687"></span></span>|
|<span data-ttu-id="ca05f-688">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-688">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-689">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-689"></span></span>|
|<span data-ttu-id="ca05f-690">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-691">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-691"></span></span>|
|<span data-ttu-id="ca05f-692">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-693">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-693"></span></span>|
|<span data-ttu-id="ca05f-694">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-694">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-695">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-695"></span></span>|
|<span data-ttu-id="ca05f-696">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-697">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-697"></span></span>|
|<span data-ttu-id="ca05f-698">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-699">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-699"></span></span>|
|<span data-ttu-id="ca05f-700">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-701">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-701"></span></span>|
|<span data-ttu-id="ca05f-702">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-703">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-703"></span></span>|
|<span data-ttu-id="ca05f-704">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-705">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-705"></span></span>|
|<span data-ttu-id="ca05f-706">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-706">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-707">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-707"></span></span>|
|<span data-ttu-id="ca05f-708">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-709">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-709"></span></span>|
   
 <span data-ttu-id="ca05f-710">**GlobalSign 扩展验证 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="ca05f-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-711">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-711">**Subject**</span></span>|
|<span data-ttu-id="ca05f-712">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-712"></span></span>|
|<span data-ttu-id="ca05f-713">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-713">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-714">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-714"></span></span>|
|<span data-ttu-id="ca05f-715">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-715">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-716">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-716"></span></span>|
|<span data-ttu-id="ca05f-717">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-717">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-718">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-718"></span></span>|
|<span data-ttu-id="ca05f-719">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-720">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-720"></span></span>|
|<span data-ttu-id="ca05f-721">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-722">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-722"></span></span>|
|<span data-ttu-id="ca05f-723">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-723">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-724">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-724"></span></span>|
|<span data-ttu-id="ca05f-725">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-726">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-726"></span></span>|
|<span data-ttu-id="ca05f-727">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-728">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-728"></span></span>|
|<span data-ttu-id="ca05f-729">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-730">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-730"></span></span>|
|<span data-ttu-id="ca05f-731">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-732">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-732"></span></span>|
|<span data-ttu-id="ca05f-733">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-734">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-734"></span></span>|
|<span data-ttu-id="ca05f-735">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-735">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-736">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-736"></span></span>|
|<span data-ttu-id="ca05f-737">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-738">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-738"></span></span>|
   
 <span data-ttu-id="ca05f-739">**GlobalSign 扩展验证 CA-SHA256-G3**</span><span class="sxs-lookup"><span data-stu-id="ca05f-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-740">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-740">**Subject**</span></span>|
|<span data-ttu-id="ca05f-741">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-741"></span></span>|
|<span data-ttu-id="ca05f-742">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-742">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-743">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-743"></span></span>|
|<span data-ttu-id="ca05f-744">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-744">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-745">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-745"></span></span>|
|<span data-ttu-id="ca05f-746">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-746">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-747">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-747"></span></span>|
|<span data-ttu-id="ca05f-748">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-749">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-749"></span></span>|
|<span data-ttu-id="ca05f-750">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-751">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-751"></span></span>|
|<span data-ttu-id="ca05f-752">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-752">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-753">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-753"></span></span>|
|<span data-ttu-id="ca05f-754">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-755">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-755"></span></span>|
|<span data-ttu-id="ca05f-756">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-757">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-757"></span></span>|
|<span data-ttu-id="ca05f-758">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-759">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-759"></span></span>|
|<span data-ttu-id="ca05f-760">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-761">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-761"></span></span>|
|<span data-ttu-id="ca05f-762">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-763">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-763"></span></span>|
|<span data-ttu-id="ca05f-764">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-764">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-765">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-765"></span></span>|
|<span data-ttu-id="ca05f-766">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-767">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-767"></span></span>|
   
 <span data-ttu-id="ca05f-768">**GlobalSign 组织验证 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="ca05f-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-769">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-769">**Subject**</span></span>|
|<span data-ttu-id="ca05f-770">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-770"></span></span>|
|<span data-ttu-id="ca05f-771">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-771">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-772">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-772"></span></span>|
|<span data-ttu-id="ca05f-773">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-773">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-774">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-774"></span></span>|
|<span data-ttu-id="ca05f-775">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-775">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-776">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-776"></span></span>|
|<span data-ttu-id="ca05f-777">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-778">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-778"></span></span>|
|<span data-ttu-id="ca05f-779">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-780">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-780"></span></span>|
|<span data-ttu-id="ca05f-781">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-781">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-782">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-782"></span></span>|
|<span data-ttu-id="ca05f-783">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-784">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-784"></span></span>|
|<span data-ttu-id="ca05f-785">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-786">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-786"></span></span>|
|<span data-ttu-id="ca05f-787">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-788">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-788"></span></span>|
|<span data-ttu-id="ca05f-789">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-790">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-790"></span></span>|
|<span data-ttu-id="ca05f-791">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-792">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-792"></span></span>|
|<span data-ttu-id="ca05f-793">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-793">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-794">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-794"></span></span>|
|<span data-ttu-id="ca05f-795">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-796">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-796"></span></span>|
   
 <span data-ttu-id="ca05f-797">**GlobalSign 组织验证 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="ca05f-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-798">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-798">**Subject**</span></span>|
|<span data-ttu-id="ca05f-799">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-799"></span></span>|
|<span data-ttu-id="ca05f-800">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-800">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-801">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-801"></span></span>|
|<span data-ttu-id="ca05f-802">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-802">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-803">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-803"></span></span>|
|<span data-ttu-id="ca05f-804">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-804">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-805">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-805"></span></span>|
|<span data-ttu-id="ca05f-806">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-807">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-807"></span></span>|
|<span data-ttu-id="ca05f-808">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-809">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-809"></span></span>|
|<span data-ttu-id="ca05f-810">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-810">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-811">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-811"></span></span>|
|<span data-ttu-id="ca05f-812">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-813">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-813"></span></span>|
|<span data-ttu-id="ca05f-814">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-815">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-815"></span></span>|
|<span data-ttu-id="ca05f-816">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-817">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-817"></span></span>|
|<span data-ttu-id="ca05f-818">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-819">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-819"></span></span>|
|<span data-ttu-id="ca05f-820">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-821">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-821"></span></span>|
|<span data-ttu-id="ca05f-822">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-822">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-823">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-823"></span></span>|
|<span data-ttu-id="ca05f-824">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-825">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-825"></span></span>|
   
 <span data-ttu-id="ca05f-826">**让我们加密证书颁发机构 X3**</span><span class="sxs-lookup"><span data-stu-id="ca05f-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-827">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-827">**Subject**</span></span>|
|<span data-ttu-id="ca05f-828">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-828"></span></span>|
|<span data-ttu-id="ca05f-829">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-829">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-830">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-830"></span></span>|
|<span data-ttu-id="ca05f-831">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-831">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-832">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-832"></span></span>|
|<span data-ttu-id="ca05f-833">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-833">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-834">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-834"></span></span>|
|<span data-ttu-id="ca05f-835">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-836">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-836"></span></span>|
|<span data-ttu-id="ca05f-837">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-838">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-838"></span></span>|
|<span data-ttu-id="ca05f-839">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-839">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-840">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-840"></span></span>|
|<span data-ttu-id="ca05f-841">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-842">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-842"></span></span>|
|<span data-ttu-id="ca05f-843">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-844">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-844"></span></span>|
|<span data-ttu-id="ca05f-845">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-846">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-846"></span></span>|
|<span data-ttu-id="ca05f-847">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-848">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-848"></span></span>|
|<span data-ttu-id="ca05f-849">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-850">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-850"></span></span>|
|<span data-ttu-id="ca05f-851">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-851">**AIA URLs**</span></span>|
|<span data-ttu-id="ca05f-852">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-852"></span></span>|
|<span data-ttu-id="ca05f-853">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-853">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-854">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-854"></span></span>|
|<span data-ttu-id="ca05f-855">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-856">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-856"></span></span>|
   
 <span data-ttu-id="ca05f-857">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="ca05f-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-858">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-858">**Subject**</span></span>|
|<span data-ttu-id="ca05f-859">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-859"></span></span>|
|<span data-ttu-id="ca05f-860">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-860">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-861">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-861"></span></span>|
|<span data-ttu-id="ca05f-862">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-862">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-863">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-863"></span></span>|
|<span data-ttu-id="ca05f-864">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-864">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-865">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-865"></span></span>|
|<span data-ttu-id="ca05f-866">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-867">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-867"></span></span>|
|<span data-ttu-id="ca05f-868">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-869">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-869"></span></span>|
|<span data-ttu-id="ca05f-870">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-870">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-871">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-871"></span></span>|
|<span data-ttu-id="ca05f-872">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-873">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-873"></span></span>|
|<span data-ttu-id="ca05f-874">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-875">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-875"></span></span>|
|<span data-ttu-id="ca05f-876">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-877">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-877"></span></span>|
|<span data-ttu-id="ca05f-878">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-879">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-879"></span></span>|
|<span data-ttu-id="ca05f-880">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-881">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-881"></span></span>|
|<span data-ttu-id="ca05f-882">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-882">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-883">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-883"></span></span>|
   
 <span data-ttu-id="ca05f-884">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="ca05f-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-885">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-885">**Subject**</span></span>|
|<span data-ttu-id="ca05f-886">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-886"></span></span>|
|<span data-ttu-id="ca05f-887">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-887">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-888">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-888"></span></span>|
|<span data-ttu-id="ca05f-889">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-889">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-890">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-890"></span></span>|
|<span data-ttu-id="ca05f-891">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-891">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-892">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-892"></span></span>|
|<span data-ttu-id="ca05f-893">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-894">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-894"></span></span>|
|<span data-ttu-id="ca05f-895">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-896">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-896"></span></span>|
|<span data-ttu-id="ca05f-897">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-897">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-898">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-898"></span></span>|
|<span data-ttu-id="ca05f-899">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-900">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-900"></span></span>|
|<span data-ttu-id="ca05f-901">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-902">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-902"></span></span>|
|<span data-ttu-id="ca05f-903">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-904">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-904"></span></span>|
|<span data-ttu-id="ca05f-905">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-906">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-906"></span></span>|
|<span data-ttu-id="ca05f-907">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-908">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-908"></span></span>|
|<span data-ttu-id="ca05f-909">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-909">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-910">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-910"></span></span>|
|<span data-ttu-id="ca05f-911">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-912">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-912"></span></span>|
   
 <span data-ttu-id="ca05f-913">**Microsoft IT TLS CA 1**</span><span class="sxs-lookup"><span data-stu-id="ca05f-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-914">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-914">**Subject**</span></span>|
|<span data-ttu-id="ca05f-915">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-915"></span></span>|
|<span data-ttu-id="ca05f-916">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-916">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-917">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-917"></span></span>|
|<span data-ttu-id="ca05f-918">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-918">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-919">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-919"></span></span>|
|<span data-ttu-id="ca05f-920">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-920">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-921">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-921"></span></span>|
|<span data-ttu-id="ca05f-922">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-923">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-923"></span></span>|
|<span data-ttu-id="ca05f-924">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-925">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-925"></span></span>|
|<span data-ttu-id="ca05f-926">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-926">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-927">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-927"></span></span>|
|<span data-ttu-id="ca05f-928">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-929">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-929"></span></span>|
|<span data-ttu-id="ca05f-930">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-931">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-931"></span></span>|
|<span data-ttu-id="ca05f-932">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-933">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-933"></span></span>|
|<span data-ttu-id="ca05f-934">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-935">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-935"></span></span>|
|<span data-ttu-id="ca05f-936">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-937">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-937"></span></span>|
|<span data-ttu-id="ca05f-938">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-938">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-939">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-939"></span></span>|
|<span data-ttu-id="ca05f-940">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-941">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-941"></span></span>|
   
 <span data-ttu-id="ca05f-942">**Microsoft IT TLS CA 2**</span><span class="sxs-lookup"><span data-stu-id="ca05f-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-943">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-943">**Subject**</span></span>|
|<span data-ttu-id="ca05f-944">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-944"></span></span>|
|<span data-ttu-id="ca05f-945">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-945">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-946">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-946"></span></span>|
|<span data-ttu-id="ca05f-947">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-947">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-948">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-948"></span></span>|
|<span data-ttu-id="ca05f-949">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-949">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-950">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-950"></span></span>|
|<span data-ttu-id="ca05f-951">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-952">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-952"></span></span>|
|<span data-ttu-id="ca05f-953">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-954">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-954"></span></span>|
|<span data-ttu-id="ca05f-955">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-955">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-956">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-956"></span></span>|
|<span data-ttu-id="ca05f-957">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-958">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-958"></span></span>|
|<span data-ttu-id="ca05f-959">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-960">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-960"></span></span>|
|<span data-ttu-id="ca05f-961">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-962">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-962"></span></span>|
|<span data-ttu-id="ca05f-963">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-964">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-964"></span></span>|
|<span data-ttu-id="ca05f-965">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-966">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-966"></span></span>|
|<span data-ttu-id="ca05f-967">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-967">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-968">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-968"></span></span>|
|<span data-ttu-id="ca05f-969">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-970">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-970"></span></span>|
   
 <span data-ttu-id="ca05f-971">**Microsoft IT TLS CA 4**</span><span class="sxs-lookup"><span data-stu-id="ca05f-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-972">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-972">**Subject**</span></span>|
|<span data-ttu-id="ca05f-973">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-973"></span></span>|
|<span data-ttu-id="ca05f-974">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-974">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-975">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-975"></span></span>|
|<span data-ttu-id="ca05f-976">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-976">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-977">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-977"></span></span>|
|<span data-ttu-id="ca05f-978">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-978">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-979">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-979"></span></span>|
|<span data-ttu-id="ca05f-980">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-981">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-981"></span></span>|
|<span data-ttu-id="ca05f-982">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-983">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-983"></span></span>|
|<span data-ttu-id="ca05f-984">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-984">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-985">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-985"></span></span>|
|<span data-ttu-id="ca05f-986">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-987">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-987"></span></span>|
|<span data-ttu-id="ca05f-988">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-989">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-989"></span></span>|
|<span data-ttu-id="ca05f-990">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-991">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-991"></span></span>|
|<span data-ttu-id="ca05f-992">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-993">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-993"></span></span>|
|<span data-ttu-id="ca05f-994">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-995">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-995"></span></span>|
|<span data-ttu-id="ca05f-996">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-996">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-997">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-997"></span></span>|
|<span data-ttu-id="ca05f-998">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-999">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-999"></span></span>|
   
 <span data-ttu-id="ca05f-1000">**Microsoft IT TLS CA 5**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-1001">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1001">**Subject**</span></span>|
|<span data-ttu-id="ca05f-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1002"></span></span>|
|<span data-ttu-id="ca05f-1003">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1003">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1004"></span></span>|
|<span data-ttu-id="ca05f-1005">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1005">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1006"></span></span>|
|<span data-ttu-id="ca05f-1007">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1008"></span></span>|
|<span data-ttu-id="ca05f-1009">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1010"></span></span>|
|<span data-ttu-id="ca05f-1011">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1012"></span></span>|
|<span data-ttu-id="ca05f-1013">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1014"></span></span>|
|<span data-ttu-id="ca05f-1015">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1016"></span></span>|
|<span data-ttu-id="ca05f-1017">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1018"></span></span>|
|<span data-ttu-id="ca05f-1019">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1020"></span></span>|
|<span data-ttu-id="ca05f-1021">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1022"></span></span>|
|<span data-ttu-id="ca05f-1023">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1024"></span></span>|
|<span data-ttu-id="ca05f-1025">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1026"></span></span>|
|<span data-ttu-id="ca05f-1027">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1028"></span></span>|
   
 <span data-ttu-id="ca05f-1029">**Symantec 类 3 EV SSL CA G3**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-1030">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1030">**Subject**</span></span>|
|<span data-ttu-id="ca05f-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1031"></span></span>|
|<span data-ttu-id="ca05f-1032">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1032">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1033"></span></span>|
|<span data-ttu-id="ca05f-1034">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="ca05f-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1035"></span></span>|
|<span data-ttu-id="ca05f-1036">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1036">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1037"></span></span>|
|<span data-ttu-id="ca05f-1038">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1039"></span></span>|
|<span data-ttu-id="ca05f-1040">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1041"></span></span>|
|<span data-ttu-id="ca05f-1042">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1043"></span></span>|
|<span data-ttu-id="ca05f-1044">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1045"></span></span>|
|<span data-ttu-id="ca05f-1046">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1047"></span></span>|
|<span data-ttu-id="ca05f-1048">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1049"></span></span>|
|<span data-ttu-id="ca05f-1050">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1051"></span></span>|
|<span data-ttu-id="ca05f-1052">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1053"></span></span>|
|<span data-ttu-id="ca05f-1054">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1055"></span></span>|
|<span data-ttu-id="ca05f-1056">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1057"></span></span>|
|<span data-ttu-id="ca05f-1058">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1059"></span></span>|
   
 <span data-ttu-id="ca05f-1060">**Symantec 类 3 安全服务器 CA-G4**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-1061">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1061">**Subject**</span></span>|
|<span data-ttu-id="ca05f-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1062"></span></span>|
|<span data-ttu-id="ca05f-1063">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1063">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1064"></span></span>|
|<span data-ttu-id="ca05f-1065">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="ca05f-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1066"></span></span>|
|<span data-ttu-id="ca05f-1067">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1067">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1068"></span></span>|
|<span data-ttu-id="ca05f-1069">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1070"></span></span>|
|<span data-ttu-id="ca05f-1071">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1072"></span></span>|
|<span data-ttu-id="ca05f-1073">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1074"></span></span>|
|<span data-ttu-id="ca05f-1075">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1076"></span></span>|
|<span data-ttu-id="ca05f-1077">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1078"></span></span>|
|<span data-ttu-id="ca05f-1079">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1080"></span></span>|
|<span data-ttu-id="ca05f-1081">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1082"></span></span>|
|<span data-ttu-id="ca05f-1083">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1084"></span></span>|
|<span data-ttu-id="ca05f-1085">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1086"></span></span>|
|<span data-ttu-id="ca05f-1087">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1088"></span></span>|
|<span data-ttu-id="ca05f-1089">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1090"></span></span>|
   
 <span data-ttu-id="ca05f-1091">**thawte SHA256 SSL CA**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-1092">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1092">**Subject**</span></span>|
|<span data-ttu-id="ca05f-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1093"></span></span>|
|<span data-ttu-id="ca05f-1094">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1094">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1095"></span></span>|
|<span data-ttu-id="ca05f-1096">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="ca05f-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1097"></span></span>|
|<span data-ttu-id="ca05f-1098">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1098">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1099"></span></span>|
|<span data-ttu-id="ca05f-1100">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1101"></span></span>|
|<span data-ttu-id="ca05f-1102">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1103"></span></span>|
|<span data-ttu-id="ca05f-1104">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1105"></span></span>|
|<span data-ttu-id="ca05f-1106">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1107"></span></span>|
|<span data-ttu-id="ca05f-1108">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1109"></span></span>|
|<span data-ttu-id="ca05f-1110">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1111"></span></span>|
|<span data-ttu-id="ca05f-1112">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1113"></span></span>|
|<span data-ttu-id="ca05f-1114">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1115"></span></span>|
|<span data-ttu-id="ca05f-1116">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1117"></span></span>|
|<span data-ttu-id="ca05f-1118">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1119"></span></span>|
|<span data-ttu-id="ca05f-1120">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1121"></span></span>|
   
 <span data-ttu-id="ca05f-1122">**Verizon Akamai SureServer CA G14 SHA2**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="ca05f-1123">**主题**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1123">**Subject**</span></span>|
|<span data-ttu-id="ca05f-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1124"></span></span>|
|<span data-ttu-id="ca05f-1125">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1125">**Issuer**</span></span>|
|<span data-ttu-id="ca05f-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1126"></span></span>|
|<span data-ttu-id="ca05f-1127">**序列号**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1127">**Serial Number**</span></span>|
|<span data-ttu-id="ca05f-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1128"></span></span>|
|<span data-ttu-id="ca05f-1129">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="ca05f-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1130"></span></span>|
|<span data-ttu-id="ca05f-1131">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="ca05f-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1132"></span></span>|
|<span data-ttu-id="ca05f-1133">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="ca05f-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1134"></span></span>|
|<span data-ttu-id="ca05f-1135">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="ca05f-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1136"></span></span>|
|<span data-ttu-id="ca05f-1137">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1138"></span></span>|
|<span data-ttu-id="ca05f-1139">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="ca05f-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1140"></span></span>|
|<span data-ttu-id="ca05f-1141">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="ca05f-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1142"></span></span>|
|<span data-ttu-id="ca05f-1143">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1144"></span></span>|
|<span data-ttu-id="ca05f-1145">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="ca05f-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1146"></span></span>|
|<span data-ttu-id="ca05f-1147">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="ca05f-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1148"></span></span>|
|<span data-ttu-id="ca05f-1149">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="ca05f-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1150"></span></span>|
|<span data-ttu-id="ca05f-1151">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="ca05f-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="ca05f-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="ca05f-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="ca05f-1153">额外的证书路径</span><span class="sxs-lookup"><span data-stu-id="ca05f-1153">Additional certificate paths</span></span>
<span data-ttu-id="ca05f-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="ca05f-1154"></span></span>

<span data-ttu-id="ca05f-1155">以下包括旧的证书不包括上面且随着时间的推移将与上面的列表合并。</span><span class="sxs-lookup"><span data-stu-id="ca05f-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
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


