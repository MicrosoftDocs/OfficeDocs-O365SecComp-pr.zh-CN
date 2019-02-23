---
title: Office 365 邮件加密的旧信息
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 1/4/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
description: 如果您尚未将 Office 365 组织移动到新的 OME 功能, 但您已经部署了 OME, 则本文中的信息适用于您的组织。Microsoft 建议您制定一个计划, 尽快移动到新的 OME 功能, 因为它对您的组织合理。有关说明, 请参阅设置基于 Azure 信息保护基础构建的新 Office 365 邮件加密功能。如果您想要详细了解新功能的工作方式, 请参阅 Office 365 邮件加密。本文的其余部分是在发布新的 OME 功能之前的 OME 行为。
ms.openlocfilehash: 1f809ca996f072269f40bcb6c7ce6f7a420cccb1
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30219252"
---
# <a name="legacy-information-for-office-365-message-encryption"></a>Office 365 邮件加密的旧信息

如果您尚未将 Office 365 组织移动到新的 OME 功能, 但您已经部署了 OME, 则本文中的信息适用于您的组织。Microsoft 建议您制定一个计划, 尽快移动到新的 OME 功能, 因为它对您的组织合理。有关说明, 请参阅[设置基于 Azure 信息保护基础构建的新 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。如果您想要详细了解新功能的工作方式, 请参阅[Office 365 邮件加密](ome.md)。本文的其余部分是在发布新的 OME 功能之前的 OME 行为。
  
使用 Office 365 邮件加密, 组织可以在组织内部和外部的人员之间发送和接收加密的电子邮件。Office 365 邮件加密适用于 Outlook.com、Yahoo、Gmail 和其他电子邮件服务。电子邮件加密有助于确保只有预期的收件人可以查看邮件内容。
  
此处为一些示例：
  
- 银行员工向客户发送信用卡对帐单
    
- 保险业公司代表向客户提供策略详细信息
    
- 抵押经纪人请求来自客户的贷款申请的财务信息
    
- 医疗保健提供商向患者发送卫生保健信息
    
- 律师向客户或其他律师发送机密信息
    
## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a>如何在没有新功能的情况下运行 Office 365 邮件加密

Office 365 邮件加密是基于 Microsoft Azure 权限管理 (Azure RMS) 构建的在线服务。使用 Azure RMS, 管理员可以定义邮件流规则, 以确定加密的条件。例如, 规则可以要求对发送到特定收件人的所有邮件进行加密。
  
观看此简短视频, 了解 Office 365 邮件加密如何工作而无需新功能。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
当某人在 Exchange Online 中发送与加密规则匹配的电子邮件时, 将使用 HTML 附件发送邮件。收件人打开 HTML 附件并按照说明在 Office 365 邮件加密门户中查看加密邮件。收件人可以选择使用 Microsoft 帐户或与 Office 365 关联的工作或学校登录, 或使用一次性的 pass 代码来查看邮件。这两个选项都有助于确保只有预期的收件人才能查看加密的邮件。此过程对于新的 OME 功能非常不同。
  
下方的图表总结了电子邮件是如何通过加密和解密过程的。
  
![显示加密电子邮件路径的图表](media/O365-Office365MessageEncryption-Concept.png)
  
有关详细信息, 请参阅[早期版本的 Office 365 邮件加密的服务信息, 然后再发布新的 OME 功能](legacy-information-for-message-encryption.md#LegacyServiceInfo)。
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a>为不使用新 OME 功能的 Office 365 邮件加密定义邮件流规则

若要在不使用新功能的情况下启用 Office 365 邮件加密, exchange online 和 exchange online Protection 管理员将定义 Exchange 邮件流规则。这些规则确定应在哪些条件下加密电子邮件, 以及删除邮件加密的条件。为规则设置加密操作后, 与规则条件匹配的任何邮件在发送之前都会被加密。
  
邮件流规则是灵活的, 允许您将条件组合在一起, 以便您可以在单个规则中满足特定的安全要求。例如, 您可以创建一个规则来加密包含指定关键字并发送给外部收件人的所有邮件。Office 365 邮件加密还会对来自加密电子邮件的收件人的回复进行加密, 并且可以创建一个规则来解密这些回复, 以方便您使用电子邮件用户。这样, 组织中的用户无需登录到加密门户即可查看答复。
  
有关如何创建 Exchange 邮件流规则的详细信息, 请参阅[定义 Office 365 邮件加密的规则](define-mail-flow-rules-to-encrypt-email.md)。
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>发送、查看和回复加密电子邮件

使用 Office 365 邮件加密时, 电子邮件将根据管理员定义的规则自动加密。携带加密邮件的电子邮件到达收件人的收件箱, 并附带一个 HTML 文件。
  
收件人按照邮件中的说明打开附件, 并使用 Microsoft 帐户或与 Office 365 相关联的工作或学校进行身份验证。如果收件人没有任何帐户, 则会将其定向到创建一个 Microsoft 帐户, 让他们登录以查看加密邮件。或者, 收件人可以选择获取一次性传递代码来查看邮件。登录或使用一次性传递代码后, 收件人可以查看解密的邮件并发送加密答复。
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a>使用 Office 365 邮件加密自定义加密邮件

作为 exchange online 和 exchange online Protection 管理员, 您可以自定义加密邮件。例如, 您可以添加公司的品牌和徽标, 指定简介, 并在加密邮件中以及在收件人查看加密邮件的门户中添加免责声明文本。使用 Windows PowerShell cmdlet, 您可以自定义加密电子邮件的收件人的查看体验的以下方面:
  
- 包含加密邮件的电子邮件介绍性文本
    
- 包含加密邮件的电子邮件免责声明文本
    
- 显示在邮件查看门户中的门户文本
    
- 显示在电子邮件和查看门户中的徽标
    
您也可以随时还原到默认的外观。
  
以下示例显示电子邮件附件中的 ContosoPharma 的自定义徽标：
  
![查看加密消息页面的示例](media/TA-OME-3attachment2.jpg)
  
 **自定义加密电子邮件以及与组织品牌的加密门户**
  
1. 使用远程 powershell 连接到 exchange online, 如[connect to Exchange online using remote powershell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated)中所述。
    
2. 按照如下所述使用 set-omeconfiguration cmdlet: [set-omeconfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)或使用下表进行指南。 
    
   **加密自定义选项**

|**自定义加密体验的这一功能**|**使用这些 Windows PowerShell 命令**|
|:-----|:-----|
|加密电子邮件随附的默认文本  <br/> 默认文本显示在说明的上方，以查看加密邮件  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> **示例：** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"` <br/> |
|包含加密邮件的电子邮件中的免责声明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> **示例：** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"` <br/> |
|显示在加密邮件查看门户顶部的文本  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> **示例：** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"` <br/> |
|徽标  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **示例：** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支持的文件格式：.png、.jpg、.bmp 或 .tiff  <br/> 徽标文件的最佳大小：小于 40 KB  <br/> 徽标图像的最佳大小：170x70 像素  <br/> |
   
 **从加密电子邮件和加密门户中删除品牌自定义**
  
1. 使用远程 powershell 连接到 exchange online, 如[connect to Exchange online using remote powershell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)中所述。
    
2. 按照如下所述使用 set-omeconfiguration cmdlet: [set-omeconfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)。若要从 DisclaimerText、EmailText 和 PortalText 值中删除您的组织的标记自定义项, 请将该值设置为`""`一个空字符串。对于所有图像值 (如 "徽标"), 请将`"$null"`值设置为。
    
   **加密自定义选项**

|**将加密体验的此功能还原到默认的文本和图片**|**使用这些 Windows PowerShell 命令**|
|:-----|:-----|
|加密电子邮件随附的默认文本  <br/> 默认文本显示在说明的上方，以查看加密邮件  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **示例：** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|包含加密邮件的电子邮件中的免责声明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **示例：** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|显示在加密邮件查看门户顶部的文本  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **将恢复为默认值的示例:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|徽标  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **将恢复为默认值的示例:**`Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
   
## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a>在新的 OME 功能发布之前的旧版 Office 365 邮件加密的服务信息
<a name="LegacyServiceInfo"> </a>

下表提供了在发布新的 OME 功能之前的 Office 365 邮件加密服务的技术详细信息。
  
|**服务详细信息**|**说明**|
|:-----|:-----|
|客户端设备要求  <br/> |只要 HTML 附件可以在支持窗体发布的现代浏览器中打开，就可以在任何客户端设备上查看加密邮件。  <br/> |
|加密算法和美国联邦信息处理标准 (FIPS) 合规性  <br/> |Office 365 邮件加密使用与 Windows Azure 信息权限管理 (IRM) 相同的加密密钥, 并支持加密模式 2 (适用于 RSA 的2k 密钥和 SHA-1 系统的256位密钥)。有关基础 IRM 加密模式的详细信息, 请参阅[AD RMS 加密模式](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx)。<br/> |
|支持的邮件类型  <br/> |仅在邮件类 ID 为 IPM 的项目中支持 Office 365 邮件加密 **。注释**。有关详细信息, 请参阅[项目类型和邮件类](https://msdn.microsoft.com/library/office/ff861573.aspx)。<br/> |
|邮件大小限制  <br/> |Office 365 邮件加密可以加密最大为 25 mb 的邮件。有关邮件大小限制的详细信息, 请参阅[Exchange Online 限制](http://technet.microsoft.com/library/exchange-online-limits.aspx)。<br/> |
|Exchange Online 电子邮件保留策略  <br/> |Exchange Online 不存储加密的邮件。  <br/> |
|Office 365 邮件加密的语言支持  <br/> | Office 365 邮件加密支持 Office 365 语言，如下所示：  <br/>  传入的电子邮件和附加的 HTML 文件根据发件人的语言设置进行本地化。  <br/>  查看门户根据收件人的浏览器设置进行本地化。  <br/>  加密邮件的正文（内容）不进行本地化。  <br/> |
|OME 门户和 OME 查看器应用的隐私信息  <br/> |[Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md)提供了有关 Microsoft 如何处理您的隐私信息的详细信息。  <br/> |
   
## <a name="frequently-asked-questions-about-legacy-ome"></a>有关旧 OME 的常见问题
<a name="LegacyServiceInfo"> </a>

遇到有关 Office 365 邮件加密的问题？下面是一些答案。如果找不到所需的内容, 请查看[office 365 社区](http://community.office365.com/en-us/forums/default.aspx)中的 office 365 社区论坛。
  
 **问: 我的用户将加密的电子邮件发送给组织外部的收件人。外部收件人是否有需要执行哪些操作才能阅读并回复通过 Office 365 邮件加密加密的电子邮件？**
  
组织外收到 Office 365 加密邮件的收件人可以通过以下任一种方式查看邮件：
  
- 通过使用与 Office 365 关联的 Microsoft 帐户或工作或学校帐户登录。
    
- 通过使用一次性的 pass 代码。
    
 **问：Office 365 加密邮件存储在云中，还是存储在 Microsoft 服务器上？**
  
否, 加密的邮件将保留在收件人的电子邮件系统中, 当收件人打开邮件时, 它将暂时发布, 以便在 Office 365 服务器上进行查看。邮件不存储在其中。
  
 **问：能否使用我的品牌自定义加密电子邮件？**
  
能，您可以使用 Windows PowerShell cmdlet 自定义显示在加密电子邮件顶部的默认文本、免责声明文本以及在电子邮件和加密门户中使用的徽标。有关详细信息，请参阅[Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md)。
  
 **问：该服务是否要求我的组织中的每个用户都有许可证？**
  
组织中发送加密电子邮件的每个用户都必须有许可证。
  
 **问：外部收件人是否需要订阅？**
  
否，外部收件人不需要订阅即可阅读或回复加密邮件。 
  
 **问: Office 365 邮件加密与 Rights Management Services (RMS) 有何不同？**
  
RMS 通过提供内置模板 (例如: 不要转发和公司机密) 为组织的内部电子邮件提供信息权限保护功能。Office 365 邮件加密支持对发送给外部收件人和内部收件人的邮件进行电子邮件加密。
  
 **问: Office 365 邮件加密与 S/MIME 有何不同？**
  
S/MIME 实质上是一种客户端加密技术，需要复杂的证书管理和发布基础结构。Office 365 邮件加密使用传输规则，且不依赖于证书发布。
  
 **问：能否通过移动设备阅读加密邮件？**
  
可以, 通过从[Google Play 商店](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409)和[Apple App store](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409)下载 OME 查看器应用程序, 可以查看 Android 和 iOS 上的邮件。在 OME 查看器应用程序中打开 HTML 附件, 然后按照说明打开加密邮件。对于其他移动设备, 只要您的邮件客户端支持表单发布, 就可以打开 HTML 附件。
  
 **问：是否对回复和转发的邮件进行加密？**
  
是，在整个线程期限内，响应都会继续进行加密。
  
 **问：Office 365 邮件加密是否提供本地化？**
  
传入电子邮件和 HTML 内容会进行本地化，具体取决于发件人电子邮件设置。查看门户根据收件人的浏览器设置进行本地化。不过，加密邮件的实际正文（内容）不会进行本地化。
  
 **问：Office 365 邮件加密使用哪种加密方法？**
  
Office 365 邮件加密使用权限管理服务 (RMS) 作为其加密基础结构。所使用的加密方法取决于从何处获取用来加密和解密邮件的 RMS 密钥。
  
- 如果使用 Microsoft Azure RMS 获取密钥, 则使用加密模式2。加密模式2是更新并增强的 AD RMS 加密实现。它支持针对签名和加密的 RSA 2048, 并支持用于签名的 SHA-256。
    
- 如果您使用 Active Directory (AD) RMS 获取这些密钥，则可以使用加密模式 1，也可以使用加密模式 2。使用的方法取决于您的本地 AD RMS 部署。加密模式 1 是原始的 AD RMS 加密实现。它支持 RSA 1024 签名和加密，并支持 sha-1 签名。该模式继续支持 RMS 的所有当前版本。
    
有关详细信息, 请参阅[AD RMS 加密模式](http://go.microsoft.com/fwlink/p/?LinkId=398616)。
  
 **问：为什么一些加密邮件显示其来自 Office365@messaging.microsoft.com？**
  
当加密回复从加密门户或通过 OME 查看器应用发送时，发送电子邮件地址将设为 Office365@messaging.microsoft.com，因为该加密邮件是通过 Microsoft 终结点发送的。这有助于防止加密邮件被标记为垃圾邮件。电子邮件上显示的名称和加密门户内的地址不会因为这个标签而更改。此外，该标签仅适用于通过门户而不是通过任何其他电子邮件客户端发送的邮件。
  
 **问: 我是 Exchange 托管加密 (EHE) 订阅者。在哪里可以了解有关升级到 Office 365 邮件加密的更多信息？**
  
所有 EHE 客户都已升级到 Office 365 邮件加密。有关详细信息, 请访问[Exchange 托管加密升级中心](http://go.microsoft.com/fwlink/p/?LinkID=511077)。
  
 **问: 我是否需要在组织的防火墙中打开任何 url、IP 地址或端口以支持 Office 365 邮件加密？**
  
是。您必须将 Exchange Online 的 URL 添加到组织的允许列表，对通过 Office 365 邮件加密进行加密的邮件启用身份验证。有关 Exchange Online URL 的列表，请参阅 [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx)。
  
 **问：我可以向多少个收件人发送 Office 365 加密邮件？**
  
加密邮件的收件人限制基于邮件的 "收件人" 字段中的字符数。 **** 组合后 (在通讯组列表展开后), "收件人**** " 字段中的收件人地址不应超过11980个字符。由于电子邮件地址可能因字符长度而异, 因此单个加密邮件没有标准收件人限制。 
  
 **问：是否可以取消发送给特定收件人的邮件？**
  
不。发送邮件后, 不能向该用户撤销邮件。
  
 **问：是否可以查看已接收和阅读的加密邮件报告吗？**
  
没有显示已查看加密邮件的报告, 但有 Office 365 报告可用, 可以利用这些报告来确定匹配特定传输规则的邮件数, 例如。
  
 **问：Microsoft 会如何处理我通过 OME 门户和 OME 查看器应用提供的信息？**
  
[Office 365 邮件加密门户隐私声明](protected-message-viewer-portal-privacy-statement.md)提供了有关 Microsoft 在你的私人信息方面所做的操作和不会执行的操作的详细信息。 
  

