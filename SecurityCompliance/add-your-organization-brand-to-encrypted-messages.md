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
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a><span data-ttu-id="8ca62-103">在加密的邮件中添加组织的品牌名称</span><span class="sxs-lookup"><span data-stu-id="8ca62-103">Add your organization's brand to your encrypted messages</span></span>

<span data-ttu-id="8ca62-p101">作为 Exchange Online 或 Exchange Online Protection 管理员，您可以将应用您公司品牌自定义您的组织的 Office 365 邮件加密电子邮件的外观和加密门户的内容。使用 Get-omeconfiguration 和 Set-omeconfiguration Windows PowerShell cmdlet，您可以自定义加密的电子邮件的收件人的查看体验的以下方面：</span><span class="sxs-lookup"><span data-stu-id="8ca62-p101">As an Exchange Online or Exchange Online Protection administrator, you can apply your company branding to customize the look of your organization's Office 365 Message Encryption email messages and the contents of the encryption portal. Using the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets, you can customize the following aspects of the viewing experience for recipients of encrypted email messages:</span></span>
  
- <span data-ttu-id="8ca62-106">包含加密邮件的电子邮件介绍性文本</span><span class="sxs-lookup"><span data-stu-id="8ca62-106">Introductory text of the email that contains the encrypted message</span></span>
    
- <span data-ttu-id="8ca62-107">包含加密邮件的电子邮件免责声明文本</span><span class="sxs-lookup"><span data-stu-id="8ca62-107">Disclaimer text of the email that contains the encrypted message</span></span>
    
- <span data-ttu-id="8ca62-108">在 OME 门户中显示的文本</span><span class="sxs-lookup"><span data-stu-id="8ca62-108">Text that appears in the OME portal</span></span>
    
- <span data-ttu-id="8ca62-109">电子邮件和 OME 门户中显示的徽标</span><span class="sxs-lookup"><span data-stu-id="8ca62-109">Logo that appears in the email message and OME portal</span></span>
    
- <span data-ttu-id="8ca62-110">在电子邮件和 OME 门户的背景色</span><span class="sxs-lookup"><span data-stu-id="8ca62-110">Background color in the email message and OME portal</span></span>
    
<span data-ttu-id="8ca62-111">您也可以随时还原到默认的外观。</span><span class="sxs-lookup"><span data-stu-id="8ca62-111">You can also revert back to the default look and feel at any time.</span></span>
  
||
|:-----|
|<span data-ttu-id="8ca62-p102">本文是系列的有关 Office 365 邮件加密的文章的较大一部分。本文旨在为管理员和 ITPros。如果您只查找有关的信息发送或接收加密的邮件， [Office 365 邮件加密 (OME)](ome.md)中的文章的列表，请参阅并找到最适合您的需求的文章。</span><span class="sxs-lookup"><span data-stu-id="8ca62-p102">This article is part of a larger series of articles about Office 365 Message Encryption. This article is intended for administrators and ITPros. If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span> |
||
   
<span data-ttu-id="8ca62-115">**自定义您的组织品牌的加密的 OME OME 门户和电子邮件消息的外观**</span><span class="sxs-lookup"><span data-stu-id="8ca62-115">**To customize the look of the OME portal and email messages encrypted by OME with your organization's brand**</span></span>
  
1. <span data-ttu-id="8ca62-116">连接到 Exchange Online 使用远程 PowerShell[连接到 Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="8ca62-116">Connect to Exchange Online using Remote PowerShell, as described in [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/en-us/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="8ca62-117">[Set-omeconfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b)中所述使用 Set-omeconfiguration cmdlet 或使用下表的指南。</span><span class="sxs-lookup"><span data-stu-id="8ca62-117">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](http://technet.microsoft.com/en-us/3ef0aec0-ce28-411d-abe8-7236f082af1b) or use the following table for guidance.</span></span> 
    
<span data-ttu-id="8ca62-118">**加密自定义选项**</span><span class="sxs-lookup"><span data-stu-id="8ca62-118">**Encryption customization options**</span></span>

|<span data-ttu-id="8ca62-119">**自定义加密体验的这一功能**</span><span class="sxs-lookup"><span data-stu-id="8ca62-119">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="8ca62-120">**使用这些命令**</span><span class="sxs-lookup"><span data-stu-id="8ca62-120">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8ca62-p103">附带加密的电子邮件的默认文本。默认文本显示上方以查看加密的邮件的说明</span><span class="sxs-lookup"><span data-stu-id="8ca62-p103">Default text that accompanies encrypted email messages. The default text appears above the instructions for viewing encrypted messages</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="8ca62-123">**示例：**</span><span class="sxs-lookup"><span data-stu-id="8ca62-123">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="8ca62-124">包含加密邮件的电子邮件中的免责声明</span><span class="sxs-lookup"><span data-stu-id="8ca62-124">Disclaimer statement in the email that contains the encrypted message</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="8ca62-125">**示例：**</span><span class="sxs-lookup"><span data-stu-id="8ca62-125">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText "This message is confidential for the use of the addressee only."` <br/> |
|<span data-ttu-id="8ca62-126">显示在加密邮件查看门户顶部的文本</span><span class="sxs-lookup"><span data-stu-id="8ca62-126">Text that appears at the top of the encrypted mail viewing portal</span></span><br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="8ca62-127">**示例：**</span><span class="sxs-lookup"><span data-stu-id="8ca62-127">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."` <br/> |
|<span data-ttu-id="8ca62-128">徽标</span><span class="sxs-lookup"><span data-stu-id="8ca62-128">Logo</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> <span data-ttu-id="8ca62-129">**示例：**</span><span class="sxs-lookup"><span data-stu-id="8ca62-129">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="8ca62-130">支持的文件格式：.png、.jpg、.bmp 或 .tiff</span><span class="sxs-lookup"><span data-stu-id="8ca62-130">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="8ca62-131">徽标文件的最佳大小：小于 40 KB</span><span class="sxs-lookup"><span data-stu-id="8ca62-131">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="8ca62-132">徽标图像的最佳大小：170x70 像素</span><span class="sxs-lookup"><span data-stu-id="8ca62-132">Optimal size of logo image: 170x70 pixels</span></span>  <br/> |
|<span data-ttu-id="8ca62-133">背景色</span><span class="sxs-lookup"><span data-stu-id="8ca62-133">Background color</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> <span data-ttu-id="8ca62-134">**示例：**</span><span class="sxs-lookup"><span data-stu-id="8ca62-134">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -BackgroundColor "#ffffff"` <br/> |
   
<span data-ttu-id="8ca62-135">**按 OME 加密 OME 门户和电子邮件中删除品牌自定义项**</span><span class="sxs-lookup"><span data-stu-id="8ca62-135">**To remove brand customizations from the OME portal and email messages encrypted by OME**</span></span>
  
1. <span data-ttu-id="8ca62-136">连接到 Exchange Online 使用远程 PowerShell[连接到 Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)中所述。</span><span class="sxs-lookup"><span data-stu-id="8ca62-136">Connect to Exchange Online using Remote PowerShell, as described in [Connect to Exchange Online Using Remote PowerShell](http://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>
    
2. <span data-ttu-id="8ca62-p104">[Set-omeconfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b)中所述使用 Set-omeconfiguration cmdlet。若要删除您的组织的品牌自定义项从 DisclaimerText，EmailText，和 PortalText 值，将值设置为空字符串， `""`。有关所有图像值，如徽标，将值设置为`"$null"`。</span><span class="sxs-lookup"><span data-stu-id="8ca62-p104">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](http://technet.microsoft.com/3ef0aec0-ce28-411d-abe8-7236f082af1b). To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string,  `""`. For all image values, such as Logo, set the value to  `"$null"`.</span></span>
    
<span data-ttu-id="8ca62-140">**加密自定义选项**</span><span class="sxs-lookup"><span data-stu-id="8ca62-140">**Encryption customization options**</span></span>

<span data-ttu-id="8ca62-141">**将加密体验的此功能还原到默认的文本和图片**</span><span class="sxs-lookup"><span data-stu-id="8ca62-141">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="8ca62-142">**使用这些命令**</span><span class="sxs-lookup"><span data-stu-id="8ca62-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8ca62-143">加密电子邮件随附的默认文本</span><span class="sxs-lookup"><span data-stu-id="8ca62-143">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="8ca62-144">默认文本显示在说明的上方，以查看加密邮件</span><span class="sxs-lookup"><span data-stu-id="8ca62-144">The default text appears above the instructions for viewing encrypted messages</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> <span data-ttu-id="8ca62-145">**示例：**</span><span class="sxs-lookup"><span data-stu-id="8ca62-145">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""` <br/> |
|<span data-ttu-id="8ca62-146">包含加密邮件的电子邮件中的免责声明</span><span class="sxs-lookup"><span data-stu-id="8ca62-146">Disclaimer statement in the email that contains the encrypted message</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> <span data-ttu-id="8ca62-147">**示例：**</span><span class="sxs-lookup"><span data-stu-id="8ca62-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""` <br/> |
|<span data-ttu-id="8ca62-148">显示在加密邮件查看门户顶部的文本</span><span class="sxs-lookup"><span data-stu-id="8ca62-148">Text that appears at the top of the encrypted mail viewing portal</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> <span data-ttu-id="8ca62-149">**示例还原回默认值：**</span><span class="sxs-lookup"><span data-stu-id="8ca62-149">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""` <br/> |
|<span data-ttu-id="8ca62-150">徽标</span><span class="sxs-lookup"><span data-stu-id="8ca62-150">Logo</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> <span data-ttu-id="8ca62-151">**示例还原回默认值：**</span><span class="sxs-lookup"><span data-stu-id="8ca62-151">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null` <br/> |
|<span data-ttu-id="8ca62-152">背景色</span><span class="sxs-lookup"><span data-stu-id="8ca62-152">Background color</span></span>  <br/> | `Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> <span data-ttu-id="8ca62-153">**示例还原回默认值：**</span><span class="sxs-lookup"><span data-stu-id="8ca62-153">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null` <br/> |
   

