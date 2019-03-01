---
title: Office 365 邮件加密的旧信息
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/4/2018
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.assetid: 5986b9e1-c824-4f8f-9b7d-a2b0ae2a7fe9
ms.collection:
- M365-security-compliance
description: 如果您尚未将 Office 365 组织移动到新的 OME 功能, 但您已经部署了 OME, 则本文中的信息适用于您的组织。Microsoft 建议您制定一个计划, 尽快移动到新的 OME 功能, 因为它对您的组织合理。有关说明, 请参阅设置基于 Azure 信息保护基础构建的新 Office 365 邮件加密功能。如果您想要详细了解新功能的工作方式, 请参阅 Office 365 邮件加密。本文的其余部分是在发布新的 OME 功能之前的 OME 行为。
ms.openlocfilehash: 03e2cb9c1f7d447f2fcf222382fcc2366faf0658
ms.sourcegitcommit: 48fa456981b5c52ab8aeace173c8366b9f36723b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "30341493"
---
# <a name="legacy-information-for-office-365-message-encryption"></a><span data-ttu-id="1333e-107">Office 365 邮件加密的旧信息</span><span class="sxs-lookup"><span data-stu-id="1333e-107">Legacy information for Office 365 Message Encryption</span></span>

<span data-ttu-id="1333e-p102">如果您尚未将 Office 365 组织移动到新的 OME 功能, 但您已经部署了 OME, 则本文中的信息适用于您的组织。Microsoft 建议您制定一个计划, 尽快移动到新的 OME 功能, 因为它对您的组织合理。有关说明, 请参阅[设置基于 Azure 信息保护基础构建的新 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。如果您想要详细了解新功能的工作方式, 请参阅[Office 365 邮件加密](ome.md)。本文的其余部分是在发布新的 OME 功能之前的 OME 行为。</span><span class="sxs-lookup"><span data-stu-id="1333e-p102">If you haven't yet moved your Office 365 organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization. Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization. For instructions, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection](set-up-new-message-encryption-capabilities.md). If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md). The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>
  
<span data-ttu-id="1333e-p103">使用 Office 365 邮件加密, 组织可以在组织内部和外部的人员之间发送和接收加密的电子邮件。Office 365 邮件加密适用于 Outlook.com、Yahoo、Gmail 和其他电子邮件服务。电子邮件加密有助于确保只有预期的收件人可以查看邮件内容。</span><span class="sxs-lookup"><span data-stu-id="1333e-p103">With Office 365 Message Encryption, your organization can send and receive encrypted email messages between people inside and outside your organization. Office 365 Message Encryption works with Outlook.com, Yahoo, Gmail, and other email services. Email message encryption helps ensure that only intended recipients can view message content.</span></span>
  
<span data-ttu-id="1333e-116">此处为一些示例：</span><span class="sxs-lookup"><span data-stu-id="1333e-116">Here are some examples:</span></span>
  
- <span data-ttu-id="1333e-117">银行员工向客户发送信用卡对帐单</span><span class="sxs-lookup"><span data-stu-id="1333e-117">A bank employee sends credit card statements to customers</span></span>
    
- <span data-ttu-id="1333e-118">保险业公司代表向客户提供策略详细信息</span><span class="sxs-lookup"><span data-stu-id="1333e-118">An insurance company representative provides policy details to customers</span></span>
    
- <span data-ttu-id="1333e-119">抵押经纪人请求来自客户的贷款申请的财务信息</span><span class="sxs-lookup"><span data-stu-id="1333e-119">A mortgage broker requests financial information from a customer for a loan application</span></span>
    
- <span data-ttu-id="1333e-120">医疗保健提供商向患者发送卫生保健信息</span><span class="sxs-lookup"><span data-stu-id="1333e-120">A health care provider sends health care information to patients</span></span>
    
- <span data-ttu-id="1333e-121">律师向客户或其他律师发送机密信息</span><span class="sxs-lookup"><span data-stu-id="1333e-121">An attorney sends confidential information to a customer or another attorney</span></span>
    
## <a name="how-office-365-message-encryption-works-without-the-new-capabilities"></a><span data-ttu-id="1333e-122">如何在没有新功能的情况下运行 Office 365 邮件加密</span><span class="sxs-lookup"><span data-stu-id="1333e-122">How Office 365 Message Encryption works without the new capabilities</span></span>

<span data-ttu-id="1333e-p104">Office 365 邮件加密是基于 Microsoft Azure 权限管理 (Azure RMS) 构建的在线服务。使用 Azure RMS, 管理员可以定义邮件流规则, 以确定加密的条件。例如, 规则可以要求对发送到特定收件人的所有邮件进行加密。</span><span class="sxs-lookup"><span data-stu-id="1333e-p104">Office 365 Message Encryption is an online service that's built on Microsoft Azure Rights Management (Azure RMS). With Azure RMS, administrators can define mail flow rules to determine the conditions for encryption. For example, a rule can require the encryption of all messages addressed to a specific recipient.</span></span>
  
<span data-ttu-id="1333e-126">观看此简短视频, 了解 Office 365 邮件加密如何工作而无需新功能。</span><span class="sxs-lookup"><span data-stu-id="1333e-126">Watch this short video to see how Office 365 Message Encryption works without the new capabilities.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/c55540e7-f7f0-42f5-b254-4b2d2fbb1d63?autoplay=false]
  
<span data-ttu-id="1333e-p105">当某人在 Exchange Online 中发送与加密规则匹配的电子邮件时, 将使用 HTML 附件发送邮件。收件人打开 HTML 附件并按照说明在 Office 365 邮件加密门户中查看加密邮件。收件人可以选择使用 Microsoft 帐户或与 Office 365 关联的工作或学校登录, 或使用一次性的 pass 代码来查看邮件。这两个选项都有助于确保只有预期的收件人才能查看加密的邮件。此过程对于新的 OME 功能非常不同。</span><span class="sxs-lookup"><span data-stu-id="1333e-p105">When someone sends an email message in Exchange Online that matches an encryption rule, the message is sent with an HTML attachment. The recipient opens the HTML attachment and follows instructions to view the encrypted message on the Office 365 Message Encryption portal. The recipient can choose to view the message by signing in with a Microsoft account or a work or school associated with Office 365, or by using a one-time pass code. Both options help ensure that only the intended recipient can view the encrypted message. This process is very different for the new OME capabilities.</span></span>
  
<span data-ttu-id="1333e-132">下方的图表总结了电子邮件是如何通过加密和解密过程的。</span><span class="sxs-lookup"><span data-stu-id="1333e-132">The following diagram summarizes the passage of an email message through the encryption and decryption process.</span></span>
  
![显示加密电子邮件路径的图表](media/O365-Office365MessageEncryption-Concept.png)
  
<span data-ttu-id="1333e-134">有关详细信息, 请参阅[早期版本的 Office 365 邮件加密的服务信息, 然后再发布新的 OME 功能](legacy-information-for-message-encryption.md#LegacyServiceInfo)。</span><span class="sxs-lookup"><span data-stu-id="1333e-134">For more information, see [Service information for legacy Office 365 Message Encryption prior to the release of the new OME capabilities](legacy-information-for-message-encryption.md#LegacyServiceInfo).</span></span>
  
## <a name="defining-mail-flow-rules-for-office-365-message-encryption-that-dont-use-the-new-ome-capabilities"></a><span data-ttu-id="1333e-135">为不使用新 OME 功能的 Office 365 邮件加密定义邮件流规则</span><span class="sxs-lookup"><span data-stu-id="1333e-135">Defining mail flow rules for Office 365 Message Encryption that don't use the new OME capabilities</span></span>

<span data-ttu-id="1333e-p106">若要在不使用新功能的情况下启用 Office 365 邮件加密, exchange online 和 exchange online Protection 管理员将定义 Exchange 邮件流规则。这些规则确定应在哪些条件下加密电子邮件, 以及删除邮件加密的条件。为规则设置加密操作后, 与规则条件匹配的任何邮件在发送之前都会被加密。</span><span class="sxs-lookup"><span data-stu-id="1333e-p106">To enable Office 365 Message Encryption without the new capabilities, Exchange Online and Exchange Online Protection administrators define Exchange mail flow rules. These rules determine under what conditions email messages should be encrypted, as well as conditions for removing message encryption. When an encryption action is set for a rule, any messages that match the rule conditions are encrypted before they're sent.</span></span>
  
<span data-ttu-id="1333e-p107">邮件流规则是灵活的, 允许您将条件组合在一起, 以便您可以在单个规则中满足特定的安全要求。例如, 您可以创建一个规则来加密包含指定关键字并发送给外部收件人的所有邮件。Office 365 邮件加密还会对来自加密电子邮件的收件人的回复进行加密, 并且可以创建一个规则来解密这些回复, 以方便您使用电子邮件用户。这样, 组织中的用户无需登录到加密门户即可查看答复。</span><span class="sxs-lookup"><span data-stu-id="1333e-p107">Mail flow rules are flexible, letting you combine conditions so you can meet specific security requirements in a single rule. For example, you can create a rule to encrypt all messages that contain specified keywords and are addressed to external recipients. Office 365 Message Encryption also encrypts replies from recipients of encrypted email, and you can create a rule that decrypts those replies as a convenience for your email users. That way, users in your organization won't have to sign in to the encryption portal to view replies.</span></span>
  
<span data-ttu-id="1333e-143">有关如何创建 Exchange 邮件流规则的详细信息, 请参阅[定义 Office 365 邮件加密的规则](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="1333e-143">For more information about how to create Exchange mail flow rules, see [Define Rules for Office 365 Message Encryption](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a><span data-ttu-id="1333e-144">发送、查看和回复加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="1333e-144">Sending, viewing, and replying to encrypted email messages</span></span>

<span data-ttu-id="1333e-p108">使用 Office 365 邮件加密时, 电子邮件将根据管理员定义的规则自动加密。携带加密邮件的电子邮件到达收件人的收件箱, 并附带一个 HTML 文件。</span><span class="sxs-lookup"><span data-stu-id="1333e-p108">With Office 365 Message Encryption, email messages are encrypted automatically, based on administrator-defined rules. An email that bears an encrypted message arrives in the recipient's Inbox with an attached HTML file.</span></span>
  
<span data-ttu-id="1333e-p109">收件人按照邮件中的说明打开附件, 并使用 Microsoft 帐户或与 Office 365 相关联的工作或学校进行身份验证。如果收件人没有任何帐户, 则会将其定向到创建一个 Microsoft 帐户, 让他们登录以查看加密邮件。或者, 收件人可以选择获取一次性传递代码来查看邮件。登录或使用一次性传递代码后, 收件人可以查看解密的邮件并发送加密答复。</span><span class="sxs-lookup"><span data-stu-id="1333e-p109">Recipients follow instructions in the message to open the attachment and authenticate by using a Microsoft account or a work or school associated with Office 365. If recipients don't have either account, they're directed to create a Microsoft account that will let them sign in to view the encrypted message. Alternatively, recipients can choose to get a one-time pass code to view the message. After signing in or using a one-time pass code, recipients can view the decrypted message and send an encrypted reply.</span></span>
  
## <a name="customize-encrypted-messages-with-office-365-message-encryption"></a><span data-ttu-id="1333e-151">使用 Office 365 邮件加密自定义加密邮件</span><span class="sxs-lookup"><span data-stu-id="1333e-151">Customize encrypted messages with Office 365 Message Encryption</span></span>

<span data-ttu-id="1333e-p110">作为 exchange online 和 exchange online Protection 管理员, 您可以自定义加密邮件。例如, 您可以添加公司的品牌和徽标, 指定简介, 并在加密邮件中以及在收件人查看加密邮件的门户中添加免责声明文本。使用 Windows PowerShell cmdlet, 您可以自定义加密电子邮件的收件人的查看体验的以下方面:</span><span class="sxs-lookup"><span data-stu-id="1333e-p110">As an Exchange Online and Exchange Online Protection administrator, you can customize your encrypted messages. For example, you can add your company's brand and logo, specify an introduction, and add disclaimer text in encrypted messages and in the portal where recipients view your encrypted messages. Using Windows PowerShell cmdlets, you can customize the following aspects of the viewing experience for recipients of encrypted email messages:</span></span>
  
- <span data-ttu-id="1333e-155">包含加密邮件的电子邮件介绍性文本</span><span class="sxs-lookup"><span data-stu-id="1333e-155">Introductory text of the email that contains the encrypted message</span></span>
    
- <span data-ttu-id="1333e-156">包含加密邮件的电子邮件免责声明文本</span><span class="sxs-lookup"><span data-stu-id="1333e-156">Disclaimer text of the email that contains the encrypted message</span></span>
    
- <span data-ttu-id="1333e-157">显示在邮件查看门户中的门户文本</span><span class="sxs-lookup"><span data-stu-id="1333e-157">Portal text that will appear in the message viewing portal</span></span>
    
- <span data-ttu-id="1333e-158">显示在电子邮件和查看门户中的徽标</span><span class="sxs-lookup"><span data-stu-id="1333e-158">Logo that will appear in the email message and viewing portal</span></span>
    
<span data-ttu-id="1333e-159">您也可以随时还原到默认的外观。</span><span class="sxs-lookup"><span data-stu-id="1333e-159">You can also revert back to the default look and feel at any time.</span></span>
  
<span data-ttu-id="1333e-160">以下示例显示电子邮件附件中的 ContosoPharma 的自定义徽标：</span><span class="sxs-lookup"><span data-stu-id="1333e-160">The following example shows a custom logo for ContosoPharma in the email attachment:</span></span>
  
![查看加密消息页面的示例](media/TA-OME-3attachment2.jpg)
  
 <span data-ttu-id="1333e-162">**自定义加密电子邮件以及与组织品牌的加密门户**</span><span class="sxs-lookup"><span data-stu-id="1333e-162">**To customize encryption email messages and the encryption portal with your organization's brand**</span></span>
  
1. <span data-ttu-id="1333e-163">使用远程 powershell 连接到 exchange online, 如[connect to Exchange online using remote powershell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated)中所述。</span><span class="sxs-lookup"><span data-stu-id="1333e-163">Connect to Exchange Online using Remote PowerShell, as described in [Connect to Exchange Online Using Remote PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-exchange-online-tenants-with-remote-windows-powershell-for-delegated).</span></span>
    
2. <span data-ttu-id="1333e-164">按照如下所述使用 set-omeconfiguration cmdlet: [set-omeconfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)或使用下表进行指南。</span><span class="sxs-lookup"><span data-stu-id="1333e-164">Use the Set-OMEConfiguration cmdlet as described here: [Set-OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b) or use the following table for guidance.</span></span> 
    
   <span data-ttu-id="1333e-165">**加密自定义选项**</span><span class="sxs-lookup"><span data-stu-id="1333e-165">**Encryption customization options**</span></span>

|<span data-ttu-id="1333e-166">**自定义加密体验的这一功能**</span><span class="sxs-lookup"><span data-stu-id="1333e-166">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="1333e-167">**使用这些 Windows PowerShell 命令**</span><span class="sxs-lookup"><span data-stu-id="1333e-167">**Use these Windows PowerShell commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1333e-168">加密电子邮件随附的默认文本</span><span class="sxs-lookup"><span data-stu-id="1333e-168">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="1333e-169">默认文本显示在说明的上方，以查看加密邮件</span><span class="sxs-lookup"><span data-stu-id="1333e-169">The default text appears above the instructions for viewing encrypted messages</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<string of up to 1024 characters>"` <br/> <span data-ttu-id="1333e-170">**示例：** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"`</span><span class="sxs-lookup"><span data-stu-id="1333e-170">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system"`</span></span> <br/> |
|<span data-ttu-id="1333e-171">包含加密邮件的电子邮件中的免责声明</span><span class="sxs-lookup"><span data-stu-id="1333e-171">Disclaimer statement in the email that contains the encrypted message</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<your disclaimer statement, string of up to 1024 characters>"` <br/> <span data-ttu-id="1333e-172">**示例：** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"`</span><span class="sxs-lookup"><span data-stu-id="1333e-172">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only"`</span></span> <br/> |
|<span data-ttu-id="1333e-173">显示在加密邮件查看门户顶部的文本</span><span class="sxs-lookup"><span data-stu-id="1333e-173">Text that appears at the top of the encrypted mail viewing portal</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<text for your portal, string of up to 128 characters>"` <br/> <span data-ttu-id="1333e-174">**示例：** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"`</span><span class="sxs-lookup"><span data-stu-id="1333e-174">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal"`</span></span> <br/> |
|<span data-ttu-id="1333e-175">徽标</span><span class="sxs-lookup"><span data-stu-id="1333e-175">Logo</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> <span data-ttu-id="1333e-176">**示例：** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)`</span><span class="sxs-lookup"><span data-stu-id="1333e-176">**Example:** `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)`</span></span> <br/> <span data-ttu-id="1333e-177">支持的文件格式：.png、.jpg、.bmp 或 .tiff</span><span class="sxs-lookup"><span data-stu-id="1333e-177">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="1333e-178">徽标文件的最佳大小：小于 40 KB</span><span class="sxs-lookup"><span data-stu-id="1333e-178">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="1333e-179">徽标图像的最佳大小：170x70 像素</span><span class="sxs-lookup"><span data-stu-id="1333e-179">Optimal size of logo image: 170x70 pixels</span></span>  <br/> |
   
 <span data-ttu-id="1333e-180">**从加密电子邮件和加密门户中删除品牌自定义**</span><span class="sxs-lookup"><span data-stu-id="1333e-180">**To remove brand customizations from encryption email messages and the encryption portal**</span></span>
  
1. <span data-ttu-id="1333e-181">使用远程 powershell 连接到 exchange online, 如[connect to Exchange online using remote powershell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="1333e-181">Connect to Exchange Online using Remote PowerShell, as described in [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="1333e-p111">按照如下所述使用 set-omeconfiguration cmdlet: [set-omeconfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)。若要从 DisclaimerText、EmailText 和 PortalText 值中删除您的组织的标记自定义项, 请将该值设置为`""`一个空字符串。对于所有图像值 (如 "徽标"), 请将`"$null"`值设置为。</span><span class="sxs-lookup"><span data-stu-id="1333e-p111">Use the Set-OMEConfiguration cmdlet as described here: [Set-OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b). To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string,  `""`. For all image values, such as Logo, set the value to  `"$null"`.</span></span>
    
   <span data-ttu-id="1333e-185">**加密自定义选项**</span><span class="sxs-lookup"><span data-stu-id="1333e-185">**Encryption customization options**</span></span>

|<span data-ttu-id="1333e-186">**将加密体验的此功能还原到默认的文本和图片**</span><span class="sxs-lookup"><span data-stu-id="1333e-186">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="1333e-187">**使用这些 Windows PowerShell 命令**</span><span class="sxs-lookup"><span data-stu-id="1333e-187">**Use these Windows PowerShell commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1333e-188">加密电子邮件随附的默认文本</span><span class="sxs-lookup"><span data-stu-id="1333e-188">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="1333e-189">默认文本显示在说明的上方，以查看加密邮件</span><span class="sxs-lookup"><span data-stu-id="1333e-189">The default text appears above the instructions for viewing encrypted messages</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> <span data-ttu-id="1333e-190">**示例：** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`</span><span class="sxs-lookup"><span data-stu-id="1333e-190">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`</span></span> <br/> |
|<span data-ttu-id="1333e-191">包含加密邮件的电子邮件中的免责声明</span><span class="sxs-lookup"><span data-stu-id="1333e-191">Disclaimer statement in the email that contains the encrypted message</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> <span data-ttu-id="1333e-192">**示例：** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`</span><span class="sxs-lookup"><span data-stu-id="1333e-192">**Example:** `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`</span></span> <br/> |
|<span data-ttu-id="1333e-193">显示在加密邮件查看门户顶部的文本</span><span class="sxs-lookup"><span data-stu-id="1333e-193">Text that appears at the top of the encrypted mail viewing portal</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> <span data-ttu-id="1333e-194">**将恢复为默认值的示例:**`Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`</span><span class="sxs-lookup"><span data-stu-id="1333e-194">**Example reverting back to default:** `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`</span></span> <br/> |
|<span data-ttu-id="1333e-195">徽标</span><span class="sxs-lookup"><span data-stu-id="1333e-195">Logo</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> <span data-ttu-id="1333e-196">**将恢复为默认值的示例:**`Set-OMEConfiguration -Identity "OME configuration" -Image $null`</span><span class="sxs-lookup"><span data-stu-id="1333e-196">**Example reverting back to default:** `Set-OMEConfiguration -Identity "OME configuration" -Image $null`</span></span> <br/> |
   
## <a name="service-information-for-legacy-office-365-message-encryption-prior-to-the-release-of-the-new-ome-capabilities"></a><span data-ttu-id="1333e-197">在新的 OME 功能发布之前的旧版 Office 365 邮件加密的服务信息</span><span class="sxs-lookup"><span data-stu-id="1333e-197">Service information for legacy Office 365 Message Encryption prior to the release of the new OME capabilities</span></span>
<span data-ttu-id="1333e-198"><a name="LegacyServiceInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="1333e-198"></span></span>

<span data-ttu-id="1333e-199">下表提供了在发布新的 OME 功能之前的 Office 365 邮件加密服务的技术详细信息。</span><span class="sxs-lookup"><span data-stu-id="1333e-199">The following table provides technical details for the Office 365 Message Encryption service prior to the release of the new OME capabilities.</span></span>
  
|<span data-ttu-id="1333e-200">**服务详细信息**</span><span class="sxs-lookup"><span data-stu-id="1333e-200">**Service details**</span></span>|<span data-ttu-id="1333e-201">**说明**</span><span class="sxs-lookup"><span data-stu-id="1333e-201">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1333e-202">客户端设备要求</span><span class="sxs-lookup"><span data-stu-id="1333e-202">Client device requirements</span></span>  <br/> |<span data-ttu-id="1333e-203">只要 HTML 附件可以在支持窗体发布的现代浏览器中打开，就可以在任何客户端设备上查看加密邮件。</span><span class="sxs-lookup"><span data-stu-id="1333e-203">Encrypted messages can be viewed on any client device, as long as the HTML attachment can be opened in a modern browser that supports Form Post.</span></span>  <br/> |
|<span data-ttu-id="1333e-204">加密算法和美国联邦信息处理标准 (FIPS) 合规性</span><span class="sxs-lookup"><span data-stu-id="1333e-204">Encryption algorithm and Federal Information Processing Standards (FIPS) compliance</span></span>  <br/> |<span data-ttu-id="1333e-p112">Office 365 邮件加密使用与 Windows Azure 信息权限管理 (IRM) 相同的加密密钥, 并支持加密模式 2 (适用于 RSA 的2k 密钥和 SHA-1 系统的256位密钥)。有关基础 IRM 加密模式的详细信息, 请参阅[AD RMS 加密模式](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1333e-p112">Office 365 Message Encryption uses the same encryption keys as Windows Azure Information Rights Management (IRM) and supports Cryptographic Mode 2 (2K key for RSA and 256 bits key for SHA-1 systems). For more information about the underlying IRM cryptographic modes, see [AD RMS Cryptographic Modes](http://technet.microsoft.com/library/hh867439%28WS.10%29.aspx).  </span></span><br/> |
|<span data-ttu-id="1333e-207">支持的邮件类型</span><span class="sxs-lookup"><span data-stu-id="1333e-207">Supported message types</span></span>  <br/> |<span data-ttu-id="1333e-p113">仅在邮件类 ID 为 IPM 的项目中支持 Office 365 邮件加密 **。注释**。有关详细信息, 请参阅[项目类型和邮件类](https://msdn.microsoft.com/library/office/ff861573.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1333e-p113">Office 365 Message Encryption is only supported for items that have a message class ID of **IPM.Note**. For more information, see [Item types and message classes](https://msdn.microsoft.com/library/office/ff861573.aspx).  </span></span><br/> |
|<span data-ttu-id="1333e-210">邮件大小限制</span><span class="sxs-lookup"><span data-stu-id="1333e-210">Message size limits</span></span>  <br/> |<span data-ttu-id="1333e-p114">Office 365 邮件加密可以加密最大为 25 mb 的邮件。有关邮件大小限制的详细信息, 请参阅[Exchange Online 限制](http://technet.microsoft.com/library/exchange-online-limits.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1333e-p114">Office 365 Message Encryption can encrypt messages of up to 25 megabytes. For more details about message size limits, see [Exchange Online Limits](http://technet.microsoft.com/library/exchange-online-limits.aspx).  </span></span><br/> |
|<span data-ttu-id="1333e-213">Exchange Online 电子邮件保留策略</span><span class="sxs-lookup"><span data-stu-id="1333e-213">Exchange Online email retention policies</span></span>  <br/> |<span data-ttu-id="1333e-214">Exchange Online 不存储加密的邮件。</span><span class="sxs-lookup"><span data-stu-id="1333e-214">Exchange Online doesn't store the encrypted messages.</span></span>  <br/> |
|<span data-ttu-id="1333e-215">Office 365 邮件加密的语言支持</span><span class="sxs-lookup"><span data-stu-id="1333e-215">Language support for Office 365 Message Encryption</span></span>  <br/> | <span data-ttu-id="1333e-216">Office 365 邮件加密支持 Office 365 语言，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1333e-216">Office 365 Message encryption supports Office 365 languages, as follows:</span></span>  <br/>  <span data-ttu-id="1333e-217">传入的电子邮件和附加的 HTML 文件根据发件人的语言设置进行本地化。</span><span class="sxs-lookup"><span data-stu-id="1333e-217">Incoming email messages and attached HTML files are localized based on the sender's language settings.</span></span>  <br/>  <span data-ttu-id="1333e-218">查看门户根据收件人的浏览器设置进行本地化。</span><span class="sxs-lookup"><span data-stu-id="1333e-218">The viewing portal is localized based on the recipient's browser settings.</span></span>  <br/>  <span data-ttu-id="1333e-219">加密邮件的正文（内容）不进行本地化。</span><span class="sxs-lookup"><span data-stu-id="1333e-219">The body (content) of the encrypted message isn't localized.</span></span>  <br/> |
|<span data-ttu-id="1333e-220">OME 门户和 OME 查看器应用的隐私信息</span><span class="sxs-lookup"><span data-stu-id="1333e-220">Privacy information for OME Portal and OME Viewer App</span></span>  <br/> |<span data-ttu-id="1333e-221">[Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md)提供了有关 Microsoft 如何处理您的隐私信息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1333e-221">The [Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md) provides detailed information about what Microsoft does and doesn't do with your private information.</span></span>  <br/> |
   
## <a name="frequently-asked-questions-about-legacy-ome"></a><span data-ttu-id="1333e-222">有关旧 OME 的常见问题</span><span class="sxs-lookup"><span data-stu-id="1333e-222">Frequently Asked Questions about legacy OME</span></span>
<span data-ttu-id="1333e-223"><a name="LegacyServiceInfo"> </a></span><span class="sxs-lookup"><span data-stu-id="1333e-223"></span></span>

<span data-ttu-id="1333e-p115">遇到有关 Office 365 邮件加密的问题？下面是一些答案。如果找不到所需的内容, 请查看[office 365 社区](http://community.office365.com/en-us/forums/default.aspx)中的 office 365 社区论坛。</span><span class="sxs-lookup"><span data-stu-id="1333e-p115">Got questions about Office 365 Message Encryption? Here are some answers. If you can't find what you need, check the Office 365 community forums at [Office 365 community](http://community.office365.com/en-us/forums/default.aspx).</span></span>
  
 <span data-ttu-id="1333e-227">**问: 我的用户将加密的电子邮件发送给组织外部的收件人。外部收件人是否有需要执行哪些操作才能阅读并回复通过 Office 365 邮件加密加密的电子邮件？**</span><span class="sxs-lookup"><span data-stu-id="1333e-227">**Q. My users send encrypted email messages to recipients outside our organization. Is there anything that external recipients have to do in order to read and reply to email messages that are encrypted with Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="1333e-228">组织外收到 Office 365 加密邮件的收件人可以通过以下任一种方式查看邮件：</span><span class="sxs-lookup"><span data-stu-id="1333e-228">Recipients outside your organization who receive Office 365 encrypted messages can view them in one of two ways:</span></span>
  
- <span data-ttu-id="1333e-229">通过使用与 Office 365 关联的 Microsoft 帐户或工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="1333e-229">By signing in with a Microsoft account or a work or school account associated with Office 365.</span></span>
    
- <span data-ttu-id="1333e-230">通过使用一次性的 pass 代码。</span><span class="sxs-lookup"><span data-stu-id="1333e-230">By using a one-time pass code.</span></span>
    
 <span data-ttu-id="1333e-231">**问：Office 365 加密邮件存储在云中，还是存储在 Microsoft 服务器上？**</span><span class="sxs-lookup"><span data-stu-id="1333e-231">**Q. Are Office 365 encrypted messages stored in the cloud or on Microsoft servers?**</span></span>
  
<span data-ttu-id="1333e-p116">否, 加密的邮件将保留在收件人的电子邮件系统中, 当收件人打开邮件时, 它将暂时发布, 以便在 Office 365 服务器上进行查看。邮件不存储在其中。</span><span class="sxs-lookup"><span data-stu-id="1333e-p116">No, the encrypted messages are kept on the recipient's email system, and when the recipient opens the message, it is temporarily posted for viewing on Office 365 servers. The messages are not stored there.</span></span>
  
 <span data-ttu-id="1333e-234">**问：能否使用我的品牌自定义加密电子邮件？**</span><span class="sxs-lookup"><span data-stu-id="1333e-234">**Q. Can I customize encrypted email messages with my brand?**</span></span>
  
<span data-ttu-id="1333e-p117">能，您可以使用 Windows PowerShell cmdlet 自定义显示在加密电子邮件顶部的默认文本、免责声明文本以及在电子邮件和加密门户中使用的徽标。有关详细信息，请参阅[Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="1333e-p117">Yes. You can use Windows PowerShell cmdlets to customize the default text that appears at the top of encrypted email messages, the disclaimer text, and the logo that you want to use for the email message and the encryption portal. For details, see [Add branding to encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
 <span data-ttu-id="1333e-238">**问：该服务是否要求我的组织中的每个用户都有许可证？**</span><span class="sxs-lookup"><span data-stu-id="1333e-238">**Q. Does the service require a license for every user in my organization?**</span></span>
  
<span data-ttu-id="1333e-239">组织中发送加密电子邮件的每个用户都必须有许可证。</span><span class="sxs-lookup"><span data-stu-id="1333e-239">A license is required for every user in the organization who sends encrypted email.</span></span>
  
 <span data-ttu-id="1333e-240">**问：外部收件人是否需要订阅？**</span><span class="sxs-lookup"><span data-stu-id="1333e-240">**Q. Do external recipients require subscriptions?**</span></span>
  
<span data-ttu-id="1333e-241">否，外部收件人不需要订阅即可阅读或回复加密邮件。</span><span class="sxs-lookup"><span data-stu-id="1333e-241">No, external recipients do not require a subscription to read or reply to encrypted messages.</span></span> 
  
 <span data-ttu-id="1333e-242">**问: Office 365 邮件加密与 Rights Management Services (RMS) 有何不同？**</span><span class="sxs-lookup"><span data-stu-id="1333e-242">**Q. How is Office 365 Message Encryption different from Rights Management Services (RMS)?**</span></span>
  
<span data-ttu-id="1333e-p118">RMS 通过提供内置模板 (例如: 不要转发和公司机密) 为组织的内部电子邮件提供信息权限保护功能。Office 365 邮件加密支持对发送给外部收件人和内部收件人的邮件进行电子邮件加密。</span><span class="sxs-lookup"><span data-stu-id="1333e-p118">RMS provides Information Rights Protection capabilities for an organization's internal emails by providing built-in templates, such as: Do not forward and Company Confidential. Office 365 Message Encryption supports email message encryption for messages that are sent to external recipients as well as internal recipients.</span></span>
  
 <span data-ttu-id="1333e-245">**问: Office 365 邮件加密与 S/MIME 有何不同？**</span><span class="sxs-lookup"><span data-stu-id="1333e-245">**Q. How is Office 365 Message Encryption different from S/MIME?**</span></span>
  
<span data-ttu-id="1333e-p119">S/MIME 实质上是一种客户端加密技术, 需要复杂的证书管理和发布基础结构。Office 365 邮件加密使用邮件流规则 (也称为传输规则), 而不依赖于证书发布。</span><span class="sxs-lookup"><span data-stu-id="1333e-p119">S/MIME is essentially a client-side encryption technology, and requires complicated certificate management and publishing infrastructure. Office 365 Message Encryption uses mail flow rules (also known as transport rules) and does not depend on certificate publishing.</span></span>
  
 <span data-ttu-id="1333e-248">**问：能否通过移动设备阅读加密邮件？**</span><span class="sxs-lookup"><span data-stu-id="1333e-248">**Q. Can I read the encrypted messages over mobile devices?**</span></span>
  
<span data-ttu-id="1333e-p120">可以, 通过从[Google Play 商店](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409)和[Apple App store](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409)下载 OME 查看器应用程序, 可以查看 Android 和 iOS 上的邮件。在 OME 查看器应用程序中打开 HTML 附件, 然后按照说明打开加密邮件。对于其他移动设备, 只要您的邮件客户端支持表单发布, 就可以打开 HTML 附件。</span><span class="sxs-lookup"><span data-stu-id="1333e-p120">Yes, you can view messages on Android and iOS by downloading the OME Viewer apps from the [Google Play store](http://go.microsoft.com/fwlink/?LinkID=525995&amp;clcid=0x409) and the [Apple App store](http://go.microsoft.com/fwlink/?LinkID=525996&amp;clcid=0x409). Open the HTML attachment in the OME Viewer app and then follow the instructions to open your encrypted message. For other mobile devices, you can open the HTML attachment as long as your mail client supports Form Post.</span></span>
  
 <span data-ttu-id="1333e-252">**问：是否对回复和转发的邮件进行加密？**</span><span class="sxs-lookup"><span data-stu-id="1333e-252">**Q. Are replies and forwarded messages encrypted?**</span></span>
  
<span data-ttu-id="1333e-p121">是，在整个线程期限内，响应都会继续进行加密。</span><span class="sxs-lookup"><span data-stu-id="1333e-p121">Yes. Responses continue to be encrypted throughout the duration of the thread.</span></span>
  
 <span data-ttu-id="1333e-255">**问：Office 365 邮件加密是否提供本地化？**</span><span class="sxs-lookup"><span data-stu-id="1333e-255">**Q. Does Office 365 Message Encryption provide localization?**</span></span>
  
<span data-ttu-id="1333e-p122">传入电子邮件和 HTML 内容会进行本地化，具体取决于发件人电子邮件设置。查看门户根据收件人的浏览器设置进行本地化。不过，加密邮件的实际正文（内容）不会进行本地化。</span><span class="sxs-lookup"><span data-stu-id="1333e-p122">Incoming email and HTML content is localized based on sender email settings. The viewing portal is localized based on recipient's browser settings. However, the actual body (content) of encrypted message isn't localized.</span></span>
  
 <span data-ttu-id="1333e-259">**问：Office 365 邮件加密使用哪种加密方法？**</span><span class="sxs-lookup"><span data-stu-id="1333e-259">**Q. What encryption method is used for Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="1333e-p123">Office 365 邮件加密使用权限管理服务 (RMS) 作为其加密基础结构。所使用的加密方法取决于从何处获取用来加密和解密邮件的 RMS 密钥。</span><span class="sxs-lookup"><span data-stu-id="1333e-p123">Office 365 Message Encryption uses Rights Management Services (RMS) as its encryption infrastructure. The encryption method used depends on where you obtain the RMS keys used to encrypt and decrypt messages.</span></span>
  
- <span data-ttu-id="1333e-p124">如果使用 Microsoft Azure RMS 获取密钥, 则使用加密模式2。加密模式2是更新并增强的 AD RMS 加密实现。它支持针对签名和加密的 RSA 2048, 并支持用于签名的 SHA-256。</span><span class="sxs-lookup"><span data-stu-id="1333e-p124">If you use Microsoft Azure RMS to obtain the keys, Cryptographic Mode 2 is used. Cryptographic Mode 2 is an updated and enhanced AD RMS cryptographic implementation. It supports RSA 2048 for signature and encryption, and supports SHA-256 for signature.</span></span>
    
- <span data-ttu-id="1333e-p125">如果您使用 Active Directory (AD) RMS 获取这些密钥，则可以使用加密模式 1，也可以使用加密模式 2。使用的方法取决于您的本地 AD RMS 部署。加密模式 1 是原始的 AD RMS 加密实现。它支持 RSA 1024 签名和加密，并支持 sha-1 签名。该模式继续支持 RMS 的所有当前版本。</span><span class="sxs-lookup"><span data-stu-id="1333e-p125">If you use Active Directory (AD) RMS to obtain the keys, either Cryptographic Mode 1 or Cryptographic Mode 2 is used. The method used depends on your on-premises AD RMS deployment. Cryptographic Mode 1 is the original AD RMS cryptographic implementation. It supports RSA 1024 for signature and encryption, and supports SHA-1 for signature. This mode continues to be supported by all current versions of RMS.</span></span>
    
<span data-ttu-id="1333e-270">有关详细信息, 请参阅[AD RMS 加密模式](http://go.microsoft.com/fwlink/p/?LinkId=398616)。</span><span class="sxs-lookup"><span data-stu-id="1333e-270">For more information, see [AD RMS Cryptographic Modes](http://go.microsoft.com/fwlink/p/?LinkId=398616).</span></span>
  
 <span data-ttu-id="1333e-271">**问：为什么一些加密邮件显示其来自 Office365@messaging.microsoft.com？**</span><span class="sxs-lookup"><span data-stu-id="1333e-271">**Q. Why do some encrypted messages say they come from Office365@messaging.microsoft.com?**</span></span>
  
<span data-ttu-id="1333e-p126">当加密回复从加密门户或通过 OME 查看器应用发送时，发送电子邮件地址将设为 Office365@messaging.microsoft.com，因为该加密邮件是通过 Microsoft 终结点发送的。这有助于防止加密邮件被标记为垃圾邮件。电子邮件上显示的名称和加密门户内的地址不会因为这个标签而更改。此外，该标签仅适用于通过门户而不是通过任何其他电子邮件客户端发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="1333e-p126">When an encrypted reply is sent from the encryption portal or through the OME Viewer app, the sending email address is set to Office365@messaging.microsoft.com because the encrypted message is sent through a Microsoft endpoint. This helps to prevent encrypted messages from being marked as spam. The displayed name on the email and the address within the encryption portal aren't changed because of this labeling. Also, this labeling only applies to messages sent through the portal, not through any other email client.</span></span>
  
 <span data-ttu-id="1333e-276">**问: 我是 Exchange 托管加密 (EHE) 订阅者。在哪里可以了解有关升级到 Office 365 邮件加密的更多信息？**</span><span class="sxs-lookup"><span data-stu-id="1333e-276">**Q. I am an Exchange Hosted Encryption (EHE) subscriber. Where can I learn more about the upgrade to Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="1333e-p127">所有 EHE 客户都已升级到 Office 365 邮件加密。有关详细信息, 请访问[Exchange 托管加密升级中心](http://go.microsoft.com/fwlink/p/?LinkID=511077)。</span><span class="sxs-lookup"><span data-stu-id="1333e-p127">All EHE customers have been upgraded to Office 365 Message Encryption. For more information, visit the [Exchange Hosted Encryption Upgrade Center](http://go.microsoft.com/fwlink/p/?LinkID=511077).</span></span>
  
 <span data-ttu-id="1333e-279">**问: 我是否需要在组织的防火墙中打开任何 url、IP 地址或端口以支持 Office 365 邮件加密？**</span><span class="sxs-lookup"><span data-stu-id="1333e-279">**Q. Do I need to open any URLs, IP addresses, or ports in my organization's firewall to support Office 365 Message Encryption?**</span></span>
  
<span data-ttu-id="1333e-p128">是。您必须将 Exchange Online 的 URL 添加到组织的允许列表，对通过 Office 365 邮件加密进行加密的邮件启用身份验证。有关 Exchange Online URL 的列表，请参阅 [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1333e-p128">Yes. You have to add URLs for Exchange Online to the allow list for your organization to enable authentication for messages encrypted by Office 365 Message Encryption. For a list of Exchange Online URLs, see [Office 365 URLs and IP Address Ranges](https://support.office.com/article/f57e35b7-0a45-42f0-855e-11aa5e7f13fd.aspx).</span></span>
  
 <span data-ttu-id="1333e-283">**问：我可以向多少个收件人发送 Office 365 加密邮件？**</span><span class="sxs-lookup"><span data-stu-id="1333e-283">**Q. How many recipients can I send an Office 365 encrypted message to?**</span></span>
  
<span data-ttu-id="1333e-p129">加密邮件的收件人限制基于邮件的 "收件人" 字段中的字符数。 \*\*\*\* 组合后 (在通讯组列表展开后), "收件人\*\*\*\* " 字段中的收件人地址不应超过11980个字符。由于电子邮件地址可能因字符长度而异, 因此单个加密邮件没有标准收件人限制。</span><span class="sxs-lookup"><span data-stu-id="1333e-p129">The recipient limit for an encrypted message is based on the number of characters in the message's **To** field. When combined (after distribution list expansion), recipient addresses in the **To** field should not exceed 11,980 characters. Because email addresses can vary in character length, there isn't a standard recipient limit for a single encrypted message.</span></span> 
  
 <span data-ttu-id="1333e-287">**问：是否可以取消发送给特定收件人的邮件？**</span><span class="sxs-lookup"><span data-stu-id="1333e-287">**Q. Is it possible to revoke a message sent to a particular recipient?**</span></span>
  
<span data-ttu-id="1333e-p130">不。发送邮件后, 不能向该用户撤销邮件。</span><span class="sxs-lookup"><span data-stu-id="1333e-p130">No. You can't revoke a message to a particular person after it's sent.</span></span>
  
 <span data-ttu-id="1333e-290">**问：是否可以查看已接收和阅读的加密邮件报告吗？**</span><span class="sxs-lookup"><span data-stu-id="1333e-290">**Q. Can I view a report of encrypted messages that have been received and read?**</span></span>
  
<span data-ttu-id="1333e-291">没有显示已查看加密邮件的报告, 但有 Office 365 报告可用, 可以利用这些报告来确定匹配特定邮件流规则 (也称为传输规则) 的邮件数 (例如,)。</span><span class="sxs-lookup"><span data-stu-id="1333e-291">There isn't a report that shows if an encrypted message has been viewed, but there are Office 365 reports available that you can leverage to determine the number of messages that matched a specific mail flow rule (also known as a transport rule), for instance.</span></span>
  
 <span data-ttu-id="1333e-292">**问：Microsoft 会如何处理我通过 OME 门户和 OME 查看器应用提供的信息？**</span><span class="sxs-lookup"><span data-stu-id="1333e-292">**Q. What does Microsoft do with the information I provide through the OME Portal and the OME Viewer App?**</span></span>
  
<span data-ttu-id="1333e-293">[Office 365 邮件加密门户隐私声明](protected-message-viewer-portal-privacy-statement.md)提供了有关 Microsoft 在你的私人信息方面所做的操作和不会执行的操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1333e-293">The [Office 365 Messaging Encryption Portal privacy statement](protected-message-viewer-portal-privacy-statement.md) provides detailed information about what Microsoft does and doesn't do with your private information.</span></span> 
  

