---
title: Office 365 云应用安全中的活动策略和警报
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 2/26/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 367f25d3-10a0-4a91-bdae-70ebb7a79c98
description: 定义与 Office 365 云应用程序安全性设置通知以触发特定活动发生或过于频繁发生时的活动策略。通过设置以触发通知的策略，您可以通知有关和监视特定活动。
ms.openlocfilehash: 6f5039d09dea98de970ab4bd28e95a6cfad73db4
ms.sourcegitcommit: 9034809b6f308bedc3b8ddcca8242586b5c30f94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2019
ms.locfileid: "28015004"
---
# <a name="activity-policies-and-alerts-in-office-365-cloud-app-security"></a>Office 365 云应用安全中的活动策略和警报

Office 365 高级安全管理现在是 Office 365 云应用程序安全性。
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|使用率 ***|
|:-----|:-----|:-----|:-----|
|[启动评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |在这里 ！  <br/> [后续步骤](anomaly-detection-policies-in-ocas.md) <br/> |[开始利用](utilization-activities-for-ocas.md) <br/> |
   
与 Office 365 云应用程序安全性，高级的云管理策略触发特定的活动发生或过于频繁发生的通知。例如，假设用户尝试登录到 Office 365，并在一分钟内 70 时间失败。假设另一个用户下载 7,000 文件，或显示为从加拿大时登录该用户应该位于另一个位置。或糟糕的是，假设已泄露某人的帐户，攻击者在使用该帐户访问您组织的云应用程序和敏感数据。
  
如果您是[全局管理员或安全管理员](permissions-in-the-security-and-compliance-center.md)，活动警报通知您事件，如这些时出现。您然后可以执行特定操作，如挂起的用户帐户，直到您可以调查发生了什么变化。
  
> [!NOTE]
> Office 365 云应用程序安全性策略是不同[警报策略在 Office 365 安全性&amp;合规性中心](alert-policies.md)。本文中所述的策略在 Office 365 云应用程序安全性门户中，定义和可帮助您更好的活动管理组织的云环境。 
  
## <a name="before-you-begin"></a>准备工作

请确保：
  
- 您的组织具有[Office 365 云应用程序安全性](office-365-cas-overview.md)，并且该服务[开启](turn-on-office-365-cas.md)。
    
- [审核日志记录](turn-audit-log-search-on-or-off.md)处于打开状态的 Office 365 环境。 
    
- 您是全局管理员或 Office 365 安全管理员。
    
## <a name="create-a-new-activity-policy"></a>创建新的活动策略

1. 以全局管理员或 security 管理员程序中，转到[https://protection.office.com](https://protection.office.com)和使用工作或学校帐户登录。 
    
2. 安全中&amp;合规性中心中，选择**警报** \> **管理高级通知**。
    
3. 选择**转到 Office 365 云应用程序安全性**。
    
    您将转到 Office 365 云应用程序安全策略页。
    
    ![当您转到 Office 365 云应用程序安全性门户时，启动与策略页](media/5cb8833c-4e08-438c-bab3-91b5106f6f3f.png)
  
4. 单击**创建策略**，，然后选择**活动策略**。
    
    ![在 O365 CAS 创建策略时，您可以选择活动策略和异常检测策略。](media/79f34535-ddf9-4a5b-a0a3-8766bf9c174c.png)
  
5. 在**创建活动策略**页中，指定**策略名称**和**说明**。若要在默认模板上基于您的策略，请在**策略模板**列表中，选择一个或不使用模板创建您自己的策略。 
    
    ![您可以与 Office 365 云应用程序安全性创建活动策略。](media/4083a76f-7074-4d6a-8200-6d76d49259d7.png)
  
6. 选择**策略严重性**（低、 中或高） 的度量如何严重其将您如果此策略会触发一条通知。这将帮助您筛选警报时正在查看其更高版本。 
    
7. 选择该策略的一个**类别**。这将帮助您筛选和排序的已触发通知或组策略时正在查看其进行更改。 
    
8. 选择**活动筛选器**设置其他操作或将触发通知基于此策略的指标。 
    
9. 下**活动匹配参数**，指定单个活动匹配筛选器时，将触发策略违规还是指定的数量的重复活动需要先触发警报。
    
    如果您选择**Repeated 活动**，请指定活动，时间段的数目和冲突的特定应用程序中的用户或任何应用程序的相同用户是否对计数。
    
10. （可选） 您可以选择要创建其他通知以接收通知 （通过电子邮件、 文本消息，或两者） 此策略中的**创建通知**。 
    
    > [!IMPORTANT]
    > 请确保您的电子邮件提供商不阻止从 no-reply@cloudappsecurity.com 发送的电子邮件。 
  
11. 选择触发挂起用户或需要用户再次登录到 Office 365 应用程序时应采取的**操作**。 
    
12. 选择**创建**以完成创建您的策略。 
    
## <a name="next-steps"></a>后续步骤

- [异常检测策略](anomaly-detection-policies-in-ocas.md)
    
- [将 SIEM 服务器集成](integrate-your-siem-server-with-office-365-cas.md)
    
- [查看并通知对其执行操作](review-office-365-cas-alerts.md)
    
- [若要简化管理您 IP 地址进行分组](group-your-ip-addresses-in-ocas.md)
    

