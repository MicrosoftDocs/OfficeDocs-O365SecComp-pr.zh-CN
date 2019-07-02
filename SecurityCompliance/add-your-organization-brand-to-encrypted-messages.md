---
title: 将组织品牌添加到加密邮件
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: 作为 Office 365 全局管理员, 你可以将组织的品牌化应用于组织的加密电子邮件和加密门户的内容。
ms.openlocfilehash: 19f227971c522f9d92aec343f1865ab7f23c13aa
ms.sourcegitcommit: b0ea2d66bc4c7f2fc0a8abab28d2ae652b1c4b73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2019
ms.locfileid: "34721369"
---
# <a name="add-your-organizations-brand-to-your-encrypted-messages"></a><span data-ttu-id="a8355-103">在加密的邮件中添加组织的品牌</span><span class="sxs-lookup"><span data-stu-id="a8355-103">Add your organization's brand to your encrypted messages</span></span>

<span data-ttu-id="a8355-104">作为 Exchange Online 或 Exchange Online Protection 管理员, 您可以应用公司品牌, 以自定义组织的 Office 365 邮件加密电子邮件的外观以及加密门户的内容。</span><span class="sxs-lookup"><span data-stu-id="a8355-104">As an Exchange Online or Exchange Online Protection administrator, you can apply your company branding to customize the look of your organization's Office 365 Message Encryption email messages and the contents of the encryption portal.</span></span> <span data-ttu-id="a8355-105">通过使用 Set-omeconfiguration 和 Set-omeconfiguration Windows PowerShell cmdlet, 您可以自定义加密电子邮件的收件人的查看体验的以下方面:</span><span class="sxs-lookup"><span data-stu-id="a8355-105">Using the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets, you can customize the following aspects of the viewing experience for recipients of encrypted email messages:</span></span>
  
- <span data-ttu-id="a8355-106">包含加密邮件的电子邮件介绍性文本</span><span class="sxs-lookup"><span data-stu-id="a8355-106">Introductory text of the email that contains the encrypted message</span></span>

- <span data-ttu-id="a8355-107">包含加密邮件的电子邮件免责声明文本</span><span class="sxs-lookup"><span data-stu-id="a8355-107">Disclaimer text of the email that contains the encrypted message</span></span>

- <span data-ttu-id="a8355-108">显示在 OME 门户中的文本</span><span class="sxs-lookup"><span data-stu-id="a8355-108">Text that appears in the OME portal</span></span>

- <span data-ttu-id="a8355-109">电子邮件和 OME 门户中显示的徽标</span><span class="sxs-lookup"><span data-stu-id="a8355-109">Logo that appears in the email message and OME portal</span></span>

- <span data-ttu-id="a8355-110">电子邮件和 OME 门户中的背景色</span><span class="sxs-lookup"><span data-stu-id="a8355-110">Background color in the email message and OME portal</span></span>

<span data-ttu-id="a8355-111">您也可以随时还原到默认的外观。</span><span class="sxs-lookup"><span data-stu-id="a8355-111">You can also revert back to the default look and feel at any time.</span></span>

 <span data-ttu-id="a8355-112">如果您想要进行更多控制, 可以使用 Office 365 高级邮件加密并为来自您的组织的加密电子邮件创建多个模板。</span><span class="sxs-lookup"><span data-stu-id="a8355-112">If you'd like more control, you can use Office 365 Advanced Message Encryption and create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="a8355-113">使用这些模板, 不仅可以控制电子邮件的外观, 还可以控制最终用户体验的各个部分。</span><span class="sxs-lookup"><span data-stu-id="a8355-113">Using these templates, you can control more than just the look and feel of the email messages, but also control parts of the end-user experience.</span></span> <span data-ttu-id="a8355-114">例如, 您可以指定是否已应用此模板的邮件收件人以及使用 Google、Yahoo 和 Microsoft 帐户的收件人是否可以使用这些帐户登录到 Office 365 邮件加密门户。</span><span class="sxs-lookup"><span data-stu-id="a8355-114">For example, you can specify whether or not recipients of mail that have this template applied and who use Google, Yahoo, and Microsoft Accounts can use these accounts to sign in to the Office 365 Message Encryption portal.</span></span> <span data-ttu-id="a8355-115">您可以使用模板来实现几个用例, 例如:</span><span class="sxs-lookup"><span data-stu-id="a8355-115">You might use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="a8355-116">每个部门的模板, 如财务、销售等。</span><span class="sxs-lookup"><span data-stu-id="a8355-116">Templates for each department, such as Finance, Sales, etc.</span></span>

- <span data-ttu-id="a8355-117">不同产品的模板</span><span class="sxs-lookup"><span data-stu-id="a8355-117">Templates for different products</span></span>

- <span data-ttu-id="a8355-118">不同地理区域或国家/地区的模板</span><span class="sxs-lookup"><span data-stu-id="a8355-118">Templates for different geographical regions or countries</span></span>

- <span data-ttu-id="a8355-119">是否允许撤消电子邮件</span><span class="sxs-lookup"><span data-stu-id="a8355-119">Whether or not you want to allow emails to be revoked</span></span>

- <span data-ttu-id="a8355-120">您是否希望发送给外部收件人的电子邮件在指定天数后过期。</span><span class="sxs-lookup"><span data-stu-id="a8355-120">Whether or not you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="a8355-121">创建模板后, 可以通过使用 Exchange 邮件流规则将它们应用于加密电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a8355-121">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="a8355-122">如果您具有 Office 365 高级邮件加密, 则可以使用这些模板吊销任何已标记的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="a8355-122">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>
  
||
|:-----|
|<span data-ttu-id="a8355-123">本文是有关 Office 365 邮件加密的更多系列文章的一部分。</span><span class="sxs-lookup"><span data-stu-id="a8355-123">This article is part of a larger series of articles about Office 365 Message Encryption.</span></span> <span data-ttu-id="a8355-124">本文适用于管理员和 ITPros。</span><span class="sxs-lookup"><span data-stu-id="a8355-124">This article is intended for administrators and ITPros.</span></span> <span data-ttu-id="a8355-125">如果只是查找有关发送或接收加密邮件的信息, 请参阅[Office 365 邮件加密 (OME)](ome.md)中的文章列表, 并找到最符合您的需求的文章。</span><span class="sxs-lookup"><span data-stu-id="a8355-125">If you're just looking for information on sending or receiving an encrypted message, see the list of articles in [Office 365 Message Encryption (OME)](ome.md) and locate the article that best fits your needs.</span></span>|
||

## <a name="create-branding-templates"></a><span data-ttu-id="a8355-126">创建品牌打造模板</span><span class="sxs-lookup"><span data-stu-id="a8355-126">Create branding templates</span></span>

<span data-ttu-id="a8355-127">在 Windows PowerShell 中使用 Set-omeconfiguration cmdlet 创建组织的品牌打造模板。</span><span class="sxs-lookup"><span data-stu-id="a8355-127">You create branding templates for your organization in Windows PowerShell with the New-OMEConfiguration cmdlet.</span></span> <span data-ttu-id="a8355-128">创建模板后, 使用 Set-omeconfiguration cmdlet 定义模板的各个部分。</span><span class="sxs-lookup"><span data-stu-id="a8355-128">Once you've created the template, you define the pieces of the template by using the Set-OMEConfiguration cmdlet.</span></span> <span data-ttu-id="a8355-129">您可以创建多个模板。</span><span class="sxs-lookup"><span data-stu-id="a8355-129">You can create multiple templates.</span></span>

![可自定义的电子邮件部件](media/ome-template-breakout.png)
  
1. <span data-ttu-id="a8355-131">在 Office 365 组织中使用具有全局管理员权限的工作或学校帐户, 启动 Windows PowerShell 会话并连接到 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="a8355-131">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="a8355-132">有关说明, 请参阅[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="a8355-132">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="a8355-133">使用 Set-omeconfiguration cmdlet 可以创建新的模板。</span><span class="sxs-lookup"><span data-stu-id="a8355-133">Use the New-OMEConfiguration cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity <OMEConfigurationIdParameter>
   ```

   <span data-ttu-id="a8355-134">For example,</span><span class="sxs-lookup"><span data-stu-id="a8355-134">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Branding template 1"
   ```

3. <span data-ttu-id="a8355-135">使用 Set-omeconfiguration cmdlet 定义您刚刚定义的模板的自定义项, 如[set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)中所述, 或使用下表获取指南。</span><span class="sxs-lookup"><span data-stu-id="a8355-135">Define the customizations for the template you just defined by using the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration) or use the following table for guidance.</span></span>

|<span data-ttu-id="a8355-136">**自定义加密体验的这一功能**</span><span class="sxs-lookup"><span data-stu-id="a8355-136">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="a8355-137">**使用这些命令**</span><span class="sxs-lookup"><span data-stu-id="a8355-137">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a8355-138">背景色</span><span class="sxs-lookup"><span data-stu-id="a8355-138">Background color</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor "<Hexadecimal color code>"` <br/> <span data-ttu-id="a8355-139">**示例：**</span><span class="sxs-lookup"><span data-stu-id="a8355-139">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"`|
|<span data-ttu-id="a8355-140">徽标</span><span class="sxs-lookup"><span data-stu-id="a8355-140">Logo</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <Byte[]>` <br/> <span data-ttu-id="a8355-141">**示例：**</span><span class="sxs-lookup"><span data-stu-id="a8355-141">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="a8355-142">支持的文件格式：.png、.jpg、.bmp 或 .tiff</span><span class="sxs-lookup"><span data-stu-id="a8355-142">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="a8355-143">徽标文件的最佳大小：小于 40 KB</span><span class="sxs-lookup"><span data-stu-id="a8355-143">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="a8355-144">徽标图像的最佳大小：170x70 像素</span><span class="sxs-lookup"><span data-stu-id="a8355-144">Optimal size of logo image: 170x70 pixels</span></span>|
|<span data-ttu-id="a8355-145">发件人姓名和电子邮件地址旁边的文本</span><span class="sxs-lookup"><span data-stu-id="a8355-145">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="a8355-146">**示例：**</span><span class="sxs-lookup"><span data-stu-id="a8355-146">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="a8355-147">显示在 "阅读邮件" 按钮上的文本</span><span class="sxs-lookup"><span data-stu-id="a8355-147">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="a8355-148">**示例：**</span><span class="sxs-lookup"><span data-stu-id="a8355-148">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="a8355-149">显示在 "阅读邮件" 按钮下方的文本</span><span class="sxs-lookup"><span data-stu-id="a8355-149">Text that appears above below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="a8355-150">**示例：**</span><span class="sxs-lookup"><span data-stu-id="a8355-150">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="a8355-151">包含加密邮件的电子邮件中的免责声明</span><span class="sxs-lookup"><span data-stu-id="a8355-151">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="a8355-152">**示例：**</span><span class="sxs-lookup"><span data-stu-id="a8355-152">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="a8355-153">显示在加密邮件查看门户顶部的文本</span><span class="sxs-lookup"><span data-stu-id="a8355-153">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="a8355-154">**示例：**</span><span class="sxs-lookup"><span data-stu-id="a8355-154">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="a8355-155">为此自定义模板启用或禁用一次性传递代码的身份验证</span><span class="sxs-lookup"><span data-stu-id="a8355-155">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="a8355-156">**示例：**</span><span class="sxs-lookup"><span data-stu-id="a8355-156">**Examples:**</span></span> <br/><span data-ttu-id="a8355-157">为此自定义模板启用一次性密码</span><span class="sxs-lookup"><span data-stu-id="a8355-157">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="a8355-158">禁用此自定义模板的一次性密码</span><span class="sxs-lookup"><span data-stu-id="a8355-158">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="a8355-159">为此自定义模板启用或禁用与 Microsoft、Google 或 Yahoo 身份的身份验证</span><span class="sxs-lookup"><span data-stu-id="a8355-159">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="a8355-160">**示例：**</span><span class="sxs-lookup"><span data-stu-id="a8355-160">**Examples:**</span></span> <br/><span data-ttu-id="a8355-161">为此自定义模板启用社交 Id</span><span class="sxs-lookup"><span data-stu-id="a8355-161">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="a8355-162">若要禁用此自定义模板的社交 Id</span><span class="sxs-lookup"><span data-stu-id="a8355-162">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="to-remove-brand-customizations-from-the-ome-portal-and-email-messages-encrypted-by-ome"></a><span data-ttu-id="a8355-163">从 OME 门户和 OME 加密的电子邮件中删除品牌自定义</span><span class="sxs-lookup"><span data-stu-id="a8355-163">To remove brand customizations from the OME portal and email messages encrypted by OME</span></span>
  
1. <span data-ttu-id="a8355-164">[连接到 Exchange Online PowerShell](https://aka.ms/exopowershell)。</span><span class="sxs-lookup"><span data-stu-id="a8355-164">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="a8355-165">使用**set-omeconfiguration** cmdlet, 如[set-omeconfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration)中所述。</span><span class="sxs-lookup"><span data-stu-id="a8355-165">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/Set-OMEConfiguration).</span></span> <span data-ttu-id="a8355-166">若要从 DisclaimerText、EmailText 和 PortalText 值中删除您的组织的标记自定义项, 请将该值设置为`""`一个空字符串。</span><span class="sxs-lookup"><span data-stu-id="a8355-166">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string,  `""`.</span></span> <span data-ttu-id="a8355-167">对于所有图像值 (如 "徽标"), 请将`"$null"`值设置为。</span><span class="sxs-lookup"><span data-stu-id="a8355-167">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

<span data-ttu-id="a8355-168">**加密自定义选项**</span><span class="sxs-lookup"><span data-stu-id="a8355-168">**Encryption customization options**</span></span>

<span data-ttu-id="a8355-169">**将加密体验的此功能还原到默认的文本和图片**</span><span class="sxs-lookup"><span data-stu-id="a8355-169">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="a8355-170">**使用这些命令**</span><span class="sxs-lookup"><span data-stu-id="a8355-170">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a8355-171">加密电子邮件随附的默认文本</span><span class="sxs-lookup"><span data-stu-id="a8355-171">Default text that accompanies encrypted email messages</span></span>  <br/> <span data-ttu-id="a8355-172">默认文本显示在说明的上方，以查看加密邮件</span><span class="sxs-lookup"><span data-stu-id="a8355-172">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -EmailText "<empty string>"` <br/> <span data-ttu-id="a8355-173">**示例：**</span><span class="sxs-lookup"><span data-stu-id="a8355-173">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
|<span data-ttu-id="a8355-174">包含加密邮件的电子邮件中的免责声明</span><span class="sxs-lookup"><span data-stu-id="a8355-174">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> DisclaimerText "<empty string>"` <br/> <span data-ttu-id="a8355-175">**示例：**</span><span class="sxs-lookup"><span data-stu-id="a8355-175">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
|<span data-ttu-id="a8355-176">显示在加密邮件查看门户顶部的文本</span><span class="sxs-lookup"><span data-stu-id="a8355-176">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -PortalText "<empty string>"` <br/> <span data-ttu-id="a8355-177">**将恢复为默认值的示例:**</span><span class="sxs-lookup"><span data-stu-id="a8355-177">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
|<span data-ttu-id="a8355-178">徽标</span><span class="sxs-lookup"><span data-stu-id="a8355-178">Logo</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -Image <"$null">` <br/> <span data-ttu-id="a8355-179">**将恢复为默认值的示例:**</span><span class="sxs-lookup"><span data-stu-id="a8355-179">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
|<span data-ttu-id="a8355-180">背景色</span><span class="sxs-lookup"><span data-stu-id="a8355-180">Background color</span></span>|`Set-OMEConfiguration -Identity <OMEConfigurationIdParameter> -BackgroundColor <"$null">` <br/> <span data-ttu-id="a8355-181">**将恢复为默认值的示例:**</span><span class="sxs-lookup"><span data-stu-id="a8355-181">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|

## <a name="create-an-exchange-mail-flow-rule-that-applies-custom-branding-to-encrypted-emails"></a><span data-ttu-id="a8355-182">创建对加密电子邮件应用自定义品牌打造的 Exchange 邮件流规则</span><span class="sxs-lookup"><span data-stu-id="a8355-182">Create an Exchange mail flow rule that applies custom branding to encrypted emails</span></span>

<span data-ttu-id="a8355-183">创建品牌模板后, 可以创建 Exchange 邮件流规则, 以根据特定条件应用该自定义品牌打造。</span><span class="sxs-lookup"><span data-stu-id="a8355-183">After you've created a branding template, you can create Exchange mail flow rules to apply that custom branding based on certain conditions.</span></span> <span data-ttu-id="a8355-184">此类规则将在以下情况下应用自定义品牌打造:</span><span class="sxs-lookup"><span data-stu-id="a8355-184">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="a8355-185">如果最终用户从 Outlook 或 web 上的 Outlook (以前称为 Outlook Web App) 客户端手动加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="a8355-185">If the email was manually encrypted by the end-user from the Outlook or Outlook on the web (formerly known as Outlook Web App) clients</span></span>

- <span data-ttu-id="a8355-186">如果电子邮件是由 Exchange 邮件流规则或 Office 365 数据丢失防护策略自动加密的</span><span class="sxs-lookup"><span data-stu-id="a8355-186">If the email was automatically encrypted by an Exchange Mail Flow rule or Office 365 Data Loss Prevention policy</span></span>

<span data-ttu-id="a8355-187">有关如何创建适用于加密的 Exchange 邮件流规则的信息, 请参阅[定义邮件流规则以在 Office 365 中加密电子邮件](define-mail-flow-rules-to-encrypt-email.md)。</span><span class="sxs-lookup"><span data-stu-id="a8355-187">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="a8355-188">在 web 浏览器中, 使用已被授予全局管理员权限的工作或学校帐户,[登录到 Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)。</span><span class="sxs-lookup"><span data-stu-id="a8355-188">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="a8355-189">选择 "**管理**" 磁贴。</span><span class="sxs-lookup"><span data-stu-id="a8355-189">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="a8355-190">在 Office 365 管理中心 中，选择" **管理中心**" \> " **Exchange**"。</span><span class="sxs-lookup"><span data-stu-id="a8355-190">In the Office 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="a8355-191">在 EAC 中, 转到 "**邮件流** \> **规则**", 然后选择 "**新建** ![" 图标](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **创建新规则**。</span><span class="sxs-lookup"><span data-stu-id="a8355-191">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="a8355-192">有关使用 EAC 的详细信息, 请参阅 exchange [Online 中的 exchange 管理中心](https://docs.microsoft.com/exchange/exchange-admin-center)。</span><span class="sxs-lookup"><span data-stu-id="a8355-192">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="a8355-193">在 "**名称**" 中, 键入规则的名称, 例如 "销售部门的品牌"。</span><span class="sxs-lookup"><span data-stu-id="a8355-193">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="a8355-194">在 "在**以下情况应用此规则**" "选择条件" 中, 选择**发件人位于组织内部**的条件以及在可用条件列表中所需的其他条件。</span><span class="sxs-lookup"><span data-stu-id="a8355-194">In **Apply this rule if** select a condition, select the condition **The sender is located inside the organization** as well as other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="a8355-195">例如, 您可能希望将特定品牌模板应用于:</span><span class="sxs-lookup"><span data-stu-id="a8355-195">For example, you might want to apply a particular branding template to:</span></span>

     - <span data-ttu-id="a8355-196">从财务部门的成员发送的所有加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="a8355-196">All encrypted emails sent from members of the finance department</span></span>
     - <span data-ttu-id="a8355-197">使用特定关键字 (如 "外部" 或 "合作伙伴") 发送的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="a8355-197">Encrypted emails sent with a certain keyword such as “External” or “Partner”</span></span>
     - <span data-ttu-id="a8355-198">发送到特定域的加密电子邮件</span><span class="sxs-lookup"><span data-stu-id="a8355-198">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="a8355-199">从**执行以下操作**, 选择 **"修改邮件安全性** > 对**OME 邮件应用自定义品牌打造**"。</span><span class="sxs-lookup"><span data-stu-id="a8355-199">From **Do the following**, select **Modify the message security** > **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="a8355-200">接下来, 从下拉菜单中选择您创建的品牌模板。</span><span class="sxs-lookup"><span data-stu-id="a8355-200">Next, from the drop-down, select a branding template from those that you created.</span></span>

8. <span data-ttu-id="a8355-201">Optional如果您希望邮件流规则还应用除自定义品牌的加密之外的加密, 请选择 **"\*\*\*\*修改邮件安全性**", 然后选择 "**应用 Office 365 邮件加密和权限保护**"。</span><span class="sxs-lookup"><span data-stu-id="a8355-201">(Optional) If you want the mail flow rule to also apply encryption in addition to the custom branding, From **Do the following**, select **Modify the message security** and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="a8355-202">从列表中选择一个 RMS 模板, 选择 "**保存**", 然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="a8355-202">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
     <span data-ttu-id="a8355-203">模板列表包含所有默认模板和选项, 以及您创建的用于 Office 365 的任何自定义模板。</span><span class="sxs-lookup"><span data-stu-id="a8355-203">The list of templates includes all default templates and options as well as any custom templates you've created for use by Office 365.</span></span> <span data-ttu-id="a8355-204">如果列表为空, 请确保已使用新功能设置了 Office 365 邮件加密, 如[设置新的 Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="a8355-204">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities as described in [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="a8355-205">有关默认模板的信息, 请参阅[配置和管理 Azure 信息保护的模板](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="a8355-205">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="a8355-206">有关 "**不要转发**" 选项的信息, 请参阅[电子邮件](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)的 "不要转发" 选项。</span><span class="sxs-lookup"><span data-stu-id="a8355-206">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="a8355-207">有关**仅加密**选项的信息, 请参阅[仅加密电子邮件选项](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)。</span><span class="sxs-lookup"><span data-stu-id="a8355-207">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

     <span data-ttu-id="a8355-208">如果要指定另一个操作, 可以选择 "**添加操作**"。</span><span class="sxs-lookup"><span data-stu-id="a8355-208">You can choose **add action** if you want to specify another action.</span></span>
