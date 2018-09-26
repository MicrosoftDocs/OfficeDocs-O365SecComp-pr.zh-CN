---
title: 电子数据展示搜索结果中的重复数据删除
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid: MOE150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
description: 您可以选择要消除重复，以便只有一个电子邮件的副本将导出即使相同的消息的多个实例可能已发现在不同的邮箱中导出的电子数据展示搜索结果。
ms.openlocfilehash: 5e54f0e5841fdbd29d1ab8b6b9509ff06e827920
ms.sourcegitcommit: 7956955cd919f6e00b64e4506605a743c5872549
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "25038005"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>电子数据展示搜索结果中的重复数据删除

本文介绍如何电子数据展示搜索结果的重复数据删除的工作方式，并说明消除算法的限制。
  
当使用 Office 365 电子数据展示工具导出电子数据展示搜索的结果，您可以选择要消除重复导出的结果。这意味着什么？当您启用重复数据删除 （默认情况下，消除不启用），即使相同的消息的多个实例可能已发现搜索邮箱中导出只有一个电子邮件的副本。重复数据删除可帮助您节省时间通过减少您需要查看和分析后导出搜索结果的项目数。但是，务必要了解重复数据删除的工作方式，并注意有限制可能会导致在导出过程标记为重复的唯一项的算法。
  
## <a name="how-duplicate-messages-are-identified"></a>如何识别重复的邮件

Office 365 电子数据展示工具使用下面的电子邮件属性的组合来确定是否重复一条消息：
  
- **InternetMessageId** -此属性指定电子邮件，它是指的是特定邮件的特定版本的全局唯一标识符的 Internet 消息的标识符。此 ID 是由发件人的电子邮件客户端程序或将邮件发送的主机电子邮件系统生成的。如果某人向多个收件人发送邮件，Internet 邮件 ID 将相同的邮件的每个实例。对原始邮件的后续修订将收到的其他消息标识符。 
    
- **ConversationTopic** -他属性指定对话线程的邮件的主题。**ConversationTopic**属性的值是描述对话的总体主题的字符串。那么组成的初始消息和在答复发送到的初始消息的所有邮件。同一对话中的邮件具有相同**ConversationTopic**属性的值。此属性的值通常是从初始消息产生对话的主题行。 
    
- **BodyTagInfo** -这是一个内部 Exchange 存储区属性。此属性的值的计算方法检查邮件的正文中的各种属性。此属性用于标识邮件正文中的差异。 
    
在电子数据展示导出过程中，这三个属性进行比较的每个与搜索条件匹配的邮件。如果这些属性相同的两个 （或多个） 的邮件，这些消息确定要重复项，并且结果是，如果启用重复数据删除只有一个副本的邮件将被导出。将导出的邮件被称为"源项"。导出的搜索结果中包含**Results.csv**和**Manifest.xml**报表包含重复的邮件的信息。在**Results.csv**文件中，由**项重复**列中具有一个值，标识重复的邮件。此列中的值与已导出的邮件**项标识**列中的值匹配。 
  
下图显示如何重复的消息与搜索结果导出**Results.csv**和**Manifest.xml**报告中显示。这些报告不包括上文所述，消除算法中所使用的电子邮件属性。相反，报告包括分配给由 Exchange 存储的项目的**项目 Identity**属性。 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>Results.csv 报告 （在 Excel 中查看）
  
![Results.csv 报告中查看有关重复项的信息](media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Manifest.xml 报告 （在 Excel 中查看）
  
![Manifest.xml 报告中查看有关重复项的信息](media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
此外，导出报告中包含重复的邮件中的其他属性。这包括重复消息位于，邮件被发送到通讯组，以及是否邮件已将抄送或密件抄送 ' d 到另一个用户的邮箱。
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>消除算法的限制

有可能导致来获取标记为重复项的唯一项的重复数据删除算法的已知的限制。务必要了解这些限制，这样可以决定使用可选的重复数据删除功能。
  
没有一种情况其中消除功能可能会错误地标识为重复一条消息和不将其导出 （但仍为导出报告中重复引文它）。这些是用户编辑，但不发送的邮件。例如，假设用户在 Outlook 中选择一条消息，将复制的消息，内容，然后将其粘贴到新邮件中。然后在用户更改的一个副本通过删除或添加附件，或更改的主题行或正文本身。如果这两个消息相匹配的电子数据展示搜索查询，如果搜索结果导出时，会启用重复数据删除将导出的邮件的唯一一个。因此，即使原始消息或复制的邮件已更改，都不修订后的邮件发送和因此或者没有更新**InternetMessageId** **ConversationTopic**和**BodyTagInfo**属性的值。如前所述，将导出报告中列出两条消息，但 
  
请注意，启用写入时复制页上保护功能时，如所示的置于诉讼保留或就地保留的邮箱的大小写，唯一邮件还可以标记为重复项。写入时复制功能将复制原始邮件 （并将其保存到用户的可恢复邮件文件夹中的版本文件夹） 保存到原始项目的修订之前。在这种情况下，修订后的副本和 （在可恢复邮件文件夹中） 原始邮件可能被认为是重复的邮件，因此只有将能导出。
  
> [!IMPORTANT]
> 如果消除算法的限制可能会影响搜索结果的质量，则不应导出项目时启用重复数据删除。如果本节中所述的情况很可能无法在搜索结果中，一个因素，并且您希望减少最有可能是重复的项目数，则应考虑启用重复数据删除。 
  
## <a name="more-information"></a>更多信息

- 导出搜索结果使用的以下电子数据展示工具之一，本文中的信息时适用：
    
  - Office 365 安全性内容搜索&amp;合规性中心
    
  - Exchange Online 中的就地电子数据展示
    
  - SharePoint Online 中的电子数据展示中心
    
- 有关导出搜索结果的详细信息，请参阅：
    
  - [从 Office 365 安全性导出搜索结果&amp;合规性中心](export-search-results.md)
    
  - [从 Office 365 安全性导出内容的搜索报告&amp;合规性中心](export-a-content-search-report.md)
    
  - [到 PST 文件的导出的就地电子数据展示搜索结果](https://go.microsoft.com/fwlink/p/?linkid=832671)
    
  - [在电子数据展示中心导出内容和创建报表](https://support.office.com/article/7b2ea190-5f9b-4876-86e5-4440354c381a)
