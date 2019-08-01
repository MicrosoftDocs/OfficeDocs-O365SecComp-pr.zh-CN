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
ms.openlocfilehash: eb8c84d696a05f86246a512f1867d8efc98881a0
ms.sourcegitcommit: 73dcdafb15b462223d1a670c781db260eb73c2f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2019
ms.locfileid: "36048085"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a>解决高级电子数据展示中的 AzCopy

加载非 Office 365 数据或文档以在高级电子数据展示中进行错误修正时, 用户界面提供了一个 Azure AzCopy 命令, 其中包含参数以及要上载的文件的位置和 Azure 存储文件将上载到的位置。 若要上传文档, 请复制此命令, 然后在本地计算机上的命令提示符处运行它。  下面的屏幕截图显示了 AzCopy 命令的示例:

![上传非 Office 365 文件](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

在运行时, 通常提供的命令是有效的。 但是, 在某些情况下, 所显示的命令将无法成功运行。 以下是几个可能的原因。

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a>本地计算机上未安装支持的 AzCopy 版本

目前, 您必须使用 AzCopy？8.1 在高级电子数据展示中加载非 Office 365 数据。 如果您不使用 AzCopy ue-v 8.1, 则在前面的屏幕截图中显示的 "**上载文件**" 页上显示的 AzCopy 命令将返回错误。 若要安装此版本, 请参阅[在 Windows 上使用 AzCopy ue-v 8.1 传输数据](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)。

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a>AzCopy 未安装在本地计算机上, 或者未安装在默认位置

如果未安装 AzCopy 或安装在默认安装位置之外的某个位置 (即 " `%ProgramFiles(x86)%`)", 则在运行 AzCopy 命令时, 可能会收到以下错误消息:

    The system cannot find the path specified.

如果本地计算机上未安装 AzCopy, 则可以从[此处](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)安装。 请务必将其安装在默认位置。

如果已安装 AzCopy, 但其安装在与默认位置不同的位置, 则可以复制命令, 将其粘贴到文本文件, 然后将路径更改为安装 AzCopy 的位置。 例如, 如果 Azcopy 位于`%ProgramFiles%`, 则可以将命令的第一部分从`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe`更改为。 `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` 在进行此更改后, 从文本文件中复制该文件, 然后运行命令提示符。

> [!TIP]
> 如果 AzCopy 安装在默认安装位置之外的其他位置, 请考虑将其卸载, 然后在默认位置重新安装它。 这将有助于防止将来出现此问题。
