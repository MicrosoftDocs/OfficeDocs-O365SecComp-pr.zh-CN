---
title: 将您的组织品牌添加到加密邮件
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 11/2/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
description: '作为 Exchange 管理员，您可以应用您的组织品牌贵组织的加密的电子邮件和加密门户的内容。 '
ms.openlocfilehash: 2f34b5cea3155f587fd7787f1f69270d1373400b
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525422"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a>在加密的邮件中添加组织的品牌名称

作为 Exchange Online 或 Exchange Online Protection 管理员，您可以将应用您公司品牌自定义您的组织的 Office 365 邮件加密电子邮件的外观和加密门户的内容。使用 Get-omeconfiguration 和 Set-omeconfiguration Windows PowerShell cmdlet，您可以自定义加密的电子邮件的收件人的查看体验的以下方面：
  
- 包含加密邮件的电子邮件介绍性文本
    
- 包含加密邮件的电子邮件免责声明文本
    
- 在 OME 门户中显示的文本
    
- 电子邮件和 OME 门户中显示的徽标
    
- 在电子邮件和 OME 门户的背景色
    
您也可以随时还原到默认的外观。
  
||
|:-----|
|本文是系列的有关 Office 365 邮件加密的文章的较大一部分。本文旨在为管理员和 ITPros。如果您只查找有关的信息发送或接收加密的邮件， [Office 365 邮件加密 (OME)](ome.md)中的文章的列表，请参阅并找到最适合您的需求的文章。 |
||
   
**自定义您的组织品牌的加密的 OME OME 门户和电子邮件消息的外观**
  
1. 连接到 Exchange Online 使用远程 PowerShell[连接到 Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)中所述。
    
2. [Set-omeconfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)中所述使用 Set-omeconfiguration cmdlet 或使用下表的指南。 
    
**加密自定义选项**

|**自定义加密体验的这一功能**|**使用这些命令**|
|:-----|:-----|
|附带加密的电子邮件的默认文本。默认文本显示上方以查看加密的邮件的说明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|包含加密邮件的电子邮件中的免责声明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only."` <br/> |
|显示在加密邮件查看门户顶部的文本<br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."` <br/> |
|徽标  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> 支持的文件格式：.png、.jpg、.bmp 或 .tiff  <br/> 徽标文件的最佳大小：小于 40 KB  <br/> 徽标图像的最佳大小：170x70 像素  <br/> |
|背景色  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -BackgroundColor "#ffffff"` <br/> |
   
**按 OME 加密 OME 门户和电子邮件中删除品牌自定义项**
  
1. 连接到 Exchange Online 使用远程 PowerShell[连接到 Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)中所述。
    
2. [Set-omeconfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)中所述使用 Set-omeconfiguration cmdlet。若要删除您的组织的品牌自定义项从 DisclaimerText，EmailText，和 PortalText 值，将值设置为空字符串， `""`。有关所有图像值，如徽标，将值设置为`"$null"`。
    
**加密自定义选项**

**将加密体验的此功能还原到默认的文本和图片**|**使用这些命令**|
|:-----|:-----|
|加密电子邮件随附的默认文本  <br/> 默认文本显示在说明的上方，以查看加密邮件  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|包含加密邮件的电子邮件中的免责声明  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> **示例：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|显示在加密邮件查看门户顶部的文本  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> **示例还原回默认值：** <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|徽标  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> **示例还原回默认值：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
|背景色  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> **示例还原回默认值：** <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null` <br/> |
   

