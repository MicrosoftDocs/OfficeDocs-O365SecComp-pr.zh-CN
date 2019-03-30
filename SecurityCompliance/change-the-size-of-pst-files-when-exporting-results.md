---
title: 导出电子数据展示搜索结果时更改 PST 文件的大小
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 您可以在导出电子数据展示搜索结果时更改下载到您的计算机上的 PST 文件的默认大小。
ms.openlocfilehash: 98b543b6e34cb9cb075a765671def91742aee6c1
ms.sourcegitcommit: e7a776a04ef6ed5e287a33cfdc36aa2d72862b55
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "30999715"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>导出电子数据展示搜索结果时更改 PST 文件的大小

使用 Office 365 电子数据展示导出工具从不同的 Microsoft 电子数据展示工具导出电子数据展示搜索的电子邮件结果时, 可以导出的 PST 文件的默认大小为 10 GB。 如果要更改此默认大小, 可以在用于导出搜索结果的计算机上编辑 Windows 注册表。 执行此操作的一个原因是, PST 文件可以放置在可移动媒体 (如 DVD、光盘或 USB 驱动器) 上。 
  
> [!NOTE]
>  Office 365 电子数据展示导出工具用于在安全与合规中心中使用内容搜索工具、Exchange online 中的就地电子数据展示和 SharePoint online 中的电子数据展示中心来导出搜索结果。
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>创建注册表设置以在导出电子数据展示搜索结果时更改 PST 文件的大小

在用于导出电子数据展示搜索结果的计算机上执行以下过程。
  
1. 如果 Office 365 电子数据展示导出工具处于打开状态, 则将其关闭。 
    
2. 使用文件名后缀 .reg 将以下文本保存到窗口注册表文件;例如, PstExportSize。 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    在上面的示例中, `PstSizeLimitInBytes`值设置为1073741824个字节或约 1 GB。 下面是`PstSizeLimitInBytes`设置的一些其他示例值。 
    
    |**大小 (以 GB 为单位) (近似)**|**以字节为单位的大小**|
    |:-----|:-----|
    |7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. 在导出`PstSizeLimitInBytes`搜索结果时, 将值更改为所需的最大 PST 文件大小, 然后保存该文件。 
    
4. 在 Windows 资源管理器中, 单击或双击您在前面步骤中创建的 .reg 文件。
    
5. 在 "用户访问控制" 窗口中, 单击 **"是"** 以让注册表编辑器进行更改。 
    
6. 当系统提示您继续时, 请单击 **"是"**。
    
    注册表编辑器将显示一条消息, 指出已成功将设置添加到注册表中。
    
7. 您可以重复步骤 3-6 以更改`PstSizeLimitInBytes`注册表设置的值。 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>在导出电子数据展示搜索结果时, 有关更改 PST 文件默认大小的常见问题

 **为什么默认大小为 10 GB？**
  
10 GB 的默认大小是基于客户反馈;10 GB 是一种很好的平衡单个 PST 中的内容量, 并具有最小的文件损坏可能性。
  
 **是否应增加或减小 PST 文件的默认大小？**
  
客户倾向于减小大小限制, 以便搜索结果能够在可在其组织中物理传送其他位置的可移动媒体上进行调整。 我们建议您不要增加默认大小, 因为 PST 文件大于 10 GB 可能存在损坏问题。
  
 **我必须在哪台计算机上执行此操作？**
  
您需要更改在其上运行 Office 365 电子数据展示导出工具的任何本地计算机上的注册表设置。
  
 **更改此设置后, 必须重新启动计算机吗？**
  
否, 无需重新启动计算机。 但是, 如果 Office 365 电子数据展示导出工具正在运行, 则必须将其关闭, 并在更改此设置后重新启动它。
  
 **是否已编辑现有注册表项或是否创建新的密钥？**
  
首次运行您在此过程中创建的 .reg 文件时, 会创建一个新的注册表项。 然后, 在每次更改并重新运行 .reg 编辑文件时, 都会编辑该设置。
