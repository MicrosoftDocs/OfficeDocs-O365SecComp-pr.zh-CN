---
title: 管理 Office 365 邮件加密
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 09f6737e-f03f-4bc8-8281-e46d24ee2a74
description: 在完成设置 up Office 365 邮件加密 (OME) 后，可以自定义多种方法中的部署的配置。例如，您可以配置是否启用一次性密码、 在 web 应用程序和更多的 Outlook 中显示保护按钮。本文中的任务说明如何。
ms.openlocfilehash: ddc86bdf0d0ce5480587862a4ed438b6c138987f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525142"
---
# <a name="manage-office-365-message-encryption"></a>管理 Office 365 邮件加密

在完成设置 up Office 365 邮件加密 (OME) 后，可以自定义多种方法中的部署的配置。例如，您可以配置是否启用一次性密码、 在 web 应用程序和更多的 Outlook 中显示**保护**按钮。本文中的任务说明如何。 
  
||
|:-----|
|本文是系列的有关 Office 365 邮件加密的文章的较大一部分。本文旨在为管理员和 IT 专业人员。如果您只查找有关的信息发送或接收加密的邮件， [Office 365 邮件加密 (OME)](ome.md)中的文章的列表，请参阅并找到最适合您的需求的文章。 |
   
## <a name="managing-whether-google-yahoo-and-microsoft-account-recipients-can-use-these-accounts-to-sign-in-to-the-office-365-message-encryption-portal"></a>管理是否 Google、 Yahoo 和 Microsoft 帐户收件人可以使用这些帐户登录到 Office 365 邮件加密门户
<a name="PermitSocialID"> </a>

默认情况下时设置的新的 Office 365 邮件加密功能，您的组织中的用户可以发送邮件到 Office 365 组织外部的收件人。如果收件人使用*社交 ID*如 Google 帐户、 Yahoo 帐户或 Microsoft 帐户，收件人可以登录到 OME 门户使用社交 id。如果您希望，您可以选择不允许使用社交 Id 登录到 OME 门户的收件人。 
  
 **若要管理允许收件人社交 Id 用于登录到 OME 门户**
  
1. [连接到 Exchange Online 使用远程 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。
    
2. 如下所示使用 SocialIdSignIn 参数运行 Set-omeconfiguration cmdlet:
    
  ```
  Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -SocialIdSignIn <$true |$false >
  ```

    例如，若要禁用社交 Id:
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $false
  ```

    启用社交 Id:
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -SocialIdSignIn $true
  ```

## <a name="managing-the-use-of-one-time-pass-codes-for-signing-in-to-the-office-365-message-encryption-portal"></a>管理使用一次性密码登录到 Office 365 邮件加密门户
<a name="GenerateOTPC"> </a>

默认情况下，如果按 OME 加密邮件的收件人不使用 Outlook 中，无论收件人，使用的帐户收件人将接收允许阅读邮件的时间有限 web 视图链接。这包括一次性密码。作为管理员，您可以管理可一次性密码以登录到 OME 门户。
  
 **若要管理为 OME 生成一次性密码**
  
1. [连接到 Exchange Online 使用远程 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。
    
2. 如下所示使用 OTPEnabled 参数运行 Set-omeconfiguration cmdlet:
    
  ```
  Set-OMEConfiguration -Identity <"OMEConfigurationIdParameter "> -OTPEnabled <$true |$false >
  ```

    例如，若要禁用一次性密码：
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $false
  ```

    若要启用一次性密码：
    
  ```
  Set-OMEConfiguration -Identity "OME Configuration" -OTPEnabled $true
  ```

## <a name="managing-the-display-of-the-protect-button-in-outlook-on-the-web"></a>管理保护按钮在 web 上的 Outlook 中的显示
<a name="DisplayProtectButton"> </a>

默认情况下在 web 上的 Outlook**保护**按钮时，不启用设置 OME。作为管理员，您可以管理为最终用户显示此按钮。 
  
 **若要管理保护按钮显示在 web 上的 Outlook**
  
1. [连接到 Exchange Online 使用远程 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。
    
2. 如下所示使用-SimplifiedClientAccessEnabled 参数运行 Set-irmconfiguration cmdlet:
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled <$true |$false >
  ```

    例如，若要禁用**保护**按钮： 
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
  ```

    若要启用**保护**按钮： 
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $true
  ```

## <a name="enable-service-side-decryption-of-email-messages-for-ios-mail-app-users"></a>启用 iOS 邮件应用程序用户的电子邮件的服务商解密
<a name="EnableServiceSideDecrypt"> </a>

IOS 邮件应用程序无法解密术 シ モ メ Office 365 邮件加密的邮件。作为 Office 365 管理员，您可以应用邮件传递到 iOS 邮件应用程序的服务商解密。当您选择这样做时，服务会将解密邮件的副本发送到 iOS 设备。消息存储解密客户端设备上。邮件还保留有关使用权限的信息，即使 iOS 邮件应用程序不适用于向用户的客户端使用权限。这意味着用户可复制或打印邮件，即使他们最初没有这样的权限。但是，如果用户尝试完成操作所需的 Office 365 邮件服务器，如转发邮件，服务器将不允许操作如果用户最初没有这样的使用权限。但是，最终用户可以通过从无论您是否设置邮件的服务商解密其 iOS 邮件应用程序中的不同帐户转发邮件变通解决不要转发使用率限制，任何附件加密和权限受保护的邮件无法查看 iOS 邮件应用程序中。
  
如果您选择不允许将解密的邮件发送到 iOS 邮件应用程序用户，用户会收到一条消息，它们没有查看邮件的权限。默认情况下，未启用电子邮件的服务商解密。
  
有关详细信息，以及客户端体验的视图，请参阅部分中，"[查看加密的邮件 iPhone 或 iPad 上](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf#iOSEncryptedMail)"中[查看 iPad 或 iPhone 上的加密的邮件](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)。
  
 **若要管理 iOS 邮件应用程序用户可以查看受 Office 365 邮件加密的邮件**
  
1. [连接到 Exchange Online 使用远程 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。
    
2. 如下所示设置 ActiveSyncOrganizations cmdlet 运行带有 AllowRMSSupportForUnenlightenedApps 参数：
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps <$true |$false >
  ```

    例如，若要配置服务以解密邮件发送到 unenlightened 应用程序之前如 iOS 邮件应用程序：
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $true
  ```

    例如，若要配置服务无法将解密的邮件发送到 unenlightened 应用程序：
    
  ```
  Set-ActiveSyncOrganizationSettings -AllowRMSSupportForUnenlightenedApps $false
  ```

## <a name="enable-service-side-decryption-of-email-attachments-for-web-browser-mail-clients"></a>启用 web 浏览器邮件客户端的电子邮件附件的服务商解密
<a name="EnableServiceSideDecrypt"> </a>

通常，当您使用 Office 365 邮件加密，附件进行自动加密。作为 Office 365 管理员，您可以应用用户从 web 浏览器下载的电子邮件附件的服务商的解密。 
  
当您选择这样做时，该服务向设备发送解密文件的副本。仍加密消息。电子邮件附件还保留有关使用权限的信息，即使在浏览器不适用于向用户的客户端使用权限。这意味着用户可复制或打印电子邮件附件，即使他们最初没有这样的权限。但是，如果用户尝试完成操作所需的 Office 365 邮件服务器，如转发附件，服务器将不允许操作如果用户最初没有这样的使用权限。
  
无论您是否设置的附件的服务商解密，任何附件加密并不能在 iOS 邮件应用程序中查看权限受保护的邮件。
  
如果您选择不允许解密电子邮件附件，这是默认值，则用户将收到一条消息，它们没有要查看附件的权限。\* \* \*插入图片？
  
有关 Office 365 如何实现加密电子邮件和电子邮件附件的仅进行加密选项的详细信息，请参阅[的电子邮件仅加密选项。](https://docs.microsoft.com/azure/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)
  
 **若要管理电子邮件附件将解密在从 web 浏览器的下载**
  
1. [连接到 Exchange Online 使用远程 PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)。
    
2. 如下所示使用 DecryptAttachmentFromPortal 参数运行 Set-irmconfiguration cmdlet:
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal <$true |$false >
  ```

    例如，若要配置服务以解密电子邮件附件时用户下载这些从 web 浏览器：
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal $true
  ```

    配置要将加密的电子邮件附件保留在下载时原样的服务：
    
  ```
  Set-IRMConfiguration -DecryptAttachmentFromPortal $false
  ```

## <a name="customizing-the-appearance-of-email-messages-and-the-ome-portal"></a>自定义电子邮件和 OME 门户网站的外观
<a name="CustomizeAppearance"> </a>

有关如何为组织自定义 OME 的详细信息，请参阅[添加到加密邮件的组织品牌](add-your-organization-brand-to-encrypted-messages.md)。
  
## <a name="disabling-the-new-capabilities-for-ome"></a>禁用 OME 的新功能
<a name="CustomizeAppearance"> </a>

我们希望它不前置，但如果需要禁用的新功能，用于 OME 非常简单。首先，您将需要删除任何邮件流规则已创建，使用新的 OME 功能。有关删除邮件流规则的信息，请参阅[管理邮件流规则](https://technet.microsoft.com/library/jj657505%28v=exchg.150%29.aspx)。然后，完成以下步骤在 Exchange Online PowerShell。
  
 **禁用 OME 的新功能**
  
1. [连接到 Exchange Online 使用远程 PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.160%29.aspx)。
    
2. 如果启用在 web 上的 Outlook 中的保护按钮，请禁用它通过使用 SimplifiedClientAccessEnabled 参数运行 Set-irmconfiguration cmdlet，如下所示：
    
  ```
  Set-IRMConfiguration -SimplifiedClientAccessEnabled $false
  ```

3. 如下所示使用 AzureRMSLicensingEnabled 参数运行 Set-irmconfiguration cmdlet:
    
  ```
  Set-IRMConfiguration -AzureRMSLicensingEnabled $false
  ```


