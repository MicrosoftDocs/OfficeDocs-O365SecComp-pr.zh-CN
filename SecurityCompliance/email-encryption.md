---
title: Office 365 中的电子邮件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/22/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c0d87cbe-6d65-4c03-88ad-5216ea5564e8
description: 比较 Office 365 包括 Office 邮件加密 (OME)、 S/MIME、 信息权限管理 (IRM) 中的加密选项并了解有关传输层安全性 (TLS)。
ms.openlocfilehash: a705637b85e73c6d1e5bcb3595dcd0b7766411e2
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525491"
---
# <a name="email-encryption-in-office-365"></a>Office 365 中的电子邮件加密

本文将包括 Office 邮件加密 (OME)、 S/MIME、 信息权限管理 (IRM) 的 Office 365 中的加密选项进行比较，并介绍了传输层安全性 (TLS)。
  
Office 365 提供了多个加密选项，可帮助您实现您的电子邮件安全的业务需求。本文介绍了三种方式来加密 Office 365 中的电子邮件。如果您想要了解有关 Office 365 中的所有安全功能的详细信息，请访问[Office 365 信任中心](http://go.microsoft.com/fwlink/p/?LinkID=282470)。本文介绍可用于 Office 365 管理员帮助 Office 365 中的安全电子邮件加密的三种类型：
  
- Office 邮件加密 (OME)。
    
- 安全/多用途 Internet 邮件扩展 (S/MIME)。
    
- 信息权限管理 (IRM)。
    
## <a name="what-is-email-encryption-and-how-does-office-365-use-it"></a>什么是电子邮件加密以及 Office 365 如何使用它？

加密是按其信息进行编码，以便仅授权的收件人可以解码和使用信息的过程。Office 365 两种方式使用加密： 在服务中，并作为客户控件。在服务中，使用加密在 Office 365 中默认设置。您无需进行任何配置。例如，Office 365 使用传输层安全性 (TLS) 进行加密的连接或会话，两个服务器之间。 
  
下面是电子邮件加密通常工作原理：
  
- 邮件是加密，或从纯文本转换成不可读的密码，通过发件人的计算机上或中央服务器时邮件在传输过程中。
    
- 时在传输过程中为了防止正在读取截获消息的情况下，消息仍保留在密码文本。
    
- 一旦收件人收到邮件，邮件将通过两种方式之一转换回可读的纯文本：
    
  - 收件人的计算机使用密钥解密邮件，或
    
  - 中央服务器代表收件人，将消息解密后验证收件人的标识。
    
有关 Office 365 如何保护服务器之间的通信的详细信息，如组织中 Office 365 或 Office 365 和 Office 365 以外的受信任的业务合作伙伴之间，请参阅[如何 Exchange Online 使用 TLS 安全电子邮件Office 365 中的连接](exchange-online-uses-tls-to-secure-email-connections.md)。
  
观看此视频介绍[Office 365 中的加密](https://www.youtube.com/watch?v=KmfxCd5ublI)。
  
## <a name="comparing-email-encryption-options-available-in-office-365"></a>Office 365 中的电子邮件加密选项比较

||**        ![介绍 OME 的概念性插图](media/2bf27b5e-bbb3-46d1-95bf-884dc27a746c.png)                 **|**        ![介绍 IRM 的概念性插图](media/9c0cc444-9448-40c6-b244-8fcc593a64e0.png)                 **|**        ![介绍 SMIME 的概念性插图](media/ae4613a8-c17e-47e1-8e13-12e891e43744.png)                 **|
|:-----|:-----|:-----|:-----|
|它是什么？  <br/> |Office 365 邮件加密 (OME) 是一项基于 Azure 权限管理 (Azure RMS) 构建的服务，允许您向组织内外发送经加密的电子邮件，而无需考虑目标电子邮件地址（Gmail、Yahoo!Mail、Outlook.com 等）。  <br/> 作为管理员，您可以设置定义加密条件的传输规则。当用户发送的邮件与规则匹配时，则自动应用加密。  <br/> 若要查看加密的邮件，收件人可以获取一个一次性密码、 使用 Microsoft 帐户，登录或使用单位电话的登录或学校相关联与 Office 365 帐户。收件人还可以发送加密的答复。这些人不需要 Office 365 订阅以查看加密的邮件或发送加密的答复。  <br/> |IRM 是一种加密解决方案，还可向电子邮件应用用法限制。它可以帮助防止未经授权的人员打印、转发或复制敏感信息。  <br/> Office 365 中的 IRM 功能使用 Azure 权限管理 (Azure RMS)。 
  <br/> |S/MIME 是一种基于证书的加密解决方案，允许您加密和邮件进行数字签名。邮件加密有助于确保只有预期的收件人可以打开并读取消息。数字签名可帮助验证发件人的标识的收件人。  <br/> 数字签名和邮件加密都可通过使用包含用于验证数字签名和加密或解密邮件的密钥的唯一数字证书来实现。  <br/> 若要使用 S/MIME，您必须对每个收件人文件具有公钥。收件人必须维护自己私钥必须保持安全。如果收件人的私钥受到威胁，收件人需要获取新的私钥和重新分发给所有潜在的发件人的公钥。  <br/> |
|它会做什么？  <br/> | OME：  <br/>  对发送到内部或外部收件人的邮件进行加密。  <br/>  允许用户将加密的邮件发送到任何电子邮件地址，包括 Outlook.com、Yahoo!Mail 和 Gmail。  <br/>  允许您作为一名管理员，自定义电子邮件查看门户以反映您的组织品牌。  <br/>  Microsoft 安全地管理和存储的密钥中，所以您不必。  <br/>  只要加密邮件（作为 HTML 附件发送）可以在浏览器中打开，就无需特殊的客户端软件。  <br/> | IRM：  <br/>  使用加密和用法限制为电子邮件和附件提供联机和脱机保护。  <br/>  使您能够作为管理员设置传输规则或 Outlook 保护规则，以自动将 IRM 应用到选定邮件。  <br/>  允许用户手动应用 Outlook 或 Outlook Web App 中的模板。  <br/> |S/MIME 通过数字签名对发件人进行身份验证，并通过加密实现邮件保密性。  <br/> |
|它不会做什么？  <br/> |OME 不允许您将使用率限制应用于邮件。例如，您无法使用其停止转发或打印加密的邮件的收件人。  <br/> |某些应用程序在所有设备上可能不支持 IRM 电子邮件。有关这些组件及其他产品支持 IRM 电子邮件的详细信息，请参阅[客户端设备功能](https://technet.microsoft.com/library/dn655136.aspx#BKMK_ClientCapabilities)。<br/> |S/MIME 不允许加密的邮件的恶意软件、 垃圾邮件或策略扫描。  <br/> |
|建议和示例场景  <br/> | 我们建议使用 OME 时要将敏感业务信息发送给组织外部的人员无论他们是通过使用者或其他企业。例如：  <br/>  银行员工向客户发送信用卡对帐单  <br/>  向患者发送医疗记录医生的 office  <br/>  律师向其他律师发送机密的法律信息  <br/> | 当您想要同时应用用法限制和加密时，我们建议使用 IRM。例如：  <br/>  发送到其团队发送有关新产品的机密的详细信息管理器将应用"不要转发"选项。  <br/>  高级管理人员需要与另一家公司共享投标方案，其中包括来自使用 Office 365 的合作伙伴的附件，并要求保护该电子邮件及其附件。  <br/> | 我们建议贵组织或收件人的组织要求，则返回 true 的对等加密时使用 S/MIME。  <br/>  S/MIME 最常用于以下场景：  <br/>  政府机构之间的通信  <br/>  企业与政府机构之间的通信  <br/> |
   
## <a name="what-encryption-options-are-available-for-my-office-365-subscription"></a>可供我的 Office 365 订阅使用的加密选项有哪些？

有关 Office 365 订阅的电子邮件加密选项的信息，请参阅[Exchange Online 服务说明](https://technet.microsoft.com/en-us/library/exchange-online-service-description.aspx)。此处，您可以找到有关以下加密功能的信息：
  
- Azure RMS，包括 IRM 功能和 OME 功能
    
- S/MIME
    
- TLS
    
- 静止数据的加密（通过 BitLocker）
    
## <a name="what-about-encryption-for-data-at-rest"></a>静止数据的加密是怎么样的？

"静态数据"是指主动不在传输过程中的数据。Office 365 中使用 BitLocker 驱动器加密加密电子邮件静态数据。BitLocker 加密以提供更好地防止未经授权的访问的 Office 365 数据中心中硬盘驱动器。若要了解详细信息，请参阅[BitLocker 概述](https://go.microsoft.com/fwlink/p/?LinkId=394737)。
  
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
  
[在 Office 365 中使用连接器配置自定义邮件流](https://technet.microsoft.com/en-us/library/jj723138%28v=exchg.150%29.aspx)
  

