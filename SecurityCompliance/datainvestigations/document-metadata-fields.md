---
title: 数据调查中的文档元数据字段 (预览)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: ''
ms.openlocfilehash: c4a7c479d730d5256efabe9120960b1590094779
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32258120"
---
# <a name="document-metadata-fields-in-data-investigations-preview"></a>数据调查中的文档元数据字段 (预览)

下表列出了数据调查 (预览) 调查中的证据集内的文档的元数据字段。 该表指示元数据字段的名称, 该字段是否可以在证据集中运行查询时进行搜索, 无论在证据集内查看所选文档的文件元数据时是否存在该字段, 以及何时是否包含该字段导出文档。 

> [!NOTE]
> 在 "**证据集**" 列中可搜索的括号中的值是您可以搜索的属性的名称。 "**文件元数据**" 列中的可查看括号中的值是您在查看文件元数据时显示的属性的名称。

|**字段名** </br>|**在证据集中可搜索** |**可在文件元数据中查看** |**Exported** |
|:-------------------------- |:---------------------------------------- |:------------------------|:------------------|
|Case 标记                  | 是 (标记)                                      |                         | 是         |
|合规性标签          |                                                 |                         | 是         |
|复合路径              |                                                 |                         | 是         |
|容器 ID               |                                                 |                         | 是         |
|会话索引         |                                                 |                         | 是         |
|Custodian                  | 是 (保管人)                                 |   是 (保管人)       | 是         |
|数据源                | 是 (源)                                    |   是 (工作负载)          | 是         |
|日期                       | 是 (date)                                      |   是 (UTC 日期)        | 是         |
|Deduped 复合路径      |                                                 |                         | 是         |
|Deduped 保管人         |                                                 |                         | 是         |
|Deduped 文件 id           |                                                 |                         | 是         |
|文档作者                | 是 (作者) *                                   |    是 (作者)         | 是         |
|文档注释               | 是 (注释)                                  |                         | 是         |
|Doc 公司                |                                                 |                         | 是         |
|文档创建日期           | 是 (createdTime) *                              |    是 (创建时间)   | 是         |
|修改的文档日期          | 是 (lastModifiedDate) *                         |                         | 是         |
|Doc 关键字               |                                                 |                         | 是         |
|文档上次保存者          |                                                 |                         | 是         |
|修改的文档            |                                                 |                         | 是         |
|文档主题                |                                                 |  是 (主题/标题)    | 是         |
|文档模板               |                                                 |                         | 是         |
|文档标题                  | 是 (标题)                                     |  是 (标题)            | 是         |
|文档版本                |                                                 |                         | 是         |
|主要主题             | 是 (dominantTheme)                             |  是 (主要主题)   | 是         |
|重复子集           |                                                 |                         | 是         |
|电子邮件操作               |                                                 |                         | 是         |
|电子邮件密件抄送                  | 是 (bcc)                                       |                         | 是         |
|电子邮件抄送                   | 是 (抄送)                                        |                         | 是         |
|电子邮件会话 ID      |                                                 |                         | 是         |
|接收的电子邮件日期        | 是 (已接收)                                  |   是 (已接收)        | 是         |
|发送电子邮件的日期            | 是 (已发送)                                      |   是 (已发送)            | 是         |
|电子邮件包含附件       |                                                 |                         | 是         |
|电子邮件重要性           |                                                 |                         | 是         |
|电子邮件 internet 标头     |                                                 |                         | 是         |
|电子邮件级别                |                                                 |                         | 是         |
|电子邮件 ID           |                                                 |                         | 是         |
|电子邮件参与者域  | 是 (participantDomains)                        |                         | 是         |
|电子邮件参与者         | 是 (参与者)                              |                         | 是         |
|电子邮件收件人域    | 是 (recipientDomains)                          |                         | 是         |
|电子邮件收件人           | 是 (收件人)                                |                         | 是         |
|电子邮件安全性             |                                                 |                         | 是         |
|电子邮件发件人               | 是 (发件人)                                    |   是 (发件人)          | 是         |
|电子邮件发件人域        | 是 (senderDomain)                              |                         | 是         |
|电子邮件敏感度          |                                                 |                         | 是         |
|电子邮件集                  | 是 (emailSetId)                                |   是 (EmailSetID)      | 是         |
|电子邮件主题              | 是 (主题)                                   |   是 (主题/标题)   | 是         |
|电子邮件线索               |                                                 |                         | 是         |
|电子邮件至                   | 是 (to)                                        |                         | 是         |
|错误代码                 | 是 (processingStatus)                          |                         | 是         |
|导出本机路径         |                                                 |                         | 是         |
|提取的文本长度      |                                                 |                         | 是         |
|提取的文本路径        |                                                 |                         | 是         |
|系列 ID                  | 是 (familyId)                                  |   是 (FamilyId)        | 是         |
|系列大小                |                                                 |                         | 是         |
|File 类                 | 是 (fileClass)                                 |   是 (File 类)      | 是         |
|文件 ID                    | 是 (fileId)                                    |   是 (Id)              | 是         |
|包含文本                   |                                                 |                         | 是         |
|包含类型             | 是 (inclusiveType)                             |   是 (包含类型)  | 是         |
|输入日期已修改        |                                                 |                         | 是         |
|输入文件 ID              |                                                 |                         | 是         |
|输入路径                 |                                                 |                         | 是         |
|Internet 邮件 ID        |                                                 |                         | 是         |
|代表          | 是 (markAsRepresentative)                      |                         | 是         |
|Item 类                 |                                                 |                         | 是         |
|加载 ID                    | 是 (loadId)                                    |                         | 是         |
|位置名称              |                                                 |                         | 是         |
|标记为透视            | 是 (markAsPivot)                               |   是 (标记为透视) | 是         |
|邮件类型               | 是 (messageKind)                               |                         | 是         |
|本机扩展           |                                                 |                         | 是         |
|本机文件名           |                                                 |    是 (FileName)      | 是         |
|本机 MD5                 |                                                 |                         | 是         |
|本机 SHA 256             |                                                 |                         | 是         |
|本机大小                | 是 (大小)                                      |   是 (NativeSize)     | 是         |
|本机类型                | 是 (文件类型)                                  |   是 (文件类型)       | 是         |
|ND ET 排序排除附加     |                                                 |                         | 是         |
|ND ET 排序 (包括附加)     |                                                 |                         | 是         |
|ND 集                     |                                                 |                         | 是         |
|O365 作者               | 是 (作者) *                                   |   是 (发件人/作者)   | 是         |
|O365 创建者            |                                                 |                         | 是         |
|O365 创建日期          | 是 (createdTime) *                              |                         | 是         |
|O365 修改日期         | 是 (lastModifiedDate) *                         |   是 (最后修改日期) | 是      |
|O365 修改者           |                                                 |                         | 是         |
|父节点                |                                                 |                         | 是         |
|透视 ID                   | 是 (pivotId)                                   |  是 (PivotID)          | 是         |
|收件人计数            |                                                 |                         | 是         |
|行号                 |                                                 |                         | 是         |
|集 ID                     |                                                 |                         | 是         |
|先设置顺序 inclusives |                                                 |                         | 是         |
|相似性百分比         |                                                 |                         | 是         |
|主题列表                | 是 (themesList)                                | 是 (主题列表)       | 是         |
|Word count                 | 是 (wordCount)                                 |                         | 是         |
|相关性分数 (问题)    | 是 (relevanceScore_issueNum)                   |                         |             |
|读取百分点值 (问题)    | 是 (readPercentile_issueNum)                   |                         |             |
|相关性标记 (问题)      | 是 (relevanceTag_issueNum)                     |                         |             |
|||||

  \*对于这些字段, 如果文档中有嵌入的值, 则搜索将设置这些值的优先级;否则, 它将尝试显示来自 Office 365 的值。
