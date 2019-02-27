---
title: 管理 Office 365 邮件加密
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- M365-security-compliance
description: 完成设置 Office 365 邮件加密 (OME) 后, 可以通过多种方式自定义部署的配置。例如, 您可以配置是否启用一次性传递代码, 在 Outlook 网页版中显示 "保护" 按钮, 等等。本文中的任务介绍了如何。
ms.openlocfilehash: 7b5297ae42d3efa071408540863c6ff7dbdee407
ms.sourcegitcommit: 686bc9a8f7a7b6810a096f07d36751d10d334409
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "30275972"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="23c5a-105">管理 Office 365 邮件加密</span><span class="sxs-lookup"><span data-stu-id="23c5a-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="23c5a-p102">完成设置 Office 365 邮件加密 (OME) 后, 可以通过多种方式自定义部署的配置。例如, 您可以配置是否启用一次性传递代码, 在 Outlook 网页版中显示 "**保护**" 按钮, 等等。本文中的任务介绍了如何。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p102">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in a number of ways. For example, you can configure whether to enable one-time pass codes, display the **Protect** button in Outlook on the web, and more. The tasks in this article describe how.</span></span>
  
||
|:-----|
|<span data-ttu-id="23c5a-p103">本文是有关 Office 365 邮件加密的更多系列文章的一部分。本文适用于管理员和 ITPros。如果只是查找有关发送或接收加密邮件的信息, 请参阅[Office 365 邮件加密 (OME)](ome.md)中的文章列表, 并找到最符合您的需求的文章。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="23c5a-112">管理 Google、Yahoo 和 Microsoft 帐户收件人是否可以使用这些帐户登录 Office 365 邮件加密门户</span><span class="sxs-lookup"><span data-stu-id="23c5a-112">Managing whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="23c5a-p104">默认情况下, 当您设置新的 Office 365 邮件加密功能时, 组织中的用户可以向位于您的 office 365 组织外部的收件人发送邮件。如果收件人使用的是 Google 帐户、Yahoo 帐户或 Microsoft 帐户等*社会 id* , 则收件人可以使用社会 id 登录到 OME 门户。如果需要, 您可以选择不允许收件人使用社交 id 登录到 OME 门户。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p104">By default, when you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization. If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal using the social ID. If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-to-allow-recipients-to-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="23c5a-116">管理是否允许收件人使用社交 id 登录到 OME 门户</span><span class="sxs-lookup"><span data-stu-id="23c5a-116">To manage whether or not to allow recipients to use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="23c5a-117">[使用远程 PowerShell 连接到 Exchange Online](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="23c5a-117">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="23c5a-118">使用 SocialIdSignIn 参数运行 set-omeconfiguration cmdlet, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="23c5a-118">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true | $false>
   ```

   <span data-ttu-id="23c5a-119">例如, 若要禁用社会 id, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="23c5a-119">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="23c5a-120">若要启用社交 id, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="23c5a-120">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="23c5a-121">管理用于登录 Office 365 邮件加密门户的一次性 pass 代码的使用</span><span class="sxs-lookup"><span data-stu-id="23c5a-121">Managing the use of one-time pass codes for signing in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="23c5a-p105">默认情况下, 如果由 OME 加密的邮件的收件人不使用 Outlook, 而不管收件人使用的帐户如何, 收件人都会收到一个限制的 web 查看链接, 让他们能够阅读邮件。这包括一次性的 pass 代码。作为管理员, 您可以管理一次性的 pass 代码是否可用于登录到 OME 门户。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p105">By default, if the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message. This includes a one-time pass code. As an administrator, you can manage whether or not one-time pass codes can be used to sign-in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-one-time-pass-codes-are-generated-for-ome"></a><span data-ttu-id="23c5a-125">管理是否为 OME 生成一次性传递代码</span><span class="sxs-lookup"><span data-stu-id="23c5a-125">To manage whether or not one-time pass codes are generated for OME</span></span>
  
1. <span data-ttu-id="23c5a-p106">在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="23c5a-128">使用 OTPEnabled 参数运行 set-omeconfiguration cmdlet:</span><span class="sxs-lookup"><span data-stu-id="23c5a-128">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="23c5a-129">例如, 若要禁用一次性传递代码, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="23c5a-129">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="23c5a-130">若要启用一次性传递代码, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="23c5a-130">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a><span data-ttu-id="23c5a-131">管理 web 上的 Outlook 中的 "保护" 按钮的显示</span><span class="sxs-lookup"><span data-stu-id="23c5a-131">Managing the display of the Protect button in Outlook on the web</span></span>

<span data-ttu-id="23c5a-p107">默认情况下, 在设置 OME 时, 不会启用 web 上的 Outlook 中的 "**保护**" 按钮。作为管理员, 您可以管理是否将此按钮显示给最终用户。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p107">By default, the **Protect** button in Outlook on the web is not enabled when you set up OME. As an administrator, you can manage whether or not to display this button to end users.</span></span>
  
### <a name="to-manage-whether-or-not-the-protect-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="23c5a-134">管理 "保护" 按钮在 web 上的 Outlook 中是否显示</span><span class="sxs-lookup"><span data-stu-id="23c5a-134">To manage whether or not the Protect button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="23c5a-p108">在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p108">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="23c5a-137">运行带-SimplifiedClientAccessEnabled 参数的 get-irmconfiguration cmdlet:</span><span class="sxs-lookup"><span data-stu-id="23c5a-137">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="23c5a-138">例如, 要禁用 "**保护**" 按钮, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="23c5a-138">For example, to disable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="23c5a-139">启用 "**保护**" 按钮的步骤:</span><span class="sxs-lookup"><span data-stu-id="23c5a-139">To enable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="23c5a-140">为 iOS 邮件应用程序用户启用电子邮件的服务端解密</span><span class="sxs-lookup"><span data-stu-id="23c5a-140">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="23c5a-p109">iOS 邮件应用程序无法解密受 Office 365 邮件加密保护的邮件。作为 Office 365 管理员, 您可以对传递到 iOS 邮件应用程序的邮件应用服务端解密。如果选择执行此操作, 则服务会将解密的邮件副本发送到 iOS 设备。在客户端设备上将邮件存储为已解密。即使 iOS 邮件应用程序不会对用户应用客户端使用权限, 该邮件也会保留有关使用权限的信息。这意味着用户可以复制或打印邮件, 即使他们最初并不具有执行此操作的权限也是如此。但是, 如果用户尝试完成需要 Office 365 邮件服务器的操作 (如转发邮件), 则如果用户最初未使用此功能, 则服务器将不允许执行此操作。但是, 最终用户可以通过将邮件从其 iOS 邮件应用程序中的不同帐户转发邮件, 来解决不转发使用限制的情况。不管您是否设置了邮件的服务端解密、加密的和受权限保护的邮件的任何附件无法在 iOS 邮件应用中查看。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p109">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption. As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app. When you choose to do this, the service sends a decrypted copy of the message to the iOS device. The message is stored decrypted on the client device. The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user. This means that the user can copy or print the message even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server will not permit the action if the user did not originally have the usage right to do so. However, end-users can work around Do Not Forward usage restriction by forwarding the message from a different account in their iOS mail app. Regardless of whether you set up service-side decryption of mail, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="23c5a-p110">如果选择不允许向 iOS 邮件应用程序用户发送解密邮件, 则用户会收到一条消息, 指出他们没有查看邮件的权限。默认情况下, 不会启用电子邮件的服务端解密。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p110">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message. By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="23c5a-152">有关详细信息以及客户端体验的视图, 请参阅[在 iPhone 或 iPad 上查看加密的邮件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)。</span><span class="sxs-lookup"><span data-stu-id="23c5a-152">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-or-not-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="23c5a-153">管理 iOS 邮件应用程序用户是否可以查看受 Office 365 邮件加密保护的邮件</span><span class="sxs-lookup"><span data-stu-id="23c5a-153">To manage whether or not iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="23c5a-p111">在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p111">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="23c5a-156">使用 AllowRMSSupportForUnenlightenedApps 参数运行 ActiveSyncOrganizations cmdlet:</span><span class="sxs-lookup"><span data-stu-id="23c5a-156">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="23c5a-157">例如, 配置服务以在将邮件发送到 unenlightened 应用程序 (如 iOS 邮件应用程序) 之前对这些邮件进行解密:</span><span class="sxs-lookup"><span data-stu-id="23c5a-157">For example, to configure the service to decrypt messages before they are sent to unenlightened apps such as the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="23c5a-158">或者, 将该服务配置为不将解密的邮件发送到 unenlightened 应用程序:</span><span class="sxs-lookup"><span data-stu-id="23c5a-158">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="23c5a-159">启用 web 浏览器邮件客户端的电子邮件附件的服务端解密</span><span class="sxs-lookup"><span data-stu-id="23c5a-159">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="23c5a-p112">通常情况下, 当您使用 Office 365 邮件加密时, 附件会自动加密。作为 Office 365 管理员, 您可以对用户从 web 浏览器下载的电子邮件附件应用服务端解密。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p112">Normally, when you use Office 365 message encryption, attachments are automatically encrypted. As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="23c5a-p113">当您选择执行此操作时, 服务会将文件的解密副本发送到设备。邮件仍加密。即使浏览器不会对用户应用客户端使用权限, 电子邮件附件也会保留有关使用权限的信息。这意味着用户可以复制或打印电子邮件附件, 即使他们最初并不具有这样做的权限。但是, 如果用户尝试完成需要 Office 365 邮件服务器的操作 (如转发附件), 则如果用户最初未使用此功能, 则服务器将不允许执行此操作。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p113">When you choose to do this, the service sends a decrypted copy of the file to the device. The message is still encrypted. The email attachment also retains information about usage rights even though the browser does not apply client-side usage rights to the user. This means that the user can copy or print the email attachment even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server will not permit the action if the user did not originally have the usage right to do so.</span></span>
  
<span data-ttu-id="23c5a-167">无论您是否设置了附件的服务端解密, 在 iOS 邮件应用程序中都不能查看加密和受权限保护的邮件的任何附件。</span><span class="sxs-lookup"><span data-stu-id="23c5a-167">Regardless of whether you set up service-side decryption of attachments, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="23c5a-168">如果选择不允许解密的电子邮件附件 (默认情况下), 用户将收到一条消息, 指出他们没有查看附件的权限。</span><span class="sxs-lookup"><span data-stu-id="23c5a-168">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="23c5a-169">有关 Office 365 如何使用仅加密选项为电子邮件和电子邮件附件实现加密的详细信息, 请参阅[电子邮件的仅加密选项。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="23c5a-169">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-or-not-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="23c5a-170">管理在从 web 浏览器下载时是否解密电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="23c5a-170">To manage whether or not email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="23c5a-p114">在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p114">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="23c5a-173">使用 DecryptAttachmentFromPortal 参数运行 get-irmconfiguration cmdlet:</span><span class="sxs-lookup"><span data-stu-id="23c5a-173">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="23c5a-174">例如, 将服务配置为在用户从 web 浏览器下载电子邮件附件时对其进行解密:</span><span class="sxs-lookup"><span data-stu-id="23c5a-174">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="23c5a-175">将服务配置为在下载时保留加密的电子邮件附件:</span><span class="sxs-lookup"><span data-stu-id="23c5a-175">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="23c5a-176">自定义电子邮件的外观和 OME 门户</span><span class="sxs-lookup"><span data-stu-id="23c5a-176">Customizing the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="23c5a-177">有关如何为组织自定义 OME 的详细信息, 请参阅[将组织的品牌添加到加密邮件](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="23c5a-177">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disabling-the-new-capabilities-for-ome"></a><span data-ttu-id="23c5a-178">禁用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="23c5a-178">Disabling the new capabilities for OME</span></span>

<span data-ttu-id="23c5a-p115">我们希望它不会到达它, 但如果需要, 禁用 OME 的新功能非常简单。首先, 您需要删除您创建的任何使用新 OME 功能的邮件流规则。有关删除邮件流规则的信息, 请参阅[管理邮件流规则](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)。然后, 在 Exchange Online PowerShell 中完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p115">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward. First, you'll need to remove any mail flow rules you've created that use the new OME capabilities. For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="23c5a-183">禁用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="23c5a-183">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="23c5a-p116">在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p116">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="23c5a-p117">如果在 web 上的 Outlook 中启用了 "**保护**" 按钮, 请通过运行带有 SimplifiedClientAccessEnabled 参数的 get-irmconfiguration cmdlet 来禁用它。否则, 请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="23c5a-p117">If you enabled the **Protect** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter. Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="23c5a-188">通过运行 get-irmconfiguration cmdlet 并将 AzureRMSLicensingEnabled 参数设置为 false 来禁用 OME 的新功能:</span><span class="sxs-lookup"><span data-stu-id="23c5a-188">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
