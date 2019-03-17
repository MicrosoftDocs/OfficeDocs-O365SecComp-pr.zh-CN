---
title: 创建关键字词典
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/29/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 标识敏感信息有时需要查找关键字，尤其是在标识通用内容（如与医疗保健相关的通信）或不当/露骨语言时。虽然可以在敏感信息类型中创建关键字列表，但关键字列表的大小受限，且必须修改 XML 才能创建或编辑它们。借助关键字词典，可以更大规模地轻松管理关键字（每个词典最多支持 100,000 个关键字）。
ms.openlocfilehash: 8e115c0feddbd55a498db3481e6ad4bc7ebb07e7
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2019
ms.locfileid: "30638909"
---
# <a name="create-a-keyword-dictionary"></a>创建关键字词典

Office 365 中的数据丢失防护 (DLP) 可标识、监视和保护敏感信息。标识敏感信息有时需要查找关键字，尤其是在标识通用内容（如与医疗保健相关的通信）或不当/露骨语言时。虽然可以在敏感信息类型中创建关键字列表，但关键字列表的大小受限，且必须修改 XML 才能创建或编辑它们。借助关键字词典，可以更大规模地轻松管理关键字（每个词典最多支持 100,000 个关键字）。
  
## <a name="basic-steps-to-creating-a-keyword-dictionary"></a>创建关键字词典的基本步骤

词典可能有多个关键字来源，最常见的来源是文件（如 .csv 或 .txt 列表）、你直接在 cmdlet 中输入的列表或现有词典。创建关键字词典时，请遵循下面的相同核心步骤：
  
1. **连接到安全与合规中心 PowerShell** - 请参阅[这篇主题](https://docs.microsoft.com/zh-CN/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
    
2. **定义或加载目标来源中的关键字** - 用于创建关键字词典的 cmdlet 接受关键字的逗号分隔列表，所以这一步因关键字来源不同而略有差异。 
    
3. **编码关键字** - 加载后的关键字会在导入前转换为字节数组。 
    
4. **创建词典** - 指定名称和说明，并创建词典。 
    
## <a name="create-a-keyword-dictionary-from-a-file"></a>通过文件创建关键字词典

如果需要创建大词典，词典通常使用从其他某来源导出的文件或列表中的关键字。本示例将创建关键字词典，其中包含要在外部电子邮件中筛查的不当语言列表。首先，需要[连接到 Office 365 安全与合规中心 PowerShell](https://docs.microsoft.com/zh-CN/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。
  
1. 将关键字复制到文本文件中，并确保每个关键字都单独占一行。
    
2. 使用 Unicode 编码保存文本文件。在记事本中，依次单击“另存为”****\>“编码”****\>“Unicode”****。
    
3. 运行下面的 cmdlet，以将文件读入变量中：
    
  ```
  $fileData = Get-Content <filename> -Encoding Byte -ReadCount 0
  ```

4. 运行下面的 cmdlet，以创建词典：
    
  ```
  New-DlpKeywordDictionary -Name <name> -Description <description> -FileData $fileData
  ```

## <a name="modifying-an-existing-keyword-dictionary"></a>修改现有关键字词典

可能需要修改一个关键字词典中的关键字，或修改一个内置词典。本示例将在 PowerShell 中修改一些关键字，在可便于使用编辑器编辑关键字的本地位置保存关键字，然后就地更新旧关键字。首先，检索词典对象：
  
```
$dict = Get-DlpKeywordDictionary -Name "Diseases"
```

打印 `$dict` 将显示各种变量。关键字本身存储在后端上的对象中，但 `$dict.KeywordDictionary` 包含它们的字符串表示形式，可用于修改词典。必须先使用 `.split(',')` 方法将关键字字符串转换回数组，然后才能修改词典。然后，使用 `.trim()` 方法清理关键字之间不必要的空格，只留下要使用的关键字。 
  
```
$terms = $dict.KeywordDictionary.split(',').trim()
```

现在从词典中删除一些关键字。由于示例词典中只有几个关键字，因此你可以很轻松地就跳到导出词典并在记事本中编辑关键字，但词典通常包含大量文本，所以必须先了解如何在 PowerShell 中轻松编辑关键字。
  
你在最后一步中将关键字保存到了数组中。虽然[从数组中删除项](https://go.microsoft.com/fwlink/p/?linkid=852620)的方法有多种，但简单方法是创建要从词典中删除的关键字数组，再只将要删除的关键字列表中没有的词典关键字复制到其中。
  
运行命令 `$terms`，以显示当前关键字列表。此命令的输出如下所示： 
  
```
aarskog's syndrome
abandonment
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipoproteinemia
abiotrophy
ablatio
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

运行下面的命令，以指定要删除的关键字：
  
```
$termsToRemove = @('abandonment', 'ablatio')
```

运行下面的命令，以实际删除列表中的关键字：
  
```
$updatedTerms = $terms | Where-Object{ $_ -notin $termsToRemove }
```

运行命令 `$updatedTerms`，以显示更新后的关键字列表。此命令的输出如下所示（指定关键字已遭删除）： 
  
```
aarskog's syndrome
abasia
abderhalden-kaufmann-lignac
abdominalgia
abduction contracture
abetalipo proteinemia
abiotrophy
ablation
ablepharia
abocclusion
abolition
aborter
abortion
abortus
aboulomania
abrami's disease
```

现在，在本地保存词典，并添加其他一些关键字。可直接在 PowerShell 中添加关键字，但仍需要在本地导出文件，以确保它是使用 Unicode 编码进行保存并包含 BOM。
  
运行下面的命令，以在本地保存词典：
  
```
Set-Content $updatedTerms -Path "C:\myPath\terms.txt"
```

现在只需打开文件，添加其他关键字，并使用 Unicode 编码 (UTF-16) 保存文件即可。现在将上传更新后的关键字，并就地更新词典。
  
```
PS> Set-DlpKeywordDictionary -Identity "Diseases" -FileData (Get-Content -Path "C:myPath\terms.txt" -Encoding Byte -ReadCount 0)
```

至此，词典已就地更新。请注意，`Identity` 字段需要使用词典名称。如果还要使用 `set-` cmdlet 更改词典名称，只需将包含新词典名称的 `-Name` 参数添加到上面的命令中即可。 
  
## <a name="using-keyword-dictionaries-in-custom-sensitive-information-types-and-dlp-policies"></a>在自定义敏感信息类型和 DLP 策略中使用关键字词典

关键字字典可用作自定义敏感信息类型的匹配要求，也可用作敏感信息类型本身。无论是上述哪种情况，都必须[使用 Office 365 安全与合规中心 PowerShell 创建自定义敏感信息类型](create-a-custom-sensitive-information-type-in-scc-powershell.md)。请按照链接文章中的说明操作，创建敏感信息类型。创建 XML 后，必须有字典的 GUID 标识符才能使用它。
  
```
<Entity id="9e5382d0-1b6a-42fd-820e-44e0d3b15b6e" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef=". . ."/>
    </Pattern>
</Entity>
```

若要获得词典标识，请运行下面的命令，并复制 **Identity** 属性值： 
  
```
Get-DlpKeywordDictionary -Name "Diseases"
```

此命令的输出如下所示：
  
```
RunspaceId        : 138e55e7-ea1e-4f7a-b824-79f2c4252255
Identity          : 8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f
Name              : Diseases
Description       : Names of diseases and injuries from ICD-10-CM lexicon
KeywordDictionary : aarskog's syndrome, abandonment, abasia, abderhalden-kaufmann-lignac, abdominalgia, abduction contracture, abetalipo
                    proteinemia, abiotrophy, ablatio, ablation, ablepharia, abocclusion, abolition, aborter, abortion, abortus, aboulomania,
                    abrami's disease, abramo
IsValid           : True
ObjectState       : Unchanged
```

将标识粘贴到自定义敏感信息类型的 XML 中，并上传它。此时，词典会出现在敏感信息类型列表中，你可以直接在策略中使用它，同时指定必须匹配多少个关键字。
  
```
<Entity id="d333c6c2-5f4c-4131-9433-db3ef72a89e8" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="8d2d44b0-91f4-41f2-94e0-21c1c5b5fc9f" />
      </Pattern>
    </Entity>
    <LocalizedStrings>
      <Resource idRef="d333c6c2-5f4c-4131-9433-db3ef72a89e8">
        <Name default="true" langcode="en-us">Diseases</Name>
        <Description default="true" langcode="en-us">Detects various diseases</Description>
      </Resource>
    </LocalizedStrings>
```


