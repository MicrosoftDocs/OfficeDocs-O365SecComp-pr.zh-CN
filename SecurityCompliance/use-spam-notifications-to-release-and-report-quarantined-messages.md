---
title: 在 Office 365 中使用用户垃圾邮件通知来发布和报告已隔离邮件
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 03/14/2019
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 56de4ed5-b0aa-4195-9f46-033d7cc086bc
ms.collection:
- M365-security-compliance
description: 如果管理员为用户启用通知, 则会收到一条通知消息, 其中列出了发送到邮箱的邮件, 并被标识为垃圾邮件、批量邮件或网络钓鱼邮件。 您可以在收到通知后释放或报告邮件。
ms.openlocfilehash: de67987b0028102bdf61889ce54ca4215182e279
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32263434"
---
# <a name="use-user-spam-notifications-to-release-and-report-quarantined-messages-in-office-365"></a>在 Office 365 中使用用户垃圾邮件通知来发布和报告已隔离邮件

如果您的管理员为用户启用了垃圾邮件通知, 您将收到一条通知消息, 其中列出发往您的邮箱的邮件, 而不是被标识为垃圾邮件和隔离的邮件。
  
> [!TIP]
> 如果你是管理员, 并且想要启用此功能, 则可以在[修改默认反垃圾邮件策略](https://go.microsoft.com/fwlink/?LinkId=800313)时选择此选项。 
  
您收到的邮件包括您拥有的垃圾邮件隔离邮件的数量, 以及列表中最后一条消息的日期和时间 (以通用协调时间或 UTC 为单位)。 此列表包含每个邮件的以下内容:
  
- **发件人**隔离邮件的发送名称和电子邮件地址。 
    
- **主题** 隔离邮件的主题行文本。 
    
- **日期** 邮件隔离的日期和时间 (UTC)。 
    
- **尺寸**邮件的大小, 以千字节 (kb) 为单位。 
    
以下是您可以使用隔离邮件执行的操作:

- 如果要在执行操作之前预览内容或标题, 请**预览**邮件。

- 如果要在执行操作之前查看设备上的邮件和附件 (如果有), 请**下载**邮件。

- 如果邮件不是垃圾邮件, 并且您希望 Office 365 将邮件发送到您的邮箱, 则**释放**。

- **发布 &** 如果邮件不是垃圾邮件, 并且您希望 Office 365 将发件人添加到安全发件人和收件人列表中, 以供将来的电子邮件。 请注意, 您的管理员可能有其他组织范围的允许/阻止配置替代安全发件人列表。

- **发布 & 报告**, 如果邮件不是垃圾邮件, 并且您想要将邮件发送到您的邮箱并将其报告给 Microsoft 进行分析。

- 如果您希望 Office 365 将发件人添加到阻止发件人列表, 则**阻止**。

请注意以下事项：
  
- 由于与邮件流规则匹配而被隔离的邮件不会包括在用户隔离的邮件中。 只有垃圾邮件隔离邮件才会列出。
    
- 您可以释放邮件并将其报告为误报（非垃圾邮件），但只能执行一次。
    

