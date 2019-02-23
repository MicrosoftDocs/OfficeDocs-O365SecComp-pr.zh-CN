---
title: 提高导出 Office 365 中的电子数据展示搜索结果时的下载速度
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: 了解如何配置 Windows 注册表, 以便在从 Office 365 安全&amp;合规性中心和 office 365 高级电子数据展示中下载搜索结果和搜索数据时增加数据吞吐量。
ms.openlocfilehash: bafe9eda98b411472098770e4178748eb84f8afd
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30216242"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a>提高导出 Office 365 中的电子数据展示搜索结果时的下载速度

当您使用 office 365 电子数据展示导出工具在 office 365 安全&amp;合规中心中下载内容搜索的结果或从 office 365 高级电子数据展示下载数据时, 该工具将启动一定数量的并发导出将数据下载到本地计算机的操作。默认情况下, 并发操作数设置为要用于下载数据的计算机中的核心数的8倍。例如, 如果您有一台双核计算机 (即一个芯片上有两个中央处理单元), 则并发导出操作的默认数量为16个。若要增加数据传输吞吐量并加快下载过程, 可以通过在用于下载搜索结果的计算机上配置 Windows 注册表设置来增加并发操作的数量。若要加快下载过程, 建议您首先设置24个并发操作。
  
如果通过低带宽网络下载搜索结果, 则增加此设置可能会产生负面影响。或者, 可以将设置增加到高带宽网络 (最大并发操作数为 512) 中的24个并发操作。配置此注册表设置后, 您可能需要将其更改为为您的环境找到最佳的并发操作数。
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a>创建注册表设置以更改导出数据时的并发操作的数量

在您将用于从安全&amp;合规中心或高级电子数据展示中的数据下载搜索结果的计算机上执行以下过程。
  
1. 如果 Office 365 电子数据展示导出工具处于打开状态, 则将其关闭。 
    
2. 使用文件名后缀 .reg 将以下文本保存到窗口注册表文件;例如, ConcurrentOperations。 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    如前所述, 我们建议您从24个并发操作开始, 然后根据需要更改此设置。
    
3. 在 Windows 资源管理器中, 单击或双击您在上一步中创建的 .reg 文件。
    
4. 在 "用户访问控制" 窗口中, 单击 **"是"** 以让注册表编辑器进行更改。 
    
5. 当系统提示您继续时, 请单击 **"是"**。
    
    注册表编辑器将显示一条消息, 指出已成功将设置添加到注册表中。
    
6. 您可以重复步骤 2-5 以更改`DownloadConcurrency`注册表设置的值。 
    
    > [!IMPORTANT]
    > 在创建或更改`DownloadConcurrency`注册表设置后, 请确保为要下载的搜索结果或数据重新创建一个新的导出作业或重新启动现有的导出作业。有关更多详细信息, 请参阅[详细信息](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo)部分。 
  
## <a name="more-information"></a>更多信息

- 首次运行您在此过程中创建的 .reg 文件时, 会创建一个新的注册表项。然后, `DownloadConcurrency`每次更改并重新运行 .reg 编辑文件时, 都会编辑注册表设置。 
    
- Office 365 电子数据展示导出工具使用[Azure AzCopy 实用工具](https://go.microsoft.com/fwlink/?linkid=849949)从安全&amp;合规性中心或从高级电子数据展示下载搜索数据。配置`DownloadConcurrency`注册表设置类似于在运行 AzCopy 实用工具时使用 **/NC**参数。因此, 的`"DownloadConcurrency=24"`注册表设置与使用 AzCopy 实用程序的参数值`/NC:24`具有相同的效果。 
    
- 如果您停止当前正在进行的导出下载, 然后重新启动它 (通过再次尝试下载搜索结果), Office 365 电子数据展示导出工具将尝试恢复相同的下载。因此, 如果你开始下载, 请先停止它, 然后更改`DownloadConcurrency`注册表设置, 如果重新启动它 (单击 "**下载导出结果**"), 下载可能会失败。这是因为导出工具将尝试使用无效的设置来恢复以前的下载, 因为您更改了注册表设置。
    
    因此, 在更改`DownloadConcurrency`注册表设置后, 请务必在安全&amp;合规中心中重新启动导出作业 (通过单击 "**重新启动导出**")。然后, 您可以下载导出的结果。有关导出搜索结果和数据的详细信息, 请参阅:
    
  - [从 Office 365 安全&amp;合规中心导出内容搜索结果](export-search-results.md)
    
  - [导出 Office 365 高级电子数据展示中的结果](export-results-in-advanced-ediscovery.md)
    
