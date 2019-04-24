---
title: Office 365 云应用安全中的活动策略和警报
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 01/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: 使用 Office 365 云应用安全性定义活动策略, 以设置在特定活动发生或发生过于频繁时触发的警报。 通过设置策略来触发通知, 可以通知并监视特定活动。
ms.openlocfilehash: cfa58182ea35551ca3a3807c23e09c9f87c7be82
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32242704"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a>Office 365 云应用安全中的活动策略和警报

|评估 * *\>**|规划 * *\>**|部署 * *\>**|利用率 * * * *|
|:-----|:-----|:-----|:-----|
|[开始评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |你在这里!  <br/> [后续步骤](anomaly-detection-policies-in-ocas.md) <br/> |[开始利用](utilization-activities-for-ocas.md) <br/> |
   
借助 Office 365 云应用安全性, 高级云管理策略将触发发生或发生过于频繁的特定活动的警报。 例如, 假设用户尝试登录到 Office 365, 并在一分钟内失败70次。 假设另一位用户下载7000文件, 或看起来像是从加拿大登录, 而该用户应位于另一个位置。 或者更糟的是, 假设某人的帐户受到威胁, 并且攻击者使用该帐户访问您组织的云应用程序和敏感数据。
  
如果您是[全局管理员或安全管理员](permissions-in-the-security-and-compliance-center.md), 活动警报会在发生类似事件时通知您。 然后, 您可以执行特定操作, 如挂起用户帐户, 直到您能够调查所发生的情况。
  
> [!NOTE]
> office 365 云应用安全策略与[office 365 安全&amp;合规中心中的警报策略](alert-policies.md)不同。 本文中所述的活动策略在 Office 365 云应用安全门户中定义, 可帮助您更好地管理组织的云环境。 
  
## <a name="before-you-begin"></a>准备工作

请确保：
  
- 您的组织具有[Office 365 云应用安全性](office-365-cas-overview.md), 并且该服务已[打开](turn-on-office-365-cas.md)。
    
- 已为您的 Office 365 环境启用[审核日志记录](turn-audit-log-search-on-or-off.md)。 
    
- 您是 Office 365 的全局管理员或安全管理员。
    
## <a name="create-a-new-activity-policy"></a>创建新的活动策略

1. 作为全局管理员或安全管理员, 请转到云应用安全门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 并登录。 <br>将转到 "Office 365 云应用安全策略" 页。<br>![当您转到 Office 365 云应用安全门户时, 将从 "策略" 页开始](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
2. 单击 "**创建策略**", 然后选择 "**活动策略**"。<br>![在 O365 CAS 中创建策略时, 可以在活动策略和异常情况检测策略之间进行选择。](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)
  
3. 在 "**创建活动策略**" 页上, 指定**策略名称**和**说明**。 若要将策略基于默认模板, 请在 "**策略模板**" 列表中选择一个模板, 或在不使用模板的情况下创建自己的策略。<br>![您可以使用 Office 365 云应用安全性创建活动策略。](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)
  
4. 选择**策略严重性**(低、中或高), 以衡量在此策略触发警报时对您有多严重。 这将帮助您在以后查看警报时对其进行筛选。 
    
5. 为此策略选择一个**类别**。 这将帮助您筛选和排序已触发的警报, 或在审阅以进行更改时对策略进行分组。 
    
6. 选择 "**活动筛选器**" 以设置将触发基于此策略的警报的其他操作或指标。 
    
7. 在 "**活动匹配参数**" 下, 指定单个活动匹配筛选器时是否将触发策略违规, 或者在警报触发之前是否需要指定数量的重复活动。<br>如果选择 "**重复活动**", 请指定活动的数量、时间范围, 以及是否会对特定应用程序中的用户或与任何应用程序相同的用户计数冲突。
    
8. (可选) 可以选择 "**创建通知**", 以创建从该策略接收通知的其他通知 (通过电子邮件、短信或两者)。<br>**确保您的电子邮件提供商不会阻止发送`no-reply@cloudappsecurity.com`的电子邮件**。 
  
9. 选择触发警报时应采取的**操作**, 以挂起用户或要求用户再次登录 Office 365 应用。 
    
10. 选择 "**创建**" 以完成策略的创建。 
    
## <a name="next-steps"></a>后续步骤

- [异常情况检测策略](anomaly-detection-policies-in-ocas.md)
    
- [集成您的 SIEM 服务器](integrate-your-siem-server-with-office-365-cas.md)
    
- [查看警报并对其执行操作](review-office-365-cas-alerts.md)
    
- [将 IP 地址分组以简化管理](group-your-ip-addresses-in-ocas.md)
    

