---
title: Office 365 证书链
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/26/2018
ms.audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ROBOTS: NOINDEX, NOFOLLOW
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.assetid: 0c03e6b3-e73f-4316-9e2b-bf4091ae96bb
description: Office 365 利用大量的不同的证书提供商。下面介绍已知客户访问 Office 365 时可能遇到的 Office 365 根证书的完整的列表。您可能需要您自己的基础结构中安装证书的信息，请参阅 Plan 第三方 SSL 证书的 Office 365。下面的证书信息适用于 Office 365 的所有全球和国家/地区云实例。
ms.openlocfilehash: 97e00833e57f8f6b7352650b0efdef51ddba77fa
ms.sourcegitcommit: 659b5f5b38ef7e838cdb44eaa38c18e48d922768
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2018
ms.locfileid: "25575356"
---
# <a name="office-365-certificate-chains"></a><span data-ttu-id="b01bb-106">Office 365 证书链</span><span class="sxs-lookup"><span data-stu-id="b01bb-106">Office 365 Certificate Chains</span></span>

<span data-ttu-id="b01bb-p102">Office 365 利用大量的不同的证书提供商。下面介绍已知客户访问 Office 365 时可能遇到的 Office 365 根证书的完整的列表。您可能需要您自己的基础结构中安装证书信息，请参阅[Office 365 的第三方 SSL 证书计划](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce)。下面的证书信息适用于 Office 365 的所有全球和国家/地区云实例。</span><span class="sxs-lookup"><span data-stu-id="b01bb-p102">Office 365 leverages a number of different certificate providers. The following describes the complete list of known Office 365 root certificates that customers may encounter when accessing Office 365. For information on the certificates you may need to install in your own infrastructure, see [Plan for third-party SSL certificates for Office 365](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce). The following certificate information applies to all worldwide and national cloud instances of Office 365.</span></span>
  

|<span data-ttu-id="b01bb-111">**证书类型**</span><span class="sxs-lookup"><span data-stu-id="b01bb-111">**Certificate type**</span></span>|<span data-ttu-id="b01bb-112">**P7b 下载**</span><span class="sxs-lookup"><span data-stu-id="b01bb-112">**P7b download**</span></span>|<span data-ttu-id="b01bb-113">**CRL 终结点**</span><span class="sxs-lookup"><span data-stu-id="b01bb-113">**CRL Endpoints**</span></span>|<span data-ttu-id="b01bb-114">**OCSP 终结点**</span><span class="sxs-lookup"><span data-stu-id="b01bb-114">**OCSP Endpoints**</span></span>|<span data-ttu-id="b01bb-115">**AIA 终结点**</span><span class="sxs-lookup"><span data-stu-id="b01bb-115">**AIA Endpoints**</span></span>|
|:-----|:-----|:-----|:-----|:-----|
|[<span data-ttu-id="b01bb-116">公共受信任的根证书</span><span class="sxs-lookup"><span data-stu-id="b01bb-116">Publicly Trusted Root Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[<span data-ttu-id="b01bb-117">Office 365 根证书绑定 (P7B)</span><span class="sxs-lookup"><span data-stu-id="b01bb-117">Office 365 Root Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |<span data-ttu-id="b01bb-118">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="b01bb-118">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="b01bb-119">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="b01bb-119">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="b01bb-120">N/A</span><span class="sxs-lookup"><span data-stu-id="b01bb-120">N/A</span></span>  <br/> |<span data-ttu-id="b01bb-121">N/A</span><span class="sxs-lookup"><span data-stu-id="b01bb-121">N/A</span></span>  <br/> |
|[<span data-ttu-id="b01bb-122">公共受信任的中间证书</span><span class="sxs-lookup"><span data-stu-id="b01bb-122">Publicly Trusted Intermediate Certificates</span></span>](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[<span data-ttu-id="b01bb-123">Office 365 中间证书绑定 (P7B)</span><span class="sxs-lookup"><span data-stu-id="b01bb-123">Office 365 Intermediate Certificate Bundle (P7B)</span></span>](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |<span data-ttu-id="b01bb-124">cdp1.public trust.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-124">cdp1.public-trust.com</span></span>  <br/> <span data-ttu-id="b01bb-125">crl.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="b01bb-125">crl.cnnic.cn</span></span>  <br/> <span data-ttu-id="b01bb-126">crl.entrust.net</span><span class="sxs-lookup"><span data-stu-id="b01bb-126">crl.entrust.net</span></span>  <br/> <span data-ttu-id="b01bb-127">crl.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-127">crl.globalsign.com</span></span>  <br/> <span data-ttu-id="b01bb-128">crl.globalsign.net</span><span class="sxs-lookup"><span data-stu-id="b01bb-128">crl.globalsign.net</span></span>  <br/> <span data-ttu-id="b01bb-129">crl.identrust.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-129">crl.identrust.com</span></span>  <br/> <span data-ttu-id="b01bb-130">crl.thawte.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-130">crl.thawte.com</span></span>  <br/> <span data-ttu-id="b01bb-131">crl3.digicert.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-131">crl3.digicert.com</span></span>  <br/> <span data-ttu-id="b01bb-132">crl4.digicert.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-132">crl4.digicert.com</span></span>  <br/> <span data-ttu-id="b01bb-133">s1.symcb.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-133">s1.symcb.com</span></span>  <br/> <span data-ttu-id="b01bb-134">www.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="b01bb-134">www.d-trust.net</span></span>  <br/> |<span data-ttu-id="b01bb-135">isrg.trustid.ocsp.identrust.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-135">isrg.trustid.ocsp.identrust.com</span></span>  <br/> <span data-ttu-id="b01bb-136">ocsp.digicert.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-136">ocsp.digicert.com</span></span>  <br/> <span data-ttu-id="b01bb-137">ocsp.entrust.net</span><span class="sxs-lookup"><span data-stu-id="b01bb-137">ocsp.entrust.net</span></span>  <br/> <span data-ttu-id="b01bb-138">ocsp.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-138">ocsp.globalsign.com</span></span>  <br/> <span data-ttu-id="b01bb-139">ocsp.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-139">ocsp.omniroot.com</span></span>  <br/> <span data-ttu-id="b01bb-140">ocsp.startssl.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-140">ocsp.startssl.com</span></span>  <br/> <span data-ttu-id="b01bb-141">ocsp.thawte.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-141">ocsp.thawte.com</span></span>  <br/> <span data-ttu-id="b01bb-142">ocsp2.globalsign.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-142">ocsp2.globalsign.com</span></span>  <br/> <span data-ttu-id="b01bb-143">ocspcnnicroot.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="b01bb-143">ocspcnnicroot.cnnic.cn</span></span>  <br/> <span data-ttu-id="b01bb-144">根-c3-ca2-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="b01bb-144">root-c3-ca2-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="b01bb-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span><span class="sxs-lookup"><span data-stu-id="b01bb-145">root-c3-ca2-ev-2009.ocsp.d-trust.net</span></span>  <br/> <span data-ttu-id="b01bb-146">s2.symcb.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-146">s2.symcb.com</span></span>  <br/> |<span data-ttu-id="b01bb-147">aia.startssl.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-147">aia.startssl.com</span></span>  <br/> <span data-ttu-id="b01bb-148">apps.identrust.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-148">apps.identrust.com</span></span>  <br/> <span data-ttu-id="b01bb-149">cacert.omniroot.com</span><span class="sxs-lookup"><span data-stu-id="b01bb-149">cacert.omniroot.com</span></span>  <br/> <span data-ttu-id="b01bb-150">www.cnnic.cn</span><span class="sxs-lookup"><span data-stu-id="b01bb-150">www.cnnic.cn</span></span>  <br/> |
   
<span data-ttu-id="b01bb-151">展开根和下面有关证书提供商的其他详细信息，请参阅的中间部分。</span><span class="sxs-lookup"><span data-stu-id="b01bb-151">Expand the root and intermediate sections below to see additional details about the certificate providers.</span></span>
  
## <a name="office-365-root-certificate-details"></a><span data-ttu-id="b01bb-152">Office 365 根证书的详细信息</span><span class="sxs-lookup"><span data-stu-id="b01bb-152">Office 365 Root Certificate Details</span></span>
<span data-ttu-id="b01bb-153"><a name="RootCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="b01bb-153"></span></span>

 <span data-ttu-id="b01bb-154">**Baltimore CyberTrust 根**</span><span class="sxs-lookup"><span data-stu-id="b01bb-154">**Baltimore CyberTrust Root**</span></span>
  
<span data-ttu-id="b01bb-155">|:-----|</span><span class="sxs-lookup"><span data-stu-id="b01bb-155">|:-----|</span></span>
|<span data-ttu-id="b01bb-156">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-156">**Subject**</span></span>|
|:-----|
|<span data-ttu-id="b01bb-157">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-157">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-158">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-158"></span></span>|
|<span data-ttu-id="b01bb-159">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-159">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-160">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-160"></span></span>|
|<span data-ttu-id="b01bb-161">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-161">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-162">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-162"></span></span>|
|<span data-ttu-id="b01bb-163">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-163">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-164">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-164"></span></span>|
|<span data-ttu-id="b01bb-165">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-165">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-166">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-166"></span></span>|
|<span data-ttu-id="b01bb-167">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-167">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-168">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-168"></span></span>|
|<span data-ttu-id="b01bb-169">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-169">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-170">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-170"></span></span>|
|<span data-ttu-id="b01bb-171">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-171">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-172">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-172"></span></span>|
|<span data-ttu-id="b01bb-173">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-173">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-174">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-174"></span></span>|
   
 <span data-ttu-id="b01bb-175">**CNNIC 根**</span><span class="sxs-lookup"><span data-stu-id="b01bb-175">**CNNIC ROOT**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-176">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-176">**Subject**</span></span>|
|<span data-ttu-id="b01bb-177">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-177"></span></span>|
|<span data-ttu-id="b01bb-178">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-178">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-179">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-179"></span></span>|
|<span data-ttu-id="b01bb-180">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-180">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-181">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-181"></span></span>|
|<span data-ttu-id="b01bb-182">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-182">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-183">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-183"></span></span>|
|<span data-ttu-id="b01bb-184">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-184">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-185">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-185"></span></span>|
|<span data-ttu-id="b01bb-186">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-186">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-187">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-187"></span></span>|
|<span data-ttu-id="b01bb-188">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-188">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-189">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-189"></span></span>|
|<span data-ttu-id="b01bb-190">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-190">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-191">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-191"></span></span>|
|<span data-ttu-id="b01bb-192">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-192">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-193">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-193"></span></span>|
|<span data-ttu-id="b01bb-194">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-194">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-195">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-195"></span></span>|
|<span data-ttu-id="b01bb-196">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-196">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-197">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-197"></span></span>|
   
 <span data-ttu-id="b01bb-198">**DigiCert 全局根 CA**</span><span class="sxs-lookup"><span data-stu-id="b01bb-198">**DigiCert Global Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-199">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-199">**Subject**</span></span>|
|<span data-ttu-id="b01bb-200">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-200"></span></span>|
|<span data-ttu-id="b01bb-201">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-201">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-202">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-202"></span></span>|
|<span data-ttu-id="b01bb-203">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-203">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-204">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-204"></span></span>|
|<span data-ttu-id="b01bb-205">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-205">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-206">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-206"></span></span>|
|<span data-ttu-id="b01bb-207">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-207">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-208">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-208"></span></span>|
|<span data-ttu-id="b01bb-209">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-209">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-210">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-210"></span></span>|
|<span data-ttu-id="b01bb-211">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-211">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-212">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-212"></span></span>|
|<span data-ttu-id="b01bb-213">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-213">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-214">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-214"></span></span>|
|<span data-ttu-id="b01bb-215">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-215">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-216">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-216"></span></span>|
|<span data-ttu-id="b01bb-217">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-217">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-218">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-218"></span></span>|
|<span data-ttu-id="b01bb-219">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-219">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-220">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-220"></span></span>|
   
 <span data-ttu-id="b01bb-221">**DigiCert 高保证 EV 根 CA**</span><span class="sxs-lookup"><span data-stu-id="b01bb-221">**DigiCert High Assurance EV Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-222">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-222">**Subject**</span></span>|
|<span data-ttu-id="b01bb-223">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-223"></span></span>|
|<span data-ttu-id="b01bb-224">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-224">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-225">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-225"></span></span>|
|<span data-ttu-id="b01bb-226">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-226">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-227">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-227"></span></span>|
|<span data-ttu-id="b01bb-228">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-228">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-229">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-229"></span></span>|
|<span data-ttu-id="b01bb-230">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-230">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-231">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-231"></span></span>|
|<span data-ttu-id="b01bb-232">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-232">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-233">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-233"></span></span>|
|<span data-ttu-id="b01bb-234">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-234">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-235">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-235"></span></span>|
|<span data-ttu-id="b01bb-236">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-236">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-237">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-237"></span></span>|
|<span data-ttu-id="b01bb-238">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-238">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-239">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-239"></span></span>|
|<span data-ttu-id="b01bb-240">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-240">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-241">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-241"></span></span>|
|<span data-ttu-id="b01bb-242">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-242">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-243">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-243"></span></span>|
   
 <span data-ttu-id="b01bb-244">**D 信任根类 3 CA 2 2009**</span><span class="sxs-lookup"><span data-stu-id="b01bb-244">**D-TRUST Root Class 3 CA 2 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-245">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-245">**Subject**</span></span>|
|<span data-ttu-id="b01bb-246">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-246"></span></span>|
|<span data-ttu-id="b01bb-247">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-247">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-248">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-248"></span></span>|
|<span data-ttu-id="b01bb-249">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-249">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-250">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-250"></span></span>|
|<span data-ttu-id="b01bb-251">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-251">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-252">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-252"></span></span>|
|<span data-ttu-id="b01bb-253">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-253">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-254">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-254"></span></span>|
|<span data-ttu-id="b01bb-255">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-255">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-256">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-256"></span></span>|
|<span data-ttu-id="b01bb-257">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-257">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-258">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-258"></span></span>|
|<span data-ttu-id="b01bb-259">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-259">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-260">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-260"></span></span>|
|<span data-ttu-id="b01bb-261">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-261">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-262">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-262"></span></span>|
|<span data-ttu-id="b01bb-263">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-263">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-264">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-264"></span></span>|
|<span data-ttu-id="b01bb-265">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-265">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-266">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-266"></span></span>|
   
 <span data-ttu-id="b01bb-267">**D 信任根类 3 CA 2 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="b01bb-267">**D-TRUST Root Class 3 CA 2 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-268">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-268">**Subject**</span></span>|
|<span data-ttu-id="b01bb-269">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-269"></span></span>|
|<span data-ttu-id="b01bb-270">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-270">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-271">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-271"></span></span>|
|<span data-ttu-id="b01bb-272">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-272">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-273">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-273"></span></span>|
|<span data-ttu-id="b01bb-274">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-274">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-275">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-275"></span></span>|
|<span data-ttu-id="b01bb-276">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-276">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-277">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-277"></span></span>|
|<span data-ttu-id="b01bb-278">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-278">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-279">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-279"></span></span>|
|<span data-ttu-id="b01bb-280">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-280">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-281">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-281"></span></span>|
|<span data-ttu-id="b01bb-282">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-282">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-283">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-283"></span></span>|
|<span data-ttu-id="b01bb-284">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-284">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-285">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-285"></span></span>|
|<span data-ttu-id="b01bb-286">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-286">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-287">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-287"></span></span>|
|<span data-ttu-id="b01bb-288">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-288">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-289">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-289"></span></span>|
   
 <span data-ttu-id="b01bb-290">**DST 根 CA X3**</span><span class="sxs-lookup"><span data-stu-id="b01bb-290">**DST Root CA X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-291">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-291">**Subject**</span></span>|
|<span data-ttu-id="b01bb-292">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-292"></span></span>|
|<span data-ttu-id="b01bb-293">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-293">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-294">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-294"></span></span>|
|<span data-ttu-id="b01bb-295">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-295">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-296">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-296"></span></span>|
|<span data-ttu-id="b01bb-297">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-297">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-298">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-298"></span></span>|
|<span data-ttu-id="b01bb-299">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-299">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-300">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-300"></span></span>|
|<span data-ttu-id="b01bb-301">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-301">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-302">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-302"></span></span>|
|<span data-ttu-id="b01bb-303">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-303">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-304">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-304"></span></span>|
|<span data-ttu-id="b01bb-305">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-305">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-306">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-306"></span></span>|
|<span data-ttu-id="b01bb-307">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-307">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-308">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-308"></span></span>|
|<span data-ttu-id="b01bb-309">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-309">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-310">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-310"></span></span>|
   
 <span data-ttu-id="b01bb-311">**委托根证书颁发机构-G2**</span><span class="sxs-lookup"><span data-stu-id="b01bb-311">**Entrust Root Certification Authority - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-312">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-312">**Subject**</span></span>|
|<span data-ttu-id="b01bb-313">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-313"></span></span>|
|<span data-ttu-id="b01bb-314">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-314">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-315">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-315"></span></span>|
|<span data-ttu-id="b01bb-316">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-316">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-317">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-317"></span></span>|
|<span data-ttu-id="b01bb-318">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-318">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-319">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-319"></span></span>|
|<span data-ttu-id="b01bb-320">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-320">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-321">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-321"></span></span>|
|<span data-ttu-id="b01bb-322">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-322">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-323">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-323"></span></span>|
|<span data-ttu-id="b01bb-324">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-324">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-325">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-325"></span></span>|
|<span data-ttu-id="b01bb-326">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-326">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-327">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-327"></span></span>|
|<span data-ttu-id="b01bb-328">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-328">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-329">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-329"></span></span>|
|<span data-ttu-id="b01bb-330">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-330">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-331">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-331"></span></span>|
   
 <span data-ttu-id="b01bb-332">**Entrust.net Certification Authority (2048)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-332">**Entrust.net Certification Authority (2048)**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-333">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-333">**Subject**</span></span>|
|<span data-ttu-id="b01bb-334">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-334"></span></span>|
|<span data-ttu-id="b01bb-335">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-335">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-336">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-336"></span></span>|
|<span data-ttu-id="b01bb-337">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-337">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-338">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-338"></span></span>|
|<span data-ttu-id="b01bb-339">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-339">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-340">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-340"></span></span>|
|<span data-ttu-id="b01bb-341">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-341">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-342">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-342"></span></span>|
|<span data-ttu-id="b01bb-343">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-343">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-344">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-344"></span></span>|
|<span data-ttu-id="b01bb-345">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-345">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-346">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-346"></span></span>|
|<span data-ttu-id="b01bb-347">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-347">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-348">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-348"></span></span>|
|<span data-ttu-id="b01bb-349">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-349">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-350">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-350"></span></span>|
|<span data-ttu-id="b01bb-351">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-351">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-352">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-352"></span></span>|
   
 <span data-ttu-id="b01bb-353">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="b01bb-353">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-354">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-354">**Subject**</span></span>|
|<span data-ttu-id="b01bb-355">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-355"></span></span>|
|<span data-ttu-id="b01bb-356">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-356">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-357">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-357"></span></span>|
|<span data-ttu-id="b01bb-358">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-358">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-359">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-359"></span></span>|
|<span data-ttu-id="b01bb-360">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-360">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-361">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-361"></span></span>|
|<span data-ttu-id="b01bb-362">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-362">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-363">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-363"></span></span>|
|<span data-ttu-id="b01bb-364">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-364">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-365">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-365"></span></span>|
|<span data-ttu-id="b01bb-366">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-366">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-367">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-367"></span></span>|
|<span data-ttu-id="b01bb-368">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-368">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-369">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-369"></span></span>|
|<span data-ttu-id="b01bb-370">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-370">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-371">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-371"></span></span>|
|<span data-ttu-id="b01bb-372">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-372">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-373">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-373"></span></span>|
|<span data-ttu-id="b01bb-374">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-374">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-375">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-375"></span></span>|
|<span data-ttu-id="b01bb-376">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-376">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-377">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-377"></span></span>|
   
 <span data-ttu-id="b01bb-378">**GlobalSign Root CA**</span><span class="sxs-lookup"><span data-stu-id="b01bb-378">**GlobalSign Root CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-379">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-379">**Subject**</span></span>|
|<span data-ttu-id="b01bb-380">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-380"></span></span>|
|<span data-ttu-id="b01bb-381">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-381">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-382">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-382"></span></span>|
|<span data-ttu-id="b01bb-383">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-383">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-384">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-384"></span></span>|
|<span data-ttu-id="b01bb-385">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-385">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-386">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-386"></span></span>|
|<span data-ttu-id="b01bb-387">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-387">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-388">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-388"></span></span>|
|<span data-ttu-id="b01bb-389">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-389">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-390">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-390"></span></span>|
|<span data-ttu-id="b01bb-391">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-391">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-392">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-392"></span></span>|
|<span data-ttu-id="b01bb-393">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-393">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-394">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-394"></span></span>|
|<span data-ttu-id="b01bb-395">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-395">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-396">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-396"></span></span>|
|<span data-ttu-id="b01bb-397">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-397">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-398">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-398"></span></span>|
   
 <span data-ttu-id="b01bb-399">**thawte 主根 CA-G3**</span><span class="sxs-lookup"><span data-stu-id="b01bb-399">**thawte Primary Root CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-400">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-400">**Subject**</span></span>|
|<span data-ttu-id="b01bb-401">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-401"></span></span>|
|<span data-ttu-id="b01bb-402">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-402">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-403">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-403"></span></span>|
|<span data-ttu-id="b01bb-404">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-404">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-405">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-405"></span></span>|
|<span data-ttu-id="b01bb-406">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-406">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-407">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-407"></span></span>|
|<span data-ttu-id="b01bb-408">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-408">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-409">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-409"></span></span>|
|<span data-ttu-id="b01bb-410">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-410">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-411">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-411"></span></span>|
|<span data-ttu-id="b01bb-412">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-412">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-413">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-413"></span></span>|
|<span data-ttu-id="b01bb-414">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-414">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-415">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-415"></span></span>|
|<span data-ttu-id="b01bb-416">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-416">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-417">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-417"></span></span>|
|<span data-ttu-id="b01bb-418">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-418">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-419">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-419"></span></span>|
   
 <span data-ttu-id="b01bb-420">**VeriSign 类 3 主要公用证书颁发机构-G5**</span><span class="sxs-lookup"><span data-stu-id="b01bb-420">**VeriSign Class 3 Public Primary Certification Authority - G5**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-421">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-421">**Subject**</span></span>|
|<span data-ttu-id="b01bb-422">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-422"></span></span>|
|<span data-ttu-id="b01bb-423">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-423">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-424">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-424"></span></span>|
|<span data-ttu-id="b01bb-425">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-425">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-426">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-426"></span></span>|
|<span data-ttu-id="b01bb-427">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-427">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-428">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-428"></span></span>|
|<span data-ttu-id="b01bb-429">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-429">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-430">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-430"></span></span>|
|<span data-ttu-id="b01bb-431">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-431">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-432">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-432"></span></span>|
|<span data-ttu-id="b01bb-433">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-433">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-434">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-434"></span></span>|
|<span data-ttu-id="b01bb-435">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-435">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-436">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-436"></span></span>|
|<span data-ttu-id="b01bb-437">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-437">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-438">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-438"></span></span>|
|<span data-ttu-id="b01bb-439">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-439">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-440">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-440"></span></span>|
   
## <a name="office-365-intermediate-certificate-details"></a><span data-ttu-id="b01bb-441">Office 365 中间证书详细信息</span><span class="sxs-lookup"><span data-stu-id="b01bb-441">Office 365 Intermediate Certificate Details</span></span>
<span data-ttu-id="b01bb-442"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="b01bb-442"></span></span>

 <span data-ttu-id="b01bb-443">**CNNIC SHA256 SSL**</span><span class="sxs-lookup"><span data-stu-id="b01bb-443">**CNNIC SHA256 SSL**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-444">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-444">**Subject**</span></span>|
|<span data-ttu-id="b01bb-445">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-445"></span></span>|
|<span data-ttu-id="b01bb-446">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-446">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-447">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-447"></span></span>|
|<span data-ttu-id="b01bb-448">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-448">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-449">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-449"></span></span>|
|<span data-ttu-id="b01bb-450">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-450">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-451">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-451"></span></span>|
|<span data-ttu-id="b01bb-452">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-452">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-453">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-453"></span></span>|
|<span data-ttu-id="b01bb-454">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-454">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-455">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-455"></span></span>|
|<span data-ttu-id="b01bb-456">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-456">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-457">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-457"></span></span>|
|<span data-ttu-id="b01bb-458">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-458">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-459">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-459"></span></span>|
|<span data-ttu-id="b01bb-460">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-460">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-461">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-461"></span></span>|
|<span data-ttu-id="b01bb-462">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-462">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-463">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-463"></span></span>|
|<span data-ttu-id="b01bb-464">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-464">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-465">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-465"></span></span>|
|<span data-ttu-id="b01bb-466">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-466">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-467">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-467"></span></span>|
|<span data-ttu-id="b01bb-468">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-468">**AIA URLs**</span></span>|
|<span data-ttu-id="b01bb-469">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-469"></span></span>|
|<span data-ttu-id="b01bb-470">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-470">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-471">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-471"></span></span>|
|<span data-ttu-id="b01bb-472">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-472">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-473">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-473"></span></span>|
   
 <span data-ttu-id="b01bb-474">**D 信任 SSL 类 3 CA 1 2009**</span><span class="sxs-lookup"><span data-stu-id="b01bb-474">**D-TRUST SSL Class 3 CA 1 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-475">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-475">**Subject**</span></span>|
|<span data-ttu-id="b01bb-476">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-476"></span></span>|
|<span data-ttu-id="b01bb-477">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-477">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-478">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-478"></span></span>|
|<span data-ttu-id="b01bb-479">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="b01bb-479">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="b01bb-480">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-480"></span></span>|
|<span data-ttu-id="b01bb-481">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-481">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-482">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-482"></span></span>|
|<span data-ttu-id="b01bb-483">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-483">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-484">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-484"></span></span>|
|<span data-ttu-id="b01bb-485">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-485">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-486">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-486"></span></span>|
|<span data-ttu-id="b01bb-487">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-487">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-488">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-488"></span></span>|
|<span data-ttu-id="b01bb-489">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-489">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-490">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-490"></span></span>|
|<span data-ttu-id="b01bb-491">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-491">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-492">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-492"></span></span>|
|<span data-ttu-id="b01bb-493">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-493">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-494">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-494"></span></span>|
|<span data-ttu-id="b01bb-495">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-495">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-496">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-496"></span></span>|
|<span data-ttu-id="b01bb-497">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-497">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-498">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-498"></span></span>|
|<span data-ttu-id="b01bb-499">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-499">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-500">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-500"></span></span>|
|<span data-ttu-id="b01bb-501">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-501">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-502">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-502"></span></span>|
|<span data-ttu-id="b01bb-503">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-503">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-504">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-504"></span></span>|
   
 <span data-ttu-id="b01bb-505">**D 信任 SSL 类 3 CA 1 EV 2009**</span><span class="sxs-lookup"><span data-stu-id="b01bb-505">**D-TRUST SSL Class 3 CA 1 EV 2009**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-506">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-506">**Subject**</span></span>|
|<span data-ttu-id="b01bb-507">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-507"></span></span>|
|<span data-ttu-id="b01bb-508">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-508">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-509">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-509"></span></span>|
|<span data-ttu-id="b01bb-510">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="b01bb-510">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="b01bb-511">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-511"></span></span>|
|<span data-ttu-id="b01bb-512">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-512">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-513">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-513"></span></span>|
|<span data-ttu-id="b01bb-514">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-514">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-515">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-515"></span></span>|
|<span data-ttu-id="b01bb-516">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-516">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-517">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-517"></span></span>|
|<span data-ttu-id="b01bb-518">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-518">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-519">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-519"></span></span>|
|<span data-ttu-id="b01bb-520">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-520">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-521">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-521"></span></span>|
|<span data-ttu-id="b01bb-522">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-522">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-523">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-523"></span></span>|
|<span data-ttu-id="b01bb-524">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-524">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-525">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-525"></span></span>|
|<span data-ttu-id="b01bb-526">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-526">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-527">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-527"></span></span>|
|<span data-ttu-id="b01bb-528">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-528">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-529">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-529"></span></span>|
|<span data-ttu-id="b01bb-530">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-530">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-531">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-531"></span></span>|
|<span data-ttu-id="b01bb-532">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-532">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-533">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-533"></span></span>|
|<span data-ttu-id="b01bb-534">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-534">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-535">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-535"></span></span>|
   
 <span data-ttu-id="b01bb-536">**DigiCert 云服务 CA-1**</span><span class="sxs-lookup"><span data-stu-id="b01bb-536">**DigiCert Cloud Services CA-1**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-537">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-537">**Subject**</span></span>|
|<span data-ttu-id="b01bb-538">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-538"></span></span>|
|<span data-ttu-id="b01bb-539">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-539">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-540">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-540"></span></span>|
|<span data-ttu-id="b01bb-541">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-541">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-542">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-542"></span></span>|
|<span data-ttu-id="b01bb-543">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-543">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-544">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-544"></span></span>|
|<span data-ttu-id="b01bb-545">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-545">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-546">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-546"></span></span>|
|<span data-ttu-id="b01bb-547">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-547">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-548">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-548"></span></span>|
|<span data-ttu-id="b01bb-549">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-549">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-550">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-550"></span></span>|
|<span data-ttu-id="b01bb-551">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-551">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-552">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-552"></span></span>|
|<span data-ttu-id="b01bb-553">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-553">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-554">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-554"></span></span>|
|<span data-ttu-id="b01bb-555">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-555">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-556">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-556"></span></span>|
|<span data-ttu-id="b01bb-557">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-557">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-558">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-558"></span></span>|
|<span data-ttu-id="b01bb-559">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-559">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-560">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-560"></span></span>|
|<span data-ttu-id="b01bb-561">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-561">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-562">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-562"></span></span>|
|<span data-ttu-id="b01bb-563">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-563">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-564">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-564"></span></span>|
   
 <span data-ttu-id="b01bb-565">**DigiCert SHA2 高保证服务器 CA**</span><span class="sxs-lookup"><span data-stu-id="b01bb-565">**DigiCert SHA2 High Assurance Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-566">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-566">**Subject**</span></span>|
|<span data-ttu-id="b01bb-567">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-567"></span></span>|
|<span data-ttu-id="b01bb-568">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-568">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-569">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-569"></span></span>|
|<span data-ttu-id="b01bb-570">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-570">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-571">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-571"></span></span>|
|<span data-ttu-id="b01bb-572">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-572">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-573">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-573"></span></span>|
|<span data-ttu-id="b01bb-574">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-574">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-575">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-575"></span></span>|
|<span data-ttu-id="b01bb-576">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-576">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-577">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-577"></span></span>|
|<span data-ttu-id="b01bb-578">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-578">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-579">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-579"></span></span>|
|<span data-ttu-id="b01bb-580">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-580">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-581">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-581"></span></span>|
|<span data-ttu-id="b01bb-582">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-582">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-583">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-583"></span></span>|
|<span data-ttu-id="b01bb-584">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-584">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-585">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-585"></span></span>|
|<span data-ttu-id="b01bb-586">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-586">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-587">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-587"></span></span>|
|<span data-ttu-id="b01bb-588">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-588">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-589">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-589"></span></span>|
|<span data-ttu-id="b01bb-590">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-590">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-591">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-591"></span></span>|
|<span data-ttu-id="b01bb-592">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-592">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-593">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-593"></span></span>|
   
 <span data-ttu-id="b01bb-594">**DigiCert SHA2 安全服务器 CA**</span><span class="sxs-lookup"><span data-stu-id="b01bb-594">**DigiCert SHA2 Secure Server CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-595">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-595">**Subject**</span></span>|
|<span data-ttu-id="b01bb-596">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-596"></span></span>|
|<span data-ttu-id="b01bb-597">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-597">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-598">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-598"></span></span>|
|<span data-ttu-id="b01bb-599">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-599">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-600">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-600"></span></span>|
|<span data-ttu-id="b01bb-601">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-601">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-602">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-602"></span></span>|
|<span data-ttu-id="b01bb-603">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-603">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-604">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-604"></span></span>|
|<span data-ttu-id="b01bb-605">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-605">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-606">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-606"></span></span>|
|<span data-ttu-id="b01bb-607">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-607">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-608">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-608"></span></span>|
|<span data-ttu-id="b01bb-609">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-609">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-610">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-610"></span></span>|
|<span data-ttu-id="b01bb-611">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-611">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-612">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-612"></span></span>|
|<span data-ttu-id="b01bb-613">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-613">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-614">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-614"></span></span>|
|<span data-ttu-id="b01bb-615">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-615">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-616">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-616"></span></span>|
|<span data-ttu-id="b01bb-617">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-617">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-618">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-618"></span></span>|
|<span data-ttu-id="b01bb-619">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-619">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-620">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-620"></span></span>|
|<span data-ttu-id="b01bb-621">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-621">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-622">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-622"></span></span>|
   
 <span data-ttu-id="b01bb-623">**委托 L1C 的证书颁发机构-**</span><span class="sxs-lookup"><span data-stu-id="b01bb-623">**Entrust Certification Authority - L1C**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-624">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-624">**Subject**</span></span>|
|<span data-ttu-id="b01bb-625">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-625"></span></span>|
|<span data-ttu-id="b01bb-626">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-626">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-627">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-627"></span></span>|
|<span data-ttu-id="b01bb-628">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-628">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-629">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-629"></span></span>|
|<span data-ttu-id="b01bb-630">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-630">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-631">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-631"></span></span>|
|<span data-ttu-id="b01bb-632">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-632">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-633">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-633"></span></span>|
|<span data-ttu-id="b01bb-634">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-634">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-635">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-635"></span></span>|
|<span data-ttu-id="b01bb-636">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-636">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-637">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-637"></span></span>|
|<span data-ttu-id="b01bb-638">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-638">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-639">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-639"></span></span>|
|<span data-ttu-id="b01bb-640">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-640">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-641">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-641"></span></span>|
|<span data-ttu-id="b01bb-642">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-642">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-643">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-643"></span></span>|
|<span data-ttu-id="b01bb-644">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-644">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-645">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-645"></span></span>|
|<span data-ttu-id="b01bb-646">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-646">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-647">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-647"></span></span>|
|<span data-ttu-id="b01bb-648">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-648">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-649">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-649"></span></span>|
|<span data-ttu-id="b01bb-650">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-650">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-651">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-651"></span></span>|
   
 <span data-ttu-id="b01bb-652">**委托 L1K 的证书颁发机构-**</span><span class="sxs-lookup"><span data-stu-id="b01bb-652">**Entrust Certification Authority - L1K**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-653">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-653">**Subject**</span></span>|
|<span data-ttu-id="b01bb-654">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-654"></span></span>|
|<span data-ttu-id="b01bb-655">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-655">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-656">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-656"></span></span>|
|<span data-ttu-id="b01bb-657">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-657">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-658">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-658"></span></span>|
|<span data-ttu-id="b01bb-659">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-659">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-660">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-660"></span></span>|
|<span data-ttu-id="b01bb-661">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-661">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-662">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-662"></span></span>|
|<span data-ttu-id="b01bb-663">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-663">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-664">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-664"></span></span>|
|<span data-ttu-id="b01bb-665">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-665">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-666">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-666"></span></span>|
|<span data-ttu-id="b01bb-667">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-667">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-668">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-668"></span></span>|
|<span data-ttu-id="b01bb-669">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-669">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-670">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-670"></span></span>|
|<span data-ttu-id="b01bb-671">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-671">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-672">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-672"></span></span>|
|<span data-ttu-id="b01bb-673">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-673">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-674">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-674"></span></span>|
|<span data-ttu-id="b01bb-675">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-675">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-676">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-676"></span></span>|
|<span data-ttu-id="b01bb-677">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-677">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-678">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-678"></span></span>|
|<span data-ttu-id="b01bb-679">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-679">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-680">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-680"></span></span>|
   
 <span data-ttu-id="b01bb-681">**GlobalSign**</span><span class="sxs-lookup"><span data-stu-id="b01bb-681">**GlobalSign**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-682">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-682">**Subject**</span></span>|
|<span data-ttu-id="b01bb-683">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-683"></span></span>|
|<span data-ttu-id="b01bb-684">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-684">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-685">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-685"></span></span>|
|<span data-ttu-id="b01bb-686">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-686">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-687">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-687"></span></span>|
|<span data-ttu-id="b01bb-688">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-688">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-689">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-689"></span></span>|
|<span data-ttu-id="b01bb-690">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-690">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-691">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-691"></span></span>|
|<span data-ttu-id="b01bb-692">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-692">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-693">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-693"></span></span>|
|<span data-ttu-id="b01bb-694">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-694">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-695">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-695"></span></span>|
|<span data-ttu-id="b01bb-696">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-696">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-697">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-697"></span></span>|
|<span data-ttu-id="b01bb-698">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-698">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-699">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-699"></span></span>|
|<span data-ttu-id="b01bb-700">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-700">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-701">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-701"></span></span>|
|<span data-ttu-id="b01bb-702">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-702">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-703">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-703"></span></span>|
|<span data-ttu-id="b01bb-704">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-704">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-705">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-705"></span></span>|
|<span data-ttu-id="b01bb-706">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-706">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-707">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-707"></span></span>|
|<span data-ttu-id="b01bb-708">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-708">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-709">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-709"></span></span>|
   
 <span data-ttu-id="b01bb-710">**GlobalSign 扩展验证 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="b01bb-710">**GlobalSign Extended Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-711">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-711">**Subject**</span></span>|
|<span data-ttu-id="b01bb-712">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-712"></span></span>|
|<span data-ttu-id="b01bb-713">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-713">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-714">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-714"></span></span>|
|<span data-ttu-id="b01bb-715">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-715">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-716">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-716"></span></span>|
|<span data-ttu-id="b01bb-717">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-717">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-718">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-718"></span></span>|
|<span data-ttu-id="b01bb-719">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-719">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-720">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-720"></span></span>|
|<span data-ttu-id="b01bb-721">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-721">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-722">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-722"></span></span>|
|<span data-ttu-id="b01bb-723">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-723">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-724">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-724"></span></span>|
|<span data-ttu-id="b01bb-725">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-725">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-726">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-726"></span></span>|
|<span data-ttu-id="b01bb-727">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-727">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-728">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-728"></span></span>|
|<span data-ttu-id="b01bb-729">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-729">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-730">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-730"></span></span>|
|<span data-ttu-id="b01bb-731">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-731">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-732">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-732"></span></span>|
|<span data-ttu-id="b01bb-733">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-733">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-734">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-734"></span></span>|
|<span data-ttu-id="b01bb-735">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-735">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-736">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-736"></span></span>|
|<span data-ttu-id="b01bb-737">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-737">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-738">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-738"></span></span>|
   
 <span data-ttu-id="b01bb-739">**GlobalSign 扩展验证 CA-SHA256-G3**</span><span class="sxs-lookup"><span data-stu-id="b01bb-739">**GlobalSign Extended Validation CA - SHA256 - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-740">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-740">**Subject**</span></span>|
|<span data-ttu-id="b01bb-741">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-741"></span></span>|
|<span data-ttu-id="b01bb-742">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-742">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-743">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-743"></span></span>|
|<span data-ttu-id="b01bb-744">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-744">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-745">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-745"></span></span>|
|<span data-ttu-id="b01bb-746">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-746">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-747">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-747"></span></span>|
|<span data-ttu-id="b01bb-748">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-748">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-749">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-749"></span></span>|
|<span data-ttu-id="b01bb-750">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-750">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-751">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-751"></span></span>|
|<span data-ttu-id="b01bb-752">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-752">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-753">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-753"></span></span>|
|<span data-ttu-id="b01bb-754">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-754">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-755">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-755"></span></span>|
|<span data-ttu-id="b01bb-756">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-756">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-757">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-757"></span></span>|
|<span data-ttu-id="b01bb-758">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-758">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-759">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-759"></span></span>|
|<span data-ttu-id="b01bb-760">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-760">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-761">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-761"></span></span>|
|<span data-ttu-id="b01bb-762">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-762">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-763">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-763"></span></span>|
|<span data-ttu-id="b01bb-764">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-764">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-765">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-765"></span></span>|
|<span data-ttu-id="b01bb-766">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-766">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-767">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-767"></span></span>|
   
 <span data-ttu-id="b01bb-768">**GlobalSign 组织验证 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="b01bb-768">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-769">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-769">**Subject**</span></span>|
|<span data-ttu-id="b01bb-770">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-770"></span></span>|
|<span data-ttu-id="b01bb-771">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-771">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-772">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-772"></span></span>|
|<span data-ttu-id="b01bb-773">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-773">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-774">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-774"></span></span>|
|<span data-ttu-id="b01bb-775">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-775">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-776">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-776"></span></span>|
|<span data-ttu-id="b01bb-777">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-777">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-778">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-778"></span></span>|
|<span data-ttu-id="b01bb-779">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-779">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-780">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-780"></span></span>|
|<span data-ttu-id="b01bb-781">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-781">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-782">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-782"></span></span>|
|<span data-ttu-id="b01bb-783">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-783">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-784">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-784"></span></span>|
|<span data-ttu-id="b01bb-785">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-785">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-786">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-786"></span></span>|
|<span data-ttu-id="b01bb-787">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-787">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-788">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-788"></span></span>|
|<span data-ttu-id="b01bb-789">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-789">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-790">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-790"></span></span>|
|<span data-ttu-id="b01bb-791">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-791">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-792">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-792"></span></span>|
|<span data-ttu-id="b01bb-793">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-793">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-794">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-794"></span></span>|
|<span data-ttu-id="b01bb-795">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-795">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-796">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-796"></span></span>|
   
 <span data-ttu-id="b01bb-797">**GlobalSign 组织验证 CA-SHA256-G2**</span><span class="sxs-lookup"><span data-stu-id="b01bb-797">**GlobalSign Organization Validation CA - SHA256 - G2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-798">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-798">**Subject**</span></span>|
|<span data-ttu-id="b01bb-799">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-799"></span></span>|
|<span data-ttu-id="b01bb-800">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-800">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-801">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-801"></span></span>|
|<span data-ttu-id="b01bb-802">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-802">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-803">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-803"></span></span>|
|<span data-ttu-id="b01bb-804">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-804">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-805">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-805"></span></span>|
|<span data-ttu-id="b01bb-806">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-806">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-807">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-807"></span></span>|
|<span data-ttu-id="b01bb-808">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-808">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-809">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-809"></span></span>|
|<span data-ttu-id="b01bb-810">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-810">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-811">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-811"></span></span>|
|<span data-ttu-id="b01bb-812">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-812">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-813">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-813"></span></span>|
|<span data-ttu-id="b01bb-814">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-814">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-815">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-815"></span></span>|
|<span data-ttu-id="b01bb-816">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-816">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-817">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-817"></span></span>|
|<span data-ttu-id="b01bb-818">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-818">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-819">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-819"></span></span>|
|<span data-ttu-id="b01bb-820">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-820">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-821">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-821"></span></span>|
|<span data-ttu-id="b01bb-822">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-822">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-823">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-823"></span></span>|
|<span data-ttu-id="b01bb-824">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-824">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-825">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-825"></span></span>|
   
 <span data-ttu-id="b01bb-826">**让我们加密证书颁发机构 X3**</span><span class="sxs-lookup"><span data-stu-id="b01bb-826">**Let's Encrypt Authority X3**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-827">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-827">**Subject**</span></span>|
|<span data-ttu-id="b01bb-828">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-828"></span></span>|
|<span data-ttu-id="b01bb-829">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-829">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-830">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-830"></span></span>|
|<span data-ttu-id="b01bb-831">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-831">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-832">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-832"></span></span>|
|<span data-ttu-id="b01bb-833">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-833">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-834">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-834"></span></span>|
|<span data-ttu-id="b01bb-835">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-835">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-836">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-836"></span></span>|
|<span data-ttu-id="b01bb-837">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-837">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-838">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-838"></span></span>|
|<span data-ttu-id="b01bb-839">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-839">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-840">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-840"></span></span>|
|<span data-ttu-id="b01bb-841">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-841">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-842">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-842"></span></span>|
|<span data-ttu-id="b01bb-843">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-843">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-844">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-844"></span></span>|
|<span data-ttu-id="b01bb-845">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-845">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-846">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-846"></span></span>|
|<span data-ttu-id="b01bb-847">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-847">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-848">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-848"></span></span>|
|<span data-ttu-id="b01bb-849">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-849">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-850">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-850"></span></span>|
|<span data-ttu-id="b01bb-851">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-851">**AIA URLs**</span></span>|
|<span data-ttu-id="b01bb-852">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-852"></span></span>|
|<span data-ttu-id="b01bb-853">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-853">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-854">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-854"></span></span>|
|<span data-ttu-id="b01bb-855">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-855">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-856">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-856"></span></span>|
   
 <span data-ttu-id="b01bb-857">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="b01bb-857">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-858">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-858">**Subject**</span></span>|
|<span data-ttu-id="b01bb-859">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-859"></span></span>|
|<span data-ttu-id="b01bb-860">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-860">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-861">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-861"></span></span>|
|<span data-ttu-id="b01bb-862">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-862">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-863">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-863"></span></span>|
|<span data-ttu-id="b01bb-864">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-864">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-865">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-865"></span></span>|
|<span data-ttu-id="b01bb-866">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-866">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-867">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-867"></span></span>|
|<span data-ttu-id="b01bb-868">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-868">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-869">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-869"></span></span>|
|<span data-ttu-id="b01bb-870">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-870">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-871">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-871"></span></span>|
|<span data-ttu-id="b01bb-872">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-872">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-873">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-873"></span></span>|
|<span data-ttu-id="b01bb-874">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-874">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-875">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-875"></span></span>|
|<span data-ttu-id="b01bb-876">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-876">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-877">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-877"></span></span>|
|<span data-ttu-id="b01bb-878">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-878">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-879">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-879"></span></span>|
|<span data-ttu-id="b01bb-880">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-880">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-881">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-881"></span></span>|
|<span data-ttu-id="b01bb-882">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-882">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-883">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-883"></span></span>|
   
 <span data-ttu-id="b01bb-884">**Microsoft IT SSL SHA2**</span><span class="sxs-lookup"><span data-stu-id="b01bb-884">**Microsoft IT SSL SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-885">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-885">**Subject**</span></span>|
|<span data-ttu-id="b01bb-886">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-886"></span></span>|
|<span data-ttu-id="b01bb-887">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-887">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-888">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-888"></span></span>|
|<span data-ttu-id="b01bb-889">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-889">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-890">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-890"></span></span>|
|<span data-ttu-id="b01bb-891">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-891">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-892">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-892"></span></span>|
|<span data-ttu-id="b01bb-893">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-893">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-894">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-894"></span></span>|
|<span data-ttu-id="b01bb-895">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-895">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-896">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-896"></span></span>|
|<span data-ttu-id="b01bb-897">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-897">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-898">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-898"></span></span>|
|<span data-ttu-id="b01bb-899">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-899">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-900">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-900"></span></span>|
|<span data-ttu-id="b01bb-901">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-901">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-902">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-902"></span></span>|
|<span data-ttu-id="b01bb-903">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-903">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-904">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-904"></span></span>|
|<span data-ttu-id="b01bb-905">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-905">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-906">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-906"></span></span>|
|<span data-ttu-id="b01bb-907">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-907">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-908">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-908"></span></span>|
|<span data-ttu-id="b01bb-909">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-909">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-910">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-910"></span></span>|
|<span data-ttu-id="b01bb-911">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-911">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-912">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-912"></span></span>|
   
 <span data-ttu-id="b01bb-913">**Microsoft IT TLS CA 1**</span><span class="sxs-lookup"><span data-stu-id="b01bb-913">**Microsoft IT TLS CA 1**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-914">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-914">**Subject**</span></span>|
|<span data-ttu-id="b01bb-915">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-915"></span></span>|
|<span data-ttu-id="b01bb-916">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-916">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-917">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-917"></span></span>|
|<span data-ttu-id="b01bb-918">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-918">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-919">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-919"></span></span>|
|<span data-ttu-id="b01bb-920">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-920">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-921">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-921"></span></span>|
|<span data-ttu-id="b01bb-922">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-922">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-923">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-923"></span></span>|
|<span data-ttu-id="b01bb-924">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-924">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-925">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-925"></span></span>|
|<span data-ttu-id="b01bb-926">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-926">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-927">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-927"></span></span>|
|<span data-ttu-id="b01bb-928">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-928">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-929">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-929"></span></span>|
|<span data-ttu-id="b01bb-930">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-930">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-931">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-931"></span></span>|
|<span data-ttu-id="b01bb-932">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-932">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-933">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-933"></span></span>|
|<span data-ttu-id="b01bb-934">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-934">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-935">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-935"></span></span>|
|<span data-ttu-id="b01bb-936">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-936">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-937">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-937"></span></span>|
|<span data-ttu-id="b01bb-938">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-938">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-939">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-939"></span></span>|
|<span data-ttu-id="b01bb-940">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-940">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-941">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-941"></span></span>|
   
 <span data-ttu-id="b01bb-942">**Microsoft IT TLS CA 2**</span><span class="sxs-lookup"><span data-stu-id="b01bb-942">**Microsoft IT TLS CA 2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-943">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-943">**Subject**</span></span>|
|<span data-ttu-id="b01bb-944">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-944"></span></span>|
|<span data-ttu-id="b01bb-945">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-945">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-946">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-946"></span></span>|
|<span data-ttu-id="b01bb-947">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-947">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-948">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-948"></span></span>|
|<span data-ttu-id="b01bb-949">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-949">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-950">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-950"></span></span>|
|<span data-ttu-id="b01bb-951">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-951">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-952">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-952"></span></span>|
|<span data-ttu-id="b01bb-953">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-953">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-954">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-954"></span></span>|
|<span data-ttu-id="b01bb-955">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-955">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-956">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-956"></span></span>|
|<span data-ttu-id="b01bb-957">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-957">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-958">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-958"></span></span>|
|<span data-ttu-id="b01bb-959">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-959">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-960">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-960"></span></span>|
|<span data-ttu-id="b01bb-961">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-961">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-962">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-962"></span></span>|
|<span data-ttu-id="b01bb-963">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-963">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-964">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-964"></span></span>|
|<span data-ttu-id="b01bb-965">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-965">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-966">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-966"></span></span>|
|<span data-ttu-id="b01bb-967">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-967">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-968">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-968"></span></span>|
|<span data-ttu-id="b01bb-969">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-969">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-970">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-970"></span></span>|
   
 <span data-ttu-id="b01bb-971">**Microsoft IT TLS CA 4**</span><span class="sxs-lookup"><span data-stu-id="b01bb-971">**Microsoft IT TLS CA 4**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-972">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-972">**Subject**</span></span>|
|<span data-ttu-id="b01bb-973">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-973"></span></span>|
|<span data-ttu-id="b01bb-974">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-974">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-975">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-975"></span></span>|
|<span data-ttu-id="b01bb-976">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-976">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-977">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-977"></span></span>|
|<span data-ttu-id="b01bb-978">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-978">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-979">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-979"></span></span>|
|<span data-ttu-id="b01bb-980">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-980">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-981">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-981"></span></span>|
|<span data-ttu-id="b01bb-982">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-982">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-983">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-983"></span></span>|
|<span data-ttu-id="b01bb-984">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-984">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-985">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-985"></span></span>|
|<span data-ttu-id="b01bb-986">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-986">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-987">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-987"></span></span>|
|<span data-ttu-id="b01bb-988">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-988">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-989">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-989"></span></span>|
|<span data-ttu-id="b01bb-990">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-990">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-991">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-991"></span></span>|
|<span data-ttu-id="b01bb-992">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-992">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-993">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-993"></span></span>|
|<span data-ttu-id="b01bb-994">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-994">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-995">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-995"></span></span>|
|<span data-ttu-id="b01bb-996">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-996">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-997">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-997"></span></span>|
|<span data-ttu-id="b01bb-998">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-998">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-999">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-999"></span></span>|
   
 <span data-ttu-id="b01bb-1000">**Microsoft IT TLS CA 5**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1000">**Microsoft IT TLS CA 5**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-1001">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1001">**Subject**</span></span>|
|<span data-ttu-id="b01bb-1002">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1002"></span></span>|
|<span data-ttu-id="b01bb-1003">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1003">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-1004">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1004"></span></span>|
|<span data-ttu-id="b01bb-1005">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1005">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-1006">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1006"></span></span>|
|<span data-ttu-id="b01bb-1007">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1007">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-1008">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1008"></span></span>|
|<span data-ttu-id="b01bb-1009">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1009">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-1010">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1010"></span></span>|
|<span data-ttu-id="b01bb-1011">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1011">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-1012">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1012"></span></span>|
|<span data-ttu-id="b01bb-1013">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1013">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-1014">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1014"></span></span>|
|<span data-ttu-id="b01bb-1015">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1015">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-1016">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1016"></span></span>|
|<span data-ttu-id="b01bb-1017">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1017">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-1018">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1018"></span></span>|
|<span data-ttu-id="b01bb-1019">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1019">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-1020">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1020"></span></span>|
|<span data-ttu-id="b01bb-1021">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1021">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-1022">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1022"></span></span>|
|<span data-ttu-id="b01bb-1023">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1023">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-1024">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1024"></span></span>|
|<span data-ttu-id="b01bb-1025">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1025">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-1026">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1026"></span></span>|
|<span data-ttu-id="b01bb-1027">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1027">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-1028">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1028"></span></span>|
   
 <span data-ttu-id="b01bb-1029">**Symantec 类 3 EV SSL CA G3**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1029">**Symantec Class 3 EV SSL CA - G3**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-1030">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1030">**Subject**</span></span>|
|<span data-ttu-id="b01bb-1031">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1031"></span></span>|
|<span data-ttu-id="b01bb-1032">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1032">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-1033">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1033"></span></span>|
|<span data-ttu-id="b01bb-1034">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1034">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="b01bb-1035">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1035"></span></span>|
|<span data-ttu-id="b01bb-1036">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1036">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-1037">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1037"></span></span>|
|<span data-ttu-id="b01bb-1038">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1038">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-1039">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1039"></span></span>|
|<span data-ttu-id="b01bb-1040">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1040">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-1041">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1041"></span></span>|
|<span data-ttu-id="b01bb-1042">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1042">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-1043">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1043"></span></span>|
|<span data-ttu-id="b01bb-1044">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1044">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-1045">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1045"></span></span>|
|<span data-ttu-id="b01bb-1046">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1046">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-1047">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1047"></span></span>|
|<span data-ttu-id="b01bb-1048">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1048">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-1049">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1049"></span></span>|
|<span data-ttu-id="b01bb-1050">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1050">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-1051">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1051"></span></span>|
|<span data-ttu-id="b01bb-1052">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1052">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-1053">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1053"></span></span>|
|<span data-ttu-id="b01bb-1054">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1054">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-1055">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1055"></span></span>|
|<span data-ttu-id="b01bb-1056">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1056">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-1057">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1057"></span></span>|
|<span data-ttu-id="b01bb-1058">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1058">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-1059">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1059"></span></span>|
   
 <span data-ttu-id="b01bb-1060">**Symantec 类 3 安全服务器 CA-G4**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1060">**Symantec Class 3 Secure Server CA - G4**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-1061">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1061">**Subject**</span></span>|
|<span data-ttu-id="b01bb-1062">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1062"></span></span>|
|<span data-ttu-id="b01bb-1063">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1063">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-1064">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1064"></span></span>|
|<span data-ttu-id="b01bb-1065">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1065">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="b01bb-1066">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1066"></span></span>|
|<span data-ttu-id="b01bb-1067">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1067">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-1068">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1068"></span></span>|
|<span data-ttu-id="b01bb-1069">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1069">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-1070">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1070"></span></span>|
|<span data-ttu-id="b01bb-1071">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1071">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-1072">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1072"></span></span>|
|<span data-ttu-id="b01bb-1073">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1073">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-1074">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1074"></span></span>|
|<span data-ttu-id="b01bb-1075">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1075">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-1076">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1076"></span></span>|
|<span data-ttu-id="b01bb-1077">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1077">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-1078">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1078"></span></span>|
|<span data-ttu-id="b01bb-1079">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1079">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-1080">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1080"></span></span>|
|<span data-ttu-id="b01bb-1081">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1081">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-1082">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1082"></span></span>|
|<span data-ttu-id="b01bb-1083">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1083">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-1084">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1084"></span></span>|
|<span data-ttu-id="b01bb-1085">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1085">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-1086">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1086"></span></span>|
|<span data-ttu-id="b01bb-1087">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1087">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-1088">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1088"></span></span>|
|<span data-ttu-id="b01bb-1089">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1089">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-1090">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1090"></span></span>|
   
 <span data-ttu-id="b01bb-1091">**thawte SHA256 SSL CA**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1091">**thawte SHA256 SSL CA**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-1092">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1092">**Subject**</span></span>|
|<span data-ttu-id="b01bb-1093">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1093"></span></span>|
|<span data-ttu-id="b01bb-1094">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1094">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-1095">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1095"></span></span>|
|<span data-ttu-id="b01bb-1096">**使用者替代名称**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1096">**Subject Alternative Name**</span></span>|
|<span data-ttu-id="b01bb-1097">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1097"></span></span>|
|<span data-ttu-id="b01bb-1098">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1098">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-1099">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1099"></span></span>|
|<span data-ttu-id="b01bb-1100">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1100">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-1101">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1101"></span></span>|
|<span data-ttu-id="b01bb-1102">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1102">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-1103">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1103"></span></span>|
|<span data-ttu-id="b01bb-1104">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1104">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-1105">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1105"></span></span>|
|<span data-ttu-id="b01bb-1106">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1106">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-1107">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1107"></span></span>|
|<span data-ttu-id="b01bb-1108">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1108">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-1109">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1109"></span></span>|
|<span data-ttu-id="b01bb-1110">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1110">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-1111">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1111"></span></span>|
|<span data-ttu-id="b01bb-1112">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1112">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-1113">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1113"></span></span>|
|<span data-ttu-id="b01bb-1114">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1114">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-1115">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1115"></span></span>|
|<span data-ttu-id="b01bb-1116">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1116">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-1117">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1117"></span></span>|
|<span data-ttu-id="b01bb-1118">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1118">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-1119">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1119"></span></span>|
|<span data-ttu-id="b01bb-1120">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1120">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-1121">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1121"></span></span>|
   
 <span data-ttu-id="b01bb-1122">**Verizon Akamai SureServer CA G14 SHA2**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1122">**Verizon Akamai SureServer CA G14-SHA2**</span></span>
  
||
|:-----|
|<span data-ttu-id="b01bb-1123">**主题**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1123">**Subject**</span></span>|
|<span data-ttu-id="b01bb-1124">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1124"></span></span>|
|<span data-ttu-id="b01bb-1125">**颁发者**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1125">**Issuer**</span></span>|
|<span data-ttu-id="b01bb-1126">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1126"></span></span>|
|<span data-ttu-id="b01bb-1127">**序列号**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1127">**Serial Number**</span></span>|
|<span data-ttu-id="b01bb-1128">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1128"></span></span>|
|<span data-ttu-id="b01bb-1129">**公共密钥长度**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1129">**Public Key Length**</span></span>|
|<span data-ttu-id="b01bb-1130">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1130"></span></span>|
|<span data-ttu-id="b01bb-1131">**签名算法**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1131">**Signature Algorithm**</span></span>|
|<span data-ttu-id="b01bb-1132">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1132"></span></span>|
|<span data-ttu-id="b01bb-1133">**不是之前的有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1133">**Validity Not Before**</span></span>|
|<span data-ttu-id="b01bb-1134">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1134"></span></span>|
|<span data-ttu-id="b01bb-1135">**不后有效性**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1135">**Validity Not After**</span></span>|
|<span data-ttu-id="b01bb-1136">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1136"></span></span>|
|<span data-ttu-id="b01bb-1137">**主题密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1137">**Subject Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-1138">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1138"></span></span>|
|<span data-ttu-id="b01bb-1139">**证书颁发机构密钥标识符**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1139">**Authority Key Identifier**</span></span>|
|<span data-ttu-id="b01bb-1140">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1140"></span></span>|
|<span data-ttu-id="b01bb-1141">**指纹 (sha-1)**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1141">**Thumbprint (SHA-1)**</span></span>|
|<span data-ttu-id="b01bb-1142">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1142"></span></span>|
|<span data-ttu-id="b01bb-1143">**指纹 （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1143">**Thumbprint (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-1144">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1144"></span></span>|
|<span data-ttu-id="b01bb-1145">**Pin （160、SHA-256 个）**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1145">**Pin (SHA-256)**</span></span>|
|<span data-ttu-id="b01bb-1146">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1146"></span></span>|
|<span data-ttu-id="b01bb-1147">**AIA Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1147">**AIA URLs**</span></span>|
|<span data-ttu-id="b01bb-1148">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1148"></span></span>|
|<span data-ttu-id="b01bb-1149">**CRL Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1149">**CRL URLs**</span></span>|
|<span data-ttu-id="b01bb-1150">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1150"></span></span>|
|<span data-ttu-id="b01bb-1151">**OCSP Url**</span><span class="sxs-lookup"><span data-stu-id="b01bb-1151">**OCSP URLs**</span></span>|
|<span data-ttu-id="b01bb-1152">:-----</span><span class="sxs-lookup"><span data-stu-id="b01bb-1152"></span></span>|
   
## <a name="additional-certificate-paths"></a><span data-ttu-id="b01bb-1153">额外的证书路径</span><span class="sxs-lookup"><span data-stu-id="b01bb-1153">Additional certificate paths</span></span>
<span data-ttu-id="b01bb-1154"><a name="IntermediateCerts"> </a></span><span class="sxs-lookup"><span data-stu-id="b01bb-1154"></span></span>

<span data-ttu-id="b01bb-1155">以下包括旧的证书不包括上面且随着时间的推移将与上面的列表合并。</span><span class="sxs-lookup"><span data-stu-id="b01bb-1155">The following include legacy certificates that aren't included above and will be merged with the list above over time.</span></span>
  
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


