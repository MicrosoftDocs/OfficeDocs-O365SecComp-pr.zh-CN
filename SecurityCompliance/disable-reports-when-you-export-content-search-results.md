---
title: 在 Office 365 安全&amp;合规中心中导出内容搜索结果时禁用报告
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: 在您的本地计算机上编辑 Windows 注册表, 以在从 Office 365 Security &amp; Comliance Center 导出内容搜索结果时禁用报告。禁用这些报告可加快下载时间并节省磁盘空间。
ms.openlocfilehash: 0be2be18eaccb618a49e1b58a5c0e53d0a339d1e
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30213472"
---
# <a name="disable-reports-when-you-export-content-search-results-in-the-office-365-security-amp-compliance-center"></a>在 Office 365 安全&amp;合规中心中导出内容搜索结果时禁用报告

当您使用 Office 365 电子数据展示导出工具导出安全&amp;合规中心中的内容搜索结果时, 该工具会自动创建和导出包含有关导出内容的其他信息的两个报告。这些报告是结果 .csv 文件和 Manifest .xml 文件 (有关这些报告的详细说明, 请参阅本主题中[有关禁用导出报告](#frequently-asked-questions-about-disabling-export-reports)部分的常见问题)。由于这些文件可能非常大, 因此可以通过防止导出这些文件, 加快下载时间并节省磁盘空间。您可以通过更改用于导出搜索结果的计算机上的 Windows 注册表来执行此操作。如果您想要在以后包含这些报告, 可以编辑注册表设置。 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>创建注册表设置以禁用导出报告

在将用于将结果导出到内容搜索的计算机上执行以下过程。
  
1. 如果 Office 365 电子数据展示导出工具处于打开状态, 则将其关闭。
    
2. 执行下列一项或两项操作, 具体取决于要禁用的导出报告。
    
    - **结果 .csv**
    
      使用文件名后缀 .reg 将以下文本保存到 Windows 注册表文件中;例如, DisableResultsCsv。
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **清单 .xml**
    
      使用文件名后缀 .reg 将以下文本保存到 Windows 注册表文件中;例如, DisableManifestXml。
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. 在 Windows 资源管理器中, 单击或双击您在前面步骤中创建的 .reg 文件。
    
4. 在 "用户访问控制" 窗口中, 单击 **"是"** 以让注册表编辑器进行更改。 
    
5. 当系统提示您继续时, 请单击 **"是"**。
    
    注册表编辑器将显示一条消息, 指出已成功将设置添加到注册表中。
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>编辑注册表设置以重新启用导出报告

如果通过在上一过程中创建 .reg 文件禁用了结果. .csv 和 .manifest 报告, 则可以编辑这些文件以重新启用报告, 以便将其导出到搜索结果中。再次在将用于将结果导出到内容搜索的计算机上执行以下过程。
  
1. 如果 Office 365 电子数据展示导出工具处于打开状态, 则将其关闭。
    
2. 编辑您在上一过程中创建的 .reg 编辑文件中的一个或两个。
    
    - **结果 .csv**
    
        在记事本中打开 DisableResultsCsv 文件, 将值`False`更改为`True`, 然后保存文件。例如, 在编辑文件后, 其外观如下所示:
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **清单 .xml**
    
        在记事本中打开 DisableManifestXml 文件, 将值`False`更改为`True`, 然后保存文件。例如, 在编辑文件后, 其外观如下所示:
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. 在 Windows 资源管理器中, 单击或双击在上一步中编辑过的 .reg 文件。
    
4. 在 "用户访问控制" 窗口中, 单击 **"是"** 以让注册表编辑器进行更改。 
    
5. 当系统提示您继续时, 请单击 **"是"**。
    
    注册表编辑器将显示一条消息, 指出已成功将设置添加到注册表中。
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>有关禁用导出报告的常见问题
<a name="faqs"> </a>

 **什么是结果 .csv 和清单 .xml 报告？**
  
结果 .csv 和清单 .xml 文件包含有关导出的内容的其他信息。
  
- **结果 .csv**包含作为搜索结果下载的每个项目的相关信息的 Excel 文档。对于电子邮件, 结果日志包含有关每封邮件的信息, 其中包括: 
    
  - 邮件在源邮箱中的位置（包括邮件位于主邮箱还是存档邮箱）。
    
  - 发送或接收邮件的日期。
    
  - 邮件的主题行。
    
  - 邮件的发件人和收件人。
    
  - 如果在导出搜索结果时启用重复数据删除功能, 则该邮件是否为重复的邮件。重复邮件在**父 ItemId**列中有一个将该邮件标识为重复的值。**父 ItemId**列中的值与导出的邮件的 "**项目 DocumentId** " 列中的值相同。 
    
    对于 SharePoint 和 OneDrive for business 网站中的文档, 结果日志包含有关每个文档的信息, 包括:
    
  - 文档的 URL。
    
  - 文档所在的网站集的 URL 。
    
  - 上次修改文档的日期。
    
  - 文档的名称（位于结果日志中的主题列）。
    
- **.manifest**一个清单文件 (xml 格式), 包含搜索结果中包含的每个项目的相关信息。此报告中的信息与 "结果 .csv" 报告相同, 但其格式为 "电子发现参考模型 (EDRM)" 指定的格式。有关 EDRM 的详细信息, 请转[https://www.edrm.net](https://www.edrm.net)到。
    
 **何时应禁止导出这些报告？**
  
这取决于您的特定需求。许多组织不需要有关搜索结果的其他信息, 也不需要这些报告。
  
 **我必须在哪台计算机上执行此操作？**
  
 您必须更改在其上运行 Office 365 电子数据展示导出工具的任何本地计算机上的注册表设置。 
  
 **更改此设置后, 必须重新启动计算机吗？**
  
否, 无需重新启动计算机。但是, 如果 Office 365 电子数据展示导出工具正在运行, 则必须将其关闭, 然后在更改注册表设置后重新启动它。
  
 **是否已编辑现有注册表项或是否创建新的密钥？**
  
首次运行本主题中的过程中创建的 .reg 文件时, 会创建一个新的注册表项。然后, 在每次更改并重新运行 .reg 编辑文件时, 都会编辑该设置。
