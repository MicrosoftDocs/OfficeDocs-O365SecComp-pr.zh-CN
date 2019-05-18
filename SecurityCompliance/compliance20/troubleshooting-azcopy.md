---
title: 解决高级电子数据展示中的 AzCopy
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 2c8378cf7b9bd21f901b1babbebdcb0b69a8ed73
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34151514"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>解决高级电子数据展示中的 AzCopy

加载非 Office 365 数据或文档以在高级电子数据展示中进行错误修正时, 用户界面提供了一个 Azure AzCopy 命令, 其中包含参数以及要上载的文件的位置和 Azure 存储文件将上载到的位置。 若要上传文档, 请复制此命令, 然后在本地计算机上的命令提示符处运行它。  下面的屏幕截图显示了 AzCopy 命令的示例:

![上传非 Office 365 文件](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

在大多数情况下, 在运行时提供的命令将运行。 但是, 在某些情况下, 所显示的命令将无法成功运行。 以下是几个可能的原因。

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy 未安装在本地计算机上, 或者未安装在默认位置

如果未安装 AzCopy 或安装在默认安装位置之外的某个位置 (即 " `%ProgramFiles(x86)%`)", 则在运行 AzCopy 命令时, 可能会收到以下错误消息:

    The system cannot find the path specified.

如果未在本地计算机上安装 AzCopy, 则可以从此处安装 (请务必将其安装在默认位置): [https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。


如果安装了 AzCopy, 但它安装在与默认位置不同的位置, 则可以复制命令, 将其粘贴到文本文件, 然后将路径更改为实际安装 AzCopy 的位置。 例如, 如果 Azcopy 位于`%ProgramFiles%`, 则可以将命令的第一部分从`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe`更改为。 `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` 在进行此更改后, 从文本文件中复制该文件, 然后运行命令提示符。

> [!TIP]
> 如果 AzCopy 安装在默认安装位置之外的其他位置, 请考虑将其卸载, 然后在默认位置重新安装它。 这将有助于防止将来出现此问题。