---
title: 从审阅集中导出文档
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: 14efa58305e1963aa43c0c94fb208e5391c87119
ms.sourcegitcommit: 9d67cb52544321a430343d39eb336112c1a11d35
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34155064"
---
# <a name="export-documents-from-a-review-set"></a>从审阅集中导出文档

可以通过3种不同的方法来导出评审集的内容:

## <a name="download"></a>下载

下载提供了一种从以本机格式的审阅集下载内容的简单方法。 它利用浏览器的数据传输功能, 以便在下载准备就绪后会出现浏览器提示。 使用此方法下载的文件将压缩到一个容器文件中, 并将成为项目级文件。 这意味着, 如果选择了附件, 您将自动收到包含附件的电子邮件。 同样, 如果您选择嵌入在 word 文档中的 excel 电子表格, 您将收到嵌入 excel 电子表格的 word 文档。 已下载项目将保留上次修改日期, 可将其视为文件属性。

若要从审阅集中下载内容, 请先选择要下载的文件, 然后选择 "操作" 菜单下的 "下载"。

![自动生成的计算机说明的屏幕截图](../media/eDiscoDownload.png)

## <a name="export"></a>导出

导出允许用户自定义下载包中包含的内容。 它提供具有以下设置的配置页:

### <a name="metadata-file"></a>元数据文件

> 可以将其视为包含与导出的文件相关联的元数据的 "加载文件"。 有关元数据文件中可用字段的列表, 请参阅\[链接\]。 此文件通常可由3个<sup>rd</sup>方引入的后续工具进行。

### <a name="tag-data"></a>标记数据

> 此内容将作为字段添加到元数据文件中。 它包含在审阅集中应用的所有标记信息。

### <a name="text-files"></a>文本文件

> 可以为从评审集导出的每个文件生成文本文件。 通常, 服务合作伙伴会将这些文件作为 ingesting 数据的一部分提供给3个<sup>rd</sup>方参与方工具。

### <a name="redacted-files"></a>编辑文件

> 如果在审阅过程中生成编辑 Pdf, 则这些文件在导出过程中可用。 用户可以决定是仅导出本机文件, 还是将具有密文的 natives 替换为 Pdf 中的刻录文件。

### <a name="export-location"></a>导出位置

> 导出的内容将传递给 Microsoft 提供的 Azure blob, 如果导出时提供了详细信息, 则可以使用客户的 blob。

## <a name="export-structure"></a>导出结构

从审阅集导出内容时, 将按以下结构组织内容。

  - 根文件夹–下载 ID
    
      - Export\_load\_file .csv = metadata 文件
    
      - 摘要 .txt = 带有导出统计信息的摘要文件
    
      - 输入\_或本机\_文件 = 包含所有本机文件
    
      - 错误\_文件 = 包含导出中包含的任何错误文件
        
          - ExtractionError –包含未从父文件正确提取的任何可用文件元数据的 csv
        
          - ProcessingError –包含处理错误的内容。 此内容是项目级别意味着, 如果附件遇到处理错误, 则包含附件的电子邮件将包含在此文件夹中。
    
      - 提取\_的\_文本文件 = 包含处理过程中生成的所有提取的文本文件。

## <a name="review-set"></a>查看设置

可将内容添加到另一个评审集。