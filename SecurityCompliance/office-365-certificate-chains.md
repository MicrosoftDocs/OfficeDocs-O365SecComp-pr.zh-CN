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
# <a name="office-365-certificate-chains"></a>Office 365 证书链

Office 365 利用大量的不同的证书提供商。下面介绍已知客户访问 Office 365 时可能遇到的 Office 365 根证书的完整的列表。您可能需要您自己的基础结构中安装证书信息，请参阅[Office 365 的第三方 SSL 证书计划](https://support.office.com/article/b48cdf63-07e0-4cda-8c12-4871590f59ce)。下面的证书信息适用于 Office 365 的所有全球和国家/地区云实例。
  

|**证书类型**|**P7b 下载**|**CRL 终结点**|**OCSP 终结点**|**AIA 终结点**|
|:-----|:-----|:-----|:-----|:-----|
|[公共受信任的根证书](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#rootcerts) <br/> |[Office 365 根证书绑定 (P7B)](http://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) <br/> |crl.globalsign.net  <br/> www.d-trust.net  <br/> |不适用  <br/> |不适用  <br/> |
|[公共受信任的中间证书](https://support.office.com/article/0c03e6b3-e73f-4316-9e2b-bf4091ae96bb#IntermediateCerts) <br/> |[Office 365 中间证书绑定 (P7B)](http://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b)  <br/> |cdp1.public trust.com  <br/> crl.cnnic.cn  <br/> crl.entrust.net  <br/> crl.globalsign.com  <br/> crl.globalsign.net  <br/> crl.identrust.com  <br/> crl.thawte.com  <br/> crl3.digicert.com  <br/> crl4.digicert.com  <br/> s1.symcb.com  <br/> www.d-trust.net  <br/> |isrg.trustid.ocsp.identrust.com  <br/> ocsp.digicert.com  <br/> ocsp.entrust.net  <br/> ocsp.globalsign.com  <br/> ocsp.omniroot.com  <br/> ocsp.startssl.com  <br/> ocsp.thawte.com  <br/> ocsp2.globalsign.com  <br/> ocspcnnicroot.cnnic.cn  <br/> 根-c3-ca2-2009.ocsp.d-trust.net  <br/> root-c3-ca2-ev-2009.ocsp.d-trust.net  <br/> s2.symcb.com  <br/> |aia.startssl.com  <br/> apps.identrust.com  <br/> cacert.omniroot.com  <br/> www.cnnic.cn  <br/> |
   
展开根和下面有关证书提供商的其他详细信息，请参阅的中间部分。
  
## <a name="office-365-root-certificate-details"></a>Office 365 根证书的详细信息
<a name="RootCerts"> </a>

 **Baltimore CyberTrust 根**
  
|:-----|
|**主题**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
   
 **CNNIC 根**
  
||
|:-----|
|**主题**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
   
 **DigiCert 全局根 CA**
  
||
|:-----|
|**主题**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
   
 **DigiCert 高保证 EV 根 CA**
  
||
|:-----|
|**主题**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
   
 **D 信任根类 3 CA 2 2009**
  
||
|:-----|
|**主题**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
   
 **D 信任根类 3 CA 2 EV 2009**
  
||
|:-----|
|**主题**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
   
 **DST 根 CA X3**
  
||
|:-----|
|**主题**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
   
 **委托根证书颁发机构-G2**
  
||
|:-----|
|**主题**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
   
 **Entrust.net Certification Authority (2048)**
  
||
|:-----|
|**主题**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
   
 **GlobalSign**
  
||
|:-----|
|**主题**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
   
 **GlobalSign Root CA**
  
||
|:-----|
|**主题**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
   
 **thawte 主根 CA-G3**
  
||
|:-----|
|**主题**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
   
 **VeriSign 类 3 主要公用证书颁发机构-G5**
  
||
|:-----|
|**主题**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
   
## <a name="office-365-intermediate-certificate-details"></a>Office 365 中间证书详细信息
<a name="IntermediateCerts"> </a>

 **CNNIC SHA256 SSL**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**AIA Url**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **D 信任 SSL 类 3 CA 1 2009**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**使用者替代名称**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **D 信任 SSL 类 3 CA 1 EV 2009**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**使用者替代名称**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **DigiCert 云服务 CA-1**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **DigiCert SHA2 高保证服务器 CA**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **DigiCert SHA2 安全服务器 CA**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **委托 L1C 的证书颁发机构-**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **委托 L1K 的证书颁发机构-**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **GlobalSign**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **GlobalSign 扩展验证 CA-SHA256-G2**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **GlobalSign 扩展验证 CA-SHA256-G3**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **GlobalSign 组织验证 CA-SHA256-G2**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **GlobalSign 组织验证 CA-SHA256-G2**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **让我们加密证书颁发机构 X3**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**AIA Url**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Microsoft IT SSL SHA2**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
   
 **Microsoft IT SSL SHA2**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Microsoft IT TLS CA 1**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Microsoft IT TLS CA 2**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Microsoft IT TLS CA 4**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Microsoft IT TLS CA 5**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Symantec 类 3 EV SSL CA G3**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**使用者替代名称**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Symantec 类 3 安全服务器 CA-G4**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**使用者替代名称**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **thawte SHA256 SSL CA**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**使用者替代名称**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
 **Verizon Akamai SureServer CA G14 SHA2**
  
||
|:-----|
|**主题**|
|:-----|
|**颁发者**|
|:-----|
|**序列号**|
|:-----|
|**公共密钥长度**|
|:-----|
|**签名算法**|
|:-----|
|**不是之前的有效性**|
|:-----|
|**不后有效性**|
|:-----|
|**主题密钥标识符**|
|:-----|
|**证书颁发机构密钥标识符**|
|:-----|
|**指纹 (sha-1)**|
|:-----|
|**指纹 （160、SHA-256 个）**|
|:-----|
|**Pin （160、SHA-256 个）**|
|:-----|
|**AIA Url**|
|:-----|
|**CRL Url**|
|:-----|
|**OCSP Url**|
|:-----|
   
## <a name="additional-certificate-paths"></a>额外的证书路径
<a name="IntermediateCerts"> </a>

以下包括旧的证书不包括上面且随着时间的推移将与上面的列表合并。
  
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

