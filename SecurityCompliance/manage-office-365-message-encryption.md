---
title: 管理 Office 365 邮件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 5/8/2019
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 完成设置 Office 365 邮件加密 (OME) 后, 您可以通过多种方式自定义部署的配置。 例如, 您可以配置是否启用一次性传递代码, 在 Outlook 网页版中显示 "保护" 按钮, 等等。 本文中的任务介绍了如何。
ms.openlocfilehash: 1afaaea3cd744878630598acd3f02dc7dc70e9cb
ms.sourcegitcommit: 865b3dc071150b20bf3967e1263fc54e75898284
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2019
ms.locfileid: "33834921"
---
# <a name="manage-office-365-message-encryption"></a>管理 Office 365 邮件加密

完成设置 Office 365 邮件加密 (OME) 后, 您可以通过多种方式自定义部署的配置。 例如, 您可以配置是否启用一次性传递代码, 在 Outlook 网页版中显示 "**保护**" 按钮, 等等。 本文中的任务介绍了如何。

## <a name="manage-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>管理 Google、Yahoo 和 Microsoft 帐户收件人是否可以使用这些帐户登录 Office 365 邮件加密门户

当您设置新的 Office 365 邮件加密功能时, 组织中的用户可以向位于您的 Office 365 组织外部的收件人发送邮件。 如果收件人使用的是 Google 帐户、Yahoo 帐户或 Microsoft 帐户等*社会 id* , 则收件人可以使用社会 id 登录到 OME 门户。 如果需要, 您可以选择不允许收件人使用社交 Id 登录到 OME 门户。
  
### <a name="to-manage-whether-recipients-can-use-social-ids-to-sign-in-to-the-ome-portal"></a>管理收件人是否可以使用社交 Id 登录到 OME 门户
  
1. [使用远程 PowerShell 连接到 Exchange Online](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。

2. 使用 SocialIdSignIn 参数运行 Set-omeconfiguration cmdlet, 如下所示:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter"> -SocialIdSignIn <$true|$false>
   ```

   例如, 若要禁用社会 Id, 请执行以下操作:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
   ```

   若要启用社交 Id, 请执行以下操作:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
   ```

## <a name="manage-the-use-of-one-time-pass-codes-for-the-office-365-message-encryption-portal"></a>管理 Office 365 邮件加密门户的一次性传递代码的使用

如果由 OME 加密的邮件的收件人不使用 Outlook, 而不管收件人使用的帐户如何, 收件人都会收到一个限制的 web 查看链接, 让他们能够阅读邮件。 该链接包括一次性的 pass 代码。 作为管理员, 你可以决定收件人是否可以使用一次性传递代码登录到 OME 门户。
  
### <a name="to-manage-whether-ome-generates-one-time-pass-codes"></a>管理 OME 是否生成一次性传递代码
  
1. 在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 并启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 OTPEnabled 参数运行 Set-omeconfiguration cmdlet:

   ```powershell
   Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true|$false>
   ```

   例如, 若要禁用一次性传递代码, 请执行以下操作:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
   ```

   若要启用一次性传递代码, 请执行以下操作:

   ```powershell
   Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
   ```

## <a name="manage-the-display-of-the-protect-button-in-outlook-on-the-web"></a>管理 web 上的 Outlook 中的 "保护" 按钮的显示

设置 OME 时, web 上的 Outlook 中的 "**保护**" 按钮处于禁用状态。 作为管理员, 您可以管理是否将此按钮显示给最终用户。
  
### <a name="to-manage-whether-the-protect-button-appears-in-outlook-on-the-web"></a>管理 "保护" 按钮在 web 上的 Outlook 中是否显示
  
1. 在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 并启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 运行带-SimplifiedClientAccessEnabled 参数的 Get-irmconfiguration cmdlet:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true|$false>
   ```

   例如, 要禁用 "**保护**" 按钮, 请执行以下操作:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

   启用 "**保护**" 按钮的步骤:

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
   ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>为 iOS 邮件应用程序用户启用电子邮件的服务端解密

IOS 邮件应用程序无法解密受 Office 365 邮件加密保护的邮件。 作为 Office 365 管理员, 您可以对传递到 iOS 邮件应用程序的邮件应用服务端解密。 当您选择使用服务端解密时, 该服务会将邮件的解密副本发送到 iOS 设备。 客户端设备存储邮件的解密副本。 即使 iOS 邮件应用程序不会对用户应用客户端使用权限, 该邮件也会保留有关使用权限的信息。 用户可以复制或打印邮件, 即使他们最初未具有这样做的权限也是如此。 但是, 如果用户尝试完成需要 Office 365 邮件服务器的操作 (如转发邮件), 则如果用户最初未使用此功能, 则服务器将不允许该操作。 但是, 最终用户可以通过从 iOS 邮件应用程序中的不同帐户转发邮件来解决 "不转发" 使用限制。 无论您是否设置了邮件的服务端解密, 在 iOS 邮件应用中无法查看加密的附件和受权限保护的邮件。
  
如果选择不允许向 iOS 邮件应用程序用户发送解密邮件, 则用户会收到一条消息, 指出他们没有查看邮件的权限。 默认情况下, 不会启用电子邮件的服务端解密。
  
有关详细信息以及客户端体验的视图, 请参阅[在 iPhone 或 iPad 上查看加密的邮件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)。
  
### <a name="to-manage-whether-ios-mail-app-users-can-view-messages-protected-by-office-365-message-encryption"></a>管理 iOS 邮件应用程序用户是否可以查看受 Office 365 邮件加密保护的邮件
  
1. 在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 并启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 AllowRMSSupportForUnenlightenedApps 参数运行 ActiveSyncOrganizations cmdlet:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true|$false>
   ```

   例如, 配置服务以在将邮件发送到 unenlightened 应用程序 (如 iOS 邮件应用程序) 之前对这些邮件进行解密:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
   ```

   或者, 将该服务配置为不将解密的邮件发送到 unenlightened 应用程序:

   ```powershell
   Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
   ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>启用 web 浏览器邮件客户端的电子邮件附件的服务端解密

通常情况下, 当您使用 Office 365 邮件加密时, 附件会自动加密。 作为 Office 365 管理员, 您可以对用户从 web 浏览器下载的电子邮件附件应用服务端解密。
  
当您使用服务端解密时, 服务会将文件的解密副本发送到设备。 邮件仍加密。 即使浏览器不会对用户应用客户端使用权限, 电子邮件附件也会保留有关使用权限的信息。 用户可以复制或打印电子邮件附件, 即使他们最初未提供这样做的权限。 但是, 如果用户尝试完成需要 Office 365 邮件服务器的操作 (如转发附件), 则如果用户最初未使用此功能, 则服务器将不允许执行此操作。
  
无论您是否设置了附件的服务端解密, 用户都无法在 iOS 邮件应用中查看加密和受权限保护的邮件的任何附件。
  
如果选择不允许解密的电子邮件附件 (默认情况下), 用户将收到一条消息, 指出他们没有查看附件的权限。
  
有关 Office 365 如何使用仅加密选项为电子邮件和电子邮件附件实现加密的详细信息, 请参阅[电子邮件的仅加密选项。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
### <a name="to-manage-whether-email-attachments-are-decrypted-on-download-from-a-web-browser"></a>管理在从 web 浏览器下载时是否解密电子邮件附件
  
1. 在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 并启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 DecryptAttachmentFromPortal 参数运行 Get-irmconfiguration cmdlet:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal <$true|$false>
   ```

   例如, 将服务配置为在用户从 web 浏览器下载电子邮件附件时对其进行解密:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $true
   ```

   将服务配置为在下载时保留加密的电子邮件附件:

   ```powershell
   Set-IRMConfiguration -DecryptAttachmentFromPortal $false
   ```

## <a name="ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail--office-365-advanced-message-encryption-only"></a>确保所有外部收件人都使用 OME 门户来阅读加密邮件 (仅适用于 Office 365 高级邮件加密)

如果您使用的是 Office 365 高级邮件加密, 则可以使用自定义品牌打造模板来强制收件人收到包装邮件, 以使收件人能够在 OME 门户中读取加密电子邮件, 而不是使用 Outlook 或 web 上的 Outlook。 如果您使用希望更好地控制收件人如何使用其接收的邮件, 则可能需要执行此操作。 例如, 如果外部收件人在 web 门户中查看电子邮件, 您可以为电子邮件设置到期日期, 并且可以撤销电子邮件。 仅在 OME 门户中支持这些功能。 创建邮件流规则时, 可以使用 "加密" 选项和 "不转发" 选项。

### <a name="create-a-custom-template-to-force-all-external-recipients-to-use-the-ome-portal-and-for-encrypted-email-to-be-revocable-and-expire-in-7-days"></a>创建自定义模板以强制所有外部收件人使用 OME 门户, 并将加密电子邮件的加密电子邮件设为可吊销并在7天后过期

1. 在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 并启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 运行 Set-omeconfiguration cmdlet:

   ```powershell
   New-OMEConfiguration -Identity "<template name>" -ExternalMailExpiryInDays 7
   ```

   其中`template name` , 是要用于 Office 365 邮件加密自定义品牌模板的名称。 For example,

   ```powershell
   New-OMEConfiguration -Identity "<One week expiration>" -ExternalMailExpiryInDays 7
   ```

3. 运行 New-transportrule cmdlet:

   ```powershell
   New-TransportRule -name "<mail flow rule name>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "<option name>" -ApplyRightsProtectionCustomizationTemplate "<template name>"
   ```

    其中：

   - `mail flow rule name`是要用于新邮件流规则的名称。

   - `option name`可以`Encrypt`是或`Do Not Forward`。

   - `template name`是您赋予自定义品牌打造模板的名称, 例如`One week expiration`。

   若要使用 "一个星期过期" 模板对所有外部电子邮件进行加密, 并应用 "仅加密" 选项, 请执行以下操作:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Encrypt" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

   若要使用 "一个星期过期" 模板对所有外部电子邮件进行加密, 并应用 "不转发" 选项, 请执行以下操作:

   ```powershell
   New-TransportRule -name "<All outgoing mail>" -FromScope "InOrganization" -ApplyRightsProtectionTemplate "Do Not Forward" -ApplyRightsProtectionCustomizationTemplate "<One week expiration>"
   ```

## <a name="customize-the-appearance-of-email-messages-and-the-ome-portal"></a>自定义电子邮件和 OME 门户的外观

有关如何为组织自定义 OME 的详细信息, 请参阅[将组织的品牌添加到加密邮件](add-your-organization-brand-to-encrypted-messages.md)。
  
## <a name="disable-the-new-capabilities-for-ome"></a>禁用 OME 的新功能

我们希望它不会到达它, 但如果需要, 禁用 OME 的新功能非常简单。 首先, 您需要删除您创建的任何使用新 OME 功能的邮件流规则。 有关删除邮件流规则的信息, 请参阅[管理邮件流规则](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)。 然后, 在 Exchange Online PowerShell 中完成这些步骤。
  
### <a name="to-disable-the-new-capabilities-for-ome"></a>禁用 OME 的新功能
  
1. 在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。 有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 如果在 web 上的 Outlook 中启用了 "**保护**" 按钮, 请通过运行带有 SimplifiedClientAccessEnabled 参数的 get-irmconfiguration cmdlet 来禁用它。 否则, 请跳过此步骤。

   ```powershell
   Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
   ```

3. 通过运行 Get-irmconfiguration cmdlet 并将 AzureRMSLicensingEnabled 参数设置为 false 来禁用 OME 的新功能:

   ```powershell
   Set-IRMConfiguration -AzureRMSLicensingEnabled $false
   ```
