---
title: 针对 Office 365 提供的内置移动设备管理的功能
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/11/2018
ms.audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.DevicePolicySupportedDevice
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: a1da44e5-7475-4992-be91-9ccec25905b0
description: Office 365 的移动设备管理可以帮助您保护和管理移动设备，如 Iphone、 Ipad、 Androids 和组织中使用的 Windows Phone。创建具有设置，可帮助控制访问组织的 Office 365 电子邮件和文档中支持的移动设备和应用程序，并让您远程擦除设备，如果它被盗的移动设备管理策略。
ms.openlocfilehash: b7200eee3b50c2fc6d3e0ea0920236d71837a88b
ms.sourcegitcommit: c31424cafbf1953f2864d7e2ceb95b329a694edb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2018
ms.locfileid: "23272597"
---
# <a name="capabilities-of-built-in-mobile-device-management-for-office-365"></a>针对 Office 365 提供的内置移动设备管理的功能

Office 365 的移动设备管理可以帮助您保护和管理移动设备，如 Iphone、 Ipad、 Androids 和许可 Office 365 用户在组织中使用的 Windows Phone。您可以创建移动设备管理策略设置，可帮助控制访问您组织的 Office 365 电子邮件和支持的移动设备和应用程序的文档。如果丢失或被盗设备时，您可以远程擦除设备，以删除组织的敏感信息。
    
需要更多的功能比 MDM 包含 Office 365？请参阅 Microsoft Intune 是否具有所需： [MDM for Office 365 和 Microsoft Intune 之间的选择](choose-between-mdm-and-intune.md)。
  
## <a name="supported-devices"></a>支持的设备

Office 365 MDM 可用于保护和管理以下类型的设备。
  
- Windows Phone 8.1 +
    
- iOS 7.1 或更高版本
    
- Android 4 或更高版本
    
- Windows 8.1\*
    
- Windows 8.1 RT\*
    
- Windows 10\*\*
    
- Windows 10 移动版\*\*
    
\*Windows 8.1 和 Windows 8.1 RT 设备的访问控制仅限于 Exchange ActiveSync。
  
\*\*要求设备加入到 Azure Active Directory 和您的组织的移动设备管理服务中注册。
  
如果您的组织中的人员使用移动设备管理 Office 365 不支持的移动设备，您可能想要阻止这些设备，以帮助确保您的组织数据更安全的 Office 365 电子邮件应用程序访问 Exchange ActiveSync。用于阻止 Exchange ActiveSync 的步骤： 请参阅[管理设备访问设置](manage-device-access-settings.md)。
  
## <a name="access-control-for-office-365-email-and-documents"></a>Office 365 电子邮件和文档的访问控制

下表中的移动设备的不同类型的受支持的应用程序将提示用户在 MDM 注册 Office 365 没有的新的移动设备管理策略应用于用户的设备，并且以前未注册设备的用户。如果用户的设备不符合策略，具体取决于您设置方式策略，用户可能被阻止访问 Office 365 资源在这些应用程序，或他们可能拥有访问，但 Office 365 将报告策略冲突。
  
||**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|
|:-----|:-----|:-----|:-----|
|**Exchange** <br/> Exchange ActiveSync 包括内置电子邮件和第三方应用程序，如 TouchDown，使用 Exchange ActiveSync 版本 14.1 或更高版本。  <br/> |![Exchange ActiveSync 图标](media/b36e36ba-88a5-4b2e-bd1d-7432b751a60c.png)Exchange ActiveSync  <br/> ![Exchange 邮件移动图标](media/5b5312b4-3bfb-4fc7-84ff-d7ab21227c10.png)Exchange 邮件  <br/> |![Exchange ActiveSync 图标](media/b36e36ba-88a5-4b2e-bd1d-7432b751a60c.png)Exchange ActiveSync  <br/> ![iPhone 邮件移动图标](media/888bdc7a-8354-4013-a0b2-0d4432a9a92e.png)邮件  <br/> |![Exchange ActiveSync 图标](media/b36e36ba-88a5-4b2e-bd1d-7432b751a60c.png)Exchange ActiveSync  <br/> ![Android 电子邮件图标](media/20b48492-4adc-40ce-99cf-1b47bd2b389d.png)电子邮件  <br/> |
|**Office** 和 **OneDrive for Business** <br/> |无支持的应用  <br/> |![iPhone Outlook 移动图标](media/6c63112d-c10c-4040-85cc-feeccc3dd424.png)Outlook  <br/> ![iPhone OneDrive 移动图标](media/560ec187-82d9-4793-b72f-7ba595972bdc.png)OneDrive  <br/> ![iPhone Word 移动图标](media/63a3a749-1f98-402f-b211-e46b9224b655.png)Word  <br/> ![iPhone Excel 移动图标](media/5b8f62c0-96aa-4602-9ed8-f837bbf5fa9e.png)Excel  <br/> ![iPhone PowerPoint 移动图标](media/17c02dca-f60a-4d13-a610-00d576a40943.png)PowerPoint  <br/> |**手机和平板电脑上：** <br/> ![Android 电话和平板电脑 Outlook 移动图标](media/ed2a813d-f481-46e0-acc9-6422f0d16072.png)Outlook  <br/> ![Android 移动电话 OneDrive 移动图标](media/64855d02-1684-4795-b4c5-863860f18722.png)OneDrive  <br/> ![Android Word 移动图标](media/f618fe83-b163-4680-b924-fcedc06ab4ba.png)Word  <br/> ![Android Excel 移动图标](media/659c7a5f-5797-4b47-a776-4a0c8f784c89.png)Excel  <br/> ![Android PowerPoint 移动图标](media/35b98bce-d7cb-40ce-87e3-07b9764207b1.png)PowerPoint  <br/> **仅手机上：** <br/> ![Office 移动移动图标](media/1aa9e978-6eb2-40aa-82da-62fb79cee313.png)Office Mobile  <br/> |
   
> [!NOTE]
>  IOS 7.1 和更高版本支持包括 iPhone 和 iPad 设备。> BlackBerry 设备的管理 Office 365 不支持移动设备管理。使用 BlackBerry 商业云服务 (BBCS) 从 BlackBerry 管理 BlackBerry 设备。> 不会提示用户注册，并且不会阻止或如果他们使用移动浏览器访问 Office 365 SharePoint 网站，Office Online 中的文档或 Outlook Web App 中的电子邮件策略违规报告。 
  
下图显示了具有新的设备的用户登录到应用程序支持的 Office 365 访问 MDM 控件时，会发生什么情况。用户被阻止之前会注册其设备访问应用程序中的 Office 365 资源。
  
![显示新设备的注册过程。](media/O365-MDM-Capabilities-EnrollmentExample.png)
  
> [!NOTE]
> Exchange ActiveSync 移动设备邮箱策略和在 Exchange 管理中心中创建的设备访问规则，将覆盖策略和在 MDM for Office 365 中创建的访问规则。设备中 MDM 注册 Office 365 后，将忽略任何 Exchange ActiveSync 移动设备邮箱策略或设备访问规则应用于该设备。若要了解有关 Exchange ActiveSync 的详细信息，请参阅[Exchange Online 中的 Exchange ActiveSync](https://go.microsoft.com/fwlink/p/?LinkId=524380)。 
  
## <a name="policy-settings-for-mobile-devices"></a>移动设备的策略设置

如果创建策略，以阻止访问与开启某些设置时，将被阻止用户使用支持的应用程序中[的 Office 365 电子邮件和文档的访问控制](#access-control-for-office-365-email-and-documents)列出的时访问 Office 365 资源。可以阻止用户访问 Office 365 资源相关的设置包括以下几节中：
  
- 安全
    
- 加密
    
- 越狱
    
- 托管电子邮件配置文件
    
例如下, 图显示了具有注册设备的用户不符合其设备应用于移动设备管理策略中的安全设置时，会发生什么情况。用户登录到应用程序支持的 Office 365 访问与 MDM 控制权。它们被阻止访问应用程序中的 Office 365 资源，直到其设备符合的安全设置。
  
![显示设备不兼容时阻止用户。](media/O365-MDM-Capabilities-ComplianceExample.png)
  
以下各节列出了可用于保护和管理移动设备连接到组织的 Office 365 资源的策略设置。 
  
### <a name="security-settings"></a>安全设置

|**设置名称**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**三星 Knox**|
|:-----|:-----|:-----|:-----|:-----|
|需要密码  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|避免简单密码  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|需要字母数字密码  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|最短密码长度  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|擦除设备之前登录失败的次数  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|设备锁定前的不活动分钟数  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|密码过期(天)  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|记住密码历史记录，并防止重复使用  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
   
### <a name="encryption-settings"></a>加密设置

|**设置名称**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**三星 Knox**|
|:-----|:-----|:-----|:-----|:-----|
|需要对设备上的数据加密  <br/> |Windows Phone 8.1 已加密且不能解密  <br/> |✖  <br/> |✔  <br/> |✔\*  <br/> |
   
\*与三星 Knox，您还可以要求对存储卡加密。
  
### <a name="jail-broken-setting"></a>越狱设置

|**设置名称**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**三星 Knox**|
|:-----|:-----|:-----|:-----|:-----|
|设备无法越狱或获得根权限  <br/> |✖  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
   
### <a name="managed-email-profile-option"></a>托管电子邮件配置文件选项

以下选项可阻止用户访问其 Office 365 电子邮件，如果他们使用的一个手动创建电子邮件配置文件。IOS 设备上的用户必须删除其手动创建电子邮件配置文件，才能访问其电子邮件。它们删除配置文件后，新的配置文件将在设备上自动创建。
  
|**设置名称**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**三星 Knox**|
|:-----|:-----|:-----|:-----|:-----|
|电子邮件配置文件已托管  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
   
### <a name="cloud-settings"></a>云设置

|**设置名称**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**三星 Knox**|
|:-----|:-----|:-----|:-----|:-----|
|需要加密备份  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|阻止云备份  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|阻止文档同步  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|阻止照片同步  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|允许 Google 备份  <br/> |不适用  <br/> |不适用  <br/> |✖  <br/> |✔  <br/> |
|允许 Google 帐户自动同步  <br/> |不适用  <br/> |不适用  <br/> |✖  <br/> |✔  <br/> |
   
### <a name="system-settings"></a>系统设置

|**设置名称**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**三星 Knox**|
|:-----|:-----|:-----|:-----|:-----|
|阻止屏幕捕获  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✔  <br/> |
|阻止从设备发送诊断数据  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✔  <br/> |
   
### <a name="application-settings"></a>应用程序设置

|**设置名称**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**三星 Knox**|
|:-----|:-----|:-----|:-----|:-----|
|阻止设备上的视频会议  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
|阻止对应用商店的访问  <br/> |✔  <br/> |✔  <br/> |✖  <br/> |✔  <br/> |
|访问应用商店时需要密码  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
   
### <a name="device-capabilities-settings"></a>设备功能设置

|**设置名称**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4+**|**三星 Knox**|
|:-----|:-----|:-----|:-----|:-----|
|阻止与可移动存储的连接  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |
|阻止蓝牙连接  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |
   
### <a name="additional-settings"></a>其他设置

您可以通过使用 PowerShell cmdlet 设置以下其他策略设置。有关详细信息，请参阅[Office 365 安全性&amp;合规性中心 cmdlet](https://go.microsoft.com/fwlink/p/?LinkId=827804)。
  
|**设置名称**|**Windows Phone 8.1 +**|**iOS 7.1+**|**Android 4 + （包括三星 Knox）**|
|:-----|:-----|:-----|:-----|
|CameraEnabled  <br/> |✔  <br/> |✔  <br/> |✔  <br/> |
|RegionRatings  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|MoviesRatings  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|TVShowsRating  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AppsRatings  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowVoiceDialing  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowVoiceAssistant  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowAssistantWhileLocked  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|AllowPassbookWhileLocked  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|MaxPasswordGracePeriod  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|PasswordQuality  <br/> |✖  <br/> |✖  <br/> |✔  <br/> |
|SystemSecurityTLS  <br/> |✖  <br/> |✔  <br/> |✖  <br/> |
|WLANEnabled  <br/> |✔  <br/> |✖  <br/> |✖  <br/> |
   
### <a name="settings-supported-by-windows"></a>支持的 Windows 的设置

您可以通过其注册为移动设备管理 Windows 8.1 和 Windows 10 设备。部署适用的策略后，具有 Windows 8.1 RT 和 Windows 10 RT 设备的用户将需要注册 MDM 在 Office 365 首次使用内置的电子邮件应用程序访问其 Office 365 电子邮件。 
  
Windows 8.1 和 Windows 10 注册为移动设备的设备支持下列设置。这些设置不会阻止用户访问 Office 365 资源。
  
 **安全设置**
  
- 需要字母数字密码
    
- 最短密码长度
    
- 擦除设备之前登录失败的次数
    
- 设备锁定前的不活动分钟数
    
- 密码过期(天)
    
- 记住密码历史记录，并防止重复使用
    
 **系统设置**
  
阻止从设备发送诊断数据
  
 **其他设置**
  
您可以使用 PowerShell cmdlet 来设置其他策略设置（如下所示）：
  
- AllowConvenienceLogon
    
- UserAccountControlStatus
    
- FirewallStatus
    
- AutoUpdateStatus
    
- AntiVirusStatus
    
- AntiVirusSignatureStatus
    
- SmartScreenEnabled
    
- WorkFoldersSyncUrl
    
## <a name="remotely-wipe-a-mobile-device"></a>远程擦除移动设备

 如果丢失或被盗设备，可以删除组织的敏感数据，并帮助阻止对贵组织的 Office 365 资源的访问，通过执行擦除从**安全&amp;合规性中心\>数据丢失防护\>设备管理**。您可以删除仅组织数据选择性擦除或完整擦除，从设备中删除所有信息并将其还原到出厂默认设置。
  
有关详细信息，请参阅[擦除 Office 365 中的移动设备](https://go.microsoft.com/fwlink/p/?LinkId=518157)。
  
## <a name="see-also"></a>另请参阅

[Office 365 移动设备管理概述](overview-of-mdm.md)
  
[创建和部署设备安全策略](create-device-security-policies.md)

