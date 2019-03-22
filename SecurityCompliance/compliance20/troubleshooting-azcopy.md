---
title: AzCopy 中的疑难解答高级电子数据展示 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: o365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 9711bee4ec9a61510b47568df37dfd3135e1e00c
ms.sourcegitcommit: cf9d9b545a7c153d314aa9c08c7fb16fcd785b3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2019
ms.locfileid: "30742494"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery-preview"></a><span data-ttu-id="0f489-102">AzCopy 中的疑难解答高级电子数据展示 (预览)</span><span class="sxs-lookup"><span data-stu-id="0f489-102">Troubleshoot AzCopy in Advanced eDiscovery (Preview)</span></span>

<span data-ttu-id="0f489-103">在高级电子数据展示 (预览版) 中加载非 Office 365 数据或文档以进行错误修正时, 用户界面提供了一个 Azure AzCopy 命令, 其中包含一些参数, 其中存储了要上载的文件的位置和 Azure文件将上载到的存储位置。</span><span class="sxs-lookup"><span data-stu-id="0f489-103">When loading non-Office 365 data or documents for error remediation in Advanced eDiscovery (Preview), the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="0f489-104">若要上传文档, 请复制此命令, 然后在本地计算机上的命令提示符处运行它。</span><span class="sxs-lookup"><span data-stu-id="0f489-104">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="0f489-105">下面的屏幕截图显示了 AzCopy 命令的示例:</span><span class="sxs-lookup"><span data-stu-id="0f489-105">The follow screenshot shows an example of an AzCopy command:</span></span>

![上传非 Office 365 文件](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="0f489-107">在大多数情况下, 在运行时提供的命令将运行。</span><span class="sxs-lookup"><span data-stu-id="0f489-107">In most cases, the command that's provided will work when you run it.</span></span> <span data-ttu-id="0f489-108">但是, 在某些情况下, 所显示的命令将无法成功运行。</span><span class="sxs-lookup"><span data-stu-id="0f489-108">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="0f489-109">以下是几个可能的原因。</span><span class="sxs-lookup"><span data-stu-id="0f489-109">Here's a few possible reasons.</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="0f489-110">AzCopy 未安装在本地计算机上, 或者未安装在默认位置</span><span class="sxs-lookup"><span data-stu-id="0f489-110">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="0f489-111">如果未安装 AzCopy 或安装在默认安装位置之外的某个位置 (即 " `%ProgramFiles(x86)%`)", 则在运行 AzCopy 命令时, 可能会收到以下错误消息:</span><span class="sxs-lookup"><span data-stu-id="0f489-111">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

    The system cannot find the path specified.

<span data-ttu-id="0f489-112">如果未在本地计算机上安装 AzCopy, 则可以从此处安装 (请务必将其安装在默认位置): [https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy)。</span><span class="sxs-lookup"><span data-stu-id="0f489-112">If AzCopy isn't install on the local computer, you can install from here (being sure to install it in the default location): [https://docs.microsoft.com/azure/storage/common/storage-use-azcopy](https://docs.microsoft.com/azure/storage/common/storage-use-azcopy).</span></span>


<span data-ttu-id="0f489-113">如果安装了 AzCopy, 但它安装在与默认位置不同的位置, 则可以复制命令, 将其粘贴到文本文件, 然后将路径更改为实际安装 AzCopy 的位置。</span><span class="sxs-lookup"><span data-stu-id="0f489-113">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is actually installed.</span></span> <span data-ttu-id="0f489-114">例如, 如果 Azcopy 位于`%ProgramFiles%`, 则可以将命令的第一部分从`%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe`更改为。 `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`</span><span class="sxs-lookup"><span data-stu-id="0f489-114">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="0f489-115">在进行此更改后, 从文本文件中复制该文件, 然后运行命令提示符。</span><span class="sxs-lookup"><span data-stu-id="0f489-115">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="0f489-116">如果 AzCopy 安装在默认安装位置之外的其他位置, 请考虑将其卸载, 然后在默认位置重新安装它。</span><span class="sxs-lookup"><span data-stu-id="0f489-116">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="0f489-117">这将有助于防止将来出现此问题。</span><span class="sxs-lookup"><span data-stu-id="0f489-117">This will help prevent this issue in the future.</span></span>