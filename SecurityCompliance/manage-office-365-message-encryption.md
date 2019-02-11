---
title: 管理 Office 365 邮件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
description: 在完成设置 up Office 365 邮件加密 (OME) 后，可以自定义多种方法中的部署的配置。例如，您可以配置是否启用一次性密码、 在 web 应用程序和更多的 Outlook 中显示保护按钮。本文中的任务说明如何。
ms.openlocfilehash: 6a9eddae2d3d166d96979d88b15845c3b7379bd9
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696226"
---
# <a name="manage-office-365-message-encryption"></a><span data-ttu-id="b0254-105">管理 Office 365 邮件加密</span><span class="sxs-lookup"><span data-stu-id="b0254-105">Manage Office 365 Message Encryption</span></span>

<span data-ttu-id="b0254-p102">在完成设置 up Office 365 邮件加密 (OME) 后，可以自定义多种方法中的部署的配置。例如，您可以配置是否启用一次性密码、 在 web 应用程序和更多的 Outlook 中显示**保护**按钮。本文中的任务说明如何。</span><span class="sxs-lookup"><span data-stu-id="b0254-p102">Once you've finished setting up Office 365 Message Encryption (OME), you can customize the configuration of your deployment in a number of ways. For example, you can configure whether to enable one-time pass codes, display the **Protect** button in Outlook on the web, and more. The tasks in this article describe how.</span></span>
  
||
|:-----|
|<span data-ttu-id="b0254-p103">本文是系列的有关 Office 365 邮件加密的文章的较大一部分。本文旨在为管理员和 ITPros。如果您只查找有关的信息发送或接收加密的邮件， [Office 365 邮件加密 (OME)](ome.md)中的文章的列表，请参阅并找到最适合您的需求的文章。</span><span class="sxs-lookup"><span data-stu-id="b0254-p103">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||

## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="b0254-112">管理是否 Google、 Yahoo 和 Microsoft 帐户收件人可以使用这些帐户登录到 Office 365 邮件加密门户</span><span class="sxs-lookup"><span data-stu-id="b0254-112">Managing whether Google, Yahoo, and Microsoft Account recipients can use these accounts to sign in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="b0254-p104">默认情况下时设置的新的 Office 365 邮件加密功能，您的组织中的用户可以发送邮件到 Office 365 组织外部的收件人。如果收件人使用*社交 ID*如 Google 帐户、 Yahoo 帐户或 Microsoft 帐户，收件人可以登录到 OME 门户使用社交 id。如果您希望，您可以选择不允许使用社交 Id 登录到 OME 门户的收件人。</span><span class="sxs-lookup"><span data-stu-id="b0254-p104">By default, when you set up the new Office 365 Message Encryption capabilities, users in your organization can send messages to recipients that are outside of your Office 365 organization. If the recipient uses a *social ID* such as a Google account, Yahoo account, or Microsoft account, the recipient can sign in to the OME portal using the social ID. If you want, you can choose not to allow recipients to use social IDs to sign in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-to-allow-recipients-to-use-social-ids-to-sign-in-to-the-ome-portal"></a><span data-ttu-id="b0254-116">若要管理允许收件人社交 Id 用于登录到 OME 门户</span><span class="sxs-lookup"><span data-stu-id="b0254-116">To manage whether or not to allow recipients to use social IDs to sign in to the OME portal</span></span>
  
1. <span data-ttu-id="b0254-117">[连接到 Exchange Online 使用远程 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b0254-117">[Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="b0254-118">如下所示使用 SocialIdSignIn 参数运行 Set-omeconfiguration cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b0254-118">Run the Set-OMEConfiguration cmdlet with the SocialIdSignIn parameter as follows:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true | $false>
   ```

   <span data-ttu-id="b0254-119">例如，若要禁用社交 Id:</span><span class="sxs-lookup"><span data-stu-id="b0254-119">For example, to disable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   <span data-ttu-id="b0254-120">启用社交 Id:</span><span class="sxs-lookup"><span data-stu-id="b0254-120">To enable social IDs:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a><span data-ttu-id="b0254-121">管理使用一次性密码登录到 Office 365 邮件加密门户</span><span class="sxs-lookup"><span data-stu-id="b0254-121">Managing the use of one-time pass codes for signing in to the Office 365 Message Encryption portal</span></span>

<span data-ttu-id="b0254-p105">默认情况下，如果按 OME 加密邮件的收件人不使用 Outlook 中，无论收件人，使用的帐户收件人将接收允许阅读邮件的时间有限 web 视图链接。这包括一次性密码。作为管理员，您可以管理可一次性密码以登录到 OME 门户。</span><span class="sxs-lookup"><span data-stu-id="b0254-p105">By default, if the recipient of a message encrypted by OME doesn't use Outlook, regardless of the account used by the recipient, the recipient receives a limited-time web-view link that lets them read the message. This includes a one-time pass code. As an administrator, you can manage whether or not one-time pass codes can be used to sign-in to the OME portal.</span></span>
  
### <a name="to-manage-whether-or-not-one-time-pass-codes-are-generated-for-ome"></a><span data-ttu-id="b0254-125">若要管理为 OME 生成一次性密码</span><span class="sxs-lookup"><span data-stu-id="b0254-125">To manage whether or not one-time pass codes are generated for OME</span></span>
  
1. <span data-ttu-id="b0254-p106">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，请启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明，请参阅[Connect to Exchange Online PowerShell 中](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="b0254-p106">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b0254-128">使用 OTPEnabled 参数运行 Set-omeconfiguration cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b0254-128">Run the Set-OMEConfiguration cmdlet with the OTPEnabled parameter:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   <span data-ttu-id="b0254-129">例如，若要禁用一次性密码：</span><span class="sxs-lookup"><span data-stu-id="b0254-129">For example, to disable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   <span data-ttu-id="b0254-130">若要启用一次性密码：</span><span class="sxs-lookup"><span data-stu-id="b0254-130">To enable one-time pass codes:</span></span>

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a><span data-ttu-id="b0254-131">管理保护按钮在 web 上的 Outlook 中的显示</span><span class="sxs-lookup"><span data-stu-id="b0254-131">Managing the display of the Protect button in Outlook on the web</span></span>

<span data-ttu-id="b0254-p107">默认情况下在 web 上的 Outlook**保护**按钮时，不启用设置 OME。作为管理员，您可以管理为最终用户显示此按钮。</span><span class="sxs-lookup"><span data-stu-id="b0254-p107">By default, the **Protect** button in Outlook on the web is not enabled when you set up OME. As an administrator, you can manage whether or not to display this button to end users.</span></span>
  
### <a name="to-manage-whether-or-not-the-protect-button-appears-in-outlook-on-the-web"></a><span data-ttu-id="b0254-134">若要管理保护按钮显示在 web 上的 Outlook</span><span class="sxs-lookup"><span data-stu-id="b0254-134">To manage whether or not the Protect button appears in Outlook on the web</span></span>
  
1. <span data-ttu-id="b0254-p108">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，请启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明，请参阅[Connect to Exchange Online PowerShell 中](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="b0254-p108">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b0254-137">运行带有-SimplifiedClientAccessEnabled 参数 Set-irmconfiguration cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b0254-137">Run the Set-IRMConfiguration cmdlet with the -SimplifiedClientAccessEnabled parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   <span data-ttu-id="b0254-138">例如，若要禁用**保护**按钮：</span><span class="sxs-lookup"><span data-stu-id="b0254-138">For example, to disable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   <span data-ttu-id="b0254-139">若要启用**保护**按钮：</span><span class="sxs-lookup"><span data-stu-id="b0254-139">To enable the **Protect** button:</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a><span data-ttu-id="b0254-140">启用 iOS 邮件应用程序用户的电子邮件的服务商解密</span><span class="sxs-lookup"><span data-stu-id="b0254-140">Enable service-side decryption of email messages for iOS mail app users</span></span>

<span data-ttu-id="b0254-p109">IOS 邮件应用程序无法解密术 シ モ メ Office 365 邮件加密的邮件。作为 Office 365 管理员，您可以应用邮件传递到 iOS 邮件应用程序的服务商解密。当您选择这样做时，服务会将解密邮件的副本发送到 iOS 设备。消息存储解密客户端设备上。邮件还保留有关使用权限的信息，即使 iOS 邮件应用程序不适用于向用户的客户端使用权限。这意味着用户可复制或打印邮件，即使他们最初没有这样的权限。但是，如果用户尝试完成操作所需的 Office 365 邮件服务器，如转发邮件，服务器将不允许操作如果用户最初没有这样的使用权限。但是，最终用户可以通过从无论您是否设置邮件的服务商解密其 iOS 邮件应用程序中的不同帐户转发邮件变通解决不要转发使用率限制，任何附件加密和权限受保护的邮件无法查看 iOS 邮件应用程序中。</span><span class="sxs-lookup"><span data-stu-id="b0254-p109">The iOS mail app can't decrypt messages protected with Office 365 Message Encryption. As an Office 365 administrator, you can apply service-side decryption for messages delivered to the iOS mail app. When you choose to do this, the service sends a decrypted copy of the message to the iOS device. The message is stored decrypted on the client device. The message also retains information about usage rights even though the iOS mail app doesn't apply client-side usage rights to the user. This means that the user can copy or print the message even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the message, the server will not permit the action if the user did not originally have the usage right to do so. However, end-users can work around Do Not Forward usage restriction by forwarding the message from a different account in their iOS mail app. Regardless of whether you set up service-side decryption of mail, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="b0254-p110">如果您选择不允许将解密的邮件发送到 iOS 邮件应用程序用户，用户会收到一条消息，它们没有查看邮件的权限。默认情况下，未启用电子邮件的服务商解密。</span><span class="sxs-lookup"><span data-stu-id="b0254-p110">If you choose not to allow decrypted messages to be sent to iOS mail app users, users receive a message that states that they don't have the rights to view the message. By default, service-side decryption of email messages is not enabled.</span></span>
  
<span data-ttu-id="b0254-152">有关详细信息，以及客户端体验的视图，请参阅[查看加密邮件 iPhone 或 iPad 上](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)。</span><span class="sxs-lookup"><span data-stu-id="b0254-152">For more information, and for a view of the client experience, see [View encrypted messages on your iPhone or iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf).</span></span>
  
### <a name="to-manage-whether-or-not-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a><span data-ttu-id="b0254-153">若要管理 iOS 邮件应用程序用户可以查看受 Office 365 邮件加密的邮件</span><span class="sxs-lookup"><span data-stu-id="b0254-153">To manage whether or not iOS mail app users can view messages protected by Office 365 Message Encryption</span></span>
  
1. <span data-ttu-id="b0254-p111">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，请启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明，请参阅[Connect to Exchange Online PowerShell 中](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="b0254-p111">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b0254-156">运行带有 AllowRMSSupportForUnenlightenedApps 参数集 ActiveSyncOrganizations cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b0254-156">Run the Set-ActiveSyncOrganizations cmdlet with the AllowRMSSupportForUnenlightenedApps parameter:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   <span data-ttu-id="b0254-157">例如，若要配置服务以解密邮件发送到 unenlightened 应用程序之前如 iOS 邮件应用程序：</span><span class="sxs-lookup"><span data-stu-id="b0254-157">For example, to configure the service to decrypt messages before they are sent to unenlightened apps such as the iOS mail app:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   <span data-ttu-id="b0254-158">或者，若要配置服务无法将解密的邮件发送到 unenlightened 应用程序：</span><span class="sxs-lookup"><span data-stu-id="b0254-158">Or, to configure the service not to send decrypted messages to unenlightened apps:</span></span>

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a><span data-ttu-id="b0254-159">启用 web 浏览器邮件客户端的电子邮件附件的服务商解密</span><span class="sxs-lookup"><span data-stu-id="b0254-159">Enable service-side decryption of email attachments for web browser mail clients</span></span>

<span data-ttu-id="b0254-p112">通常，当您使用 Office 365 邮件加密，附件进行自动加密。作为 Office 365 管理员，您可以应用用户从 web 浏览器下载的电子邮件附件的服务商的解密。</span><span class="sxs-lookup"><span data-stu-id="b0254-p112">Normally, when you use Office 365 message encryption, attachments are automatically encrypted. As an Office 365 administrator, you can apply service-side decryption for email attachments that users download from a web browser.</span></span>
  
<span data-ttu-id="b0254-p113">当您选择这样做时，该服务向设备发送解密文件的副本。仍加密消息。电子邮件附件还保留有关使用权限的信息，即使在浏览器不适用于向用户的客户端使用权限。这意味着用户可复制或打印电子邮件附件，即使他们最初没有这样的权限。但是，如果用户尝试完成操作所需的 Office 365 邮件服务器，如转发附件，服务器将不允许操作如果用户最初没有这样的使用权限。</span><span class="sxs-lookup"><span data-stu-id="b0254-p113">When you choose to do this, the service sends a decrypted copy of the file to the device. The message is still encrypted. The email attachment also retains information about usage rights even though the browser does not apply client-side usage rights to the user. This means that the user can copy or print the email attachment even if they did not originally have the rights to do so. However, if the user attempts to complete an action that requires the Office 365 mail server, such as forwarding the attachment, the server will not permit the action if the user did not originally have the usage right to do so.</span></span>
  
<span data-ttu-id="b0254-167">无论您是否设置的附件的服务商解密，任何附件加密并不能在 iOS 邮件应用程序中查看权限受保护的邮件。</span><span class="sxs-lookup"><span data-stu-id="b0254-167">Regardless of whether you set up service-side decryption of attachments, any attachments to encrypted and rights protected mail cannot be viewed in the iOS mail app.</span></span>
  
<span data-ttu-id="b0254-168">如果您选择不允许解密电子邮件附件，这是默认值，则用户将收到一条消息，它们没有要查看附件的权限。</span><span class="sxs-lookup"><span data-stu-id="b0254-168">If you choose not to allow decrypted email attachments, which is the default, users receive a message that states that they don't have the rights to view the attachment.</span></span>
  
<span data-ttu-id="b0254-169">有关 Office 365 如何实现加密电子邮件和电子邮件附件的仅进行加密选项的详细信息，请参阅[的电子邮件仅加密选项。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="b0254-169">For more information about how Office 365 implements encryption for emails and email attachments with the Encrypt-Only option, see [Encrypt-Only option for emails.](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span></span>
  
### <a name="to-manage-whether-or-not-email-attachments-are-decrypted-on-download-from-a-web-browser"></a><span data-ttu-id="b0254-170">若要管理电子邮件附件将解密在从 web 浏览器的下载</span><span class="sxs-lookup"><span data-stu-id="b0254-170">To manage whether or not email attachments are decrypted on download from a web browser</span></span>
  
1. <span data-ttu-id="b0254-p114">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，请启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明，请参阅[Connect to Exchange Online PowerShell 中](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="b0254-p114">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b0254-173">使用 DecryptAttachmentFromPortal 参数运行 Set-irmconfiguration cmdlet:</span><span class="sxs-lookup"><span data-stu-id="b0254-173">Run the Set-IRMConfiguration cmdlet with the DecryptAttachmentFromPortal parameter:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   <span data-ttu-id="b0254-174">例如，若要配置服务以解密电子邮件附件时用户下载这些从 web 浏览器：</span><span class="sxs-lookup"><span data-stu-id="b0254-174">For example, to configure the service to decrypt email attachments when a user downloads them from a web browser:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   <span data-ttu-id="b0254-175">配置要将加密的电子邮件附件保留在下载时原样的服务：</span><span class="sxs-lookup"><span data-stu-id="b0254-175">To configure the service to leave encrypted email attachments as they are upon download:</span></span>

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a><span data-ttu-id="b0254-176">自定义电子邮件和 OME 门户网站的外观</span><span class="sxs-lookup"><span data-stu-id="b0254-176">Customizing the appearance of email messages and the OME portal</span></span>

<span data-ttu-id="b0254-177">有关如何为组织自定义 OME 的详细信息，请参阅[添加到加密邮件的组织品牌](add-your-organization-brand-to-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="b0254-177">For detailed information about how you can customize OME for your organization, see [Add your organization's brand to your encrypted messages](add-your-organization-brand-to-encrypted-messages.md).</span></span>
  
## <a name="disabling-the-new-capabilities-for-ome"></a><span data-ttu-id="b0254-178">禁用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="b0254-178">Disabling the new capabilities for OME</span></span>

<span data-ttu-id="b0254-p115">我们希望它不前置，但如果需要禁用的新功能，用于 OME 非常简单。首先，您将需要删除任何邮件流规则已创建，使用新的 OME 功能。有关删除邮件流规则的信息，请参阅[管理邮件流规则](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)。然后，完成以下步骤在 Exchange Online PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b0254-p115">We hope it doesn't come to it, but if you need to, disabling the new capabilities for OME is very straightforward. First, you'll need to remove any mail flow rules you've created that use the new OME capabilities. For information about removing mail flow rules, see [Manage mail flow rules](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx). Then, complete these steps in Exchange Online PowerShell.</span></span>
  
### <a name="to-disable-the-new-capabilities-for-ome"></a><span data-ttu-id="b0254-183">禁用 OME 的新功能</span><span class="sxs-lookup"><span data-stu-id="b0254-183">To disable the new capabilities for OME</span></span>
  
1. <span data-ttu-id="b0254-p116">使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，请启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明，请参阅[Connect to Exchange Online PowerShell 中](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="b0254-p116">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online. For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b0254-p117">如果启用在 web 上的 Outlook 中的**保护**按钮，请通过运行带有 SimplifiedClientAccessEnabled 参数 Set-irmconfiguration cmdlet 禁用它。否则，跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="b0254-p117">If you enabled the **Protect** button in Outlook on the web, disable it by running the Set-IRMConfiguration cmdlet with the SimplifiedClientAccessEnabled parameter. Otherwise, skip this step.</span></span>

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. <span data-ttu-id="b0254-188">通过运行带有 AzureRMSLicensingEnabled 参数设置为 false 的 Set-irmconfiguration cmdlet 禁用 OME 的新功能：</span><span class="sxs-lookup"><span data-stu-id="b0254-188">Disable the new capabilities for OME by running the Set-IRMConfiguration cmdlet with the AzureRMSLicensingEnabled parameter set to false:</span></span>

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
