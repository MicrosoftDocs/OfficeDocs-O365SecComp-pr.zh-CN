---
title: 使用 Office 365 云应用安全创建应用发现报告
ms.author: deniseb
author: denisebmsft
manager: laurawi
ms.date: 1/28/2019
ms.audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3e68e691-1fc4-4d3e-a2c0-d3134eb64055
description: 创建具有 office 365 云应用安全性的报告, 使您能够了解组织中的人员如何使用 office 365 和其他应用程序。
ms.openlocfilehash: 23165a52a09e5bcde46ee3ab2110dc17d0faf7f4
ms.sourcegitcommit: f57b4001ef1327f0ea622e716a4d7d78f1769b49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/23/2019
ms.locfileid: "30220292"
---
# <a name="create-app-discovery-reports-using-office-365-cloud-app-security"></a>使用 Office 365 云应用安全创建应用发现报告

|评估 * *\>**|规划 * *\>**|部署 * *\>**|利用率 * * * *|
|:-----|:-----|:-----|:-----|
|[开始评估](office-365-cas-overview.md) <br/> |[开始规划](get-ready-for-office-365-cas.md) <br/> |[开始部署](turn-on-office-365-cas.md) <br/> |你在这里!  <br/> [后续步骤](#next-steps) <br/> |
   
Office 365 云应用安全帮助全局管理员、安全管理员和安全读者深入了解组织中的云服务人员正在使用。例如, 您可以查看用户在何处存储和协作处理文档, 以及将多少数据上载到 Office 365 之外的应用或服务。
  
若要生成应用发现报告, 请从防火墙和代理手动上载 web 流量日志文件, 然后 Office 365 云应用安全性分析并分析这些文件中的报告。
  
> [!NOTE]
> 您必须是全局管理员、安全管理员或安全读者才能执行本文中所述的任务。若要了解详细信息, 请参阅[Office 365 安全&amp;合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。 
  
## <a name="create-a-report-with-app-discovery"></a>创建包含应用程序发现的报告

若要创建应用发现报告, 请确定要分析的日志文件的供应商数据源, 选择日志文件, 然后请求报告。
  
> [!NOTE]
> 使用包含峰值流量周期的 web 流量日志文件, 以获取组织中的使用情况的最佳表示。 
  
1. 收集[适用于 Office 365 云应用安全的 web 流量日志和数据源](web-traffic-logs-and-data-sources-for-ocas.md)。
    
2. 转到云应用安全门户 ([https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)) 并登录。 
       
3. 选择 "**发现** \> **创建新报告**"。 <br>![在 Office 365 CAS 门户中, 选择 "发现"](media/73b5299f-94b5-49dd-a00f-154d188eb2c5.png)<br>
  
4. 为报表指定名称和说明, 然后在 "**数据源**" 列表中选择 web 流量日志的数据源。 <br>![在 O365 CAS 中, 选择\> "发现创建新报告"](media/22e660f0-5eb2-49fa-9fea-f88a5809a07b.png)<br>如果未列出您想要使用的数据源, 则可以请求添加该数据源。选择 "**其他**" 作为 "**数据源**", 然后键入要尝试上载的数据源的名称。我们将查看日志, 并告知我们是否为生成它的数据源添加支持。 
  
5. 浏览到您收集的日志文件的位置, 并选择这些文件。日志文件必须由您为报告选择的数据源生成。
    
6. 单击 "**创建**" 以启动报告创建过程。 
    
7. 若要查看报告的状态, 请单击 "**管理快照报告**"。报告准备就绪后, 您将看到 "**查看报告**" 选项。 
    
## <a name="next-steps"></a>后续步骤

- [查看警报并对其执行操作](review-office-365-cas-alerts.md)
    
- [查看 Office 365 云应用安全中的应用发现结果](review-app-discovery-findings-in-ocas.md)
    
- 查看[Office 365 云应用安全性的利用率活动](utilization-activities-for-ocas.md)
    

