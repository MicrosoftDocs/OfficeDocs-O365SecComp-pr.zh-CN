---
title: 将组织品牌添加到加密邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- M365-security-compliance
description: 作为 Exchange 管理员, 您可以将组织的品牌化应用于组织的加密电子邮件和加密门户的内容。
ms.openlocfilehash: 237824890d2b519e36cf5205a1f5c3dcc0fe830a
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213332"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>在加密的邮件中添加组织的品牌名称

作为 Exchange online 或 exchange online Protection 管理员, 您可以应用公司品牌, 以自定义组织的 Office 365 邮件加密电子邮件的外观以及加密门户的内容。通过使用 set-omeconfiguration 和 set-omeconfiguration Windows PowerShell cmdlet, 您可以自定义加密电子邮件的收件人的查看体验的以下方面:
  
- 包含加密邮件的电子邮件介绍性文本
- 包含加密邮件的电子邮件免责声明文本
- 显示在 OME 门户中的文本
- 电子邮件和 OME 门户中显示的徽标
- 电子邮件和 OME 门户中的背景色

您也可以随时还原到默认的外观。

如果您希望获得更多控制, 可以为来自组织的加密电子邮件创建多个模板。使用这些模板, 不仅可以控制电子邮件的外观, 还可以控制最终用户体验的各个部分。例如, 您可以指定是否已应用此模板的邮件收件人以及使用 Google、Yahoo 和 Microsoft 帐户的收件人是否可以使用这些帐户登录到 Office 365 邮件加密门户。您可以使用模板来实现几个用例, 例如:

- 每个部门的模板, 如财务、销售等。
- 不同产品的模板
- 不同地理区域或国家/地区的模板

创建模板后, 可以通过使用 Exchange 邮件流规则将它们应用于加密电子邮件。使用这些模板进行品牌化的所有邮件都可以被撤销。
  
||
|:-----|
|本文是有关 Office 365 邮件加密的更多系列文章的一部分。本文适用于管理员和 ITPros。如果只是查找有关发送或接收加密邮件的信息, 请参阅[Office 365 邮件加密 (OME)](ome.md)中的文章列表, 并找到最符合您的需求的文章。|
||

## <a name="create-branding-templates"></a>创建品牌打造模板

在 Windows PowerShell 中使用 set-omeconfiguration cmdlet 创建组织的品牌打造模板。创建模板后, 使用 set-omeconfiguration cmdlet 定义模板的各个部分。您可以创建多个模板。

![可自定义的电子邮件部件](media/ome-template-breakout.png)
  
1. 在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用 set-omeconfiguration cmdlet 可以创建新的模板。

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```
   例如，

   ```powershell
   New-OMEConfiguration -Identity <Branding template 1>
   ```
3. 使用 set-omeconfiguration cmdlet 定义您刚刚定义的模板的自定义项, 如[set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)中所述, 或使用下表获取指南。

|**自定义加密体验的这一功能**|**使用这些命令**|
|:-----|:-----|
|背景色|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|徽标|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支持的文件格式：.png、.jpg、.bmp 或 .tiff  <br/> 徽标文件的最佳大小：小于 40 KB  <br/> 徽标图像的最佳大小：170x70 像素|
|发件人姓名和电子邮件地址旁边的文本|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|显示在 "阅读邮件" 按钮上的文本|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|显示在 "阅读邮件" 按钮下方的文本|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|包含加密邮件的电子邮件中的免责声明|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|显示在加密邮件查看门户顶部的文本|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|为此自定义模板启用或禁用一次性传递代码的身份验证|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> **示例：** <br/>为此自定义模板启用一次性密码 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> 禁用此自定义模板的一次性密码 <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|为此自定义模板启用或禁用与 Microsoft、Google 或 Yahoo 身份的身份验证|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> **示例：** <br/>为此自定义模板启用社交 id <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> 若要禁用此自定义模板的社交 id <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a>从 OME 门户和 OME 加密的电子邮件中删除品牌自定义
  
1. [连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。

2. 使用**set-omeconfiguration** cmdlet, 如[set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)中所述。若要从 DisclaimerText、EmailText 和 PortalText 值中删除您的组织的标记自定义项, 请将该值设置为`""`一个空字符串。对于所有图像值 (如 "徽标"), 请将`"$null"`值设置为。

**加密自定义选项**

**将加密体验的此功能还原到默认的文本和图片**|**使用这些命令**|
|:-----|:-----|
|加密电子邮件随附的默认文本  <br/> 默认文本显示在说明的上方，以查看加密邮件|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|包含加密邮件的电子邮件中的免责声明|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|显示在加密邮件查看门户顶部的文本|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **将恢复为默认值的示例:** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
|徽标|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **将恢复为默认值的示例:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|背景色|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **将恢复为默认值的示例:** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a>创建对加密电子邮件应用自定义品牌打造的 Exchange 邮件流规则

创建品牌模板后, 可以创建 Exchange 邮件流规则, 以根据特定条件应用该自定义品牌打造。此类规则将在以下情况下应用自定义品牌打造:

- 如果最终用户从 outlook 或 web 上的 outlook (以前称为 Outlook web App) 客户端手动加密电子邮件
- 如果电子邮件是由 Exchange 邮件流规则或 Office 365 数据丢失防护策略自动加密的

有关如何创建适用于加密的 Exchange 邮件流规则的信息, 请参阅[定义邮件流规则以在 Office 365 中加密电子邮件](define-mail-flow-rules-to-encrypt-email.md)。

1. 在 web 浏览器中, 使用已被授予全局管理员权限的工作或学校帐户,[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。

2. 选择 "**管理**" 磁贴。

3. 在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。

4. 在 EAC 中, 转到 "**邮件流** \> **规则**", 然后选择 "**新建** ![" 图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。有关使用 EAC 的详细信息, 请参阅 exchange [Online 中的 exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。

5. 在 "**名称**" 中, 键入规则的名称, 例如 "销售部门的品牌"。

6. 在 "在**以下情况应用此规则**" "选择条件" 中, 选择**发件人位于组织内部**的条件以及在可用条件列表中所需的其他条件。例如, 您可能希望将特定品牌模板应用于:

     - 从财务部门的成员发送的所有加密电子邮件
     - 使用特定关键字 (如 "外部" 或 "合作伙伴") 发送的加密电子邮件
     - 发送到特定域的加密电子邮件

7. 从**执行以下操作**, 选择 **"修改邮件安全性** > 对**OME 邮件应用自定义品牌打造**"。接下来, 从下拉菜单中选择您创建的品牌模板。
8. Optional如果您希望邮件流规则还应用除自定义品牌的加密之外的加密, 请选择 **"****修改邮件安全性**", 然后选择 "**应用 Office 365 邮件加密和权限保护**"。从列表中选择一个 RMS 模板, 选择 "**保存**", 然后选择 **"确定"**。
  
     模板列表包含所有默认模板和选项, 以及您创建的用于 Office 365 的任何自定义模板。如果列表为空, 请确保已使用新功能设置了 Office 365 邮件加密, 如[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)中所述。有关默认模板的信息, 请参阅[配置和管理 Azure 信息保护的模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。有关 "**不要转发**" 选项的信息, 请参阅[电子邮件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)的 "不要转发" 选项。有关**仅加密**选项的信息, 请参阅[仅加密电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。

     如果要指定另一个操作, 可以选择 "**添加操作**"。
