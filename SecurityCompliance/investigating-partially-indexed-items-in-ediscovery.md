---
title: 使用 Office 365 电子数据展示调查部分索引项
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: 部分，索引项目 （还呼叫未编制索引项） 是 Exchange 邮箱项目和 SharePoint 上的文档和 OneDrive 网站的某种原因或者没有完全内容搜索编制索引。本文中，您可以了解项为什么不能用于搜索索引和部分索引项目以返回，识别部分已索引项，搜索错误并使用 PowerShell 脚本来确定贵组织的遭受部分索引的电子邮件项目。
ms.openlocfilehash: 4e8e8c31e6c5450a9b84a1240c2ae8d891c1bd6f
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525951"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a>使用 Office 365 电子数据展示调查部分索引项

从 Office 365 安全性运行内容搜索&amp;合规性中心自动包括部分索引的项目中估计的搜索结果时运行的搜索。部分索引的项目是 Exchange 邮箱项目和 SharePoint 和 OneDrive 上的一些原因或者没有完全编制索引以搜索业务网站的文档。大多数电子邮件和网站文档因为它们归属于[索引限制的电子邮件](limits-for-content-search.md#indexinglimits)成功编制索引。但是，某些项可能会超过这些索引限制，并将部分编制索引。下面是其他原因项不能用于搜索索引以及当您运行内容搜索部分索引项目以返回：
  
- 电子邮件有文件类型无法进行索引; 附加的的文件在大多数情况下，文件类型是[无法识别或不受支持的索引](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)
    
- 电子邮件有有效的处理程序中，不附加的文件，如图像文件;这是部分索引的电子邮件项目的最常见原因
    
- 文件太多附加到电子邮件
    
- 附加到电子邮件的文件是太大
    
- 文件类型支持检索，但是特定文件出现检索错误
    
尽管各不相同，大多数 Office 365 组织客户可以通过音量和小于 12%的内容具有按部分编制索引的大小小于 1%的内容。与大小卷之间的差异的原因是较大的文件具有更高版本包含不能完全编制索引的内容的概率。
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>部分索引的项计数搜索为何更改？

Office 365 安全性运行内容搜索后&amp;的详细统计信息中显示的搜索结果统计信息中列出合规性中心、 总数和搜索的位置中的部分索引项目的大小搜索。请注意这些称为*未编制索引的项*中的搜索统计信息。下面是会影响搜索结果中返回的部分索引项的数目的几个事项： 
  
- 如果部分编制索引和搜索查询匹配的项目，它包含在计数 （和大小） 的搜索结果项目和部分索引的项。但是，当导出的同一个搜索结果，项是只包括在组搜索结果;它不包含为部分索引项。
    
- 如果您指定一个日期范围的搜索查询 （包括其关键字查询中） 或使用条件，与日期范围不匹配任何部分索引的项不包含的部分索引的项计数。仅在日期范围内的部分索引的项目包含在部分索引项的计数。
    
 **注意：** 位于 SharePoint 中的部分索引的项目和 OneDrive 网站*不*包括在搜索的详细统计信息中显示的部分索引项目估计。但是，当您将导出的内容的搜索结果，则可以导出部分索引的项目。例如，如果您仅网站在搜索中搜索内容，估计数目部分索引的项目将为零。 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>计算贵组织中的部分索引项目的比率

若要了解部分索引项目的组织的风险，可以搜索所有内容中运行的所有邮箱 （通过使用空白关键字查询）。在下面的以下示例中，有 56,208 (4,830 MB) 完全编制索引项和 470 (316 MB) 部分，索引项目。
  
![搜索统计信息显示的示例部分索引项](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
您可以使用以下计算确定部分索引项目的百分比。
  
 **计算贵组织中的部分索引项的比例：**

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
使用上面的示例中，从搜索结果。 部分编制索引的所有邮箱项目 84%。
  
 **计算贵组织中的部分索引项目大小的百分比：**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

因此，在上一示例中，6.54%的邮箱项目的总大小为从部分索引项。如上文所述，大多数客户可以通过音量和小于 12%的内容按部分编制索引的大小的小于 1%的内容的 Office 365 组织。

## <a name="working-with-partially-indexed-items"></a>部分使用索引项

在情况下时您需要检查部分项目以验证它们不包含相关信息，您可以[导出内容的搜索报告](export-a-content-search-report.md)包含有关部分索引项目的信息。导出内容的搜索报告时，务必选择包括部分索引的项目导出选项之一。 
  
![选择导出部分索引的项目的第二个或第三个选项](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
导出内容的搜索结果或内容的搜索报告使用以下选项之一时，导出包括名为未编制索引 Items.csv 的报告。此报告包括大部分相同的信息的 ResultsLog.csv 文件;但是，未编制索引 Items.csv 文件还包括相关的部分索引项目的两个字段：**错误标记**和**Error 属性**。这些字段包含有关每个部分索引项的索引错误的信息。使用这两个字段中的信息可帮助您确定针对特定的索引错误影响您调查。如果是这样，您可以执行目标内容搜索和导出和检索特定的电子邮件和 SharePoint 或 OneDrive 文档，以便您可以检查它们来确定它们是否与调查相关。有关分步说明，请参阅[Prepare 目标内容搜索 Office 365 中的 CSV 文件](csv-file-for-an-id-list-content-search.md)。
  
 **注意：** 未编制索引 Items.csv 文件还包含名为**错误类型**和**错误消息**的字段。这些是包含信息类似于在**错误标记**和**Error 属性**字段中，但不是详细信息的信息的旧字段。您可以安全地忽略这些旧的字段。 
  
## <a name="errors-related-to-partially-indexed-items"></a>与部分索引项目相关的错误

错误标记的信息、 错误和文件类型的两个部分组成。例如，在此错误/filetype 对：

```
 parseroutputsize_xls
```

   
 `parseroutputsize`错误和`xls`发生的错误的文件类型的文件类型。在情况下已未识别的文件类型或文件类型不适用于该错误，您将看到值`noformat`替换的文件类型。 
  
以下是原因的索引错误和警告的错误可能的说明的列表。
  
|**错误标记**|**说明**|
|:-----|:-----|
| `attachmentcount` <br/> |电子邮件有附件太多，并且这些附件的一些或者没有处理。  <br/> |
| `attachmentdepth` <br/> |内容检索器和文档分析程序找到嵌套在其他附件的附件太多的级别。一些这些附件未处理。  <br/> |
| `attachmentrms` <br/> |附件失败，因为受 RMS 保护解码。  <br/> |
| `attachmentsize` <br/> |附加到电子邮件的文件太大，无法进行处理。  <br/> |
| `indexingtruncated` <br/> |编写时处理的电子邮件到索引，编制索引的属性之一太大，已被截断。错误属性字段中列出的截断的属性。  <br/> |
| `invalidunicode` <br/> |电子邮件包含无法处理为有效的 Unicode 的文本。针对此项目编制索引可能不完整。  <br/> |
| `parserencrypted` <br/> |附件或电子邮件的内容进行加密，和 Office 365 无法对内容进行解码。  <br/> |
| `parsererror` <br/> |在分析过程中出现未知的错误。这通常会导致从软件错误或服务崩溃。  <br/> |
| `parserinputsize` <br/> |附件已被太大，分析程序处理，并解析该附件未发生或未完成。  <br/> |
| `parsermalformed` <br/> |附件格式不正确，无法由分析程序处理。此结果从可以旧文件格式，由不兼容的软件或病毒伪装以外声明为内容创建的文件。  <br/> |
| `parseroutputsize` <br/> |附件的分析的输出太大，且必须被截断。  <br/> |
| `parserunknowntype` <br/> |附件具有 Office 365 无法检测的文件类型。  <br/> |
| `parserunsupportedtype` <br/> |附件具有 Office 365could 检测，但分析该文件类型不受支持的文件类型。  <br/> |
| `propertytoobig` <br/> |电子邮件属性的值在 Exchange 存储区是太大，无法检索和无法处理邮件。这通常只发生一封电子邮件的正文属性。  <br/> |
| `retrieverrms` <br/> |内容检索器失败进行解码受 RMS 保护的邮件。  <br/> |
| `wordbreakertruncated` <br/> |在编制索引过程，文档中标识词太多。属性的处理停止时达到此限制，并且属性会被截断。  <br/> |
   
错误字段介绍哪些字段影响在错误标记字段中列出的处理错误。如果您要搜索的属性，如`subject`或`participants`，邮件的正文中的错误不会影响您的搜索结果。确定完全您可能需要进一步调查哪些部分索引的项目时，这很有用。
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>使用 PowerShell 脚本来确定贵组织的遭受部分索引的电子邮件项目

以下步骤演示如何运行搜索所有项目中所有 Exchange 邮箱，然后生成有关贵组织的比率的部分索引的电子邮件项目的报告 （按计数和大小） 并显示的项目数的 PowerShell 脚本 （和其文件类型） 的每个索引所发生的错误。使用在上一节中的错误标记说明标识检索错误。
  
1. 使用.ps1; filename 后缀将以下文本保存到的 Windows PowerShell 脚本文件例如， `PartiallyIndexedItems.ps1`。

```
  write-host "**************************************************"
  write-host "     Office 365 Security &amp; Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "   eDiscovery Partially Indexed Item Statistics   " -foregroundColor yellow -backgroundcolor darkgreen
  write-host "**************************************************"
  " " 
  # Create a search with Error Tags Refinders enabled
  Remove-ComplianceSearch "RefinerTest" -Confirm:$false -ErrorAction 'SilentlyContinue'
  New-ComplianceSearch -Name "RefinerTest" -ContentMatchQuery "size>0" -RefinerNames ErrorTags -ExchangeLocation ALL
  Start-ComplianceSearch "RefinerTest"
  # Loop while search is in progress
  do{
      Write-host "Waiting for search to complete..."
      Start-Sleep -s 5
      $complianceSearch = Get-ComplianceSearch "RefinerTest"
  }while ($complianceSearch.Status -ne 'Completed')
  $refiners = $complianceSearch.Refiners | ConvertFrom-Json
  $errorTagProperties = $refiners.Entries | Get-Member -MemberType NoteProperty
  $partiallyIndexedRatio = $complianceSearch.UnindexedItems / $complianceSearch.Items
  $partiallyIndexedSizeRatio = $complianceSearch.UnindexedSize / $complianceSearch.Size
  " "
  "===== Partially indexed items ====="
  "         Total          Ratio"
  "Count    {0:N0}{1:P2}" -f $complianceSearch.Items.ToString("N0").PadRight(15, " "), $partiallyIndexedRatio
  "Size(GB) {0:N2}{1:P2}" -f ($complianceSearch.Size / 1GB).ToString("N2").PadRight(15, " "), $partiallyIndexedSizeRatio
  " "
  Write-Host ===== Reasons for partially indexed items =====
  foreach($errorTagProperty in $errorTagProperties)
  {
      $name = $refiners.Entries.($errorTagProperty.Name).Name
      $count = $refiners.Entries.($errorTagProperty.Name).TotalCount
      $frag = $name.Split("{_}")
      $errorTag = $frag[0]
      $fileType = $frag[1]
      if ($errorTag -ne $lastErrorTag)
      {
          $errorTag
      }
      "    " + $fileType + " => " + $count
      $lastErrorTag = $errorTag
  }
  
```
   
2. [连接到 Office 365 安全性&amp;合规性中心 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084)。
    
3. 安全性&amp;合规性中心 PowerShell 中，转到步骤 1 中保存该脚本的位置的文件夹，然后运行脚本。例如：

    ```
    .\PartiallyIndexedItems.ps1
    ```
   
下面是一个示例 fo 脚本返回的输出。
  
![从部分生成您的组织暴露程度报告的脚本的输出示例编制索引的电子邮件项目](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
请注意以下事项：
  
1. 总数和电子邮件项目的大小和您的组织比部分索引的电子邮件项目 （按计数和大小）
    
2. 列表错误标记和发生错误的相应的文件类型。
  
## <a name="see-also"></a>另请参阅

[处理 Office 365 内容搜索中的部分索引项](partially-indexed-items-in-content-search.md)
