---
title: 将您的组织品牌添加到加密邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
description: 作为 Exchange 管理员，您可以应用您的组织品牌贵组织的加密的电子邮件和加密门户的内容。
ms.openlocfilehash: 4b22b72a8b77c2978a7cf25166978759119c272c
ms.sourcegitcommit: 7e2a0185cadea7f3a6afc5ddc445eac2e1ce22eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2019
ms.locfileid: "29696216"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>在加密的邮件中添加组织的品牌名称

作为 Exchange Online 或 Exchange Online Protection 管理员，您可以将应用您公司品牌自定义您的组织的 Office 365 邮件加密电子邮件的外观和加密门户的内容。使用 Get-omeconfiguration 和 Set-omeconfiguration Windows PowerShell cmdlet，您可以自定义加密的电子邮件的收件人的查看体验的以下方面：
  
- 包含加密邮件的电子邮件介绍性文本
- 包含加密邮件的电子邮件免责声明文本
- 在 OME 门户中显示的文本
- 电子邮件和 OME 门户中显示的徽标
- 在电子邮件和 OME 门户的背景色

您也可以随时还原到默认的外观。

如果需要更多控制，您可以创建多个模板的加密电子邮件来自您的组织。使用这些模板，您可以控制远不止外观的电子邮件，但还控制最终用户体验的部分。例如，您可以指定的邮件的收件人的已应用此模板，并使用 Google、 Yahoo 和 Microsoft 帐户可以使用这些帐户登录到 Office 365 邮件加密门户。您可以使用模板来满足多个用例，例如：

- 每个部门，例如财务、 销售等的的模板。
- 不同产品的模板
- 不同地理区域或国家/地区的模板

创建模板后，您可以将其应用于加密的电子邮件使用 Exchange 邮件流规则。可以撤消品牌使用这些模板的所有邮件。
  
||
|:-----|
|本文是系列的有关 Office 365 邮件加密的文章的较大一部分。本文旨在为管理员和 ITPros。如果您只查找有关的信息发送或接收加密的邮件， [Office 365 邮件加密 (OME)](ome.md)中的文章的列表，请参阅并找到最适合您的需求的文章。 |
||

## <a name="create-branding-templates"></a>创建品牌模板

您在 Windows PowerShell 新建 OMEConfiguration cmdlet 与贵组织中创建品牌的模板。创建模板后，您可以使用 Set-omeconfiguration cmdlet 定义的模板的部分。您可以创建多个模板。

![可自定义电子邮件部件](media/ome-template-breakout.png)
  
1. 使用 Office 365 组织中具有全局管理员权限的工作或学校帐户，请启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明，请参阅[Connect to Exchange Online PowerShell 中](https://aka.ms/exopowershell)。

2. 新建 OMEConfiguration cmdlet 用于创建新的模板。
     ```powershell
     New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
     ```
     例如，
     ```powershell
     New-OMEConfiguration -Identity <Branding template 1>
     ```
3. 定义您刚才定义使用 Set-omeconfiguration cmdlet [Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)中所述的模板的自定义项或使用下表的指南。

|**自定义加密体验的这一功能**|**使用这些命令**|
|:-----|:-----|
|背景色  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> |
|徽标  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支持的文件格式：.png、.jpg、.bmp 或 .tiff  <br/> 徽标文件的最佳大小：小于 40 KB  <br/> 徽标图像的最佳大小：170x70 像素  <br/> |
|旁边发件人的姓名和电子邮件地址的文本| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|在"阅读邮件"按钮上显示的文本| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|在"阅读邮件"按钮下方上方显示的文本| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|包含加密邮件的电子邮件中的免责声明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|显示在加密邮件查看门户顶部的文本<br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."` <br/> |
|启用或禁用与此自定义模板一次性密码的身份验证| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **示例：** <br/>若要启用此自定义模板的一次性密码 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> 若要禁用此自定义模板的一次性密码 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|启用或禁用与此自定义模板的 Microsoft、 Google 或 Yahoo 标识的身份验证| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **示例：** <br/>若要启用此自定义模板的社交 Id <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> 若要禁用此自定义模板的社交 Id <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a>按 OME 加密 OME 门户和电子邮件中删除品牌自定义项
  
1. [连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. [Set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)中所述使用 Set-omeconfiguration cmdlet。若要删除您的组织的品牌自定义项从 DisclaimerText，EmailText，和 PortalText 值，将值设置为空字符串， `""`。有关所有图像值，如徽标，将值设置为`"$null"`。

**加密自定义选项**

**将加密体验的此功能还原到默认的文本和图片**|**使用这些命令**|
|:-----|:-----|
|加密电子邮件随附的默认文本  <br/> 默认文本显示在说明的上方，以查看加密邮件| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|包含加密邮件的电子邮件中的免责声明| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|显示在加密邮件查看门户顶部的文本| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **示例还原回默认值：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|徽标| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **示例还原回默认值：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|背景色| `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **示例还原回默认值：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a>创建 Exchange 邮件流规则适用的自定义品牌对加密的电子邮件

您已创建的品牌模板后，您可以创建 Exchange 邮件流规则应用的自定义品牌根据某些条件。此类的规则将应用自定义品牌在下列情况下：

- 如果由最终用户从 Outlook 或 OWA 客户端手动加密电子邮件
- 如果由 Exchange 邮件流规则或 Office 365 数据丢失预防策略自动加密电子邮件

有关如何创建 Exchange 邮件流规则适用加密的信息，请参阅[定义邮件流规则来加密 Office 365 中的电子邮件](define-mail-flow-rules-to-encrypt-email.md)。

1. 在 web 浏览器中，使用工作或学校帐户已被授予全局管理员权限，[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择**管理员**图块。

3. 在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。

4. 在 EAC 中，转到**邮件流** \> **规则**和选择**新建**![新图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。有关使用 EAC 的详细信息，请参阅[Exchange Admin Center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在**名称**框中，键入该规则，例如品牌的销售部门的名称。

6. 在**以下情况应用此规则**中选择一个条件，从可用条件列表中选择**发件人位于组织内部**的条件，以及其他所需的条件。例如，您可能想要应用到的特定品牌模板：

     - 从的财务部门成员发送的所有加密电子邮件
     - 与特定关键字如"外部"或"合作伙伴"发送加密电子邮件
     - 加密电子邮件发送到特定域

7. 从**执行以下操作**，选择**修改邮件安全性** > **应用自定义品牌 OME 消息**。接下来，从下拉菜单中，选择与您创建一个品牌模板。
8. （可选）如果您想要同样适用除了自定义加密的邮件流规则品牌，**执行以下操作**，从选择**修改邮件安全性**，然后选择**应用 Office 365 邮件加密和权限保护**。从列表中选择的 RMS 模板，选择**保存**，然后选择**确定**。
  
     模板的列表包含所有的默认模板和选项，以及您已创建的任何自定义模板使用 Office 365。如果列表为空，确保您已设置 Office 365 邮件加密的新功能与[Office 365 邮件加密的新功能的设置](set-up-new-message-encryption-capabilities.md)中所述。有关默认模板的信息，请参阅[配置和管理 Azure 信息保护模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关**不要转发**选项的信息，请参阅[不要转发的电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)。有关**仅加密**选项的信息，请参阅[仅加密的电子邮件的选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

     如果您希望指定另一项操作，可以选择**添加操作**。
