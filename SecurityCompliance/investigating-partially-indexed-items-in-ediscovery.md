---
title: 使用 Office 365 电子数据展示调查部分索引项
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 1/26/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid: MOE150
ms.assetid: 4e8ff113-6361-41e2-915a-6338a7e2a1ed
description: 部分索引项目 (也称为未编制索引项) 是 SharePoint 和 OneDrive 网站上的 Exchange 邮箱项目和文档, 由于某些原因未完全为内容搜索编制索引。 在本文中, 您可以了解为什么无法将项目编入搜索, 并作为部分索引项目返回, 确定部分索引项目的搜索错误, 以及使用 PowerShell 脚本确定组织的部分索引电子邮件的公开程度。items.
ms.openlocfilehash: d6b1326498780a5d40e49ff22aa1ac7d16bee8e4
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32254116"
---
# <a name="investigating-partially-indexed-items-in-office-365-ediscovery"></a>使用 Office 365 电子数据展示调查部分索引项

从安全 & 合规中心运行的内容搜索会在运行搜索时自动在估计的搜索结果中包含部分索引的项目。 部分索引项目是指 SharePoint 和 OneDrive for business 网站上的 Exchange 邮箱项目和文档, 因为某些原因未完全编制搜索索引。 大多数电子邮件和网站文档都已成功编制索引, 因为它们位于[电子邮件的索引限制](limits-for-content-search.md#indexing-limits-for-email-messages)内。 但是, 某些项目可能超出这些索引限制, 将对其进行部分索引。 以下是在运行内容搜索时无法将项目编入索引并作为部分索引项目返回的其他原因:
  
- 电子邮件包含无法编制索引的文件类型的附加文件;在大多数情况下,[无法识别或不支持对文件类型进行索引](partially-indexed-items-in-content-search.md#file-types-not-indexed-for-search)
    
- 电子邮件有一个没有有效处理程序的附加文件, 如图像文件;这是部分索引的电子邮件项目的最常见原因
    
- 附加到电子邮件的文件过多
    
- 附加到电子邮件的文件过大
    
- 文件类型支持索引, 但特定文件发生索引错误
    
尽管它不同, 但大多数 Office 365 组织客户的内容数量少于 1%, 而按部分索引的大小少于 12% 的内容。 卷与大小之间的差异在于, 较大的文件包含无法完全编制索引的内容的可能性较高。
  
## <a name="why-does-the-partially-indexed-item-count-change-for-a-search"></a>对于搜索, 部分索引项目数的变化是什么？

在 Security & 合规中心中运行内容搜索后, 搜索的位置中的部分索引项目的总数和大小将列在搜索结果统计信息中, 并显示在搜索的详细统计信息中。 请注意, 这些项在搜索统计信息中称为未*编制索引的项*。 下面几项操作将影响在搜索结果中返回的部分已编制索引项的数目: 
  
- 如果项目已部分编制了索引, 并且与搜索查询相匹配, 则会将其包含在搜索结果项的计数 (和大小) 和部分索引项中。 但是, 当导出相同搜索的结果时, 该项目仅包含在一组搜索结果中;它不包含为部分索引项。
    
- 如果为搜索查询指定日期范围 (通过将其包含在关键字查询中或使用条件), 则任何不符合日期范围的部分索引项都不会包含在部分索引项的计数中。 只有位于日期范围内的部分索引项才包含在部分索引项的计数中。
    
 **注意:** 位于 SharePoint 和 OneDrive 网站中的部分索引项*不*包含在搜索的详细统计信息中显示的部分索引项的估计中。 但是, 当您导出内容搜索的结果时, 可以导出部分索引的项目。 例如, 如果您仅搜索内容搜索中的网站, 估计的数字部分索引项将为零。 
  
## <a name="calculating-the-ratio-of-partially-indexed-items-in-your-organization"></a>计算组织中部分索引项目的比率

若要了解组织对部分索引项目的暴露程度, 可以对所有邮箱中的所有内容运行搜索 (通过使用空白的关键字查询)。 在下面的示例中, 有 56208 (4830 MB) 的完全索引项和 470 (316 MB) 部分索引项。
  
![显示部分索引项目的搜索统计信息示例](media/0f6a5cf7-4c98-44a0-a0dd-5aed67124641.png)
  
您可以使用以下计算来确定部分索引项目的百分比。
  
 **若要计算组织中部分索引项目的比率, 请执行以下操作:**

`(Total number of partially indexed items/Total number of items) x 100`


`(470/56,208) x 100 = 0.84%`
 
通过使用上一示例中的搜索结果, 将对所有邮箱项目的 84% 进行部分索引。
  
 **若要计算组织中部分索引项目大小的百分比, 请执行以下操作:**

`(Size of all partially indexed items/Size of all items) x 100`

`(316 MB/4830 MB) x 100 = 6.54%`

所以在上一示例中, 邮箱项目总大小的 6.54% 来自部分索引项目。 如前所述, 大多数 Office 365 组织客户的内容少于 1%, 而按部分索引的大小少于 12% 的内容。

## <a name="working-with-partially-indexed-items"></a>使用部分索引项目

在需要检查部分项目以验证它们不包含相关信息的情况下, 您可以导出包含部分索引项目相关信息的[内容搜索报告](export-a-content-search-report.md)。 导出内容搜索报告时, 请务必选择包含部分索引项目的导出选项之一。 
  
![选择第二个或第三个选项以导出部分索引项目](media/624a62b4-78f7-4329-ab5d-e62e3b369885.png)
  
当您使用其中一个选项导出内容搜索结果或内容搜索报告时, 导出将包含一个名为 "未编制索引的项目 .csv" 的报告。 此报告包含与 ResultsLog 文件相同的大部分信息;但是, 未编制索引的项目 .csv 文件还包含与部分索引项目相关的两个字段:**错误标记**和**错误属性**。 这些字段包含有关每个部分索引项的索引错误的信息。 使用这两个字段中的信息可帮助您确定您的调查是否有特定影响的索引错误。 如果这样做, 您可以执行目标内容搜索并检索和导出特定的电子邮件和 SharePoint 或 OneDrive 文档, 以便您可以对其进行检查以确定它们是否与您的调查相关。 有关分步说明, 请参阅[在 Office 365 中准备用于目标内容搜索的 CSV 文件](csv-file-for-an-id-list-content-search.md)。
  
 **注意:** 未编制索引的项目 .csv 文件还包含名为 "**错误类型**" 和 "**错误消息**" 的字段。 这些字段包含的信息与 "**错误标记**" 和 "**错误属性**" 字段中的信息类似, 但详细信息较少。 您可以安全地忽略这些旧字段。 
  
## <a name="errors-related-to-partially-indexed-items"></a>与部分索引项目相关的错误

错误标记由两条信息组成, 即错误和文件类型。 例如, 在此错误/文件对:

```
 parseroutputsize_xls
```

   
 `parseroutputsize`是错误, `xls`是发生错误的文件的文件类型。 如果无法识别文件类型或文件类型不适用于该错误, 您将看到替换文件类型的值`noformat` 。 
  
下面列出了索引错误和可能的错误原因的说明。
  
|**错误标记**|**Description**|
|:-----|:-----|
| `attachmentcount` <br/> |电子邮件的附件过多, 其中一些附件未处理。  <br/> |
| `attachmentdepth` <br/> |内容检索器和文档分析程序发现嵌套在其他附件中的附件级别过多。 其中一些附件未处理。  <br/> |
| `attachmentrms` <br/> |由于受 RMS 保护, 附件无法进行解码。  <br/> |
| `attachmentsize` <br/> |附加到电子邮件的文件太大, 无法处理。  <br/> |
| `indexingtruncated` <br/> |将已处理的电子邮件写入索引时, 其中一个可索引的属性太大, 已被截尾取整。 截断的属性在 "错误属性" 字段中列出。  <br/> |
| `invalidunicode` <br/> |电子邮件包含无法处理为有效 Unicode 的文本。 此项的索引可能不完整。  <br/> |
| `parserencrypted` <br/> |附件或电子邮件的内容已加密, Office 365 无法对内容进行解码。  <br/> |
| `parsererror` <br/> |分析过程中出现未知错误。 这通常是由于软件错误或服务崩溃造成的。  <br/> |
| `parserinputsize` <br/> |由于附件太大, 分析程序无法处理该附件, 并且该附件的分析未发生或未完成。  <br/> |
| `parsermalformed` <br/> |附件格式不正确, 无法由分析器进行处理。 此结果来自旧文件格式、由不兼容软件创建的文件, 或假装为非声明内容的病毒。  <br/> |
| `parseroutputsize` <br/> |对附件解析的输出太大, 必须将其截断。  <br/> |
| `parserunknowntype` <br/> |附件的文件类型为 Office 365 无法检测到的文件类型。  <br/> |
| `parserunsupportedtype` <br/> |附件具有 Office 365could 检测的文件类型, 但不支持解析该文件类型。  <br/> |
| `propertytoobig` <br/> |Exchange 存储中的电子邮件属性的值太大, 无法检索, 并且无法处理邮件。 这通常只发生在电子邮件的 body 属性中。  <br/> |
| `retrieverrms` <br/> |内容检索器无法对受 RMS 保护的邮件进行解码。  <br/> |
| `wordbreakertruncated` <br/> |编制索引期间在文档中标识了过多的单词。 属性处理在达到限制时停止, 属性被截断。  <br/> |
   
"错误" 域说明 "错误标记" 字段中列出的处理错误会影响哪些字段。 如果您正在搜索属性 (例如`subject`或`participants`), 则邮件正文中的错误不会影响您的搜索结果。 当准确确定可能需要进一步调查的部分已编制索引项时, 这可能很有用。
  
## <a name="using-a-powershell-script-to-determine-your-organizations-exposure-to-partially-indexed-email-items"></a>使用 PowerShell 脚本确定组织部分索引的电子邮件项的公开程度

下面的步骤演示了如何运行 PowerShell 脚本, 以搜索所有 Exchange 邮箱中的所有项目, 然后生成有关组织的部分索引的电子邮件项目 (按计数和按大小) 的比率的报告, 并显示项目数 (和它们的文件类型), 用于发生的每个索引错误。 使用上一节中的错误标记说明来标识索引错误。
  
1. 使用文件名后缀. ps1; 将以下文本保存到 Windows PowerShell 脚本文件中。例如, `PartiallyIndexedItems.ps1`。

```
  write-host "**************************************************"
  write-host "     Security & Compliance Center      " -foregroundColor yellow -backgroundcolor darkgreen
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
   
2. [连接到安全 & 合规中心 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=627084)。
    
3. 在 Security & 合规性中心 PowerShell 中, 转到在步骤1中保存脚本的文件夹, 然后运行该脚本;例如:

    ```
    .\PartiallyIndexedItems.ps1
    ```
   
下面的示例展示了脚本返回的输出。
  
![生成来自组织公开的报告的脚本的输出示例, 以部分索引的电子邮件项目](media/aeab5943-c15d-431a-bdb2-82f135abc2f3.png)
  
请注意以下几点：
  
1. 电子邮件项目的总数和大小, 以及组织的部分索引的电子邮件项目的比率 (按计数和按大小)
    
2. 列表错误标记以及发生错误的相应文件类型。
  
## <a name="see-also"></a>另请参阅

[处理 Office 365 内容搜索中的部分索引项](partially-indexed-items-in-content-search.md)
