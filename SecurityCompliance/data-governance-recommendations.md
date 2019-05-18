---
title: 如何确定数据治理建议的内容
ms.author: brendonb
author: stephow-MSFT
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Office 365 安全与合规中心根据你组织的当前设置提供数据治理建议，并允许你通过几次单击进行设置。其中一些建议会检测组织中的特定内容，然后提供管理该内容的建议步骤。例如，建议可能会检测包含业务关键内容的项目（如律师-客户特权或 NDA 信息），然后让你自动为这些项目应用保留标签，以确保根据需要对它们进行分类和保留。本主题列出了你可能会看到的数据治理建议，并介绍了为触发每条建议而检测的内容。
ms.openlocfilehash: 3d96b7c15d5b6a0f6ec3bbf467bd8a1099af559a
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34153704"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a>如何确定数据治理建议的内容

Office 365 安全与合规中心根据你组织的当前设置提供数据治理建议，并允许你通过几次单击进行设置。其中一些建议会检测组织中的特定内容，然后提供管理该内容的建议步骤。例如，建议可能会检测包含业务关键内容的项目（如律师-客户特权或 NDA 信息），然后让你自动为这些项目应用保留标签，以确保根据需要对它们进行分类和保留。

本主题列出了你可能会看到的数据治理建议，并介绍了为触发每条建议而检测的内容。

## <a name="clean-up-voicemail"></a>清理语音邮件

在用户邮箱中检测到标识为“语音邮件”的邮件类型的电子邮件时，将显示此建议。详细了解 [Exchange 中的邮件属性](https://docs.microsoft.com/zh-CN/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange)。

## <a name="label-attorney-client-privilege-content"></a>标记律师-客户特权内容 

当满足以下任一条件时，将显示此建议。

- 在电子邮件正文中检测到以下关键字的任何组合：
    - ACP
    - 律师客户特权
    - 律师-客户特权
    - 律师-客户特权的

- 在 SharePoint 或 OneDrive 文件中检测到以下关键字的任意组合：
    - ACP
    - 律师客户特权*
    - AC 特权

## <a name="retain-audio-files"></a>保留音频文件

在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。

- .MP3
- .WMA
- .WAV
- .RA
- .RAM
- .RM
- .MID
- .OGG
- .AIFF
- .PCM
- .AAC
- .FLAC
- .ALAC

## <a name="retain-cad-files"></a>保留 CAD 文件

在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。

- .3DXML
- .ACIS
- .ARC
- .ASM
- .CAT*
- .CGR
- .DW*
- .DX*
- .EDRW
- .IAM
- .IGES
- .IGS
- .IPT
- .JT
- .MF1
- .NEU
- .PAR
- .PKG
- .PRC
- .PRT
- .PSM
- .PWD
- .SLD*
- .STEP
- .STL
- .STP
- .U3D
- .UNV
- .VRML
- .WRL
- .X_*
- .XAS
- .XMT*
- .XPR

## <a name="retain-image-files"></a>保留图像文件

在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。

- .JPEG
- .GIF
- .TIF*
- .BMP
- .PNG
- .RAW
- .PSD
- .PSP
- .JPG
- .EXIF
- .PPM
- .PGM
- .PBM
- .PNM
- .WEBP

## <a name="retain-nda-content"></a>保留 NDA 内容 

当满足以下任一条件时，将显示此建议。

- 在电子邮件正文中检测到以下关键字的任何组合：
    - NDA
    - “保密性协议”
    - “保密协议”

- 在 SharePoint 或 OneDrive 中的 .PDF 或 .DOC 文件中检测到以下关键字的任意组合：
    - NDA
    - 保密协议

## <a name="retain-software-development-files"></a>保留软件开发文件

在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。

- .ASAX
- .ASM
- .ASP*
- .BAT
- .CONFIG
- .CS
- .CSS
- .DISCO
- .HTM*
- .INC
- .JAD
- .JAVA
- .JS*
- .LIB
- .O
- .PHP
- .RC
- .RESX
- .RPT
- .RSS
- .SCPT
- .SRC
- .VB*
- .WSF
- .XCODEPROJ
- .XML
- .XSD
- .XSL*

## <a name="retain-video-files"></a>保留视频文件

在 SharePoint 或 OneDrive 中检测到以下任何文件类型时，将显示此建议。

- .AVCHD
- .AVI
- .FLV
- .MOV
- .MP2V
- .MP4
- .MP4V
- .MPE
- .MPEG
- .MPEG1
- .MPEG2
- .MPEG4
- .MPG
- .MPG2
- .MPG4
- .WMV
- .XMV
