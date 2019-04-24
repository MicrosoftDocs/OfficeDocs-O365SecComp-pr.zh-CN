---
title: 启用 Office 365 云应用安全
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
ms.assetid: ba919c73-d021-404d-9850-eec57e78678c
description: 阅读本文, 了解如何在 Microsoft Azure 中启用 Office 365 云应用安全性 (受云应用安全性的支持)。
ms.openlocfilehash: 1227545b1e4d1521dc1820342f09aabdf16ec2c6
ms.sourcegitcommit: 0017dc6a5f81c165d9dfd88be39a6bb17856582e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32264124"
---
# <a name="turn-on-office-365-cloud-app-security"></a>启用 Office 365 云应用安全
  
|评估 * *\>**|规划 * *\>**|部署 * *\>**|利用率 * * * *|
|:-----|:-----|:-----|:-----|
|[开始评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |你在这里!  <br/> [后续步骤](activity-policies-and-alerts.md) <br/> |[开始利用](utilization-activities-for-ocas.md) <br/> |
  
## <a name="turn-on-office-365-cloud-app-security"></a>启用 Office 365 云应用安全

> [!IMPORTANT]
> 您必须是全局管理员或安全管理员才能执行以下任务。 若要了解详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。 为了使 office 365 云应用安全正常工作, 必须为你的 Office 365 环境**启用审核日志记录**。 有关详细信息, 请参阅[打开或关闭 Office 365 审核日志搜索](turn-audit-log-search-on-or-off.md)。 
  
1. 作为全局管理员或安全管理员, 请转到[https://protection.office.com](https://security.microsoft.com)并使用 Office 365 的工作或学校帐户登录并登录。 (这会将您带到&amp;安全合规中心。) 
    
2. 转到 "**通知** \> " "**管理高级警报**"。
    
3. 选择 **"启用 Office 365 云应用安全"**。
    
4. 选择 "**转到 Office 365 云应用安全性**"。<br/>![在 "安全&amp;合规性中心" 中, 选择 "管理高级警报" 以转到 Office 365 云应用安全](media/958632d4-03e3-4ade-8e22-d5509db6fca7.png)<br/>这将转到 Office 365 云应用安全门户, 在其中可以查看报告以及创建或编辑策略。

在您启用 Office 365 云应用安全性之后, 可以通过访问[https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)并登录来转到云应用安全门户。
    
> [!NOTE]
> 打开 office 365 云应用安全性时, 将会将有关 Office 365 用户帐户和用户活动的审核信息转移到[Microsoft 云应用安全性](https://aka.ms/whatiscas)。 这将允许 Office 365 提供高级警报、筛选和其他功能, 以便你可以获取信息并采取有关可疑活动的操作。 
  
## <a name="next-steps"></a>后续步骤

- [活动策略](activity-policies-and-alerts.md)
    
- [异常情况检测策略](anomaly-detection-policies-in-ocas.md)
    
- [集成您的 SIEM 服务器](integrate-your-siem-server-with-office-365-cas.md)
    
- [将 IP 地址分组以简化管理](group-your-ip-addresses-in-ocas.md)
    

