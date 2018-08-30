---
title: Office 365 邮件加密的旧信息
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/4/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
description: 如果您没有尚未将您的 Office 365 组织移到 OME 的新功能，但您已经部署了 OME，本文中的信息适用于您的组织。Microsoft 建议您进行规划，以将移动到新的 OME 功能只要很合理为您的组织。有关说明，请参阅 Set up 内置到 Azure 信息保护顶部的新 Office 365 邮件加密功能。如果您想要找出有关的新功能，首先工作的方式的详细信息，请参阅 Office 365 邮件加密。本文的其余部分是指之前的版本的新功能，OME OME 行为。
ms.openlocfilehash: d5b21cbe0004ca7bda38085bd5d8ef5f2a22b04e
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525490"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Office 365 邮件加密的旧信息

如果您没有尚未将您的 Office 365 组织移到 OME 的新功能，但您已经部署了 OME，本文中的信息适用于您的组织。Microsoft 建议您进行规划，以将移动到新的 OME 功能只要很合理为您的组织。有关说明，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](set-up-new-message-encryption-capabilities.md)。如果您想要找出有关的新功能，首先工作的方式的详细信息，请参阅[Office 365 邮件加密](ome.md)。本文的其余部分是指之前的版本的新功能，OME OME 行为。
  
与 Office 365 邮件加密，您的组织可以发送和接收组织内外的人员之间的加密的电子邮件。Office 365 邮件加密处理 Outlook.com、 Yahoo、 Gmail 和其他电子邮件服务。仅预期收件人的电子邮件加密有助于确保可以查看邮件的内容。
  
下面是一些示例：
  
- 银行员工向客户发送信用卡对帐单
    
- 保险公司代表向客户提供政策详细信息
    
- 抵押经纪人请求贷款应用程序客户的财务信息
    
- 保健提供程序向患者发送保健信息
    
- 律师向客户或其他律师发送机密信息
    
## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>Office 365 邮件加密没有的新功能的工作方式

Office 365 邮件加密是基于 Microsoft Azure 权限管理 (Azure RMS) 的联机服务。使用 Azure RMS，管理员可以定义邮件流规则来确定加密的条件。例如，规则可以要求的所有邮件发送到特定收件人的加密。
  
观看此简短视频以了解 Office 365 邮件加密没有的新功能的工作原理。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
当某人发送一封电子邮件在 Exchange Online 的与加密规则匹配时，与一个 HTML 附件发送邮件。收件人打开 HTML 附件，并按照说明 Office 365 邮件加密门户上查看加密的邮件。收件人可以选择通过登录时的 Microsoft 帐户或工作或学校与 Office 365 中，或通过使用一次性密码查看邮件。这两个选项帮助确保仅预期接收人可以查看加密的邮件。此进程是非常新 OME 功能的不同。
  
下方的图表总结了电子邮件是如何通过加密和解密过程的。
  
![显示加密电子邮件路径的图表](media/O365-Office365MessageEncryption-Concept.png)
  
有关详细信息，请参阅[旧 Office 365 邮件加密之前的版本的新功能，OME 的服务信息](legacy-information-for-message-encryption.md#LegacyServiceInfo)。
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>定义不使用新的 OME 功能的 Office 365 邮件加密的邮件流规则

若要启用没有的新功能的 Office 365 邮件加密，Exchange Online 和 Exchange Online Protection 管理员定义 Exchange 邮件流规则。这些规则确定在什么条件电子邮件消息应进行加密，以及删除邮件加密的条件。当加密操作设置规则时，匹配的规则条件的任何邮件进行加密，他们正在发送之前。
  
邮件流规则是灵活，让您组合条件，所以您可以满足在单个规则中的特定的安全要求。例如，您可以创建所有包含指定的关键词和发往外部收件人的邮件进行加密的规则。Office 365 邮件加密还将加密的加密的电子邮件收件人的答复还可以创建这些答复解密为方便电子邮件用户的规则。这样，您的组织中的用户不需要登录到加密门户以查看答复。
  
有关如何创建 Exchange 邮件流规则的详细信息，请参阅[Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>发送、查看和回复加密电子邮件

与 Office 365 邮件加密，电子邮件进行加密自动根据管理员定义规则。携带加密的邮件的电子邮件到达收件人的收件箱中替换为附加的 HTML 文件。
  
收件人按照打开附件和使用 Microsoft 帐户或工作或学校与 Office 365 进行身份验证的消息中的说明。如果收件人没有任一帐户，他们正在定向创建 Microsoft 帐户，使其登录以查看加密的邮件。或者，可以选择收件人获取一次性密码以查看邮件。登录或使用一次性传递代码后, 收件人可以查看解密的邮件并发送加密的答复。
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>自定义与 Office 365 邮件加密的加密的邮件

作为 Exchange Online 和 Exchange Online Protection 管理员，您可以自定义加密的邮件。例如，您可以添加您的公司品牌和徽标，指定介绍，并在加密邮件和门户其中收件人查看加密的邮件添加免责声明文本。使用 Windows PowerShell cmdlet，您可以自定义加密的电子邮件的收件人的查看体验的以下方面：
  
- 包含加密邮件的电子邮件介绍性文本
    
- 包含加密邮件的电子邮件免责声明文本
    
- 显示在邮件查看门户中的门户文本
    
- 显示在电子邮件和查看门户中的徽标
    
您也可以随时还原到默认的外观。
  
以下示例显示电子邮件附件中的 ContosoPharma 的自定义徽标：
  
![查看加密消息页面的示例](media/TA-OME-3attachment2.jpg)
  
 **自定义加密电子邮件和使用组织品牌的加密门户**
  
1. 连接到 Exchange Online 使用远程 PowerShell[连接到 Exchange Online Using Remote PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated)中所述。
    
2. 使用 Set-omeconfiguration cmdlet 此处所述： [Set-omeconfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)或使用下表指导。 
    
   **加密自定义选项**

|**自定义加密体验的这一功能**|**使用这些 Windows PowerShell 命令**|
|:-----|:-----|
|加密电子邮件随附的默认文本  <br/> 默认文本显示在说明的上方，以查看加密邮件  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **示例：**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
|包含加密邮件的电子邮件中的免责声明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **示例：**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
|显示在加密邮件查看门户顶部的文本  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **示例：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
|徽标  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **示例：**`Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支持的文件格式：.png、.jpg、.bmp 或 .tiff  <br/> 徽标文件的最佳大小：小于 40 KB  <br/> 徽标图像的最佳大小：170x70 像素  <br/> |
   
 **若要移除加密电子邮件和加密门户的品牌自定义项**
  
1. 连接到 Exchange Online 使用远程 PowerShell[连接到 Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)中所述。
    
2. 使用 Set-omeconfiguration cmdlet 此处所述： [Set-omeconfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)。若要删除您的组织的品牌自定义项从 DisclaimerText，EmailText，和 PortalText 值，将值设置为空字符串， `""`。有关所有图像值，如徽标，将值设置为`"$null"`。
    
   **加密自定义选项**

|**将加密体验的此功能还原到默认的文本和图片**|**使用这些 Windows PowerShell 命令**|
|:-----|:-----|
|加密电子邮件随附的默认文本  <br/> 默认文本显示在说明的上方，以查看加密邮件  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **示例：**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|包含加密邮件的电子邮件中的免责声明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **示例：**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|显示在加密邮件查看门户顶部的文本  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **还原为默认的示例：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|徽标  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **还原为默认的示例：**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
   
## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>服务信息的旧 Office 365 邮件加密之前版本的新 OME 功能
<a name="LegacyServiceInfo"> </a>

下表之前的新功能，OME 的版本的 Office 365 邮件加密服务提供的技术详细信息。
  
|**服务详细信息**|**说明**|
|:-----|:-----|
|客户端设备要求  <br/> |只要 HTML 附件可以在支持窗体发布的现代浏览器中打开，就可以在任何客户端设备上查看加密邮件。  <br/> |
|加密算法和美国联邦信息处理标准 (FIPS) 合规性  <br/> |Office 365 邮件加密使用作为 Windows Azure 信息权限管理 (IRM) 的相同的加密密钥，并为 sha-1 系统支持加密模式 2 （2k 密钥 RSA） 和 256 位密钥。有关基础的 IRM 加密模式的详细信息，请参阅[AD RMS 加密模式](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx)。<br/> |
|支持的邮件类型  <br/> |具有邮件类**IPM 的 ID 的项目才支持 office 365 邮件加密。注意**。有关详细信息，请参阅[项目类型和邮件类](https://msdn.microsoft.com/library/office/ff861573.aspx)。<br/> |
|邮件大小限制  <br/> |Office 365 邮件加密可以加密邮件的最多 25 兆字节。有关邮件大小限制的详细信息，请参阅[Exchange Online 限制](http://technet.microsoft.com/library/exchange-online-limits.aspx)。<br/> |
|Exchange Online 电子邮件保留策略  <br/> |Exchange Online 不存储已加密的邮件。  <br/> |
|Office 365 邮件加密的语言支持  <br/> | Office 365 邮件加密支持 Office 365 语言，如下所示：  <br/>  传入电子邮件和附加的 HTML 文件根据发件人的语言设置本地化。  <br/>  查看门户根据收件人的浏览器设置进行本地化。  <br/>  加密邮件的正文（内容）不进行本地化。  <br/> |
|OME 门户和 OME 查看器应用的隐私信息  <br/> |[Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md)提供了有关 Microsoft 如何处理您的隐私信息的详细信息。  <br/> |
   
## <a name="frequently-asked-questions-about-legacy-ome"></a>有关旧 OME 的常见问题
<a name="LegacyServiceInfo"> </a>

获得有关 Office 365 邮件加密的问题？以下是一些解答。如果找不到您的需要则检查 Office 365 社区论坛在[Office 365 社区](http://community.office365.com/en-us/forums/default.aspx)。
  
 **问： 我的用户向我们组织外部的收件人发送加密的电子邮件。还有什么外部收件人必须执行的操作以读取和回复与 Office 365 邮件加密的加密电子邮件？**
  
组织外收到 Office 365 加密邮件的收件人可以通过以下任一种方式查看邮件：
  
- 通过登录时 Microsoft 帐户或 Office 365 与关联的工作或学校帐户。
    
- 使用一次性传递代码。
    
 **问：Office 365 加密邮件存储在云中，还是存储在 Microsoft 服务器上？**
  
否，已加密的邮件保留在收件人的电子邮件系统，并且当收件人打开邮件时，暂时发布以便在 Office 365 服务器上查看。消息存储不存在。
  
 **问：能否使用我的品牌自定义加密电子邮件？**
  
能，您可以使用 Windows PowerShell cmdlet 自定义显示在加密电子邮件顶部的默认文本、免责声明文本以及在电子邮件和加密门户中使用的徽标。有关详细信息，请参阅[Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md)。
  
 **问：该服务是否要求我的组织中的每个用户都有许可证？**
  
组织中发送加密电子邮件的每个用户都必须有许可证。
  
 **问：外部收件人是否需要订阅？**
  
否，外部收件人不需要订阅即可阅读或回复加密邮件。 
  
 **问： 如何为 Office 365 邮件加密不同从权限管理服务 (RMS)？**
  
RMS 提供的组织的内部电子邮件的信息权限保护功能通过提供内置模板，例如： 不要转发和公司机密。Office 365 邮件加密支持电子邮件加密的外部收件人以及内部收件人发送邮件。
  
 **问： 如何为 Office 365 邮件加密 S/MIME 不同？**
  
S/MIME 实质上是一种客户端加密技术，需要复杂的证书管理和发布基础结构。Office 365 邮件加密使用传输规则，且不依赖于证书发布。
  
 **问：能否通过移动设备阅读加密邮件？**
  
是，您可以通过从[Google 播放存储](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409)和[Apple 应用程序存储](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409)下载 OME 查看器应用程序在 Android 和 iOS 查看邮件。OME 查看器应用程序中打开 HTML 附件，然后按照说明进行操作以打开您的加密的邮件。对于其他移动设备，可以打开 HTML 附件，只要您的邮件客户端支持窗体发布。
  
 **问：是否对回复和转发的邮件进行加密？**
  
是，在整个线程期限内，响应都会继续进行加密。
  
 **问：Office 365 邮件加密是否提供本地化？**
  
传入电子邮件和 HTML 内容会进行本地化，具体取决于发件人电子邮件设置。查看门户根据收件人的浏览器设置进行本地化。不过，加密邮件的实际正文（内容）不会进行本地化。
  
 **问：Office 365 邮件加密使用哪种加密方法？**
  
Office 365 邮件加密使用权限管理服务 (RMS) 作为其加密基础结构。所使用的加密方法取决于从何处获取用来加密和解密邮件的 RMS 密钥。
  
- 如果您使用 Microsoft Azure RMS 获取密钥，则使用加密模式 2。加密模式 2 是更新和增强 AD RMS 加密实现。它支持 RSA 2048 签名和加密，并支持的签名 160、SHA-256 个。
    
- 如果您使用 Active Directory (AD) RMS 获取这些密钥，则可以使用加密模式 1，也可以使用加密模式 2。使用的方法取决于您的本地 AD RMS 部署。加密模式 1 是原始的 AD RMS 加密实现。它支持 RSA 1024 签名和加密，并支持 sha-1 签名。该模式继续支持 RMS 的所有当前版本。
    
有关详细信息，请参阅[AD RMS 加密模式](http://go.microsoft.com/fwlink/p/?LinkId=398616)。
  
 **问：为什么一些加密邮件显示其来自 Office365@messaging.microsoft.com？**
  
当加密回复从加密门户或通过 OME 查看器应用发送时，发送电子邮件地址将设为 Office365@messaging.microsoft.com，因为该加密邮件是通过 Microsoft 终结点发送的。这有助于防止加密邮件被标记为垃圾邮件。电子邮件上显示的名称和加密门户内的地址不会因为这个标签而更改。此外，该标签仅适用于通过门户而不是通过任何其他电子邮件客户端发送的邮件。
  
 **问： 我是 Exchange Hosted Encryption (EHE) 订阅者。其中了解有关升级到 Office 365 邮件加密的详细信息？**
  
所有 EHE 客户已都升级到 Office 365 邮件加密。有关详细信息，请访问[Exchange 托管加密升级中心](http://go.microsoft.com/fwlink/p/?LinkID=511077)。
  
 **问： 我需要吗的打开任何 Url、 IP 地址或在我的组织的防火墙端口以支持 Office 365 邮件加密？**
  
是。您必须将 Exchange Online 的 URL 添加到组织的允许列表，对通过 Office 365 邮件加密进行加密的邮件启用身份验证。有关 Exchange Online URL 的列表，请参阅 [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx)。
  
 **问：我可以向多少个收件人发送 Office 365 加密邮件？**
  
加密邮件的收件人限制基于消息的**收件人**字段中的字符数。当合并 （后通讯组列表扩展） 时，**到**字段中的收件人地址不应超过 11,980 字符。电子邮件地址的字符长度可以改变，因为没有标准收件人限制为单个加密消息。 
  
 **问：是否可以取消发送给特定收件人的邮件？**
  
不。已发送，则不能撤消到某个人一条消息。
  
 **问：是否可以查看已接收和阅读的加密邮件报告吗？**
  
没有显示，是否已查看加密的邮件，但有可用，您可以利用若要确定匹配特定传输规则，例如的邮件数的 Office 365 报告的报告。
  
 **问：Microsoft 会如何处理我通过 OME 门户和 OME 查看器应用提供的信息？**
  
[Office 365 邮件加密门户隐私声明](protected-message-viewer-portal-privacy-statement.md)提供有关 Microsoft 支持和不与您的私人信息的详细的信息。 
  

