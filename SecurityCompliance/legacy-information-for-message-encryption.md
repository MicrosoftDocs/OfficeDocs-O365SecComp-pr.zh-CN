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
# <a name="legacy-information-for-office-365-message-encryption"></a><span data-ttu-id="a4eea-107">Office 365 邮件加密的旧信息</span><span class="sxs-lookup"><span data-stu-id="a4eea-107">Legacy information for Office 365 Message Encryption</span></span>

<span data-ttu-id="a4eea-p102">如果您没有尚未将您的 Office 365 组织移到 OME 的新功能，但您已经部署了 OME，本文中的信息适用于您的组织。Microsoft 建议您进行规划，以将移动到新的 OME 功能只要很合理为您的组织。有关说明，请参阅[设置新的 Office 365 邮件加密功能构建到 Azure 信息保护的顶部](set-up-new-message-encryption-capabilities.md)。如果您想要找出有关的新功能，首先工作的方式的详细信息，请参阅[Office 365 邮件加密](ome.md)。本文的其余部分是指之前的版本的新功能，OME OME 行为。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p102">If you haven't yet moved your Office 365 organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization. Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md). The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>
  
<span data-ttu-id="a4eea-p103">与 Office 365 邮件加密，您的组织可以发送和接收组织内外的人员之间的加密的电子邮件。Office 365 邮件加密处理 Outlook.com、 Yahoo、 Gmail 和其他电子邮件服务。仅预期收件人的电子邮件加密有助于确保可以查看邮件的内容。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p103">With Office 365 Message Encryption, your organization can send and receive encrypted email messages between people inside and outside your organization. Office 365 Message Encryption works with Outlook.com, Yahoo, Gmail, and other email services. Email message encryption helps ensure that only intended recipients can view message content.</span></span>
  
<span data-ttu-id="a4eea-116">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="a4eea-116">Here are some examples:</span></span>
  
- <span data-ttu-id="a4eea-117">银行员工向客户发送信用卡对帐单</span><span class="sxs-lookup"><span data-stu-id="a4eea-117">A bank employee sends credit card statements to customers</span></span>
    
- <span data-ttu-id="a4eea-118">保险公司代表向客户提供政策详细信息</span><span class="sxs-lookup"><span data-stu-id="a4eea-118">An insurance company representative provides policy details to customers</span></span>
    
- <span data-ttu-id="a4eea-119">抵押经纪人请求贷款应用程序客户的财务信息</span><span class="sxs-lookup"><span data-stu-id="a4eea-119">A mortgage broker requests financial information from a customer for a loan application</span></span>
    
- <span data-ttu-id="a4eea-120">保健提供程序向患者发送保健信息</span><span class="sxs-lookup"><span data-stu-id="a4eea-120">A health care provider sends health care information to patients</span></span>
    
- <span data-ttu-id="a4eea-121">律师向客户或其他律师发送机密信息</span><span class="sxs-lookup"><span data-stu-id="a4eea-121">An attorney sends confidential information to a customer or another attorney</span></span>
    
## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a><span data-ttu-id="a4eea-122">Office 365 邮件加密没有的新功能的工作方式</span><span class="sxs-lookup"><span data-stu-id="a4eea-122">How Office 365 Message Encryption works without the new capabilities</span></span>

<span data-ttu-id="a4eea-p104">Office 365 邮件加密是基于 Microsoft Azure 权限管理 (Azure RMS) 的联机服务。使用 Azure RMS，管理员可以定义邮件流规则来确定加密的条件。例如，规则可以要求的所有邮件发送到特定收件人的加密。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p104">Office 365 Message Encryption is an online service that's built on Microsoft Azure Rights Management (Azure RMS). With Azure RMS, administrators can define mail flow rules to determine the conditions for encryption. For example, a rule can require the encryption of all messages addressed to a specific recipient.</span></span>
  
<span data-ttu-id="a4eea-126">观看此简短视频以了解 Office 365 邮件加密没有的新功能的工作原理。</span><span class="sxs-lookup"><span data-stu-id="a4eea-126">Watch this short video to see how Office 365 Message Encryption works without the new capabilities.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
<span data-ttu-id="a4eea-p105">当某人发送一封电子邮件在 Exchange Online 的与加密规则匹配时，与一个 HTML 附件发送邮件。收件人打开 HTML 附件，并按照说明 Office 365 邮件加密门户上查看加密的邮件。收件人可以选择通过登录时的 Microsoft 帐户或工作或学校与 Office 365 中，或通过使用一次性密码查看邮件。这两个选项帮助确保仅预期接收人可以查看加密的邮件。此进程是非常新 OME 功能的不同。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p105">When someone sends an email message in Exchange Online that matches an encryption rule, the message is sent with an HTML attachment. The recipient opens the HTML attachment and follows instructions to view the encrypted message on the Office 365 Message Encryption portal. The recipient can choose to view the message by signing in with a Microsoft account or a work or school associated with Office 365, or by using a one-time pass code. Both options help ensure that only the intended recipient can view the encrypted message. This process is very different for the new OME capabilities.</span></span>
  
<span data-ttu-id="a4eea-132">下方的图表总结了电子邮件是如何通过加密和解密过程的。</span><span class="sxs-lookup"><span data-stu-id="a4eea-132">The following diagram summarizes the passage of an email message through the encryption and decryption process.</span></span>
  
![显示加密电子邮件路径的图表](media/O365-Office365MessageEncryption-Concept.png)
  
<span data-ttu-id="a4eea-134">有关详细信息，请参阅[旧 Office 365 邮件加密之前的版本的新功能，OME 的服务信息](legacy-information-for-message-encryption.md#LegacyServiceInfo)。</span><span class="sxs-lookup"><span data-stu-id="a4eea-134">For more information, see [Service information for legacy Office 365 Message Encryption prior to the release of the new OME capabilities](legacy-information-for-message-encryption.md#LegacyServiceInfo).</span></span>
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a><span data-ttu-id="a4eea-135">定义不使用新的 OME 功能的 Office 365 邮件加密的邮件流规则</span><span class="sxs-lookup"><span data-stu-id="a4eea-135">Defining mail flow rules for Office 365 Message Encryption that don't use the new OME capabilities</span></span>

<span data-ttu-id="a4eea-p106">若要启用没有的新功能的 Office 365 邮件加密，Exchange Online 和 Exchange Online Protection 管理员定义 Exchange 邮件流规则。这些规则确定在什么条件电子邮件消息应进行加密，以及删除邮件加密的条件。当加密操作设置规则时，匹配的规则条件的任何邮件进行加密，他们正在发送之前。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p106">To enable Office 365 Message Encryption without the new capabilities, Exchange Online and Exchange Online Protection administrators define Exchange mail flow rules. These rules determine under what conditions email messages should be encrypted, as well as conditions for removing message encryption. When an encryption action is set for a rule, any messages that match the rule conditions are encrypted before they're sent.</span></span>
  
<span data-ttu-id="a4eea-p107">邮件流规则是灵活，让您组合条件，所以您可以满足在单个规则中的特定的安全要求。例如，您可以创建所有包含指定的关键词和发往外部收件人的邮件进行加密的规则。Office 365 邮件加密还将加密的加密的电子邮件收件人的答复还可以创建这些答复解密为方便电子邮件用户的规则。这样，您的组织中的用户不需要登录到加密门户以查看答复。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p107">Mail flow rules are flexible, letting you combine conditions so you can meet specific security requirements in a single rule. For example, you can create a rule to encrypt all messages that contain specified keywords and are addressed to external recipients. Office 365 Message Encryption also encrypts replies from recipients of encrypted email, and you can create a rule that decrypts those replies as a convenience for your email users. That way, users in your organization won't have to sign in to the encryption portal to view replies.</span></span>
  
<span data-ttu-id="a4eea-143">有关如何创建 Exchange 邮件流规则的详细信息，请参阅[Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="a4eea-143">For more information about how to create Exchange mail flow rules, see [Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a><span data-ttu-id="a4eea-144">发送、查看和回复加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="a4eea-144">Sending, viewing, and replying to encrypted email messages</span></span>

<span data-ttu-id="a4eea-p108">与 Office 365 邮件加密，电子邮件进行加密自动根据管理员定义规则。携带加密的邮件的电子邮件到达收件人的收件箱中替换为附加的 HTML 文件。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p108">With Office 365 Message Encryption, email messages are encrypted automatically, based on administrator-defined rules. An email that bears an encrypted message arrives in the recipient's Inbox with an attached HTML file.</span></span>
  
<span data-ttu-id="a4eea-p109">收件人按照打开附件和使用 Microsoft 帐户或工作或学校与 Office 365 进行身份验证的消息中的说明。如果收件人没有任一帐户，他们正在定向创建 Microsoft 帐户，使其登录以查看加密的邮件。或者，可以选择收件人获取一次性密码以查看邮件。登录或使用一次性传递代码后, 收件人可以查看解密的邮件并发送加密的答复。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p109">Recipients follow instructions in the message to open the attachment and authenticate by using a Microsoft account or a work or school associated with Office 365. If recipients don't have either account, they're directed to create a Microsoft account that will let them sign in to view the encrypted message. Alternatively, recipients can choose to get a one-time pass code to view the message. After signing in or using a one-time pass code, recipients can view the decrypted message and send an encrypted reply.</span></span>
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a><span data-ttu-id="a4eea-151">自定义与 Office 365 邮件加密的加密的邮件</span><span class="sxs-lookup"><span data-stu-id="a4eea-151">Customize encrypted messages with Office 365 Message Encryption</span></span>

<span data-ttu-id="a4eea-p110">作为 Exchange Online 和 Exchange Online Protection 管理员，您可以自定义加密的邮件。例如，您可以添加您的公司品牌和徽标，指定介绍，并在加密邮件和门户其中收件人查看加密的邮件添加免责声明文本。使用 Windows PowerShell cmdlet，您可以自定义加密的电子邮件的收件人的查看体验的以下方面：</span><span class="sxs-lookup"><span data-stu-id="a4eea-p110">As an Exchange Online and Exchange Online Protection administrator, you can customize your encrypted messages. For example, you can add your company's brand and logo, specify an introduction, and add disclaimer text in encrypted messages and in the portal where recipients view your encrypted messages. Using Windows PowerShell cmdlets, you can customize the following aspects of the viewing experience for recipients of encrypted email messages:</span></span>
  
- <span data-ttu-id="a4eea-155">包含加密邮件的电子邮件介绍性文本</span><span class="sxs-lookup"><span data-stu-id="a4eea-155">Introductory text of the email that contains the encrypted message</span></span>
    
- <span data-ttu-id="a4eea-156">包含加密邮件的电子邮件免责声明文本</span><span class="sxs-lookup"><span data-stu-id="a4eea-156">Disclaimer text of the email that contains the encrypted message</span></span>
    
- <span data-ttu-id="a4eea-157">显示在邮件查看门户中的门户文本</span><span class="sxs-lookup"><span data-stu-id="a4eea-157">Portal text that will appear in the message viewing portal</span></span>
    
- <span data-ttu-id="a4eea-158">显示在电子邮件和查看门户中的徽标</span><span class="sxs-lookup"><span data-stu-id="a4eea-158">Logo that will appear in the email message and viewing portal</span></span>
    
<span data-ttu-id="a4eea-159">您也可以随时还原到默认的外观。</span><span class="sxs-lookup"><span data-stu-id="a4eea-159">You can also revert back to the default look and feel at any time.</span></span>
  
<span data-ttu-id="a4eea-160">以下示例显示电子邮件附件中的 ContosoPharma 的自定义徽标：</span><span class="sxs-lookup"><span data-stu-id="a4eea-160">The following example shows a custom logo for ContosoPharma in the email attachment:</span></span>
  
![查看加密消息页面的示例](media/TA-OME-3attachment2.jpg)
  
 <span data-ttu-id="a4eea-162">**自定义加密电子邮件和使用组织品牌的加密门户**</span><span class="sxs-lookup"><span data-stu-id="a4eea-162">**To customize encryption email messages and the encryption portal with your organization's brand**</span></span>
  
1. <span data-ttu-id="a4eea-163">连接到 Exchange Online 使用远程 PowerShell[连接到 Exchange Online Using Remote PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated)中所述。</span><span class="sxs-lookup"><span data-stu-id="a4eea-163">Connect to Exchange Online using Remote PowerShell, as described in [Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated).</span></span>
    
2. <span data-ttu-id="a4eea-164">使用 Set-omeconfiguration cmdlet 此处所述： [Set-omeconfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)或使用下表指导。</span><span class="sxs-lookup"><span data-stu-id="a4eea-164">Use the Set-OMEConfiguration cmdlet as described here: [Set-OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b) or use the following table for guidance.</span></span> 
    
   <span data-ttu-id="a4eea-165">**加密自定义选项**</span><span class="sxs-lookup"><span data-stu-id="a4eea-165">**Encryption customization options**</span></span>

|<span data-ttu-id="a4eea-166">**自定义加密体验的这一功能**</span><span class="sxs-lookup"><span data-stu-id="a4eea-166">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="a4eea-167">**使用这些 Windows PowerShell 命令**</span><span class="sxs-lookup"><span data-stu-id="a4eea-167">**Use these Windows PowerShell commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a4eea-168">加密电子邮件随附的默认文本</span><span class="sxs-lookup"><span data-stu-id="a4eea-168">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="a4eea-169">默认文本显示在说明的上方，以查看加密邮件</span><span class="sxs-lookup"><span data-stu-id="a4eea-169">The default text appears above the instructions for viewing encrypted messages</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> <span data-ttu-id="a4eea-170">**示例：**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"`</span><span class="sxs-lookup"><span data-stu-id="a4eea-170">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"`</span></span> <br/> |
|<span data-ttu-id="a4eea-171">包含加密邮件的电子邮件中的免责声明</span><span class="sxs-lookup"><span data-stu-id="a4eea-171">Disclaimer statement in the email that contains the encrypted message</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> <span data-ttu-id="a4eea-172">**示例：**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"`</span><span class="sxs-lookup"><span data-stu-id="a4eea-172">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"`</span></span> <br/> |
|<span data-ttu-id="a4eea-173">显示在加密邮件查看门户顶部的文本</span><span class="sxs-lookup"><span data-stu-id="a4eea-173">Text that appears at the top of the encrypted mail viewing portal</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> <span data-ttu-id="a4eea-174">**示例：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"`</span><span class="sxs-lookup"><span data-stu-id="a4eea-174">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"`</span></span> <br/> |
|<span data-ttu-id="a4eea-175">徽标</span><span class="sxs-lookup"><span data-stu-id="a4eea-175">Logo</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> <span data-ttu-id="a4eea-176">**示例：**`Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)`</span><span class="sxs-lookup"><span data-stu-id="a4eea-176">**Example:** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)`</span></span> <br/> <span data-ttu-id="a4eea-177">支持的文件格式：.png、.jpg、.bmp 或 .tiff</span><span class="sxs-lookup"><span data-stu-id="a4eea-177">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="a4eea-178">徽标文件的最佳大小：小于 40 KB</span><span class="sxs-lookup"><span data-stu-id="a4eea-178">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="a4eea-179">徽标图像的最佳大小：170x70 像素</span><span class="sxs-lookup"><span data-stu-id="a4eea-179">Optimal size of logo image: 170x70 pixels</span></span>  <br/> |
   
 <span data-ttu-id="a4eea-180">**若要移除加密电子邮件和加密门户的品牌自定义项**</span><span class="sxs-lookup"><span data-stu-id="a4eea-180">**To remove brand customizations from encryption email messages and the encryption portal**</span></span>
  
1. <span data-ttu-id="a4eea-181">连接到 Exchange Online 使用远程 PowerShell[连接到 Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="a4eea-181">Connect to Exchange Online using Remote PowerShell, as described in [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="a4eea-p111">使用 Set-omeconfiguration cmdlet 此处所述： [Set-omeconfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)。若要删除您的组织的品牌自定义项从 DisclaimerText，EmailText，和 PortalText 值，将值设置为空字符串， `""`。有关所有图像值，如徽标，将值设置为`"$null"`。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p111">Use the Set-OMEConfiguration cmdlet as described here: [Set-OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b). To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string,  `""`. For all image values, such as Logo, set the value to  `"$null"`.</span></span>
    
   <span data-ttu-id="a4eea-185">**加密自定义选项**</span><span class="sxs-lookup"><span data-stu-id="a4eea-185">**Encryption customization options**</span></span>

|<span data-ttu-id="a4eea-186">**将加密体验的此功能还原到默认的文本和图片**</span><span class="sxs-lookup"><span data-stu-id="a4eea-186">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="a4eea-187">**使用这些 Windows PowerShell 命令**</span><span class="sxs-lookup"><span data-stu-id="a4eea-187">**Use these Windows PowerShell commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a4eea-188">加密电子邮件随附的默认文本</span><span class="sxs-lookup"><span data-stu-id="a4eea-188">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="a4eea-189">默认文本显示在说明的上方，以查看加密邮件</span><span class="sxs-lookup"><span data-stu-id="a4eea-189">The default text appears above the instructions for viewing encrypted messages</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> <span data-ttu-id="a4eea-190">**示例：**`Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`</span><span class="sxs-lookup"><span data-stu-id="a4eea-190">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`</span></span> <br/> |
|<span data-ttu-id="a4eea-191">包含加密邮件的电子邮件中的免责声明</span><span class="sxs-lookup"><span data-stu-id="a4eea-191">Disclaimer statement in the email that contains the encrypted message</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> <span data-ttu-id="a4eea-192">**示例：**`Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`</span><span class="sxs-lookup"><span data-stu-id="a4eea-192">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`</span></span> <br/> |
|<span data-ttu-id="a4eea-193">显示在加密邮件查看门户顶部的文本</span><span class="sxs-lookup"><span data-stu-id="a4eea-193">Text that appears at the top of the encrypted mail viewing portal</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> <span data-ttu-id="a4eea-194">**还原为默认的示例：**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`</span><span class="sxs-lookup"><span data-stu-id="a4eea-194">**Example reverting back to default:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`</span></span> <br/> |
|<span data-ttu-id="a4eea-195">徽标</span><span class="sxs-lookup"><span data-stu-id="a4eea-195">Logo</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> <span data-ttu-id="a4eea-196">**还原为默认的示例：**`Set-OMEConfiguration -Identity "OME configuration" -Image $null`</span><span class="sxs-lookup"><span data-stu-id="a4eea-196">**Example reverting back to default:** `Set-OMEConfiguration -Identity "OME configuration" -Image $null`</span></span> <br/> |
   
## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a><span data-ttu-id="a4eea-197">服务信息的旧 Office 365 邮件加密之前版本的新 OME 功能</span><span class="sxs-lookup"><span data-stu-id="a4eea-197">Service information for legacy Office 365 Message Encryption prior to the release of the new OME capabilities</span></span>
<span data-ttu-id="a4eea-198"><a name="LegacyServiceInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="a4eea-198"></span></span>

<span data-ttu-id="a4eea-199">下表之前的新功能，OME 的版本的 Office 365 邮件加密服务提供的技术详细信息。</span><span class="sxs-lookup"><span data-stu-id="a4eea-199">The following table provides technical details for the Office 365 Message Encryption service prior to the release of the new OME capabilities.</span></span>
  
|<span data-ttu-id="a4eea-200">**服务详细信息**</span><span class="sxs-lookup"><span data-stu-id="a4eea-200">**Service details**</span></span>|<span data-ttu-id="a4eea-201">**说明**</span><span class="sxs-lookup"><span data-stu-id="a4eea-201">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a4eea-202">客户端设备要求</span><span class="sxs-lookup"><span data-stu-id="a4eea-202">Client device requirements</span></span>  <br/> |<span data-ttu-id="a4eea-203">只要 HTML 附件可以在支持窗体发布的现代浏览器中打开，就可以在任何客户端设备上查看加密邮件。</span><span class="sxs-lookup"><span data-stu-id="a4eea-203">Encrypted messages can be viewed on any client device, as long as the HTML attachment can be opened in a modern browser that supports Form Post.</span></span>  <br/> |
|<span data-ttu-id="a4eea-204">加密算法和美国联邦信息处理标准 (FIPS) 合规性</span><span class="sxs-lookup"><span data-stu-id="a4eea-204">Encryption algorithm and Federal Information Processing Standards (FIPS) compliance</span></span>  <br/> |<span data-ttu-id="a4eea-p112">Office 365 邮件加密使用作为 Windows Azure 信息权限管理 (IRM) 的相同的加密密钥，并为 sha-1 系统支持加密模式 2 （2k 密钥 RSA） 和 256 位密钥。有关基础的 IRM 加密模式的详细信息，请参阅[AD RMS 加密模式](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p112">Office 365 Message Encryption uses the same encryption keys as Windows Azure Information Rights Management (IRM) and supports Cryptographic Mode 2 (2K key for RSA and 256 bits key for SHA-1 systems). For more information about the underlying IRM cryptographic modes, see [AD RMS Cryptographic Modes](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx).  </span></span><br/> |
|<span data-ttu-id="a4eea-207">支持的邮件类型</span><span class="sxs-lookup"><span data-stu-id="a4eea-207">Supported message types</span></span>  <br/> |<span data-ttu-id="a4eea-p113">具有邮件类**IPM 的 ID 的项目才支持 office 365 邮件加密。注意**。有关详细信息，请参阅[项目类型和邮件类](https://msdn.microsoft.com/library/office/ff861573.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p113">Office 365 Message Encryption is only supported for items that have a message class ID of **IPM.Note**. For more information, see [Item types and message classes](https://msdn.microsoft.com/library/office/ff861573.aspx).  </span></span><br/> |
|<span data-ttu-id="a4eea-210">邮件大小限制</span><span class="sxs-lookup"><span data-stu-id="a4eea-210">Message size limits</span></span>  <br/> |<span data-ttu-id="a4eea-p114">Office 365 邮件加密可以加密邮件的最多 25 兆字节。有关邮件大小限制的详细信息，请参阅[Exchange Online 限制](http://technet.microsoft.com/library/exchange-online-limits.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p114">Office 365 Message Encryption can encrypt messages of up to 25 megabytes. For more details about message size limits, see [Exchange Online Limits](http://technet.microsoft.com/library/exchange-online-limits.aspx).  </span></span><br/> |
|<span data-ttu-id="a4eea-213">Exchange Online 电子邮件保留策略</span><span class="sxs-lookup"><span data-stu-id="a4eea-213">Exchange Online email retention policies</span></span>  <br/> |<span data-ttu-id="a4eea-214">Exchange Online 不存储已加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="a4eea-214">Exchange Online doesn't store the encrypted messages.</span></span>  <br/> |
|<span data-ttu-id="a4eea-215">Office 365 邮件加密的语言支持</span><span class="sxs-lookup"><span data-stu-id="a4eea-215">Language support for Office 365 Message Encryption</span></span>  <br/> | <span data-ttu-id="a4eea-216">Office 365 邮件加密支持 Office 365 语言，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a4eea-216">Office 365 Message encryption supports Office 365 languages, as follows:</span></span>  <br/>  <span data-ttu-id="a4eea-217">传入电子邮件和附加的 HTML 文件根据发件人的语言设置本地化。</span><span class="sxs-lookup"><span data-stu-id="a4eea-217">Incoming email messages and attached HTML files are localized based on the sender's language settings.</span></span>  <br/>  <span data-ttu-id="a4eea-218">查看门户根据收件人的浏览器设置进行本地化。</span><span class="sxs-lookup"><span data-stu-id="a4eea-218">The viewing portal is localized based on the recipient's browser settings.</span></span>  <br/>  <span data-ttu-id="a4eea-219">加密邮件的正文（内容）不进行本地化。</span><span class="sxs-lookup"><span data-stu-id="a4eea-219">The body (content) of the encrypted message isn't localized.</span></span>  <br/> |
|<span data-ttu-id="a4eea-220">OME 门户和 OME 查看器应用的隐私信息</span><span class="sxs-lookup"><span data-stu-id="a4eea-220">Privacy information for OME Portal and OME Viewer App</span></span>  <br/> |<span data-ttu-id="a4eea-221">[Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md)提供了有关 Microsoft 如何处理您的隐私信息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a4eea-221">The [Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md) provides detailed information about what Microsoft does and doesn't do with your private information.</span></span>  <br/> |
   
## <a name="frequently-asked-questions-about-legacy-ome"></a><span data-ttu-id="a4eea-222">有关旧 OME 的常见问题</span><span class="sxs-lookup"><span data-stu-id="a4eea-222">Frequently Asked Questions about legacy OME</span></span>
<span data-ttu-id="a4eea-223"><a name="LegacyServiceInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="a4eea-223"></span></span>

<span data-ttu-id="a4eea-p115">获得有关 Office 365 邮件加密的问题？以下是一些解答。如果找不到您的需要则检查 Office 365 社区论坛在[Office 365 社区](http://community.office365.com/en-us/forums/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p115">Got questions about Office 365 Message Encryption? Here are some answers. If you can't find what you need, check the Office 365 community forums at [Office 365 community](http://community.office365.com/en-us/forums/default.aspx).</span></span>
  
 <span data-ttu-id="a4eea-227">**问： 我的用户向我们组织外部的收件人发送加密的电子邮件。还有什么外部收件人必须执行的操作以读取和回复与 Office 365 邮件加密的加密电子邮件？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-227">**Q. My users send encrypted email messages to recipients outside our organization. Is there anything that external recipients have to do in order to read and reply to email messages that are encrypted with Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="a4eea-228">组织外收到 Office 365 加密邮件的收件人可以通过以下任一种方式查看邮件：</span><span class="sxs-lookup"><span data-stu-id="a4eea-228">Recipients outside your organization who receive Office 365 encrypted messages can view them in one of two ways:</span></span>
  
- <span data-ttu-id="a4eea-229">通过登录时 Microsoft 帐户或 Office 365 与关联的工作或学校帐户。</span><span class="sxs-lookup"><span data-stu-id="a4eea-229">By signing in with a Microsoft account or a work or school account associated with Office 365.</span></span>
    
- <span data-ttu-id="a4eea-230">使用一次性传递代码。</span><span class="sxs-lookup"><span data-stu-id="a4eea-230">By using a one-time pass code.</span></span>
    
 <span data-ttu-id="a4eea-231">**问：Office 365 加密邮件存储在云中，还是存储在 Microsoft 服务器上？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-231">**Q. Are Office 365 encrypted messages stored in the cloud or on Microsoft servers?**</span></span>
  
<span data-ttu-id="a4eea-p116">否，已加密的邮件保留在收件人的电子邮件系统，并且当收件人打开邮件时，暂时发布以便在 Office 365 服务器上查看。消息存储不存在。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p116">No, the encrypted messages are kept on the recipient's email system, and when the recipient opens the message, it is temporarily posted for viewing on Office 365 servers. The messages are not stored there.</span></span>
  
 <span data-ttu-id="a4eea-234">**问：能否使用我的品牌自定义加密电子邮件？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-234">**Q. Can I customize encrypted email messages with my brand?**</span></span>
  
<span data-ttu-id="a4eea-p117">能，您可以使用 Windows PowerShell cmdlet 自定义显示在加密电子邮件顶部的默认文本、免责声明文本以及在电子邮件和加密门户中使用的徽标。有关详细信息，请参阅[Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p117">Yes. You can use Windows PowerShell cmdlets to customize the default text that appears at the top of encrypted email messages, the disclaimer text, and the logo that you want to use for the email message and the encryption portal. For details, see [Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
 <span data-ttu-id="a4eea-238">**问：该服务是否要求我的组织中的每个用户都有许可证？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-238">**Q. Does the service require a license for every user in my organization?**</span></span>
  
<span data-ttu-id="a4eea-239">组织中发送加密电子邮件的每个用户都必须有许可证。</span><span class="sxs-lookup"><span data-stu-id="a4eea-239">A license is required for every user in the organization who sends encrypted email.</span></span>
  
 <span data-ttu-id="a4eea-240">**问：外部收件人是否需要订阅？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-240">**Q. Do external recipients require subscriptions?**</span></span>
  
<span data-ttu-id="a4eea-241">否，外部收件人不需要订阅即可阅读或回复加密邮件。</span><span class="sxs-lookup"><span data-stu-id="a4eea-241">No, external recipients do not require a subscription to read or reply to encrypted messages.</span></span> 
  
 <span data-ttu-id="a4eea-242">**问： 如何为 Office 365 邮件加密不同从权限管理服务 (RMS)？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-242">**Q. How is Office 365 Message Encryption different from Rights Management Services (RMS)?**</span></span>
  
<span data-ttu-id="a4eea-p118">RMS 提供的组织的内部电子邮件的信息权限保护功能通过提供内置模板，例如： 不要转发和公司机密。Office 365 邮件加密支持电子邮件加密的外部收件人以及内部收件人发送邮件。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p118">RMS provides Information Rights Protection capabilities for an organization's internal emails by providing built-in templates, such as: Do not forward and Company Confidential. Office 365 Message Encryption supports email message encryption for messages that are sent to external recipients as well as internal recipients.</span></span>
  
 <span data-ttu-id="a4eea-245">**问： 如何为 Office 365 邮件加密 S/MIME 不同？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-245">**Q. How is Office 365 Message Encryption different from S/MIME?**</span></span>
  
<span data-ttu-id="a4eea-p119">S/MIME 实质上是一种客户端加密技术，需要复杂的证书管理和发布基础结构。Office 365 邮件加密使用传输规则，且不依赖于证书发布。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p119">S/MIME is essentially a client-side encryption technology, and requires complicated certificate management and publishing infrastructure. Office 365 Message Encryption uses transport rules and does not depend on certificate publishing.</span></span>
  
 <span data-ttu-id="a4eea-248">**问：能否通过移动设备阅读加密邮件？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-248">**Q. Can I read the encrypted messages over mobile devices?**</span></span>
  
<span data-ttu-id="a4eea-p120">是，您可以通过从[Google 播放存储](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409)和[Apple 应用程序存储](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409)下载 OME 查看器应用程序在 Android 和 iOS 查看邮件。OME 查看器应用程序中打开 HTML 附件，然后按照说明进行操作以打开您的加密的邮件。对于其他移动设备，可以打开 HTML 附件，只要您的邮件客户端支持窗体发布。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p120">Yes, you can view messages on Android and iOS by downloading the OME Viewer apps from the [Google Play store](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409) and the [Apple App store](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409). Open the HTML attachment in the OME Viewer app and then follow the instructions to open your encrypted message. For other mobile devices, you can open the HTML attachment as long as your mail client supports Form Post.</span></span>
  
 <span data-ttu-id="a4eea-252">**问：是否对回复和转发的邮件进行加密？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-252">**Q. Are replies and forwarded messages encrypted?**</span></span>
  
<span data-ttu-id="a4eea-p121">是，在整个线程期限内，响应都会继续进行加密。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p121">Yes. Responses continue to be encrypted throughout the duration of the thread.</span></span>
  
 <span data-ttu-id="a4eea-255">**问：Office 365 邮件加密是否提供本地化？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-255">**Q. Does Office 365 Message Encryption provide localization?**</span></span>
  
<span data-ttu-id="a4eea-p122">传入电子邮件和 HTML 内容会进行本地化，具体取决于发件人电子邮件设置。查看门户根据收件人的浏览器设置进行本地化。不过，加密邮件的实际正文（内容）不会进行本地化。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p122">Incoming email and HTML content is localized based on sender email settings. The viewing portal is localized based on recipient's browser settings. However, the actual body (content) of encrypted message isn't localized.</span></span>
  
 <span data-ttu-id="a4eea-259">**问：Office 365 邮件加密使用哪种加密方法？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-259">**Q. What encryption method is used for Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="a4eea-p123">Office 365 邮件加密使用权限管理服务 (RMS) 作为其加密基础结构。所使用的加密方法取决于从何处获取用来加密和解密邮件的 RMS 密钥。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p123">Office 365 Message Encryption uses Rights Management Services (RMS) as its encryption infrastructure. The encryption method used depends on where you obtain the RMS keys used to encrypt and decrypt messages.</span></span>
  
- <span data-ttu-id="a4eea-p124">如果您使用 Microsoft Azure RMS 获取密钥，则使用加密模式 2。加密模式 2 是更新和增强 AD RMS 加密实现。它支持 RSA 2048 签名和加密，并支持的签名 160、SHA-256 个。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p124">If you use Microsoft Azure RMS to obtain the keys, Cryptographic Mode 2 is used. Cryptographic Mode 2 is an updated and enhanced AD RMS cryptographic implementation. It supports RSA 2048 for signature and encryption, and supports SHA-256 for signature.</span></span>
    
- <span data-ttu-id="a4eea-p125">如果您使用 Active Directory (AD) RMS 获取这些密钥，则可以使用加密模式 1，也可以使用加密模式 2。使用的方法取决于您的本地 AD RMS 部署。加密模式 1 是原始的 AD RMS 加密实现。它支持 RSA 1024 签名和加密，并支持 sha-1 签名。该模式继续支持 RMS 的所有当前版本。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p125">If you use Active Directory (AD) RMS to obtain the keys, either Cryptographic Mode 1 or Cryptographic Mode 2 is used. The method used depends on your on-premises AD RMS deployment. Cryptographic Mode 1 is the original AD RMS cryptographic implementation. It supports RSA 1024 for signature and encryption, and supports SHA-1 for signature. This mode continues to be supported by all current versions of RMS.</span></span>
    
<span data-ttu-id="a4eea-270">有关详细信息，请参阅[AD RMS 加密模式](http://go.microsoft.com/fwlink/p/?LinkId=398616)。</span><span class="sxs-lookup"><span data-stu-id="a4eea-270">For more information, see [AD RMS Cryptographic Modes](http://go.microsoft.com/fwlink/p/?LinkId=398616).</span></span>
  
 <span data-ttu-id="a4eea-271">**问：为什么一些加密邮件显示其来自 Office365@messaging.microsoft.com？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-271">**Q. Why do some encrypted messages say they come from Office365@messaging.microsoft.com?**</span></span>
  
<span data-ttu-id="a4eea-p126">当加密回复从加密门户或通过 OME 查看器应用发送时，发送电子邮件地址将设为 Office365@messaging.microsoft.com，因为该加密邮件是通过 Microsoft 终结点发送的。这有助于防止加密邮件被标记为垃圾邮件。电子邮件上显示的名称和加密门户内的地址不会因为这个标签而更改。此外，该标签仅适用于通过门户而不是通过任何其他电子邮件客户端发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p126">When an encrypted reply is sent from the encryption portal or through the OME Viewer app, the sending email address is set to Office365@messaging.microsoft.com because the encrypted message is sent through a Microsoft endpoint. This helps to prevent encrypted messages from being marked as spam. The displayed name on the email and the address within the encryption portal aren't changed because of this labeling. Also, this labeling only applies to messages sent through the portal, not through any other email client.</span></span>
  
 <span data-ttu-id="a4eea-276">**问： 我是 Exchange Hosted Encryption (EHE) 订阅者。其中了解有关升级到 Office 365 邮件加密的详细信息？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-276">**Q. I am an Exchange Hosted Encryption (EHE) subscriber. Where can I learn more about the upgrade to Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="a4eea-p127">所有 EHE 客户已都升级到 Office 365 邮件加密。有关详细信息，请访问[Exchange 托管加密升级中心](http://go.microsoft.com/fwlink/p/?LinkID=511077)。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p127">All EHE customers have been upgraded to Office 365 Message Encryption. For more information, visit the [Exchange Hosted Encryption Upgrade Center](http://go.microsoft.com/fwlink/p/?LinkID=511077).</span></span>
  
 <span data-ttu-id="a4eea-279">**问： 我需要吗的打开任何 Url、 IP 地址或在我的组织的防火墙端口以支持 Office 365 邮件加密？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-279">**Q. Do I need to open any URLs, IP addresses, or ports in my organization's firewall to support Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="a4eea-p128">是。您必须将 Exchange Online 的 URL 添加到组织的允许列表，对通过 Office 365 邮件加密进行加密的邮件启用身份验证。有关 Exchange Online URL 的列表，请参阅 [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p128">Yes. You have to add URLs for Exchange Online to the allow list for your organization to enable authentication for messages encrypted by Office 365 Message Encryption. For a list of Exchange Online URLs, see [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx).</span></span>
  
 <span data-ttu-id="a4eea-283">**问：我可以向多少个收件人发送 Office 365 加密邮件？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-283">**Q. How many recipients can I send an Office 365 encrypted message to?**</span></span>
  
<span data-ttu-id="a4eea-p129">加密邮件的收件人限制基于消息的**收件人**字段中的字符数。当合并 （后通讯组列表扩展） 时，**到**字段中的收件人地址不应超过 11,980 字符。电子邮件地址的字符长度可以改变，因为没有标准收件人限制为单个加密消息。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p129">The recipient limit for an encrypted message is based on the number of characters in the message's **To** field. When combined (after distribution list expansion), recipient addresses in the **To** field should not exceed 11,980 characters. Because email addresses can vary in character length, there isn't a standard recipient limit for a single encrypted message.</span></span> 
  
 <span data-ttu-id="a4eea-287">**问：是否可以取消发送给特定收件人的邮件？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-287">**Q. Is it possible to revoke a message sent to a particular recipient?**</span></span>
  
<span data-ttu-id="a4eea-p130">不。已发送，则不能撤消到某个人一条消息。</span><span class="sxs-lookup"><span data-stu-id="a4eea-p130">No. You can't revoke a message to a particular person after it's sent.</span></span>
  
 <span data-ttu-id="a4eea-290">**问：是否可以查看已接收和阅读的加密邮件报告吗？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-290">**Q. Can I view a report of encrypted messages that have been received and read?**</span></span>
  
<span data-ttu-id="a4eea-291">没有显示，是否已查看加密的邮件，但有可用，您可以利用若要确定匹配特定传输规则，例如的邮件数的 Office 365 报告的报告。</span><span class="sxs-lookup"><span data-stu-id="a4eea-291">There isn't a report that shows if an encrypted message has been viewed, but there are Office 365 reports available that you can leverage to determine the number of messages that matched a specific transport rule, for instance.</span></span>
  
 <span data-ttu-id="a4eea-292">**问：Microsoft 会如何处理我通过 OME 门户和 OME 查看器应用提供的信息？**</span><span class="sxs-lookup"><span data-stu-id="a4eea-292">**Q. What does Microsoft do with the information I provide through the OME Portal and the OME Viewer App?**</span></span>
  
<span data-ttu-id="a4eea-293">[Office 365 邮件加密门户隐私声明](protected-message-viewer-portal-privacy-statement.md)提供有关 Microsoft 支持和不与您的私人信息的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="a4eea-293">The [Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md) provides detailed information about what Microsoft does and doesn't do with your private information.</span></span> 
  

