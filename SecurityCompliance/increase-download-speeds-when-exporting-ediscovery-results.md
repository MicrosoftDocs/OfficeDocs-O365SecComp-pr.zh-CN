---
title: 从 Office 365 导出电子数据展示搜索结果时增加下载速度
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: c4c8f689-9d52-4e80-ae4b-1411ee9efc43
description: 了解如何配置 Windows 注册表，以下载搜索结果时提高数据吞吐量和搜索数据从 Office 365 安全性&amp;合规性中心和 Office 365 高级电子数据展示。
ms.openlocfilehash: 3f456f5ee0312d4d4d7b95f868520e6756a90fd1
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22526063"
---
# <a name="increase-the-download-speed-when-exporting-ediscovery-search-results-from-office-365"></a>从 Office 365 导出电子数据展示搜索结果时增加下载速度

当您使用 Office 365 电子数据展示导出工具下载 Office 365 安全性内容的搜索结果的&amp;合规性中心或下载的数据，从 Office 365 高级电子数据展示，该工具启动一定数量的并发导出若要下载到本地计算机上的数据的操作。默认情况下并发操作的数量设置为 8 时间所使用下载的数据的计算机中的核心数目。例如，如果您有双核计算机 （这意味着在一个芯片上的两个中央处理单元），并发导出操作的默认数量为 16。为了提高数据传输吞吐量和大的加速下载过程，您可以通过配置用于下载搜索结果的计算机上的 Windows 注册表设置增加并发操作的数量。到大下载过程中的加速，我们建议您启动的设置为 24 并发操作。
  
如果您通过低带宽网络下载搜索结果，增加此设置可能会产生负面影响。此外，您可能能够增加到超过 24 并发操作高带宽网络 （并发操作的最大数量为 512） 中的设置。在配置此注册表设置后，您可能需要将其更改为查找并发操作为您的环境的最佳数量。
  
## <a name="create-a-registry-setting-to-change-the-number-of-concurrent-operations-when-exporting-data"></a>创建注册表设置导出数据时更改并发操作的数量

您将使用从安全下载搜索结果的计算机上执行以下过程&amp;合规性中心或高级电子数据展示中的数据。
  
1. 如果已打开，请关闭 Office 365 电子数据展示导出工具。 
    
2. 使用 filename 后缀.reg; 将以下文本保存到窗口注册表文件例如，ConcurrentOperations.reg。 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "DownloadConcurrency"="24"
    ```

    与以前所述，我们建议您开始 24 并行操作，然后更改此设置根据。
    
3. 在 Windows 资源管理器中，单击或双击在上一步中创建该.reg 文件。
    
4. 在用户访问控制窗口中，单击**是**可允许注册表编辑器中进行的更改。 
    
5. 当提示您继续，请单击**是**。
    
    在注册表编辑器将显示一条消息告知设置已成功添加到注册表。
    
6. 您可以重复步骤 2-5 更改的值`DownloadConcurrency`注册表设置。 
    
    > [!IMPORTANT]
    > 创建或更改后`DownloadConcurrency`注册表设置，请务必创建新的导出作业或重新启动的搜索结果或要下载的数据的现有导出作业。请参阅[详细信息](increase-download-speeds-when-exporting-ediscovery-results.md#moreinfo)部分的详细信息。 
  
## <a name="more-information"></a>详细信息

- 首次运行此过程中创建该.reg 文件创建一个新的注册表项。然后`DownloadConcurrency`注册表设置编辑每次更改并重新运行该.reg 编辑文件。 
    
- Office 365 电子数据展示导出工具使用[Azure AzCopy 实用程序](https://go.microsoft.com/fwlink/?linkid=849949)从安全下载搜索数据&amp;合规性中心或高级电子数据展示。配置`DownloadConcurrency`注册表设置是类似于运行 AzCopy 实用程序时使用 **/NC**参数。因此的注册表设置`"DownloadConcurrency=24"`会具有相同的效果与使用参数值为`/NC:24`使用 AzCopy 实用程序。 
    
- 如果您停止当前正在进行，然后重新启动它 （通过尝试再次下载搜索结果） 的导出下载，Office 365 电子数据展示导出工具将尝试恢复相同下载。因此，如果启动下载，将其，停止，然后更改`DownloadConcurrency`注册表设置，下载可能失败如果重新启动 （通过单击**下载导出结果**）。这是因为导出工具将尝试恢复以前的下载使用无效，因为您更改了注册表设置的设置。
    
    因此，之后更改`DownloadConcurrency`注册表设置，请务必重新启动 （通过单击**重新启动导出**） 安全中导出作业&amp;合规性中心。然后您可以下载导出的结果。有关导出搜索结果以及数据的详细信息，请参阅：
    
  - [从 Office 365 安全性导出内容的搜索结果&amp;合规性中心](export-search-results.md)
    
  - [导出 Office 365 高级电子数据展示中的结果](export-results-in-advanced-ediscovery.md)
    
