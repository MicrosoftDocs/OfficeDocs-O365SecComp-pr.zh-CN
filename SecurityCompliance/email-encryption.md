---
title: Office 365 中的电子邮件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
ms.audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
ms.collection:
- M365-security-compliance
description: 比较 office 365 中的加密选项, 包括 office 邮件加密 (OME)、S/MIME、信息权限管理 (IRM), 并了解传输层安全性 (TLS)。
ms.openlocfilehash: 18f3d5098557f65a0738254b57882689c013d677
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32256766"
---
# <a name="email-encryption-in-office-365"></a>Office 365 中的电子邮件加密

本文比较 office 365 中的加密选项, 包括 office 邮件加密 (OME)、S/MIME、信息权限管理 (IRM), 并引入了传输层安全性 (TLS)。
  
Office 365 提供了多个加密选项来帮助你满足对电子邮件安全性的业务需求。 本文介绍了在 Office 365 中对电子邮件进行加密的三种方法。 若要了解有关 Office 365 中的所有安全功能的详细信息, 请访问[office 365 信任中心](http://go.microsoft.com/fwlink/p/?LinkID=282470)。 本文介绍了 office 365 管理员可用于帮助保护 office 365 中的电子邮件的三种类型的加密:
  
- Office 邮件加密 (OME)。
    
- 安全/多用途 Internet 邮件扩展 (S/MIME)。
    
- 信息权限管理 (IRM)。
    
## <a name="what-is-email-encryption-and-how-does-office-365-use-it"></a>什么是电子邮件加密以及 Office 365 如何使用它？

加密是将信息进行编码以便只有经过授权的收件人可以解码和使用信息的过程。 Office 365 通过两种方式使用加密: 在服务中和作为客户控件。 在该服务中, 默认情况下在 Office 365 中使用加密;您无需配置任何内容。 例如，Office 365 使用传输层安全性 (TLS) 加密两个服务器之间的连接或会话。 
  
下面是电子邮件加密通常的工作原理:
  
- 邮件在发件人的计算机上或在邮件传输过程中由中央服务器加密或从纯文本转换为不可读的密文。
    
- 邮件在传输过程中仍保持为密文, 以防止在邮件被截取时阅读。
    
- 一旦收件人收到邮件，邮件将通过两种方式之一转换回可读的纯文本：
    
  - 收件人的计算机使用密钥来解密邮件, 或
    
  - 在验证收件人标识之后, 中央服务器代表收件人解密邮件。
    
有关 office 365 如何保护服务器之间的通信安全的详细信息, 例如, 在 office 365 内部的组织之间或 office 365 与 office 365 之外的受信任商业合作伙伴之间, 请参阅[Exchange Online 如何使用 TLS 保护电子邮件Office 365 中的连接](exchange-online-uses-tls-to-secure-email-connections.md)。
  
观看此视频, 了解[Office 365 中的加密](https://www.youtube.com/watch?v=KmfxCd5ublI)简介。
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Office 365 中的电子邮件加密选项比较

||![介绍 OME 的概念性插图](media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)|![介绍 IRM 的概念性插图](media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)|![介绍 SMIME 的概念性插图](media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)|
|:-----|:-----|:-----|:-----|
|它是什么？|Office 365 邮件加密 (OME) 是一项基于 Azure 权限管理 (Azure RMS) 构建的服务，允许您向组织内外发送经加密的电子邮件，而无需考虑目标电子邮件地址（Gmail、Yahoo!Mail、Outlook.com 等）。  <br/> 作为管理员，您可以设置定义加密条件的传输规则。当用户发送的邮件与规则匹配时，则自动应用加密。  <br/> 若要查看加密邮件，收件人可以使用一次性密码、通过 Microsoft 帐户登录或使用与 Office 365 关联的工作或学校帐户登录。 此外，收件人也可发送加密回复。 他们不需要 Office 365 订阅即可查看加密邮件或发送加密答复。|IRM 是一种加密解决方案，还可向电子邮件应用用法限制。它可以帮助防止未经授权的人员打印、转发或复制敏感信息。  <br/> Office 365 中的 IRM 功能使用 Azure 权限管理 (Azure RMS)。|S/MIME 是一种基于证书的加密解决方案，其允许您对邮件进行加密和数字签名。 邮件加密有助于确保只有预期收件人可以打开并阅读该邮件。 数字签名帮助收件人验证发件人的身份。  <br/> 数字签名和邮件加密都可通过使用包含用于验证数字签名和加密或解密邮件的密钥的唯一数字证书来实现。  <br/> 若要使用 S/MIME，您必须在文件上具有各个收件人的公钥。 收件人必须维护其自己的私钥，必须保持安全。 如果收件人的私钥受到威胁, 收件人需要获取一个新的私钥, 并将公钥重新分发给所有潜在的发件人。|
|它会做什么？|OME  <br/>  对发送到内部或外部收件人的邮件进行加密。  <br/>  允许用户将加密的邮件发送到任何电子邮件地址，包括 Outlook.com、Yahoo!Mail 和 Gmail。  <br/>  允许您以管理员身份自定义电子邮件查看门户, 以反映您的组织的品牌。  <br/>  Microsoft 安全管理和存储密钥, 因此您不必这样做。  <br/>  只要加密邮件（作为 HTML 附件发送）可以在浏览器中打开，就无需特殊的客户端软件。|IRM  <br/>  使用加密和用法限制为电子邮件和附件提供联机和脱机保护。  <br/>  使您能够作为管理员设置传输规则或 Outlook 保护规则，以自动将 IRM 应用到选定邮件。  <br/>  允许用户在 outlook 或 web 上的 outlook 中手动应用模板 (以前称为 outlook web App)。|S/MIME 通过数字签名对发件人进行身份验证，并通过加密实现邮件保密性。|
|它不会做什么？|OME 不允许您对邮件应用使用限制。 例如, 不能使用它阻止收件人转发或打印加密邮件。|某些应用程序可能并不是在所有设备上都支持 IRM 电子邮件。 有关支持 IRM 电子邮件的这些产品和其他产品的详细信息, 请参阅[客户端设备功能](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities)。|S/MIME 不允许扫描加密邮件中的恶意软件、垃圾邮件或策略。|
|建议和示例场景|如果您希望将敏感业务信息发送给组织外部的人员, 无论他们是消费者还是其他企业, 我们建议使用 OME。 例如：  <br/>  银行员工向客户发送信用卡对帐单  <br/>  医生的办公室向患者发送医学记录  <br/>  律师向其他律师发送机密的法律信息|当您想要同时应用用法限制和加密时，我们建议使用 IRM。例如：  <br/>  向团队发送有关新产品的机密详细信息的经理将应用 "不转发" 选项。  <br/>  高级管理人员需要与另一家公司共享投标方案，其中包括来自使用 Office 365 的合作伙伴的附件，并要求保护该电子邮件及其附件。|如果您的组织或收件人的组织需要真正的对等加密, 我们建议使用 S/MIME。  <br/>  S/MIME 最常用于以下场景：  <br/>  政府机构之间的通信  <br/>  企业与政府机构之间的通信|
   
## <a name="what-encryption-options-are-available-for-my-office-365-subscription"></a>可供我的 Office 365 订阅使用的加密选项有哪些？

有关 Office 365 订阅的电子邮件加密选项的信息, 请参阅[Exchange Online 服务说明](https://technet.microsoft.com/en-us/library/exchange-online-service-description.aspx)。 在此处，您可以查看有关以下加密功能的信息：
  
- Azure RMS，包括 IRM 功能和 OME 功能
    
- S/MIME
    
- TLS
    
- 静止数据的加密（通过 BitLocker）
    
## <a name="what-about-encryption-for-data-at-rest"></a>静止数据的加密是怎么样的？

"静止的数据" 是指在传输中不活动的数据。 在 Office 365 中，静止电子邮件数据使用 BitLocker 驱动器加密进行加密。 BitLocker 对 Office 365 数据中心中的硬盘进行加密，以更好地防止未经授权的访问。 若要了解详细信息，请参阅 [BitLocker 概述](https://go.microsoft.com/fwlink/p/?LinkId=394737)。
  
## <a name="more-information-about-email-encryption-options-in-office-365"></a>有关 Office 365 中的电子邮件加密选项的详细信息

有关本文提及的电子邮件加密选项和 TLS 的详细信息，请参阅以下文章：
  
 **OME**
  
[Office 365 邮件加密 (OME)](ome.md)
  
 **IRM**
  
[Exchange Online 中的信息权限管理](https://technet.microsoft.com/en-us/library/jj983436%28v=exchg.150%29.aspx)
  
[什么是 Azure 权限管理？](https://technet.microsoft.com/library/jj585026)
  
 **S/MIME**
  
[将 S/MIME 用于邮件签名和加密](https://technet.microsoft.com/library/dn626158)
  
[了解 S/MIME](https://technet.microsoft.com/library/aa995740%28v=exchg.65%29.aspx)
  
[了解公钥加密](https://technet.microsoft.com/library/aa998077%28v=exchg.65%29.aspx)
  
 **TLS**
  
[使用 Office 365 中的连接器配置自定义邮件流](https://technet.microsoft.com/en-us/library/jj723138%28v=exchg.150%29.aspx)
  

