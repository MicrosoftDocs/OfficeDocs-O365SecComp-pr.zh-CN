---
title: Exchange Online 如何进行电子邮件保密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 5/24/2018
ms.audience: ITPro
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
description: 除了 Office 365 信任中心它适用于 Office 365 提供安全、 隐私和合规性信息，您可能想了解 Office 365 如何帮助保护您在其数据中心中提供的机密。我们使用称为分布式密钥管理器 (DKM) 的技术。
ms.openlocfilehash: a8fe1a2c9393958a391ec69a9a476a06de8c7576
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525928"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Exchange Online 如何进行电子邮件保密

本文介绍了 Microsoft 如何在数据中心内进行电子邮件保密。
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>我们如何对您提供的机密信息进行保密？

除了 Office 365 信任中心提供[安全、 隐私和 Office 365 的合规性信息](https://go.microsoft.com/fwlink/?linkid=874644)，您可能想了解 Office 365 如何帮助保护您在其数据中心中提供的机密。我们使用称为分布式密钥管理器 (DKM) 的技术。
  
分布式密钥管理器 (DKM) 是一种客户端功能，可使用一组密钥加密和解密信息。只有 Active Directory 域服务内特定安全组中的成员才可以使用这些密钥解密由 DKM 加密的数据。在 Exchange Online 中，只有其下运行 Exchange 进程的特定服务帐户才属于此类安全组。根据数据中心内的标准操作过程，任何人都不会得到此安全组中的凭据，因此没有人能够使用密钥解密这些加密数据。
  
若要进行调试、疑难解答或审核，数据中心管理员必须提出提升访问权限请求，以获取此安全组中的临时凭据。此过程需要经过多级法律审批。如果被授予访问权限，则可以记录和审核所有活动。此外，授予的访问权限只在一段固定期限内有效，到期后便会自动失效。
  
为了提供额外保护，DKM 技术具有自动密钥滚动更新和存档功能。这样还可以确保您能够继续访问旧内容，而无需无限期地依赖同一密钥。

  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Exchange Online 在何处使用 DKM？

Microsoft 使用 DKM 在 Exchange Online 数据中心内加密您的机密信息。例如：
  
- 已连接帐户的电子邮件帐户凭据。已连接帐户是第三方帐户，如 Hotmail、Gmail 和 Yahoo! 邮件帐户。
    
- 权限管理服务 (RMS) 根键。这些是客户键的任一导入从 Azure RMS 或从客户的本地 Active Directory 域服务 RMS 部署用于加密和解密电子邮件与 RMS 或 Office 365 邮件加密 (OME)。
    
## <a name="related-topics"></a>相关主题

[Office 365 中的加密](encryption.md)
  
[有关 Office 365 加密的技术参考详情](technical-reference-details-about-encryption.md)
  
[服务 Office 365 安全性保证&amp;合规性中心](https://go.microsoft.com/fwlink/?linkid=874645)
  

