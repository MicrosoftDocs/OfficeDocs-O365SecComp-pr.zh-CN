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
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="d56c7-102">解决高级电子数据展示中的 AzCopy</span><span class="sxs-lookup"><span data-stu-id="d56c7-102">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="d56c7-103">加载非 Office 365 数据或文档以在高级电子数据展示中进行错误修正时, 用户界面提供了一个 Azure AzCopy 命令, 其中包含参数以及要上载的文件的位置和 Azure 存储文件将上载到的位置。</span><span class="sxs-lookup"><span data-stu-id="d56c7-103">When loading non-Office 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="d56c7-104">若要上传文档, 请复制此命令, 然后在本地计算机上的命令提示符处运行它。</span><span class="sxs-lookup"><span data-stu-id="d56c7-104">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="d56c7-105">下面的屏幕截图显示了 AzCopy 命令的示例:</span><span class="sxs-lookup"><span data-stu-id="d56c7-105">The follow screenshot shows an example of an AzCopy command:</span></span>

![上传非 Office 365 文件](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="d56c7-107">在运行时, 通常提供的命令是有效的。</span><span class="sxs-lookup"><span data-stu-id="d56c7-107">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="d56c7-108">但是, 在某些情况下, 所显示的命令将无法成功运行。</span><span class="sxs-lookup"><span data-stu-id="d56c7-108">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="d56c7-109">以下是几个可能的原因。</span><span class="sxs-lookup"><span data-stu-id="d56c7-109">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="d56c7-110">本地计算机上未安装支持的 AzCopy 版本</span><span class="sxs-lookup"><span data-stu-id="d56c7-110">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="d56c7-111">目前, 您必须使用 AzCopy？8.1 在高级电子数据展示中加载非 Office 365 数据。</span><span class="sxs-lookup"><span data-stu-id="d56c7-111">At this time, you must use AzCopy v8.1 to load non-Office 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="d56c7-112">如果您不使用 AzCopy ue-v 8.1, 则在前面的屏幕截图中显示的 "**上载文件**" 页上显示的 AzCopy 命令将返回错误。</span><span class="sxs-lookup"><span data-stu-id="d56c7-112">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="d56c7-113">若要安装此版本, 请参阅[在 Windows 上使用 AzCopy ue-v 8.1 传输数据](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="d56c7-113">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="d56c7-114">AzCopy 未安装在本地计算机上, 或者未安装在默认位置</span><span class="sxs-lookup"><span data-stu-id="d56c7-114">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="d56c7-115">如果未安装 AzCopy 或安装在默认安装位置之外的某个位置 (即 " `%ProgramFiles(x86)%`)", 则在运行 AzCopy 命令时, 可能会收到以下错误消息:</span><span class="sxs-lookup"><span data-stu-id="d56c7-115">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

    The system cannot find the path specified.

<span data-ttu-id="d56c7-116">如果本地计算机上未安装 AzCopy, 则可以从[此处](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy)安装。</span><span class="sxs-lookup"><span data-stu-id="d56c7-116">If AzCopy isn't installed on the local computer, you can install from [here](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="d56c7-117">请务必将其安装在默认位置。</span><span class="sxs-lookup"><span data-stu-id="d56c7-117">Be sure to install it in the default location.</span></span>

<span data-ttu-id="d56c7-118">如果已安装 AzCopy, 但其安装在与默认位置不同的位置, 则可以复制命令, 将其粘贴到文本文件, 然后将路径更改为安装 AzCopy 的位置。</span><span class="sxs-lookup"><span data-stu-id="d56c7-118">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="d56c7-119">例如, 如果 Azcopy 位于`%ProgramFiles%`, 则可以将命令的第一部分从`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe`更改为。 `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`</span><span class="sxs-lookup"><span data-stu-id="d56c7-119">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="d56c7-120">在进行此更改后, 从文本文件中复制该文件, 然后运行命令提示符。</span><span class="sxs-lookup"><span data-stu-id="d56c7-120">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="d56c7-121">如果 AzCopy 安装在默认安装位置之外的其他位置, 请考虑将其卸载, 然后在默认位置重新安装它。</span><span class="sxs-lookup"><span data-stu-id="d56c7-121">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="d56c7-122">这将有助于防止将来出现此问题。</span><span class="sxs-lookup"><span data-stu-id="d56c7-122">This will help prevent this issue in the future.</span></span>
