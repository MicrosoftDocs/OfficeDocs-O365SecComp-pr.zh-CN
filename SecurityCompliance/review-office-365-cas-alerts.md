---
title: 查看 Office 365 云应用安全中的警报并执行相应操作
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: 使用 Office 365 Cloud App Security 中的 "通知" 页面查看潜在问题并采取措施。 您可以取消或解决通知, 如有必要, 请挂起用户帐户。
ms.openlocfilehash: ddef10293fca7b722a13babdca5c05bbe2398cb3
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32261472"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a>查看 Office 365 云应用安全中的警报并执行相应操作
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|利用率 * * * *|
|:-----|:-----|:-----|:-----|
|[开始评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |[开始部署](turn-on-office-365-cas.md) <br/> |你在这里!  <br/> [后续步骤](#next-steps) <br/> |
   
您可以使用 Office 365 Cloud App Security 中的 "通知" 页面查看潜在问题, 并在需要时执行操作。
  
> [!NOTE]
> 若要执行本文中的任务, 您必须是全局管理员或安全管理员。 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="how-to-get-to-the-alerts-page"></a>如何转到 "通知" 页

1. 转到云应用安全门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 并登录。
  
2. 在屏幕顶部的导航栏中, 选择 "**通知**"。<br/>![在 "通知" 页面上, 您可以查看触发的警报以及执行的任何操作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
 
> [!NOTE]
> 云应用安全警报在安全 & 合规性中心 (转到**警报** > **查看警报**) 中也可见。 但是, 目前您必须在云应用安全门户和 Security & 合规性中心中解决这些警报。 若要了解详细信息, 请参阅[查看云应用安全警报](alert-policies.md#viewing-cloud-app-security-alerts)。) 
 
## <a name="review-and-handle-alerts"></a>查看和处理警报

警报可帮助您识别 Office 365 云环境中您可能想要进一步调查的活动。 您可能还决定根据您看到的警报创建新策略或编辑现有策略。 例如, 如果您看到管理员从奇怪的位置登录, 则可能决定设置一个策略, 以防止管理员从某些位置登录 Office 365。
  
> [!TIP]
> 您可以按**类别**或**严重性**筛选警报, 以便可以先管理最重要的警报。 
  
对于每个通知, 请查看导致其出现的原因, 以便您可以决定要采取的操作。 若要查看有关警报的更多详细信息, 并执行操作 (如解决警报或挂起用户帐户), 请选择 "通知" 以打开 "详细信息" 页。 在 "详细信息" 页上, 您可以查看与警报相关的活动日志、帐户和用户, 并执行以下操作:
  
- **消除**如果警报为误报, 请将其关闭。 您可以选择添加注释, 说明为什么消除了它。 
    
- **解决警报**如果警报是由您知道不是威胁的活动触发的, 请对其进行解析。 您可以选择添加注释, 说明您解决它的原因。 
    
- **挂起**如果您怀疑某个帐户上有未经授权登录, 例如, 当您知道该用户实际位于本地办公室时, 某人从其他国家/地区登录, 则可以在调查正在进行的操作时[挂起该帐户](suspend-or-restore-an-account-in-ocas.md)。 
    
## <a name="next-steps"></a>后续步骤

- [调查活动](investigate-an-activity-in-office-365-cas.md)
    
- [挂起或还原用户帐户](suspend-or-restore-an-account-in-ocas.md)
    
- 查看受支持的[Web 流量日志和数据源](web-traffic-logs-and-data-sources-for-ocas.md)的列表
    
- 查看[Office 365 云应用安全性的利用率活动](utilization-activities-for-ocas.md)
    

