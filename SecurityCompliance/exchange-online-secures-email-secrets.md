---
title: Exchange Online 如何进行电子邮件保密
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 5/24/2018
ms.audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 989ba10c-f73f-4efb-ad1b-af3322e5f376
ms.collection:
- M365-security-compliance
description: 除了提供 office 365 的安全性、隐私和合规性信息的 office 365 信任中心之外, 您可能还需要了解 office 365 如何帮助保护您在其数据中心中提供的密码。 我们使用一种称为 "分布式密钥管理器" (DKM) 的技术。
ms.openlocfilehash: ba4c661899273f5e07c2468631298f5500d0e32f
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32255480"
---
# <a name="how-exchange-online-secures-your-email-secrets"></a>Exchange Online 如何进行电子邮件保密

本文介绍了 Microsoft 如何在其数据中心中保护你的电子邮件机密。
  
## <a name="how-do-we-secure-secret-information-provided-by-you"></a>我们如何保护你提供的机密信息的安全？

除了提供[office 365 的安全性、隐私和合规性信息](https://go.microsoft.com/fwlink/?linkid=874644)的 office 365 信任中心之外, 您可能还需要了解 office 365 如何帮助保护您在其数据中心中提供的密码。 我们使用一种称为 "分布式密钥管理器" (DKM) 的技术。
  
分布式密钥管理器 (DKM) 是一种使用一组用于加密和解密信息的密钥的客户端功能。 只有 Active Directory 域服务中特定安全组的成员才能访问这些密钥, 以便对由 DKM 加密的数据进行解密。 在 exchange Online 中, 仅在运行 exchange 进程的特定服务帐户是该安全组的一部分。 作为数据中心中的标准操作过程的一部分, 将不会向任何人提供属于此安全组的凭据, 因此没有人能够访问可以解密这些机密的密钥。
  
对于调试、故障排除或审核目的, 数据中心管理员必须请求提升的访问权限, 才能获取属于安全组一部分的临时凭据。 此过程需要多个合法的法律审批级别。 如果授予访问权限, 则会记录并审核所有活动。 此外, 仅授予对设置的时间间隔的访问权限, 在此间隔之后它将自动过期。
  
对于额外保护, DKM 技术包括自动化密钥滚动更新和存档。 这还可确保您可以继续访问较旧的内容, 而无需无限期地依赖相同的密钥。
  
## <a name="where-does-exchange-online-make-use-of-dkm"></a>Exchange Online 在哪里使用 DKM？

Microsoft 使用 DKM 在 Exchange Online 数据中心中加密你的机密。 例如：
  
- 已连接帐户的电子邮件帐户凭据。 已连接帐户是第三方帐户, 如 Hotmail、Gmail 和 yahoo! 邮件帐户。
    
- 权限管理服务 (RMS) 根键。 这些客户密钥可从 Azure RMS 导入, 也可以从客户的本地 Active Directory 域服务 RMS 部署中导入, 这些部署用于使用 RMS 或 Office 365 邮件加密 (OME) 对电子邮件进行加密和解密。
    
## <a name="related-topics"></a>相关主题

[Office 365 中的加密](encryption.md)
  
[有关 Office 365 加密的技术参考详情](technical-reference-details-about-encryption.md)
  
[Office 365 安全&amp;合规中心中的服务保证](https://go.microsoft.com/fwlink/?linkid=874645)
  

