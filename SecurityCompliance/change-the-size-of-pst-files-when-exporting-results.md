---
title: 导出电子数据展示搜索结果时更改 PST 文件的大小
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 11/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: 04e9de2d-765b-457b-a98a-d0f60bfb13f2
description: 您可以更改的下载到您的计算机来导出电子数据展示搜索结果时的 PST 文件的默认大小。
ms.openlocfilehash: 1479db72117729d2e5cfa6feec1d9a0d9a60ffb5
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25037985"
---
# <a name="change-the-size-of-pst-files-when-exporting-ediscovery-search-results"></a>导出电子数据展示搜索结果时更改 PST 文件的大小

如果您使用 Office 365 电子数据展示导出工具从不同的 Microsoft 电子数据展示工具导出电子数据展示搜索的电子邮件结果，可以导出的 PST 文件的默认大小是 10 GB。如果您想要更改此默认大小，您可以编辑用于导出搜索结果的计算机上的 Windows 注册表。若要执行此操作的一个原因是以便 PST 文件可容纳的可移动介质、 此类 DVD、 光盘或 USB 驱动器。 
  
> [!NOTE]
>  Office 365 电子数据展示导出工具用于在 Office 365 安全性使用内容搜索时导出搜索结果&amp;合规性中心、 Exchange Online 中的就地电子数据展示和 SharePoint Online 中的电子数据展示中心。 
  
## <a name="create-a-registry-setting-to-change-the-size-of-pst-files-when-you-export-ediscovery-search-results"></a>创建一个注册表设置来导出电子数据展示搜索结果时更改的 PST 文件大小

您将使用导出的电子数据展示搜索结果的计算机上执行以下过程。
  
1. 如果已打开，请关闭 Office 365 电子数据展示导出工具。 
    
2. 使用 filename 后缀.reg; 将以下文本保存到窗口注册表文件例如，PstExportSize.reg。 
    
    ```
    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool]
    "PstSizeLimitInBytes"="1073741824"
    ```

    在上例中，`PstSizeLimitInBytes`值设置为 1073741824 字节或约为 1 GB。下面是一些其他示例值`PstSizeLimitInBytes`设置。 
    
    |**Gb （约） 大小**|**以字节为单位的大小**|
    |:-----|:-----|
    |.7 GB (700 MB)  <br/> |751619277  <br/> |
    |2 GB  <br/> |2147483648  <br/> |
    |4 GB  <br/> |4294967296  <br/> |
    |8 GB  <br/> |8589934592  <br/> |
   
3. 更改`PstSizeLimitInBytes`的 PST 文件时导出搜索结果中，然后保存该文件所需的最大大小的值。 
    
4. 在 Windows 资源管理器中，单击或双击在上一步骤中创建该.reg 文件。
    
5. 在用户访问控制窗口中，单击**是**可允许注册表编辑器中进行的更改。 
    
6. 当提示您继续，请单击**是**。
    
    在注册表编辑器将显示一条消息告知设置已成功添加到注册表。
    
7. 您可以重复步骤 3-6 以更改的值`PstSizeLimitInBytes`注册表设置。 
  
## <a name="frequently-asked-questions-about-changing-the-default-size-of-pst-files-when-you-export-ediscovery-search-results"></a>有关导出电子数据展示搜索结果时更改 PST 文件的默认大小的常见问题

 **为什么是默认大小为 10 GB？**
  
10 GB 的默认大小基于客户反馈;10 GB 是内容的很好的平衡之间中单个 PST 文件损坏的最小有机会及最佳量。
  
 **应增加或减少 PST 文件的默认大小？**
  
客户通常以减小大小限制，以便他们可以从物理上隔离附带其组织中的其他位置的可移动介质适合的搜索结果。我们不建议您增加默认大小，因为 PST 文件大于 10 GB 可能有损坏问题。
  
 **有哪些计算机上执行此？**
  
您需要更改运行 Office 365 电子数据展示导出工具的任何本地计算机上的注册表设置。
  
 **更改此设置后，是否需要重新启动计算机？**
  
否，您无需重新启动计算机。但是，如果正在运行 Office 365 电子数据展示导出工具，您将需要关闭它，并在重新启动它后更改此设置。
  
 **执行获取编辑现有的注册表项或执行创建新的密钥？**
  
首次运行此过程中创建该.reg 文件创建一个新的注册表项。然后设置编辑每次更改并重新运行该.reg 编辑文件。
