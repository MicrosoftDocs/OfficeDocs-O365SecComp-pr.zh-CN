---
title: 搜索和删除邮件 - 管理员帮助
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/20/2017
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.custom: TN2DMC
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8c36bb03-e716-4fdd-9958-4aa7a2a1db42
description: 管理员可以使用 Search-Mailbox cmdlet 来搜索用户邮箱，然后从邮箱中删除邮件。
ms.openlocfilehash: c5f727d7772e23cc8723eee6a45e51e3ac074648
ms.sourcegitcommit: e9dca2d6a7838f98bb7eca127fdda2372cda402c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2018
ms.locfileid: "23002820"
---
# <a name="search-for-and-delete-messages---admin-help"></a>搜索和删除邮件 - 管理员帮助
  
管理员可以使用 **Search-Mailbox** cmdlet 来搜索用户邮箱，然后从邮箱中删除邮件。 
  
若要使用一个步骤搜索并删除邮件，请运行带有  **DeleteContent** 开关的 _Search-Mailbox_ cmdlet。但是，在执行此操作时，无法预览搜索结果或生成搜索返回的邮件的日志，您可能意外删除不想删除的邮件。若要在删除搜索中找到的邮件之前预览这些邮件的日志，需要运行带有  **LogOnly** 开关的 _Search-Mailbox_ cmdlet。 
  
作为额外保护措施，可以使用  _TargetMailbox_ 和  _TargetFolder_ 参数，首先将邮件复制到另一个邮箱。这样可保留已删除邮件的副本，以防需要再次访问这些邮件。 
  
## <a name="before-you-begin"></a>准备工作

- 估计完成时间：10 分钟。实际时间可能因邮箱大小和搜索查询而异。
    
- 不能使用 Exchange 管理中心 (EAC) 执行这些过程。必须使用命令行管理程序。
    
- 您需要分配有以下两个管理角色才能在用户邮箱中搜索和删除邮件：
    
  - **邮箱搜索**-此角色允许您跨组织中的多个邮箱搜索的邮件。默认情况下，管理员不分配此角色。若要指定自己此角色，以便您可以搜索邮箱，请将自己添加为发现管理角色组的成员。请参阅[将用户添加到发现管理角色组](http://technet.microsoft.com/library/729e09d8-614b-431f-ae04-ae41fb4c628e.aspx)。
    
  - **邮箱导入导出**-此角色可以从用户的邮箱中删除邮件。默认情况下，此角色不分配给任何角色组。若要从用户的邮箱中删除邮件，您可以向组织管理角色组添加邮箱导入导出角色。有关详细信息，请参阅[管理角色组](http://technet.microsoft.com/library/ab9b7a3b-bf67-4ba1-bde5-8e6ac174b82c.aspx)中的"将角色添加到角色组"部分。 
    
- 如果要从中删除邮件的邮箱启用了单个项目恢复，则必须首先禁用该功能。有关详细信息，请参阅[启用或禁用邮箱的单个项目恢复](http://technet.microsoft.com/library/2e7f1bcd-8395-45ad-86ce-22868bd46af0.aspx)。
    
- 如果您要从中删除邮件的邮箱置于保持状态，建议您先咨询您的记录管理或法律部门之前保留中移除并删除邮箱内容。您获得批准后，请按照列出[Clean Up Recoverable Items Folder](http://technet.microsoft.com/library/82c310f8-de2f-46f2-8e1a-edb6055d6e69.aspx)主题中的步骤。
    
- 使用 **Search-Mailbox** cmdlet，最多可搜索到 10,000 个邮箱。如果你是 Exchange Online 组织，并拥有超过 10,000 个邮箱，则可以使用合规性搜索功能（或相应的 **New-ComplianceSearch** cmdlet）搜索任意数量的邮箱。然后，你可以使用 **New-ComplianceSearchAction** cmdlet 删除由合规性搜索返回的邮件。有关详细信息，请参阅 [从你的 Office 365 组织搜索和删除电子邮件](https://go.microsoft.com/fwlink/p/?LinkId=786856)。
    
- 如果添加一个搜索查询（通过使用  *SearchQuery*  参数）， **Search-Mailbox** cmdlet 最多返回搜索结果中的 10,000 个项目。因此，如果添加一个搜索查询，则可能需要多次运行 **Search-Mailbox** 命令才能将 10,000 多个项目删除。 
    
- 运行**Search-mailbox** cmdlet 时，还将搜索用户的存档邮箱。同样，使用**Search-mailbox** cmdlet 与_DeleteContent_开关时，将删除主存档邮箱中的项目。要防止这样，您可以包括*DoNotIncludeArchive*开关。此外，我们建议不用于_DeleteContent_开关删除邮件在 Exchange Online 邮箱的自动扩展启用了存档因为可能出现意外的数据丢失。 
    
## <a name="search-messages-and-log-the-search-results"></a>搜索邮件并记录搜索结果

本示例在 April Stewart 的邮箱中搜索 Subject 字段中包含"Your bank statement"短语的邮件，并将搜索结果记录在管理员邮箱的 SearchAndDeleteLog 文件夹中。不会将邮件复制到目标邮箱或从目标邮箱删除。
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

此示例将搜索组织的所有邮箱，查找文件名中包含"特洛伊木马"一词的任何类型的附加文件的邮件，并向管理员的邮箱发送一封日志邮件。
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery attachment:trojan* -TargetMailbox administrator -TargetFolder "SearchAndDeleteLog" -LogOnly -LogLevel Full
```

有关详细的语法和参数信息，请参阅 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。
  
 
## <a name="search-and-delete-messages"></a>搜索并删除邮件

本示例在 April Stewart 的邮箱中搜索 Subject 字段中包含"Your bank statement"短语的邮件，然后从源邮箱中删除这些邮件，而不将搜索结果复制到另一个文件夹。如前所述，您需要分配"邮箱导入导出"管理角色才能从用户邮箱删除邮件。
  
> [!IMPORTANT]
> 在使用带有  **DeleteContent** 开关的 _Search-Mailbox_ cmdlet 时，会从源邮箱中永久删除邮件。在永久删除邮件之前，建议您在删除搜索中找到的邮件之前使用  _LogOnly_ 开关生成这些邮件的日志，或是在从源邮箱中删除这些邮件之前将其复制到另一个邮箱。 
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -DeleteContent
```

本示例在 April Stewart 的邮箱中搜索 Subject 字段中包含"Your bank statement"短语的邮件，将搜索结果复制到 BackupMailbox 邮箱中的 AprilStewart-DeletedMessages 文件夹，然后从 April 的邮箱中删除这些邮件。
  
```
Search-Mailbox -Identity "April Stewart" -SearchQuery 'Subject:"Your bank statement"' -TargetMailbox "BackupMailbox" -TargetFolder "AprilStewart-DeletedMessages" -LogLevel Full -DeleteContent
```

此示例将搜索组织的所有邮箱，查找主题行为"下载此文件"邮件，然后将其永久删除。 
  
```
Get-Mailbox -ResultSize unlimited | Search-Mailbox -SearchQuery 'Subject:"Download this file"' -DeleteContent
```

有关详细的语法和参数信息，请参阅 [Search-Mailbox](http://technet.microsoft.com/library/9ee3b02c-d343-4816-a583-a90b1fad4b26.aspx)。

## <a name="using-the--loglevel-full-parameter"></a>使用 -LogLevel Full 参数

在上述部分示例中， _LogLevel_ 参数和  `Full` 值用于记录由 **Search-Mailbox** cmdlet 返回的结果的详细信息。 包含此参数时，将创建电子邮件并将其发送到  _TargetMailbox_ 参数指定的邮箱。日志文件（名为 Search Results.csv 的 CSV 格式文件）附加到此电子邮件，并置于由  _TargetFolder_ 参数指定的文件夹中。运行 **Search-Mailbox** cmdlet 时，日志文件包含搜索结果中的每个邮件的行。 
