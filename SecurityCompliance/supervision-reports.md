---
title: 监督报表
ms.author: brendonb
author: brendonb
manager: laurawi
ms.date: 5/12/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2a762db5-e1c9-4c09-aa8e-bef49ce97209
description: 使用监督报告以查看的电子邮件需要合规性查看以及谁应执行它。
ms.openlocfilehash: e18d083c0aad8be945c628516e593462da8e3898
ms.sourcegitcommit: 36c5466056cdef6ad2a8d9372f2bc009a30892bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "22525002"
---
# <a name="supervision-reports"></a>监督报表

监督策略定义其组织中的通信需要审阅的合规性，以及谁将执行这些 reviews （英文）。使用监督报表查看级别的策略和审阅者的查看活动。对于每个策略，您还可以查看活动的当前状态查看 live 统计信息。[了解更多有关监督策略](configure-supervision-policies.md)。 
  
> [!NOTE]
> 使用监督策略要求对您的组织的 Office 365 E5 订阅。如果您不具有该计划，并且想要尝试监督，您还可以[注册试用版的 Office 365 企业 E5](https://go.microsoft.com/fwlink/p/?LinkID=698279)。 
  
您可以使用监督报告：
  
- 验证您的策略都按预期工作。 
    
- 找出多少封电子邮件将被标识进行审阅。
    
- 找出多少封电子邮件不符合以及哪些传递审阅。此信息可帮助您决定是否要调整您的策略或更改审阅者的人数。
    
## <a name="view-the-supervision-report"></a>查看监督报告

1. 登录到[安全&amp;合规性中心](https://protection.office.com/)使用您有权查看监督报告的 Office 365 组织中的管理帐户的凭据。 
    
2. 转到**报告** \> **仪表板**。您将看到监督的报告小部件和其他报告您有权访问。
    
3. 单击要打开详细的报告页上的**监督**构件。 
    
> [!NOTE]
> 如果您不能访问**报告**页上，检查您监督审阅角色组的成员[进行监督在组织中可用](configure-supervision-policies.md#SRavailable)中所述。要包含在此角色组，可以创建和管理监督策略并运行报告。 
  
## <a name="how-to-use-the-report"></a>如何使用报告

当监督策略识别电子邮件进行审阅时，电子邮件传递到审阅者的监督文件夹中 Outlook 和 Outlook web 应用程序。此报告列出了在审阅过程中每个阶段每项策略的名称和通信数目。
  
使用报告：
  
- 查看数据的所有或特定的策略。
    
- 查看按 （如符合、 Questionable 等） 的标记类型、 审阅者或消息类型分组的数据。
    
- 将数据导出到 CSV 文件。
    
- 筛选上查看活动日期、 标记类型、 审阅者、 消息类型基于的数据。
    
下面是您可能会看到**标记类型**列中的值的细分。 
  
|**标记类型**|**含义**|
|:-----|:-----|
|未检查  <br/> |尚未评审的电子邮件数。这些电子邮件正在等待审阅在 Outlook 中的审阅者的监督文件夹中。  <br/> |
|符合标准  <br/> |电子邮件数审核和标记为兼容。需要没有进一步的操作。  <br/> |
|可疑  <br/> |电子邮件数审核和标记可疑。这会作为一个标志;其他审阅人可以帮助检查电子邮件是否需要合规性的调查。  <br/> |
|不兼容 （活动）  <br/> |当前正在调查审阅者的不符合电子邮件数。  <br/> |
|不兼容 （解析）  <br/> |不兼容的电子邮件的审阅者调查和解析数。  <br/> |
   
## <a name="more-details"></a>更多详细信息

- 将出现在此报告中之前，必须首先设置监督策略。
    
- 如果删除了策略，仍显示历史数据。但是，它们显示为"非存在策略，"和**导出**函数不可用。 
    
- 如果报表不显示任何数据，默认情况下，则可能是因为当前日期范围没有要显示的数据。在这些情况下，使用**筛选器**控件更改的日期范围。 
    

