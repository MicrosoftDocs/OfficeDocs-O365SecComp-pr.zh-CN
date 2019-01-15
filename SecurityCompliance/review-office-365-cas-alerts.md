---
title: 查看 Office 365 云应用安全中的警报并执行相应操作
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 97e9c3d9-df89-458e-924b-369becee5532
description: 使用在 Office 365 云应用程序安全性通知页上查看潜在问题并执行操作。可以关闭或解决通知，并有必要，暂停的用户帐户。
ms.openlocfilehash: 2665f4ebc9c5c24b95da64954a606dfc0df99082
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2019
ms.locfileid: "28014824"
---
# <a name="review-and-take-action-on-alerts-in-office-365-cloud-app-security"></a>查看 Office 365 云应用安全中的警报并执行相应操作
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|使用率 ***|
|:-----|:-----|:-----|:-----|
|[启动评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |[开始部署](turn-on-office-365-cas.md) <br/> |在这里 ！  <br/> [后续步骤](#next-steps) <br/> |
   
可以使用在 Office 365 云应用程序安全性通知页以查看潜在的问题，如果需要采取的操作。
  
> [!NOTE]
> 您必须是要执行本文中的任务的全局管理员或 security 管理员程序。请参阅[Permissions in Office 365 安全性&amp;合规性中心](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="how-to-get-to-the-alerts-page"></a>如何获取通知页面

1. 以全局管理员或 security 管理员程序中，转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。 
    
2. 安全中&amp;合规性中心中，选择**警报** \> **管理高级通知**。
    
3. 选择**转到 Office 365 云应用程序安全性**。<br/>![安全中&amp;合规性中心中，选择管理高级通知转到 Office 365 云应用程序安全性](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)
  
4. 在屏幕顶部导航栏中，选择**通知**。<br/>![在通知页中，您可以看到触发的通知和执行任何操作。](media/3b53d4c9-4b13-435d-8547-8c0f9ae6b914.png)
  
## <a name="review-and-handle-alerts"></a>查看并处理通知

通知帮助您识别您可能想要进一步调查的 Office 365 云环境中的活动。您还可能决定创建新策略或编辑现有策略基于您看到通知。例如，如果您看到管理员从奇怪位置登录时，您可能决定阻止来自特定位置登录到 Office 365 管理员的策略设置。
  
> [!TIP]
> 使您可以先管理最重要的类型，您可以筛选通知按**类别**或**严重性**。 
  
每个通知，查找到什么导致它以便您可以决定要采取什么操作。若要查看有关通知的详细信息并采取措施，如解决通知或挂起的用户帐户，请选择该通知可打开的详细信息页。在详细信息页上，您可以查看活动日志、 帐户和与此通知中，相关的用户，并执行如下操作：
  
- **消除**如果该通知误报，关闭它。您可以选择添加注释，说明为什么您消除的位置。 
    
- **解决警报**如果通过触发通知您知道活动不威胁，解决问题。您可以选择添加注释，说明您解析的原因。 
    
- **挂起**如果您怀疑未经授权的登录帐户，例如，某人时您认识的人登录从另一个国家/地区的项物理上位于本地 office，则可以[挂起帐户](suspend-or-restore-an-account-in-ocas.md)当您研究了什么事。 
    
## <a name="next-steps"></a>后续步骤

- [调查活动](investigate-an-activity-in-office-365-cas.md)
    
- [暂停或还原的用户帐户](suspend-or-restore-an-account-in-ocas.md)
    
- 查看受支持的[Web 流量日志和数据源](web-traffic-logs-and-data-sources-for-ocas.md)的列表
    
- 查看您[的 Office 365 云应用程序安全性的使用率活动](utilization-activities-for-ocas.md)
    

