---
title: 导出 Office 365 安全性内容的搜索结果时禁用报告&amp;合规性中心
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/30/2016
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid: MOE150
ms.assetid: c9b0ff0c-282b-4a44-b43f-cfc5b96557f9
description: 编辑本地计算机上的 Windows 注册表禁用报告，从 Office 365 安全性导出内容的搜索结果时&amp;Comliance 中心。禁用这些报告可加快下载时间和节省磁盘空间。
ms.openlocfilehash: 62782c472adca892e1dcf239a45fe80f0fa7251b
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25037975"
---
# <a name="disable-reports-when-you-export-content-search-results-in-the-office-365-security-amp-compliance-center"></a>导出 Office 365 安全性内容的搜索结果时禁用报告&amp;合规性中心

当您使用 Office 365 电子数据展示导出工具的安全中内容搜索结果导出&amp;合规性中心，该工具自动创建，并将导出包含有关导出的内容的其他信息的两个报表。这些报告是 Results.csv 文件和 Manifest.xml 文件 （请参阅有关这些报告的详细说明本主题中的[有关禁用导出报告的常见问题](#frequently-asked-questions-about-disabling-export-reports)一节）。由于这些文件可能会非常大，您可以加快下载时间和通过防止这些文件导出节省磁盘空间。您可以通过更改 Windows 注册表用于导出搜索结果的计算机上执行此操作。如果您想要包括在以后的报告，您可以编辑注册表设置。 
  
## <a name="create-registry-settings-to-disable-the-export-reports"></a>创建注册表设置来禁用导出报告

您将使用导出内容的搜索结果的计算机上执行以下过程。
  
1. 如果已打开，请关闭 Office 365 电子数据展示导出工具。
    
2. 执行一个或两个以下步骤，具体取决于哪个导出报告您想要禁用。
    
    - **Results.csv**
    
      将以下文本保存到 Windows 注册表文件中，使用.reg; filename 后缀例如，DisableResultsCsv.reg。
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d False 
      ```

    - **Manifest.xml**
    
      将以下文本保存到 Windows 注册表文件中，使用.reg; filename 后缀例如，DisableManifestXml.reg。
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d False 
      ```

3. 在 Windows 资源管理器中，单击或双击在上一步骤中创建该.reg 文件。
    
4. 在用户访问控制窗口中，单击**是**可允许注册表编辑器中进行的更改。 
    
5. 当提示您继续，请单击**是**。
    
    在注册表编辑器将显示一条消息告知设置已成功添加到注册表。
  
## <a name="edit-registry-settings-to-re-enable-the-export-reports"></a>编辑注册表设置，以重新启用导出报告

如果您在前面过程中创建的.reg 文件禁用 Results.csv 和 Manifest.xml 报告，您可以编辑这些文件，若要重新启用报告，以便它与搜索结果导出。同样，您将使用导出内容的搜索结果的计算机上执行以下过程。
  
1. 如果已打开，请关闭 Office 365 电子数据展示导出工具。
    
2. 编辑一个或两个您在前一过程中创建的.reg 编辑文件。
    
    - **Results.csv**
    
        打开 DisableResultsCsv.reg 文件在记事本中，更改值`False`到`True`，然后保存该文件。例如，编辑该文件后，则它类似于此：
    
        ```
        Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultCsvEnabled /t REG_SZ /d True
        ```

    - **Manifest.xml**
    
        打开 DisableManifestXml.reg 文件在记事本中，更改值`False`到`True`，然后保存该文件。例如，编辑该文件后，则它类似于此：
    
      ```
      Windows Registry Editor Version 5.00
      reg add HKLM\SOFTWARE\Microsoft\Exchange\Client\eDiscovery\ExportTool /v ResultEdrmEnabled /t REG_SZ /d True
      ```

3. 在 Windows 资源管理器中，单击或双击在上一步中编辑.reg 文件。
    
4. 在用户访问控制窗口中，单击**是**可允许注册表编辑器中进行的更改。 
    
5. 当提示您继续，请单击**是**。
    
    在注册表编辑器将显示一条消息告知设置已成功添加到注册表。
  
## <a name="frequently-asked-questions-about-disabling-export-reports"></a>有关禁用导出报告的常见问题
<a name="faqs"> </a>

 **Results.csv 和 Manifest.xml 报告有哪些？**
  
Results.csv 和 Manifest.xml 文件包含有关已导出的内容的其他信息。
  
- 包含有关作为搜索结果是下载每个项目的信息的**Results.csv** Excel 文档。为电子邮件，结果日志包含有关每封邮件的信息包括： 
    
  - 邮件在源邮箱中的位置（包括邮件位于主邮箱还是存档邮箱）。
    
  - 发送或接收邮件的日期。
    
  - 邮件的主题行。
    
  - 邮件的发件人和收件人。
    
  - 邮件是否重复的邮件如果导出搜索结果时启用重复数据删除。重复的邮件将具有标识为重复的消息的**父 ItemId**列中的值。**父 ItemId**列中的值是已导出的邮件**项 DocumentId**列中的值相同。 
    
    对于来自 SharePoint 和 OneDrive for Business 站点的文档，结果日志包含有关每个文档的信息包括：
    
  - 文档的 URL。
    
  - 文档所在的网站集的 URL 。
    
  - 上次修改文档的日期。
    
  - 文档的名称（位于结果日志中的主题列）。
    
- **Manifest.xml**清单文件 （以 XML 格式） 包含在搜索结果中包含每个项目的信息。此报告中的信息相同 Results.csv 报告，但其格式指定通过电子发现参考模型 (EDRM)。有关 EDRM 的详细信息，请转到[https://www.edrm.net](https://www.edrm.net)。
    
 **时应禁用导出这些报告？**
  
这取决于您的特定需求。许多组织不需要有关搜索结果的其他信息，并且不需要这些报告。
  
 **有哪些计算机上执行此？**
  
 您必须更改运行 Office 365 电子数据展示导出工具的任何本地计算机上的注册表设置。 
  
 **更改此设置后，是否需要重新启动计算机？**
  
否，您无需重新启动计算机。但是，如果正在运行 Office 365 电子数据展示导出工具，您需要关闭它，然后重新启动它后更改的注册表设置。
  
 **执行获取编辑现有的注册表项或执行创建新的密钥？**
  
首次运行您在本主题中的过程中创建该.reg 文件创建一个新的注册表项。然后设置编辑每次更改并重新运行该.reg 编辑文件。
