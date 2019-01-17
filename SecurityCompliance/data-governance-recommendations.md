---
title: 如何确定数据治理建议的内容
ms.author: brendonb
author: stephow-MSFT
manager: laurawi
ms.date: 1/15/2019
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Office 365 安全与合规中心根据你组织的当前设置提供数据治理建议，并允许你通过几次单击进行设置。其中一些建议会检测组织中的特定内容，然后提供管理该内容的建议步骤。例如，建议可能会检测包含业务关键内容的项目（如律师-客户特权或 NDA 信息），然后让你自动为这些项目应用保留标签，以确保根据需要对它们进行分类和保留。本主题列出了你可能会看到的数据治理建议，并介绍了为触发每条建议而检测的内容。
ms.openlocfilehash: a3f803105ea5c2626c8c2a26ad898df5f45af2f0
ms.sourcegitcommit: c7737903ff2e1d047682ee61f7ac21b0bdd1c6fd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "28263936"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="4e9a1-106">如何确定数据治理建议的内容</span><span class="sxs-lookup"><span data-stu-id="4e9a1-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="4e9a1-p102">Office 365 安全与合规中心根据你组织的当前设置提供数据治理建议，并允许你通过几次单击进行设置。其中一些建议会检测组织中的特定内容，然后提供管理该内容的建议步骤。例如，建议可能会检测包含业务关键内容的项目（如律师-客户特权或 NDA 信息），然后让你自动为这些项目应用保留标签，以确保根据需要对它们进行分类和保留。</span><span class="sxs-lookup"><span data-stu-id="4e9a1-p102">The Office 365 Security & Compliance Center provides recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they’re classified and retained as needed.</span></span>

<span data-ttu-id="4e9a1-110">本主题列出了你可能会看到的数据治理建议，并介绍了为触发每条建议而检测的内容。</span><span class="sxs-lookup"><span data-stu-id="4e9a1-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="4e9a1-111">清理语音邮件</span><span class="sxs-lookup"><span data-stu-id="4e9a1-111">Clean up voicemail</span></span>

<span data-ttu-id="4e9a1-p103">在用户邮箱中检测到标识为“语音邮件”的邮件类型的电子邮件时，将显示此建议。详细了解 [Exchange 中的邮件属性](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange)。</span><span class="sxs-lookup"><span data-stu-id="4e9a1-p103">This recommendation appears when email messages identified as the message type ‘voicemail’ are detected in users’ mailboxes. Learn more about [message properties in Exchange](https://docs.microsoft.com/en-us/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="4e9a1-114">标记律师-客户特权内容</span><span class="sxs-lookup"><span data-stu-id="4e9a1-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="4e9a1-115">当满足以下任一条件时，将显示此建议。</span><span class="sxs-lookup"><span data-stu-id="4e9a1-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="4e9a1-116">在电子邮件正文中检测到以下关键字的任何组合：</span><span class="sxs-lookup"><span data-stu-id="4e9a1-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="4e9a1-117">ACP</span><span class="sxs-lookup"><span data-stu-id="4e9a1-117">ACP</span></span>
    - <span data-ttu-id="4e9a1-118">律师客户特权</span><span class="sxs-lookup"><span data-stu-id="4e9a1-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="4e9a1-119">律师-客户特权</span><span class="sxs-lookup"><span data-stu-id="4e9a1-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="4e9a1-120">律师-客户特权的</span><span class="sxs-lookup"><span data-stu-id="4e9a1-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="4e9a1-121">在 SharePoint 或 OneDrive 文件中检测到以下关键字的任意组合：</span><span class="sxs-lookup"><span data-stu-id="4e9a1-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="4e9a1-122">ACP</span><span class="sxs-lookup"><span data-stu-id="4e9a1-122">ACP</span></span>
    - <span data-ttu-id="4e9a1-123">律师客户特权\*</span><span class="sxs-lookup"><span data-stu-id="4e9a1-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="4e9a1-124">AC 特权</span><span class="sxs-lookup"><span data-stu-id="4e9a1-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="4e9a1-125">保留音频文件</span><span class="sxs-lookup"><span data-stu-id="4e9a1-125">Retain audio files</span></span>

<span data-ttu-id="4e9a1-126">在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。</span><span class="sxs-lookup"><span data-stu-id="4e9a1-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="4e9a1-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="4e9a1-127">MP3 (default)</span></span>
- <span data-ttu-id="4e9a1-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="4e9a1-128">WMA</span></span>
- <span data-ttu-id="4e9a1-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="4e9a1-129">WAV</span></span>
- <span data-ttu-id="4e9a1-130">.RA</span><span class="sxs-lookup"><span data-stu-id="4e9a1-130">.RA</span></span>
- <span data-ttu-id="4e9a1-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="4e9a1-131">RAM</span></span>
- <span data-ttu-id="4e9a1-132">.RM</span><span class="sxs-lookup"><span data-stu-id="4e9a1-132">rm</span></span>
- <span data-ttu-id="4e9a1-133">.MID</span><span class="sxs-lookup"><span data-stu-id="4e9a1-133">.MID</span></span>
- <span data-ttu-id="4e9a1-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="4e9a1-134">.OGG</span></span>
- <span data-ttu-id="4e9a1-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="4e9a1-135">.AIFF</span></span>
- <span data-ttu-id="4e9a1-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="4e9a1-136">.PCM</span></span>
- <span data-ttu-id="4e9a1-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="4e9a1-137">.AAC</span></span>
- <span data-ttu-id="4e9a1-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="4e9a1-138">.FLAC</span></span>
- <span data-ttu-id="4e9a1-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="4e9a1-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="4e9a1-140">保留 CAD 文件</span><span class="sxs-lookup"><span data-stu-id="4e9a1-140">Retain CAD files</span></span>

<span data-ttu-id="4e9a1-141">在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。</span><span class="sxs-lookup"><span data-stu-id="4e9a1-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="4e9a1-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="4e9a1-142">.3DXML</span></span>
- <span data-ttu-id="4e9a1-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="4e9a1-143">.ACIS</span></span>
- <span data-ttu-id="4e9a1-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="4e9a1-144">ARC
</span></span>
- <span data-ttu-id="4e9a1-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="4e9a1-145">asm</span></span>
- <span data-ttu-id="4e9a1-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="4e9a1-146">cat</span></span>
- <span data-ttu-id="4e9a1-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="4e9a1-147">.CGR</span></span>
- <span data-ttu-id="4e9a1-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="4e9a1-148">DW</span></span>
- <span data-ttu-id="4e9a1-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="4e9a1-149">Dx</span></span>
- <span data-ttu-id="4e9a1-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="4e9a1-150">.EDRW</span></span>
- <span data-ttu-id="4e9a1-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="4e9a1-151">.IAM</span></span>
- <span data-ttu-id="4e9a1-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="4e9a1-152">.IGES</span></span>
- <span data-ttu-id="4e9a1-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="4e9a1-153">.IGS</span></span>
- <span data-ttu-id="4e9a1-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="4e9a1-154">.IPT</span></span>
- <span data-ttu-id="4e9a1-155">.JT</span><span class="sxs-lookup"><span data-stu-id="4e9a1-155">.JT</span></span>
- <span data-ttu-id="4e9a1-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="4e9a1-156">.MF1</span></span>
- <span data-ttu-id="4e9a1-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="4e9a1-157">.NEU</span></span>
- <span data-ttu-id="4e9a1-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="4e9a1-158">.PAR</span></span>
- <span data-ttu-id="4e9a1-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="4e9a1-159">.PKG</span></span>
- <span data-ttu-id="4e9a1-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="4e9a1-160">PRC
</span></span>
- <span data-ttu-id="4e9a1-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="4e9a1-161">.PRT</span></span>
- <span data-ttu-id="4e9a1-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="4e9a1-162">.PSM</span></span>
- <span data-ttu-id="4e9a1-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="4e9a1-163">.PWD</span></span>
- <span data-ttu-id="4e9a1-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="4e9a1-164">.SLD\*</span></span>
- <span data-ttu-id="4e9a1-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="4e9a1-165">Step</span></span>
- <span data-ttu-id="4e9a1-166">.STL</span><span class="sxs-lookup"><span data-stu-id="4e9a1-166">.STL</span></span>
- <span data-ttu-id="4e9a1-167">.STP</span><span class="sxs-lookup"><span data-stu-id="4e9a1-167">.STP</span></span>
- <span data-ttu-id="4e9a1-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="4e9a1-168">.U3D</span></span>
- <span data-ttu-id="4e9a1-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="4e9a1-169">.UNV</span></span>
- <span data-ttu-id="4e9a1-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="4e9a1-170">.VRML</span></span>
- <span data-ttu-id="4e9a1-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="4e9a1-171">.WRL</span></span>
- <span data-ttu-id="4e9a1-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="4e9a1-172">X</span></span>
- <span data-ttu-id="4e9a1-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="4e9a1-173">.XAS</span></span>
- <span data-ttu-id="4e9a1-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="4e9a1-174">.XMT\*</span></span>
- <span data-ttu-id="4e9a1-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="4e9a1-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="4e9a1-176">保留图像文件</span><span class="sxs-lookup"><span data-stu-id="4e9a1-176">Retain image files</span></span>

<span data-ttu-id="4e9a1-177">在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。</span><span class="sxs-lookup"><span data-stu-id="4e9a1-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="4e9a1-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="4e9a1-178">JPEG</span></span>
- <span data-ttu-id="4e9a1-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="4e9a1-179">GIF</span></span>
- <span data-ttu-id="4e9a1-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="4e9a1-180">tif</span></span>
- <span data-ttu-id="4e9a1-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="4e9a1-181">.bmp</span></span>
- <span data-ttu-id="4e9a1-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="4e9a1-182">PNG</span></span>
- <span data-ttu-id="4e9a1-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="4e9a1-183">.RAW</span></span>
- <span data-ttu-id="4e9a1-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="4e9a1-184">.PSD</span></span>
- <span data-ttu-id="4e9a1-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="4e9a1-185">PSP
</span></span>
- <span data-ttu-id="4e9a1-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="4e9a1-186">.jpg</span></span>
- <span data-ttu-id="4e9a1-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="4e9a1-187">.EXIF</span></span>
- <span data-ttu-id="4e9a1-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="4e9a1-188">PPM capabilities</span></span>
- <span data-ttu-id="4e9a1-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="4e9a1-189">.PGM</span></span>
- <span data-ttu-id="4e9a1-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="4e9a1-190">.PBM</span></span>
- <span data-ttu-id="4e9a1-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="4e9a1-191">.PNM</span></span>
- <span data-ttu-id="4e9a1-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="4e9a1-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="4e9a1-193">保留 NDA 内容</span><span class="sxs-lookup"><span data-stu-id="4e9a1-193">Retain NDA content</span></span> 

<span data-ttu-id="4e9a1-194">当满足以下任一条件时，将显示此建议。</span><span class="sxs-lookup"><span data-stu-id="4e9a1-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="4e9a1-195">在电子邮件正文中检测到以下关键字的任何组合：</span><span class="sxs-lookup"><span data-stu-id="4e9a1-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="4e9a1-196">NDA</span><span class="sxs-lookup"><span data-stu-id="4e9a1-196">NDA</span></span>
    - <span data-ttu-id="4e9a1-197">“保密性协议”</span><span class="sxs-lookup"><span data-stu-id="4e9a1-197">“Non-Disclosure Agreement”</span></span>
    - <span data-ttu-id="4e9a1-198">“保密协议”</span><span class="sxs-lookup"><span data-stu-id="4e9a1-198">“Non Disclosure Agreement”</span></span>

- <span data-ttu-id="4e9a1-199">在 SharePoint 或 OneDrive 中的 .PDF 或 .DOC 文件中检测到以下关键字的任意组合：</span><span class="sxs-lookup"><span data-stu-id="4e9a1-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="4e9a1-200">NDA</span><span class="sxs-lookup"><span data-stu-id="4e9a1-200">NDA</span></span>
    - <span data-ttu-id="4e9a1-201">保密协议</span><span class="sxs-lookup"><span data-stu-id="4e9a1-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="4e9a1-202">保留软件开发文件</span><span class="sxs-lookup"><span data-stu-id="4e9a1-202">Retain software development files</span></span>

<span data-ttu-id="4e9a1-203">在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。</span><span class="sxs-lookup"><span data-stu-id="4e9a1-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="4e9a1-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="4e9a1-204">.ASAX</span></span>
- <span data-ttu-id="4e9a1-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="4e9a1-205">asm</span></span>
- <span data-ttu-id="4e9a1-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="4e9a1-206">asp</span></span>
- <span data-ttu-id="4e9a1-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="4e9a1-207">bat</span></span>
- <span data-ttu-id="4e9a1-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="4e9a1-208">.config</span></span>
- <span data-ttu-id="4e9a1-209">.CS</span><span class="sxs-lookup"><span data-stu-id="4e9a1-209">cs</span></span>
- <span data-ttu-id="4e9a1-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="4e9a1-210">CSS</span></span>
- <span data-ttu-id="4e9a1-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="4e9a1-211">.DISCO</span></span>
- <span data-ttu-id="4e9a1-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="4e9a1-212">htm</span></span>
- <span data-ttu-id="4e9a1-213">.INC</span><span class="sxs-lookup"><span data-stu-id="4e9a1-213">.INC</span></span>
- <span data-ttu-id="4e9a1-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="4e9a1-214">.JAD</span></span>
- <span data-ttu-id="4e9a1-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="4e9a1-215">Java</span></span>
- <span data-ttu-id="4e9a1-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="4e9a1-216">.js</span></span>
- <span data-ttu-id="4e9a1-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="4e9a1-217">\lib</span></span>
- <span data-ttu-id="4e9a1-218">.O</span><span class="sxs-lookup"><span data-stu-id="4e9a1-218">O</span></span>
- <span data-ttu-id="4e9a1-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="4e9a1-219">PHP</span></span>
- <span data-ttu-id="4e9a1-220">.RC</span><span class="sxs-lookup"><span data-stu-id="4e9a1-220">.RC</span></span>
- <span data-ttu-id="4e9a1-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="4e9a1-221">\*.resx</span></span>
- <span data-ttu-id="4e9a1-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="4e9a1-222">.RPT</span></span>
- <span data-ttu-id="4e9a1-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="4e9a1-223">RSS</span></span>
- <span data-ttu-id="4e9a1-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="4e9a1-224">.SCPT</span></span>
- <span data-ttu-id="4e9a1-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="4e9a1-225">.SRC</span></span>
- <span data-ttu-id="4e9a1-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="4e9a1-226">.vb</span></span>
- <span data-ttu-id="4e9a1-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="4e9a1-227">.wsf</span></span>
- <span data-ttu-id="4e9a1-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="4e9a1-228">.XCODEPROJ</span></span>
- <span data-ttu-id="4e9a1-229">.XML</span><span class="sxs-lookup"><span data-stu-id="4e9a1-229">XML</span></span>
- <span data-ttu-id="4e9a1-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="4e9a1-230">.XSD</span></span>
- <span data-ttu-id="4e9a1-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="4e9a1-231">XSL</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="4e9a1-232">保留视频文件</span><span class="sxs-lookup"><span data-stu-id="4e9a1-232">Retain video files</span></span>

<span data-ttu-id="4e9a1-233">在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。</span><span class="sxs-lookup"><span data-stu-id="4e9a1-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="4e9a1-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="4e9a1-234">.AVCHD</span></span>
- <span data-ttu-id="4e9a1-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="4e9a1-235">avi</span></span>
- <span data-ttu-id="4e9a1-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="4e9a1-236">.FLV</span></span>
- <span data-ttu-id="4e9a1-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="4e9a1-237">.MOV</span></span>
- <span data-ttu-id="4e9a1-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="4e9a1-238">.MP2V</span></span>
- <span data-ttu-id="4e9a1-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="4e9a1-239">.MP4</span></span>
- <span data-ttu-id="4e9a1-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="4e9a1-240">.MP4V</span></span>
- <span data-ttu-id="4e9a1-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="4e9a1-241">.MPE</span></span>
- <span data-ttu-id="4e9a1-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="4e9a1-242">MPEG</span></span>
- <span data-ttu-id="4e9a1-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="4e9a1-243">.MPEG1</span></span>
- <span data-ttu-id="4e9a1-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="4e9a1-244">.MPEG2</span></span>
- <span data-ttu-id="4e9a1-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="4e9a1-245">.MPEG4</span></span>
- <span data-ttu-id="4e9a1-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="4e9a1-246">.MPG</span></span>
- <span data-ttu-id="4e9a1-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="4e9a1-247">.MPG2</span></span>
- <span data-ttu-id="4e9a1-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="4e9a1-248">.MPG4</span></span>
- <span data-ttu-id="4e9a1-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="4e9a1-249">.WMV</span></span>
- <span data-ttu-id="4e9a1-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="4e9a1-250">.XMV</span></span>
