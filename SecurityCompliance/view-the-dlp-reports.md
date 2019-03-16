---
title: 查看数据丢失防护报告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 6/7/2018
ms.audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
description: 使用 Office 365 中的 dlp 报告, 您可以快速查看 dlp 策略匹配、覆盖或误报的数量;查看它们是按时间趋势上升还是下降;以不同的方式筛选报表;并在图表上的某一行上选择一个点, 以查看其他详细信息。
ms.openlocfilehash: 447245f945bd777f56cca71320a72a9d9dd8720e
ms.sourcegitcommit: 8657e003ab1ff49113f222d1ee8400eff174cb54
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2019
ms.locfileid: "30639019"
---
# <a name="view-the-reports-for-data-loss-prevention"></a>查看数据丢失防护报告

创建数据丢失防护 (DLP) 策略后, 您需要验证它们是否按预期工作, 并帮助您保持合规性。 在 Office 365 安全&amp;合规中心中使用 DLP 报告, 您可以快速查看:
  
- **DLP 策略匹配**此报告显示一段时间内 DLP 策略匹配项的计数。 您可以按日期、位置、策略或操作筛选报告。 您可以使用此报告执行以下操作: 
    
  - 在测试模式下运行 DLP 策略时对其进行调整或优化。 您可以查看与内容匹配的特定规则。
    
  - 重点关注特定的时间段，并了解峰值和发展趋势的原因。
    
  - 发现违反组织的 DLP 策略的业务流程。
    
  - 通过查看应用于内容的操作来了解 DLP 策略的任何业务影响。
    
  - 通过显示该策略的匹配结果，验证该策略是否遵守特定 DLP 策略。
    
  - 查看最常用用户的列表, 并重复在您的组织中参与事件的用户。
    
  - 查看组织中的最高敏感信息类型的列表。
    
- **DLP 事件**此报告还显示策略匹配一段时间, 如策略匹配报告。 但是, 策略匹配报告将显示规则级别的匹配项;例如, 如果电子邮件符合三个不同的规则, 则策略匹配报告将显示三个不同的行项目。 相比之下, 事件报告在项目级别显示匹配项;例如, 如果电子邮件与三个不同的规则匹配, 则事件报告将显示该内容的单个行项目。 
    
  由于报告计数的聚合方式不同, 因此策略匹配报告可更好地识别与特定规则的匹配项, 并精确优化 DLP 策略。 事件报告更适合标识对 DLP 策略存在问题的特定内容片段。
    
- **DLP 误报和重写**如果您的 DLP 策略允许用户覆盖它或报告误报, 则此报告将显示一段时间内此类实例的计数。 您可以按日期、位置或策略筛选报告。 您可以使用此报告执行以下操作: 
    
  - 通过查看哪些策略会导致大量误报来调整或优化 DLP 策略。
    
  - 查看用户通过覆盖策略解析策略提示时提交的理由。
    
  - 通过提供大量用户覆盖来发现 DLP 策略与有效业务流程发生冲突的位置。
    
所有 DLP 报告都可以显示最近四个月的时间段内的数据。 最新的数据可能需要长达24小时才能显示在报告中。
  
您&amp;可以在安全合规性中心\> **报告** \> **仪表板**中找到这些报告。
  
![DLP 策略匹配报告](media/117d20c9-d379-403f-ad68-1f5cd6c4e5cf.png)
  
## <a name="view-the-justification-submitted-by-a-user-for-an-override"></a>查看用户为替代而提交的理由

如果你的 DLP 策略允许用户覆盖它, 则可以使用误报和覆盖报告查看用户在策略提示中提交的文本。
  
![DLP 误报和重写报告详细信息中的调整字段](media/e11e3126-026d-4e77-a16d-74a0686d1fa3.png)
  
## <a name="take-action-on-insights-and-recommendations"></a>对见解和建议采取措施

报告可以显示见解和建议, 在其中可以单击红色警告图标以查看有关潜在问题的详细信息, 并采取可能的补救措施。
  
![单击见解图标可查看详细信息和要执行的操作](media/51782036-7299-4960-8175-75c2b1637159.png)
  
## <a name="permissions-for-dlp-reports"></a>DLP 报告的权限

若要在 Security & 合规性中心中查看 DLP 报告, 您必须分配:

- Exchange 管理中心中的**安全读者**角色。 默认情况下, 将此角色分配给 Exchange 管理中心中的 "组织管理" 和 "安全读者" 角色组。

- Security & 合规性中心中**仅查看 DLP 合规性管理**角色。 默认情况下, 将此角色分配给安全 & 合规中心中的合规性管理员、组织管理、安全管理员和安全读者角色组。

- Exchange 管理中心中的 "**仅查看收件人**" 角色。 默认情况下, 将此角色分配给 Exchange 管理中心中的合规性管理、组织管理和仅查看组织管理角色组。

## <a name="find-the-cmdlets-for-the-dlp-reports"></a>查找 DLP 报告的 cmdlet

若要将大多数 cmdlet 用于安全&amp;合规性中心, 您需要执行以下操作:
  
1. [使用远程 PowerShell 连接到 Office 365 安全与合规中心](http://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)
    
2. 使用这些[Office 365 安全&amp;合规中心 cmdlet](http://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)中的任何一个
    
但是, DLP 报告需要跨 Office 365 请求获取数据, 包括 Exchange Online。 因此, DLP 报告的 cmdlet 在 Exchange Online powershell 中可用, 而不在安全&amp;合规中心 powershell 中。 因此, 若要使用 DLP 报告的 cmdlet, 需要执行以下操作:
  
1. [Connect to Exchange Online using remote PowerShell](http://go.microsoft.com/fwlink/?LinkID=799773&amp;clcid=0x409)
    
2. 为 DLP 报告使用以下任一 cmdlet:
    
      - [get-dlpdetectionsreport](http://go.microsoft.com/fwlink/?LinkID=799774&amp;clcid=0x409)
    
      - [get-dlpdetailreport](http://go.microsoft.com/fwlink/?LinkID=799775&amp;clcid=0x409)
    

