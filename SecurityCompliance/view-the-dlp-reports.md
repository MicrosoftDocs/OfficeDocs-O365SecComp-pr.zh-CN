---
title: 查看数据丢失防护报告
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 41eb4324-c513-4fa5-91c8-8fbd8aaba83b
description: 与 Office 365 中的 DLP 报告，您可以快速查看 DLP 策略匹配、 重写或误报; 的数请参阅是否他们正在向上或向下随时间推移趋势;以不同方式; 筛选报表和通过选择在图表上线上的某个点查看其他详细信息。
ms.openlocfilehash: 379e66fc3f2611cf338739d030c2b1d48e7416d8
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "23013906"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>查看数据丢失防护报告

创建数据丢失防护 (DLP) 策略后，您需要确认他们正在使用为您应和帮助您保持兼容。使用 DLP 报告 Office 365 安全性&amp;合规性中心，您可以快速查看：
  
- **DLP 策略匹配**此报表显示一段时间的 DLP 策略匹配的计数。您可以按日期、 位置、 策略或操作筛选报告。您可以使用此报告： 
    
  - 调整或优化您的 DLP 策略，当您在测试模式下运行它们。您可以查看匹配内容的特定规则。
    
  - 重点关注特定的时间段，并了解峰值和发展趋势的原因。
    
  - 发现违反组织的 DLP 策略的业务流程。
    
  - 通过查看操作应用于的内容，了解 DLP 策略的任何业务影响。
    
  - 通过显示该策略的匹配结果，验证该策略是否遵守特定 DLP 策略。
    
  - 查看最多的用户的列表，并重复用户分配给您的组织中的事件。
    
  - 查看组织中的顶部的敏感信息类型列表。
    
- **DLP 事件**此报告还会显示策略匹配随时间推移，如策略匹配报告。但是，策略匹配规则级别; 报表显示匹配项例如，如果电子邮件匹配三个不同的规则，该策略匹配报表显示三个不同行项。相比之下，事件报告将显示匹配项级别;例如，如果电子邮件匹配三个不同的规则，事件报告将显示的内容的单个行项。 
    
  由于不同聚合报告计数，策略匹配报告是更好的匹配标识与特定规则和微调 DLP 策略。事件报告是内容的用于标识特定片段 DLP 策略有问题的更好。
    
- **DLP 误报和覆盖**如果您的 DLP 策略允许用户将其重写或报告为误报，此报告显示随时间这种情况下的计数。您可以按日期、 位置或策略筛选报告。您可以使用此报告： 
    
  - 调整或通过查看哪些策略会引发大量误报优化您的 DLP 策略。
    
  - 查看用户提交的时它们通过覆盖该策略解析策略提示的理由。
    
  - 发现与通过承担大量的用户的有效业务流程的 DLP 策略冲突将重写。
    
所有 DLP 报告可以都显示的最新的四个月的时间段中的数据。最新的数据可能需要 24 小时要显示在报告中。
  
您可以安全中找到这些报告&amp;合规性中心\>**报告** \> **仪表板**。
  
![DLP 策略匹配报告](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>查看由重写为用户提交理由

如果您的 DLP 策略允许用户覆盖它，您可以使用误报以及如何重写报表以查看策略提示中的用户提交的文本。
  
![理由字段中的 DLP 误报和覆盖报告的详细信息](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>执行上见解和建议的操作

报告可显示见解和建议，您可以单击红色的警告图标以查看有关潜在问题的详细信息并采取可能补救措施。
  
![单击以查看详细信息和要执行的操作的真知灼见图标](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="find-the-cmdlets-for-the-dlp-reports"></a>查找适用于 DLP 报告 cmdlet

要用于安全的大部分 cmdlet&amp;合规性中心，您需要：
  
1. [连接到 Office 365 安全性&amp;合规性中心使用远程 PowerShell](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. 使用下列任一[Office 365 安全性&amp;合规性中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)
    
但是，DLP 报告需要拉跨 Office 365，包括 Exchange Online 中的数据。因此，DLP 报告的 cmdlet 是在 Exchange Online Powershell 中可用 — 不在安全&amp;合规性中心 Powershell。因此，若要使用 DLP 报告 cmdlet，您需要：
  
1. [Connect to Exchange Online using remote PowerShell](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. 使用这些 cmdlet 的任何 DLP 报告：
    
      - [Get-DlpDetectionsReport](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [Get-DlpDetailReport](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

